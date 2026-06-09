# CdpAllocateClient

- ea: `0x14000bce0`
- end: `0x14000bd29`
- name: `CdpAllocateClient`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b4d0`
- `0x14000be70`

## callees

- `0x14000bce0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000bcf4`
- `ntoskrnl!ExAllocatePool2` at `0x14000bcf4`

## pseudocode

```c
_QWORD *CdpAllocateClient()
{
  _QWORD *result; // rax

  result = (_QWORD *)ExAllocatePool2(256, 40, 1816355907);
  if ( result )
  {
    result[1] = 0;
    result[2] = 0;
    result[3] = 0;
    result[4] = 0;
    *result = &CdClientType;
  }
  return result;
}

```

## disassembly

```asm
0x14000bce0  sub     rsp, 28h
0x14000bce4  mov     edx, 28h ; '('
0x14000bce9  mov     r8d, 6C436443h
0x14000bcef  mov     ecx, 100h
0x14000bcf4  call    cs:__imp_ExAllocatePool2
0x14000bcfb  nop     dword ptr [rax+rax+00h]
0x14000bd00  test    rax, rax
0x14000bd03  jz      short loc_14000BD27
0x14000bd05  xor     ecx, ecx
0x14000bd07  mov     [rax+8], rcx
0x14000bd0b  mov     [rax+10h], rcx
0x14000bd0f  mov     [rax+18h], rcx
0x14000bd13  mov     [rax+20h], rcx
0x14000bd17  lea     rcx, CdClientType
0x14000bd1e  mov     [rax], rcx
0x14000bd21  add     rsp, 28h
0x14000bd25  retn
0x14000bd27  jmp     short loc_14000BD21
```
