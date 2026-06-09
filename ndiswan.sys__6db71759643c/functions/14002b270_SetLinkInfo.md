# SetLinkInfo

- ea: `0x14002b270`
- end: `0x14002b9fd`
- name: `SetLinkInfo`
- size: `1933`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002cc0`
- `0x1400048c0`
- `0x140005494`
- `0x14000550c`
- `0x140007364`
- `0x1400084d8`
- `0x1400085b0`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a5f4`
- `0x140010640`
- `0x1400161f0`
- `0x140016700`
- `0x14002a8e0`
- `0x14002b270`
- `0x14002e8dc`
- `0x140035960`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002b4bf`
- `ntoskrnl!KeInitializeEvent` at `0x14002b580`
- `ntoskrnl!KeInitializeEvent` at `0x14002b4bf`
- `ntoskrnl!KeInitializeEvent` at `0x14002b580`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b46f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b46f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b5bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b681`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b981`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b9c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b5bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b681`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b981`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b9c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b59b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b65e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b699`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b99c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b59b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b65e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b699`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b99c`

## pseudocode

```c
__int64 __fastcall SetLinkInfo(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  int v7; // r15d
  int v8; // eax
  __int64 v9; // rcx
  char *v10; // rbx
  char *v11; // rdi
  bool v12; // zf
  char v13; // r12
  _DWORD *v14; // r14
  KIRQL v15; // al
  KIRQL v16; // dl
  KSPIN_LOCK *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // ecx
  int v23; // eax
  int v24; // eax
  __int64 (__fastcall *v25)(); // rax
  char *v26; // rdx
  char *i; // rcx
  int v28; // ecx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  KIRQL v34; // al
  PVOID v36; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Entry; // [rsp+38h] [rbp-C8h] BYREF
  struct _KEVENT v38[14]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v39; // [rsp+190h] [rbp+90h] BYREF
  __int128 v40; // [rsp+1A0h] [rbp+A0h]
  __int128 v41; // [rsp+1B0h] [rbp+B0h]

  v36 = 0;
  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  *a5 = 0;
  if ( a2 < 0x38 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a2, 56);
    }
    *a5 = 56;
    return (unsigned int)-1073741820;
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v8 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v8 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
  v9 = *(_QWORD *)a1;
  if ( v8 )
  {
    v7 = ValidateLinkAndBundle(v9, 1, &v36, &Entry);
    if ( v7 < 0 )
      goto LABEL_17;
LABEL_22:
    v11 = (char *)v36;
    v13 = 0;
    v14 = (_DWORD *)*((_QWORD *)v36 + 9);
    if ( v14[30] == 12 && v14[31] == 12 )
    {
      v13 = 1;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_32:
        KeWaitForSingleObject(v14 + 120, Executive, 0, 1u, 0);
        if ( (v14[5] & 1) != 0 )
        {
          memset(v38, 0, 0x108u);
          v38[0].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)1;
          v39 = 0;
          v40 = 0;
          v41 = 0;
          KeInitializeEvent(&v38[10], NotificationEvent, 0);
          *(_QWORD *)&v38[1].Header.Lock = v14;
          *(_QWORD *)&v39 = *((_QWORD *)v11 + 7);
          *((_QWORD *)&v39 + 1) = *(_QWORD *)(a1 + 8);
          *((_QWORD *)&v40 + 1) = *(_QWORD *)(a1 + 24);
          v41 = *(_OWORD *)(a1 + 32);
          *(_QWORD *)&v38[4].Header.Lock = &v39;
          LODWORD(v38[3].Header.WaitListHead.Flink) = 1;
          LODWORD(v38[3].Header.WaitListHead.Blink) = 67174664;
          LODWORD(v38[4].Header.WaitListHead.Flink) = 48;
          NdisWanSubmitNdisRequestLegacy(v14, v38);
        }
        else
        {
          v39 = 0;
          v40 = 0;
          memset(v38, 0, 0x148u);
          v38[0].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)1;
          KeInitializeEvent((PRKEVENT)&v38[12].Header.WaitListHead.Blink, NotificationEvent, 0);
          *(_QWORD *)&v38[1].Header.Lock = v14;
          v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 92);
          v11[744] = v15;
          v16 = v15;
          v17 = (KSPIN_LOCK *)(v11 + 736);
          if ( *((_DWORD *)v11 + 6) == 2 )
          {
            ++*((_DWORD *)v11 + 8);
            KeReleaseSpinLock(v17, v15);
            *(_QWORD *)&v39 = *(_QWORD *)(a1 + 8);
            *((_QWORD *)&v39 + 1) = *(_QWORD *)(a1 + 24);
            v40 = *(_OWORD *)(a1 + 32);
            v38[3].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)&v39;
            v38[2].Header.LockNV = 15466902;
            v38[2].Header.SignalState = 1;
            LODWORD(v38[3].Header.WaitListHead.Flink) = 67174785;
            v38[4].Header.LockNV = 32;
            v38[1].Header.WaitListHead.Flink = 0;
            v38[1].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)*((_QWORD *)v11 + 7);
            NdisWanSubmitNdisRequest(v14, v38);
            v11[744] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 92);
            DerefVc(v11);
            v16 = v11[744];
            v17 = (KSPIN_LOCK *)(v11 + 736);
          }
          KeReleaseSpinLock(v17, v16);
        }
        v10 = (char *)Entry;
        v10[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 221);
        v20 = *(_DWORD *)(a1 + 24);
        if ( v13 )
        {
          *((_DWORD *)v11 + 72) |= v20;
          *((_DWORD *)v11 + 73) |= *(_DWORD *)(a1 + 28);
          v18 = *((unsigned int *)v11 + 73);
          v19 = *((unsigned int *)v11 + 72);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, v19, v18);
          }
        }
        else
        {
          *((_DWORD *)v11 + 72) = v20;
          *((_DWORD *)v11 + 73) = *(_DWORD *)(a1 + 28);
        }
        v21 = *(_DWORD *)(a1 + 8);
        *((_DWORD *)v11 + 68) = v21;
        *((_DWORD *)v11 + 38) = v21;
        v22 = v14[42];
        if ( v22 < v21 )
          *((_DWORD *)v11 + 38) = v22;
        v23 = *(_DWORD *)(a1 + 12);
        *((_DWORD *)v11 + 69) = v23;
        *((_DWORD *)v11 + 46) = v23;
        *((_DWORD *)v11 + 74) = *(_DWORD *)(a1 + 32);
        *((_DWORD *)v11 + 75) = *(_DWORD *)(a1 + 36);
        *((_DWORD *)v11 + 76) = *(_DWORD *)(a1 + 40);
        *((_DWORD *)v11 + 77) = *(_DWORD *)(a1 + 44);
        *((_DWORD *)v11 + 79) = *(_DWORD *)(a1 + 52);
        *((_DWORD *)v11 + 78) = *(_DWORD *)(a1 + 48);
        v24 = *((_DWORD *)v11 + 73);
        if ( (v24 & 0x100) != 0 )
        {
          v25 = ReceivePPP;
        }
        else if ( (v24 & 0x1000) != 0 )
        {
          v25 = ReceiveSLIP;
        }
        else if ( (v24 & 0x10000000) != 0 )
        {
          v25 = ReceivePassThrough;
        }
        else
        {
          v25 = DetectFraming;
          if ( v13 )
            v25 = DetectBroadbandFraming;
        }
        *((_QWORD *)v11 + 15) = v25;
        if ( _bittest((const signed __int32 *)v11 + 72, 0x1Cu) )
        {
          if ( (*((_DWORD *)v10 + 4) & 0x80000) == 0 )
          {
            v19 = (unsigned int)v14[31];
            if ( (((_DWORD)v19 - 8) & 0xFFFFFFFA) == 0 && (_DWORD)v19 != 12 )
            {
              if ( v10[1784] )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, v19);
                }
                *((_DWORD *)v10 + 4) |= 0x80000u;
              }
            }
          }
        }
        v26 = v10 + 48;
        *(_QWORD *)(v10 + 68) = 0;
        for ( i = (char *)*((_QWORD *)v10 + 6); i != v26; i = *(char **)i )
        {
          *((_DWORD *)v10 + 17) |= *((_DWORD *)i + 72);
          *((_DWORD *)v10 + 18) |= *((_DWORD *)i + 73);
        }
        v28 = glMRRU;
        *((_DWORD *)v10 + 19) = *((_DWORD *)v11 + 78);
        if ( *((_DWORD *)v11 + 79) )
          v28 = *((_DWORD *)v11 + 79);
        *((_DWORD *)v10 + 20) = v28;
        if ( ((*((_DWORD *)v10 + 17) | *((_DWORD *)v10 + 18)) & 0x6000) != 0 )
        {
          LOBYTE(v26) = 16;
          v7 = sl_compress_init(v10 + 400, v26, v18, v19);
          if ( v7 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
            }
          }
        }
        v29 = *((_DWORD *)v10 + 17);
        if ( (v29 & 0x10) != 0 )
        {
          if ( (v29 & 0x20) != 0 )
          {
            *((_DWORD *)v10 + 24) = 4095;
            *((_DWORD *)v10 + 25) = 2048;
          }
          else
          {
            *((_DWORD *)v10 + 24) = 0xFFFFFF;
            *((_DWORD *)v10 + 25) = 0x800000;
          }
        }
        v30 = *((_DWORD *)v10 + 18);
        if ( (v30 & 0x10) != 0 )
        {
          if ( (v30 & 0x20) != 0 )
          {
            *((_DWORD *)v10 + 62) = 4095;
            *((_DWORD *)v10 + 63) = 2048;
          }
          else
          {
            *((_DWORD *)v10 + 62) = 0xFFFFFF;
            *((_DWORD *)v10 + 63) = 0x800000;
          }
        }
        SetBundleFlags(v10, 0x800000, 4095, 2048);
        UpdateBundleInfo(v32, v31, v33);
        goto LABEL_18;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        66,
        WPP_5659416b879e33cc7e241cd80588418e_Traceguids,
        *(unsigned int *)(a1 + 24),
        *(_DWORD *)(a1 + 28));
    }
    goto LABEL_32;
  }
  v7 = 0;
  if ( (unsigned __int8)AreLinkAndBundleValid(v9, 1, &v36, &Entry) )
    goto LABEL_22;
  v7 = 601;
LABEL_17:
  v10 = (char *)Entry;
  v11 = (char *)v36;
LABEL_18:
  if ( v10 )
  {
    v12 = (*((_DWORD *)v10 + 6))-- == 1;
    if ( v12 )
      DoDerefBundleCBWork(v10);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v10 + 221, v10[1776]);
  }
  if ( v11 )
  {
    v34 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 92);
    v11[744] = v34;
    v12 = (*((_DWORD *)v11 + 7))-- == 1;
    if ( v12 )
      DoDerefLinkCBWork(v11);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v11 + 92, v34);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002b270  mov     [rsp-8+arg_10], rbx
0x14002b275  mov     [rsp-8+arg_18], rsi
0x14002b27a  push    rbp
0x14002b27b  push    rdi
0x14002b27c  push    r12
0x14002b27e  push    r14
0x14002b280  push    r15
0x14002b282  lea     rbp, [rsp-0D0h]
0x14002b28a  sub     rsp, 1D0h
0x14002b291  mov     rax, cs:__security_cookie
0x14002b298  xor     rax, rsp
0x14002b29b  mov     [rbp+0F0h+var_30], rax
0x14002b2a2  mov     rbx, [rbp+0F0h+arg_20]
0x14002b2a9  mov     edi, edx
0x14002b2ab  mov     rsi, rcx
0x14002b2ae  mov     [rsp+1F0h+var_1C0], 0
0x14002b2b7  mov     [rsp+1F0h+Entry], 0
0x14002b2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b2c7  lea     rax, WPP_GLOBAL_Control
0x14002b2ce  cmp     rcx, rax
0x14002b2d1  jz      short loc_14002B2FC
0x14002b2d3  mov     eax, [rcx+2Ch]
0x14002b2d6  test    al, 20h
0x14002b2d8  jz      short loc_14002B2F5
0x14002b2da  cmp     byte ptr [rcx+29h], 5
0x14002b2de  jb      short loc_14002B2F5
0x14002b2e0  mov     rcx, [rcx+18h]
0x14002b2e4  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002b2eb  mov     edx, 3Fh ; '?'
0x14002b2f0  call    WPP_SF_
0x14002b2f5  lea     rax, WPP_GLOBAL_Control
0x14002b2fc  mov     r14d, 38h ; '8'
0x14002b302  mov     dword ptr [rbx], 0
0x14002b308  cmp     edi, r14d
0x14002b30b  jnb     short loc_14002B350
0x14002b30d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b314  cmp     rcx, rax
0x14002b317  jz      short loc_14002B342
0x14002b319  mov     eax, [rcx+2Ch]
0x14002b31c  test    al, 20h
0x14002b31e  jz      short loc_14002B342
0x14002b320  cmp     byte ptr [rcx+29h], 3
0x14002b324  jb      short loc_14002B342
0x14002b326  mov     rcx, [rcx+18h]
0x14002b32a  lea     edx, [r14+8]
0x14002b32e  mov     r9d, edi
0x14002b331  mov     dword ptr [rsp+1F0h+Timeout], r14d
0x14002b336  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002b33d  call    WPP_SF_dd
0x14002b342  mov     [rbx], r14d
0x14002b345  mov     r15d, 0C0000004h
0x14002b34b  jmp     loc_14002B9CE
0x14002b350  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x14002b356  mov     ebx, 1
0x14002b35b  test    al, 10h
0x14002b35d  jz      short loc_14002B363
0x14002b35f  and     eax, ebx
0x14002b361  jmp     short loc_14002B368
0x14002b363  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x14002b368  mov     rcx, [rsi]
0x14002b36b  lea     r9, [rsp+1F0h+Entry]
0x14002b370  lea     r8, [rsp+1F0h+var_1C0]
0x14002b375  mov     dl, bl
0x14002b377  test    eax, eax
0x14002b379  jnz     short loc_14002B3B9
0x14002b37b  xor     r15d, r15d
0x14002b37e  call    AreLinkAndBundleValid
0x14002b383  test    al, al
0x14002b385  jnz     short loc_14002B3C5
0x14002b387  mov     r15d, 259h
0x14002b38d  mov     rbx, [rsp+1F0h+Entry]
0x14002b392  mov     rdi, [rsp+1F0h+var_1C0]
0x14002b397  or      esi, 0FFFFFFFFh
0x14002b39a  test    rbx, rbx
0x14002b39d  jz      loc_14002B98D
0x14002b3a3  add     [rbx+18h], esi
0x14002b3a6  jnz     loc_14002B974
0x14002b3ac  mov     rcx, rbx; Entry
0x14002b3af  call    DoDerefBundleCBWork
0x14002b3b4  jmp     loc_14002B98D
0x14002b3b9  call    ValidateLinkAndBundle
0x14002b3be  mov     r15d, eax
0x14002b3c1  test    eax, eax
0x14002b3c3  js      short loc_14002B38D
0x14002b3c5  mov     rdi, [rsp+1F0h+var_1C0]
0x14002b3ca  xor     r12b, r12b
0x14002b3cd  mov     r14, [rdi+48h]
0x14002b3d1  cmp     dword ptr [r14+78h], 0Ch
0x14002b3d6  jnz     short loc_14002B417
0x14002b3d8  cmp     dword ptr [r14+7Ch], 0Ch
0x14002b3dd  jnz     short loc_14002B417
0x14002b3df  mov     r12b, bl
0x14002b3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b3e9  lea     rax, WPP_GLOBAL_Control
0x14002b3f0  cmp     rcx, rax
0x14002b3f3  jz      short loc_14002B457
0x14002b3f5  mov     eax, [rcx+2Ch]
0x14002b3f8  test    al, 20h
0x14002b3fa  jz      short loc_14002B417
0x14002b3fc  cmp     byte ptr [rcx+29h], 5
0x14002b400  jb      short loc_14002B417
0x14002b402  mov     rcx, [rcx+18h]
0x14002b406  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002b40d  mov     edx, 41h ; 'A'
0x14002b412  call    WPP_SF_
0x14002b417  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b41e  lea     rax, WPP_GLOBAL_Control
0x14002b425  cmp     rcx, rax
0x14002b428  jz      short loc_14002B457
0x14002b42a  mov     eax, [rcx+2Ch]
0x14002b42d  test    al, 20h
0x14002b42f  jz      short loc_14002B457
0x14002b431  cmp     byte ptr [rcx+29h], 5
0x14002b435  jb      short loc_14002B457
0x14002b437  mov     eax, [rsi+1Ch]
0x14002b43a  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002b441  mov     r9d, [rsi+18h]
0x14002b445  mov     edx, 42h ; 'B'
0x14002b44a  mov     rcx, [rcx+18h]
0x14002b44e  mov     dword ptr [rsp+1F0h+Timeout], eax
0x14002b452  call    WPP_SF_dd
0x14002b457  lea     rcx, [r14+1E0h]; Object
0x14002b45e  mov     [rsp+1F0h+Timeout], 0; Timeout
0x14002b467  mov     r9b, bl; Alertable
0x14002b46a  xor     r8d, r8d; WaitMode
0x14002b46d  xor     edx, edx; WaitReason
0x14002b46f  call    cs:__imp_KeWaitForSingleObject
0x14002b476  nop     dword ptr [rax+rax+00h]
0x14002b47b  mov     eax, [r14+14h]
0x14002b47f  xor     edx, edx; Val
0x14002b481  test    bl, al
0x14002b483  jz      loc_14002B551
0x14002b489  mov     r8d, 108h; Size
0x14002b48f  lea     rcx, [rsp+1F0h+var_1B0]; void *
0x14002b494  call    memset
0x14002b499  xorps   xmm0, xmm0
0x14002b49c  mov     [rsp+1F0h+var_1A0], rbx
0x14002b4a1  xor     r8d, r8d; State
0x14002b4a4  lea     rcx, [rbp+0F0h+Event]; Event
0x14002b4a8  xor     edx, edx; Type
0x14002b4aa  movups  [rbp+0F0h+var_60], xmm0
0x14002b4b1  movups  [rbp+0F0h+var_50], xmm0
0x14002b4b8  movups  [rbp+0F0h+var_40], xmm0
0x14002b4bf  call    cs:__imp_KeInitializeEvent
0x14002b4c6  nop     dword ptr [rax+rax+00h]
0x14002b4cb  mov     [rsp+1F0h+var_198], r14
0x14002b4d0  lea     rdx, [rsp+1F0h+var_1B0]
0x14002b4d5  mov     rax, [rdi+38h]
0x14002b4d9  mov     rcx, r14
0x14002b4dc  mov     qword ptr [rbp+0F0h+var_60], rax
0x14002b4e3  mov     eax, [rsi+8]
0x14002b4e6  mov     dword ptr [rbp+0F0h+var_60+8], eax
0x14002b4ec  mov     eax, [rsi+0Ch]
0x14002b4ef  mov     dword ptr [rbp+0F0h+var_60+0Ch], eax
0x14002b4f5  mov     eax, [rsi+18h]
0x14002b4f8  mov     dword ptr [rbp+0F0h+var_50+8], eax
0x14002b4fe  mov     eax, [rsi+1Ch]
0x14002b501  mov     dword ptr [rbp+0F0h+var_50+0Ch], eax
0x14002b507  mov     eax, [rsi+20h]
0x14002b50a  mov     dword ptr [rbp+0F0h+var_40], eax
0x14002b510  mov     eax, [rsi+24h]
0x14002b513  mov     dword ptr [rbp+0F0h+var_40+4], eax
0x14002b519  mov     eax, [rsi+28h]
0x14002b51c  mov     dword ptr [rbp+0F0h+var_40+8], eax
0x14002b522  mov     eax, [rsi+2Ch]
0x14002b525  mov     dword ptr [rbp+0F0h+var_40+0Ch], eax
0x14002b52b  lea     rax, [rbp+0F0h+var_60]
0x14002b532  mov     [rbp+0F0h+var_150], rax
0x14002b536  mov     [rbp+0F0h+var_160], ebx
0x14002b539  mov     dword ptr [rbp+0F0h+var_158], 4010108h
0x14002b540  mov     [rbp+0F0h+var_148], 30h ; '0'
0x14002b547  call    NdisWanSubmitNdisRequestLegacy
0x14002b54c  jmp     loc_14002B68D
0x14002b551  xorps   xmm0, xmm0
0x14002b554  lea     rcx, [rsp+1F0h+var_1B0]; void *
0x14002b559  mov     r8d, 148h; Size
0x14002b55f  movups  [rbp+0F0h+var_60], xmm0
0x14002b566  movups  [rbp+0F0h+var_50], xmm0
0x14002b56d  call    memset
0x14002b572  xor     r8d, r8d; State
0x14002b575  mov     [rsp+1F0h+var_1A0], rbx
0x14002b57a  xor     edx, edx; Type
0x14002b57c  lea     rcx, [rbp+0F0h+var_80]; Event
0x14002b580  call    cs:__imp_KeInitializeEvent
0x14002b587  nop     dword ptr [rax+rax+00h]
0x14002b58c  lea     rbx, [rdi+2E0h]
0x14002b593  mov     [rsp+1F0h+var_198], r14
0x14002b598  mov     rcx, rbx; SpinLock
0x14002b59b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002b5a2  nop     dword ptr [rax+rax+00h]
0x14002b5a7  mov     [rdi+2E8h], al
0x14002b5ad  mov     dl, al; NewIrql
0x14002b5af  cmp     dword ptr [rdi+18h], 2
0x14002b5b3  mov     rcx, rbx; SpinLock
0x14002b5b6  jnz     loc_14002B681
0x14002b5bc  inc     dword ptr [rdi+20h]
0x14002b5bf  call    cs:__imp_KeReleaseSpinLock
0x14002b5c6  nop     dword ptr [rax+rax+00h]
0x14002b5cb  mov     eax, [rsi+8]
0x14002b5ce  lea     rdx, [rsp+1F0h+var_1B0]
0x14002b5d3  mov     dword ptr [rbp+0F0h+var_60], eax
0x14002b5d9  mov     rcx, r14
0x14002b5dc  mov     eax, [rsi+0Ch]
0x14002b5df  mov     dword ptr [rbp+0F0h+var_60+4], eax
0x14002b5e5  mov     eax, [rsi+18h]
0x14002b5e8  mov     dword ptr [rbp+0F0h+var_60+8], eax
0x14002b5ee  mov     eax, [rsi+1Ch]
0x14002b5f1  mov     dword ptr [rbp+0F0h+var_60+0Ch], eax
0x14002b5f7  mov     eax, [rsi+20h]
0x14002b5fa  mov     dword ptr [rbp+0F0h+var_50], eax
0x14002b600  mov     eax, [rsi+24h]
0x14002b603  mov     dword ptr [rbp+0F0h+var_50+4], eax
0x14002b609  mov     eax, [rsi+28h]
0x14002b60c  mov     dword ptr [rbp+0F0h+var_50+8], eax
0x14002b612  mov     eax, [rsi+2Ch]
0x14002b615  mov     dword ptr [rbp+0F0h+var_50+0Ch], eax
0x14002b61b  lea     rax, [rbp+0F0h+var_60]
0x14002b622  mov     [rbp+0F0h+var_158], rax
0x14002b626  mov     [rsp+1F0h+var_180], 0EC0196h
0x14002b62e  mov     [rsp+1F0h+var_17C], 1
0x14002b636  mov     [rbp+0F0h+var_160], 4010181h
0x14002b63d  mov     dword ptr [rbp+0F0h+var_150], 20h ; ' '
0x14002b644  mov     [rsp+1F0h+var_190], 0
0x14002b64d  mov     rax, [rdi+38h]
0x14002b651  mov     [rsp+1F0h+var_188], rax
0x14002b656  call    NdisWanSubmitNdisRequest
0x14002b65b  mov     rcx, rbx; SpinLock
0x14002b65e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002b665  nop     dword ptr [rax+rax+00h]
0x14002b66a  mov     rcx, rdi
0x14002b66d  mov     [rdi+2E8h], al
0x14002b673  call    DerefVc
0x14002b678  mov     dl, [rdi+2E8h]; NewIrql
0x14002b67e  mov     rcx, rbx; SpinLock
0x14002b681  call    cs:__imp_KeReleaseSpinLock
0x14002b688  nop     dword ptr [rax+rax+00h]
0x14002b68d  mov     rbx, [rsp+1F0h+Entry]
0x14002b692  lea     rcx, [rbx+6E8h]; SpinLock
0x14002b699  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002b6a0  nop     dword ptr [rax+rax+00h]
0x14002b6a5  mov     [rbx+6F0h], al
0x14002b6ab  mov     eax, [rsi+18h]
0x14002b6ae  test    r12b, r12b
0x14002b6b1  jz      short loc_14002B70C
0x14002b6b3  or      [rdi+120h], eax
0x14002b6b9  mov     eax, [rsi+1Ch]
0x14002b6bc  or      [rdi+124h], eax
0x14002b6c2  mov     r8d, [rdi+124h]
0x14002b6c9  mov     r9d, [rdi+120h]
0x14002b6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b6d7  lea     rdx, WPP_GLOBAL_Control
0x14002b6de  cmp     rcx, rdx
0x14002b6e1  jz      short loc_14002B722
0x14002b6e3  mov     eax, [rcx+2Ch]
0x14002b6e6  test    al, 20h
0x14002b6e8  jz      short loc_14002B722
0x14002b6ea  cmp     byte ptr [rcx+29h], 5
0x14002b6ee  jb      short loc_14002B722
0x14002b6f0  mov     rcx, [rcx+18h]
0x14002b6f4  mov     edx, 43h ; 'C'
0x14002b6f9  mov     dword ptr [rsp+1F0h+Timeout], r8d
0x14002b6fe  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002b705  call    WPP_SF_dd
0x14002b70a  jmp     short loc_14002B71B
0x14002b70c  mov     [rdi+120h], eax
0x14002b712  mov     eax, [rsi+1Ch]
0x14002b715  mov     [rdi+124h], eax
0x14002b71b  lea     rdx, WPP_GLOBAL_Control
0x14002b722  mov     eax, [rsi+8]
0x14002b725  mov     [rdi+110h], eax
0x14002b72b  mov     [rdi+98h], eax
0x14002b731  mov     ecx, [r14+0A8h]
0x14002b738  cmp     ecx, eax
0x14002b73a  jnb     short loc_14002B742
0x14002b73c  mov     [rdi+98h], ecx
0x14002b742  mov     eax, [rsi+0Ch]
0x14002b745  mov     [rdi+114h], eax
0x14002b74b  mov     [rdi+0B8h], eax
0x14002b751  mov     eax, [rsi+20h]
0x14002b754  mov     [rdi+128h], eax
0x14002b75a  mov     eax, [rsi+24h]
0x14002b75d  mov     [rdi+12Ch], eax
0x14002b763  mov     eax, [rsi+28h]
0x14002b766  mov     [rdi+130h], eax
0x14002b76c  mov     eax, [rsi+2Ch]
0x14002b76f  mov     [rdi+134h], eax
0x14002b775  mov     eax, [rsi+34h]
0x14002b778  mov     [rdi+13Ch], eax
0x14002b77e  mov     eax, [rsi+30h]
0x14002b781  mov     [rdi+138h], eax
0x14002b787  mov     eax, [rdi+124h]
0x14002b78d  bt      eax, 8
0x14002b791  jnb     short loc_14002B79C
0x14002b793  lea     rax, ReceivePPP
0x14002b79a  jmp     short loc_14002B7CF
0x14002b79c  bt      eax, 0Ch
0x14002b7a0  jnb     short loc_14002B7AB
0x14002b7a2  lea     rax, ReceiveSLIP
0x14002b7a9  jmp     short loc_14002B7CF
0x14002b7ab  bt      eax, 1Ch
  ... truncated ...
```
