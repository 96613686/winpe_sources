# PcQuerySetMiniport

- ea: `0x140010630`
- end: `0x1400107d5`
- name: `PcQuerySetMiniport`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001f2a0`

## callees

- `0x140010630`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x1400107ad`
- `NDIS!NdisReleaseRWLock` at `0x1400107ad`
- `NDIS!NdisAcquireRWLockWrite` at `0x140010784`
- `NDIS!NdisAcquireRWLockWrite` at `0x140010784`

## pseudocode

```c
__int64 __fastcall PcQuerySetMiniport(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, int a5)
{
  bool v6; // zf
  __int64 result; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+18h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( a3 > 0xFB010108 )
  {
    if ( a3 == -83820279 || a3 == -83820278 || a3 == -16711421 )
      return 3221226205LL;
    v6 = a3 == -16711420;
  }
  else
  {
    if ( a3 == -83820280 || a3 == -83820288 || a3 == -83820287 || a3 == -83820284 || a3 == -83820282 )
      return 3221226205LL;
    v6 = a3 == -83820281;
  }
  if ( !v6 )
  {
    if ( a2 )
    {
      if ( a3 == -83820277 )
      {
        result = 0;
        *(_OWORD *)(a2 + 140) = 0;
        *(_OWORD *)(a2 + 152) = 0;
        *(_DWORD *)(a2 + 308) = 0;
        *(_QWORD *)(a2 + 312) = 0;
        return result;
      }
      return 3221226205LL;
    }
    switch ( a3 )
    {
      case 0xFB010103:
        if ( a5 != 4 )
          return 3221225507LL;
        break;
      case 0xFB01010B:
        NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState, 0);
        *(_OWORD *)(a1 + 80) = 0;
        *(_OWORD *)(a1 + 92) = 0;
        *(_DWORD *)(a1 + 108) = 0;
        *(_QWORD *)(a1 + 112) = 0;
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState);
        return 0;
      case 0xFB01010D:
        if ( a5 == 4 )
        {
          if ( *a4 != 1 )
            return *a4 != 2 ? 0xC000000D : 0;
          return 0;
        }
        return 3221225507LL;
      case 0xFB010112:
        if ( a5 == 4 )
        {
          LODWORD(WPP_MAIN_CB.DeviceExtension) = *a4;
          return 0;
        }
        return 3221225507LL;
      case 0xFB010113:
        if ( a5 == 4 )
        {
          LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink) = *a4;
          return 0;
        }
        return 3221225507LL;
    }
  }
  return 3221226205LL;
}

```

## disassembly

```asm
0x140010630  push    rbx
0x140010632  sub     rsp, 20h
0x140010636  xor     eax, eax
0x140010638  mov     rbx, rcx
0x14001063b  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140010640  mov     [rsp+28h+LockState.Flags], al
0x140010644  mov     eax, 0FB010108h
0x140010649  cmp     r8d, eax
0x14001064c  ja      short loc_140010691
0x14001064e  jz      loc_1400107C9
0x140010654  cmp     r8d, 0FB010100h
0x14001065b  jz      loc_1400107C9
0x140010661  cmp     r8d, 0FB010101h
0x140010668  jz      loc_1400107C9
0x14001066e  cmp     r8d, 0FB010104h
0x140010675  jz      loc_1400107C9
0x14001067b  cmp     r8d, 0FB010106h
0x140010682  jz      loc_1400107C9
0x140010688  cmp     r8d, 0FB010107h
0x14001068f  jmp     short loc_1400106BF
0x140010691  cmp     r8d, 0FB010109h
0x140010698  jz      loc_1400107C9
0x14001069e  cmp     r8d, 0FB01010Ah
0x1400106a5  jz      loc_1400107C9
0x1400106ab  cmp     r8d, 0FF010103h
0x1400106b2  jz      loc_1400107C9
0x1400106b8  cmp     r8d, 0FF010104h
0x1400106bf  jz      loc_1400107C9
0x1400106c5  test    rdx, rdx
0x1400106c8  jz      short loc_1400106FC
0x1400106ca  cmp     r8d, 0FB01010Bh
0x1400106d1  jnz     loc_1400107C9
0x1400106d7  xorps   xmm0, xmm0
0x1400106da  xor     eax, eax
0x1400106dc  movups  xmmword ptr [rdx+8Ch], xmm0
0x1400106e3  movups  xmmword ptr [rdx+98h], xmm0
0x1400106ea  mov     [rdx+134h], eax
0x1400106f0  mov     [rdx+138h], rax
0x1400106f7  jmp     loc_1400107CE
0x1400106fc  cmp     r8d, 0FB010103h
0x140010703  jz      loc_1400107BB
0x140010709  cmp     r8d, 0FB01010Bh
0x140010710  jz      short loc_140010778
0x140010712  cmp     r8d, 0FB01010Dh
0x140010719  jz      short loc_14001075B
0x14001071b  cmp     r8d, 0FB010112h
0x140010722  jz      short loc_140010747
0x140010724  cmp     r8d, 0FB010113h
0x14001072b  jnz     loc_1400107C9
0x140010731  cmp     [rsp+28h+arg_20], 4
0x140010736  jnz     loc_1400107C2
0x14001073c  mov     eax, [r9]
0x14001073f  mov     dword ptr cs:WPP_MAIN_CB.Queue, eax
0x140010745  jmp     short loc_140010757
0x140010747  cmp     [rsp+28h+arg_20], 4
0x14001074c  jnz     short loc_1400107C2
0x14001074e  mov     eax, [r9]
0x140010751  mov     dword ptr cs:WPP_MAIN_CB.DeviceExtension, eax
0x140010757  xor     eax, eax
0x140010759  jmp     short loc_1400107CE
0x14001075b  cmp     [rsp+28h+arg_20], 4
0x140010760  jnz     short loc_1400107C2
0x140010762  mov     eax, [r9]
0x140010765  cmp     eax, 1
0x140010768  jz      short loc_140010757
0x14001076a  sub     eax, 2
0x14001076d  neg     eax
0x14001076f  sbb     eax, eax
0x140010771  and     eax, 0C000000Dh
0x140010776  jmp     short loc_1400107CE
0x140010778  mov     rcx, [rcx+10h]; Lock
0x14001077c  lea     rdx, [rsp+28h+LockState]; LockState
0x140010781  xor     r8d, r8d; Flags
0x140010784  call    cs:__imp_NdisAcquireRWLockWrite
0x14001078b  nop     dword ptr [rax+rax+00h]
0x140010790  xorps   xmm0, xmm0
0x140010793  lea     rdx, [rsp+28h+LockState]; LockState
0x140010798  movups  xmmword ptr [rbx+50h], xmm0
0x14001079c  xor     eax, eax
0x14001079e  movups  xmmword ptr [rbx+5Ch], xmm0
0x1400107a2  mov     [rbx+6Ch], eax
0x1400107a5  mov     [rbx+70h], rax
0x1400107a9  mov     rcx, [rbx+10h]; Lock
0x1400107ad  call    cs:__imp_NdisReleaseRWLock
0x1400107b4  nop     dword ptr [rax+rax+00h]
0x1400107b9  jmp     short loc_140010757
0x1400107bb  cmp     [rsp+28h+arg_20], 4
0x1400107c0  jz      short loc_1400107C9
0x1400107c2  mov     eax, 0C0000023h
0x1400107c7  jmp     short loc_1400107CE
0x1400107c9  mov     eax, 0C00002DDh
0x1400107ce  add     rsp, 20h
0x1400107d2  pop     rbx
0x1400107d3  retn
```
