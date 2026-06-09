# PcQueryGuidData

- ea: `0x140010360`
- end: `0x140010628`
- name: `PcQueryGuidData`
- size: `712`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400107dc`
- `0x14001f2a0`

## callees

- `0x140002594`
- `0x140010360`
- `0x14001dc8c`

## import_xrefs

- `NDIS!NdisAcquireRWLockRead` at `0x14001049a`
- `NDIS!NdisAcquireRWLockRead` at `0x1400104dc`
- `NDIS!NdisAcquireRWLockRead` at `0x14001059d`
- `NDIS!NdisAcquireRWLockRead` at `0x14001049a`
- `NDIS!NdisAcquireRWLockRead` at `0x1400104dc`
- `NDIS!NdisAcquireRWLockRead` at `0x14001059d`
- `NDIS!NdisReleaseRWLock` at `0x1400104b2`
- `NDIS!NdisReleaseRWLock` at `0x1400104f5`
- `NDIS!NdisReleaseRWLock` at `0x1400104b2`
- `NDIS!NdisReleaseRWLock` at `0x1400104f5`

## pseudocode

```c
__int64 __fastcall PcQueryGuidData(__int64 a1, unsigned __int8 *a2, unsigned int a3, __int64 a4, int a5)
{
  unsigned int DeviceExtension; // eax
  unsigned int v9; // eax
  unsigned __int64 v10; // rsi
  int v11; // eax
  int v12; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+34h] [rbp-14h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+30h] BYREF

  v13 = 0;
  v12 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( !a2 )
  {
    if ( a3 > 0xFF010103 )
    {
      if ( a3 != -16711420 )
        return 3221226205LL;
      goto LABEL_44;
    }
    if ( a3 != -16711421 )
    {
      if ( a3 <= 0xFB010109 )
      {
        switch ( a3 )
        {
          case 0xFB010109:
            *(_OWORD *)a4 = *(_OWORD *)&PcgDefaultProfile;
            return 0;
          case 0xFB010100:
            return PcpCollectNetworkAddressList(a1, (unsigned int *)&a5, (_WORD *)a4);
          case 0xFB010101:
LABEL_26:
            NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState, 0);
            v10 = *(_QWORD *)(a1 + 32);
            NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState);
            v11 = -1;
            if ( v10 <= 0xFFFFFFFF )
              v11 = v10;
            *(_DWORD *)a4 = v11;
            return 0;
          case 0xFB010103:
            *(_DWORD *)a4 = -1;
            return 0;
          case 0xFB010104:
            *(_DWORD *)a4 = -1;
            return 0;
        }
        if ( a3 != -83820282 )
        {
          if ( a3 != -83820281 )
            return 3221226205LL;
          goto LABEL_26;
        }
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState, 0);
        *(_DWORD *)a4 = *(_DWORD *)(a1 + 48);
LABEL_30:
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState);
        return 0;
      }
      if ( a3 == -83820278 )
        goto LABEL_44;
      if ( a3 == -83820277 )
      {
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState, 0);
        *(_DWORD *)a4 = 1;
        *(_DWORD *)(a4 + 4) = 28;
        *(_OWORD *)(a4 + 8) = *(_OWORD *)(a1 + 80);
        *(_OWORD *)(a4 + 20) = *(_OWORD *)(a1 + 92);
        *(_DWORD *)(a4 + 36) = 3;
        *(_DWORD *)(a4 + 40) = 4;
        *(_DWORD *)(a4 + 44) = *(_DWORD *)(a1 + 108);
        *(_DWORD *)(a4 + 48) = 4;
        *(_DWORD *)(a4 + 52) = 8;
        *(_QWORD *)(a4 + 56) = *(_QWORD *)(a1 + 112);
        *(_DWORD *)(a4 + 64) = 5;
        *(_DWORD *)(a4 + 68) = 20;
        *(_OWORD *)(a4 + 72) = 0;
        *(_DWORD *)(a4 + 88) = 0;
        goto LABEL_30;
      }
      if ( a3 != -83820275 )
      {
        if ( a3 == -83820270 )
        {
          DeviceExtension = (unsigned int)WPP_MAIN_CB.DeviceExtension;
        }
        else
        {
          if ( a3 != -83820269 )
            return 3221226205LL;
          DeviceExtension = (unsigned int)WPP_MAIN_CB.Queue.ListEntry.Flink;
        }
        goto LABEL_10;
      }
    }
LABEL_44:
    *(_DWORD *)a4 = 0;
    return 0;
  }
  if ( a3 == -83820286 )
    goto LABEL_44;
  if ( a3 == -83820283 )
  {
    v9 = a2[216];
  }
  else
  {
    if ( a3 == -83820277 )
      return PcpQueryFlowStats((_DWORD)a2, a4, a5, (unsigned int)&v13, (__int64)&v12);
    if ( a3 != -83820273 )
    {
      if ( a3 == -83820272 )
      {
        DeviceExtension = a2[218];
      }
      else
      {
        if ( a3 != -83820271 )
          return 3221226205LL;
        DeviceExtension = a2[219];
      }
      goto LABEL_10;
    }
    v9 = a2[217];
  }
  DeviceExtension = v9 >> 2;
LABEL_10:
  *(_DWORD *)a4 = DeviceExtension;
  return 0;
}

```

## disassembly

```asm
0x140010360  push    rbp
0x140010362  push    rbx
0x140010363  push    rsi
0x140010364  push    rdi
0x140010365  mov     rbp, rsp
0x140010368  sub     rsp, 48h
0x14001036c  mov     rax, rdx
0x14001036f  mov     rdi, rcx
0x140010372  xor     edx, edx
0x140010374  xor     ecx, ecx
0x140010376  mov     [rbp+var_14], edx
0x140010379  mov     rbx, r9
0x14001037c  mov     [rbp+var_18], edx
0x14001037f  mov     word ptr [rbp+LockState.OldIrql], cx
0x140010383  mov     [rbp+LockState.Flags], cl
0x140010386  test    rax, rax
0x140010389  jz      loc_140010421
0x14001038f  cmp     r8d, 0FB010102h
0x140010396  jz      loc_140010619
0x14001039c  cmp     r8d, 0FB010105h
0x1400103a3  jz      short loc_140010418
0x1400103a5  cmp     r8d, 0FB01010Bh
0x1400103ac  jz      short loc_1400103F7
0x1400103ae  cmp     r8d, 0FB01010Fh
0x1400103b5  jz      short loc_1400103EB
0x1400103b7  cmp     r8d, 0FB010110h
0x1400103be  jz      short loc_1400103E2
0x1400103c0  cmp     r8d, 0FB010111h
0x1400103c7  jz      short loc_1400103D3
0x1400103c9  mov     eax, 0C00002DDh
0x1400103ce  jmp     loc_14001061E
0x1400103d3  movzx   eax, byte ptr [rax+0DBh]
0x1400103da  mov     [r9], eax
0x1400103dd  jmp     loc_14001061C
0x1400103e2  movzx   eax, byte ptr [rax+0DAh]
0x1400103e9  jmp     short loc_1400103DA
0x1400103eb  movzx   eax, byte ptr [rax+0D9h]
0x1400103f2  shr     eax, 2
0x1400103f5  jmp     short loc_1400103DA
0x1400103f7  mov     r8d, [rbp+arg_20]
0x1400103fb  lea     rcx, [rbp+var_18]
0x1400103ff  mov     [rsp+48h+var_28], rcx
0x140010404  lea     r9, [rbp+var_14]
0x140010408  mov     rcx, rax
0x14001040b  mov     rdx, rbx
0x14001040e  call    PcpQueryFlowStats
0x140010413  jmp     loc_14001061E
0x140010418  movzx   eax, byte ptr [rax+0D8h]
0x14001041f  jmp     short loc_1400103F2
0x140010421  mov     eax, 0FF010103h
0x140010426  cmp     r8d, eax
0x140010429  ja      loc_14001060C
0x14001042f  jz      loc_140010619
0x140010435  mov     eax, 0FB010109h
0x14001043a  cmp     r8d, eax
0x14001043d  ja      loc_140010543
0x140010443  jz      loc_140010532
0x140010449  cmp     r8d, 0FB010100h
0x140010450  jz      loc_14001051E
0x140010456  cmp     r8d, 0FB010101h
0x14001045d  jz      short loc_14001048F
0x14001045f  cmp     r8d, 0FB010103h
0x140010466  jz      loc_140010512
0x14001046c  cmp     r8d, 0FB010104h
0x140010473  jz      loc_140010506
0x140010479  cmp     r8d, 0FB010106h
0x140010480  jz      short loc_1400104D1
0x140010482  cmp     r8d, 0FB010107h
0x140010489  jnz     loc_1400103C9
0x14001048f  mov     rcx, [rdi+10h]; Lock
0x140010493  lea     rdx, [rbp+LockState]; LockState
0x140010497  xor     r8d, r8d; Flags
0x14001049a  call    cs:__imp_NdisAcquireRWLockRead
0x1400104a1  nop     dword ptr [rax+rax+00h]
0x1400104a6  mov     rcx, [rdi+10h]; Lock
0x1400104aa  lea     rdx, [rbp+LockState]; LockState
0x1400104ae  mov     rsi, [rdi+20h]
0x1400104b2  call    cs:__imp_NdisReleaseRWLock
0x1400104b9  nop     dword ptr [rax+rax+00h]
0x1400104be  mov     eax, 0FFFFFFFFh
0x1400104c3  cmp     rsi, rax
0x1400104c6  ja      short loc_1400104CA
0x1400104c8  mov     eax, esi
0x1400104ca  mov     [rbx], eax
0x1400104cc  jmp     loc_14001061C
0x1400104d1  mov     rcx, [rdi+10h]; Lock
0x1400104d5  lea     rdx, [rbp+LockState]; LockState
0x1400104d9  xor     r8d, r8d; Flags
0x1400104dc  call    cs:__imp_NdisAcquireRWLockRead
0x1400104e3  nop     dword ptr [rax+rax+00h]
0x1400104e8  mov     eax, [rdi+30h]
0x1400104eb  mov     [rbx], eax
0x1400104ed  mov     rcx, [rdi+10h]; Lock
0x1400104f1  lea     rdx, [rbp+LockState]; LockState
0x1400104f5  call    cs:__imp_NdisReleaseRWLock
0x1400104fc  nop     dword ptr [rax+rax+00h]
0x140010501  jmp     loc_14001061C
0x140010506  mov     dword ptr [r9], 0FFFFFFFFh
0x14001050d  jmp     loc_14001061C
0x140010512  mov     dword ptr [r9], 0FFFFFFFFh
0x140010519  jmp     loc_14001061C
0x14001051e  mov     r8, rbx
0x140010521  lea     rdx, [rbp+arg_20]
0x140010525  mov     rcx, rdi
0x140010528  call    PcpCollectNetworkAddressList
0x14001052d  jmp     loc_14001061E
0x140010532  movups  xmm0, xmmword ptr cs:PcgDefaultProfile
0x140010539  movdqu  xmmword ptr [r9], xmm0
0x14001053e  jmp     loc_14001061C
0x140010543  cmp     r8d, 0FB01010Ah
0x14001054a  jz      loc_140010619
0x140010550  cmp     r8d, 0FB01010Bh
0x140010557  jz      short loc_140010592
0x140010559  cmp     r8d, 0FB01010Dh
0x140010560  jz      loc_140010619
0x140010566  cmp     r8d, 0FB010112h
0x14001056d  jz      short loc_140010587
0x14001056f  cmp     r8d, 0FB010113h
0x140010576  jnz     loc_1400103C9
0x14001057c  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x140010582  jmp     loc_1400103DA
0x140010587  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceExtension
0x14001058d  jmp     loc_1400103DA
0x140010592  mov     rcx, [rdi+10h]; Lock
0x140010596  lea     rdx, [rbp+LockState]; LockState
0x14001059a  xor     r8d, r8d; Flags
0x14001059d  call    cs:__imp_NdisAcquireRWLockRead
0x1400105a4  nop     dword ptr [rax+rax+00h]
0x1400105a9  mov     dword ptr [rbx], 1
0x1400105af  mov     ecx, 4
0x1400105b4  mov     dword ptr [rbx+4], 1Ch
0x1400105bb  movups  xmm0, xmmword ptr [rdi+50h]
0x1400105bf  movups  xmmword ptr [rbx+8], xmm0
0x1400105c3  movups  xmm1, xmmword ptr [rdi+5Ch]
0x1400105c7  xorps   xmm0, xmm0
0x1400105ca  movups  xmmword ptr [rbx+14h], xmm1
0x1400105ce  mov     dword ptr [rbx+24h], 3
0x1400105d5  mov     [rbx+28h], ecx
0x1400105d8  mov     eax, [rdi+6Ch]
0x1400105db  mov     [rbx+2Ch], eax
0x1400105de  mov     [rbx+30h], ecx
0x1400105e1  mov     dword ptr [rbx+34h], 8
0x1400105e8  mov     rax, [rdi+70h]
0x1400105ec  mov     [rbx+38h], rax
0x1400105f0  xor     eax, eax
0x1400105f2  mov     dword ptr [rbx+40h], 5
0x1400105f9  mov     dword ptr [rbx+44h], 14h
0x140010600  movups  xmmword ptr [rbx+48h], xmm0
0x140010604  mov     [rbx+58h], eax
0x140010607  jmp     loc_1400104ED
0x14001060c  cmp     r8d, 0FF010104h
0x140010613  jnz     loc_1400103C9
0x140010619  mov     [r9], edx
0x14001061c  xor     eax, eax
0x14001061e  add     rsp, 48h
0x140010622  pop     rdi
0x140010623  pop     rsi
0x140010624  pop     rbx
0x140010625  pop     rbp
0x140010626  retn
```
