# EncodeHelperAttribute

- ea: `0x18001be28`
- end: `0x18001bec7`
- name: `EncodeHelperAttribute`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000cde4`
- `0x18000d390`

## callees

- `0x18001be28`
- `0x18001bf14`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001be94`
- `ole32!CoTaskMemFree` at `0x18001be94`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001be59`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001be59`
- `RPCRT4!MesHandleFree` at `0x18001beb2`
- `RPCRT4!MesHandleFree` at `0x18001beb2`

## pseudocode

```c
__int64 __fastcall EncodeHelperAttribute(__int64 a1, char **a2, _QWORD *a3)
{
  RPC_STATUS v6; // eax
  signed int v7; // ebx
  unsigned int v9; // [rsp+48h] [rbp+10h] BYREF
  handle_t Handle; // [rsp+58h] [rbp+20h] BYREF

  Handle = 0;
  v9 = 0;
  v6 = MesEncodeDynBufferHandleCreate(a2, &v9, &Handle);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    v7 = Protected_HELPER_ATTRIBUTE_Encode(Handle, a1);
    *a3 = v9;
  }
  if ( *a2 && v7 < 0 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
    *a3 = 0;
  }
  if ( Handle )
    MesHandleFree(Handle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001be28  mov     rax, rsp
0x18001be2b  mov     [rax+8], rbx
0x18001be2f  push    rbp
0x18001be30  push    rsi
0x18001be31  push    rdi
0x18001be32  sub     rsp, 20h
0x18001be36  mov     rdi, rdx
0x18001be39  mov     qword ptr [rax+20h], 0
0x18001be41  mov     rsi, r8
0x18001be44  mov     dword ptr [rax+10h], 0
0x18001be4b  mov     rbp, rcx
0x18001be4e  lea     r8, [rax+20h]; pHandle
0x18001be52  mov     rcx, rdi; pBuffer
0x18001be55  lea     rdx, [rax+10h]; pEncodedSize
0x18001be59  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18001be5f  mov     ebx, eax
0x18001be61  test    eax, eax
0x18001be63  jz      short loc_18001BE72
0x18001be65  jle     short loc_18001BE88
0x18001be67  movzx   ebx, ax
0x18001be6a  or      ebx, 80070000h
0x18001be70  jmp     short loc_18001BE88
0x18001be72  mov     rcx, [rsp+38h+Handle]
0x18001be77  mov     rdx, rbp
0x18001be7a  call    Protected_HELPER_ATTRIBUTE_Encode
0x18001be7f  mov     ecx, [rsp+38h+arg_8]
0x18001be83  mov     ebx, eax
0x18001be85  mov     [rsi], rcx
0x18001be88  mov     rcx, [rdi]; pv
0x18001be8b  test    rcx, rcx
0x18001be8e  jz      short loc_18001BEA8
0x18001be90  test    ebx, ebx
0x18001be92  jns     short loc_18001BEA8
0x18001be94  call    cs:__imp_CoTaskMemFree
0x18001be9a  mov     qword ptr [rdi], 0
0x18001bea1  mov     qword ptr [rsi], 0
0x18001bea8  mov     rcx, [rsp+38h+Handle]; Handle
0x18001bead  test    rcx, rcx
0x18001beb0  jz      short loc_18001BEB8
0x18001beb2  call    cs:__imp_MesHandleFree
0x18001beb8  mov     eax, ebx
0x18001beba  mov     rbx, [rsp+38h+arg_0]
0x18001bebf  add     rsp, 20h
0x18001bec3  pop     rdi
0x18001bec4  pop     rsi
0x18001bec5  pop     rbp
0x18001bec6  retn
```
