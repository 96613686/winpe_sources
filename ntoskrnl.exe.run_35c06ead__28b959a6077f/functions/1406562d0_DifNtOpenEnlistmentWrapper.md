# DifNtOpenEnlistmentWrapper

- ea: `0x1406562d0`
- end: `0x14065645d`
- name: `DifNtOpenEnlistmentWrapper`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x1406562d0`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtOpenEnlistment` at `0x1406563d1`
- `ext-ms-win-ntos-tm-l1-1-0!NtOpenEnlistment` at `0x1406563d1`

## pseudocode

```c
__int64 __fastcall DifNtOpenEnlistmentWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        void *a3,
        GUID *a4,
        OBJECT_ATTRIBUTES *ObjectAttributes)
{
  __int64 APIThunkContextById; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r14
  int v13; // ecx
  BOOLEAN v14; // si
  _QWORD *i; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  BOOLEAN v19; // di
  _QWORD *j; // rbx
  __int128 v22; // [rsp+30h] [rbp-48h] BYREF
  __int128 v23; // [rsp+40h] [rbp-38h]
  __int128 v24; // [rsp+50h] [rbp-28h]
  __int64 v25; // [rsp+60h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+40h]

  v25 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(539);
  v12 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v13 = *(_DWORD *)(APIThunkContextById + 12);
    if ( (v13 & 0x18) != 0 )
    {
      *(_QWORD *)&v22 = retaddr;
    }
    else if ( (v13 & 4) != 0 )
    {
      *(_QWORD *)&v22 = DifGetReturnAddressForWrappers();
    }
    *((_QWORD *)&v24 + 1) = a1;
    *((_QWORD *)&v22 + 1) = ObjectAttributes;
    LODWORD(v24) = a2;
    *((_QWORD *)&v23 + 1) = a3;
    *(_QWORD *)&v23 = a4;
    if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
      || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v12 + 32); i != (_QWORD *)(v12 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v22, v9, v10, v11);
      }
      if ( v14 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v25) = NtOpenEnlistment(a1, a2, a3, a4, ObjectAttributes);
  if ( v12 )
  {
    if ( !VfDifRunningWithoutReboot && (v19 = 0, (VfOptionFlags & 0x800) == 0)
      || (v19 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v12 + 48); j != (_QWORD *)(v12 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v22, v16, v17, v18);
      }
      if ( v19 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1406562d0  mov     [rsp-40h+EnlistmentHandle], rcx
0x1406562d5  push    rbp
0x1406562d6  push    rbx
0x1406562d7  push    rsi
0x1406562d8  push    rdi
0x1406562d9  push    r12
0x1406562db  push    r13
0x1406562dd  push    r14
0x1406562df  push    r15
0x1406562e1  mov     rbp, rsp
0x1406562e4  sub     rsp, 78h
0x1406562e8  xorps   xmm0, xmm0
0x1406562eb  xor     eax, eax
0x1406562ed  mov     ecx, 21Bh
0x1406562f2  mov     [rbp+var_18], rax
0x1406562f6  movups  [rbp+var_48], xmm0
0x1406562fa  mov     r15, r9
0x1406562fd  mov     r12, r8
0x140656300  movups  [rbp+var_38], xmm0
0x140656304  mov     r13d, edx
0x140656307  movups  [rbp+var_28], xmm0
0x14065630b  call    DifGetAPIThunkContextById
0x140656310  mov     r14, rax
0x140656313  test    rax, rax
0x140656316  jz      loc_1406563BB
0x14065631c  mov     ecx, [rax+0Ch]
0x14065631f  test    cl, 18h
0x140656322  jz      short loc_14065632E
0x140656324  mov     rcx, [rbp+40h]
0x140656328  mov     qword ptr [rbp+var_48], rcx
0x14065632c  jmp     short loc_14065633C
0x14065632e  test    cl, 4
0x140656331  jz      short loc_14065633C
0x140656333  call    DifGetReturnAddressForWrappers
0x140656338  mov     qword ptr [rbp+var_48], rax
0x14065633c  cmp     cs:VfDifRunningWithoutReboot, 0
0x140656343  mov     rax, [rbp+EnlistmentHandle]
0x140656347  mov     qword ptr [rbp+var_28+8], rax
0x14065634b  mov     rax, [rbp+arg_20]
0x14065634f  mov     qword ptr [rbp+var_48+8], rax
0x140656353  mov     dword ptr [rbp+var_28], r13d
0x140656357  mov     qword ptr [rbp+var_38+8], r12
0x14065635b  mov     qword ptr [rbp+var_38], r15
0x14065635f  jnz     short loc_140656370
0x140656361  xor     sil, sil
0x140656364  test    cs:VfOptionFlags, 800h
0x14065636e  jz      short loc_140656383
0x140656370  lea     rcx, DifRebootlessRundown; RunRef
0x140656377  call    ExAcquireRundownProtection_0
0x14065637c  mov     sil, al
0x14065637f  test    al, al
0x140656381  jz      short loc_1406563BB
0x140656383  lea     rdi, [r14+20h]
0x140656387  mov     rbx, [rdi]
0x14065638a  jmp     short loc_1406563A5
0x14065638c  lea     rax, [rbx-10h]
0x140656390  test    rax, rax
0x140656393  jz      short loc_1406563A2
0x140656395  mov     rax, [rax+8]
0x140656399  lea     rcx, [rbp+var_48]
0x14065639d  call    _guard_dispatch_icall_no_overrides
0x1406563a2  mov     rbx, [rbx]
0x1406563a5  cmp     rbx, rdi
0x1406563a8  jnz     short loc_14065638C
0x1406563aa  test    sil, sil
0x1406563ad  jz      short loc_1406563BB
0x1406563af  lea     rcx, DifRebootlessRundown; RunRef
0x1406563b6  call    ExReleaseRundownProtection_0
0x1406563bb  mov     rax, [rbp+arg_20]
0x1406563bf  mov     r9, r15; EnlistmentGuid
0x1406563c2  mov     rcx, [rbp+EnlistmentHandle]; EnlistmentHandle
0x1406563c6  mov     r8, r12; ResourceManagerHandle
0x1406563c9  mov     edx, r13d; DesiredAccess
0x1406563cc  mov     [rsp+78h+ObjectAttributes], rax; ObjectAttributes
0x1406563d1  call    cs:__imp_NtOpenEnlistment
0x1406563d8  nop     dword ptr [rax+rax+00h]
0x1406563dd  mov     dword ptr [rbp+var_18], eax
0x1406563e0  test    r14, r14
0x1406563e3  jz      short loc_140656448
0x1406563e5  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406563ec  jnz     short loc_1406563FD
0x1406563ee  xor     dil, dil
0x1406563f1  test    cs:VfOptionFlags, 800h
0x1406563fb  jz      short loc_140656410
0x1406563fd  lea     rcx, DifRebootlessRundown; RunRef
0x140656404  call    ExAcquireRundownProtection_0
0x140656409  mov     dil, al
0x14065640c  test    al, al
0x14065640e  jz      short loc_140656448
0x140656410  lea     rsi, [r14+30h]
0x140656414  mov     rbx, [rsi]
0x140656417  jmp     short loc_140656432
0x140656419  lea     rax, [rbx-10h]
0x14065641d  test    rax, rax
0x140656420  jz      short loc_14065642F
0x140656422  mov     rax, [rax+8]
0x140656426  lea     rcx, [rbp+var_48]
0x14065642a  call    _guard_dispatch_icall_no_overrides
0x14065642f  mov     rbx, [rbx]
0x140656432  cmp     rbx, rsi
0x140656435  jnz     short loc_140656419
0x140656437  test    dil, dil
0x14065643a  jz      short loc_140656448
0x14065643c  lea     rcx, DifRebootlessRundown; RunRef
0x140656443  call    ExReleaseRundownProtection_0
0x140656448  mov     eax, dword ptr [rbp+var_18]
0x14065644b  add     rsp, 78h
0x14065644f  pop     r15
0x140656451  pop     r14
0x140656453  pop     r13
0x140656455  pop     r12
0x140656457  pop     rdi
0x140656458  pop     rsi
0x140656459  pop     rbx
0x14065645a  pop     rbp
0x14065645b  retn
```
