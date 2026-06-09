# _GetSidStringFromSelf(ushort * *)

- ea: `0x180006ad0`
- end: `0x180006dcb`
- name: `?_GetSidStringFromSelf@@YAJPEAPEAG@Z`
- size: `763`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008910`

## callees

- `0x180005b60`
- `0x18000608c`
- `0x1800063e0`
- `0x180006a9c`
- `0x180006ad0`
- `0x180007c60`
- `0x18000dc34`
- `0x18001214c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006b7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006be4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006b7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006be4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d73`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006b04`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006b04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006b36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006b36`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180006b48`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180006b48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006aec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006aec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dc0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006bff`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006bff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006bc8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006bc8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006bb0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006ce9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006bb0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006ce9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006c2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006c2a`

## string_xrefs

- `0x180006c81`: `minio\profapi\path.cpp`
- `0x180006d31`: `minio\profapi\path.cpp`
- `0x180006d92`: `minio\profapi\path.cpp`

## pseudocode

```c
__int64 __fastcall _GetSidStringFromSelf(unsigned __int16 **a1)
{
  HANDLE CurrentThread; // rax
  int Error; // eax
  unsigned int v4; // ebx
  void *v5; // rdi
  HANDLE CurrentProcess; // rax
  const char *v7; // r9
  void *v8; // r14
  HANDLE ProcessHeap; // rax
  LPWSTR v10; // rdi
  void *v11; // rsi
  int v12; // ebx
  DWORD LengthSid; // ebx
  HANDLE v14; // rax
  void *v15; // rax
  void *v16; // r14
  int v18; // eax
  BOOL TokenInformation; // eax
  unsigned int v20; // ebx
  DWORD LastError; // ebx
  int ReturnLength; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD TokenInformationLength; // [rsp+70h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp+40h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_6;
  Error = ResultFromKnownLastError();
  v4 = Error;
  if ( Error != -2147023888 )
  {
    if ( Error < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"minio\\profapi\\path.cpp",
        (const char *)(unsigned int)Error,
        ReturnLength);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v4;
    }
LABEL_6:
    v8 = TokenHandle;
    TokenInformationLength = 200;
    ProcessHeap = GetProcessHeap();
    StringSid = (LPWSTR)HeapAlloc(ProcessHeap, 8u, 0xC8u);
    v10 = StringSid;
    if ( !StringSid )
    {
      v12 = -2147024882;
      goto LABEL_23;
    }
    v11 = 0;
    if ( GetTokenInformation(v8, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength) )
    {
      v12 = 0;
    }
    else
    {
      v12 = ResultFromKnownLastError();
      if ( v12 == -2147024774 )
      {
        v18 = ResultFromHeapReAlloc(v10, TokenInformationLength, (void **)&StringSid);
        v10 = StringSid;
        v12 = v18;
        if ( v18 < 0 )
          goto LABEL_14;
        TokenInformation = GetTokenInformation(
                             v8,
                             TokenUser,
                             StringSid,
                             TokenInformationLength,
                             &TokenInformationLength);
        v12 = ResultFromWin32Bool(TokenInformation);
      }
    }
    if ( v12 < 0 )
      goto LABEL_14;
    LengthSid = GetLengthSid(*(PSID *)v10);
    TokenInformationLength = LengthSid;
    v14 = GetProcessHeap();
    v15 = HeapAlloc(v14, 8u, LengthSid);
    v16 = v15;
    if ( v15 )
    {
      if ( CopySid(TokenInformationLength, v15, *(PSID *)v10) )
      {
        v12 = 0;
LABEL_13:
        v11 = v16;
        goto LABEL_14;
      }
      v12 = ResultFromKnownLastError();
      if ( v12 >= 0 )
        goto LABEL_13;
      ResultFromHeapFree(v16);
    }
    else
    {
      v12 = -2147024882;
    }
LABEL_14:
    ResultFromHeapFree(v10);
    if ( v12 < 0 )
      goto LABEL_23;
    StringSid = 0;
    if ( ConvertSidToStringSidW(v11, &StringSid) )
    {
      v12 = 0;
    }
    else
    {
      v12 = ResultFromKnownLastError();
      if ( v12 < 0 )
      {
LABEL_18:
        ResultFromHeapFree(v11);
        if ( v12 >= 0 )
        {
          if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(TokenHandle);
          return 0;
        }
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"minio\\profapi\\path.cpp",
          (const char *)(unsigned int)v12,
          ReturnLength);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return (unsigned int)v12;
      }
    }
    *a1 = StringSid;
    goto LABEL_18;
  }
  v5 = TokenHandle;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v5);
    SetLastError(LastError);
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    goto LABEL_6;
  v20 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xAE, (unsigned int)"minio\\profapi\\path.cpp", v7);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v20;
}

```

## disassembly

```asm
0x180006ad0  push    rbp
0x180006ad2  push    rbx
0x180006ad3  push    rdi
0x180006ad4  push    r12
0x180006ad6  push    r15
0x180006ad8  mov     rbp, rsp
0x180006adb  sub     rsp, 40h
0x180006adf  xor     r12d, r12d
0x180006ae2  mov     r15, rcx
0x180006ae5  mov     [rcx], r12
0x180006ae8  mov     [rbp+TokenHandle], r12
0x180006aec  call    cs:__imp_GetCurrentThread
0x180006af2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180006af6  mov     edx, 8; DesiredAccess
0x180006afb  mov     rcx, rax; ThreadHandle
0x180006afe  mov     r8d, 1; OpenAsSelf
0x180006b04  call    cs:__imp_OpenThreadToken
0x180006b0a  test    eax, eax
0x180006b0c  jnz     short loc_180006B56
0x180006b0e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006b13  mov     ebx, eax
0x180006b15  cmp     eax, 800703F0h
0x180006b1a  jnz     loc_180006D86
0x180006b20  mov     rdi, [rbp+TokenHandle]
0x180006b24  lea     rax, [rdi-1]
0x180006b28  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006b2c  jbe     loc_180006D60
0x180006b32  mov     [rbp+TokenHandle], r12
0x180006b36  call    cs:__imp_GetCurrentProcess
0x180006b3c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180006b40  mov     edx, 8; DesiredAccess
0x180006b45  mov     rcx, rax; ProcessHandle
0x180006b48  call    cs:__imp_OpenProcessToken
0x180006b4e  test    eax, eax
0x180006b50  jz      loc_180006D2D
0x180006b56  mov     [rsp+40h+var_8], rsi
0x180006b5b  mov     [rsp+40h+var_10], r14
0x180006b60  mov     r14, [rbp+TokenHandle]
0x180006b64  mov     [rbp+TokenInformationLength], 0C8h
0x180006b6b  call    cs:__imp_GetProcessHeap
0x180006b71  mov     edx, 8; dwFlags
0x180006b76  mov     r8d, 0C8h; dwBytes
0x180006b7c  mov     rcx, rax; hHeap
0x180006b7f  call    cs:__imp_HeapAlloc
0x180006b85  mov     [rbp+StringSid], rax
0x180006b89  mov     rdi, rax
0x180006b8c  test    rax, rax
0x180006b8f  jz      loc_180006C78
0x180006b95  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180006b99  lea     rax, [rbp+TokenInformationLength]
0x180006b9d  mov     r8, rdi; TokenInformation
0x180006ba0  mov     qword ptr [rsp+40h+ReturnLength], rax; ReturnLength
0x180006ba5  mov     edx, 1; TokenInformationClass
0x180006baa  mov     rcx, r14; TokenHandle
0x180006bad  mov     rsi, r12
0x180006bb0  call    cs:__imp_GetTokenInformation
0x180006bb6  test    eax, eax
0x180006bb8  jz      loc_180006CA2
0x180006bbe  mov     ebx, r12d
0x180006bc1  test    ebx, ebx
0x180006bc3  js      short loc_180006C13
0x180006bc5  mov     rcx, [rdi]; pSid
0x180006bc8  call    cs:__imp_GetLengthSid
0x180006bce  mov     ebx, eax
0x180006bd0  mov     [rbp+TokenInformationLength], ebx
0x180006bd3  call    cs:__imp_GetProcessHeap
0x180006bd9  mov     r8d, ebx; dwBytes
0x180006bdc  mov     edx, 8; dwFlags
0x180006be1  mov     rcx, rax; hHeap
0x180006be4  call    cs:__imp_HeapAlloc
0x180006bea  mov     r14, rax
0x180006bed  test    rax, rax
0x180006bf0  jz      loc_180006DB6
0x180006bf6  mov     r8, [rdi]; pSourceSid
0x180006bf9  mov     rdx, rax; pDestinationSid
0x180006bfc  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180006bff  call    cs:__imp_CopySid
0x180006c05  test    eax, eax
0x180006c07  jz      loc_180006CFD
0x180006c0d  mov     ebx, r12d
0x180006c10  mov     rsi, r14
0x180006c13  mov     rcx, rdi; lpMem
0x180006c16  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180006c1b  test    ebx, ebx
0x180006c1d  js      short loc_180006C7D
0x180006c1f  lea     rdx, [rbp+StringSid]; StringSid
0x180006c23  mov     [rbp+StringSid], r12
0x180006c27  mov     rcx, rsi; Sid
0x180006c2a  call    cs:__imp_ConvertSidToStringSidW
0x180006c30  test    eax, eax
0x180006c32  jz      loc_180006D19
0x180006c38  mov     ebx, r12d
0x180006c3b  mov     rax, [rbp+StringSid]
0x180006c3f  mov     [r15], rax
0x180006c42  mov     rcx, rsi; lpMem
0x180006c45  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180006c4a  test    ebx, ebx
0x180006c4c  js      short loc_180006C7D
0x180006c4e  mov     rcx, [rbp+TokenHandle]; hObject
0x180006c52  lea     rax, [rcx-1]
0x180006c56  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006c5a  jbe     loc_180006DC0
0x180006c60  xor     eax, eax
0x180006c62  mov     rsi, [rsp+40h+var_8]
0x180006c67  mov     r14, [rsp+40h+var_10]
0x180006c6c  add     rsp, 40h
0x180006c70  pop     r15
0x180006c72  pop     r12
0x180006c74  pop     rdi
0x180006c75  pop     rbx
0x180006c76  pop     rbp
0x180006c77  retn
0x180006c78  mov     ebx, 8007000Eh
0x180006c7d  mov     rcx, [rbp+28h]; this
0x180006c81  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180006c88  mov     r9d, ebx; char *
0x180006c8b  mov     edx, 0B5h; void *
0x180006c90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c95  lea     rcx, [rbp+TokenHandle]
0x180006c99  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006c9e  mov     eax, ebx
0x180006ca0  jmp     short loc_180006C62
0x180006ca2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006ca7  mov     ebx, eax
0x180006ca9  cmp     eax, 8007007Ah
0x180006cae  jnz     loc_180006BC1
0x180006cb4  mov     edx, [rbp+TokenInformationLength]; dwBytes
0x180006cb7  lea     r8, [rbp+StringSid]; void **
0x180006cbb  mov     rcx, rdi; lpMem
0x180006cbe  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180006cc3  mov     rdi, [rbp+StringSid]
0x180006cc7  mov     ebx, eax
0x180006cc9  test    eax, eax
0x180006ccb  js      loc_180006C13
0x180006cd1  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180006cd5  lea     rax, [rbp+TokenInformationLength]
0x180006cd9  mov     r8, rdi; TokenInformation
0x180006cdc  mov     qword ptr [rsp+40h+ReturnLength], rax; ReturnLength
0x180006ce1  mov     edx, 1; TokenInformationClass
0x180006ce6  mov     rcx, r14; TokenHandle
0x180006ce9  call    cs:__imp_GetTokenInformation
0x180006cef  mov     ecx, eax; int
0x180006cf1  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180006cf6  mov     ebx, eax
0x180006cf8  jmp     loc_180006BC1
0x180006cfd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006d02  mov     ebx, eax
0x180006d04  test    eax, eax
0x180006d06  jns     loc_180006C10
0x180006d0c  mov     rcx, r14; lpMem
0x180006d0f  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180006d14  jmp     loc_180006C13
0x180006d19  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006d1e  mov     ebx, eax
0x180006d20  test    eax, eax
0x180006d22  jns     loc_180006C3B
0x180006d28  jmp     loc_180006C42
0x180006d2d  mov     rcx, [rbp+28h]; this
0x180006d31  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180006d38  mov     edx, 0AEh; void *
0x180006d3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006d42  mov     rcx, [rbp+TokenHandle]; hObject
0x180006d46  mov     ebx, eax
0x180006d48  lea     rdx, [rcx-1]
0x180006d4c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180006d50  jbe     short loc_180006D7E
0x180006d52  mov     eax, ebx
0x180006d54  add     rsp, 40h
0x180006d58  pop     r15
0x180006d5a  pop     r12
0x180006d5c  pop     rdi
0x180006d5d  pop     rbx
0x180006d5e  pop     rbp
0x180006d5f  retn
0x180006d60  call    cs:__imp_GetLastError
0x180006d66  mov     rcx, rdi; hObject
0x180006d69  mov     ebx, eax
0x180006d6b  call    cs:__imp_CloseHandle
0x180006d71  mov     ecx, ebx; dwErrCode
0x180006d73  call    cs:__imp_SetLastError
0x180006d79  jmp     loc_180006B32
0x180006d7e  call    cs:__imp_CloseHandle
0x180006d84  jmp     short loc_180006D52
0x180006d86  test    ebx, ebx
0x180006d88  jns     loc_180006B56
0x180006d8e  mov     rcx, [rbp+28h]; this
0x180006d92  lea     r8, aMinioProfapiPa; "minio\\profapi\\path.cpp"
0x180006d99  mov     r9d, ebx; char *
0x180006d9c  mov     edx, 0B2h; void *
0x180006da1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006da6  lea     rcx, [rbp+TokenHandle]
0x180006daa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006daf  mov     eax, ebx
0x180006db1  jmp     loc_180006C6C
0x180006db6  mov     ebx, 8007000Eh
0x180006dbb  jmp     loc_180006C13
0x180006dc0  call    cs:__imp_CloseHandle
0x180006dc6  jmp     loc_180006C60
```
