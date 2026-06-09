# ValidateReadWaveFormat

- ea: `0x1800034e0`
- end: `0x180003553`
- name: `ValidateReadWaveFormat`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002540`
- `0x180002e70`
- `0x180005990`
- `0x18000cfe0`

## callees

- `0x1800034e0`
- `0x180003f10`

## pseudocode

```c
_BOOL8 __fastcall ValidateReadWaveFormat(_WORD *a1)
{
  int v2; // ecx

  if ( !(unsigned int)ValidateReadPointer(a1, 16) )
    return 0;
  if ( *a1 != 1 )
  {
    if ( (unsigned int)ValidateReadPointer(a1 + 8, 2) )
    {
      v2 = (unsigned __int16)a1[8];
      if ( (_WORD)v2 )
        return (unsigned int)ValidateReadPointer(a1 + 8, (unsigned int)(v2 + 2)) != 0;
      return 1;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800034e0  mov     [rsp+arg_0], rbx
0x1800034e5  push    rdi
0x1800034e6  sub     rsp, 20h
0x1800034ea  mov     edx, 10h
0x1800034ef  mov     rbx, rcx
0x1800034f2  call    ValidateReadPointer
0x1800034f7  test    eax, eax
0x1800034f9  jz      short loc_180003542
0x1800034fb  mov     edi, 1
0x180003500  cmp     di, [rbx]
0x180003503  jz      short loc_180003546
0x180003505  mov     edx, 2
0x18000350a  lea     rcx, [rbx+10h]
0x18000350e  call    ValidateReadPointer
0x180003513  test    eax, eax
0x180003515  jz      short loc_180003542
0x180003517  movzx   ecx, word ptr [rbx+10h]
0x18000351b  xor     eax, eax
0x18000351d  cmp     ax, cx
0x180003520  jz      short loc_180003546
0x180003522  lea     edx, [rcx+2]
0x180003525  lea     rcx, [rbx+10h]
0x180003529  call    ValidateReadPointer
0x18000352e  xor     ecx, ecx
0x180003530  test    eax, eax
0x180003532  setnz   cl
0x180003535  mov     eax, ecx
0x180003537  mov     rbx, [rsp+28h+arg_0]
0x18000353c  add     rsp, 20h
0x180003540  pop     rdi
0x180003541  retn
0x180003542  xor     eax, eax
0x180003544  jmp     short loc_180003537
0x180003546  mov     rbx, [rsp+28h+arg_0]
0x18000354b  mov     eax, edi
0x18000354d  add     rsp, 20h
0x180003551  pop     rdi
0x180003552  retn
```
