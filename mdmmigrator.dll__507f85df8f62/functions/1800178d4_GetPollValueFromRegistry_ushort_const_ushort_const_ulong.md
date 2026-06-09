# GetPollValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x1800178d4`
- end: `0x180017a6e`
- name: `?GetPollValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `410`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c054`

## callees

- `0x1800022e0`
- `0x180006bd4`
- `0x1800178d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017a33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017a33`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180017931`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180017931`

## pseudocode

```c
__int64 __fastcall GetPollValueFromRegistry(const unsigned __int16 *a1, LPCWSTR lpValue, unsigned int *a3)
{
  LSTATUS ValueW; // ecx
  __int64 v7; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v9; // rdx
  WCHAR *v10; // rcx
  __int64 v11; // r8
  WCHAR *v12; // rdx
  __int64 result; // rax
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[88]; // [rsp+50h] [rbp-B0h] BYREF

  pcbData = 4;
  pdwType = 0;
  pvData = 0;
  ValueW = 0;
  if ( !lpValue || !a3 )
    return (unsigned int)ValueW;
  v7 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(0, lpValue);
  v9 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v9 = &dword_18002237C;
  v10 = SubKey;
  v11 = 85;
  do
  {
    if ( !v7 )
      break;
    if ( !*v9 )
      break;
    *v10++ = *v9++;
    --v7;
    --v11;
  }
  while ( v11 );
  v12 = v10 - 1;
  result = v11 == 0 ? 0x8007007A : 0;
  if ( v11 )
    v12 = v10;
  *v12 = 0;
  if ( v11 )
  {
    result = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDB);
    if ( (int)result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x55u, a1);
      if ( (int)result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x55u, L"\\");
        if ( (int)result >= 0 )
        {
          result = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDBPoll);
          if ( (int)result >= 0 )
          {
            ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, lpValue, 0x10u, &pdwType, &pvData, &pcbData);
            *a3 = pvData;
            if ( ValueW > 0 )
              return (unsigned __int16)ValueW | 0x80070000;
            return (unsigned int)ValueW;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800178d4  push    rbp
0x1800178d6  push    rbx
0x1800178d7  push    rsi
0x1800178d8  push    rdi
0x1800178d9  push    r12
0x1800178db  push    r14
0x1800178dd  push    r15
0x1800178df  lea     rbp, [rsp-10h]
0x1800178e4  sub     rsp, 110h
0x1800178eb  mov     rax, cs:__security_cookie
0x1800178f2  xor     rax, rsp
0x1800178f5  mov     [rbp+40h+var_40], rax
0x1800178f9  xor     r15d, r15d
0x1800178fc  mov     [rsp+140h+var_FC], 4
0x180017904  mov     [rsp+140h+var_F8], r15d
0x180017909  mov     r14, rcx
0x18001790c  mov     [rsp+140h+var_100], r15d
0x180017911  mov     rdi, r8
0x180017914  mov     rsi, rdx
0x180017917  mov     ecx, r15d
0x18001791a  test    rdx, rdx
0x18001791d  jz      loc_180017A4E
0x180017923  test    r8, r8
0x180017926  jz      loc_180017A4E
0x18001792c  mov     ebx, 7FFFFFFEh
0x180017931  call    cs:__imp_RtlIsStateSeparationEnabled
0x180017937  lea     rcx, dword_18002237C
0x18001793e  test    al, al
0x180017940  lea     rdx, aOsdata; "OSData\\"
0x180017947  lea     r12d, [r15+55h]
0x18001794b  cmovz   rdx, rcx
0x18001794f  lea     rcx, [rsp+140h+SubKey]
0x180017954  mov     r8d, r12d
0x180017957  test    rbx, rbx
0x18001795a  jz      short loc_180017978
0x18001795c  movzx   eax, word ptr [rdx]
0x18001795f  test    ax, ax
0x180017962  jz      short loc_180017978
0x180017964  mov     [rcx], ax
0x180017967  add     rdx, 2
0x18001796b  add     rcx, 2
0x18001796f  dec     rbx
0x180017972  sub     r8, 1
0x180017976  jnz     short loc_180017957
0x180017978  mov     rax, r8
0x18001797b  lea     rdx, [rcx-2]
0x18001797f  neg     rax
0x180017982  sbb     eax, eax
0x180017984  not     eax
0x180017986  and     eax, 8007007Ah
0x18001798b  test    r8, r8
0x18001798e  cmovnz  rdx, rcx
0x180017992  mov     [rdx], r15w
0x180017996  jz      loc_180017A50
0x18001799c  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x1800179a3  mov     rdx, r12; unsigned __int64
0x1800179a6  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x1800179ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800179b0  test    eax, eax
0x1800179b2  js      loc_180017A50
0x1800179b8  mov     r8, r14; unsigned __int16 *
0x1800179bb  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x1800179c0  mov     rdx, r12; unsigned __int64
0x1800179c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800179c8  test    eax, eax
0x1800179ca  js      loc_180017A50
0x1800179d0  lea     r8, asc_180021D44; "\\"
0x1800179d7  mov     rdx, r12; unsigned __int64
0x1800179da  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x1800179df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800179e4  test    eax, eax
0x1800179e6  js      short loc_180017A50
0x1800179e8  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x1800179ef  mov     rdx, r12; unsigned __int64
0x1800179f2  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x1800179f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800179fc  test    eax, eax
0x1800179fe  js      short loc_180017A50
0x180017a00  lea     rax, [rsp+140h+var_FC]
0x180017a05  mov     r9d, 10h; dwFlags
0x180017a0b  mov     [rsp+140h+pcbData], rax; pcbData
0x180017a10  lea     rdx, [rsp+140h+SubKey]; lpSubKey
0x180017a15  lea     rax, [rsp+140h+var_100]
0x180017a1a  mov     r8, rsi; lpValue
0x180017a1d  mov     [rsp+140h+pvData], rax; pvData
0x180017a22  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180017a29  lea     rax, [rsp+140h+var_F8]
0x180017a2e  mov     [rsp+140h+pdwType], rax; pdwType
0x180017a33  call    cs:__imp_RegGetValueW
0x180017a39  mov     ecx, eax
0x180017a3b  mov     eax, [rsp+140h+var_100]
0x180017a3f  mov     [rdi], eax
0x180017a41  test    ecx, ecx
0x180017a43  jle     short loc_180017A4E
0x180017a45  movzx   ecx, cx
0x180017a48  or      ecx, 80070000h
0x180017a4e  mov     eax, ecx
0x180017a50  mov     rcx, [rbp+40h+var_40]
0x180017a54  xor     rcx, rsp; StackCookie
0x180017a57  call    __security_check_cookie
0x180017a5c  add     rsp, 110h
0x180017a63  pop     r15
0x180017a65  pop     r14
0x180017a67  pop     r12
0x180017a69  pop     rdi
0x180017a6a  pop     rsi
0x180017a6b  pop     rbx
0x180017a6c  pop     rbp
0x180017a6d  retn
```
