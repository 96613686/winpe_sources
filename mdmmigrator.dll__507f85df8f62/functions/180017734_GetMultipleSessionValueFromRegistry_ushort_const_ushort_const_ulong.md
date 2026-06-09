# GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x180017734`
- end: `0x1800178ce`
- name: `?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z`
- size: `410`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValue, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c61c`

## callees

- `0x1800022e0`
- `0x180006bd4`
- `0x180017734`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017893`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017893`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180017791`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180017791`

## pseudocode

```c
__int64 __fastcall GetMultipleSessionValueFromRegistry(const unsigned __int16 *a1, LPCWSTR lpValue, unsigned int *a3)
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
  WCHAR SubKey[96]; // [rsp+50h] [rbp-B0h] BYREF

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
  v11 = 96;
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
    result = StringCchCatW(SubKey, 0x60u, c_szEnrollmentsDB);
    if ( (int)result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x60u, a1);
      if ( (int)result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x60u, L"\\");
        if ( (int)result >= 0 )
        {
          result = StringCchCatW(SubKey, 0x60u, c_szEnrollmentsDBMultipleSession);
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
0x180017734  push    rbp
0x180017736  push    rbx
0x180017737  push    rsi
0x180017738  push    rdi
0x180017739  push    r12
0x18001773b  push    r14
0x18001773d  push    r15
0x18001773f  lea     rbp, [rsp-20h]
0x180017744  sub     rsp, 120h
0x18001774b  mov     rax, cs:__security_cookie
0x180017752  xor     rax, rsp
0x180017755  mov     [rbp+50h+var_40], rax
0x180017759  xor     r15d, r15d
0x18001775c  mov     [rsp+150h+var_10C], 4
0x180017764  mov     [rsp+150h+var_108], r15d
0x180017769  mov     r14, rcx
0x18001776c  mov     [rsp+150h+var_110], r15d
0x180017771  mov     rdi, r8
0x180017774  mov     rsi, rdx
0x180017777  mov     ecx, r15d
0x18001777a  test    rdx, rdx
0x18001777d  jz      loc_1800178AE
0x180017783  test    r8, r8
0x180017786  jz      loc_1800178AE
0x18001778c  mov     ebx, 7FFFFFFEh
0x180017791  call    cs:__imp_RtlIsStateSeparationEnabled
0x180017797  lea     rcx, dword_18002237C
0x18001779e  test    al, al
0x1800177a0  lea     rdx, aOsdata; "OSData\\"
0x1800177a7  lea     r12d, [r15+60h]
0x1800177ab  cmovz   rdx, rcx
0x1800177af  lea     rcx, [rsp+150h+SubKey]
0x1800177b4  mov     r8d, r12d
0x1800177b7  test    rbx, rbx
0x1800177ba  jz      short loc_1800177D8
0x1800177bc  movzx   eax, word ptr [rdx]
0x1800177bf  test    ax, ax
0x1800177c2  jz      short loc_1800177D8
0x1800177c4  mov     [rcx], ax
0x1800177c7  add     rdx, 2
0x1800177cb  add     rcx, 2
0x1800177cf  dec     rbx
0x1800177d2  sub     r8, 1
0x1800177d6  jnz     short loc_1800177B7
0x1800177d8  mov     rax, r8
0x1800177db  lea     rdx, [rcx-2]
0x1800177df  neg     rax
0x1800177e2  sbb     eax, eax
0x1800177e4  not     eax
0x1800177e6  and     eax, 8007007Ah
0x1800177eb  test    r8, r8
0x1800177ee  cmovnz  rdx, rcx
0x1800177f2  mov     [rdx], r15w
0x1800177f6  jz      loc_1800178B0
0x1800177fc  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x180017803  mov     rdx, r12; unsigned __int64
0x180017806  lea     rcx, [rsp+150h+SubKey]; unsigned __int16 *
0x18001780b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017810  test    eax, eax
0x180017812  js      loc_1800178B0
0x180017818  mov     r8, r14; unsigned __int16 *
0x18001781b  lea     rcx, [rsp+150h+SubKey]; unsigned __int16 *
0x180017820  mov     rdx, r12; unsigned __int64
0x180017823  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017828  test    eax, eax
0x18001782a  js      loc_1800178B0
0x180017830  lea     r8, asc_180021D44; "\\"
0x180017837  mov     rdx, r12; unsigned __int64
0x18001783a  lea     rcx, [rsp+150h+SubKey]; unsigned __int16 *
0x18001783f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017844  test    eax, eax
0x180017846  js      short loc_1800178B0
0x180017848  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x18001784f  mov     rdx, r12; unsigned __int64
0x180017852  lea     rcx, [rsp+150h+SubKey]; unsigned __int16 *
0x180017857  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001785c  test    eax, eax
0x18001785e  js      short loc_1800178B0
0x180017860  lea     rax, [rsp+150h+var_10C]
0x180017865  mov     r9d, 10h; dwFlags
0x18001786b  mov     [rsp+150h+pcbData], rax; pcbData
0x180017870  lea     rdx, [rsp+150h+SubKey]; lpSubKey
0x180017875  lea     rax, [rsp+150h+var_110]
0x18001787a  mov     r8, rsi; lpValue
0x18001787d  mov     [rsp+150h+pvData], rax; pvData
0x180017882  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180017889  lea     rax, [rsp+150h+var_108]
0x18001788e  mov     [rsp+150h+pdwType], rax; pdwType
0x180017893  call    cs:__imp_RegGetValueW
0x180017899  mov     ecx, eax
0x18001789b  mov     eax, [rsp+150h+var_110]
0x18001789f  mov     [rdi], eax
0x1800178a1  test    ecx, ecx
0x1800178a3  jle     short loc_1800178AE
0x1800178a5  movzx   ecx, cx
0x1800178a8  or      ecx, 80070000h
0x1800178ae  mov     eax, ecx
0x1800178b0  mov     rcx, [rbp+50h+var_40]
0x1800178b4  xor     rcx, rsp; StackCookie
0x1800178b7  call    __security_check_cookie
0x1800178bc  add     rsp, 120h
0x1800178c3  pop     r15
0x1800178c5  pop     r14
0x1800178c7  pop     r12
0x1800178c9  pop     rdi
0x1800178ca  pop     rsi
0x1800178cb  pop     rbx
0x1800178cc  pop     rbp
0x1800178cd  retn
```
