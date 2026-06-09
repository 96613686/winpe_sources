# OneXCreatePlapRuntimeState

- ea: `0x180031ed8`
- end: `0x18003208d`
- name: `OneXCreatePlapRuntimeState`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180017a68`

## callees

- `0x180031204`
- `0x180031ed8`
- `0x180032094`
- `0x180032488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031f81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031f8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031f81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031f8a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031fb5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031fb5`
- `MobileNetworking!FreeMemory` at `0x180032063`
- `MobileNetworking!FreeMemory` at `0x180032063`
- `MobileNetworking!AllocateMemory` at `0x180031f44`
- `MobileNetworking!AllocateMemory` at `0x180031f44`

## string_xrefs

- `0x180031f15`: `OneXCreatePlapRuntimeState`

## pseudocode

```c
__int64 __fastcall OneXCreatePlapRuntimeState(int a1, unsigned int a2, void *a3, void *a4, _QWORD *a5)
{
  _QWORD *v5; // r12
  __int64 v8; // rsi
  DWORD LastError; // ebx
  __int64 v11; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  __int64 v15; // [rsp+48h] [rbp-18h] BYREF
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF
  __int64 v17; // [rsp+58h] [rbp-8h] BYREF
  int v18; // [rsp+90h] [rbp+30h] BYREF

  v5 = a5;
  v8 = a2;
  v15 = 0;
  v18 = 0;
  *a5 = 0;
  v16 = 0;
  v17 = 0;
  LastError = AllocateMemory(56, &v15, "OneXCreatePlapRuntimeState", 365);
  if ( LastError )
    goto LABEL_11;
  LastError = OneXQueryUserBlob(a1, v8, (_DWORD)a3, (unsigned int)&v18, (__int64)&v16);
  if ( LastError )
    goto LABEL_11;
  if ( a4 )
  {
    v11 = v15;
    CurrentProcess = GetCurrentProcess();
    v13 = GetCurrentProcess();
    if ( !DuplicateHandle(v13, a4, CurrentProcess, (LPHANDLE)(v11 + 8), 0, 0, 2u) )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_11;
    }
    *(_DWORD *)v15 |= 1u;
  }
  *(_DWORD *)v15 |= 2u;
  *(_DWORD *)(v15 + 16) = v18;
  *(_QWORD *)(v15 + 24) = v16;
  if ( (unsigned __int64)(2580 * v8) > 0xFFFFFFFF )
  {
    LastError = 534;
    goto LABEL_11;
  }
  LastError = OneXEncryptMemory(2580 * v8, a3, (__int64)&v17);
  if ( LastError )
  {
LABEL_11:
    FreeMemory(&v16, "OneXHlpFreeMemory", 414);
    OneXFreeRuntimeState(v15);
    return LastError;
  }
  *(_DWORD *)v15 |= 4u;
  *(_DWORD *)(v15 + 40) = v8;
  *(_QWORD *)(v15 + 48) = v17;
  *(_DWORD *)(v15 + 44) = 0;
  *v5 = v15;
  return LastError;
}

```

## disassembly

```asm
0x180031ed8  mov     [rsp-28h+arg_8], rbx
0x180031edd  mov     [rsp-28h+arg_10], rsi
0x180031ee2  push    rbp
0x180031ee3  push    rdi
0x180031ee4  push    r12
0x180031ee6  push    r14
0x180031ee8  push    r15
0x180031eea  mov     rbp, rsp
0x180031eed  sub     rsp, 60h
0x180031ef1  mov     r12, [rbp+arg_20]
0x180031ef5  mov     r14, r9
0x180031ef8  mov     r15, r8
0x180031efb  mov     esi, edx
0x180031efd  mov     rdi, rcx
0x180031f00  mov     [rbp+var_18], 0
0x180031f08  mov     r9d, 16Dh
0x180031f0e  mov     [rbp+arg_0], 0
0x180031f15  lea     r8, aOnexcreateplap; "OneXCreatePlapRuntimeState"
0x180031f1c  mov     qword ptr [r12], 0
0x180031f24  lea     rdx, [rbp+var_18]
0x180031f28  mov     [rbp+var_10], 0
0x180031f30  mov     ecx, 38h ; '8'
0x180031f35  mov     [rbp+var_8], 0
0x180031f3d  mov     [rbp+var_20], 0
0x180031f44  call    cs:__imp_AllocateMemory
0x180031f4a  mov     ebx, eax
0x180031f4c  test    eax, eax
0x180031f4e  jnz     loc_180032052
0x180031f54  lea     rax, [rbp+var_10]
0x180031f58  mov     r8, r15
0x180031f5b  lea     r9, [rbp+arg_0]
0x180031f5f  mov     qword ptr [rsp+60h+dwDesiredAccess], rax
0x180031f64  mov     edx, esi
0x180031f66  mov     rcx, rdi
0x180031f69  call    OneXQueryUserBlob
0x180031f6e  mov     ebx, eax
0x180031f70  test    eax, eax
0x180031f72  jnz     loc_180032052
0x180031f78  test    r14, r14
0x180031f7b  jz      short loc_180031FD6
0x180031f7d  mov     rdi, [rbp+var_18]
0x180031f81  call    cs:__imp_GetCurrentProcess
0x180031f87  mov     rbx, rax
0x180031f8a  call    cs:__imp_GetCurrentProcess
0x180031f90  mov     [rsp+60h+dwOptions], 2; dwOptions
0x180031f98  lea     r9, [rdi+8]; lpTargetHandle
0x180031f9c  mov     rcx, rax; hSourceProcessHandle
0x180031f9f  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x180031fa7  mov     r8, rbx; hTargetProcessHandle
0x180031faa  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x180031fb2  mov     rdx, r14; hSourceHandle
0x180031fb5  call    cs:__imp_DuplicateHandle
0x180031fbb  test    eax, eax
0x180031fbd  jnz     short loc_180031FCF
0x180031fbf  call    cs:__imp_GetLastError
0x180031fc5  mov     ebx, eax
0x180031fc7  test    eax, eax
0x180031fc9  jnz     loc_180032052
0x180031fcf  mov     rax, [rbp+var_18]
0x180031fd3  or      dword ptr [rax], 1
0x180031fd6  mov     rax, [rbp+var_18]
0x180031fda  or      dword ptr [rax], 2
0x180031fdd  mov     rcx, [rbp+var_18]
0x180031fe1  mov     eax, [rbp+arg_0]
0x180031fe4  mov     [rcx+10h], eax
0x180031fe7  mov     rcx, [rbp+var_18]
0x180031feb  mov     rax, [rbp+var_10]
0x180031fef  mov     [rcx+18h], rax
0x180031ff3  mov     eax, 0FFFFFFFFh
0x180031ff8  imul    rcx, rsi, 0A14h; Size
0x180031fff  cmp     rcx, rax
0x180032002  ja      short loc_18003204D
0x180032004  lea     rax, [rbp+var_8]
0x180032008  mov     rdx, r15; Src
0x18003200b  lea     r9, [rbp+var_20]
0x18003200f  mov     qword ptr [rsp+60h+dwDesiredAccess], rax; __int64
0x180032014  call    OneXEncryptMemory
0x180032019  mov     ebx, eax
0x18003201b  test    eax, eax
0x18003201d  jnz     short loc_180032052
0x18003201f  mov     rax, [rbp+var_18]
0x180032023  or      dword ptr [rax], 4
0x180032026  mov     rax, [rbp+var_18]
0x18003202a  mov     [rax+28h], esi
0x18003202d  mov     rcx, [rbp+var_18]
0x180032031  mov     rax, [rbp+var_8]
0x180032035  mov     [rcx+30h], rax
0x180032039  mov     eax, [rbp+var_20]
0x18003203c  mov     rcx, [rbp+var_18]
0x180032040  mov     [rcx+2Ch], eax
0x180032043  mov     rax, [rbp+var_18]
0x180032047  mov     [r12], rax
0x18003204b  jmp     short loc_180032072
0x18003204d  mov     ebx, 216h
0x180032052  mov     r8d, 19Eh
0x180032058  lea     rdx, aOnexhlpfreemem; "OneXHlpFreeMemory"
0x18003205f  lea     rcx, [rbp+var_10]
0x180032063  call    cs:__imp_FreeMemory
0x180032069  mov     rcx, [rbp+var_18]
0x18003206d  call    OneXFreeRuntimeState
0x180032072  lea     r11, [rsp+60h+var_s0]
0x180032077  mov     eax, ebx
0x180032079  mov     rbx, [r11+38h]
0x18003207d  mov     rsi, [r11+40h]
0x180032081  mov     rsp, r11
0x180032084  pop     r15
0x180032086  pop     r14
0x180032088  pop     r12
0x18003208a  pop     rdi
0x18003208b  pop     rbp
0x18003208c  retn
```
