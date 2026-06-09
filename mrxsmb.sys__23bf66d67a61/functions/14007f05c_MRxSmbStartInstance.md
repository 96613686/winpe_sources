# MRxSmbStartInstance

- ea: `0x14007f05c`
- end: `0x14007f583`
- name: `MRxSmbStartInstance`
- size: `1319`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x14001f0e0`

## callees

- `0x140010f94`
- `0x1400255d0`
- `0x14003838c`
- `0x14003d8dc`
- `0x140040938`
- `0x1400417ec`
- `0x140042f6c`
- `0x140043044`
- `0x1400432d8`
- `0x14004334c`
- `0x14007f05c`
- `0x1400822b0`
- `0x1400823fc`

## import_xrefs

- `ntoskrnl!IoUnregisterFileSystem` at `0x14007f545`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14007f545`
- `ntoskrnl!IoRegisterFileSystem` at `0x14007f26d`
- `ntoskrnl!IoRegisterFileSystem` at `0x14007f26d`
- `rdbss!RxUnregisterMinirdr` at `0x14007f555`
- `rdbss!RxUnregisterMinirdr` at `0x14007f555`
- `rdbss!RxNameCacheFinalize` at `0x14007f50c`
- `rdbss!RxNameCacheFinalize` at `0x14007f50c`
- `rdbss!RxNameCacheInitializeEx` at `0x14007f493`
- `rdbss!RxNameCacheInitializeEx` at `0x14007f493`
- `rdbss!RxRegisterMinirdr` at `0x14007f1d6`
- `rdbss!RxRegisterMinirdr` at `0x14007f1d6`
- `rdbss!RxStartMinirdr` at `0x14007f4bf`
- `rdbss!RxStartMinirdr` at `0x14007f4bf`

## pseudocode

```c
__int64 __fastcall MRxSmbStartInstance(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v4; // edx
  __int16 v5; // r13
  __int16 v6; // r15
  __int16 v7; // r8
  int v8; // ecx
  ULONG DeviceExtensionSize; // ebx
  int v10; // eax
  ULONG v11; // r12d
  ULONG DeviceCharacteristics; // edi
  NTSTATUS v13; // eax
  NTSTATUS started; // edi
  PRDBSS_DEVICE_OBJECT v15; // rax
  int v16; // ebx
  struct _LIST_ENTRY **p_Blink; // rdi
  struct _LIST_ENTRY *v18; // r8
  PRDBSS_DEVICE_OBJECT v19; // rdx
  unsigned __int64 v20; // rdx
  PRDBSS_DEVICE_OBJECT v21; // rcx
  __int64 v22; // rbx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  int v27; // ebx
  int v28; // ebx
  UNICODE_STRING DeviceName; // [rsp+40h] [rbp-10h] BYREF
  PRDBSS_DEVICE_OBJECT DeviceObject; // [rsp+98h] [rbp+48h] BYREF
  __int16 v33; // [rsp+A0h] [rbp+50h]

  DeviceObject = 0;
  DeviceName = 0;
  if ( a3 < 0x7C )
    return (unsigned int)-1073741808;
  v4 = *(unsigned __int16 *)(a2 + 118);
  if ( !(_WORD)v4 || (v4 & 1) != 0 || a3 < v4 || a3 < v4 + 120 )
    return (unsigned int)-1073741808;
  v5 = *(_WORD *)(a2 + 12) & 2;
  v6 = *(_WORD *)(a2 + 12) & 0x40;
  v7 = *(_WORD *)(a2 + 12) & 0x80;
  v8 = ((*(_WORD *)(a2 + 12) & 0x10) << 10) | 0x687;
  v33 = *(_WORD *)(a2 + 12) & 4;
  DeviceExtensionSize = v6 != 0 ? 1604 : 1536;
  if ( v33 )
  {
    v8 |= 0x40000u;
    DeviceExtensionSize = v6 != 0 ? 1748 : 1680;
  }
  DeviceName.MaximumLength = v4;
  v10 = v8 | 0x8800;
  DeviceName.Length = v4;
  if ( !v7 )
    v10 = v8;
  v11 = v10 | 0x20000;
  DeviceCharacteristics = v7 != 0 ? 655376 : 16;
  if ( v5 )
    v11 = v10;
  DeviceName.Buffer = (wchar_t *)(a2 + 120);
  if ( !*(_BYTE *)(a2 + 116)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids, &DeviceName);
  }
  v13 = RxRegisterMinirdr(
          &DeviceObject,
          *(PDRIVER_OBJECT *)(*(_QWORD *)(a1 + 80) + 8LL),
          (PMINIRDR_DISPATCH)&MRxSmbDispatch,
          v11,
          &DeviceName,
          DeviceExtensionSize,
          0x14u,
          DeviceCharacteristics);
  started = v13;
  if ( v13 >= 0 )
  {
    v15 = DeviceObject;
    v16 = 1;
    LODWORD(DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Flink) = -1;
    p_Blink = &v15[1].RxNetNameTableInDeviceObject.HashBuckets[23].Blink;
    WORD1(DeviceObject->RxNetNameTableInDeviceObject.HashBuckets[30].Blink) = *(_WORD *)(a2 + 12);
    if ( v5 )
    {
      IoRegisterFileSystem(&DeviceObject->DeviceObject);
      v16 = 2;
    }
    if ( v6 )
    {
      v18 = (struct _LIST_ENTRY *)(((unsigned __int64)p_Blink + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink = v18;
      v19 = DeviceObject;
      p_Blink = (struct _LIST_ENTRY **)((char *)&v18[3].Blink + 4);
      DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink->Flink = *(struct _LIST_ENTRY **)(a2 + 20);
      v19[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink->Blink = *(struct _LIST_ENTRY **)(a2 + 28);
      v19[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink[1] = *(struct _LIST_ENTRY *)(a2 + 36);
      v19[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink[2] = *(struct _LIST_ENTRY *)(a2 + 52);
      LODWORD(v19[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink[3].Flink) = *(_DWORD *)(a2 + 68);
      HIDWORD(v19[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink[3].Flink) = *(_DWORD *)(a2 + 72);
      LOBYTE(v19[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink[3].Blink) = *(_BYTE *)(a2 + 76);
      BYTE1(v19[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink[3].Blink) = *(_BYTE *)(a2 + 77);
    }
    else
    {
      DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink = (struct _LIST_ENTRY *)&dword_14007D104;
    }
    if ( v33 )
      v20 = ((unsigned __int64)p_Blink + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    else
      v20 = 0;
    started = MRxSmbInitializeTransportArrayInstance(DeviceObject, v20);
    if ( started >= 0 )
    {
      started = InitialializeSubRdrDialectTable(DeviceObject);
      if ( started < 0 )
        goto LABEL_47;
      started = MRxSmbInitializeConnectionEngine(DeviceObject);
      if ( started < 0 )
        goto LABEL_46;
      started = MRxSmbInitializeExchangeEngine(DeviceObject);
      if ( started < 0
        || (MRxSmbSubRdrInstanceNotification(DeviceObject, a2),
            started = StartSubRedirectorForDialect(DeviceObject, 0),
            started < 0) )
      {
LABEL_45:
        MRxSmbStopConnectionEngine(DeviceObject);
        UninitializeSubRdrCertificateMappingsList(DeviceObject);
        goto LABEL_46;
      }
      LOBYTE(DeviceObject->RxNetNameTableInDeviceObject.HashBuckets[30].Blink) = *(_BYTE *)(a2 + 116);
      LODWORD(DeviceObject[1].RxNetNameTableInDeviceObject.MemberQueue.Blink) = *(_DWORD *)(a2 + 4);
      HIDWORD(DeviceObject[1].RxNetNameTableInDeviceObject.MemberQueue.Blink) = *(_DWORD *)(a2 + 8);
      BYTE1(DeviceObject->RxNetNameTableInDeviceObject.HashBuckets[30].Blink) = *(_BYTE *)(a2 + 12) & 1;
      v21 = DeviceObject;
      *(_OWORD *)&DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.OwnerTable = *(_OWORD *)(a2 + 80);
      *(_OWORD *)&v21[1].RxNetNameTableInDeviceObject.TableLock.SharedWaiters = *(_OWORD *)(a2 + 96);
      LODWORD(v21[1].RxNetNameTableInDeviceObject.TableLock.OwnerEntry.OwnerThread) = *(_DWORD *)(a2 + 112);
      RxNameCacheInitializeEx(&DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.ActiveEntries, 8, 128);
      DeviceObject->DeviceObject.Flags &= ~0x80u;
      v22 = *(_QWORD *)(a1 + 80);
      *(_QWORD *)(a1 + 80) = DeviceObject;
      started = RxStartMinirdr((PRX_CONTEXT)a1, (PBOOLEAN)(a1 + 35));
      *(_QWORD *)(a1 + 80) = v22;
      if ( started >= 0 )
        return (unsigned int)started;
      v16 = 7;
    }
    v23 = v16 - 1;
    if ( !v23 )
    {
LABEL_50:
      RxUnregisterMinirdr(DeviceObject);
      return (unsigned int)started;
    }
    v24 = v23 - 1;
    if ( !v24 )
    {
LABEL_48:
      if ( v5 )
        IoUnregisterFileSystem(&DeviceObject->DeviceObject);
      goto LABEL_50;
    }
    v25 = v24 - 1;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 )
          {
            if ( v28 != 1 )
              return (unsigned int)started;
            RxNameCacheFinalize((PNAME_CACHE_CONTROL)&DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.ActiveEntries);
          }
        }
        goto LABEL_45;
      }
LABEL_46:
      UninitialializeSubRdrDialectTable(DeviceObject);
    }
LABEL_47:
    MRxSmbUninitializeTransportArrayInstance(DeviceObject);
    goto LABEL_48;
  }
  DeviceObject = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids, (unsigned int)v13);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x14007f05c  mov     [rsp-38h+arg_18], rbx
0x14007f061  mov     [rsp-38h+RxContext], rcx
0x14007f066  push    rbp
0x14007f067  push    rsi
0x14007f068  push    rdi
0x14007f069  push    r12
0x14007f06b  push    r13
0x14007f06d  push    r14
0x14007f06f  push    r15
0x14007f071  mov     rbp, rsp
0x14007f074  sub     rsp, 50h
0x14007f078  xor     r10d, r10d
0x14007f07b  xorps   xmm0, xmm0
0x14007f07e  mov     [rbp+DeviceObject], r10
0x14007f082  mov     r14, rdx
0x14007f085  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x14007f089  cmp     r8d, 7Ch ; '|'
0x14007f08d  jb      loc_14007F563
0x14007f093  movzx   edx, word ptr [rdx+76h]
0x14007f097  test    dx, dx
0x14007f09a  jz      loc_14007F563
0x14007f0a0  test    dl, 1
0x14007f0a3  jnz     loc_14007F563
0x14007f0a9  mov     eax, edx
0x14007f0ab  cmp     r8d, edx
0x14007f0ae  jb      loc_14007F563
0x14007f0b4  add     eax, 78h ; 'x'
0x14007f0b7  cmp     r8d, eax
0x14007f0ba  jb      loc_14007F563
0x14007f0c0  movzx   ecx, word ptr [r14+0Ch]
0x14007f0c5  lea     r11d, [r10+2]
0x14007f0c9  movzx   r13d, cx
0x14007f0cd  lea     eax, [r11+7Eh]
0x14007f0d1  movzx   r9d, cx
0x14007f0d5  movzx   r15d, cx
0x14007f0d9  movzx   r8d, cx
0x14007f0dd  and     r13w, r11w
0x14007f0e1  setnz   sil
0x14007f0e5  and     ecx, 10h
0x14007f0e8  shl     ecx, 0Ah
0x14007f0eb  and     r15w, 40h
0x14007f0f0  and     r8w, ax
0x14007f0f4  and     r9w, 4
0x14007f0f9  or      ecx, 687h
0x14007f0ff  mov     [rbp+arg_10], r9w
0x14007f104  movzx   eax, r15w
0x14007f108  neg     ax
0x14007f10b  sbb     ebx, ebx
0x14007f10d  and     ebx, 44h
0x14007f110  add     ebx, 600h
0x14007f116  test    r9w, r9w
0x14007f11a  jz      short loc_14007F126
0x14007f11c  bts     ecx, 12h
0x14007f120  add     ebx, 90h
0x14007f126  mov     eax, ecx
0x14007f128  mov     [rbp+var_10.MaximumLength], dx
0x14007f12c  or      eax, 8800h
0x14007f131  mov     [rbp+var_10.Length], dx
0x14007f135  test    r8w, r8w
0x14007f139  cmovz   eax, ecx
0x14007f13c  neg     r8w
0x14007f140  mov     r12d, eax
0x14007f143  sbb     edi, edi
0x14007f145  bts     r12d, 11h
0x14007f14a  and     edi, 0A0000h
0x14007f150  add     edi, 10h
0x14007f153  test    r13w, r13w
0x14007f157  cmovnz  r12d, eax
0x14007f15b  lea     rax, [r14+78h]
0x14007f15f  mov     [rbp+var_10.Buffer], rax
0x14007f163  lea     rax, WPP_GLOBAL_Control
0x14007f16a  cmp     [r14+74h], r10b
0x14007f16e  jnz     short loc_14007F1A3
0x14007f170  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007f177  cmp     rcx, rax
0x14007f17a  jz      short loc_14007F1A3
0x14007f17c  mov     eax, [rcx+2Ch]
0x14007f17f  test    r11b, al
0x14007f182  jz      short loc_14007F1A3
0x14007f184  cmp     [rcx+29h], r11b
0x14007f188  jb      short loc_14007F1A3
0x14007f18a  mov     rcx, [rcx+18h]
0x14007f18e  lea     r9, [rbp+var_10]
0x14007f192  mov     edx, 2Dh ; '-'
0x14007f197  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14007f19e  call    WPP_SF_Z
0x14007f1a3  mov     rdx, [rbp+RxContext]
0x14007f1a7  lea     rax, [rbp+var_10]
0x14007f1ab  mov     [rsp+50h+DeviceCharacteristics], edi; DeviceCharacteristics
0x14007f1af  lea     r8, MRxSmbDispatch; MrdrDispatch
0x14007f1b6  mov     [rsp+50h+DeviceType], 14h; DeviceType
0x14007f1be  lea     rcx, [rbp+DeviceObject]; DeviceObject
0x14007f1c2  mov     [rsp+50h+DeviceExtensionSize], ebx; DeviceExtensionSize
0x14007f1c6  mov     r9d, r12d; Controls
0x14007f1c9  mov     rdx, [rdx+50h]
0x14007f1cd  mov     [rsp+50h+DeviceName], rax; DeviceName
0x14007f1d2  mov     rdx, [rdx+8]; DriverObject
0x14007f1d6  call    cs:__imp_RxRegisterMinirdr
0x14007f1dd  nop     dword ptr [rax+rax+00h]
0x14007f1e2  xor     r12d, r12d
0x14007f1e5  mov     edi, eax
0x14007f1e7  test    eax, eax
0x14007f1e9  jns     short loc_14007F239
0x14007f1eb  mov     [rbp+DeviceObject], r12
0x14007f1ef  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007f1f6  lea     rax, WPP_GLOBAL_Control
0x14007f1fd  cmp     rcx, rax
0x14007f200  jz      loc_14007F568
0x14007f206  mov     edx, [rcx+2Ch]
0x14007f209  test    dl, 1
0x14007f20c  jz      loc_14007F568
0x14007f212  cmp     byte ptr [rcx+29h], 1
0x14007f216  jb      loc_14007F568
0x14007f21c  mov     rcx, [rcx+18h]
0x14007f220  lea     edx, [r12+2Eh]
0x14007f225  mov     r9d, edi
0x14007f228  lea     r8, WPP_c86fdb6c24cc347f0e6836246d5ec6ea_Traceguids
0x14007f22f  call    WPP_SF_d
0x14007f234  jmp     loc_14007F568
0x14007f239  mov     rax, [rbp+DeviceObject]
0x14007f23d  mov     ebx, 1
0x14007f242  mov     dword ptr [rax+930h], 0FFFFFFFFh
0x14007f24c  lea     rdi, [rax+0B20h]
0x14007f253  mov     rax, [rbp+DeviceObject]
0x14007f257  movzx   ecx, word ptr [r14+0Ch]
0x14007f25c  mov     [rax+522h], cx
0x14007f263  test    r13w, r13w
0x14007f267  jz      short loc_14007F27E
0x14007f269  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x14007f26d  call    cs:__imp_IoRegisterFileSystem
0x14007f274  nop     dword ptr [rax+rax+00h]
0x14007f279  mov     ebx, 2
0x14007f27e  mov     rax, [rbp+DeviceObject]
0x14007f282  test    r15w, r15w
0x14007f286  jz      loc_14007F384
0x14007f28c  lea     r8, [rdi+7]
0x14007f290  and     r8, 0FFFFFFFFFFFFFFF8h
0x14007f294  mov     [rax+938h], r8
0x14007f29b  mov     rdx, [rbp+DeviceObject]
0x14007f29f  mov     eax, [r14+14h]
0x14007f2a3  lea     rdi, [r8+3Ch]
0x14007f2a7  mov     rcx, [rdx+938h]
0x14007f2ae  mov     [rcx], eax
0x14007f2b0  mov     rcx, [rdx+938h]
0x14007f2b7  mov     eax, [r14+18h]
0x14007f2bb  mov     [rcx+4], eax
0x14007f2be  mov     rcx, [rdx+938h]
0x14007f2c5  mov     eax, [r14+1Ch]
0x14007f2c9  mov     [rcx+8], eax
0x14007f2cc  mov     rcx, [rdx+938h]
0x14007f2d3  mov     eax, [r14+20h]
0x14007f2d7  mov     [rcx+0Ch], eax
0x14007f2da  mov     rcx, [rdx+938h]
0x14007f2e1  mov     eax, [r14+24h]
0x14007f2e5  mov     [rcx+10h], eax
0x14007f2e8  mov     rcx, [rdx+938h]
0x14007f2ef  mov     eax, [r14+28h]
0x14007f2f3  mov     [rcx+14h], eax
0x14007f2f6  mov     rcx, [rdx+938h]
0x14007f2fd  mov     eax, [r14+2Ch]
0x14007f301  mov     [rcx+18h], eax
0x14007f304  mov     rcx, [rdx+938h]
0x14007f30b  mov     eax, [r14+30h]
0x14007f30f  mov     [rcx+1Ch], eax
0x14007f312  mov     rcx, [rdx+938h]
0x14007f319  mov     eax, [r14+34h]
0x14007f31d  mov     [rcx+20h], eax
0x14007f320  mov     rcx, [rdx+938h]
0x14007f327  mov     eax, [r14+38h]
0x14007f32b  mov     [rcx+24h], eax
0x14007f32e  mov     rcx, [rdx+938h]
0x14007f335  mov     eax, [r14+3Ch]
0x14007f339  mov     [rcx+28h], eax
0x14007f33c  mov     rcx, [rdx+938h]
0x14007f343  mov     eax, [r14+40h]
0x14007f347  mov     [rcx+2Ch], eax
0x14007f34a  mov     rcx, [rdx+938h]
0x14007f351  mov     eax, [r14+44h]
0x14007f355  mov     [rcx+30h], eax
0x14007f358  mov     rcx, [rdx+938h]
0x14007f35f  mov     eax, [r14+48h]
0x14007f363  mov     [rcx+34h], eax
0x14007f366  mov     rcx, [rdx+938h]
0x14007f36d  mov     al, [r14+4Ch]
0x14007f371  mov     [rcx+38h], al
0x14007f374  mov     rcx, [rdx+938h]
0x14007f37b  mov     al, [r14+4Dh]
0x14007f37f  mov     [rcx+39h], al
0x14007f382  jmp     short loc_14007F392
0x14007f384  lea     rcx, dword_14007D104
0x14007f38b  mov     [rax+938h], rcx
0x14007f392  mov     rcx, [rbp+DeviceObject]
0x14007f396  cmp     [rbp+arg_10], r12w
0x14007f39b  jz      short loc_14007F3A7
0x14007f39d  lea     rdx, [rdi+7]
0x14007f3a1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14007f3a5  jmp     short loc_14007F3A9
0x14007f3a7  xor     edx, edx
0x14007f3a9  call    MRxSmbInitializeTransportArrayInstance
0x14007f3ae  mov     edi, eax
0x14007f3b0  test    eax, eax
0x14007f3b2  js      loc_14007F4DE
0x14007f3b8  mov     rcx, [rbp+DeviceObject]
0x14007f3bc  call    InitialializeSubRdrDialectTable
0x14007f3c1  mov     edi, eax
0x14007f3c3  test    eax, eax
0x14007f3c5  js      loc_14007F533
0x14007f3cb  mov     rcx, [rbp+DeviceObject]
0x14007f3cf  call    MRxSmbInitializeConnectionEngine
0x14007f3d4  mov     edi, eax
0x14007f3d6  test    eax, eax
0x14007f3d8  js      loc_14007F52A
0x14007f3de  mov     rcx, [rbp+DeviceObject]
0x14007f3e2  call    MRxSmbInitializeExchangeEngine
0x14007f3e7  mov     edi, eax
0x14007f3e9  test    eax, eax
0x14007f3eb  js      loc_14007F518
0x14007f3f1  mov     rcx, [rbp+DeviceObject]
0x14007f3f5  mov     rdx, r14
0x14007f3f8  call    MRxSmbSubRdrInstanceNotification
0x14007f3fd  mov     rcx, [rbp+DeviceObject]
0x14007f401  xor     edx, edx
0x14007f403  call    StartSubRedirectorForDialect
0x14007f408  mov     edi, eax
0x14007f40a  test    eax, eax
0x14007f40c  js      loc_14007F518
0x14007f412  mov     cl, [r14+74h]
0x14007f416  xor     r9d, r9d
0x14007f419  mov     rax, [rbp+DeviceObject]
0x14007f41d  mov     qword ptr [rsp+50h+DeviceExtensionSize], r12
0x14007f422  mov     [rsp+50h+DeviceName], r12
0x14007f427  lea     edx, [r9+8]
0x14007f42b  mov     [rax+520h], cl
0x14007f431  lea     r8d, [rdx+78h]
0x14007f435  mov     ecx, [r14+4]
0x14007f439  mov     rax, [rbp+DeviceObject]
0x14007f43d  mov     [rax+928h], ecx
0x14007f443  mov     ecx, [r14+8]
0x14007f447  mov     rax, [rbp+DeviceObject]
0x14007f44b  mov     [rax+92Ch], ecx
0x14007f451  mov     cl, [r14+0Ch]
0x14007f455  mov     rax, [rbp+DeviceObject]
0x14007f459  and     cl, 1
0x14007f45c  mov     [rax+521h], cl
0x14007f462  mov     rcx, [rbp+DeviceObject]
0x14007f466  movups  xmm0, xmmword ptr [r14+50h]
0x14007f46b  movups  xmmword ptr [rcx+940h], xmm0
0x14007f472  movups  xmm1, xmmword ptr [r14+60h]
0x14007f477  movups  xmmword ptr [rcx+950h], xmm1
0x14007f47e  mov     eax, [r14+70h]
0x14007f482  mov     [rcx+960h], eax
0x14007f488  mov     rcx, [rbp+DeviceObject]
0x14007f48c  add     rcx, 970h
0x14007f493  call    cs:__imp_RxNameCacheInitializeEx
0x14007f49a  nop     dword ptr [rax+rax+00h]
0x14007f49f  mov     r14, [rbp+RxContext]
0x14007f4a3  mov     rax, [rbp+DeviceObject]
0x14007f4a7  mov     rcx, r14; RxContext
0x14007f4aa  lea     rdx, [r14+23h]; PostToFsp
0x14007f4ae  btr     dword ptr [rax+30h], 7
0x14007f4b3  mov     rax, [rbp+DeviceObject]
0x14007f4b7  mov     rbx, [r14+50h]
0x14007f4bb  mov     [r14+50h], rax
0x14007f4bf  call    cs:__imp_RxStartMinirdr
0x14007f4c6  nop     dword ptr [rax+rax+00h]
0x14007f4cb  mov     edi, eax
0x14007f4cd  mov     [r14+50h], rbx
0x14007f4d1  test    eax, eax
0x14007f4d3  jns     loc_14007F568
0x14007f4d9  mov     ebx, 7
0x14007f4de  sub     ebx, 1
0x14007f4e1  jz      short loc_14007F551
0x14007f4e3  sub     ebx, 1
0x14007f4e6  jz      short loc_14007F53C
0x14007f4e8  sub     ebx, 1
0x14007f4eb  jz      short loc_14007F533
0x14007f4ed  sub     ebx, 1
0x14007f4f0  jz      short loc_14007F52A
0x14007f4f2  sub     ebx, 1
0x14007f4f5  jz      short loc_14007F518
0x14007f4f7  sub     ebx, 1
0x14007f4fa  jz      short loc_14007F518
0x14007f4fc  cmp     ebx, 1
0x14007f4ff  jnz     short loc_14007F568
0x14007f501  mov     rcx, [rbp+DeviceObject]
0x14007f505  add     rcx, 970h; NameCacheCtl
0x14007f50c  call    cs:__imp_RxNameCacheFinalize
0x14007f513  nop     dword ptr [rax+rax+00h]
0x14007f518  mov     rcx, [rbp+DeviceObject]
0x14007f51c  call    MRxSmbStopConnectionEngine
0x14007f521  mov     rcx, [rbp+DeviceObject]
0x14007f525  call    UninitializeSubRdrCertificateMappingsList
0x14007f52a  mov     rcx, [rbp+DeviceObject]
0x14007f52e  call    UninitialializeSubRdrDialectTable
0x14007f533  mov     rcx, [rbp+DeviceObject]
0x14007f537  call    MRxSmbUninitializeTransportArrayInstance
0x14007f53c  test    sil, sil
0x14007f53f  jz      short loc_14007F551
0x14007f541  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x14007f545  call    cs:__imp_IoUnregisterFileSystem
  ... truncated ...
```
