# UxSslReleaseReceiveBuffers

- ea: `0x14006e530`
- end: `0x14006eadf`
- name: `UxSslReleaseReceiveBuffers`
- size: `1455`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a350`
- `0x140049d08`
- `0x14005dfd0`
- `0x14006e4ec`
- `0x14006e530`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e635`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e6cc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e757`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e635`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e6cc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006e757`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e803`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e82a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e803`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e82a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e9de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e9de`

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
0x14006e530  push    rbx
0x14006e532  push    rbp
0x14006e533  push    rdi
0x14006e534  push    r14
0x14006e536  sub     rsp, 0A8h
0x14006e53d  mov     rax, cs:__security_cookie
0x14006e544  xor     rax, rsp
0x14006e547  mov     [rsp+0C8h+var_38], rax
0x14006e54f  mov     r14, rdx
0x14006e552  mov     rbp, rcx
0x14006e555  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e55c  jnz     loc_14006E8F0
0x14006e562  mov     rbx, [r14+20h]
0x14006e566  mov     edi, 0FFFFFFFFh
0x14006e56b  mov     eax, edi
0x14006e56d  lea     rdx, [rbx+14h]; BugCheckParameter2
0x14006e571  lock xadd [rdx], eax
0x14006e575  dec     eax
0x14006e577  cmp     cs:UxDebugCheckRefcount, 0
0x14006e57e  jnz     loc_14006E7C3
0x14006e584  mov     [rsp+0C8h+arg_10], rsi
0x14006e58c  mov     [rsp+0C8h+var_28], r15
0x14006e594  xor     r15d, r15d
0x14006e597  test    eax, eax
0x14006e599  jnz     loc_14006E67D
0x14006e59f  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e5a6  jnz     loc_14006E864
0x14006e5ac  mov     rsi, [rbx+28h]
0x14006e5b0  test    rsi, rsi
0x14006e5b3  jz      loc_14006E652
0x14006e5b9  lea     rdx, [rsi+14h]; BugCheckParameter2
0x14006e5bd  lock xadd [rdx], edi
0x14006e5c1  dec     edi
0x14006e5c3  cmp     cs:UxDebugCheckRefcount, r15b
0x14006e5ca  jnz     loc_14006E7DF
0x14006e5d0  test    edi, edi
0x14006e5d2  jnz     short loc_14006E64E
0x14006e5d4  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e5db  jnz     loc_14006E913
0x14006e5e1  mov     eax, [rsi+78h]
0x14006e5e4  mov     dword ptr [rsi+10h], 6C735875h
0x14006e5eb  test    eax, eax
0x14006e5ed  jnz     loc_14006E768
0x14006e5f3  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e5fa  jnz     loc_14006E931
0x14006e600  cmp     cs:UxCompactMode, r15b
0x14006e607  jnz     loc_14006E823
0x14006e60d  mov     edi, [rsi]
0x14006e60f  mov     rcx, cs:qword_1401A0610
0x14006e616  inc     edi
0x14006e618  shl     rdi, 7
0x14006e61c  add     rdi, rcx
0x14006e61f  movzx   eax, byte ptr [rdi+0B0h]
0x14006e626  test    al, al
0x14006e628  jz      loc_14006E7B5
0x14006e62e  mov     rdx, rsi; Entry
0x14006e631  lea     rcx, [rdi+40h]; Lookaside
0x14006e635  call    cs:__imp_ExFreeToLookasideListEx
0x14006e63c  nop     dword ptr [rax+rax+00h]
0x14006e641  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e648  jnz     loc_14006EA24
0x14006e64e  mov     [rbx+28h], r15
0x14006e652  lea     rax, [rbp+730h]
0x14006e659  mov     dword ptr [rbx+10h], 64735875h
0x14006e660  cmp     rbx, rax
0x14006e663  jnz     loc_14006E715
0x14006e669  mov     [rbp+5D8h], rbx
0x14006e670  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e677  jnz     loc_14006EA74
0x14006e67d  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e684  mov     [r14+20h], r15
0x14006e688  mov     dword ptr [r14+10h], 69624C75h
0x14006e690  jnz     loc_14006EA8F
0x14006e696  cmp     cs:UxCompactMode, r15b
0x14006e69d  jnz     loc_14006E7FC
0x14006e6a3  mov     ebx, [r14]
0x14006e6a6  mov     rcx, cs:qword_1401A0700
0x14006e6ad  inc     ebx
0x14006e6af  shl     rbx, 7
0x14006e6b3  add     rbx, rcx
0x14006e6b6  movzx   eax, byte ptr [rbx+0B0h]
0x14006e6bd  test    al, al
0x14006e6bf  jz      loc_14006E8E2
0x14006e6c5  mov     rdx, r14; Entry
0x14006e6c8  lea     rcx, [rbx+40h]; Lookaside
0x14006e6cc  call    cs:__imp_ExFreeToLookasideListEx
0x14006e6d3  nop     dword ptr [rax+rax+00h]
0x14006e6d8  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14006e6df  jnz     loc_14006EAC4
0x14006e6e5  mov     rsi, [rsp+0C8h+arg_10]
0x14006e6ed  xor     eax, eax
0x14006e6ef  mov     r15, [rsp+0C8h+var_28]
0x14006e6f7  mov     rcx, [rsp+0C8h+var_38]
0x14006e6ff  xor     rcx, rsp; StackCookie
0x14006e702  call    __security_check_cookie
0x14006e707  add     rsp, 0A8h
0x14006e70e  pop     r14
0x14006e710  pop     rdi
0x14006e711  pop     rbp
0x14006e712  pop     rbx
0x14006e713  retn
0x14006e715  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e71c  jnz     loc_14006EA3F
0x14006e722  cmp     cs:UxCompactMode, r15b
0x14006e729  mov     rcx, cs:qword_1401A06D0
0x14006e730  jnz     loc_14006E84A
0x14006e736  mov     edi, [rbx]
0x14006e738  inc     edi
0x14006e73a  shl     rdi, 7
0x14006e73e  add     rdi, rcx
0x14006e741  movzx   eax, byte ptr [rdi+0B0h]
0x14006e748  test    al, al
0x14006e74a  jz      loc_14006E8D4
0x14006e750  mov     rdx, rbx; Entry
0x14006e753  lea     rcx, [rdi+40h]; Lookaside
0x14006e757  call    cs:__imp_ExFreeToLookasideListEx
0x14006e75e  nop     dword ptr [rax+rax+00h]
0x14006e763  jmp     loc_14006E670
0x14006e768  cmp     eax, 1
0x14006e76b  jz      loc_14006E887
0x14006e771  cmp     eax, 2
0x14006e774  jnz     loc_14006E9D0
0x14006e77a  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e781  jnz     loc_14006E99B
0x14006e787  cmp     cs:UxCompactMode, r15b
0x14006e78e  mov     rcx, cs:qword_1401A0670
0x14006e795  jnz     loc_14006E857
0x14006e79b  mov     edi, [rsi]
0x14006e79d  inc     edi
0x14006e79f  shl     rdi, 7
0x14006e7a3  add     rdi, rcx
0x14006e7a6  movzx   eax, byte ptr [rdi+0B0h]
0x14006e7ad  test    al, al
0x14006e7af  jnz     loc_14006E62E
0x14006e7b5  lea     rdx, [rdi+40h]
0x14006e7b9  call    PplpLazyInitializeLookasideList
0x14006e7be  jmp     loc_14006E62E
0x14006e7c3  cmp     eax, edi
0x14006e7c5  jg      loc_14006E584
0x14006e7cb  movsxd  r9, eax; BugCheckParameter4
0x14006e7ce  mov     ecx, 3; BugCheckParameter1
0x14006e7d3  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x14006e7d9  call    UlBugCheckEx
0x14006e7df  cmp     edi, 0FFFFFFFFh
0x14006e7e2  jg      loc_14006E5D0
0x14006e7e8  movsxd  r9, edi; BugCheckParameter4
0x14006e7eb  mov     ecx, 3; BugCheckParameter1
0x14006e7f0  mov     r8d, 46h ; 'F'; BugCheckParameter3
0x14006e7f6  call    UlBugCheckEx
0x14006e7fc  mov     rbx, cs:qword_1401A0700
0x14006e803  call    cs:__imp_KeGetCurrentNodeNumber
0x14006e80a  nop     dword ptr [rax+rax+00h]
0x14006e80f  movzx   r8d, ax
0x14006e813  mov     rdx, r14
0x14006e816  mov     rcx, rbx
0x14006e819  call    PplFreeToLookasideListProcessor
0x14006e81e  jmp     loc_14006E6D8
0x14006e823  mov     rdi, cs:qword_1401A0610
0x14006e82a  call    cs:__imp_KeGetCurrentNodeNumber
0x14006e831  nop     dword ptr [rax+rax+00h]
0x14006e836  movzx   r8d, ax
0x14006e83a  mov     rdx, rsi
0x14006e83d  mov     rcx, rdi
0x14006e840  call    PplFreeToLookasideListProcessor
0x14006e845  jmp     loc_14006E641
0x14006e84a  mov     rdx, rbx
0x14006e84d  call    PnlFreeToLookasideList
0x14006e852  jmp     loc_14006E670
0x14006e857  mov     rdx, rsi
0x14006e85a  call    PnlFreeToLookasideList
0x14006e85f  jmp     loc_14006E641
0x14006e864  mov     edx, 0C1h
0x14006e869  mov     [rsp+0C8h+var_A8], rbx
0x14006e86e  mov     ecx, 411h
0x14006e873  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x14006e87a  mov     r9, rbp
0x14006e87d  call    WPP_SF_qq
0x14006e882  jmp     loc_14006E5AC
0x14006e887  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e88e  jnz     loc_14006E966
0x14006e894  mov     rcx, cs:qword_1401A0640
0x14006e89b  jmp     short loc_14006E8B1
0x14006e89d  cmp     cs:UxDebugDisableLookaside, r15b
0x14006e8a4  jnz     loc_14006E9EF
0x14006e8aa  mov     rcx, cs:qword_1401A06A0
0x14006e8b1  cmp     cs:UxCompactMode, r15b
0x14006e8b8  mov     rdx, rsi
0x14006e8bb  jz      short loc_14006E8C7
0x14006e8bd  call    PnlFreeToLookasideList
0x14006e8c2  jmp     loc_14006E641
0x14006e8c7  mov     r8d, [rsi]
0x14006e8ca  call    PplFreeToLookasideListProcessor
0x14006e8cf  jmp     loc_14006E641
0x14006e8d4  lea     rdx, [rdi+40h]
0x14006e8d8  call    PplpLazyInitializeLookasideList
0x14006e8dd  jmp     loc_14006E750
0x14006e8e2  lea     rdx, [rbx+40h]
0x14006e8e6  call    PplpLazyInitializeLookasideList
0x14006e8eb  jmp     loc_14006E6C5
0x14006e8f0  mov     edx, 36h ; '6'
0x14006e8f5  mov     [rsp+0C8h+var_A8], r14
0x14006e8fa  mov     ecx, 411h
0x14006e8ff  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x14006e906  mov     r9, rbp
0x14006e909  call    WPP_SF_qq
0x14006e90e  jmp     loc_14006E562
0x14006e913  mov     edx, 0Ah
0x14006e918  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14006e91f  mov     ecx, 411h
0x14006e924  mov     r9, rsi
0x14006e927  call    WPP_SF_q
0x14006e92c  jmp     loc_14006E5E1
0x14006e931  xor     edx, edx; Val
0x14006e933  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006e938  mov     r8d, 60h ; '`'; Size
0x14006e93e  call    memset
0x14006e943  mov     eax, cs:dword_1401A0628
0x14006e949  lea     rdx, [rsp+0C8h+var_98]
0x14006e94e  mov     [rsp+0C8h+var_70], eax
0x14006e952  mov     rcx, rsi
0x14006e955  mov     rax, cs:off_1401A0638
0x14006e95c  call    _guard_dispatch_icall
0x14006e961  jmp     loc_14006E641
0x14006e966  xor     edx, edx; Val
0x14006e968  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006e96d  mov     r8d, 60h ; '`'; Size
0x14006e973  call    memset
0x14006e978  mov     eax, cs:dword_1401A0658
0x14006e97e  lea     rdx, [rsp+0C8h+var_98]
0x14006e983  mov     [rsp+0C8h+var_70], eax
0x14006e987  mov     rcx, rsi
0x14006e98a  mov     rax, cs:off_1401A0668
0x14006e991  call    _guard_dispatch_icall
0x14006e996  jmp     loc_14006E641
0x14006e99b  xor     edx, edx; Val
0x14006e99d  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006e9a2  mov     r8d, 60h ; '`'; Size
0x14006e9a8  call    memset
0x14006e9ad  mov     eax, cs:dword_1401A0688
0x14006e9b3  lea     rdx, [rsp+0C8h+var_98]
0x14006e9b8  mov     [rsp+0C8h+var_70], eax
0x14006e9bc  mov     rcx, rsi
0x14006e9bf  mov     rax, cs:off_1401A0698
0x14006e9c6  call    _guard_dispatch_icall
0x14006e9cb  jmp     loc_14006E641
0x14006e9d0  cmp     eax, 3
0x14006e9d3  jz      loc_14006E89D
0x14006e9d9  xor     edx, edx; Tag
0x14006e9db  mov     rcx, rsi; P
0x14006e9de  call    cs:__imp_ExFreePoolWithTag
0x14006e9e5  nop     dword ptr [rax+rax+00h]
0x14006e9ea  jmp     loc_14006E641
0x14006e9ef  xor     edx, edx; Val
0x14006e9f1  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006e9f6  mov     r8d, 60h ; '`'; Size
0x14006e9fc  call    memset
0x14006ea01  mov     eax, cs:dword_1401A06B8
0x14006ea07  lea     rdx, [rsp+0C8h+var_98]
0x14006ea0c  mov     [rsp+0C8h+var_70], eax
0x14006ea10  mov     rcx, rsi
0x14006ea13  mov     rax, cs:off_1401A06C8
0x14006ea1a  call    _guard_dispatch_icall
0x14006ea1f  jmp     loc_14006E641
0x14006ea24  mov     edx, 0Bh
0x14006ea29  lea     r8, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids
0x14006ea30  mov     ecx, 411h
0x14006ea35  call    WPP_SF_
0x14006ea3a  jmp     loc_14006E64E
0x14006ea3f  xor     edx, edx; Val
0x14006ea41  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006ea46  mov     r8d, 60h ; '`'; Size
0x14006ea4c  call    memset
0x14006ea51  mov     eax, cs:dword_1401A06E8
0x14006ea57  lea     rdx, [rsp+0C8h+var_98]
0x14006ea5c  mov     [rsp+0C8h+var_70], eax
0x14006ea60  mov     rcx, rbx
0x14006ea63  mov     rax, cs:off_1401A06F8
0x14006ea6a  call    _guard_dispatch_icall
0x14006ea6f  jmp     loc_14006E670
0x14006ea74  mov     edx, 0C2h
0x14006ea79  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x14006ea80  mov     ecx, 411h
0x14006ea85  call    WPP_SF_
0x14006ea8a  jmp     loc_14006E67D
0x14006ea8f  xor     edx, edx; Val
0x14006ea91  lea     rcx, [rsp+0C8h+var_98]; void *
0x14006ea96  mov     r8d, 60h ; '`'; Size
0x14006ea9c  call    memset
0x14006eaa1  mov     eax, cs:dword_1401A0718
0x14006eaa7  lea     rdx, [rsp+0C8h+var_98]
0x14006eaac  mov     [rsp+0C8h+var_70], eax
0x14006eab0  mov     rcx, r14
0x14006eab3  mov     rax, cs:off_1401A0728
0x14006eaba  call    _guard_dispatch_icall
0x14006eabf  jmp     loc_14006E6D8
0x14006eac4  mov     edx, 37h ; '7'
0x14006eac9  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x14006ead0  mov     ecx, 411h
0x14006ead5  call    WPP_SF_
0x14006eada  jmp     loc_14006E6E5
  ... truncated ...
```
