# CSecurityAttributesForSharedObjects::_InitializeWithInheritance(ushort const *)

- ea: `0x180022070`
- end: `0x18002223d`
- name: `?_InitializeWithInheritance@CSecurityAttributesForSharedObjects@@AEAAJPEBG@Z`
- size: `461`
- prototype: `int(CSecurityAttributesForSharedObjects *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020fa0`
- `0x1800a73bc`

## callees

- `0x180022070`
- `0x180023eac`
- `0x180024418`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022139`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022139`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002214b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002214b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800221b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800221b5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800220b4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x1800220b4`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800220e1`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180022123`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800220e1`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180022123`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x1800221a5`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x1800221a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800220f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800220f9`

## pseudocode

```c
__int64 __fastcall CSecurityAttributesForSharedObjects::_InitializeWithInheritance(
        PSECURITY_DESCRIPTOR *this,
        const unsigned __int16 *a2)
{
  int Error; // ebx
  void *v5; // rsi
  HANDLE CurrentProcess; // rax
  PSECURITY_DESCRIPTOR v7; // rdx
  DWORD nLengthNeeded; // [rsp+40h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-28h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-20h] BYREF

  Error = CSecurityAttributesForSharedObjects::_InitializeChildSD((CSecurityAttributesForSharedObjects *)this);
  if ( Error >= 0 )
  {
    if ( SetSecurityDescriptorControl(this[2], 0x500u, 0x500u) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        return (unsigned int)Error;
    }
    nLengthNeeded = 0;
    GetFileSecurityW(a2, 4u, 0, 0, &nLengthNeeded);
    if ( GetLastError() != 122 )
      goto LABEL_12;
    v5 = CoTaskMemAlloc(nLengthNeeded);
    if ( !v5 )
      return (unsigned int)-2147024882;
    if ( GetFileSecurityW(a2, 4u, v5, nLengthNeeded, &nLengthNeeded) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      TokenHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        v7 = this[2];
        GenericMapping.GenericRead = 1179785;
        GenericMapping.GenericWrite = 1179926;
        GenericMapping.GenericExecute = 1179808;
        GenericMapping.GenericAll = 2032127;
        if ( CreatePrivateObjectSecurityEx(v5, v7, this + 9, 0, 0, 1u, TokenHandle, &GenericMapping) )
          Error = 0;
        else
          Error = ResultFromKnownLastError();
        CloseHandle(TokenHandle);
      }
    }
    CoTaskMemFree(v5);
    if ( Error >= 0 )
    {
LABEL_12:
      this[5] = this[9];
      this[1] = this + 4;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180022070  mov     [rsp-18h+arg_10], rbx
0x180022075  mov     [rsp-18h+arg_18], rsi
0x18002207a  push    rbp
0x18002207b  push    rdi
0x18002207c  push    r14
0x18002207e  mov     rbp, rsp
0x180022081  sub     rsp, 70h
0x180022085  mov     rax, cs:__security_cookie
0x18002208c  xor     rax, rsp
0x18002208f  mov     [rbp+var_10], rax
0x180022093  mov     r14, rdx
0x180022096  mov     rdi, rcx
0x180022099  call    ?_InitializeChildSD@CSecurityAttributesForSharedObjects@@AEAAJXZ; CSecurityAttributesForSharedObjects::_InitializeChildSD(void)
0x18002209e  mov     ebx, eax
0x1800220a0  test    eax, eax
0x1800220a2  js      loc_1800221D8
0x1800220a8  mov     rcx, [rdi+10h]; pSecurityDescriptor
0x1800220ac  mov     edx, 500h; ControlBitsOfInterest
0x1800220b1  mov     r8d, edx; ControlBitsToSet
0x1800220b4  call    cs:__imp_SetSecurityDescriptorControl
0x1800220ba  test    eax, eax
0x1800220bc  jz      loc_18002220C
0x1800220c2  xor     ebx, ebx
0x1800220c4  xor     r9d, r9d; nLength
0x1800220c7  mov     [rbp+nLengthNeeded], 0
0x1800220ce  lea     rax, [rbp+nLengthNeeded]
0x1800220d2  xor     r8d, r8d; pSecurityDescriptor
0x1800220d5  mov     rcx, r14; lpFileName
0x1800220d8  mov     [rsp+70h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800220dd  lea     edx, [r9+4]; RequestedInformation
0x1800220e1  call    cs:__imp_GetFileSecurityW
0x1800220e7  call    cs:__imp_GetLastError
0x1800220ed  cmp     eax, 7Ah ; 'z'
0x1800220f0  jnz     loc_1800221C8
0x1800220f6  mov     ecx, [rbp+nLengthNeeded]; cb
0x1800220f9  call    cs:__imp_CoTaskMemAlloc
0x1800220ff  mov     rsi, rax
0x180022102  test    rax, rax
0x180022105  jz      loc_180022226
0x18002210b  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18002210f  lea     rax, [rbp+nLengthNeeded]
0x180022113  mov     r8, rsi; pSecurityDescriptor
0x180022116  mov     [rsp+70h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002211b  mov     edx, 4; RequestedInformation
0x180022120  mov     rcx, r14; lpFileName
0x180022123  call    cs:__imp_GetFileSecurityW
0x180022129  test    eax, eax
0x18002212b  jz      loc_18002222D
0x180022131  mov     [rbp+TokenHandle], 0
0x180022139  call    cs:__imp_GetCurrentProcess
0x18002213f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180022143  mov     edx, 0F01FFh; DesiredAccess
0x180022148  mov     rcx, rax; ProcessHandle
0x18002214b  call    cs:__imp_OpenProcessToken
0x180022151  test    eax, eax
0x180022153  jz      loc_1800221FB
0x180022159  mov     rdx, [rdi+10h]; CreatorDescriptor
0x18002215d  lea     rax, [rbp+var_20]
0x180022161  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x180022166  lea     r8, [rdi+48h]; NewDescriptor
0x18002216a  mov     rax, [rbp+TokenHandle]
0x18002216e  xor     r9d, r9d; ObjectType
0x180022171  mov     [rsp+70h+Token], rax; Token
0x180022176  mov     rcx, rsi; ParentDescriptor
0x180022179  mov     [rsp+70h+AutoInheritFlags], 1; AutoInheritFlags
0x180022181  mov     dword ptr [rsp+70h+lpnLengthNeeded], 0; IsContainerObject
0x180022189  mov     [rbp+var_20.GenericRead], 120089h
0x180022190  mov     [rbp+var_20.GenericWrite], 120116h
0x180022197  mov     [rbp+var_20.GenericExecute], 1200A0h
0x18002219e  mov     [rbp+var_20.GenericAll], 1F01FFh
0x1800221a5  call    cs:__imp_CreatePrivateObjectSecurityEx
0x1800221ab  test    eax, eax
0x1800221ad  jz      short loc_18002221D
0x1800221af  xor     ebx, ebx
0x1800221b1  mov     rcx, [rbp+TokenHandle]; hObject
0x1800221b5  call    cs:__imp_CloseHandle
0x1800221bb  mov     rcx, rsi; pv
0x1800221be  call    cs:__imp_CoTaskMemFree
0x1800221c4  test    ebx, ebx
0x1800221c6  js      short loc_1800221D8
0x1800221c8  mov     rax, [rdi+48h]
0x1800221cc  lea     rcx, [rdi+20h]
0x1800221d0  mov     [rcx+8], rax
0x1800221d4  mov     [rdi+8], rcx
0x1800221d8  mov     eax, ebx
0x1800221da  mov     rcx, [rbp+var_10]
0x1800221de  xor     rcx, rsp; StackCookie
0x1800221e1  call    __security_check_cookie
0x1800221e6  lea     r11, [rsp+70h+var_s0]
0x1800221eb  mov     rbx, [r11+30h]
0x1800221ef  mov     rsi, [r11+38h]
0x1800221f3  mov     rsp, r11
0x1800221f6  pop     r14
0x1800221f8  pop     rdi
0x1800221f9  pop     rbp
0x1800221fa  retn
0x1800221fb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022200  mov     ebx, eax
0x180022202  test    eax, eax
0x180022204  jns     loc_180022159
0x18002220a  jmp     short loc_1800221BB
0x18002220c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022211  mov     ebx, eax
0x180022213  test    eax, eax
0x180022215  jns     loc_1800220C4
0x18002221b  jmp     short loc_1800221D8
0x18002221d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022222  mov     ebx, eax
0x180022224  jmp     short loc_1800221B1
0x180022226  mov     ebx, 8007000Eh
0x18002222b  jmp     short loc_1800221D8
0x18002222d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022232  mov     ebx, eax
0x180022234  test    eax, eax
0x180022236  js      short loc_1800221BB
0x180022238  jmp     loc_180022131
```
