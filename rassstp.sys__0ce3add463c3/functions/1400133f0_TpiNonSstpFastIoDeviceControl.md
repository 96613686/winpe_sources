# TpiNonSstpFastIoDeviceControl

- ea: `0x1400133f0`
- end: `0x140013abf`
- name: `TpiNonSstpFastIoDeviceControl`
- size: `1743`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140012290`

## callees

- `0x140002030`
- `0x140002aa0`
- `0x140002bd8`
- `0x140002c08`
- `0x140002f88`
- `0x140002fc4`
- `0x140003090`
- `0x140005e10`
- `0x140012de0`
- `0x140012f40`
- `0x140013008`
- `0x140013150`
- `0x1400133f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400136f1`
- `ntoskrnl!ExAllocatePool2` at `0x1400136f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a5b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400135d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001387c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013969`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400135d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001387c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013969`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140013524`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14001374f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140013524`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14001374f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400135f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001360d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400138ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400139a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400135f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001360d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400138ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400139a7`
- `fwpkclnt!DPChannelCreate0` at `0x140013900`
- `fwpkclnt!DPChannelCreate0` at `0x140013900`

## pseudocode

```c
void __fastcall TpiNonSstpFastIoDeviceControl(void *Src, int a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // r9d
  int v6; // r8d
  __int64 ContextFromCorrelationGuid; // rsi
  int *v9; // rdi
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  int *p_Source1; // r9
  KIRQL v13; // al
  int v14; // edx
  KSPIN_LOCK *v15; // rcx
  __int64 v16; // rdx
  int *Pool2; // rax
  int v18; // r13d
  KIRQL v19; // cl
  int v20; // eax
  int v21; // r8d
  KIRQL v22; // [rsp+30h] [rbp-78h]
  int v24; // [rsp+34h] [rbp-74h]
  NDIS_HANDLE NdisVcHandlea; // [rsp+38h] [rbp-70h]
  _QWORD v27[3]; // [rsp+40h] [rbp-68h] BYREF
  __int128 Source1; // [rsp+58h] [rbp-50h] BYREF
  int v29; // [rsp+68h] [rbp-40h]
  int v30; // [rsp+6Ch] [rbp-3Ch]
  char *v31; // [rsp+70h] [rbp-38h]

  v5 = a3;
  v6 = a2;
  v27[1] = a4;
  ContextFromCorrelationGuid = 0;
  v27[2] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    v6 = a2;
    v5 = a3;
  }
  v9 = 0;
  if ( v5 == 1212440 )
  {
    if ( v6 == 4144 )
    {
      Pool2 = (int *)ExAllocatePool2(64, 4144, 1836073811);
      v9 = Pool2;
      if ( Pool2 )
      {
        if ( ((unsigned __int8)Src & 7) != 0 )
          ExRaiseDatatypeMisalignment();
        RtlCopyFromUser(Pool2, Src, 0x1030u);
        if ( (unsigned int)v9[10] <= 0x1000 )
        {
          ContextFromCorrelationGuid = GetContextFromCorrelationGuid(v9);
          if ( !ContextFromCorrelationGuid )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
              || !BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              goto LABEL_58;
            }
            v11 = 104;
            p_Source1 = v9;
            goto LABEL_57;
          }
          *(_DWORD *)a4 = 0;
          *(_QWORD *)(a4 + 8) = 0;
          NdisVcHandlea = 0;
          v18 = 0;
          v27[0] = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF__guid_D(
              WPP_GLOBAL_Control->AttachedDevice,
              105,
              WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
              v9,
              v9[4]);
          }
          if ( !v9[4] )
          {
            v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(ContextFromCorrelationGuid + 32));
            v22 = v19;
            NdisVcHandlea = *(NDIS_HANDLE *)(ContextFromCorrelationGuid + 40);
            if ( *(_BYTE *)(ContextFromCorrelationGuid + 507) )
            {
              v20 = 1;
              v24 = 1;
            }
            else
            {
              v30 = 0;
              v24 = 0;
              *((_QWORD *)&Source1 + 1) = DPSendCompleteCallback;
              *(_QWORD *)&Source1 = DPReceiveCallback;
              v29 = v9[10];
              v31 = (char *)(v9 + 11);
              KeReleaseSpinLock((PKSPIN_LOCK)(ContextFromCorrelationGuid + 32), v19);
              v9[4] = DPChannelCreate0(&Source1, v27);
              v20 = 0;
              v19 = v22;
            }
            v21 = v9[4];
            if ( v21 >= 0 )
            {
              if ( !v20 )
              {
                v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(ContextFromCorrelationGuid + 32));
                *(_QWORD *)(ContextFromCorrelationGuid + 21136) = v27[0];
              }
              *(_DWORD *)(ContextFromCorrelationGuid + 21128) = v9[5];
              *(_QWORD *)(ContextFromCorrelationGuid + 21104) = *((_QWORD *)v9 + 3);
              *(_QWORD *)(ContextFromCorrelationGuid + 21112) = *((_QWORD *)v9 + 4);
              KeReleaseSpinLock((PKSPIN_LOCK)(ContextFromCorrelationGuid + 32), v19);
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF__guid_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  106,
                  WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
                  v9,
                  v21);
              }
              *(_DWORD *)a4 = v9[4];
            }
            v18 = v24;
          }
          if ( v18 )
          {
            TpiFsmIndicateLinkParamChange(NdisVcHandlea);
          }
          else
          {
            TpiFsmNewCallComplete(ContextFromCorrelationGuid, v9[4]);
            if ( !v9[4] )
              TpiFsmCryptoBindingComplete(ContextFromCorrelationGuid);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
          }
          *(_DWORD *)a4 = -1073741811;
          *(_QWORD *)(a4 + 8) = 4096;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
        }
        *(_DWORD *)a4 = -1073741801;
        *(_QWORD *)(a4 + 8) = 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
      }
      *(_DWORD *)a4 = -1073741811;
      *(_QWORD *)(a4 + 8) = 4144;
    }
  }
  else
  {
    if ( v5 != 1212480 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
        v5 = a3;
      }
      *(_DWORD *)a4 = -1073741637;
      *(_QWORD *)(a4 + 8) = v5;
      goto LABEL_81;
    }
    if ( v6 != 16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
      }
      *(_DWORD *)a4 = -1073741811;
      *(_QWORD *)(a4 + 8) = 16;
      goto LABEL_81;
    }
    Source1 = 0;
    if ( ((unsigned __int8)Src & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&Source1, Src, 0x10u);
    ContextFromCorrelationGuid = GetContextFromCorrelationGuid(&Source1);
    if ( !ContextFromCorrelationGuid )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_58;
      }
      v11 = 109;
      p_Source1 = (int *)&Source1;
LABEL_57:
      WPP_SF__guid_(v10->AttachedDevice, v11, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, p_Source1);
LABEL_58:
      *(_DWORD *)a4 = -1073741816;
      *(_QWORD *)(a4 + 8) = 0;
      goto LABEL_81;
    }
    *(_DWORD *)a4 = 0;
    *(_QWORD *)(a4 + 8) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, &Source1);
    }
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(ContextFromCorrelationGuid + 32));
    v14 = *(_DWORD *)(ContextFromCorrelationGuid + 21088);
    v15 = (KSPIN_LOCK *)(ContextFromCorrelationGuid + 32);
    if ( (v14 & 0x200) != 0 )
    {
      KeReleaseSpinLock(v15, v13);
      LOBYTE(v16) = 0;
    }
    else
    {
      *(_DWORD *)(ContextFromCorrelationGuid + 21088) = v14 & 0xFFFFFFFB;
      KeReleaseSpinLock(v15, v13);
      v16 = 1;
    }
    TpiFsmDisconnectComplete(ContextFromCorrelationGuid, v16, 0);
  }
LABEL_81:
  if ( v9 )
    ExFreePoolWithTag(v9, 0x6D704353u);
  if ( ContextFromCorrelationGuid )
    DereferenceRefCount(ContextFromCorrelationGuid);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 112, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
}

```

## disassembly

```asm
0x1400133f0  push    rsi
0x1400133f2  push    rdi
0x1400133f3  push    r12
0x1400133f5  push    r13
0x1400133f7  push    r14
0x1400133f9  sub     rsp, 80h
0x140013400  mov     rax, cs:__security_cookie
0x140013407  xor     rax, rsp
0x14001340a  mov     [rsp+0A8h+var_30], rax
0x14001340f  mov     r14, r9
0x140013412  mov     r9d, r8d
0x140013415  mov     [rsp+0A8h+var_74], r8d
0x14001341a  mov     r8d, edx
0x14001341d  mov     dword ptr [rsp+0A8h+NdisVcHandle], edx
0x140013421  mov     r13, rcx
0x140013424  mov     [rsp+0A8h+var_60], r14
0x140013429  xor     esi, esi
0x14001342b  mov     [rsp+0A8h+var_58], rsi
0x140013430  lea     r12, WPP_GLOBAL_Control
0x140013437  mov     rcx, cs:WPP_GLOBAL_Control
0x14001343e  cmp     rcx, r12
0x140013441  jz      short loc_14001346C
0x140013443  mov     eax, [rcx+2Ch]
0x140013446  and     eax, 81h
0x14001344b  cmp     al, 81h
0x14001344d  jnz     short loc_14001346C
0x14001344f  lea     edx, [rsi+63h]
0x140013452  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140013459  mov     rcx, [rcx+18h]
0x14001345d  call    WPP_SF_
0x140013462  mov     r8d, dword ptr [rsp+0A8h+NdisVcHandle]
0x140013467  mov     r9d, [rsp+0A8h+var_74]
0x14001346c  xor     edi, edi
0x14001346e  mov     eax, r9d
0x140013471  sub     eax, 128018h
0x140013476  jz      loc_140013690
0x14001347c  cmp     eax, 28h ; '('
0x14001347f  jz      short loc_1400134C7
0x140013481  mov     rcx, cs:WPP_GLOBAL_Control
0x140013488  cmp     rcx, r12
0x14001348b  jz      short loc_1400134B4
0x14001348d  mov     eax, [rcx+2Ch]
0x140013490  test    al, 2
0x140013492  jz      short loc_1400134B4
0x140013494  lea     edx, [rdi+1]
0x140013497  cmp     [rcx+29h], dl
0x14001349a  jb      short loc_1400134B4
0x14001349c  lea     edx, [rdi+6Fh]
0x14001349f  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400134a6  mov     rcx, [rcx+18h]
0x1400134aa  call    WPP_SF_d
0x1400134af  mov     r9d, [rsp+0A8h+var_74]
0x1400134b4  mov     dword ptr [r14], 0C00000BBh
0x1400134bb  mov     eax, r9d
0x1400134be  mov     [r14+8], rax
0x1400134c2  jmp     loc_140013A4E
0x1400134c7  cmp     r8d, 10h
0x1400134cb  jz      short loc_140013516
0x1400134cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134d4  cmp     rcx, r12
0x1400134d7  jz      short loc_140013502
0x1400134d9  mov     eax, [rcx+2Ch]
0x1400134dc  test    al, 2
0x1400134de  jz      short loc_140013502
0x1400134e0  mov     edx, 1
0x1400134e5  cmp     [rcx+29h], dl
0x1400134e8  jb      short loc_140013502
0x1400134ea  mov     edx, 6Bh ; 'k'
0x1400134ef  mov     r9d, r8d
0x1400134f2  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400134f9  mov     rcx, [rcx+18h]
0x1400134fd  call    WPP_SF_d
0x140013502  mov     dword ptr [r14], 0C000000Dh
0x140013509  mov     qword ptr [r14+8], 10h
0x140013511  jmp     loc_140013A4E
0x140013516  xorps   xmm0, xmm0
0x140013519  movups  [rsp+0A8h+Source1], xmm0
0x14001351e  test    r13b, 3
0x140013522  jz      short loc_140013531
0x140013524  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14001352b  nop     dword ptr [rax+rax+00h]
0x140013530  int     3; Trap to Debugger
0x140013531  mov     r8d, 10h; Size
0x140013537  mov     rdx, r13; Src
0x14001353a  lea     rcx, [rsp+0A8h+Source1]; void *
0x14001353f  call    RtlCopyFromUser
0x140013544  nop
0x140013545  lea     rcx, [rsp+0A8h+Source1]; Source1
0x14001354a  call    GetContextFromCorrelationGuid
0x14001354f  mov     rsi, rax
0x140013552  test    rax, rax
0x140013555  jnz     short loc_14001358C
0x140013557  mov     rcx, cs:WPP_GLOBAL_Control
0x14001355e  cmp     rcx, r12
0x140013561  jz      loc_140013800
0x140013567  mov     edx, [rcx+2Ch]
0x14001356a  test    dl, 2
0x14001356d  jz      loc_140013800
0x140013573  lea     edx, [rax+1]
0x140013576  cmp     [rcx+29h], dl
0x140013579  jb      loc_140013800
0x14001357f  lea     edx, [rax+6Dh]
0x140013582  lea     r9, [rsp+0A8h+Source1]
0x140013587  jmp     loc_1400137F0
0x14001358c  mov     dword ptr [r14], 0
0x140013593  mov     qword ptr [r14+8], 0
0x14001359b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135a2  cmp     rcx, r12
0x1400135a5  jz      short loc_1400135CE
0x1400135a7  mov     eax, [rcx+2Ch]
0x1400135aa  test    al, 2
0x1400135ac  jz      short loc_1400135CE
0x1400135ae  cmp     byte ptr [rcx+29h], 3
0x1400135b2  jb      short loc_1400135CE
0x1400135b4  mov     edx, 6Eh ; 'n'
0x1400135b9  lea     r9, [rsp+0A8h+Source1]
0x1400135be  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400135c5  mov     rcx, [rcx+18h]
0x1400135c9  call    WPP_SF__guid_
0x1400135ce  lea     r14, [rsi+20h]
0x1400135d2  mov     rcx, r14; SpinLock
0x1400135d5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400135dc  nop     dword ptr [rax+rax+00h]
0x1400135e1  mov     edx, [rsi+5260h]
0x1400135e7  mov     rcx, r14; SpinLock
0x1400135ea  bt      edx, 9
0x1400135ee  jnb     short loc_140013602
0x1400135f0  mov     dl, al; NewIrql
0x1400135f2  call    cs:__imp_KeReleaseSpinLock
0x1400135f9  nop     dword ptr [rax+rax+00h]
0x1400135fe  xor     dl, dl
0x140013600  jmp     short loc_14001361E
0x140013602  and     edx, 0FFFFFFFBh
0x140013605  mov     [rsi+5260h], edx
0x14001360b  mov     dl, al; NewIrql
0x14001360d  call    cs:__imp_KeReleaseSpinLock
0x140013614  nop     dword ptr [rax+rax+00h]
0x140013619  mov     edx, 1
0x14001361e  xor     r8d, r8d
0x140013621  mov     rcx, rsi
0x140013624  call    TpiFsmDisconnectComplete
0x140013629  jmp     loc_140013A4E
0x14001362e  lea     rax, WPP_GLOBAL_Control
0x140013635  mov     rcx, cs:WPP_GLOBAL_Control
0x14001363c  cmp     rcx, rax
0x14001363f  jz      short loc_140013669
0x140013641  mov     eax, [rcx+2Ch]
0x140013644  test    al, 2
0x140013646  jz      short loc_140013669
0x140013648  cmp     byte ptr [rcx+29h], 1
0x14001364c  jb      short loc_140013669
0x14001364e  mov     edx, 6Ch ; 'l'
0x140013653  mov     r9d, 128040h
0x140013659  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140013660  mov     rcx, [rcx+18h]
0x140013664  call    WPP_SF_d
0x140013669  mov     rax, [rsp+0A8h+var_60]
0x14001366e  mov     dword ptr [rax], 0C000000Dh
0x140013674  mov     qword ptr [rax+8], 0
0x14001367c  lea     r12, WPP_GLOBAL_Control
0x140013683  mov     rsi, [rsp+0A8h+var_58]
0x140013688  mov     rdi, rsi
0x14001368b  jmp     loc_140013A4E
0x140013690  mov     ecx, 1030h
0x140013695  cmp     r8d, ecx
0x140013698  jz      short loc_1400136E3
0x14001369a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400136a1  cmp     rcx, r12
0x1400136a4  jz      short loc_1400136CF
0x1400136a6  mov     eax, [rcx+2Ch]
0x1400136a9  test    al, 2
0x1400136ab  jz      short loc_1400136CF
0x1400136ad  mov     edx, 1
0x1400136b2  cmp     [rcx+29h], dl
0x1400136b5  jb      short loc_1400136CF
0x1400136b7  mov     edx, 64h ; 'd'
0x1400136bc  mov     r9d, r8d
0x1400136bf  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400136c6  mov     rcx, [rcx+18h]
0x1400136ca  call    WPP_SF_d
0x1400136cf  mov     dword ptr [r14], 0C000000Dh
0x1400136d6  mov     qword ptr [r14+8], 1030h
0x1400136de  jmp     loc_140013A4E
0x1400136e3  mov     r8d, 6D704353h
0x1400136e9  mov     rdx, rcx
0x1400136ec  mov     ecx, 40h ; '@'
0x1400136f1  call    cs:__imp_ExAllocatePool2
0x1400136f8  nop     dword ptr [rax+rax+00h]
0x1400136fd  mov     rdi, rax
0x140013700  mov     [rsp+0A8h+NdisVcHandle], rax
0x140013705  test    rax, rax
0x140013708  jnz     short loc_140013749
0x14001370a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013711  cmp     rcx, r12
0x140013714  jz      short loc_140013739
0x140013716  mov     edx, [rcx+2Ch]
0x140013719  test    dl, 2
0x14001371c  jz      short loc_140013739
0x14001371e  lea     edx, [rax+1]
0x140013721  cmp     [rcx+29h], dl
0x140013724  jb      short loc_140013739
0x140013726  lea     edx, [rax+65h]
0x140013729  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140013730  mov     rcx, [rcx+18h]
0x140013734  call    WPP_SF_
0x140013739  mov     dword ptr [r14], 0C0000017h
0x140013740  mov     [r14+8], rsi
0x140013744  jmp     loc_140013A4E
0x140013749  test    r13b, 7
0x14001374d  jz      short loc_14001375C
0x14001374f  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140013756  nop     dword ptr [rax+rax+00h]
0x14001375b  int     3; Trap to Debugger
0x14001375c  mov     r8d, 1030h; Size
0x140013762  mov     rdx, r13; Src
0x140013765  mov     rcx, rdi; void *
0x140013768  call    RtlCopyFromUser
0x14001376d  nop
0x14001376e  mov     r9d, [rdi+28h]
0x140013772  mov     r13d, 1000h
0x140013778  cmp     r9d, r13d
0x14001377b  jbe     short loc_1400137BF
0x14001377d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013784  cmp     rcx, r12
0x140013787  jz      short loc_1400137AF
0x140013789  mov     eax, [rcx+2Ch]
0x14001378c  test    al, 2
0x14001378e  jz      short loc_1400137AF
0x140013790  mov     edx, 1
0x140013795  cmp     [rcx+29h], dl
0x140013798  jb      short loc_1400137AF
0x14001379a  mov     edx, 67h ; 'g'
0x14001379f  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400137a6  mov     rcx, [rcx+18h]
0x1400137aa  call    WPP_SF_d
0x1400137af  mov     dword ptr [r14], 0C000000Dh
0x1400137b6  mov     [r14+8], r13
0x1400137ba  jmp     loc_140013A4E
0x1400137bf  mov     rcx, rdi; Source1
0x1400137c2  call    GetContextFromCorrelationGuid
0x1400137c7  mov     rsi, rax
0x1400137ca  test    rax, rax
0x1400137cd  jnz     short loc_140013814
0x1400137cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137d6  cmp     rcx, r12
0x1400137d9  jz      short loc_140013800
0x1400137db  mov     eax, [rcx+2Ch]
0x1400137de  test    al, 2
0x1400137e0  jz      short loc_140013800
0x1400137e2  lea     edx, [rsi+1]
0x1400137e5  cmp     [rcx+29h], dl
0x1400137e8  jb      short loc_140013800
0x1400137ea  lea     edx, [rsi+68h]
0x1400137ed  mov     r9, rdi
0x1400137f0  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400137f7  mov     rcx, [rcx+18h]
0x1400137fb  call    WPP_SF__guid_
0x140013800  mov     dword ptr [r14], 0C0000008h
0x140013807  mov     qword ptr [r14+8], 0
0x14001380f  jmp     loc_140013A4E
0x140013814  mov     dword ptr [r14], 0
0x14001381b  mov     qword ptr [r14+8], 0
0x140013823  mov     [rsp+0A8h+NdisVcHandle], 0
0x14001382c  xor     r13d, r13d
0x14001382f  mov     [rsp+0A8h+var_68], r13
0x140013834  mov     rcx, cs:WPP_GLOBAL_Control
0x14001383b  cmp     rcx, r12
0x14001383e  jz      short loc_14001386B
0x140013840  mov     eax, [rcx+2Ch]
0x140013843  test    al, 2
0x140013845  jz      short loc_14001386B
0x140013847  cmp     byte ptr [rcx+29h], 3
0x14001384b  jb      short loc_14001386B
0x14001384d  lea     edx, [r13+69h]
0x140013851  mov     eax, [rdi+10h]
0x140013854  mov     [rsp+0A8h+var_88], eax
0x140013858  mov     r9, rdi
0x14001385b  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140013862  mov     rcx, [rcx+18h]
0x140013866  call    WPP_SF__guid_D
0x14001386b  cmp     [rdi+10h], r13d
0x14001386f  jnz     loc_1400139B8
0x140013875  lea     r13, [rsi+20h]
0x140013879  mov     rcx, r13; SpinLock
0x14001387c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013883  nop     dword ptr [rax+rax+00h]
0x140013888  mov     cl, al
0x14001388a  mov     [rsp+0A8h+var_78], al
0x14001388e  mov     rax, [rsi+28h]
0x140013892  mov     [rsp+0A8h+NdisVcHandle], rax
0x140013897  cmp     byte ptr [rsi+1FBh], 0
0x14001389e  jz      short loc_1400138AD
0x1400138a0  mov     edx, 1
0x1400138a5  mov     eax, edx
0x1400138a7  mov     [rsp+0A8h+var_74], edx
0x1400138ab  jmp     short loc_14001391C
0x1400138ad  mov     [rsp+0A8h+var_3C], 0
0x1400138b5  mov     [rsp+0A8h+var_74], 0
0x1400138bd  lea     rax, DPSendCompleteCallback
0x1400138c4  mov     qword ptr [rsp+0A8h+Source1+8], rax
  ... truncated ...
```
