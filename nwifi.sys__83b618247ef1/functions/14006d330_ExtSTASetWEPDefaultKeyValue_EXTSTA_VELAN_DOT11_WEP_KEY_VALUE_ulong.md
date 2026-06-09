# ExtSTASetWEPDefaultKeyValue(EXTSTA_VELAN *,_DOT11_WEP_KEY_VALUE *,ulong)

- ea: `0x14006d330`
- end: `0x14006d7fc`
- name: `?ExtSTASetWEPDefaultKeyValue@@YAJPEAUEXTSTA_VELAN@@PEAU_DOT11_WEP_KEY_VALUE@@K@Z`
- size: `1228`
- prototype: `int(struct EXTSTA_VELAN *, struct _DOT11_WEP_KEY_VALUE *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a82c`
- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x14006d330`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006d51b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006d51b`
- `ntoskrnl!ExAllocatePool2` at `0x14006d530`
- `ntoskrnl!ExAllocatePool2` at `0x14006d530`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006d746`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006d746`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d757`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d757`
- `NDIS!NdisReleaseRWLock` at `0x14006d5b9`
- `NDIS!NdisReleaseRWLock` at `0x14006d680`
- `NDIS!NdisReleaseRWLock` at `0x14006d5b9`
- `NDIS!NdisReleaseRWLock` at `0x14006d680`
- `NDIS!NdisAcquireRWLockRead` at `0x14006d590`
- `NDIS!NdisAcquireRWLockRead` at `0x14006d590`

## pseudocode

```c
__int64 __fastcall ExtSTASetWEPDefaultKeyValue(
        struct EXTSTA_VELAN *a1,
        struct _DOT11_WEP_KEY_VALUE *a2,
        unsigned int a3)
{
  __int64 v3; // r9
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
  v3 = *((unsigned int *)a2 + 6);
  v5 = a1;
  if ( (unsigned int)v3 <= 0xFFFF
    && (int)v3 + 28 >= (unsigned int)v3
    && a3 >= (int)v3 + 28
    && (v6 = *((_DWORD *)a2 + 1)) != 0 )
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
          if ( (unsigned int)(v3 + 38) < 0x10 )
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
            Pool2 = (char *)ExAllocatePool2(64, v20, 808464432, v3);
          }
          else
          {
            p_DeviceQueue = &stru_1400B0180;
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
0x14006d330  mov     [rsp+arg_8], rbp
0x14006d335  mov     [rsp+arg_18], rsi
0x14006d33a  mov     dword ptr [rsp+Size], r8d
0x14006d33f  push    rdi
0x14006d340  push    r12
0x14006d342  push    r13
0x14006d344  push    r14
0x14006d346  push    r15
0x14006d348  sub     rsp, 30h
0x14006d34c  mov     r9d, [rdx+18h]
0x14006d350  mov     rbp, rdx
0x14006d353  mov     rdi, rcx
0x14006d356  cmp     r9d, 0FFFFh
0x14006d35d  ja      loc_14006D7CD
0x14006d363  lea     eax, [r9+1Ch]
0x14006d367  cmp     eax, r9d
0x14006d36a  jb      loc_14006D7CD
0x14006d370  cmp     r8d, eax
0x14006d373  jb      loc_14006D7CD
0x14006d379  mov     eax, [rdx+4]
0x14006d37c  mov     esi, 1
0x14006d381  cmp     eax, esi
0x14006d383  jb      loc_14006D7CD
0x14006d389  mov     ecx, [rcx+6BCh]
0x14006d38f  lea     r12d, [rax-1]
0x14006d393  lea     eax, [r12-4]
0x14006d398  lea     r15, [rdx+8]
0x14006d39c  cmp     eax, 3
0x14006d39f  ja      loc_14006D44C
0x14006d3a5  mov     eax, 7B8h
0x14006d3aa  xor     r8d, r8d
0x14006d3ad  cmp     ecx, esi
0x14006d3af  lea     edx, [rax+70h]
0x14006d3b2  cmovnz  eax, edx
0x14006d3b5  lea     r10d, [rdx-68h]
0x14006d3b9  mov     r11d, [rax+rdi]
0x14006d3bd  lea     eax, [rdx+8]
0x14006d3c0  cmovnz  r10d, eax
0x14006d3c4  cmp     r8d, r11d
0x14006d3c7  jnb     short loc_14006D3DF
0x14006d3c9  mov     rcx, [r10+rdi]
0x14006d3cd  mov     eax, [r15]
0x14006d3d0  cmp     [rcx+r8*4], eax
0x14006d3d4  jz      loc_14006D4C1
0x14006d3da  add     r8d, esi
0x14006d3dd  jmp     short loc_14006D3C4
0x14006d3df  cmp     cs:Microsoft_Windows_NWiFiEnableBits, 0
0x14006d3e6  jge     short loc_14006D40E
0x14006d3e8  mov     r9, [rdi+0A38h]
0x14006d3ef  lea     rdx, UnsupportedAlgorithm
0x14006d3f6  mov     eax, [r15]
0x14006d3f9  mov     [rsp+58h+var_30], eax
0x14006d3fd  lea     r8, [r9+1338h]
0x14006d404  mov     qword ptr [rsp+58h+var_38], r8
0x14006d409  call    McTemplateK0pjq_EtwWriteTransfer
0x14006d40e  mov     edi, 0C000000Dh
0x14006d413  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d41a  lea     rsi, WPP_GLOBAL_Control
0x14006d421  cmp     rcx, rsi
0x14006d424  jz      loc_14006D7D2
0x14006d42a  mov     r9d, [r15]
0x14006d42d  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006d434  mov     rcx, [rcx+18h]
0x14006d438  mov     edx, 16h
0x14006d43d  mov     [rsp+58h+var_38], r12d
0x14006d442  call    WPP_SF_Dd
0x14006d447  jmp     loc_14006D7D2
0x14006d44c  mov     r8d, [r15]
0x14006d44f  test    r15, r15
0x14006d452  jz      short loc_14006D457
0x14006d454  mov     [r15], r8d
0x14006d457  mov     eax, 798h
0x14006d45c  xor     edx, edx
0x14006d45e  cmp     ecx, esi
0x14006d460  lea     r10d, [rax+70h]
0x14006d464  cmovnz  eax, r10d
0x14006d468  mov     r11d, [rax+rdi]
0x14006d46c  lea     eax, [r10+8]
0x14006d470  lea     r10d, [rax-70h]
0x14006d474  cmovnz  r10d, eax
0x14006d478  cmp     edx, r11d
0x14006d47b  jnb     short loc_14006D48B
0x14006d47d  mov     rax, [r10+rdi]
0x14006d481  cmp     [rax+rdx*4], r8d
0x14006d485  jz      short loc_14006D4C1
0x14006d487  add     edx, esi
0x14006d489  jmp     short loc_14006D478
0x14006d48b  lea     eax, [r8-1]
0x14006d48f  test    eax, 0FFFFFFFBh
0x14006d494  jnz     loc_14006D76C
0x14006d49a  xor     edx, edx
0x14006d49c  mov     r8d, 101h
0x14006d4a2  cmp     edx, r11d
0x14006d4a5  jnb     loc_14006D76C
0x14006d4ab  mov     rax, [r10+rdi]
0x14006d4af  cmp     [rax+rdx*4], r8d
0x14006d4b3  jz      short loc_14006D4B9
0x14006d4b5  add     edx, esi
0x14006d4b7  jmp     short loc_14006D4A2
0x14006d4b9  test    r15, r15
0x14006d4bc  jz      short loc_14006D4C1
0x14006d4be  mov     [r15], r8d
0x14006d4c1  lea     r13d, [r9+16h]
0x14006d4c5  lea     eax, [r13+10h]
0x14006d4c9  cmp     eax, 10h
0x14006d4cc  jb      loc_14006D765
0x14006d4d2  mov     ecx, 40h ; '@'
0x14006d4d7  mov     r14d, 30303030h
0x14006d4dd  cmp     eax, ecx
0x14006d4df  ja      short loc_14006D4EA
0x14006d4e1  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x14006d4e8  jmp     short loc_14006D518
0x14006d4ea  cmp     eax, 100h
0x14006d4ef  ja      short loc_14006D4FA
0x14006d4f1  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006d4f8  jmp     short loc_14006D518
0x14006d4fa  cmp     eax, 400h
0x14006d4ff  ja      short loc_14006D50A
0x14006d501  lea     rsi, Lookaside
0x14006d508  jmp     short loc_14006D518
0x14006d50a  cmp     eax, 800h
0x14006d50f  ja      short loc_14006D529
0x14006d511  lea     rsi, stru_1400B0180
0x14006d518  mov     rcx, rsi; Lookaside
0x14006d51b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006d522  nop     dword ptr [rax+rax+00h]
0x14006d527  jmp     short loc_14006D53C
0x14006d529  xor     esi, esi
0x14006d52b  mov     edx, eax
0x14006d52d  mov     r8d, r14d
0x14006d530  call    cs:__imp_ExAllocatePool2
0x14006d537  nop     dword ptr [rax+rax+00h]
0x14006d53c  test    rax, rax
0x14006d53f  jz      loc_14006D765
0x14006d545  mov     [rax+8], r14d
0x14006d549  xor     edx, edx; Val
0x14006d54b  lea     r14, [rax+10h]
0x14006d54f  mov     r8d, r13d; Size
0x14006d552  mov     rcx, r14; void *
0x14006d555  mov     [rax], rsi
0x14006d558  call    memset
0x14006d55d  cmp     dword ptr [rbp+0], 0
0x14006d561  lea     rsi, WPP_GLOBAL_Control
0x14006d568  jnz     loc_14006D68C
0x14006d56e  mov     rcx, [rdi+0A38h]
0x14006d575  lea     rdx, [rsp+58h+LockState]; LockState
0x14006d57a  xor     eax, eax
0x14006d57c  mov     [rsp+58h+LockState.OldIrql], 0
0x14006d581  mov     word ptr [rsp+58h+LockState.LockState], ax
0x14006d586  xor     r8d, r8d; Flags
0x14006d589  mov     rcx, [rcx+90h]; Lock
0x14006d590  call    cs:__imp_NdisAcquireRWLockRead
0x14006d597  nop     dword ptr [rax+rax+00h]
0x14006d59c  mov     eax, [rdi+14Ch]
0x14006d5a2  test    eax, eax
0x14006d5a4  jnz     short loc_14006D61B
0x14006d5a6  mov     rcx, [rdi+0A38h]
0x14006d5ad  lea     rdx, [rsp+58h+LockState]; LockState
0x14006d5b2  mov     rcx, [rcx+90h]; Lock
0x14006d5b9  call    cs:__imp_NdisReleaseRWLock
0x14006d5c0  nop     dword ptr [rax+rax+00h]
0x14006d5c5  cmp     cs:Microsoft_Windows_NWiFiEnableBits, 0
0x14006d5cc  jge     short loc_14006D5F5
0x14006d5ce  mov     r9, [rdi+0A38h]
0x14006d5d5  lea     rdx, NoAssociation
0x14006d5dc  mov     [rsp+58h+var_30], 0C0000184h
0x14006d5e4  lea     r8, [r9+1338h]
0x14006d5eb  mov     qword ptr [rsp+58h+var_38], r8
0x14006d5f0  call    McTemplateK0pjq_EtwWriteTransfer
0x14006d5f5  mov     edi, 0C0000184h
0x14006d5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d601  lea     rsi, WPP_GLOBAL_Control
0x14006d608  cmp     rcx, rsi
0x14006d60b  jz      loc_14006D71E
0x14006d611  mov     edx, 18h
0x14006d616  jmp     loc_14006D70E
0x14006d61b  cmp     dword ptr [rdi+64Ch], 1
0x14006d622  jnz     short loc_14006D65D
0x14006d624  cmp     eax, 1
0x14006d627  jz      short loc_14006D64A
0x14006d629  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d630  cmp     rcx, rsi
0x14006d633  jz      short loc_14006D64A
0x14006d635  mov     rcx, [rcx+18h]
0x14006d639  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006d640  mov     edx, 19h
0x14006d645  call    WPP_SF_
0x14006d64a  mov     eax, [rdi+644h]
0x14006d650  mov     [r14+0Ch], eax
0x14006d654  movzx   eax, word ptr [rdi+648h]
0x14006d65b  jmp     short loc_14006D668
0x14006d65d  mov     eax, [rbp+0Ch]
0x14006d660  mov     [r14+0Ch], eax
0x14006d664  movzx   eax, word ptr [rbp+10h]
0x14006d668  mov     [r14+10h], ax
0x14006d66d  lea     rdx, [rsp+58h+LockState]; LockState
0x14006d672  mov     rcx, [rdi+0A38h]
0x14006d679  mov     rcx, [rcx+90h]; Lock
0x14006d680  call    cs:__imp_NdisReleaseRWLock
0x14006d687  nop     dword ptr [rax+rax+00h]
0x14006d68c  mov     dword ptr [r14], 180180h
0x14006d693  lea     rdx, [rbp+1Ch]; Src
0x14006d697  mov     [r14+4], r12d
0x14006d69b  lea     rcx, [r14+16h]; void *
0x14006d69f  cmp     dword ptr [rbp+14h], 1
0x14006d6a3  setnz   al
0x14006d6a6  mov     [r14+12h], al
0x14006d6aa  cmp     dword ptr [rbp+0], 0
0x14006d6ae  setnz   al
0x14006d6b1  mov     [r14+13h], al
0x14006d6b5  mov     eax, [r15]
0x14006d6b8  mov     [r14+8], eax
0x14006d6bc  movzx   eax, word ptr [rbp+18h]
0x14006d6c0  mov     r8d, eax; Size
0x14006d6c3  mov     [r14+14h], ax
0x14006d6c8  call    memmove
0x14006d6cd  mov     rcx, [rdi+0A38h]
0x14006d6d4  mov     r9, r14; void *
0x14006d6d7  mov     edx, 1; unsigned int
0x14006d6dc  mov     [rsp+58h+var_38], r13d; unsigned int
0x14006d6e1  mov     r8d, 0E01018Bh; unsigned int
0x14006d6e7  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006d6eb  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006d6f0  cmp     byte ptr [r14+12h], 0
0x14006d6f5  mov     edi, eax
0x14006d6f7  jnz     short loc_14006D71E
0x14006d6f9  test    eax, eax
0x14006d6fb  jz      short loc_14006D71E
0x14006d6fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d704  cmp     rcx, rsi
0x14006d707  jz      short loc_14006D71E
0x14006d709  mov     edx, 1Ah
0x14006d70e  mov     rcx, [rcx+18h]
0x14006d712  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006d719  call    WPP_SF_
0x14006d71e  test    r14, r14
0x14006d721  jz      loc_14006D7D2
0x14006d727  mov     r8d, r13d; Size
0x14006d72a  xor     edx, edx; Val
0x14006d72c  mov     rcx, r14; void *
0x14006d72f  call    memset
0x14006d734  lea     rcx, [r14-10h]; P
0x14006d738  mov     rax, [rcx]
0x14006d73b  test    rax, rax
0x14006d73e  jz      short loc_14006D754
0x14006d740  mov     rdx, rcx; Entry
0x14006d743  mov     rcx, rax; Lookaside
0x14006d746  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006d74d  nop     dword ptr [rax+rax+00h]
0x14006d752  jmp     short loc_14006D7D2
0x14006d754  mov     edx, [rcx+8]; Tag
0x14006d757  call    cs:__imp_ExFreePoolWithTag
0x14006d75e  nop     dword ptr [rax+rax+00h]
0x14006d763  jmp     short loc_14006D7D2
0x14006d765  mov     edi, 0C000009Ah
0x14006d76a  jmp     short loc_14006D7D2
0x14006d76c  cmp     cs:Microsoft_Windows_NWiFiEnableBits, 0
0x14006d773  jge     short loc_14006D79B
0x14006d775  mov     r9, [rdi+0A38h]
0x14006d77c  lea     rdx, UnsupportedAlgorithm
0x14006d783  mov     eax, [r15]
0x14006d786  mov     [rsp+58h+var_30], eax
0x14006d78a  lea     r8, [r9+1338h]
0x14006d791  mov     qword ptr [rsp+58h+var_38], r8
0x14006d796  call    McTemplateK0pjq_EtwWriteTransfer
0x14006d79b  mov     edi, 0C000000Dh
0x14006d7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d7a7  lea     rsi, WPP_GLOBAL_Control
0x14006d7ae  cmp     rcx, rsi
0x14006d7b1  jz      short loc_14006D7D2
0x14006d7b3  mov     r9d, [r15]
0x14006d7b6  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006d7bd  mov     rcx, [rcx+18h]
0x14006d7c1  mov     edx, 17h
0x14006d7c6  call    WPP_SF_d
0x14006d7cb  jmp     short loc_14006D7D2
0x14006d7cd  mov     edi, 0C000000Dh
0x14006d7d2  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x14006d7d7  xor     edx, edx; Val
0x14006d7d9  mov     rcx, rbp; void *
0x14006d7dc  call    memset
0x14006d7e1  mov     rbp, [rsp+58h+arg_8]
0x14006d7e6  mov     eax, edi
0x14006d7e8  mov     rsi, [rsp+58h+arg_18]
0x14006d7ed  add     rsp, 30h
0x14006d7f1  pop     r15
0x14006d7f3  pop     r14
0x14006d7f5  pop     r13
0x14006d7f7  pop     r12
0x14006d7f9  pop     rdi
0x14006d7fa  retn
```
