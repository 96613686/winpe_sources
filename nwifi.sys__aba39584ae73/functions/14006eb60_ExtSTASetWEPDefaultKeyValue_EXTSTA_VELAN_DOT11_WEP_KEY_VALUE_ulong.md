# ExtSTASetWEPDefaultKeyValue(EXTSTA_VELAN *,_DOT11_WEP_KEY_VALUE *,ulong)

- ea: `0x14006eb60`
- end: `0x14006f02c`
- name: `?ExtSTASetWEPDefaultKeyValue@@YAJPEAUEXTSTA_VELAN@@PEAU_DOT11_WEP_KEY_VALUE@@K@Z`
- size: `1228`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, struct _DOT11_WEP_KEY_VALUE *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a81c`
- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x14006eb60`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ed4b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ed4b`
- `ntoskrnl!ExAllocatePool2` at `0x14006ed60`
- `ntoskrnl!ExAllocatePool2` at `0x14006ed60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006ef76`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006ef76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ef87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ef87`
- `NDIS!NdisReleaseRWLock` at `0x14006ede9`
- `NDIS!NdisReleaseRWLock` at `0x14006eeb0`
- `NDIS!NdisReleaseRWLock` at `0x14006ede9`
- `NDIS!NdisReleaseRWLock` at `0x14006eeb0`
- `NDIS!NdisAcquireRWLockRead` at `0x14006edc0`
- `NDIS!NdisAcquireRWLockRead` at `0x14006edc0`

## pseudocode

```c
__int64 __fastcall ExtSTASetWEPDefaultKeyValue(
        struct EXTSTA_VELAN *a1,
        struct _DOT11_WEP_KEY_VALUE *a2,
        unsigned int a3)
{
  unsigned int v3; // r9d
  struct EXTSTA_VELAN *v5; // rdi
  int v6; // eax
  int v7; // r12d
  unsigned int *v8; // r15
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r10
  unsigned int v12; // edi
  unsigned int v13; // r8d
  __int64 v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // r11d
  __int64 v17; // r10
  __int64 i; // rdx
  unsigned int v19; // r13d
  unsigned int v20; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rsi
  char *Pool2; // rax
  _BYTE *v23; // r14
  _VELAN *pGenVElan; // rcx
  unsigned int uNumAssoc; // eax
  int v26; // ecx
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  __int16 v29; // ax
  size_t v30; // r8
  unsigned int v31; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF
  size_t Size; // [rsp+70h] [rbp+18h]

  LODWORD(Size) = a3;
  v3 = *((_DWORD *)a2 + 6);
  v5 = a1;
  if ( v3 <= 0xFFFF && v3 + 28 >= v3 && a3 >= v3 + 28 && (v6 = *((_DWORD *)a2 + 1)) != 0 )
  {
    LODWORD(a1) = a1->Rw.DesiredBSSType;
    v7 = v6 - 1;
    v8 = (unsigned int *)((char *)a2 + 8);
    if ( (unsigned int)(v6 - 5) > 3 )
    {
      v13 = *v8;
      if ( a2 != (struct _DOT11_WEP_KEY_VALUE *)-8LL )
        *v8 = v13;
      v14 = 1944;
      v15 = 0;
      if ( (_DWORD)a1 != 1 )
        v14 = 2056;
      v16 = *(unsigned int *)((char *)&v5->ModuleStatus.uValue + v14);
      v17 = 1952;
      if ( (_DWORD)a1 != 1 )
        v17 = 2064;
      while ( (unsigned int)v15 < v16 )
      {
        if ( *(_DWORD *)(*(_QWORD *)((char *)&v5->ModuleStatus.0 + v17) + 4 * v15) == v13 )
        {
LABEL_33:
          v19 = v3 + 22;
          v20 = v3 + 38;
          if ( v3 + 38 < 0x10 )
            goto LABEL_67;
          if ( v20 <= 0x40 )
          {
            p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
            goto LABEL_42;
          }
          if ( v20 <= 0x100 )
          {
            p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
            goto LABEL_42;
          }
          if ( v20 <= 0x400 )
          {
            p_DeviceQueue = &Lookaside;
            goto LABEL_42;
          }
          if ( v20 > 0x800 )
          {
            p_DeviceQueue = 0;
            Pool2 = (char *)ExAllocatePool2(64, v20, 808464432);
          }
          else
          {
            p_DeviceQueue = &stru_1400B31C0;
LABEL_42:
            Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
          }
          if ( !Pool2 )
          {
LABEL_67:
            v12 = -1073741670;
            goto LABEL_73;
          }
          *((_DWORD *)Pool2 + 2) = 808464432;
          v23 = Pool2 + 16;
          *(_QWORD *)Pool2 = p_DeviceQueue;
          memset(Pool2 + 16, 0, v19);
          if ( !*(_DWORD *)a2 )
          {
            pGenVElan = v5->pGenVElan;
            LockState.OldIrql = 0;
            *(_WORD *)&LockState.LockState = 0;
            NdisAcquireRWLockRead(pGenVElan->pRWLock, &LockState, 0);
            uNumAssoc = v5->AssocMgr.uNumAssoc;
            if ( !uNumAssoc )
            {
              NdisReleaseRWLock(v5->pGenVElan->pRWLock, &LockState);
              if ( Microsoft_Windows_NWiFiEnableBits < 0 )
                McTemplateK0pjq_EtwWriteTransfer(
                  v26,
                  (unsigned int)NoAssociation,
                  &v5->pGenVElan->gDeviceId,
                  v5->pGenVElan,
                  (__int64)&v5->pGenVElan->gDeviceId,
                  132);
              v12 = -1073741436;
              v27 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                v28 = 24;
                goto LABEL_62;
              }
              goto LABEL_63;
            }
            if ( v5->RoD.CurrentBSSType == dot11_BSS_type_infrastructure )
            {
              if ( uNumAssoc != 1 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids);
              *((_DWORD *)v23 + 3) = *(_DWORD *)v5->RoD.CurrentBSSID;
              v29 = *(_WORD *)&v5->RoD.CurrentBSSID[4];
            }
            else
            {
              *((_DWORD *)v23 + 3) = *((_DWORD *)a2 + 3);
              v29 = *((_WORD *)a2 + 8);
            }
            *((_WORD *)v23 + 8) = v29;
            NdisReleaseRWLock(v5->pGenVElan->pRWLock, &LockState);
          }
          *(_DWORD *)v23 = 1573248;
          *((_DWORD *)v23 + 1) = v7;
          v23[18] = *((_DWORD *)a2 + 5) != 1;
          v23[19] = *(_DWORD *)a2 != 0;
          *((_DWORD *)v23 + 2) = *v8;
          v30 = *((unsigned __int16 *)a2 + 12);
          *((_WORD *)v23 + 10) = *((_WORD *)a2 + 12);
          memmove(v23 + 22, (char *)a2 + 28, v30);
          v31 = PtRequestAdapterSync(v5->pGenVElan->pAdapt, 1u, 0xE01018Bu, v23, v19);
          v12 = v31;
          if ( !v23[18] )
          {
            if ( v31 )
            {
              v27 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                v28 = 26;
LABEL_62:
                WPP_SF_(v27->AttachedDevice, v28, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids);
              }
            }
          }
LABEL_63:
          if ( v23 )
          {
            memset(v23, 0, v19);
            if ( *((_QWORD *)v23 - 2) )
              ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v23 - 2), v23 - 16);
            else
              ExFreePoolWithTag(v23 - 16, *((_DWORD *)v23 - 2));
          }
          goto LABEL_73;
        }
        v15 = (unsigned int)(v15 + 1);
      }
      if ( ((v13 - 1) & 0xFFFFFFFB) == 0 )
      {
        for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)((char *)&v5->ModuleStatus.0 + v17) + 4 * i) == 257 )
          {
            if ( v8 )
              *v8 = 257;
            goto LABEL_33;
          }
        }
      }
      if ( Microsoft_Windows_NWiFiEnableBits < 0 )
        McTemplateK0pjq_EtwWriteTransfer(
          (_DWORD)a1,
          (unsigned int)UnsupportedAlgorithm,
          &v5->pGenVElan->gDeviceId,
          v5->pGenVElan,
          (__int64)&v5->pGenVElan->gDeviceId,
          *v8);
      v12 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, *v8);
    }
    else
    {
      v9 = 1976;
      v10 = 0;
      if ( (_DWORD)a1 != 1 )
        v9 = 2088;
      v11 = 1984;
      if ( (_DWORD)a1 != 1 )
        v11 = 2096;
      while ( (unsigned int)v10 < *(unsigned int *)((char *)&v5->ModuleStatus.uValue + v9) )
      {
        a1 = *(struct EXTSTA_VELAN **)((char *)&v5->ModuleStatus.0 + v11);
        if ( *(&a1->ModuleStatus.uValue + v10) == *v8 )
          goto LABEL_33;
        v10 = (unsigned int)(v10 + 1);
      }
      if ( Microsoft_Windows_NWiFiEnableBits < 0 )
        McTemplateK0pjq_EtwWriteTransfer(
          (_DWORD)a1,
          (unsigned int)UnsupportedAlgorithm,
          &v5->pGenVElan->gDeviceId,
          v5->pGenVElan,
          (__int64)&v5->pGenVElan->gDeviceId,
          *v8);
      v12 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, *v8, v7);
    }
  }
  else
  {
    v12 = -1073741811;
  }
LABEL_73:
  memset(a2, 0, (unsigned int)Size);
  return v12;
}

```

## disassembly

```asm
0x14006eb60  mov     [rsp+arg_8], rbp
0x14006eb65  mov     [rsp+arg_18], rsi
0x14006eb6a  mov     dword ptr [rsp+Size], r8d
0x14006eb6f  push    rdi
0x14006eb70  push    r12
0x14006eb72  push    r13
0x14006eb74  push    r14
0x14006eb76  push    r15
0x14006eb78  sub     rsp, 30h
0x14006eb7c  mov     r9d, [rdx+18h]
0x14006eb80  mov     rbp, rdx
0x14006eb83  mov     rdi, rcx
0x14006eb86  cmp     r9d, 0FFFFh
0x14006eb8d  ja      loc_14006EFFD
0x14006eb93  lea     eax, [r9+1Ch]
0x14006eb97  cmp     eax, r9d
0x14006eb9a  jb      loc_14006EFFD
0x14006eba0  cmp     r8d, eax
0x14006eba3  jb      loc_14006EFFD
0x14006eba9  mov     eax, [rdx+4]
0x14006ebac  mov     esi, 1
0x14006ebb1  cmp     eax, esi
0x14006ebb3  jb      loc_14006EFFD
0x14006ebb9  mov     ecx, [rcx+6BCh]
0x14006ebbf  lea     r12d, [rax-1]
0x14006ebc3  lea     eax, [r12-4]
0x14006ebc8  lea     r15, [rdx+8]
0x14006ebcc  cmp     eax, 3
0x14006ebcf  ja      loc_14006EC7C
0x14006ebd5  mov     eax, 7B8h
0x14006ebda  xor     r8d, r8d
0x14006ebdd  cmp     ecx, esi
0x14006ebdf  lea     edx, [rax+70h]
0x14006ebe2  cmovnz  eax, edx
0x14006ebe5  lea     r10d, [rdx-68h]
0x14006ebe9  mov     r11d, [rax+rdi]
0x14006ebed  lea     eax, [rdx+8]
0x14006ebf0  cmovnz  r10d, eax
0x14006ebf4  cmp     r8d, r11d
0x14006ebf7  jnb     short loc_14006EC0F
0x14006ebf9  mov     rcx, [r10+rdi]
0x14006ebfd  mov     eax, [r15]
0x14006ec00  cmp     [rcx+r8*4], eax
0x14006ec04  jz      loc_14006ECF1
0x14006ec0a  add     r8d, esi
0x14006ec0d  jmp     short loc_14006EBF4
0x14006ec0f  cmp     cs:Microsoft_Windows_NWiFiEnableBits, 0
0x14006ec16  jge     short loc_14006EC3E
0x14006ec18  mov     r9, [rdi+0A38h]
0x14006ec1f  lea     rdx, UnsupportedAlgorithm
0x14006ec26  mov     eax, [r15]
0x14006ec29  mov     [rsp+58h+var_30], eax
0x14006ec2d  lea     r8, [r9+1338h]
0x14006ec34  mov     qword ptr [rsp+58h+var_38], r8
0x14006ec39  call    McTemplateK0pjq_EtwWriteTransfer
0x14006ec3e  mov     edi, 0C000000Dh
0x14006ec43  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ec4a  lea     rsi, WPP_GLOBAL_Control
0x14006ec51  cmp     rcx, rsi
0x14006ec54  jz      loc_14006F002
0x14006ec5a  mov     r9d, [r15]
0x14006ec5d  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006ec64  mov     rcx, [rcx+18h]
0x14006ec68  mov     edx, 16h
0x14006ec6d  mov     [rsp+58h+var_38], r12d
0x14006ec72  call    WPP_SF_Dd
0x14006ec77  jmp     loc_14006F002
0x14006ec7c  mov     r8d, [r15]
0x14006ec7f  test    r15, r15
0x14006ec82  jz      short loc_14006EC87
0x14006ec84  mov     [r15], r8d
0x14006ec87  mov     eax, 798h
0x14006ec8c  xor     edx, edx
0x14006ec8e  cmp     ecx, esi
0x14006ec90  lea     r10d, [rax+70h]
0x14006ec94  cmovnz  eax, r10d
0x14006ec98  mov     r11d, [rax+rdi]
0x14006ec9c  lea     eax, [r10+8]
0x14006eca0  lea     r10d, [rax-70h]
0x14006eca4  cmovnz  r10d, eax
0x14006eca8  cmp     edx, r11d
0x14006ecab  jnb     short loc_14006ECBB
0x14006ecad  mov     rax, [r10+rdi]
0x14006ecb1  cmp     [rax+rdx*4], r8d
0x14006ecb5  jz      short loc_14006ECF1
0x14006ecb7  add     edx, esi
0x14006ecb9  jmp     short loc_14006ECA8
0x14006ecbb  lea     eax, [r8-1]
0x14006ecbf  test    eax, 0FFFFFFFBh
0x14006ecc4  jnz     loc_14006EF9C
0x14006ecca  xor     edx, edx
0x14006eccc  mov     r8d, 101h
0x14006ecd2  cmp     edx, r11d
0x14006ecd5  jnb     loc_14006EF9C
0x14006ecdb  mov     rax, [r10+rdi]
0x14006ecdf  cmp     [rax+rdx*4], r8d
0x14006ece3  jz      short loc_14006ECE9
0x14006ece5  add     edx, esi
0x14006ece7  jmp     short loc_14006ECD2
0x14006ece9  test    r15, r15
0x14006ecec  jz      short loc_14006ECF1
0x14006ecee  mov     [r15], r8d
0x14006ecf1  lea     r13d, [r9+16h]
0x14006ecf5  lea     eax, [r13+10h]
0x14006ecf9  cmp     eax, 10h
0x14006ecfc  jb      loc_14006EF95
0x14006ed02  mov     ecx, 40h ; '@'
0x14006ed07  mov     r14d, 30303030h
0x14006ed0d  cmp     eax, ecx
0x14006ed0f  ja      short loc_14006ED1A
0x14006ed11  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x14006ed18  jmp     short loc_14006ED48
0x14006ed1a  cmp     eax, 100h
0x14006ed1f  ja      short loc_14006ED2A
0x14006ed21  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006ed28  jmp     short loc_14006ED48
0x14006ed2a  cmp     eax, 400h
0x14006ed2f  ja      short loc_14006ED3A
0x14006ed31  lea     rsi, Lookaside
0x14006ed38  jmp     short loc_14006ED48
0x14006ed3a  cmp     eax, 800h
0x14006ed3f  ja      short loc_14006ED59
0x14006ed41  lea     rsi, stru_1400B31C0
0x14006ed48  mov     rcx, rsi; Lookaside
0x14006ed4b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006ed52  nop     dword ptr [rax+rax+00h]
0x14006ed57  jmp     short loc_14006ED6C
0x14006ed59  xor     esi, esi
0x14006ed5b  mov     edx, eax
0x14006ed5d  mov     r8d, r14d
0x14006ed60  call    cs:__imp_ExAllocatePool2
0x14006ed67  nop     dword ptr [rax+rax+00h]
0x14006ed6c  test    rax, rax
0x14006ed6f  jz      loc_14006EF95
0x14006ed75  mov     [rax+8], r14d
0x14006ed79  xor     edx, edx; Val
0x14006ed7b  lea     r14, [rax+10h]
0x14006ed7f  mov     r8d, r13d; Size
0x14006ed82  mov     rcx, r14; void *
0x14006ed85  mov     [rax], rsi
0x14006ed88  call    memset
0x14006ed8d  cmp     dword ptr [rbp+0], 0
0x14006ed91  lea     rsi, WPP_GLOBAL_Control
0x14006ed98  jnz     loc_14006EEBC
0x14006ed9e  mov     rcx, [rdi+0A38h]
0x14006eda5  lea     rdx, [rsp+58h+LockState]; LockState
0x14006edaa  xor     eax, eax
0x14006edac  mov     [rsp+58h+LockState.OldIrql], 0
0x14006edb1  mov     word ptr [rsp+58h+LockState.LockState], ax
0x14006edb6  xor     r8d, r8d; Flags
0x14006edb9  mov     rcx, [rcx+90h]; Lock
0x14006edc0  call    cs:__imp_NdisAcquireRWLockRead
0x14006edc7  nop     dword ptr [rax+rax+00h]
0x14006edcc  mov     eax, [rdi+14Ch]
0x14006edd2  test    eax, eax
0x14006edd4  jnz     short loc_14006EE4B
0x14006edd6  mov     rcx, [rdi+0A38h]
0x14006eddd  lea     rdx, [rsp+58h+LockState]; LockState
0x14006ede2  mov     rcx, [rcx+90h]; Lock
0x14006ede9  call    cs:__imp_NdisReleaseRWLock
0x14006edf0  nop     dword ptr [rax+rax+00h]
0x14006edf5  cmp     cs:Microsoft_Windows_NWiFiEnableBits, 0
0x14006edfc  jge     short loc_14006EE25
0x14006edfe  mov     r9, [rdi+0A38h]
0x14006ee05  lea     rdx, NoAssociation
0x14006ee0c  mov     [rsp+58h+var_30], 0C0000184h
0x14006ee14  lea     r8, [r9+1338h]
0x14006ee1b  mov     qword ptr [rsp+58h+var_38], r8
0x14006ee20  call    McTemplateK0pjq_EtwWriteTransfer
0x14006ee25  mov     edi, 0C0000184h
0x14006ee2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ee31  lea     rsi, WPP_GLOBAL_Control
0x14006ee38  cmp     rcx, rsi
0x14006ee3b  jz      loc_14006EF4E
0x14006ee41  mov     edx, 18h
0x14006ee46  jmp     loc_14006EF3E
0x14006ee4b  cmp     dword ptr [rdi+64Ch], 1
0x14006ee52  jnz     short loc_14006EE8D
0x14006ee54  cmp     eax, 1
0x14006ee57  jz      short loc_14006EE7A
0x14006ee59  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ee60  cmp     rcx, rsi
0x14006ee63  jz      short loc_14006EE7A
0x14006ee65  mov     rcx, [rcx+18h]
0x14006ee69  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006ee70  mov     edx, 19h
0x14006ee75  call    WPP_SF_
0x14006ee7a  mov     eax, [rdi+644h]
0x14006ee80  mov     [r14+0Ch], eax
0x14006ee84  movzx   eax, word ptr [rdi+648h]
0x14006ee8b  jmp     short loc_14006EE98
0x14006ee8d  mov     eax, [rbp+0Ch]
0x14006ee90  mov     [r14+0Ch], eax
0x14006ee94  movzx   eax, word ptr [rbp+10h]
0x14006ee98  mov     [r14+10h], ax
0x14006ee9d  lea     rdx, [rsp+58h+LockState]; LockState
0x14006eea2  mov     rcx, [rdi+0A38h]
0x14006eea9  mov     rcx, [rcx+90h]; Lock
0x14006eeb0  call    cs:__imp_NdisReleaseRWLock
0x14006eeb7  nop     dword ptr [rax+rax+00h]
0x14006eebc  mov     dword ptr [r14], 180180h
0x14006eec3  lea     rdx, [rbp+1Ch]; Src
0x14006eec7  mov     [r14+4], r12d
0x14006eecb  lea     rcx, [r14+16h]; void *
0x14006eecf  cmp     dword ptr [rbp+14h], 1
0x14006eed3  setnz   al
0x14006eed6  mov     [r14+12h], al
0x14006eeda  cmp     dword ptr [rbp+0], 0
0x14006eede  setnz   al
0x14006eee1  mov     [r14+13h], al
0x14006eee5  mov     eax, [r15]
0x14006eee8  mov     [r14+8], eax
0x14006eeec  movzx   eax, word ptr [rbp+18h]
0x14006eef0  mov     r8d, eax; Size
0x14006eef3  mov     [r14+14h], ax
0x14006eef8  call    memmove
0x14006eefd  mov     rcx, [rdi+0A38h]
0x14006ef04  mov     r9, r14; void *
0x14006ef07  mov     edx, 1; unsigned int
0x14006ef0c  mov     [rsp+58h+var_38], r13d; unsigned int
0x14006ef11  mov     r8d, 0E01018Bh; unsigned int
0x14006ef17  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006ef1b  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006ef20  cmp     byte ptr [r14+12h], 0
0x14006ef25  mov     edi, eax
0x14006ef27  jnz     short loc_14006EF4E
0x14006ef29  test    eax, eax
0x14006ef2b  jz      short loc_14006EF4E
0x14006ef2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ef34  cmp     rcx, rsi
0x14006ef37  jz      short loc_14006EF4E
0x14006ef39  mov     edx, 1Ah
0x14006ef3e  mov     rcx, [rcx+18h]
0x14006ef42  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006ef49  call    WPP_SF_
0x14006ef4e  test    r14, r14
0x14006ef51  jz      loc_14006F002
0x14006ef57  mov     r8d, r13d; Size
0x14006ef5a  xor     edx, edx; Val
0x14006ef5c  mov     rcx, r14; void *
0x14006ef5f  call    memset
0x14006ef64  lea     rcx, [r14-10h]; P
0x14006ef68  mov     rax, [rcx]
0x14006ef6b  test    rax, rax
0x14006ef6e  jz      short loc_14006EF84
0x14006ef70  mov     rdx, rcx; Entry
0x14006ef73  mov     rcx, rax; Lookaside
0x14006ef76  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006ef7d  nop     dword ptr [rax+rax+00h]
0x14006ef82  jmp     short loc_14006F002
0x14006ef84  mov     edx, [rcx+8]; Tag
0x14006ef87  call    cs:__imp_ExFreePoolWithTag
0x14006ef8e  nop     dword ptr [rax+rax+00h]
0x14006ef93  jmp     short loc_14006F002
0x14006ef95  mov     edi, 0C000009Ah
0x14006ef9a  jmp     short loc_14006F002
0x14006ef9c  cmp     cs:Microsoft_Windows_NWiFiEnableBits, 0
0x14006efa3  jge     short loc_14006EFCB
0x14006efa5  mov     r9, [rdi+0A38h]
0x14006efac  lea     rdx, UnsupportedAlgorithm
0x14006efb3  mov     eax, [r15]
0x14006efb6  mov     [rsp+58h+var_30], eax
0x14006efba  lea     r8, [r9+1338h]
0x14006efc1  mov     qword ptr [rsp+58h+var_38], r8
0x14006efc6  call    McTemplateK0pjq_EtwWriteTransfer
0x14006efcb  mov     edi, 0C000000Dh
0x14006efd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006efd7  lea     rsi, WPP_GLOBAL_Control
0x14006efde  cmp     rcx, rsi
0x14006efe1  jz      short loc_14006F002
0x14006efe3  mov     r9d, [r15]
0x14006efe6  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006efed  mov     rcx, [rcx+18h]
0x14006eff1  mov     edx, 17h
0x14006eff6  call    WPP_SF_d
0x14006effb  jmp     short loc_14006F002
0x14006effd  mov     edi, 0C000000Dh
0x14006f002  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x14006f007  xor     edx, edx; Val
0x14006f009  mov     rcx, rbp; void *
0x14006f00c  call    memset
0x14006f011  mov     rbp, [rsp+58h+arg_8]
0x14006f016  mov     eax, edi
0x14006f018  mov     rsi, [rsp+58h+arg_18]
0x14006f01d  add     rsp, 30h
0x14006f021  pop     r15
0x14006f023  pop     r14
0x14006f025  pop     r13
0x14006f027  pop     r12
0x14006f029  pop     rdi
0x14006f02a  retn
```
