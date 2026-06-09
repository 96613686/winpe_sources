# MupAcquireUncProviderByName

- ea: `0x140019880`
- end: `0x14001993c`
- name: `MupAcquireUncProviderByName`
- size: `188`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140001cf8`
- `0x140003140`
- `0x140013130`
- `0x14001a8d0`
- `0x14001efe0`

## callees

- `0x1400036c8`
- `0x140019810`
- `0x140019880`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400198d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400198d6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001988d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001988d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400198a2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400198a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400198e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400198e2`

## pseudocode

```c
__int64 __fastcall MupAcquireUncProviderByName(PCUNICODE_STRING String1)
{
  __int64 ProviderByName; // rax
  __int64 v3; // rbx
  int v4; // eax

  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(&Resource, 1u);
  ProviderByName = MupiFindProviderByName(String1);
  v3 = ProviderByName;
  if ( ProviderByName )
  {
    v4 = *(_DWORD *)(ProviderByName + 68);
    if ( v4 == 4 || v4 == 1 )
      v3 = 0;
    else
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 4));
  }
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_Zq(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x10u,
      (__int64)WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids,
      &String1->Length,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x140019880  mov     [rsp+arg_0], rbx
0x140019885  push    rdi
0x140019886  sub     rsp, 30h
0x14001988a  mov     rdi, rcx
0x14001988d  call    cs:__imp_KeEnterCriticalRegion
0x140019894  nop     dword ptr [rax+rax+00h]
0x140019899  mov     dl, 1; Wait
0x14001989b  lea     rcx, Resource; Resource
0x1400198a2  call    cs:__imp_ExAcquireResourceSharedLite
0x1400198a9  nop     dword ptr [rax+rax+00h]
0x1400198ae  mov     rcx, rdi; String1
0x1400198b1  call    MupiFindProviderByName
0x1400198b6  mov     rbx, rax
0x1400198b9  test    rax, rax
0x1400198bc  jz      short loc_1400198CF
0x1400198be  mov     eax, [rax+44h]
0x1400198c1  cmp     eax, 4
0x1400198c4  jz      short loc_140019919
0x1400198c6  cmp     eax, 1
0x1400198c9  jz      short loc_140019919
0x1400198cb  lock inc dword ptr [rbx+4]
0x1400198cf  lea     rcx, Resource; Resource
0x1400198d6  call    cs:__imp_ExReleaseResourceLite
0x1400198dd  nop     dword ptr [rax+rax+00h]
0x1400198e2  call    cs:__imp_KeLeaveCriticalRegion
0x1400198e9  nop     dword ptr [rax+rax+00h]
0x1400198ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400198f5  lea     rax, WPP_GLOBAL_Control
0x1400198fc  cmp     rcx, rax
0x1400198ff  jz      short loc_14001990A
0x140019901  test    dword ptr [rcx+2Ch], 4000000h
0x140019908  jnz     short loc_14001991D
0x14001990a  mov     rax, rbx
0x14001990d  mov     rbx, [rsp+38h+arg_0]
0x140019912  add     rsp, 30h
0x140019916  pop     rdi
0x140019917  retn
0x140019919  xor     ebx, ebx
0x14001991b  jmp     short loc_1400198CF
0x14001991d  mov     rcx, [rcx+18h]
0x140019921  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x140019928  mov     edx, 10h
0x14001992d  mov     [rsp+38h+var_18], rbx
0x140019932  mov     r9, rdi
0x140019935  call    WPP_SF_Zq
0x14001993a  jmp     short loc_14001990A
```
