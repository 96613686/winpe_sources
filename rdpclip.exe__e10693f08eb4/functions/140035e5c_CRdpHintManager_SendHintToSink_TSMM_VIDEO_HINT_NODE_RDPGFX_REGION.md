# CRdpHintManager::SendHintToSink(TSMM_VIDEO_HINT_NODE *,_RDPGFX_REGION *)

- ea: `0x140035e5c`
- end: `0x140036252`
- name: `?SendHintToSink@CRdpHintManager@@AEAAJPEAUTSMM_VIDEO_HINT_NODE@@PEAU_RDPGFX_REGION@@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(CRdpHintManager *__hidden this, struct TSMM_VIDEO_HINT_NODE *, struct _RDPGFX_REGION *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400366c4`
- `0x1400369a0`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x140011054`
- `0x1400331d0`
- `0x140035e5c`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `USER32!CopyRect` at `0x140035f5e`
- `USER32!CopyRect` at `0x140035f82`
- `USER32!CopyRect` at `0x140035f5e`
- `USER32!CopyRect` at `0x140035f82`
- `USER32!OffsetRect` at `0x140035f72`
- `USER32!OffsetRect` at `0x140035f99`
- `USER32!OffsetRect` at `0x1400360b9`
- `USER32!OffsetRect` at `0x1400360db`
- `USER32!OffsetRect` at `0x140035f72`
- `USER32!OffsetRect` at `0x140035f99`
- `USER32!OffsetRect` at `0x1400360b9`
- `USER32!OffsetRect` at `0x1400360db`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::SendHintToSink(
        CRdpHintManager *this,
        struct TSMM_VIDEO_HINT_NODE *a2,
        struct _RDPGFX_REGION *a3)
{
  unsigned int v6; // eax
  int v7; // ebx
  int v8; // esi
  int v9; // edi
  int v10; // r15d
  int v11; // r14d
  __int64 v12; // rax
  unsigned int *v13; // rcx
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int64 v21; // rax
  unsigned int v22; // eax
  CRdpHintManager *v23; // rcx
  CRdpHintManager *v24; // rcx
  unsigned int i; // ebx
  CRdpHintManager *v26; // rcx
  int v27; // r8d
  __int64 v28; // r9
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v30; // eax
  __int64 v32; // [rsp+28h] [rbp-D8h]
  int v33; // [rsp+50h] [rbp-B0h]
  int v34; // [rsp+54h] [rbp-ACh]
  struct tagRECT rcDst; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECT rc; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v38; // [rsp+80h] [rbp-80h] BYREF
  struct tagRECT v39; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v40[64]; // [rsp+98h] [rbp-68h] BYREF

  rc = 0;
  rcDst = 0;
  memset_0(&v38, 0, 0x418u);
  if ( a2 )
  {
    if ( *((_QWORD *)this + 10) )
    {
      if ( !a3 )
        a3 = (struct TSMM_VIDEO_HINT_NODE *)((char *)a2 + 112);
      v8 = *((_DWORD *)this + 702);
      v9 = *((_DWORD *)this + 703);
      v10 = *((_DWORD *)a2 + 24);
      v11 = *((_DWORD *)a2 + 25);
      v34 = *((_DWORD *)a2 + 20);
      v33 = *((_DWORD *)a2 + 21);
      CopyRect(&rcDst, (const RECT *)a2 + 6);
      OffsetRect(&rcDst, -v8, -v9);
      CopyRect(&rc, (const RECT *)a2 + 5);
      OffsetRect(&rc, -v10, -v11);
      v12 = 8;
      v13 = &v38;
      do
      {
        v14 = *((_OWORD *)a3 + 1);
        *(_OWORD *)v13 = *(_OWORD *)a3;
        v15 = *((_OWORD *)a3 + 2);
        *((_OWORD *)v13 + 1) = v14;
        v16 = *((_OWORD *)a3 + 3);
        *((_OWORD *)v13 + 2) = v15;
        v17 = *((_OWORD *)a3 + 4);
        *((_OWORD *)v13 + 3) = v16;
        v18 = *((_OWORD *)a3 + 5);
        *((_OWORD *)v13 + 4) = v17;
        v19 = *((_OWORD *)a3 + 6);
        *((_OWORD *)v13 + 5) = v18;
        v20 = *((_OWORD *)a3 + 7);
        a3 = (struct _RDPGFX_REGION *)((char *)a3 + 128);
        *((_OWORD *)v13 + 6) = v19;
        *((_OWORD *)v13 + 7) = v20;
        v13 += 32;
        --v12;
      }
      while ( v12 );
      v21 = *((_QWORD *)a3 + 2);
      *(_OWORD *)v13 = *(_OWORD *)a3;
      *((_QWORD *)v13 + 2) = v21;
      if ( v38 <= 0x40 )
      {
        if ( *((_DWORD *)a2 + 6) == 1 )
        {
          CRdpHintManager::AdjustRectByScalingFactor((CRdpHintManager *)v13, &rc, *((_DWORD *)a2 + 14));
          CRdpHintManager::AdjustRectByScalingFactor(v23, &rcDst, *((_DWORD *)a2 + 14));
          CRdpHintManager::AdjustRectByScalingFactor(v24, &v39, *((_DWORD *)a2 + 14));
        }
        OffsetRect(&v39, -v34, -v33);
        for ( i = 0; i < v38; ++i )
        {
          OffsetRect((LPRECT)&v40[i], -v34, -v33);
          if ( *((_DWORD *)a2 + 6) == 1 )
            CRdpHintManager::AdjustRectByScalingFactor(v26, (struct tagRECT *)&v40[i], *((_DWORD *)a2 + 14));
        }
        v27 = *((_DWORD *)a2 + 293) | *((_DWORD *)a2 + 294);
        v28 = *((_QWORD *)a2 + 9);
        *((_DWORD *)a2 + 293) = *((_DWORD *)a2 + 294);
        v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, int, struct tagRECT *, struct tagRECT *, unsigned int *))(**((_QWORD **)this + 10) + 40LL))(
               *((_QWORD *)this + 10),
               *((_QWORD *)a2 + 2),
               *((unsigned int *)a2 + 6),
               v28,
               *((_DWORD *)a2 + 292),
               v27,
               &rc,
               &rcDst,
               &v38);
        if ( v7 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v32) = v7;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            88,
            (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"m_spHintApiEventSink->SetRenderHint() failed",
            v32);
        }
      }
      else
      {
        v7 = -2147418113;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids, v22);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
          v30,
          -2147418113);
      }
      return (unsigned int)-2147418113;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        v6,
        (__int64)"pNode");
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140035e5c  mov     [rsp-8+arg_18], rbx
0x140035e61  push    rbp
0x140035e62  push    rsi
0x140035e63  push    rdi
0x140035e64  push    r12
0x140035e66  push    r13
0x140035e68  push    r14
0x140035e6a  push    r15
0x140035e6c  lea     rbp, [rsp-3B0h]
0x140035e74  sub     rsp, 4B0h
0x140035e7b  mov     rax, cs:__security_cookie
0x140035e82  xor     rax, rsp
0x140035e85  mov     [rbp+3E0h+var_40], rax
0x140035e8c  mov     r13, r8
0x140035e8f  mov     [rsp+4E0h+var_488], rcx
0x140035e94  mov     r12, rdx
0x140035e97  mov     rbx, rcx
0x140035e9a  xorps   xmm0, xmm0
0x140035e9d  lea     rcx, [rbp+3E0h+var_460]; void *
0x140035ea1  xorps   xmm1, xmm1
0x140035ea4  xor     edx, edx; Val
0x140035ea6  mov     r8d, 418h; Size
0x140035eac  movups  xmmword ptr [rsp+4E0h+rc.left], xmm0
0x140035eb1  movups  xmmword ptr [rsp+4E0h+rcDst.left], xmm1
0x140035eb6  call    memset_0
0x140035ebb  test    r12, r12
0x140035ebe  jnz     short loc_140035F19
0x140035ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x140035ec7  lea     rax, WPP_GLOBAL_Control
0x140035ece  cmp     rcx, rax
0x140035ed1  jz      short loc_140035F0F
0x140035ed3  test    byte ptr [rcx+1Ch], 8
0x140035ed7  jz      short loc_140035F0F
0x140035ed9  cmp     byte ptr [rcx+19h], 2
0x140035edd  jb      short loc_140035F0F
0x140035edf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035ee4  lea     rcx, aPnode; "pNode"
0x140035eeb  mov     r9d, eax
0x140035eee  mov     [rsp+4E0h+var_4C0], rcx
0x140035ef3  lea     edx, [r12+55h]
0x140035ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x140035eff  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140035f06  mov     rcx, [rcx+10h]
0x140035f0a  call    WPP_SF_Ds
0x140035f0f  mov     ebx, 80004003h
0x140035f14  jmp     loc_140036226
0x140035f19  cmp     qword ptr [rbx+50h], 0
0x140035f1e  jz      loc_1400361D6
0x140035f24  test    r13, r13
0x140035f27  jnz     short loc_140035F2E
0x140035f29  lea     r13, [r12+70h]
0x140035f2e  mov     eax, [r12+50h]
0x140035f33  lea     rdx, [r12+60h]; lprcSrc
0x140035f38  mov     esi, [rbx+0AF8h]
0x140035f3e  lea     rcx, [rsp+4E0h+rcDst]; lprcDst
0x140035f43  mov     edi, [rbx+0AFCh]
0x140035f49  mov     r15d, [rdx]
0x140035f4c  mov     r14d, [r12+64h]
0x140035f51  mov     [rsp+4E0h+var_48C], eax
0x140035f55  mov     eax, [r12+54h]
0x140035f5a  mov     [rsp+4E0h+var_490], eax
0x140035f5e  call    cs:__imp_CopyRect
0x140035f64  neg     edi
0x140035f66  lea     rcx, [rsp+4E0h+rcDst]; lprc
0x140035f6b  neg     esi
0x140035f6d  mov     r8d, edi; dy
0x140035f70  mov     edx, esi; dx
0x140035f72  call    cs:__imp_OffsetRect
0x140035f78  lea     rdx, [r12+50h]; lprcSrc
0x140035f7d  lea     rcx, [rsp+4E0h+rc]; lprcDst
0x140035f82  call    cs:__imp_CopyRect
0x140035f88  neg     r14d
0x140035f8b  lea     rcx, [rsp+4E0h+rc]; lprc
0x140035f90  neg     r15d
0x140035f93  mov     r8d, r14d; dy
0x140035f96  mov     edx, r15d; dx
0x140035f99  call    cs:__imp_OffsetRect
0x140035f9f  mov     eax, 8
0x140035fa4  lea     rcx, [rbp+3E0h+var_460]
0x140035fa8  lea     edx, [rax+78h]
0x140035fab  movups  xmm0, xmmword ptr [r13+0]
0x140035fb0  movups  xmm1, xmmword ptr [r13+10h]
0x140035fb5  movups  xmmword ptr [rcx], xmm0
0x140035fb8  movups  xmm0, xmmword ptr [r13+20h]
0x140035fbd  movups  xmmword ptr [rcx+10h], xmm1
0x140035fc1  movups  xmm1, xmmword ptr [r13+30h]
0x140035fc6  movups  xmmword ptr [rcx+20h], xmm0
0x140035fca  movups  xmm0, xmmword ptr [r13+40h]
0x140035fcf  movups  xmmword ptr [rcx+30h], xmm1
0x140035fd3  movups  xmm1, xmmword ptr [r13+50h]
0x140035fd8  movups  xmmword ptr [rcx+40h], xmm0
0x140035fdc  movups  xmm0, xmmword ptr [r13+60h]
0x140035fe1  movups  xmmword ptr [rcx+50h], xmm1
0x140035fe5  movups  xmm1, xmmword ptr [r13+70h]
0x140035fea  add     r13, rdx
0x140035fed  movups  xmmword ptr [rcx+60h], xmm0
0x140035ff1  movups  xmmword ptr [rcx+70h], xmm1
0x140035ff5  add     rcx, rdx; this
0x140035ff8  sub     rax, 1
0x140035ffc  jnz     short loc_140035FAB
0x140035ffe  movups  xmm0, xmmword ptr [r13+0]
0x140036003  mov     rax, [r13+10h]
0x140036007  movups  xmmword ptr [rcx], xmm0
0x14003600a  mov     [rcx+10h], rax
0x14003600e  cmp     [rbp+3E0h+var_460], 40h ; '@'
0x140036012  jbe     short loc_140036070
0x140036014  mov     ebx, 8000FFFFh
0x140036019  mov     rcx, cs:WPP_GLOBAL_Control
0x140036020  lea     rax, WPP_GLOBAL_Control
0x140036027  cmp     rcx, rax
0x14003602a  jz      loc_140036226
0x140036030  test    dword ptr [rcx+1Ch], 200h
0x140036037  jz      loc_140036226
0x14003603d  cmp     byte ptr [rcx+19h], 2
0x140036041  jb      loc_140036226
0x140036047  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003604c  mov     rcx, cs:WPP_GLOBAL_Control
0x140036053  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x14003605a  mov     edx, 57h ; 'W'
0x14003605f  mov     r9d, eax
0x140036062  mov     rcx, [rcx+10h]
0x140036066  call    WPP_SF_d
0x14003606b  jmp     loc_140036226
0x140036070  cmp     dword ptr [r12+18h], 1
0x140036076  jnz     short loc_1400360A4
0x140036078  mov     r8d, [r12+38h]; unsigned int
0x14003607d  lea     rdx, [rsp+4E0h+rc]; struct tagRECT *
0x140036082  call    ?AdjustRectByScalingFactor@CRdpHintManager@@AEAAXPEAUtagRECT@@K@Z; CRdpHintManager::AdjustRectByScalingFactor(tagRECT *,ulong)
0x140036087  mov     r8d, [r12+38h]; unsigned int
0x14003608c  lea     rdx, [rsp+4E0h+rcDst]; struct tagRECT *
0x140036091  call    ?AdjustRectByScalingFactor@CRdpHintManager@@AEAAXPEAUtagRECT@@K@Z; CRdpHintManager::AdjustRectByScalingFactor(tagRECT *,ulong)
0x140036096  mov     r8d, [r12+38h]; unsigned int
0x14003609b  lea     rdx, [rbp+3E0h+var_458]; struct tagRECT *
0x14003609f  call    ?AdjustRectByScalingFactor@CRdpHintManager@@AEAAXPEAUtagRECT@@K@Z; CRdpHintManager::AdjustRectByScalingFactor(tagRECT *,ulong)
0x1400360a4  mov     edi, [rsp+4E0h+var_490]
0x1400360a8  lea     rcx, [rbp+3E0h+var_458]; lprc
0x1400360ac  mov     esi, [rsp+4E0h+var_48C]
0x1400360b0  neg     edi
0x1400360b2  neg     esi
0x1400360b4  mov     r8d, edi; dy
0x1400360b7  mov     edx, esi; dx
0x1400360b9  call    cs:__imp_OffsetRect
0x1400360bf  xor     ebx, ebx
0x1400360c1  cmp     [rbp+3E0h+var_460], ebx
0x1400360c4  jbe     short loc_1400360FD
0x1400360c6  mov     eax, ebx
0x1400360c8  lea     r14, [rbp+3E0h+var_448]
0x1400360cc  shl     rax, 4
0x1400360d0  mov     r8d, edi; dy
0x1400360d3  add     r14, rax
0x1400360d6  mov     edx, esi; dx
0x1400360d8  mov     rcx, r14; lprc
0x1400360db  call    cs:__imp_OffsetRect
0x1400360e1  cmp     dword ptr [r12+18h], 1
0x1400360e7  jnz     short loc_1400360F6
0x1400360e9  mov     r8d, [r12+38h]; unsigned int
0x1400360ee  mov     rdx, r14; struct tagRECT *
0x1400360f1  call    ?AdjustRectByScalingFactor@CRdpHintManager@@AEAAXPEAUtagRECT@@K@Z; CRdpHintManager::AdjustRectByScalingFactor(tagRECT *,ulong)
0x1400360f6  inc     ebx
0x1400360f8  cmp     ebx, [rbp+3E0h+var_460]
0x1400360fb  jb      short loc_1400360C6
0x1400360fd  mov     eax, [r12+498h]
0x140036105  lea     rdx, [rbp+3E0h+var_460]
0x140036109  mov     rcx, [rsp+4E0h+var_488]
0x14003610e  mov     r8d, eax
0x140036111  or      r8d, [r12+494h]
0x140036119  mov     r9, [r12+48h]
0x14003611e  mov     [rsp+4E0h+var_4A0], rdx
0x140036123  lea     rdx, [rsp+4E0h+rcDst]
0x140036128  mov     [rsp+4E0h+var_4A8], rdx
0x14003612d  lea     rdx, [rsp+4E0h+rc]
0x140036132  mov     [r12+494h], eax
0x14003613a  mov     rcx, [rcx+50h]
0x14003613e  mov     [rsp+4E0h+var_4B0], rdx
0x140036143  mov     rdx, [r12+10h]
0x140036148  mov     dword ptr [rsp+4E0h+var_4B8], r8d
0x14003614d  mov     r8d, [r12+490h]
0x140036155  mov     rax, [rcx]
0x140036158  mov     dword ptr [rsp+4E0h+var_4C0], r8d
0x14003615d  mov     r8d, [r12+18h]
0x140036162  mov     rax, [rax+28h]
0x140036166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003616b  mov     ebx, eax
0x14003616d  test    eax, eax
0x14003616f  jns     loc_140036226
0x140036175  mov     rcx, cs:WPP_GLOBAL_Control
0x14003617c  lea     rax, WPP_GLOBAL_Control
0x140036183  cmp     rcx, rax
0x140036186  jz      loc_140036226
0x14003618c  test    byte ptr [rcx+1Ch], 8
0x140036190  jz      loc_140036226
0x140036196  cmp     byte ptr [rcx+19h], 2
0x14003619a  jb      loc_140036226
0x1400361a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400361a5  lea     rcx, aMSphintapieven; "m_spHintApiEventSink->SetRenderHint() f"...
0x1400361ac  mov     dword ptr [rsp+4E0h+var_4B8], ebx
0x1400361b0  mov     [rsp+4E0h+var_4C0], rcx
0x1400361b5  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400361bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400361c3  mov     edx, 58h ; 'X'
0x1400361c8  mov     r9d, eax
0x1400361cb  mov     rcx, [rcx+10h]
0x1400361cf  call    WPP_SF_DsD
0x1400361d4  jmp     short loc_140036226
0x1400361d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400361dd  lea     rax, WPP_GLOBAL_Control
0x1400361e4  cmp     rcx, rax
0x1400361e7  jz      short loc_140036221
0x1400361e9  test    byte ptr [rcx+1Ch], 8
0x1400361ed  jz      short loc_140036221
0x1400361ef  cmp     byte ptr [rcx+19h], 2
0x1400361f3  jb      short loc_140036221
0x1400361f5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400361fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140036201  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140036208  mov     edx, 56h ; 'V'
0x14003620d  mov     dword ptr [rsp+4E0h+var_4C0], 8000FFFFh
0x140036215  mov     r9d, eax
0x140036218  mov     rcx, [rcx+10h]
0x14003621c  call    WPP_SF_Dd
0x140036221  mov     ebx, 8000FFFFh
0x140036226  mov     eax, ebx
0x140036228  mov     rcx, [rbp+3E0h+var_40]
0x14003622f  xor     rcx, rsp; StackCookie
0x140036232  call    __security_check_cookie
0x140036237  mov     rbx, [rsp+4E0h+arg_18]
0x14003623f  add     rsp, 4B0h
0x140036246  pop     r15
0x140036248  pop     r14
0x14003624a  pop     r13
0x14003624c  pop     r12
0x14003624e  pop     rdi
0x14003624f  pop     rsi
0x140036250  pop     rbp
0x140036251  retn
```
