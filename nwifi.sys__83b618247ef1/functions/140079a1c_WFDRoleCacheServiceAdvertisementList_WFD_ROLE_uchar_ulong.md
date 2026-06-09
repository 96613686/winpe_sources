# WFDRoleCacheServiceAdvertisementList(_WFD_ROLE *,uchar *,ulong)

- ea: `0x140079a1c`
- end: `0x140079d76`
- name: `?WFDRoleCacheServiceAdvertisementList@@YAHPEAU_WFD_ROLE@@PEAEK@Z`
- size: `858`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, unsigned __int8 *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x14007b340`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140079a1c`
- `0x14007ca5c`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079b67`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079b67`
- `ntoskrnl!ExAllocatePool2` at `0x140079b7a`
- `ntoskrnl!ExAllocatePool2` at `0x140079b7a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079ce9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079ce9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079cfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079cfa`
- `NDIS!NdisAcquireRWLockWrite` at `0x140079ca2`
- `NDIS!NdisAcquireRWLockWrite` at `0x140079ca2`
- `NDIS!NdisReleaseRWLock` at `0x140079cc6`
- `NDIS!NdisReleaseRWLock` at `0x140079cc6`

## pseudocode

```c
__int64 __fastcall WFDRoleCacheServiceAdvertisementList(
        struct _WFD_ROLE *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        __int64 a4)
{
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  __int64 v8; // rcx
  unsigned int v9; // r14d
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  char *Pool2; // rax
  _WFDSVC_SERVICE_ADVERTISEMENT_ENTRY *v16; // rbp
  unsigned int v17; // r15d
  unsigned __int8 *v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdx
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
    v8 = *((unsigned int *)a2 + 2);
    v9 = 156 * v8;
    if ( (unsigned __int64)(156 * v8) > 0xFFFFFFFF )
    {
      LODWORD(p_WaitListHead) = -1073741675;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)p_WaitListHead;
      v11 = 59;
      goto LABEL_38;
    }
    v12 = 180 * v8;
    if ( (unsigned __int64)(180 * v8) <= 0xFFFFFFFF )
    {
      v13 = *((unsigned int *)a2 + 3);
      if ( a3 < (int)v13 + (int)v12 )
      {
        LODWORD(p_WaitListHead) = -1073741811;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)p_WaitListHead;
        WPP_SF_DDDDD(WPP_GLOBAL_Control->AttachedDevice, v12, v13, a3, v13, v12, v8);
        goto LABEL_39;
      }
      v14 = v9 + 16;
      if ( v9 >= 0xFFFFFFF0 )
      {
LABEL_26:
        LODWORD(p_WaitListHead) = -1073741670;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)p_WaitListHead;
        v11 = 62;
        goto LABEL_38;
      }
      if ( v14 > 0x40 )
      {
        if ( v14 > 0x100 )
        {
          if ( v14 > 0x400 )
          {
            if ( v14 > 0x800 )
            {
              Pool2 = (char *)ExAllocatePool2(64, v14, 808613750, a4);
LABEL_25:
              if ( Pool2 )
              {
                *((_DWORD *)Pool2 + 2) = 808613750;
                v16 = (_WFDSVC_SERVICE_ADVERTISEMENT_ENTRY *)(Pool2 + 16);
                *(_QWORD *)Pool2 = p_WaitListHead;
                LODWORD(p_WaitListHead) = 0;
                v17 = 0;
                memset(Pool2 + 16, 0, v9);
                v18 = &a2[*((unsigned int *)a2 + 3)];
                if ( *((_DWORD *)a2 + 2) )
                {
                  do
                  {
                    v19 = v17++;
                    v20 = v19;
                    v16[v20].AdvertisementID = *(_DWORD *)&v18[180 * v19];
                    v16[v20].ConfigMethods = *(_DWORD *)&v18[180 * v19 + 12];
                    v16[v20].bAutoAccept = v18[180 * v19 + 17];
                    v16[v20].ServiceStatus = v18[180 * v19 + 16];
                    *(_OWORD *)&v16[v20].SessionInfo.uSessionInfoLength = *(_OWORD *)&v18[180 * v19 + 18];
                    *(_OWORD *)&v16[v20].SessionInfo.ucSessionInfo[14] = *(_OWORD *)&v18[180 * v19 + 34];
                    *(_OWORD *)&v16[v20].SessionInfo.ucSessionInfo[30] = *(_OWORD *)&v18[180 * v19 + 50];
                    *(_OWORD *)&v16[v20].SessionInfo.ucSessionInfo[46] = *(_OWORD *)&v18[180 * v19 + 66];
                    *(_OWORD *)&v16[v20].SessionInfo.ucSessionInfo[62] = *(_OWORD *)&v18[180 * v19 + 82];
                    *(_OWORD *)&v16[v20].SessionInfo.ucSessionInfo[78] = *(_OWORD *)&v18[180 * v19 + 98];
                    *(_OWORD *)&v16[v20].SessionInfo.ucSessionInfo[94] = *(_OWORD *)&v18[180 * v19 + 114];
                    *(_OWORD *)&v16[v20].SessionInfo.ucSessionInfo[110] = *(_OWORD *)&v18[180 * v19 + 130];
                    *(_OWORD *)&v16[v20].SessionInfo.ucSessionInfo[126] = *(_OWORD *)&v18[180 * v19 + 146];
                    *(_WORD *)&v16[v20].SessionInfo.ucSessionInfo[142] = *(_WORD *)&v18[180 * v19 + 162];
                  }
                  while ( v17 < *((_DWORD *)a2 + 2) );
                }
                NdisAcquireRWLockWrite(a1->pRWLock, &LockState, 0);
                pCachedServiceAdvertisementList = a1->pCachedServiceAdvertisementList;
                pRWLock = a1->pRWLock;
                a1->uCachedServiceAdvertisementCount = v17;
                a1->pCachedServiceAdvertisementList = v16;
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
            p_WaitListHead = &stru_1400B0180;
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
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)p_WaitListHead;
    v11 = 60;
  }
  else
  {
    LODWORD(p_WaitListHead) = -1073741811;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)p_WaitListHead;
    v11 = 58;
  }
LABEL_38:
  WPP_SF_(v10->AttachedDevice, v11, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
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
0x140079a1c  mov     r11, rsp
0x140079a1f  push    rbx
0x140079a20  push    rbp
0x140079a21  push    rsi
0x140079a22  push    rdi
0x140079a23  push    r12
0x140079a25  push    r13
0x140079a27  push    r14
0x140079a29  push    r15
0x140079a2b  sub     rsp, 48h
0x140079a2f  xor     eax, eax
0x140079a31  mov     byte ptr [r11+10h], 0
0x140079a36  mov     [r11+11h], ax
0x140079a3b  mov     ebp, r8d
0x140079a3e  mov     rsi, rdx
0x140079a41  mov     rdi, rcx
0x140079a44  mov     rcx, cs:WPP_GLOBAL_Control
0x140079a4b  lea     r12, WPP_GLOBAL_Control
0x140079a52  lea     r13, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079a59  cmp     rcx, r12
0x140079a5c  jz      short loc_140079A6D
0x140079a5e  mov     rcx, [rcx+18h]
0x140079a62  lea     edx, [rax+39h]
0x140079a65  mov     r8, r13
0x140079a68  call    WPP_SF_
0x140079a6d  test    rsi, rsi
0x140079a70  jz      loc_140079D20
0x140079a76  cmp     ebp, 28h ; '('
0x140079a79  jb      loc_140079D20
0x140079a7f  test    rdi, rdi
0x140079a82  jz      loc_140079D20
0x140079a88  xor     ebx, ebx
0x140079a8a  cmp     dword ptr [rdi+10h], 1
0x140079a8e  jnz     loc_140079D42
0x140079a94  mov     ecx, [rsi+8]
0x140079a97  mov     eax, 0FFFFFFFFh
0x140079a9c  imul    r14, rcx, 9Ch
0x140079aa3  cmp     r14, rax
0x140079aa6  jbe     short loc_140079AC7
0x140079aa8  mov     ebx, 0C0000095h
0x140079aad  mov     rcx, cs:WPP_GLOBAL_Control
0x140079ab4  cmp     rcx, r12
0x140079ab7  jz      loc_140079D62
0x140079abd  mov     edx, 3Bh ; ';'
0x140079ac2  jmp     loc_140079D36
0x140079ac7  imul    rdx, rcx, 0B4h
0x140079ace  cmp     rdx, rax
0x140079ad1  ja      loc_140079D08
0x140079ad7  mov     r8d, [rsi+0Ch]
0x140079adb  lea     eax, [r8+rdx]
0x140079adf  cmp     ebp, eax
0x140079ae1  jnb     short loc_140079B16
0x140079ae3  mov     ebx, 0C000000Dh
0x140079ae8  mov     rax, cs:WPP_GLOBAL_Control
0x140079aef  cmp     rax, r12
0x140079af2  jz      loc_140079D62
0x140079af8  mov     [rsp+88h+var_58], ecx
0x140079afc  mov     r9d, ebp
0x140079aff  mov     rcx, [rax+18h]
0x140079b03  mov     [rsp+88h+var_60], edx
0x140079b07  mov     [rsp+88h+var_68], r8d
0x140079b0c  call    WPP_SF_DDDDD
0x140079b11  jmp     loc_140079D42
0x140079b16  lea     eax, [r14+10h]
0x140079b1a  cmp     eax, 10h
0x140079b1d  jb      short loc_140079B8B
0x140079b1f  mov     ecx, 40h ; '@'
0x140079b24  mov     ebp, 30327776h
0x140079b29  cmp     eax, ecx
0x140079b2b  ja      short loc_140079B36
0x140079b2d  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140079b34  jmp     short loc_140079B64
0x140079b36  cmp     eax, 100h
0x140079b3b  ja      short loc_140079B46
0x140079b3d  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140079b44  jmp     short loc_140079B64
0x140079b46  cmp     eax, 400h
0x140079b4b  ja      short loc_140079B56
0x140079b4d  lea     rbx, Lookaside
0x140079b54  jmp     short loc_140079B64
0x140079b56  cmp     eax, 800h
0x140079b5b  ja      short loc_140079B75
0x140079b5d  lea     rbx, stru_1400B0180
0x140079b64  mov     rcx, rbx; Lookaside
0x140079b67  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140079b6e  nop     dword ptr [rax+rax+00h]
0x140079b73  jmp     short loc_140079B86
0x140079b75  mov     edx, eax
0x140079b77  mov     r8d, ebp
0x140079b7a  call    cs:__imp_ExAllocatePool2
0x140079b81  nop     dword ptr [rax+rax+00h]
0x140079b86  test    rax, rax
0x140079b89  jnz     short loc_140079BAA
0x140079b8b  mov     ebx, 0C000009Ah
0x140079b90  mov     rcx, cs:WPP_GLOBAL_Control
0x140079b97  cmp     rcx, r12
0x140079b9a  jz      loc_140079D62
0x140079ba0  mov     edx, 3Eh ; '>'
0x140079ba5  jmp     loc_140079D36
0x140079baa  mov     [rax+8], ebp
0x140079bad  xor     edx, edx; Val
0x140079baf  lea     rbp, [rax+10h]
0x140079bb3  mov     [rax], rbx
0x140079bb6  mov     rcx, rbp; void *
0x140079bb9  mov     r8d, r14d; Size
0x140079bbc  xor     ebx, ebx
0x140079bbe  xor     r15d, r15d
0x140079bc1  call    memset
0x140079bc6  mov     r8d, [rsi+0Ch]
0x140079bca  add     r8, rsi
0x140079bcd  cmp     [rsi+8], ebx
0x140079bd0  jbe     loc_140079C93
0x140079bd6  mov     eax, r15d
0x140079bd9  inc     r15d
0x140079bdc  imul    rdx, rax, 9Ch
0x140079be3  imul    rcx, rax, 0B4h
0x140079bea  mov     eax, [rcx+r8]
0x140079bee  mov     [rdx+rbp], eax
0x140079bf1  mov     eax, [rcx+r8+0Ch]
0x140079bf6  mov     [rdx+rbp+4], eax
0x140079bfa  mov     al, [rcx+r8+11h]
0x140079bff  mov     [rdx+rbp+9], al
0x140079c03  mov     al, [rcx+r8+10h]
0x140079c08  mov     [rdx+rbp+8], al
0x140079c0c  movups  xmm0, xmmword ptr [rcx+r8+12h]
0x140079c12  movups  xmmword ptr [rdx+rbp+0Ah], xmm0
0x140079c17  movups  xmm1, xmmword ptr [rcx+r8+22h]
0x140079c1d  movups  xmmword ptr [rdx+rbp+1Ah], xmm1
0x140079c22  movups  xmm0, xmmword ptr [rcx+r8+32h]
0x140079c28  movups  xmmword ptr [rdx+rbp+2Ah], xmm0
0x140079c2d  movups  xmm1, xmmword ptr [rcx+r8+42h]
0x140079c33  movups  xmmword ptr [rdx+rbp+3Ah], xmm1
0x140079c38  movups  xmm0, xmmword ptr [rcx+r8+52h]
0x140079c3e  movups  xmmword ptr [rdx+rbp+4Ah], xmm0
0x140079c43  movups  xmm1, xmmword ptr [rcx+r8+62h]
0x140079c49  movups  xmmword ptr [rdx+rbp+5Ah], xmm1
0x140079c4e  movups  xmm0, xmmword ptr [rcx+r8+72h]
0x140079c54  movups  xmmword ptr [rdx+rbp+6Ah], xmm0
0x140079c59  movups  xmm1, xmmword ptr [rcx+r8+82h]
0x140079c62  movups  xmmword ptr [rdx+rbp+7Ah], xmm1
0x140079c67  movups  xmm0, xmmword ptr [rcx+r8+92h]
0x140079c70  movups  xmmword ptr [rdx+rbp+8Ah], xmm0
0x140079c78  movzx   eax, word ptr [rcx+r8+0A2h]
0x140079c81  mov     [rdx+rbp+9Ah], ax
0x140079c89  cmp     r15d, [rsi+8]
0x140079c8d  jb      loc_140079BD6
0x140079c93  mov     rcx, [rdi+20h]; Lock
0x140079c97  lea     rdx, [rsp+88h+LockState]; LockState
0x140079c9f  xor     r8d, r8d; Flags
0x140079ca2  call    cs:__imp_NdisAcquireRWLockWrite
0x140079ca9  nop     dword ptr [rax+rax+00h]
0x140079cae  mov     rsi, [rdi+38h]
0x140079cb2  lea     rdx, [rsp+88h+LockState]; LockState
0x140079cba  mov     rcx, [rdi+20h]; Lock
0x140079cbe  mov     [rdi+40h], r15d
0x140079cc2  mov     [rdi+38h], rbp
0x140079cc6  call    cs:__imp_NdisReleaseRWLock
0x140079ccd  nop     dword ptr [rax+rax+00h]
0x140079cd2  test    rsi, rsi
0x140079cd5  jz      short loc_140079D42
0x140079cd7  lea     rcx, [rsi-10h]; P
0x140079cdb  mov     rax, [rcx]
0x140079cde  test    rax, rax
0x140079ce1  jz      short loc_140079CF7
0x140079ce3  mov     rdx, rcx; Entry
0x140079ce6  mov     rcx, rax; Lookaside
0x140079ce9  call    cs:__imp_ExFreeToNPagedLookasideList
0x140079cf0  nop     dword ptr [rax+rax+00h]
0x140079cf5  jmp     short loc_140079D42
0x140079cf7  mov     edx, [rcx+8]; Tag
0x140079cfa  call    cs:__imp_ExFreePoolWithTag
0x140079d01  nop     dword ptr [rax+rax+00h]
0x140079d06  jmp     short loc_140079D42
0x140079d08  mov     ebx, 0C0000095h
0x140079d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d14  cmp     rcx, r12
0x140079d17  jz      short loc_140079D62
0x140079d19  mov     edx, 3Ch ; '<'
0x140079d1e  jmp     short loc_140079D36
0x140079d20  mov     ebx, 0C000000Dh
0x140079d25  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d2c  cmp     rcx, r12
0x140079d2f  jz      short loc_140079D62
0x140079d31  mov     edx, 3Ah ; ':'
0x140079d36  mov     rcx, [rcx+18h]
0x140079d3a  mov     r8, r13
0x140079d3d  call    WPP_SF_
0x140079d42  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d49  cmp     rcx, r12
0x140079d4c  jz      short loc_140079D62
0x140079d4e  mov     rcx, [rcx+18h]
0x140079d52  mov     edx, 3Fh ; '?'
0x140079d57  mov     r9d, ebx
0x140079d5a  mov     r8, r13
0x140079d5d  call    WPP_SF_d
0x140079d62  mov     eax, ebx
0x140079d64  add     rsp, 48h
0x140079d68  pop     r15
0x140079d6a  pop     r14
0x140079d6c  pop     r13
0x140079d6e  pop     r12
0x140079d70  pop     rdi
0x140079d71  pop     rsi
0x140079d72  pop     rbp
0x140079d73  pop     rbx
0x140079d74  retn
```
