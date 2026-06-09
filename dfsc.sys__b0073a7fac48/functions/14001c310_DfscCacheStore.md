# DfscCacheStore

- ea: `0x14001c310`
- end: `0x14001c8a6`
- name: `DfscCacheStore`
- size: `1430`
- prototype: `ULONG_PTR __fastcall(char *, ULONG_PTR, ULONG_PTR)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14001a718`
- `0x14001c270`

## callees

- `0x140002570`
- `0x1400025a0`
- `0x1400025f4`
- `0x1400026a4`
- `0x140002740`
- `0x140011a78`
- `0x1400199e4`
- `0x14001c310`
- `0x14001d090`
- `0x140028da0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c436`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c452`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c436`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c452`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c42a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c446`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c42a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c446`
- `ntoskrnl!KeBugCheckEx` at `0x14001c850`
- `ntoskrnl!KeBugCheckEx` at `0x14001c850`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14001c5fd`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14001c5fd`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14001c7b0`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14001c7b0`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001c36e`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001c36e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c33e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c3c3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c33e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001c3c3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c32c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c3ae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c32c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c3ae`

## pseudocode

```c
ULONG_PTR __fastcall DfscCacheStore(char *a1, ULONG_PTR a2, ULONG_PTR a3)
{
  struct _RTL_SPLAY_LINKS **p_RightChild; // rbp
  int v7; // edx
  int v8; // r8d
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _UNICODE_PREFIX_TABLE_ENTRY *v10; // r14
  __int64 v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  unsigned int v17; // eax
  char *v18; // rcx

  p_RightChild = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(a3 + 56), 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qqZ(WPP_GLOBAL_Control->AttachedDevice, v7, v8, (_DWORD)a1, a2, a2 + 144);
  UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)a3, (PCUNICODE_STRING)(a2 + 144), 0);
  v10 = UnicodePrefix;
  if ( UnicodePrefix )
  {
    p_RightChild = &UnicodePrefix[-2].Links.RightChild;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        (unsigned int)WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids,
        (_DWORD)p_RightChild,
        (__int64)(p_RightChild + 18));
    }
    if ( *(_WORD *)(a2 + 144) > *((_WORD *)p_RightChild + 72) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids);
      }
      p_RightChild = 0;
      goto LABEL_3;
    }
    if ( *(_BYTE *)(a2 + 15) )
      *((_BYTE *)p_RightChild + 15) = 1;
    if ( !*(_DWORD *)(a2 + 8) && !*(_WORD *)(a2 + 24) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids);
      }
LABEL_48:
      DfscRmDereferenceReferral((PVOID)a2);
      a2 = (ULONG_PTR)p_RightChild;
      p_RightChild = 0;
      goto LABEL_3;
    }
    if ( (*(_DWORD *)(a3 + 40) & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids);
      }
      if ( a1 != (char *)p_RightChild )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids);
        }
        goto LABEL_48;
      }
      if ( (unsigned __int8)DfscRmEquivalentReferral(a2, p_RightChild) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids);
        }
        v18 = (char *)(a2 + 16);
        if ( !*((_BYTE *)p_RightChild + 16) || *v18 )
        {
          *((_DWORD *)p_RightChild + 10) = *(_DWORD *)(a2 + 40);
          p_RightChild[4] = (struct _RTL_SPLAY_LINKS *)MEMORY[0xFFFFF78000000320];
        }
        if ( *v18 )
          *((_BYTE *)p_RightChild + 16) = *v18;
        goto LABEL_48;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, p_RightChild);
    }
    RtlRemoveUnicodePrefix((PUNICODE_PREFIX_TABLE)a3, v10);
    *((_WORD *)p_RightChild + 6) &= ~1u;
  }
LABEL_3:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, a2);
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 4));
  if ( (*(_BYTE *)(a2 + 12) & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, a2);
    }
    *(_WORD *)(a2 + 12) |= 1u;
    *(_QWORD *)(a2 + 32) = MEMORY[0xFFFFF78000000320];
    if ( !RtlInsertUnicodePrefix(
            (PUNICODE_PREFIX_TABLE)a3,
            (PUNICODE_STRING)(a2 + 144),
            (PUNICODE_PREFIX_TABLE_ENTRY)(a2 + 72)) )
      KeBugCheckEx(0x10Bu, 1u, a3, a2, a2 + 144);
    *(_QWORD *)(a2 + 64) = a3;
    ++*(_DWORD *)(a3 + 44);
    *(_DWORD *)(a3 + 48) += *(unsigned __int16 *)(a2 + 2);
    v17 = *(_DWORD *)(a3 + 52);
    if ( v17 && *(_DWORD *)(a3 + 48) > v17 )
      DfscAgeOutOldestCacheEntries(a3);
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(a3 + 160), 1u);
  if ( p_RightChild )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, p_RightChild);
    }
    DfscRmUnlinkReferral(p_RightChild);
    DfscRmDereferenceReferral(p_RightChild);
  }
  v11 = *(_QWORD *)(a2 + 48);
  v12 = (_QWORD *)(a2 + 48);
  if ( v11 )
  {
    if ( *(_QWORD **)(v11 + 8) != v12 || (v13 = *(_QWORD **)(a2 + 56), (_QWORD *)*v13 != v12) )
LABEL_74:
      __fastfail(3u);
    *v13 = v11;
    *(_QWORD *)(v11 + 8) = v13;
  }
  v14 = *(_QWORD *)(a3 + 24);
  v15 = (_QWORD *)(a3 + 24);
  if ( *(_QWORD *)(v14 + 8) != a3 + 24 )
    goto LABEL_74;
  *(_QWORD *)(a2 + 56) = v15;
  *v12 = v14;
  *(_QWORD *)(v14 + 8) = v12;
  *v15 = v12;
  ExReleaseResourceLite((PERESOURCE)(a3 + 160));
  KeLeaveCriticalRegion();
  ExReleaseResourceLite((PERESOURCE)(a3 + 56));
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids, a2);
  return a2;
}

```

## disassembly

```asm
0x14001c310  push    rbx
0x14001c312  push    rbp
0x14001c313  push    rsi
0x14001c314  push    rdi
0x14001c315  push    r12
0x14001c317  push    r13
0x14001c319  push    r14
0x14001c31b  push    r15
0x14001c31d  sub     rsp, 38h
0x14001c321  mov     rdi, r8
0x14001c324  mov     rbx, rdx
0x14001c327  mov     r12, rcx
0x14001c32a  xor     ebp, ebp
0x14001c32c  call    cs:__imp_KeEnterCriticalRegion
0x14001c333  nop     dword ptr [rax+rax+00h]
0x14001c338  mov     dl, 1; Wait
0x14001c33a  lea     rcx, [rdi+38h]; Resource
0x14001c33e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c345  nop     dword ptr [rax+rax+00h]
0x14001c34a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c351  lea     r13, WPP_GLOBAL_Control
0x14001c358  cmp     rcx, r13
0x14001c35b  jnz     loc_14001C544
0x14001c361  xor     r8d, r8d; CaseInsensitiveIndex
0x14001c364  lea     rdx, [rbx+90h]; FullName
0x14001c36b  mov     rcx, rdi; PrefixTable
0x14001c36e  call    cs:__imp_RtlFindUnicodePrefix
0x14001c375  nop     dword ptr [rax+rax+00h]
0x14001c37a  mov     r14, rax
0x14001c37d  test    rax, rax
0x14001c380  jnz     loc_14001C4CC
0x14001c386  mov     rsi, 0FFFFF78000000320h
0x14001c390  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c397  cmp     rcx, r13
0x14001c39a  jnz     loc_14001C4A2
0x14001c3a0  lock inc dword ptr [rbx+4]
0x14001c3a4  test    byte ptr [rbx+0Ch], 1
0x14001c3a8  jz      loc_14001C5D0
0x14001c3ae  call    cs:__imp_KeEnterCriticalRegion
0x14001c3b5  nop     dword ptr [rax+rax+00h]
0x14001c3ba  mov     dl, 1; Wait
0x14001c3bc  lea     rcx, [rdi+0A0h]; Resource
0x14001c3c3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001c3ca  nop     dword ptr [rax+rax+00h]
0x14001c3cf  test    rbp, rbp
0x14001c3d2  jnz     loc_14001C85D
0x14001c3d8  mov     rcx, [rbx+30h]
0x14001c3dc  lea     rax, [rbx+30h]
0x14001c3e0  test    rcx, rcx
0x14001c3e3  jz      short loc_14001C403
0x14001c3e5  cmp     [rcx+8], rax
0x14001c3e9  jnz     loc_14001C89F
0x14001c3ef  mov     rdx, [rax+8]
0x14001c3f3  cmp     [rdx], rax
0x14001c3f6  jnz     loc_14001C89F
0x14001c3fc  mov     [rdx], rcx
0x14001c3ff  mov     [rcx+8], rdx
0x14001c403  mov     rdx, [rdi+18h]
0x14001c407  lea     rcx, [rdi+18h]
0x14001c40b  cmp     [rdx+8], rcx
0x14001c40f  jnz     loc_14001C89F
0x14001c415  mov     [rax+8], rcx
0x14001c419  mov     [rax], rdx
0x14001c41c  mov     [rdx+8], rax
0x14001c420  mov     [rcx], rax
0x14001c423  lea     rcx, [rdi+0A0h]; Resource
0x14001c42a  call    cs:__imp_ExReleaseResourceLite
0x14001c431  nop     dword ptr [rax+rax+00h]
0x14001c436  call    cs:__imp_KeLeaveCriticalRegion
0x14001c43d  nop     dword ptr [rax+rax+00h]
0x14001c442  lea     rcx, [rdi+38h]; Resource
0x14001c446  call    cs:__imp_ExReleaseResourceLite
0x14001c44d  nop     dword ptr [rax+rax+00h]
0x14001c452  call    cs:__imp_KeLeaveCriticalRegion
0x14001c459  nop     dword ptr [rax+rax+00h]
0x14001c45e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c465  cmp     rcx, r13
0x14001c468  jnz     short loc_14001C47F
0x14001c46a  mov     rax, rbx
0x14001c46d  add     rsp, 38h
0x14001c471  pop     r15
0x14001c473  pop     r14
0x14001c475  pop     r13
0x14001c477  pop     r12
0x14001c479  pop     rdi
0x14001c47a  pop     rsi
0x14001c47b  pop     rbp
0x14001c47c  pop     rbx
0x14001c47d  retn
0x14001c47f  test    dword ptr [rcx+2Ch], 400000h
0x14001c486  jz      short loc_14001C46A
0x14001c488  mov     rcx, [rcx+18h]
0x14001c48c  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c493  mov     edx, 18h
0x14001c498  mov     r9, rbx
0x14001c49b  call    WPP_SF_q
0x14001c4a0  jmp     short loc_14001C46A
0x14001c4a2  test    dword ptr [rcx+2Ch], 400000h
0x14001c4a9  jz      loc_14001C3A0
0x14001c4af  mov     rcx, [rcx+18h]
0x14001c4b3  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c4ba  mov     edx, 15h
0x14001c4bf  mov     r9, rbx
0x14001c4c2  call    WPP_SF_q
0x14001c4c7  jmp     loc_14001C3A0
0x14001c4cc  lea     rbp, [rax-48h]
0x14001c4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c4d7  cmp     rcx, r13
0x14001c4da  jz      short loc_14001C4E9
0x14001c4dc  test    dword ptr [rcx+2Ch], 400000h
0x14001c4e3  jnz     loc_14001C694
0x14001c4e9  movzx   edx, word ptr [rbp+90h]
0x14001c4f0  movzx   r8d, word ptr [rbx+90h]
0x14001c4f8  cmp     r8w, dx
0x14001c4fc  ja      loc_14001C6BD
0x14001c502  cmp     byte ptr [rbx+0Fh], 0
0x14001c506  jnz     loc_14001C6F6
0x14001c50c  cmp     dword ptr [rbx+8], 0
0x14001c510  jnz     short loc_14001C573
0x14001c512  cmp     word ptr [rbx+18h], 0
0x14001c517  jnz     short loc_14001C573
0x14001c519  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c520  cmp     rcx, r13
0x14001c523  jz      short loc_14001C532
0x14001c525  test    dword ptr [rcx+2Ch], 400000h
0x14001c52c  jnz     loc_14001C6FF
0x14001c532  mov     rcx, rbx; P
0x14001c535  call    DfscRmDereferenceReferral
0x14001c53a  mov     rbx, rbp
0x14001c53d  xor     ebp, ebp
0x14001c53f  jmp     loc_14001C386
0x14001c544  test    dword ptr [rcx+2Ch], 400000h
0x14001c54b  jz      loc_14001C361
0x14001c551  mov     rcx, [rcx+18h]
0x14001c555  lea     rax, [rbx+90h]
0x14001c55c  mov     [rsp+78h+var_50], rax
0x14001c561  mov     r9, r12
0x14001c564  mov     [rsp+78h+BugCheckParameter4], rbx
0x14001c569  call    WPP_SF_qqZ
0x14001c56e  jmp     loc_14001C361
0x14001c573  mov     eax, [rdi+28h]
0x14001c576  test    al, 1
0x14001c578  jz      loc_14001C77D
0x14001c57e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c585  cmp     rcx, r13
0x14001c588  jnz     loc_14001C719
0x14001c58e  cmp     r12, rbp
0x14001c591  jz      loc_14001C740
0x14001c597  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c59e  cmp     rcx, r13
0x14001c5a1  jz      short loc_14001C5C1
0x14001c5a3  test    dword ptr [rcx+2Ch], 400000h
0x14001c5aa  jz      short loc_14001C5C1
0x14001c5ac  mov     rcx, [rcx+18h]
0x14001c5b0  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c5b7  mov     edx, 12h
0x14001c5bc  call    WPP_SF_
0x14001c5c1  mov     rsi, 0FFFFF78000000320h
0x14001c5cb  jmp     loc_14001C682
0x14001c5d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c5d7  cmp     rcx, r13
0x14001c5da  jnz     loc_14001C811
0x14001c5e0  or      word ptr [rbx+0Ch], 1
0x14001c5e5  lea     r8, [rbx+48h]; PrefixTableEntry
0x14001c5e9  mov     rax, [rsi]
0x14001c5ec  mov     rcx, rdi; PrefixTable
0x14001c5ef  lea     rsi, [rbx+90h]
0x14001c5f6  mov     [rbx+20h], rax
0x14001c5fa  mov     rdx, rsi; Prefix
0x14001c5fd  call    cs:__imp_RtlInsertUnicodePrefix
0x14001c604  nop     dword ptr [rax+rax+00h]
0x14001c609  test    al, al
0x14001c60b  jz      loc_14001C83B
0x14001c611  mov     [rbx+40h], rdi
0x14001c615  inc     dword ptr [rdi+2Ch]
0x14001c618  movzx   eax, word ptr [rbx+2]
0x14001c61c  add     [rdi+30h], eax
0x14001c61f  mov     eax, [rdi+34h]
0x14001c622  mov     ecx, [rdi+30h]
0x14001c625  test    eax, eax
0x14001c627  jz      loc_14001C3AE
0x14001c62d  cmp     ecx, eax
0x14001c62f  jbe     loc_14001C3AE
0x14001c635  mov     rcx, rdi
0x14001c638  call    DfscAgeOutOldestCacheEntries
0x14001c63d  jmp     loc_14001C3AE
0x14001c642  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c649  cmp     rcx, r13
0x14001c64c  jnz     loc_14001C7CA
0x14001c652  cmp     byte ptr [rbp+10h], 0
0x14001c656  lea     rcx, [rbx+10h]
0x14001c65a  jnz     loc_14001C7F1
0x14001c660  mov     eax, [rbx+28h]
0x14001c663  mov     rsi, 0FFFFF78000000320h
0x14001c66d  mov     [rbp+28h], eax
0x14001c670  mov     rax, [rsi]
0x14001c673  mov     [rbp+20h], rax
0x14001c677  movzx   eax, byte ptr [rcx]
0x14001c67a  test    al, al
0x14001c67c  jnz     loc_14001C809
0x14001c682  mov     rcx, rbx; P
0x14001c685  call    DfscRmDereferenceReferral
0x14001c68a  mov     rbx, rbp
0x14001c68d  xor     ebp, ebp
0x14001c68f  jmp     loc_14001C390
0x14001c694  mov     rcx, [rcx+18h]
0x14001c698  lea     rax, [rbp+90h]
0x14001c69f  mov     edx, 0Dh
0x14001c6a4  mov     [rsp+78h+BugCheckParameter4], rax
0x14001c6a9  mov     r9, rbp
0x14001c6ac  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c6b3  call    WPP_SF_qZ
0x14001c6b8  jmp     loc_14001C4E9
0x14001c6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c6c4  cmp     rcx, r13
0x14001c6c7  jz      short loc_14001C6EF
0x14001c6c9  test    dword ptr [rcx+2Ch], 400000h
0x14001c6d0  jz      short loc_14001C6EF
0x14001c6d2  mov     rcx, [rcx+18h]
0x14001c6d6  mov     r9d, edx
0x14001c6d9  mov     dword ptr [rsp+78h+BugCheckParameter4], r8d
0x14001c6de  mov     edx, 0Eh
0x14001c6e3  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c6ea  call    WPP_SF_dd
0x14001c6ef  xor     ebp, ebp
0x14001c6f1  jmp     loc_14001C386
0x14001c6f6  mov     byte ptr [rbp+0Fh], 1
0x14001c6fa  jmp     loc_14001C50C
0x14001c6ff  mov     rcx, [rcx+18h]
0x14001c703  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c70a  mov     edx, 0Fh
0x14001c70f  call    WPP_SF_
0x14001c714  jmp     loc_14001C532
0x14001c719  test    dword ptr [rcx+2Ch], 400000h
0x14001c720  jz      loc_14001C58E
0x14001c726  mov     rcx, [rcx+18h]
0x14001c72a  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c731  mov     edx, 10h
0x14001c736  call    WPP_SF_
0x14001c73b  jmp     loc_14001C58E
0x14001c740  mov     rdx, rbp
0x14001c743  mov     rcx, rbx
0x14001c746  call    DfscRmEquivalentReferral
0x14001c74b  test    al, al
0x14001c74d  jnz     loc_14001C642
0x14001c753  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c75a  cmp     rcx, r13
0x14001c75d  jz      short loc_14001C77D
0x14001c75f  test    dword ptr [rcx+2Ch], 400000h
0x14001c766  jz      short loc_14001C77D
0x14001c768  mov     rcx, [rcx+18h]
0x14001c76c  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c773  mov     edx, 13h
0x14001c778  call    WPP_SF_
0x14001c77d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c784  cmp     rcx, r13
0x14001c787  jz      short loc_14001C7AA
0x14001c789  test    dword ptr [rcx+2Ch], 400000h
0x14001c790  jz      short loc_14001C7AA
0x14001c792  mov     rcx, [rcx+18h]
0x14001c796  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c79d  mov     edx, 14h
0x14001c7a2  mov     r9, rbp
0x14001c7a5  call    WPP_SF_q
0x14001c7aa  mov     rdx, r14; PrefixTableEntry
0x14001c7ad  mov     rcx, rdi; PrefixTable
0x14001c7b0  call    cs:__imp_RtlRemoveUnicodePrefix
0x14001c7b7  nop     dword ptr [rax+rax+00h]
0x14001c7bc  mov     eax, 0FFFEh
0x14001c7c1  and     [rbp+0Ch], ax
0x14001c7c5  jmp     loc_14001C386
0x14001c7ca  test    dword ptr [rcx+2Ch], 400000h
0x14001c7d1  jz      loc_14001C652
0x14001c7d7  mov     rcx, [rcx+18h]
0x14001c7db  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c7e2  mov     edx, 11h
0x14001c7e7  call    WPP_SF_
0x14001c7ec  jmp     loc_14001C652
0x14001c7f1  cmp     byte ptr [rcx], 0
0x14001c7f4  jnz     loc_14001C660
0x14001c7fa  mov     rsi, 0FFFFF78000000320h
0x14001c804  jmp     loc_14001C677
0x14001c809  mov     [rbp+10h], al
0x14001c80c  jmp     loc_14001C682
0x14001c811  test    dword ptr [rcx+2Ch], 400000h
0x14001c818  jz      loc_14001C5E0
0x14001c81e  mov     rcx, [rcx+18h]
0x14001c822  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c829  mov     edx, 16h
0x14001c82e  mov     r9, rbx
0x14001c831  call    WPP_SF_q
0x14001c836  jmp     loc_14001C5E0
0x14001c83b  mov     r9, rbx; BugCheckParameter3
0x14001c83e  mov     [rsp+78h+BugCheckParameter4], rsi; BugCheckParameter4
0x14001c843  mov     r8, rdi; BugCheckParameter2
0x14001c846  mov     edx, 1; BugCheckParameter1
0x14001c84b  mov     ecx, 10Bh; BugCheckCode
0x14001c850  call    cs:__imp_KeBugCheckEx
0x14001c85d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c864  cmp     rcx, r13
  ... truncated ...
```
