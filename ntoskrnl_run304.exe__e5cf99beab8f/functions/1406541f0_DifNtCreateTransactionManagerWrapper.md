# DifNtCreateTransactionManagerWrapper

- ea: `0x1406541f0`
- end: `0x140654386`
- name: `DifNtCreateTransactionManagerWrapper`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x1406541f0`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransactionManager` at `0x1406542fa`
- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransactionManager` at `0x1406542fa`

## pseudocode

```c
__int64 __fastcall DifNtCreateTransactionManagerWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        OBJECT_ATTRIBUTES *a3,
        UNICODE_STRING *a4,
        ULONG CreateOptions,
        ULONG CommitStrength)
{
  __int64 APIThunkContextById; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r14
  int v13; // ecx
  BOOLEAN v14; // si
  _QWORD *i; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  BOOLEAN v18; // di
  _QWORD *j; // rbx
  __int128 v21; // [rsp+30h] [rbp-48h] BYREF
  __int128 v22; // [rsp+40h] [rbp-38h]
  __int128 v23; // [rsp+50h] [rbp-28h]
  __int64 v24; // [rsp+60h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+40h]

  v24 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(530);
  v12 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v13 = *(_DWORD *)(APIThunkContextById + 12);
    if ( (v13 & 0x18) != 0 )
    {
      *(_QWORD *)&v21 = retaddr;
    }
    else if ( (v13 & 4) != 0 )
    {
      *(_QWORD *)&v21 = DifGetReturnAddressForWrappers();
    }
    *((_QWORD *)&v23 + 1) = a1;
    *((_QWORD *)&v21 + 1) = __PAIR64__(CreateOptions, CommitStrength);
    LODWORD(v23) = a2;
    *((_QWORD *)&v22 + 1) = a3;
    *(_QWORD *)&v22 = a4;
    if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
      || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v12 + 32); i != (_QWORD *)(v12 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v21, v10, v11);
      }
      if ( v14 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v24) = NtCreateTransactionManager(a1, a2, a3, a4, CreateOptions, CommitStrength);
  if ( v12 )
  {
    if ( !VfDifRunningWithoutReboot && (v18 = 0, (VfOptionFlags & 0x800) == 0)
      || (v18 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v12 + 48); j != (_QWORD *)(v12 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v21, v16, v17);
      }
      if ( v18 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1406541f0  mov     [rsp-40h+TmHandle], rcx
0x1406541f5  push    rbp
0x1406541f6  push    rbx
0x1406541f7  push    rsi
0x1406541f8  push    rdi
0x1406541f9  push    r12
0x1406541fb  push    r13
0x1406541fd  push    r14
0x1406541ff  push    r15
0x140654201  mov     rbp, rsp
0x140654204  sub     rsp, 78h
0x140654208  xorps   xmm0, xmm0
0x14065420b  xor     eax, eax
0x14065420d  mov     ecx, 212h
0x140654212  mov     [rbp+var_18], rax
0x140654216  movups  [rbp+var_48], xmm0
0x14065421a  mov     r15, r9
0x14065421d  mov     r12, r8
0x140654220  movups  [rbp+var_38], xmm0
0x140654224  mov     r13d, edx
0x140654227  movups  [rbp+var_28], xmm0
0x14065422b  call    DifGetAPIThunkContextById
0x140654230  mov     r14, rax
0x140654233  test    rax, rax
0x140654236  jz      loc_1406542DF
0x14065423c  mov     ecx, [rax+0Ch]
0x14065423f  test    cl, 18h
0x140654242  jz      short loc_14065424E
0x140654244  mov     rcx, [rbp+40h]
0x140654248  mov     qword ptr [rbp+var_48], rcx
0x14065424c  jmp     short loc_14065425C
0x14065424e  test    cl, 4
0x140654251  jz      short loc_14065425C
0x140654253  call    DifGetReturnAddressForWrappers
0x140654258  mov     qword ptr [rbp+var_48], rax
0x14065425c  cmp     cs:VfDifRunningWithoutReboot, 0
0x140654263  mov     rax, [rbp+TmHandle]
0x140654267  mov     qword ptr [rbp+var_28+8], rax
0x14065426b  mov     eax, [rbp+arg_20]
0x14065426e  mov     dword ptr [rbp+var_48+0Ch], eax
0x140654271  mov     eax, [rbp+arg_28]
0x140654274  mov     dword ptr [rbp+var_48+8], eax
0x140654277  mov     dword ptr [rbp+var_28], r13d
0x14065427b  mov     qword ptr [rbp+var_38+8], r12
0x14065427f  mov     qword ptr [rbp+var_38], r15
0x140654283  jnz     short loc_140654294
0x140654285  xor     sil, sil
0x140654288  test    cs:VfOptionFlags, 800h
0x140654292  jz      short loc_1406542A7
0x140654294  lea     rcx, DifRebootlessRundown; RunRef
0x14065429b  call    ExAcquireRundownProtection_0
0x1406542a0  mov     sil, al
0x1406542a3  test    al, al
0x1406542a5  jz      short loc_1406542DF
0x1406542a7  lea     rdi, [r14+20h]
0x1406542ab  mov     rbx, [rdi]
0x1406542ae  jmp     short loc_1406542C9
0x1406542b0  lea     rax, [rbx-10h]
0x1406542b4  test    rax, rax
0x1406542b7  jz      short loc_1406542C6
0x1406542b9  mov     rax, [rax+8]
0x1406542bd  lea     rcx, [rbp+var_48]
0x1406542c1  call    _guard_dispatch_icall_no_overrides
0x1406542c6  mov     rbx, [rbx]
0x1406542c9  cmp     rbx, rdi
0x1406542cc  jnz     short loc_1406542B0
0x1406542ce  test    sil, sil
0x1406542d1  jz      short loc_1406542DF
0x1406542d3  lea     rcx, DifRebootlessRundown; RunRef
0x1406542da  call    ExReleaseRundownProtection_0
0x1406542df  mov     eax, [rbp+arg_28]
0x1406542e2  mov     r9, r15; LogFileName
0x1406542e5  mov     rcx, [rbp+TmHandle]; TmHandle
0x1406542e9  mov     r8, r12; ObjectAttributes
0x1406542ec  mov     [rsp+78h+CommitStrength], eax; CommitStrength
0x1406542f0  mov     edx, r13d; DesiredAccess
0x1406542f3  mov     eax, [rbp+arg_20]
0x1406542f6  mov     [rsp+78h+CreateOptions], eax; CreateOptions
0x1406542fa  call    cs:__imp_NtCreateTransactionManager
0x140654301  nop     dword ptr [rax+rax+00h]
0x140654306  mov     dword ptr [rbp+var_18], eax
0x140654309  test    r14, r14
0x14065430c  jz      short loc_140654371
0x14065430e  cmp     cs:VfDifRunningWithoutReboot, 0
0x140654315  jnz     short loc_140654326
0x140654317  xor     dil, dil
0x14065431a  test    cs:VfOptionFlags, 800h
0x140654324  jz      short loc_140654339
0x140654326  lea     rcx, DifRebootlessRundown; RunRef
0x14065432d  call    ExAcquireRundownProtection_0
0x140654332  mov     dil, al
0x140654335  test    al, al
0x140654337  jz      short loc_140654371
0x140654339  lea     rsi, [r14+30h]
0x14065433d  mov     rbx, [rsi]
0x140654340  jmp     short loc_14065435B
0x140654342  lea     rax, [rbx-10h]
0x140654346  test    rax, rax
0x140654349  jz      short loc_140654358
0x14065434b  mov     rax, [rax+8]
0x14065434f  lea     rcx, [rbp+var_48]
0x140654353  call    _guard_dispatch_icall_no_overrides
0x140654358  mov     rbx, [rbx]
0x14065435b  cmp     rbx, rsi
0x14065435e  jnz     short loc_140654342
0x140654360  test    dil, dil
0x140654363  jz      short loc_140654371
0x140654365  lea     rcx, DifRebootlessRundown; RunRef
0x14065436c  call    ExReleaseRundownProtection_0
0x140654371  mov     eax, dword ptr [rbp+var_18]
0x140654374  add     rsp, 78h
0x140654378  pop     r15
0x14065437a  pop     r14
0x14065437c  pop     r13
0x14065437e  pop     r12
0x140654380  pop     rdi
0x140654381  pop     rsi
0x140654382  pop     rbx
0x140654383  pop     rbp
0x140654384  retn
```
