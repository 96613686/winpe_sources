# EncodeRootCauseInfo

- ea: `0x18002b3a8`
- end: `0x18002b447`
- name: `EncodeRootCauseInfo`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005aa0`

## callees

- `0x18002b3a8`
- `0x18002b4dc`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18002b432`
- `RPCRT4!MesHandleFree` at `0x18002b432`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002b3d9`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002b3d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b414`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b414`

## pseudocode

```c
__int64 __fastcall EncodeRootCauseInfo(__int64 a1, char **a2, _QWORD *a3)
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
    v7 = Protected_RootCauseInfo_Encode(Handle, a1);
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
0x18002b3a8  mov     rax, rsp
0x18002b3ab  mov     [rax+8], rbx
0x18002b3af  push    rbp
0x18002b3b0  push    rsi
0x18002b3b1  push    rdi
0x18002b3b2  sub     rsp, 20h
0x18002b3b6  mov     rdi, rdx
0x18002b3b9  mov     qword ptr [rax+20h], 0
0x18002b3c1  mov     rsi, r8
0x18002b3c4  mov     dword ptr [rax+10h], 0
0x18002b3cb  mov     rbp, rcx
0x18002b3ce  lea     r8, [rax+20h]; pHandle
0x18002b3d2  mov     rcx, rdi; pBuffer
0x18002b3d5  lea     rdx, [rax+10h]; pEncodedSize
0x18002b3d9  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002b3df  mov     ebx, eax
0x18002b3e1  test    eax, eax
0x18002b3e3  jz      short loc_18002B3F2
0x18002b3e5  jle     short loc_18002B408
0x18002b3e7  movzx   ebx, ax
0x18002b3ea  or      ebx, 80070000h
0x18002b3f0  jmp     short loc_18002B408
0x18002b3f2  mov     rcx, [rsp+38h+Handle]
0x18002b3f7  mov     rdx, rbp
0x18002b3fa  call    Protected_RootCauseInfo_Encode
0x18002b3ff  mov     ecx, [rsp+38h+arg_8]
0x18002b403  mov     ebx, eax
0x18002b405  mov     [rsi], rcx
0x18002b408  mov     rcx, [rdi]; pv
0x18002b40b  test    rcx, rcx
0x18002b40e  jz      short loc_18002B428
0x18002b410  test    ebx, ebx
0x18002b412  jns     short loc_18002B428
0x18002b414  call    cs:__imp_CoTaskMemFree
0x18002b41a  mov     qword ptr [rdi], 0
0x18002b421  mov     qword ptr [rsi], 0
0x18002b428  mov     rcx, [rsp+38h+Handle]; Handle
0x18002b42d  test    rcx, rcx
0x18002b430  jz      short loc_18002B438
0x18002b432  call    cs:__imp_MesHandleFree
0x18002b438  mov     eax, ebx
0x18002b43a  mov     rbx, [rsp+38h+arg_0]
0x18002b43f  add     rsp, 20h
0x18002b443  pop     rdi
0x18002b444  pop     rsi
0x18002b445  pop     rbp
0x18002b446  retn
```
