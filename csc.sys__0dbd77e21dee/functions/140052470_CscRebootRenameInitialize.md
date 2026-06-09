# CscRebootRenameInitialize

- ea: `0x140052470`
- end: `0x140052517`
- name: `CscRebootRenameInitialize`
- size: `167`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140090740`

## callees

- `0x1400190ec`
- `0x140052470`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400524b8`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400524b8`
- `ntoskrnl!ExInitializeResourceLite` at `0x140052486`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400524a2`
- `ntoskrnl!ExInitializeResourceLite` at `0x140052486`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400524a2`

## pseudocode

```c
__int64 __fastcall CscRebootRenameInitialize(PERESOURCE Resource)
{
  NTSTATUS v2; // ebx
  int v3; // ecx

  v2 = ExInitializeResourceLite(Resource + 1);
  if ( v2 >= 0 )
  {
    v2 = ExInitializeResourceLite(Resource);
    if ( v2 >= 0 )
    {
      v3 = 0;
    }
    else
    {
      ExDeleteResourceLite(Resource + 1);
      v3 = 583;
    }
  }
  else
  {
    v3 = 577;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids,
      (unsigned int)v2,
      v3);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140052470  mov     [rsp+arg_0], rbx
0x140052475  mov     [rsp+arg_8], rsi
0x14005247a  push    rdi
0x14005247b  sub     rsp, 30h
0x14005247f  mov     rsi, rcx
0x140052482  add     rcx, 68h ; 'h'; Resource
0x140052486  call    cs:__imp_ExInitializeResourceLite
0x14005248d  nop     dword ptr [rax+rax+00h]
0x140052492  mov     ebx, eax
0x140052494  test    eax, eax
0x140052496  jns     short loc_14005249F
0x140052498  mov     ecx, 241h
0x14005249d  jmp     short loc_1400524CD
0x14005249f  mov     rcx, rsi; Resource
0x1400524a2  call    cs:__imp_ExInitializeResourceLite
0x1400524a9  nop     dword ptr [rax+rax+00h]
0x1400524ae  mov     ebx, eax
0x1400524b0  test    eax, eax
0x1400524b2  jns     short loc_1400524CB
0x1400524b4  lea     rcx, [rsi+68h]; Resource
0x1400524b8  call    cs:__imp_ExDeleteResourceLite
0x1400524bf  nop     dword ptr [rax+rax+00h]
0x1400524c4  mov     ecx, 247h
0x1400524c9  jmp     short loc_1400524CD
0x1400524cb  xor     ecx, ecx
0x1400524cd  mov     r10, cs:WPP_GLOBAL_Control
0x1400524d4  lea     rax, WPP_GLOBAL_Control
0x1400524db  cmp     r10, rax
0x1400524de  jz      short loc_140052504
0x1400524e0  mov     eax, [r10+2Ch]
0x1400524e4  test    al, 20h
0x1400524e6  jz      short loc_140052504
0x1400524e8  mov     [rsp+38h+var_18], ecx
0x1400524ec  lea     r8, WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids
0x1400524f3  mov     rcx, [r10+18h]
0x1400524f7  mov     edx, 0Eh
0x1400524fc  mov     r9d, ebx
0x1400524ff  call    WPP_SF_Dd
0x140052504  mov     rsi, [rsp+38h+arg_8]
0x140052509  mov     eax, ebx
0x14005250b  mov     rbx, [rsp+38h+arg_0]
0x140052510  add     rsp, 30h
0x140052514  pop     rdi
0x140052515  retn
```
