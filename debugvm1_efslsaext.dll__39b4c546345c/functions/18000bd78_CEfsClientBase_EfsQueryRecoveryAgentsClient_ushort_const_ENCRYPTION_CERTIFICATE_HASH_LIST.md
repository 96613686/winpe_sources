# CEfsClientBase::EfsQueryRecoveryAgentsClient(ushort const *,_ENCRYPTION_CERTIFICATE_HASH_LIST * *)

- ea: `0x18000bd78`
- end: `0x18000bfba`
- name: `?EfsQueryRecoveryAgentsClient@CEfsClientBase@@QEAAKPEBGPEAPEAU_ENCRYPTION_CERTIFICATE_HASH_LIST@@@Z`
- size: `578`
- prototype: `unsigned int(CEfsClientBase *__hidden this, const unsigned __int16 *, struct _ENCRYPTION_CERTIFICATE_HASH_LIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180007a30`

## callees

- `0x18000ade8`
- `0x18000bd78`
- `0x18000c6d0`
- `0x18000d700`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bebe`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bebe`
- `ntdll!RtlFreeHeap` at `0x18000bf80`
- `ntdll!RtlFreeHeap` at `0x18000bfa1`
- `ntdll!RtlFreeHeap` at `0x18000bf80`
- `ntdll!RtlFreeHeap` at `0x18000bfa1`
- `RPCRT4!RpcBindingUnbind` at `0x18000be86`
- `RPCRT4!RpcBindingUnbind` at `0x18000be86`
- `RPCRT4!RpcBindingFree` at `0x18000bf5f`
- `RPCRT4!RpcBindingFree` at `0x18000bf5f`
- `RPCRT4!RpcBindingBind` at `0x18000bea5`
- `RPCRT4!RpcBindingBind` at `0x18000bea5`

## pseudocode

```c
__int64 __fastcall CEfsClientBase::EfsQueryRecoveryAgentsClient(
        CEfsClientBase *this,
        const unsigned __int16 *a2,
        struct _ENCRYPTION_CERTIFICATE_HASH_LIST **a3)
{
  CEfsClientBase *v5; // rcx
  unsigned int FullName; // edi
  __int64 v7; // rax
  PVOID P; // [rsp+58h] [rbp-30h] BYREF
  PVOID v10; // [rsp+60h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE v11; // [rsp+A0h] [rbp+18h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+A8h] [rbp+20h] BYREF

  v11 = a3;
  Binding = 0;
  P = 0;
  v10 = 0;
  *a3 = 0;
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
      FullName = (*(__int64 (__fastcall **)(RPC_BINDING_HANDLE, PVOID, struct _ENCRYPTION_CERTIFICATE_HASH_LIST **))(v7 + 56))(
                   Binding,
                   P,
                   a3);
    }
    else
    {
      FullName = CEfsClientBase::CreateLocalRpcBinding(v5, &Binding);
      if ( FullName )
        goto LABEL_10;
      FullName = EfsRpcQueryRecoveryAgents(Binding, P, a3);
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
0x18000bd78  mov     r11, rsp
0x18000bd7b  mov     [r11+10h], rbx
0x18000bd7f  mov     [r11+18h], r8
0x18000bd83  push    rsi
0x18000bd84  push    rdi
0x18000bd85  push    r14
0x18000bd87  sub     rsp, 70h
0x18000bd8b  mov     rsi, r8
0x18000bd8e  mov     r10, rdx
0x18000bd91  mov     r14, rcx
0x18000bd94  xor     ebx, ebx
0x18000bd96  mov     [r11+20h], rbx
0x18000bd9a  mov     [r11-30h], rbx
0x18000bd9e  mov     [r11-28h], rbx
0x18000bda2  mov     [r8], rbx
0x18000bda5  lea     rax, [rcx+8]
0x18000bda9  mov     [r11-40h], rax
0x18000bdad  mov     [r11-48h], rbx
0x18000bdb1  mov     [rsp+88h+var_50], ebx; int
0x18000bdb5  mov     [r11-58h], rbx
0x18000bdb9  mov     [rsp+88h+var_60], ebx; unsigned int
0x18000bdbd  mov     [r11-68h], rbx
0x18000bdc1  xor     r9d, r9d; unsigned int
0x18000bdc4  lea     r8, [r11-28h]; unsigned __int16 **
0x18000bdc8  lea     rdx, [r11-30h]; unsigned __int16 **
0x18000bdcc  mov     rcx, r10; unsigned __int16 *
0x18000bdcf  call    ?EfspGetFullName@@YAKPEBGPEAPEAG1KPEAKKPEAXHPEAH4@Z; EfspGetFullName(ushort const *,ushort * *,ushort * *,ulong,ulong *,ulong,void *,int,int *,int *)
0x18000bdd4  mov     edi, eax
0x18000bdd6  test    eax, eax
0x18000bdd8  jnz     loc_18000BF65
0x18000bdde  mov     rdx, [rsp+88h+var_28]
0x18000bde3  cmp     word ptr [rdx], 2Eh ; '.'
0x18000bde7  jnz     loc_18000BEDF
0x18000bded  cmp     [rdx+2], bx
0x18000bdf1  jnz     loc_18000BEDF
0x18000bdf7  lea     rdx, [rsp+88h+Binding]; void **
0x18000bdff  call    ?CreateLocalRpcBinding@CEfsClientBase@@IEAAKPEAPEAX@Z; CEfsClientBase::CreateLocalRpcBinding(void * *)
0x18000be04  mov     edi, eax
0x18000be06  test    eax, eax
0x18000be08  jnz     loc_18000BF65
0x18000be0e  mov     eax, ebx
0x18000be10  mov     [rsp+88h+arg_0], eax
0x18000be17  cmp     eax, 3
0x18000be1a  jnb     loc_18000BEDD
0x18000be20  mov     r8, rsi
0x18000be23  mov     rdx, [rsp+88h+P]
0x18000be28  mov     rcx, [rsp+88h+Binding]
0x18000be30  call    EfsRpcQueryRecoveryAgents
0x18000be35  mov     edi, eax
0x18000be37  mov     [rsp+88h+var_38], eax
0x18000be3b  jmp     loc_18000BEDD
0x18000be40  mov     edi, eax
0x18000be42  mov     [rsp+88h+var_38], eax
0x18000be46  xor     cl, cl
0x18000be48  add     eax, 0FFFFF954h
0x18000be4d  cmp     eax, 2Dh ; '-'
0x18000be50  ja      short loc_18000BE66
0x18000be52  mov     rdx, 2000000C4201h
0x18000be5c  bt      rdx, rax
0x18000be60  jnb     short loc_18000BE66
0x18000be62  mov     cl, 1
0x18000be64  jmp     short loc_18000BE7A
0x18000be66  cmp     edi, 6BBh
0x18000be6c  jz      short loc_18000BE7A
0x18000be6e  cmp     edi, 5B4h
0x18000be74  jz      short loc_18000BE7A
0x18000be76  xor     ebx, ebx
0x18000be78  jmp     short loc_18000BEDD
0x18000be7a  test    cl, cl
0x18000be7c  jz      short loc_18000BEB9
0x18000be7e  mov     rcx, [rsp+88h+Binding]; Binding
0x18000be86  call    cs:__imp_RpcBindingUnbind
0x18000be8c  test    eax, eax
0x18000be8e  jz      short loc_18000BE94
0x18000be90  xor     ebx, ebx
0x18000be92  jmp     short loc_18000BEDD
0x18000be94  lea     r8, qword_180016C60; IfSpec
0x18000be9b  mov     rdx, [rsp+88h+Binding]; Binding
0x18000bea3  xor     ecx, ecx; pAsync
0x18000bea5  call    cs:__imp_RpcBindingBind
0x18000beab  mov     edi, eax
0x18000bead  mov     [rsp+88h+var_38], eax
0x18000beb1  test    eax, eax
0x18000beb3  jns     short loc_18000BEB9
0x18000beb5  xor     ebx, ebx
0x18000beb7  jmp     short loc_18000BEDD
0x18000beb9  mov     ecx, 12Ch; dwMilliseconds
0x18000bebe  call    cs:__imp_Sleep
0x18000bec4  nop
0x18000bec5  mov     eax, [rsp+88h+arg_0]
0x18000becc  inc     eax
0x18000bece  xor     ebx, ebx
0x18000bed0  mov     rsi, [rsp+88h+arg_10]
0x18000bed8  jmp     loc_18000BE10
0x18000bedd  jmp     short loc_18000BF42
0x18000bedf  mov     rax, [r14]
0x18000bee2  lea     rcx, [rsp+88h+Binding]
0x18000beea  mov     [rsp+88h+var_68], rcx
0x18000beef  mov     r9d, 1
0x18000bef5  xor     r8d, r8d
0x18000bef8  mov     rcx, r14
0x18000befb  mov     rax, [rax+10h]
0x18000beff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf04  mov     edi, eax
0x18000bf06  test    eax, eax
0x18000bf08  jnz     short loc_18000BF65
0x18000bf0a  mov     rax, [r14]
0x18000bf0d  mov     rcx, r14
0x18000bf10  mov     rax, [rax+8]
0x18000bf14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf19  mov     r8, rsi
0x18000bf1c  mov     rdx, [rsp+88h+P]
0x18000bf21  mov     rcx, [rsp+88h+Binding]
0x18000bf29  mov     rax, [rax+38h]
0x18000bf2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf32  mov     edi, eax
0x18000bf34  mov     [rsp+88h+var_38], eax
0x18000bf38  jmp     short loc_18000BF42
0x18000bf3a  mov     edi, eax
0x18000bf3c  mov     [rsp+88h+var_38], eax
0x18000bf40  xor     ebx, ebx
0x18000bf42  mov     rax, [rsp+88h+Binding]
0x18000bf4a  test    rax, rax
0x18000bf4d  mov     [rsp+88h+arg_10], rax
0x18000bf55  jz      short loc_18000BF65
0x18000bf57  lea     rcx, [rsp+88h+arg_10]; Binding
0x18000bf5f  call    cs:__imp_RpcBindingFree
0x18000bf65  cmp     [rsp+88h+P], rbx
0x18000bf6a  jz      short loc_18000BF86
0x18000bf6c  mov     rcx, gs:60h
0x18000bf75  mov     r8, [rsp+88h+P]; P
0x18000bf7a  xor     edx, edx; Flags
0x18000bf7c  mov     rcx, [rcx+30h]; HeapHandle
0x18000bf80  call    cs:__imp_RtlFreeHeap
0x18000bf86  cmp     [rsp+88h+var_28], rbx
0x18000bf8b  jz      short loc_18000BFA7
0x18000bf8d  mov     rcx, gs:60h
0x18000bf96  mov     r8, [rsp+88h+var_28]; P
0x18000bf9b  xor     edx, edx; Flags
0x18000bf9d  mov     rcx, [rcx+30h]; HeapHandle
0x18000bfa1  call    cs:__imp_RtlFreeHeap
0x18000bfa7  mov     eax, edi
0x18000bfa9  mov     rbx, [rsp+88h+arg_8]
0x18000bfb1  add     rsp, 70h
0x18000bfb5  pop     r14
0x18000bfb7  pop     rdi
0x18000bfb8  pop     rsi
0x18000bfb9  retn
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
