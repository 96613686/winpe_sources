# EncodeBlob(_ENCODE_OBJECT *,ulong *,void * *)

- ea: `0x18005f5b8`
- end: `0x18005f6a8`
- name: `?EncodeBlob@@YAJPEAU_ENCODE_OBJECT@@PEAKPEAPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(struct _ENCODE_OBJECT *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180059d7c`

## callees

- `0x180009590`
- `0x18005f5b8`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x180080c90`
- `RPCRT4!RpcExceptionFilter` at `0x180080c90`
- `RPCRT4!MesHandleFree` at `0x18005f67e`
- `RPCRT4!MesHandleFree` at `0x18005f67e`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18005f601`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18005f601`
- `RPCRT4!NdrMesTypeEncode3` at `0x18005f64c`
- `RPCRT4!NdrMesTypeEncode3` at `0x18005f64c`

## pseudocode

```c
__int64 __fastcall EncodeBlob(struct _ENCODE_OBJECT *a1, unsigned int *a2, wil::details **a3)
{
  RPC_STATUS v6; // eax
  void *v7; // rdx
  signed int v8; // ebx
  struct _ENCODE_OBJECT *pObject; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+10h] BYREF
  handle_t Handle; // [rsp+70h] [rbp+18h] BYREF
  wil::details *v13; // [rsp+78h] [rbp+20h] BYREF

  Handle = 0;
  v13 = 0;
  v11 = 0;
  *a2 = 0;
  *a3 = 0;
  v6 = MesEncodeDynBufferHandleCreate((char **)&v13, &v11, &Handle);
  v8 = v6;
  if ( v6 >= 1 )
    v8 = (unsigned __int16)v6 | 0x80010000;
  if ( v8 >= 0 )
  {
    pObject = a1;
    NdrMesTypeEncode3(Handle, &stru_180094728, &stru_180089A90, (const unsigned int **)&off_1800A3070, 0, &pObject);
    *a2 = v11;
    *a3 = v13;
  }
  if ( Handle )
    MesHandleFree(Handle);
  if ( v8 < 0 && v13 )
    wil::details::FreeProcessHeap(v13, v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005f5b8  mov     rax, rsp
0x18005f5bb  mov     [rax+8], rbx
0x18005f5bf  push    rsi
0x18005f5c0  push    r14
0x18005f5c2  push    r15
0x18005f5c4  sub     rsp, 40h
0x18005f5c8  mov     rsi, r8
0x18005f5cb  mov     r14, rdx
0x18005f5ce  mov     r15, rcx
0x18005f5d1  mov     qword ptr [rax+18h], 0
0x18005f5d9  mov     qword ptr [rax+20h], 0
0x18005f5e1  mov     dword ptr [rax+10h], 0
0x18005f5e8  mov     dword ptr [rdx], 0
0x18005f5ee  mov     qword ptr [r8], 0
0x18005f5f5  lea     r8, [rax+18h]; pHandle
0x18005f5f9  lea     rdx, [rax+10h]; pEncodedSize
0x18005f5fd  lea     rcx, [rax+20h]; pBuffer
0x18005f601  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18005f607  mov     ebx, eax
0x18005f609  cmp     eax, 1
0x18005f60c  jl      short loc_18005F617
0x18005f60e  movzx   ebx, ax
0x18005f611  or      ebx, 80010000h
0x18005f617  test    ebx, ebx
0x18005f619  js      short loc_18005F674
0x18005f61b  mov     [rsp+58h+var_28], r15
0x18005f620  lea     rax, [rsp+58h+var_28]
0x18005f625  mov     [rsp+58h+pObject], rax; pObject
0x18005f62a  mov     [rsp+58h+nTypeIndex], 0; nTypeIndex
0x18005f632  lea     r9, off_1800A3070; ArrTypeOffset
0x18005f639  lea     r8, stru_180089A90; pProxyInfo
0x18005f640  lea     rdx, stru_180094728; pPicklingInfo
0x18005f647  mov     rcx, [rsp+58h+Handle]; Handle
0x18005f64c  call    cs:__imp_NdrMesTypeEncode3
0x18005f652  nop
0x18005f653  mov     eax, [rsp+58h+arg_8]
0x18005f657  mov     [r14], eax
0x18005f65a  mov     rax, [rsp+58h+arg_18]
0x18005f65f  mov     [rsi], rax
0x18005f662  jmp     short loc_18005F674
0x18005f664  mov     ebx, eax
0x18005f666  cmp     eax, 1
0x18005f669  jl      short loc_18005F674
0x18005f66b  movzx   ebx, ax
0x18005f66e  or      ebx, 80010000h
0x18005f674  mov     rcx, [rsp+58h+Handle]; Handle
0x18005f679  test    rcx, rcx
0x18005f67c  jz      short loc_18005F684
0x18005f67e  call    cs:__imp_MesHandleFree
0x18005f684  test    ebx, ebx
0x18005f686  jns     short loc_18005F697
0x18005f688  mov     rcx, [rsp+58h+arg_18]; this
0x18005f68d  test    rcx, rcx
0x18005f690  jz      short loc_18005F697
0x18005f692  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18005f697  mov     eax, ebx
0x18005f699  mov     rbx, [rsp+58h+arg_0]
0x18005f69e  add     rsp, 40h
0x18005f6a2  pop     r15
0x18005f6a4  pop     r14
0x18005f6a6  pop     rsi
0x18005f6a7  retn
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
