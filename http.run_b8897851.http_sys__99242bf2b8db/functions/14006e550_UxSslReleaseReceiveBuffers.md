# UxSslReleaseReceiveBuffers

- ea: `0x14006e550`
- end: `0x14006eaff`
- name: `UxSslReleaseReceiveBuffers`
- size: `1455`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a350`
- `0x140049d28`
- `0x14005dff0`
- `0x14006e50c`
- `0x14006e550`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e655`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e6ec`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e777`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e655`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e6ec`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e777`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e823`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e84a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e823`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e84a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e9fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e9fe`

## pseudocode

```c
__int64 __fastcall UxSslReleaseReceiveBuffers(__int64 a1, _QWORD *a2)
{
  volatile signed __int32 *v4; // rbx
  int v5; // eax
  volatile signed __int32 *v6; // rsi
  int v7; // edi
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  bool v11; // zf
  unsigned __int64 v12; // rbx
  unsigned __int64 v14; // rdi
  __int64 v15; // rbx
  USHORT v16; // ax
  __int64 v17; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v19; // rcx
  _DWORD v20[24]; // [rsp+30h] [rbp-98h] BYREF

  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qq(1041, 54, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, a1, a2);
  v4 = (volatile signed __int32 *)a2[4];
  v5 = _InterlockedDecrement(v4 + 5);
  if ( UxDebugCheckRefcount && v5 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v4 + 5), 0x46u, v5);
  if ( !v5 )
  {
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qq(1041, 193, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, v4);
    v6 = (volatile signed __int32 *)*((_QWORD *)v4 + 5);
    if ( !v6 )
      goto LABEL_20;
    v7 = _InterlockedDecrement(v6 + 5);
    if ( UxDebugCheckRefcount && v7 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v6 + 5), 0x46u, v7);
    if ( v7 )
    {
LABEL_19:
      *((_QWORD *)v4 + 5) = 0;
LABEL_20:
      *((_DWORD *)v4 + 4) = 1685280885;
      if ( v4 == (volatile signed __int32 *)(a1 + 1840) )
      {
        *(_QWORD *)(a1 + 1496) = v4;
      }
      else if ( UxDebugDisableLookaside )
      {
        memset(v20, 0, sizeof(v20));
        v20[10] = dword_1401A06E8;
        ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A06F8)(v4, v20);
      }
      else if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A06D0, v4);
      }
      else
      {
        v14 = qword_1401A06D0 + ((unsigned __int64)(unsigned int)(*v4 + 1) << 7);
        if ( !*(_BYTE *)(v14 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A06D0, v14 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 64), (PVOID)v4);
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 194, WPP_6033a49e77e7395416619077875677ff_Traceguids);
      goto LABEL_24;
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v6);
    v8 = *((_DWORD *)v6 + 30);
    *((_DWORD *)v6 + 4) = 1819498613;
    switch ( v8 )
    {
      case 0u:
        if ( UxDebugDisableLookaside )
        {
          memset(v20, 0, sizeof(v20));
          v20[10] = dword_1401A0628;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0638)(v6, v20);
        }
        else
        {
          if ( !UxCompactMode )
          {
            v9 = qword_1401A0610;
            v10 = qword_1401A0610 + ((unsigned __int64)(unsigned int)(*v6 + 1) << 7);
            if ( *(_BYTE *)(v10 + 176) )
            {
LABEL_16:
              ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 64), (PVOID)v6);
              goto LABEL_17;
            }
LABEL_42:
            PplpLazyInitializeLookasideList(v9, v10 + 64);
            goto LABEL_16;
          }
          v17 = qword_1401A0610;
          CurrentNodeNumber = KeGetCurrentNodeNumber();
          PplFreeToLookasideListProcessor(v17, v6, CurrentNodeNumber);
        }
        goto LABEL_17;
      case 1u:
        if ( UxDebugDisableLookaside )
        {
          memset(v20, 0, sizeof(v20));
          v20[10] = dword_1401A0658;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0668)(v6, v20);
          goto LABEL_17;
        }
        v19 = qword_1401A0640;
        break;
      case 2u:
        if ( UxDebugDisableLookaside )
        {
          memset(v20, 0, sizeof(v20));
          v20[10] = dword_1401A0688;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0698)(v6, v20);
        }
        else
        {
          v9 = qword_1401A0670;
          if ( !UxCompactMode )
          {
            v10 = qword_1401A0670 + ((unsigned __int64)(unsigned int)(*v6 + 1) << 7);
            if ( *(_BYTE *)(v10 + 176) )
              goto LABEL_16;
            goto LABEL_42;
          }
          PnlFreeToLookasideList(qword_1401A0670, v6);
        }
LABEL_17:
        if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
          WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
        goto LABEL_19;
      case 3u:
        if ( UxDebugDisableLookaside )
        {
          memset(v20, 0, sizeof(v20));
          v20[10] = dword_1401A06B8;
          ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A06C8)(v6, v20);
          goto LABEL_17;
        }
        v19 = qword_1401A06A0;
        break;
      default:
        ExFreePoolWithTag((PVOID)v6, 0);
        goto LABEL_17;
    }
    if ( UxCompactMode )
      PnlFreeToLookasideList(v19, v6);
    else
      PplFreeToLookasideListProcessor(v19, v6, *(unsigned int *)v6);
    goto LABEL_17;
  }
LABEL_24:
  v11 = UxDebugDisableLookaside == 0;
  a2[4] = 0;
  *((_DWORD *)a2 + 4) = 1768049781;
  if ( v11 )
  {
    if ( UxCompactMode )
    {
      v15 = qword_1401A0700;
      v16 = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v15, a2, v16);
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
    memset(v20, 0, sizeof(v20));
    v20[10] = dword_1401A0718;
    ((void (__fastcall *)(_QWORD *, _DWORD *))off_1401A0728)(a2, v20);
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1041, 55, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14006e550  push    rbx
0x14006e552  push    rbp
0x14006e553  push    rdi
0x14006e554  push    r14
0x14006e556  sub     rsp, 0A8h
0x14006e55d  mov     rax, cs:__security_cookie
0x14006e564  xor     rax, rsp
0x14006e567  mov     [rsp+0C8h+var_38], rax
0x14006e56f  mov     r14, rdx
0x14006e572  mov     rbp, rcx
0x14006e575  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e57c  jnz     loc_14006E910
0x14006e582  mov     rbx, [r14+20h]
0x14006e586  mov     edi, 0FFFFFFFFh
0x14006e58b  mov     eax, edi
0x14006e58d  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14006e591  lock xadd [rdx], eax
0x14006e595  dec     eax
0x14006e597  cmp     cs:UxDebugCheckRefcount, 0
0x14006e59e  jnz     loc_14006E7E3
0x14006e5a4  mov     [rsp+0C8h+arg_10], rsi
0x14006e5ac  mov     [rsp+0C8h+var_28], r15
0x14006e5b4  xor     r15d, r15d
0x14006e5b7  test    eax, eax
0x14006e5b9  jnz     loc_14006E69D
0x14006e5bf  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e5c6  jnz     loc_14006E884
0x14006e5cc  mov     rsi, [rbx+28h]
0x14006e5d0  test    rsi, rsi
0x14006e5d3  jz      loc_14006E672
0x14006e5d9  lea     rdx, [rsi+14h]; BugCheckParameter2
0x14006e5dd  lock xadd [rdx], edi
0x14006e5e1  dec     edi
0x14006e5e3  cmp     cs:UxDebugCheckRefcount, r15b
0x14006e5ea  jnz     loc_14006E7FF
0x14006e5f0  test    edi, edi
0x14006e5f2  jnz     short loc_14006E66E
0x14006e5f4  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e5fb  jnz     loc_14006E933
0x14006e601  mov     eax, [rsi+78h]
0x14006e604  mov     dword ptr [rsi+10h], 6C735875h
0x14006e60b  test    eax, eax
0x14006e60d  jnz     loc_14006E788
0x14006e613  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e61a  jnz     loc_14006E951
0x14006e620  cmp     cs:UxCompactMode, r15b
0x14006e627  jnz     loc_14006E843
0x14006e62d  mov     edi, [rsi]
0x14006e62f  mov     rcx, cs:qword_1401A0610
0x14006e636  inc     edi
0x14006e638  shl     rdi, 7
0x14006e63c  add     rdi, rcx
0x14006e63f  movzx   eax, byte ptr [rdi+0B0h]
0x14006e646  test    al, al
0x14006e648  jz      loc_14006E7D5
0x14006e64e  mov     rdx, rsi; Entry
0x14006e651  lea     rcx, [rdi+40h]; Lookaside
0x14006e655  call    cs:__imp_ExFreeToLookasideListEx
0x14006e65c  nop     dword ptr [rax+rax+00h]
0x14006e661  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e668  jnz     loc_14006EA44
0x14006e66e  mov     [rbx+28h], r15
0x14006e672  lea     rax, [rbp+730h]
0x14006e679  mov     dword ptr [rbx+10h], 64735875h
0x14006e680  cmp     rbx, rax
0x14006e683  jnz     loc_14006E735
0x14006e689  mov     [rbp+5D8h], rbx
0x14006e690  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e697  jnz     loc_14006EA94
0x14006e69d  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e6a4  mov     [r14+20h], r15
0x14006e6a8  mov     dword ptr [r14+10h], 69624C75h
0x14006e6b0  jnz     loc_14006EAAF
0x14006e6b6  cmp     cs:UxCompactMode, r15b
0x14006e6bd  jnz     loc_14006E81C
0x14006e6c3  mov     ebx, [r14]
0x14006e6c6  mov     rcx, cs:qword_1401A0700
0x14006e6cd  inc     ebx
0x14006e6cf  shl     rbx, 7
0x14006e6d3  add     rbx, rcx
0x14006e6d6  movzx   eax, byte ptr [rbx+0B0h]
0x14006e6dd  test    al, al
0x14006e6df  jz      loc_14006E902
0x14006e6e5  mov     rdx, r14; Entry
0x14006e6e8  lea     rcx, [rbx+40h]; Lookaside
0x14006e6ec  call    cs:__imp_ExFreeToLookasideListEx
0x14006e6f3  nop     dword ptr [rax+rax+00h]
0x14006e6f8  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e6ff  jnz     loc_14006EAE4
0x14006e705  mov     rsi, [rsp+0C8h+arg_10]
0x14006e70d  xor     eax, eax
0x14006e70f  mov     r15, [rsp+0C8h+var_28]
0x14006e717  mov     rcx, [rsp+0C8h+var_38]
0x14006e71f  xor     rcx, rsp; StackCookie
0x14006e722  call    __security_check_cookie
0x14006e727  add     rsp, 0A8h
0x14006e72e  pop     r14
0x14006e730  pop     rdi
0x14006e731  pop     rbp
0x14006e732  pop     rbx
0x14006e733  retn
0x14006e735  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e73c  jnz     loc_14006EA5F
0x14006e742  cmp     cs:UxCompactMode, r15b
0x14006e749  mov     rcx, cs:qword_1401A06D0
0x14006e750  jnz     loc_14006E86A
0x14006e756  mov     edi, [rbx]
0x14006e758  inc     edi
0x14006e75a  shl     rdi, 7
0x14006e75e  add     rdi, rcx
0x14006e761  movzx   eax, byte ptr [rdi+0B0h]
0x14006e768  test    al, al
0x14006e76a  jz      loc_14006E8F4
0x14006e770  mov     rdx, rbx; Entry
0x14006e773  lea     rcx, [rdi+40h]; Lookaside
0x14006e777  call    cs:__imp_ExFreeToLookasideListEx
0x14006e77e  nop     dword ptr [rax+rax+00h]
0x14006e783  jmp     loc_14006E690
0x14006e788  cmp     eax, 1
0x14006e78b  jz      loc_14006E8A7
0x14006e791  cmp     eax, 2
0x14006e794  jnz     loc_14006E9F0
0x14006e79a  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e7a1  jnz     loc_14006E9BB
0x14006e7a7  cmp     cs:UxCompactMode, r15b
0x14006e7ae  mov     rcx, cs:qword_1401A0670
0x14006e7b5  jnz     loc_14006E877
0x14006e7bb  mov     edi, [rsi]
0x14006e7bd  inc     edi
0x14006e7bf  shl     rdi, 7
0x14006e7c3  add     rdi, rcx
0x14006e7c6  movzx   eax, byte ptr [rdi+0B0h]
0x14006e7cd  test    al, al
0x14006e7cf  jnz     loc_14006E64E
0x14006e7d5  lea     rdx, [rdi+40h]
0x14006e7d9  call    PplpLazyInitializeLookasideList
0x14006e7de  jmp     loc_14006E64E
0x14006e7e3  cmp     eax, edi
0x14006e7e5  jg      loc_14006E5A4
0x14006e7eb  movsxd  r9, eax; BugCheckParameter4
0x14006e7ee  mov     ecx, 3; BugCheckParameter1
0x14006e7f3  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x14006e7f9  call    UlBugCheckEx
0x14006e7ff  cmp     edi, 0FFFFFFFFh
0x14006e802  jg      loc_14006E5F0
0x14006e808  movsxd  r9, edi; BugCheckParameter4
0x14006e80b  mov     ecx, 3; BugCheckParameter1
0x14006e810  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x14006e816  call    UlBugCheckEx
0x14006e81c  mov     rbx, cs:qword_1401A0700
0x14006e823  call    cs:__imp_KeGetCurrentNodeNumber
0x14006e82a  nop     dword ptr [rax+rax+00h]
0x14006e82f  movzx   r8d, ax
0x14006e833  mov     rdx, r14
0x14006e836  mov     rcx, rbx
0x14006e839  call    PplFreeToLookasideListProcessor
0x14006e83e  jmp     loc_14006E6F8
0x14006e843  mov     rdi, cs:qword_1401A0610
0x14006e84a  call    cs:__imp_KeGetCurrentNodeNumber
0x14006e851  nop     dword ptr [rax+rax+00h]
0x14006e856  movzx   r8d, ax
0x14006e85a  mov     rdx, rsi
0x14006e85d  mov     rcx, rdi
0x14006e860  call    PplFreeToLookasideListProcessor
0x14006e865  jmp     loc_14006E661
0x14006e86a  mov     rdx, rbx
0x14006e86d  call    PnlFreeToLookasideList
0x14006e872  jmp     loc_14006E690
0x14006e877  mov     rdx, rsi
0x14006e87a  call    PnlFreeToLookasideList
0x14006e87f  jmp     loc_14006E661
0x14006e884  mov     edx, 0C1h
0x14006e889  mov     [rsp+0C8h+var_A8], rbx
0x14006e88e  mov     ecx, 411h
0x14006e893  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x14006e89a  mov     r9, rbp
0x14006e89d  call    WPP_SF_qq
0x14006e8a2  jmp     loc_14006E5CC
0x14006e8a7  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e8ae  jnz     loc_14006E986
0x14006e8b4  mov     rcx, cs:qword_1401A0640
0x14006e8bb  jmp     short loc_14006E8D1
0x14006e8bd  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e8c4  jnz     loc_14006EA0F
0x14006e8ca  mov     rcx, cs:qword_1401A06A0
0x14006e8d1  cmp     cs:UxCompactMode, r15b
0x14006e8d8  mov     rdx, rsi
0x14006e8db  jz      short loc_14006E8E7
0x14006e8dd  call    PnlFreeToLookasideList
0x14006e8e2  jmp     loc_14006E661
0x14006e8e7  mov     r8d, [rsi]
0x14006e8ea  call    PplFreeToLookasideListProcessor
0x14006e8ef  jmp     loc_14006E661
0x14006e8f4  lea     rdx, [rdi+40h]
0x14006e8f8  call    PplpLazyInitializeLookasideList
0x14006e8fd  jmp     loc_14006E770
0x14006e902  lea     rdx, [rbx+40h]
0x14006e906  call    PplpLazyInitializeLookasideList
0x14006e90b  jmp     loc_14006E6E5
0x14006e910  mov     edx, 36h ; '6'
0x14006e915  mov     [rsp+0C8h+var_A8], r14
0x14006e91a  mov     ecx, 411h
0x14006e91f  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x14006e926  mov     r9, rbp
0x14006e929  call    WPP_SF_qq
0x14006e92e  jmp     loc_14006E582
0x14006e933  mov     edx, 0Ah
0x14006e938  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14006e93f  mov     ecx, 411h
0x14006e944  mov     r9, rsi
0x14006e947  call    WPP_SF_q
0x14006e94c  jmp     loc_14006E601
0x14006e951  xor     edx, edx; Val
0x14006e953  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006e958  mov     r8d, 60h ; '`'; Size
0x14006e95e  call    memset
0x14006e963  mov     eax, cs:dword_1401A0628
0x14006e969  lea     rdx, [rsp+0C8h+var_98]
0x14006e96e  mov     [rsp+0C8h+var_70], eax
0x14006e972  mov     rcx, rsi
0x14006e975  mov     rax, cs:off_1401A0638
0x14006e97c  call    _guard_dispatch_icall
0x14006e981  jmp     loc_14006E661
0x14006e986  xor     edx, edx; Val
0x14006e988  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006e98d  mov     r8d, 60h ; '`'; Size
0x14006e993  call    memset
0x14006e998  mov     eax, cs:dword_1401A0658
0x14006e99e  lea     rdx, [rsp+0C8h+var_98]
0x14006e9a3  mov     [rsp+0C8h+var_70], eax
0x14006e9a7  mov     rcx, rsi
0x14006e9aa  mov     rax, cs:off_1401A0668
0x14006e9b1  call    _guard_dispatch_icall
0x14006e9b6  jmp     loc_14006E661
0x14006e9bb  xor     edx, edx; Val
0x14006e9bd  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006e9c2  mov     r8d, 60h ; '`'; Size
0x14006e9c8  call    memset
0x14006e9cd  mov     eax, cs:dword_1401A0688
0x14006e9d3  lea     rdx, [rsp+0C8h+var_98]
0x14006e9d8  mov     [rsp+0C8h+var_70], eax
0x14006e9dc  mov     rcx, rsi
0x14006e9df  mov     rax, cs:off_1401A0698
0x14006e9e6  call    _guard_dispatch_icall
0x14006e9eb  jmp     loc_14006E661
0x14006e9f0  cmp     eax, 3
0x14006e9f3  jz      loc_14006E8BD
0x14006e9f9  xor     edx, edx; Tag
0x14006e9fb  mov     rcx, rsi; P
0x14006e9fe  call    cs:__imp_ExFreePoolWithTag
0x14006ea05  nop     dword ptr [rax+rax+00h]
0x14006ea0a  jmp     loc_14006E661
0x14006ea0f  xor     edx, edx; Val
0x14006ea11  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006ea16  mov     r8d, 60h ; '`'; Size
0x14006ea1c  call    memset
0x14006ea21  mov     eax, cs:dword_1401A06B8
0x14006ea27  lea     rdx, [rsp+0C8h+var_98]
0x14006ea2c  mov     [rsp+0C8h+var_70], eax
0x14006ea30  mov     rcx, rsi
0x14006ea33  mov     rax, cs:off_1401A06C8
0x14006ea3a  call    _guard_dispatch_icall
0x14006ea3f  jmp     loc_14006E661
0x14006ea44  mov     edx, 0Bh
0x14006ea49  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14006ea50  mov     ecx, 411h
0x14006ea55  call    WPP_SF_
0x14006ea5a  jmp     loc_14006E66E
0x14006ea5f  xor     edx, edx; Val
0x14006ea61  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006ea66  mov     r8d, 60h ; '`'; Size
0x14006ea6c  call    memset
0x14006ea71  mov     eax, cs:dword_1401A06E8
0x14006ea77  lea     rdx, [rsp+0C8h+var_98]
0x14006ea7c  mov     [rsp+0C8h+var_70], eax
0x14006ea80  mov     rcx, rbx
0x14006ea83  mov     rax, cs:off_1401A06F8
0x14006ea8a  call    _guard_dispatch_icall
0x14006ea8f  jmp     loc_14006E690
0x14006ea94  mov     edx, 0C2h
0x14006ea99  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x14006eaa0  mov     ecx, 411h
0x14006eaa5  call    WPP_SF_
0x14006eaaa  jmp     loc_14006E69D
0x14006eaaf  xor     edx, edx; Val
0x14006eab1  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006eab6  mov     r8d, 60h ; '`'; Size
0x14006eabc  call    memset
0x14006eac1  mov     eax, cs:dword_1401A0718
0x14006eac7  lea     rdx, [rsp+0C8h+var_98]
0x14006eacc  mov     [rsp+0C8h+var_70], eax
0x14006ead0  mov     rcx, r14
0x14006ead3  mov     rax, cs:off_1401A0728
0x14006eada  call    _guard_dispatch_icall
0x14006eadf  jmp     loc_14006E6F8
0x14006eae4  mov     edx, 37h ; '7'
0x14006eae9  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x14006eaf0  mov     ecx, 411h
0x14006eaf5  call    WPP_SF_
0x14006eafa  jmp     loc_14006E705
  ... truncated ...
```
