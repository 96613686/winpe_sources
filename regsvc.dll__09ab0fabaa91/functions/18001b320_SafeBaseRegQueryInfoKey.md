# SafeBaseRegQueryInfoKey

- ea: `0x18001b320`
- end: `0x18001b542`
- name: `SafeBaseRegQueryInfoKey`
- size: `546`
- prototype: `__int64 __fastcall(HKEY *, _WORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001b320`
- `0x18001b9c0`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001b4a1`
- `RPCRT4!RpcRaiseException` at `0x18001b4aa`
- `RPCRT4!RpcRaiseException` at `0x18001b4bf`
- `RPCRT4!RpcRaiseException` at `0x18001b4a1`
- `RPCRT4!RpcRaiseException` at `0x18001b4aa`
- `RPCRT4!RpcRaiseException` at `0x18001b4bf`
- `RPCRT4!RpcImpersonateClient` at `0x18001b4b3`
- `RPCRT4!RpcImpersonateClient` at `0x18001b4b3`
- `RPCRT4!RpcRevertToSelf` at `0x18001b50f`
- `RPCRT4!RpcRevertToSelf` at `0x18001b50f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b483`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001b483`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b423`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b423`

## pseudocode

```c
__int64 __fastcall SafeBaseRegQueryInfoKey(
        HKEY *a1,
        _WORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  HLOCAL v14; // rax
  unsigned int InfoKeyOldInternal; // ebx
  int v16; // edi
  RPC_STATUS v17; // eax
  RPC_STATUS v18; // eax
  int RpcCallAttributes; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v21[36]; // [rsp+74h] [rbp-D4h] BYREF
  unsigned int v22; // [rsp+98h] [rbp-B0h]

  if ( a1
    && a2
    && !*a2
    && a3
    && !*(_WORD *)a3
    && !*(_WORD *)(a3 + 2)
    && !*(_QWORD *)(a3 + 8)
    && a4
    && a5
    && a7
    && a8
    && a9
    && a11 )
  {
    if ( !a2[1] || (v14 = LocalAlloc(0x40u, (unsigned __int16)a2[1]), (*(_QWORD *)(a3 + 8) = v14) != 0) )
    {
      *(_WORD *)(a3 + 2) = a2[1];
      *(_WORD *)a3 = 0;
      if ( *a1 == HKEY_PERFORMANCE_DATA || *a1 == HKEY_PERFORMANCE_TEXT || (v16 = 0, *a1 == HKEY_PERFORMANCE_NLSTEXT) )
      {
        memset_0(v21, 0, 0x74u);
        RpcCallAttributes = 3;
        v17 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
        if ( v17 != 1746 )
        {
          if ( v17 )
            RpcRaiseException(v17);
          if ( v22 < 6 )
            RpcRaiseException(5);
        }
        v18 = RpcImpersonateClient(0);
        if ( v18 )
          RpcRaiseException(v18);
        v16 = 1;
      }
      InfoKeyOldInternal = BaseRegQueryInfoKeyOldInternal(*a1, a6, a7, a8, a9, a10, a11);
      if ( v16 )
        RpcRevertToSelf();
    }
    else
    {
      return 14;
    }
  }
  else
  {
    return 87;
  }
  return InfoKeyOldInternal;
}

```

## disassembly

```asm
0x18001b320  push    rbx
0x18001b322  push    rbp
0x18001b323  push    rsi
0x18001b324  push    rdi
0x18001b325  push    r12
0x18001b327  push    r13
0x18001b329  push    r14
0x18001b32b  push    r15
0x18001b32d  sub     rsp, 108h
0x18001b334  mov     rax, cs:__security_cookie
0x18001b33b  xor     rax, rsp
0x18001b33e  mov     [rsp+148h+var_58], rax
0x18001b346  mov     rax, [rsp+148h+arg_28]
0x18001b34e  mov     rsi, rcx
0x18001b351  mov     r14, [rsp+148h+arg_20]
0x18001b359  xor     ecx, ecx
0x18001b35b  mov     r15, [rsp+148h+arg_30]
0x18001b363  mov     rbp, r9
0x18001b366  mov     r12, [rsp+148h+arg_38]
0x18001b36e  mov     rbx, r8
0x18001b371  mov     r13, [rsp+148h+arg_40]
0x18001b379  mov     rdi, rdx
0x18001b37c  mov     [rsp+148h+var_E8], rax
0x18001b381  mov     rax, [rsp+148h+arg_48]
0x18001b389  mov     [rsp+148h+var_F0], rax
0x18001b38e  mov     rax, [rsp+148h+arg_50]
0x18001b396  mov     [rsp+148h+var_F8], rax
0x18001b39b  test    rsi, rsi
0x18001b39e  jz      loc_18001B517
0x18001b3a4  test    rdx, rdx
0x18001b3a7  jz      loc_18001B517
0x18001b3ad  cmp     [rdx], cx
0x18001b3b0  jnz     loc_18001B517
0x18001b3b6  test    rbx, rbx
0x18001b3b9  jz      loc_18001B517
0x18001b3bf  cmp     [r8], cx
0x18001b3c3  jnz     loc_18001B517
0x18001b3c9  cmp     [r8+2], cx
0x18001b3ce  jnz     loc_18001B517
0x18001b3d4  cmp     [r8+8], rcx
0x18001b3d8  jnz     loc_18001B517
0x18001b3de  test    r9, r9
0x18001b3e1  jz      loc_18001B517
0x18001b3e7  test    r14, r14
0x18001b3ea  jz      loc_18001B517
0x18001b3f0  test    r15, r15
0x18001b3f3  jz      loc_18001B517
0x18001b3f9  test    r12, r12
0x18001b3fc  jz      loc_18001B517
0x18001b402  test    r13, r13
0x18001b405  jz      loc_18001B517
0x18001b40b  test    rax, rax
0x18001b40e  jz      loc_18001B517
0x18001b414  cmp     [rdx+2], cx
0x18001b418  jz      short loc_18001B43C
0x18001b41a  movzx   edx, word ptr [rdx+2]; uBytes
0x18001b41e  mov     ecx, 40h ; '@'; uFlags
0x18001b423  call    cs:__imp_LocalAlloc
0x18001b429  xor     ecx, ecx
0x18001b42b  mov     [rbx+8], rax
0x18001b42f  test    rax, rax
0x18001b432  jnz     short loc_18001B43C
0x18001b434  lea     ebx, [rax+0Eh]
0x18001b437  jmp     loc_18001B51C
0x18001b43c  movzx   eax, word ptr [rdi+2]
0x18001b440  mov     [rbx+2], ax
0x18001b444  mov     [rbx], cx
0x18001b447  cmp     qword ptr [rsi], 0FFFFFFFF80000004h
0x18001b44e  jz      short loc_18001B464
0x18001b450  cmp     qword ptr [rsi], 0FFFFFFFF80000050h
0x18001b457  jz      short loc_18001B464
0x18001b459  cmp     qword ptr [rsi], 0FFFFFFFF80000060h
0x18001b460  mov     edi, ecx
0x18001b462  jnz     short loc_18001B4CB
0x18001b464  xor     edx, edx; Val
0x18001b466  lea     rcx, [rsp+148h+var_D4]; void *
0x18001b46b  lea     r8d, [rdx+74h]; Size
0x18001b46f  call    memset_0
0x18001b474  lea     rdx, [rsp+148h+RpcCallAttributes]; RpcCallAttributes
0x18001b479  mov     [rsp+148h+RpcCallAttributes], 3
0x18001b481  xor     ecx, ecx; ClientBinding
0x18001b483  call    cs:__imp_RpcServerInqCallAttributesW
0x18001b489  cmp     eax, 6D2h
0x18001b48e  jz      short loc_18001B4B1
0x18001b490  test    eax, eax
0x18001b492  jnz     short loc_18001B4A8
0x18001b494  cmp     [rsp+148h+var_B0], 6
0x18001b49c  jnb     short loc_18001B4B1
0x18001b49e  lea     ecx, [rax+5]; exception
0x18001b4a1  call    cs:__imp_RpcRaiseException
0x18001b4a7  int     3; Trap to Debugger
0x18001b4a8  mov     ecx, eax; exception
0x18001b4aa  call    cs:__imp_RpcRaiseException
0x18001b4b0  int     3; Trap to Debugger
0x18001b4b1  xor     ecx, ecx; BindingHandle
0x18001b4b3  call    cs:__imp_RpcImpersonateClient
0x18001b4b9  test    eax, eax
0x18001b4bb  jz      short loc_18001B4C6
0x18001b4bd  mov     ecx, eax; exception
0x18001b4bf  call    cs:__imp_RpcRaiseException
0x18001b4c5  int     3; Trap to Debugger
0x18001b4c6  mov     edi, 1
0x18001b4cb  mov     rax, [rsp+148h+var_F8]
0x18001b4d0  mov     r9, r14
0x18001b4d3  mov     rcx, [rsi]; HKEY
0x18001b4d6  mov     r8, rbp
0x18001b4d9  mov     [rsp+148h+var_100], rax; __int64
0x18001b4de  mov     rdx, rbx
0x18001b4e1  mov     rax, [rsp+148h+var_F0]
0x18001b4e6  mov     [rsp+148h+var_108], rax; __int64
0x18001b4eb  mov     rax, [rsp+148h+var_E8]
0x18001b4f0  mov     [rsp+148h+var_110], r13; __int64
0x18001b4f5  mov     [rsp+148h+var_118], r12; __int64
0x18001b4fa  mov     [rsp+148h+var_120], r15; __int64
0x18001b4ff  mov     [rsp+148h+var_128], rax; __int64
0x18001b504  call    BaseRegQueryInfoKeyOldInternal
0x18001b509  mov     ebx, eax
0x18001b50b  test    edi, edi
0x18001b50d  jz      short loc_18001B51C
0x18001b50f  call    cs:__imp_RpcRevertToSelf
0x18001b515  jmp     short loc_18001B51C
0x18001b517  mov     ebx, 57h ; 'W'
0x18001b51c  mov     eax, ebx
0x18001b51e  mov     rcx, [rsp+148h+var_58]
0x18001b526  xor     rcx, rsp; StackCookie
0x18001b529  call    __security_check_cookie
0x18001b52e  add     rsp, 108h
0x18001b535  pop     r15
0x18001b537  pop     r14
0x18001b539  pop     r13
0x18001b53b  pop     r12
0x18001b53d  pop     rdi
0x18001b53e  pop     rsi
0x18001b53f  pop     rbp
0x18001b540  pop     rbx
0x18001b541  retn
```
