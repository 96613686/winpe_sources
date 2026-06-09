# DfscCmInitState

- ea: `0x14001fb50`
- end: `0x140020655`
- name: `DfscCmInitState`
- size: `2821`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400015c0`
- `0x14001d9b0`

## callees

- `0x140002340`
- `0x1400025a0`
- `0x1400025f4`
- `0x140002aa0`
- `0x140002b18`
- `0x140002fcc`
- `0x1400050fc`
- `0x14001c8ac`
- `0x14001cfd0`
- `0x14001d090`
- `0x14001f540`
- `0x14001fb50`
- `0x140028680`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400205b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400205b0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001fc7c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001fdf3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001fc7c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001fdf3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fed6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ffc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020063`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fed6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ffc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020063`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001feca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ffbd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140020057`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001feca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ffbd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140020057`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001fea0`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001fea0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001fe8a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001ffea`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001fe8a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001ffea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fe78`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ffd5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001fe78`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ffd5`
- `ntoskrnl!ExAllocatePool2` at `0x14002007f`
- `ntoskrnl!ExAllocatePool2` at `0x14002007f`
- `MUP!MupSurrogateCheckNegativeCache` at `0x14001fe1e`
- `MUP!MupSurrogateCheckNegativeCache` at `0x14001fe1e`

## pseudocode

```c
__int64 __fastcall DfscCmInitState(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int v3; // ebx
  unsigned __int64 v4; // rcx
  unsigned __int16 v5; // ax
  unsigned __int16 v6; // dx
  wchar_t v7; // r8
  __int16 v8; // r8
  __int64 v9; // r13
  int v10; // edi
  unsigned int v11; // ebx
  __int64 result; // rax
  UNICODE_STRING *v13; // rsi
  unsigned int v14; // ebx
  __int64 v15; // rax
  unsigned __int16 v16; // cx
  unsigned __int16 v17; // dx
  wchar_t v18; // r8
  __int16 v19; // r8
  __int64 v20; // rax
  char *SecurityDescriptor; // r13
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _RTL_SPLAY_LINKS **p_RightChild; // rbx
  _QWORD *v24; // rsi
  int v25; // ebx
  unsigned __int64 v26; // rdx
  unsigned int v27; // r8d
  __int64 v28; // rax
  struct _RTL_SPLAY_LINKS *v29; // rax
  struct _RTL_SPLAY_LINKS *v30; // rcx
  struct _RTL_SPLAY_LINKS *v31; // rdx
  struct _RTL_SPLAY_LINKS *v32; // rdx
  struct _RTL_SPLAY_LINKS *v33; // rax
  __int64 Pool2; // rax
  __int64 v35; // r12
  int v36; // edx
  int v37; // r8d
  UNICODE_STRING *v38; // r15
  __int64 v39; // rcx
  unsigned __int16 v40; // dx
  int v41; // edx
  __int64 v42; // r9
  USHORT Length; // cx
  _WORD *v44; // rax
  char v45; // r10
  __int64 v46; // r9
  __int64 v47; // rcx
  unsigned int v48; // r8d
  __int64 v49; // rax
  unsigned __int64 v50; // rdx
  bool v51; // zf
  WCHAR *v52; // rdx
  __int16 v53; // r8
  UNICODE_STRING String2; // [rsp+40h] [rbp-30h] BYREF
  __int128 v55; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-10h] BYREF
  struct _UNICODE_STRING *DestinationString; // [rsp+C0h] [rbp+50h]

  if ( *(_WORD *)(a1 + 290) > 0x10u )
  {
    v9 = a1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1);
    }
    v11 = 9;
    v10 = -1073741634;
    goto LABEL_26;
  }
  if ( !*(_WORD *)(a1 + 32) )
  {
    v11 = 9;
    *(_DWORD *)(a1 + 324) = 2;
    v10 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v9 = a1;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1);
      }
      goto LABEL_26;
    }
LABEL_50:
    v9 = a1;
    goto LABEL_26;
  }
  v2 = a1 + 8;
  *(_QWORD *)(a1 + 216) = 0;
  *(_DWORD *)(a1 + 208) = 0;
  v55 = 0;
  v3 = 0;
  while ( v3 < 4 )
  {
    v4 = 16LL * v3;
    v5 = *(_WORD *)(v2 + 120) >> 1;
    v6 = asc_14000C080[v4 / 2] >> 1;
    String1 = 0;
    for ( String2 = 0; v6; --v6 )
    {
      v7 = (&off_14000C088)[v4 / 8][v6 - 1];
      if ( v7 != 92 && v7 )
        break;
    }
    if ( v5 )
    {
      while ( 1 )
      {
        v8 = *(_WORD *)(*(_QWORD *)(v2 + 128) + 2LL * v5 - 2);
        if ( v8 != 92 )
        {
          if ( v8 )
            break;
        }
        if ( !--v5 )
          goto LABEL_18;
      }
      if ( v5 != v6 || !v6 )
        goto LABEL_12;
      String1 = *(UNICODE_STRING *)(v4 + 49280 + 0x140000000LL);
      String1.Length = 2 * v6;
      String2 = *(UNICODE_STRING *)(v2 + 120);
      String2.Length = 2 * v5;
      if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
        goto LABEL_19;
      ++v3;
    }
    else
    {
LABEL_18:
      if ( !v6 )
        goto LABEL_19;
LABEL_12:
      ++v3;
    }
  }
  v13 = (UNICODE_STRING *)(v2 + 104);
  v14 = 0;
  while ( v14 < 3 )
  {
    v15 = 2LL * v14;
    v16 = v13->Length >> 1;
    v17 = LOWORD(qword_14000C048[v15]) >> 1;
    String2 = 0;
    for ( String1 = 0; v17; --v17 )
    {
      v18 = (&off_14000C050)[v15][v17 - 1];
      if ( v18 != 92 && v18 )
        break;
    }
    if ( v16 )
    {
      while ( 1 )
      {
        v19 = *(_WORD *)(*(_QWORD *)(v2 + 112) + 2LL * v16 - 2);
        if ( v19 != 92 )
        {
          if ( v19 )
            break;
        }
        if ( !--v16 )
          goto LABEL_53;
      }
      if ( v16 != v17 || !v17 )
        goto LABEL_36;
      String2 = *(UNICODE_STRING *)(v15 * 8 + 49224 + 0x140000000LL);
      String2.Length = 2 * v17;
      String1 = *v13;
      String1.Length = 2 * v16;
      if ( !RtlCompareUnicodeString(&String2, &String1, 1u) )
        goto LABEL_19;
      ++v14;
    }
    else
    {
LABEL_53:
      if ( !v17 )
        goto LABEL_19;
LABEL_36:
      ++v14;
    }
  }
  if ( !(unsigned int)MupSurrogateCheckNegativeCache(*(_QWORD *)v2, v2 + 184) )
  {
LABEL_19:
    v9 = a1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1);
      }
    }
    *(_DWORD *)(a1 + 324) = 2;
    v10 = -1073741823;
    v11 = 9;
    goto LABEL_26;
  }
  DestinationString = (struct _UNICODE_STRING *)(v2 + 200);
  v20 = *(_QWORD *)(v2 + 240);
  if ( v20 )
    SecurityDescriptor = *(char **)(v20 + 136);
  else
    SecurityDescriptor = (char *)WPP_MAIN_CB.SecurityDescriptor;
  String2.Buffer = *(PWSTR *)(v2 + 80);
  String2.MaximumLength = *(_WORD *)(v2 + 74);
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String2.Length = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(SecurityDescriptor + 56), 1u);
  UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)SecurityDescriptor, (PCUNICODE_STRING)(v2 + 72), 0);
  if ( !UnicodePrefix
    || (p_RightChild = &UnicodePrefix[-2].Links.RightChild, (BYTE4(UnicodePrefix[-2].Prefix) & 1) == 0) )
  {
    ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 56));
    KeLeaveCriticalRegion();
    goto LABEL_46;
  }
  v26 = *(unsigned __int16 *)(v2 + 72);
  v27 = *((unsigned __int16 *)p_RightChild + 72);
  if ( (unsigned __int16)v27 >= (unsigned __int16)v26 )
  {
    if ( (_WORD)v27 == (_WORD)v26 )
    {
      v49 = *(_QWORD *)(v2 + 80) - 2LL;
      v50 = v26 >> 1;
      v51 = *(_WORD *)(v49 + 2 * v50) == 92;
      v52 = (WCHAR *)(v49 + 2 * v50);
      if ( v51 )
      {
        String2.Length = 2;
        String2.Buffer = v52;
      }
    }
  }
  else
  {
    v28 = *(_QWORD *)(v2 + 80);
    String2.Length = v26 - v27;
    String2.Buffer = (PWSTR)(v28 + 2 * ((unsigned __int64)v27 >> 1));
  }
  _InterlockedIncrement((volatile signed __int32 *)p_RightChild + 1);
  ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 56));
  KeLeaveCriticalRegion();
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(SecurityDescriptor + 160), 1u);
  if ( SecurityDescriptor == (char *)p_RightChild[8] )
  {
    v29 = p_RightChild[6];
    v30 = (struct _RTL_SPLAY_LINKS *)(p_RightChild + 6);
    if ( !v29 )
      goto LABEL_64;
    if ( v29->LeftChild != v30 )
      goto LABEL_124;
    v31 = p_RightChild[7];
    if ( v31->Parent != v30 )
      goto LABEL_124;
    v31->Parent = v29;
    v29->LeftChild = v31;
    v30->Parent = 0;
LABEL_64:
    if ( (*((_BYTE *)p_RightChild + 12) & 1) != 0 )
    {
      v32 = (struct _RTL_SPLAY_LINKS *)*((_QWORD *)SecurityDescriptor + 3);
      v33 = (struct _RTL_SPLAY_LINKS *)(SecurityDescriptor + 24);
      if ( (char *)v32->LeftChild == SecurityDescriptor + 24 )
      {
        v30->Parent = v32;
        p_RightChild[7] = v33;
        v32->LeftChild = v30;
        v33->Parent = v30;
        goto LABEL_67;
      }
LABEL_124:
      __fastfail(3u);
    }
  }
LABEL_67:
  ExReleaseResourceLite((PERESOURCE)(SecurityDescriptor + 160));
  KeLeaveCriticalRegion();
  Pool2 = ExAllocatePool2(258, 40, 1648584260);
  v35 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_QWORD *)(Pool2 + 24) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_DWORD *)Pool2 = 2654467;
    *(_DWORD *)(Pool2 + 4) = 1;
    *(_QWORD *)(Pool2 + 16) = p_RightChild;
    DfscRmIsTimeToRefresh(Pool2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_qqDZ(
        WPP_GLOBAL_Control->AttachedDevice,
        v36,
        v37,
        v35,
        *(_QWORD *)(v35 + 16),
        *(_DWORD *)(v35 + 8),
        (__int64)(p_RightChild + 18));
    }
    if ( !*((_DWORD *)p_RightChild + 2) && !*((_WORD *)p_RightChild + 12) )
      *(_DWORD *)(v35 + 8) |= 2u;
    v38 = (UNICODE_STRING *)(v2 + 200);
    *(_WORD *)(v35 + 32) = -1;
    if ( v2 != -200 )
      *v38 = String2;
    v9 = a1;
    *(_QWORD *)(a1 + 272) = v35;
    v39 = *(unsigned __int16 *)(v2 + 72);
    v40 = *(_WORD *)(v2 + 88);
    if ( v40 > (unsigned __int16)v39 )
    {
      v53 = *(_WORD *)(v2 + 200);
      if ( !v53 )
        *(_QWORD *)(v2 + 208) = *(_QWORD *)(v2 + 80) + v39;
      *(_WORD *)(v2 + 200) = v40 + v53 - v39;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          (unsigned int)WPP_55706db06074317498eaf8c01331c814_Traceguids,
          v2 + 88,
          v2 + 200);
      }
    }
    v41 = *(unsigned __int16 *)(v2 + 200);
    v42 = *(unsigned __int16 *)(v2 + 216);
    if ( (unsigned __int16)v42 <= (unsigned __int16)v41 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_55706db06074317498eaf8c01331c814_Traceguids, v42, v41);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_55706db06074317498eaf8c01331c814_Traceguids, v42, v41);
      }
      *(_WORD *)(v2 + 216) = *(_WORD *)(v2 + 200);
    }
    Length = v38->Length;
    *((_QWORD *)&v55 + 1) = *(_QWORD *)(v2 + 96);
    LOWORD(v55) = *(_WORD *)(v2 + 88) - Length;
    WORD1(v55) = *(_WORD *)(v2 + 90) - Length;
    *(_OWORD *)(v2 + 184) = v55;
    if ( (int)DfscGetPathComponents(
                (__int16 *)(v2 + 184),
                (struct _UNICODE_STRING *)(v2 + 104),
                (struct _UNICODE_STRING *)(v2 + 120),
                (struct _UNICODE_STRING *)(v2 + 152),
                (PUNICODE_STRING)(v2 + 136)) >= 0
      && v2 != -104
      && v13->Length
      && (v44 = *(_WORD **)(v2 + 112)) != 0
      && *v44 )
    {
      if ( !*(_WORD *)(v2 + 136) )
        goto LABEL_92;
      v45 = 0;
      v46 = *((_QWORD *)&v55 + 1);
      v47 = ((unsigned __int16)v55 >> 1) - 1;
      v48 = *(unsigned __int16 *)(v2 + 152) >> 1;
      *(_QWORD *)(v2 + 176) = *((_QWORD *)&v55 + 1);
      if ( (unsigned int)v47 < v48 )
        goto LABEL_92;
      do
      {
        if ( *(_WORD *)(v46 + 2 * v47) == 58 )
        {
          v45 = 1;
          *(_WORD *)(v2 + 170) = 2 * v47;
          *(_WORD *)(v2 + 168) = 2 * v47;
        }
        if ( *(_WORD *)(v46 + 2 * v47) == 92 )
          break;
        v47 = (unsigned int)(v47 - 1);
      }
      while ( (unsigned int)v47 >= v48 );
      if ( !v45 )
LABEL_92:
        *(_OWORD *)(v2 + 168) = v55;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1bce9a35ce9f35cd7964d25412ee5844_Traceguids, &v55);
    }
    v24 = (_QWORD *)(a1 + 272);
    v10 = 0;
LABEL_113:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, v9, *v24);
    }
    if ( *v24 && !*(_DWORD *)(*(_QWORD *)(*v24 + 16LL) + 8LL) && (unsigned __int8)DfscIsSpecialShare(v9 + 32) )
      v11 = 4;
    else
      v11 = 1;
    goto LABEL_26;
  }
  DfscRmDereferenceReferral((volatile signed __int32 *)p_RightChild);
LABEL_46:
  v24 = (_QWORD *)(a1 + 272);
  v25 = 0;
  v10 = DfscDomainCacheLookup(v2, v2 + 8, a1 + 272);
  if ( v10 >= 0 )
  {
    v25 = 2;
    RtlInitUnicodeString(DestinationString, 0);
  }
  if ( v10 )
  {
    v11 = 3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v9 = a1;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1, v10);
      goto LABEL_26;
    }
    goto LABEL_50;
  }
  if ( v25 )
  {
    v9 = a1;
    goto LABEL_113;
  }
  v9 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1);
  v11 = 3;
LABEL_26:
  result = v11;
  *(_DWORD *)(v9 + 316) = v10;
  return result;
}

```

## disassembly

```asm
0x14001fb50  mov     [rsp-38h+arg_18], rbx
0x14001fb55  mov     [rsp-38h+arg_0], rcx
0x14001fb5a  push    rbp
0x14001fb5b  push    rsi
0x14001fb5c  push    rdi
0x14001fb5d  push    r12
0x14001fb5f  push    r13
0x14001fb61  push    r14
0x14001fb63  push    r15
0x14001fb65  mov     rbp, rsp
0x14001fb68  sub     rsp, 70h
0x14001fb6c  cmp     word ptr [rcx+122h], 10h
0x14001fb74  mov     r14, rcx
0x14001fb77  ja      loc_140020323
0x14001fb7d  cmp     word ptr [rcx+20h], 0
0x14001fb82  jz      loc_1400202AD
0x14001fb88  xor     r12d, r12d
0x14001fb8b  lea     rdi, [rcx+8]
0x14001fb8f  xorps   xmm0, xmm0
0x14001fb92  mov     [rcx+0D8h], r12
0x14001fb99  mov     [rcx+0D0h], r12d
0x14001fba0  lea     r15, cs:140000000h
0x14001fba7  movups  [rbp+var_20], xmm0
0x14001fbab  mov     ebx, r12d
0x14001fbae  mov     r11d, 0FFFFh
0x14001fbb4  cmp     ebx, 4
0x14001fbb7  jnb     loc_14001FD21
0x14001fbbd  movzx   eax, word ptr [rdi+78h]
0x14001fbc1  xorps   xmm0, xmm0
0x14001fbc4  mov     ecx, ebx
0x14001fbc6  xorps   xmm1, xmm1
0x14001fbc9  shl     rcx, 4
0x14001fbcd  movzx   edx, word ptr [rcx+r15+0C080h]
0x14001fbd6  lea     r10, [rcx+0C080h]
0x14001fbdd  shr     ax, 1
0x14001fbe0  shr     dx, 1
0x14001fbe3  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001fbe7  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14001fbeb  jz      short loc_14001FC13
0x14001fbed  mov     r9, [rcx+r15+0C088h]
0x14001fbf5  movzx   ecx, dx
0x14001fbf8  movzx   r8d, word ptr [r9+rcx*2-2]
0x14001fbfe  cmp     r8w, 5Ch ; '\'
0x14001fc03  jz      loc_14001FC99
0x14001fc09  test    r8w, r8w
0x14001fc0d  jz      loc_14001FC99
0x14001fc13  test    ax, ax
0x14001fc16  jz      loc_14001FCA8
0x14001fc1c  mov     r9, [rdi+80h]
0x14001fc23  movzx   ecx, ax
0x14001fc26  movzx   r8d, word ptr [r9+rcx*2-2]
0x14001fc2c  cmp     r8w, 5Ch ; '\'
0x14001fc31  jz      loc_140020252
0x14001fc37  test    r8w, r8w
0x14001fc3b  jz      loc_140020252
0x14001fc41  cmp     ax, dx
0x14001fc44  jz      short loc_14001FC4D
0x14001fc46  inc     ebx
0x14001fc48  jmp     loc_14001FBB4
0x14001fc4d  test    dx, dx
0x14001fc50  jz      short loc_14001FC46
0x14001fc52  movups  xmm0, xmmword ptr [r10+r15]
0x14001fc57  add     dx, dx
0x14001fc5a  lea     rcx, [rbp+String1]; String1
0x14001fc5e  add     ax, ax
0x14001fc61  mov     r8b, 1; CaseInSensitive
0x14001fc64  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001fc68  mov     [rbp+String1.Length], dx
0x14001fc6c  lea     rdx, [rbp+String2]; String2
0x14001fc70  movups  xmm0, xmmword ptr [rdi+78h]
0x14001fc74  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001fc78  mov     [rbp+String2.Length], ax
0x14001fc7c  call    cs:__imp_RtlCompareUnicodeString
0x14001fc83  nop     dword ptr [rax+rax+00h]
0x14001fc88  test    eax, eax
0x14001fc8a  jz      short loc_14001FCAD
0x14001fc8c  mov     r11d, 0FFFFh
0x14001fc92  inc     ebx
0x14001fc94  jmp     loc_14001FBB4
0x14001fc99  add     dx, r11w
0x14001fc9d  jnz     loc_14001FBF5
0x14001fca3  jmp     loc_14001FC13
0x14001fca8  test    dx, dx
0x14001fcab  jnz     short loc_14001FC46
0x14001fcad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fcb4  lea     r14, WPP_GLOBAL_Control
0x14001fcbb  mov     r13, [rbp+arg_0]
0x14001fcbf  cmp     rcx, r14
0x14001fcc2  jz      short loc_14001FCEA
0x14001fcc4  test    dword ptr [rcx+2Ch], 200000h
0x14001fccb  jnz     loc_14002042D
0x14001fcd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fcd8  cmp     rcx, r14
0x14001fcdb  jz      short loc_14001FCEA
0x14001fcdd  test    dword ptr [rcx+2Ch], 400000h
0x14001fce4  jnz     loc_14002044A
0x14001fcea  mov     dword ptr [r13+144h], 2
0x14001fcf5  mov     edi, 0C0000001h
0x14001fcfa  mov     ebx, 9
0x14001fcff  mov     eax, ebx
0x14001fd01  mov     [r13+13Ch], edi
0x14001fd08  mov     rbx, [rsp+70h+arg_18]
0x14001fd10  add     rsp, 70h
0x14001fd14  pop     r15
0x14001fd16  pop     r14
0x14001fd18  pop     r13
0x14001fd1a  pop     r12
0x14001fd1c  pop     rdi
0x14001fd1d  pop     rsi
0x14001fd1e  pop     rbp
0x14001fd1f  retn
0x14001fd21  lea     rsi, [rdi+68h]
0x14001fd25  mov     ebx, r12d
0x14001fd28  nop     dword ptr [rax+rax+00000000h]
0x14001fd30  cmp     ebx, 3
0x14001fd33  jnb     loc_14001FE14
0x14001fd39  movzx   ecx, word ptr [rsi]
0x14001fd3c  xorps   xmm0, xmm0
0x14001fd3f  mov     eax, ebx
0x14001fd41  xorps   xmm1, xmm1
0x14001fd44  shl     rax, 4
0x14001fd48  movzx   edx, word ptr [rax+r15+0C048h]
0x14001fd51  lea     r10, [rax+0C048h]
0x14001fd58  shr     cx, 1
0x14001fd5b  shr     dx, 1
0x14001fd5e  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001fd62  movups  xmmword ptr [rbp+String1.Length], xmm1
0x14001fd66  jz      short loc_14001FD8E
0x14001fd68  mov     r9, [rax+r15+0C050h]
0x14001fd70  movzx   eax, dx
0x14001fd73  movzx   r8d, word ptr [r9+rax*2-2]
0x14001fd79  cmp     r8w, 5Ch ; '\'
0x14001fd7e  jz      loc_14001FF30
0x14001fd84  test    r8w, r8w
0x14001fd88  jz      loc_14001FF30
0x14001fd8e  test    cx, cx
0x14001fd91  jz      loc_14001FF3F
0x14001fd97  mov     r9, [rsi+8]
0x14001fd9b  movzx   eax, cx
0x14001fd9e  movzx   r8d, word ptr [r9+rax*2-2]
0x14001fda4  cmp     r8w, 5Ch ; '\'
0x14001fda9  jz      loc_14002029E
0x14001fdaf  test    r8w, r8w
0x14001fdb3  jz      loc_14002029E
0x14001fdb9  cmp     cx, dx
0x14001fdbc  jz      short loc_14001FDC5
0x14001fdbe  inc     ebx
0x14001fdc0  jmp     loc_14001FD30
0x14001fdc5  test    dx, dx
0x14001fdc8  jz      short loc_14001FDBE
0x14001fdca  movups  xmm0, xmmword ptr [r10+r15]
0x14001fdcf  add     dx, dx
0x14001fdd2  add     cx, cx
0x14001fdd5  mov     r8b, 1; CaseInSensitive
0x14001fdd8  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001fddc  mov     [rbp+String2.Length], dx
0x14001fde0  lea     rdx, [rbp+String1]; String2
0x14001fde4  movups  xmm0, xmmword ptr [rsi]
0x14001fde7  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001fdeb  mov     [rbp+String1.Length], cx
0x14001fdef  lea     rcx, [rbp+String2]; String1
0x14001fdf3  call    cs:__imp_RtlCompareUnicodeString
0x14001fdfa  nop     dword ptr [rax+rax+00h]
0x14001fdff  test    eax, eax
0x14001fe01  jz      loc_14001FCAD
0x14001fe07  mov     r11d, 0FFFFh
0x14001fe0d  inc     ebx
0x14001fe0f  jmp     loc_14001FD30
0x14001fe14  mov     rcx, [rdi]
0x14001fe17  lea     rdx, [rdi+0B8h]
0x14001fe1e  call    cs:__imp_MupSurrogateCheckNegativeCache
0x14001fe25  nop     dword ptr [rax+rax+00h]
0x14001fe2a  test    eax, eax
0x14001fe2c  jz      loc_14001FCAD
0x14001fe32  lea     rax, [r14+110h]
0x14001fe39  mov     [rbp+arg_8], rax
0x14001fe3d  lea     rax, [rdi+0C8h]
0x14001fe44  mov     [rbp+DestinationString], rax
0x14001fe48  mov     rax, [rdi+0F0h]
0x14001fe4f  test    rax, rax
0x14001fe52  jnz     loc_14002034D
0x14001fe58  mov     r13, cs:WPP_MAIN_CB.SecurityDescriptor
0x14001fe5f  mov     rax, [rdi+50h]
0x14001fe63  mov     [rbp+String2.Buffer], rax
0x14001fe67  movzx   eax, word ptr [rdi+4Ah]
0x14001fe6b  mov     [rbp+String2.MaximumLength], ax
0x14001fe6f  mov     dword ptr [rbp+String2+4], r12d
0x14001fe73  mov     [rbp+String2.Length], r12w
0x14001fe78  call    cs:__imp_KeEnterCriticalRegion
0x14001fe7f  nop     dword ptr [rax+rax+00h]
0x14001fe84  mov     dl, 1; Wait
0x14001fe86  lea     rcx, [r13+38h]; Resource
0x14001fe8a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001fe91  nop     dword ptr [rax+rax+00h]
0x14001fe96  xor     r8d, r8d; CaseInsensitiveIndex
0x14001fe99  lea     rdx, [rdi+48h]; FullName
0x14001fe9d  mov     rcx, r13; PrefixTable
0x14001fea0  call    cs:__imp_RtlFindUnicodePrefix
0x14001fea7  nop     dword ptr [rax+rax+00h]
0x14001feac  lea     r14, WPP_GLOBAL_Control
0x14001feb3  test    rax, rax
0x14001feb6  jz      short loc_14001FEC6
0x14001feb8  test    byte ptr [rax-3Ch], 1
0x14001febc  lea     rbx, [rax-48h]
0x14001fec0  jnz     loc_14001FF7F
0x14001fec6  lea     rcx, [r13+38h]; Resource
0x14001feca  call    cs:__imp_ExReleaseResourceLite
0x14001fed1  nop     dword ptr [rax+rax+00h]
0x14001fed6  call    cs:__imp_KeLeaveCriticalRegion
0x14001fedd  nop     dword ptr [rax+rax+00h]
0x14001fee2  mov     r15d, 2
0x14001fee8  mov     rsi, [rbp+arg_8]
0x14001feec  lea     rdx, [rdi+8]
0x14001fef0  mov     r8, rsi
0x14001fef3  mov     rcx, rdi
0x14001fef6  xor     ebx, ebx
0x14001fef8  call    DfscDomainCacheLookup
0x14001fefd  mov     edi, eax
0x14001feff  test    eax, eax
0x14001ff01  jns     loc_1400205A7
0x14001ff07  test    edi, edi
0x14001ff09  jz      loc_140020359
0x14001ff0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ff16  lea     r14, WPP_GLOBAL_Control
0x14001ff1d  mov     ebx, 3
0x14001ff22  cmp     rcx, r14
0x14001ff25  jnz     short loc_14001FF4D
0x14001ff27  mov     r13, [rbp+arg_0]
0x14001ff2b  jmp     loc_14001FCFF
0x14001ff30  add     dx, r11w
0x14001ff34  jnz     loc_14001FD70
0x14001ff3a  jmp     loc_14001FD8E
0x14001ff3f  test    dx, dx
0x14001ff42  jnz     loc_14001FDBE
0x14001ff48  jmp     loc_14001FCAD
0x14001ff4d  test    dword ptr [rcx+2Ch], 200000h
0x14001ff54  mov     r13, [rbp+arg_0]
0x14001ff58  jz      loc_14001FCFF
0x14001ff5e  mov     rcx, [rcx+18h]
0x14001ff62  lea     r8, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids
0x14001ff69  mov     edx, 12h
0x14001ff6e  mov     dword ptr [rsp+70h+var_50], edi
0x14001ff72  mov     r9, r13
0x14001ff75  call    WPP_SF_qD
0x14001ff7a  jmp     loc_14001FCFF
0x14001ff7f  movzx   edx, word ptr [rdi+48h]
0x14001ff83  mov     r15d, 2
0x14001ff89  movzx   r8d, word ptr [rbx+90h]
0x14001ff91  cmp     r8w, dx
0x14001ff95  jnb     loc_140020467
0x14001ff9b  mov     rax, [rdi+50h]
0x14001ff9f  mov     ecx, r8d
0x14001ffa2  shr     rcx, 1
0x14001ffa5  sub     dx, r8w
0x14001ffa9  mov     [rbp+String2.Length], dx
0x14001ffad  lea     rcx, [rax+rcx*2]
0x14001ffb1  mov     [rbp+String2.Buffer], rcx
0x14001ffb5  lock inc dword ptr [rbx+4]
0x14001ffb9  lea     rcx, [r13+38h]; Resource
0x14001ffbd  call    cs:__imp_ExReleaseResourceLite
0x14001ffc4  nop     dword ptr [rax+rax+00h]
0x14001ffc9  call    cs:__imp_KeLeaveCriticalRegion
0x14001ffd0  nop     dword ptr [rax+rax+00h]
0x14001ffd5  call    cs:__imp_KeEnterCriticalRegion
0x14001ffdc  nop     dword ptr [rax+rax+00h]
0x14001ffe1  mov     dl, 1; Wait
0x14001ffe3  lea     rcx, [r13+0A0h]; Resource
0x14001ffea  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001fff1  nop     dword ptr [rax+rax+00h]
0x14001fff6  cmp     r13, [rbx+40h]
0x14001fffa  jnz     short loc_140020050
0x14001fffc  mov     rax, [rbx+30h]
0x140020000  lea     rcx, [rbx+30h]
0x140020004  test    rax, rax
0x140020007  jz      short loc_14002002A
0x140020009  cmp     [rax+8], rcx
0x14002000d  jnz     loc_140020494
0x140020013  mov     rdx, [rcx+8]
0x140020017  cmp     [rdx], rcx
0x14002001a  jnz     loc_140020494
0x140020020  mov     [rdx], rax
0x140020023  mov     [rax+8], rdx
0x140020027  mov     [rcx], r12
0x14002002a  test    byte ptr [rbx+0Ch], 1
0x14002002e  jz      short loc_140020050
0x140020030  mov     rdx, [r13+18h]
0x140020034  lea     rax, [r13+18h]
0x140020038  cmp     [rdx+8], rax
0x14002003c  jnz     loc_140020494
0x140020042  mov     [rcx], rdx
0x140020045  mov     [rcx+8], rax
0x140020049  mov     [rdx+8], rcx
0x14002004d  mov     [rax], rcx
0x140020050  lea     rcx, [r13+0A0h]; Resource
0x140020057  call    cs:__imp_ExReleaseResourceLite
0x14002005e  nop     dword ptr [rax+rax+00h]
0x140020063  call    cs:__imp_KeLeaveCriticalRegion
0x14002006a  nop     dword ptr [rax+rax+00h]
0x14002006f  mov     edx, 28h ; '('
0x140020074  mov     ecx, 102h
  ... truncated ...
```
