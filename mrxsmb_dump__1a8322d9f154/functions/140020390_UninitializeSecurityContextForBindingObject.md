# UninitializeSecurityContextForBindingObject

- ea: `0x140020390`
- end: `0x14002052f`
- name: `UninitializeSecurityContextForBindingObject`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140020390`
- `0x1400383d0`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14002050b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14002050b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005e59a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14005e59a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002044b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002044b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400203d6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400203d6`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14002051e`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14002051e`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x140020482`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x140020482`
- `ksecdd!FreeCredentialsHandle` at `0x140020474`
- `ksecdd!FreeCredentialsHandle` at `0x140020474`
- `ksecdd!DeleteSecurityContext` at `0x1400204b7`
- `ksecdd!DeleteSecurityContext` at `0x1400204b7`

## pseudocode

```c
__int64 __fastcall UninitializeSecurityContextForBindingObject(struct _SecHandle *a1)
{
  ULONG_PTR dwLower; // rbp
  char v2; // r15
  __int64 v3; // r12
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  struct _SecHandle *v9; // rsi
  struct _SecHandle *v10; // r14
  __int64 v12; // rax
  __int64 v13; // rcx

  dwLower = a1[27].dwLower;
  v2 = 0;
  v3 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids, a1);
  }
  ExAcquirePushLockExclusiveEx(&a1[28].dwUpper, 0);
  if ( dwLower )
  {
    v8 = *(_QWORD *)(dwLower + 520);
    if ( v8 )
    {
      if ( !RxReferenceSiloAndAcquireRundown(v8, v5, v6, v7) )
      {
        v9 = a1 + 30;
        v10 = a1 + 29;
        goto LABEL_9;
      }
      v12 = *(_QWORD *)(dwLower + 520);
      if ( v12 )
        v13 = *(_QWORD *)(v12 + 40);
      else
        v13 = 0;
      v3 = PsAttachSiloToCurrentThread(v13);
      v2 = 1;
    }
  }
  v9 = a1 + 30;
  if ( a1[30].dwLower != -1 && a1[30].dwUpper != -1 )
    FreeCredentialsHandle(a1 + 30);
  v10 = a1 + 29;
  if ( a1[29].dwLower != -1 && a1[29].dwUpper != -1 )
    DeleteSecurityContext(a1 + 29);
  if ( v2 )
  {
    PsDetachSiloFromCurrentThread(v3);
    RxDereferenceSiloAndReleaseRundown(*(_QWORD *)(dwLower + 520));
  }
LABEL_9:
  a1[30].dwUpper = -1;
  v9->dwLower = -1;
  a1[29].dwUpper = -1;
  v10->dwLower = -1;
  return ExReleasePushLockExclusiveEx(&a1[28].dwUpper, 0);
}

```

## disassembly

```asm
0x140020390  push    rbx
0x140020392  push    rbp
0x140020393  push    rsi
0x140020394  push    rdi
0x140020395  push    r12
0x140020397  push    r14
0x140020399  push    r15
0x14002039b  sub     rsp, 20h
0x14002039f  mov     rbp, [rcx+1B0h]
0x1400203a6  xor     r15b, r15b
0x1400203a9  xor     r12d, r12d
0x1400203ac  mov     rbx, rcx
0x1400203af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400203b6  lea     rax, WPP_GLOBAL_Control
0x1400203bd  cmp     rcx, rax
0x1400203c0  jz      short loc_1400203CD
0x1400203c2  mov     eax, [rcx+2Ch]
0x1400203c5  test    al, 40h
0x1400203c7  jnz     loc_1400204C8
0x1400203cd  xor     edx, edx
0x1400203cf  lea     rcx, [rbx+1C8h]
0x1400203d6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400203dd  nop     dword ptr [rax+rax+00h]
0x1400203e2  test    rbp, rbp
0x1400203e5  jz      short loc_1400203F7
0x1400203e7  mov     rcx, [rbp+208h]
0x1400203ee  test    rcx, rcx
0x1400203f1  jnz     loc_140020482
0x1400203f7  lea     rsi, [rbx+1E0h]
0x1400203fe  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140020402  jnz     short loc_140020467
0x140020404  lea     r14, [rbx+1D0h]
0x14002040b  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x14002040f  jnz     loc_1400204A6
0x140020415  test    r15b, r15b
0x140020418  jnz     loc_140020508
0x14002041e  xor     edx, edx
0x140020420  mov     qword ptr [rbx+1E8h], 0FFFFFFFFFFFFFFFFh
0x14002042b  lea     rcx, [rbx+1C8h]
0x140020432  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140020439  mov     qword ptr [rbx+1D8h], 0FFFFFFFFFFFFFFFFh
0x140020444  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x14002044b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140020452  nop     dword ptr [rax+rax+00h]
0x140020457  add     rsp, 20h
0x14002045b  pop     r15
0x14002045d  pop     r14
0x14002045f  pop     r12
0x140020461  pop     rdi
0x140020462  pop     rsi
0x140020463  pop     rbp
0x140020464  pop     rbx
0x140020465  retn
0x140020467  cmp     qword ptr [rbx+1E8h], 0FFFFFFFFFFFFFFFFh
0x14002046f  jz      short loc_140020404
0x140020471  mov     rcx, rsi; phCredential
0x140020474  call    cs:__imp_FreeCredentialsHandle
0x14002047b  nop     dword ptr [rax+rax+00h]
0x140020480  jmp     short loc_140020404
0x140020482  call    cs:__imp_RxReferenceSiloAndAcquireRundown
0x140020489  nop     dword ptr [rax+rax+00h]
0x14002048e  test    rax, rax
0x140020491  jnz     short loc_1400204EF
0x140020493  lea     rsi, [rbx+1E0h]
0x14002049a  lea     r14, [rbx+1D0h]
0x1400204a1  jmp     loc_14002041E
0x1400204a6  cmp     qword ptr [rbx+1D8h], 0FFFFFFFFFFFFFFFFh
0x1400204ae  jz      loc_140020415
0x1400204b4  mov     rcx, r14; phContext
0x1400204b7  call    cs:__imp_DeleteSecurityContext
0x1400204be  nop     dword ptr [rax+rax+00h]
0x1400204c3  jmp     loc_140020415
0x1400204c8  cmp     byte ptr [rcx+29h], 4
0x1400204cc  jb      loc_1400203CD
0x1400204d2  mov     rcx, [rcx+18h]
0x1400204d6  lea     r8, WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids
0x1400204dd  mov     edx, 11h
0x1400204e2  mov     r9, rbx
0x1400204e5  call    WPP_SF_q
0x1400204ea  jmp     loc_1400203CD
0x1400204ef  mov     rax, [rbp+208h]
0x1400204f6  test    rax, rax
0x1400204f9  jz      loc_14005E598
0x1400204ff  mov     rcx, [rax+28h]
0x140020503  jmp     loc_14005E59A
0x140020508  mov     rcx, r12
0x14002050b  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140020512  nop     dword ptr [rax+rax+00h]
0x140020517  mov     rcx, [rbp+208h]
0x14002051e  call    cs:__imp_RxDereferenceSiloAndReleaseRundown
0x140020525  nop     dword ptr [rax+rax+00h]
0x14002052a  jmp     loc_14002041E
0x14005e598  xor     ecx, ecx
0x14005e59a  call    cs:__imp_PsAttachSiloToCurrentThread
0x14005e5a1  nop     dword ptr [rax+rax+00h]
0x14005e5a6  mov     r12, rax
0x14005e5a9  mov     r15b, 1
0x14005e5ac  jmp     loc_1400203F7
```
