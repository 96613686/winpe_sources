# Smb2UpdateFileInfoCacheEntry

- ea: `0x140007bd0`
- end: `0x140008477`
- name: `Smb2UpdateFileInfoCacheEntry`
- size: `2215`
- prototype: `char __fastcall(_QWORD *, struct _NAME_CACHE_CONTROL_ *, int, unsigned int, int, void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140005630`
- `0x140005820`
- `0x1400129f0`
- `0x140058140`

## callees

- `0x140007bd0`
- `0x14000ad90`
- `0x140012210`
- `0x140029c14`
- `0x14002a9ac`
- `0x140032f6c`
- `0x140037120`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140007e43`
- `ntoskrnl!ExAllocatePool2` at `0x140007e43`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140008049`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140008049`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140007f27`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140007f27`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140007f37`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140007f37`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008360`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140008360`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140007cf3`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140007d4e`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140008238`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x14000828e`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140007cf3`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140007d4e`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x140008238`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x14000828e`
- `ntoskrnl!KeBugCheckEx` at `0x14000838b`
- `ntoskrnl!KeBugCheckEx` at `0x14000838b`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400081f1`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400081f1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400080c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400080c6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140007da9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140007da9`
- `rdbss!RxNameCacheExpireEntry` at `0x1400082df`
- `rdbss!RxNameCacheExpireEntry` at `0x1400082df`
- `rdbss!RxNameCacheActivateEntry` at `0x140008073`
- `rdbss!RxNameCacheActivateEntry` at `0x140008073`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14000812b`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14000812b`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140007dd2`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400082c4`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140007dd2`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400082c4`
- `rdbss!RxCrackPathName` at `0x140007cab`
- `rdbss!RxCrackPathName` at `0x140007cab`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140007df3`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140007df3`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x140007c7d`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x140007c7d`
- `mrxsmb!MRxSmbDeviceObject` at `0x140007ee0`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140007ef4`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140007ef4`

## pseudocode

```c
char __fastcall Smb2UpdateFileInfoCacheEntry(
        _QWORD *a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        int a3,
        unsigned int a4,
        int a5,
        void *Src,
        size_t Size)
{
  __int64 v7; // rsi
  __int64 v9; // r14
  struct _NAME_CACHE_CONTROL_ *v10; // r15
  unsigned __int64 v12; // rax
  unsigned int v13; // ebx
  unsigned __int64 v14; // rcx
  ULONGLONG v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rsi
  __int64 InstanceConfigurationBlock; // rax
  __int64 *v19; // rcx
  __int64 *v20; // rsi
  int v21; // r15d
  int v22; // eax
  __int64 v23; // r12
  __int64 Pool2; // rax
  __int64 v25; // r15
  char v26; // r12
  __int16 v27; // ax
  __int64 v28; // rbx
  __int64 v29; // rdi
  KIRQL v30; // r14
  ULONG_PTR v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  _QWORD *v36; // rdx
  _QWORD *v37; // r8
  __int64 v38; // rax
  unsigned __int64 v39; // rcx
  char v40; // di
  ULONG v41; // r8d
  int v42; // edx
  int v43; // r8d
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rax
  ULONGLONG v47; // rcx
  unsigned __int64 v48; // rcx
  ULONGLONG v49; // rcx
  struct _NAME_CACHE *Entry; // rax
  __int64 FirstBindingObject; // rax
  int v53; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING String; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+90h] [rbp-70h]
  int v59; // [rsp+94h] [rbp-6Ch]
  __int64 v60; // [rsp+98h] [rbp-68h]
  ULONG MRxContext; // [rsp+A0h] [rbp-60h]
  __int64 v62; // [rsp+A8h] [rbp-58h]
  UNICODE_STRING Source; // [rsp+B0h] [rbp-50h] BYREF
  PNAME_CACHE_CONTROL NameCacheCtl; // [rsp+C0h] [rbp-40h]
  char v65; // [rsp+D0h] [rbp-30h] BYREF

  v7 = a1[7];
  v59 = a3;
  v9 = *(_QWORD *)(v7 + 136);
  v10 = a2;
  Source = 0;
  NameCacheCtl = a2;
  Destination = 0;
  LODWORD(v12) = *(_DWORD *)(v9 + 8);
  *(_QWORD *)&v57.Length = v7;
  v62 = v9;
  if ( (v12 & 2) == 0 )
    return v12;
  LOBYTE(v12) = a3 - 1;
  if ( a3 == 1 )
  {
    v13 = Size;
    LODWORD(v12) = FsRtlValidateFileInformationBufferEx(0, a4, Src, (unsigned int)Size, 0, 0, 0);
    if ( (v12 & 0x80000000) != 0LL )
      return v12;
LABEL_4:
    v60 = a1[7] + 360LL;
    RxCrackPathName(v60, 0, 0, &Source);
    *(_DWORD *)&Destination.Length = 0x1000000;
    Destination.Buffer = (PWSTR)&v65;
    String = Destination;
    if ( Source.Length )
    {
      v12 = Source.Length + 68LL;
      if ( v12 > 0x100 )
        return v12;
    }
    RtlInt64ToUnicodeString(*(_QWORD *)(v9 + 32), 0x10u, &String);
    String.Buffer[(unsigned __int64)String.Length >> 1] = 58;
    v14 = (unsigned __int16)(String.Length + 2);
    String.MaximumLength -= v14;
    Destination.Length = String.Length + 2;
    String.Buffer += v14 >> 1;
    v15 = *(_QWORD *)(v9 + 24);
    String.Length = 0;
    RtlInt64ToUnicodeString(v15, 0x10u, &String);
    String.Buffer[(unsigned __int64)String.Length >> 1] = 58;
    Destination.Length += String.Length + 2;
    String.Length += 2;
    if ( Source.Length )
      RtlAppendUnicodeStringToString(&Destination, &Source);
    MRxContext = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1[9] + 40LL) + 40LL) + 264LL);
    ExAcquirePushLockExclusiveEx(&Smb2FileInfoCacheLock, 0);
    *(_BYTE *)(*(_QWORD *)(v7 + 136) + 81LL) = 1;
    *(_QWORD *)&String.Length = RxNameCacheFetchEntryEx(v10, &Destination, 0, 0);
    v17 = *(_QWORD *)&String.Length;
    if ( !*(_QWORD *)&String.Length )
    {
      LOBYTE(v16) = 1;
      v45 = RxNameCacheCreateEntryEx(v10, &Destination, 0, v16);
      *(_QWORD *)&String.Length = v45;
      v17 = v45;
      if ( !v45 )
      {
LABEL_49:
        if ( Source.Length )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qZ(
              WPP_GLOBAL_Control->AttachedDevice,
              12,
              (unsigned int)WPP_165ae4eb9836382541088391da4351a7_Traceguids,
              (_DWORD)a1,
              a1[7] + 360LL);
          }
          Destination.Length = 0;
          v47 = *(_QWORD *)(v9 + 32);
          v57 = Destination;
          RtlInt64ToUnicodeString(v47, 0x10u, &v57);
          v57.Buffer[(unsigned __int64)v57.Length >> 1] = 58;
          v48 = (unsigned __int16)(v57.Length + 2);
          v57.MaximumLength -= v48;
          Destination.Length = v57.Length + 2;
          v57.Buffer += v48 >> 1;
          v49 = *(_QWORD *)(v9 + 24);
          v57.Length = 0;
          RtlInt64ToUnicodeString(v49, 0x10u, &v57);
          v57.Buffer[(unsigned __int64)v57.Length >> 1] = 58;
          Destination.Length += v57.Length + 2;
          Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v10, &Destination, 0, 0);
          if ( Entry )
            RxNameCacheExpireEntry(v10, Entry);
        }
        LOBYTE(v12) = ExReleasePushLockExclusiveEx(&Smb2FileInfoCacheLock, 0);
        return v12;
      }
      v46 = *(_QWORD *)(v45 + 40);
      *(_QWORD *)(v46 + 20) = 96;
      *(_WORD *)(v46 + 10) = -1;
      *(_QWORD *)(v46 + 12) = 84;
      *(_QWORD *)v46 = 0;
    }
    InstanceConfigurationBlock = MRxSmbGetInstanceConfigurationBlock(a1[10]);
    v19 = *(__int64 **)(v17 + 40);
    v20 = 0;
    v21 = *(_DWORD *)(InstanceConfigurationBlock + 12);
    v58 = v21;
    while ( v19 )
    {
      v27 = *((_WORD *)v19 + 5);
      if ( v27 == (_WORD)a3 && *((_DWORD *)v19 + 3) == a4 && *((_DWORD *)v19 + 4) == a5 )
      {
        if ( *((_DWORD *)v19 + 5) >= v13 )
          goto LABEL_19;
        *((_WORD *)v19 + 5) = -1;
        *(__int64 *)((char *)v19 + 12) = 84;
        *((_DWORD *)v19 + 6) = 0;
      }
      else if ( v27 == -1 && *((_DWORD *)v19 + 5) >= v13 )
      {
        *((_WORD *)v19 + 5) = a3;
        *((_DWORD *)v19 + 3) = a4;
        *((_DWORD *)v19 + 4) = a5;
LABEL_19:
        *((_DWORD *)v19 + 6) = v13;
        memmove((char *)v19 + 28, Src, v13);
        v26 = 1;
        goto LABEL_20;
      }
      v20 = v19;
      v19 = (__int64 *)*v19;
    }
    v22 = v13 + 47;
    if ( a3 != 3 )
      v22 = 47;
    v23 = (v13 + v22) & 0xFFFFFFF0;
    Pool2 = ExAllocatePool2(258, v23, 1666086994);
    v25 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 20) = v23 - 32;
      *(_WORD *)(Pool2 + 10) = v59;
      *(_DWORD *)(Pool2 + 12) = a4;
      *(_DWORD *)(Pool2 + 16) = a5;
      *(_DWORD *)(Pool2 + 24) = v13;
      *(_QWORD *)Pool2 = 0;
      memmove((void *)(Pool2 + 28), Src, v13);
      *v20 = v25;
      v26 = 1;
    }
    else
    {
      v26 = 0;
    }
    v21 = v58;
LABEL_20:
    if ( a1[10] != MRxSmbDeviceObject || !*(_BYTE *)(MRxSmbGetConfigurationBlock(MRxSmbDeviceObject) + 232) )
    {
LABEL_42:
      v40 = MRxContext;
      if ( !v26 )
        v21 = 0;
      v41 = v21;
      v10 = NameCacheCtl;
      RxNameCacheActivateEntry(NameCacheCtl, *(PNAME_CACHE *)&String.Length, v41, MRxContext);
      v44 = v60;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qdddZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          v42,
          v43,
          (_DWORD)a1,
          v40,
          v59,
          a4,
          (__int64)&Destination,
          v60);
      }
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
      {
        LOWORD(v53) = *(_WORD *)v44 >> 1;
        McTemplateK0pphzr2q_EtwWriteTransfer(
          (unsigned __int16)v53,
          (unsigned int)SmbUpdateInfoCache,
          (_DWORD)a1 + 412,
          (_DWORD)a1,
          *(_DWORD *)&v57.Length,
          v53,
          *(_QWORD *)(v44 + 8));
      }
      v9 = v62;
      goto LABEL_49;
    }
    v21 = 0;
    v28 = *(_QWORD *)(*(_QWORD *)(a1[9] + 40LL) + 40LL);
    v29 = *(_QWORD *)(v28 + 24);
    v30 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v29 + 1920));
    *(_DWORD *)(v29 + 2352) = (unsigned int)PsGetCurrentThreadId();
    if ( *(_DWORD *)(v28 + 12) )
    {
LABEL_41:
      *(_DWORD *)(v29 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v29 + 1920), v30);
      goto LABEL_42;
    }
    v32 = *(_QWORD *)(v28 + 416);
    v33 = *(unsigned __int16 *)(v32 + 2);
    if ( (_WORD)v33 )
    {
      v34 = v33 + v32 + 8;
      if ( !v34 )
        goto LABEL_59;
    }
    else
    {
      v34 = 8;
    }
    v35 = *(_QWORD **)v34;
    if ( *(_QWORD *)v34 )
    {
      v36 = *(_QWORD **)(v34 + 8);
      if ( v36 )
      {
        if ( v35[1] == v34 && *v36 == v34 )
        {
          while ( v35 != (_QWORD *)v34 )
          {
            if ( !v35 )
              goto LABEL_59;
            if ( !*v35 )
              goto LABEL_59;
            v37 = (_QWORD *)v35[1];
            if ( !v37 || *(_QWORD **)(*v35 + 8LL) != v35 || (_QWORD *)*v37 != v35 )
              goto LABEL_59;
            v31 = (ULONG_PTR)(v35 - 50);
            v36 = (_QWORD *)*((int *)v35 - 98);
            if ( (int)v36 < 0 )
              KeBugCheckEx(0x27u, 0xA0001u, v31, *((int *)v35 - 98), 0);
            if ( *(_WORD *)v31 != 0xE2FF )
            {
              if ( v35 != (_QWORD *)400 )
              {
                v38 = *(_QWORD *)(v31 + 392);
                if ( v38 )
                  goto LABEL_39;
              }
              break;
            }
            v35 = (_QWORD *)*v35;
          }
          FirstBindingObject = SmbCeGetFirstBindingObjectEx(
                                 *(_QWORD *)(*(_QWORD *)(v28 + 416) + 384LL),
                                 v36,
                                 v31,
                                 58111);
          if ( !FirstBindingObject )
            goto LABEL_41;
          v38 = *(_QWORD *)(FirstBindingObject + 392);
          if ( !v38 )
            goto LABEL_41;
LABEL_39:
          v39 = *(_QWORD *)(v38 + 280);
          if ( v39 >= 0xC738 )
          {
            v21 = 60;
            if ( v39 < 0x31128 )
              v21 = 30;
          }
          else
          {
            v21 = 10;
          }
          goto LABEL_41;
        }
      }
    }
LABEL_59:
    __fastfail(3u);
  }
  if ( a3 == 3 )
  {
    v13 = Size;
    LOBYTE(v12) = RtlValidRelativeSecurityDescriptor(Src, Size, 0);
    if ( !(_BYTE)v12 )
      return v12;
    goto LABEL_4;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v12) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (v12 & 0x80u) != 0LL )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        LOBYTE(v12) = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_165ae4eb9836382541088391da4351a7_Traceguids);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140007bd0  push    rbp
0x140007bd2  push    rsi
0x140007bd3  push    rdi
0x140007bd4  push    r12
0x140007bd6  push    r13
0x140007bd8  push    r14
0x140007bda  push    r15
0x140007bdc  lea     rbp, [rsp-0E0h]
0x140007be4  sub     rsp, 1E0h
0x140007beb  mov     rax, cs:__security_cookie
0x140007bf2  xor     rax, rsp
0x140007bf5  mov     [rbp+110h+var_40], rax
0x140007bfc  mov     rsi, [rcx+38h]
0x140007c00  xorps   xmm0, xmm0
0x140007c03  mov     rdi, [rbp+110h+Src]
0x140007c0a  xorps   xmm1, xmm1
0x140007c0d  mov     r10d, r9d
0x140007c10  mov     [rsp+210h+var_1C0], r9d
0x140007c15  mov     r12d, r8d
0x140007c18  mov     [rbp+110h+var_17C], r8d
0x140007c1c  mov     r14, [rsi+88h]
0x140007c23  mov     r15, rdx
0x140007c26  movups  xmmword ptr [rbp+110h+Source.Length], xmm0
0x140007c2a  mov     [rbp+110h+NameCacheCtl], rdx
0x140007c2e  mov     r13, rcx
0x140007c31  movups  xmmword ptr [rsp+210h+Destination.Length], xmm1
0x140007c36  mov     eax, [r14+8]
0x140007c3a  mov     qword ptr [rbp+110h+var_190.Length], rsi
0x140007c3e  mov     [rbp+110h+var_168], r14
0x140007c42  test    al, 2
0x140007c44  jz      loc_1400080DA
0x140007c4a  mov     eax, r8d
0x140007c4d  mov     [rsp+210h+arg_10], rbx
0x140007c55  xor     ecx, ecx
0x140007c57  sub     eax, 1
0x140007c5a  jnz     loc_1400081DA
0x140007c60  mov     ebx, dword ptr [rbp+110h+Size]
0x140007c66  mov     r8, rdi
0x140007c69  mov     dword ptr [rsp+210h+var_1E0], ecx
0x140007c6d  mov     r9d, ebx
0x140007c70  mov     [rsp+210h+var_1E8], rcx
0x140007c75  mov     edx, r10d
0x140007c78  mov     [rsp+210h+BugCheckParameter4], rcx
0x140007c7d  call    cs:__imp_FsRtlValidateFileInformationBufferEx
0x140007c84  nop     dword ptr [rax+rax+00h]
0x140007c89  test    eax, eax
0x140007c8b  js      loc_1400080D2
0x140007c91  mov     rax, [r13+38h]
0x140007c95  lea     r9, [rbp+110h+Source]
0x140007c99  add     rax, 168h
0x140007c9f  xor     r8d, r8d
0x140007ca2  mov     rcx, rax
0x140007ca5  mov     [rbp+110h+var_178], rax
0x140007ca9  xor     edx, edx
0x140007cab  call    cs:__imp_RxCrackPathName
0x140007cb2  nop     dword ptr [rax+rax+00h]
0x140007cb7  lea     rax, [rbp+110h+var_140]
0x140007cbb  mov     dword ptr [rsp+210h+Destination.Length], 1000000h
0x140007cc3  mov     [rsp+210h+Destination.Buffer], rax
0x140007cc8  mov     ecx, 100h
0x140007ccd  movzx   eax, [rbp+110h+Source.Length]
0x140007cd1  movaps  xmm0, xmmword ptr [rsp+210h+Destination.Length]
0x140007cd6  movdqa  xmmword ptr [rsp+210h+String.Length], xmm0
0x140007cdc  test    ax, ax
0x140007cdf  jnz     loc_1400081AD
0x140007ce5  mov     rcx, [r14+20h]; Value
0x140007ce9  lea     r8, [rsp+210h+String]; String
0x140007cee  mov     edx, 10h; Base
0x140007cf3  call    cs:__imp_RtlInt64ToUnicodeString
0x140007cfa  nop     dword ptr [rax+rax+00h]
0x140007cff  mov     rax, [rsp+210h+String.Buffer]
0x140007d04  lea     r8, [rsp+210h+String]; String
0x140007d09  movzx   ecx, [rsp+210h+String.Length]
0x140007d0e  mov     edx, 10h; Base
0x140007d13  shr     rcx, 1
0x140007d16  mov     word ptr [rax+rcx*2], 3Ah ; ':'
0x140007d1c  movzx   eax, [rsp+210h+String.Length]
0x140007d21  add     ax, 2
0x140007d25  movzx   ecx, ax
0x140007d28  sub     [rsp+210h+String.MaximumLength], cx
0x140007d2d  mov     rax, [rsp+210h+String.Buffer]
0x140007d32  mov     [rsp+210h+Destination.Length], cx
0x140007d37  shr     rcx, 1
0x140007d3a  lea     rcx, [rax+rcx*2]
0x140007d3e  xor     eax, eax
0x140007d40  mov     [rsp+210h+String.Buffer], rcx
0x140007d45  mov     rcx, [r14+18h]; Value
0x140007d49  mov     [rsp+210h+String.Length], ax
0x140007d4e  call    cs:__imp_RtlInt64ToUnicodeString
0x140007d55  nop     dword ptr [rax+rax+00h]
0x140007d5a  movzx   ecx, [rsp+210h+String.Length]
0x140007d5f  mov     rax, [rsp+210h+String.Buffer]
0x140007d64  shr     rcx, 1
0x140007d67  mov     word ptr [rax+rcx*2], 3Ah ; ':'
0x140007d6d  movzx   eax, [rsp+210h+String.Length]
0x140007d72  add     ax, 2
0x140007d76  add     [rsp+210h+Destination.Length], ax
0x140007d7b  cmp     [rbp+110h+Source.Length], 0
0x140007d80  mov     [rsp+210h+String.Length], ax
0x140007d85  jnz     loc_140008357
0x140007d8b  mov     rax, [r13+48h]
0x140007d8f  xor     edx, edx
0x140007d91  mov     rcx, [rax+28h]
0x140007d95  mov     rax, [rcx+28h]
0x140007d99  lea     rcx, Smb2FileInfoCacheLock
0x140007da0  mov     eax, [rax+108h]
0x140007da6  mov     [rbp+110h+MRxContext], eax
0x140007da9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140007db0  nop     dword ptr [rax+rax+00h]
0x140007db5  mov     rcx, [rsi+88h]
0x140007dbc  lea     rdx, [rsp+210h+Destination]
0x140007dc1  mov     eax, 1
0x140007dc6  xor     r9d, r9d
0x140007dc9  xor     r8d, r8d
0x140007dcc  xchg    al, [rcx+51h]
0x140007dcf  mov     rcx, r15
0x140007dd2  call    cs:__imp_RxNameCacheFetchEntryEx
0x140007dd9  nop     dword ptr [rax+rax+00h]
0x140007dde  mov     qword ptr [rsp+210h+String.Length], rax
0x140007de3  mov     rsi, rax
0x140007de6  test    rax, rax
0x140007de9  jz      loc_14000811D
0x140007def  mov     rcx, [r13+50h]
0x140007df3  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140007dfa  nop     dword ptr [rax+rax+00h]
0x140007dff  mov     rcx, [rsi+28h]
0x140007e03  mov     r8d, 0FFFFh
0x140007e09  mov     r14d, [rbp+110h+arg_20]
0x140007e10  xor     esi, esi
0x140007e12  mov     r15d, [rax+0Ch]
0x140007e16  mov     [rbp+110h+var_180], r15d
0x140007e1a  test    rcx, rcx
0x140007e1d  jnz     short loc_140007E9D
0x140007e1f  cmp     r12d, 3
0x140007e23  lea     eax, [rbx+2Fh]
0x140007e26  mov     ecx, 2Fh ; '/'
0x140007e2b  mov     r8d, 634E7852h
0x140007e31  cmovnz  eax, ecx
0x140007e34  mov     ecx, 102h
0x140007e39  add     eax, ebx
0x140007e3b  and     eax, 0FFFFFFF0h
0x140007e3e  mov     edx, eax
0x140007e40  mov     r12d, eax
0x140007e43  call    cs:__imp_ExAllocatePool2
0x140007e4a  nop     dword ptr [rax+rax+00h]
0x140007e4f  mov     r15, rax
0x140007e52  test    rax, rax
0x140007e55  jz      loc_140008371
0x140007e5b  lea     ecx, [r12-20h]
0x140007e60  mov     r8d, ebx; Size
0x140007e63  mov     [rax+14h], ecx
0x140007e66  mov     rdx, rdi; Src
0x140007e69  mov     eax, [rbp+110h+var_17C]
0x140007e6c  lea     rcx, [r15+1Ch]; void *
0x140007e70  mov     [r15+0Ah], ax
0x140007e75  mov     eax, [rsp+210h+var_1C0]
0x140007e79  mov     [r15+0Ch], eax
0x140007e7d  mov     [r15+10h], r14d
0x140007e81  mov     [r15+18h], ebx
0x140007e85  mov     qword ptr [r15], 0
0x140007e8c  call    memmove
0x140007e91  mov     [rsi], r15
0x140007e94  mov     r12b, 1
0x140007e97  mov     r15d, [rbp+110h+var_180]
0x140007e9b  jmp     short loc_140007EE0
0x140007e9d  movzx   eax, word ptr [rcx+0Ah]
0x140007ea1  mov     edx, [rsp+210h+var_1C0]
0x140007ea5  cmp     ax, r12w
0x140007ea9  jnz     loc_1400080FD
0x140007eaf  cmp     [rcx+0Ch], edx
0x140007eb2  jnz     loc_1400080FD
0x140007eb8  cmp     [rcx+10h], r14d
0x140007ebc  jnz     loc_1400080FD
0x140007ec2  cmp     [rcx+14h], ebx
0x140007ec5  jb      loc_14000816E
0x140007ecb  mov     [rcx+18h], ebx
0x140007ece  mov     rdx, rdi; Src
0x140007ed1  add     rcx, 1Ch; void *
0x140007ed5  mov     r8d, ebx; Size
0x140007ed8  call    memmove
0x140007edd  mov     r12b, 1
0x140007ee0  mov     rax, cs:__imp_MRxSmbDeviceObject
0x140007ee7  mov     rcx, [rax]
0x140007eea  cmp     [r13+50h], rcx
0x140007eee  jnz     loc_140008055
0x140007ef4  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140007efb  nop     dword ptr [rax+rax+00h]
0x140007f00  cmp     byte ptr [rax+0E8h], 0
0x140007f07  jz      loc_140008055
0x140007f0d  mov     rax, [r13+48h]
0x140007f11  xor     r15d, r15d
0x140007f14  mov     rcx, [rax+28h]
0x140007f18  mov     rbx, [rcx+28h]
0x140007f1c  mov     rdi, [rbx+18h]
0x140007f20  lea     rcx, [rdi+780h]; SpinLock
0x140007f27  call    cs:__imp_ExAcquireSpinLockExclusive
0x140007f2e  nop     dword ptr [rax+rax+00h]
0x140007f33  movzx   r14d, al
0x140007f37  call    cs:__imp_PsGetCurrentThreadId
0x140007f3e  nop     dword ptr [rax+rax+00h]
0x140007f43  mov     [rdi+930h], eax
0x140007f49  cmp     [rbx+0Ch], r15d
0x140007f4d  jnz     loc_140008034
0x140007f53  mov     rcx, [rbx+1A0h]
0x140007f5a  movzx   edx, word ptr [rcx+2]
0x140007f5e  test    dx, dx
0x140007f61  jz      loc_14000819B
0x140007f67  add     rcx, 8
0x140007f6b  add     rcx, rdx
0x140007f6e  jz      loc_140008194
0x140007f74  mov     rax, [rcx]
0x140007f77  test    rax, rax
0x140007f7a  jz      loc_140008194
0x140007f80  mov     rdx, [rcx+8]
0x140007f84  test    rdx, rdx
0x140007f87  jz      loc_140008194
0x140007f8d  cmp     [rax+8], rcx
0x140007f91  jnz     loc_140008194
0x140007f97  cmp     [rdx], rcx
0x140007f9a  jnz     loc_140008194
0x140007fa0  mov     r9d, 0E2FFh
0x140007fa6  cmp     rax, rcx
0x140007fa9  jz      loc_140008398
0x140007faf  test    rax, rax
0x140007fb2  jz      loc_140008194
0x140007fb8  mov     rdx, [rax]
0x140007fbb  test    rdx, rdx
0x140007fbe  jz      loc_140008194
0x140007fc4  mov     r8, [rax+8]
0x140007fc8  test    r8, r8
0x140007fcb  jz      loc_140008194
0x140007fd1  cmp     [rdx+8], rax
0x140007fd5  jnz     loc_140008194
0x140007fdb  cmp     [r8], rax
0x140007fde  jnz     loc_140008194
0x140007fe4  lea     r8, [rax-190h]; BugCheckParameter2
0x140007feb  movsxd  rdx, dword ptr [r8+8]
0x140007fef  test    edx, edx
0x140007ff1  js      loc_140008379
0x140007ff7  cmp     [r8], r9w
0x140007ffb  jz      loc_1400081A5
0x140008001  test    r8, r8
0x140008004  jz      loc_140008398
0x14000800a  mov     rax, [r8+188h]
0x140008011  test    rax, rax
0x140008014  jz      loc_140008398
0x14000801a  mov     rcx, [rax+118h]
0x140008021  cmp     rcx, 0C738h
0x140008028  jnb     loc_1400081BF
0x14000802e  mov     r15d, 0Ah
0x140008034  movzx   edx, r14b; OldIrql
0x140008038  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x140008042  lea     rcx, [rdi+780h]; SpinLock
0x140008049  call    cs:__imp_ExReleaseSpinLockExclusive
0x140008050  nop     dword ptr [rax+rax+00h]
0x140008055  mov     edi, [rbp+110h+MRxContext]
0x140008058  xor     eax, eax
0x14000805a  mov     rdx, qword ptr [rsp+210h+String.Length]; NameCache
0x14000805f  test    r12b, r12b
0x140008062  mov     r9d, edi; MRxContext
0x140008065  cmovz   r15d, eax
0x140008069  mov     r8d, r15d; LifeTime
0x14000806c  mov     r15, [rbp+110h+NameCacheCtl]
0x140008070  mov     rcx, r15; NameCacheCtl
0x140008073  call    cs:__imp_RxNameCacheActivateEntry
0x14000807a  nop     dword ptr [rax+rax+00h]
0x14000807f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008086  lea     rsi, WPP_GLOBAL_Control
0x14000808d  mov     rbx, [rbp+110h+var_178]
0x140008091  cmp     rcx, rsi
0x140008094  jz      short loc_1400080A1
0x140008096  mov     eax, [rcx+2Ch]
0x140008099  test    al, al
0x14000809b  js      loc_1400083B9
0x1400080a1  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 2
0x1400080a8  jnz     loc_1400083F6
0x1400080ae  mov     r14, [rbp+110h+var_168]
0x1400080b2  cmp     [rbp+110h+Source.Length], 0
0x1400080b7  jnz     loc_14000820A
0x1400080bd  xor     edx, edx
0x1400080bf  lea     rcx, Smb2FileInfoCacheLock
0x1400080c6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400080cd  nop     dword ptr [rax+rax+00h]
0x1400080d2  mov     rbx, [rsp+210h+arg_10]
0x1400080da  mov     rcx, [rbp+110h+var_40]
0x1400080e1  xor     rcx, rsp; StackCookie
0x1400080e4  call    __security_check_cookie
0x1400080e9  add     rsp, 1E0h
0x1400080f0  pop     r15
0x1400080f2  pop     r14
0x1400080f4  pop     r13
0x1400080f6  pop     r12
0x1400080f8  pop     rdi
0x1400080f9  pop     rsi
0x1400080fa  pop     rbp
0x1400080fb  retn
0x1400080fd  cmp     ax, r8w
0x140008101  jnz     loc_140008189
0x140008107  cmp     [rcx+14h], ebx
0x14000810a  jb      short loc_140008189
  ... truncated ...
```
