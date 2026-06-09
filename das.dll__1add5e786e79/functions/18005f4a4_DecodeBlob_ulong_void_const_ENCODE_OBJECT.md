# DecodeBlob(ulong,void const *,_ENCODE_OBJECT * *)

- ea: `0x18005f4a4`
- end: `0x18005f5b1`
- name: `?DecodeBlob@@YAJKPEBXPEAPEAU_ENCODE_OBJECT@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(size_t Size, void *Src, struct _ENCODE_OBJECT **pObject)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005ae54`

## callees

- `0x180009220`
- `0x180009590`
- `0x18005f4a4`
- `0x18007e9d8`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18005f59d`
- `RPCRT4!MesHandleFree` at `0x18005f59d`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18005f513`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18005f513`
- `RPCRT4!NdrMesTypeDecode3` at `0x18005f554`
- `RPCRT4!NdrMesTypeDecode3` at `0x18005f554`

## pseudocode

```c
__int64 __fastcall DecodeBlob(size_t Size, void *Src, struct _ENCODE_OBJECT **pObject)
{
  size_t v5; // rbx
  wil::details *v6; // rax
  void *v7; // rdx
  wil::details *v8; // rdi
  signed int v9; // ebx
  char *v10; // rcx
  RPC_STATUS v11; // eax
  bool v12; // zf
  handle_t pHandle; // [rsp+68h] [rbp+10h] BYREF
  struct _ENCODE_OBJECT **v15; // [rsp+70h] [rbp+18h]
  wil::details *v16; // [rsp+78h] [rbp+20h]

  v15 = pObject;
  v5 = (unsigned int)Size;
  pHandle = 0;
  *pObject = 0;
  if ( ((unsigned __int8)Src & 7) != 0 )
  {
    v6 = (wil::details *)DAF_user_alloc((unsigned int)Size);
    v8 = v6;
    v16 = v6;
    if ( !v6 )
    {
      v9 = -2147024882;
LABEL_10:
      v12 = v9 == 0;
      goto LABEL_11;
    }
    memcpy_0(v6, Src, v5);
    v10 = (char *)v8;
  }
  else
  {
    v8 = 0;
    v16 = 0;
    v10 = (char *)Src;
  }
  v11 = MesDecodeBufferHandleCreate(v10, v5, &pHandle);
  v9 = v11;
  if ( v11 >= 1 )
    v9 = (unsigned __int16)v11 | 0x80010000;
  v12 = v9 == 0;
  if ( v9 >= 0 )
  {
    NdrMesTypeDecode3(pHandle, &stru_180094728, &stru_180089A90, (const unsigned int **)&off_1800A3070, 0, pObject);
    goto LABEL_10;
  }
LABEL_11:
  if ( v12 && !*pObject )
    v9 = -2147024809;
  if ( v8 )
    wil::details::FreeProcessHeap(v8, v7);
  if ( pHandle )
    MesHandleFree(pHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005f4a4  mov     [rsp+arg_10], r8
0x18005f4a9  push    rbx
0x18005f4aa  push    rsi
0x18005f4ab  push    rdi
0x18005f4ac  push    r14
0x18005f4ae  push    r15
0x18005f4b0  sub     rsp, 30h
0x18005f4b4  mov     rsi, r8
0x18005f4b7  mov     r14, rdx
0x18005f4ba  mov     ebx, ecx
0x18005f4bc  mov     [rsp+58h+pHandle], 0
0x18005f4c5  mov     qword ptr [r8], 0
0x18005f4cc  test    dl, 7
0x18005f4cf  jz      short loc_18005F502
0x18005f4d1  mov     ecx, ebx
0x18005f4d3  call    DAF_user_alloc
0x18005f4d8  mov     rdi, rax
0x18005f4db  mov     [rsp+58h+arg_18], rax
0x18005f4e0  test    rax, rax
0x18005f4e3  jnz     short loc_18005F4EF
0x18005f4e5  mov     ebx, 8007000Eh
0x18005f4ea  jmp     loc_18005F576
0x18005f4ef  mov     r8, rbx; Size
0x18005f4f2  mov     rdx, r14; Src
0x18005f4f5  mov     rcx, rdi; void *
0x18005f4f8  call    memcpy_0
0x18005f4fd  mov     rcx, rdi
0x18005f500  jmp     short loc_18005F50C
0x18005f502  xor     edi, edi
0x18005f504  mov     [rsp+58h+arg_18], rdi
0x18005f509  mov     rcx, r14; Buffer
0x18005f50c  lea     r8, [rsp+58h+pHandle]; pHandle
0x18005f511  mov     edx, ebx; BufferSize
0x18005f513  call    cs:__imp_MesDecodeBufferHandleCreate
0x18005f519  cmp     eax, 1
0x18005f51c  mov     ebx, eax
0x18005f51e  jl      short loc_18005F529
0x18005f520  movzx   ebx, ax
0x18005f523  or      ebx, 80010000h
0x18005f529  test    ebx, ebx
0x18005f52b  js      short loc_18005F578
0x18005f52d  mov     [rsp+58h+pObject], rsi; pObject
0x18005f532  mov     [rsp+58h+nTypeIndex], 0; nTypeIndex
0x18005f53a  lea     r9, off_1800A3070; ArrTypeOffset
0x18005f541  lea     r8, stru_180089A90; pProxyInfo
0x18005f548  lea     rdx, stru_180094728; pPicklingInfo
0x18005f54f  mov     rcx, [rsp+58h+pHandle]; Handle
0x18005f554  call    cs:__imp_NdrMesTypeDecode3
0x18005f55a  jmp     short loc_18005F576
0x18005f55c  mov     ebx, eax
0x18005f55e  cmp     eax, 1
0x18005f561  jl      short loc_18005F56C
0x18005f563  movzx   ebx, ax
0x18005f566  or      ebx, 80010000h
0x18005f56c  mov     rsi, [rsp+58h+arg_10]
0x18005f571  mov     rdi, [rsp+58h+arg_18]
0x18005f576  test    ebx, ebx
0x18005f578  jnz     short loc_18005F586
0x18005f57a  mov     eax, 80070057h
0x18005f57f  cmp     qword ptr [rsi], 0
0x18005f583  cmovz   ebx, eax
0x18005f586  test    rdi, rdi
0x18005f589  jz      short loc_18005F593
0x18005f58b  mov     rcx, rdi; this
0x18005f58e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18005f593  mov     rcx, [rsp+58h+pHandle]; Handle
0x18005f598  test    rcx, rcx
0x18005f59b  jz      short loc_18005F5A3
0x18005f59d  call    cs:__imp_MesHandleFree
0x18005f5a3  mov     eax, ebx
0x18005f5a5  add     rsp, 30h
0x18005f5a9  pop     r15
0x18005f5ab  pop     r14
0x18005f5ad  pop     rdi
0x18005f5ae  pop     rsi
0x18005f5af  pop     rbx
0x18005f5b0  retn
0x180080c82  push    rbp
0x180080c84  sub     rsp, 30h
0x180080c88  mov     rbp, rdx
0x180080c8b  mov     rcx, [rcx]
0x180080c8e  mov     ecx, [rcx]; ExceptionCode
0x180080c90  call    cs:__imp_RpcExceptionFilter
0x180080c96  nop
0x180080c97  add     rsp, 30h
0x180080c9b  pop     rbp
0x180080c9c  retn
```
