# CNetDiagClient::ExtractRootCauseInfo(void *,CRootCauseInfo *)

- ea: `0x18000c7e4`
- end: `0x18000c8f3`
- name: `?ExtractRootCauseInfo@CNetDiagClient@@IEAAJPEAXPEAVCRootCauseInfo@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this, void *, struct CRootCauseInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e2d4`

## callees

- `0x18000c7e4`
- `0x18001bfa0`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000c82a`
- `ole32!CoTaskMemAlloc` at `0x18000c82a`
- `ole32!CoTaskMemFree` at `0x18000c8d3`
- `ole32!CoTaskMemFree` at `0x18000c8d3`
- `wdi!WdiGetParameterDataLength` at `0x18000c80c`
- `wdi!WdiGetParameterDataLength` at `0x18000c80c`
- `wdi!WdiGetParameterData` at `0x18000c847`
- `wdi!WdiGetParameterData` at `0x18000c847`
- `RPCRT4!MesHandleFree` at `0x18000c8a9`
- `RPCRT4!MesHandleFree` at `0x18000c8a9`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000c86f`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000c86f`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::ExtractRootCauseInfo(CNetDiagClient *this, void *a2, struct CRootCauseInfo *a3)
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
      ParameterDataLength = Protected_RootCauseInfo_Decode(pHandle, (char *)a3 + 24);
    }
    if ( pHandle )
      MesHandleFree(pHandle);
    if ( ParameterDataLength < 0 )
    {
      *((_QWORD *)a3 + 1) = 0;
      *((_DWORD *)a3 + 4) = 0;
      memset_0(v10, 0, 0x40u);
      goto LABEL_14;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c7e4  mov     rax, rsp
0x18000c7e7  mov     [rax+10h], rbx
0x18000c7eb  mov     [rax+8], rcx
0x18000c7ef  push    rbp
0x18000c7f0  push    rsi
0x18000c7f1  push    rdi
0x18000c7f2  sub     rsp, 20h
0x18000c7f6  mov     rbp, rdx
0x18000c7f9  mov     dword ptr [rax+8], 0
0x18000c800  mov     rcx, rbp
0x18000c803  lea     rdx, [rax+8]
0x18000c807  mov     rsi, r8
0x18000c80a  xor     edi, edi
0x18000c80c  call    cs:__imp_WdiGetParameterDataLength
0x18000c812  mov     ebx, eax
0x18000c814  test    eax, eax
0x18000c816  js      loc_18000C8D0
0x18000c81c  mov     eax, dword ptr [rsp+38h+cb]
0x18000c820  test    eax, eax
0x18000c822  jz      loc_18000C8EF
0x18000c828  mov     ecx, eax; cb
0x18000c82a  call    cs:__imp_CoTaskMemAlloc
0x18000c830  mov     rdi, rax
0x18000c833  test    rax, rax
0x18000c836  jz      loc_18000C8E8
0x18000c83c  mov     r8d, dword ptr [rsp+38h+cb]
0x18000c841  mov     rdx, rax
0x18000c844  mov     rcx, rbp
0x18000c847  call    cs:__imp_WdiGetParameterData
0x18000c84d  mov     ebx, eax
0x18000c84f  test    eax, eax
0x18000c851  js      short loc_18000C8D0
0x18000c853  mov     edx, dword ptr [rsp+38h+cb]; BufferSize
0x18000c857  lea     r8, [rsp+38h+pHandle]; pHandle
0x18000c85c  mov     rcx, rdi; Buffer
0x18000c85f  mov     [rsi+10h], edx
0x18000c862  mov     [rsi+8], rdi
0x18000c866  mov     [rsp+38h+pHandle], 0
0x18000c86f  call    cs:__imp_MesDecodeBufferHandleCreate
0x18000c875  mov     ebx, eax
0x18000c877  test    eax, eax
0x18000c879  jz      short loc_18000C88C
0x18000c87b  jle     short loc_18000C886
0x18000c87d  movzx   ebx, ax
0x18000c880  or      ebx, 80070000h
0x18000c886  lea     rbp, [rsi+18h]
0x18000c88a  jmp     short loc_18000C89F
0x18000c88c  mov     rcx, [rsp+38h+pHandle]
0x18000c891  lea     rbp, [rsi+18h]
0x18000c895  mov     rdx, rbp
0x18000c898  call    Protected_RootCauseInfo_Decode
0x18000c89d  mov     ebx, eax
0x18000c89f  mov     rcx, [rsp+38h+pHandle]; Handle
0x18000c8a4  test    rcx, rcx
0x18000c8a7  jz      short loc_18000C8AF
0x18000c8a9  call    cs:__imp_MesHandleFree
0x18000c8af  test    ebx, ebx
0x18000c8b1  jns     short loc_18000C8EF
0x18000c8b3  xor     edx, edx; Val
0x18000c8b5  mov     qword ptr [rsi+8], 0
0x18000c8bd  mov     rcx, rbp; void *
0x18000c8c0  mov     dword ptr [rsi+10h], 0
0x18000c8c7  lea     r8d, [rdx+40h]; Size
0x18000c8cb  call    memset_0
0x18000c8d0  mov     rcx, rdi; pv
0x18000c8d3  call    cs:__imp_CoTaskMemFree
0x18000c8d9  mov     eax, ebx
0x18000c8db  mov     rbx, [rsp+38h+arg_8]
0x18000c8e0  add     rsp, 20h
0x18000c8e4  pop     rdi
0x18000c8e5  pop     rsi
0x18000c8e6  pop     rbp
0x18000c8e7  retn
0x18000c8e8  mov     ebx, 8007000Eh
0x18000c8ed  jmp     short loc_18000C8D0
0x18000c8ef  xor     eax, eax
0x18000c8f1  jmp     short loc_18000C8DB
```
