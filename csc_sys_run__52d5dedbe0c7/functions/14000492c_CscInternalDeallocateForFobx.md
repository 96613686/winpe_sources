# CscInternalDeallocateForFobx

- ea: `0x14000492c`
- end: `0x140004a27`
- name: `CscInternalDeallocateForFobx`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003690`
- `0x140062b70`

## callees

- `0x14000492c`
- `0x140018930`
- `0x140080758`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140004977`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004977`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000499a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400049f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000499a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400049f4`
- `ntoskrnl!ExDeleteResourceLite` at `0x140004986`
- `ntoskrnl!ExDeleteResourceLite` at `0x140004986`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004968`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004968`
- `rdbss!RxPrefixTableEndLookup` at `0x1400049e2`
- `rdbss!RxPrefixTableEndLookup` at `0x1400049e2`

## pseudocode

```c
void __fastcall CscInternalDeallocateForFobx(__int64 a1)
{
  __int64 v1; // rbx
  struct _ERESOURCE *v3; // rbx
  unsigned int v4; // ebx

  v1 = *(_QWORD *)(a1 + 64);
  if ( v1 )
  {
    if ( *(_DWORD *)(v1 + 32) == 3 && *(_QWORD *)(v1 + 40) )
    {
      RxPrefixTableEndLookup();
      ExFreePoolWithTag(*(PVOID *)(v1 + 40), 0);
      *(_QWORD *)(v1 + 40) = 0;
    }
    if ( *(_QWORD *)(v1 + 16) )
      CscQueryDirDeallocateEnumContext(v1);
    v3 = (struct _ERESOURCE *)(v1 + 88);
    ExAcquireResourceExclusiveLite(v3, 1u);
    ExReleaseResourceLite(v3);
    v4 = ExDeleteResourceLite(v3);
    ExFreePoolWithTag(*(PVOID *)(a1 + 64), 0);
    *(_QWORD *)(a1 + 64) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 223, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v4);
  }
}

```

## disassembly

```asm
0x14000492c  mov     [rsp+arg_0], rbx
0x140004931  push    rdi
0x140004932  sub     rsp, 20h
0x140004936  mov     rbx, [rcx+40h]
0x14000493a  mov     rdi, rcx
0x14000493d  test    rbx, rbx
0x140004940  jz      loc_1400049C9
0x140004946  cmp     dword ptr [rbx+20h], 3
0x14000494a  jz      loc_1400049D5
0x140004950  cmp     qword ptr [rbx+10h], 0
0x140004955  jz      short loc_14000495F
0x140004957  mov     rcx, rbx
0x14000495a  call    CscQueryDirDeallocateEnumContext
0x14000495f  add     rbx, 58h ; 'X'
0x140004963  mov     dl, 1; Wait
0x140004965  mov     rcx, rbx; Resource
0x140004968  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000496f  nop     dword ptr [rax+rax+00h]
0x140004974  mov     rcx, rbx; Resource
0x140004977  call    cs:__imp_ExReleaseResourceLite
0x14000497e  nop     dword ptr [rax+rax+00h]
0x140004983  mov     rcx, rbx; Resource
0x140004986  call    cs:__imp_ExDeleteResourceLite
0x14000498d  nop     dword ptr [rax+rax+00h]
0x140004992  mov     rcx, [rdi+40h]; P
0x140004996  xor     edx, edx; Tag
0x140004998  mov     ebx, eax
0x14000499a  call    cs:__imp_ExFreePoolWithTag
0x1400049a1  nop     dword ptr [rax+rax+00h]
0x1400049a6  mov     qword ptr [rdi+40h], 0
0x1400049ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049b5  lea     rax, WPP_GLOBAL_Control
0x1400049bc  cmp     rcx, rax
0x1400049bf  jz      short loc_1400049C9
0x1400049c1  mov     edx, [rcx+2Ch]
0x1400049c4  test    dl, 40h
0x1400049c7  jnz     short loc_140004A0D
0x1400049c9  mov     rbx, [rsp+28h+arg_0]
0x1400049ce  add     rsp, 20h
0x1400049d2  pop     rdi
0x1400049d3  retn
0x1400049d5  mov     rcx, [rbx+28h]
0x1400049d9  test    rcx, rcx
0x1400049dc  jz      loc_140004950
0x1400049e2  call    cs:__imp_RxPrefixTableEndLookup
0x1400049e9  nop     dword ptr [rax+rax+00h]
0x1400049ee  mov     rcx, [rbx+28h]; P
0x1400049f2  xor     edx, edx; Tag
0x1400049f4  call    cs:__imp_ExFreePoolWithTag
0x1400049fb  nop     dword ptr [rax+rax+00h]
0x140004a00  mov     qword ptr [rbx+28h], 0
0x140004a08  jmp     loc_140004950
0x140004a0d  mov     rcx, [rcx+18h]
0x140004a11  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140004a18  mov     edx, 0DFh
0x140004a1d  mov     r9d, ebx
0x140004a20  call    WPP_SF_d
0x140004a25  jmp     short loc_1400049C9
```
