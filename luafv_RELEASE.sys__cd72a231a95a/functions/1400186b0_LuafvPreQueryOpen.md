# LuafvPreQueryOpen

- ea: `0x1400186b0`
- end: `0x14001874d`
- name: `LuafvPreQueryOpen`
- size: `157`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400185bc`
- `0x1400186b0`
- `0x140018760`

## pseudocode

```c
__int64 __fastcall LuafvPreQueryOpen(__int64 a1)
{
  unsigned int v2; // ebx
  int VirtualizationCaller; // eax
  int v4; // edi

  v2 = 1;
  if ( !DisableVirt )
  {
    VirtualizationCaller = LuafvQueryVirtualizationCaller(a1);
    v4 = VirtualizationCaller;
    if ( VirtualizationCaller < 0 )
    {
      LuafvLogFileError(a1, 0, &LuafvQueryVirtualizationFailed, (unsigned int)VirtualizationCaller);
      if ( v4 == -1073741670 || v4 == -1073741773 )
      {
        *(_DWORD *)(a1 + 24) = v4;
        v2 = 4;
        *(_QWORD *)(a1 + 32) = 0;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400186b0  mov     rax, rsp
0x1400186b3  mov     [rax+8], rbx
0x1400186b7  mov     [rax+10h], rsi
0x1400186bb  push    rdi
0x1400186bc  sub     rsp, 30h
0x1400186c0  cmp     cs:DisableVirt, 0
0x1400186c7  mov     rsi, rcx
0x1400186ca  mov     byte ptr [rax+20h], 0
0x1400186ce  mov     ebx, 1
0x1400186d3  mov     dword ptr [rax-18h], 0
0x1400186da  jnz     short loc_1400186F6
0x1400186dc  lea     r8, [rax-18h]
0x1400186e0  lea     rdx, [rax+20h]
0x1400186e4  call    LuafvQueryVirtualizationCaller
0x1400186e9  mov     edi, eax
0x1400186eb  test    eax, eax
0x1400186ed  js      short loc_140018717
0x1400186ef  cmp     [rsp+38h+arg_18], 0
0x1400186f4  jnz     short loc_140018709
0x1400186f6  mov     rsi, [rsp+38h+arg_8]
0x1400186fb  mov     eax, ebx
0x1400186fd  mov     rbx, [rsp+38h+arg_0]
0x140018702  add     rsp, 30h
0x140018706  pop     rdi
0x140018707  retn
0x140018709  test    [rsp+38h+var_18], bl
0x14001870d  mov     eax, 6
0x140018712  cmovz   ebx, eax
0x140018715  jmp     short loc_1400186F6
0x140018717  mov     r9d, edi
0x14001871a  lea     r8, LuafvQueryVirtualizationFailed
0x140018721  xor     edx, edx
0x140018723  mov     rcx, rsi
0x140018726  call    LuafvLogFileError
0x14001872b  cmp     edi, 0C000009Ah
0x140018731  jz      short loc_14001873B
0x140018733  cmp     edi, 0C0000033h
0x140018739  jnz     short loc_1400186F6
0x14001873b  mov     [rsi+18h], edi
0x14001873e  mov     ebx, 4
0x140018743  mov     qword ptr [rsi+20h], 0
0x14001874b  jmp     short loc_1400186F6
```
