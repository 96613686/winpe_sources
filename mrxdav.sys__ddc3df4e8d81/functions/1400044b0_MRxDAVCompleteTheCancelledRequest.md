# MRxDAVCompleteTheCancelledRequest

- ea: `0x1400044b0`
- end: `0x14000493f`
- name: `MRxDAVCompleteTheCancelledRequest`
- size: `1167`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140004350`

## callees

- `0x140001680`
- `0x1400017e4`
- `0x1400044b0`
- `0x140004dac`
- `0x140004e98`
- `0x140004f50`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400044eb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004583`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400045b8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004609`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004640`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004677`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400046c3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004762`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400047ac`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004800`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004837`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000486e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400048a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400048d1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400048fd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400044eb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004583`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400045b8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004609`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004640`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004677`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400046c3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004762`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400047ac`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004800`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004837`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000486e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400048a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400048d1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400048fd`

## pseudocode

```c
__int64 __fastcall MRxDAVCompleteTheCancelledRequest(__int64 a1, unsigned int a2)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  int v6; // r14d
  unsigned int v7; // edi
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rdx
  __int64 v12; // r14
  __int64 v13; // r14
  __int64 v14; // rbx
  HANDLE v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // r14

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qq(v4, 22, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId, a1);
  }
  v6 = *(_DWORD *)(a1 + 744);
  v7 = 0;
  if ( v6 > 7 )
  {
    switch ( v6 )
    {
      case 8:
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
        }
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v9 = PsGetCurrentThreadId();
        v10 = 35;
        goto LABEL_73;
      case 11:
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
        }
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v9 = PsGetCurrentThreadId();
        v10 = 25;
        goto LABEL_73;
      case 12:
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
        }
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v9 = PsGetCurrentThreadId();
        v10 = 27;
        goto LABEL_73;
      case 13:
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
        }
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v9 = PsGetCurrentThreadId();
        v10 = 36;
        goto LABEL_73;
      case 15:
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
        }
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v9 = PsGetCurrentThreadId();
        v10 = 37;
        goto LABEL_73;
    }
    if ( v6 != 16 )
    {
      if ( v6 == 17 )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
        }
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v9 = PsGetCurrentThreadId();
        v10 = 39;
        goto LABEL_73;
      }
      goto LABEL_46;
    }
    v19 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 72LL) + 32LL);
    if ( v19 )
      v13 = *(_QWORD *)(v19 + 136);
    else
      v13 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v15 = PsGetCurrentThreadId();
      v16 = 38;
      goto LABEL_36;
    }
LABEL_37:
    if ( *(_DWORD *)(v13 + 20) )
    {
      _InterlockedExchange((volatile __int32 *)(v13 + 16), 1);
      *(_DWORD *)(v13 + 20) = 0;
    }
    return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
  }
  switch ( v6 )
  {
    case 7:
      v12 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 72LL) + 32LL);
      if ( v12 )
        v13 = *(_QWORD *)(v12 + 136);
      else
        v13 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v15 = PsGetCurrentThreadId();
        v16 = 26;
LABEL_36:
        WPP_SF_qq(v14, v16, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v15, a1);
        goto LABEL_37;
      }
      goto LABEL_37;
    case 0:
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      v10 = 28;
      goto LABEL_73;
    case 1:
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      v10 = 33;
      goto LABEL_73;
    case 2:
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      v10 = 34;
      goto LABEL_73;
    case 3:
      return (unsigned int)MRxDAVHandleCreateSrvCallCancellation(a1);
    case 4:
      return (unsigned int)MRxDAVHandleCreateVNetRootCancellation(a1);
    case 5:
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      v10 = 30;
      goto LABEL_73;
    case 6:
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      v10 = 32;
LABEL_73:
      WPP_SF_qq(v8, v10, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v9, a1);
      return (unsigned int)MRxDAVHandleGeneralCancellation(a1, a2);
  }
LABEL_46:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v18 = PsGetCurrentThreadId();
    WPP_SF_qD(v17, 23, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v18, v6);
  }
  return v7;
}

```

## disassembly

```asm
0x1400044b0  push    rbx
0x1400044b2  push    rbp
0x1400044b3  push    rsi
0x1400044b4  push    rdi
0x1400044b5  push    r12
0x1400044b7  push    r14
0x1400044b9  push    r15
0x1400044bb  sub     rsp, 30h
0x1400044bf  mov     ebp, edx
0x1400044c1  mov     rsi, rcx
0x1400044c4  mov     rbx, cs:WPP_GLOBAL_Control
0x1400044cb  lea     r15, WPP_GLOBAL_Control
0x1400044d2  lea     r12, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x1400044d9  cmp     rbx, r15
0x1400044dc  jz      short loc_14000450F
0x1400044de  test    dword ptr [rbx+2Ch], 4000h
0x1400044e5  jz      short loc_14000450F
0x1400044e7  mov     rbx, [rbx+18h]
0x1400044eb  call    cs:__imp_PsGetCurrentThreadId
0x1400044f2  nop     dword ptr [rax+rax+00h]
0x1400044f7  mov     edx, 16h
0x1400044fc  mov     [rsp+68h+var_48], rsi
0x140004501  mov     r9, rax
0x140004504  mov     r8, r12
0x140004507  mov     rcx, rbx
0x14000450a  call    WPP_SF_qq
0x14000450f  mov     r14d, [rsi+2E8h]
0x140004516  xor     edi, edi
0x140004518  cmp     r14d, 7
0x14000451c  jg      loc_140004703
0x140004522  jz      loc_14000468D
0x140004528  mov     ecx, r14d
0x14000452b  test    r14d, r14d
0x14000452e  jz      loc_140004656
0x140004534  sub     ecx, 1
0x140004537  jz      loc_14000461F
0x14000453d  sub     ecx, 1
0x140004540  jz      loc_1400045E8
0x140004546  sub     ecx, 1
0x140004549  jz      loc_1400045DB
0x14000454f  sub     ecx, 1
0x140004552  jz      short loc_1400045CE
0x140004554  sub     ecx, 1
0x140004557  jz      short loc_140004597
0x140004559  cmp     ecx, 1
0x14000455c  jnz     loc_140004741
0x140004562  mov     rbx, cs:WPP_GLOBAL_Control
0x140004569  cmp     rbx, r15
0x14000456c  jz      loc_140004921
0x140004572  test    dword ptr [rbx+2Ch], 2000h
0x140004579  jz      loc_140004921
0x14000457f  mov     rbx, [rbx+18h]
0x140004583  call    cs:__imp_PsGetCurrentThreadId
0x14000458a  nop     dword ptr [rax+rax+00h]
0x14000458f  lea     edx, [rdi+20h]
0x140004592  jmp     loc_14000490E
0x140004597  mov     rbx, cs:WPP_GLOBAL_Control
0x14000459e  cmp     rbx, r15
0x1400045a1  jz      loc_140004921
0x1400045a7  test    dword ptr [rbx+2Ch], 2000h
0x1400045ae  jz      loc_140004921
0x1400045b4  mov     rbx, [rbx+18h]
0x1400045b8  call    cs:__imp_PsGetCurrentThreadId
0x1400045bf  nop     dword ptr [rax+rax+00h]
0x1400045c4  mov     edx, 1Eh
0x1400045c9  jmp     loc_14000490E
0x1400045ce  mov     rcx, rsi
0x1400045d1  call    MRxDAVHandleCreateVNetRootCancellation
0x1400045d6  jmp     loc_14000492B
0x1400045db  mov     rcx, rsi
0x1400045de  call    MRxDAVHandleCreateSrvCallCancellation
0x1400045e3  jmp     loc_14000492B
0x1400045e8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400045ef  cmp     rbx, r15
0x1400045f2  jz      loc_140004921
0x1400045f8  test    dword ptr [rbx+2Ch], 2000h
0x1400045ff  jz      loc_140004921
0x140004605  mov     rbx, [rbx+18h]
0x140004609  call    cs:__imp_PsGetCurrentThreadId
0x140004610  nop     dword ptr [rax+rax+00h]
0x140004615  mov     edx, 22h ; '"'
0x14000461a  jmp     loc_14000490E
0x14000461f  mov     rbx, cs:WPP_GLOBAL_Control
0x140004626  cmp     rbx, r15
0x140004629  jz      loc_140004921
0x14000462f  test    dword ptr [rbx+2Ch], 2000h
0x140004636  jz      loc_140004921
0x14000463c  mov     rbx, [rbx+18h]
0x140004640  call    cs:__imp_PsGetCurrentThreadId
0x140004647  nop     dword ptr [rax+rax+00h]
0x14000464c  mov     edx, 21h ; '!'
0x140004651  jmp     loc_14000490E
0x140004656  mov     rbx, cs:WPP_GLOBAL_Control
0x14000465d  cmp     rbx, r15
0x140004660  jz      loc_140004921
0x140004666  test    dword ptr [rbx+2Ch], 2000h
0x14000466d  jz      loc_140004921
0x140004673  mov     rbx, [rbx+18h]
0x140004677  call    cs:__imp_PsGetCurrentThreadId
0x14000467e  nop     dword ptr [rax+rax+00h]
0x140004683  mov     edx, 1Ch
0x140004688  jmp     loc_14000490E
0x14000468d  mov     rax, [rsi+50h]
0x140004691  mov     rcx, [rax+48h]
0x140004695  mov     r14, [rcx+20h]
0x140004699  test    r14, r14
0x14000469c  jnz     short loc_1400046A3
0x14000469e  mov     r14, rdi
0x1400046a1  jmp     short loc_1400046AA
0x1400046a3  mov     r14, [r14+88h]
0x1400046aa  mov     rbx, cs:WPP_GLOBAL_Control
0x1400046b1  cmp     rbx, r15
0x1400046b4  jz      short loc_1400046E7
0x1400046b6  test    dword ptr [rbx+2Ch], 2000h
0x1400046bd  jz      short loc_1400046E7
0x1400046bf  mov     rbx, [rbx+18h]
0x1400046c3  call    cs:__imp_PsGetCurrentThreadId
0x1400046ca  nop     dword ptr [rax+rax+00h]
0x1400046cf  mov     edx, 1Ah
0x1400046d4  mov     r9, rax
0x1400046d7  mov     [rsp+68h+var_48], rsi
0x1400046dc  mov     r8, r12
0x1400046df  mov     rcx, rbx
0x1400046e2  call    WPP_SF_qq
0x1400046e7  cmp     [r14+14h], edi
0x1400046eb  jz      loc_140004921
0x1400046f1  mov     eax, 1
0x1400046f6  xchg    eax, [r14+10h]
0x1400046fa  mov     [r14+14h], edi
0x1400046fe  jmp     loc_140004921
0x140004703  mov     ecx, r14d
0x140004706  sub     ecx, 8
0x140004709  jz      loc_1400048E4
0x14000470f  sub     ecx, 3
0x140004712  jz      loc_1400048B8
0x140004718  sub     ecx, 1
0x14000471b  jz      loc_140004884
0x140004721  sub     ecx, 1
0x140004724  jz      loc_14000484D
0x14000472a  sub     ecx, 2
0x14000472d  jz      loc_140004816
0x140004733  sub     ecx, 1
0x140004736  jz      loc_1400047C2
0x14000473c  cmp     ecx, 1
0x14000473f  jz      short loc_14000478B
0x140004741  mov     rbx, cs:WPP_GLOBAL_Control
0x140004748  cmp     rbx, r15
0x14000474b  jz      loc_14000492D
0x140004751  test    dword ptr [rbx+2Ch], 2000h
0x140004758  jz      loc_14000492D
0x14000475e  mov     rbx, [rbx+18h]
0x140004762  call    cs:__imp_PsGetCurrentThreadId
0x140004769  nop     dword ptr [rax+rax+00h]
0x14000476e  mov     edx, 17h
0x140004773  mov     dword ptr [rsp+68h+var_48], r14d
0x140004778  mov     r9, rax
0x14000477b  mov     r8, r12
0x14000477e  mov     rcx, rbx
0x140004781  call    WPP_SF_qD
0x140004786  jmp     loc_14000492D
0x14000478b  mov     rbx, cs:WPP_GLOBAL_Control
0x140004792  cmp     rbx, r15
0x140004795  jz      loc_140004921
0x14000479b  test    dword ptr [rbx+2Ch], 2000h
0x1400047a2  jz      loc_140004921
0x1400047a8  mov     rbx, [rbx+18h]
0x1400047ac  call    cs:__imp_PsGetCurrentThreadId
0x1400047b3  nop     dword ptr [rax+rax+00h]
0x1400047b8  mov     edx, 27h ; '''
0x1400047bd  jmp     loc_14000490E
0x1400047c2  mov     rax, [rsi+50h]
0x1400047c6  mov     rcx, [rax+48h]
0x1400047ca  mov     r14, [rcx+20h]
0x1400047ce  test    r14, r14
0x1400047d1  jnz     short loc_1400047D8
0x1400047d3  mov     r14, rdi
0x1400047d6  jmp     short loc_1400047DF
0x1400047d8  mov     r14, [r14+88h]
0x1400047df  mov     rbx, cs:WPP_GLOBAL_Control
0x1400047e6  cmp     rbx, r15
0x1400047e9  jz      loc_1400046E7
0x1400047ef  test    dword ptr [rbx+2Ch], 2000h
0x1400047f6  jz      loc_1400046E7
0x1400047fc  mov     rbx, [rbx+18h]
0x140004800  call    cs:__imp_PsGetCurrentThreadId
0x140004807  nop     dword ptr [rax+rax+00h]
0x14000480c  mov     edx, 26h ; '&'
0x140004811  jmp     loc_1400046D4
0x140004816  mov     rbx, cs:WPP_GLOBAL_Control
0x14000481d  cmp     rbx, r15
0x140004820  jz      loc_140004921
0x140004826  test    dword ptr [rbx+2Ch], 2000h
0x14000482d  jz      loc_140004921
0x140004833  mov     rbx, [rbx+18h]
0x140004837  call    cs:__imp_PsGetCurrentThreadId
0x14000483e  nop     dword ptr [rax+rax+00h]
0x140004843  mov     edx, 25h ; '%'
0x140004848  jmp     loc_14000490E
0x14000484d  mov     rbx, cs:WPP_GLOBAL_Control
0x140004854  cmp     rbx, r15
0x140004857  jz      loc_140004921
0x14000485d  test    dword ptr [rbx+2Ch], 2000h
0x140004864  jz      loc_140004921
0x14000486a  mov     rbx, [rbx+18h]
0x14000486e  call    cs:__imp_PsGetCurrentThreadId
0x140004875  nop     dword ptr [rax+rax+00h]
0x14000487a  mov     edx, 24h ; '$'
0x14000487f  jmp     loc_14000490E
0x140004884  mov     rbx, cs:WPP_GLOBAL_Control
0x14000488b  cmp     rbx, r15
0x14000488e  jz      loc_140004921
0x140004894  test    dword ptr [rbx+2Ch], 2000h
0x14000489b  jz      loc_140004921
0x1400048a1  mov     rbx, [rbx+18h]
0x1400048a5  call    cs:__imp_PsGetCurrentThreadId
0x1400048ac  nop     dword ptr [rax+rax+00h]
0x1400048b1  mov     edx, 1Bh
0x1400048b6  jmp     short loc_14000490E
0x1400048b8  mov     rbx, cs:WPP_GLOBAL_Control
0x1400048bf  cmp     rbx, r15
0x1400048c2  jz      short loc_140004921
0x1400048c4  test    dword ptr [rbx+2Ch], 2000h
0x1400048cb  jz      short loc_140004921
0x1400048cd  mov     rbx, [rbx+18h]
0x1400048d1  call    cs:__imp_PsGetCurrentThreadId
0x1400048d8  nop     dword ptr [rax+rax+00h]
0x1400048dd  mov     edx, 19h
0x1400048e2  jmp     short loc_14000490E
0x1400048e4  mov     rbx, cs:WPP_GLOBAL_Control
0x1400048eb  cmp     rbx, r15
0x1400048ee  jz      short loc_140004921
0x1400048f0  test    dword ptr [rbx+2Ch], 2000h
0x1400048f7  jz      short loc_140004921
0x1400048f9  mov     rbx, [rbx+18h]
0x1400048fd  call    cs:__imp_PsGetCurrentThreadId
0x140004904  nop     dword ptr [rax+rax+00h]
0x140004909  mov     edx, 23h ; '#'
0x14000490e  mov     r9, rax
0x140004911  mov     [rsp+68h+var_48], rsi
0x140004916  mov     r8, r12
0x140004919  mov     rcx, rbx
0x14000491c  call    WPP_SF_qq
0x140004921  mov     edx, ebp
0x140004923  mov     rcx, rsi
0x140004926  call    MRxDAVHandleGeneralCancellation
0x14000492b  mov     edi, eax
0x14000492d  mov     eax, edi
0x14000492f  add     rsp, 30h
0x140004933  pop     r15
0x140004935  pop     r14
0x140004937  pop     r12
0x140004939  pop     rdi
0x14000493a  pop     rsi
0x14000493b  pop     rbp
0x14000493c  pop     rbx
0x14000493d  retn
```
