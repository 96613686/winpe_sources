# ThreadContextInfo::SetValidCallTargetInternal<0>(void *,void *,void *,bool)

- ea: `0x1801b5ad4`
- end: `0x1801b5c35`
- name: `??$SetValidCallTargetInternal@$0A@@ThreadContextInfo@@AEAAXPEAX00_N@Z`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801b51b8`

## callees

- `0x180024030`
- `0x1801b5ad4`
- `0x1801b5c3c`
- `0x1801b5cc8`
- `0x1801b5d34`
- `0x1803c4080`
- `0x1805a9a91`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801b5be6`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801b5be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5bff`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801b5b2a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801b5b2a`
- `api-ms-win-core-memory-l1-1-3!SetProcessValidCallTargets` at `0x1801b5b98`
- `api-ms-win-core-memory-l1-1-3!SetProcessValidCallTargets` at `0x1801b5b98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadContextInfo::SetValidCallTargetInternal<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5)
{
  unsigned __int64 v7; // rsi
  __int64 v8; // rbx
  const WCHAR *v9; // rax
  DWORD LastError; // eax
  _BYTE pExceptionObject[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h]
  _QWORD v13[2]; // [rsp+40h] [rbp-38h] BYREF

  v12 = -2;
  if ( ThreadContextInfo::IsCFGEnabled((ThreadContextInfo *)a1) )
  {
    if ( GlobalSecurityPolicy::s_ro_disableSetProcessValidCallTargets )
      RaiseFailFastException(0, 0, 1u);
    v7 = a2 & 0xFFFFFFFFFFFFF000uLL;
    v13[0] = a2 & 0xFFF;
    v13[1] = a5;
    if ( !*(_BYTE *)(a1 + 24) )
    {
      v9 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 8) + 8LL))(a1 + 8);
      *(_QWORD *)(a1 + 16) = LoadLibraryExW(v9, 0, 0x800u);
      *(_BYTE *)(a1 + 24) = 1;
    }
    v8 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
    Memory::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)pExceptionObject, 1);
    LODWORD(v8) = SetProcessValidCallTargets(v8, v7, 4096, 1, v13);
    Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)pExceptionObject);
    if ( !(_DWORD)v8 )
    {
      LastError = GetLastError();
      if ( LastError == 1455 )
        Js::Throw::OutOfMemory();
      if ( LastError == 5 )
        throw (Js::OperationAbortedException *)pExceptionObject;
      Js::Throw::InternalError();
    }
  }
}

```

## disassembly

```asm
0x1801b5ad4  mov     r11, rsp
0x1801b5ad7  mov     [r11+20h], r9
0x1801b5adb  mov     [r11+18h], r8
0x1801b5adf  mov     [r11+10h], rdx
0x1801b5ae3  mov     [r11+8], rcx
0x1801b5ae7  push    rbx
0x1801b5ae8  push    rsi
0x1801b5ae9  push    rdi
0x1801b5aea  sub     rsp, 60h
0x1801b5aee  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x1801b5af6  mov     rax, cs:__security_cookie
0x1801b5afd  xor     rax, rsp
0x1801b5b00  mov     [rsp+78h+var_28], rax
0x1801b5b05  mov     rdi, rcx
0x1801b5b08  mov     rbx, rdx
0x1801b5b0b  call    ?IsCFGEnabled@ThreadContextInfo@@QEAA_NXZ; ThreadContextInfo::IsCFGEnabled(void)
0x1801b5b10  test    al, al
0x1801b5b12  jz      loc_1801B5BB4
0x1801b5b18  mov     al, cs:?s_ro_disableSetProcessValidCallTargets@GlobalSecurityPolicy@@0_NC; bool volatile GlobalSecurityPolicy::s_ro_disableSetProcessValidCallTargets
0x1801b5b1e  test    al, al
0x1801b5b20  jz      short loc_1801B5B36
0x1801b5b22  xor     edx, edx; pContextRecord
0x1801b5b24  xor     ecx, ecx; pExceptionRecord
0x1801b5b26  lea     r8d, [rdx+1]; dwFlags
0x1801b5b2a  call    cs:__imp_RaiseFailFastException
0x1801b5b31  nop     dword ptr [rax+rax+00h]
0x1801b5b36  mov     rsi, rbx
0x1801b5b39  and     rsi, 0FFFFFFFFFFFFF000h
0x1801b5b40  and     ebx, 0FFFh
0x1801b5b46  mov     [rsp+78h+var_38], rbx
0x1801b5b4b  movzx   eax, [rsp+78h+arg_20]
0x1801b5b53  mov     [rsp+78h+var_30], rax
0x1801b5b58  cmp     byte ptr [rdi+18h], 0
0x1801b5b5c  jz      short loc_1801B5BCA
0x1801b5b5e  mov     rax, [rdi]
0x1801b5b61  mov     rcx, rdi
0x1801b5b64  mov     rax, [rax]
0x1801b5b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5b6c  mov     rbx, rax
0x1801b5b6f  mov     dl, 1; bool
0x1801b5b71  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1801b5b76  call    ??0AutoEnableDynamicCodeGen@Memory@@QEAA@_N@Z; Memory::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x1801b5b7b  nop
0x1801b5b7c  lea     rax, [rsp+78h+var_38]
0x1801b5b81  mov     [rsp+78h+var_58], rax
0x1801b5b86  mov     r9d, 1
0x1801b5b8c  mov     r8d, 1000h
0x1801b5b92  mov     rdx, rsi
0x1801b5b95  mov     rcx, rbx
0x1801b5b98  call    cs:__imp_SetProcessValidCallTargets
0x1801b5b9f  nop     dword ptr [rax+rax+00h]
0x1801b5ba4  mov     ebx, eax
0x1801b5ba6  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1801b5bab  call    ??1AutoEnableDynamicCodeGen@Memory@@QEAA@XZ; Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen(void)
0x1801b5bb0  test    ebx, ebx
0x1801b5bb2  jz      short loc_1801B5BFF
0x1801b5bb4  mov     rcx, [rsp+78h+var_28]
0x1801b5bb9  xor     rcx, rsp; StackCookie
0x1801b5bbc  call    __security_check_cookie
0x1801b5bc1  add     rsp, 60h
0x1801b5bc5  pop     rdi
0x1801b5bc6  pop     rsi
0x1801b5bc7  pop     rbx
0x1801b5bc8  retn
0x1801b5bca  mov     rax, [rdi+8]
0x1801b5bce  lea     rcx, [rdi+8]
0x1801b5bd2  mov     rax, [rax+8]
0x1801b5bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5bdb  mov     rcx, rax; lpLibFileName
0x1801b5bde  xor     edx, edx; hFile
0x1801b5be0  mov     r8d, 800h; dwFlags
0x1801b5be6  call    cs:__imp_LoadLibraryExW
0x1801b5bed  nop     dword ptr [rax+rax+00h]
0x1801b5bf2  mov     [rdi+10h], rax
0x1801b5bf6  mov     byte ptr [rdi+18h], 1
0x1801b5bfa  jmp     loc_1801B5B5E
0x1801b5bff  call    cs:__imp_GetLastError
0x1801b5c06  nop     dword ptr [rax+rax+00h]
0x1801b5c0b  cmp     eax, 5AFh
0x1801b5c10  jnz     short loc_1801B5C18
0x1801b5c12  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1801b5c18  cmp     eax, 5
0x1801b5c1b  jnz     short loc_1801B5C2F
0x1801b5c1d  lea     rdx, _TI2?AVOperationAbortedException@Js@@; pThrowInfo
0x1801b5c24  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1801b5c29  call    _CxxThrowException_0
0x1801b5c2f  call    ?InternalError@Throw@Js@@SAXXZ; Js::Throw::InternalError(void)
```
