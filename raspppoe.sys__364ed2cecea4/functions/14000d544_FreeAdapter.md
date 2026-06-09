# FreeAdapter

- ea: `0x14000d544`
- end: `0x14000d5d7`
- name: `FreeAdapter`
- size: `147`
- prototype: `__int64 __fastcall(PVOID VirtualAddress)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400014e0`
- `0x14000d5e0`

## callees

- `0x14000110c`
- `0x14000d544`

## import_xrefs

- `NDIS!NdisFreeMemory` at `0x14000d591`
- `NDIS!NdisFreeMemory` at `0x14000d591`

## pseudocode

```c
void __fastcall FreeAdapter(PVOID VirtualAddress)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x35u,
      (__int64)WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  NdisFreeMemory(VirtualAddress, 0x2C8u, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x36u,
      (__int64)WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
}

```

## disassembly

```asm
0x14000d544  mov     [rsp+arg_0], rbx
0x14000d549  push    rdi
0x14000d54a  sub     rsp, 20h
0x14000d54e  mov     rbx, rcx
0x14000d551  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d558  lea     rdi, WPP_GLOBAL_Control
0x14000d55f  cmp     rcx, rdi
0x14000d562  jz      short loc_14000D586
0x14000d564  mov     eax, [rcx+2Ch]
0x14000d567  test    al, 1
0x14000d569  jz      short loc_14000D586
0x14000d56b  cmp     byte ptr [rcx+29h], 3
0x14000d56f  jb      short loc_14000D586
0x14000d571  mov     rcx, [rcx+18h]
0x14000d575  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x14000d57c  mov     edx, 35h ; '5'
0x14000d581  call    WPP_SF_
0x14000d586  xor     r8d, r8d; MemoryFlags
0x14000d589  mov     edx, 2C8h; Length
0x14000d58e  mov     rcx, rbx; VirtualAddress
0x14000d591  call    cs:__imp_NdisFreeMemory
0x14000d598  nop     dword ptr [rax+rax+00h]
0x14000d59d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d5a4  cmp     rcx, rdi
0x14000d5a7  jz      short loc_14000D5CB
0x14000d5a9  mov     eax, [rcx+2Ch]
0x14000d5ac  test    al, 1
0x14000d5ae  jz      short loc_14000D5CB
0x14000d5b0  cmp     byte ptr [rcx+29h], 3
0x14000d5b4  jb      short loc_14000D5CB
0x14000d5b6  mov     rcx, [rcx+18h]
0x14000d5ba  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x14000d5c1  mov     edx, 36h ; '6'
0x14000d5c6  call    WPP_SF_
0x14000d5cb  mov     rbx, [rsp+28h+arg_0]
0x14000d5d0  add     rsp, 20h
0x14000d5d4  pop     rdi
0x14000d5d5  retn
```
