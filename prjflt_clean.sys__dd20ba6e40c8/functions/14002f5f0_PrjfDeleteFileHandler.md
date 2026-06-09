# PrjfDeleteFileHandler

- ea: `0x14002f5f0`
- end: `0x14002fd9c`
- name: `PrjfDeleteFileHandler`
- size: `1964`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140031a00`

## callees

- `0x140003e6c`
- `0x14000d008`
- `0x14000d128`
- `0x14000d5e8`
- `0x140021f8c`
- `0x14002f5f0`
- `0x140033878`
- `0x1400396a4`
- `0x14003d620`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f9f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f9f9`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f9df`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f9df`
- `ntoskrnl!ExAllocatePool2` at `0x14002f934`
- `ntoskrnl!ExAllocatePool2` at `0x14002f934`
- `FLTMGR!FltClose` at `0x14002f9ca`
- `FLTMGR!FltClose` at `0x14002f9ca`

## pseudocode

```c
__int64 __fastcall PrjfDeleteFileHandler(PFLT_INSTANCE Instance, unsigned int *a2, __int64 a3, _DWORD *a4)
{
  __int64 v5; // rdx
  char *v7; // r12
  signed int v8; // ebx
  unsigned int v9; // ecx
  char *v10; // r14
  _WORD *v11; // rax
  unsigned __int64 i; // rcx
  __int64 v13; // rdx
  _WORD *v14; // rax
  unsigned __int16 v15; // r15
  __int16 v16; // bx
  unsigned __int16 v17; // ax
  __int64 v18; // r12
  _DWORD *v20; // r14
  char v21; // r10
  __int16 v22; // [rsp+30h] [rbp-39h]
  char v23; // [rsp+48h] [rbp-21h]
  char v24; // [rsp+50h] [rbp-19h]
  PVOID Object; // [rsp+60h] [rbp-9h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-1h] BYREF
  struct _UNICODE_STRING P; // [rsp+70h] [rbp+7h] BYREF
  __int64 UnionContextByVirtualizationInstanceInfo; // [rsp+D8h] [rbp+6Fh]
  char v29; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v30; // [rsp+E8h] [rbp+7Fh]

  v30 = (__int64)a4;
  *a4 = 0;
  v5 = *a2;
  FileHandle = 0;
  v7 = 0;
  Object = 0;
  v29 = 0;
  P = 0;
  if ( (unsigned int)v5 > (unsigned int)a3 )
  {
    v8 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_44;
    WPP_RECORDER_AND_TRACE_SF_sD(
      526,
      v5,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      190,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      95);
    goto LABEL_40;
  }
  if ( (unsigned int)v5 < 0x62 )
  {
    v8 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_44;
    LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
    WPP_RECORDER_AND_TRACE_SF_sDdd(526, v5, a3, *((_QWORD *)WPP_GLOBAL_Control + 8));
    goto LABEL_40;
  }
  v9 = a2[23];
  if ( v9 < 0x62 )
  {
    v8 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_44;
    WPP_RECORDER_AND_TRACE_SF_sD(
      526,
      v5,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      192,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      110);
    goto LABEL_40;
  }
  a3 = v9 + *((unsigned __int16 *)a2 + 48);
  if ( (unsigned int)a3 >= v9 )
  {
    if ( (unsigned int)v5 < (unsigned int)a3 )
    {
      v8 = -1073741811;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_44;
      WPP_RECORDER_AND_TRACE_SF_sD(
        526,
        v5,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        194,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        128);
      goto LABEL_40;
    }
    UnionContextByVirtualizationInstanceInfo = PrjfGetUnionContextByVirtualizationInstanceInfo(a2 + 2, Instance);
    v7 = (char *)UnionContextByVirtualizationInstanceInfo;
    if ( !UnionContextByVirtualizationInstanceInfo )
    {
      v8 = -1073741811;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sD(
          526,
          v5,
          a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          195,
          (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          138);
      goto LABEL_40;
    }
    v10 = (char *)a2 + a2[23];
    if ( !v10 )
    {
      v8 = -1073741811;
LABEL_69:
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v24 = 13;
      v23 = -98;
      v22 = 196;
      goto LABEL_72;
    }
    v11 = (_WORD *)((char *)a2 + a2[23]);
    for ( i = (unsigned __int64)*((unsigned __int16 *)a2 + 48) >> 1; i; --i )
    {
      if ( !*v11 )
        break;
      ++v11;
    }
    v5 = i == 0 ? 0xC000000D : 0;
    if ( !i )
    {
      v8 = -1073741811;
      goto LABEL_69;
    }
    v13 = 0x7FFF;
    v14 = (_WORD *)((char *)a2 + a2[23]);
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    v8 = v13 == 0 ? 0xC000000D : 0;
    if ( !v13 )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v5 = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v24 = v8;
      v23 = -90;
      v22 = 197;
      goto LABEL_72;
    }
    v15 = *(_WORD *)(UnionContextByVirtualizationInstanceInfo + 40);
    v16 = -2 - 2 * v13;
    if ( (unsigned __int16)(v15 + v16) < v15 )
    {
      v5 = 3221225621LL;
      P.MaximumLength = -1;
      v8 = -1073741675;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v21 = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v24 = -107;
      v23 = -81;
      v22 = 198;
    }
    else
    {
      v17 = v15 - 2 * v13;
      if ( v17 >= 2u )
      {
        v18 = *(_QWORD *)(UnionContextByVirtualizationInstanceInfo + 48);
        P.MaximumLength = v15 - 2 * v13;
        P.Buffer = (PWSTR)ExAllocatePool2(256, v17, 1953319504);
        if ( !P.Buffer )
        {
          v8 = -1073741670;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_AND_TRACE_SF_sD(
              526,
              v5,
              a3,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              200,
              (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
              194);
          }
LABEL_39:
          v7 = (char *)UnionContextByVirtualizationInstanceInfo;
          goto LABEL_40;
        }
        v8 = PrjfRelPathToFullPath(&P, v15, v18, v10, v16);
        if ( v8 < 0 )
        {
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_AND_TRACE_SF_sDL(
              526,
              v5,
              a3,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              201,
              (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
              206,
              v8);
          }
          goto LABEL_39;
        }
        v20 = (_DWORD *)v30;
        v7 = (char *)UnionContextByVirtualizationInstanceInfo;
        v8 = PrjfDecideUpdateDeleteOnFileStateAndUpdateFlags(
               Instance,
               a2[22],
               &P,
               &FileHandle,
               (PFILE_OBJECT *)&Object,
               (_DWORD *)v30,
               0,
               0,
               &v29);
        if ( v8 < 0 )
          goto LABEL_40;
        v8 = PrjfSetDeleteDisposition(
               Instance,
               (PFILE_OBJECT)Object,
               a2[22],
               v29,
               UnionContextByVirtualizationInstanceInfo,
               v20);
        if ( v8 >= 0 )
          goto LABEL_40;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_40;
        v24 = v8;
        v23 = -13;
        v22 = 202;
LABEL_72:
        WPP_RECORDER_AND_TRACE_SF_sDL(
          526,
          v5,
          a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          v22,
          (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          v23,
          v24);
        goto LABEL_40;
      }
      v5 = 3221225621LL;
      P.MaximumLength = -1;
      v8 = -1073741675;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      v21 = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v24 = -107;
      v23 = -73;
      v22 = 199;
    }
    LOBYTE(v5) = v21;
    goto LABEL_72;
  }
  v5 = 3221225621LL;
  v8 = -1073741675;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_44;
  LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
  WPP_RECORDER_AND_TRACE_SF_sDL(
    526,
    v5,
    a3,
    *((_QWORD *)WPP_GLOBAL_Control + 8),
    2,
    14,
    193,
    (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
    (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
    121,
    149);
LABEL_40:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
LABEL_44:
  if ( P.Buffer )
    ExFreePoolWithTag(P.Buffer, 0x746D4A50u);
  if ( v7 )
    PrjfReleaseUnionContext(v7, v5, a3, (__int64)a4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002f5f0  mov     [rsp-8+arg_0], rbx
0x14002f5f5  mov     [rsp-8+arg_18], r9
0x14002f5fa  push    rbp
0x14002f5fb  push    rsi
0x14002f5fc  push    rdi
0x14002f5fd  push    r12
0x14002f5ff  push    r13
0x14002f601  push    r14
0x14002f603  push    r15
0x14002f605  lea     rbp, [rsp-27h]
0x14002f60a  sub     rsp, 90h
0x14002f611  xor     r15d, r15d
0x14002f614  mov     rsi, rdx
0x14002f617  mov     [r9], r15d
0x14002f61a  xorps   xmm0, xmm0
0x14002f61d  mov     edx, [rdx]
0x14002f61f  mov     r13, rcx
0x14002f622  mov     [rbp+57h+FileHandle], r15
0x14002f626  mov     r12d, r15d
0x14002f629  mov     [rbp+57h+Object], r15
0x14002f62d  mov     [rbp+57h+arg_10], r15b
0x14002f631  movups  xmmword ptr [rbp+57h+P.Length], xmm0
0x14002f635  cmp     edx, r8d
0x14002f638  jbe     short loc_14002F6B3
0x14002f63a  mov     ebx, 0C000000Dh
0x14002f63f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f645  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f64c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f653  setnz   r8b
0x14002f657  and     dl, 40h
0x14002f65a  jnz     short loc_14002F665
0x14002f65c  test    r8b, r8b
0x14002f65f  jz      loc_14002F9EB
0x14002f665  mov     dword ptr [rsp+0C0h+var_78], 175Fh
0x14002f66d  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f674  mov     [rsp+0C0h+var_80], rax
0x14002f679  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f680  mov     [rsp+0C0h+var_88], rax
0x14002f685  mov     word ptr [rsp+0C0h+var_90], 0BEh
0x14002f68c  mov     r9, cs:WPP_GLOBAL_Control
0x14002f693  mov     ecx, 20Eh
0x14002f698  mov     dword ptr [rsp+0C0h+var_98], 0Eh
0x14002f6a0  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14002f6a5  mov     r9, [r9+40h]
0x14002f6a9  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002f6ae  jmp     loc_14002F9C1
0x14002f6b3  cmp     edx, 62h ; 'b'
0x14002f6b6  jnb     loc_14002F741
0x14002f6bc  mov     ebx, 0C000000Dh
0x14002f6c1  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x14002f6c8  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f6cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f6d6  setnz   r8b
0x14002f6da  and     r10b, 40h
0x14002f6de  jnz     short loc_14002F6E9
0x14002f6e0  test    r8b, r8b
0x14002f6e3  jz      loc_14002F9EB
0x14002f6e9  mov     r9, cs:WPP_GLOBAL_Control
0x14002f6f0  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f6f7  mov     [rsp+0C0h+var_68], 62h ; 'b'
0x14002f6ff  mov     ecx, 20Eh
0x14002f704  mov     dword ptr [rsp+0C0h+var_70], edx
0x14002f708  mov     dl, r10b
0x14002f70b  mov     dword ptr [rsp+0C0h+var_78], 1767h
0x14002f713  mov     r9, [r9+40h]
0x14002f717  mov     [rsp+0C0h+var_80], rax
0x14002f71c  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f723  mov     [rsp+0C0h+var_88], rax
0x14002f728  mov     word ptr [rsp+0C0h+var_90], 0BFh
0x14002f72f  mov     dword ptr [rsp+0C0h+var_98], 0Eh
0x14002f737  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x14002f73c  jmp     loc_14002F9C1
0x14002f741  mov     ecx, [rsi+5Ch]
0x14002f744  cmp     ecx, 62h ; 'b'
0x14002f747  jnb     short loc_14002F7A0
0x14002f749  mov     ebx, 0C000000Dh
0x14002f74e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f754  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f75b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f762  setnz   r8b
0x14002f766  and     dl, 40h
0x14002f769  jnz     short loc_14002F774
0x14002f76b  test    r8b, r8b
0x14002f76e  jz      loc_14002F9EB
0x14002f774  mov     dword ptr [rsp+0C0h+var_78], 176Eh
0x14002f77c  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f783  mov     [rsp+0C0h+var_80], rax
0x14002f788  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f78f  mov     [rsp+0C0h+var_88], rax
0x14002f794  mov     word ptr [rsp+0C0h+var_90], 0C0h
0x14002f79b  jmp     loc_14002F68C
0x14002f7a0  movzx   r8d, word ptr [rsi+60h]
0x14002f7a5  add     r8d, ecx
0x14002f7a8  cmp     r8d, ecx
0x14002f7ab  jb      loc_14002FD2D
0x14002f7b1  cmp     edx, r8d
0x14002f7b4  jnb     short loc_14002F80D
0x14002f7b6  mov     ebx, 0C000000Dh
0x14002f7bb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f7c1  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f7c8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f7cf  setnz   r8b
0x14002f7d3  and     dl, 40h
0x14002f7d6  jnz     short loc_14002F7E1
0x14002f7d8  test    r8b, r8b
0x14002f7db  jz      loc_14002F9EB
0x14002f7e1  mov     dword ptr [rsp+0C0h+var_78], 1780h
0x14002f7e9  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f7f0  mov     [rsp+0C0h+var_80], rax
0x14002f7f5  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f7fc  mov     [rsp+0C0h+var_88], rax
0x14002f801  mov     word ptr [rsp+0C0h+var_90], 0C2h
0x14002f808  jmp     loc_14002F68C
0x14002f80d  lea     rcx, [rsi+8]
0x14002f811  mov     rdx, r13
0x14002f814  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x14002f819  mov     [rbp+57h+arg_8], rax
0x14002f81d  mov     r12, rax
0x14002f820  test    rax, rax
0x14002f823  jnz     short loc_14002F87C
0x14002f825  mov     ebx, 0C000000Dh
0x14002f82a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f830  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f837  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f83e  setnz   r8b
0x14002f842  and     dl, 40h
0x14002f845  jnz     short loc_14002F850
0x14002f847  test    r8b, r8b
0x14002f84a  jz      loc_14002F9C1
0x14002f850  mov     dword ptr [rsp+0C0h+var_78], 178Ah
0x14002f858  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f85f  mov     [rsp+0C0h+var_80], rax
0x14002f864  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f86b  mov     [rsp+0C0h+var_88], rax
0x14002f870  mov     word ptr [rsp+0C0h+var_90], 0C3h
0x14002f877  jmp     loc_14002F68C
0x14002f87c  mov     r14d, [rsi+5Ch]
0x14002f880  mov     edi, 2
0x14002f885  add     r14, rsi
0x14002f888  jz      loc_14002FCB0
0x14002f88e  movzx   ecx, word ptr [rsi+60h]
0x14002f892  mov     rax, r14
0x14002f895  shr     rcx, 1
0x14002f898  jz      short loc_14002F8A9
0x14002f89a  cmp     [rax], r15w
0x14002f89e  jz      short loc_14002F8A9
0x14002f8a0  add     rax, rdi
0x14002f8a3  sub     rcx, 1
0x14002f8a7  jnz     short loc_14002F89A
0x14002f8a9  mov     rax, rcx
0x14002f8ac  mov     ebx, 0C000000Dh
0x14002f8b1  neg     rax
0x14002f8b4  sbb     edx, edx
0x14002f8b6  not     edx
0x14002f8b8  and     edx, ebx
0x14002f8ba  test    rcx, rcx
0x14002f8bd  jnz     short loc_14002F8C6
0x14002f8bf  mov     ebx, edx
0x14002f8c1  jmp     loc_14002FCB5
0x14002f8c6  mov     edx, 7FFFh
0x14002f8cb  mov     rax, r14
0x14002f8ce  cmp     [rax], r15w
0x14002f8d2  jz      short loc_14002F8DD
0x14002f8d4  add     rax, rdi
0x14002f8d7  sub     rdx, 1
0x14002f8db  jnz     short loc_14002F8CE
0x14002f8dd  mov     rax, rdx
0x14002f8e0  neg     rax
0x14002f8e3  sbb     ecx, ecx
0x14002f8e5  not     ecx
0x14002f8e7  and     ebx, ecx
0x14002f8e9  test    rdx, rdx
0x14002f8ec  jz      loc_14002FC5D
0x14002f8f2  movzx   r15d, word ptr [r12+28h]
0x14002f8f8  add     dx, dx
0x14002f8fb  mov     ebx, 0FFFEh
0x14002f900  sub     bx, dx
0x14002f903  lea     eax, [r15+rbx]
0x14002f907  cmp     ax, r15w
0x14002f90b  jb      loc_14002FBF8
0x14002f911  add     ax, di
0x14002f914  cmp     ax, di
0x14002f917  jb      loc_14002FB8D
0x14002f91d  mov     r12, [r12+30h]
0x14002f922  mov     ecx, 100h
0x14002f927  movzx   edx, ax
0x14002f92a  mov     r8d, 746D4A50h
0x14002f930  mov     [rbp+57h+P.MaximumLength], ax
0x14002f934  call    cs:__imp_ExAllocatePool2
0x14002f93b  nop     dword ptr [rax+rax+00h]
0x14002f940  mov     [rbp+57h+P.Buffer], rax
0x14002f944  test    rax, rax
0x14002f947  jnz     loc_14002FA30
0x14002f94d  mov     ebx, 0C000009Ah
0x14002f952  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f958  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f95f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f966  setnz   r8b
0x14002f96a  and     dl, 40h
0x14002f96d  jnz     short loc_14002F974
0x14002f96f  test    r8b, r8b
0x14002f972  jz      short loc_14002F9BD
0x14002f974  mov     r9, cs:WPP_GLOBAL_Control
0x14002f97b  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f982  mov     dword ptr [rsp+0C0h+var_78], 17C2h
0x14002f98a  mov     ecx, 20Eh
0x14002f98f  mov     [rsp+0C0h+var_80], rax
0x14002f994  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f99b  mov     [rsp+0C0h+var_88], rax
0x14002f9a0  mov     r9, [r9+40h]
0x14002f9a4  mov     word ptr [rsp+0C0h+var_90], 0C8h
0x14002f9ab  mov     dword ptr [rsp+0C0h+var_98], 0Eh
0x14002f9b3  mov     byte ptr [rsp+0C0h+var_A0], dil
0x14002f9b8  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002f9bd  mov     r12, [rbp+57h+arg_8]
0x14002f9c1  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002f9c5  test    rcx, rcx
0x14002f9c8  jz      short loc_14002F9D6
0x14002f9ca  call    cs:__imp_FltClose
0x14002f9d1  nop     dword ptr [rax+rax+00h]
0x14002f9d6  mov     rcx, [rbp+57h+Object]; Object
0x14002f9da  test    rcx, rcx
0x14002f9dd  jz      short loc_14002F9EB
0x14002f9df  call    cs:__imp_ObfDereferenceObject
0x14002f9e6  nop     dword ptr [rax+rax+00h]
0x14002f9eb  mov     rcx, [rbp+57h+P.Buffer]; P
0x14002f9ef  test    rcx, rcx
0x14002f9f2  jz      short loc_14002FA05
0x14002f9f4  mov     edx, 746D4A50h; Tag
0x14002f9f9  call    cs:__imp_ExFreePoolWithTag
0x14002fa00  nop     dword ptr [rax+rax+00h]
0x14002fa05  test    r12, r12
0x14002fa08  jz      short loc_14002FA12
0x14002fa0a  mov     rcx, r12; P
0x14002fa0d  call    PrjfReleaseUnionContext
0x14002fa12  mov     eax, ebx
0x14002fa14  mov     rbx, [rsp+0C0h+arg_0]
0x14002fa1c  add     rsp, 90h
0x14002fa23  pop     r15
0x14002fa25  pop     r14
0x14002fa27  pop     r13
0x14002fa29  pop     r12
0x14002fa2b  pop     rdi
0x14002fa2c  pop     rsi
0x14002fa2d  pop     rbp
0x14002fa2e  retn
0x14002fa30  mov     r9, r14
0x14002fa33  mov     word ptr [rsp+0C0h+var_A0], bx
0x14002fa38  mov     r8, r12
0x14002fa3b  lea     rcx, [rbp+57h+P]
0x14002fa3f  movzx   edx, r15w
0x14002fa43  call    PrjfRelPathToFullPath
0x14002fa48  xor     r15d, r15d
0x14002fa4b  mov     ebx, eax
0x14002fa4d  test    eax, eax
0x14002fa4f  jns     short loc_14002FAC9
0x14002fa51  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002fa57  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fa5e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fa65  setnz   r8b
0x14002fa69  and     dl, 40h
0x14002fa6c  jnz     short loc_14002FA77
0x14002fa6e  test    r8b, r8b
0x14002fa71  jz      loc_14002F9BD
0x14002fa77  mov     r9, cs:WPP_GLOBAL_Control
0x14002fa7e  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002fa85  mov     dword ptr [rsp+0C0h+var_70], ebx
0x14002fa89  mov     ecx, 20Eh
0x14002fa8e  mov     dword ptr [rsp+0C0h+var_78], 17CEh
0x14002fa96  mov     [rsp+0C0h+var_80], rax
0x14002fa9b  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002faa2  mov     r9, [r9+40h]
0x14002faa6  mov     [rsp+0C0h+var_88], rax
0x14002faab  mov     word ptr [rsp+0C0h+var_90], 0C9h
0x14002fab2  mov     dword ptr [rsp+0C0h+var_98], 0Eh
0x14002faba  mov     byte ptr [rsp+0C0h+var_A0], dil
0x14002fabf  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002fac4  jmp     loc_14002F9BD
0x14002fac9  mov     r14, [rbp+57h+arg_18]
0x14002facd  lea     rax, [rbp+57h+arg_10]
0x14002fad1  mov     edx, [rsi+58h]
0x14002fad4  lea     r9, [rbp+57h+FileHandle]
0x14002fad8  mov     [rsp+0C0h+var_80], rax
0x14002fadd  lea     r8, [rbp+57h+P]
0x14002fae1  mov     [rsp+0C0h+var_88], r15
0x14002fae6  lea     rax, [rbp+57h+Object]
0x14002faea  mov     [rsp+0C0h+var_90], r15
0x14002faef  mov     rcx, r13
0x14002faf2  mov     [rsp+0C0h+var_98], r14
0x14002faf7  mov     [rsp+0C0h+var_A0], rax
0x14002fafc  call    PrjfDecideUpdateDeleteOnFileStateAndUpdateFlags
0x14002fb01  mov     r12, [rbp+57h+arg_8]
0x14002fb05  mov     ebx, eax
0x14002fb07  test    eax, eax
0x14002fb09  js      loc_14002F9C1
0x14002fb0f  mov     r9b, [rbp+57h+arg_10]
0x14002fb13  mov     rcx, r13; Instance
0x14002fb16  mov     r8d, [rsi+58h]
0x14002fb1a  mov     rdx, [rbp+57h+Object]; FileObject
0x14002fb1e  mov     [rsp+0C0h+var_98], r14; __int64
  ... truncated ...
```
