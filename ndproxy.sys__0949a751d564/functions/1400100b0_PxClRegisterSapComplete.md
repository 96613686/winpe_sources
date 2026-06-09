# PxClRegisterSapComplete

- ea: `0x1400100b0`
- end: `0x140010234`
- name: `PxClRegisterSapComplete`
- size: `388`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140014ca0`

## callees

- `0x140001c0c`
- `0x1400078f0`
- `0x140007c50`
- `0x14000f750`
- `0x1400100b0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010115`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001018a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010115`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001018a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001015e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010217`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001015e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010217`
- `NDIS!NdisClDeregisterSap` at `0x1400101c3`
- `NDIS!NdisClDeregisterSap` at `0x1400101c3`

## pseudocode

```c
void __fastcall PxClRegisterSapComplete(int a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  __int64 v6; // r14
  KSPIN_LOCK *v9; // rcx
  __int64 *v10; // rcx
  __int64 **v11; // rax
  bool v12; // zf
  KIRQL v13; // al
  KSPIN_LOCK *v14; // rcx
  KIRQL v15; // dl
  NDIS_STATUS v16; // eax
  KIRQL v17; // al
  __int64 v18; // rdx

  v4 = a2[4];
  v6 = a2[5];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a2, a1);
  v9 = (KSPIN_LOCK *)(v4 + 184);
  if ( a1 )
  {
    _InterlockedExchange((volatile __int32 *)a2 + 4, 0);
    *(_BYTE *)(v4 + 192) = KeAcquireSpinLockRaiseToDpc(v9);
    v10 = (__int64 *)*a2;
    if ( *(__int64 **)(*a2 + 8) != a2 || (v11 = (__int64 **)a2[1], *v11 != a2) )
      __fastfail(3u);
    *v11 = v10;
    v10[1] = (__int64)v11;
    if ( v4 )
    {
      v12 = (*(_DWORD *)(v4 + 20))-- == 1;
      if ( v12 )
        DoDerefClAfWork(v4);
      else
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 184), *(_BYTE *)(v4 + 192));
    }
    *(_QWORD *)(v6 + 64) = 0;
    PxFreeClSap(a2);
  }
  else
  {
    a2[7] = a4;
    v13 = KeAcquireSpinLockRaiseToDpc(v9);
    *(_BYTE *)(v4 + 192) = v13;
    v14 = (KSPIN_LOCK *)(v4 + 184);
    v15 = v13;
    if ( *(_DWORD *)(v4 + 16) != 3
      || (KeReleaseSpinLock(v14, v13),
          v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 120)),
          v18 = *(_QWORD *)(v6 + 80),
          v14 = (KSPIN_LOCK *)(v6 + 120),
          *(_BYTE *)(v6 + 128) = v17,
          v12 = *(_DWORD *)(v18 + 12) == 0,
          v15 = v17,
          v12) )
    {
      KeReleaseSpinLock(v14, v15);
      _InterlockedExchange((volatile __int32 *)a2 + 4, 1);
      v16 = NdisClDeregisterSap((NDIS_HANDLE)a2[7]);
      if ( v16 != 259 )
        PxClDeregisterSapComplete(v16, a2);
    }
    else
    {
      KeReleaseSpinLock(v14, v17);
      _InterlockedExchange((volatile __int32 *)a2 + 4, 3);
    }
  }
}

```

## disassembly

```asm
0x1400100b0  push    rbx
0x1400100b2  push    rbp
0x1400100b3  push    rsi
0x1400100b4  push    rdi
0x1400100b5  push    r14
0x1400100b7  push    r15
0x1400100b9  sub     rsp, 38h
0x1400100bd  mov     rdi, [rdx+20h]
0x1400100c1  mov     r15, r9
0x1400100c4  mov     r14, [rdx+28h]
0x1400100c8  mov     rbx, rdx
0x1400100cb  mov     esi, ecx
0x1400100cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400100d4  lea     rax, WPP_GLOBAL_Control
0x1400100db  cmp     rcx, rax
0x1400100de  jz      short loc_140010102
0x1400100e0  cmp     byte ptr [rcx+29h], 5
0x1400100e4  jb      short loc_140010102
0x1400100e6  mov     rcx, [rcx+18h]
0x1400100ea  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x1400100f1  mov     edx, 17h
0x1400100f6  mov     [rsp+68h+var_48], esi
0x1400100fa  mov     r9, rbx
0x1400100fd  call    WPP_SF_qD
0x140010102  lea     rbp, [rdi+0B8h]
0x140010109  mov     rcx, rbp; SpinLock
0x14001010c  test    esi, esi
0x14001010e  jz      short loc_140010186
0x140010110  xor     eax, eax
0x140010112  xchg    eax, [rbx+10h]
0x140010115  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001011c  nop     dword ptr [rax+rax+00h]
0x140010121  mov     [rdi+0C0h], al
0x140010127  mov     rcx, [rbx]
0x14001012a  cmp     [rcx+8], rbx
0x14001012e  jnz     short loc_14001017F
0x140010130  mov     rax, [rbx+8]
0x140010134  cmp     [rax], rbx
0x140010137  jnz     short loc_14001017F
0x140010139  mov     [rax], rcx
0x14001013c  mov     [rcx+8], rax
0x140010140  test    rdi, rdi
0x140010143  jz      short loc_14001016A
0x140010145  add     dword ptr [rdi+14h], 0FFFFFFFFh
0x140010149  jnz     short loc_140010155
0x14001014b  mov     rcx, rdi
0x14001014e  call    DoDerefClAfWork
0x140010153  jmp     short loc_14001016A
0x140010155  mov     dl, [rdi+0C0h]; NewIrql
0x14001015b  mov     rcx, rbp; SpinLock
0x14001015e  call    cs:__imp_KeReleaseSpinLock
0x140010165  nop     dword ptr [rax+rax+00h]
0x14001016a  mov     rcx, rbx; P
0x14001016d  mov     qword ptr [r14+40h], 0
0x140010175  call    PxFreeClSap
0x14001017a  jmp     loc_140010226
0x14001017f  mov     ecx, 3
0x140010184  int     29h; Win8: RtlFailFast(ecx)
0x140010186  mov     [rbx+38h], r15
0x14001018a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010191  nop     dword ptr [rax+rax+00h]
0x140010196  mov     esi, 3
0x14001019b  mov     [rdi+0C0h], al
0x1400101a1  mov     rcx, rbp; SpinLock
0x1400101a4  mov     dl, al; NewIrql
0x1400101a6  cmp     [rdi+10h], esi
0x1400101a9  jz      short loc_1400101E2
0x1400101ab  call    cs:__imp_KeReleaseSpinLock
0x1400101b2  nop     dword ptr [rax+rax+00h]
0x1400101b7  mov     eax, 1
0x1400101bc  xchg    eax, [rbx+10h]
0x1400101bf  mov     rcx, [rbx+38h]; NdisSapHandle
0x1400101c3  call    cs:__imp_NdisClDeregisterSap
0x1400101ca  nop     dword ptr [rax+rax+00h]
0x1400101cf  cmp     eax, 103h
0x1400101d4  jz      short loc_140010226
0x1400101d6  mov     rdx, rbx
0x1400101d9  mov     ecx, eax
0x1400101db  call    PxClDeregisterSapComplete
0x1400101e0  jmp     short loc_140010226
0x1400101e2  call    cs:__imp_KeReleaseSpinLock
0x1400101e9  nop     dword ptr [rax+rax+00h]
0x1400101ee  lea     rdi, [r14+78h]
0x1400101f2  mov     rcx, rdi; SpinLock
0x1400101f5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400101fc  nop     dword ptr [rax+rax+00h]
0x140010201  mov     rdx, [r14+50h]
0x140010205  mov     rcx, rdi; SpinLock
0x140010208  mov     [r14+80h], al
0x14001020f  cmp     dword ptr [rdx+0Ch], 0
0x140010213  mov     dl, al; NewIrql
0x140010215  jz      short loc_1400101AB
0x140010217  call    cs:__imp_KeReleaseSpinLock
0x14001021e  nop     dword ptr [rax+rax+00h]
0x140010223  xchg    esi, [rbx+10h]
0x140010226  add     rsp, 38h
0x14001022a  pop     r15
0x14001022c  pop     r14
0x14001022e  pop     rdi
0x14001022f  pop     rsi
0x140010230  pop     rbp
0x140010231  pop     rbx
0x140010232  retn
```
