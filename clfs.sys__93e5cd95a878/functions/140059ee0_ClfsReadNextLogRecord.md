# ClfsReadNextLogRecord

- ea: `0x140059ee0`
- end: `0x14005a377`
- name: `ClfsReadNextLogRecord`
- size: `1175`
- prototype: `NTSTATUS __stdcall(PVOID pvReadContext, PVOID *ppvBuffer, PULONG pcbBuffer, PCLFS_RECORD_TYPE peRecordType, PCLFS_LSN plsnUser, PCLFS_LSN plsnUndoNext, PCLFS_LSN plsnPrevious, PCLFS_LSN plsnRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x140059ee0`
- `0x14005a380`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005a033`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005a033`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005a123`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079d5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005a123`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079d5f`

## string_xrefs

- `0x14005a10b`: `ClfsReadNextLogRecord`
- `0x14005a1eb`: `ClfsReadNextLogRecord`
- `0x14005a22e`: `ClfsReadNextLogRecord`
- `0x14005a35b`: `ClfsReadNextLogRecord`

## pseudocode

```c
NTSTATUS __stdcall ClfsReadNextLogRecord(
        PVOID pvReadContext,
        PVOID *ppvBuffer,
        PULONG pcbBuffer,
        PCLFS_RECORD_TYPE peRecordType,
        PCLFS_LSN plsnUser,
        PCLFS_LSN plsnUndoNext,
        PCLFS_LSN plsnPrevious,
        PCLFS_LSN plsnRecord)
{
  CLS_RECORD_TYPE v10; // cl
  int v11; // eax
  NTSTATUS v12; // r15d
  struct _CLFS_RECORD_HEADER *v13; // rdx
  struct _CLFS_RECORD_HEADER *v15; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int8 v16; // [rsp+70h] [rbp+8h]
  PVOID *v17; // [rsp+78h] [rbp+10h]
  ULONG *v18; // [rsp+80h] [rbp+18h]

  v18 = pcbBuffer;
  v17 = ppvBuffer;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      231,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadNextLogRecord",
      117);
    pcbBuffer = v18;
    ppvBuffer = v17;
  }
  if ( !pvReadContext || !peRecordType || !plsnUndoNext || !plsnPrevious || !plsnRecord || !ppvBuffer || !pcbBuffer )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        232,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadNextLogRecord",
        131,
        -1073741811);
    }
    return -1073741811;
  }
  *plsnUndoNext = CLFS_LSN_NULL;
  *plsnPrevious = CLFS_LSN_NULL;
  *plsnRecord = CLFS_LSN_NULL;
  *ppvBuffer = 0;
  *pcbBuffer = 0;
  if ( plsnUser && CLFS_LSN_INVALID.ullOffset == plsnUser->ullOffset )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        233,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadNextLogRecord",
        155,
        -1073741811);
    }
    return -1073741811;
  }
  v10 = *peRecordType;
  if ( *peRecordType )
  {
    if ( v10 != (v10 & 0x3F) )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          234,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsReadNextLogRecord",
          182,
          -1073741811);
      }
      return -1073741811;
    }
  }
  else
  {
    v10 = 1;
  }
  v16 = v10 & 3;
  if ( (v10 & 3) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        235,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadNextLogRecord",
        193,
        -1073741811);
    }
    return -1073741811;
  }
  if ( *(_DWORD *)pvReadContext != -1040322545
    || *((_DWORD *)pvReadContext + 1) != 176
    || (v11 = *((_DWORD *)pvReadContext + 32), (v11 & 0x14) == 0) )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        236,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadNextLogRecord",
        210,
        -1073741811);
    }
    return -1073741811;
  }
  if ( plsnUser )
  {
    if ( (v11 & 0x10) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          237,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsReadNextLogRecord",
          224,
          -1073741811);
      }
      return -1073741811;
    }
    if ( (unsigned int)(*((_DWORD *)pvReadContext + 18) - 1) > 1 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          238,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsReadNextLogRecord",
          240,
          -1073741811);
      }
      return -1073741811;
    }
  }
  if ( !*((_QWORD *)pvReadContext + 19) )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        239,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadNextLogRecord",
        254,
        -1073741811);
    }
    return -1073741811;
  }
  KeEnterCriticalRegion();
  v12 = CClfsKernelMarshallingContext::ReadNextLogRecord(
          *((CClfsKernelMarshallingContext **)pvReadContext + 19),
          (struct _LOGIOCB *)pvReadContext,
          v16,
          plsnUser,
          &v15);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        240,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadNextLogRecord",
        36,
        v12,
        v12);
    }
  }
  else
  {
    v13 = v15;
    *peRecordType = *((_BYTE *)v15 + 36);
    *plsnRecord = *(PCLFS_LSN)v13;
    *plsnUndoNext = *(CLFS_LSN *)((char *)v13 + 8);
    *plsnPrevious = *(CLFS_LSN *)((char *)v13 + 16);
    *v18 = *((_DWORD *)v13 + 6) - *((unsigned __int16 *)v13 + 17);
    *v17 = (char *)v13 + *((unsigned __int16 *)v13 + 17);
  }
  KeLeaveCriticalRegion();
  if ( v12 >= 0
    && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      241,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadNextLogRecord",
      70);
  }
  return v12;
}

```

## disassembly

```asm
0x140059ee0  mov     rax, rsp
0x140059ee3  mov     [rax+20h], r9
0x140059ee7  mov     [rax+18h], r8
0x140059eeb  mov     [rax+10h], rdx
0x140059eef  push    rbx
0x140059ef0  push    r12
0x140059ef2  push    r13
0x140059ef4  push    r14
0x140059ef6  push    r15
0x140059ef8  sub     rsp, 40h
0x140059efc  mov     r13, r9
0x140059eff  mov     r15, rcx
0x140059f02  mov     qword ptr [rax-30h], 0
0x140059f0a  lea     r14, WPP_GLOBAL_Control
0x140059f11  mov     rcx, cs:WPP_GLOBAL_Control
0x140059f18  mov     ebx, 4000000h
0x140059f1d  cmp     rcx, r14
0x140059f20  jz      short loc_140059F2B
0x140059f22  test    [rcx+2Ch], ebx
0x140059f25  jnz     loc_14005A221
0x140059f2b  test    r15, r15
0x140059f2e  jz      loc_14005A207
0x140059f34  test    r13, r13
0x140059f37  jz      loc_14005A207
0x140059f3d  mov     rcx, [rsp+68h+plsnUndoNext]
0x140059f45  test    rcx, rcx
0x140059f48  jz      loc_14005A207
0x140059f4e  mov     r9, [rsp+68h+plsnPrevious]
0x140059f56  test    r9, r9
0x140059f59  jz      loc_14005A207
0x140059f5f  mov     r10, [rsp+68h+plsnRecord]
0x140059f67  test    r10, r10
0x140059f6a  jz      loc_14005A207
0x140059f70  test    rdx, rdx
0x140059f73  jz      loc_14005A207
0x140059f79  test    r8, r8
0x140059f7c  jz      loc_14005A207
0x140059f82  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140059f89  mov     [rcx], rax
0x140059f8c  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140059f93  mov     [r9], rax
0x140059f96  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140059f9d  mov     [r10], rax
0x140059fa0  mov     qword ptr [rdx], 0
0x140059fa7  mov     dword ptr [r8], 0
0x140059fae  mov     r12, [rsp+68h+plsnUser]
0x140059fb6  test    r12, r12
0x140059fb9  jnz     loc_14005A14A
0x140059fbf  mov     cl, [r13+0]
0x140059fc3  test    cl, cl
0x140059fc5  jnz     loc_14005A18E
0x140059fcb  mov     cl, 1
0x140059fcd  and     cl, 3
0x140059fd0  mov     [rsp+68h+arg_0], cl
0x140059fd4  jz      loc_14005A257
0x140059fda  cmp     dword ptr [r15], 0C1FDF00Fh
0x140059fe1  jnz     loc_14005A30D
0x140059fe7  cmp     dword ptr [r15+4], 0B0h
0x140059fef  jnz     loc_14005A30D
0x140059ff5  mov     eax, [r15+80h]
0x140059ffc  test    al, 14h
0x140059ffe  jz      loc_14005A30D
0x14005a004  test    r12, r12
0x14005a007  jz      short loc_14005A025
0x14005a009  test    al, 10h
0x14005a00b  jnz     loc_14005A282
0x14005a011  test    r12, r12
0x14005a014  jz      short loc_14005A025
0x14005a016  mov     eax, [r15+48h]
0x14005a01a  dec     eax
0x14005a01c  cmp     eax, 1
0x14005a01f  ja      loc_14005A2AD
0x14005a025  cmp     qword ptr [r15+98h], 0
0x14005a02d  jz      loc_14005A2DD
0x14005a033  call    cs:__imp_KeEnterCriticalRegion
0x14005a03a  nop     dword ptr [rax+rax+00h]
0x14005a03f  nop
0x14005a040  lea     rax, [rsp+68h+var_30]
0x14005a045  mov     [rsp+68h+var_48], rax; struct _CLFS_RECORD_HEADER **
0x14005a04a  mov     r9, r12; union _CLS_LSN *
0x14005a04d  mov     r8b, [rsp+68h+arg_0]; unsigned __int8
0x14005a052  mov     rdx, r15; struct _LOGIOCB *
0x14005a055  mov     rcx, [r15+98h]; this
0x14005a05c  call    ?ReadNextLogRecord@CClfsKernelMarshallingContext@@QEAAJQEAXEQEAT_CLS_LSN@@AEAPEAU_CLFS_RECORD_HEADER@@@Z; CClfsKernelMarshallingContext::ReadNextLogRecord(void * const,uchar,_CLS_LSN * const,_CLFS_RECORD_HEADER * &)
0x14005a061  mov     r15d, eax
0x14005a064  mov     [rsp+68h+var_38], eax
0x14005a068  jmp     short loc_14005A085
0x14005a06a  mov     r15d, eax
0x14005a06d  mov     [rsp+68h+var_38], eax
0x14005a071  lea     r14, WPP_GLOBAL_Control
0x14005a078  mov     ebx, 4000000h
0x14005a07d  mov     r13, [rsp+68h+arg_18]
0x14005a085  test    r15d, r15d
0x14005a088  jnz     short loc_14005A0E6
0x14005a08a  mov     rdx, [rsp+68h+var_30]
0x14005a08f  mov     al, [rdx+24h]
0x14005a092  mov     [r13+0], al
0x14005a096  mov     rax, [rdx]
0x14005a099  mov     rcx, [rsp+68h+plsnRecord]
0x14005a0a1  mov     [rcx], rax
0x14005a0a4  mov     rax, [rdx+8]
0x14005a0a8  mov     rcx, [rsp+68h+plsnUndoNext]
0x14005a0b0  mov     [rcx], rax
0x14005a0b3  mov     rax, [rdx+10h]
0x14005a0b7  mov     rcx, [rsp+68h+plsnPrevious]
0x14005a0bf  mov     [rcx], rax
0x14005a0c2  movzx   eax, word ptr [rdx+22h]
0x14005a0c6  mov     ecx, [rdx+18h]
0x14005a0c9  sub     ecx, eax
0x14005a0cb  mov     rax, [rsp+68h+arg_10]
0x14005a0d3  mov     [rax], ecx
0x14005a0d5  movzx   eax, word ptr [rdx+22h]
0x14005a0d9  add     rax, rdx
0x14005a0dc  mov     rcx, [rsp+68h+arg_8]
0x14005a0e1  mov     [rcx], rax
0x14005a0e4  jmp     short loc_14005A123
0x14005a0e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a0ed  cmp     rcx, r14
0x14005a0f0  jz      short loc_14005A123
0x14005a0f2  mov     eax, [rcx+2Ch]
0x14005a0f5  test    ebx, eax
0x14005a0f7  jz      short loc_14005A123
0x14005a0f9  mov     edx, 0F0h
0x14005a0fe  mov     [rsp+68h+var_40], r15d
0x14005a103  mov     dword ptr [rsp+68h+var_48], 1D24h
0x14005a10b  lea     r9, aClfsreadnextlo; "ClfsReadNextLogRecord"
0x14005a112  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005a119  mov     rcx, [rcx+18h]
0x14005a11d  call    WPP_SF_slD
0x14005a122  nop
0x14005a123  call    cs:__imp_KeLeaveCriticalRegion
0x14005a12a  nop     dword ptr [rax+rax+00h]
0x14005a12f  test    r15d, r15d
0x14005a132  jns     loc_14005A1C5
0x14005a138  mov     eax, r15d
0x14005a13b  add     rsp, 40h
0x14005a13f  pop     r15
0x14005a141  pop     r14
0x14005a143  pop     r13
0x14005a145  pop     r12
0x14005a147  pop     rbx
0x14005a148  retn
0x14005a14a  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14005a151  cmp     rax, [r12]
0x14005a155  jnz     loc_140059FBF
0x14005a15b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a162  cmp     rcx, r14
0x14005a165  jz      loc_14005A217
0x14005a16b  test    [rcx+2Ch], ebx
0x14005a16e  jz      loc_14005A217
0x14005a174  mov     edx, 0E9h
0x14005a179  mov     [rsp+68h+var_40], 0C000000Dh
0x14005a181  mov     dword ptr [rsp+68h+var_48], 1C9Bh
0x14005a189  jmp     loc_14005A35B
0x14005a18e  mov     al, cl
0x14005a190  and     al, 3Fh
0x14005a192  cmp     cl, al
0x14005a194  jz      loc_140059FCD
0x14005a19a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a1a1  cmp     rcx, r14
0x14005a1a4  jz      short loc_14005A217
0x14005a1a6  test    [rcx+2Ch], ebx
0x14005a1a9  jz      short loc_14005A217
0x14005a1ab  mov     edx, 0EAh
0x14005a1b0  mov     [rsp+68h+var_40], 0C000000Dh
0x14005a1b8  mov     dword ptr [rsp+68h+var_48], 1CB6h
0x14005a1c0  jmp     loc_14005A35B
0x14005a1c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a1cc  cmp     rcx, r14
0x14005a1cf  jz      loc_14005A138
0x14005a1d5  test    [rcx+2Ch], ebx
0x14005a1d8  jz      loc_14005A138
0x14005a1de  mov     edx, 0F1h
0x14005a1e3  mov     dword ptr [rsp+68h+var_48], 1D46h
0x14005a1eb  lea     r9, aClfsreadnextlo; "ClfsReadNextLogRecord"
0x14005a1f2  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005a1f9  mov     rcx, [rcx+18h]
0x14005a1fd  call    WPP_SF_sd
0x14005a202  jmp     loc_14005A138
0x14005a207  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a20e  cmp     rcx, r14
0x14005a211  jnz     loc_14005A33D
0x14005a217  mov     eax, 0C000000Dh
0x14005a21c  jmp     loc_14005A13B
0x14005a221  mov     edx, 0E7h
0x14005a226  mov     dword ptr [rsp+68h+var_48], 1C75h
0x14005a22e  lea     r9, aClfsreadnextlo; "ClfsReadNextLogRecord"
0x14005a235  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005a23c  mov     rcx, [rcx+18h]
0x14005a240  call    WPP_SF_sd
0x14005a245  mov     r8, [rsp+68h+arg_10]
0x14005a24d  mov     rdx, [rsp+68h+arg_8]
0x14005a252  jmp     loc_140059F2B
0x14005a257  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a25e  cmp     rcx, r14
0x14005a261  jz      short loc_14005A217
0x14005a263  test    [rcx+2Ch], ebx
0x14005a266  jz      short loc_14005A217
0x14005a268  mov     edx, 0EBh
0x14005a26d  mov     [rsp+68h+var_40], 0C000000Dh
0x14005a275  mov     dword ptr [rsp+68h+var_48], 1CC1h
0x14005a27d  jmp     loc_14005A35B
0x14005a282  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a289  cmp     rcx, r14
0x14005a28c  jz      short loc_14005A217
0x14005a28e  test    [rcx+2Ch], ebx
0x14005a291  jz      short loc_14005A217
0x14005a293  mov     edx, 0EDh
0x14005a298  mov     [rsp+68h+var_40], 0C000000Dh
0x14005a2a0  mov     dword ptr [rsp+68h+var_48], 1CE0h
0x14005a2a8  jmp     loc_14005A35B
0x14005a2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a2b4  cmp     rcx, r14
0x14005a2b7  jz      loc_14005A217
0x14005a2bd  test    [rcx+2Ch], ebx
0x14005a2c0  jz      loc_14005A217
0x14005a2c6  mov     edx, 0EEh
0x14005a2cb  mov     [rsp+68h+var_40], 0C000000Dh
0x14005a2d3  mov     dword ptr [rsp+68h+var_48], 1CF0h
0x14005a2db  jmp     short loc_14005A35B
0x14005a2dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a2e4  cmp     rcx, r14
0x14005a2e7  jz      loc_14005A217
0x14005a2ed  test    [rcx+2Ch], ebx
0x14005a2f0  jz      loc_14005A217
0x14005a2f6  mov     edx, 0EFh
0x14005a2fb  mov     [rsp+68h+var_40], 0C000000Dh
0x14005a303  mov     dword ptr [rsp+68h+var_48], 1CFEh
0x14005a30b  jmp     short loc_14005A35B
0x14005a30d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a314  cmp     rcx, r14
0x14005a317  jz      loc_14005A217
0x14005a31d  test    [rcx+2Ch], ebx
0x14005a320  jz      loc_14005A217
0x14005a326  mov     edx, 0ECh
0x14005a32b  mov     [rsp+68h+var_40], 0C000000Dh
0x14005a333  mov     dword ptr [rsp+68h+var_48], 1CD2h
0x14005a33b  jmp     short loc_14005A35B
0x14005a33d  test    [rcx+2Ch], ebx
0x14005a340  jz      loc_14005A217
0x14005a346  mov     edx, 0E8h
0x14005a34b  mov     [rsp+68h+var_40], 0C000000Dh
0x14005a353  mov     dword ptr [rsp+68h+var_48], 1C83h
0x14005a35b  lea     r9, aClfsreadnextlo; "ClfsReadNextLogRecord"
0x14005a362  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005a369  mov     rcx, [rcx+18h]
0x14005a36d  call    WPP_SF_slD
0x14005a372  jmp     loc_14005A217
0x140079d56  push    rbp
0x140079d58  sub     rsp, 30h
0x140079d5c  mov     rbp, rdx
0x140079d5f  call    cs:__imp_KeLeaveCriticalRegion
0x140079d66  nop     dword ptr [rax+rax+00h]
0x140079d6b  nop
0x140079d6c  add     rsp, 30h
0x140079d70  pop     rbp
0x140079d71  retn
```
