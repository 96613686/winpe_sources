# ParameterToAttribute(void *,tagHELPER_ATTRIBUTE *)

- ea: `0x180006b60`
- end: `0x180006c3d`
- name: `?ParameterToAttribute@@YAJPEAXPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(void *, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800061c0`

## callees

- `0x180006b60`
- `0x18002b450`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180006be6`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180006be6`
- `RPCRT4!MesHandleFree` at `0x180006c18`
- `RPCRT4!MesHandleFree` at `0x180006c18`
- `wdi!WdiGetParameterData` at `0x180006bc5`
- `wdi!WdiGetParameterData` at `0x180006bc5`
- `wdi!WdiGetParameterDataLength` at `0x180006b91`
- `wdi!WdiGetParameterDataLength` at `0x180006b91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c21`

## pseudocode

```c
__int64 __fastcall ParameterToAttribute(void *a1, struct tagHELPER_ATTRIBUTE *a2)
{
  signed int ParameterDataLength; // ebx
  char *v5; // rax
  char *v6; // rdi
  RPC_STATUS v8; // eax
  SIZE_T cb; // [rsp+40h] [rbp+8h] BYREF
  handle_t pHandle; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(cb) = 0;
  if ( !a1 || !a2 )
    return 2147942487LL;
  ParameterDataLength = WdiGetParameterDataLength(a1, &cb);
  if ( ParameterDataLength >= 0 )
  {
    v5 = (char *)CoTaskMemAlloc((unsigned int)cb);
    v6 = v5;
    if ( !v5 )
      return 2147942414LL;
    ParameterDataLength = WdiGetParameterData(a1, v5, (unsigned int)cb);
    if ( ParameterDataLength >= 0 )
    {
      pHandle = 0;
      v8 = MesDecodeBufferHandleCreate(v6, cb, &pHandle);
      ParameterDataLength = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          ParameterDataLength = (unsigned __int16)v8 | 0x80070000;
      }
      else
      {
        ParameterDataLength = Protected_HELPER_ATTRIBUTE_Decode(pHandle, a2);
      }
      if ( pHandle )
        MesHandleFree(pHandle);
    }
    CoTaskMemFree(v6);
  }
  return (unsigned int)ParameterDataLength;
}

```

## disassembly

```asm
0x180006b60  mov     [rsp+arg_8], rbx
0x180006b65  push    rbp
0x180006b66  push    rsi
0x180006b67  push    rdi
0x180006b68  sub     rsp, 20h
0x180006b6c  mov     dword ptr [rsp+38h+cb], 0
0x180006b74  mov     rbp, rdx
0x180006b77  mov     rsi, rcx
0x180006b7a  test    rcx, rcx
0x180006b7d  jz      loc_180006C2B
0x180006b83  test    rdx, rdx
0x180006b86  jz      loc_180006C2B
0x180006b8c  lea     rdx, [rsp+38h+cb]
0x180006b91  call    cs:__imp_WdiGetParameterDataLength
0x180006b97  mov     ebx, eax
0x180006b99  test    eax, eax
0x180006b9b  js      loc_180006C27
0x180006ba1  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x180006ba5  call    cs:__imp_CoTaskMemAlloc
0x180006bab  mov     rdi, rax
0x180006bae  test    rax, rax
0x180006bb1  jnz     short loc_180006BBA
0x180006bb3  mov     eax, 8007000Eh
0x180006bb8  jmp     short loc_180006C30
0x180006bba  mov     r8d, dword ptr [rsp+38h+cb]
0x180006bbf  mov     rdx, rdi
0x180006bc2  mov     rcx, rsi
0x180006bc5  call    cs:__imp_WdiGetParameterData
0x180006bcb  mov     ebx, eax
0x180006bcd  test    eax, eax
0x180006bcf  js      short loc_180006C1E
0x180006bd1  mov     edx, dword ptr [rsp+38h+cb]; BufferSize
0x180006bd5  lea     r8, [rsp+38h+pHandle]; pHandle
0x180006bda  mov     rcx, rdi; Buffer
0x180006bdd  mov     [rsp+38h+pHandle], 0
0x180006be6  call    cs:__imp_MesDecodeBufferHandleCreate
0x180006bec  mov     ebx, eax
0x180006bee  test    eax, eax
0x180006bf0  jz      short loc_180006BFF
0x180006bf2  jle     short loc_180006C0E
0x180006bf4  movzx   ebx, ax
0x180006bf7  or      ebx, 80070000h
0x180006bfd  jmp     short loc_180006C0E
0x180006bff  mov     rcx, [rsp+38h+pHandle]
0x180006c04  mov     rdx, rbp
0x180006c07  call    Protected_HELPER_ATTRIBUTE_Decode
0x180006c0c  mov     ebx, eax
0x180006c0e  mov     rcx, [rsp+38h+pHandle]; Handle
0x180006c13  test    rcx, rcx
0x180006c16  jz      short loc_180006C1E
0x180006c18  call    cs:__imp_MesHandleFree
0x180006c1e  mov     rcx, rdi; pv
0x180006c21  call    cs:__imp_CoTaskMemFree
0x180006c27  mov     eax, ebx
0x180006c29  jmp     short loc_180006C30
0x180006c2b  mov     eax, 80070057h
0x180006c30  mov     rbx, [rsp+38h+arg_8]
0x180006c35  add     rsp, 20h
0x180006c39  pop     rdi
0x180006c3a  pop     rsi
0x180006c3b  pop     rbp
0x180006c3c  retn
```
