# CScrub::LogLastVolumeScrubResult(long,uchar)

- ea: `0x180021db4`
- end: `0x180022265`
- name: `?LogLastVolumeScrubResult@CScrub@@QEAAXJE@Z`
- size: `1201`
- prototype: `void __fastcall(CScrub *this, int, char)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001ec84`
- `0x1800273d8`

## callees

- `0x18000b8b8`
- `0x18000bfcc`
- `0x180012158`
- `0x1800137d4`
- `0x180021db4`
- `0x18002cfe4`
- `0x18002d1a0`
- `0x18002d2bc`
- `0x18002d440`
- `0x18002d558`
- `0x18002d674`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800221e2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800221e2`

## string_xrefs

- `0x180021e05`: `Completed`
- `0x180021ef6`: `Completed`
- `0x180021f71`: `Completed`
- `0x180021fcb`: `Completed`
- `0x180022062`: `Completed`
- `0x1800220d3`: `Completed`
- `0x18002213f`: `Completed`
- `0x180022197`: `Completed`

## pseudocode

```c
void __fastcall CScrub::LogLastVolumeScrubResult(CScrub *this, int a2, char a3)
{
  int v4; // eax
  __int64 v5; // rsi
  int v6; // r12d
  char v8; // r15
  const char *v9; // r14
  PVOID *v10; // r10
  const char *v11; // rcx
  const char *v12; // rcx
  const char *v13; // rcx
  const char *v14; // rcx
  const char *v15; // rax
  const char *v16; // rax
  unsigned int i; // edi
  __int64 v18; // r8
  RTL_SRWLOCK *v19; // [rsp+B0h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 315);
  v5 = *((_QWORD *)this + 163) + 16LL;
  v6 = a2;
  if ( (v4 & 0x40000000) != 0 )
  {
    v8 = 1;
  }
  else if ( (v4 & 0x20000000) != 0 )
  {
    v8 = 2;
  }
  else
  {
    v8 = 0;
  }
  v9 = "Progress";
  if ( a3 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        188,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        *(_WORD *)(*((_QWORD *)this + 163) + 184LL));
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    v6 = 0;
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_28;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZld(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        *((_BYTE *)this + 1497),
        a2);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    {
      v11 = "Progress";
      if ( !a3 )
        v11 = "Completed";
      WPP_SF_DDZsIIIII(
        (TRACEHANDLE)v10[2],
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)v11,
        *(_QWORD *)(v5 + 32),
        *(_QWORD *)(v5 + 24),
        *(_QWORD *)(v5 + 40),
        *(_QWORD *)(v5 + 48),
        *(_QWORD *)(v5 + 56));
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    {
      v12 = "Progress";
      if ( !a3 )
        v12 = "Completed";
      WPP_SF_DDZsii(
        (TRACEHANDLE)v10[2],
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)v12,
        *(_QWORD *)(v5 + 8),
        *(_QWORD *)(v5 + 16));
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_28:
  if ( (*((_DWORD *)this + 315) & 0x20000000) == 0 )
  {
LABEL_41:
    if ( v10 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
      {
        v15 = "Progress";
        if ( !a3 )
          v15 = "Completed";
        WPP_SF_DDZsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          (__int64)v15,
          *((_DWORD *)this + 343));
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
        {
          v16 = "Progress";
          if ( !a3 )
            v16 = "Completed";
          WPP_SF_DDZsi(
            (TRACEHANDLE)v10[2],
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            (__int64)v16,
            16 * *(_BYTE *)v5);
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
        {
          if ( !a3 )
            v9 = "Completed";
          WPP_SF_DDZsI(
            (TRACEHANDLE)v10[2],
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            (__int64)v9,
            *(_QWORD *)v5);
        }
      }
    }
    goto LABEL_59;
  }
  if ( v10 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    {
      v13 = "Progress";
      if ( !a3 )
        v13 = "Completed";
      WPP_SF_DDZsii(
        (TRACEHANDLE)v10[2],
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)v13,
        *(_QWORD *)(v5 + 64),
        *(_QWORD *)(v5 + 72));
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
      {
        v14 = "Progress";
        if ( !a3 )
          v14 = "Completed";
        WPP_SF_DDZsii(
          (TRACEHANDLE)v10[2],
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          (__int64)v14,
          *(_QWORD *)(v5 + 80),
          *(_QWORD *)(v5 + 88));
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_41;
    }
  }
LABEL_59:
  v19 = (RTL_SRWLOCK *)((char *)this + 1504);
  AcquireSRWLockExclusive((PSRWLOCK)this + 188);
  for ( i = 0; i < *((_DWORD *)this + 378); ++i )
    EventWriteScrubError(
      *((struct _SCRUB_ENVIRONMENT **)this + 1),
      *(const struct _SCRUB_VOLUME_IDENTIFIER **)this,
      (CScrub *)((char *)this + 40 * i + 1520));
  CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v19);
  LOBYTE(v18) = a3;
  EventWriteVolumeScanComplete(
    *((struct _SCRUB_ENVIRONMENT **)this + 1),
    *(const struct _SCRUB_VOLUME_IDENTIFIER **)this,
    v18,
    *((_BYTE *)this + 1497),
    v6,
    (const struct _SCRUB_CHECKPOINT_STATS *)v5,
    *((_DWORD *)this + 342),
    v8);
}

```

## disassembly

```asm
0x180021db4  push    rbx
0x180021db6  push    rbp
0x180021db7  push    rsi
0x180021db8  push    rdi
0x180021db9  push    r12
0x180021dbb  push    r13
0x180021dbd  push    r14
0x180021dbf  push    r15
0x180021dc1  sub     rsp, 68h
0x180021dc5  mov     rsi, [rcx+518h]
0x180021dcc  mov     bpl, r8b
0x180021dcf  mov     eax, [rcx+4ECh]
0x180021dd5  add     rsi, 10h
0x180021dd9  mov     r12d, edx
0x180021ddc  mov     rbx, rcx
0x180021ddf  mov     r13d, 1
0x180021de5  bt      eax, 1Eh
0x180021de9  jnb     short loc_180021DF1
0x180021deb  movzx   r15d, r13w
0x180021def  jmp     short loc_180021E05
0x180021df1  bt      eax, 1Dh
0x180021df5  jnb     short loc_180021DFF
0x180021df7  mov     r15d, 2
0x180021dfd  jmp     short loc_180021E05
0x180021dff  xor     eax, eax
0x180021e01  movzx   r15d, ax
0x180021e05  lea     rax, aCompleted; "Completed"
0x180021e0c  lea     r14, aProgress; "Progress"
0x180021e13  test    bpl, bpl
0x180021e16  jz      short loc_180021E7F
0x180021e18  mov     r10, cs:WPP_GLOBAL_Control
0x180021e1f  lea     rdi, WPP_GLOBAL_Control
0x180021e26  cmp     r10, rdi
0x180021e29  jz      short loc_180021E7A
0x180021e2b  test    [r10+1Ch], r13b
0x180021e2f  jz      short loc_180021E7A
0x180021e31  cmp     byte ptr [r10+19h], 4
0x180021e36  jb      short loc_180021E7A
0x180021e38  mov     r8, [rcx]
0x180021e3b  mov     edx, 0BCh
0x180021e40  movzx   eax, word ptr [rsi+0A8h]
0x180021e47  mov     rcx, [r10+10h]
0x180021e4b  mov     [rsp+0A8h+var_78], eax
0x180021e4f  mov     r9, [r8]
0x180021e52  mov     rax, [r8+40h]
0x180021e56  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180021e5d  mov     [rsp+0A8h+var_80], rax
0x180021e62  mov     eax, [r9+24h]
0x180021e66  mov     r9d, [r9+10h]
0x180021e6a  mov     dword ptr [rsp+0A8h+var_88], eax
0x180021e6e  call    WPP_SF_DDZd
0x180021e73  mov     r10, cs:WPP_GLOBAL_Control
0x180021e7a  xor     r12d, r12d
0x180021e7d  jmp     short loc_180021EDD
0x180021e7f  mov     r10, cs:WPP_GLOBAL_Control
0x180021e86  lea     rdi, WPP_GLOBAL_Control
0x180021e8d  cmp     r10, rdi
0x180021e90  jz      loc_180021FD2
0x180021e96  test    [r10+1Ch], r13b
0x180021e9a  jz      short loc_180021EDD
0x180021e9c  cmp     byte ptr [r10+19h], 4
0x180021ea1  jb      short loc_180021EDD
0x180021ea3  mov     rcx, [rcx]
0x180021ea6  movzx   eax, byte ptr [rbx+5D9h]
0x180021ead  mov     dword ptr [rsp+0A8h+var_70], edx
0x180021eb1  mov     [rsp+0A8h+var_78], eax
0x180021eb5  mov     r9, [rcx]
0x180021eb8  mov     rax, [rcx+40h]
0x180021ebc  mov     rcx, [r10+10h]
0x180021ec0  mov     [rsp+0A8h+var_80], rax
0x180021ec5  mov     eax, [r9+24h]
0x180021ec9  mov     r9d, [r9+10h]
0x180021ecd  mov     dword ptr [rsp+0A8h+var_88], eax
0x180021ed1  call    WPP_SF_DDZld
0x180021ed6  mov     r10, cs:WPP_GLOBAL_Control
0x180021edd  cmp     r10, rdi
0x180021ee0  jz      loc_180021FCB
0x180021ee6  test    [r10+1Ch], r13b
0x180021eea  jz      short loc_180021F61
0x180021eec  cmp     byte ptr [r10+19h], 4
0x180021ef1  jb      short loc_180021F61
0x180021ef3  mov     rdx, [rbx]
0x180021ef6  lea     rax, aCompleted; "Completed"
0x180021efd  test    bpl, bpl
0x180021f00  mov     rcx, r14
0x180021f03  cmovz   rcx, rax
0x180021f07  mov     rax, [rsi+38h]
0x180021f0b  mov     r9, [rdx]
0x180021f0e  mov     qword ptr [rsp+0A8h+var_50], rax; char
0x180021f13  mov     rax, [rsi+30h]
0x180021f17  mov     qword ptr [rsp+0A8h+var_58], rax; char
0x180021f1c  mov     rax, [rsi+28h]
0x180021f20  mov     qword ptr [rsp+0A8h+var_60], rax; char
0x180021f25  mov     rax, [rsi+18h]
0x180021f29  mov     qword ptr [rsp+0A8h+var_68], rax; char
0x180021f2e  mov     rax, [rsi+20h]
0x180021f32  mov     qword ptr [rsp+0A8h+var_70], rax; char
0x180021f37  mov     rax, [rdx+40h]
0x180021f3b  mov     qword ptr [rsp+0A8h+var_78], rcx; __int64
0x180021f40  mov     rcx, [r10+10h]; LoggerHandle
0x180021f44  mov     [rsp+0A8h+var_80], rax; __int64
0x180021f49  mov     eax, [r9+24h]
0x180021f4d  mov     r9d, [r9+10h]
0x180021f51  mov     dword ptr [rsp+0A8h+var_88], eax; char
0x180021f55  call    WPP_SF_DDZsIIIII
0x180021f5a  mov     r10, cs:WPP_GLOBAL_Control
0x180021f61  cmp     r10, rdi
0x180021f64  jz      short loc_180021FCB
0x180021f66  test    [r10+1Ch], r13b
0x180021f6a  jz      short loc_180021FCB
0x180021f6c  cmp     byte ptr [r10+19h], 4
0x180021f71  lea     rax, aCompleted; "Completed"
0x180021f78  jb      short loc_180021FD2
0x180021f7a  mov     r8, [rbx]
0x180021f7d  test    bpl, bpl
0x180021f80  mov     rcx, r14
0x180021f83  mov     edx, 0BFh
0x180021f88  cmovz   rcx, rax
0x180021f8c  mov     rax, [rsi+10h]
0x180021f90  mov     qword ptr [rsp+0A8h+var_68], rax; char
0x180021f95  mov     rax, [rsi+8]
0x180021f99  mov     r9, [r8]
0x180021f9c  mov     qword ptr [rsp+0A8h+var_70], rax; char
0x180021fa1  mov     rax, [r8+40h]
0x180021fa5  mov     qword ptr [rsp+0A8h+var_78], rcx; __int64
0x180021faa  mov     rcx, [r10+10h]; LoggerHandle
0x180021fae  mov     [rsp+0A8h+var_80], rax; __int64
0x180021fb3  mov     eax, [r9+24h]
0x180021fb7  mov     r9d, [r9+10h]
0x180021fbb  mov     dword ptr [rsp+0A8h+var_88], eax; char
0x180021fbf  call    WPP_SF_DDZsii
0x180021fc4  mov     r10, cs:WPP_GLOBAL_Control
0x180021fcb  lea     rax, aCompleted; "Completed"
0x180021fd2  test    dword ptr [rbx+4ECh], 20000000h
0x180021fdc  jz      loc_1800220B7
0x180021fe2  cmp     r10, rdi
0x180021fe5  jz      loc_1800221D3
0x180021feb  test    [r10+1Ch], r13b
0x180021fef  jz      short loc_180022049
0x180021ff1  cmp     byte ptr [r10+19h], 4
0x180021ff6  jb      short loc_180022049
0x180021ff8  mov     r8, [rbx]
0x180021ffb  test    bpl, bpl
0x180021ffe  mov     rcx, r14
0x180022001  mov     edx, 0C0h
0x180022006  cmovz   rcx, rax
0x18002200a  mov     rax, [rsi+48h]
0x18002200e  mov     qword ptr [rsp+0A8h+var_68], rax; char
0x180022013  mov     rax, [rsi+40h]
0x180022017  mov     r9, [r8]
0x18002201a  mov     qword ptr [rsp+0A8h+var_70], rax; char
0x18002201f  mov     rax, [r8+40h]
0x180022023  mov     qword ptr [rsp+0A8h+var_78], rcx; __int64
0x180022028  mov     rcx, [r10+10h]; LoggerHandle
0x18002202c  mov     [rsp+0A8h+var_80], rax; __int64
0x180022031  mov     eax, [r9+24h]
0x180022035  mov     r9d, [r9+10h]
0x180022039  mov     dword ptr [rsp+0A8h+var_88], eax; char
0x18002203d  call    WPP_SF_DDZsii
0x180022042  mov     r10, cs:WPP_GLOBAL_Control
0x180022049  cmp     r10, rdi
0x18002204c  jz      loc_1800221D3
0x180022052  test    [r10+1Ch], r13b
0x180022056  jz      short loc_1800220B7
0x180022058  cmp     byte ptr [r10+19h], 4
0x18002205d  jb      short loc_1800220B7
0x18002205f  mov     r8, [rbx]
0x180022062  lea     rax, aCompleted; "Completed"
0x180022069  test    bpl, bpl
0x18002206c  mov     rcx, r14
0x18002206f  mov     edx, 0C1h
0x180022074  cmovz   rcx, rax
0x180022078  mov     rax, [rsi+58h]
0x18002207c  mov     r9, [r8]
0x18002207f  mov     qword ptr [rsp+0A8h+var_68], rax; char
0x180022084  mov     rax, [rsi+50h]
0x180022088  mov     qword ptr [rsp+0A8h+var_70], rax; char
0x18002208d  mov     rax, [r8+40h]
0x180022091  mov     qword ptr [rsp+0A8h+var_78], rcx; __int64
0x180022096  mov     rcx, [r10+10h]; LoggerHandle
0x18002209a  mov     [rsp+0A8h+var_80], rax; __int64
0x18002209f  mov     eax, [r9+24h]
0x1800220a3  mov     r9d, [r9+10h]
0x1800220a7  mov     dword ptr [rsp+0A8h+var_88], eax; char
0x1800220ab  call    WPP_SF_DDZsii
0x1800220b0  mov     r10, cs:WPP_GLOBAL_Control
0x1800220b7  cmp     r10, rdi
0x1800220ba  jz      loc_1800221D3
0x1800220c0  test    [r10+1Ch], r13b
0x1800220c4  jz      short loc_18002211F
0x1800220c6  cmp     byte ptr [r10+19h], 4
0x1800220cb  jb      short loc_18002211F
0x1800220cd  mov     ecx, [rbx+55Ch]
0x1800220d3  lea     r8, aCompleted; "Completed"
0x1800220da  mov     rdx, [rbx]
0x1800220dd  test    bpl, bpl
0x1800220e0  mov     dword ptr [rsp+0A8h+var_70], ecx; char
0x1800220e4  mov     rax, r14
0x1800220e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220ee  cmovz   rax, r8
0x1800220f2  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x1800220f7  mov     r9, [rdx]
0x1800220fa  mov     rax, [rdx+40h]
0x1800220fe  mov     rcx, [rcx+10h]; LoggerHandle
0x180022102  mov     [rsp+0A8h+var_80], rax; __int64
0x180022107  mov     eax, [r9+24h]
0x18002210b  mov     r9d, [r9+10h]
0x18002210f  mov     dword ptr [rsp+0A8h+var_88], eax; char
0x180022113  call    WPP_SF_DDZsd
0x180022118  mov     r10, cs:WPP_GLOBAL_Control
0x18002211f  cmp     r10, rdi
0x180022122  jz      loc_1800221D3
0x180022128  test    [r10+1Ch], r13b
0x18002212c  jz      short loc_180022182
0x18002212e  cmp     byte ptr [r10+19h], 4
0x180022133  jb      short loc_180022182
0x180022135  imul    rcx, [rsi], 2710h
0x18002213c  mov     rdx, [rbx]
0x18002213f  lea     r8, aCompleted; "Completed"
0x180022146  mov     qword ptr [rsp+0A8h+var_70], rcx; char
0x18002214b  test    bpl, bpl
0x18002214e  mov     rcx, [r10+10h]; LoggerHandle
0x180022152  mov     rax, r14
0x180022155  cmovz   rax, r8
0x180022159  mov     r9, [rdx]
0x18002215c  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x180022161  mov     rax, [rdx+40h]
0x180022165  mov     [rsp+0A8h+var_80], rax; __int64
0x18002216a  mov     eax, [r9+24h]
0x18002216e  mov     r9d, [r9+10h]
0x180022172  mov     dword ptr [rsp+0A8h+var_88], eax; char
0x180022176  call    WPP_SF_DDZsi
0x18002217b  mov     r10, cs:WPP_GLOBAL_Control
0x180022182  cmp     r10, rdi
0x180022185  jz      short loc_1800221D3
0x180022187  test    [r10+1Ch], r13b
0x18002218b  jz      short loc_1800221D3
0x18002218d  cmp     byte ptr [r10+19h], 4
0x180022192  jb      short loc_1800221D3
0x180022194  mov     rcx, [rbx]
0x180022197  lea     rax, aCompleted; "Completed"
0x18002219e  test    bpl, bpl
0x1800221a1  cmovz   r14, rax
0x1800221a5  mov     rax, [rsi]
0x1800221a8  mov     r9, [rcx]
0x1800221ab  mov     qword ptr [rsp+0A8h+var_70], rax; char
0x1800221b0  mov     rax, [rcx+40h]
0x1800221b4  mov     rcx, [r10+10h]; LoggerHandle
0x1800221b8  mov     qword ptr [rsp+0A8h+var_78], r14; __int64
0x1800221bd  mov     [rsp+0A8h+var_80], rax; __int64
0x1800221c2  mov     eax, [r9+24h]
0x1800221c6  mov     r9d, [r9+10h]
0x1800221ca  mov     dword ptr [rsp+0A8h+var_88], eax; char
0x1800221ce  call    WPP_SF_DDZsI
0x1800221d3  lea     rcx, [rbx+5E0h]; SRWLock
0x1800221da  mov     [rsp+0A8h+arg_0], rcx
0x1800221e2  call    cs:__imp_AcquireSRWLockExclusive
0x1800221e8  xor     edi, edi
0x1800221ea  cmp     [rbx+5E8h], edi
0x1800221f0  jbe     short loc_180022217
0x1800221f2  mov     rdx, [rbx]; struct _SCRUB_VOLUME_IDENTIFIER *
0x1800221f5  mov     eax, edi
0x1800221f7  add     rax, 26h ; '&'
0x1800221fb  lea     rcx, [rax+rax*4]
0x1800221ff  lea     r8, [rbx+rcx*8]; struct _SCRUB_ERROR_RECORD *
0x180022203  mov     rcx, [rbx+8]; struct _SCRUB_ENVIRONMENT *
0x180022207  call    ?EventWriteScrubError@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_SCRUB_VOLUME_IDENTIFIER@@PEBU_SCRUB_ERROR_RECORD@@@Z; EventWriteScrubError(_SCRUB_ENVIRONMENT *,_SCRUB_VOLUME_IDENTIFIER const *,_SCRUB_ERROR_RECORD const *)
0x18002220c  add     edi, r13d
0x18002220f  cmp     edi, [rbx+5E8h]
0x180022215  jb      short loc_1800221F2
0x180022217  lea     rcx, [rsp+0A8h+arg_0]; this
0x18002221f  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180022224  mov     eax, [rbx+558h]
0x18002222a  mov     r8b, bpl; unsigned __int8
0x18002222d  mov     r9b, [rbx+5D9h]; unsigned __int8
0x180022234  mov     rdx, [rbx]; struct _SCRUB_VOLUME_IDENTIFIER *
0x180022237  mov     rcx, [rbx+8]; struct _SCRUB_ENVIRONMENT *
0x18002223b  mov     word ptr [rsp+0A8h+var_70], r15w; char
0x180022241  mov     [rsp+0A8h+var_78], eax; unsigned int
0x180022245  mov     [rsp+0A8h+var_80], rsi; struct _SCRUB_CHECKPOINT_STATS *
0x18002224a  mov     dword ptr [rsp+0A8h+var_88], r12d; int
0x18002224f  call    ?EventWriteVolumeScanComplete@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_SCRUB_VOLUME_IDENTIFIER@@EEJPEBU_SCRUB_CHECKPOINT_STATS@@KG@Z; EventWriteVolumeScanComplete(_SCRUB_ENVIRONMENT *,_SCRUB_VOLUME_IDENTIFIER const *,uchar,uchar,long,_SCRUB_CHECKPOINT_STATS const *,ulong,ushort)
0x180022254  add     rsp, 68h
0x180022258  pop     r15
0x18002225a  pop     r14
0x18002225c  pop     r13
0x18002225e  pop     r12
0x180022260  pop     rdi
0x180022261  pop     rsi
0x180022262  pop     rbp
0x180022263  pop     rbx
0x180022264  retn
```
