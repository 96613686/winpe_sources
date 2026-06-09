# DrDeleteAllConnections(ulong)

- ea: `0x14002c9ec`
- end: `0x14002cca0`
- name: `?DrDeleteAllConnections@@YAJK@Z`
- size: `692`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c6e0`

## callees

- `0x140003ee0`
- `0x14002c9ec`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002ca19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002ca19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002cc82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002cc82`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002ca3a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002cb8f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002ca3a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002cb8f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cb4c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc1f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc68`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cb4c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc1f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc68`
- `rdbss!RxPrefixTableEndLookup` at `0x14002cbf7`
- `rdbss!RxPrefixTableEndLookup` at `0x14002cc3e`
- `rdbss!RxPrefixTableEndLookup` at `0x14002cbf7`
- `rdbss!RxPrefixTableEndLookup` at `0x14002cc3e`
- `rdbss!RxDereference` at `0x14002cbab`
- `rdbss!RxDereference` at `0x14002cbab`
- `rdbss!RxReference` at `0x14002cb09`
- `rdbss!RxReference` at `0x14002cb09`
- `rdbss!RxpTrackReference` at `0x14002cb2e`
- `rdbss!RxpTrackReference` at `0x14002cb2e`
- `rdbss!RxPrefixTableLookupNextObject` at `0x14002cbe1`
- `rdbss!RxPrefixTableLookupNextObject` at `0x14002cbe1`
- `rdbss!RxPrefixTableLookupFirstObject` at `0x14002ca76`
- `rdbss!RxPrefixTableLookupFirstObject` at `0x14002ca76`
- `rdbss!RxFinalizeConnection` at `0x14002cb69`
- `rdbss!RxFinalizeConnection` at `0x14002cb69`
- `rdbss!RxpTrackDereference` at `0x14002cbd0`
- `rdbss!RxpTrackDereference` at `0x14002cbd0`

## string_xrefs

- `0x14002cb22`: `DrDeleteAllConnections`
- `0x14002cbc4`: `DrDeleteAllConnections`

## pseudocode

```c
__int64 __fastcall DrDeleteAllConnections(int a1)
{
  unsigned int v2; // edi
  __int64 i; // rax
  __int64 v4; // rbx
  __int64 v5; // rax
  struct _NET_ROOT *v6; // r15
  _BYTE v8[96]; // [rsp+48h] [rbp-60h] BYREF

  v2 = 0;
  memset(v8, 0, 48);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)((char *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData + 24), 1u);
  for ( i = RxPrefixTableLookupFirstObject(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData, 0, 0, 60178, v8);
        ;
        i = RxPrefixTableLookupNextObject(v8) )
  {
    v4 = i;
    if ( !i )
      break;
    v5 = *(_QWORD *)(i + 40);
    if ( !v5 || *(_DWORD *)(v5 + 44) != 32 )
    {
      v6 = *(struct _NET_ROOT **)(v4 + 32);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_DZddd(
          WPP_GLOBAL_Control->AttachedDevice,
          36,
          v4 + 224,
          *(_DWORD *)(v4 + 352),
          v4 + 224,
          *(_DWORD *)(v4 + 204),
          *(_DWORD *)(v4 + 88),
          *(_BYTE *)(v4 + 192));
      if ( a1 == *(_DWORD *)(v4 + 88) )
      {
        RxReference((PVOID)v4);
        RxpTrackReference(4u, "DrDeleteAllConnections", 0x36Au, (PVOID)v4);
        ExReleaseResourceLite((PERESOURCE)((char *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData + 24));
        v2 = RxFinalizeConnection(v6, (PV_NET_ROOT)v4, 1u);
        ExAcquireResourceExclusiveLite(
          (PERESOURCE)((char *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData + 24),
          1u);
        RxDereference((PVOID)v4, LHS_ExclusiveLockHeld);
        RxpTrackDereference(4u, "DrDeleteAllConnections", 0x376u, (PVOID)v4);
      }
    }
  }
  RxPrefixTableEndLookup(v8);
  ExReleaseResourceLite((PERESOURCE)((char *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[7].DpcData + 24));
  KeLeaveCriticalRegion();
  return v2;
}

```

## disassembly

```asm
0x14002c9ec  mov     rax, rsp
0x14002c9ef  push    rbx
0x14002c9f0  push    rsi
0x14002c9f1  push    rdi
0x14002c9f2  push    r14
0x14002c9f4  push    r15
0x14002c9f6  sub     rsp, 80h
0x14002c9fd  mov     r14d, ecx
0x14002ca00  xor     edi, edi
0x14002ca02  mov     [rax-68h], dil
0x14002ca06  xorps   xmm0, xmm0
0x14002ca09  movups  xmmword ptr [rax-60h], xmm0
0x14002ca0d  movups  xmmword ptr [rax-50h], xmm0
0x14002ca11  movups  xmmword ptr [rax-40h], xmm0
0x14002ca15  mov     [rax-67h], dil
0x14002ca19  call    cs:__imp_KeEnterCriticalRegion
0x14002ca20  nop     dword ptr [rax+rax+00h]
0x14002ca25  nop
0x14002ca26  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002ca2d  mov     rcx, [rax+1F8h]
0x14002ca34  add     rcx, 18h; Resource
0x14002ca38  mov     dl, 1; Wait
0x14002ca3a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002ca41  nop     dword ptr [rax+rax+00h]
0x14002ca46  mov     sil, 1
0x14002ca49  mov     [rsp+0A8h+var_68], sil
0x14002ca4e  mov     [rsp+0A8h+var_67], sil
0x14002ca53  mov     r9d, 0EB12h
0x14002ca59  lea     rax, [rsp+0A8h+var_60]
0x14002ca5e  mov     [rsp+0A8h+var_88], rax
0x14002ca63  xor     r8d, r8d
0x14002ca66  xor     edx, edx
0x14002ca68  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002ca6f  mov     rcx, [rcx+1F8h]
0x14002ca76  call    cs:__imp_RxPrefixTableLookupFirstObject
0x14002ca7d  nop     dword ptr [rax+rax+00h]
0x14002ca82  mov     rbx, rax
0x14002ca85  test    rax, rax
0x14002ca88  jz      loc_14002CBF2
0x14002ca8e  mov     rax, [rax+28h]
0x14002ca92  test    rax, rax
0x14002ca95  jz      short loc_14002CAA2
0x14002ca97  cmp     dword ptr [rax+2Ch], 20h ; ' '
0x14002ca9b  jnz     short loc_14002CAA2
0x14002ca9d  jmp     loc_14002CBDC
0x14002caa2  mov     r15, [rbx+20h]
0x14002caa6  lea     rax, WPP_GLOBAL_Control
0x14002caad  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cab4  cmp     rcx, rax
0x14002cab7  jz      short loc_14002CAFC
0x14002cab9  cmp     byte ptr [rcx+29h], 4
0x14002cabd  jb      short loc_14002CAFC
0x14002cabf  movzx   eax, byte ptr [rbx+0C0h]
0x14002cac6  lea     r8, [rbx+0E0h]
0x14002cacd  mov     edx, 24h ; '$'
0x14002cad2  mov     [rsp+0A8h+var_70], eax
0x14002cad6  mov     eax, [rbx+58h]
0x14002cad9  mov     [rsp+0A8h+var_78], eax
0x14002cadd  mov     eax, [rbx+0CCh]
0x14002cae3  mov     [rsp+0A8h+var_80], eax
0x14002cae7  mov     [rsp+0A8h+var_88], r8
0x14002caec  mov     r9d, [rbx+160h]
0x14002caf3  mov     rcx, [rcx+18h]
0x14002caf7  call    WPP_SF_DZddd
0x14002cafc  cmp     r14d, [rbx+58h]
0x14002cb00  jnz     loc_14002CBDC
0x14002cb06  mov     rcx, rbx; Instance
0x14002cb09  call    cs:__imp_RxReference
0x14002cb10  nop     dword ptr [rax+rax+00h]
0x14002cb15  mov     dword ptr [rsp+0A8h+var_88], eax
0x14002cb19  mov     r9, rbx; Instance
0x14002cb1c  mov     r8d, 36Ah; Line
0x14002cb22  lea     rdx, FileName; "DrDeleteAllConnections"
0x14002cb29  mov     ecx, 4; TraceType
0x14002cb2e  call    cs:__imp_RxpTrackReference
0x14002cb35  nop     dword ptr [rax+rax+00h]
0x14002cb3a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002cb41  mov     rcx, [rax+1F8h]
0x14002cb48  add     rcx, 18h; Resource
0x14002cb4c  call    cs:__imp_ExReleaseResourceLite
0x14002cb53  nop     dword ptr [rax+rax+00h]
0x14002cb58  mov     [rsp+0A8h+var_68], 0
0x14002cb5d  mov     r8d, 1; ForceFilesClosed
0x14002cb63  mov     rdx, rbx; VNetRoot
0x14002cb66  mov     rcx, r15; NetRoot
0x14002cb69  call    cs:__imp_RxFinalizeConnection
0x14002cb70  nop     dword ptr [rax+rax+00h]
0x14002cb75  mov     edi, eax
0x14002cb77  mov     [rsp+0A8h+var_64], eax
0x14002cb7b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002cb82  mov     rcx, [rcx+1F8h]
0x14002cb89  add     rcx, 18h; Resource
0x14002cb8d  mov     dl, 1; Wait
0x14002cb8f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002cb96  nop     dword ptr [rax+rax+00h]
0x14002cb9b  mov     sil, 1
0x14002cb9e  mov     [rsp+0A8h+var_68], sil
0x14002cba3  mov     edx, 2; LockHoldingState
0x14002cba8  mov     rcx, rbx; Instance
0x14002cbab  call    cs:__imp_RxDereference
0x14002cbb2  nop     dword ptr [rax+rax+00h]
0x14002cbb7  mov     dword ptr [rsp+0A8h+var_88], eax
0x14002cbbb  mov     r9, rbx; Instance
0x14002cbbe  mov     r8d, 376h; Line
0x14002cbc4  lea     rdx, FileName; "DrDeleteAllConnections"
0x14002cbcb  mov     ecx, 4; TraceType
0x14002cbd0  call    cs:__imp_RxpTrackDereference
0x14002cbd7  nop     dword ptr [rax+rax+00h]
0x14002cbdc  lea     rcx, [rsp+0A8h+var_60]
0x14002cbe1  call    cs:__imp_RxPrefixTableLookupNextObject
0x14002cbe8  nop     dword ptr [rax+rax+00h]
0x14002cbed  jmp     loc_14002CA82
0x14002cbf2  lea     rcx, [rsp+0A8h+var_60]
0x14002cbf7  call    cs:__imp_RxPrefixTableEndLookup
0x14002cbfe  nop     dword ptr [rax+rax+00h]
0x14002cc03  mov     [rsp+0A8h+var_67], 0
0x14002cc08  test    sil, sil
0x14002cc0b  jz      short loc_14002CC30
0x14002cc0d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002cc14  mov     rcx, [rax+1F8h]
0x14002cc1b  add     rcx, 18h; Resource
0x14002cc1f  call    cs:__imp_ExReleaseResourceLite
0x14002cc26  nop     dword ptr [rax+rax+00h]
0x14002cc2b  mov     [rsp+0A8h+var_68], 0
0x14002cc30  jmp     short loc_14002CC82
0x14002cc32  cmp     [rsp+0A8h+var_67], 0
0x14002cc37  jz      short loc_14002CC4F
0x14002cc39  lea     rcx, [rsp+0A8h+var_60]
0x14002cc3e  call    cs:__imp_RxPrefixTableEndLookup
0x14002cc45  nop     dword ptr [rax+rax+00h]
0x14002cc4a  mov     [rsp+0A8h+var_67], 0
0x14002cc4f  cmp     [rsp+0A8h+var_68], 0
0x14002cc54  jz      short loc_14002CC79
0x14002cc56  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002cc5d  mov     rcx, [rax+1F8h]
0x14002cc64  add     rcx, 18h; Resource
0x14002cc68  call    cs:__imp_ExReleaseResourceLite
0x14002cc6f  nop     dword ptr [rax+rax+00h]
0x14002cc74  mov     [rsp+0A8h+var_68], 0
0x14002cc79  mov     edi, 0C000000Dh
0x14002cc7e  mov     [rsp+0A8h+var_64], edi
0x14002cc82  call    cs:__imp_KeLeaveCriticalRegion
0x14002cc89  nop     dword ptr [rax+rax+00h]
0x14002cc8e  mov     eax, edi
0x14002cc90  add     rsp, 80h
0x14002cc97  pop     r15
0x14002cc99  pop     r14
0x14002cc9b  pop     rdi
0x14002cc9c  pop     rsi
0x14002cc9d  pop     rbx
0x14002cc9e  retn
```
