# CRdpHintManager::ProcessRenderHint(unsigned __int64,ulong,ulong,HWND__ *,tagRECT *)

- ea: `0x140035a70`
- end: `0x140035dd1`
- name: `?ProcessRenderHint@CRdpHintManager@@EEAAJ_KKKPEAUHWND__@@PEAUtagRECT@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(CRdpHintManager *__hidden this, unsigned __int64, unsigned int, unsigned int, HWND, RECT *lprcSrc)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x140036260`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x14000d350`
- `0x14000efb8`
- `0x1400303f4`
- `0x140032ee0`
- `0x1400333cc`
- `0x1400339a0`
- `0x140035a70`
- `0x1400366a0`
- `0x1400370a0`
- `0x140037170`
- `0x14006b010`

## import_xrefs

- `USER32!CopyRect` at `0x140035d87`
- `USER32!CopyRect` at `0x140035d87`

## string_xrefs

- `0x140035ca8`: `CreateHintNode() failed`
- `0x140035d63`: `Received update for non-existing hint id`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::ProcessRenderHint(
        CRdpHintManager *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned int a4,
        HWND a5,
        RECT *lprcSrc)
{
  RECT *v6; // rbx
  unsigned int v7; // r12d
  unsigned __int64 v9; // r13
  HWND v11; // rbp
  LONG right; // r13d
  int v13; // r12d
  int v14; // r13d
  const wchar_t *v15; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r9d
  const wchar_t *v21; // rdi
  unsigned int v22; // eax
  int v23; // edx
  int v24; // r8d
  int HintNode; // edi
  unsigned int v26; // eax
  int v27; // edx
  const char *v28; // rcx
  unsigned int v29; // eax
  struct TSMM_VIDEO_HINT_NODE *v30; // rsi
  unsigned int v32; // [rsp+20h] [rbp-88h]
  __int64 v33; // [rsp+28h] [rbp-80h]
  char v34; // [rsp+50h] [rbp-58h]
  char v35; // [rsp+58h] [rbp-50h]
  struct TSMM_VIDEO_HINT_NODE *v36; // [rsp+60h] [rbp-48h] BYREF
  LONG left; // [rsp+B0h] [rbp+8h]

  v6 = lprcSrc;
  v7 = a4;
  v36 = 0;
  v9 = a2;
  if ( lprcSrc )
  {
    v11 = a5;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      right = lprcSrc->right;
      v13 = lprcSrc->bottom - lprcSrc->top;
      LODWORD(lprcSrc) = lprcSrc->top;
      v14 = right - v6->left;
      left = v6->left;
      if ( a3 == 1 )
      {
        v15 = (const wchar_t *)L"RENDER_HINT_VIDEO";
      }
      else
      {
        v15 = L"RENDER_HINT_MAPPEDWINDOW";
        if ( a3 != 2 )
          v15 = L"[UNKNOWN]";
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v35 = v13;
      v7 = a4;
      v34 = v14;
      v9 = a2;
      WPP_SF_DSdqidddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v18,
        CurrentThreadActivityIdPrefix,
        (__int64)v15,
        a4,
        (char)a5,
        a2,
        left,
        (char)lprcSrc,
        v34,
        v35);
    }
    v19 = v6->right - v6->left;
    v20 = v6->bottom - v6->top;
  }
  else
  {
    v11 = a5;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      if ( a3 == 1 )
      {
        v21 = (const wchar_t *)L"RENDER_HINT_VIDEO";
      }
      else
      {
        v21 = L"RENDER_HINT_MAPPEDWINDOW";
        if ( a3 != 2 )
          v21 = L"[UNKNOWN]";
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSdqi(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v24, v22, (__int64)v21, v7, (char)a5, v9);
    }
    v19 = 0;
    v20 = 0;
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsVOBRHintExternal((RDPGraphicsTraceLogging *)a3, v7, v19, v20, v32);
  lprcSrc = (RECT *)((char *)this + 56);
  CTSCriticalSection::Lock((CRdpHintManager *)((char *)this + 56));
  if ( (unsigned int)CRdpHintManager::GetHintNodeWithHintId(this, v9, &v36) )
  {
    v30 = v36;
    HintNode = 0;
    if ( *((_DWORD *)v36 + 15) && v6 )
      CopyRect((LPRECT)((char *)v36 + 40), v6);
    *((_DWORD *)v30 + 291) = 1;
    CRdpHintManager::AdjustGeometryForWindow(this, v11);
    CRdpHintManager::UpdateHints(this);
  }
  else if ( v7 == 1 )
  {
    HintNode = CRdpHintManager::CreateHintNode(this, v9, a3, v11, v6);
    if ( HintNode >= 0 )
    {
      HintNode = (*(__int64 (__fastcall **)(_QWORD, HWND, __int64))(**((_QWORD **)this + 9) + 24LL))(
                   *((_QWORD *)this + 9),
                   v11,
                   1);
      if ( HintNode < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        v27 = 60;
        v28 = "m_spWindowTracker->TrackWindow() failed";
        goto LABEL_27;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      v27 = 59;
      v28 = "CreateHintNode() failed";
LABEL_27:
      LODWORD(v33) = HintNode;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        v26,
        (__int64)v28,
        v33);
    }
  }
  else
  {
    HintNode = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v33) = -2147024809;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        v29,
        (__int64)"Received update for non-existing hint id",
        v33);
    }
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&lprcSrc);
  return (unsigned int)HintNode;
}

```

## disassembly

```asm
0x140035a70  mov     rax, rsp
0x140035a73  mov     [rax+18h], rbx
0x140035a77  mov     [rax+20h], r9d
0x140035a7b  mov     [rax+10h], rdx
0x140035a7f  push    rbp
0x140035a80  push    rsi
0x140035a81  push    rdi
0x140035a82  push    r12
0x140035a84  push    r13
0x140035a86  push    r14
0x140035a88  push    r15
0x140035a8a  sub     rsp, 70h
0x140035a8e  mov     rbx, [rsp+0A8h+lprcSrc]
0x140035a96  mov     r12d, r9d
0x140035a99  mov     qword ptr [rax-48h], 0
0x140035aa1  mov     r14d, r8d
0x140035aa4  mov     r13, rdx
0x140035aa7  mov     r15, rcx
0x140035aaa  test    rbx, rbx
0x140035aad  jz      loc_140035B9F
0x140035ab3  mov     rax, cs:WPP_GLOBAL_Control
0x140035aba  lea     rsi, WPP_GLOBAL_Control
0x140035ac1  mov     rbp, [rsp+0A8h+arg_20]
0x140035ac9  cmp     rax, rsi
0x140035acc  jz      loc_140035B8B
0x140035ad2  test    dword ptr [rax+1Ch], 200h
0x140035ad9  jz      loc_140035B8B
0x140035adf  cmp     byte ptr [rax+19h], 5
0x140035ae3  jb      loc_140035B8B
0x140035ae9  mov     eax, [rbx+4]
0x140035aec  mov     r12d, [rbx+0Ch]
0x140035af0  mov     r13d, [rbx+8]
0x140035af4  sub     r12d, eax
0x140035af7  mov     dword ptr [rsp+0A8h+lprcSrc], eax
0x140035afe  mov     eax, [rbx]
0x140035b00  sub     r13d, eax
0x140035b03  mov     [rsp+0A8h+arg_0], eax
0x140035b0a  cmp     r8d, 1
0x140035b0e  jnz     short loc_140035B19
0x140035b10  lea     rdi, aRenderHintVide; "RENDER_HINT_VIDEO"
0x140035b17  jmp     short loc_140035B2F
0x140035b19  cmp     r14d, 2
0x140035b1d  lea     rdi, aRenderHintMapp; "RENDER_HINT_MAPPEDWINDOW"
0x140035b24  lea     rax, aUnknown_1; "[UNKNOWN]"
0x140035b2b  cmovnz  rdi, rax
0x140035b2f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035b34  mov     ecx, dword ptr [rsp+0A8h+lprcSrc]
0x140035b3b  mov     r9d, eax
0x140035b3e  mov     dword ptr [rsp+0A8h+var_50], r12d
0x140035b43  mov     r12d, [rsp+0A8h+arg_18]
0x140035b4b  mov     dword ptr [rsp+0A8h+var_58], r13d
0x140035b50  mov     r13, [rsp+0A8h+arg_8]
0x140035b58  mov     [rsp+0A8h+var_60], ecx
0x140035b5c  mov     ecx, [rsp+0A8h+arg_0]
0x140035b63  mov     [rsp+0A8h+var_68], ecx
0x140035b67  mov     rcx, cs:WPP_GLOBAL_Control
0x140035b6e  mov     [rsp+0A8h+var_70], r13
0x140035b73  mov     [rsp+0A8h+var_78], rbp
0x140035b78  mov     dword ptr [rsp+0A8h+var_80], r12d
0x140035b7d  mov     rcx, [rcx+10h]
0x140035b81  mov     [rsp+0A8h+var_88], rdi
0x140035b86  call    WPP_SF_DSdqidddd
0x140035b8b  mov     r8d, [rbx+8]
0x140035b8f  sub     r8d, [rbx]
0x140035b92  mov     r9d, [rbx+0Ch]
0x140035b96  sub     r9d, [rbx+4]
0x140035b9a  jmp     loc_140035C20
0x140035b9f  mov     rax, cs:WPP_GLOBAL_Control
0x140035ba6  lea     rsi, WPP_GLOBAL_Control
0x140035bad  mov     rbp, [rsp+0A8h+arg_20]
0x140035bb5  cmp     rax, rsi
0x140035bb8  jz      short loc_140035C1A
0x140035bba  test    dword ptr [rax+1Ch], 200h
0x140035bc1  jz      short loc_140035C1A
0x140035bc3  cmp     byte ptr [rax+19h], 5
0x140035bc7  jb      short loc_140035C1A
0x140035bc9  cmp     r14d, 1
0x140035bcd  jnz     short loc_140035BD8
0x140035bcf  lea     rdi, aRenderHintVide; "RENDER_HINT_VIDEO"
0x140035bd6  jmp     short loc_140035BEE
0x140035bd8  cmp     r14d, 2
0x140035bdc  lea     rdi, aRenderHintMapp; "RENDER_HINT_MAPPEDWINDOW"
0x140035be3  lea     rax, aUnknown_1; "[UNKNOWN]"
0x140035bea  cmovnz  rdi, rax
0x140035bee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x140035bfa  mov     r9d, eax
0x140035bfd  mov     [rsp+0A8h+var_70], r13
0x140035c02  mov     [rsp+0A8h+var_78], rbp
0x140035c07  mov     dword ptr [rsp+0A8h+var_80], r12d
0x140035c0c  mov     rcx, [rcx+10h]
0x140035c10  mov     [rsp+0A8h+var_88], rdi; unsigned int
0x140035c15  call    WPP_SF_DSdqi
0x140035c1a  xor     r8d, r8d; unsigned int
0x140035c1d  xor     r9d, r9d; unsigned int
0x140035c20  mov     edx, r12d; unsigned int
0x140035c23  mov     ecx, r14d; this
0x140035c26  call    ?LogRDPGraphicsVOBRHintExternal@RDPGraphicsTraceLogging@@YAXIIII@Z; RDPGraphicsTraceLogging::LogRDPGraphicsVOBRHintExternal(uint,uint,uint,uint)
0x140035c2b  lea     rcx, [r15+38h]; this
0x140035c2f  mov     [rsp+0A8h+lprcSrc], rcx
0x140035c37  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x140035c3c  lea     r8, [rsp+0A8h+var_48]; struct TSMM_VIDEO_HINT_NODE **
0x140035c41  mov     rdx, r13; unsigned __int64
0x140035c44  mov     rcx, r15; this
0x140035c47  call    ?GetHintNodeWithHintId@CRdpHintManager@@EEAAH_KPEAPEAUTSMM_VIDEO_HINT_NODE@@@Z; CRdpHintManager::GetHintNodeWithHintId(unsigned __int64,TSMM_VIDEO_HINT_NODE * *)
0x140035c4c  test    eax, eax
0x140035c4e  jnz     loc_140035D6F
0x140035c54  cmp     r12d, 1
0x140035c58  jnz     loc_140035D34
0x140035c5e  mov     r9, rbp; HWND
0x140035c61  mov     [rsp+0A8h+var_88], rbx; struct tagRECT *
0x140035c66  mov     r8d, r14d; unsigned int
0x140035c69  mov     rdx, r13; unsigned __int64
0x140035c6c  mov     rcx, r15; this
0x140035c6f  call    ?CreateHintNode@CRdpHintManager@@AEAAJ_KKPEAUHWND__@@PEAUtagRECT@@@Z; CRdpHintManager::CreateHintNode(unsigned __int64,ulong,HWND__ *,tagRECT *)
0x140035c74  mov     edi, eax
0x140035c76  test    eax, eax
0x140035c78  jns     short loc_140035CD7
0x140035c7a  mov     rax, cs:WPP_GLOBAL_Control
0x140035c81  cmp     rax, rsi
0x140035c84  jz      loc_140035DAA
0x140035c8a  test    byte ptr [rax+1Ch], 8
0x140035c8e  jz      loc_140035DAA
0x140035c94  cmp     byte ptr [rax+19h], 2
0x140035c98  jb      loc_140035DAA
0x140035c9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035ca3  lea     edx, [r12+3Ah]
0x140035ca8  lea     rcx, aCreatehintnode; "CreateHintNode() failed"
0x140035caf  mov     dword ptr [rsp+0A8h+var_80], edi
0x140035cb3  mov     [rsp+0A8h+var_88], rcx
0x140035cb8  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140035cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140035cc6  mov     r9d, eax
0x140035cc9  mov     rcx, [rcx+10h]
0x140035ccd  call    WPP_SF_DsD
0x140035cd2  jmp     loc_140035DAA
0x140035cd7  mov     rcx, [r15+48h]
0x140035cdb  mov     r8d, 1
0x140035ce1  mov     rdx, rbp
0x140035ce4  mov     rax, [rcx]
0x140035ce7  mov     rax, [rax+18h]
0x140035ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035cf0  mov     edi, eax
0x140035cf2  test    eax, eax
0x140035cf4  jns     loc_140035DAA
0x140035cfa  mov     rax, cs:WPP_GLOBAL_Control
0x140035d01  cmp     rax, rsi
0x140035d04  jz      loc_140035DAA
0x140035d0a  test    byte ptr [rax+1Ch], 8
0x140035d0e  jz      loc_140035DAA
0x140035d14  cmp     byte ptr [rax+19h], 2
0x140035d18  jb      loc_140035DAA
0x140035d1e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035d23  mov     edx, 3Ch ; '<'
0x140035d28  lea     rcx, aMSpwindowtrack_1; "m_spWindowTracker->TrackWindow() failed"
0x140035d2f  jmp     loc_140035CAF
0x140035d34  mov     edi, 80070057h
0x140035d39  mov     rax, cs:WPP_GLOBAL_Control
0x140035d40  cmp     rax, rsi
0x140035d43  jz      short loc_140035DAA
0x140035d45  test    byte ptr [rax+1Ch], 8
0x140035d49  jz      short loc_140035DAA
0x140035d4b  cmp     byte ptr [rax+19h], 2
0x140035d4f  jb      short loc_140035DAA
0x140035d51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035d56  mov     edx, 3Dh ; '='
0x140035d5b  mov     dword ptr [rsp+0A8h+var_80], 80070057h
0x140035d63  lea     rcx, aReceivedUpdate; "Received update for non-existing hint i"...
0x140035d6a  jmp     loc_140035CB3
0x140035d6f  mov     rsi, [rsp+0A8h+var_48]
0x140035d74  xor     edi, edi
0x140035d76  cmp     [rsi+3Ch], edi
0x140035d79  jz      short loc_140035D8D
0x140035d7b  test    rbx, rbx
0x140035d7e  jz      short loc_140035D8D
0x140035d80  lea     rcx, [rsi+28h]; lprcDst
0x140035d84  mov     rdx, rbx; lprcSrc
0x140035d87  call    cs:__imp_CopyRect
0x140035d8d  mov     rdx, rbp; HWND
0x140035d90  mov     dword ptr [rsi+48Ch], 1
0x140035d9a  mov     rcx, r15; this
0x140035d9d  call    ?AdjustGeometryForWindow@CRdpHintManager@@EEAAJPEAUHWND__@@@Z; CRdpHintManager::AdjustGeometryForWindow(HWND__ *)
0x140035da2  mov     rcx, r15; this
0x140035da5  call    ?UpdateHints@CRdpHintManager@@AEAAXXZ; CRdpHintManager::UpdateHints(void)
0x140035daa  lea     rcx, [rsp+0A8h+lprcSrc]; this
0x140035db2  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140035db7  mov     rbx, [rsp+0A8h+arg_10]
0x140035dbf  mov     eax, edi
0x140035dc1  add     rsp, 70h
0x140035dc5  pop     r15
0x140035dc7  pop     r14
0x140035dc9  pop     r13
0x140035dcb  pop     r12
0x140035dcd  pop     rdi
0x140035dce  pop     rsi
0x140035dcf  pop     rbp
0x140035dd0  retn
```
