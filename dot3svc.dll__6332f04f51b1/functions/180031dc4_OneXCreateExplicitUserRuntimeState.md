# OneXCreateExplicitUserRuntimeState

- ea: `0x180031dc4`
- end: `0x180031ecf`
- name: `OneXCreateExplicitUserRuntimeState`
- size: `267`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017a68`

## callees

- `0x180031dc4`
- `0x180032094`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031e22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031e2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031e22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031e2b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031e4e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031e4e`
- `MobileNetworking!AllocateMemory` at `0x180031e01`
- `MobileNetworking!AllocateMemory` at `0x180031e01`

## string_xrefs

- `0x180031df5`: `OneXCreateExplicitUserRuntimeState`

## pseudocode

```c
__int64 __fastcall OneXCreateExplicitUserRuntimeState(HANDLE hSourceHandle, int a2, __int64 a3, _QWORD *a4)
{
  DWORD LastError; // esi
  HANDLE *v8; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v10; // rax
  int v11; // ecx
  _DWORD *v13; // [rsp+98h] [rbp+20h] BYREF

  *a4 = 0;
  v13 = 0;
  LastError = AllocateMemory(56, &v13, "OneXCreateExplicitUserRuntimeState", 324);
  if ( LastError )
    goto LABEL_7;
  if ( hSourceHandle )
  {
    v8 = (HANDLE *)v13;
    CurrentProcess = GetCurrentProcess();
    v10 = GetCurrentProcess();
    if ( DuplicateHandle(v10, hSourceHandle, CurrentProcess, v8 + 1, 0, 0, 2u) || (LastError = GetLastError()) == 0 )
    {
      *v13 |= 1u;
      v11 = *v13 | 8;
      *v13 = v11;
      *v13 = v11 & 0xFFFFFFFB;
      v13[8] = a2;
      v13[9] = 2;
      goto LABEL_6;
    }
LABEL_7:
    OneXFreeRuntimeState(v13);
    return LastError;
  }
LABEL_6:
  *a4 = v13;
  return LastError;
}

```

## disassembly

```asm
0x180031dc4  mov     rax, rsp
0x180031dc7  push    rbx
0x180031dc8  push    rbp
0x180031dc9  push    rsi
0x180031dca  push    rdi
0x180031dcb  push    r14
0x180031dcd  push    r15
0x180031dcf  sub     rsp, 48h
0x180031dd3  mov     r14, r9
0x180031dd6  mov     qword ptr [r9], 0
0x180031ddd  mov     r15d, edx
0x180031de0  mov     qword ptr [rax+20h], 0
0x180031de8  mov     rbp, rcx
0x180031deb  lea     rdx, [rax+20h]
0x180031def  mov     r9d, 144h
0x180031df5  lea     r8, aOnexcreateexpl; "OneXCreateExplicitUserRuntimeState"
0x180031dfc  mov     ecx, 38h ; '8'
0x180031e01  call    cs:__imp_AllocateMemory
0x180031e07  mov     esi, eax
0x180031e09  test    eax, eax
0x180031e0b  jnz     loc_180031EB3
0x180031e11  test    rbp, rbp
0x180031e14  jz      loc_180031EA6
0x180031e1a  mov     rdi, [rsp+78h+arg_18]
0x180031e22  call    cs:__imp_GetCurrentProcess
0x180031e28  mov     rbx, rax
0x180031e2b  call    cs:__imp_GetCurrentProcess
0x180031e31  mov     [rsp+78h+dwOptions], 2; dwOptions
0x180031e39  lea     r9, [rdi+8]; lpTargetHandle
0x180031e3d  mov     rcx, rax; hSourceProcessHandle
0x180031e40  mov     [rsp+78h+bInheritHandle], esi; bInheritHandle
0x180031e44  mov     r8, rbx; hTargetProcessHandle
0x180031e47  mov     [rsp+78h+dwDesiredAccess], esi; dwDesiredAccess
0x180031e4b  mov     rdx, rbp; hSourceHandle
0x180031e4e  call    cs:__imp_DuplicateHandle
0x180031e54  test    eax, eax
0x180031e56  jnz     short loc_180031E64
0x180031e58  call    cs:__imp_GetLastError
0x180031e5e  mov     esi, eax
0x180031e60  test    eax, eax
0x180031e62  jnz     short loc_180031EB3
0x180031e64  mov     rax, [rsp+78h+arg_18]
0x180031e6c  or      dword ptr [rax], 1
0x180031e6f  mov     rax, [rsp+78h+arg_18]
0x180031e77  mov     ecx, [rax]
0x180031e79  or      ecx, 8
0x180031e7c  mov     [rax], ecx
0x180031e7e  and     ecx, 0FFFFFFFBh
0x180031e81  mov     rax, [rsp+78h+arg_18]
0x180031e89  mov     [rax], ecx
0x180031e8b  mov     rax, [rsp+78h+arg_18]
0x180031e93  mov     [rax+20h], r15d
0x180031e97  mov     rax, [rsp+78h+arg_18]
0x180031e9f  mov     dword ptr [rax+24h], 2
0x180031ea6  mov     rax, [rsp+78h+arg_18]
0x180031eae  mov     [r14], rax
0x180031eb1  jmp     short loc_180031EC0
0x180031eb3  mov     rcx, [rsp+78h+arg_18]
0x180031ebb  call    OneXFreeRuntimeState
0x180031ec0  mov     eax, esi
0x180031ec2  add     rsp, 48h
0x180031ec6  pop     r15
0x180031ec8  pop     r14
0x180031eca  pop     rdi
0x180031ecb  pop     rsi
0x180031ecc  pop     rbp
0x180031ecd  pop     rbx
0x180031ece  retn
```
