# WFDRoleCacheServiceAdvertisementList(_WFD_ROLE *,uchar *,ulong)

- ea: `0x14007b24c`
- end: `0x14007b5a6`
- name: `?WFDRoleCacheServiceAdvertisementList@@YAHPEAU_WFD_ROLE@@PEAEK@Z`
- size: `858`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x14007cb70`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x14007b24c`
- `0x14007e28c`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007b397`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007b397`
- `ntoskrnl!ExAllocatePool2` at `0x14007b3aa`
- `ntoskrnl!ExAllocatePool2` at `0x14007b3aa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b519`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b519`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b52a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b52a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007b4d2`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007b4d2`
- `NDIS!NdisReleaseRWLock` at `0x14007b4f6`
- `NDIS!NdisReleaseRWLock` at `0x14007b4f6`

## pseudocode

```c
__int64 __fastcall WFDRoleCacheServiceAdvertisementList(struct _WFD_ROLE *a1, unsigned __int8 *a2, unsigned int a3)
{
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  __int64 v7; // rcx
  unsigned int v8; // r14d
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // eax
  char *Pool2; // rax
  _WFDSVC_SERVICE_ADVERTISEMENT_ENTRY *v15; // rbp
  unsigned int v16; // r15d
  unsigned __int8 *v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdx
  _WFDSVC_SERVICE_ADVERTISEMENT_ENTRY *pCachedServiceAdvertisementList; // rsi
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+98h] [rbp+10h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
  if ( a2 && a3 >= 0x28 && a1 )
  {
    p_WaitListHead = 0;
    if ( a1->RoleType != WFD_ROLE_TYPE_DEVICE )
      goto LABEL_39;
    v7 = *((unsigned int *)a2 + 2);
    v8 = 156 * v7;
    if ( (unsigned __int64)(156 * v7) > 0xFFFFFFFF )
    {
      LODWORD(p_WaitListHead) = -1073741675;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)p_WaitListHead;
      v10 = 59;
      goto LABEL_38;
    }
    v11 = 180 * v7;
    if ( (unsigned __int64)(180 * v7) <= 0xFFFFFFFF )
    {
      v12 = *((unsigned int *)a2 + 3);
      if ( a3 < (int)v12 + (int)v11 )
      {
        LODWORD(p_WaitListHead) = -1073741811;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)p_WaitListHead;
        WPP_SF_DDDDD(WPP_GLOBAL_Control->AttachedDevice, v11, v12, a3, v12, v11, v7);
        goto LABEL_39;
      }
      v13 = v8 + 16;
      if ( v8 >= 0xFFFFFFF0 )
      {
LABEL_26:
        LODWORD(p_WaitListHead) = -1073741670;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)p_WaitListHead;
        v10 = 62;
        goto LABEL_38;
      }
      if ( v13 > 0x40 )
      {
        if ( v13 > 0x100 )
        {
          if ( v13 > 0x400 )
          {
            if ( v13 > 0x800 )
            {
              Pool2 = (char *)ExAllocatePool2(64, v13, 808613750);
LABEL_25:
              if ( Pool2 )
              {
                *((_DWORD *)Pool2 + 2) = 808613750;
                v15 = (_WFDSVC_SERVICE_ADVERTISEMENT_ENTRY *)(Pool2 + 16);
                *(_QWORD *)Pool2 = p_WaitListHead;
                LODWORD(p_WaitListHead) = 0;
                v16 = 0;
                memset(Pool2 + 16, 0, v8);
                v17 = &a2[*((unsigned int *)a2 + 3)];
                if ( *((_DWORD *)a2 + 2) )
                {
                  do
                  {
                    v18 = v16++;
                    v19 = v18;
                    v15[v19].AdvertisementID = *(_DWORD *)&v17[180 * v18];
                    v15[v19].ConfigMethods = *(_DWORD *)&v17[180 * v18 + 12];
                    v15[v19].bAutoAccept = v17[180 * v18 + 17];
                    v15[v19].ServiceStatus = v17[180 * v18 + 16];
                    *(_OWORD *)&v15[v19].SessionInfo.uSessionInfoLength = *(_OWORD *)&v17[180 * v18 + 18];
                    *(_OWORD *)&v15[v19].SessionInfo.ucSessionInfo[14] = *(_OWORD *)&v17[180 * v18 + 34];
                    *(_OWORD *)&v15[v19].SessionInfo.ucSessionInfo[30] = *(_OWORD *)&v17[180 * v18 + 50];
                    *(_OWORD *)&v15[v19].SessionInfo.ucSessionInfo[46] = *(_OWORD *)&v17[180 * v18 + 66];
                    *(_OWORD *)&v15[v19].SessionInfo.ucSessionInfo[62] = *(_OWORD *)&v17[180 * v18 + 82];
                    *(_OWORD *)&v15[v19].SessionInfo.ucSessionInfo[78] = *(_OWORD *)&v17[180 * v18 + 98];
                    *(_OWORD *)&v15[v19].SessionInfo.ucSessionInfo[94] = *(_OWORD *)&v17[180 * v18 + 114];
                    *(_OWORD *)&v15[v19].SessionInfo.ucSessionInfo[110] = *(_OWORD *)&v17[180 * v18 + 130];
                    *(_OWORD *)&v15[v19].SessionInfo.ucSessionInfo[126] = *(_OWORD *)&v17[180 * v18 + 146];
                    *(_WORD *)&v15[v19].SessionInfo.ucSessionInfo[142] = *(_WORD *)&v17[180 * v18 + 162];
                  }
                  while ( v16 < *((_DWORD *)a2 + 2) );
                }
                NdisAcquireRWLockWrite(a1->pRWLock, &LockState, 0);
                pCachedServiceAdvertisementList = a1->pCachedServiceAdvertisementList;
                pRWLock = a1->pRWLock;
                a1->uCachedServiceAdvertisementCount = v16;
                a1->pCachedServiceAdvertisementList = v15;
                NdisReleaseRWLock(pRWLock, &LockState);
                if ( pCachedServiceAdvertisementList )
                {
                  if ( *(_QWORD *)&pCachedServiceAdvertisementList[-1].SessionInfo.ucSessionInfo[128] )
                    ExFreeToNPagedLookasideList(
                      *(PNPAGED_LOOKASIDE_LIST *)&pCachedServiceAdvertisementList[-1].SessionInfo.ucSessionInfo[128],
                      &pCachedServiceAdvertisementList[-1].SessionInfo.ucSessionInfo[128]);
                  else
                    ExFreePoolWithTag(
                      &pCachedServiceAdvertisementList[-1].SessionInfo.ucSessionInfo[128],
                      *(_DWORD *)&pCachedServiceAdvertisementList[-1].SessionInfo.ucSessionInfo[136]);
                }
                goto LABEL_39;
              }
              goto LABEL_26;
            }
            p_WaitListHead = &stru_1400B31C0;
          }
          else
          {
            p_WaitListHead = &Lookaside;
          }
        }
        else
        {
          p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
      }
      Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
      goto LABEL_25;
    }
    LODWORD(p_WaitListHead) = -1073741675;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)p_WaitListHead;
    v10 = 60;
  }
  else
  {
    LODWORD(p_WaitListHead) = -1073741811;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)p_WaitListHead;
    v10 = 58;
  }
LABEL_38:
  WPP_SF_(v9->AttachedDevice, v10, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
LABEL_39:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      63,
      WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
      (unsigned int)p_WaitListHead);
  return (unsigned int)p_WaitListHead;
}

```

## disassembly

```asm
0x14007b24c  mov     r11, rsp
0x14007b24f  push    rbx
0x14007b250  push    rbp
0x14007b251  push    rsi
0x14007b252  push    rdi
0x14007b253  push    r12
0x14007b255  push    r13
0x14007b257  push    r14
0x14007b259  push    r15
0x14007b25b  sub     rsp, 48h
0x14007b25f  xor     eax, eax
0x14007b261  mov     byte ptr [r11+10h], 0
0x14007b266  mov     [r11+11h], ax
0x14007b26b  mov     ebp, r8d
0x14007b26e  mov     rsi, rdx
0x14007b271  mov     rdi, rcx
0x14007b274  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b27b  lea     r12, WPP_GLOBAL_Control
0x14007b282  lea     r13, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007b289  cmp     rcx, r12
0x14007b28c  jz      short loc_14007B29D
0x14007b28e  mov     rcx, [rcx+18h]
0x14007b292  lea     edx, [rax+39h]
0x14007b295  mov     r8, r13
0x14007b298  call    WPP_SF_
0x14007b29d  test    rsi, rsi
0x14007b2a0  jz      loc_14007B550
0x14007b2a6  cmp     ebp, 28h ; '('
0x14007b2a9  jb      loc_14007B550
0x14007b2af  test    rdi, rdi
0x14007b2b2  jz      loc_14007B550
0x14007b2b8  xor     ebx, ebx
0x14007b2ba  cmp     dword ptr [rdi+10h], 1
0x14007b2be  jnz     loc_14007B572
0x14007b2c4  mov     ecx, [rsi+8]
0x14007b2c7  mov     eax, 0FFFFFFFFh
0x14007b2cc  imul    r14, rcx, 9Ch
0x14007b2d3  cmp     r14, rax
0x14007b2d6  jbe     short loc_14007B2F7
0x14007b2d8  mov     ebx, 0C0000095h
0x14007b2dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b2e4  cmp     rcx, r12
0x14007b2e7  jz      loc_14007B592
0x14007b2ed  mov     edx, 3Bh ; ';'
0x14007b2f2  jmp     loc_14007B566
0x14007b2f7  imul    rdx, rcx, 0B4h
0x14007b2fe  cmp     rdx, rax
0x14007b301  ja      loc_14007B538
0x14007b307  mov     r8d, [rsi+0Ch]
0x14007b30b  lea     eax, [r8+rdx]
0x14007b30f  cmp     ebp, eax
0x14007b311  jnb     short loc_14007B346
0x14007b313  mov     ebx, 0C000000Dh
0x14007b318  mov     rax, cs:WPP_GLOBAL_Control
0x14007b31f  cmp     rax, r12
0x14007b322  jz      loc_14007B592
0x14007b328  mov     [rsp+88h+var_58], ecx
0x14007b32c  mov     r9d, ebp
0x14007b32f  mov     rcx, [rax+18h]
0x14007b333  mov     [rsp+88h+var_60], edx
0x14007b337  mov     [rsp+88h+var_68], r8d
0x14007b33c  call    WPP_SF_DDDDD
0x14007b341  jmp     loc_14007B572
0x14007b346  lea     eax, [r14+10h]
0x14007b34a  cmp     eax, 10h
0x14007b34d  jb      short loc_14007B3BB
0x14007b34f  mov     ecx, 40h ; '@'
0x14007b354  mov     ebp, 30327776h
0x14007b359  cmp     eax, ecx
0x14007b35b  ja      short loc_14007B366
0x14007b35d  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007b364  jmp     short loc_14007B394
0x14007b366  cmp     eax, 100h
0x14007b36b  ja      short loc_14007B376
0x14007b36d  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007b374  jmp     short loc_14007B394
0x14007b376  cmp     eax, 400h
0x14007b37b  ja      short loc_14007B386
0x14007b37d  lea     rbx, Lookaside
0x14007b384  jmp     short loc_14007B394
0x14007b386  cmp     eax, 800h
0x14007b38b  ja      short loc_14007B3A5
0x14007b38d  lea     rbx, stru_1400B31C0
0x14007b394  mov     rcx, rbx; Lookaside
0x14007b397  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007b39e  nop     dword ptr [rax+rax+00h]
0x14007b3a3  jmp     short loc_14007B3B6
0x14007b3a5  mov     edx, eax
0x14007b3a7  mov     r8d, ebp
0x14007b3aa  call    cs:__imp_ExAllocatePool2
0x14007b3b1  nop     dword ptr [rax+rax+00h]
0x14007b3b6  test    rax, rax
0x14007b3b9  jnz     short loc_14007B3DA
0x14007b3bb  mov     ebx, 0C000009Ah
0x14007b3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b3c7  cmp     rcx, r12
0x14007b3ca  jz      loc_14007B592
0x14007b3d0  mov     edx, 3Eh ; '>'
0x14007b3d5  jmp     loc_14007B566
0x14007b3da  mov     [rax+8], ebp
0x14007b3dd  xor     edx, edx; Val
0x14007b3df  lea     rbp, [rax+10h]
0x14007b3e3  mov     [rax], rbx
0x14007b3e6  mov     rcx, rbp; void *
0x14007b3e9  mov     r8d, r14d; Size
0x14007b3ec  xor     ebx, ebx
0x14007b3ee  xor     r15d, r15d
0x14007b3f1  call    memset
0x14007b3f6  mov     r8d, [rsi+0Ch]
0x14007b3fa  add     r8, rsi
0x14007b3fd  cmp     [rsi+8], ebx
0x14007b400  jbe     loc_14007B4C3
0x14007b406  mov     eax, r15d
0x14007b409  inc     r15d
0x14007b40c  imul    rdx, rax, 9Ch
0x14007b413  imul    rcx, rax, 0B4h
0x14007b41a  mov     eax, [rcx+r8]
0x14007b41e  mov     [rdx+rbp], eax
0x14007b421  mov     eax, [rcx+r8+0Ch]
0x14007b426  mov     [rdx+rbp+4], eax
0x14007b42a  mov     al, [rcx+r8+11h]
0x14007b42f  mov     [rdx+rbp+9], al
0x14007b433  mov     al, [rcx+r8+10h]
0x14007b438  mov     [rdx+rbp+8], al
0x14007b43c  movups  xmm0, xmmword ptr [rcx+r8+12h]
0x14007b442  movups  xmmword ptr [rdx+rbp+0Ah], xmm0
0x14007b447  movups  xmm1, xmmword ptr [rcx+r8+22h]
0x14007b44d  movups  xmmword ptr [rdx+rbp+1Ah], xmm1
0x14007b452  movups  xmm0, xmmword ptr [rcx+r8+32h]
0x14007b458  movups  xmmword ptr [rdx+rbp+2Ah], xmm0
0x14007b45d  movups  xmm1, xmmword ptr [rcx+r8+42h]
0x14007b463  movups  xmmword ptr [rdx+rbp+3Ah], xmm1
0x14007b468  movups  xmm0, xmmword ptr [rcx+r8+52h]
0x14007b46e  movups  xmmword ptr [rdx+rbp+4Ah], xmm0
0x14007b473  movups  xmm1, xmmword ptr [rcx+r8+62h]
0x14007b479  movups  xmmword ptr [rdx+rbp+5Ah], xmm1
0x14007b47e  movups  xmm0, xmmword ptr [rcx+r8+72h]
0x14007b484  movups  xmmword ptr [rdx+rbp+6Ah], xmm0
0x14007b489  movups  xmm1, xmmword ptr [rcx+r8+82h]
0x14007b492  movups  xmmword ptr [rdx+rbp+7Ah], xmm1
0x14007b497  movups  xmm0, xmmword ptr [rcx+r8+92h]
0x14007b4a0  movups  xmmword ptr [rdx+rbp+8Ah], xmm0
0x14007b4a8  movzx   eax, word ptr [rcx+r8+0A2h]
0x14007b4b1  mov     [rdx+rbp+9Ah], ax
0x14007b4b9  cmp     r15d, [rsi+8]
0x14007b4bd  jb      loc_14007B406
0x14007b4c3  mov     rcx, [rdi+20h]; Lock
0x14007b4c7  lea     rdx, [rsp+88h+LockState]; LockState
0x14007b4cf  xor     r8d, r8d; Flags
0x14007b4d2  call    cs:__imp_NdisAcquireRWLockWrite
0x14007b4d9  nop     dword ptr [rax+rax+00h]
0x14007b4de  mov     rsi, [rdi+38h]
0x14007b4e2  lea     rdx, [rsp+88h+LockState]; LockState
0x14007b4ea  mov     rcx, [rdi+20h]; Lock
0x14007b4ee  mov     [rdi+40h], r15d
0x14007b4f2  mov     [rdi+38h], rbp
0x14007b4f6  call    cs:__imp_NdisReleaseRWLock
0x14007b4fd  nop     dword ptr [rax+rax+00h]
0x14007b502  test    rsi, rsi
0x14007b505  jz      short loc_14007B572
0x14007b507  lea     rcx, [rsi-10h]; P
0x14007b50b  mov     rax, [rcx]
0x14007b50e  test    rax, rax
0x14007b511  jz      short loc_14007B527
0x14007b513  mov     rdx, rcx; Entry
0x14007b516  mov     rcx, rax; Lookaside
0x14007b519  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b520  nop     dword ptr [rax+rax+00h]
0x14007b525  jmp     short loc_14007B572
0x14007b527  mov     edx, [rcx+8]; Tag
0x14007b52a  call    cs:__imp_ExFreePoolWithTag
0x14007b531  nop     dword ptr [rax+rax+00h]
0x14007b536  jmp     short loc_14007B572
0x14007b538  mov     ebx, 0C0000095h
0x14007b53d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b544  cmp     rcx, r12
0x14007b547  jz      short loc_14007B592
0x14007b549  mov     edx, 3Ch ; '<'
0x14007b54e  jmp     short loc_14007B566
0x14007b550  mov     ebx, 0C000000Dh
0x14007b555  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b55c  cmp     rcx, r12
0x14007b55f  jz      short loc_14007B592
0x14007b561  mov     edx, 3Ah ; ':'
0x14007b566  mov     rcx, [rcx+18h]
0x14007b56a  mov     r8, r13
0x14007b56d  call    WPP_SF_
0x14007b572  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b579  cmp     rcx, r12
0x14007b57c  jz      short loc_14007B592
0x14007b57e  mov     rcx, [rcx+18h]
0x14007b582  mov     edx, 3Fh ; '?'
0x14007b587  mov     r9d, ebx
0x14007b58a  mov     r8, r13
0x14007b58d  call    WPP_SF_d
0x14007b592  mov     eax, ebx
0x14007b594  add     rsp, 48h
0x14007b598  pop     r15
0x14007b59a  pop     r14
0x14007b59c  pop     r13
0x14007b59e  pop     r12
0x14007b5a0  pop     rdi
0x14007b5a1  pop     rsi
0x14007b5a2  pop     rbp
0x14007b5a3  pop     rbx
0x14007b5a4  retn
```
