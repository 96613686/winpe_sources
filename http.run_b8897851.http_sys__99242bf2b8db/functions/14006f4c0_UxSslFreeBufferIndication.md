# UxSslFreeBufferIndication

- ea: `0x14006f4c0`
- end: `0x14006f9f9`
- name: `UxSslFreeBufferIndication`
- size: `1337`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140080680`

## callees

- `0x14000a350`
- `0x140049d28`
- `0x14005dff0`
- `0x14006e50c`
- `0x14006f4c0`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f5b8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f64d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f6c9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f5b8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f64d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f6c9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006f775`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006f775`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f913`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f913`

## pseudocode

```c
void __fastcall UxSslFreeBufferIndication(__int64 a1, _QWORD *a2)
{
  volatile signed __int32 *v2; // rbx
  int v5; // eax
  volatile signed __int32 *v6; // rdi
  int v7; // ebp
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned __int64 v10; // rbp
  bool v11; // zf
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rdi
  __int64 v14; // rbx
  USHORT CurrentNodeNumber; // ax
  _DWORD v16[24]; // [rsp+30h] [rbp-98h] BYREF

  v2 = (volatile signed __int32 *)a2[4];
  v5 = _InterlockedDecrement(v2 + 5);
  if ( UxDebugCheckRefcount && v5 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v2 + 5), 0x46u, v5);
  if ( !v5 )
  {
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qq(1041, 193, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, v2);
    v6 = (volatile signed __int32 *)*((_QWORD *)v2 + 5);
    if ( !v6 )
      goto LABEL_18;
    v7 = _InterlockedDecrement(v6 + 5);
    if ( UxDebugCheckRefcount && v7 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v6 + 5), 0x46u, v7);
    if ( v7 )
    {
LABEL_17:
      *((_QWORD *)v2 + 5) = 0;
LABEL_18:
      *((_DWORD *)v2 + 4) = 1685280885;
      if ( v2 == (volatile signed __int32 *)(a1 + 1840) )
      {
        *(_QWORD *)(a1 + 1496) = v2;
      }
      else if ( UxDebugDisableLookaside )
      {
        memset(v16, 0, sizeof(v16));
        v16[10] = dword_1401A06E8;
        ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A06F8)(v2, v16);
      }
      else if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A06D0, v2);
      }
      else
      {
        v13 = qword_1401A06D0 + ((unsigned __int64)(unsigned int)(*v2 + 1) << 7);
        if ( !*(_BYTE *)(v13 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A06D0, v13 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v13 + 64), (PVOID)v2);
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 194, WPP_6033a49e77e7395416619077875677ff_Traceguids);
      goto LABEL_22;
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v6);
    v8 = *((_DWORD *)v6 + 30);
    *((_DWORD *)v6 + 4) = 1819498613;
    if ( v8 )
    {
      switch ( v8 )
      {
        case 1u:
          if ( UxDebugDisableLookaside )
          {
            memset(v16, 0, sizeof(v16));
            v16[10] = dword_1401A0658;
            ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0668)(v6, v16);
            goto LABEL_15;
          }
          v9 = qword_1401A0640;
          break;
        case 2u:
          if ( !UxDebugDisableLookaside )
          {
            v9 = qword_1401A0670;
            if ( !UxCompactMode )
            {
              v10 = qword_1401A0670 + ((unsigned __int64)(unsigned int)(*v6 + 1) << 7);
              if ( *(_BYTE *)(v10 + 176) )
                goto LABEL_14;
              goto LABEL_37;
            }
            goto LABEL_51;
          }
          memset(v16, 0, sizeof(v16));
          v16[10] = dword_1401A0688;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0698)(v6, v16);
          goto LABEL_15;
        case 3u:
          if ( UxDebugDisableLookaside )
          {
            memset(v16, 0, sizeof(v16));
            v16[10] = dword_1401A06B8;
            ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A06C8)(v6, v16);
            goto LABEL_15;
          }
          v9 = qword_1401A06A0;
          break;
        default:
          ExFreePoolWithTag((PVOID)v6, 0);
          goto LABEL_15;
      }
      if ( UxCompactMode )
      {
LABEL_51:
        PnlFreeToLookasideList(v9, v6);
        goto LABEL_15;
      }
      PplFreeToLookasideListProcessor(v9, v6, *(unsigned int *)v6);
    }
    else
    {
      if ( !UxDebugDisableLookaside )
      {
        v9 = qword_1401A0610;
        if ( !UxCompactMode )
        {
          v10 = qword_1401A0610 + ((unsigned __int64)(unsigned int)(*v6 + 1) << 7);
          if ( *(_BYTE *)(v10 + 176) )
          {
LABEL_14:
            ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 64), (PVOID)v6);
            goto LABEL_15;
          }
LABEL_37:
          PplpLazyInitializeLookasideList(v9, v10 + 64);
          goto LABEL_14;
        }
        goto LABEL_51;
      }
      memset(v16, 0, sizeof(v16));
      v16[10] = dword_1401A0628;
      ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0638)(v6, v16);
    }
LABEL_15:
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
    goto LABEL_17;
  }
LABEL_22:
  v11 = UxDebugDisableLookaside == 0;
  a2[4] = 0;
  *((_DWORD *)a2 + 4) = 1768049781;
  if ( v11 )
  {
    if ( UxCompactMode )
    {
      v14 = qword_1401A0700;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v14, a2, CurrentNodeNumber);
    }
    else
    {
      v12 = qword_1401A0700 + ((unsigned __int64)(unsigned int)(*(_DWORD *)a2 + 1) << 7);
      if ( !*(_BYTE *)(v12 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0700, v12 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v12 + 64), a2);
    }
  }
  else
  {
    memset(v16, 0, sizeof(v16));
    v16[10] = dword_1401A0718;
    ((void (__fastcall *)(_QWORD *, _DWORD *))off_1401A0728)(a2, v16);
  }
}

```

## disassembly

```asm
0x14006f4c0  push    rbx
0x14006f4c2  push    rbp
0x14006f4c3  push    rsi
0x14006f4c4  push    r14
0x14006f4c6  sub     rsp, 0A8h
0x14006f4cd  mov     rax, cs:__security_cookie
0x14006f4d4  xor     rax, rsp
0x14006f4d7  mov     [rsp+0C8h+var_38], rax
0x14006f4df  mov     rbx, [rdx+20h]
0x14006f4e3  mov     ebp, 0FFFFFFFFh
0x14006f4e8  mov     rsi, rdx
0x14006f4eb  mov     r14, rcx
0x14006f4ee  mov     eax, ebp
0x14006f4f0  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14006f4f4  lock xadd [rdx], eax
0x14006f4f8  dec     eax
0x14006f4fa  cmp     cs:UxDebugCheckRefcount, 0
0x14006f501  jnz     loc_14006F735
0x14006f507  mov     [rsp+0C8h+arg_10], rdi
0x14006f50f  mov     [rsp+0C8h+var_28], r15
0x14006f517  xor     r15d, r15d
0x14006f51a  test    eax, eax
0x14006f51c  jnz     loc_14006F600
0x14006f522  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006f529  jnz     loc_14006F7BC
0x14006f52f  mov     rdi, [rbx+28h]
0x14006f533  test    rdi, rdi
0x14006f536  jz      loc_14006F5D5
0x14006f53c  lea     rdx, [rdi+14h]; BugCheckParameter2
0x14006f540  lock xadd [rdx], ebp
0x14006f544  dec     ebp
0x14006f546  cmp     cs:UxDebugCheckRefcount, r15b
0x14006f54d  jnz     loc_14006F751
0x14006f553  test    ebp, ebp
0x14006f555  jnz     short loc_14006F5D1
0x14006f557  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006f55e  jnz     loc_14006F848
0x14006f564  mov     eax, [rdi+78h]
0x14006f567  mov     dword ptr [rdi+10h], 6C735875h
0x14006f56e  test    eax, eax
0x14006f570  jnz     loc_14006F6DA
0x14006f576  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f57d  jnz     loc_14006F866
0x14006f583  cmp     cs:UxCompactMode, r15b
0x14006f58a  mov     rcx, cs:qword_1401A0610
0x14006f591  jnz     loc_14006F795
0x14006f597  mov     ebp, [rdi]
0x14006f599  inc     ebp
0x14006f59b  shl     rbp, 7
0x14006f59f  add     rbp, rcx
0x14006f5a2  movzx   eax, byte ptr [rbp+0B0h]
0x14006f5a9  test    al, al
0x14006f5ab  jz      loc_14006F727
0x14006f5b1  mov     rdx, rdi; Entry
0x14006f5b4  lea     rcx, [rbp+40h]; Lookaside
0x14006f5b8  call    cs:__imp_ExFreeToLookasideListEx
0x14006f5bf  nop     dword ptr [rax+rax+00h]
0x14006f5c4  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006f5cb  jnz     loc_14006F959
0x14006f5d1  mov     [rbx+28h], r15
0x14006f5d5  lea     rax, [r14+730h]
0x14006f5dc  mov     dword ptr [rbx+10h], 64735875h
0x14006f5e3  cmp     rbx, rax
0x14006f5e6  jnz     loc_14006F687
0x14006f5ec  mov     [r14+5D8h], rbx
0x14006f5f3  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006f5fa  jnz     loc_14006F9A9
0x14006f600  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f607  mov     [rsi+20h], r15
0x14006f60b  mov     dword ptr [rsi+10h], 69624C75h
0x14006f612  jnz     loc_14006F9C4
0x14006f618  cmp     cs:UxCompactMode, r15b
0x14006f61f  jnz     loc_14006F76E
0x14006f625  mov     ebx, [rsi]
0x14006f627  mov     rcx, cs:qword_1401A0700
0x14006f62e  inc     ebx
0x14006f630  shl     rbx, 7
0x14006f634  add     rbx, rcx
0x14006f637  movzx   eax, byte ptr [rbx+0B0h]
0x14006f63e  test    al, al
0x14006f640  jz      loc_14006F83A
0x14006f646  mov     rdx, rsi; Entry
0x14006f649  lea     rcx, [rbx+40h]; Lookaside
0x14006f64d  call    cs:__imp_ExFreeToLookasideListEx
0x14006f654  nop     dword ptr [rax+rax+00h]
0x14006f659  mov     rdi, [rsp+0C8h+arg_10]
0x14006f661  mov     r15, [rsp+0C8h+var_28]
0x14006f669  mov     rcx, [rsp+0C8h+var_38]
0x14006f671  xor     rcx, rsp; StackCookie
0x14006f674  call    __security_check_cookie
0x14006f679  add     rsp, 0A8h
0x14006f680  pop     r14
0x14006f682  pop     rsi
0x14006f683  pop     rbp
0x14006f684  pop     rbx
0x14006f685  retn
0x14006f687  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f68e  jnz     loc_14006F974
0x14006f694  cmp     cs:UxCompactMode, r15b
0x14006f69b  mov     rcx, cs:qword_1401A06D0
0x14006f6a2  jnz     loc_14006F7A2
0x14006f6a8  mov     edi, [rbx]
0x14006f6aa  inc     edi
0x14006f6ac  shl     rdi, 7
0x14006f6b0  add     rdi, rcx
0x14006f6b3  movzx   eax, byte ptr [rdi+0B0h]
0x14006f6ba  test    al, al
0x14006f6bc  jz      loc_14006F82C
0x14006f6c2  mov     rdx, rbx; Entry
0x14006f6c5  lea     rcx, [rdi+40h]; Lookaside
0x14006f6c9  call    cs:__imp_ExFreeToLookasideListEx
0x14006f6d0  nop     dword ptr [rax+rax+00h]
0x14006f6d5  jmp     loc_14006F5F3
0x14006f6da  cmp     eax, 1
0x14006f6dd  jz      loc_14006F7DF
0x14006f6e3  cmp     eax, 2
0x14006f6e6  jnz     loc_14006F905
0x14006f6ec  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f6f3  jnz     loc_14006F8D0
0x14006f6f9  cmp     cs:UxCompactMode, r15b
0x14006f700  mov     rcx, cs:qword_1401A0670
0x14006f707  jnz     loc_14006F7AF
0x14006f70d  mov     ebp, [rdi]
0x14006f70f  inc     ebp
0x14006f711  shl     rbp, 7
0x14006f715  add     rbp, rcx
0x14006f718  movzx   eax, byte ptr [rbp+0B0h]
0x14006f71f  test    al, al
0x14006f721  jnz     loc_14006F5B1
0x14006f727  lea     rdx, [rbp+40h]
0x14006f72b  call    PplpLazyInitializeLookasideList
0x14006f730  jmp     loc_14006F5B1
0x14006f735  cmp     eax, ebp
0x14006f737  jg      loc_14006F507
0x14006f73d  movsxd  r9, eax; BugCheckParameter4
0x14006f740  mov     ecx, 3; BugCheckParameter1
0x14006f745  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x14006f74b  call    UlBugCheckEx
0x14006f751  cmp     ebp, 0FFFFFFFFh
0x14006f754  jg      loc_14006F553
0x14006f75a  movsxd  r9, ebp; BugCheckParameter4
0x14006f75d  mov     ecx, 3; BugCheckParameter1
0x14006f762  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x14006f768  call    UlBugCheckEx
0x14006f76e  mov     rbx, cs:qword_1401A0700
0x14006f775  call    cs:__imp_KeGetCurrentNodeNumber
0x14006f77c  nop     dword ptr [rax+rax+00h]
0x14006f781  movzx   r8d, ax
0x14006f785  mov     rdx, rsi
0x14006f788  mov     rcx, rbx
0x14006f78b  call    PplFreeToLookasideListProcessor
0x14006f790  jmp     loc_14006F659
0x14006f795  mov     rdx, rdi
0x14006f798  call    PnlFreeToLookasideList
0x14006f79d  jmp     loc_14006F5C4
0x14006f7a2  mov     rdx, rbx
0x14006f7a5  call    PnlFreeToLookasideList
0x14006f7aa  jmp     loc_14006F5F3
0x14006f7af  mov     rdx, rdi
0x14006f7b2  call    PnlFreeToLookasideList
0x14006f7b7  jmp     loc_14006F5C4
0x14006f7bc  mov     edx, 0C1h
0x14006f7c1  mov     [rsp+0C8h+var_A8], rbx
0x14006f7c6  mov     ecx, 411h
0x14006f7cb  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x14006f7d2  mov     r9, r14
0x14006f7d5  call    WPP_SF_qq
0x14006f7da  jmp     loc_14006F52F
0x14006f7df  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f7e6  jnz     loc_14006F89B
0x14006f7ec  mov     rcx, cs:qword_1401A0640
0x14006f7f3  jmp     short loc_14006F809
0x14006f7f5  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f7fc  jnz     loc_14006F924
0x14006f802  mov     rcx, cs:qword_1401A06A0
0x14006f809  cmp     cs:UxCompactMode, r15b
0x14006f810  mov     rdx, rdi
0x14006f813  jz      short loc_14006F81F
0x14006f815  call    PnlFreeToLookasideList
0x14006f81a  jmp     loc_14006F5C4
0x14006f81f  mov     r8d, [rdi]
0x14006f822  call    PplFreeToLookasideListProcessor
0x14006f827  jmp     loc_14006F5C4
0x14006f82c  lea     rdx, [rdi+40h]
0x14006f830  call    PplpLazyInitializeLookasideList
0x14006f835  jmp     loc_14006F6C2
0x14006f83a  lea     rdx, [rbx+40h]
0x14006f83e  call    PplpLazyInitializeLookasideList
0x14006f843  jmp     loc_14006F646
0x14006f848  mov     edx, 0Ah
0x14006f84d  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14006f854  mov     ecx, 411h
0x14006f859  mov     r9, rdi
0x14006f85c  call    WPP_SF_q
0x14006f861  jmp     loc_14006F564
0x14006f866  xor     edx, edx; Val
0x14006f868  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f86d  mov     r8d, 60h ; '`'; Size
0x14006f873  call    memset
0x14006f878  mov     eax, cs:dword_1401A0628
0x14006f87e  lea     rdx, [rsp+0C8h+var_98]
0x14006f883  mov     [rsp+0C8h+var_70], eax
0x14006f887  mov     rcx, rdi
0x14006f88a  mov     rax, cs:off_1401A0638
0x14006f891  call    _guard_dispatch_icall
0x14006f896  jmp     loc_14006F5C4
0x14006f89b  xor     edx, edx; Val
0x14006f89d  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f8a2  mov     r8d, 60h ; '`'; Size
0x14006f8a8  call    memset
0x14006f8ad  mov     eax, cs:dword_1401A0658
0x14006f8b3  lea     rdx, [rsp+0C8h+var_98]
0x14006f8b8  mov     [rsp+0C8h+var_70], eax
0x14006f8bc  mov     rcx, rdi
0x14006f8bf  mov     rax, cs:off_1401A0668
0x14006f8c6  call    _guard_dispatch_icall
0x14006f8cb  jmp     loc_14006F5C4
0x14006f8d0  xor     edx, edx; Val
0x14006f8d2  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f8d7  mov     r8d, 60h ; '`'; Size
0x14006f8dd  call    memset
0x14006f8e2  mov     eax, cs:dword_1401A0688
0x14006f8e8  lea     rdx, [rsp+0C8h+var_98]
0x14006f8ed  mov     [rsp+0C8h+var_70], eax
0x14006f8f1  mov     rcx, rdi
0x14006f8f4  mov     rax, cs:off_1401A0698
0x14006f8fb  call    _guard_dispatch_icall
0x14006f900  jmp     loc_14006F5C4
0x14006f905  cmp     eax, 3
0x14006f908  jz      loc_14006F7F5
0x14006f90e  xor     edx, edx; Tag
0x14006f910  mov     rcx, rdi; P
0x14006f913  call    cs:__imp_ExFreePoolWithTag
0x14006f91a  nop     dword ptr [rax+rax+00h]
0x14006f91f  jmp     loc_14006F5C4
0x14006f924  xor     edx, edx; Val
0x14006f926  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f92b  mov     r8d, 60h ; '`'; Size
0x14006f931  call    memset
0x14006f936  mov     eax, cs:dword_1401A06B8
0x14006f93c  lea     rdx, [rsp+0C8h+var_98]
0x14006f941  mov     [rsp+0C8h+var_70], eax
0x14006f945  mov     rcx, rdi
0x14006f948  mov     rax, cs:off_1401A06C8
0x14006f94f  call    _guard_dispatch_icall
0x14006f954  jmp     loc_14006F5C4
0x14006f959  mov     edx, 0Bh
0x14006f95e  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14006f965  mov     ecx, 411h
0x14006f96a  call    WPP_SF_
0x14006f96f  jmp     loc_14006F5D1
0x14006f974  xor     edx, edx; Val
0x14006f976  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f97b  mov     r8d, 60h ; '`'; Size
0x14006f981  call    memset
0x14006f986  mov     eax, cs:dword_1401A06E8
0x14006f98c  lea     rdx, [rsp+0C8h+var_98]
0x14006f991  mov     [rsp+0C8h+var_70], eax
0x14006f995  mov     rcx, rbx
0x14006f998  mov     rax, cs:off_1401A06F8
0x14006f99f  call    _guard_dispatch_icall
0x14006f9a4  jmp     loc_14006F5F3
0x14006f9a9  mov     edx, 0C2h
0x14006f9ae  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x14006f9b5  mov     ecx, 411h
0x14006f9ba  call    WPP_SF_
0x14006f9bf  jmp     loc_14006F600
0x14006f9c4  xor     edx, edx; Val
0x14006f9c6  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f9cb  mov     r8d, 60h ; '`'; Size
0x14006f9d1  call    memset
0x14006f9d6  mov     eax, cs:dword_1401A0718
0x14006f9dc  lea     rdx, [rsp+0C8h+var_98]
0x14006f9e1  mov     [rsp+0C8h+var_70], eax
0x14006f9e5  mov     rcx, rsi
0x14006f9e8  mov     rax, cs:off_1401A0728
0x14006f9ef  call    _guard_dispatch_icall
0x14006f9f4  jmp     loc_14006F659
```
