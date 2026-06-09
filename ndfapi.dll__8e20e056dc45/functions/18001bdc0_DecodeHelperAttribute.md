# DecodeHelperAttribute

- ea: `0x18001bdc0`
- end: `0x18001be20`
- name: `DecodeHelperAttribute`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e0c4`
- `0x180011934`

## callees

- `0x18001bdc0`
- `0x18001bed0`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18001be0d`
- `RPCRT4!MesHandleFree` at `0x18001be0d`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001bddb`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001bddb`

## pseudocode

```c
__int64 __fastcall DecodeHelperAttribute(char *a1, unsigned int a2, __int64 a3)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  handle_t pHandle; // [rsp+48h] [rbp+20h] BYREF

  pHandle = 0;
  v4 = MesDecodeBufferHandleCreate(a1, a2, &pHandle);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v5 = Protected_HELPER_ATTRIBUTE_Decode(pHandle, a3);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  return v5;
}

```

## disassembly

```asm
0x18001bdc0  mov     [rsp+arg_0], rbx
0x18001bdc5  push    rdi
0x18001bdc6  sub     rsp, 20h
0x18001bdca  mov     rdi, r8
0x18001bdcd  mov     [rsp+28h+pHandle], 0
0x18001bdd6  lea     r8, [rsp+28h+pHandle]; pHandle
0x18001bddb  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001bde1  mov     ebx, eax
0x18001bde3  test    eax, eax
0x18001bde5  jz      short loc_18001BDF4
0x18001bde7  jle     short loc_18001BE03
0x18001bde9  movzx   ebx, ax
0x18001bdec  or      ebx, 80070000h
0x18001bdf2  jmp     short loc_18001BE03
0x18001bdf4  mov     rcx, [rsp+28h+pHandle]
0x18001bdf9  mov     rdx, rdi
0x18001bdfc  call    Protected_HELPER_ATTRIBUTE_Decode
0x18001be01  mov     ebx, eax
0x18001be03  mov     rcx, [rsp+28h+pHandle]; Handle
0x18001be08  test    rcx, rcx
0x18001be0b  jz      short loc_18001BE13
0x18001be0d  call    cs:__imp_MesHandleFree
0x18001be13  mov     eax, ebx
0x18001be15  mov     rbx, [rsp+28h+arg_0]
0x18001be1a  add     rsp, 20h
0x18001be1e  pop     rdi
0x18001be1f  retn
```
