# MdaCreateNetRoot

- ea: `0x140025484`
- end: `0x140025bda`
- name: `MdaCreateNetRoot`
- size: `1878`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140025be0`

## callees

- `0x140003bd0`
- `0x140005c90`
- `0x14000c370`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140019d7c`
- `0x140019fc4`
- `0x14001f904`
- `0x14001fad0`
- `0x14001fe8c`
- `0x140023dd0`
- `0x140025484`
- `0x1400280c4`
- `0x140030638`
- `0x140038550`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140025780`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140025780`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400256d4`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025885`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400256d4`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025885`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x1400256ed`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14002589e`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x1400256ed`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14002589e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025793`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025964`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025793`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025964`
- `ntoskrnl!KeInitializeEvent` at `0x14002561d`
- `ntoskrnl!KeInitializeEvent` at `0x14002561d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025a8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025a8e`
- `ntoskrnl!ExAllocatePool2` at `0x140025554`
- `ntoskrnl!ExAllocatePool2` at `0x1400255b7`
- `ntoskrnl!ExAllocatePool2` at `0x140025554`
- `ntoskrnl!ExAllocatePool2` at `0x1400255b7`

## pseudocode

```c
__int64 __fastcall MdaCreateNetRoot(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v6; // r12
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r15
  _DWORD *Pool2; // rax
  _QWORD *v11; // r14
  _DWORD *v12; // rbx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  unsigned int v16; // edi
  __int16 v17; // dx
  const UNICODE_STRING *SourceString; // r12
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  PUNICODE_PREFIX_TABLE_ENTRY v20; // rdi
  _WORD *p_Length; // r9
  const UNICODE_STRING *Prefix; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rdi
  __int64 inited; // rax
  __int64 v27; // rax
  char v28; // di
  int v29; // r8d
  int v30; // r8d
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  void *v34; // rcx
  __int64 v35; // rax
  int Registry; // eax
  char v37; // cl
  int v39; // [rsp+40h] [rbp-38h]
  __int128 v40; // [rsp+48h] [rbp-30h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+58h] [rbp-20h] BYREF
  __int64 v42; // [rsp+C0h] [rbp+48h] BYREF
  PUNICODE_PREFIX_TABLE_ENTRY v43; // [rsp+C8h] [rbp+50h] BYREF
  __int64 v44; // [rsp+D0h] [rbp+58h]
  __int64 v45; // [rsp+D8h] [rbp+60h]

  v44 = a3;
  v3 = *(_QWORD *)(a1 + 80);
  LOBYTE(v42) = 0;
  v45 = v3;
  v40 = 0;
  FirstName = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  v6 = *(_QWORD *)(a2 + 32);
  *(_BYTE *)(a2 + 76) = 0;
  *(_DWORD *)(a2 + 80) = 7;
  v39 = v6;
  v7 = **(unsigned __int16 **)(v6 + 64);
  v8 = **(unsigned __int16 **)(a2 + 88);
  if ( (unsigned __int16)v8 < (unsigned __int16)v7 || (((_DWORD)v8 - (_DWORD)v7 + 7) & 0xFFFFFFF8) > 0xFFFE )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_84;
    v14 = 45;
    goto LABEL_83;
  }
  v9 = *(_QWORD *)(v6 + 32);
  Pool2 = (_DWORD *)ExAllocatePool2(258, ((v8 - v7 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 264, 1314022990);
  v11 = (_QWORD *)(a2 + 40);
  v12 = Pool2;
  *(_QWORD *)(a2 + 40) = Pool2;
  if ( !Pool2 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_84;
    v14 = 46;
LABEL_83:
    WPP_SF_(v13->AttachedDevice, v14, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
LABEL_84:
    v16 = -1073741670;
LABEL_85:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    return v16;
  }
  memset(Pool2, 0, 0x108u);
  v15 = ExAllocatePool2(66, 56, 1280468558);
  *((_QWORD *)v12 + 6) = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    v16 = -1073741670;
    goto LABEL_68;
  }
  *(_DWORD *)v15 = 1;
  *(_QWORD *)(v15 + 8) = 0;
  *(_DWORD *)(v15 + 16) = 0;
  KeInitializeEvent((PRKEVENT)(v15 + 24), SynchronizationEvent, 0);
  *((_QWORD *)v12 + 8) = v12 + 14;
  *((_QWORD *)v12 + 7) = v12 + 14;
  *(_OWORD *)(v12 + 2) = *(_OWORD *)*(_QWORD *)(a2 + 88);
  *((_QWORD *)v12 + 2) += 2 * ((unsigned __int64)**(unsigned __int16 **)(v6 + 64) >> 1);
  *((_WORD *)v12 + 4) -= **(_WORD **)(v6 + 64);
  v17 = *((_WORD *)v12 + 4);
  *((_WORD *)v12 + 5) -= **(_WORD **)(v6 + 64);
  if ( !v17 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    v16 = -1073741634;
    goto LABEL_68;
  }
  *((_WORD *)v12 + 13) = v17;
  SourceString = (const UNICODE_STRING *)(v12 + 6);
  *((_WORD *)v12 + 12) = 0;
  *((_QWORD *)v12 + 4) = ((unsigned __int64)v12 + 271) & 0xFFFFFFFFFFFFFFF8uLL;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v9 + 216));
  UnicodePrefix = RtlFindUnicodePrefix(*(PUNICODE_PREFIX_TABLE *)(v9 + 232), (PCUNICODE_STRING)(v12 + 2), 0);
  v20 = UnicodePrefix;
  if ( UnicodePrefix && (p_Length = &UnicodePrefix->Prefix->Length, *p_Length == *((_WORD *)v12 + 4)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_ZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
        (_DWORD)p_Length,
        (__int64)(v12 + 2));
    Prefix = v20->Prefix;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids, v12 + 2);
    Prefix = (const UNICODE_STRING *)(v12 + 2);
  }
  RtlCopyUnicodeString((PUNICODE_STRING)(v12 + 6), Prefix);
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v9 + 216));
  v23 = 0;
  if ( (SourceString->Length & 0xFFFE) != 0 )
  {
    do
    {
      v24 = *((_QWORD *)v12 + 4);
      if ( *(_WORD *)(v24 + 2 * v23) == 92 )
        *(_WORD *)(v24 + 2 * v23) = 47;
      v23 = (unsigned int)(v23 + 1);
    }
    while ( (unsigned int)v23 < SourceString->Length >> 1 );
  }
  v25 = v45;
  inited = HacInitTable(v45);
  *((_QWORD *)v12 + 9) = inited;
  if ( !inited )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    v16 = -1073741670;
    goto LABEL_68;
  }
  LODWORD(v40) = 0;
  *((_QWORD *)&v40 + 1) = 0;
  v27 = HacAllocate(v25, *((_QWORD *)v12 + 9), &v40, 0);
  *((_QWORD *)v12 + 5) = v27;
  if ( !v27 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    v16 = -1073741670;
LABEL_67:
    --*(_DWORD *)(*((_QWORD *)v12 + 9) + 76LL);
    HacFreeTable(*(_QWORD *)(a1 + 80), *((_QWORD *)v12 + 9));
LABEL_68:
    v34 = (void *)*((_QWORD *)v12 + 6);
    if ( v34 )
    {
      ExFreePoolWithTag(v34, 0);
      *((_QWORD *)v12 + 6) = 0;
    }
    ExFreePoolWithTag(v12, 0);
    *v11 = 0;
    goto LABEL_85;
  }
  v28 = 0;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v9 + 216));
  v43 = RtlFindUnicodePrefix(*(PUNICODE_PREFIX_TABLE *)(v9 + 232), (PCUNICODE_STRING)(v12 + 2), 0);
  if ( !v43
    && (unsigned __int8)MdaFindPrefixOfUnicodePrefix(
                          *(_QWORD *)(v9 + 232),
                          (int)v12 + 8,
                          v29,
                          (int)&v43,
                          (__int64)&v42,
                          &FirstName) )
  {
    do
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_ZdZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          53,
          (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
          v43->Prefix,
          v42,
          (__int64)&FirstName,
          (__int64)(v12 + 2));
      v28 = 1;
    }
    while ( (unsigned __int8)MdaFindPrefixOfUnicodePrefix(
                               *(_QWORD *)(v9 + 232),
                               (int)v12 + 8,
                               v30,
                               (int)&v43,
                               (__int64)&v42,
                               &FirstName) );
    SourceString = (const UNICODE_STRING *)(v12 + 6);
  }
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v9 + 216));
  if ( v28 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    HacConstructFakeDirectory(*((_QWORD *)v12 + 5));
    v31 = *((_QWORD *)v12 + 5);
    if ( v31 )
      *(_DWORD *)(v31 + 284) |= 2u;
  }
  else
  {
    v32 = *((_QWORD *)v12 + 5);
    if ( v32 )
      *(_DWORD *)(v32 + 284) |= 4u;
    if ( (unsigned int)MntMount(v39, a1, (int)v12, v44, SourceString, *((_QWORD *)v12 + 5) + 216LL) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      v16 = -1073741634;
      v33 = *((_QWORD *)v12 + 5);
      if ( v33 )
        *(_DWORD *)(v33 + 284) |= 8u;
      HacDereference(*(_QWORD *)(a1 + 80), *((_QWORD *)v12 + 5));
      goto LABEL_67;
    }
    *v12 |= 1u;
  }
  HacInsertEntry(v45, *((_QWORD *)v12 + 5));
  v35 = *((_QWORD *)v12 + 5);
  if ( v35 )
    *(_DWORD *)(v35 + 284) |= 4u;
  MdaNotifyInitializeSync(v12 + 26);
  *((_QWORD *)v12 + 12) = v12 + 22;
  *((_QWORD *)v12 + 11) = v12 + 22;
  _InterlockedIncrement(v12 + 62);
  _InterlockedIncrement(v12 + 63);
  v12[64] |= 1u;
  LODWORD(v42) = 0;
  Registry = NfsReadRegistry(
               &stru_140041070,
               L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Auth",
               (__int64)&v42,
               4);
  v37 = 15;
  if ( Registry >= 0 )
    v37 = v42;
  v12[21] = v37 & 0xF | v12[21] & 0xFFFFFFF0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140025484  mov     [rsp-40h+arg_10], r8
0x140025489  push    rbp
0x14002548a  push    rbx
0x14002548b  push    rsi
0x14002548c  push    rdi
0x14002548d  push    r12
0x14002548f  push    r13
0x140025491  push    r14
0x140025493  push    r15
0x140025495  mov     rbp, rsp
0x140025498  sub     rsp, 78h
0x14002549c  mov     rax, [rcx+50h]
0x1400254a0  xor     esi, esi
0x1400254a2  xorps   xmm0, xmm0
0x1400254a5  mov     byte ptr [rbp+arg_0], sil
0x1400254a9  xorps   xmm1, xmm1
0x1400254ac  mov     [rbp+arg_18], rax
0x1400254b0  movups  [rbp+var_30], xmm0
0x1400254b4  mov     rdi, rdx
0x1400254b7  mov     r13, rcx
0x1400254ba  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x1400254be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254c5  lea     r9, WPP_GLOBAL_Control
0x1400254cc  cmp     rcx, r9
0x1400254cf  jz      short loc_1400254F2
0x1400254d1  mov     eax, [rcx+2Ch]
0x1400254d4  test    al, 8
0x1400254d6  jz      short loc_1400254F2
0x1400254d8  mov     rcx, [rcx+18h]
0x1400254dc  lea     edx, [rsi+2Ch]
0x1400254df  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400254e6  call    WPP_SF_
0x1400254eb  lea     r9, WPP_GLOBAL_Control
0x1400254f2  mov     r12, [rdi+20h]
0x1400254f6  mov     [rdi+4Ch], sil
0x1400254fa  mov     dword ptr [rdi+50h], 7
0x140025501  mov     qword ptr [rbp+var_38], r12
0x140025505  mov     rax, [r12+40h]
0x14002550a  movzx   ecx, word ptr [rax]
0x14002550d  mov     rax, [rdi+58h]
0x140025511  movzx   edx, word ptr [rax]
0x140025514  cmp     dx, cx
0x140025517  jb      loc_140025B66
0x14002551d  mov     eax, edx
0x14002551f  sub     eax, ecx
0x140025521  add     eax, 7
0x140025524  and     eax, 0FFFFFFF8h
0x140025527  cmp     eax, 0FFFEh
0x14002552c  ja      loc_140025B66
0x140025532  mov     r15, [r12+20h]
0x140025537  sub     rdx, rcx
0x14002553a  add     rdx, 7
0x14002553e  mov     ecx, 102h
0x140025543  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140025547  mov     r8d, 4E52664Eh
0x14002554d  add     rdx, 108h
0x140025554  call    cs:__imp_ExAllocatePool2
0x14002555b  nop     dword ptr [rax+rax+00h]
0x140025560  lea     r14, [rdi+28h]
0x140025564  mov     rbx, rax
0x140025567  mov     [r14], rax
0x14002556a  test    rax, rax
0x14002556d  jnz     short loc_140025599
0x14002556f  mov     rcx, cs:WPP_GLOBAL_Control
0x140025576  lea     rax, WPP_GLOBAL_Control
0x14002557d  cmp     rcx, rax
0x140025580  jz      loc_140025B8E
0x140025586  mov     eax, [rcx+2Ch]
0x140025589  test    al, 1
0x14002558b  jz      loc_140025B8E
0x140025591  lea     edx, [rbx+2Eh]
0x140025594  jmp     loc_140025B7E
0x140025599  xor     edx, edx; Val
0x14002559b  mov     r8d, 108h; Size
0x1400255a1  mov     rcx, rbx; void *
0x1400255a4  call    memset
0x1400255a9  mov     edx, 38h ; '8'
0x1400255ae  mov     r8d, 4C52664Eh
0x1400255b4  lea     ecx, [rdx+0Ah]
0x1400255b7  call    cs:__imp_ExAllocatePool2
0x1400255be  nop     dword ptr [rax+rax+00h]
0x1400255c3  mov     [rbx+30h], rax
0x1400255c7  test    rax, rax
0x1400255ca  jnz     short loc_140025605
0x1400255cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400255d3  lea     rax, WPP_GLOBAL_Control
0x1400255da  cmp     rcx, rax
0x1400255dd  jz      short loc_1400255FB
0x1400255df  mov     eax, [rcx+2Ch]
0x1400255e2  test    al, 1
0x1400255e4  jz      short loc_1400255FB
0x1400255e6  mov     rcx, [rcx+18h]
0x1400255ea  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400255f1  mov     edx, 2Fh ; '/'
0x1400255f6  call    WPP_SF_
0x1400255fb  mov     edi, 0C000009Ah
0x140025600  jmp     loc_140025A6E
0x140025605  xor     r8d, r8d; State
0x140025608  mov     dword ptr [rax], 1
0x14002560e  lea     rcx, [rax+18h]; Event
0x140025612  mov     [rax+8], rsi
0x140025616  mov     [rax+10h], esi
0x140025619  lea     edx, [r8+1]; Type
0x14002561d  call    cs:__imp_KeInitializeEvent
0x140025624  nop     dword ptr [rax+rax+00h]
0x140025629  lea     rax, [rbx+38h]
0x14002562d  mov     [rax+8], rax
0x140025631  lea     rsi, [rbx+8]
0x140025635  mov     [rax], rax
0x140025638  mov     rax, [rdi+58h]
0x14002563c  movups  xmm0, xmmword ptr [rax]
0x14002563f  movdqu  xmmword ptr [rsi], xmm0
0x140025643  mov     rax, [r12+40h]
0x140025648  movzx   ecx, word ptr [rax]
0x14002564b  shr     rcx, 1
0x14002564e  add     rcx, rcx
0x140025651  add     [rbx+10h], rcx
0x140025655  mov     rax, [r12+40h]
0x14002565a  movzx   ecx, word ptr [rax]
0x14002565d  sub     [rsi], cx
0x140025660  mov     rax, [r12+40h]
0x140025665  movzx   edx, word ptr [rsi]
0x140025668  movzx   ecx, word ptr [rax]
0x14002566b  xor     eax, eax
0x14002566d  sub     [rbx+0Ah], cx
0x140025671  test    dx, dx
0x140025674  jnz     short loc_1400256B1
0x140025676  mov     rcx, cs:WPP_GLOBAL_Control
0x14002567d  lea     rax, WPP_GLOBAL_Control
0x140025684  cmp     rcx, rax
0x140025687  jz      short loc_1400256A5
0x140025689  mov     eax, [rcx+2Ch]
0x14002568c  test    al, 1
0x14002568e  jz      short loc_1400256A5
0x140025690  mov     rcx, [rcx+18h]
0x140025694  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002569b  mov     edx, 30h ; '0'
0x1400256a0  call    WPP_SF_
0x1400256a5  mov     edi, 0C00000BEh
0x1400256aa  xor     esi, esi
0x1400256ac  jmp     loc_140025A6E
0x1400256b1  mov     [rbx+1Ah], dx
0x1400256b5  lea     r12, [rbx+18h]
0x1400256b9  mov     [r12], ax
0x1400256be  lea     rax, [rbx+10Fh]
0x1400256c5  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400256c9  mov     [rbx+20h], rax
0x1400256cd  mov     rcx, [r15+0D8h]; FastMutex
0x1400256d4  call    cs:__imp_ExAcquireFastMutex
0x1400256db  nop     dword ptr [rax+rax+00h]
0x1400256e0  mov     rcx, [r15+0E8h]; PrefixTable
0x1400256e7  xor     r8d, r8d; CaseInsensitiveIndex
0x1400256ea  mov     rdx, rsi; FullName
0x1400256ed  call    cs:__imp_RtlFindUnicodePrefix
0x1400256f4  nop     dword ptr [rax+rax+00h]
0x1400256f9  mov     rdi, rax
0x1400256fc  test    rax, rax
0x1400256ff  jz      short loc_140025748
0x140025701  mov     r9, [rax+30h]
0x140025705  movzx   eax, word ptr [rsi]
0x140025708  cmp     [r9], ax
0x14002570c  jnz     short loc_140025748
0x14002570e  mov     rcx, cs:WPP_GLOBAL_Control
0x140025715  lea     rax, WPP_GLOBAL_Control
0x14002571c  cmp     rcx, rax
0x14002571f  jz      short loc_140025742
0x140025721  mov     eax, [rcx+2Ch]
0x140025724  test    al, 2
0x140025726  jz      short loc_140025742
0x140025728  mov     rcx, [rcx+18h]
0x14002572c  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025733  mov     edx, 31h ; '1'
0x140025738  mov     [rsp+78h+SourceString], rsi
0x14002573d  call    WPP_SF_ZZ
0x140025742  mov     rdx, [rdi+30h]
0x140025746  jmp     short loc_14002577D
0x140025748  mov     rcx, cs:WPP_GLOBAL_Control
0x14002574f  lea     rax, WPP_GLOBAL_Control
0x140025756  cmp     rcx, rax
0x140025759  jz      short loc_14002577A
0x14002575b  mov     eax, [rcx+2Ch]
0x14002575e  test    al, 2
0x140025760  jz      short loc_14002577A
0x140025762  mov     rcx, [rcx+18h]
0x140025766  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002576d  mov     edx, 32h ; '2'
0x140025772  mov     r9, rsi
0x140025775  call    WPP_SF_Z
0x14002577a  mov     rdx, rsi; SourceString
0x14002577d  mov     rcx, r12; DestinationString
0x140025780  call    cs:__imp_RtlCopyUnicodeString
0x140025787  nop     dword ptr [rax+rax+00h]
0x14002578c  mov     rcx, [r15+0D8h]; FastMutex
0x140025793  call    cs:__imp_ExReleaseFastMutex
0x14002579a  nop     dword ptr [rax+rax+00h]
0x14002579f  movzx   eax, word ptr [r12]
0x1400257a4  xor     ecx, ecx
0x1400257a6  test    eax, 0FFFFFFFEh
0x1400257ab  jbe     short loc_1400257CD
0x1400257ad  mov     r8, [rbx+20h]
0x1400257b1  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x1400257b7  jnz     short loc_1400257C0
0x1400257b9  mov     word ptr [r8+rcx*2], 2Fh ; '/'
0x1400257c0  movzx   eax, word ptr [r12]
0x1400257c5  inc     ecx
0x1400257c7  shr     eax, 1
0x1400257c9  cmp     ecx, eax
0x1400257cb  jb      short loc_1400257AD
0x1400257cd  mov     rdi, [rbp+arg_18]
0x1400257d1  mov     rcx, rdi
0x1400257d4  call    HacInitTable
0x1400257d9  xor     ecx, ecx
0x1400257db  mov     [rbx+48h], rax
0x1400257df  test    rax, rax
0x1400257e2  jnz     short loc_14002581D
0x1400257e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400257eb  lea     rax, WPP_GLOBAL_Control
0x1400257f2  cmp     rcx, rax
0x1400257f5  jz      short loc_140025813
0x1400257f7  mov     eax, [rcx+2Ch]
0x1400257fa  test    al, 1
0x1400257fc  jz      short loc_140025813
0x1400257fe  mov     rcx, [rcx+18h]
0x140025802  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025809  mov     edx, 33h ; '3'
0x14002580e  call    WPP_SF_
0x140025813  mov     edi, 0C000009Ah
0x140025818  jmp     loc_1400256AA
0x14002581d  mov     dword ptr [rbp+var_30], ecx
0x140025820  lea     r8, [rbp+var_30]
0x140025824  mov     qword ptr [rbp+var_30+8], rcx
0x140025828  xor     r9d, r9d
0x14002582b  mov     rdx, [rbx+48h]
0x14002582f  mov     rcx, rdi
0x140025832  call    HacAllocate
0x140025837  mov     [rbx+28h], rax
0x14002583b  test    rax, rax
0x14002583e  jnz     short loc_14002587B
0x140025840  mov     rcx, cs:WPP_GLOBAL_Control
0x140025847  lea     rax, WPP_GLOBAL_Control
0x14002584e  cmp     rcx, rax
0x140025851  jz      short loc_14002586F
0x140025853  mov     eax, [rcx+2Ch]
0x140025856  test    al, 1
0x140025858  jz      short loc_14002586F
0x14002585a  mov     rcx, [rcx+18h]
0x14002585e  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025865  mov     edx, 34h ; '4'
0x14002586a  call    WPP_SF_
0x14002586f  mov     edi, 0C000009Ah
0x140025874  xor     esi, esi
0x140025876  jmp     loc_140025A5A
0x14002587b  mov     rcx, [r15+0D8h]; FastMutex
0x140025882  xor     dil, dil
0x140025885  call    cs:__imp_ExAcquireFastMutex
0x14002588c  nop     dword ptr [rax+rax+00h]
0x140025891  mov     rcx, [r15+0E8h]; PrefixTable
0x140025898  xor     r8d, r8d; CaseInsensitiveIndex
0x14002589b  mov     rdx, rsi; FullName
0x14002589e  call    cs:__imp_RtlFindUnicodePrefix
0x1400258a5  nop     dword ptr [rax+rax+00h]
0x1400258aa  mov     [rbp+arg_8], rax
0x1400258ae  test    rax, rax
0x1400258b1  jnz     loc_14002595D
0x1400258b7  mov     rcx, [r15+0E8h]; int
0x1400258be  lea     rax, [rbp+var_20]
0x1400258c2  mov     [rsp+78h+FirstName], rax; FirstName
0x1400258c7  lea     r9, [rbp+arg_8]; int
0x1400258cb  lea     rax, [rbp+arg_0]
0x1400258cf  mov     rdx, rsi; int
0x1400258d2  mov     [rsp+78h+SourceString], rax; __int64
0x1400258d7  call    MdaFindPrefixOfUnicodePrefix
0x1400258dc  test    al, al
0x1400258de  jz      short loc_14002595D
0x1400258e0  lea     r12, WPP_GLOBAL_Control
0x1400258e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400258ee  cmp     rcx, r12
0x1400258f1  jz      short loc_14002592D
0x1400258f3  mov     eax, [rcx+2Ch]
0x1400258f6  test    al, 2
0x1400258f8  jz      short loc_14002592D
0x1400258fa  movzx   eax, byte ptr [rbp+arg_0]
0x1400258fe  lea     r8, [rbp+var_20]
0x140025902  mov     r9, [rbp+arg_8]
0x140025906  mov     edx, 35h ; '5'
0x14002590b  mov     rcx, [rcx+18h]
0x14002590f  mov     [rsp+78h+var_48], rsi
0x140025914  mov     [rsp+78h+FirstName], r8
0x140025919  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025920  mov     r9, [r9+30h]
0x140025924  mov     dword ptr [rsp+78h+SourceString], eax
0x140025928  call    WPP_SF_ZdZZ
0x14002592d  mov     rcx, [r15+0E8h]; int
0x140025934  lea     rax, [rbp+var_20]
0x140025938  mov     [rsp+78h+FirstName], rax; FirstName
0x14002593d  lea     r9, [rbp+arg_8]; int
0x140025941  lea     rax, [rbp+arg_0]
0x140025945  mov     rdx, rsi; int
0x140025948  mov     [rsp+78h+SourceString], rax; __int64
0x14002594d  mov     dil, 1
  ... truncated ...
```
