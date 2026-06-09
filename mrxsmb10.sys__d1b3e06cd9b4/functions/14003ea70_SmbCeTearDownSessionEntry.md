# SmbCeTearDownSessionEntry

- ea: `0x14003ea70`
- end: `0x14003eb25`
- name: `SmbCeTearDownSessionEntry`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000cda8`

## callees

- `0x140005c60`
- `0x14000ebd8`
- `0x14001111c`
- `0x14003ea70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003eace`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003eaf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003eace`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003eaf3`
- `rdbss!RxFinalizeSecurityContext` at `0x14003eab4`
- `rdbss!RxFinalizeSecurityContext` at `0x14003eab4`

## pseudocode

```c
__int64 __fastcall SmbCeTearDownSessionEntry(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids, a1);
  RxFinalizeSecurityContext(a1 + 144);
  v2 = *(void **)(a1 + 400);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *(_QWORD *)(a1 + 400) = 0;
  }
  v3 = *(void **)(a1 + 392);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    *(_QWORD *)(a1 + 392) = 0;
  }
  UninitializeSecurityContextsForSession(a1 + 128);
  return SmbMmFreeObjectPool(a1);
}

```

## disassembly

```asm
0x14003ea70  push    rbx
0x14003ea72  sub     rsp, 20h
0x14003ea76  mov     rbx, rcx
0x14003ea79  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003ea80  lea     rax, WPP_GLOBAL_Control
0x14003ea87  cmp     rcx, rax
0x14003ea8a  jz      short loc_14003EAAD
0x14003ea8c  test    dword ptr [rcx+2Ch], 200h
0x14003ea93  jz      short loc_14003EAAD
0x14003ea95  mov     rcx, [rcx+18h]
0x14003ea99  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x14003eaa0  mov     edx, 1Fh
0x14003eaa5  mov     r9, rbx
0x14003eaa8  call    WPP_SF_q
0x14003eaad  lea     rcx, [rbx+90h]
0x14003eab4  call    cs:__imp_RxFinalizeSecurityContext
0x14003eabb  nop     dword ptr [rax+rax+00h]
0x14003eac0  mov     rcx, [rbx+190h]; P
0x14003eac7  test    rcx, rcx
0x14003eaca  jz      short loc_14003EAE5
0x14003eacc  xor     edx, edx; Tag
0x14003eace  call    cs:__imp_ExFreePoolWithTag
0x14003ead5  nop     dword ptr [rax+rax+00h]
0x14003eada  mov     qword ptr [rbx+190h], 0
0x14003eae5  mov     rcx, [rbx+188h]; P
0x14003eaec  test    rcx, rcx
0x14003eaef  jz      short loc_14003EB0A
0x14003eaf1  xor     edx, edx; Tag
0x14003eaf3  call    cs:__imp_ExFreePoolWithTag
0x14003eafa  nop     dword ptr [rax+rax+00h]
0x14003eaff  mov     qword ptr [rbx+188h], 0
0x14003eb0a  lea     rcx, [rbx+80h]
0x14003eb11  call    UninitializeSecurityContextsForSession
0x14003eb16  mov     rcx, rbx
0x14003eb19  call    SmbMmFreeObjectPool
0x14003eb1e  add     rsp, 20h
0x14003eb22  pop     rbx
0x14003eb23  retn
```
