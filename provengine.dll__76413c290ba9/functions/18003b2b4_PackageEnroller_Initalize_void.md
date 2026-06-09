# PackageEnroller::Initalize(void)

- ea: `0x18003b2b4`
- end: `0x18003b45a`
- name: `?Initalize@PackageEnroller@@AEAAXXZ`
- size: `422`
- prototype: `void __fastcall(PackageEnroller *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035fb0`

## callees

- `0x1800092dc`
- `0x18000b030`
- `0x180021cf4`
- `0x18002f9bc`
- `0x18003b2b4`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003b39b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003b39b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b302`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b302`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b355`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b355`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b30a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b30a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b2f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b2f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x21,
      (int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
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
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2A,
        (int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
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
0x18003b2b4  mov     [rsp+arg_8], rbx
0x18003b2b9  mov     [rsp+arg_10], rbp
0x18003b2be  push    rsi
0x18003b2bf  push    rdi
0x18003b2c0  push    r14
0x18003b2c2  sub     rsp, 0C0h
0x18003b2c9  mov     rax, cs:__security_cookie
0x18003b2d0  xor     rax, rsp
0x18003b2d3  mov     [rsp+0D8h+var_28], rax
0x18003b2db  xor     r14d, r14d
0x18003b2de  mov     rdi, rcx
0x18003b2e1  cmp     [rcx+20h], r14
0x18003b2e5  jz      loc_18003B41D
0x18003b2eb  lea     rsi, [rcx+8]
0x18003b2ef  mov     rbp, [rsi]
0x18003b2f2  test    rbp, rbp
0x18003b2f5  jz      short loc_18003B310
0x18003b2f7  call    cs:__imp_GetLastError
0x18003b2fd  mov     rcx, rbp; hKey
0x18003b300  mov     ebx, eax
0x18003b302  call    cs:__imp_RegCloseKey
0x18003b308  mov     ecx, ebx; dwErrCode
0x18003b30a  call    cs:__imp_SetLastError
0x18003b310  mov     [rsi], r14
0x18003b313  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x18003b318  mov     [rsp+0D8h+lpdwDisposition], r14; lpdwDisposition
0x18003b31d  lea     rcx, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Provisioning\\Enro"...
0x18003b324  mov     [rsp+0D8h+phkResult], rsi; phkResult
0x18003b329  lea     rdx, aOsdataSoftware_3; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18003b330  test    al, al
0x18003b332  mov     [rsp+0D8h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003b337  mov     [rsp+0D8h+samDesired], 3; samDesired
0x18003b33f  cmovz   rdx, rcx; lpSubKey
0x18003b343  mov     [rsp+0D8h+dwOptions], r14d; unsigned int
0x18003b348  xor     r9d, r9d; lpClass
0x18003b34b  xor     r8d, r8d; Reserved
0x18003b34e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b355  call    cs:__imp_RegCreateKeyExW
0x18003b35b  test    eax, eax
0x18003b35d  jnz     loc_18003B43D
0x18003b363  lea     r8, [rdi+10h]
0x18003b367  mov     [rsp+0D8h+pcbData], 4Eh ; 'N'
0x18003b36f  cmp     qword ptr [r8+18h], 8
0x18003b374  jb      short loc_18003B379
0x18003b376  mov     r8, [r8]; lpValue
0x18003b379  mov     rcx, [rsi]; hkey
0x18003b37c  lea     rax, [rsp+0D8h+pcbData]
0x18003b381  mov     [rsp+0D8h+lpSecurityAttributes], rax; pcbData
0x18003b386  xor     edx, edx; lpSubKey
0x18003b388  lea     rax, [rsp+0D8h+pvData]
0x18003b38d  mov     qword ptr [rsp+0D8h+samDesired], rax; pvData
0x18003b392  mov     qword ptr [rsp+0D8h+dwOptions], r14; unsigned int
0x18003b397  lea     r9d, [rdx+2]; dwFlags
0x18003b39b  call    cs:__imp_RegGetValueW
0x18003b3a1  cmp     eax, 2
0x18003b3a4  jz      short loc_18003B3D8
0x18003b3a6  test    eax, eax
0x18003b3a8  jnz     short loc_18003B400
0x18003b3aa  cmp     [rsp+0D8h+pvData], r14w
0x18003b3b0  jnz     short loc_18003B3B7
0x18003b3b2  mov     r8, r14
0x18003b3b5  jmp     short loc_18003B3CA
0x18003b3b7  lea     rax, [rsp+0D8h+pvData]
0x18003b3bc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b3c0  inc     r8
0x18003b3c3  cmp     [rax+r8*2], r14w
0x18003b3c8  jnz     short loc_18003B3C0
0x18003b3ca  lea     rcx, [rdi+30h]; void *
0x18003b3ce  lea     rdx, [rsp+0D8h+pvData]; Src
0x18003b3d3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003b3d8  mov     rcx, [rsp+0D8h+var_28]
0x18003b3e0  xor     rcx, rsp; StackCookie
0x18003b3e3  call    __security_check_cookie
0x18003b3e8  lea     r11, [rsp+0D8h+var_18]
0x18003b3f0  mov     rbx, [r11+28h]
0x18003b3f4  mov     rbp, [r11+30h]
0x18003b3f8  mov     rsp, r11
0x18003b3fb  pop     r14
0x18003b3fd  pop     rdi
0x18003b3fe  pop     rsi
0x18003b3ff  retn
0x18003b400  mov     rcx, [rsp+0D8h]; this
0x18003b408  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18003b40f  mov     r9d, eax; char *
0x18003b412  mov     edx, 2Ah ; '*'; void *
0x18003b417  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003b41d  mov     rcx, [rsp+0D8h]; this
0x18003b425  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18003b42c  mov     r9d, 80070057h; char *
0x18003b432  mov     edx, 1Ch; void *
0x18003b437  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b43d  mov     rcx, [rsp+0D8h]; this
0x18003b445  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18003b44c  mov     r9d, eax; char *
0x18003b44f  mov     edx, 21h ; '!'; void *
0x18003b454  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
