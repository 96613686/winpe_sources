# HsmiCreateAllocateECPTags

- ea: `0x140049e30`
- end: `0x14004a1ad`
- name: `HsmiCreateAllocateECPTags`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140049778`

## callees

- `0x140003c50`
- `0x14001e580`
- `0x140049e30`

## import_xrefs

- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14004a055`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14004a055`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140049ffe`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140049ffe`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140049e58`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140049e58`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140049fe8`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140049fe8`
- `FLTMGR!FltObjectReference` at `0x14004a0fa`
- `FLTMGR!FltObjectReference` at `0x14004a0fa`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140049f25`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140049f25`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14004a02d`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14004a02d`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14004a0e7`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14004a0e7`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14004a0a4`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14004a0a4`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14004a18e`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14004a18e`
- `FLTMGR!FltObjectDereference` at `0x14004a169`
- `FLTMGR!FltObjectDereference` at `0x14004a169`

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
  __int64 v13; // rdi
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
  unsigned int ExtraCreateParameter; // eax
  PVOID EcpContext; // [rsp+80h] [rbp+18h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp+20h] BYREF

  EcpContext = 0;
  v4 = ExAllocateFromPagedLookasideList(&stru_1400292C0);
  v5 = v4;
  if ( !v4 )
  {
    LODWORD(v13) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
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
    v13 = (unsigned int)FltAddOpenReparseEntry(Filter, a1, v5);
    HsmDbgBreakOnStatus(v13);
    if ( (int)v13 >= 0 )
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
    v13 = (unsigned int)FltAllocateExtraCreateParameterList(Filter, 0, &EcpList);
    HsmDbgBreakOnStatus(v13);
    if ( (int)v13 < 0 )
      goto LABEL_20;
    FsRtlSetEcpListIntoIrp(v19, EcpList);
  }
  if ( EcpContext )
    goto LABEL_30;
  v13 = (unsigned int)FltAllocateExtraCreateParameterFromLookasideList(
                        Filter,
                        &ECP_TYPE_OPEN_REPARSE_GUID,
                        0x10u,
                        0,
                        0,
                        qword_140029140,
                        &EcpContext);
  HsmDbgBreakOnStatus(v13);
  if ( (int)v13 < 0 )
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
  v13 = (unsigned int)FltObjectReference(Filter);
  HsmDbgBreakOnStatus(v13);
  if ( (int)v13 < 0 )
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
0x140049e30  mov     [rsp+arg_0], rbx
0x140049e35  push    rbp
0x140049e36  push    rsi
0x140049e37  push    rdi
0x140049e38  push    r14
0x140049e3a  push    r15
0x140049e3c  sub     rsp, 40h
0x140049e40  mov     rbp, rcx
0x140049e43  xor     r15d, r15d
0x140049e46  lea     rcx, stru_1400292C0; Lookaside
0x140049e4d  mov     [rsp+68h+arg_10], r15
0x140049e55  mov     r14, rdx
0x140049e58  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140049e5f  nop     dword ptr [rax+rax+00h]
0x140049e64  mov     rbx, rax
0x140049e67  test    rax, rax
0x140049e6a  jz      loc_14004A13B
0x140049e70  xor     edx, edx; Val
0x140049e72  mov     r8d, 300h; Size
0x140049e78  mov     rcx, rax; void *
0x140049e7b  call    memset
0x140049e80  mov     edx, r15d
0x140049e83  mov     eax, edx
0x140049e85  lea     rax, [rax+rax*2]
0x140049e89  shl     rax, 4
0x140049e8d  add     rax, rbx
0x140049e90  mov     dword ptr [rax+14h], 80000000h
0x140049e97  mov     word ptr [rax+28h], 30h ; '0'
0x140049e9d  test    edx, edx
0x140049e9f  jz      loc_140049FA7
0x140049ea5  mov     rcx, [rbx+8]
0x140049ea9  cmp     [rcx], rbx
0x140049eac  jnz     loc_14004A1A6
0x140049eb2  mov     [rax], rbx
0x140049eb5  mov     [rax+8], rcx
0x140049eb9  mov     [rcx], rax
0x140049ebc  mov     [rbx+8], rax
0x140049ec0  mov     ecx, edx
0x140049ec2  and     ecx, 0Fh
0x140049ec5  shl     ecx, 0Ch
0x140049ec8  or      ecx, cs:dword_140029670
0x140049ece  mov     [rax+10h], ecx
0x140049ed1  bt      ecx, 0Dh
0x140049ed5  jb      short loc_140049EDB
0x140049ed7  or      dword ptr [rax+14h], 6
0x140049edb  inc     edx
0x140049edd  cmp     edx, 10h
0x140049ee0  jb      short loc_140049E83
0x140049ee2  mov     rax, [rbx]
0x140049ee5  cmp     [rax+8], rbx
0x140049ee9  jnz     loc_14004A1A6
0x140049eef  mov     rcx, [rbx+8]
0x140049ef3  cmp     [rcx], rbx
0x140049ef6  jnz     loc_14004A1A6
0x140049efc  mov     [rcx], rax
0x140049eff  mov     [rax+8], rcx
0x140049f03  mov     [rbx+8], rbx
0x140049f07  mov     [rbx], rbx
0x140049f0a  mov     rax, [rbp+10h]
0x140049f0e  mov     rcx, cs:Filter; Filter
0x140049f15  cmp     [rax+4], r15b
0x140049f19  jnz     loc_14004A00C
0x140049f1f  mov     r8, rbx
0x140049f22  mov     rdx, rbp
0x140049f25  call    cs:__imp_FltAddOpenReparseEntry
0x140049f2c  nop     dword ptr [rax+rax+00h]
0x140049f31  mov     ecx, eax
0x140049f33  mov     edi, eax
0x140049f35  call    HsmDbgBreakOnStatus
0x140049f3a  test    edi, edi
0x140049f3c  js      short loc_140049FB3
0x140049f3e  mov     rdx, [rbx]
0x140049f41  mov     rax, [rdx]
0x140049f44  cmp     [rax+8], rdx
0x140049f48  jnz     loc_14004A1A6
0x140049f4e  mov     r8, [rdx+8]
0x140049f52  cmp     [r8], rdx
0x140049f55  jnz     loc_14004A1A6
0x140049f5b  mov     rax, [rbx+30h]
0x140049f5f  lea     rcx, [rbx+30h]
0x140049f63  cmp     [rax+8], rcx
0x140049f67  jnz     loc_14004A1A6
0x140049f6d  mov     rax, [rcx+8]
0x140049f71  cmp     [rax], rcx
0x140049f74  jnz     loc_14004A1A6
0x140049f7a  mov     [r8], rcx
0x140049f7d  mov     rax, [rcx+8]
0x140049f81  mov     [rdx+8], rax
0x140049f85  mov     rax, [rcx+8]
0x140049f89  mov     [rax], rdx
0x140049f8c  mov     [rcx+8], r8
0x140049f90  mov     [r14], rbx
0x140049f93  mov     rbx, [rsp+68h+arg_0]
0x140049f98  mov     eax, edi
0x140049f9a  add     rsp, 40h
0x140049f9e  pop     r15
0x140049fa0  pop     r14
0x140049fa2  pop     rdi
0x140049fa3  pop     rsi
0x140049fa4  pop     rbp
0x140049fa5  retn
0x140049fa7  mov     [rax+8], rax
0x140049fab  mov     [rax], rax
0x140049fae  jmp     loc_140049EC0
0x140049fb3  cmp     [rbx], rbx
0x140049fb6  jz      short loc_140049FF4
0x140049fb8  mov     rax, [rbx+2D0h]
0x140049fbf  mov     [rax+8], rbx
0x140049fc3  mov     rcx, [rbx+2D0h]
0x140049fca  mov     [rbx], rcx
0x140049fcd  mov     rax, [rbp+10h]
0x140049fd1  cmp     [rax+4], r15b
0x140049fd5  jnz     loc_14004A14C
0x140049fdb  mov     rcx, cs:Filter
0x140049fe2  mov     r8, rbx
0x140049fe5  mov     rdx, rbp
0x140049fe8  call    cs:__imp_FltRemoveOpenReparseEntry
0x140049fef  nop     dword ptr [rax+rax+00h]
0x140049ff4  mov     rdx, rbx; Entry
0x140049ff7  lea     rcx, stru_1400292C0; Lookaside
0x140049ffe  call    cs:__imp_ExFreeToPagedLookasideList
0x14004a005  nop     dword ptr [rax+rax+00h]
0x14004a00a  jmp     short loc_140049F93
0x14004a00c  mov     rsi, [rax+18h]
0x14004a010  mov     rdx, [rsi+70h]; EcpList
0x14004a014  mov     [rsp+68h+EcpList], rdx
0x14004a01c  test    rdx, rdx
0x14004a01f  jnz     loc_14004A17A
0x14004a025  lea     r8, [rsp+68h+EcpList]; EcpList
0x14004a02d  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14004a034  nop     dword ptr [rax+rax+00h]
0x14004a039  mov     ecx, eax
0x14004a03b  mov     edi, eax
0x14004a03d  call    HsmDbgBreakOnStatus
0x14004a042  test    edi, edi
0x14004a044  js      loc_140049FB3
0x14004a04a  mov     rdx, [rsp+68h+EcpList]; EcpList
0x14004a052  mov     rcx, rsi; Irp
0x14004a055  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x14004a05c  nop     dword ptr [rax+rax+00h]
0x14004a061  cmp     [rsp+68h+arg_10], r15
0x14004a069  jnz     loc_14004A0F3
0x14004a06f  mov     rcx, cs:Filter; Filter
0x14004a076  lea     rax, [rsp+68h+arg_10]
0x14004a07e  mov     [rsp+68h+EcpContext], rax; EcpContext
0x14004a083  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x14004a08a  lea     rax, qword_140029140
0x14004a091  xor     r9d, r9d; Flags
0x14004a094  mov     [rsp+68h+LookasideList], rax; LookasideList
0x14004a099  mov     r8d, 10h; SizeOfContext
0x14004a09f  mov     [rsp+68h+CleanupCallback], r15; CleanupCallback
0x14004a0a4  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14004a0ab  nop     dword ptr [rax+rax+00h]
0x14004a0b0  mov     ecx, eax
0x14004a0b2  mov     edi, eax
0x14004a0b4  call    HsmDbgBreakOnStatus
0x14004a0b9  test    edi, edi
0x14004a0bb  js      loc_140049FB3
0x14004a0c1  mov     rax, [rsp+68h+arg_10]
0x14004a0c9  mov     [rax+8], rax
0x14004a0cd  mov     [rax], rax
0x14004a0d0  mov     r8, [rsp+68h+arg_10]; EcpContext
0x14004a0d8  mov     rdx, [rsp+68h+EcpList]; EcpList
0x14004a0e0  mov     rcx, cs:Filter; Filter
0x14004a0e7  call    cs:__imp_FltInsertExtraCreateParameter
0x14004a0ee  nop     dword ptr [rax+rax+00h]
0x14004a0f3  mov     rcx, cs:Filter; FltObject
0x14004a0fa  call    cs:__imp_FltObjectReference
0x14004a101  nop     dword ptr [rax+rax+00h]
0x14004a106  mov     ecx, eax
0x14004a108  mov     edi, eax
0x14004a10a  call    HsmDbgBreakOnStatus
0x14004a10f  test    edi, edi
0x14004a111  js      loc_140049FB3
0x14004a117  mov     rax, [rsp+68h+arg_10]
0x14004a11f  mov     rcx, [rax]
0x14004a122  cmp     [rcx+8], rax
0x14004a126  jnz     short loc_14004A1A6
0x14004a128  mov     [rbx], rcx
0x14004a12b  mov     [rbx+8], rax
0x14004a12f  mov     [rcx+8], rbx
0x14004a133  mov     [rax], rbx
0x14004a136  jmp     loc_140049F3E
0x14004a13b  mov     edi, 0C000009Ah
0x14004a140  mov     ecx, edi
0x14004a142  call    HsmDbgBreakOnStatus
0x14004a147  jmp     loc_140049F93
0x14004a14c  cmp     [rcx+8], rbx
0x14004a150  jnz     short loc_14004A1A6
0x14004a152  mov     rax, [rbx+8]
0x14004a156  cmp     [rax], rbx
0x14004a159  jnz     short loc_14004A1A6
0x14004a15b  mov     [rax], rcx
0x14004a15e  mov     [rcx+8], rax
0x14004a162  mov     rcx, cs:Filter; FltObject
0x14004a169  call    cs:__imp_FltObjectDereference
0x14004a170  nop     dword ptr [rax+rax+00h]
0x14004a175  jmp     loc_140049FF4
0x14004a17a  lea     r9, [rsp+68h+arg_10]; EcpContext
0x14004a182  mov     [rsp+68h+CleanupCallback], r15; EcpContextSize
0x14004a187  lea     r8, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x14004a18e  call    cs:__imp_FltFindExtraCreateParameter
0x14004a195  nop     dword ptr [rax+rax+00h]
0x14004a19a  mov     ecx, eax
0x14004a19c  call    HsmDbgBreakOnStatus
0x14004a1a1  jmp     loc_14004A061
0x14004a1a6  mov     ecx, 3
0x14004a1ab  int     29h; Win8: RtlFailFast(ecx)
```
