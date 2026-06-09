# CNetDiagClient::ExtractRepairOption(void *,CRepairInfo *)

- ea: `0x18000c6b4`
- end: `0x18000c7dc`
- name: `?ExtractRepairOption@CNetDiagClient@@IEAAJPEAXPEAVCRepairInfo@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this, void *, struct CRepairInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000e2d4`

## callees

- `0x18000c6b4`
- `0x18001bf58`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000c6fa`
- `ole32!CoTaskMemAlloc` at `0x18000c6fa`
- `ole32!CoTaskMemFree` at `0x18000c7bc`
- `ole32!CoTaskMemFree` at `0x18000c7bc`
- `wdi!WdiGetParameterDataLength` at `0x18000c6dc`
- `wdi!WdiGetParameterDataLength` at `0x18000c6dc`
- `wdi!WdiGetParameterData` at `0x18000c717`
- `wdi!WdiGetParameterData` at `0x18000c717`
- `RPCRT4!MesHandleFree` at `0x18000c77d`
- `RPCRT4!MesHandleFree` at `0x18000c77d`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000c743`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000c743`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::ExtractRepairOption(CNetDiagClient *this, void *a2, struct CRepairInfo *a3)
{
  void *v5; // rdi
  signed int ParameterDataLength; // ebx
  LPVOID v7; // rax
  unsigned int v8; // edx
  RPC_STATUS v9; // eax
  char *v10; // rbp
  unsigned int cb; // [rsp+40h] [rbp+8h] BYREF
  int cb_4; // [rsp+44h] [rbp+Ch]
  handle_t pHandle; // [rsp+58h] [rbp+20h] BYREF

  cb_4 = HIDWORD(this);
  cb = 0;
  v5 = 0;
  ParameterDataLength = WdiGetParameterDataLength(a2, &cb);
  if ( ParameterDataLength < 0 )
    goto LABEL_14;
  if ( cb )
  {
    v7 = CoTaskMemAlloc(cb);
    v5 = v7;
    if ( !v7 )
    {
      ParameterDataLength = -2147024882;
      goto LABEL_14;
    }
    ParameterDataLength = WdiGetParameterData(a2, v7, cb);
    if ( ParameterDataLength < 0 )
    {
LABEL_14:
      CoTaskMemFree(v5);
      return (unsigned int)ParameterDataLength;
    }
    v8 = cb;
    *((_DWORD *)a3 + 4) = cb;
    *((_QWORD *)a3 + 1) = v5;
    pHandle = 0;
    v9 = MesDecodeBufferHandleCreate((char *)v5, v8, &pHandle);
    ParameterDataLength = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        ParameterDataLength = (unsigned __int16)v9 | 0x80070000;
      v10 = (char *)a3 + 24;
    }
    else
    {
      v10 = (char *)a3 + 24;
      ParameterDataLength = Protected_RepairInfo_Decode(pHandle, (char *)a3 + 24);
    }
    if ( pHandle )
      MesHandleFree(pHandle);
    if ( ParameterDataLength < 0 )
    {
      *((_QWORD *)a3 + 17) = 0;
      *((_QWORD *)a3 + 1) = 0;
      *((_DWORD *)a3 + 4) = 0;
      *((_DWORD *)a3 + 36) = 0;
      memset_0(v10, 0, 0x70u);
      goto LABEL_14;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c6b4  mov     rax, rsp
0x18000c6b7  mov     [rax+10h], rbx
0x18000c6bb  mov     [rax+8], rcx
0x18000c6bf  push    rbp
0x18000c6c0  push    rsi
0x18000c6c1  push    rdi
0x18000c6c2  sub     rsp, 20h
0x18000c6c6  mov     rbp, rdx
0x18000c6c9  mov     dword ptr [rax+8], 0
0x18000c6d0  mov     rcx, rbp
0x18000c6d3  lea     rdx, [rax+8]
0x18000c6d7  mov     rsi, r8
0x18000c6da  xor     edi, edi
0x18000c6dc  call    cs:__imp_WdiGetParameterDataLength
0x18000c6e2  mov     ebx, eax
0x18000c6e4  test    eax, eax
0x18000c6e6  js      loc_18000C7B9
0x18000c6ec  mov     eax, dword ptr [rsp+38h+cb]
0x18000c6f0  test    eax, eax
0x18000c6f2  jz      loc_18000C7D8
0x18000c6f8  mov     ecx, eax; cb
0x18000c6fa  call    cs:__imp_CoTaskMemAlloc
0x18000c700  mov     rdi, rax
0x18000c703  test    rax, rax
0x18000c706  jz      loc_18000C7D1
0x18000c70c  mov     r8d, dword ptr [rsp+38h+cb]
0x18000c711  mov     rdx, rax
0x18000c714  mov     rcx, rbp
0x18000c717  call    cs:__imp_WdiGetParameterData
0x18000c71d  mov     ebx, eax
0x18000c71f  test    eax, eax
0x18000c721  js      loc_18000C7B9
0x18000c727  mov     edx, dword ptr [rsp+38h+cb]; BufferSize
0x18000c72b  lea     r8, [rsp+38h+pHandle]; pHandle
0x18000c730  mov     rcx, rdi; Buffer
0x18000c733  mov     [rsi+10h], edx
0x18000c736  mov     [rsi+8], rdi
0x18000c73a  mov     [rsp+38h+pHandle], 0
0x18000c743  call    cs:__imp_MesDecodeBufferHandleCreate
0x18000c749  mov     ebx, eax
0x18000c74b  test    eax, eax
0x18000c74d  jz      short loc_18000C760
0x18000c74f  jle     short loc_18000C75A
0x18000c751  movzx   ebx, ax
0x18000c754  or      ebx, 80070000h
0x18000c75a  lea     rbp, [rsi+18h]
0x18000c75e  jmp     short loc_18000C773
0x18000c760  mov     rcx, [rsp+38h+pHandle]
0x18000c765  lea     rbp, [rsi+18h]
0x18000c769  mov     rdx, rbp
0x18000c76c  call    Protected_RepairInfo_Decode
0x18000c771  mov     ebx, eax
0x18000c773  mov     rcx, [rsp+38h+pHandle]; Handle
0x18000c778  test    rcx, rcx
0x18000c77b  jz      short loc_18000C783
0x18000c77d  call    cs:__imp_MesHandleFree
0x18000c783  test    ebx, ebx
0x18000c785  jns     short loc_18000C7D8
0x18000c787  xor     edx, edx; Val
0x18000c789  mov     qword ptr [rsi+88h], 0
0x18000c794  mov     rcx, rbp; void *
0x18000c797  mov     qword ptr [rsi+8], 0
0x18000c79f  mov     dword ptr [rsi+10h], 0
0x18000c7a6  mov     dword ptr [rsi+90h], 0
0x18000c7b0  lea     r8d, [rdx+70h]; Size
0x18000c7b4  call    memset_0
0x18000c7b9  mov     rcx, rdi; pv
0x18000c7bc  call    cs:__imp_CoTaskMemFree
0x18000c7c2  mov     eax, ebx
0x18000c7c4  mov     rbx, [rsp+38h+arg_8]
0x18000c7c9  add     rsp, 20h
0x18000c7cd  pop     rdi
0x18000c7ce  pop     rsi
0x18000c7cf  pop     rbp
0x18000c7d0  retn
0x18000c7d1  mov     ebx, 8007000Eh
0x18000c7d6  jmp     short loc_18000C7B9
0x18000c7d8  xor     eax, eax
0x18000c7da  jmp     short loc_18000C7C4
```
