# OneXCreateDefaultOneXParams

- ea: `0x18003103c`
- end: `0x1800310c6`
- name: `OneXCreateDefaultOneXParams`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180031510`

## callees

- `0x18003103c`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x1800310b3`
- `MobileNetworking!FreeMemory` at `0x1800310b3`
- `MobileNetworking!AllocateMemory` at `0x180031068`
- `MobileNetworking!AllocateMemory` at `0x180031068`

## string_xrefs

- `0x180031058`: `OneXCreateDefaultOneXParams`
- `0x1800310a7`: `OneXCreateDefaultOneXParams`

## pseudocode

```c
__int64 __fastcall OneXCreateDefaultOneXParams(_QWORD *a1)
{
  unsigned int v2; // ebx
  _DWORD *v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v2 = AllocateMemory(16, &v4, "OneXCreateDefaultOneXParams", 95);
  if ( v2 )
  {
    FreeMemory(&v4, "OneXCreateDefaultOneXParams", 111);
  }
  else
  {
    *v4 = 2;
    v4[1] = 16;
    v4[2] = 1;
    *a1 = v4;
  }
  return v2;
}

```

## disassembly

```asm
0x18003103c  mov     [rsp+arg_0], rbx
0x180031041  push    rdi
0x180031042  sub     rsp, 20h
0x180031046  mov     rdi, rcx
0x180031049  mov     [rsp+28h+arg_8], 0
0x180031052  mov     r9d, 5Fh ; '_'
0x180031058  lea     r8, aOnexcreatedefa; "OneXCreateDefaultOneXParams"
0x18003105f  lea     rdx, [rsp+28h+arg_8]
0x180031064  lea     ecx, [r9-4Fh]
0x180031068  call    cs:__imp_AllocateMemory
0x18003106e  mov     ebx, eax
0x180031070  test    eax, eax
0x180031072  jnz     short loc_1800310A1
0x180031074  mov     rcx, [rsp+28h+arg_8]
0x180031079  mov     dword ptr [rcx], 2
0x18003107f  mov     rcx, [rsp+28h+arg_8]
0x180031084  mov     dword ptr [rcx+4], 10h
0x18003108b  mov     rcx, [rsp+28h+arg_8]
0x180031090  mov     dword ptr [rcx+8], 1
0x180031097  mov     rcx, [rsp+28h+arg_8]
0x18003109c  mov     [rdi], rcx
0x18003109f  jmp     short loc_1800310B9
0x1800310a1  mov     r8d, 6Fh ; 'o'
0x1800310a7  lea     rdx, aOnexcreatedefa; "OneXCreateDefaultOneXParams"
0x1800310ae  lea     rcx, [rsp+28h+arg_8]
0x1800310b3  call    cs:__imp_FreeMemory
0x1800310b9  mov     eax, ebx
0x1800310bb  mov     rbx, [rsp+28h+arg_0]
0x1800310c0  add     rsp, 20h
0x1800310c4  pop     rdi
0x1800310c5  retn
```
