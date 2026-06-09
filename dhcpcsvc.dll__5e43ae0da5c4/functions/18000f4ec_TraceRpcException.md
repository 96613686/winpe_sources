# TraceRpcException

- ea: `0x18000f4ec`
- end: `0x18000f51f`
- name: `TraceRpcException`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `47`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001240`
- `0x180001490`
- `0x180001bd0`
- `0x180002ca0`
- `0x180003d50`
- `0x180005be0`
- `0x180005d30`
- `0x180006180`
- `0x180006a1c`
- `0x180006b78`
- `0x180006c90`
- `0x180006e10`
- `0x180007010`
- `0x180007200`
- `0x180007480`
- `0x1800075d0`
- `0x180007950`
- `0x180007aa0`
- `0x180007c00`
- `0x180007dd0`
- `0x180008210`
- `0x18000847c`
- `0x180008700`
- `0x180008dd4`
- `0x180009d40`
- `0x18000a180`
- `0x18000a2d0`
- `0x18000a4d0`
- `0x18000a950`
- `0x18000ac50`
- `0x18000b180`
- `0x18000b360`
- `0x18000b590`
- `0x18000b7c0`
- `0x18000b9d0`
- `0x18000bd64`
- `0x18000bf80`
- `0x18000c110`
- `0x18000c2f0`
- `0x18000c400`
- `0x18000c540`
- `0x18000c7d0`
- `0x18000c990`
- `0x18000cc10`
- `0x18000cfe0`
- `0x18000d660`

## callees

- `0x18000f4ec`
- `0x180012a40`

## pseudocode

```c
__int64 __fastcall TraceRpcException(int a1, __int64 a2)
{
  __int64 result; // rax

  result = a2;
  if ( (xmmword_18001E1E0 & 2) != 0 )
    return WPP_SF_DS(1025, 13, (unsigned int)WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids, a1, a2);
  return result;
}

```

## disassembly

```asm
0x18000f4ec  sub     rsp, 38h
0x18000f4f0  mov     rax, rdx
0x18000f4f3  mov     r9d, ecx
0x18000f4f6  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000f4fd  jz      short loc_18000F51A
0x18000f4ff  mov     edx, 0Dh
0x18000f504  mov     [rsp+38h+var_18], rax
0x18000f509  mov     ecx, 401h
0x18000f50e  lea     r8, WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids
0x18000f515  call    WPP_SF_DS
0x18000f51a  add     rsp, 38h
0x18000f51e  retn
```
