# FltCopyOpenReparseList

- ea: `0x18004ffa0`
- end: `0x18005019e`
- name: `FltCopyOpenReparseList`
- size: `510`
- prototype: `__int64 __fastcall(struct _FLT_FILTER *, struct _FLT_CALLBACK_DATA *, struct _ECP_LIST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180082ae0`

## callees

- `0x180009f20`
- `0x18004ffa0`
- `0x1800501e0`
- `0x180064df0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800500f8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800500f8`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18005008a`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18005008a`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1800500cc`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1800500cc`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x18005001d`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180050055`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x18005001d`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180050055`

## pseudocode

```c
__int64 __fastcall FltCopyOpenReparseList(struct _FLT_FILTER *a1, struct _FLT_CALLBACK_DATA *a2, struct _ECP_LIST *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  UCHAR MajorFunction; // r9
  unsigned int ExtraCreateParameter; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  char *v11; // rax
  char *v12; // rbx
  char *v13; // rax
  _WORD *v14; // rdx
  __int16 v15; // ax
  _QWORD *v16; // rax
  PVOID *v17; // rcx
  PECP_LIST EcpList; // [rsp+30h] [rbp-10h] BYREF
  PVOID v19; // [rsp+68h] [rbp+28h] BYREF
  PVOID EcpContext; // [rsp+78h] [rbp+38h] BYREF

  Iopb = a2->Iopb;
  EcpList = 0;
  EcpContext = 0;
  v19 = 0;
  MajorFunction = Iopb->MajorFunction;
  if ( MajorFunction && MajorFunction != 0xF2 && MajorFunction != 0xF9 )
    return 3221225712LL;
  FltGetEcpListFromCallbackData(a1, a2, &EcpList);
  if ( EcpList )
  {
    ExtraCreateParameter = FsRtlFindExtraCreateParameter(EcpList, &ECP_TYPE_OPEN_REPARSE_GUID, &EcpContext, 0);
    if ( (int)FltpDbgStatus(ExtraCreateParameter, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1374, 0) >= 0 )
    {
      FsRtlFindExtraCreateParameter(a3, &ECP_TYPE_OPEN_REPARSE_GUID, &v19, 0);
      if ( !v19 )
      {
        v9 = FsRtlAllocateExtraCreateParameterFromLookasideList(
               &ECP_TYPE_OPEN_REPARSE_GUID,
               0x10u,
               0,
               0,
               qword_18003F2C0,
               &v19);
        if ( (int)FltpDbgStatus(v9, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1400, 0) < 0 )
          return v9;
        v10 = v19;
        *((_QWORD *)v19 + 1) = v19;
        *v10 = v10;
        FsRtlInsertExtraCreateParameter(a3, v19);
      }
      v11 = (char *)EcpContext;
      v12 = (char *)EcpContext;
      while ( 1 )
      {
        v12 = *(char **)v12;
        if ( v12 == v11 )
          break;
        v13 = (char *)ExAllocateFromPagedLookasideList(&stru_18003F340);
        v14 = v13;
        if ( !v13 )
        {
          FltFreeOpenReparseList(a1, a3);
          return 3221225626LL;
        }
        *((_QWORD *)v13 + 1) = v13;
        *(_QWORD *)v13 = v13;
        *((_DWORD *)v13 + 4) = *((_DWORD *)v12 + 4);
        *((_DWORD *)v13 + 5) = *((_DWORD *)v12 + 5) & 0xFFFFFFFE;
        *(_OWORD *)(v13 + 24) = *(_OWORD *)(v12 + 24);
        if ( *((int *)v12 + 5) < 0 )
        {
          v15 = *((_WORD *)v12 + 20);
          if ( (unsigned __int16)v15 > 0x30u )
            v15 = 48;
          v14[20] = v15;
          v14[21] = *((_WORD *)v12 + 21);
        }
        v16 = v19;
        v17 = (PVOID *)*((_QWORD *)v19 + 1);
        if ( *v17 != v19 )
          __fastfail(3u);
        *(_QWORD *)v14 = v19;
        *((_QWORD *)v14 + 1) = v17;
        *v17 = v14;
        v16[1] = v14;
        v11 = (char *)EcpContext;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004ffa0  mov     [rsp-18h+arg_0], rbx
0x18004ffa5  mov     [rsp-18h+arg_10], rsi
0x18004ffaa  push    rbp
0x18004ffab  push    rdi
0x18004ffac  push    r15
0x18004ffae  mov     rbp, rsp
0x18004ffb1  sub     rsp, 40h
0x18004ffb5  mov     rax, [rdx+10h]
0x18004ffb9  mov     rdi, r8
0x18004ffbc  mov     [rbp+EcpList], 0
0x18004ffc4  mov     rsi, rcx
0x18004ffc7  mov     [rbp+EcpContext], 0
0x18004ffcf  mov     [rbp+arg_8], 0
0x18004ffd7  mov     r9b, [rax+4]
0x18004ffdb  test    r9b, r9b
0x18004ffde  jz      short loc_18004FFF6
0x18004ffe0  cmp     r9b, 0F2h
0x18004ffe4  jz      short loc_18004FFF6
0x18004ffe6  cmp     r9b, 0F9h
0x18004ffea  jz      short loc_18004FFF6
0x18004ffec  mov     eax, 0C00000F0h
0x18004fff1  jmp     loc_18005018A
0x18004fff6  lea     r8, [rbp+EcpList]; EcpList
0x18004fffa  call    FltGetEcpListFromCallbackData
0x18004ffff  mov     rcx, [rbp+EcpList]; EcpList
0x180050003  test    rcx, rcx
0x180050006  jz      loc_180050188
0x18005000c  lea     rbx, ECP_TYPE_OPEN_REPARSE_GUID
0x180050013  xor     r9d, r9d; EcpContextSize
0x180050016  mov     rdx, rbx; EcpType
0x180050019  lea     r8, [rbp+EcpContext]; EcpContext
0x18005001d  call    cs:__imp_FsRtlFindExtraCreateParameter
0x180050024  nop     dword ptr [rax+rax+00h]
0x180050029  mov     r8d, 55Eh
0x18005002f  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x180050036  mov     ecx, eax
0x180050038  xor     r9d, r9d
0x18005003b  call    FltpDbgStatus
0x180050040  test    eax, eax
0x180050042  js      loc_180050188
0x180050048  xor     r9d, r9d; EcpContextSize
0x18005004b  lea     r8, [rbp+arg_8]; EcpContext
0x18005004f  mov     rdx, rbx; EcpType
0x180050052  mov     rcx, rdi; EcpList
0x180050055  call    cs:__imp_FsRtlFindExtraCreateParameter
0x18005005c  nop     dword ptr [rax+rax+00h]
0x180050061  cmp     [rbp+arg_8], 0
0x180050066  jnz     short loc_1800500D8
0x180050068  xor     r9d, r9d; CleanupCallback
0x18005006b  lea     rax, [rbp+arg_8]
0x18005006f  mov     [rsp+40h+var_18], rax; EcpContext
0x180050074  xor     r8d, r8d; Flags
0x180050077  lea     rax, qword_18003F2C0
0x18005007e  mov     rcx, rbx; EcpType
0x180050081  mov     [rsp+40h+LookasideList], rax; LookasideList
0x180050086  lea     edx, [r9+10h]; SizeOfContext
0x18005008a  call    cs:__imp_FsRtlAllocateExtraCreateParameterFromLookasideList
0x180050091  nop     dword ptr [rax+rax+00h]
0x180050096  mov     r8d, 578h
0x18005009c  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x1800500a3  mov     ecx, eax
0x1800500a5  xor     r9d, r9d
0x1800500a8  mov     ebx, eax
0x1800500aa  call    FltpDbgStatus
0x1800500af  test    eax, eax
0x1800500b1  jns     short loc_1800500BA
0x1800500b3  mov     eax, ebx
0x1800500b5  jmp     loc_18005018A
0x1800500ba  mov     rax, [rbp+arg_8]
0x1800500be  mov     rcx, rdi; EcpList
0x1800500c1  mov     [rax+8], rax
0x1800500c5  mov     [rax], rax
0x1800500c8  mov     rdx, [rbp+arg_8]; EcpContext
0x1800500cc  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1800500d3  nop     dword ptr [rax+rax+00h]
0x1800500d8  mov     rax, [rbp+EcpContext]
0x1800500dc  mov     r15d, 30h ; '0'
0x1800500e2  mov     rbx, rax
0x1800500e5  mov     rbx, [rbx]
0x1800500e8  cmp     rbx, rax
0x1800500eb  jz      loc_180050188
0x1800500f1  lea     rcx, stru_18003F340; Lookaside
0x1800500f8  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1800500ff  nop     dword ptr [rax+rax+00h]
0x180050104  mov     rdx, rax
0x180050107  test    rax, rax
0x18005010a  jz      short loc_180050176
0x18005010c  mov     [rax+8], rax
0x180050110  mov     [rax], rax
0x180050113  mov     ecx, [rbx+10h]
0x180050116  mov     [rax+10h], ecx
0x180050119  mov     ecx, [rbx+14h]
0x18005011c  and     ecx, 0FFFFFFFEh
0x18005011f  mov     [rax+14h], ecx
0x180050122  movups  xmm0, xmmword ptr [rbx+18h]
0x180050126  movdqu  xmmword ptr [rax+18h], xmm0
0x18005012b  cmp     dword ptr [rbx+14h], 0
0x18005012f  jge     short loc_18005014B
0x180050131  movzx   eax, word ptr [rbx+28h]
0x180050135  cmp     r15w, ax
0x180050139  jnb     short loc_18005013F
0x18005013b  movzx   eax, r15w
0x18005013f  mov     [rdx+28h], ax
0x180050143  movzx   eax, word ptr [rbx+2Ah]
0x180050147  mov     [rdx+2Ah], ax
0x18005014b  mov     rax, [rbp+arg_8]
0x18005014f  mov     rcx, [rax+8]
0x180050153  cmp     [rcx], rax
0x180050156  jnz     short loc_18005016F
0x180050158  mov     [rdx], rax
0x18005015b  mov     [rdx+8], rcx
0x18005015f  mov     [rcx], rdx
0x180050162  mov     [rax+8], rdx
0x180050166  mov     rax, [rbp+EcpContext]
0x18005016a  jmp     loc_1800500E5
0x18005016f  mov     ecx, 3
0x180050174  int     29h; Win8: RtlFailFast(ecx)
0x180050176  mov     rdx, rdi
0x180050179  mov     rcx, rsi
0x18005017c  call    FltFreeOpenReparseList
0x180050181  mov     eax, 0C000009Ah
0x180050186  jmp     short loc_18005018A
0x180050188  xor     eax, eax
0x18005018a  mov     rbx, [rsp+40h+arg_0]
0x18005018f  mov     rsi, [rsp+40h+arg_10]
0x180050194  add     rsp, 40h
0x180050198  pop     r15
0x18005019a  pop     rdi
0x18005019b  pop     rbp
0x18005019c  retn
```
