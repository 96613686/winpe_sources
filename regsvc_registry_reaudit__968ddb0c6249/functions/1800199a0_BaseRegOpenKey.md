# BaseRegOpenKey

- ea: `0x1800199a0`
- end: `0x180019ba6`
- name: `BaseRegOpenKey`
- size: `518`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x180017210`
- `0x180017dfc`
- `0x1800199a0`
- `0x18001ac84`
- `0x18001acc8`
- `0x18001ad14`

## import_xrefs

- `ntdll!NtClose` at `0x180019b7b`
- `ntdll!NtClose` at `0x18001e728`
- `ntdll!NtClose` at `0x180019b7b`
- `ntdll!NtClose` at `0x18001e728`
- `RPCRT4!RpcRaiseException` at `0x180019aac`
- `RPCRT4!RpcRaiseException` at `0x180019ab4`
- `RPCRT4!RpcRaiseException` at `0x180019ac8`
- `RPCRT4!RpcRaiseException` at `0x180019aac`
- `RPCRT4!RpcRaiseException` at `0x180019ab4`
- `RPCRT4!RpcRaiseException` at `0x180019ac8`
- `RPCRT4!RpcImpersonateClient` at `0x180019abc`
- `RPCRT4!RpcImpersonateClient` at `0x180019abc`
- `RPCRT4!RpcRevertToSelf` at `0x180019b5c`
- `RPCRT4!RpcRevertToSelf` at `0x18001e709`
- `RPCRT4!RpcRevertToSelf` at `0x180019b5c`
- `RPCRT4!RpcRevertToSelf` at `0x18001e709`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019a8e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180019a8e`

## pseudocode

```c
__int64 __fastcall BaseRegOpenKey(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, HANDLE **a5)
{
  int v7; // r14d
  int v8; // r15d
  unsigned int v9; // ebx
  HANDLE v10; // rbx
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  HANDLE v13; // rcx
  HANDLE *v14; // rax
  int v16; // [rsp+40h] [rbp-E8h] BYREF
  int v17; // [rsp+44h] [rbp-E4h]
  HANDLE *v18; // [rsp+48h] [rbp-E0h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-D8h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-D0h]
  unsigned int v21; // [rsp+5Ch] [rbp-CCh]
  _DWORD RpcCallAttributes[32]; // [rsp+60h] [rbp-C8h] BYREF

  v20 = a4;
  v21 = a3;
  v7 = 0;
  v18 = 0;
  v16 = 0;
  v8 = 0;
  v17 = 0;
  Handle = 0;
  *a5 = 0;
  if ( !a1 || (*(_DWORD *)(a1 + 8) & 0xFFFFFFF8) != 0 )
  {
    v9 = 87;
    goto LABEL_28;
  }
  v10 = *(HANDLE *)a1;
  if ( (*(_BYTE *)(a1 + 8) & 4) != 0 )
  {
    RegSvcLogAllowedExactPathEvent(*(HANDLE *)a1);
LABEL_9:
    v9 = 5;
    goto LABEL_28;
  }
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0
    && (RestrictedHandlesQuota >= 0x10000 || !(unsigned int)RegSecCheckPath(a1, a2, &v16)) )
  {
    goto LABEL_9;
  }
  if ( v10 == RestrictedMachineHandle )
  {
    v7 = 1;
  }
  else if ( v10 == RestrictedUserHandle )
  {
    v7 = 2;
  }
  memset_0(RpcCallAttributes, 0, 0x78u);
  RpcCallAttributes[0] = 3;
  v11 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v11 != 1746 )
  {
    if ( v11 )
      RpcRaiseException(v11);
    if ( RpcCallAttributes[10] < 6u )
      RpcRaiseException(5);
  }
  v12 = RpcImpersonateClient(0);
  if ( v12 )
    RpcRaiseException(v12);
  v8 = 1;
  v17 = 1;
  v9 = BaseRegOpenKeyInternal(v10, a2, v21, v20, v7, &Handle);
  if ( !v9 )
  {
    v9 = RegSvcContextAllocate(&v18);
    if ( !v9 )
    {
      v13 = Handle;
      v14 = v18;
      *v18 = Handle;
      Handle = 0;
      if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
      {
        if ( v13 )
        {
          *((_DWORD *)v14 + 2) |= 2u;
          _InterlockedIncrement(&RestrictedHandlesQuota);
          if ( v16 != v9 )
            *((_DWORD *)v14 + 2) |= 4u;
        }
      }
      *a5 = v14;
      v18 = 0;
      v9 = 0;
    }
  }
LABEL_28:
  if ( v8 )
    RpcRevertToSelf();
  if ( v18 )
    RegSvcContextCleanup();
  if ( Handle )
    NtClose(Handle);
  return v9;
}

```

## disassembly

```asm
0x1800199a0  push    rbx
0x1800199a2  push    rsi
0x1800199a3  push    rdi
0x1800199a4  push    r12
0x1800199a6  push    r13
0x1800199a8  push    r14
0x1800199aa  push    r15
0x1800199ac  sub     rsp, 0F0h
0x1800199b3  mov     rax, cs:__security_cookie
0x1800199ba  xor     rax, rsp
0x1800199bd  mov     [rsp+128h+var_48], rax
0x1800199c5  mov     [rsp+128h+var_D0], r9d
0x1800199ca  mov     [rsp+128h+var_CC], r8d
0x1800199cf  mov     r12, rdx
0x1800199d2  mov     rdi, rcx
0x1800199d5  mov     r13, [rsp+128h+arg_20]
0x1800199dd  xor     r14d, r14d
0x1800199e0  mov     [rsp+128h+var_E0], r14
0x1800199e5  mov     [rsp+128h+var_E8], r14d
0x1800199ea  xor     r15d, r15d
0x1800199ed  mov     [rsp+128h+var_E4], r15d
0x1800199f2  mov     [rsp+128h+Handle], r14
0x1800199f7  mov     [r13+0], r15
0x1800199fb  test    rcx, rcx
0x1800199fe  jz      short loc_180019A09
0x180019a00  test    dword ptr [rcx+8], 0FFFFFFF8h
0x180019a07  jz      short loc_180019A13
0x180019a09  mov     ebx, 57h ; 'W'
0x180019a0e  jmp     loc_180019B57
0x180019a13  mov     rbx, [rcx]
0x180019a16  test    byte ptr [rcx+8], 4
0x180019a1a  jz      short loc_180019A26
0x180019a1c  mov     rcx, rbx; KeyHandle
0x180019a1f  call    RegSvcLogAllowedExactPathEvent
0x180019a24  jmp     short loc_180019A46
0x180019a26  test    byte ptr [rcx+8], 1
0x180019a2a  jz      short loc_180019A50
0x180019a2c  cmp     cs:RestrictedHandlesQuota, 10000h
0x180019a36  jge     short loc_180019A46
0x180019a38  lea     r8, [rsp+128h+var_E8]
0x180019a3d  call    RegSecCheckPath
0x180019a42  test    eax, eax
0x180019a44  jnz     short loc_180019A50
0x180019a46  mov     ebx, 5
0x180019a4b  jmp     loc_180019B57
0x180019a50  mov     esi, 2
0x180019a55  cmp     rbx, cs:RestrictedMachineHandle
0x180019a5c  jnz     short loc_180019A64
0x180019a5e  lea     r14d, [rsi-1]
0x180019a62  jmp     short loc_180019A6F
0x180019a64  cmp     rbx, cs:RestrictedUserHandle
0x180019a6b  cmovz   r14d, esi
0x180019a6f  xor     edx, edx; Val
0x180019a71  lea     r8d, [rdx+78h]; Size
0x180019a75  lea     rcx, [rsp+128h+RpcCallAttributes]; void *
0x180019a7a  call    memset_0
0x180019a7f  mov     [rsp+128h+RpcCallAttributes], 3
0x180019a87  lea     rdx, [rsp+128h+RpcCallAttributes]; RpcCallAttributes
0x180019a8c  xor     ecx, ecx; ClientBinding
0x180019a8e  call    cs:__imp_RpcServerInqCallAttributesW
0x180019a94  cmp     eax, 6D2h
0x180019a99  jz      short loc_180019ABA
0x180019a9b  test    eax, eax
0x180019a9d  jnz     short loc_180019AB2
0x180019a9f  cmp     [rsp+128h+var_A0], 6
0x180019aa7  jnb     short loc_180019ABA
0x180019aa9  lea     ecx, [rax+5]; exception
0x180019aac  call    cs:__imp_RpcRaiseException
0x180019ab2  mov     ecx, eax; exception
0x180019ab4  call    cs:__imp_RpcRaiseException
0x180019aba  xor     ecx, ecx; BindingHandle
0x180019abc  call    cs:__imp_RpcImpersonateClient
0x180019ac2  test    eax, eax
0x180019ac4  jz      short loc_180019ACE
0x180019ac6  mov     ecx, eax; exception
0x180019ac8  call    cs:__imp_RpcRaiseException
0x180019ace  mov     r15d, 1
0x180019ad4  mov     [rsp+128h+var_E4], r15d
0x180019ad9  lea     rax, [rsp+128h+Handle]
0x180019ade  mov     [rsp+128h+var_100], rax
0x180019ae3  mov     [rsp+128h+var_108], r14d
0x180019ae8  mov     r9d, [rsp+128h+var_D0]
0x180019aed  mov     r8d, [rsp+128h+var_CC]
0x180019af2  mov     rdx, r12
0x180019af5  mov     rcx, rbx
0x180019af8  call    BaseRegOpenKeyInternal
0x180019afd  mov     ebx, eax
0x180019aff  test    eax, eax
0x180019b01  jnz     short loc_180019B57
0x180019b03  lea     rcx, [rsp+128h+var_E0]
0x180019b08  call    RegSvcContextAllocate
0x180019b0d  mov     ebx, eax
0x180019b0f  test    eax, eax
0x180019b11  jnz     short loc_180019B57
0x180019b13  mov     rcx, [rsp+128h+Handle]
0x180019b18  mov     rax, [rsp+128h+var_E0]
0x180019b1d  mov     [rax], rcx
0x180019b20  mov     [rsp+128h+Handle], 0
0x180019b29  test    [rdi+8], r15b
0x180019b2d  jz      short loc_180019B48
0x180019b2f  test    rcx, rcx
0x180019b32  jz      short loc_180019B48
0x180019b34  or      [rax+8], esi
0x180019b37  lock inc cs:RestrictedHandlesQuota
0x180019b3e  cmp     [rsp+128h+var_E8], ebx
0x180019b42  jz      short loc_180019B48
0x180019b44  or      dword ptr [rax+8], 4
0x180019b48  mov     [r13+0], rax
0x180019b4c  mov     [rsp+128h+var_E0], 0
0x180019b55  xor     ebx, ebx
0x180019b57  test    r15d, r15d
0x180019b5a  jz      short loc_180019B62
0x180019b5c  call    cs:__imp_RpcRevertToSelf
0x180019b62  mov     rcx, [rsp+128h+var_E0]
0x180019b67  test    rcx, rcx
0x180019b6a  jz      short loc_180019B71
0x180019b6c  call    RegSvcContextCleanup
0x180019b71  mov     rcx, [rsp+128h+Handle]; Handle
0x180019b76  test    rcx, rcx
0x180019b79  jz      short loc_180019B81
0x180019b7b  call    cs:__imp_NtClose
0x180019b81  mov     eax, ebx
0x180019b83  mov     rcx, [rsp+128h+var_48]
0x180019b8b  xor     rcx, rsp; StackCookie
0x180019b8e  call    __security_check_cookie
0x180019b93  add     rsp, 0F0h
0x180019b9a  pop     r15
0x180019b9c  pop     r14
0x180019b9e  pop     r13
0x180019ba0  pop     r12
0x180019ba2  pop     rdi
0x180019ba3  pop     rsi
0x180019ba4  pop     rbx
0x180019ba5  retn
0x18001e6fa  push    rbp
0x18001e6fc  sub     rsp, 40h
0x18001e700  mov     rbp, rdx
0x18001e703  cmp     dword ptr [rbp+44h], 0
0x18001e707  jz      short loc_18001E710
0x18001e709  call    cs:__imp_RpcRevertToSelf
0x18001e70f  nop
0x18001e710  mov     rcx, [rbp+48h]
0x18001e714  test    rcx, rcx
0x18001e717  jz      short loc_18001E71F
0x18001e719  call    RegSvcContextCleanup
0x18001e71e  nop
0x18001e71f  mov     rcx, [rbp+50h]; Handle
0x18001e723  test    rcx, rcx
0x18001e726  jz      short loc_18001E72F
0x18001e728  call    cs:__imp_NtClose
0x18001e72e  nop
0x18001e72f  add     rsp, 40h
0x18001e733  pop     rbp
0x18001e734  retn
```
