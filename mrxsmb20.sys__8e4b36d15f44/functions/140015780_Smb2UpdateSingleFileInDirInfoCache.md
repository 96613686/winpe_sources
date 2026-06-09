# Smb2UpdateSingleFileInDirInfoCache

- ea: `0x140015780`
- end: `0x140015cd7`
- name: `Smb2UpdateSingleFileInDirInfoCache`
- size: `1367`
- prototype: `__int64 __fastcall(_QWORD *, struct _NAME_CACHE_CONTROL_ *, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140005820`
- `0x1400129f0`

## callees

- `0x140004d30`
- `0x140004f20`
- `0x140015780`
- `0x140015ce0`
- `0x14002d630`
- `0x1400355c8`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x140015b8a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140015c0b`
- `ntoskrnl!ExReleasePushLockEx` at `0x140015b8a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140015c0b`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400158b1`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400158b1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140015b48`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140015b48`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015959`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015a6c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015959`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140015a6c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015922`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015afc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015bc7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015922`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015afc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140015bc7`
- `rdbss!RxNameCacheCheckEntry` at `0x1400159c9`
- `rdbss!RxNameCacheCheckEntry` at `0x1400159c9`
- `rdbss!RxNameCacheExpireEntry` at `0x140015ad5`
- `rdbss!RxNameCacheExpireEntry` at `0x140015ad5`
- `rdbss!RxNameCacheActivateEntry` at `0x140015a57`
- `rdbss!RxNameCacheActivateEntry` at `0x140015a57`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001593c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001593c`
- `rdbss!RxDiagnosticTrace` at `0x140015a38`
- `rdbss!RxDiagnosticTrace` at `0x140015a38`
- `rdbss!RxCrackPathName` at `0x1400157e3`
- `rdbss!RxCrackPathName` at `0x14001590d`
- `rdbss!RxCrackPathName` at `0x1400157e3`
- `rdbss!RxCrackPathName` at `0x14001590d`

## pseudocode

```c
__int64 __fastcall Smb2UpdateSingleFileInDirInfoCache(
        _QWORD *a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 result; // rax
  __int64 v7; // rax
  struct _LIST_ENTRY *v8; // r12
  __int64 *v9; // r13
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v13; // rbx
  __int64 v14; // rcx
  struct _LIST_ENTRY *Flink; // rsi
  unsigned __int32 v16; // r14d
  int v17; // r8d
  int v18; // eax
  __int64 *v19; // r14
  int v20; // ebx
  __int64 v21; // r8
  int v22; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING String1; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING String; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+70h] [rbp-90h] BYREF
  __int128 v28; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v29[18]; // [rsp+90h] [rbp-70h] BYREF
  ULONG HashValue; // [rsp+160h] [rbp+60h] BYREF
  __int64 v31; // [rsp+170h] [rbp+70h]
  __int64 v32; // [rsp+178h] [rbp+78h]

  v32 = a4;
  v31 = a3;
  String = 0;
  String1 = 0;
  v27 = 0;
  memset(v29, 0, 0x88u);
  result = RxCrackPathName(a1[7] + 360LL, &String, &String1, &v27);
  if ( !String1.Length )
    return result;
  if ( (_WORD)v27 )
    return result;
  result = a1[7];
  if ( (*(_BYTE *)(result + 355) & 0x3C) == 0xC )
    return result;
  v7 = a1[8];
  LODWORD(v32) = 0;
  v8 = 0;
  v23 = 0;
  v9 = 0;
  if ( v7 )
  {
    v10 = *(_QWORD *)(v7 + 56);
    if ( v10 )
    {
      v9 = (__int64 *)(v10 + 8);
      v11 = *(_QWORD **)(*(_QWORD *)(a1[9] + 40LL) + 40LL);
      if ( (*(_DWORD *)(v11[53] + 184LL) & 0x800) == 0 && (*(_BYTE *)(v11[3] + 1314LL) & 4) != 0 )
        v23 = -1;
      else
        v23 = v11[12];
    }
  }
  HashValue = 0;
  RtlHashUnicodeString(&String, 1u, 0, &HashValue);
  memset(v29, 0, 0x88u);
  LODWORD(v29[0]) = 8973226;
  v29[13] = &v29[12];
  v29[12] = &v29[12];
  v29[9] = &v29[8];
  v29[8] = &v29[8];
  LODWORD(v29[14]) = HashValue;
  while ( 1 )
  {
    v28 = 0;
    RxCrackPathName(&String, 0, &v28, 0);
    ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
    while ( 1 )
    {
      Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v28, 0, v29);
      v13 = Entry;
      if ( !Entry )
      {
        ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
        goto LABEL_13;
      }
      if ( RxNameCacheCheckEntry(Entry, 0) == RX_NC_SUCCESS )
        break;
      RxNameCacheExpireEntry(a2, v13);
    }
    Flink = v13->Link.Flink;
    if ( Flink )
    {
      v16 = _InterlockedIncrement((volatile signed __int32 *)&Flink[2].Flink + 1);
      if ( v16 <= 1 )
        __int2c();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qdd(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
          Flink,
          v16 - 1,
          v16);
      }
      v22 = v16;
      RxDiagnosticTrace(Flink->Blink, 8, "Ref %d --> %d", v16 - 1);
      v8 = v13[1].Link.Flink;
    }
    RxNameCacheActivateEntry(a2, v13, 0, 0);
    ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
    if ( !Flink )
      break;
    v18 = (int)Flink[2].Flink;
    if ( v18 )
    {
      if ( v18 != 3 )
        goto LABEL_50;
      ExAcquirePushLockExclusiveEx(&Flink[6].Blink, 0);
      if ( LODWORD(Flink[2].Flink) == 3 )
        _InterlockedIncrement((volatile signed __int32 *)&Flink[3].Blink);
      goto LABEL_49;
    }
    v24 = 0;
    HashValue = 0;
    if ( v9 && (struct _LIST_ENTRY *)v23 == v8 )
    {
      v19 = v9;
    }
    else
    {
      v19 = &v24;
      v24 = 0;
    }
    if ( HIDWORD(*v19) == LODWORD(Flink[2].Blink) )
    {
      if ( (int)*v19 >= 0 )
        __int2c();
      v20 = v32;
    }
    else
    {
      *v19 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_ZqZ(WPP_GLOBAL_Control->AttachedDevice, 24, v17, (unsigned int)&String1, (char)Flink, (__int64)&String);
      }
      ExAcquirePushLockSharedEx(&Flink[6].Blink, 0);
      LODWORD(v32) = QueryFileInfoFromDirectoryCache(Flink, &String1, (__int64)v19, 0, (__int64)&HashValue);
      ExReleasePushLockEx(&Flink[6].Blink, 0);
      v20 = v32;
      if ( (_DWORD)v32 == -1073741789 || (_DWORD)v32 == -1073741802 )
      {
        LODWORD(v32) = 0;
LABEL_45:
        if ( HIDWORD(*v19) != LODWORD(Flink[2].Blink) || (int)*v19 >= 0 )
          __int2c();
        ExAcquirePushLockExclusiveEx(&Flink[6].Blink, 0);
        v21 = *(_QWORD *)(a1[7] + 136LL);
        _InterlockedIncrement((volatile signed __int32 *)(v21 + 88));
        LOBYTE(v21) = v23 != (_QWORD)v8;
        UpdateDirectoryCacheEntry((int)Flink, (int)v19, v21, v31, v22, &String1);
LABEL_49:
        ExReleasePushLockEx(&Flink[6].Blink, 0);
        goto LABEL_50;
      }
    }
    if ( v20 >= 0 )
      goto LABEL_45;
LABEL_50:
    Smb2DereferenceDirCacheObject(Flink);
  }
LABEL_13:
  result = v29[12];
  if ( (_QWORD *)v29[12] != &v29[12] )
  {
    if ( *(_QWORD **)(v29[12] + 8LL) != &v29[12] || (v14 = v29[13], *(_QWORD **)v29[13] != &v29[12]) )
      __fastfail(3u);
    *(_QWORD *)v29[13] = v29[12];
    *(_QWORD *)(result + 8) = v14;
  }
  return result;
}

```

## disassembly

```asm
0x140015780  mov     [rsp-8+arg_18], r9
0x140015785  mov     [rsp-8+arg_10], r8
0x14001578a  push    rbp
0x14001578b  push    rsi
0x14001578c  push    rdi
0x14001578d  push    r15
0x14001578f  lea     rbp, [rsp-38h]
0x140015794  sub     rsp, 138h
0x14001579b  xorps   xmm0, xmm0
0x14001579e  mov     r15, rdx
0x1400157a1  mov     rdi, rcx
0x1400157a4  xorps   xmm1, xmm1
0x1400157a7  mov     esi, 88h
0x1400157ac  lea     rcx, [rbp+50h+var_C0]; void *
0x1400157b0  mov     r8d, esi; Size
0x1400157b3  xor     edx, edx; Val
0x1400157b5  movups  xmmword ptr [rsp+150h+String.Length], xmm0
0x1400157ba  movups  xmmword ptr [rsp+150h+var_100.Length], xmm1
0x1400157bf  movups  [rsp+150h+var_E0], xmm0
0x1400157c4  call    memset
0x1400157c9  mov     rcx, [rdi+38h]
0x1400157cd  lea     r9, [rsp+150h+var_E0]
0x1400157d2  add     rcx, 168h
0x1400157d9  lea     r8, [rsp+150h+var_100]
0x1400157de  lea     rdx, [rsp+150h+String]
0x1400157e3  call    cs:__imp_RxCrackPathName
0x1400157ea  nop     dword ptr [rax+rax+00h]
0x1400157ef  cmp     [rsp+150h+var_100.Length], 0
0x1400157f5  jz      loc_1400159B8
0x1400157fb  cmp     word ptr [rsp+150h+var_E0], 0
0x140015801  jnz     loc_1400159B8
0x140015807  mov     rax, [rdi+38h]
0x14001580b  movzx   ecx, byte ptr [rax+163h]
0x140015812  and     cl, 3Ch
0x140015815  cmp     cl, 0Ch
0x140015818  jz      loc_1400159B8
0x14001581e  mov     rax, [rdi+40h]
0x140015822  mov     [rsp+150h+arg_8], rbx
0x14001582a  mov     [rsp+150h+var_20], r12
0x140015832  mov     [rsp+150h+var_28], r13
0x14001583a  mov     [rsp+150h+var_30], r14
0x140015842  xor     r14d, r14d
0x140015845  mov     dword ptr [rbp+50h+arg_18], r14d
0x140015849  mov     r12d, r14d
0x14001584c  mov     [rsp+150h+var_110], r14
0x140015851  mov     r13d, r14d
0x140015854  test    rax, rax
0x140015857  jz      short loc_14001589F
0x140015859  mov     rcx, [rax+38h]
0x14001585d  test    rcx, rcx
0x140015860  jz      short loc_14001589F
0x140015862  mov     rax, [rdi+48h]
0x140015866  lea     r13, [rcx+8]
0x14001586a  mov     rcx, [rax+28h]
0x14001586e  mov     rdx, [rcx+28h]
0x140015872  mov     rax, [rdx+1A8h]
0x140015879  test    dword ptr [rax+0B8h], 800h
0x140015883  jnz     short loc_140015896
0x140015885  mov     rax, [rdx+18h]
0x140015889  test    byte ptr [rax+522h], 4
0x140015890  jnz     loc_140015C27
0x140015896  mov     rbx, [rdx+60h]
0x14001589a  mov     [rsp+150h+var_110], rbx
0x14001589f  lea     r9, [rbp+50h+HashValue]; HashValue
0x1400158a3  mov     [rbp+50h+HashValue], r14d
0x1400158a7  xor     r8d, r8d; HashAlgorithm
0x1400158aa  lea     rcx, [rsp+150h+String]; String
0x1400158af  mov     dl, 1; CaseInSensitive
0x1400158b1  call    cs:__imp_RtlHashUnicodeString
0x1400158b8  nop     dword ptr [rax+rax+00h]
0x1400158bd  mov     r8, rsi; Size
0x1400158c0  lea     rcx, [rbp+50h+var_C0]; void *
0x1400158c4  xor     edx, edx; Val
0x1400158c6  call    memset
0x1400158cb  lea     rax, [rbp+50h+var_60]
0x1400158cf  mov     [rbp+50h+var_C0], 88EBAAh
0x1400158d6  mov     [rbp+50h+var_58], rax
0x1400158da  lea     rax, [rbp+50h+var_60]
0x1400158de  mov     [rbp+50h+var_60], rax
0x1400158e2  lea     rax, [rbp+50h+var_80]
0x1400158e6  mov     [rbp+50h+var_78], rax
0x1400158ea  lea     rax, [rbp+50h+var_80]
0x1400158ee  mov     [rbp+50h+var_80], rax
0x1400158f2  mov     eax, [rbp+50h+HashValue]
0x1400158f5  mov     [rbp+50h+var_50], eax
0x1400158f8  xorps   xmm0, xmm0
0x1400158fb  lea     r8, [rbp+50h+var_D0]
0x1400158ff  xor     r9d, r9d
0x140015902  lea     rcx, [rsp+150h+String]
0x140015907  xor     edx, edx
0x140015909  movups  [rbp+50h+var_D0], xmm0
0x14001590d  call    cs:__imp_RxCrackPathName
0x140015914  nop     dword ptr [rax+rax+00h]
0x140015919  xor     edx, edx
0x14001591b  lea     rcx, Smb2DirCacheLock
0x140015922  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140015929  nop     dword ptr [rax+rax+00h]
0x14001592e  lea     r9, [rbp+50h+var_C0]
0x140015932  xor     r8d, r8d
0x140015935  lea     rdx, [rbp+50h+var_D0]
0x140015939  mov     rcx, r15
0x14001593c  call    cs:__imp_RxNameCacheFetchEntryEx
0x140015943  nop     dword ptr [rax+rax+00h]
0x140015948  xor     edx, edx; MRxContext
0x14001594a  mov     rbx, rax
0x14001594d  test    rax, rax
0x140015950  jnz     short loc_1400159C6
0x140015952  lea     rcx, Smb2DirCacheLock
0x140015959  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140015960  nop     dword ptr [rax+rax+00h]
0x140015965  mov     rax, [rbp+50h+var_60]
0x140015969  lea     rcx, [rbp+50h+var_60]
0x14001596d  mov     r14, [rsp+150h+var_30]
0x140015975  mov     r13, [rsp+150h+var_28]
0x14001597d  mov     r12, [rsp+150h+var_20]
0x140015985  mov     rbx, [rsp+150h+arg_8]
0x14001598d  cmp     rax, rcx
0x140015990  jz      short loc_1400159B8
0x140015992  lea     rcx, [rbp+50h+var_60]
0x140015996  cmp     [rax+8], rcx
0x14001599a  jnz     loc_140015AE6
0x1400159a0  mov     rcx, [rbp+50h+var_58]
0x1400159a4  lea     rdx, [rbp+50h+var_60]
0x1400159a8  cmp     [rcx], rdx
0x1400159ab  jnz     loc_140015AE6
0x1400159b1  mov     [rcx], rax
0x1400159b4  mov     [rax+8], rcx
0x1400159b8  add     rsp, 138h
0x1400159bf  pop     r15
0x1400159c1  pop     rdi
0x1400159c2  pop     rsi
0x1400159c3  pop     rbp
0x1400159c4  retn
0x1400159c6  mov     rcx, rbx; NameCache
0x1400159c9  call    cs:__imp_RxNameCacheCheckEntry
0x1400159d0  nop     dword ptr [rax+rax+00h]
0x1400159d5  test    eax, eax
0x1400159d7  jnz     loc_140015ACF
0x1400159dd  mov     rsi, [rbx+28h]
0x1400159e1  test    rsi, rsi
0x1400159e4  jz      short loc_140015A4B
0x1400159e6  mov     r14d, 1
0x1400159ec  lock xadd [rsi+24h], r14d
0x1400159f2  inc     r14d
0x1400159f5  cmp     r14d, 1
0x1400159f9  jbe     loc_140015C4C
0x1400159ff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015a06  lea     rax, WPP_GLOBAL_Control
0x140015a0d  cmp     rcx, rax
0x140015a10  jz      short loc_140015A1F
0x140015a12  test    dword ptr [rcx+2Ch], 100h
0x140015a19  jnz     loc_140015C53
0x140015a1f  mov     rcx, [rsi+8]
0x140015a23  lea     r9d, [r14-1]
0x140015a27  lea     r8, aRefDD; "Ref %d --> %d"
0x140015a2e  mov     dword ptr [rsp+150h+var_130], r14d
0x140015a33  mov     edx, 8
0x140015a38  call    cs:__imp_RxDiagnosticTrace
0x140015a3f  nop     dword ptr [rax+rax+00h]
0x140015a44  mov     r12, [rbx+78h]
0x140015a48  xor     r14d, r14d
0x140015a4b  xor     r9d, r9d; MRxContext
0x140015a4e  xor     r8d, r8d; LifeTime
0x140015a51  mov     rdx, rbx; NameCache
0x140015a54  mov     rcx, r15; NameCacheCtl
0x140015a57  call    cs:__imp_RxNameCacheActivateEntry
0x140015a5e  nop     dword ptr [rax+rax+00h]
0x140015a63  xor     edx, edx
0x140015a65  lea     rcx, Smb2DirCacheLock
0x140015a6c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140015a73  nop     dword ptr [rax+rax+00h]
0x140015a78  test    rsi, rsi
0x140015a7b  jz      loc_140015965
0x140015a81  mov     eax, [rsi+20h]
0x140015a84  test    eax, eax
0x140015a86  jnz     short loc_140015AED
0x140015a88  mov     [rsp+150h+var_108], r14
0x140015a8d  mov     [rbp+50h+HashValue], r14d
0x140015a91  test    r13, r13
0x140015a94  jz      loc_140015C39
0x140015a9a  cmp     [rsp+150h+var_110], r12
0x140015a9f  jnz     loc_140015C39
0x140015aa5  mov     r14, r13
0x140015aa8  mov     rcx, [r14]
0x140015aab  mov     rax, rcx
0x140015aae  shr     rax, 20h
0x140015ab2  cmp     eax, [rsi+28h]
0x140015ab5  jnz     short loc_140015B1B
0x140015ab7  test    ecx, ecx
0x140015ab9  jns     loc_140015CC9
0x140015abf  mov     ebx, dword ptr [rbp+50h+arg_18]
0x140015ac2  test    ebx, ebx
0x140015ac4  jns     loc_140015BAA
0x140015aca  jmp     loc_140015C17
0x140015acf  mov     rdx, rbx; NameCache
0x140015ad2  mov     rcx, r15; NameCacheCtl
0x140015ad5  call    cs:__imp_RxNameCacheExpireEntry
0x140015adc  nop     dword ptr [rax+rax+00h]
0x140015ae1  jmp     loc_14001592E
0x140015ae6  mov     ecx, 3
0x140015aeb  int     29h; Win8: RtlFailFast(ecx)
0x140015aed  cmp     eax, 3
0x140015af0  jnz     loc_140015C17
0x140015af6  xor     edx, edx
0x140015af8  lea     rcx, [rsi+68h]
0x140015afc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140015b03  nop     dword ptr [rax+rax+00h]
0x140015b08  cmp     dword ptr [rsi+20h], 3
0x140015b0c  jnz     loc_140015C05
0x140015b12  lock inc dword ptr [rsi+38h]
0x140015b16  jmp     loc_140015C05
0x140015b1b  mov     qword ptr [r14], 0
0x140015b22  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015b29  lea     rax, WPP_GLOBAL_Control
0x140015b30  cmp     rcx, rax
0x140015b33  jz      short loc_140015B42
0x140015b35  test    dword ptr [rcx+2Ch], 100h
0x140015b3c  jnz     loc_140015C87
0x140015b42  xor     edx, edx
0x140015b44  lea     rcx, [rsi+68h]
0x140015b48  call    cs:__imp_ExAcquirePushLockSharedEx
0x140015b4f  nop     dword ptr [rax+rax+00h]
0x140015b54  lea     rax, [rbp+50h+HashValue]
0x140015b58  mov     r9d, 4
0x140015b5e  mov     [rsp+150h+var_120], rax; __int64
0x140015b63  lea     rdx, [rsp+150h+var_100]; String1
0x140015b68  mov     [rsp+150h+String1], 0; __int64
0x140015b71  mov     r8b, 1
0x140015b74  mov     rcx, rsi; Context
0x140015b77  mov     [rsp+150h+var_130], r14; int
0x140015b7c  call    QueryFileInfoFromDirectoryCache
0x140015b81  xor     edx, edx
0x140015b83  mov     dword ptr [rbp+50h+arg_18], eax
0x140015b86  lea     rcx, [rsi+68h]
0x140015b8a  call    cs:__imp_ExReleasePushLockEx
0x140015b91  nop     dword ptr [rax+rax+00h]
0x140015b96  mov     ebx, dword ptr [rbp+50h+arg_18]
0x140015b99  cmp     ebx, 0C0000023h
0x140015b9f  jnz     loc_140015CB8
0x140015ba5  xor     eax, eax
0x140015ba7  mov     dword ptr [rbp+50h+arg_18], eax
0x140015baa  mov     rcx, [r14]
0x140015bad  mov     rax, rcx
0x140015bb0  shr     rax, 20h
0x140015bb4  cmp     eax, [rsi+28h]
0x140015bb7  jnz     short loc_140015C35
0x140015bb9  test    ecx, ecx
0x140015bbb  jns     loc_140015CD0
0x140015bc1  xor     edx, edx
0x140015bc3  lea     rcx, [rsi+68h]
0x140015bc7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140015bce  nop     dword ptr [rax+rax+00h]
0x140015bd3  mov     rax, [rdi+38h]
0x140015bd7  mov     r8, [rax+88h]
0x140015bde  lock inc dword ptr [r8+58h]
0x140015be3  cmp     [rsp+150h+var_110], r12
0x140015be8  lea     rax, [rsp+150h+var_100]
0x140015bed  mov     r9, [rbp+50h+arg_10]; int
0x140015bf1  mov     rdx, r14; int
0x140015bf4  setnz   r8b; int
0x140015bf8  mov     [rsp+150h+String1], rax; String1
0x140015bfd  mov     rcx, rsi; int
0x140015c00  call    UpdateDirectoryCacheEntry
0x140015c05  xor     edx, edx
0x140015c07  lea     rcx, [rsi+68h]
0x140015c0b  call    cs:__imp_ExReleasePushLockEx
0x140015c12  nop     dword ptr [rax+rax+00h]
0x140015c17  mov     rcx, rsi; P
0x140015c1a  call    Smb2DereferenceDirCacheObject
0x140015c1f  xor     r14d, r14d
0x140015c22  jmp     loc_1400158F8
0x140015c27  mov     [rsp+150h+var_110], 0FFFFFFFFFFFFFFFFh
0x140015c30  jmp     loc_14001589F
0x140015c35  int     2Ch; Windows NT - assertion failure
0x140015c37  jmp     short loc_140015BC1
0x140015c39  lea     r14, [rsp+150h+var_108]
0x140015c3e  mov     [rsp+150h+var_108], 0
0x140015c47  jmp     loc_140015AA8
0x140015c4c  int     2Ch; Windows NT - assertion failure
0x140015c4e  jmp     loc_1400159FF
0x140015c53  cmp     byte ptr [rcx+29h], 4
0x140015c57  jb      loc_140015A1F
0x140015c5d  mov     rcx, [rcx+18h]
0x140015c61  lea     eax, [r14-1]
0x140015c65  mov     edx, 0Bh
0x140015c6a  mov     dword ptr [rsp+150h+String1], r14d
0x140015c6f  mov     r9, rsi
0x140015c72  mov     dword ptr [rsp+150h+var_130], eax
0x140015c76  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x140015c7d  call    WPP_SF_qdd
0x140015c82  jmp     loc_140015A1F
0x140015c87  cmp     byte ptr [rcx+29h], 2
0x140015c8b  jb      loc_140015B42
0x140015c91  mov     rcx, [rcx+18h]
0x140015c95  lea     rax, [rsp+150h+String]
0x140015c9a  mov     [rsp+150h+String1], rax
0x140015c9f  lea     r9, [rsp+150h+var_100]
0x140015ca4  mov     edx, 18h
0x140015ca9  mov     [rsp+150h+var_130], rsi
0x140015cae  call    WPP_SF_ZqZ
  ... truncated ...
```
