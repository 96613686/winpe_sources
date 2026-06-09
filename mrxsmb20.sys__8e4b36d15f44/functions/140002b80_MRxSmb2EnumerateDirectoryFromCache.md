# MRxSmb2EnumerateDirectoryFromCache

- ea: `0x140002b80`
- end: `0x14000355e`
- name: `MRxSmb2EnumerateDirectoryFromCache`
- size: `2526`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400028d0`

## callees

- `0x140001c70`
- `0x1400020a0`
- `0x140002b80`
- `0x140004b30`
- `0x140004d30`
- `0x14000ad90`
- `0x1400297fc`
- `0x14002a780`
- `0x14002ed54`
- `0x140032dbc`
- `0x1400356ac`
- `0x140035760`
- `0x1400358f0`
- `0x140037120`
- `0x140037240`

## import_xrefs

- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140002d73`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140002dce`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140002d73`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140002dce`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140002f8f`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140002f8f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003817a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003817a`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x140002eee`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x140002eee`
- `ntoskrnl!ExReleasePushLockEx` at `0x14000302f`
- `ntoskrnl!ExReleasePushLockEx` at `0x14000302f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140002fd3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140002fd3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002e57`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000331c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002e57`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000331c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140002e09`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000327b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140002e09`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000327b`
- `rdbss!RxClearMinirdrCancelRoutine` at `0x14003810d`
- `rdbss!RxClearMinirdrCancelRoutine` at `0x14003810d`
- `rdbss!RxNameCacheCheckEntry` at `0x1400031cf`
- `rdbss!RxNameCacheCheckEntry` at `0x1400031cf`
- `rdbss!RxNameCacheExpireEntry` at `0x140003307`
- `rdbss!RxNameCacheExpireEntry` at `0x140003341`
- `rdbss!RxNameCacheExpireEntry` at `0x140003307`
- `rdbss!RxNameCacheExpireEntry` at `0x140003341`
- `rdbss!RxNameCacheActivateEntry` at `0x140003211`
- `rdbss!RxNameCacheActivateEntry` at `0x140003211`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140002e25`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400032d1`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140002e25`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400032d1`
- `rdbss!RxCrackPathName` at `0x140003266`
- `rdbss!RxCrackPathName` at `0x140003266`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140002cd5`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140002cd5`

## pseudocode

```c
__int64 __fastcall MRxSmb2EnumerateDirectoryFromCache(__int64 a1)
{
  const UNICODE_STRING *v1; // r15
  int v3; // esi
  PWSTR Buffer; // r14
  __int64 v5; // rbx
  int v6; // r12d
  __int64 v7; // r13
  bool v8; // zf
  char v9; // cl
  BOOL v10; // ecx
  __int64 *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  PNAME_CACHE_CONTROL v14; // rbx
  __int64 v15; // rsi
  ULONGLONG v16; // rcx
  unsigned __int64 v17; // rcx
  ULONGLONG v18; // rcx
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v20; // rsi
  __int64 v21; // rax
  int v22; // r8d
  char v23; // dl
  __int64 v24; // rax
  int v25; // edx
  int v26; // r8d
  __int64 v28; // rcx
  _QWORD *v29; // rdx
  __int64 v30; // rax
  struct _NAME_CACHE *v31; // rax
  int v32; // r8d
  void (__fastcall *v33)(__int64); // r15
  int v34; // [rsp+30h] [rbp-D8h]
  unsigned __int8 v35; // [rsp+48h] [rbp-C0h]
  char v36; // [rsp+49h] [rbp-BFh] BYREF
  PNAME_CACHE_CONTROL String; // [rsp+50h] [rbp-B8h] BYREF
  struct _UNICODE_STRING String_8; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-A0h]
  _QWORD v40[3]; // [rsp+70h] [rbp-98h] BYREF
  PNAME_CACHE_CONTROL NameCacheCtl; // [rsp+88h] [rbp-80h]
  __int64 v42; // [rsp+90h] [rbp-78h]
  __int64 v43; // [rsp+98h] [rbp-70h]
  char v44; // [rsp+A8h] [rbp-60h] BYREF

  v1 = *(const UNICODE_STRING **)(a1 + 64);
  v3 = -1073741802;
  v36 = 0;
  Buffer = v1[3].Buffer;
  v5 = *((_QWORD *)Buffer + 2);
  if ( v5 == -1 )
    return (unsigned int)v3;
  v6 = *(_DWORD *)(a1 + 448);
  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
  NameCacheCtl = *(PNAME_CACHE_CONTROL *)(v7 + 424);
  v8 = *(_BYTE *)(a1 + 516) == 0;
  v39 = *(_QWORD *)(a1 + 56) + 360LL;
  if ( v8 )
  {
    if ( v5 )
      goto LABEL_39;
  }
  else if ( v5 )
  {
    Smb2DereferenceDirCacheObject((PVOID)v5);
    *((_QWORD *)Buffer + 2) = 0;
    *((_QWORD *)Buffer + 3) = 0;
    *((_QWORD *)Buffer + 4) = 0;
  }
  v5 = 0;
  v9 = *(_BYTE *)(a1 + 32);
  if ( v9 )
  {
    if ( v9 == 12 )
    {
      v10 = (*(_DWORD *)(a1 + 120) & 0x10000000) == 0;
      if ( *(_BYTE *)(a1 + 33) != 1 )
        v10 = 0;
      LODWORD(String) = v10;
    }
    else
    {
      LOBYTE(String) = 0;
    }
  }
  else
  {
    LOBYTE(String) = (*(_DWORD *)(a1 + 120) & 0x10000000) == 0;
  }
  if ( v6 != 79 && v6 != 12 )
  {
    switch ( v6 )
    {
      case 1:
      case 2:
      case 3:
      case 37:
      case 38:
      case 60:
      case 63:
      case 78:
      case 80:
      case 81:
        break;
      default:
        goto LABEL_51;
    }
  }
  v11 = *(__int64 **)(a1 + 56);
  if ( v11[3] >= 104857600 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids, v11 + 45);
    }
    goto LABEL_51;
  }
  v12 = v11[17];
  if ( (*(_DWORD *)(v12 + 56) & 0x400) == 0 )
  {
    v13 = *(_QWORD *)(v11[15] + 32);
    if ( (*(_DWORD *)(v13 + 96) & 0x80u) == 0
      && (*(_BYTE *)(*(_QWORD *)(v13 + 32) + 764LL) & 8) != 0
      && (*(_DWORD *)(v12 + 8) & 1) == 0
      && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL) + 424LL) + 184LL)
        & 0x800000) == 0
      && *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(*(_QWORD *)(a1 + 80)) + 20)
      && (v6 != 60 && v6 != 63 || (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 1314LL) & 4) != 0)
      && (_BYTE)String
      && dbgShouldCacheDirInformation )
    {
      String = (PNAME_CACHE_CONTROL)(*(_QWORD *)(a1 + 80) + 2416LL);
      v14 = (PNAME_CACHE_CONTROL)((char *)NameCacheCtl + 1112);
      v42 = *(_QWORD *)(a1 + 56);
      NameCacheCtl = (PNAME_CACHE_CONTROL)((char *)NameCacheCtl + 1112);
      v15 = *(_QWORD *)(v42 + 136);
      v40[2] = &v44;
      v40[1] = 0x800000;
      v16 = *(_QWORD *)(v15 + 32);
      String_8 = *(struct _UNICODE_STRING *)&v40[1];
      v43 = v15;
      RtlInt64ToUnicodeString(v16, 0x10u, &String_8);
      String_8.Buffer[(unsigned __int64)String_8.Length >> 1] = 58;
      v17 = (unsigned __int16)(String_8.Length + 2);
      String_8.MaximumLength -= v17;
      LOWORD(v40[1]) = String_8.Length + 2;
      String_8.Buffer += v17 >> 1;
      v18 = *(_QWORD *)(v15 + 24);
      String_8.Length = 0;
      RtlInt64ToUnicodeString(v18, 0x10u, &String_8);
      String_8.Buffer[(unsigned __int64)String_8.Length >> 1] = 58;
      LOWORD(v40[1]) += String_8.Length + 2;
      String_8.Length += 2;
      ExAcquirePushLockExclusiveEx(&Smb2GlobalFilePropertyCacheLock, 0);
      Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(String, &v40[1], 0, 0);
      *(_QWORD *)&String_8.Length = Entry;
      v20 = Entry;
      v35 = 1;
      if ( Entry )
      {
        if ( RxNameCacheCheckEntry(Entry, 0) )
        {
          RxNameCacheExpireEntry(String, v20);
          v35 = 1;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_Ziiq(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              v43,
              v42 + 360,
              *(_QWORD *)(v43 + 32),
              *(_QWORD *)(v43 + 24),
              (char)String);
          }
          RxNameCacheActivateEntry(String, *(PNAME_CACHE *)&String_8.Length, 0, 0);
          v35 = 0;
        }
      }
      ExReleasePushLockExclusiveEx(&Smb2GlobalFilePropertyCacheLock, 0);
      while ( 1 )
      {
        v21 = Smb2FindOrCreateDirCacheObject(a1, v14, v39, v35, &String, &v36);
        v5 = v21;
        if ( !v21 )
          goto LABEL_73;
        if ( !*(_DWORD *)(v21 + 56) && !*(_DWORD *)(v21 + 68) )
          break;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids, v21);
        }
        v28 = *(_QWORD *)(a1 + 56);
        String = 0;
        *(_OWORD *)&v40[1] = 0;
        RxCrackPathName(v28 + 360, 0, &v40[1], 0);
        ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
        v29 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
        if ( (*(_DWORD *)(v29[53] + 184LL) & 0x800) == 0 && (*(_BYTE *)(v29[3] + 1314LL) & 4) != 0 )
          v30 = -1;
        else
          v30 = v29[12];
        String = (PNAME_CACHE_CONTROL)v30;
        v31 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(NameCacheCtl, &v40[1], &String, 0);
        *(_QWORD *)&String_8.Length = v31;
        if ( v31 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_iqZ(WPP_GLOBAL_Control->AttachedDevice, 17, v32, (_DWORD)String, a1, (__int64)&v40[1]);
            v31 = *(struct _NAME_CACHE **)&String_8.Length;
          }
          RxNameCacheExpireEntry(NameCacheCtl, v31);
        }
        ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
        Smb2DereferenceDirCacheObject((PVOID)v5);
        v14 = NameCacheCtl;
      }
      v23 = v36;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qdZ(WPP_GLOBAL_Control->AttachedDevice, v39, v22, v21, v36, v39);
        v23 = v36;
      }
      if ( v23 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v7 + 536));
        Smb2PopulateDirectoryCache((_QWORD *)a1, (_DWORD *)v5);
      }
      v3 = FsRtlCancellableWaitForSingleObject(*(PVOID *)(v5 + 112), 0, *(PIRP *)(a1 + 40));
      if ( v3 < 0 )
      {
        v33 = (void (__fastcall *)(__int64))RxClearMinirdrCancelRoutine(a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids, a1);
        }
        if ( v33 )
          v33(a1);
        KeWaitForSingleObject(*(PVOID *)(v5 + 112), Executive, 0, 0, 0);
        *((_QWORD *)Buffer + 2) = -1;
        goto LABEL_50;
      }
      if ( *(_DWORD *)(v5 + 32) || *(_DWORD *)(v5 + 56) || *(_DWORD *)(v5 + 68) )
      {
LABEL_73:
        v3 = -1073741802;
        goto LABEL_51;
      }
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
      {
        LOWORD(v34) = *(_WORD *)v39 >> 1;
        McTemplateK0pphzr2q_EtwWriteTransfer(
          (unsigned __int16)v34,
          (unsigned int)SmbPopulateDirCache,
          a1 + 412,
          a1,
          *(_QWORD *)(a1 + 56),
          v34,
          *(_QWORD *)(v39 + 8));
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqZ(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          (unsigned int)WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
          v5,
          (char)v1,
          (char)Buffer,
          v39);
      }
      *((_QWORD *)Buffer + 2) = v5;
LABEL_39:
      if ( v6 == 79 )
      {
LABEL_40:
        if ( *(_DWORD *)(v5 + 52) == 63 )
        {
LABEL_41:
          Smb2DereferenceDirCacheObject(*((PVOID *)Buffer + 2));
          v5 = 0;
          v3 = -1073741802;
          goto LABEL_51;
        }
      }
      else if ( v6 != 12 )
      {
        switch ( v6 )
        {
          case 1:
          case 2:
          case 3:
            break;
          case 37:
          case 38:
          case 78:
            if ( !v5 )
              break;
            goto LABEL_40;
          case 60:
          case 63:
            if ( v5 && *(_DWORD *)(v5 + 52) == 37 )
              goto LABEL_41;
            break;
          case 80:
          case 81:
            if ( v5 && *(_DWORD *)(v5 + 52) != 81 )
              goto LABEL_41;
            break;
          default:
            goto LABEL_41;
        }
      }
      if ( *(_BYTE *)(a1 + 516) || *(_BYTE *)(a1 + 519) )
        RtlUpcaseUnicodeString((PUNICODE_STRING)&v1[5], v1 + 5, 0);
      if ( *(_BYTE *)(a1 + 516) )
      {
        *((_QWORD *)Buffer + 3) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqqZ(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            (unsigned int)WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
            a1,
            *(_QWORD *)(a1 + 72),
            *((_QWORD *)Buffer + 2),
            v39);
        }
      }
      v24 = *((_QWORD *)Buffer + 2);
      v5 = 0;
      if ( v24 && v24 != -1 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v7 + 552));
        ExAcquirePushLockSharedEx(*((_QWORD *)Buffer + 2) + 104LL, 0);
        v3 = EnumerateDirectoryFromCache(
               *((unsigned int **)Buffer + 2),
               (__m128i *)&v1[5],
               *(_BYTE *)(a1 + 520),
               v6,
               (unsigned __int64 *)Buffer + 3,
               *(_QWORD *)(a1 + 456),
               (unsigned int *)(a1 + 472),
               *(_BYTE *)(a1 + 517));
        ExReleasePushLockEx(*((_QWORD *)Buffer + 2) + 104LL, 0);
        if ( v3 == -2147483642 && *(_BYTE *)(a1 + 519) )
          v3 = -1073741809;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqiDZ(
            WPP_GLOBAL_Control->AttachedDevice,
            v25,
            v26,
            a1,
            *((_QWORD *)Buffer + 2),
            *((_QWORD *)Buffer + 3),
            v3,
            v39);
        }
        v5 = 0;
      }
LABEL_50:
      if ( v3 != -1073741802 )
        goto LABEL_52;
    }
  }
LABEL_51:
  *((_QWORD *)Buffer + 2) = -1;
LABEL_52:
  if ( v5 )
    Smb2DereferenceDirCacheObject((PVOID)v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140002b80  mov     r11, rsp
0x140002b83  mov     [r11+20h], rbx
0x140002b87  push    rbp
0x140002b88  push    rsi
0x140002b89  push    rdi
0x140002b8a  push    r14
0x140002b8c  push    r15
0x140002b8e  lea     rbp, [r11-58h]
0x140002b92  sub     rsp, 130h
0x140002b99  mov     rax, cs:__security_cookie
0x140002ba0  xor     rax, rsp
0x140002ba3  mov     [rbp+50h+var_30], rax
0x140002ba7  mov     r15, [rcx+40h]
0x140002bab  mov     rdi, rcx
0x140002bae  mov     esi, 0C0000016h
0x140002bb3  mov     byte ptr [rsp+150h+var_110+1], 0
0x140002bb8  mov     r14, [r15+38h]
0x140002bbc  mov     rbx, [r14+10h]
0x140002bc0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140002bc4  jz      loc_140003096
0x140002bca  mov     rax, [rcx+48h]
0x140002bce  lea     rdx, cs:140000000h
0x140002bd5  mov     [r11+10h], r12
0x140002bd9  mov     r12d, [rdi+1C0h]
0x140002be0  mov     [r11+18h], r13
0x140002be4  mov     rcx, [rax+28h]
0x140002be8  mov     r13, [rcx+28h]
0x140002bec  mov     rax, [r13+1A8h]
0x140002bf3  mov     [rbp+50h+NameCacheCtl], rax
0x140002bf7  mov     rax, [rdi+38h]
0x140002bfb  add     rax, 168h
0x140002c01  cmp     byte ptr [rdi+204h], 0
0x140002c08  mov     [rsp+150h+var_F0], rax
0x140002c0d  jnz     loc_140003173
0x140002c13  test    rbx, rbx
0x140002c16  jnz     loc_140002F5C
0x140002c1c  mov     eax, [rdi+78h]
0x140002c1f  xor     ebx, ebx
0x140002c21  movzx   ecx, byte ptr [rdi+20h]
0x140002c25  shr     eax, 1Ch
0x140002c28  not     al
0x140002c2a  and     al, 1
0x140002c2c  test    cl, cl
0x140002c2e  jz      loc_1400031B7
0x140002c34  cmp     cl, 0Ch
0x140002c37  jnz     loc_140003363
0x140002c3d  movzx   ecx, al
0x140002c40  xor     eax, eax
0x140002c42  cmp     byte ptr [rdi+21h], 1
0x140002c46  cmovnz  ecx, eax
0x140002c49  mov     dword ptr [rsp+150h+String.Length], ecx
0x140002c4d  cmp     r12d, 4Fh ; 'O'
0x140002c51  jnz     loc_1400031A8
0x140002c57  mov     rdx, [rdi+38h]; jumptable 0000000140038104 cases 1-3,37,38,60,63,78,80,81
0x140002c5b  cmp     qword ptr [rdx+18h], 6400000h
0x140002c63  jge     loc_14000336C
0x140002c69  mov     r8, [rdx+88h]
0x140002c70  test    dword ptr [r8+38h], 400h
0x140002c78  jnz     def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002c7e  mov     rax, [rdx+78h]
0x140002c82  mov     rcx, [rax+20h]
0x140002c86  mov     eax, [rcx+60h]
0x140002c89  test    al, al
0x140002c8b  js      def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002c91  mov     rax, [rcx+20h]
0x140002c95  test    byte ptr [rax+2FCh], 8
0x140002c9c  jz      def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002ca2  mov     eax, [r8+8]
0x140002ca6  test    al, 1
0x140002ca8  jnz     def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002cae  mov     rax, [rdi+48h]
0x140002cb2  mov     rcx, [rax+28h]
0x140002cb6  mov     rax, [rcx+28h]
0x140002cba  mov     rcx, [rax+1A8h]
0x140002cc1  test    dword ptr [rcx+0B8h], 800000h
0x140002ccb  jnz     def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002cd1  mov     rcx, [rdi+50h]
0x140002cd5  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140002cdc  nop     dword ptr [rax+rax+00h]
0x140002ce1  cmp     [rax+14h], ebx
0x140002ce4  jz      def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002cea  cmp     r12d, 3Ch ; '<'
0x140002cee  jz      loc_1400033B9
0x140002cf4  cmp     r12d, 3Fh ; '?'
0x140002cf8  jz      loc_1400033B9
0x140002cfe  cmp     byte ptr [rsp+150h+String.Length], bl
0x140002d02  jz      def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002d08  movzx   eax, cs:dbgShouldCacheDirInformation
0x140002d0f  test    al, al
0x140002d11  jz      def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002d17  mov     rax, [rdi+50h]
0x140002d1b  lea     r8, [rsp+150h+String.Buffer]; String
0x140002d20  mov     rbx, [rbp+50h+NameCacheCtl]
0x140002d24  add     rax, 970h
0x140002d2a  mov     qword ptr [rsp+150h+String.Length], rax
0x140002d2f  add     rbx, 458h
0x140002d36  mov     rax, [rdi+38h]
0x140002d3a  mov     edx, 10h; Base
0x140002d3f  mov     [rbp+50h+var_C8], rax
0x140002d43  mov     [rbp+50h+NameCacheCtl], rbx
0x140002d47  mov     rsi, [rax+88h]
0x140002d4e  lea     rax, [rbp+50h+var_B0]
0x140002d52  mov     qword ptr [rsp+150h+var_E8+10h], rax
0x140002d57  mov     qword ptr [rsp+150h+var_E8+8], 800000h
0x140002d60  movaps  xmm0, xmmword ptr [rsp+150h+var_E8+8]
0x140002d65  mov     rcx, [rsi+20h]; Value
0x140002d69  movdqa  xmmword ptr [rsp+150h+String.Buffer], xmm0
0x140002d6f  mov     [rbp+50h+var_C0], rsi
0x140002d73  call    cs:__imp_RtlInt64ToUnicodeString
0x140002d7a  nop     dword ptr [rax+rax+00h]
0x140002d7f  mov     rax, [rsp+150h+var_F8]
0x140002d84  lea     r8, [rsp+150h+String.Buffer]; String
0x140002d89  movzx   ecx, word ptr [rsp+150h+String.Buffer]
0x140002d8e  mov     edx, 10h; Base
0x140002d93  shr     rcx, 1
0x140002d96  mov     word ptr [rax+rcx*2], 3Ah ; ':'
0x140002d9c  movzx   eax, word ptr [rsp+150h+String.Buffer]
0x140002da1  add     ax, 2
0x140002da5  movzx   ecx, ax
0x140002da8  sub     word ptr [rsp+150h+String.Buffer+2], cx
0x140002dad  mov     rax, [rsp+150h+var_F8]
0x140002db2  mov     word ptr [rsp+150h+var_E8+8], cx
0x140002db7  shr     rcx, 1
0x140002dba  lea     rcx, [rax+rcx*2]
0x140002dbe  xor     eax, eax
0x140002dc0  mov     [rsp+150h+var_F8], rcx
0x140002dc5  mov     rcx, [rsi+18h]; Value
0x140002dc9  mov     word ptr [rsp+150h+String.Buffer], ax
0x140002dce  call    cs:__imp_RtlInt64ToUnicodeString
0x140002dd5  nop     dword ptr [rax+rax+00h]
0x140002dda  movzx   ecx, word ptr [rsp+150h+String.Buffer]
0x140002ddf  xor     edx, edx
0x140002de1  mov     rax, [rsp+150h+var_F8]
0x140002de6  shr     rcx, 1
0x140002de9  mov     word ptr [rax+rcx*2], 3Ah ; ':'
0x140002def  lea     rcx, Smb2GlobalFilePropertyCacheLock
0x140002df6  movzx   eax, word ptr [rsp+150h+String.Buffer]
0x140002dfb  add     ax, 2
0x140002dff  add     word ptr [rsp+150h+var_E8+8], ax
0x140002e04  mov     word ptr [rsp+150h+String.Buffer], ax
0x140002e09  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140002e10  nop     dword ptr [rax+rax+00h]
0x140002e15  mov     rcx, qword ptr [rsp+150h+String.Length]
0x140002e1a  lea     rdx, [rsp+150h+var_E8+8]
0x140002e1f  xor     r9d, r9d
0x140002e22  xor     r8d, r8d
0x140002e25  call    cs:__imp_RxNameCacheFetchEntryEx
0x140002e2c  nop     dword ptr [rax+rax+00h]
0x140002e31  mov     [rsp+150h+String.Buffer], rax
0x140002e36  mov     rsi, rax
0x140002e39  mov     byte ptr [rsp+150h+var_110], 1
0x140002e3e  test    rax, rax
0x140002e41  jnz     loc_1400031CA
0x140002e47  lea     rsi, WPP_GLOBAL_Control
0x140002e4e  xor     edx, edx
0x140002e50  lea     rcx, Smb2GlobalFilePropertyCacheLock
0x140002e57  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140002e5e  nop     dword ptr [rax+rax+00h]
0x140002e63  movzx   r9d, byte ptr [rsp+150h+var_110]
0x140002e69  lea     rax, [rsp+150h+var_110+1]
0x140002e6e  mov     r8, [rsp+150h+var_F0]
0x140002e73  mov     rdx, rbx
0x140002e76  mov     [rsp+150h+var_128], rax
0x140002e7b  mov     rcx, rdi
0x140002e7e  lea     rax, [rsp+150h+String]
0x140002e83  mov     [rsp+150h+Timeout], rax
0x140002e88  call    Smb2FindOrCreateDirCacheObject
0x140002e8d  mov     rbx, rax
0x140002e90  test    rax, rax
0x140002e93  jz      loc_1400031C0
0x140002e99  mov     eax, [rax+38h]
0x140002e9c  test    eax, eax
0x140002e9e  jnz     loc_140003227
0x140002ea4  mov     eax, [rbx+44h]
0x140002ea7  test    eax, eax
0x140002ea9  jnz     loc_140003227
0x140002eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140002eb6  movzx   edx, byte ptr [rsp+150h+var_110+1]
0x140002ebb  cmp     rcx, rsi
0x140002ebe  jz      short loc_140002ECD
0x140002ec0  test    dword ptr [rcx+2Ch], 100h
0x140002ec7  jnz     loc_140003474
0x140002ecd  test    dl, dl
0x140002ecf  jz      short loc_140002EE4
0x140002ed1  lock inc qword ptr [r13+218h]
0x140002ed9  mov     rdx, rbx
0x140002edc  mov     rcx, rdi
0x140002edf  call    Smb2PopulateDirectoryCache
0x140002ee4  mov     r8, [rdi+28h]; Irp
0x140002ee8  xor     edx, edx; Timeout
0x140002eea  mov     rcx, [rbx+70h]; Object
0x140002eee  call    cs:__imp_FsRtlCancellableWaitForSingleObject
0x140002ef5  nop     dword ptr [rax+rax+00h]
0x140002efa  mov     esi, eax
0x140002efc  test    eax, eax
0x140002efe  js      loc_14003810A
0x140002f04  cmp     dword ptr [rbx+20h], 0
0x140002f08  jnz     loc_1400031C0
0x140002f0e  mov     eax, [rbx+38h]
0x140002f11  test    eax, eax
0x140002f13  jnz     loc_1400031C0
0x140002f19  mov     eax, [rbx+44h]
0x140002f1c  test    eax, eax
0x140002f1e  jnz     loc_1400031C0
0x140002f24  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 2
0x140002f2b  jnz     loc_1400034A4
0x140002f31  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f38  lea     rdx, WPP_GLOBAL_Control
0x140002f3f  cmp     rcx, rdx
0x140002f42  jz      short loc_140002F51
0x140002f44  test    dword ptr [rcx+2Ch], 100h
0x140002f4b  jnz     loc_1400034E9
0x140002f51  mov     [r14+10h], rbx
0x140002f55  lea     rdx, cs:140000000h
0x140002f5c  cmp     r12d, 4Fh ; 'O'
0x140002f60  jnz     loc_1400030BC
0x140002f66  cmp     dword ptr [rbx+34h], 3Fh ; '?'
0x140002f6a  jnz     loc_1400030D1; jumptable 00000001400381B3 cases 1-3
0x140002f70  mov     rcx, [r14+10h]; jumptable 00000001400381B3 default case, cases 4-36,39-59,61,62,64-77,79
0x140002f74  call    Smb2DereferenceDirCacheObject
0x140002f79  xor     ebx, ebx
0x140002f7b  mov     esi, 0C0000016h
0x140002f80  jmp     def_140038104; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140002f85  lea     rcx, [r15+50h]; DestinationString
0x140002f89  xor     r8d, r8d; AllocateDestinationString
0x140002f8c  mov     rdx, rcx; SourceString
0x140002f8f  call    cs:__imp_RtlUpcaseUnicodeString
0x140002f96  nop     dword ptr [rax+rax+00h]
0x140002f9b  cmp     byte ptr [rdi+204h], 0
0x140002fa2  jnz     loc_1400030F0
0x140002fa8  mov     rax, [r14+10h]
0x140002fac  xor     ebx, ebx
0x140002fae  test    rax, rax
0x140002fb1  jz      loc_140003069
0x140002fb7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140002fbb  jz      loc_140003069
0x140002fc1  lock inc qword ptr [r13+228h]
0x140002fc9  mov     rcx, [r14+10h]
0x140002fcd  xor     edx, edx
0x140002fcf  add     rcx, 68h ; 'h'
0x140002fd3  call    cs:__imp_ExAcquirePushLockSharedEx
0x140002fda  nop     dword ptr [rax+rax+00h]
0x140002fdf  movzx   eax, byte ptr [rdi+205h]
0x140002fe6  lea     rcx, [rdi+1D8h]
0x140002fed  movzx   r8d, byte ptr [rdi+208h]
0x140002ff5  lea     rbx, [r14+18h]
0x140002ff9  mov     [rsp+150h+var_118], al; char
0x140002ffd  lea     rdx, [r15+50h]
0x140003001  mov     rax, [rdi+1C8h]
0x140003008  mov     r9d, r12d
0x14000300b  mov     [rsp+150h+var_120], rcx; __int64
0x140003010  mov     rcx, [r14+10h]; Context
0x140003014  mov     [rsp+150h+var_128], rax; __int64
0x140003019  mov     [rsp+150h+Timeout], rbx; __int64
0x14000301e  call    EnumerateDirectoryFromCache
0x140003023  mov     rcx, [r14+10h]
0x140003027  xor     edx, edx
0x140003029  add     rcx, 68h ; 'h'
0x14000302d  mov     esi, eax
0x14000302f  call    cs:__imp_ExReleasePushLockEx
0x140003036  nop     dword ptr [rax+rax+00h]
0x14000303b  cmp     esi, 80000006h
0x140003041  jz      loc_14000315F
0x140003047  mov     rcx, cs:WPP_GLOBAL_Control
0x14000304e  lea     rax, WPP_GLOBAL_Control
0x140003055  cmp     rcx, rax
0x140003058  jz      short loc_140003067
0x14000305a  test    dword ptr [rcx+2Ch], 100h
0x140003061  jnz     loc_140003524
0x140003067  xor     ebx, ebx
0x140003069  cmp     esi, 0C0000016h
0x14000306f  jnz     short loc_140003079
0x140003071  mov     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh; jumptable 0000000140038104 default case, cases 4-36,39-59,61,62,64-77,79
0x140003079  mov     r13, [rsp+150h+arg_10]
0x140003081  mov     r12, [rsp+150h+arg_8]
0x140003089  test    rbx, rbx
0x14000308c  jz      short loc_140003096
0x14000308e  mov     rcx, rbx; P
0x140003091  call    Smb2DereferenceDirCacheObject
0x140003096  mov     eax, esi
0x140003098  mov     rcx, [rbp+50h+var_30]
0x14000309c  xor     rcx, rsp; StackCookie
0x14000309f  call    __security_check_cookie
0x1400030a4  mov     rbx, [rsp+150h+arg_18]
0x1400030ac  add     rsp, 130h
0x1400030b3  pop     r15
0x1400030b5  pop     r14
0x1400030b7  pop     rdi
0x1400030b8  pop     rsi
0x1400030b9  pop     rbp
0x1400030ba  retn
0x1400030bc  cmp     r12d, 0Ch
0x1400030c0  jnz     loc_140038193
0x1400030c6  jmp     short loc_1400030D1; jumptable 00000001400381B3 cases 1-3
0x1400030c8  test    rbx, rbx; jumptable 00000001400381B3 cases 37,38,78
0x1400030cb  jnz     loc_140002F66
0x1400030d1  cmp     byte ptr [rdi+204h], 0; jumptable 00000001400381B3 cases 1-3
0x1400030d8  jnz     loc_140002F85
0x1400030de  cmp     byte ptr [rdi+207h], 0
0x1400030e5  jz      loc_140002F9B
  ... truncated ...
```
