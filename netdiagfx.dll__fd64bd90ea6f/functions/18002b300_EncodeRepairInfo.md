# EncodeRepairInfo

- ea: `0x18002b300`
- end: `0x18002b39f`
- name: `EncodeRepairInfo`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180005800`

## callees

- `0x18002b300`
- `0x18002b494`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18002b38a`
- `RPCRT4!MesHandleFree` at `0x18002b38a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002b331`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002b331`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b36c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b36c`

## pseudocode

```c
__int64 __fastcall EncodeRepairInfo(__int64 a1, char **a2, _QWORD *a3)
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
    v7 = Protected_RepairInfo_Encode(Handle, a1);
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
0x18002b300  mov     rax, rsp
0x18002b303  mov     [rax+8], rbx
0x18002b307  push    rbp
0x18002b308  push    rsi
0x18002b309  push    rdi
0x18002b30a  sub     rsp, 20h
0x18002b30e  mov     rdi, rdx
0x18002b311  mov     qword ptr [rax+20h], 0
0x18002b319  mov     rsi, r8
0x18002b31c  mov     dword ptr [rax+10h], 0
0x18002b323  mov     rbp, rcx
0x18002b326  lea     r8, [rax+20h]; pHandle
0x18002b32a  mov     rcx, rdi; pBuffer
0x18002b32d  lea     rdx, [rax+10h]; pEncodedSize
0x18002b331  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002b337  mov     ebx, eax
0x18002b339  test    eax, eax
0x18002b33b  jz      short loc_18002B34A
0x18002b33d  jle     short loc_18002B360
0x18002b33f  movzx   ebx, ax
0x18002b342  or      ebx, 80070000h
0x18002b348  jmp     short loc_18002B360
0x18002b34a  mov     rcx, [rsp+38h+Handle]
0x18002b34f  mov     rdx, rbp
0x18002b352  call    Protected_RepairInfo_Encode
0x18002b357  mov     ecx, [rsp+38h+arg_8]
0x18002b35b  mov     ebx, eax
0x18002b35d  mov     [rsi], rcx
0x18002b360  mov     rcx, [rdi]; pv
0x18002b363  test    rcx, rcx
0x18002b366  jz      short loc_18002B380
0x18002b368  test    ebx, ebx
0x18002b36a  jns     short loc_18002B380
0x18002b36c  call    cs:__imp_CoTaskMemFree
0x18002b372  mov     qword ptr [rdi], 0
0x18002b379  mov     qword ptr [rsi], 0
0x18002b380  mov     rcx, [rsp+38h+Handle]; Handle
0x18002b385  test    rcx, rcx
0x18002b388  jz      short loc_18002B390
0x18002b38a  call    cs:__imp_MesHandleFree
0x18002b390  mov     eax, ebx
0x18002b392  mov     rbx, [rsp+38h+arg_0]
0x18002b397  add     rsp, 20h
0x18002b39b  pop     rdi
0x18002b39c  pop     rsi
0x18002b39d  pop     rbp
0x18002b39e  retn
```
