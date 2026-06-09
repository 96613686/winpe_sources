# DfscGetCacheReferral

- ea: `0x14001d110`
- end: `0x14001d940`
- name: `DfscGetCacheReferral`
- size: `2096`
- prototype: `__int64 __fastcall(__int64, __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020660`

## callees

- `0x1400025a0`
- `0x140002aa0`
- `0x140002b18`
- `0x1400050fc`
- `0x14001c8ac`
- `0x14001cfd0`
- `0x14001d090`
- `0x14001d110`
- `0x14001f540`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001d758`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001d758`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001d21d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001d338`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001d21d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001d338`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d40a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d48f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d52d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d92f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d40a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d48f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d52d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d92f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d3fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d483`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d521`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d923`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d3fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d483`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d521`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d923`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001d3db`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001d3db`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001d3c5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001d4b0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001d3c5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001d4b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d3b3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d49b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d3b3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d49b`
- `ntoskrnl!ExAllocatePool2` at `0x14001d549`
- `ntoskrnl!ExAllocatePool2` at `0x14001d549`
- `MUP!MupSurrogateCheckNegativeCache` at `0x14001d363`
- `MUP!MupSurrogateCheckNegativeCache` at `0x14001d363`

## pseudocode

```c
__int64 __fastcall DfscGetCacheReferral(__int64 a1, __int64 *a2, _DWORD *a3)
{
  unsigned int v3; // ebx
  unsigned __int64 v6; // rcx
  unsigned __int16 v7; // ax
  unsigned __int16 v8; // dx
  wchar_t v9; // r8
  __int16 v10; // r8
  UNICODE_STRING *v12; // rsi
  unsigned int v13; // ebx
  __int64 v14; // rax
  unsigned __int16 v15; // cx
  unsigned __int16 v16; // dx
  wchar_t v17; // r8
  __int16 v18; // r8
  __int64 v19; // r14
  struct _UNICODE_STRING *v20; // rbx
  char *SecurityDescriptor; // r14
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _RTL_SPLAY_LINKS **p_RightChild; // rbx
  unsigned __int64 v24; // rdx
  unsigned int v25; // r8d
  __int64 v26; // rax
  struct _RTL_SPLAY_LINKS *v27; // rax
  struct _RTL_SPLAY_LINKS *v28; // rcx
  struct _RTL_SPLAY_LINKS *v29; // rdx
  struct _RTL_SPLAY_LINKS *v30; // rdx
  struct _RTL_SPLAY_LINKS *v31; // rax
  __int64 Pool2; // rax
  __int64 v33; // r14
  int v34; // edx
  int v35; // r8d
  UNICODE_STRING *v36; // r15
  int v37; // r14d
  __int64 v38; // rcx
  unsigned __int16 v39; // dx
  int v40; // edx
  __int64 v41; // r9
  USHORT Length; // cx
  _WORD *v43; // rax
  char v44; // r10
  __int64 v45; // r9
  __int64 v46; // rcx
  unsigned int v47; // r8d
  __int64 v48; // rax
  unsigned __int64 v49; // rdx
  bool v50; // zf
  WCHAR *v51; // rdx
  __int16 v52; // r8
  UNICODE_STRING String2; // [rsp+40h] [rbp-38h] BYREF
  __int128 v54; // [rsp+50h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-18h] BYREF

  *a3 = 0;
  v54 = 0;
  v3 = 0;
  while ( v3 < 4 )
  {
    v6 = 16LL * v3;
    v7 = *(_WORD *)(a1 + 120) >> 1;
    v8 = asc_14000C080[v6 / 2] >> 1;
    String1 = 0;
    for ( String2 = 0; v8; --v8 )
    {
      v9 = (&off_14000C088)[v6 / 8][v8 - 1];
      if ( v9 != 92 && v9 )
        break;
    }
    if ( v7 )
    {
      while ( 1 )
      {
        v10 = *(_WORD *)(*(_QWORD *)(a1 + 128) + 2LL * v7 - 2);
        if ( v10 != 92 )
        {
          if ( v10 )
            break;
        }
        if ( !--v7 )
          goto LABEL_16;
      }
      if ( v7 != v8 || !v8 )
        goto LABEL_10;
      String1 = *(UNICODE_STRING *)(v6 + 49280 + 0x140000000LL);
      String1.Length = 2 * v8;
      String2 = *(UNICODE_STRING *)(a1 + 120);
      String2.Length = 2 * v7;
      if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
        goto LABEL_17;
      ++v3;
    }
    else
    {
LABEL_16:
      if ( !v8 )
        goto LABEL_17;
LABEL_10:
      ++v3;
    }
  }
  v12 = (UNICODE_STRING *)(a1 + 104);
  v13 = 0;
  while ( v13 < 3 )
  {
    v14 = 2LL * v13;
    v15 = v12->Length >> 1;
    v16 = LOWORD(qword_14000C048[v14]) >> 1;
    String2 = 0;
    for ( String1 = 0; v16; --v16 )
    {
      v17 = (&off_14000C050)[v14][v16 - 1];
      if ( v17 != 92 && v17 )
        break;
    }
    if ( v15 )
    {
      while ( 1 )
      {
        v18 = *(_WORD *)(*(_QWORD *)(a1 + 112) + 2LL * v15 - 2);
        if ( v18 != 92 )
        {
          if ( v18 )
            break;
        }
        if ( !--v15 )
          goto LABEL_39;
      }
      if ( v15 != v16 || !v16 )
        goto LABEL_27;
      String2 = *(UNICODE_STRING *)(v14 * 8 + 49224 + 0x140000000LL);
      String2.Length = 2 * v16;
      String1 = *v12;
      String1.Length = 2 * v15;
      if ( !RtlCompareUnicodeString(&String2, &String1, 1u) )
        goto LABEL_17;
      ++v13;
    }
    else
    {
LABEL_39:
      if ( !v16 )
        goto LABEL_17;
LABEL_27:
      ++v13;
    }
  }
  if ( !(unsigned int)MupSurrogateCheckNegativeCache(*(_QWORD *)a1, a1 + 184) )
  {
LABEL_17:
    *a3 = 1;
    return 0;
  }
  v19 = *(_QWORD *)(a1 + 240);
  v20 = (struct _UNICODE_STRING *)(a1 + 200);
  if ( v19 )
    SecurityDescriptor = *(char **)(v19 + 136);
  else
    SecurityDescriptor = (char *)WPP_MAIN_CB.SecurityDescriptor;
  String2.Buffer = *(PWSTR *)(a1 + 80);
  String2.MaximumLength = *(_WORD *)(a1 + 74);
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String2.Length = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(SecurityDescriptor + 56), 1u);
  UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)SecurityDescriptor, (PCUNICODE_STRING)(a1 + 72), 0);
  if ( !UnicodePrefix )
  {
    ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 56));
    KeLeaveCriticalRegion();
    goto LABEL_79;
  }
  p_RightChild = &UnicodePrefix[-2].Links.RightChild;
  if ( (BYTE4(UnicodePrefix[-2].Prefix) & 1) == 0 )
  {
    ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 56));
    KeLeaveCriticalRegion();
    v20 = (struct _UNICODE_STRING *)(a1 + 200);
LABEL_79:
    v37 = DfscDomainCacheLookup(a1, a1 + 8, a2);
    if ( v37 >= 0 )
    {
      *a3 = 2;
      RtlInitUnicodeString(v20, 0);
    }
    return (unsigned int)v37;
  }
  v24 = *(unsigned __int16 *)(a1 + 72);
  v25 = *((unsigned __int16 *)p_RightChild + 72);
  if ( (unsigned __int16)v25 >= (unsigned __int16)v24 )
  {
    if ( (_WORD)v25 == (_WORD)v24 )
    {
      v48 = *(_QWORD *)(a1 + 80) - 2LL;
      v49 = v24 >> 1;
      v50 = *(_WORD *)(v48 + 2 * v49) == 92;
      v51 = (WCHAR *)(v48 + 2 * v49);
      if ( v50 )
      {
        String2.Length = 2;
        String2.Buffer = v51;
      }
    }
  }
  else
  {
    v26 = *(_QWORD *)(a1 + 80);
    String2.Length = v24 - v25;
    String2.Buffer = (PWSTR)(v26 + 2 * ((unsigned __int64)v25 >> 1));
  }
  _InterlockedIncrement((volatile signed __int32 *)p_RightChild + 1);
  ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 56));
  KeLeaveCriticalRegion();
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(SecurityDescriptor + 160), 1u);
  if ( SecurityDescriptor == (char *)p_RightChild[8] )
  {
    v27 = p_RightChild[6];
    v28 = (struct _RTL_SPLAY_LINKS *)(p_RightChild + 6);
    if ( !v27 )
      goto LABEL_48;
    if ( v27->LeftChild != v28 )
      goto LABEL_92;
    v29 = p_RightChild[7];
    if ( v29->Parent != v28 )
      goto LABEL_92;
    v29->Parent = v27;
    v27->LeftChild = v29;
    v28->Parent = 0;
LABEL_48:
    if ( (*((_BYTE *)p_RightChild + 12) & 1) != 0 )
    {
      v30 = (struct _RTL_SPLAY_LINKS *)*((_QWORD *)SecurityDescriptor + 3);
      v31 = (struct _RTL_SPLAY_LINKS *)(SecurityDescriptor + 24);
      if ( (char *)v30->LeftChild == SecurityDescriptor + 24 )
      {
        v28->Parent = v30;
        p_RightChild[7] = v31;
        v30->LeftChild = v28;
        v31->Parent = v28;
        goto LABEL_51;
      }
LABEL_92:
      __fastfail(3u);
    }
  }
LABEL_51:
  ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 160));
  KeLeaveCriticalRegion();
  Pool2 = ExAllocatePool2(258, 40, 1648584260);
  v33 = Pool2;
  if ( !Pool2 )
  {
    DfscRmDereferenceReferral(p_RightChild);
    v20 = (struct _UNICODE_STRING *)(a1 + 200);
    goto LABEL_79;
  }
  *(_QWORD *)(Pool2 + 8) = 0;
  *(_QWORD *)(Pool2 + 24) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_DWORD *)Pool2 = 2654467;
  *(_DWORD *)(Pool2 + 4) = 1;
  *(_QWORD *)(Pool2 + 16) = p_RightChild;
  DfscRmIsTimeToRefresh(Pool2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qqDZ(
      WPP_GLOBAL_Control->AttachedDevice,
      v34,
      v35,
      v33,
      *(_QWORD *)(v33 + 16),
      *(_DWORD *)(v33 + 8),
      (__int64)(p_RightChild + 18));
  if ( !*((_DWORD *)p_RightChild + 2) && !*((_WORD *)p_RightChild + 12) )
    *(_DWORD *)(v33 + 8) |= 2u;
  v36 = (UNICODE_STRING *)(a1 + 200);
  *(_WORD *)(v33 + 32) = -1;
  if ( a1 != -200 )
    *v36 = String2;
  *a2 = v33;
  v37 = 0;
  v38 = *(unsigned __int16 *)(a1 + 72);
  v39 = *(_WORD *)(a1 + 88);
  *a3 = 2;
  if ( v39 > (unsigned __int16)v38 )
  {
    v52 = *(_WORD *)(a1 + 200);
    if ( !v52 )
      *(_QWORD *)(a1 + 208) = *(_QWORD *)(a1 + 80) + v38;
    *(_WORD *)(a1 + 200) = v39 + v52 - v38;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_ZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        (unsigned int)WPP_55706db06074317498eaf8c01331c814_Traceguids,
        a1 + 88,
        a1 + 200);
    }
  }
  v40 = *(unsigned __int16 *)(a1 + 200);
  v41 = *(unsigned __int16 *)(a1 + 216);
  if ( (unsigned __int16)v41 <= (unsigned __int16)v40 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_55706db06074317498eaf8c01331c814_Traceguids, v41, v40);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_55706db06074317498eaf8c01331c814_Traceguids, v41, v40);
    }
    *(_WORD *)(a1 + 216) = *(_WORD *)(a1 + 200);
  }
  Length = v36->Length;
  *((_QWORD *)&v54 + 1) = *(_QWORD *)(a1 + 96);
  LOWORD(v54) = *(_WORD *)(a1 + 88) - Length;
  WORD1(v54) = *(_WORD *)(a1 + 90) - Length;
  *(_OWORD *)(a1 + 184) = v54;
  if ( (int)DfscGetPathComponents(
              (__int16 *)(a1 + 184),
              (struct _UNICODE_STRING *)(a1 + 104),
              (struct _UNICODE_STRING *)(a1 + 120),
              (struct _UNICODE_STRING *)(a1 + 152),
              (PUNICODE_STRING)(a1 + 136)) >= 0
    && a1 != -104
    && v12->Length
    && (v43 = *(_WORD **)(a1 + 112)) != 0
    && *v43 )
  {
    if ( !*(_WORD *)(a1 + 136) )
      goto LABEL_76;
    v44 = 0;
    v45 = *((_QWORD *)&v54 + 1);
    v46 = ((unsigned __int16)v54 >> 1) - 1;
    v47 = *(unsigned __int16 *)(a1 + 152) >> 1;
    *(_QWORD *)(a1 + 176) = *((_QWORD *)&v54 + 1);
    if ( (unsigned int)v46 < v47 )
      goto LABEL_76;
    do
    {
      if ( *(_WORD *)(v45 + 2 * v46) == 58 )
      {
        v44 = 1;
        *(_WORD *)(a1 + 170) = 2 * v46;
        *(_WORD *)(a1 + 168) = 2 * v46;
      }
      if ( *(_WORD *)(v45 + 2 * v46) == 92 )
        break;
      v46 = (unsigned int)(v46 - 1);
    }
    while ( (unsigned int)v46 >= v47 );
    if ( !v44 )
LABEL_76:
      *(_OWORD *)(a1 + 168) = v54;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1bce9a35ce9f35cd7964d25412ee5844_Traceguids, &v54);
  }
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x14001d110  mov     [rsp-30h+arg_10], r8
0x14001d115  mov     [rsp-30h+arg_8], rdx
0x14001d11a  push    rbp
0x14001d11b  push    rbx
0x14001d11c  push    rdi
0x14001d11d  push    r13
0x14001d11f  push    r14
0x14001d121  push    r15
0x14001d123  mov     rbp, rsp
0x14001d126  sub     rsp, 78h
0x14001d12a  xor     r13d, r13d
0x14001d12d  mov     [rsp+78h+arg_0], rsi
0x14001d135  xorps   xmm0, xmm0
0x14001d138  mov     [r8], r13d
0x14001d13b  movups  [rbp+var_28], xmm0
0x14001d13f  mov     ebx, r13d
0x14001d142  lea     r15, cs:140000000h
0x14001d149  mov     r14, r8
0x14001d14c  mov     rdi, rcx
0x14001d14f  mov     r11d, 0FFFFh
0x14001d155  cmp     ebx, 4
0x14001d158  jnb     loc_14001D26E
0x14001d15e  movzx   eax, word ptr [rdi+78h]
0x14001d162  xorps   xmm0, xmm0
0x14001d165  mov     ecx, ebx
0x14001d167  xorps   xmm1, xmm1
0x14001d16a  shl     rcx, 4
0x14001d16e  movzx   edx, word ptr [rcx+r15+0C080h]
0x14001d177  lea     r10, [rcx+0C080h]
0x14001d17e  shr     ax, 1
0x14001d181  shr     dx, 1
0x14001d184  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001d188  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14001d18c  jz      short loc_14001D1B4
0x14001d18e  mov     r9, [rcx+r15+0C088h]
0x14001d196  movzx   ecx, dx
0x14001d199  movzx   r8d, word ptr [r9+rcx*2-2]
0x14001d19f  cmp     r8w, 5Ch ; '\'
0x14001d1a4  jz      loc_14001D23A
0x14001d1aa  test    r8w, r8w
0x14001d1ae  jz      loc_14001D23A
0x14001d1b4  test    ax, ax
0x14001d1b7  jz      loc_14001D249
0x14001d1bd  mov     r9, [rdi+80h]
0x14001d1c4  movzx   ecx, ax
0x14001d1c7  movzx   r8d, word ptr [r9+rcx*2-2]
0x14001d1cd  cmp     r8w, 5Ch ; '\'
0x14001d1d2  jz      loc_14001D766
0x14001d1d8  test    r8w, r8w
0x14001d1dc  jz      loc_14001D766
0x14001d1e2  cmp     ax, dx
0x14001d1e5  jz      short loc_14001D1EE
0x14001d1e7  inc     ebx
0x14001d1e9  jmp     loc_14001D155
0x14001d1ee  test    dx, dx
0x14001d1f1  jz      short loc_14001D1E7
0x14001d1f3  movups  xmm0, xmmword ptr [r10+r15]
0x14001d1f8  add     dx, dx
0x14001d1fb  lea     rcx, [rbp+String1]; String1
0x14001d1ff  add     ax, ax
0x14001d202  mov     r8b, 1; CaseInSensitive
0x14001d205  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001d209  mov     [rbp+String1.Length], dx
0x14001d20d  lea     rdx, [rbp+String2]; String2
0x14001d211  movups  xmm0, xmmword ptr [rdi+78h]
0x14001d215  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001d219  mov     [rbp+String2.Length], ax
0x14001d21d  call    cs:__imp_RtlCompareUnicodeString
0x14001d224  nop     dword ptr [rax+rax+00h]
0x14001d229  test    eax, eax
0x14001d22b  jz      short loc_14001D24E
0x14001d22d  mov     r11d, 0FFFFh
0x14001d233  inc     ebx
0x14001d235  jmp     loc_14001D155
0x14001d23a  add     dx, r11w
0x14001d23e  jnz     loc_14001D196
0x14001d244  jmp     loc_14001D1B4
0x14001d249  test    dx, dx
0x14001d24c  jnz     short loc_14001D1E7
0x14001d24e  mov     dword ptr [r14], 1
0x14001d255  xor     eax, eax
0x14001d257  mov     rsi, [rsp+78h+arg_0]
0x14001d25f  add     rsp, 78h
0x14001d263  pop     r15
0x14001d265  pop     r14
0x14001d267  pop     r13
0x14001d269  pop     rdi
0x14001d26a  pop     rbx
0x14001d26b  pop     rbp
0x14001d26c  retn
0x14001d26e  lea     rsi, [rdi+68h]
0x14001d272  mov     ebx, r13d
0x14001d275  cmp     ebx, 3
0x14001d278  jnb     loc_14001D359
0x14001d27e  movzx   ecx, word ptr [rsi]
0x14001d281  xorps   xmm0, xmm0
0x14001d284  mov     eax, ebx
0x14001d286  xorps   xmm1, xmm1
0x14001d289  shl     rax, 4
0x14001d28d  movzx   edx, word ptr [rax+r15+0C048h]
0x14001d296  lea     r10, [rax+0C048h]
0x14001d29d  shr     cx, 1
0x14001d2a0  shr     dx, 1
0x14001d2a3  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001d2a7  movups  xmmword ptr [rbp+String1.Length], xmm1
0x14001d2ab  jz      short loc_14001D2D3
0x14001d2ad  mov     r9, [rax+r15+0C050h]
0x14001d2b5  movzx   eax, dx
0x14001d2b8  movzx   r8d, word ptr [r9+rax*2-2]
0x14001d2be  cmp     r8w, 5Ch ; '\'
0x14001d2c3  jz      loc_14001D428
0x14001d2c9  test    r8w, r8w
0x14001d2cd  jz      loc_14001D428
0x14001d2d3  test    cx, cx
0x14001d2d6  jz      loc_14001D437
0x14001d2dc  mov     r9, [rsi+8]
0x14001d2e0  movzx   eax, cx
0x14001d2e3  movzx   r8d, word ptr [r9+rax*2-2]
0x14001d2e9  cmp     r8w, 5Ch ; '\'
0x14001d2ee  jz      loc_14001D7B2
0x14001d2f4  test    r8w, r8w
0x14001d2f8  jz      loc_14001D7B2
0x14001d2fe  cmp     cx, dx
0x14001d301  jz      short loc_14001D30A
0x14001d303  inc     ebx
0x14001d305  jmp     loc_14001D275
0x14001d30a  test    dx, dx
0x14001d30d  jz      short loc_14001D303
0x14001d30f  movups  xmm0, xmmword ptr [r10+r15]
0x14001d314  add     dx, dx
0x14001d317  add     cx, cx
0x14001d31a  mov     r8b, 1; CaseInSensitive
0x14001d31d  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001d321  mov     [rbp+String2.Length], dx
0x14001d325  lea     rdx, [rbp+String1]; String2
0x14001d329  movups  xmm0, xmmword ptr [rsi]
0x14001d32c  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001d330  mov     [rbp+String1.Length], cx
0x14001d334  lea     rcx, [rbp+String2]; String1
0x14001d338  call    cs:__imp_RtlCompareUnicodeString
0x14001d33f  nop     dword ptr [rax+rax+00h]
0x14001d344  test    eax, eax
0x14001d346  jz      loc_14001D24E
0x14001d34c  mov     r11d, 0FFFFh
0x14001d352  inc     ebx
0x14001d354  jmp     loc_14001D275
0x14001d359  mov     rcx, [rdi]
0x14001d35c  lea     rdx, [rdi+0B8h]
0x14001d363  call    cs:__imp_MupSurrogateCheckNegativeCache
0x14001d36a  nop     dword ptr [rax+rax+00h]
0x14001d36f  test    eax, eax
0x14001d371  jz      loc_14001D24E
0x14001d377  mov     r14, [rdi+0F0h]
0x14001d37e  lea     rbx, [rdi+0C8h]
0x14001d385  mov     [rsp+78h+var_8], r12
0x14001d38a  test    r14, r14
0x14001d38d  jnz     loc_14001D7C1
0x14001d393  mov     r14, cs:WPP_MAIN_CB.SecurityDescriptor
0x14001d39a  mov     rax, [rdi+50h]
0x14001d39e  mov     [rbp+String2.Buffer], rax
0x14001d3a2  movzx   eax, word ptr [rdi+4Ah]
0x14001d3a6  mov     [rbp+String2.MaximumLength], ax
0x14001d3aa  mov     dword ptr [rbp+String2+4], r13d
0x14001d3ae  mov     [rbp+String2.Length], r13w
0x14001d3b3  call    cs:__imp_KeEnterCriticalRegion
0x14001d3ba  nop     dword ptr [rax+rax+00h]
0x14001d3bf  mov     dl, 1; Wait
0x14001d3c1  lea     rcx, [r14+38h]; Resource
0x14001d3c5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001d3cc  nop     dword ptr [rax+rax+00h]
0x14001d3d1  xor     r8d, r8d; CaseInsensitiveIndex
0x14001d3d4  lea     rdx, [rdi+48h]; FullName
0x14001d3d8  mov     rcx, r14; PrefixTable
0x14001d3db  call    cs:__imp_RtlFindUnicodePrefix
0x14001d3e2  nop     dword ptr [rax+rax+00h]
0x14001d3e7  test    rax, rax
0x14001d3ea  jz      loc_14001D91F
0x14001d3f0  test    byte ptr [rax-3Ch], 1
0x14001d3f4  lea     rbx, [rax-48h]
0x14001d3f8  jnz     short loc_14001D445
0x14001d3fa  lea     rcx, [r14+38h]; Resource
0x14001d3fe  call    cs:__imp_ExReleaseResourceLite
0x14001d405  nop     dword ptr [rax+rax+00h]
0x14001d40a  call    cs:__imp_KeLeaveCriticalRegion
0x14001d411  nop     dword ptr [rax+rax+00h]
0x14001d416  lea     rbx, [rdi+0C8h]
0x14001d41d  mov     r13d, 2
0x14001d423  jmp     loc_14001D735
0x14001d428  add     dx, r11w
0x14001d42c  jnz     loc_14001D2B5
0x14001d432  jmp     loc_14001D2D3
0x14001d437  test    dx, dx
0x14001d43a  jnz     loc_14001D303
0x14001d440  jmp     loc_14001D24E
0x14001d445  movzx   edx, word ptr [rdi+48h]
0x14001d449  mov     r13d, 2
0x14001d44f  movzx   r8d, word ptr [rbx+90h]
0x14001d457  cmp     r8w, dx
0x14001d45b  jnb     loc_14001D7CD
0x14001d461  mov     rax, [rdi+50h]
0x14001d465  mov     ecx, r8d
0x14001d468  shr     rcx, 1
0x14001d46b  sub     dx, r8w
0x14001d46f  mov     [rbp+String2.Length], dx
0x14001d473  lea     rcx, [rax+rcx*2]
0x14001d477  mov     [rbp+String2.Buffer], rcx
0x14001d47b  lock inc dword ptr [rbx+4]
0x14001d47f  lea     rcx, [r14+38h]; Resource
0x14001d483  call    cs:__imp_ExReleaseResourceLite
0x14001d48a  nop     dword ptr [rax+rax+00h]
0x14001d48f  call    cs:__imp_KeLeaveCriticalRegion
0x14001d496  nop     dword ptr [rax+rax+00h]
0x14001d49b  call    cs:__imp_KeEnterCriticalRegion
0x14001d4a2  nop     dword ptr [rax+rax+00h]
0x14001d4a7  mov     dl, 1; Wait
0x14001d4a9  lea     rcx, [r14+0A0h]; Resource
0x14001d4b0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001d4b7  nop     dword ptr [rax+rax+00h]
0x14001d4bc  cmp     r14, [rbx+40h]
0x14001d4c0  jnz     short loc_14001D51A
0x14001d4c2  mov     rax, [rbx+30h]
0x14001d4c6  lea     rcx, [rbx+30h]
0x14001d4ca  test    rax, rax
0x14001d4cd  jz      short loc_14001D4F4
0x14001d4cf  cmp     [rax+8], rcx
0x14001d4d3  jnz     loc_14001D7FA
0x14001d4d9  mov     rdx, [rcx+8]
0x14001d4dd  cmp     [rdx], rcx
0x14001d4e0  jnz     loc_14001D7FA
0x14001d4e6  mov     [rdx], rax
0x14001d4e9  mov     [rax+8], rdx
0x14001d4ed  mov     qword ptr [rcx], 0
0x14001d4f4  test    byte ptr [rbx+0Ch], 1
0x14001d4f8  jz      short loc_14001D51A
0x14001d4fa  mov     rdx, [r14+18h]
0x14001d4fe  lea     rax, [r14+18h]
0x14001d502  cmp     [rdx+8], rax
0x14001d506  jnz     loc_14001D7FA
0x14001d50c  mov     [rcx], rdx
0x14001d50f  mov     [rcx+8], rax
0x14001d513  mov     [rdx+8], rcx
0x14001d517  mov     [rax], rcx
0x14001d51a  lea     rcx, [r14+0A0h]; Resource
0x14001d521  call    cs:__imp_ExReleaseResourceLite
0x14001d528  nop     dword ptr [rax+rax+00h]
0x14001d52d  call    cs:__imp_KeLeaveCriticalRegion
0x14001d534  nop     dword ptr [rax+rax+00h]
0x14001d539  mov     edx, 28h ; '('
0x14001d53e  mov     ecx, 102h
0x14001d543  mov     r8d, 62436644h
0x14001d549  call    cs:__imp_ExAllocatePool2
0x14001d550  nop     dword ptr [rax+rax+00h]
0x14001d555  mov     r14, rax
0x14001d558  test    rax, rax
0x14001d55b  jz      loc_14001D726
0x14001d561  mov     qword ptr [rax+8], 0
0x14001d569  mov     rcx, rax
0x14001d56c  mov     qword ptr [rax+18h], 0
0x14001d574  mov     qword ptr [rax+20h], 0
0x14001d57c  mov     dword ptr [rax], 288103h
0x14001d582  mov     dword ptr [rax+4], 1
0x14001d589  mov     [rax+10h], rbx
0x14001d58d  call    DfscRmIsTimeToRefresh
0x14001d592  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d599  lea     r10, WPP_GLOBAL_Control
0x14001d5a0  cmp     rcx, r10
0x14001d5a3  jz      short loc_14001D5B2
0x14001d5a5  test    dword ptr [rcx+2Ch], 400000h
0x14001d5ac  jnz     loc_14001D801
0x14001d5b2  cmp     dword ptr [rbx+8], 0
0x14001d5b6  jz      loc_14001D836
0x14001d5bc  lea     r15, [rdi+0C8h]
0x14001d5c3  mov     word ptr [r14+20h], 0FFFFh
0x14001d5ca  test    r15, r15
0x14001d5cd  jz      short loc_14001D5D7
0x14001d5cf  movups  xmm0, xmmword ptr [rbp+String2.Length]
0x14001d5d3  movups  xmmword ptr [r15], xmm0
0x14001d5d7  mov     r8, [rbp+arg_8]
0x14001d5db  mov     rax, [rbp+arg_10]
0x14001d5df  mov     [r8], r14
0x14001d5e2  xor     r14d, r14d
0x14001d5e5  movzx   ecx, word ptr [rdi+48h]
0x14001d5e9  movzx   edx, word ptr [rdi+58h]
0x14001d5ed  mov     [rax], r13d
0x14001d5f0  cmp     dx, cx
0x14001d5f3  ja      loc_14001D84A
0x14001d5f9  movzx   edx, word ptr [rdi+0C8h]
0x14001d600  movzx   r9d, word ptr [rdi+0D8h]
0x14001d608  cmp     r9w, dx
0x14001d60c  jbe     loc_14001D775
0x14001d612  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d619  cmp     rcx, r10
0x14001d61c  jz      short loc_14001D62B
0x14001d61e  test    dword ptr [rcx+2Ch], 400000h
0x14001d625  jnz     loc_14001D8BD
0x14001d62b  movzx   eax, word ptr [rdi+0C8h]
0x14001d632  mov     [rdi+0D8h], ax
0x14001d639  movzx   ecx, word ptr [r15]
0x14001d63d  lea     rbx, [rsi+20h]
0x14001d641  mov     rax, [rdi+60h]
  ... truncated ...
```
