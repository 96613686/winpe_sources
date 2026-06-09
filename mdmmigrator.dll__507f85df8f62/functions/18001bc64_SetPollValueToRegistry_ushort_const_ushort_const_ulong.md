# SetPollValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x18001bc64`
- end: `0x18001bdb0`
- name: `?SetPollValueToRegistry@@YAJPEBG0K@Z`
- size: `332`
- prototype: `LSTATUS __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c054`

## callees

- `0x1800022e0`
- `0x180006bd4`
- `0x18001bc64`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18001bc94`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001bc94`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bd80`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bd80`

## pseudocode

```c
LSTATUS __fastcall SetPollValueToRegistry(const unsigned __int16 *a1, LPCWSTR lpValueName, int a3)
{
  __int64 v5; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // rdx
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rdx
  LSTATUS result; // eax
  _DWORD Data[4]; // [rsp+30h] [rbp-F8h] BYREF
  WCHAR SubKey[88]; // [rsp+40h] [rbp-E8h] BYREF

  Data[0] = a3;
  v5 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, lpValueName);
  v7 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v7 = &dword_18002237C;
  v8 = SubKey;
  v9 = 85;
  do
  {
    if ( !v5 )
      break;
    if ( !*v7 )
      break;
    *v8++ = *v7++;
    --v5;
    --v9;
  }
  while ( v9 );
  v10 = v8 - 1;
  result = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v10 = v8;
  *v10 = 0;
  if ( v9 )
  {
    result = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDB);
    if ( result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x55u, a1);
      if ( result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x55u, L"\\");
        if ( result >= 0 )
        {
          result = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDBPoll);
          if ( result >= 0 )
          {
            result = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, lpValueName, 4u, Data, 4u);
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
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
0x18001bc64  push    rbx
0x18001bc66  push    rbp
0x18001bc67  push    rsi
0x18001bc68  push    rdi
0x18001bc69  push    r14
0x18001bc6b  sub     rsp, 100h
0x18001bc72  mov     rax, cs:__security_cookie
0x18001bc79  xor     rax, rsp
0x18001bc7c  mov     [rsp+128h+var_38], rax
0x18001bc84  mov     rsi, rdx
0x18001bc87  mov     [rsp+128h+Data], r8d
0x18001bc8c  mov     rdi, rcx
0x18001bc8f  mov     ebx, 7FFFFFFEh
0x18001bc94  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001bc9a  xor     ebp, ebp
0x18001bc9c  lea     rcx, dword_18002237C
0x18001bca3  test    al, al
0x18001bca5  lea     rdx, aOsdata; "OSData\\"
0x18001bcac  cmovz   rdx, rcx
0x18001bcb0  lea     rcx, [rsp+128h+SubKey]
0x18001bcb5  lea     r14d, [rbp+55h]
0x18001bcb9  mov     r8d, r14d
0x18001bcbc  test    rbx, rbx
0x18001bcbf  jz      short loc_18001BCDD
0x18001bcc1  movzx   eax, word ptr [rdx]
0x18001bcc4  test    ax, ax
0x18001bcc7  jz      short loc_18001BCDD
0x18001bcc9  mov     [rcx], ax
0x18001bccc  add     rdx, 2
0x18001bcd0  add     rcx, 2
0x18001bcd4  dec     rbx
0x18001bcd7  sub     r8, 1
0x18001bcdb  jnz     short loc_18001BCBC
0x18001bcdd  mov     rax, r8
0x18001bce0  lea     rdx, [rcx-2]
0x18001bce4  neg     rax
0x18001bce7  sbb     eax, eax
0x18001bce9  not     eax
0x18001bceb  and     eax, 8007007Ah
0x18001bcf0  test    r8, r8
0x18001bcf3  cmovnz  rdx, rcx
0x18001bcf7  mov     [rdx], bp
0x18001bcfa  jz      loc_18001BD92
0x18001bd00  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x18001bd07  mov     rdx, r14; unsigned __int64
0x18001bd0a  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18001bd0f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bd14  test    eax, eax
0x18001bd16  js      short loc_18001BD92
0x18001bd18  mov     r8, rdi; unsigned __int16 *
0x18001bd1b  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18001bd20  mov     rdx, r14; unsigned __int64
0x18001bd23  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bd28  test    eax, eax
0x18001bd2a  js      short loc_18001BD92
0x18001bd2c  lea     r8, asc_180021D44; "\\"
0x18001bd33  mov     rdx, r14; unsigned __int64
0x18001bd36  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18001bd3b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bd40  test    eax, eax
0x18001bd42  js      short loc_18001BD92
0x18001bd44  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x18001bd4b  mov     rdx, r14; unsigned __int64
0x18001bd4e  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18001bd53  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bd58  test    eax, eax
0x18001bd5a  js      short loc_18001BD92
0x18001bd5c  mov     r9d, 4; dwType
0x18001bd62  lea     rax, [rsp+128h+Data]
0x18001bd67  mov     [rsp+128h+cbData], r9d; cbData
0x18001bd6c  lea     rdx, [rsp+128h+SubKey]; lpSubKey
0x18001bd71  mov     r8, rsi; lpValueName
0x18001bd74  mov     [rsp+128h+lpData], rax; lpData
0x18001bd79  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bd80  call    cs:__imp_RegSetKeyValueW
0x18001bd86  test    eax, eax
0x18001bd88  jle     short loc_18001BD92
0x18001bd8a  movzx   eax, ax
0x18001bd8d  or      eax, 80070000h
0x18001bd92  mov     rcx, [rsp+128h+var_38]
0x18001bd9a  xor     rcx, rsp; StackCookie
0x18001bd9d  call    __security_check_cookie
0x18001bda2  add     rsp, 100h
0x18001bda9  pop     r14
0x18001bdab  pop     rdi
0x18001bdac  pop     rsi
0x18001bdad  pop     rbp
0x18001bdae  pop     rbx
0x18001bdaf  retn
```
