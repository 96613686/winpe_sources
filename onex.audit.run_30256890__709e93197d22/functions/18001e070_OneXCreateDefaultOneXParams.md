# OneXCreateDefaultOneXParams

- ea: `0x18001e070`
- end: `0x18001e0fa`
- name: `OneXCreateDefaultOneXParams`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001df38`

## callees

- `0x18001e070`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18001e09c`
- `MobileNetworking!AllocateMemory` at `0x18001e09c`
- `MobileNetworking!FreeMemory` at `0x18001e0e7`
- `MobileNetworking!FreeMemory` at `0x18001e0e7`

## string_xrefs

- `0x18001e08c`: `OneXCreateDefaultOneXParams`
- `0x18001e0db`: `OneXCreateDefaultOneXParams`

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
0x18001e070  mov     [rsp+arg_0], rbx
0x18001e075  push    rdi
0x18001e076  sub     rsp, 20h
0x18001e07a  mov     rdi, rcx
0x18001e07d  mov     [rsp+28h+arg_8], 0
0x18001e086  mov     r9d, 5Fh ; '_'
0x18001e08c  lea     r8, aOnexcreatedefa_1; "OneXCreateDefaultOneXParams"
0x18001e093  lea     rdx, [rsp+28h+arg_8]
0x18001e098  lea     ecx, [r9-4Fh]
0x18001e09c  call    cs:__imp_AllocateMemory
0x18001e0a2  mov     ebx, eax
0x18001e0a4  test    eax, eax
0x18001e0a6  jnz     short loc_18001E0D5
0x18001e0a8  mov     rcx, [rsp+28h+arg_8]
0x18001e0ad  mov     dword ptr [rcx], 2
0x18001e0b3  mov     rcx, [rsp+28h+arg_8]
0x18001e0b8  mov     dword ptr [rcx+4], 10h
0x18001e0bf  mov     rcx, [rsp+28h+arg_8]
0x18001e0c4  mov     dword ptr [rcx+8], 1
0x18001e0cb  mov     rcx, [rsp+28h+arg_8]
0x18001e0d0  mov     [rdi], rcx
0x18001e0d3  jmp     short loc_18001E0ED
0x18001e0d5  mov     r8d, 6Fh ; 'o'
0x18001e0db  lea     rdx, aOnexcreatedefa_1; "OneXCreateDefaultOneXParams"
0x18001e0e2  lea     rcx, [rsp+28h+arg_8]
0x18001e0e7  call    cs:__imp_FreeMemory
0x18001e0ed  mov     eax, ebx
0x18001e0ef  mov     rbx, [rsp+28h+arg_0]
0x18001e0f4  add     rsp, 20h
0x18001e0f8  pop     rdi
0x18001e0f9  retn
```
