# BaseRegCreateKey

- ea: `0x180019290`
- end: `0x1800194d0`
- name: `BaseRegCreateKey`
- size: `576`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x180016d3c`
- `0x180017dfc`
- `0x180019290`
- `0x18001ac84`
- `0x18001acc8`
- `0x18001ad14`

## import_xrefs

- `ntdll!NtClose` at `0x1800194a5`
- `ntdll!NtClose` at `0x18001e6e6`
- `ntdll!NtClose` at `0x1800194a5`
- `ntdll!NtClose` at `0x18001e6e6`
- `RPCRT4!RpcRaiseException` at `0x1800193bb`
- `RPCRT4!RpcRaiseException` at `0x1800193c3`
- `RPCRT4!RpcRaiseException` at `0x1800193d7`
- `RPCRT4!RpcRaiseException` at `0x1800193bb`
- `RPCRT4!RpcRaiseException` at `0x1800193c3`
- `RPCRT4!RpcRaiseException` at `0x1800193d7`
- `RPCRT4!RpcImpersonateClient` at `0x1800193cb`
- `RPCRT4!RpcImpersonateClient` at `0x1800193cb`
- `RPCRT4!RpcRevertToSelf` at `0x180019486`
- `RPCRT4!RpcRevertToSelf` at `0x18001e6c7`
- `RPCRT4!RpcRevertToSelf` at `0x180019486`
- `RPCRT4!RpcRevertToSelf` at `0x18001e6c7`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001939d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001939d`

## pseudocode

```c
__int64 __fastcall BaseRegCreateKey(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        HANDLE **a7,
        __int64 a8)
{
  int v9; // r15d
  char v10; // si
  int v11; // r14d
  HANDLE v12; // rbx
  unsigned int KeyInternal; // ebx
  RPC_STATUS v14; // eax
  RPC_STATUS v15; // eax
  HANDLE v16; // rcx
  HANDLE *v17; // rax
  int v19; // [rsp+50h] [rbp-F8h] BYREF
  int v20; // [rsp+54h] [rbp-F4h]
  HANDLE *v21; // [rsp+58h] [rbp-F0h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-E8h] BYREF
  int v23; // [rsp+68h] [rbp-E0h]
  __int64 v24; // [rsp+70h] [rbp-D8h]
  __int64 v25; // [rsp+78h] [rbp-D0h]
  _DWORD RpcCallAttributes[32]; // [rsp+80h] [rbp-C8h] BYREF

  v23 = a4;
  v9 = a2;
  v25 = a6;
  v24 = a8;
  v10 = 0;
  v21 = 0;
  v19 = 0;
  v11 = 0;
  v20 = 0;
  Handle = 0;
  *a7 = 0;
  if ( !a1 || (v12 = *(HANDLE *)a1) == 0 || (*(_DWORD *)(a1 + 8) & 0xFFFFFFF8) != 0 )
  {
    KeyInternal = 87;
    goto LABEL_29;
  }
  if ( (*(_BYTE *)(a1 + 8) & 4) != 0 )
  {
    RegSvcLogAllowedExactPathEvent(*(HANDLE *)a1);
LABEL_10:
    KeyInternal = 5;
    goto LABEL_29;
  }
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0
    && (RestrictedHandlesQuota >= 0x10000 || !(unsigned int)RegSecCheckPath(a1, a2, &v19)) )
  {
    goto LABEL_10;
  }
  if ( v12 == RestrictedMachineHandle )
  {
    v10 = 1;
  }
  else if ( v12 == RestrictedUserHandle )
  {
    v10 = 2;
  }
  memset_0(RpcCallAttributes, 0, 0x78u);
  RpcCallAttributes[0] = 3;
  v14 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v14 != 1746 )
  {
    if ( v14 )
      RpcRaiseException(v14);
    if ( RpcCallAttributes[10] < 6u )
      RpcRaiseException(5);
  }
  v15 = RpcImpersonateClient(0);
  if ( v15 )
    RpcRaiseException(v15);
  v11 = 1;
  v20 = 1;
  KeyInternal = BaseRegCreateKeyInternal((_DWORD)v12, v9, a3, v23, a5, v25, v10, (__int64)&Handle, v24);
  if ( !KeyInternal )
  {
    KeyInternal = RegSvcContextAllocate(&v21);
    if ( !KeyInternal )
    {
      v16 = Handle;
      v17 = v21;
      *v21 = Handle;
      Handle = 0;
      if ( (v10 & 1) != 0 )
      {
        if ( v16 )
        {
          *((_DWORD *)v17 + 2) |= 2u;
          _InterlockedIncrement(&RestrictedHandlesQuota);
          if ( v19 != KeyInternal )
            *((_DWORD *)v17 + 2) |= 4u;
        }
      }
      *a7 = v17;
      v21 = 0;
      KeyInternal = 0;
    }
  }
LABEL_29:
  if ( v11 )
    RpcRevertToSelf();
  if ( v21 )
    RegSvcContextCleanup();
  if ( Handle )
    NtClose(Handle);
  return KeyInternal;
}

```

## disassembly

```asm
0x180019290  push    rbx
0x180019292  push    rsi
0x180019293  push    rdi
0x180019294  push    r12
0x180019296  push    r13
0x180019298  push    r14
0x18001929a  push    r15
0x18001929c  sub     rsp, 110h
0x1800192a3  mov     rax, cs:__security_cookie
0x1800192aa  xor     rax, rsp
0x1800192ad  mov     [rsp+148h+var_48], rax
0x1800192b5  mov     [rsp+148h+var_E0], r9d
0x1800192ba  mov     r13, r8
0x1800192bd  mov     r15, rdx
0x1800192c0  mov     rax, [rsp+148h+arg_28]
0x1800192c8  mov     [rsp+148h+var_D0], rax
0x1800192cd  mov     r12, [rsp+148h+arg_30]
0x1800192d5  mov     rax, [rsp+148h+arg_38]
0x1800192dd  mov     [rsp+148h+var_D8], rax
0x1800192e2  xor     esi, esi
0x1800192e4  mov     [rsp+148h+var_F0], rsi
0x1800192e9  mov     [rsp+148h+var_F8], esi
0x1800192ed  xor     r14d, r14d
0x1800192f0  mov     [rsp+148h+var_F4], r14d
0x1800192f5  mov     [rsp+148h+Handle], rsi
0x1800192fa  mov     [r12], r14
0x1800192fe  test    rcx, rcx
0x180019301  jz      short loc_180019314
0x180019303  mov     rbx, [rcx]
0x180019306  test    rbx, rbx
0x180019309  jz      short loc_180019314
0x18001930b  test    dword ptr [rcx+8], 0FFFFFFF8h
0x180019312  jz      short loc_18001931E
0x180019314  mov     ebx, 57h ; 'W'
0x180019319  jmp     loc_180019481
0x18001931e  test    byte ptr [rcx+8], 4
0x180019322  jz      short loc_18001932E
0x180019324  mov     rcx, rbx; KeyHandle
0x180019327  call    RegSvcLogAllowedExactPathEvent
0x18001932c  jmp     short loc_18001934E
0x18001932e  test    byte ptr [rcx+8], 1
0x180019332  jz      short loc_180019358
0x180019334  cmp     cs:RestrictedHandlesQuota, 10000h
0x18001933e  jge     short loc_18001934E
0x180019340  lea     r8, [rsp+148h+var_F8]
0x180019345  call    RegSecCheckPath
0x18001934a  test    eax, eax
0x18001934c  jnz     short loc_180019358
0x18001934e  mov     ebx, 5
0x180019353  jmp     loc_180019481
0x180019358  mov     edi, 2
0x18001935d  cmp     rbx, cs:RestrictedMachineHandle
0x180019364  jnz     short loc_18001936B
0x180019366  lea     esi, [rdi-1]
0x180019369  jmp     short loc_180019375
0x18001936b  cmp     rbx, cs:RestrictedUserHandle
0x180019372  cmovz   esi, edi
0x180019375  xor     edx, edx; Val
0x180019377  lea     r8d, [rdx+78h]; Size
0x18001937b  lea     rcx, [rsp+148h+RpcCallAttributes]; void *
0x180019383  call    memset_0
0x180019388  mov     [rsp+148h+RpcCallAttributes], 3
0x180019393  lea     rdx, [rsp+148h+RpcCallAttributes]; RpcCallAttributes
0x18001939b  xor     ecx, ecx; ClientBinding
0x18001939d  call    cs:__imp_RpcServerInqCallAttributesW
0x1800193a3  cmp     eax, 6D2h
0x1800193a8  jz      short loc_1800193C9
0x1800193aa  test    eax, eax
0x1800193ac  jnz     short loc_1800193C1
0x1800193ae  cmp     [rsp+148h+var_A0], 6
0x1800193b6  jnb     short loc_1800193C9
0x1800193b8  lea     ecx, [rax+5]; exception
0x1800193bb  call    cs:__imp_RpcRaiseException
0x1800193c1  mov     ecx, eax; exception
0x1800193c3  call    cs:__imp_RpcRaiseException
0x1800193c9  xor     ecx, ecx; BindingHandle
0x1800193cb  call    cs:__imp_RpcImpersonateClient
0x1800193d1  test    eax, eax
0x1800193d3  jz      short loc_1800193DD
0x1800193d5  mov     ecx, eax; exception
0x1800193d7  call    cs:__imp_RpcRaiseException
0x1800193dd  mov     r14d, 1
0x1800193e3  mov     [rsp+148h+var_F4], r14d
0x1800193e8  mov     rax, [rsp+148h+var_D8]
0x1800193ed  mov     [rsp+148h+var_108], rax
0x1800193f2  lea     rax, [rsp+148h+Handle]
0x1800193f7  mov     [rsp+148h+var_110], rax
0x1800193fc  mov     [rsp+148h+var_118], esi
0x180019400  mov     rax, [rsp+148h+var_D0]
0x180019405  mov     [rsp+148h+var_120], rax
0x18001940a  mov     eax, [rsp+148h+arg_20]
0x180019411  mov     [rsp+148h+var_128], eax
0x180019415  mov     r9d, [rsp+148h+var_E0]
0x18001941a  mov     r8, r13
0x18001941d  mov     rdx, r15
0x180019420  mov     rcx, rbx
0x180019423  call    BaseRegCreateKeyInternal
0x180019428  mov     ebx, eax
0x18001942a  test    eax, eax
0x18001942c  jnz     short loc_180019481
0x18001942e  lea     rcx, [rsp+148h+var_F0]
0x180019433  call    RegSvcContextAllocate
0x180019438  mov     ebx, eax
0x18001943a  test    eax, eax
0x18001943c  jnz     short loc_180019481
0x18001943e  mov     rcx, [rsp+148h+Handle]
0x180019443  mov     rax, [rsp+148h+var_F0]
0x180019448  mov     [rax], rcx
0x18001944b  mov     [rsp+148h+Handle], 0
0x180019454  test    r14b, sil
0x180019457  jz      short loc_180019472
0x180019459  test    rcx, rcx
0x18001945c  jz      short loc_180019472
0x18001945e  or      [rax+8], edi
0x180019461  lock inc cs:RestrictedHandlesQuota
0x180019468  cmp     [rsp+148h+var_F8], ebx
0x18001946c  jz      short loc_180019472
0x18001946e  or      dword ptr [rax+8], 4
0x180019472  mov     [r12], rax
0x180019476  mov     [rsp+148h+var_F0], 0
0x18001947f  xor     ebx, ebx
0x180019481  test    r14d, r14d
0x180019484  jz      short loc_18001948C
0x180019486  call    cs:__imp_RpcRevertToSelf
0x18001948c  mov     rcx, [rsp+148h+var_F0]
0x180019491  test    rcx, rcx
0x180019494  jz      short loc_18001949B
0x180019496  call    RegSvcContextCleanup
0x18001949b  mov     rcx, [rsp+148h+Handle]; Handle
0x1800194a0  test    rcx, rcx
0x1800194a3  jz      short loc_1800194AB
0x1800194a5  call    cs:__imp_NtClose
0x1800194ab  mov     eax, ebx
0x1800194ad  mov     rcx, [rsp+148h+var_48]
0x1800194b5  xor     rcx, rsp; StackCookie
0x1800194b8  call    __security_check_cookie
0x1800194bd  add     rsp, 110h
0x1800194c4  pop     r15
0x1800194c6  pop     r14
0x1800194c8  pop     r13
0x1800194ca  pop     r12
0x1800194cc  pop     rdi
0x1800194cd  pop     rsi
0x1800194ce  pop     rbx
0x1800194cf  retn
0x18001e6b8  push    rbp
0x18001e6ba  sub     rsp, 50h
0x18001e6be  mov     rbp, rdx
0x18001e6c1  cmp     dword ptr [rbp+54h], 0
0x18001e6c5  jz      short loc_18001E6CE
0x18001e6c7  call    cs:__imp_RpcRevertToSelf
0x18001e6cd  nop
0x18001e6ce  mov     rcx, [rbp+58h]
0x18001e6d2  test    rcx, rcx
0x18001e6d5  jz      short loc_18001E6DD
0x18001e6d7  call    RegSvcContextCleanup
0x18001e6dc  nop
0x18001e6dd  mov     rcx, [rbp+60h]; Handle
0x18001e6e1  test    rcx, rcx
0x18001e6e4  jz      short loc_18001E6ED
0x18001e6e6  call    cs:__imp_NtClose
0x18001e6ec  nop
0x18001e6ed  add     rsp, 50h
0x18001e6f1  pop     rbp
0x18001e6f2  retn
```
