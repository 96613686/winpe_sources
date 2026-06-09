# CSOperationDispatcher::CSOperationDispatcher(void)

- ea: `0x18000c63c`
- end: `0x18000c6d3`
- name: `??0CSOperationDispatcher@@QEAA@XZ`
- size: `151`
- prototype: `CSOperationDispatcher *__fastcall(CSOperationDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000c540`

## callees

- `0x1800028ec`
- `0x18000c63c`
- `0x1800139d0`
- `0x180013a74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c6b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c6b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CSOperationDispatcher *__fastcall CSOperationDispatcher::CSOperationDispatcher(CSOperationDispatcher *this)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rax

  *(_QWORD *)this = 0;
  v2 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v3 = operator new(0x10u);
  v3[1] = 0;
  *v2 = v3;
  *v3 = v2;
  *((_QWORD *)this + 6) = 0;
  *((_WORD *)this + 28) = 0;
  *((_DWORD *)this + 15) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl'::`2'::impl) )
    CSOperationDispatcher::_TryEnsureThreadpoolWorkCreated(this);
  else
    *((_QWORD *)this + 8) = CreateEventW(0, 1, 1, 0);
  return this;
}

```

## disassembly

```asm
0x18000c63c  mov     [rsp+arg_0], rbx
0x18000c641  mov     [rsp+arg_8], rsi
0x18000c646  push    rdi
0x18000c647  sub     rsp, 20h
0x18000c64b  mov     rdi, rcx
0x18000c64e  xor     esi, esi
0x18000c650  mov     [rcx], rsi
0x18000c653  lea     rbx, [rcx+8]
0x18000c657  mov     [rbx], rsi
0x18000c65a  mov     [rbx+8], rsi
0x18000c65e  mov     [rbx+10h], rsi
0x18000c662  mov     [rbx+18h], rsi
0x18000c666  mov     [rbx+20h], rsi
0x18000c66a  lea     ecx, [rsi+10h]; Size
0x18000c66d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c672  mov     [rax+8], rsi
0x18000c676  mov     [rbx], rax
0x18000c679  mov     [rax], rbx
0x18000c67c  xor     eax, eax
0x18000c67e  mov     [rdi+30h], rax
0x18000c682  mov     [rdi+38h], si
0x18000c686  mov     [rdi+3Ch], esi
0x18000c689  mov     [rdi+40h], rsi
0x18000c68d  mov     [rdi+48h], esi
0x18000c690  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl(void)'::`2'::impl
0x18000c697  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(void)
0x18000c69c  test    al, al
0x18000c69e  jz      short loc_18000C6AA
0x18000c6a0  mov     rcx, rdi; pv
0x18000c6a3  call    ?_TryEnsureThreadpoolWorkCreated@CSOperationDispatcher@@AEAA_NXZ; CSOperationDispatcher::_TryEnsureThreadpoolWorkCreated(void)
0x18000c6a8  jmp     short loc_18000C6C0
0x18000c6aa  xor     r9d, r9d; lpName
0x18000c6ad  lea     edx, [r9+1]; bManualReset
0x18000c6b1  mov     r8d, edx; bInitialState
0x18000c6b4  xor     ecx, ecx; lpEventAttributes
0x18000c6b6  call    cs:__imp_CreateEventW
0x18000c6bc  mov     [rdi+40h], rax
0x18000c6c0  mov     rax, rdi
0x18000c6c3  mov     rbx, [rsp+28h+arg_0]
0x18000c6c8  mov     rsi, [rsp+28h+arg_8]
0x18000c6cd  add     rsp, 20h
0x18000c6d1  pop     rdi
0x18000c6d2  retn
```
