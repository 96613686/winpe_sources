# CallSetFullCallId

- ea: `0x14000398c`
- end: `0x1400039f2`
- name: `CallSetFullCallId`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000360c`

## callees

- `0x14000398c`

## import_xrefs

- `cng!SystemPrng` at `0x1400039b0`
- `cng!SystemPrng` at `0x1400039b0`

## pseudocode

```c
__int64 __fastcall CallSetFullCallId(__int64 a1)
{
  __int64 result; // rax
  int v3; // [rsp+38h] [rbp+10h] BYREF

  if ( PptpCallIdMaskSet )
  {
    v3 = 0;
    SystemPrng(&v3, 4);
    result = *(_QWORD *)(a1 + 200) + (unsigned __int16)(v3 & ~(_WORD)PptpCallIdMask);
  }
  else
  {
    result = *(_QWORD *)(a1 + 200) + (unsigned int)PptpBaseCallId;
  }
  *(_QWORD *)(a1 + 208) = result;
  return result;
}

```

## disassembly

```asm
0x14000398c  push    rbx
0x14000398e  sub     rsp, 20h
0x140003992  cmp     cs:PptpCallIdMaskSet, 0
0x140003999  mov     rbx, rcx
0x14000399c  jz      short loc_1400039D7
0x14000399e  mov     edx, 4
0x1400039a3  mov     [rsp+28h+arg_8], 0
0x1400039ab  lea     rcx, [rsp+28h+arg_8]
0x1400039b0  call    cs:__imp_SystemPrng
0x1400039b7  nop     dword ptr [rax+rax+00h]
0x1400039bc  mov     edx, cs:PptpCallIdMask
0x1400039c2  mov     eax, [rsp+28h+arg_8]
0x1400039c6  not     edx
0x1400039c8  and     rdx, rax
0x1400039cb  movzx   eax, dx
0x1400039ce  add     rax, [rbx+0C8h]
0x1400039d5  jmp     short loc_1400039E4
0x1400039d7  mov     eax, cs:PptpBaseCallId
0x1400039dd  add     rax, [rcx+0C8h]
0x1400039e4  mov     [rbx+0D0h], rax
0x1400039eb  add     rsp, 20h
0x1400039ef  pop     rbx
0x1400039f0  retn
```
