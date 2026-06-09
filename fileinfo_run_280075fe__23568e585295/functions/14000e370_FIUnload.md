# FIUnload

- ea: `0x14000e370`
- end: `0x14000e597`
- name: `FIUnload`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140018078`

## callees

- `0x14000d24c`
- `0x14000e370`
- `0x14000f810`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000e424`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000e424`
- `ntoskrnl!EtwUnregister` at `0x14000e49d`
- `ntoskrnl!EtwUnregister` at `0x14000e57d`
- `ntoskrnl!EtwUnregister` at `0x14000e49d`
- `ntoskrnl!EtwUnregister` at `0x14000e57d`
- `ntoskrnl!PfFileInfoNotify` at `0x14000e3fd`
- `ntoskrnl!PfFileInfoNotify` at `0x14000e3fd`
- `ntoskrnl!IoDeleteDevice` at `0x14000e437`
- `ntoskrnl!IoDeleteDevice` at `0x14000e437`
- `ntoskrnl!ExDeleteTimer` at `0x14000e3b4`
- `ntoskrnl!ExDeleteTimer` at `0x14000e3b4`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x14000e472`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x14000e472`
- `FLTMGR!FltUnregisterFilter` at `0x14000e485`
- `FLTMGR!FltUnregisterFilter` at `0x14000e485`

## pseudocode

```c
__int64 __fastcall FIUnload(char a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v4; // rcx
  int v5; // edi
  unsigned __int64 v6; // rax
  _QWORD *v7; // rdx
  unsigned __int64 v8; // rbx
  char v9; // al
  REGHANDLE v10; // rcx
  __int128 v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 *v12; // [rsp+30h] [rbp-18h]

  v12 = 0;
  v11 = 0;
  if ( (a1 & 1) == 0 )
    return 3221225659LL;
  dword_1400093C0 |= 8u;
  if ( qword_1400099C0 )
  {
    LOBYTE(a3) = 1;
    LOBYTE(a2) = 1;
    ExDeleteTimer(qword_1400099C0, a2, a3, 0, v11, *((_QWORD *)&v11 + 1), v12);
  }
  if ( (dword_1400093C0 & 2) != 0 )
  {
    *((_QWORD *)&v11 + 1) = 8;
    dword_1400093C0 &= ~2u;
    *(_QWORD *)&v11 = 0xB0000000FLL;
    v12 = &qword_1400094E8;
    PfFileInfoNotify(&v11);
  }
  if ( DeviceObject )
  {
    if ( (dword_1400093C0 & 4) != 0 )
      IoWMIRegistrationControl(DeviceObject, 2u);
    IoDeleteDevice(DeviceObject);
    DeviceObject = 0;
  }
  if ( (dword_1400093C0 & 1) != 0 )
  {
    dword_1400093C0 &= ~1u;
    FltDeleteExtraCreateParameterLookasideList((PFLT_FILTER)FIGlobals, qword_1400095C0, 0);
    FltUnregisterFilter((PFLT_FILTER)FIGlobals);
  }
  if ( qword_140009A28 )
  {
    EtwUnregister(qword_140009A28);
    qword_140009A28 = 0;
  }
  FIFileObjectContextsDeleteAll();
  v4 = qword_140009948;
  if ( (qword_140009950 & 1) != 0 && qword_140009948 )
    v4 = (unsigned __int64)&qword_140009948 ^ qword_140009948;
  v5 = qword_140009950 & 1;
  if ( v4 )
  {
    while ( 1 )
    {
      v6 = *(_QWORD *)v4;
      if ( *(_QWORD *)v4 )
        break;
      v7 = (_QWORD *)(v4 + 8);
      v6 = *(_QWORD *)(v4 + 8);
      if ( v6 )
      {
LABEL_22:
        if ( v5 )
          v4 ^= v6;
        else
          v4 = v6;
        *v7 = 0;
      }
      else
      {
        v8 = *(_QWORD *)(v4 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v5 && v8 )
          v8 ^= v4;
        FIPfConflictTelemetryTreeDelete((PVOID)v4);
        if ( !v8 )
          goto LABEL_31;
        v4 = v8;
      }
    }
    v7 = (_QWORD *)v4;
    goto LABEL_22;
  }
LABEL_31:
  v9 = qword_140009950;
  qword_140009948 = 0;
  qword_140009950 = 0;
  if ( (v9 & 1) != 0 )
    LOBYTE(qword_140009950) = 1;
  v10 = RegHandle;
  dword_140009000 = 0;
  RegHandle = 0;
  EtwUnregister(v10);
  return 0;
}

```

## disassembly

```asm
0x14000e370  mov     [rsp+arg_8], rbx
0x14000e375  push    rdi
0x14000e376  sub     rsp, 40h
0x14000e37a  xor     eax, eax
0x14000e37c  xorps   xmm0, xmm0
0x14000e37f  mov     [rsp+48h+var_18], rax
0x14000e384  movups  [rsp+48h+var_28], xmm0
0x14000e389  test    cl, 1
0x14000e38c  jnz     short loc_14000E398
0x14000e38e  mov     eax, 0C00000BBh
0x14000e393  jmp     loc_14000E58B
0x14000e398  or      cs:dword_1400093C0, 8
0x14000e39f  mov     rcx, cs:qword_1400099C0
0x14000e3a6  test    rcx, rcx
0x14000e3a9  jz      short loc_14000E3C0
0x14000e3ab  mov     r8b, 1
0x14000e3ae  xor     r9d, r9d
0x14000e3b1  mov     dl, r8b
0x14000e3b4  call    cs:__imp_ExDeleteTimer
0x14000e3bb  nop     dword ptr [rax+rax+00h]
0x14000e3c0  mov     eax, cs:dword_1400093C0
0x14000e3c6  test    al, 2
0x14000e3c8  jz      short loc_14000E409
0x14000e3ca  and     eax, 0FFFFFFFDh
0x14000e3cd  mov     qword ptr [rsp+48h+var_28+8], 8
0x14000e3d6  mov     cs:dword_1400093C0, eax
0x14000e3dc  lea     rcx, [rsp+48h+var_28]
0x14000e3e1  lea     rax, qword_1400094E8
0x14000e3e8  mov     dword ptr [rsp+48h+var_28], 0Fh
0x14000e3f0  mov     [rsp+48h+var_18], rax
0x14000e3f5  mov     dword ptr [rsp+48h+var_28+4], 0Bh
0x14000e3fd  call    cs:__imp_PfFileInfoNotify
0x14000e404  nop     dword ptr [rax+rax+00h]
0x14000e409  mov     rcx, cs:DeviceObject; DeviceObject
0x14000e410  test    rcx, rcx
0x14000e413  jz      short loc_14000E44E
0x14000e415  mov     eax, cs:dword_1400093C0
0x14000e41b  test    al, 4
0x14000e41d  jz      short loc_14000E430
0x14000e41f  mov     edx, 2; Action
0x14000e424  call    cs:__imp_IoWMIRegistrationControl
0x14000e42b  nop     dword ptr [rax+rax+00h]
0x14000e430  mov     rcx, cs:DeviceObject; DeviceObject
0x14000e437  call    cs:__imp_IoDeleteDevice
0x14000e43e  nop     dword ptr [rax+rax+00h]
0x14000e443  mov     cs:DeviceObject, 0
0x14000e44e  mov     eax, cs:dword_1400093C0
0x14000e454  test    al, 1
0x14000e456  jz      short loc_14000E491
0x14000e458  mov     rcx, cs:FIGlobals; Filter
0x14000e45f  lea     rdx, qword_1400095C0; Lookaside
0x14000e466  and     eax, 0FFFFFFFEh
0x14000e469  xor     r8d, r8d; Flags
0x14000e46c  mov     cs:dword_1400093C0, eax
0x14000e472  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x14000e479  nop     dword ptr [rax+rax+00h]
0x14000e47e  mov     rcx, cs:FIGlobals; Filter
0x14000e485  call    cs:__imp_FltUnregisterFilter
0x14000e48c  nop     dword ptr [rax+rax+00h]
0x14000e491  mov     rcx, cs:qword_140009A28; RegHandle
0x14000e498  test    rcx, rcx
0x14000e49b  jz      short loc_14000E4B4
0x14000e49d  call    cs:__imp_EtwUnregister
0x14000e4a4  nop     dword ptr [rax+rax+00h]
0x14000e4a9  mov     cs:qword_140009A28, 0
0x14000e4b4  call    FIFileObjectContextsDeleteAll
0x14000e4b9  movzx   eax, byte ptr cs:xmmword_140009948+8
0x14000e4c0  mov     rcx, qword ptr cs:xmmword_140009948
0x14000e4c7  test    al, 1
0x14000e4c9  jz      short loc_14000E4DA
0x14000e4cb  test    rcx, rcx
0x14000e4ce  jz      short loc_14000E4DA
0x14000e4d0  lea     rdx, xmmword_140009948
0x14000e4d7  xor     rcx, rdx; P
0x14000e4da  mov     edi, eax
0x14000e4dc  and     edi, 1
0x14000e4df  test    rcx, rcx
0x14000e4e2  jz      short loc_14000E537
0x14000e4e4  mov     rax, [rcx]
0x14000e4e7  test    rax, rax
0x14000e4ea  jz      short loc_14000E4F1
0x14000e4ec  mov     rdx, rcx
0x14000e4ef  jmp     short loc_14000E4FD
0x14000e4f1  lea     rdx, [rcx+8]
0x14000e4f5  mov     rax, [rdx]
0x14000e4f8  test    rax, rax
0x14000e4fb  jz      short loc_14000E512
0x14000e4fd  test    edi, edi
0x14000e4ff  jz      short loc_14000E506
0x14000e501  xor     rcx, rax
0x14000e504  jmp     short loc_14000E509
0x14000e506  mov     rcx, rax
0x14000e509  mov     qword ptr [rdx], 0
0x14000e510  jmp     short loc_14000E4E4
0x14000e512  mov     rbx, [rcx+10h]
0x14000e516  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000e51a  test    edi, edi
0x14000e51c  jz      short loc_14000E526
0x14000e51e  test    rbx, rbx
0x14000e521  jz      short loc_14000E526
0x14000e523  xor     rbx, rcx
0x14000e526  xor     edx, edx
0x14000e528  call    FIPfConflictTelemetryTreeDelete
0x14000e52d  test    rbx, rbx
0x14000e530  jz      short loc_14000E537
0x14000e532  mov     rcx, rbx
0x14000e535  jmp     short loc_14000E4E4
0x14000e537  movzx   eax, byte ptr cs:xmmword_140009948+8
0x14000e53e  mov     qword ptr cs:xmmword_140009948, 0
0x14000e549  mov     qword ptr cs:xmmword_140009948+8, 0
0x14000e554  bt      eax, 0
0x14000e558  jnb     short loc_14000E561
0x14000e55a  mov     byte ptr cs:xmmword_140009948+8, 1
0x14000e561  mov     rcx, cs:RegHandle; RegHandle
0x14000e568  mov     cs:dword_140009000, 0
0x14000e572  mov     cs:RegHandle, 0
0x14000e57d  call    cs:__imp_EtwUnregister
0x14000e584  nop     dword ptr [rax+rax+00h]
0x14000e589  xor     eax, eax
0x14000e58b  mov     rbx, [rsp+48h+arg_8]
0x14000e590  add     rsp, 40h
0x14000e594  pop     rdi
0x14000e595  retn
```
