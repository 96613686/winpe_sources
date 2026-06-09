# EnvGetString(ushort const *)

- ea: `0x180004ed0`
- end: `0x180004fda`
- name: `?EnvGetString@@YAPEAGPEBG@Z`
- size: `266`
- prototype: `unsigned __int16 *__fastcall(wchar_t *Source)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002f30`
- `0x180008f00`

## callees

- `0x180004d50`
- `0x180004ed0`
- `0x18000c1a8`
- `0x18000d614`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004f5f`
- `KERNEL32!GetLastError` at `0x180004fb0`
- `KERNEL32!GetLastError` at `0x180004f5f`
- `KERNEL32!GetLastError` at `0x180004fb0`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004f43`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004fcf`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004f43`
- `KERNEL32!GetEnvironmentVariableW` at `0x180004fcf`
- `KERNEL32!SetLastError` at `0x180004fbc`
- `KERNEL32!SetLastError` at `0x180004fbc`

## string_xrefs

- `0x180004f11`: `COMPlus_`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall EnvGetString(wchar_t *Source)
{
  unsigned __int64 v2; // rax
  signed int EnvironmentVariableW; // eax
  DWORD v4; // edi
  unsigned __int64 v5; // rbx
  DWORD LastError; // esi
  WCHAR *v7; // rbx
  wchar_t Destination[64]; // [rsp+30h] [rbp-98h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( Source[v2] );
  if ( v2 > 0x37 )
    return 0;
  wcscpy_s(Destination, 0x40u, L"COMPlus_");
  wcscat_s(Destination, 0x40u, Source);
  EnvironmentVariableW = GetEnvironmentVariableW(Destination, 0, 0);
  v4 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
    return 0;
  v5 = 2LL * EnvironmentVariableW;
  if ( !is_mul_ok(EnvironmentVariableW, 2u) )
    v5 = -1;
  LastError = GetLastError();
  v7 = (WCHAR *)ClrAllocInProcessHeapBootstrap(0, v5);
  if ( LastError )
  {
    if ( !GetLastError() )
      SetLastError(LastError);
  }
  if ( !v7 )
    return 0;
  GetEnvironmentVariableW(Destination, v7, v4);
  return v7;
}

```

## disassembly

```asm
0x180004ed0  mov     [rsp+arg_8], rbx
0x180004ed5  mov     [rsp+arg_10], rsi
0x180004eda  push    rdi
0x180004edb  sub     rsp, 0C0h
0x180004ee2  mov     rax, cs:__security_cookie
0x180004ee9  xor     rax, rsp
0x180004eec  mov     [rsp+0C8h+var_18], rax
0x180004ef4  mov     rbx, rcx
0x180004ef7  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180004efe  mov     rax, rsi
0x180004f01  inc     rax
0x180004f04  cmp     word ptr [rcx+rax*2], 0
0x180004f09  jnz     short loc_180004F01
0x180004f0b  cmp     rax, 37h ; '7'
0x180004f0f  ja      short loc_180004F89
0x180004f11  lea     r8, aComplus; "COMPlus_"
0x180004f18  mov     edx, 40h ; '@'; SizeInWords
0x180004f1d  lea     rcx, [rsp+0C8h+Destination]; Destination
0x180004f22  call    wcscpy_s
0x180004f27  mov     r8, rbx; Source
0x180004f2a  mov     edx, 40h ; '@'; SizeInWords
0x180004f2f  lea     rcx, [rsp+0C8h+Destination]; Destination
0x180004f34  call    wcscat_s
0x180004f39  xor     r8d, r8d; nSize
0x180004f3c  xor     edx, edx; lpBuffer
0x180004f3e  lea     rcx, [rsp+0C8h+Destination]; lpName
0x180004f43  call    cs:__imp_GetEnvironmentVariableW
0x180004f49  movsxd  rdi, eax
0x180004f4c  test    eax, eax
0x180004f4e  jz      short loc_180004F89
0x180004f50  mov     eax, 2
0x180004f55  mul     rdi
0x180004f58  mov     rbx, rax
0x180004f5b  cmovb   rbx, rsi
0x180004f5f  call    cs:__imp_GetLastError
0x180004f65  mov     esi, eax
0x180004f67  mov     [rsp+0C8h+var_A8], eax
0x180004f6b  mov     [rsp+0C8h+var_A4], 2
0x180004f73  mov     rdx, rbx; unsigned __int64
0x180004f76  xor     ecx, ecx; unsigned int
0x180004f78  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x180004f7d  mov     rbx, rax
0x180004f80  test    esi, esi
0x180004f82  jnz     short loc_180004FB0
0x180004f84  test    rbx, rbx
0x180004f87  jnz     short loc_180004FC4
0x180004f89  xor     eax, eax
0x180004f8b  mov     rcx, [rsp+0C8h+var_18]
0x180004f93  xor     rcx, rsp; StackCookie
0x180004f96  call    __security_check_cookie
0x180004f9b  lea     r11, [rsp+0C8h+var_8]
0x180004fa3  mov     rbx, [r11+18h]
0x180004fa7  mov     rsi, [r11+20h]
0x180004fab  mov     rsp, r11
0x180004fae  pop     rdi
0x180004faf  retn
0x180004fb0  call    cs:__imp_GetLastError
0x180004fb6  test    eax, eax
0x180004fb8  jnz     short loc_180004F84
0x180004fba  mov     ecx, esi; dwErrCode
0x180004fbc  call    cs:__imp_SetLastError
0x180004fc2  jmp     short loc_180004F84
0x180004fc4  mov     r8d, edi; nSize
0x180004fc7  mov     rdx, rbx; lpBuffer
0x180004fca  lea     rcx, [rsp+0C8h+Destination]; lpName
0x180004fcf  call    cs:__imp_GetEnvironmentVariableW
0x180004fd5  mov     rax, rbx
0x180004fd8  jmp     short loc_180004F8B
```
