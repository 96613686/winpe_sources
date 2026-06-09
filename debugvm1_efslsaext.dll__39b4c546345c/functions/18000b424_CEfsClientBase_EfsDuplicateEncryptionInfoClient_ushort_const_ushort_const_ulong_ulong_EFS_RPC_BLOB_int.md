# CEfsClientBase::EfsDuplicateEncryptionInfoClient(ushort const *,ushort const *,ulong,ulong,_EFS_RPC_BLOB *,int)

- ea: `0x18000b424`
- end: `0x18000b7ff`
- name: `?EfsDuplicateEncryptionInfoClient@CEfsClientBase@@QEAAKPEBG0KKPEAU_EFS_RPC_BLOB@@H@Z`
- size: `987`
- prototype: `unsigned int(CEfsClientBase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, struct _EFS_RPC_BLOB *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180007590`

## callees

- `0x18000ade8`
- `0x18000b424`
- `0x18000c530`
- `0x18000d700`
- `0x18000e14c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b650`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b650`
- `ntdll!RtlFreeHeap` at `0x18000b775`
- `ntdll!RtlFreeHeap` at `0x18000b79c`
- `ntdll!RtlFreeHeap` at `0x18000b7bd`
- `ntdll!RtlFreeHeap` at `0x18000b7e4`
- `ntdll!RtlFreeHeap` at `0x18000b775`
- `ntdll!RtlFreeHeap` at `0x18000b79c`
- `ntdll!RtlFreeHeap` at `0x18000b7bd`
- `ntdll!RtlFreeHeap` at `0x18000b7e4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000b754`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000b754`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b4a7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b4a7`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000b74c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000b74c`
- `RPCRT4!RpcBindingUnbind` at `0x18000b615`
- `RPCRT4!RpcBindingUnbind` at `0x18000b615`
- `RPCRT4!RpcBindingFree` at `0x18000b697`
- `RPCRT4!RpcBindingFree` at `0x18000b697`
- `RPCRT4!RpcBindingBind` at `0x18000b634`
- `RPCRT4!RpcBindingBind` at `0x18000b634`

## pseudocode

```c
__int64 __fastcall CEfsClientBase::EfsDuplicateEncryptionInfoClient(
        CEfsClientBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        struct _EFS_RPC_BLOB *a6,
        int a7)
{
  unsigned int FullName; // edi
  DWORD FileAttributesW; // eax
  bool v11; // zf
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // r14d
  int v15; // r15d
  struct _EFS_RPC_BLOB *v16; // r12
  CEfsClientBase *v17; // rcx
  __int64 v18; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE v21; // [rsp+60h] [rbp-68h] BYREF
  int v22; // [rsp+68h] [rbp-60h] BYREF
  PVOID P; // [rsp+70h] [rbp-58h] BYREF
  PVOID v24; // [rsp+78h] [rbp-50h] BYREF
  PVOID v25; // [rsp+80h] [rbp-48h] BYREF
  PVOID v26; // [rsp+88h] [rbp-40h] BYREF
  unsigned int v27; // [rsp+D0h] [rbp+8h]
  unsigned int v29; // [rsp+E8h] [rbp+20h] BYREF

  v22 = 0;
  Binding = 0;
  v25 = 0;
  v26 = 0;
  v24 = 0;
  P = 0;
  v29 = a4;
  v27 = 0;
  FullName = EfspGetFullName(
               a2,
               (unsigned __int16 **)&v24,
               (unsigned __int16 **)&v25,
               0,
               0,
               0,
               0,
               0,
               0,
               (int *)this + 2);
  if ( !FullName )
  {
    FileAttributesW = GetFileAttributesW(a2);
    if ( FileAttributesW != -1 )
    {
      v11 = (FileAttributesW & 0x10) == 0;
      v12 = 0;
      if ( !v11 )
        v12 = 2;
      v27 = v12;
    }
    v13 = 128;
    v14 = a5;
    if ( a5 )
      v13 = a5;
    v15 = a7;
    v16 = a6;
    FullName = EfspGetFullName(a3, (unsigned __int16 **)&P, (unsigned __int16 **)&v26, v27, &v29, v13, a6, a7, &v22, 0);
    if ( !FullName )
    {
      if ( !(unsigned int)EfspIsSrcDestSvrSame((wchar_t *)v25, (wchar_t *)v26) )
      {
        FullName = 87;
        goto LABEL_19;
      }
      if ( *(_WORD *)v25 != 46 || *((_WORD *)v25 + 1) )
      {
        FullName = (*(__int64 (__fastcall **)(CEfsClientBase *, PVOID, _QWORD, __int64, RPC_BINDING_HANDLE *))(*(_QWORD *)this + 16LL))(
                     this,
                     v25,
                     0,
                     1,
                     &Binding);
        if ( FullName )
          goto LABEL_19;
        v18 = (*(__int64 (__fastcall **)(CEfsClientBase *))(*(_QWORD *)this + 8LL))(this);
        FullName = (*(__int64 (__fastcall **)(RPC_BINDING_HANDLE, PVOID, PVOID, _QWORD, unsigned int, struct _EFS_RPC_BLOB *, int))(v18 + 88))(
                     Binding,
                     v24,
                     P,
                     v29,
                     v14,
                     v16,
                     v15);
      }
      else
      {
        FullName = CEfsClientBase::CreateLocalRpcBinding(v17, &Binding);
        if ( FullName )
          goto LABEL_19;
        LODWORD(v21) = 0;
        FullName = EfsRpcDuplicateEncryptionInfoFile(
                     (_DWORD)Binding,
                     (_DWORD)v24,
                     (_DWORD)P,
                     v29,
                     v14,
                     (__int64)v16,
                     v15);
      }
      v21 = Binding;
      if ( Binding )
        RpcBindingFree(&v21);
    }
  }
LABEL_19:
  if ( FullName && v22 )
  {
    if ( v27 == 2 )
      RemoveDirectoryW(a3);
    else
      DeleteFileW(a3);
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v26 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v26);
  if ( v24 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
  if ( v25 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
  return FullName;
}

```

## disassembly

```asm
0x18000b424  mov     r11, rsp
0x18000b427  mov     [r11+18h], r8
0x18000b42b  push    rbx
0x18000b42c  push    rsi
0x18000b42d  push    rdi
0x18000b42e  push    r12
0x18000b430  push    r13
0x18000b432  push    r14
0x18000b434  push    r15
0x18000b436  sub     rsp, 90h
0x18000b43d  mov     rsi, rdx
0x18000b440  mov     r13, rcx
0x18000b443  xor     ebx, ebx
0x18000b445  mov     [rsp+0C8h+var_60], ebx
0x18000b449  mov     [r11-70h], rbx
0x18000b44d  mov     [r11-48h], rbx
0x18000b451  mov     [r11-40h], rbx
0x18000b455  mov     [r11-50h], rbx
0x18000b459  mov     [r11-58h], rbx
0x18000b45d  mov     [r11+20h], r9d
0x18000b461  mov     [rsp+0C8h+arg_0], ebx
0x18000b468  lea     rax, [rcx+8]
0x18000b46c  mov     [r11-80h], rax
0x18000b470  mov     [rsp+0C8h+var_88], rbx; int *
0x18000b475  mov     [rsp+0C8h+var_90], ebx; int
0x18000b479  mov     [rsp+0C8h+var_98], rbx; void *
0x18000b47e  mov     [rsp+0C8h+var_A0], ebx; unsigned int
0x18000b482  mov     [rsp+0C8h+var_A8], rbx; unsigned int *
0x18000b487  xor     r9d, r9d; unsigned int
0x18000b48a  lea     r8, [r11-48h]; unsigned __int16 **
0x18000b48e  lea     rdx, [r11-50h]; unsigned __int16 **
0x18000b492  mov     rcx, rsi; unsigned __int16 *
0x18000b495  call    ?EfspGetFullName@@YAKPEBGPEAPEAG1KPEAKKPEAXHPEAH4@Z; EfspGetFullName(ushort const *,ushort * *,ushort * *,ulong,ulong *,ulong,void *,int,int *,int *)
0x18000b49a  mov     edi, eax
0x18000b49c  test    eax, eax
0x18000b49e  jnz     loc_18000B72C
0x18000b4a4  mov     rcx, rsi; lpFileName
0x18000b4a7  call    cs:__imp_GetFileAttributesW
0x18000b4ad  lea     esi, [rbx+2]
0x18000b4b0  cmp     eax, 0FFFFFFFFh
0x18000b4b3  jz      short loc_18000B4C3
0x18000b4b5  test    al, 10h
0x18000b4b7  mov     eax, ebx
0x18000b4b9  cmovnz  eax, esi
0x18000b4bc  mov     [rsp+0C8h+arg_0], eax
0x18000b4c3  mov     eax, 80h
0x18000b4c8  mov     r14d, [rsp+0C8h+arg_20]
0x18000b4d0  test    r14d, r14d
0x18000b4d3  cmovnz  eax, r14d
0x18000b4d7  mov     [rsp+0C8h+var_80], rbx; int *
0x18000b4dc  lea     rcx, [rsp+0C8h+var_60]
0x18000b4e1  mov     [rsp+0C8h+var_88], rcx; int *
0x18000b4e6  mov     r15d, [rsp+0C8h+arg_30]
0x18000b4ee  mov     [rsp+0C8h+var_90], r15d; int
0x18000b4f3  mov     r12, [rsp+0C8h+arg_28]
0x18000b4fb  mov     [rsp+0C8h+var_98], r12; void *
0x18000b500  mov     [rsp+0C8h+var_A0], eax; unsigned int
0x18000b504  lea     rax, [rsp+0C8h+arg_18]
0x18000b50c  mov     [rsp+0C8h+var_A8], rax; unsigned int *
0x18000b511  mov     r9d, [rsp+0C8h+arg_0]; unsigned int
0x18000b519  lea     r8, [rsp+0C8h+var_40]; unsigned __int16 **
0x18000b521  lea     rdx, [rsp+0C8h+P]; unsigned __int16 **
0x18000b526  mov     rcx, [rsp+0C8h+lpPathName]; unsigned __int16 *
0x18000b52e  call    ?EfspGetFullName@@YAKPEBGPEAPEAG1KPEAKKPEAXHPEAH4@Z; EfspGetFullName(ushort const *,ushort * *,ushort * *,ulong,ulong *,ulong,void *,int,int *,int *)
0x18000b533  mov     edi, eax
0x18000b535  test    eax, eax
0x18000b537  jnz     loc_18000B731
0x18000b53d  mov     rdx, [rsp+0C8h+var_40]; String1
0x18000b545  mov     rcx, [rsp+0C8h+var_48]; String2
0x18000b54d  call    ?EfspIsSrcDestSvrSame@@YAHPEBG0@Z; EfspIsSrcDestSvrSame(ushort const *,ushort const *)
0x18000b552  test    eax, eax
0x18000b554  jz      loc_18000B725
0x18000b55a  mov     rdx, [rsp+0C8h+var_48]
0x18000b562  cmp     word ptr [rdx], 2Eh ; '.'
0x18000b566  jnz     loc_18000B6A2
0x18000b56c  cmp     [rdx+2], bx
0x18000b570  jnz     loc_18000B6A2
0x18000b576  lea     rdx, [rsp+0C8h+Binding]; void **
0x18000b57b  call    ?CreateLocalRpcBinding@CEfsClientBase@@IEAAKPEAPEAX@Z; CEfsClientBase::CreateLocalRpcBinding(void * *)
0x18000b580  mov     edi, eax
0x18000b582  test    eax, eax
0x18000b584  jnz     loc_18000B731
0x18000b58a  mov     eax, ebx
0x18000b58c  mov     dword ptr [rsp+0C8h+var_68], eax
0x18000b590  cmp     eax, 3
0x18000b593  jnb     loc_18000B67F
0x18000b599  mov     dword ptr [rsp+0C8h+var_98], r15d
0x18000b59e  mov     qword ptr [rsp+0C8h+var_A0], r12
0x18000b5a3  mov     dword ptr [rsp+0C8h+var_A8], r14d
0x18000b5a8  mov     r9d, [rsp+0C8h+arg_18]
0x18000b5b0  mov     r8, [rsp+0C8h+P]
0x18000b5b5  mov     rdx, [rsp+0C8h+var_50]
0x18000b5ba  mov     rcx, [rsp+0C8h+Binding]
0x18000b5bf  call    EfsRpcDuplicateEncryptionInfoFile
0x18000b5c4  mov     edi, eax
0x18000b5c6  mov     [rsp+0C8h+var_78], eax
0x18000b5ca  jmp     loc_18000B67F
0x18000b5cf  mov     edi, eax
0x18000b5d1  mov     [rsp+0C8h+var_78], eax
0x18000b5d5  xor     cl, cl
0x18000b5d7  add     eax, 0FFFFF954h
0x18000b5dc  cmp     eax, 2Dh ; '-'
0x18000b5df  ja      short loc_18000B5F5
0x18000b5e1  mov     rdx, 2000000C4201h
0x18000b5eb  bt      rdx, rax
0x18000b5ef  jnb     short loc_18000B5F5
0x18000b5f1  mov     cl, 1
0x18000b5f3  jmp     short loc_18000B60C
0x18000b5f5  cmp     edi, 6BBh
0x18000b5fb  jz      short loc_18000B60C
0x18000b5fd  cmp     edi, 5B4h
0x18000b603  jz      short loc_18000B60C
0x18000b605  xor     ebx, ebx
0x18000b607  lea     esi, [rbx+2]
0x18000b60a  jmp     short loc_18000B67F
0x18000b60c  test    cl, cl
0x18000b60e  jz      short loc_18000B64B
0x18000b610  mov     rcx, [rsp+0C8h+Binding]; Binding
0x18000b615  call    cs:__imp_RpcBindingUnbind
0x18000b61b  test    eax, eax
0x18000b61d  jz      short loc_18000B626
0x18000b61f  xor     ebx, ebx
0x18000b621  lea     esi, [rbx+2]
0x18000b624  jmp     short loc_18000B67F
0x18000b626  lea     r8, qword_180016C60; IfSpec
0x18000b62d  mov     rdx, [rsp+0C8h+Binding]; Binding
0x18000b632  xor     ecx, ecx; pAsync
0x18000b634  call    cs:__imp_RpcBindingBind
0x18000b63a  mov     edi, eax
0x18000b63c  mov     [rsp+0C8h+var_78], eax
0x18000b640  test    eax, eax
0x18000b642  jns     short loc_18000B64B
0x18000b644  xor     ebx, ebx
0x18000b646  lea     esi, [rbx+2]
0x18000b649  jmp     short loc_18000B67F
0x18000b64b  mov     ecx, 12Ch; dwMilliseconds
0x18000b650  call    cs:__imp_Sleep
0x18000b656  nop
0x18000b657  mov     eax, dword ptr [rsp+0C8h+var_68]
0x18000b65b  inc     eax
0x18000b65d  xor     ebx, ebx
0x18000b65f  lea     esi, [rbx+2]
0x18000b662  mov     r15d, [rsp+0C8h+arg_30]
0x18000b66a  mov     r12, [rsp+0C8h+arg_28]
0x18000b672  mov     r14d, [rsp+0C8h+arg_20]
0x18000b67a  jmp     loc_18000B58C
0x18000b67f  mov     rax, [rsp+0C8h+Binding]
0x18000b684  mov     [rsp+0C8h+var_68], rax
0x18000b689  test    rax, rax
0x18000b68c  jz      loc_18000B731
0x18000b692  lea     rcx, [rsp+0C8h+var_68]; Binding
0x18000b697  call    cs:__imp_RpcBindingFree
0x18000b69d  jmp     loc_18000B731
0x18000b6a2  mov     rax, [r13+0]
0x18000b6a6  lea     rcx, [rsp+0C8h+Binding]
0x18000b6ab  mov     [rsp+0C8h+var_A8], rcx
0x18000b6b0  mov     r9d, 1
0x18000b6b6  xor     r8d, r8d
0x18000b6b9  mov     rcx, r13
0x18000b6bc  mov     rax, [rax+10h]
0x18000b6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c5  mov     edi, eax
0x18000b6c7  test    eax, eax
0x18000b6c9  jnz     short loc_18000B731
0x18000b6cb  mov     rax, [r13+0]
0x18000b6cf  mov     rcx, r13
0x18000b6d2  mov     rax, [rax+8]
0x18000b6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6db  mov     dword ptr [rsp+0C8h+var_98], r15d
0x18000b6e0  mov     qword ptr [rsp+0C8h+var_A0], r12
0x18000b6e5  mov     dword ptr [rsp+0C8h+var_A8], r14d
0x18000b6ea  mov     r9d, [rsp+0C8h+arg_18]
0x18000b6f2  mov     r8, [rsp+0C8h+P]
0x18000b6f7  mov     rdx, [rsp+0C8h+var_50]
0x18000b6fc  mov     rcx, [rsp+0C8h+Binding]
0x18000b701  mov     rax, [rax+58h]
0x18000b705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b70a  mov     edi, eax
0x18000b70c  mov     [rsp+0C8h+var_78], eax
0x18000b710  jmp     loc_18000B67F
0x18000b715  mov     edi, eax
0x18000b717  mov     [rsp+0C8h+var_78], eax
0x18000b71b  xor     ebx, ebx
0x18000b71d  lea     esi, [rbx+2]
0x18000b720  jmp     loc_18000B67F
0x18000b725  mov     edi, 57h ; 'W'
0x18000b72a  jmp     short loc_18000B731
0x18000b72c  mov     esi, 2
0x18000b731  test    edi, edi
0x18000b733  jz      short loc_18000B75A
0x18000b735  cmp     [rsp+0C8h+var_60], ebx
0x18000b739  jz      short loc_18000B75A
0x18000b73b  mov     rcx, [rsp+0C8h+lpPathName]; lpFileName
0x18000b743  cmp     [rsp+0C8h+arg_0], esi
0x18000b74a  jnz     short loc_18000B754
0x18000b74c  call    cs:__imp_RemoveDirectoryW
0x18000b752  jmp     short loc_18000B75A
0x18000b754  call    cs:__imp_DeleteFileW
0x18000b75a  cmp     [rsp+0C8h+P], rbx
0x18000b75f  jz      short loc_18000B77B
0x18000b761  mov     rcx, gs:60h
0x18000b76a  mov     r8, [rsp+0C8h+P]; P
0x18000b76f  xor     edx, edx; Flags
0x18000b771  mov     rcx, [rcx+30h]; HeapHandle
0x18000b775  call    cs:__imp_RtlFreeHeap
0x18000b77b  cmp     [rsp+0C8h+var_40], rbx
0x18000b783  jz      short loc_18000B7A2
0x18000b785  mov     rcx, gs:60h
0x18000b78e  mov     r8, [rsp+0C8h+var_40]; P
0x18000b796  xor     edx, edx; Flags
0x18000b798  mov     rcx, [rcx+30h]; HeapHandle
0x18000b79c  call    cs:__imp_RtlFreeHeap
0x18000b7a2  cmp     [rsp+0C8h+var_50], rbx
0x18000b7a7  jz      short loc_18000B7C3
0x18000b7a9  mov     rcx, gs:60h
0x18000b7b2  mov     r8, [rsp+0C8h+var_50]; P
0x18000b7b7  xor     edx, edx; Flags
0x18000b7b9  mov     rcx, [rcx+30h]; HeapHandle
0x18000b7bd  call    cs:__imp_RtlFreeHeap
0x18000b7c3  cmp     [rsp+0C8h+var_48], rbx
0x18000b7cb  jz      short loc_18000B7EA
0x18000b7cd  mov     rcx, gs:60h
0x18000b7d6  mov     r8, [rsp+0C8h+var_48]; P
0x18000b7de  xor     edx, edx; Flags
0x18000b7e0  mov     rcx, [rcx+30h]; HeapHandle
0x18000b7e4  call    cs:__imp_RtlFreeHeap
0x18000b7ea  mov     eax, edi
0x18000b7ec  add     rsp, 90h
0x18000b7f3  pop     r15
0x18000b7f5  pop     r14
0x18000b7f7  pop     r13
0x18000b7f9  pop     r12
0x18000b7fb  pop     rdi
0x18000b7fc  pop     rsi
0x18000b7fd  pop     rbx
0x18000b7fe  retn
0x18001246a  push    rbp
0x18001246c  sub     rsp, 50h
0x180012470  mov     rbp, rdx
0x180012473  mov     rcx, [rcx]
0x180012476  mov     ecx, [rcx]; ExceptionCode
0x180012478  call    cs:__imp_RpcExceptionFilter
0x18001247e  nop
0x18001247f  add     rsp, 50h
0x180012483  pop     rbp
0x180012484  retn
0x180012486  push    rbp
0x180012488  sub     rsp, 50h
0x18001248c  mov     rbp, rdx
0x18001248f  mov     rcx, [rcx]
0x180012492  mov     ecx, [rcx]; ExceptionCode
0x180012494  call    cs:__imp_I_RpcExceptionFilter
0x18001249a  nop
0x18001249b  add     rsp, 50h
0x18001249f  pop     rbp
0x1800124a0  retn
```
