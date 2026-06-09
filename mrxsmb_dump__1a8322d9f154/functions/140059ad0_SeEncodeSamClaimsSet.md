# SeEncodeSamClaimsSet

- ea: `0x140059ad0`
- end: `0x140059c9a`
- name: `SeEncodeSamClaimsSet`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400598a4`

## callees

- `0x14004aae0`
- `0x140059ad0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140059ba7`
- `ntoskrnl!ExAllocatePool2` at `0x140059ba7`
- `msrpc!I_RpcExceptionFilter` at `0x14005a9b0`
- `msrpc!I_RpcExceptionFilter` at `0x14005a9d2`
- `msrpc!I_RpcExceptionFilter` at `0x14005a9b0`
- `msrpc!I_RpcExceptionFilter` at `0x14005a9d2`
- `msrpc!MesHandleFree` at `0x140059c7e`
- `msrpc!MesHandleFree` at `0x140059c7e`
- `msrpc!NdrMesTypeEncode3` at `0x140059c2f`
- `msrpc!NdrMesTypeEncode3` at `0x140059c2f`
- `msrpc!MesEncodeDynBufferHandleCreate` at `0x140059b20`
- `msrpc!MesEncodeDynBufferHandleCreate` at `0x140059b20`
- `msrpc!NdrMesTypeAlignSize3` at `0x140059b61`
- `msrpc!NdrMesTypeAlignSize3` at `0x140059b61`
- `msrpc!MesBufferHandleReset` at `0x140059bf2`
- `msrpc!MesBufferHandleReset` at `0x140059bf2`

## pseudocode

```c
__int64 __fastcall SeEncodeSamClaimsSet(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  void *v5; // rsi
  __int64 v6; // r12
  __int64 Pool2; // rax
  unsigned int v8; // ebx
  __int64 v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+38h] [rbp-40h] BYREF
  __int64 v12; // [rsp+40h] [rbp-38h]
  __int64 v13; // [rsp+48h] [rbp-30h]
  __int64 v14; // [rsp+80h] [rbp+8h] BYREF
  _DWORD *v15; // [rsp+88h] [rbp+10h]
  _QWORD *v16; // [rsp+90h] [rbp+18h]
  int v17; // [rsp+98h] [rbp+20h] BYREF

  v16 = a3;
  v15 = a2;
  v14 = a1;
  v11 = 0;
  v17 = 0;
  v5 = 0;
  v12 = 0;
  v13 = 0;
  v10 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( !(unsigned int)MesEncodeDynBufferHandleCreate(&v11, &v17, &v10) )
  {
    v6 = NdrMesTypeAlignSize3(v10, "TP 3\a", &off_140062488, &off_1400701A8, 0, &v14);
    v13 = v6;
    Pool2 = ExAllocatePool2(66, v6, 1834185815);
    v5 = (void *)Pool2;
    v12 = Pool2;
    if ( !Pool2 )
    {
      v8 = -1073741801;
      goto LABEL_8;
    }
    v11 = Pool2;
    v8 = MesBufferHandleReset(v10, 1, 0, &v11, v6, &v17);
    if ( !v8 )
    {
      NdrMesTypeEncode3(v10, "TP 3\a", &off_140062488, &off_1400701A8, 0, &v14);
      *a3 = v5;
      *a2 = v17;
      goto LABEL_11;
    }
  }
  v8 = -1073741823;
LABEL_8:
  if ( v5 )
    MIDL_user_free(v5);
LABEL_11:
  MesHandleFree(v10);
  return v8;
}

```

## disassembly

```asm
0x140059ad0  mov     rax, rsp
0x140059ad3  mov     [rax+18h], r8
0x140059ad7  mov     [rax+10h], rdx
0x140059adb  mov     [rax+8], rcx
0x140059adf  push    rbx
0x140059ae0  push    rsi
0x140059ae1  push    r12
0x140059ae3  push    r14
0x140059ae5  push    r15
0x140059ae7  sub     rsp, 50h
0x140059aeb  mov     r14, r8
0x140059aee  mov     r15, rdx
0x140059af1  mov     qword ptr [rax-40h], 0
0x140059af9  mov     dword ptr [rax+20h], 0
0x140059b00  xor     esi, esi
0x140059b02  mov     [rsp+78h+var_38], rsi
0x140059b07  mov     [rax-30h], rsi
0x140059b0b  mov     [rax-48h], rsi
0x140059b0f  mov     [rdx], esi
0x140059b11  mov     [r8], rsi
0x140059b14  lea     r8, [rax-48h]
0x140059b18  lea     rdx, [rax+20h]
0x140059b1c  lea     rcx, [rax-40h]
0x140059b20  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x140059b27  nop     dword ptr [rax+rax+00h]
0x140059b2c  mov     ebx, eax
0x140059b2e  test    eax, eax
0x140059b30  jnz     loc_140059C58
0x140059b36  lea     rax, [rsp+78h+arg_0]
0x140059b3e  mov     [rsp+78h+var_50], rax
0x140059b43  mov     [rsp+78h+var_58], ebx
0x140059b47  lea     r9, off_1400701A8
0x140059b4e  lea     r8, off_140062488
0x140059b55  lea     rdx, aTp3; "TP 3\a"
0x140059b5c  mov     rcx, [rsp+78h+var_48]
0x140059b61  call    cs:__imp_NdrMesTypeAlignSize3
0x140059b68  nop     dword ptr [rax+rax+00h]
0x140059b6d  mov     r12, rax
0x140059b70  mov     [rsp+78h+var_30], rax
0x140059b75  jmp     short loc_140059B93
0x140059b77  mov     ebx, eax
0x140059b79  mov     r14, [rsp+78h+arg_10]
0x140059b81  mov     r15, [rsp+78h+arg_8]
0x140059b89  mov     rsi, [rsp+78h+var_38]
0x140059b8e  mov     r12, [rsp+78h+var_30]
0x140059b93  test    ebx, ebx
0x140059b95  jnz     loc_140059C58
0x140059b9b  mov     r8d, 6D537457h
0x140059ba1  mov     rdx, r12
0x140059ba4  lea     ecx, [rbx+42h]
0x140059ba7  call    cs:__imp_ExAllocatePool2
0x140059bae  nop     dword ptr [rax+rax+00h]
0x140059bb3  mov     rsi, rax
0x140059bb6  mov     [rsp+78h+var_38], rax
0x140059bbb  test    rax, rax
0x140059bbe  jnz     short loc_140059BCA
0x140059bc0  mov     ebx, 0C0000017h
0x140059bc5  jmp     loc_140059C5D
0x140059bca  mov     [rsp+78h+var_40], rax
0x140059bcf  lea     rax, [rsp+78h+arg_18]
0x140059bd7  mov     [rsp+78h+var_50], rax
0x140059bdc  mov     [rsp+78h+var_58], r12d
0x140059be1  lea     r9, [rsp+78h+var_40]
0x140059be6  xor     r8d, r8d
0x140059be9  lea     edx, [r8+1]
0x140059bed  mov     rcx, [rsp+78h+var_48]
0x140059bf2  call    cs:__imp_MesBufferHandleReset
0x140059bf9  nop     dword ptr [rax+rax+00h]
0x140059bfe  mov     ebx, eax
0x140059c00  test    eax, eax
0x140059c02  jnz     short loc_140059C58
0x140059c04  lea     rax, [rsp+78h+arg_0]
0x140059c0c  mov     [rsp+78h+var_50], rax
0x140059c11  mov     [rsp+78h+var_58], ebx
0x140059c15  lea     r9, off_1400701A8
0x140059c1c  lea     r8, off_140062488
0x140059c23  lea     rdx, aTp3; "TP 3\a"
0x140059c2a  mov     rcx, [rsp+78h+var_48]
0x140059c2f  call    cs:__imp_NdrMesTypeEncode3
0x140059c36  nop     dword ptr [rax+rax+00h]
0x140059c3b  jmp     short loc_140059C54
0x140059c3d  mov     ebx, eax
0x140059c3f  mov     r14, [rsp+78h+arg_10]
0x140059c47  mov     r15, [rsp+78h+arg_8]
0x140059c4f  mov     rsi, [rsp+78h+var_38]
0x140059c54  test    ebx, ebx
0x140059c56  jz      short loc_140059C6C
0x140059c58  mov     ebx, 0C0000001h
0x140059c5d  test    rsi, rsi
0x140059c60  jz      short loc_140059C79
0x140059c62  mov     rcx, rsi; void *
0x140059c65  call    MIDL_user_free
0x140059c6a  jmp     short loc_140059C79
0x140059c6c  mov     [r14], rsi
0x140059c6f  mov     eax, [rsp+78h+arg_18]
0x140059c76  mov     [r15], eax
0x140059c79  mov     rcx, [rsp+78h+var_48]
0x140059c7e  call    cs:__imp_MesHandleFree
0x140059c85  nop     dword ptr [rax+rax+00h]
0x140059c8a  mov     eax, ebx
0x140059c8c  add     rsp, 50h
0x140059c90  pop     r15
0x140059c92  pop     r14
0x140059c94  pop     r12
0x140059c96  pop     rsi
0x140059c97  pop     rbx
0x140059c98  retn
0x14005a9a2  push    rbp
0x14005a9a4  sub     rsp, 30h
0x14005a9a8  mov     rbp, rdx
0x14005a9ab  mov     rcx, [rcx]
0x14005a9ae  mov     ecx, [rcx]; ExceptionCode
0x14005a9b0  call    cs:__imp_I_RpcExceptionFilter
0x14005a9b7  nop     dword ptr [rax+rax+00h]
0x14005a9bc  nop
0x14005a9bd  add     rsp, 30h
0x14005a9c1  pop     rbp
0x14005a9c2  retn
0x14005a9c4  push    rbp
0x14005a9c6  sub     rsp, 30h
0x14005a9ca  mov     rbp, rdx
0x14005a9cd  mov     rcx, [rcx]
0x14005a9d0  mov     ecx, [rcx]; ExceptionCode
0x14005a9d2  call    cs:__imp_I_RpcExceptionFilter
0x14005a9d9  nop     dword ptr [rax+rax+00h]
0x14005a9de  nop
0x14005a9df  add     rsp, 30h
0x14005a9e3  pop     rbp
0x14005a9e4  retn
```
