# MupAcquireUncProviderByName

- ea: `0x1400198d0`
- end: `0x14001998c`
- name: `MupAcquireUncProviderByName`
- size: `188`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140001cf8`
- `0x140003140`
- `0x140013180`
- `0x14001a920`
- `0x14001f030`

## callees

- `0x1400036c8`
- `0x140019860`
- `0x1400198d0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140019926`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019926`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400198dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400198dd`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400198f2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400198f2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019932`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019932`

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
0x1400198d0  mov     [rsp+arg_0], rbx
0x1400198d5  push    rdi
0x1400198d6  sub     rsp, 30h
0x1400198da  mov     rdi, rcx
0x1400198dd  call    cs:__imp_KeEnterCriticalRegion
0x1400198e4  nop     dword ptr [rax+rax+00h]
0x1400198e9  mov     dl, 1; Wait
0x1400198eb  lea     rcx, Resource; Resource
0x1400198f2  call    cs:__imp_ExAcquireResourceSharedLite
0x1400198f9  nop     dword ptr [rax+rax+00h]
0x1400198fe  mov     rcx, rdi; String1
0x140019901  call    MupiFindProviderByName
0x140019906  mov     rbx, rax
0x140019909  test    rax, rax
0x14001990c  jz      short loc_14001991F
0x14001990e  mov     eax, [rax+44h]
0x140019911  cmp     eax, 4
0x140019914  jz      short loc_140019969
0x140019916  cmp     eax, 1
0x140019919  jz      short loc_140019969
0x14001991b  lock inc dword ptr [rbx+4]
0x14001991f  lea     rcx, Resource; Resource
0x140019926  call    cs:__imp_ExReleaseResourceLite
0x14001992d  nop     dword ptr [rax+rax+00h]
0x140019932  call    cs:__imp_KeLeaveCriticalRegion
0x140019939  nop     dword ptr [rax+rax+00h]
0x14001993e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019945  lea     rax, WPP_GLOBAL_Control
0x14001994c  cmp     rcx, rax
0x14001994f  jz      short loc_14001995A
0x140019951  test    dword ptr [rcx+2Ch], 4000000h
0x140019958  jnz     short loc_14001996D
0x14001995a  mov     rax, rbx
0x14001995d  mov     rbx, [rsp+38h+arg_0]
0x140019962  add     rsp, 30h
0x140019966  pop     rdi
0x140019967  retn
0x140019969  xor     ebx, ebx
0x14001996b  jmp     short loc_14001991F
0x14001996d  mov     rcx, [rcx+18h]
0x140019971  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x140019978  mov     edx, 10h
0x14001997d  mov     [rsp+38h+var_18], rbx
0x140019982  mov     r9, rdi
0x140019985  call    WPP_SF_Zq
0x14001998a  jmp     short loc_14001995A
```
