# CEfsClientBase::EfsRemoveUsersClient(ushort const *,_ENCRYPTION_CERTIFICATE_HASH_LIST *)

- ea: `0x18000c21c`
- end: `0x18000c45b`
- name: `?EfsRemoveUsersClient@CEfsClientBase@@QEAAKPEBGPEAU_ENCRYPTION_CERTIFICATE_HASH_LIST@@@Z`
- size: `575`
- prototype: `unsigned int(CEfsClientBase *__hidden this, const unsigned __int16 *, struct _ENCRYPTION_CERTIFICATE_HASH_LIST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007c20`

## callees

- `0x18000ade8`
- `0x18000c21c`
- `0x18000c760`
- `0x18000d700`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c35f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c35f`
- `ntdll!RtlFreeHeap` at `0x18000c421`
- `ntdll!RtlFreeHeap` at `0x18000c442`
- `ntdll!RtlFreeHeap` at `0x18000c421`
- `ntdll!RtlFreeHeap` at `0x18000c442`
- `RPCRT4!RpcBindingUnbind` at `0x18000c327`
- `RPCRT4!RpcBindingUnbind` at `0x18000c327`
- `RPCRT4!RpcExceptionFilter` at `0x180012478`
- `RPCRT4!RpcExceptionFilter` at `0x180012478`
- `RPCRT4!RpcBindingFree` at `0x18000c400`
- `RPCRT4!RpcBindingFree` at `0x18000c400`
- `RPCRT4!RpcBindingBind` at `0x18000c346`
- `RPCRT4!RpcBindingBind` at `0x18000c346`
- `RPCRT4!I_RpcExceptionFilter` at `0x180012494`
- `RPCRT4!I_RpcExceptionFilter` at `0x180012494`

## pseudocode

```c
__int64 __fastcall CEfsClientBase::EfsRemoveUsersClient(
        CEfsClientBase *this,
        const unsigned __int16 *a2,
        struct _ENCRYPTION_CERTIFICATE_HASH_LIST *a3)
{
  CEfsClientBase *v5; // rcx
  unsigned int FullName; // edi
  __int64 v7; // rax
  PVOID P; // [rsp+58h] [rbp-30h] BYREF
  PVOID v10; // [rsp+60h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE v11; // [rsp+90h] [rbp+8h] BYREF
  struct _ENCRYPTION_CERTIFICATE_HASH_LIST *v12; // [rsp+A0h] [rbp+18h]
  RPC_BINDING_HANDLE Binding; // [rsp+A8h] [rbp+20h] BYREF

  v12 = a3;
  Binding = 0;
  P = 0;
  v10 = 0;
  FullName = EfspGetFullName(a2, (unsigned __int16 **)&P, (unsigned __int16 **)&v10, 0, 0, 0, 0, 0, 0, (int *)this + 2);
  if ( !FullName )
  {
    if ( *(_WORD *)v10 != 46 || *((_WORD *)v10 + 1) )
    {
      FullName = (*(__int64 (__fastcall **)(CEfsClientBase *, PVOID, _QWORD, __int64, RPC_BINDING_HANDLE *))(*(_QWORD *)this + 16LL))(
                   this,
                   v10,
                   0,
                   1,
                   &Binding);
      if ( FullName )
        goto LABEL_10;
      v7 = (*(__int64 (__fastcall **)(CEfsClientBase *))(*(_QWORD *)this + 8LL))(this);
      FullName = (*(__int64 (__fastcall **)(RPC_BINDING_HANDLE, PVOID, struct _ENCRYPTION_CERTIFICATE_HASH_LIST *))(v7 + 64))(
                   Binding,
                   P,
                   a3);
    }
    else
    {
      FullName = CEfsClientBase::CreateLocalRpcBinding(v5, &Binding);
      if ( FullName )
        goto LABEL_10;
      LODWORD(v11) = 0;
      FullName = EfsRpcRemoveUsersFromFile(Binding, P, a3);
    }
    v11 = Binding;
    if ( Binding )
      RpcBindingFree(&v11);
  }
LABEL_10:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return FullName;
}

```

## disassembly

```asm
0x18000c21c  mov     r11, rsp
0x18000c21f  mov     [r11+10h], rbx
0x18000c223  mov     [r11+18h], r8
0x18000c227  push    rsi
0x18000c228  push    rdi
0x18000c229  push    r14
0x18000c22b  sub     rsp, 70h
0x18000c22f  mov     rsi, r8
0x18000c232  mov     r10, rdx
0x18000c235  mov     r14, rcx
0x18000c238  xor     ebx, ebx
0x18000c23a  mov     [r11+20h], rbx
0x18000c23e  mov     [r11-30h], rbx
0x18000c242  mov     [r11-28h], rbx
0x18000c246  lea     rax, [rcx+8]
0x18000c24a  mov     [r11-40h], rax
0x18000c24e  mov     [r11-48h], rbx
0x18000c252  mov     [rsp+88h+var_50], ebx; int
0x18000c256  mov     [r11-58h], rbx
0x18000c25a  mov     [rsp+88h+var_60], ebx; unsigned int
0x18000c25e  mov     [r11-68h], rbx
0x18000c262  xor     r9d, r9d; unsigned int
0x18000c265  lea     r8, [r11-28h]; unsigned __int16 **
0x18000c269  lea     rdx, [r11-30h]; unsigned __int16 **
0x18000c26d  mov     rcx, r10; unsigned __int16 *
0x18000c270  call    ?EfspGetFullName@@YAKPEBGPEAPEAG1KPEAKKPEAXHPEAH4@Z; EfspGetFullName(ushort const *,ushort * *,ushort * *,ulong,ulong *,ulong,void *,int,int *,int *)
0x18000c275  mov     edi, eax
0x18000c277  test    eax, eax
0x18000c279  jnz     loc_18000C406
0x18000c27f  mov     rdx, [rsp+88h+var_28]
0x18000c284  cmp     word ptr [rdx], 2Eh ; '.'
0x18000c288  jnz     loc_18000C380
0x18000c28e  cmp     [rdx+2], bx
0x18000c292  jnz     loc_18000C380
0x18000c298  lea     rdx, [rsp+88h+Binding]; void **
0x18000c2a0  call    ?CreateLocalRpcBinding@CEfsClientBase@@IEAAKPEAPEAX@Z; CEfsClientBase::CreateLocalRpcBinding(void * *)
0x18000c2a5  mov     edi, eax
0x18000c2a7  test    eax, eax
0x18000c2a9  jnz     loc_18000C406
0x18000c2af  mov     eax, ebx
0x18000c2b1  mov     dword ptr [rsp+88h+arg_0], eax
0x18000c2b8  cmp     eax, 3
0x18000c2bb  jnb     loc_18000C37E
0x18000c2c1  mov     r8, rsi
0x18000c2c4  mov     rdx, [rsp+88h+P]
0x18000c2c9  mov     rcx, [rsp+88h+Binding]
0x18000c2d1  call    EfsRpcRemoveUsersFromFile
0x18000c2d6  mov     edi, eax
0x18000c2d8  mov     [rsp+88h+var_38], eax
0x18000c2dc  jmp     loc_18000C37E
0x18000c2e1  mov     edi, eax
0x18000c2e3  mov     [rsp+88h+var_38], eax
0x18000c2e7  xor     cl, cl
0x18000c2e9  add     eax, 0FFFFF954h
0x18000c2ee  cmp     eax, 2Dh ; '-'
0x18000c2f1  ja      short loc_18000C307
0x18000c2f3  mov     rdx, 2000000C4201h
0x18000c2fd  bt      rdx, rax
0x18000c301  jnb     short loc_18000C307
0x18000c303  mov     cl, 1
0x18000c305  jmp     short loc_18000C31B
0x18000c307  cmp     edi, 6BBh
0x18000c30d  jz      short loc_18000C31B
0x18000c30f  cmp     edi, 5B4h
0x18000c315  jz      short loc_18000C31B
0x18000c317  xor     ebx, ebx
0x18000c319  jmp     short loc_18000C37E
0x18000c31b  test    cl, cl
0x18000c31d  jz      short loc_18000C35A
0x18000c31f  mov     rcx, [rsp+88h+Binding]; Binding
0x18000c327  call    cs:__imp_RpcBindingUnbind
0x18000c32d  test    eax, eax
0x18000c32f  jz      short loc_18000C335
0x18000c331  xor     ebx, ebx
0x18000c333  jmp     short loc_18000C37E
0x18000c335  lea     r8, qword_180016C60; IfSpec
0x18000c33c  mov     rdx, [rsp+88h+Binding]; Binding
0x18000c344  xor     ecx, ecx; pAsync
0x18000c346  call    cs:__imp_RpcBindingBind
0x18000c34c  mov     edi, eax
0x18000c34e  mov     [rsp+88h+var_38], eax
0x18000c352  test    eax, eax
0x18000c354  jns     short loc_18000C35A
0x18000c356  xor     ebx, ebx
0x18000c358  jmp     short loc_18000C37E
0x18000c35a  mov     ecx, 12Ch; dwMilliseconds
0x18000c35f  call    cs:__imp_Sleep
0x18000c365  nop
0x18000c366  mov     eax, dword ptr [rsp+88h+arg_0]
0x18000c36d  inc     eax
0x18000c36f  xor     ebx, ebx
0x18000c371  mov     rsi, [rsp+88h+arg_10]
0x18000c379  jmp     loc_18000C2B1
0x18000c37e  jmp     short loc_18000C3E3
0x18000c380  mov     rax, [r14]
0x18000c383  lea     rcx, [rsp+88h+Binding]
0x18000c38b  mov     [rsp+88h+var_68], rcx
0x18000c390  mov     r9d, 1
0x18000c396  xor     r8d, r8d
0x18000c399  mov     rcx, r14
0x18000c39c  mov     rax, [rax+10h]
0x18000c3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3a5  mov     edi, eax
0x18000c3a7  test    eax, eax
0x18000c3a9  jnz     short loc_18000C406
0x18000c3ab  mov     rax, [r14]
0x18000c3ae  mov     rcx, r14
0x18000c3b1  mov     rax, [rax+8]
0x18000c3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ba  mov     r8, rsi
0x18000c3bd  mov     rdx, [rsp+88h+P]
0x18000c3c2  mov     rcx, [rsp+88h+Binding]
0x18000c3ca  mov     rax, [rax+40h]
0x18000c3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3d3  mov     edi, eax
0x18000c3d5  mov     [rsp+88h+var_38], eax
0x18000c3d9  jmp     short loc_18000C3E3
0x18000c3db  mov     edi, eax
0x18000c3dd  mov     [rsp+88h+var_38], eax
0x18000c3e1  xor     ebx, ebx
0x18000c3e3  mov     rax, [rsp+88h+Binding]
0x18000c3eb  test    rax, rax
0x18000c3ee  mov     [rsp+88h+arg_0], rax
0x18000c3f6  jz      short loc_18000C406
0x18000c3f8  lea     rcx, [rsp+88h+arg_0]; Binding
0x18000c400  call    cs:__imp_RpcBindingFree
0x18000c406  cmp     [rsp+88h+P], rbx
0x18000c40b  jz      short loc_18000C427
0x18000c40d  mov     rcx, gs:60h
0x18000c416  mov     r8, [rsp+88h+P]; P
0x18000c41b  xor     edx, edx; Flags
0x18000c41d  mov     rcx, [rcx+30h]; HeapHandle
0x18000c421  call    cs:__imp_RtlFreeHeap
0x18000c427  cmp     [rsp+88h+var_28], rbx
0x18000c42c  jz      short loc_18000C448
0x18000c42e  mov     rcx, gs:60h
0x18000c437  mov     r8, [rsp+88h+var_28]; P
0x18000c43c  xor     edx, edx; Flags
0x18000c43e  mov     rcx, [rcx+30h]; HeapHandle
0x18000c442  call    cs:__imp_RtlFreeHeap
0x18000c448  mov     eax, edi
0x18000c44a  mov     rbx, [rsp+88h+arg_8]
0x18000c452  add     rsp, 70h
0x18000c456  pop     r14
0x18000c458  pop     rdi
0x18000c459  pop     rsi
0x18000c45a  retn
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
