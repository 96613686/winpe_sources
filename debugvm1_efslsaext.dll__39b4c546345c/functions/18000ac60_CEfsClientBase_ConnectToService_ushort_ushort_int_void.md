# CEfsClientBase::ConnectToService(ushort *,ushort *,int,void * *)

- ea: `0x18000ac60`
- end: `0x18000ade1`
- name: `?ConnectToService@CEfsClientBase@@MEAAKPEAG0HPEAPEAX@Z`
- size: `385`
- prototype: `unsigned int(CEfsClientBase *__hidden this, unsigned __int16 *, unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18000a870`

## callees

- `0x180005c94`
- `0x18000ac60`
- `0x180011c10`
- `0x18001200e`
- `0x180012040`
- `0x180013010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000ace2`
- `ntdll!RtlNtStatusToDosError` at `0x18000ace2`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18000ad88`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18000ad88`
- `RPCRT4!RpcBindingFree` at `0x18000adb8`
- `RPCRT4!RpcBindingFree` at `0x18000adb8`

## pseudocode

```c
__int64 __fastcall CEfsClientBase::ConnectToService(
        CEfsClientBase *this,
        char *a2,
        unsigned __int16 *a3,
        int a4,
        void **a5)
{
  unsigned __int16 *v9; // rax
  NTSTATUS v10; // eax
  ULONG v11; // eax
  RPC_BINDING_HANDLE v12; // rcx
  ULONG v13; // ebx
  unsigned __int16 *v14; // rdx
  const wchar_t *v15; // r9
  __int64 v16; // rdx
  unsigned __int16 *v17; // rax
  __int64 v18; // rcx
  unsigned __int16 *v19; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-D0h] BYREF
  RPC_BINDING_HANDLE v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 ServerPrincName[272]; // [rsp+40h] [rbp-C0h] BYREF

  Binding = 0;
  memset_0(ServerPrincName, 0, 0x214u);
  *a5 = 0;
  v9 = (unsigned __int16 *)(**(__int64 (__fastcall ***)(CEfsClientBase *))this)(this);
  v10 = RpcpBindRpc(a2, v9, a3, &Binding);
  if ( v10 < 0 )
    goto LABEL_2;
  if ( !a4 )
    goto LABEL_14;
  v14 = 0;
  if ( *(_WORD *)a2 != 46 || *((_WORD *)a2 + 1) )
  {
    v15 = L"HOST/";
    v16 = 266;
    v17 = ServerPrincName;
    v18 = 2147483646;
    do
    {
      if ( !v18 )
        break;
      if ( !*v15 )
        break;
      *v17++ = *v15++;
      --v18;
      --v16;
    }
    while ( v16 );
    v19 = v17 - 1;
    if ( v16 )
      v19 = v17;
    *v19 = 0;
    StringCchCatW(ServerPrincName, 0x10Au, (const unsigned __int16 *)a2);
    v14 = ServerPrincName;
  }
  v10 = RpcBindingSetAuthInfoW(Binding, v14, 6u, 9u, 0, 0);
  if ( v10 < 0 )
  {
LABEL_2:
    v11 = RtlNtStatusToDosError(v10);
    v12 = Binding;
    v13 = v11;
  }
  else
  {
LABEL_14:
    v12 = 0;
    *a5 = Binding;
    v13 = 0;
    Binding = 0;
  }
  if ( v12 )
  {
    v22 = v12;
    RpcBindingFree(&v22);
  }
  return v13;
}

```

## disassembly

```asm
0x18000ac60  push    rbp
0x18000ac62  push    rbx
0x18000ac63  push    rsi
0x18000ac64  push    rdi
0x18000ac65  push    r12
0x18000ac67  push    r14
0x18000ac69  push    r15
0x18000ac6b  lea     rbp, [rsp-170h]
0x18000ac73  sub     rsp, 270h
0x18000ac7a  mov     rax, cs:__security_cookie
0x18000ac81  xor     rax, rsp
0x18000ac84  mov     [rbp+1A0h+var_40], rax
0x18000ac8b  mov     r15, [rbp+1A0h+arg_20]
0x18000ac92  mov     rdi, r8
0x18000ac95  mov     rsi, rdx
0x18000ac98  mov     rbx, rcx
0x18000ac9b  xor     r12d, r12d
0x18000ac9e  lea     rcx, [rsp+2A0h+ServerPrincName]; void *
0x18000aca3  xor     edx, edx; Val
0x18000aca5  mov     [rsp+2A0h+Binding], r12
0x18000acaa  mov     r8d, 214h; Size
0x18000acb0  mov     r14d, r9d
0x18000acb3  call    memset_0
0x18000acb8  mov     [r15], r12
0x18000acbb  mov     rcx, rbx
0x18000acbe  mov     rax, [rbx]
0x18000acc1  mov     rax, [rax]
0x18000acc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc9  mov     rdx, rax
0x18000accc  lea     r9, [rsp+2A0h+Binding]
0x18000acd1  mov     r8, rdi
0x18000acd4  mov     rcx, rsi; Src
0x18000acd7  call    RpcpBindRpc
0x18000acdc  test    eax, eax
0x18000acde  jns     short loc_18000ACF4
0x18000ace0  mov     ecx, eax; Status
0x18000ace2  call    cs:__imp_RtlNtStatusToDosError
0x18000ace8  mov     rcx, [rsp+2A0h+Binding]
0x18000aced  mov     ebx, eax
0x18000acef  jmp     loc_18000ADA9
0x18000acf4  test    r14d, r14d
0x18000acf7  jz      loc_18000AD96
0x18000acfd  cmp     word ptr [rsi], 2Eh ; '.'
0x18000ad01  mov     rdx, r12
0x18000ad04  jnz     short loc_18000AD0D
0x18000ad06  cmp     [rsi+2], r12w
0x18000ad0b  jz      short loc_18000AD6F
0x18000ad0d  mov     r10d, 10Ah
0x18000ad13  lea     r9, aHost; "HOST/"
0x18000ad1a  mov     edx, r10d
0x18000ad1d  lea     rax, [rsp+2A0h+ServerPrincName]
0x18000ad22  mov     ecx, 7FFFFFFEh
0x18000ad27  test    rcx, rcx
0x18000ad2a  jz      short loc_18000AD4B
0x18000ad2c  movzx   r8d, word ptr [r9]
0x18000ad30  test    r8w, r8w
0x18000ad34  jz      short loc_18000AD4B
0x18000ad36  mov     [rax], r8w
0x18000ad3a  add     r9, 2
0x18000ad3e  add     rax, 2
0x18000ad42  dec     rcx
0x18000ad45  sub     rdx, 1
0x18000ad49  jnz     short loc_18000AD27
0x18000ad4b  test    rdx, rdx
0x18000ad4e  lea     rcx, [rax-2]
0x18000ad52  mov     r8, rsi; unsigned __int16 *
0x18000ad55  mov     rdx, r10; unsigned __int64
0x18000ad58  cmovnz  rcx, rax
0x18000ad5c  mov     [rcx], r12w
0x18000ad60  lea     rcx, [rsp+2A0h+ServerPrincName]; unsigned __int16 *
0x18000ad65  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ad6a  lea     rdx, [rsp+2A0h+ServerPrincName]; ServerPrincName
0x18000ad6f  mov     rcx, [rsp+2A0h+Binding]; Binding
0x18000ad74  mov     r9d, 9; AuthnSvc
0x18000ad7a  mov     [rsp+2A0h+AuthzSvc], r12d; AuthzSvc
0x18000ad7f  mov     [rsp+2A0h+AuthIdentity], r12; AuthIdentity
0x18000ad84  lea     r8d, [r9-3]; AuthnLevel
0x18000ad88  call    cs:__imp_RpcBindingSetAuthInfoW
0x18000ad8e  test    eax, eax
0x18000ad90  js      loc_18000ACE0
0x18000ad96  mov     rax, [rsp+2A0h+Binding]
0x18000ad9b  mov     rcx, r12
0x18000ad9e  mov     [r15], rax
0x18000ada1  mov     ebx, r12d
0x18000ada4  mov     [rsp+2A0h+Binding], rcx
0x18000ada9  test    rcx, rcx
0x18000adac  jz      short loc_18000ADBE
0x18000adae  mov     [rsp+2A0h+var_268], rcx
0x18000adb3  lea     rcx, [rsp+2A0h+var_268]; Binding
0x18000adb8  call    cs:__imp_RpcBindingFree
0x18000adbe  mov     eax, ebx
0x18000adc0  mov     rcx, [rbp+1A0h+var_40]
0x18000adc7  xor     rcx, rsp; StackCookie
0x18000adca  call    __security_check_cookie
0x18000adcf  add     rsp, 270h
0x18000add6  pop     r15
0x18000add8  pop     r14
0x18000adda  pop     r12
0x18000addc  pop     rdi
0x18000addd  pop     rsi
0x18000adde  pop     rbx
0x18000addf  pop     rbp
0x18000ade0  retn
```
