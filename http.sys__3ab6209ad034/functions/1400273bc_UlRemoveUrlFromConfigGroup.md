# UlRemoveUrlFromConfigGroup

- ea: `0x1400273bc`
- end: `0x14002783a`
- name: `UlRemoveUrlFromConfigGroup`
- size: `1150`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140016b40`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x1400262a4`
- `0x140026418`
- `0x140026530`
- `0x1400272c8`
- `0x1400273bc`
- `0x140027840`
- `0x140074ad8`
- `0x1400fdd3c`
- `0x1401506e8`
- `0x140167c40`
- `0x1401c3e00`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c8bcc`
- `0x1401c8c38`
- `0x1401c8cb0`
- `0x1401c9430`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140027551`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140027551`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14002749e`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14002749e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002755d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002755d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027628`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027628`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002748b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002748b`

## pseudocode

```c
__int64 __fastcall UlRemoveUrlFromConfigGroup(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, char a6, __int64 a7)
{
  int v11; // ecx
  int v12; // r8d
  char v13; // r13
  __int64 v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // r15
  int v17; // eax
  int v18; // ebx
  __int64 v19; // rbx
  int RegistrationNode; // eax
  _DWORD *ObjectFromOpaqueId; // rax
  _DWORD *v22; // rdi
  __int64 v24; // rcx
  int v25; // ecx
  int v26; // r8d
  int v27; // eax
  int v28; // eax
  __int64 v29[24]; // [rsp+50h] [rbp-81h] BYREF
  PVOID P; // [rsp+120h] [rbp+4Fh] BYREF
  PVOID v31; // [rsp+128h] [rbp+57h] BYREF
  __int64 v32; // [rsp+130h] [rbp+5Fh]

  v32 = a3;
  v31 = 0;
  P = 0;
  memset(v29, 0, 0x88u);
  v13 = a6;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqSqLl(v11, 108, v12, a1, a2, *(_QWORD *)(a3 + 8), a4, a5, a6);
  v14 = *(_QWORD *)(a2 + 8);
  if ( (BYTE8(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_Si(v11, 109, v12, *(_QWORD *)(a3 + 8), *(_QWORD *)(a2 + 8));
  v15 = *(_QWORD *)(a3 + 8);
  v16 = *(_QWORD *)(a1 + 56);
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqLqq(1028, 27, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v16, v15, 1, &P, v29);
  P = 0;
  v17 = HttpParseUrl(v16 + 4396, v15, 257, v29);
  v18 = v17;
  if ( v17 >= 0 )
    P = (PVOID)v29[1];
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qqD(1028, 28, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, P, v29, v17);
  if ( v18 >= 0 )
  {
    v19 = *(_QWORD *)(a1 + 56);
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v19 + 1368));
    if ( !*(_DWORD *)a2 )
    {
      v28 = UlpDeleteReservationEntry(*(_QWORD *)(a1 + 56), (unsigned int)v29, a4, a5, v13, 0);
      v18 = v28;
      if ( v28 < 0 && (xmmword_1401A2C90 & 0x10) != 0 )
        WPP_SF_Sd(516, 116, (unsigned int)WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v29[1], v28);
      goto LABEL_23;
    }
    if ( *(_DWORD *)a2 == 1 )
    {
      RegistrationNode = UlpTreeFindRegistrationNode(*(_QWORD *)(a1 + 56), P, &v31);
      v18 = RegistrationNode;
      if ( RegistrationNode < 0 )
      {
        if ( (xmmword_1401A2C90 & 0x10) != 0 )
          WPP_SF_d(516, 111, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)RegistrationNode);
        goto LABEL_23;
      }
      ObjectFromOpaqueId = (_DWORD *)UxGetObjectFromOpaqueId(
                                       v14,
                                       2,
                                       (unsigned int)UlReferenceServerSession,
                                       (unsigned int)UlValidateConfigGroup,
                                       a1);
      v22 = ObjectFromOpaqueId;
      if ( ObjectFromOpaqueId && *ObjectFromOpaqueId == 1245932629 )
      {
        if ( *((_DWORD **)v31 + 11) == ObjectFromOpaqueId )
        {
          v18 = UlpTreeDeleteRegistration(v31);
          UlEventLogRemoveUrl(v24, v14, v29, a7);
          if ( (xmmword_1401A2CA0 & 0x10) != 0 )
            WPP_SF_diS(v25, 114, v26, v18, v14, v29[1]);
          if ( v18 < 0 )
          {
            if ( (xmmword_1401A2C90 & 0x10) != 0 )
              WPP_SF_d(516, 115, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)v18);
          }
          else
          {
            UlFlushCacheForRemoveUrl(v29, v22);
            if ( *((_DWORD **)v22 + 4) == v22 + 8
              && v22 != (_DWORD *)-120LL
              && (v22[32] & 1) != 0
              && *((_QWORD *)v22 + 30) )
            {
              UlDisableLoggingConfig();
            }
          }
        }
        else
        {
          if ( (xmmword_1401A2C90 & 0x10) != 0 )
            WPP_SF_(516, 113, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids);
          v18 = -1073741734;
        }
      }
      else
      {
        if ( (xmmword_1401A2C90 & 0x10) != 0 )
          WPP_SF_q(516, 112, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v14);
        v18 = -1073741811;
        if ( !v22 )
          goto LABEL_23;
      }
      v27 = _InterlockedDecrement(v22 + 1);
      if ( UxDebugCheckRefcount && v27 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)(v22 + 1), 0xBu, v27);
      if ( !v27 )
        UlFreeConfigGroup(v22);
    }
    else
    {
      v18 = -1073741811;
    }
LABEL_23:
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 1368LL));
    KeLeaveCriticalRegion();
    goto LABEL_24;
  }
  if ( (xmmword_1401A2C90 & 0x10) != 0 )
    WPP_SF_Sd(516, 110, (unsigned int)WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, *(_QWORD *)(v32 + 8), v18);
LABEL_24:
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_d(1028, 117, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400273bc  mov     [rsp-8+arg_18], rbx
0x1400273c1  mov     [rsp-8+arg_10], r8
0x1400273c6  push    rbp
0x1400273c7  push    rsi
0x1400273c8  push    rdi
0x1400273c9  push    r12
0x1400273cb  push    r13
0x1400273cd  push    r14
0x1400273cf  push    r15
0x1400273d1  lea     rbp, [rsp-0Fh]
0x1400273d6  sub     rsp, 0E0h
0x1400273dd  mov     rbx, r8
0x1400273e0  mov     [rbp+3Fh+arg_8], 0
0x1400273e8  mov     rdi, rdx
0x1400273eb  mov     [rbp+3Fh+P], 0
0x1400273f3  mov     r14, rcx
0x1400273f6  xor     edx, edx; Val
0x1400273f8  mov     r8d, 88h; Size
0x1400273fe  lea     rcx, [rsp+110h+var_C0]; void *
0x140027403  mov     r12, r9
0x140027406  call    memset
0x14002740b  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140027412  movsx   r13d, [rbp+3Fh+arg_28]
0x140027417  jnz     loc_140027654
0x14002741d  mov     rsi, [rdi+8]
0x140027421  test    byte ptr cs:xmmword_1401A2CA0+8, 10h
0x140027428  jnz     loc_140027685
0x14002742e  mov     rbx, [rbx+8]
0x140027432  mov     r15, [r14+38h]
0x140027436  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x14002743d  jnz     loc_14002769D
0x140027443  lea     rcx, [r15+112Ch]
0x14002744a  mov     [rbp+3Fh+P], 0
0x140027452  lea     r9, [rsp+110h+var_C0]
0x140027457  mov     r8d, 101h
0x14002745d  mov     rdx, rbx
0x140027460  call    HttpParseUrl
0x140027465  xor     r15d, r15d
0x140027468  mov     ebx, eax
0x14002746a  test    eax, eax
0x14002746c  jns     loc_1400276DB
0x140027472  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x140027479  jnz     loc_1400276E8
0x14002747f  test    ebx, ebx
0x140027481  js      loc_140027715
0x140027487  mov     rbx, [r14+38h]
0x14002748b  call    cs:__imp_KeEnterCriticalRegion
0x140027492  nop     dword ptr [rax+rax+00h]
0x140027497  mov     rcx, [rbx+558h]
0x14002749e  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400274a5  nop     dword ptr [rax+rax+00h]
0x1400274aa  mov     ecx, [rdi]
0x1400274ac  test    ecx, ecx
0x1400274ae  jz      loc_140173626
0x1400274b4  cmp     ecx, 1
0x1400274b7  jnz     short loc_140027531
0x1400274b9  mov     rdx, [rbp+3Fh+P]
0x1400274bd  lea     r8, [rbp+3Fh+arg_8]
0x1400274c1  mov     rcx, [r14+38h]
0x1400274c5  call    UlpTreeFindRegistrationNode
0x1400274ca  mov     ebx, eax
0x1400274cc  test    eax, eax
0x1400274ce  js      loc_140027749
0x1400274d4  lea     r9, UlValidateConfigGroup
0x1400274db  mov     [rsp+110h+var_F0], r14
0x1400274e0  lea     r8, UlReferenceServerSession
0x1400274e7  mov     edx, 2
0x1400274ec  mov     rcx, rsi
0x1400274ef  call    UxGetObjectFromOpaqueId
0x1400274f4  mov     rdi, rax
0x1400274f7  test    rax, rax
0x1400274fa  jz      loc_1400277F1
0x140027500  cmp     dword ptr [rax], 4A436C55h
0x140027506  jnz     loc_1400277F1
0x14002750c  mov     rcx, [rbp+3Fh+arg_8]; P
0x140027510  cmp     [rcx+58h], rax
0x140027514  jz      loc_1400275A1
0x14002751a  test    byte ptr cs:xmmword_1401A2C90, 10h
0x140027521  jnz     loc_140027774
0x140027527  mov     ebx, 0C000005Ah
0x14002752c  jmp     loc_1400275FB
0x140027531  mov     ebx, 0C000000Dh
0x140027536  jmp     short loc_140027546
0x140027538  mov     ebx, 0C000000Dh
0x14002753d  test    rdi, rdi
0x140027540  jnz     loc_1400275FB
0x140027546  mov     rcx, [r14+38h]
0x14002754a  mov     rcx, [rcx+558h]
0x140027551  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x140027558  nop     dword ptr [rax+rax+00h]
0x14002755d  call    cs:__imp_KeLeaveCriticalRegion
0x140027564  nop     dword ptr [rax+rax+00h]
0x140027569  mov     rcx, [rbp+3Fh+P]; P
0x14002756d  test    rcx, rcx
0x140027570  jnz     loc_140027626
0x140027576  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x14002757d  jnz     loc_14002781C
0x140027583  mov     eax, ebx
0x140027585  mov     rbx, [rsp+110h+arg_18]
0x14002758d  add     rsp, 0E0h
0x140027594  pop     r15
0x140027596  pop     r14
0x140027598  pop     r13
0x14002759a  pop     r12
0x14002759c  pop     rdi
0x14002759d  pop     rsi
0x14002759e  pop     rbp
0x14002759f  retn
0x1400275a1  call    UlpTreeDeleteRegistration
0x1400275a6  mov     r9, [rbp+3Fh+arg_30]
0x1400275aa  lea     r8, [rsp+110h+var_C0]
0x1400275af  mov     rdx, rsi
0x1400275b2  mov     ebx, eax
0x1400275b4  call    UlEventLogRemoveUrl
0x1400275b9  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400275c0  jnz     loc_14002778F
0x1400275c6  test    ebx, ebx
0x1400275c8  js      loc_1400277AF
0x1400275ce  mov     rdx, rdi
0x1400275d1  lea     rcx, [rsp+110h+var_C0]
0x1400275d6  call    UlFlushCacheForRemoveUrl
0x1400275db  lea     rax, [rdi+20h]
0x1400275df  cmp     [rax], rax
0x1400275e2  jnz     short loc_1400275FB
0x1400275e4  lea     rcx, [rdi+78h]
0x1400275e8  test    rcx, rcx
0x1400275eb  jz      short loc_1400275FB
0x1400275ed  mov     eax, [rdi+80h]
0x1400275f3  test    al, 1
0x1400275f5  jnz     loc_1400277DA
0x1400275fb  lea     rdx, [rdi+4]; BugCheckParameter2
0x1400275ff  or      eax, 0FFFFFFFFh
0x140027602  lock xadd [rdx], eax
0x140027606  dec     eax
0x140027608  cmp     cs:UxDebugCheckRefcount, r15b
0x14002760f  jnz     short loc_14002763D
0x140027611  test    eax, eax
0x140027613  jnz     loc_140027546
0x140027619  mov     rcx, rdi; P
0x14002761c  call    UlFreeConfigGroup
0x140027621  jmp     loc_140027546
0x140027626  xor     edx, edx; Tag
0x140027628  call    cs:__imp_ExFreePoolWithTag
0x14002762f  nop     dword ptr [rax+rax+00h]
0x140027634  mov     [rbp+3Fh+P], r15
0x140027638  jmp     loc_140027576
0x14002763d  cmp     eax, 0FFFFFFFFh
0x140027640  jg      short loc_140027611
0x140027642  mov     ecx, 3; BugCheckParameter1
0x140027647  movsxd  r9, eax; BugCheckParameter4
0x14002764a  lea     r8d, [rcx+8]; BugCheckParameter3
0x14002764e  call    UlBugCheckEx
0x140027654  mov     eax, [rbp+3Fh+arg_20]
0x140027657  mov     edx, 6Ch ; 'l'
0x14002765c  mov     [rsp+110h+var_D0], r13d
0x140027661  mov     r9, r14
0x140027664  mov     dword ptr [rsp+110h+var_D8], eax
0x140027668  mov     rax, [rbx+8]
0x14002766c  mov     [rsp+110h+var_E0], r12
0x140027671  mov     [rsp+110h+var_E8], rax
0x140027676  mov     [rsp+110h+var_F0], rdi
0x14002767b  call    WPP_SF_qqSqLl
0x140027680  jmp     loc_14002741D
0x140027685  mov     r9, [rbx+8]
0x140027689  mov     edx, 6Dh ; 'm'
0x14002768e  mov     [rsp+110h+var_F0], rsi
0x140027693  call    WPP_SF_Si
0x140027698  jmp     loc_14002742E
0x14002769d  lea     rax, [rsp+110h+var_C0]
0x1400276a2  mov     edx, 1Bh
0x1400276a7  mov     [rsp+110h+var_D8], rax
0x1400276ac  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400276b3  lea     rax, [rbp+3Fh+P]
0x1400276b7  mov     ecx, 404h
0x1400276bc  mov     [rsp+110h+var_E0], rax
0x1400276c1  mov     r9, r15
0x1400276c4  mov     dword ptr [rsp+110h+var_E8], 1
0x1400276cc  mov     [rsp+110h+var_F0], rbx
0x1400276d1  call    WPP_SF_qqLqq
0x1400276d6  jmp     loc_140027443
0x1400276db  mov     rax, [rbp+3Fh+var_B8]
0x1400276df  mov     [rbp+3Fh+P], rax
0x1400276e3  jmp     loc_140027472
0x1400276e8  mov     r9, [rbp+3Fh+P]
0x1400276ec  lea     rax, [rsp+110h+var_C0]
0x1400276f1  mov     edx, 1Ch
0x1400276f6  mov     dword ptr [rsp+110h+var_E8], ebx
0x1400276fa  mov     ecx, 404h
0x1400276ff  mov     [rsp+110h+var_F0], rax
0x140027704  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x14002770b  call    WPP_SF_qqD
0x140027710  jmp     loc_14002747F
0x140027715  test    byte ptr cs:xmmword_1401A2C90, 10h
0x14002771c  jz      loc_140027569
0x140027722  mov     r9, [rbp+3Fh+arg_10]
0x140027726  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x14002772d  mov     edx, 6Eh ; 'n'
0x140027732  mov     dword ptr [rsp+110h+var_F0], ebx
0x140027736  mov     ecx, 204h
0x14002773b  mov     r9, [r9+8]
0x14002773f  call    WPP_SF_Sd
0x140027744  jmp     loc_140027569
0x140027749  test    byte ptr cs:xmmword_1401A2C90, 10h
0x140027750  jz      loc_140027546
0x140027756  mov     edx, 6Fh ; 'o'
0x14002775b  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x140027762  mov     ecx, 204h
0x140027767  mov     r9d, eax
0x14002776a  call    WPP_SF_d
0x14002776f  jmp     loc_140027546
0x140027774  mov     edx, 71h ; 'q'
0x140027779  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x140027780  mov     ecx, 204h
0x140027785  call    WPP_SF_
0x14002778a  jmp     loc_140027527
0x14002778f  mov     rax, [rbp+3Fh+var_B8]
0x140027793  mov     edx, 72h ; 'r'
0x140027798  mov     [rsp+110h+var_E8], rax
0x14002779d  mov     r9d, ebx
0x1400277a0  mov     [rsp+110h+var_F0], rsi
0x1400277a5  call    WPP_SF_diS
0x1400277aa  jmp     loc_1400275C6
0x1400277af  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400277b6  jz      loc_1400275FB
0x1400277bc  mov     edx, 73h ; 's'
0x1400277c1  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400277c8  mov     ecx, 204h
0x1400277cd  mov     r9d, ebx
0x1400277d0  call    WPP_SF_d
0x1400277d5  jmp     loc_1400275FB
0x1400277da  cmp     [rdi+0F0h], r15
0x1400277e1  jz      loc_1400275FB
0x1400277e7  call    UlDisableLoggingConfig
0x1400277ec  jmp     loc_1400275FB
0x1400277f1  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400277f8  jz      loc_140027538
0x1400277fe  mov     edx, 70h ; 'p'
0x140027803  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x14002780a  mov     ecx, 204h
0x14002780f  mov     r9, rsi
0x140027812  call    WPP_SF_q
0x140027817  jmp     loc_140027538
0x14002781c  mov     edx, 75h ; 'u'
0x140027821  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x140027828  mov     ecx, 404h
0x14002782d  mov     r9d, ebx
0x140027830  call    WPP_SF_d
0x140027835  jmp     loc_140027583
0x140173626  mov     r9d, [rbp+3Fh+arg_20]
0x14017362a  lea     rdx, [rsp+110h+var_C0]
0x14017362f  mov     rcx, [r14+38h]
0x140173633  mov     r8, r12
0x140173636  mov     byte ptr [rsp+110h+var_E8], r15b
0x14017363b  mov     byte ptr [rsp+110h+var_F0], r13b
0x140173640  call    UlpDeleteReservationEntry
0x140173645  mov     ebx, eax
0x140173647  test    eax, eax
0x140173649  jns     loc_140027546
0x14017364f  test    byte ptr cs:xmmword_1401A2C90, 10h
0x140173656  jz      loc_140027546
0x14017365c  mov     r9, [rbp+3Fh+var_B8]
0x140173660  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x140173667  mov     edx, 74h ; 't'
0x14017366c  mov     dword ptr [rsp+110h+var_F0], eax
0x140173670  mov     ecx, 204h
0x140173675  call    WPP_SF_Sd
0x14017367a  nop
0x14017367b  jmp     loc_140027546
```
