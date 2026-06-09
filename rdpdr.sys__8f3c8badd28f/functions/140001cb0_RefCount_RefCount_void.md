# RefCount::~RefCount(void)

- ea: `0x140001cb0`
- end: `0x140001d0e`
- name: `??1RefCount@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(RefCount *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140003800`
- `0x14001652c`
- `0x14001b0e8`
- `0x14001bcb0`
- `0x140020a30`
- `0x14002a1c0`
- `0x14002c894`
- `0x14002c900`

## callees

- `0x140001cb0`
- `0x140003b98`

## pseudocode

```c
void __fastcall RefCount::~RefCount(RefCount *this)
{
  *(_QWORD *)this = &RefCount::`vftable';
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_b03ff0e4f24d3f3b02d8d6e68cf38037_Traceguids,
      this,
      *((_DWORD *)this + 4));
  *(_QWORD *)this = &TopObj::`vftable';
}

```

## disassembly

```asm
0x140001cb0  push    rbx
0x140001cb2  sub     rsp, 30h
0x140001cb6  lea     rax, ??_7RefCount@@6B@; const RefCount::`vftable'
0x140001cbd  mov     rbx, rcx
0x140001cc0  mov     [rcx], rax
0x140001cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cca  lea     rax, WPP_GLOBAL_Control
0x140001cd1  cmp     rcx, rax
0x140001cd4  jnz     short loc_140001CE7
0x140001cd6  lea     rax, ??_7TopObj@@6B@; const TopObj::`vftable'
0x140001cdd  mov     [rbx], rax
0x140001ce0  add     rsp, 30h
0x140001ce4  pop     rbx
0x140001ce5  retn
0x140001ce7  cmp     byte ptr [rcx+29h], 5
0x140001ceb  jb      short loc_140001CD6
0x140001ced  mov     eax, [rbx+10h]
0x140001cf0  lea     r8, WPP_b03ff0e4f24d3f3b02d8d6e68cf38037_Traceguids
0x140001cf7  mov     rcx, [rcx+18h]
0x140001cfb  mov     edx, 0Ah
0x140001d00  mov     r9, rbx
0x140001d03  mov     [rsp+38h+var_18], eax
0x140001d07  call    WPP_SF_qd
0x140001d0c  jmp     short loc_140001CD6
```
