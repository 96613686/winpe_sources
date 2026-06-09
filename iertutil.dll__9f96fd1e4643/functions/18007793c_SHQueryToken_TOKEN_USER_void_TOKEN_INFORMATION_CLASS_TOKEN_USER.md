# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER * *)

- ea: `0x18007793c`
- end: `0x180077a60`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_USER@@@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180077e50`

## callees

- `0x18005f4ac`
- `0x180071ac8`
- `0x18007793c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800779cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800779cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077a4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077a4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800779db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077a39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800779db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077a39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800779c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180077a13`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800779c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180077a13`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(void *a1, DWORD a2, _QWORD *a3)
{
  void *v4; // rcx
  int v5; // ebx
  HANDLE v6; // r14
  void *v7; // rdi
  signed int LastError; // eax
  void *v9; // rcx
  int v10; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  TokenInformationLength = a2;
  TokenInformation = a1;
  *a3 = 0;
  TokenHandle = 0;
  v5 = SHOpenEffectiveToken((__int64)a1, &TokenHandle);
  if ( v5 >= 0 )
  {
    v6 = TokenHandle;
    TokenInformation = 0;
    TokenInformationLength = 2048;
    v5 = CTLocalAllocPolicy::Alloc(v4, 0x40u, 0x800u, &TokenInformation);
    if ( v5 >= 0 )
    {
      v7 = TokenInformation;
      if ( !GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError == 122 )
        {
          LocalFree(v7);
          v10 = CTLocalAllocPolicy::Alloc(v9, 0x40u, TokenInformationLength, &TokenInformation);
          v7 = TokenInformation;
          v5 = v10;
          if ( v10 < 0 )
          {
LABEL_11:
            LocalFree(v7);
            goto LABEL_13;
          }
          if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
            goto LABEL_12;
          LastError = GetLastError();
          v5 = LastError;
        }
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_11;
      }
LABEL_12:
      *a3 = v7;
    }
  }
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007793c  mov     [rsp-28h+TokenInformationLength], edx
0x180077940  mov     [rsp-28h+TokenInformation], rcx
0x180077945  push    rbp
0x180077946  push    rbx
0x180077947  push    rsi
0x180077948  push    rdi
0x180077949  push    r14
0x18007794b  mov     rbp, rsp
0x18007794e  sub     rsp, 30h
0x180077952  lea     rdx, [rbp+TokenHandle]
0x180077956  mov     qword ptr [r8], 0
0x18007795d  mov     rsi, r8
0x180077960  mov     [rbp+TokenHandle], 0
0x180077968  call    SHOpenEffectiveToken
0x18007796d  mov     ebx, eax
0x18007796f  test    eax, eax
0x180077971  js      loc_180077A44
0x180077977  mov     r14, [rbp+TokenHandle]
0x18007797b  lea     r9, [rbp+TokenInformation]; void **
0x18007797f  mov     r8d, 800h; unsigned __int64
0x180077985  mov     [rbp+TokenInformation], 0
0x18007798d  mov     edx, 40h ; '@'; unsigned int
0x180077992  mov     [rbp+TokenInformationLength], r8d
0x180077996  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18007799b  mov     ebx, eax
0x18007799d  test    eax, eax
0x18007799f  js      loc_180077A44
0x1800779a5  mov     rdi, [rbp+TokenInformation]
0x1800779a9  lea     rax, [rbp+TokenInformationLength]
0x1800779ad  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800779b1  mov     r8, rdi; TokenInformation
0x1800779b4  mov     edx, 1; TokenInformationClass
0x1800779b9  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800779be  mov     rcx, r14; TokenHandle
0x1800779c1  call    cs:__imp_GetTokenInformation
0x1800779c7  test    eax, eax
0x1800779c9  jnz     short loc_180077A41
0x1800779cb  call    cs:__imp_GetLastError
0x1800779d1  mov     ebx, eax
0x1800779d3  cmp     eax, 7Ah ; 'z'
0x1800779d6  jnz     short loc_180077A25
0x1800779d8  mov     rcx, rdi; hMem
0x1800779db  call    cs:__imp_LocalFree
0x1800779e1  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x1800779e5  lea     r9, [rbp+TokenInformation]; void **
0x1800779e9  lea     edx, [rbx-3Ah]; unsigned int
0x1800779ec  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800779f1  mov     rdi, [rbp+TokenInformation]
0x1800779f5  mov     ebx, eax
0x1800779f7  test    eax, eax
0x1800779f9  js      short loc_180077A36
0x1800779fb  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800779ff  lea     rax, [rbp+TokenInformationLength]
0x180077a03  mov     r8, rdi; TokenInformation
0x180077a06  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180077a0b  mov     edx, 1; TokenInformationClass
0x180077a10  mov     rcx, r14; TokenHandle
0x180077a13  call    cs:__imp_GetTokenInformation
0x180077a19  test    eax, eax
0x180077a1b  jnz     short loc_180077A41
0x180077a1d  call    cs:__imp_GetLastError
0x180077a23  mov     ebx, eax
0x180077a25  test    eax, eax
0x180077a27  jle     short loc_180077A32
0x180077a29  movzx   ebx, ax
0x180077a2c  or      ebx, 80070000h
0x180077a32  test    ebx, ebx
0x180077a34  jns     short loc_180077A41
0x180077a36  mov     rcx, rdi; hMem
0x180077a39  call    cs:__imp_LocalFree
0x180077a3f  jmp     short loc_180077A44
0x180077a41  mov     [rsi], rdi
0x180077a44  mov     rcx, [rbp+TokenHandle]; hObject
0x180077a48  test    rcx, rcx
0x180077a4b  jz      short loc_180077A53
0x180077a4d  call    cs:__imp_CloseHandle
0x180077a53  mov     eax, ebx
0x180077a55  add     rsp, 30h
0x180077a59  pop     r14
0x180077a5b  pop     rdi
0x180077a5c  pop     rsi
0x180077a5d  pop     rbx
0x180077a5e  pop     rbp
0x180077a5f  retn
```
