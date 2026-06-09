# HsmiCreateAllocateECPTags

- ea: `0x140049f20`
- end: `0x14004a29d`
- name: `HsmiCreateAllocateECPTags`
- size: `893`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140049868`

## callees

- `0x140003c50`
- `0x14001e600`
- `0x140049f20`

## import_xrefs

- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14004a145`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14004a145`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004a0ee`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004a0ee`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140049f48`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140049f48`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x14004a0d8`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x14004a0d8`
- `FLTMGR!FltObjectReference` at `0x14004a1ea`
- `FLTMGR!FltObjectReference` at `0x14004a1ea`
- `FLTMGR!FltAddOpenReparseEntry` at `0x14004a015`
- `FLTMGR!FltAddOpenReparseEntry` at `0x14004a015`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14004a11d`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14004a11d`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14004a1d7`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14004a1d7`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14004a194`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14004a194`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14004a27e`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14004a27e`
- `FLTMGR!FltObjectDereference` at `0x14004a259`
- `FLTMGR!FltObjectDereference` at `0x14004a259`

## pseudocode

```c
__int64 __fastcall HsmiCreateAllocateECPTags(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  unsigned int i; // edx
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  int v9; // ecx
  __int64 v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rax
  NTSTATUS v13; // edi
  __int64 v14; // rdx
  _QWORD *v15; // r8
  _QWORD *v16; // rcx
  __int64 v18; // rcx
  IRP *v19; // rsi
  struct _ECP_LIST *UserBuffer; // rdx
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  NTSTATUS ExtraCreateParameter; // eax
  PVOID EcpContext; // [rsp+80h] [rbp+18h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp+20h] BYREF

  EcpContext = 0;
  v4 = ExAllocateFromPagedLookasideList(&stru_1400292C0);
  v5 = v4;
  if ( !v4 )
  {
    v13 = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
    return (unsigned int)v13;
  }
  memset(v4, 0, 0x300u);
  for ( i = 0; i < 0x10; ++i )
  {
    v7 = &v5[6 * i];
    *((_DWORD *)v7 + 5) = 0x80000000;
    *((_WORD *)v7 + 20) = 48;
    if ( i )
    {
      v8 = (_QWORD *)v5[1];
      if ( (_QWORD *)*v8 != v5 )
        goto LABEL_38;
      *v7 = v5;
      v7[1] = v8;
      *v8 = v7;
      v5[1] = v7;
    }
    else
    {
      v7[1] = v7;
      *v7 = v7;
    }
    v9 = dword_140029670 | ((i & 0xF) << 12);
    *((_DWORD *)v7 + 4) = v9;
    if ( (v9 & 0x2000) == 0 )
      *((_DWORD *)v7 + 5) |= 6u;
  }
  v10 = *v5;
  if ( *(_QWORD **)(*v5 + 8LL) != v5 )
    goto LABEL_38;
  v11 = (_QWORD *)v5[1];
  if ( (_QWORD *)*v11 != v5 )
    goto LABEL_38;
  *v11 = v10;
  *(_QWORD *)(v10 + 8) = v11;
  v5[1] = v5;
  *v5 = v5;
  v12 = *(_QWORD *)(a1 + 16);
  if ( !*(_BYTE *)(v12 + 4) )
  {
    v13 = FltAddOpenReparseEntry(Filter, a1, v5);
    HsmDbgBreakOnStatus(v13);
    if ( v13 >= 0 )
      goto LABEL_13;
    goto LABEL_20;
  }
  v19 = *(IRP **)(v12 + 24);
  UserBuffer = (struct _ECP_LIST *)v19->UserBuffer;
  EcpList = UserBuffer;
  if ( UserBuffer )
  {
    ExtraCreateParameter = FltFindExtraCreateParameter(Filter, UserBuffer, &ECP_TYPE_OPEN_REPARSE_GUID, &EcpContext, 0);
    HsmDbgBreakOnStatus(ExtraCreateParameter);
  }
  else
  {
    v13 = FltAllocateExtraCreateParameterList(Filter, 0, &EcpList);
    HsmDbgBreakOnStatus(v13);
    if ( v13 < 0 )
      goto LABEL_20;
    FsRtlSetEcpListIntoIrp(v19, EcpList);
  }
  if ( EcpContext )
    goto LABEL_30;
  v13 = FltAllocateExtraCreateParameterFromLookasideList(
          Filter,
          &ECP_TYPE_OPEN_REPARSE_GUID,
          0x10u,
          0,
          0,
          qword_140029140,
          &EcpContext);
  HsmDbgBreakOnStatus(v13);
  if ( v13 < 0 )
  {
LABEL_20:
    if ( (_QWORD *)*v5 == v5 )
    {
LABEL_23:
      ExFreeToPagedLookasideList(&stru_1400292C0, v5);
      return (unsigned int)v13;
    }
    *(_QWORD *)(v5[90] + 8LL) = v5;
    v18 = v5[90];
    *v5 = v18;
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 16) + 4LL) )
    {
      FltRemoveOpenReparseEntry(Filter, a1, v5);
      goto LABEL_23;
    }
    if ( *(_QWORD **)(v18 + 8) == v5 )
    {
      v24 = (_QWORD *)v5[1];
      if ( (_QWORD *)*v24 == v5 )
      {
        *v24 = v18;
        *(_QWORD *)(v18 + 8) = v24;
        FltObjectDereference(Filter);
        goto LABEL_23;
      }
    }
LABEL_38:
    __fastfail(3u);
  }
  v21 = EcpContext;
  *((_QWORD *)EcpContext + 1) = EcpContext;
  *v21 = v21;
  FltInsertExtraCreateParameter(Filter, EcpList, EcpContext);
LABEL_30:
  v13 = FltObjectReference(Filter);
  HsmDbgBreakOnStatus(v13);
  if ( v13 < 0 )
    goto LABEL_20;
  v22 = EcpContext;
  v23 = *(_QWORD *)EcpContext;
  if ( *(PVOID *)(*(_QWORD *)EcpContext + 8LL) != EcpContext )
    goto LABEL_38;
  *v5 = v23;
  v5[1] = v22;
  *(_QWORD *)(v23 + 8) = v5;
  *v22 = v5;
LABEL_13:
  v14 = *v5;
  if ( *(_QWORD *)(*(_QWORD *)*v5 + 8LL) != *v5 )
    goto LABEL_38;
  v15 = *(_QWORD **)(v14 + 8);
  if ( *v15 != v14 )
    goto LABEL_38;
  v16 = v5 + 6;
  if ( *(_QWORD **)(v5[6] + 8LL) != v5 + 6 || *(_QWORD **)v5[7] != v16 )
    goto LABEL_38;
  *v15 = v16;
  *(_QWORD *)(v14 + 8) = v5[7];
  *(_QWORD *)v5[7] = v14;
  v5[7] = v15;
  *a2 = v5;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140049f20  mov     [rsp+arg_0], rbx
0x140049f25  push    rbp
0x140049f26  push    rsi
0x140049f27  push    rdi
0x140049f28  push    r14
0x140049f2a  push    r15
0x140049f2c  sub     rsp, 40h
0x140049f30  mov     rbp, rcx
0x140049f33  xor     r15d, r15d
0x140049f36  lea     rcx, stru_1400292C0; Lookaside
0x140049f3d  mov     [rsp+68h+arg_10], r15
0x140049f45  mov     r14, rdx
0x140049f48  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140049f4f  nop     dword ptr [rax+rax+00h]
0x140049f54  mov     rbx, rax
0x140049f57  test    rax, rax
0x140049f5a  jz      loc_14004A22B
0x140049f60  xor     edx, edx; Val
0x140049f62  mov     r8d, 300h; Size
0x140049f68  mov     rcx, rax; void *
0x140049f6b  call    memset
0x140049f70  mov     edx, r15d
0x140049f73  mov     eax, edx
0x140049f75  lea     rax, [rax+rax*2]
0x140049f79  shl     rax, 4
0x140049f7d  add     rax, rbx
0x140049f80  mov     dword ptr [rax+14h], 80000000h
0x140049f87  mov     word ptr [rax+28h], 30h ; '0'
0x140049f8d  test    edx, edx
0x140049f8f  jz      loc_14004A097
0x140049f95  mov     rcx, [rbx+8]
0x140049f99  cmp     [rcx], rbx
0x140049f9c  jnz     loc_14004A296
0x140049fa2  mov     [rax], rbx
0x140049fa5  mov     [rax+8], rcx
0x140049fa9  mov     [rcx], rax
0x140049fac  mov     [rbx+8], rax
0x140049fb0  mov     ecx, edx
0x140049fb2  and     ecx, 0Fh
0x140049fb5  shl     ecx, 0Ch
0x140049fb8  or      ecx, cs:dword_140029670
0x140049fbe  mov     [rax+10h], ecx
0x140049fc1  bt      ecx, 0Dh
0x140049fc5  jb      short loc_140049FCB
0x140049fc7  or      dword ptr [rax+14h], 6
0x140049fcb  inc     edx
0x140049fcd  cmp     edx, 10h
0x140049fd0  jb      short loc_140049F73
0x140049fd2  mov     rax, [rbx]
0x140049fd5  cmp     [rax+8], rbx
0x140049fd9  jnz     loc_14004A296
0x140049fdf  mov     rcx, [rbx+8]
0x140049fe3  cmp     [rcx], rbx
0x140049fe6  jnz     loc_14004A296
0x140049fec  mov     [rcx], rax
0x140049fef  mov     [rax+8], rcx
0x140049ff3  mov     [rbx+8], rbx
0x140049ff7  mov     [rbx], rbx
0x140049ffa  mov     rax, [rbp+10h]
0x140049ffe  mov     rcx, cs:Filter; Filter
0x14004a005  cmp     [rax+4], r15b
0x14004a009  jnz     loc_14004A0FC
0x14004a00f  mov     r8, rbx
0x14004a012  mov     rdx, rbp
0x14004a015  call    cs:__imp_FltAddOpenReparseEntry
0x14004a01c  nop     dword ptr [rax+rax+00h]
0x14004a021  mov     ecx, eax
0x14004a023  mov     edi, eax
0x14004a025  call    HsmDbgBreakOnStatus
0x14004a02a  test    edi, edi
0x14004a02c  js      short loc_14004A0A3
0x14004a02e  mov     rdx, [rbx]
0x14004a031  mov     rax, [rdx]
0x14004a034  cmp     [rax+8], rdx
0x14004a038  jnz     loc_14004A296
0x14004a03e  mov     r8, [rdx+8]
0x14004a042  cmp     [r8], rdx
0x14004a045  jnz     loc_14004A296
0x14004a04b  mov     rax, [rbx+30h]
0x14004a04f  lea     rcx, [rbx+30h]
0x14004a053  cmp     [rax+8], rcx
0x14004a057  jnz     loc_14004A296
0x14004a05d  mov     rax, [rcx+8]
0x14004a061  cmp     [rax], rcx
0x14004a064  jnz     loc_14004A296
0x14004a06a  mov     [r8], rcx
0x14004a06d  mov     rax, [rcx+8]
0x14004a071  mov     [rdx+8], rax
0x14004a075  mov     rax, [rcx+8]
0x14004a079  mov     [rax], rdx
0x14004a07c  mov     [rcx+8], r8
0x14004a080  mov     [r14], rbx
0x14004a083  mov     rbx, [rsp+68h+arg_0]
0x14004a088  mov     eax, edi
0x14004a08a  add     rsp, 40h
0x14004a08e  pop     r15
0x14004a090  pop     r14
0x14004a092  pop     rdi
0x14004a093  pop     rsi
0x14004a094  pop     rbp
0x14004a095  retn
0x14004a097  mov     [rax+8], rax
0x14004a09b  mov     [rax], rax
0x14004a09e  jmp     loc_140049FB0
0x14004a0a3  cmp     [rbx], rbx
0x14004a0a6  jz      short loc_14004A0E4
0x14004a0a8  mov     rax, [rbx+2D0h]
0x14004a0af  mov     [rax+8], rbx
0x14004a0b3  mov     rcx, [rbx+2D0h]
0x14004a0ba  mov     [rbx], rcx
0x14004a0bd  mov     rax, [rbp+10h]
0x14004a0c1  cmp     [rax+4], r15b
0x14004a0c5  jnz     loc_14004A23C
0x14004a0cb  mov     rcx, cs:Filter
0x14004a0d2  mov     r8, rbx
0x14004a0d5  mov     rdx, rbp
0x14004a0d8  call    cs:__imp_FltRemoveOpenReparseEntry
0x14004a0df  nop     dword ptr [rax+rax+00h]
0x14004a0e4  mov     rdx, rbx; Entry
0x14004a0e7  lea     rcx, stru_1400292C0; Lookaside
0x14004a0ee  call    cs:__imp_ExFreeToPagedLookasideList
0x14004a0f5  nop     dword ptr [rax+rax+00h]
0x14004a0fa  jmp     short loc_14004A083
0x14004a0fc  mov     rsi, [rax+18h]
0x14004a100  mov     rdx, [rsi+70h]; EcpList
0x14004a104  mov     [rsp+68h+EcpList], rdx
0x14004a10c  test    rdx, rdx
0x14004a10f  jnz     loc_14004A26A
0x14004a115  lea     r8, [rsp+68h+EcpList]; EcpList
0x14004a11d  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14004a124  nop     dword ptr [rax+rax+00h]
0x14004a129  mov     ecx, eax
0x14004a12b  mov     edi, eax
0x14004a12d  call    HsmDbgBreakOnStatus
0x14004a132  test    edi, edi
0x14004a134  js      loc_14004A0A3
0x14004a13a  mov     rdx, [rsp+68h+EcpList]; EcpList
0x14004a142  mov     rcx, rsi; Irp
0x14004a145  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x14004a14c  nop     dword ptr [rax+rax+00h]
0x14004a151  cmp     [rsp+68h+arg_10], r15
0x14004a159  jnz     loc_14004A1E3
0x14004a15f  mov     rcx, cs:Filter; Filter
0x14004a166  lea     rax, [rsp+68h+arg_10]
0x14004a16e  mov     [rsp+68h+EcpContext], rax; EcpContext
0x14004a173  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x14004a17a  lea     rax, qword_140029140
0x14004a181  xor     r9d, r9d; Flags
0x14004a184  mov     [rsp+68h+LookasideList], rax; LookasideList
0x14004a189  mov     r8d, 10h; SizeOfContext
0x14004a18f  mov     [rsp+68h+CleanupCallback], r15; CleanupCallback
0x14004a194  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14004a19b  nop     dword ptr [rax+rax+00h]
0x14004a1a0  mov     ecx, eax
0x14004a1a2  mov     edi, eax
0x14004a1a4  call    HsmDbgBreakOnStatus
0x14004a1a9  test    edi, edi
0x14004a1ab  js      loc_14004A0A3
0x14004a1b1  mov     rax, [rsp+68h+arg_10]
0x14004a1b9  mov     [rax+8], rax
0x14004a1bd  mov     [rax], rax
0x14004a1c0  mov     r8, [rsp+68h+arg_10]; EcpContext
0x14004a1c8  mov     rdx, [rsp+68h+EcpList]; EcpList
0x14004a1d0  mov     rcx, cs:Filter; Filter
0x14004a1d7  call    cs:__imp_FltInsertExtraCreateParameter
0x14004a1de  nop     dword ptr [rax+rax+00h]
0x14004a1e3  mov     rcx, cs:Filter; FltObject
0x14004a1ea  call    cs:__imp_FltObjectReference
0x14004a1f1  nop     dword ptr [rax+rax+00h]
0x14004a1f6  mov     ecx, eax
0x14004a1f8  mov     edi, eax
0x14004a1fa  call    HsmDbgBreakOnStatus
0x14004a1ff  test    edi, edi
0x14004a201  js      loc_14004A0A3
0x14004a207  mov     rax, [rsp+68h+arg_10]
0x14004a20f  mov     rcx, [rax]
0x14004a212  cmp     [rcx+8], rax
0x14004a216  jnz     short loc_14004A296
0x14004a218  mov     [rbx], rcx
0x14004a21b  mov     [rbx+8], rax
0x14004a21f  mov     [rcx+8], rbx
0x14004a223  mov     [rax], rbx
0x14004a226  jmp     loc_14004A02E
0x14004a22b  mov     edi, 0C000009Ah
0x14004a230  mov     ecx, edi
0x14004a232  call    HsmDbgBreakOnStatus
0x14004a237  jmp     loc_14004A083
0x14004a23c  cmp     [rcx+8], rbx
0x14004a240  jnz     short loc_14004A296
0x14004a242  mov     rax, [rbx+8]
0x14004a246  cmp     [rax], rbx
0x14004a249  jnz     short loc_14004A296
0x14004a24b  mov     [rax], rcx
0x14004a24e  mov     [rcx+8], rax
0x14004a252  mov     rcx, cs:Filter; FltObject
0x14004a259  call    cs:__imp_FltObjectDereference
0x14004a260  nop     dword ptr [rax+rax+00h]
0x14004a265  jmp     loc_14004A0E4
0x14004a26a  lea     r9, [rsp+68h+arg_10]; EcpContext
0x14004a272  mov     [rsp+68h+CleanupCallback], r15; EcpContextSize
0x14004a277  lea     r8, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x14004a27e  call    cs:__imp_FltFindExtraCreateParameter
0x14004a285  nop     dword ptr [rax+rax+00h]
0x14004a28a  mov     ecx, eax
0x14004a28c  call    HsmDbgBreakOnStatus
0x14004a291  jmp     loc_14004A151
0x14004a296  mov     ecx, 3
0x14004a29b  int     29h; Win8: RtlFailFast(ecx)
```
