# PpfEvtLogCreateFromTcgLog

- ea: `0x180027eb0`
- end: `0x18002833d`
- name: `PpfEvtLogCreateFromTcgLog`
- size: `1165`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1800107e8`
- `0x18001b2b0`
- `0x18001bd00`
- `0x18004de90`

## callees

- `0x180003270`
- `0x1800278c4`
- `0x180027944`
- `0x180027aec`
- `0x180027eb0`
- `0x1800290f4`
- `0x180055158`
- `0x1800551f8`
- `0x1800554ec`
- `0x180059010`

## string_xrefs

- `0x180027f62`: `PpfEvtLogCreateFromTcgLog`
- `0x180028106`: `PpfEvtLogCreateFromTcgLog`
- `0x18002830c`: `PpfEvtLogCreateFromTcgLog`

## pseudocode

```c
__int64 __fastcall PpfEvtLogCreateFromTcgLog(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4, __int64 a5)
{
  char v5; // r12
  __int64 v6; // r15
  void *v7; // r14
  int v8; // edx
  unsigned int v9; // ebx
  int inited; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // r13d
  __int64 v13; // rax
  unsigned int v14; // r15d
  int EventDigestTableFromWbclEvent; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // edx
  int v20; // eax
  __int64 v21; // rax
  __int64 (*v22)(void); // rax
  char Size; // [rsp+28h] [rbp-D8h]
  size_t Sizea; // [rsp+28h] [rbp-D8h]
  size_t v26; // [rsp+38h] [rbp-C8h]
  size_t v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+5Ch] [rbp-A4h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch] BYREF
  void *Src; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  unsigned int v35; // [rsp+80h] [rbp-80h]
  void *v36; // [rsp+88h] [rbp-78h] BYREF
  int v37[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[46]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v39; // [rsp+C8h] [rbp-38h]
  _DWORD *v40; // [rsp+D0h] [rbp-30h]
  _OWORD v41[3]; // [rsp+D8h] [rbp-28h] BYREF

  v5 = 0;
  v40 = a4;
  v35 = a2;
  v39 = a3;
  v6 = a1;
  v34 = a1;
  v7 = 0;
  v33 = 0;
  v31 = 0;
  *(_QWORD *)v37 = 0;
  v28 = 0;
  v27 = 0;
  v36 = 0;
  Src = 0;
  v29 = 0;
  memset(v38, 0, sizeof(v38));
  memset(v41, 0, sizeof(v41));
  if ( !a1 )
  {
    v8 = 1710;
LABEL_3:
    v9 = -1073741811;
    Size = 13;
LABEL_4:
    PpfEvtLogTraceHelper(
      (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
      v8,
      (int)"PpfEvtLogCreateFromTcgLog",
      1,
      "Error: 0x%x",
      Size);
    goto LABEL_46;
  }
  if ( !a3 )
  {
    v8 = 1714;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 1718;
    goto LABEL_3;
  }
  if ( a5 )
    *(_QWORD *)a5 = 1572864;
  inited = WbclApiInitIterator(a1, a2, v38);
  if ( inited < 0 )
  {
    v8 = 1736;
    v9 = inited & 0xAFFFFFFF | 0x40000000;
    Size = v9;
    goto LABEL_4;
  }
  v11 = 0;
  v30 = 0;
  v12 = 0;
  if ( !(unsigned int)WbclApiGetCurrentElement((struct _WBCL_Iterator *)v38, (unsigned int *)&v27, 0) )
  {
    while ( a5 )
    {
      ++*(_WORD *)a5;
      if ( HIDWORD(v27) == 3 )
        break;
      v13 = (unsigned int)v28;
      if ( (unsigned int)v28 < 0x18 )
        *(_WORD *)(a5 + 2) = v28;
      if ( !v5 )
        goto LABEL_23;
      ++*(_WORD *)(a5 + 4);
      if ( (unsigned int)v13 < 0x18 )
        *(_WORD *)(a5 + 6) = ++*((_WORD *)v41 + v13);
LABEL_24:
      v14 = v11 + v27;
      if ( v11 + (unsigned int)v27 < v11 )
      {
        v9 = -1073741675;
        PpfEvtLogTraceHelper(
          (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
          1776,
          (int)"PpfEvtLogCreateFromTcgLog",
          1,
          "Error: 0x%x",
          149);
        goto LABEL_46;
      }
      EventDigestTableFromWbclEvent = PpfEvtLogCreateEventDigestTableFromWbclEvent((struct _WBCL_Iterator *)v38);
      v9 = EventDigestTableFromWbclEvent;
      if ( EventDigestTableFromWbclEvent < 0 )
      {
        PpfEvtLogTraceHelper(
          (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
          1781,
          (int)"PpfEvtLogCreateFromTcgLog",
          1,
          "Error: 0x%x",
          EventDigestTableFromWbclEvent);
        goto LABEL_46;
      }
      if ( v12 + v29 < v12 )
      {
        v9 = -1073741675;
        PpfEvtLogTraceHelper(
          (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
          1786,
          (int)"PpfEvtLogCreateFromTcgLog",
          1,
          "Error: 0x%x",
          149);
        goto LABEL_46;
      }
      ++v30;
      v12 += v29;
      v11 = v14;
      if ( (unsigned int)WbclApiMoveToNextElement((struct _WBCL_Iterator *)v38)
        || (unsigned int)WbclApiGetCurrentElement((struct _WBCL_Iterator *)v38, (unsigned int *)&v27, 0) )
      {
        v6 = v34;
        goto LABEL_30;
      }
    }
    if ( v5 )
      goto LABEL_24;
LABEL_23:
    v5 = 1;
    goto LABEL_24;
  }
LABEL_30:
  if ( a5 )
    PpfEvtLogTraceHelper(
      (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
      1802,
      (int)"PpfEvtLogCreateFromTcgLog",
      0,
      "NumberOfEvents: %u, LastValidEventPcr: %u, LastValidSourceEventIndex: %u, LastValidEventPcrEventCountIndex: %u",
      *(_WORD *)a5);
  v16 = PpfEvtLogAllocateAndInitializeHeader(
          *(unsigned __int16 *)&v38[44],
          *(_DWORD *)&v38[40],
          v30,
          v12,
          v11,
          0,
          (__int64)&v33,
          (__int64)&v31,
          (__int64)v37);
  v9 = v16;
  if ( v16 >= 0 )
  {
    v17 = WbclApiInitIterator(v6, v35, v38);
    if ( v17 >= 0 )
    {
      while ( 1 )
      {
        if ( (unsigned int)WbclApiGetCurrentElement((struct _WBCL_Iterator *)v38, (unsigned int *)&v27, (__int64)&v36) )
        {
LABEL_45:
          v21 = v33;
          v33 = 0;
          *v39 = v21;
          *v40 = v31;
          goto LABEL_46;
        }
        if ( v7 )
        {
          ((void (__fastcall *)(void *))FreeFn)(v7);
          Src = 0;
          v29 = 0;
        }
        v18 = PpfEvtLogCreateEventDigestTableFromWbclEvent((struct _WBCL_Iterator *)v38);
        v9 = v18;
        if ( v18 < 0 )
          break;
        v7 = Src;
        LODWORD(v26) = v27;
        LODWORD(Sizea) = v29;
        v20 = PpfEvtLogAddEventAndMovePast((int)v37, v19, SHIDWORD(v27), v28, Src, Sizea, v36, v26);
        v9 = v20;
        if ( v20 < 0 )
        {
          PpfEvtLogTraceHelper(
            (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
            1863,
            (int)"PpfEvtLogCreateFromTcgLog",
            1,
            "Error: 0x%x",
            v20);
          goto LABEL_46;
        }
        if ( (unsigned int)WbclApiMoveToNextElement((struct _WBCL_Iterator *)v38) )
          goto LABEL_45;
      }
      PpfEvtLogTraceHelper(
        (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
        1851,
        (int)"PpfEvtLogCreateFromTcgLog",
        1,
        "Error: 0x%x",
        v18);
      v7 = Src;
    }
    else
    {
      v9 = v17 & 0xAFFFFFFF | 0x40000000;
    }
  }
  else
  {
    PpfEvtLogTraceHelper(
      (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
      1819,
      (int)"PpfEvtLogCreateFromTcgLog",
      1,
      "Error: 0x%x",
      v16);
  }
LABEL_46:
  v22 = FreeFn;
  if ( FreeFn && v33 )
  {
    FreeFn();
    v22 = FreeFn;
  }
  if ( v7 )
    ((void (__fastcall *)(void *))v22)(v7);
  return v9;
}

```

## disassembly

```asm
0x180027eb0  push    rbp
0x180027eb2  push    rbx
0x180027eb3  push    rsi
0x180027eb4  push    rdi
0x180027eb5  push    r12
0x180027eb7  push    r13
0x180027eb9  push    r14
0x180027ebb  push    r15
0x180027ebd  lea     rbp, [rsp-18h]
0x180027ec2  sub     rsp, 118h
0x180027ec9  mov     rax, cs:__security_cookie
0x180027ed0  xor     rax, rsp
0x180027ed3  mov     [rbp+50h+var_48], rax
0x180027ed7  mov     rsi, [rbp+50h+arg_20]
0x180027ede  xor     r12d, r12d
0x180027ee1  mov     [rbp+50h+var_80], r9
0x180027ee5  xorps   xmm0, xmm0
0x180027ee8  mov     [rbp+50h+var_D0], edx
0x180027eeb  mov     rax, r8
0x180027eee  mov     [rbp+50h+var_88], rax
0x180027ef2  mov     r15, rcx
0x180027ef5  mov     [rsp+150h+var_D8], rcx
0x180027efa  mov     r14d, r12d
0x180027efd  mov     [rsp+150h+var_E0], r12
0x180027f02  mov     [rsp+150h+var_EC], r12d
0x180027f07  mov     qword ptr [rbp+50h+var_C0], r12
0x180027f0b  mov     [rsp+150h+var_F8], r12d
0x180027f10  mov     dword ptr [rsp+150h+var_100+4], r12d
0x180027f15  mov     dword ptr [rsp+150h+var_100], r12d
0x180027f1a  mov     [rbp+50h+var_C8], r12
0x180027f1e  mov     [rsp+150h+var_E8], r12
0x180027f23  mov     dword ptr [rsp+150h+var_F4], r12d
0x180027f28  movups  xmmword ptr [rbp+50h+var_B8.currentElementPtr+4], xmm0
0x180027f2c  movups  xmmword ptr [rbp+50h+var_B8.numberOfDigests+2], xmm0
0x180027f30  movups  xmmword ptr [rbp+50h+var_B8.firstElementPtr], xmm0
0x180027f34  movups  [rbp+50h+var_78], xmm0
0x180027f38  movups  [rbp+50h+var_68], xmm0
0x180027f3c  movups  [rbp+50h+var_58], xmm0
0x180027f40  test    rcx, rcx
0x180027f43  jnz     short loc_180027F7F
0x180027f45  mov     edx, 6AEh; int
0x180027f4a  mov     eax, 0C000000Dh
0x180027f4f  mov     ebx, eax
0x180027f51  mov     dword ptr [rsp+150h+Size], eax; char
0x180027f55  mov     r9d, 1; int
0x180027f5b  lea     rax, aError0xX; "Error: 0x%x"
0x180027f62  lea     r8, aPpfevtlogcreat; "PpfEvtLogCreateFromTcgLog"
0x180027f69  mov     [rsp+150h+Src], rax; Format
0x180027f6e  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x180027f75  call    PpfEvtLogTraceHelper
0x180027f7a  jmp     loc_1800282A5
0x180027f7f  test    rax, rax
0x180027f82  jnz     short loc_180027F8B
0x180027f84  mov     edx, 6B2h
0x180027f89  jmp     short loc_180027F4A
0x180027f8b  test    r9, r9
0x180027f8e  jnz     short loc_180027F97
0x180027f90  mov     edx, 6B6h
0x180027f95  jmp     short loc_180027F4A
0x180027f97  test    rsi, rsi
0x180027f9a  jz      short loc_180027FA3
0x180027f9c  mov     qword ptr [rsi], 180000h
0x180027fa3  lea     r8, [rbp+50h+var_B8]
0x180027fa7  mov     rcx, r15
0x180027faa  call    WbclApiInitIterator
0x180027faf  mov     ebx, eax
0x180027fb1  test    eax, eax
0x180027fb3  jns     short loc_180027FC8
0x180027fb5  btr     ebx, 1Ch
0x180027fb9  mov     edx, 6C8h
0x180027fbe  bts     ebx, 1Eh
0x180027fc2  mov     dword ptr [rsp+150h+Size], ebx
0x180027fc6  jmp     short loc_180027F55
0x180027fc8  xor     ebx, ebx
0x180027fca  lea     rax, [rsp+150h+var_100]
0x180027fcf  mov     [rsp+150h+Size], rbx; __int64
0x180027fd4  lea     r8, [rsp+150h+var_100+4]
0x180027fd9  xor     r9d, r9d
0x180027fdc  mov     [rsp+150h+Src], rax; unsigned int *
0x180027fe1  lea     rdx, [rsp+150h+var_F8]
0x180027fe6  mov     dword ptr [rsp+150h+var_F4+4], ebx
0x180027fea  lea     rcx, [rbp+50h+var_B8]; struct _WBCL_Iterator *
0x180027fee  xor     r13d, r13d
0x180027ff1  call    WbclApiGetCurrentElement
0x180027ff6  lea     edi, [rbx+1]
0x180027ff9  test    eax, eax
0x180027ffb  jnz     loc_1800280C7
0x180028001  test    rsi, rsi
0x180028004  jz      short loc_18002803B
0x180028006  add     [rsi], di
0x180028009  cmp     dword ptr [rsp+150h+var_100+4], 3
0x18002800e  jz      short loc_18002803B
0x180028010  mov     eax, [rsp+150h+var_F8]
0x180028014  cmp     eax, 18h
0x180028017  jnb     short loc_18002801D
0x180028019  mov     [rsi+2], ax
0x18002801d  test    r12b, r12b
0x180028020  jz      short loc_180028040
0x180028022  add     [rsi+4], di
0x180028026  cmp     eax, 18h
0x180028029  jnb     short loc_180028043
0x18002802b  add     word ptr [rbp+rax*2+50h+var_78], di
0x180028030  movzx   eax, word ptr [rbp+rax*2+50h+var_78]
0x180028035  mov     [rsi+6], ax
0x180028039  jmp     short loc_180028043
0x18002803b  test    r12b, r12b
0x18002803e  jnz     short loc_180028043
0x180028040  mov     r12b, dil
0x180028043  mov     r15d, dword ptr [rsp+150h+var_100]
0x180028048  add     r15d, ebx
0x18002804b  cmp     r15d, ebx
0x18002804e  jb      loc_180028191
0x180028054  lea     r8, [rsp+150h+var_F4]
0x180028059  xor     edx, edx
0x18002805b  lea     rcx, [rbp+50h+var_B8]; struct _WBCL_Iterator *
0x18002805f  call    PpfEvtLogCreateEventDigestTableFromWbclEvent
0x180028064  mov     ebx, eax
0x180028066  test    eax, eax
0x180028068  js      loc_180028180
0x18002806e  mov     ecx, dword ptr [rsp+150h+var_F4]
0x180028072  add     ecx, r13d
0x180028075  cmp     ecx, r13d
0x180028078  jb      loc_180028168
0x18002807e  add     dword ptr [rsp+150h+var_F4+4], edi
0x180028082  mov     r13d, ecx
0x180028085  lea     rcx, [rbp+50h+var_B8]; struct _WBCL_Iterator *
0x180028089  mov     ebx, r15d
0x18002808c  call    WbclApiMoveToNextElement
0x180028091  test    eax, eax
0x180028093  jnz     short loc_1800280C2
0x180028095  lea     rax, [rsp+150h+var_100]
0x18002809a  mov     [rsp+150h+Size], r14; __int64
0x18002809f  xor     r9d, r9d
0x1800280a2  mov     [rsp+150h+Src], rax; unsigned int *
0x1800280a7  lea     r8, [rsp+150h+var_100+4]
0x1800280ac  lea     rdx, [rsp+150h+var_F8]
0x1800280b1  lea     rcx, [rbp+50h+var_B8]; struct _WBCL_Iterator *
0x1800280b5  call    WbclApiGetCurrentElement
0x1800280ba  test    eax, eax
0x1800280bc  jz      loc_180028001
0x1800280c2  mov     r15, [rsp+150h+var_D8]
0x1800280c7  xor     r12d, r12d
0x1800280ca  test    rsi, rsi
0x1800280cd  jz      short loc_180028117
0x1800280cf  movzx   eax, word ptr [rsi+6]
0x1800280d3  xor     r9d, r9d; int
0x1800280d6  movzx   ecx, word ptr [rsi+4]
0x1800280da  movzx   edx, word ptr [rsi+2]
0x1800280de  movzx   r8d, word ptr [rsi]
0x1800280e2  mov     dword ptr [rsp+150h+var_110], eax
0x1800280e6  lea     rax, aNumberofevents; "NumberOfEvents: %u, LastValidEventPcr: "...
0x1800280ed  mov     dword ptr [rsp+150h+var_118], ecx
0x1800280f1  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x1800280f8  mov     dword ptr [rsp+150h+var_120], edx
0x1800280fc  mov     edx, 70Ah; int
0x180028101  mov     dword ptr [rsp+150h+Size], r8d; char
0x180028106  lea     r8, aPpfevtlogcreat; "PpfEvtLogCreateFromTcgLog"
0x18002810d  mov     [rsp+150h+Src], rax; Format
0x180028112  call    PpfEvtLogTraceHelper
0x180028117  mov     r8d, dword ptr [rsp+150h+var_F4+4]
0x18002811c  lea     rax, [rbp+50h+var_C0]
0x180028120  mov     edx, dword ptr [rbp+50h+var_B8.hashAlgorithm]
0x180028123  mov     r9d, r13d
0x180028126  movzx   ecx, [rbp+50h+var_8C]
0x18002812a  mov     [rsp+150h+var_110], rax
0x18002812f  lea     rax, [rsp+150h+var_EC]
0x180028134  mov     [rsp+150h+var_118], rax
0x180028139  lea     rax, [rsp+150h+var_E0]
0x18002813e  mov     [rsp+150h+var_120], rax
0x180028143  mov     dword ptr [rsp+150h+Size], r12d
0x180028148  mov     dword ptr [rsp+150h+Src], ebx
0x18002814c  call    PpfEvtLogAllocateAndInitializeHeader
0x180028151  mov     ebx, eax
0x180028153  test    eax, eax
0x180028155  jns     short loc_1800281A9
0x180028157  mov     dword ptr [rsp+150h+Size], eax
0x18002815b  mov     r9d, edi
0x18002815e  mov     edx, 71Bh
0x180028163  jmp     loc_180027F5B
0x180028168  mov     eax, 0C0000095h
0x18002816d  mov     r9d, edi
0x180028170  mov     ebx, eax
0x180028172  mov     dword ptr [rsp+150h+Size], eax
0x180028176  mov     edx, 6FAh
0x18002817b  jmp     loc_180027F5B
0x180028180  mov     dword ptr [rsp+150h+Size], eax
0x180028184  mov     r9d, edi
0x180028187  mov     edx, 6F5h
0x18002818c  jmp     loc_180027F5B
0x180028191  mov     eax, 0C0000095h
0x180028196  mov     r9d, edi
0x180028199  mov     ebx, eax
0x18002819b  mov     dword ptr [rsp+150h+Size], eax
0x18002819f  mov     edx, 6F0h
0x1800281a4  jmp     loc_180027F5B
0x1800281a9  mov     edx, [rbp+50h+var_D0]
0x1800281ac  lea     r8, [rbp+50h+var_B8]
0x1800281b0  mov     rcx, r15
0x1800281b3  call    WbclApiInitIterator
0x1800281b8  test    eax, eax
0x1800281ba  jns     loc_180028257
0x1800281c0  mov     ebx, eax
0x1800281c2  btr     ebx, 1Ch
0x1800281c6  bts     ebx, 1Eh
0x1800281ca  jmp     loc_1800282A5
0x1800281cf  test    r14, r14
0x1800281d2  jz      short loc_1800281ED
0x1800281d4  mov     rax, cs:_FreeFn
0x1800281db  mov     rcx, r14
0x1800281de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e3  mov     [rsp+150h+var_E8], r12
0x1800281e8  mov     dword ptr [rsp+150h+var_F4], r12d
0x1800281ed  lea     r8, [rsp+150h+var_F4]
0x1800281f2  lea     rdx, [rsp+150h+var_E8]
0x1800281f7  lea     rcx, [rbp+50h+var_B8]; struct _WBCL_Iterator *
0x1800281fb  call    PpfEvtLogCreateEventDigestTableFromWbclEvent
0x180028200  mov     ebx, eax
0x180028202  test    eax, eax
0x180028204  js      loc_180028308
0x18002820a  mov     eax, dword ptr [rsp+150h+var_100]
0x18002820e  lea     rcx, [rbp+50h+var_C0]; int
0x180028212  mov     r14, [rsp+150h+var_E8]
0x180028217  mov     r9d, [rsp+150h+var_F8]; int
0x18002821c  mov     r8d, dword ptr [rsp+150h+var_100+4]; int
0x180028221  mov     dword ptr [rsp+150h+var_118], eax; size_t
0x180028225  mov     rax, [rbp+50h+var_C8]
0x180028229  mov     [rsp+150h+var_120], rax; void *
0x18002822e  mov     eax, dword ptr [rsp+150h+var_F4]
0x180028232  mov     dword ptr [rsp+150h+Size], eax; Size
0x180028236  mov     [rsp+150h+Src], r14; Src
0x18002823b  call    PpfEvtLogAddEventAndMovePast
0x180028240  mov     ebx, eax
0x180028242  test    eax, eax
0x180028244  js      loc_1800282F7
0x18002824a  lea     rcx, [rbp+50h+var_B8]; struct _WBCL_Iterator *
0x18002824e  call    WbclApiMoveToNextElement
0x180028253  test    eax, eax
0x180028255  jnz     short loc_18002828A
0x180028257  lea     rax, [rbp+50h+var_C8]
0x18002825b  mov     [rsp+150h+Size], rax; __int64
0x180028260  lea     r9, [rsp+150h+var_D8]
0x180028265  lea     rax, [rsp+150h+var_100]
0x18002826a  lea     r8, [rsp+150h+var_100+4]
0x18002826f  mov     [rsp+150h+Src], rax; unsigned int *
0x180028274  lea     rdx, [rsp+150h+var_F8]
0x180028279  lea     rcx, [rbp+50h+var_B8]; struct _WBCL_Iterator *
0x18002827d  call    WbclApiGetCurrentElement
0x180028282  test    eax, eax
0x180028284  jz      loc_1800281CF
0x18002828a  mov     rax, [rsp+150h+var_E0]
0x18002828f  mov     rcx, [rbp+50h+var_88]
0x180028293  mov     [rsp+150h+var_E0], r12
0x180028298  mov     [rcx], rax
0x18002829b  mov     rcx, [rbp+50h+var_80]
0x18002829f  mov     eax, [rsp+150h+var_EC]
0x1800282a3  mov     [rcx], eax
0x1800282a5  mov     rax, cs:_FreeFn
0x1800282ac  test    rax, rax
0x1800282af  jz      short loc_1800282C7
0x1800282b1  mov     rcx, [rsp+150h+var_E0]
0x1800282b6  test    rcx, rcx
0x1800282b9  jz      short loc_1800282C7
0x1800282bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282c0  mov     rax, cs:_FreeFn
0x1800282c7  test    r14, r14
0x1800282ca  jz      short loc_1800282D4
0x1800282cc  mov     rcx, r14
0x1800282cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282d4  mov     eax, ebx
0x1800282d6  mov     rcx, [rbp+50h+var_48]
0x1800282da  xor     rcx, rsp; StackCookie
0x1800282dd  call    __security_check_cookie
0x1800282e2  add     rsp, 118h
0x1800282e9  pop     r15
0x1800282eb  pop     r14
0x1800282ed  pop     r13
0x1800282ef  pop     r12
0x1800282f1  pop     rdi
0x1800282f2  pop     rsi
0x1800282f3  pop     rbx
0x1800282f4  pop     rbp
0x1800282f5  retn
0x1800282f7  mov     dword ptr [rsp+150h+Size], eax
0x1800282fb  mov     r9d, edi
0x1800282fe  mov     edx, 747h
0x180028303  jmp     loc_180027F5B
0x180028308  mov     dword ptr [rsp+150h+Size], eax; char
0x18002830c  lea     r8, aPpfevtlogcreat; "PpfEvtLogCreateFromTcgLog"
0x180028313  lea     rax, aError0xX; "Error: 0x%x"
0x18002831a  mov     r9d, edi; int
0x18002831d  mov     edx, 73Bh; int
0x180028322  mov     [rsp+150h+Src], rax; Format
0x180028327  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x18002832e  call    PpfEvtLogTraceHelper
0x180028333  mov     r14, [rsp+150h+var_E8]
0x180028338  jmp     loc_1800282A5
```
