# BindingCleanup

- ea: `0x140003f70`
- end: `0x140004003`
- name: `BindingCleanup`
- size: `147`
- prototype: `__int64 __fastcall(PVOID VirtualAddress)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004100`
- `0x140004e10`

## callees

- `0x14000110c`
- `0x140003f70`

## import_xrefs

- `NDIS!NdisFreeMemory` at `0x140003fbd`
- `NDIS!NdisFreeMemory` at `0x140003fbd`

## pseudocode

```c
void __fastcall BindingCleanup(PVOID VirtualAddress)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x17u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  NdisFreeMemory(VirtualAddress, 0x1E0u, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x18u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
}

```

## disassembly

```asm
0x140003f70  mov     [rsp+arg_0], rbx
0x140003f75  push    rdi
0x140003f76  sub     rsp, 20h
0x140003f7a  mov     rbx, rcx
0x140003f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f84  lea     rdi, WPP_GLOBAL_Control
0x140003f8b  cmp     rcx, rdi
0x140003f8e  jz      short loc_140003FB2
0x140003f90  mov     eax, [rcx+2Ch]
0x140003f93  test    al, 4
0x140003f95  jz      short loc_140003FB2
0x140003f97  cmp     byte ptr [rcx+29h], 3
0x140003f9b  jb      short loc_140003FB2
0x140003f9d  mov     rcx, [rcx+18h]
0x140003fa1  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140003fa8  mov     edx, 17h
0x140003fad  call    WPP_SF_
0x140003fb2  xor     r8d, r8d; MemoryFlags
0x140003fb5  mov     edx, 1E0h; Length
0x140003fba  mov     rcx, rbx; VirtualAddress
0x140003fbd  call    cs:__imp_NdisFreeMemory
0x140003fc4  nop     dword ptr [rax+rax+00h]
0x140003fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fd0  cmp     rcx, rdi
0x140003fd3  jz      short loc_140003FF7
0x140003fd5  mov     eax, [rcx+2Ch]
0x140003fd8  test    al, 4
0x140003fda  jz      short loc_140003FF7
0x140003fdc  cmp     byte ptr [rcx+29h], 3
0x140003fe0  jb      short loc_140003FF7
0x140003fe2  mov     rcx, [rcx+18h]
0x140003fe6  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140003fed  mov     edx, 18h
0x140003ff2  call    WPP_SF_
0x140003ff7  mov     rbx, [rsp+28h+arg_0]
0x140003ffc  add     rsp, 20h
0x140004000  pop     rdi
0x140004001  retn
```
