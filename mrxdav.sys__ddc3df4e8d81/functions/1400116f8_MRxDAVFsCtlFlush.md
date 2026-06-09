# MRxDAVFsCtlFlush

- ea: `0x1400116f8`
- end: `0x140011a15`
- name: `MRxDAVFsCtlFlush`
- size: `797`
- prototype: `__int64 __fastcall(PMRX_FCB Fcb)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140011440`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001afc`
- `0x140001b64`
- `0x1400116f8`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140011734`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001176c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400117bf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001184d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400118ba`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011911`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001196e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400119fe`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028ebd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011734`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001176c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400117bf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001184d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400118ba`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140011911`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001196e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400119fe`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028ebd`
- `rdbss!RxFlushFcbInSystemCache` at `0x140011888`
- `rdbss!RxFlushFcbInSystemCache` at `0x140011888`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14001194d`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14001194d`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140011813`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140011813`

## pseudocode

```c
__int64 __fastcall MRxDAVFsCtlFlush(PMRX_FCB Fcb)
{
  struct _LIST_ENTRY *Flink; // r12
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax
  __int64 v7; // rdi
  int Flink_low; // ebx
  HANDLE v9; // rax
  int v10; // edi
  DWORD LowPart; // r13d
  __int64 v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  LONG HighPart; // ebx
  __int64 v18; // rdi
  HANDLE v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rbx
  HANDLE v23; // rax
  char v25; // [rsp+80h] [rbp+8h]

  v25 = 0;
  Flink = Fcb->Header.FilterContexts.Flink;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v3, 63, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, CurrentThreadId);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v6 = PsGetCurrentThreadId();
    WPP_SF_qqq(v5, 64, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v6, Flink, Fcb);
  }
  if ( LOWORD(Flink->Flink) != 0xEC22 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      Flink_low = LOWORD(Flink->Flink);
      v9 = PsGetCurrentThreadId();
      WPP_SF_qD(v7, 65, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v9, Flink_low);
    }
    v10 = -1073741637;
    goto LABEL_29;
  }
  LowPart = Fcb[3].Header.ValidDataLength.LowPart;
  if ( Fcb[3].Header.ValidDataLength.QuadPart )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      HighPart = Fcb[3].Header.ValidDataLength.HighPart;
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v19 = PsGetCurrentThreadId();
      WPP_SF_qll(v18, v20, v21, v19, LowPart, HighPart);
    }
    v10 = -1073741811;
  }
  else
  {
    v10 = RxAcquireExclusiveFcbResourceInMRx(Fcb);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_29;
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      v14 = 67;
      goto LABEL_17;
    }
    v25 = 1;
    v10 = RxFlushFcbInSystemCache((PFCB)Flink, 1u);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_29;
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      v14 = 68;
LABEL_17:
      WPP_SF_qD(v12, v14, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v13, v10);
      goto LABEL_29;
    }
    if ( ((__int64)Flink[14].Blink & 0x4000) != 0 )
    {
      v10 = 0;
      goto LABEL_29;
    }
    v10 = UMRxAsyncEngOuterWrapper((__int64)Fcb, v15, v16, 0x10u, MRxDAVFsCtlContinuation, (__int64)"MRxDAVFsCtlFlush");
    if ( v10 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      v14 = 69;
      goto LABEL_17;
    }
  }
LABEL_29:
  if ( v25 )
    RxReleaseFcbResourceInMRx(Fcb);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v23 = PsGetCurrentThreadId();
    WPP_SF_qD(v22, 71, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v23, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400116f8  mov     rax, rsp
0x1400116fb  push    rbx
0x1400116fc  push    rsi
0x1400116fd  push    rdi
0x1400116fe  push    r12
0x140011700  push    r13
0x140011702  push    r14
0x140011704  sub     rsp, 48h
0x140011708  mov     r14, rcx
0x14001170b  mov     byte ptr [rax+8], 0
0x14001170f  mov     r12, [rcx+38h]
0x140011713  lea     r13, WPP_GLOBAL_Control
0x14001171a  mov     rbx, cs:WPP_GLOBAL_Control
0x140011721  mov     esi, 2000h
0x140011726  cmp     rbx, r13
0x140011729  jz      short loc_140011757
0x14001172b  test    [rbx+2Ch], esi
0x14001172e  jz      short loc_140011757
0x140011730  mov     rbx, [rbx+18h]
0x140011734  call    cs:__imp_PsGetCurrentThreadId
0x14001173b  nop     dword ptr [rax+rax+00h]
0x140011740  mov     r9, rax
0x140011743  mov     edx, 3Fh ; '?'
0x140011748  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x14001174f  mov     rcx, rbx
0x140011752  call    WPP_SF_q
0x140011757  mov     rbx, cs:WPP_GLOBAL_Control
0x14001175e  cmp     rbx, r13
0x140011761  jz      short loc_140011799
0x140011763  test    [rbx+2Ch], esi
0x140011766  jz      short loc_140011799
0x140011768  mov     rbx, [rbx+18h]
0x14001176c  call    cs:__imp_PsGetCurrentThreadId
0x140011773  nop     dword ptr [rax+rax+00h]
0x140011778  mov     r9, rax
0x14001177b  mov     edx, 40h ; '@'
0x140011780  mov     [rsp+78h+var_50], r14
0x140011785  mov     [rsp+78h+var_58], r12
0x14001178a  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011791  mov     rcx, rbx
0x140011794  call    WPP_SF_qqq
0x140011799  movzx   ecx, word ptr [r12]
0x14001179e  mov     eax, 0EC22h
0x1400117a3  cmp     cx, ax
0x1400117a6  jz      short loc_1400117F0
0x1400117a8  mov     rdi, cs:WPP_GLOBAL_Control
0x1400117af  cmp     rdi, r13
0x1400117b2  jz      short loc_1400117E6
0x1400117b4  test    [rdi+2Ch], esi
0x1400117b7  jz      short loc_1400117E6
0x1400117b9  mov     rdi, [rdi+18h]
0x1400117bd  mov     ebx, ecx
0x1400117bf  call    cs:__imp_PsGetCurrentThreadId
0x1400117c6  nop     dword ptr [rax+rax+00h]
0x1400117cb  mov     r9, rax
0x1400117ce  mov     edx, 41h ; 'A'
0x1400117d3  mov     dword ptr [rsp+78h+var_58], ebx
0x1400117d7  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x1400117de  mov     rcx, rdi
0x1400117e1  call    WPP_SF_qD
0x1400117e6  mov     edi, 0C00000BBh
0x1400117eb  jmp     loc_14001193D
0x1400117f0  mov     r13d, [r14+238h]
0x1400117f7  test    r13d, r13d
0x1400117fa  jnz     loc_1400118EE
0x140011800  cmp     [r14+23Ch], r13d
0x140011807  jnz     loc_1400118EE
0x14001180d  mov     rdx, r12
0x140011810  mov     rcx, r14; Fcb
0x140011813  call    cs:__imp_RxAcquireExclusiveFcbResourceInMRx
0x14001181a  nop     dword ptr [rax+rax+00h]
0x14001181f  mov     edi, eax
0x140011821  mov     [rsp+78h+var_44], eax
0x140011825  test    eax, eax
0x140011827  jz      short loc_140011876
0x140011829  mov     rbx, cs:WPP_GLOBAL_Control
0x140011830  lea     r13, WPP_GLOBAL_Control
0x140011837  cmp     rbx, r13
0x14001183a  jz      loc_1400118EC
0x140011840  test    [rbx+2Ch], esi
0x140011843  jz      loc_1400118EC
0x140011849  mov     rbx, [rbx+18h]
0x14001184d  call    cs:__imp_PsGetCurrentThreadId
0x140011854  nop     dword ptr [rax+rax+00h]
0x140011859  mov     edx, 43h ; 'C'
0x14001185e  mov     r9, rax
0x140011861  mov     dword ptr [rsp+78h+var_58], edi
0x140011865  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x14001186c  mov     rcx, rbx
0x14001186f  call    WPP_SF_qD
0x140011874  jmp     short loc_1400118EC
0x140011876  mov     al, 1
0x140011878  mov     [rsp+78h+arg_0], al
0x14001187f  mov     [rsp+78h+var_48], al
0x140011883  mov     dl, al; SynchronizeWithLazyWriter
0x140011885  mov     rcx, r12; Fcb
0x140011888  call    cs:__imp_RxFlushFcbInSystemCache
0x14001188f  nop     dword ptr [rax+rax+00h]
0x140011894  mov     edi, eax
0x140011896  mov     [rsp+78h+var_44], eax
0x14001189a  test    eax, eax
0x14001189c  jns     short loc_1400118CD
0x14001189e  mov     rbx, cs:WPP_GLOBAL_Control
0x1400118a5  lea     r13, WPP_GLOBAL_Control
0x1400118ac  cmp     rbx, r13
0x1400118af  jz      short loc_1400118EC
0x1400118b1  test    [rbx+2Ch], esi
0x1400118b4  jz      short loc_1400118EC
0x1400118b6  mov     rbx, [rbx+18h]
0x1400118ba  call    cs:__imp_PsGetCurrentThreadId
0x1400118c1  nop     dword ptr [rax+rax+00h]
0x1400118c6  mov     edx, 44h ; 'D'
0x1400118cb  jmp     short loc_14001185E
0x1400118cd  test    dword ptr [r12+0E8h], 4000h
0x1400118d9  jz      loc_1400119A6
0x1400118df  xor     edi, edi
0x1400118e1  mov     [rsp+78h+var_44], edi
0x1400118e5  lea     r13, WPP_GLOBAL_Control
0x1400118ec  jmp     short loc_14001193D
0x1400118ee  mov     rdi, cs:WPP_GLOBAL_Control
0x1400118f5  lea     rax, WPP_GLOBAL_Control
0x1400118fc  cmp     rdi, rax
0x1400118ff  jz      short loc_140011931
0x140011901  test    [rdi+2Ch], esi
0x140011904  jz      short loc_140011931
0x140011906  mov     ebx, [r14+23Ch]
0x14001190d  mov     rdi, [rdi+18h]
0x140011911  call    cs:__imp_PsGetCurrentThreadId
0x140011918  nop     dword ptr [rax+rax+00h]
0x14001191d  mov     r9, rax
0x140011920  mov     dword ptr [rsp+78h+var_50], ebx
0x140011924  mov     dword ptr [rsp+78h+var_58], r13d
0x140011929  mov     rcx, rdi
0x14001192c  call    WPP_SF_qll
0x140011931  mov     edi, 0C000000Dh
0x140011936  lea     r13, WPP_GLOBAL_Control
0x14001193d  cmp     [rsp+78h+arg_0], 0
0x140011945  jz      short loc_140011959
0x140011947  mov     rdx, r12
0x14001194a  mov     rcx, r14; Fcb
0x14001194d  call    cs:__imp_RxReleaseFcbResourceInMRx
0x140011954  nop     dword ptr [rax+rax+00h]
0x140011959  mov     rbx, cs:WPP_GLOBAL_Control
0x140011960  cmp     rbx, r13
0x140011963  jz      short loc_140011995
0x140011965  test    [rbx+2Ch], esi
0x140011968  jz      short loc_140011995
0x14001196a  mov     rbx, [rbx+18h]
0x14001196e  call    cs:__imp_PsGetCurrentThreadId
0x140011975  nop     dword ptr [rax+rax+00h]
0x14001197a  mov     r9, rax
0x14001197d  mov     edx, 47h ; 'G'
0x140011982  mov     dword ptr [rsp+78h+var_58], edi
0x140011986  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x14001198d  mov     rcx, rbx
0x140011990  call    WPP_SF_qD
0x140011995  mov     eax, edi
0x140011997  add     rsp, 48h
0x14001199b  pop     r14
0x14001199d  pop     r13
0x14001199f  pop     r12
0x1400119a1  pop     rdi
0x1400119a2  pop     rsi
0x1400119a3  pop     rbx
0x1400119a4  retn
0x1400119a6  mov     r9d, 10h
0x1400119ac  lea     rax, aMrxdavfsctlflu; "MRxDAVFsCtlFlush"
0x1400119b3  mov     [rsp+78h+var_50], rax
0x1400119b8  lea     rax, MRxDAVFsCtlContinuation
0x1400119bf  mov     [rsp+78h+var_58], rax
0x1400119c4  mov     rcx, r14
0x1400119c7  call    UMRxAsyncEngOuterWrapper
0x1400119cc  mov     edi, eax
0x1400119ce  mov     [rsp+78h+var_44], eax
0x1400119d2  test    eax, eax
0x1400119d4  jns     loc_1400118E5
0x1400119da  mov     rbx, cs:WPP_GLOBAL_Control
0x1400119e1  lea     r13, WPP_GLOBAL_Control
0x1400119e8  cmp     rbx, r13
0x1400119eb  jz      loc_1400118EC
0x1400119f1  test    [rbx+2Ch], esi
0x1400119f4  jz      loc_1400118EC
0x1400119fa  mov     rbx, [rbx+18h]
0x1400119fe  call    cs:__imp_PsGetCurrentThreadId
0x140011a05  nop     dword ptr [rax+rax+00h]
0x140011a0a  mov     edx, 45h ; 'E'
0x140011a0f  jmp     loc_14001185E
0x140028e8c  push    rbx
0x140028e8e  push    rbp
0x140028e8f  sub     rsp, 38h
0x140028e93  mov     rbp, rdx
0x140028e96  movzx   eax, cl
0x140028e99  test    cl, cl
0x140028e9b  jz      short loc_140028EE8
0x140028e9d  lea     rax, WPP_GLOBAL_Control
0x140028ea4  mov     rbx, cs:WPP_GLOBAL_Control
0x140028eab  cmp     rbx, rax
0x140028eae  jz      short loc_140028EE1
0x140028eb0  mov     eax, [rbx+2Ch]
0x140028eb3  bt      eax, 0Dh
0x140028eb7  jnb     short loc_140028EE1
0x140028eb9  mov     rbx, [rbx+18h]
0x140028ebd  call    cs:__imp_PsGetCurrentThreadId
0x140028ec4  nop     dword ptr [rax+rax+00h]
0x140028ec9  mov     r9, rax
0x140028ecc  mov     edx, 46h ; 'F'
0x140028ed1  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140028ed8  mov     rcx, rbx
0x140028edb  call    WPP_SF_q
0x140028ee0  nop
0x140028ee1  mov     dword ptr [rbp+34h], 0C000000Dh
0x140028ee8  add     rsp, 38h
0x140028eec  pop     rbp
0x140028eed  pop     rbx
0x140028eee  retn
```
