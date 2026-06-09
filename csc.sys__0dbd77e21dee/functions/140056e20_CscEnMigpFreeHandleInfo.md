# CscEnMigpFreeHandleInfo

- ea: `0x140056e20`
- end: `0x140056f7c`
- name: `CscEnMigpFreeHandleInfo`
- size: `348`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140055f18`

## callees

- `0x140016a04`
- `0x140018930`
- `0x1400190ec`
- `0x140056e20`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140056f30`
- `ntoskrnl!ExReleaseResourceLite` at `0x140056f30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056eed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056eed`
- `ntoskrnl!ExDeleteResourceLite` at `0x140056f0e`
- `ntoskrnl!ExDeleteResourceLite` at `0x140056f0e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140056e6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140056e6f`

## pseudocode

```c
__int64 __fastcall CscEnMigpFreeHandleInfo(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // edi
  int v5; // esi
  void *v6; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_296f452431843577cb3e1b6de981fe55_Traceguids, a1);
  ExAcquireResourceExclusiveLite(&CscEnImportpState, 1u);
  *a2 = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 4), 0, 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_296f452431843577cb3e1b6de981fe55_Traceguids,
        *(unsigned int *)(a1 + 4));
    }
    v4 = -1073741816;
    v5 = 1388;
  }
  else if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    v6 = *(void **)(a1 + 144);
    v4 = 0;
    v5 = 0;
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0x21407343u);
      *(_QWORD *)(a1 + 144) = 0;
    }
    *a2 = *(_QWORD *)(a1 + 136);
    ExDeleteResourceLite((PERESOURCE)(a1 + 32));
    *(_BYTE *)a1 &= ~1u;
    --word_14003BF48;
  }
  else
  {
    v4 = -1073740768;
    v5 = 1395;
  }
  ExReleaseResourceLite(&CscEnImportpState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_296f452431843577cb3e1b6de981fe55_Traceguids, v4, v5);
  return v4;
}

```

## disassembly

```asm
0x140056e20  push    rbx
0x140056e22  push    rsi
0x140056e23  push    rdi
0x140056e24  push    r14
0x140056e26  push    r15
0x140056e28  sub     rsp, 30h
0x140056e2c  mov     r14, rdx
0x140056e2f  mov     rbx, rcx
0x140056e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140056e39  lea     r15, WPP_GLOBAL_Control
0x140056e40  cmp     rcx, r15
0x140056e43  jz      short loc_140056E66
0x140056e45  test    dword ptr [rcx+2Ch], 20000h
0x140056e4c  jz      short loc_140056E66
0x140056e4e  mov     rcx, [rcx+18h]
0x140056e52  lea     r8, WPP_296f452431843577cb3e1b6de981fe55_Traceguids
0x140056e59  mov     edx, 19h
0x140056e5e  mov     r9, rbx
0x140056e61  call    WPP_SF_q
0x140056e66  mov     dl, 1; Wait
0x140056e68  lea     rcx, CscEnImportpState; Resource
0x140056e6f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140056e76  nop     dword ptr [rax+rax+00h]
0x140056e7b  xor     ecx, ecx
0x140056e7d  mov     qword ptr [r14], 0
0x140056e84  xor     eax, eax
0x140056e86  lock cmpxchg [rbx+4], ecx
0x140056e8b  jz      short loc_140056EC7
0x140056e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140056e94  cmp     rcx, r15
0x140056e97  jz      short loc_140056EBB
0x140056e99  test    dword ptr [rcx+2Ch], 20000h
0x140056ea0  jz      short loc_140056EBB
0x140056ea2  mov     r9d, [rbx+4]
0x140056ea6  lea     r8, WPP_296f452431843577cb3e1b6de981fe55_Traceguids
0x140056ead  mov     rcx, [rcx+18h]
0x140056eb1  mov     edx, 1Ah
0x140056eb6  call    WPP_SF_d
0x140056ebb  mov     edi, 0C0000008h
0x140056ec0  mov     esi, 56Ch
0x140056ec5  jmp     short loc_140056F29
0x140056ec7  test    byte ptr [rbx], 1
0x140056eca  jnz     short loc_140056ED8
0x140056ecc  mov     edi, 0C0000420h
0x140056ed1  mov     esi, 573h
0x140056ed6  jmp     short loc_140056F29
0x140056ed8  mov     rcx, [rbx+90h]; P
0x140056edf  xor     edi, edi
0x140056ee1  xor     esi, esi
0x140056ee3  test    rcx, rcx
0x140056ee6  jz      short loc_140056F00
0x140056ee8  mov     edx, 21407343h; Tag
0x140056eed  call    cs:__imp_ExFreePoolWithTag
0x140056ef4  nop     dword ptr [rax+rax+00h]
0x140056ef9  mov     [rbx+90h], rsi
0x140056f00  mov     rax, [rbx+88h]
0x140056f07  lea     rcx, [rbx+20h]; Resource
0x140056f0b  mov     [r14], rax
0x140056f0e  call    cs:__imp_ExDeleteResourceLite
0x140056f15  nop     dword ptr [rax+rax+00h]
0x140056f1a  and     byte ptr [rbx], 0FEh
0x140056f1d  mov     eax, 0FFFFh
0x140056f22  add     cs:word_14003BF48, ax
0x140056f29  lea     rcx, CscEnImportpState; Resource
0x140056f30  call    cs:__imp_ExReleaseResourceLite
0x140056f37  nop     dword ptr [rax+rax+00h]
0x140056f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056f43  cmp     rcx, r15
0x140056f46  jz      short loc_140056F6D
0x140056f48  test    dword ptr [rcx+2Ch], 20000h
0x140056f4f  jz      short loc_140056F6D
0x140056f51  mov     rcx, [rcx+18h]
0x140056f55  lea     r8, WPP_296f452431843577cb3e1b6de981fe55_Traceguids
0x140056f5c  mov     edx, 1Bh
0x140056f61  mov     [rsp+58h+var_38], esi
0x140056f65  mov     r9d, edi
0x140056f68  call    WPP_SF_Dd
0x140056f6d  mov     eax, edi
0x140056f6f  add     rsp, 30h
0x140056f73  pop     r15
0x140056f75  pop     r14
0x140056f77  pop     rdi
0x140056f78  pop     rsi
0x140056f79  pop     rbx
0x140056f7a  retn
```
