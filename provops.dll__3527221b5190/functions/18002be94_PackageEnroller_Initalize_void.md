# PackageEnroller::Initalize(void)

- ea: `0x18002be94`
- end: `0x18002c03a`
- name: `?Initalize@PackageEnroller@@AEAAXXZ`
- size: `422`
- prototype: `void __fastcall(PackageEnroller *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bddc`

## callees

- `0x18001434c`
- `0x18001b388`
- `0x18001b3a8`
- `0x1800210f0`
- `0x18002be94`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bed7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002beea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002beea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002bf35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002bf35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bee2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bf7b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002bf7b`

## pseudocode

```c
void __fastcall PackageEnroller::Initalize(PackageEnroller *this)
{
  HKEY *phkResult; // rsi
  HKEY v3; // rbp
  DWORD LastError; // ebx
  bool IsStateSeparationEnabled; // al
  const WCHAR *v6; // rdx
  unsigned int Key; // eax
  const WCHAR *v8; // r8
  unsigned int ValueW; // eax
  unsigned __int64 v10; // r8
  int dwOptions; // [rsp+20h] [rbp-B8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-B8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-B8h]
  DWORD pcbData[4]; // [rsp+50h] [rbp-88h] BYREF
  _WORD pvData[40]; // [rsp+60h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( !*((_QWORD *)this + 4) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      (const char *)0x80070057LL,
      dwOptions);
  phkResult = (HKEY *)((char *)this + 8);
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
  {
    LastError = GetLastError();
    RegCloseKey(v3);
    SetLastError(LastError);
  }
  *phkResult = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v6 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Enrollments";
  if ( !IsStateSeparationEnabled )
    v6 = L"SOFTWARE\\Microsoft\\Provisioning\\Enrollments";
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0, 0, 3u, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      (const char *)Key,
      dwOptionsa);
  v8 = (const WCHAR *)((char *)this + 16);
  pcbData[0] = 78;
  if ( *((_QWORD *)this + 5) >= 8u )
    v8 = *(const WCHAR **)v8;
  ValueW = RegGetValueW(*phkResult, 0, v8, 2u, 0, pvData, pcbData);
  if ( ValueW != 2 )
  {
    if ( ValueW )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
        (const char *)ValueW,
        dwOptionsb);
    if ( pvData[0] )
    {
      v10 = -1;
      do
        ++v10;
      while ( pvData[v10] );
    }
    else
    {
      v10 = 0;
    }
    std::wstring::assign((_QWORD *)this + 6, (char *)pvData, v10);
  }
}

```

## disassembly

```asm
0x18002be94  mov     [rsp+arg_8], rbx
0x18002be99  mov     [rsp+arg_10], rbp
0x18002be9e  push    rsi
0x18002be9f  push    rdi
0x18002bea0  push    r14
0x18002bea2  sub     rsp, 0C0h
0x18002bea9  mov     rax, cs:__security_cookie
0x18002beb0  xor     rax, rsp
0x18002beb3  mov     [rsp+0D8h+var_28], rax
0x18002bebb  xor     r14d, r14d
0x18002bebe  mov     rdi, rcx
0x18002bec1  cmp     [rcx+20h], r14
0x18002bec5  jz      loc_18002BFFD
0x18002becb  lea     rsi, [rcx+8]
0x18002becf  mov     rbp, [rsi]
0x18002bed2  test    rbp, rbp
0x18002bed5  jz      short loc_18002BEF0
0x18002bed7  call    cs:__imp_GetLastError
0x18002bedd  mov     rcx, rbp; hKey
0x18002bee0  mov     ebx, eax
0x18002bee2  call    cs:__imp_RegCloseKey
0x18002bee8  mov     ecx, ebx; dwErrCode
0x18002beea  call    cs:__imp_SetLastError
0x18002bef0  mov     [rsi], r14
0x18002bef3  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x18002bef8  mov     [rsp+0D8h+lpdwDisposition], r14; lpdwDisposition
0x18002befd  lea     rcx, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Provisioning\\Enro"...
0x18002bf04  mov     [rsp+0D8h+phkResult], rsi; phkResult
0x18002bf09  lea     rdx, aOsdataSoftware_2; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18002bf10  test    al, al
0x18002bf12  mov     [rsp+0D8h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002bf17  mov     [rsp+0D8h+samDesired], 3; samDesired
0x18002bf1f  cmovz   rdx, rcx; lpSubKey
0x18002bf23  mov     [rsp+0D8h+dwOptions], r14d; unsigned int
0x18002bf28  xor     r9d, r9d; lpClass
0x18002bf2b  xor     r8d, r8d; Reserved
0x18002bf2e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bf35  call    cs:__imp_RegCreateKeyExW
0x18002bf3b  test    eax, eax
0x18002bf3d  jnz     loc_18002C01D
0x18002bf43  lea     r8, [rdi+10h]
0x18002bf47  mov     [rsp+0D8h+pcbData], 4Eh ; 'N'
0x18002bf4f  cmp     qword ptr [r8+18h], 8
0x18002bf54  jb      short loc_18002BF59
0x18002bf56  mov     r8, [r8]; lpValue
0x18002bf59  mov     rcx, [rsi]; hkey
0x18002bf5c  lea     rax, [rsp+0D8h+pcbData]
0x18002bf61  mov     [rsp+0D8h+lpSecurityAttributes], rax; pcbData
0x18002bf66  xor     edx, edx; lpSubKey
0x18002bf68  lea     rax, [rsp+0D8h+pvData]
0x18002bf6d  mov     qword ptr [rsp+0D8h+samDesired], rax; pvData
0x18002bf72  mov     qword ptr [rsp+0D8h+dwOptions], r14; unsigned int
0x18002bf77  lea     r9d, [rdx+2]; dwFlags
0x18002bf7b  call    cs:__imp_RegGetValueW
0x18002bf81  cmp     eax, 2
0x18002bf84  jz      short loc_18002BFB8
0x18002bf86  test    eax, eax
0x18002bf88  jnz     short loc_18002BFE0
0x18002bf8a  cmp     [rsp+0D8h+pvData], r14w
0x18002bf90  jnz     short loc_18002BF97
0x18002bf92  mov     r8, r14
0x18002bf95  jmp     short loc_18002BFAA
0x18002bf97  lea     rax, [rsp+0D8h+pvData]
0x18002bf9c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002bfa0  inc     r8
0x18002bfa3  cmp     [rax+r8*2], r14w
0x18002bfa8  jnz     short loc_18002BFA0
0x18002bfaa  lea     rcx, [rdi+30h]; void *
0x18002bfae  lea     rdx, [rsp+0D8h+pvData]; Src
0x18002bfb3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002bfb8  mov     rcx, [rsp+0D8h+var_28]
0x18002bfc0  xor     rcx, rsp; StackCookie
0x18002bfc3  call    __security_check_cookie
0x18002bfc8  lea     r11, [rsp+0D8h+var_18]
0x18002bfd0  mov     rbx, [r11+28h]
0x18002bfd4  mov     rbp, [r11+30h]
0x18002bfd8  mov     rsp, r11
0x18002bfdb  pop     r14
0x18002bfdd  pop     rdi
0x18002bfde  pop     rsi
0x18002bfdf  retn
0x18002bfe0  mov     rcx, [rsp+0D8h]; this
0x18002bfe8  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18002bfef  mov     r9d, eax; char *
0x18002bff2  mov     edx, 2Ah ; '*'; void *
0x18002bff7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002bffd  mov     rcx, [rsp+0D8h]; this
0x18002c005  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18002c00c  mov     r9d, 80070057h; char *
0x18002c012  mov     edx, 1Ch; void *
0x18002c017  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c01d  mov     rcx, [rsp+0D8h]; this
0x18002c025  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18002c02c  mov     r9d, eax; char *
0x18002c02f  mov     edx, 21h ; '!'; void *
0x18002c034  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
