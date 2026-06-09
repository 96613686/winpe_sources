# __MRxSmbAllocateSideBuffer

- ea: `0x14002c464`
- end: `0x14002c588`
- name: `__MRxSmbAllocateSideBuffer`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002a430`
- `0x140043368`
- `0x140043f88`

## callees

- `0x14000edac`
- `0x14002c464`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14002c572`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002c572`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002c537`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002c537`
- `ntoskrnl!ExAllocatePool2` at `0x14002c488`
- `ntoskrnl!ExAllocatePool2` at `0x14002c488`

## pseudocode

```c
void __fastcall _MRxSmbAllocateSideBuffer(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v4; // rbp
  __int64 Pool2; // rax
  __int64 v6; // rbx
  signed __int32 v7; // eax
  _QWORD *v8; // rcx

  v2 = *(_QWORD *)(a1 + 56);
  v4 = *(_QWORD *)(a1 + 64);
  Pool2 = ExAllocatePool2(66, 16432, 1665428819);
  v6 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 1246511699;
    *(_QWORD *)(Pool2 + 40) = a2;
    *(_QWORD *)(Pool2 + 32) = v4;
    *(_QWORD *)(Pool2 + 24) = v2;
    *(_QWORD *)(a2 + 16) = Pool2 + 48;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        Pool2 + 48,
        v4,
        v2);
    v7 = _InterlockedIncrement(&MRxSmbSideBuffersSerialNumber);
    *(_DWORD *)(v6 + 4) = v7;
    *(_DWORD *)(a2 + 24) = v7;
    _InterlockedIncrement(&MRxSmbSideBuffersCount);
    if ( !MRxSmbSideBuffersList )
    {
      qword_14001F828 = (__int64)&MRxSmbSideBuffersList;
      MRxSmbSideBuffersList = (__int64)&MRxSmbSideBuffersList;
    }
    ExAcquireFastMutex(&MRxSmbSerializationMutex);
    v8 = (_QWORD *)qword_14001F828;
    if ( *(__int64 **)qword_14001F828 != &MRxSmbSideBuffersList )
      __fastfail(3u);
    *(_QWORD *)(v6 + 16) = qword_14001F828;
    *(_QWORD *)(v6 + 8) = &MRxSmbSideBuffersList;
    *v8 = v6 + 8;
    qword_14001F828 = v6 + 8;
    ExReleaseFastMutex(&MRxSmbSerializationMutex);
  }
}

```

## disassembly

```asm
0x14002c464  push    rbx
0x14002c466  push    rbp
0x14002c467  push    rsi
0x14002c468  push    rdi
0x14002c469  sub     rsp, 38h
0x14002c46d  mov     rsi, [rcx+38h]
0x14002c471  mov     rdi, rdx
0x14002c474  mov     rbp, [rcx+40h]
0x14002c478  mov     edx, 4030h
0x14002c47d  mov     ecx, 42h ; 'B'
0x14002c482  mov     r8d, 63446D53h
0x14002c488  call    cs:__imp_ExAllocatePool2
0x14002c48f  nop     dword ptr [rax+rax+00h]
0x14002c494  mov     rbx, rax
0x14002c497  test    rax, rax
0x14002c49a  jz      loc_14002C57E
0x14002c4a0  lea     r9, [rax+30h]
0x14002c4a4  mov     dword ptr [rax], 4A4C4253h
0x14002c4aa  mov     [rax+28h], rdi
0x14002c4ae  mov     [rax+20h], rbp
0x14002c4b2  mov     [rax+18h], rsi
0x14002c4b6  mov     [rdi+10h], r9
0x14002c4ba  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c4c1  lea     rax, WPP_GLOBAL_Control
0x14002c4c8  cmp     rcx, rax
0x14002c4cb  jz      short loc_14002C4F5
0x14002c4cd  test    dword ptr [rcx+2Ch], 200h
0x14002c4d4  jz      short loc_14002C4F5
0x14002c4d6  mov     rcx, [rcx+18h]
0x14002c4da  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002c4e1  mov     edx, 0Ah
0x14002c4e6  mov     [rsp+58h+var_30], rsi
0x14002c4eb  mov     [rsp+58h+var_38], rbp
0x14002c4f0  call    WPP_SF_qqq
0x14002c4f5  mov     eax, 1
0x14002c4fa  lock xadd cs:MRxSmbSideBuffersSerialNumber, eax
0x14002c502  inc     eax
0x14002c504  mov     [rbx+4], eax
0x14002c507  mov     [rdi+18h], eax
0x14002c50a  lock inc cs:MRxSmbSideBuffersCount
0x14002c511  cmp     cs:MRxSmbSideBuffersList, 0
0x14002c519  lea     rdi, MRxSmbSideBuffersList
0x14002c520  jnz     short loc_14002C530
0x14002c522  mov     cs:qword_14001F828, rdi
0x14002c529  mov     cs:MRxSmbSideBuffersList, rdi
0x14002c530  lea     rcx, MRxSmbSerializationMutex; FastMutex
0x14002c537  call    cs:__imp_ExAcquireFastMutex
0x14002c53e  nop     dword ptr [rax+rax+00h]
0x14002c543  mov     rcx, cs:qword_14001F828
0x14002c54a  cmp     [rcx], rdi
0x14002c54d  jz      short loc_14002C556
0x14002c54f  mov     ecx, 3
0x14002c554  int     29h; Win8: RtlFailFast(ecx)
0x14002c556  lea     rax, [rbx+8]
0x14002c55a  mov     [rax+8], rcx
0x14002c55e  mov     [rax], rdi
0x14002c561  mov     [rcx], rax
0x14002c564  lea     rcx, MRxSmbSerializationMutex; FastMutex
0x14002c56b  mov     cs:qword_14001F828, rax
0x14002c572  call    cs:__imp_ExReleaseFastMutex
0x14002c579  nop     dword ptr [rax+rax+00h]
0x14002c57e  add     rsp, 38h
0x14002c582  pop     rdi
0x14002c583  pop     rsi
0x14002c584  pop     rbp
0x14002c585  pop     rbx
0x14002c586  retn
```
