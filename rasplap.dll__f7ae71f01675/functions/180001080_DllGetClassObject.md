# DllGetClassObject

- ea: `0x180001080`
- end: `0x1800011c2`
- name: `DllGetClassObject`
- size: `322`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001080`
- `0x1800011d0`
- `0x180001200`
- `0x180002970`
- `0x18000c010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800010f0`
- `ntdll!NtQueryInformationToken` at `0x1800010f0`
- `ADVAPI32!OpenProcessToken` at `0x1800010c3`
- `ADVAPI32!OpenProcessToken` at `0x1800010c3`
- `KERNEL32!GetLastError` at `0x18000119c`
- `KERNEL32!GetLastError` at `0x18000119c`
- `KERNEL32!CloseHandle` at `0x18000110f`
- `KERNEL32!CloseHandle` at `0x18000110f`
- `KERNEL32!GetCurrentProcess` at `0x1800010b0`
- `KERNEL32!GetCurrentProcess` at `0x1800010b0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  BOOL v4; // edi
  HANDLE CurrentProcess; // rax
  __int64 v8; // rax
  CClassFactory *v10; // rax
  CClassFactory *v11; // rax
  CClassFactory *v12; // rdi
  HRESULT v13; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+18h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp+20h] BYREF

  TokenHandle = 0;
  v4 = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) >= 0 )
      v4 = TokenInformation != 0;
  }
  else
  {
    GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( !v4 )
    DebugInitEx();
  *ppv = 0;
  v8 = *(_QWORD *)&CLSID_RASProvider.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_RASProvider.Data1 == *(_QWORD *)&rclsid->Data1 )
    v8 = *(_QWORD *)CLSID_RASProvider.Data4 - *(_QWORD *)rclsid->Data4;
  if ( v8 )
    return -2147221231;
  v10 = (CClassFactory *)operator new(0x10u);
  if ( !v10 )
    return -2147024882;
  v11 = CClassFactory::CClassFactory(v10);
  v12 = v11;
  if ( !v11 )
    return -2147024882;
  v13 = (**(__int64 (__fastcall ***)(CClassFactory *, const IID *const, LPVOID *))v11)(v11, riid, ppv);
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v12 + 16LL))(v12);
  return v13;
}

```

## disassembly

```asm
0x180001080  mov     [rsp+arg_0], rbx
0x180001085  mov     [rsp+arg_8], rbp
0x18000108a  push    rsi
0x18000108b  push    rdi
0x18000108c  push    r14
0x18000108e  sub     rsp, 40h
0x180001092  xor     r14d, r14d
0x180001095  mov     rsi, r8
0x180001098  mov     [rsp+58h+TokenHandle], r14
0x18000109d  mov     edi, r14d
0x1800010a0  mov     [rsp+58h+arg_18], r14d
0x1800010a5  mov     rbp, rdx
0x1800010a8  mov     [rsp+58h+TokenInformation], r14d
0x1800010ad  mov     rbx, rcx
0x1800010b0  call    cs:__imp_GetCurrentProcess
0x1800010b6  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800010bb  mov     edx, 8; DesiredAccess
0x1800010c0  mov     rcx, rax; ProcessHandle
0x1800010c3  call    cs:__imp_OpenProcessToken
0x1800010c9  test    eax, eax
0x1800010cb  jz      loc_18000119C
0x1800010d1  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800010d6  lea     rax, [rsp+58h+arg_18]
0x1800010db  mov     r9d, 4; TokenInformationLength
0x1800010e1  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800010e6  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1800010eb  mov     edx, 1Dh; TokenInformationClass
0x1800010f0  call    cs:__imp_NtQueryInformationToken
0x1800010f6  test    eax, eax
0x1800010f8  js      short loc_180001105
0x1800010fa  cmp     [rsp+58h+TokenInformation], r14d
0x1800010ff  jnz     loc_1800011B8
0x180001105  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000110a  test    rcx, rcx
0x18000110d  jz      short loc_180001115
0x18000110f  call    cs:__imp_CloseHandle
0x180001115  test    edi, edi
0x180001117  jz      loc_1800011AE
0x18000111d  mov     [rsi], r14
0x180001120  mov     rax, qword ptr cs:CLSID_RASProvider.Data1
0x180001127  sub     rax, [rbx]
0x18000112a  jnz     short loc_180001137
0x18000112c  mov     rax, qword ptr cs:CLSID_RASProvider.Data4
0x180001133  sub     rax, [rbx+8]
0x180001137  test    rax, rax
0x18000113a  jz      short loc_180001143
0x18000113c  mov     eax, 80040111h
0x180001141  jmp     short loc_180001189
0x180001143  mov     ecx, 10h; Size
0x180001148  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000114d  test    rax, rax
0x180001150  jz      short loc_1800011A7
0x180001152  mov     rcx, rax; this
0x180001155  call    ??0CClassFactory@@AEAA@XZ; CClassFactory::CClassFactory(void)
0x18000115a  mov     rdi, rax
0x18000115d  test    rax, rax
0x180001160  jz      short loc_1800011A7
0x180001162  mov     rcx, [rax]
0x180001165  mov     r8, rsi
0x180001168  mov     rdx, rbp
0x18000116b  mov     rax, [rcx]
0x18000116e  mov     rcx, rdi
0x180001171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001176  mov     rcx, [rdi]
0x180001179  mov     ebx, eax
0x18000117b  mov     rax, [rcx+10h]
0x18000117f  mov     rcx, rdi
0x180001182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001187  mov     eax, ebx
0x180001189  mov     rbx, [rsp+58h+arg_0]
0x18000118e  mov     rbp, [rsp+58h+arg_8]
0x180001193  add     rsp, 40h
0x180001197  pop     r14
0x180001199  pop     rdi
0x18000119a  pop     rsi
0x18000119b  retn
0x18000119c  call    cs:__imp_GetLastError
0x1800011a2  jmp     loc_180001105
0x1800011a7  mov     eax, 8007000Eh
0x1800011ac  jmp     short loc_180001189
0x1800011ae  call    DebugInitEx
0x1800011b3  jmp     loc_18000111D
0x1800011b8  mov     edi, 1
0x1800011bd  jmp     loc_180001105
```
