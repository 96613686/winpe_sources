# UxSslFreeBufferIndication

- ea: `0x14006f4a0`
- end: `0x14006f9d9`
- name: `UxSslFreeBufferIndication`
- size: `1337`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140080660`

## callees

- `0x14000a350`
- `0x140049d08`
- `0x14005dfd0`
- `0x14006e4ec`
- `0x14006f4a0`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f598`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f62d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f6a9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f598`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f62d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006f6a9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006f755`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006f755`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f8f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f8f3`

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
0x14006f4a0  push    rbx
0x14006f4a2  push    rbp
0x14006f4a3  push    rsi
0x14006f4a4  push    r14
0x14006f4a6  sub     rsp, 0A8h
0x14006f4ad  mov     rax, cs:__security_cookie
0x14006f4b4  xor     rax, rsp
0x14006f4b7  mov     [rsp+0C8h+var_38], rax
0x14006f4bf  mov     rbx, [rdx+20h]
0x14006f4c3  mov     ebp, 0FFFFFFFFh
0x14006f4c8  mov     rsi, rdx
0x14006f4cb  mov     r14, rcx
0x14006f4ce  mov     eax, ebp
0x14006f4d0  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14006f4d4  lock xadd [rdx], eax
0x14006f4d8  dec     eax
0x14006f4da  cmp     cs:UxDebugCheckRefcount, 0
0x14006f4e1  jnz     loc_14006F715
0x14006f4e7  mov     [rsp+0C8h+arg_10], rdi
0x14006f4ef  mov     [rsp+0C8h+var_28], r15
0x14006f4f7  xor     r15d, r15d
0x14006f4fa  test    eax, eax
0x14006f4fc  jnz     loc_14006F5E0
0x14006f502  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006f509  jnz     loc_14006F79C
0x14006f50f  mov     rdi, [rbx+28h]
0x14006f513  test    rdi, rdi
0x14006f516  jz      loc_14006F5B5
0x14006f51c  lea     rdx, [rdi+14h]; BugCheckParameter2
0x14006f520  lock xadd [rdx], ebp
0x14006f524  dec     ebp
0x14006f526  cmp     cs:UxDebugCheckRefcount, r15b
0x14006f52d  jnz     loc_14006F731
0x14006f533  test    ebp, ebp
0x14006f535  jnz     short loc_14006F5B1
0x14006f537  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006f53e  jnz     loc_14006F828
0x14006f544  mov     eax, [rdi+78h]
0x14006f547  mov     dword ptr [rdi+10h], 6C735875h
0x14006f54e  test    eax, eax
0x14006f550  jnz     loc_14006F6BA
0x14006f556  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f55d  jnz     loc_14006F846
0x14006f563  cmp     cs:UxCompactMode, r15b
0x14006f56a  mov     rcx, cs:qword_1401A0610
0x14006f571  jnz     loc_14006F775
0x14006f577  mov     ebp, [rdi]
0x14006f579  inc     ebp
0x14006f57b  shl     rbp, 7
0x14006f57f  add     rbp, rcx
0x14006f582  movzx   eax, byte ptr [rbp+0B0h]
0x14006f589  test    al, al
0x14006f58b  jz      loc_14006F707
0x14006f591  mov     rdx, rdi; Entry
0x14006f594  lea     rcx, [rbp+40h]; Lookaside
0x14006f598  call    cs:__imp_ExFreeToLookasideListEx
0x14006f59f  nop     dword ptr [rax+rax+00h]
0x14006f5a4  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006f5ab  jnz     loc_14006F939
0x14006f5b1  mov     [rbx+28h], r15
0x14006f5b5  lea     rax, [r14+730h]
0x14006f5bc  mov     dword ptr [rbx+10h], 64735875h
0x14006f5c3  cmp     rbx, rax
0x14006f5c6  jnz     loc_14006F667
0x14006f5cc  mov     [r14+5D8h], rbx
0x14006f5d3  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006f5da  jnz     loc_14006F989
0x14006f5e0  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f5e7  mov     [rsi+20h], r15
0x14006f5eb  mov     dword ptr [rsi+10h], 69624C75h
0x14006f5f2  jnz     loc_14006F9A4
0x14006f5f8  cmp     cs:UxCompactMode, r15b
0x14006f5ff  jnz     loc_14006F74E
0x14006f605  mov     ebx, [rsi]
0x14006f607  mov     rcx, cs:qword_1401A0700
0x14006f60e  inc     ebx
0x14006f610  shl     rbx, 7
0x14006f614  add     rbx, rcx
0x14006f617  movzx   eax, byte ptr [rbx+0B0h]
0x14006f61e  test    al, al
0x14006f620  jz      loc_14006F81A
0x14006f626  mov     rdx, rsi; Entry
0x14006f629  lea     rcx, [rbx+40h]; Lookaside
0x14006f62d  call    cs:__imp_ExFreeToLookasideListEx
0x14006f634  nop     dword ptr [rax+rax+00h]
0x14006f639  mov     rdi, [rsp+0C8h+arg_10]
0x14006f641  mov     r15, [rsp+0C8h+var_28]
0x14006f649  mov     rcx, [rsp+0C8h+var_38]
0x14006f651  xor     rcx, rsp; StackCookie
0x14006f654  call    __security_check_cookie
0x14006f659  add     rsp, 0A8h
0x14006f660  pop     r14
0x14006f662  pop     rsi
0x14006f663  pop     rbp
0x14006f664  pop     rbx
0x14006f665  retn
0x14006f667  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f66e  jnz     loc_14006F954
0x14006f674  cmp     cs:UxCompactMode, r15b
0x14006f67b  mov     rcx, cs:qword_1401A06D0
0x14006f682  jnz     loc_14006F782
0x14006f688  mov     edi, [rbx]
0x14006f68a  inc     edi
0x14006f68c  shl     rdi, 7
0x14006f690  add     rdi, rcx
0x14006f693  movzx   eax, byte ptr [rdi+0B0h]
0x14006f69a  test    al, al
0x14006f69c  jz      loc_14006F80C
0x14006f6a2  mov     rdx, rbx; Entry
0x14006f6a5  lea     rcx, [rdi+40h]; Lookaside
0x14006f6a9  call    cs:__imp_ExFreeToLookasideListEx
0x14006f6b0  nop     dword ptr [rax+rax+00h]
0x14006f6b5  jmp     loc_14006F5D3
0x14006f6ba  cmp     eax, 1
0x14006f6bd  jz      loc_14006F7BF
0x14006f6c3  cmp     eax, 2
0x14006f6c6  jnz     loc_14006F8E5
0x14006f6cc  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f6d3  jnz     loc_14006F8B0
0x14006f6d9  cmp     cs:UxCompactMode, r15b
0x14006f6e0  mov     rcx, cs:qword_1401A0670
0x14006f6e7  jnz     loc_14006F78F
0x14006f6ed  mov     ebp, [rdi]
0x14006f6ef  inc     ebp
0x14006f6f1  shl     rbp, 7
0x14006f6f5  add     rbp, rcx
0x14006f6f8  movzx   eax, byte ptr [rbp+0B0h]
0x14006f6ff  test    al, al
0x14006f701  jnz     loc_14006F591
0x14006f707  lea     rdx, [rbp+40h]
0x14006f70b  call    PplpLazyInitializeLookasideList
0x14006f710  jmp     loc_14006F591
0x14006f715  cmp     eax, ebp
0x14006f717  jg      loc_14006F4E7
0x14006f71d  movsxd  r9, eax; BugCheckParameter4
0x14006f720  mov     ecx, 3; BugCheckParameter1
0x14006f725  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x14006f72b  call    UlBugCheckEx
0x14006f731  cmp     ebp, 0FFFFFFFFh
0x14006f734  jg      loc_14006F533
0x14006f73a  movsxd  r9, ebp; BugCheckParameter4
0x14006f73d  mov     ecx, 3; BugCheckParameter1
0x14006f742  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x14006f748  call    UlBugCheckEx
0x14006f74e  mov     rbx, cs:qword_1401A0700
0x14006f755  call    cs:__imp_KeGetCurrentNodeNumber
0x14006f75c  nop     dword ptr [rax+rax+00h]
0x14006f761  movzx   r8d, ax
0x14006f765  mov     rdx, rsi
0x14006f768  mov     rcx, rbx
0x14006f76b  call    PplFreeToLookasideListProcessor
0x14006f770  jmp     loc_14006F639
0x14006f775  mov     rdx, rdi
0x14006f778  call    PnlFreeToLookasideList
0x14006f77d  jmp     loc_14006F5A4
0x14006f782  mov     rdx, rbx
0x14006f785  call    PnlFreeToLookasideList
0x14006f78a  jmp     loc_14006F5D3
0x14006f78f  mov     rdx, rdi
0x14006f792  call    PnlFreeToLookasideList
0x14006f797  jmp     loc_14006F5A4
0x14006f79c  mov     edx, 0C1h
0x14006f7a1  mov     [rsp+0C8h+var_A8], rbx
0x14006f7a6  mov     ecx, 411h
0x14006f7ab  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x14006f7b2  mov     r9, r14
0x14006f7b5  call    WPP_SF_qq
0x14006f7ba  jmp     loc_14006F50F
0x14006f7bf  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f7c6  jnz     loc_14006F87B
0x14006f7cc  mov     rcx, cs:qword_1401A0640
0x14006f7d3  jmp     short loc_14006F7E9
0x14006f7d5  cmp     cs:UxDebugDisableLookaside, r15b
0x14006f7dc  jnz     loc_14006F904
0x14006f7e2  mov     rcx, cs:qword_1401A06A0
0x14006f7e9  cmp     cs:UxCompactMode, r15b
0x14006f7f0  mov     rdx, rdi
0x14006f7f3  jz      short loc_14006F7FF
0x14006f7f5  call    PnlFreeToLookasideList
0x14006f7fa  jmp     loc_14006F5A4
0x14006f7ff  mov     r8d, [rdi]
0x14006f802  call    PplFreeToLookasideListProcessor
0x14006f807  jmp     loc_14006F5A4
0x14006f80c  lea     rdx, [rdi+40h]
0x14006f810  call    PplpLazyInitializeLookasideList
0x14006f815  jmp     loc_14006F6A2
0x14006f81a  lea     rdx, [rbx+40h]
0x14006f81e  call    PplpLazyInitializeLookasideList
0x14006f823  jmp     loc_14006F626
0x14006f828  mov     edx, 0Ah
0x14006f82d  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14006f834  mov     ecx, 411h
0x14006f839  mov     r9, rdi
0x14006f83c  call    WPP_SF_q
0x14006f841  jmp     loc_14006F544
0x14006f846  xor     edx, edx; Val
0x14006f848  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f84d  mov     r8d, 60h ; '`'; Size
0x14006f853  call    memset
0x14006f858  mov     eax, cs:dword_1401A0628
0x14006f85e  lea     rdx, [rsp+0C8h+var_98]
0x14006f863  mov     [rsp+0C8h+var_70], eax
0x14006f867  mov     rcx, rdi
0x14006f86a  mov     rax, cs:off_1401A0638
0x14006f871  call    _guard_dispatch_icall
0x14006f876  jmp     loc_14006F5A4
0x14006f87b  xor     edx, edx; Val
0x14006f87d  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f882  mov     r8d, 60h ; '`'; Size
0x14006f888  call    memset
0x14006f88d  mov     eax, cs:dword_1401A0658
0x14006f893  lea     rdx, [rsp+0C8h+var_98]
0x14006f898  mov     [rsp+0C8h+var_70], eax
0x14006f89c  mov     rcx, rdi
0x14006f89f  mov     rax, cs:off_1401A0668
0x14006f8a6  call    _guard_dispatch_icall
0x14006f8ab  jmp     loc_14006F5A4
0x14006f8b0  xor     edx, edx; Val
0x14006f8b2  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f8b7  mov     r8d, 60h ; '`'; Size
0x14006f8bd  call    memset
0x14006f8c2  mov     eax, cs:dword_1401A0688
0x14006f8c8  lea     rdx, [rsp+0C8h+var_98]
0x14006f8cd  mov     [rsp+0C8h+var_70], eax
0x14006f8d1  mov     rcx, rdi
0x14006f8d4  mov     rax, cs:off_1401A0698
0x14006f8db  call    _guard_dispatch_icall
0x14006f8e0  jmp     loc_14006F5A4
0x14006f8e5  cmp     eax, 3
0x14006f8e8  jz      loc_14006F7D5
0x14006f8ee  xor     edx, edx; Tag
0x14006f8f0  mov     rcx, rdi; P
0x14006f8f3  call    cs:__imp_ExFreePoolWithTag
0x14006f8fa  nop     dword ptr [rax+rax+00h]
0x14006f8ff  jmp     loc_14006F5A4
0x14006f904  xor     edx, edx; Val
0x14006f906  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f90b  mov     r8d, 60h ; '`'; Size
0x14006f911  call    memset
0x14006f916  mov     eax, cs:dword_1401A06B8
0x14006f91c  lea     rdx, [rsp+0C8h+var_98]
0x14006f921  mov     [rsp+0C8h+var_70], eax
0x14006f925  mov     rcx, rdi
0x14006f928  mov     rax, cs:off_1401A06C8
0x14006f92f  call    _guard_dispatch_icall
0x14006f934  jmp     loc_14006F5A4
0x14006f939  mov     edx, 0Bh
0x14006f93e  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14006f945  mov     ecx, 411h
0x14006f94a  call    WPP_SF_
0x14006f94f  jmp     loc_14006F5B1
0x14006f954  xor     edx, edx; Val
0x14006f956  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f95b  mov     r8d, 60h ; '`'; Size
0x14006f961  call    memset
0x14006f966  mov     eax, cs:dword_1401A06E8
0x14006f96c  lea     rdx, [rsp+0C8h+var_98]
0x14006f971  mov     [rsp+0C8h+var_70], eax
0x14006f975  mov     rcx, rbx
0x14006f978  mov     rax, cs:off_1401A06F8
0x14006f97f  call    _guard_dispatch_icall
0x14006f984  jmp     loc_14006F5D3
0x14006f989  mov     edx, 0C2h
0x14006f98e  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x14006f995  mov     ecx, 411h
0x14006f99a  call    WPP_SF_
0x14006f99f  jmp     loc_14006F5E0
0x14006f9a4  xor     edx, edx; Val
0x14006f9a6  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006f9ab  mov     r8d, 60h ; '`'; Size
0x14006f9b1  call    memset
0x14006f9b6  mov     eax, cs:dword_1401A0718
0x14006f9bc  lea     rdx, [rsp+0C8h+var_98]
0x14006f9c1  mov     [rsp+0C8h+var_70], eax
0x14006f9c5  mov     rcx, rsi
0x14006f9c8  mov     rax, cs:off_1401A0728
0x14006f9cf  call    _guard_dispatch_icall
0x14006f9d4  jmp     loc_14006F639
```
