# SafeBaseRegEnumKey

- ea: `0x18001ae40`
- end: `0x18001b033`
- name: `SafeBaseRegEnumKey`
- size: `499`
- prototype: `__int64 __fastcall(HANDLE *, ULONG, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1800059a0`
- `0x180007740`
- `0x180008042`
- `0x18001ae40`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001afc3`
- `RPCRT4!RpcRaiseException` at `0x18001afcc`
- `RPCRT4!RpcRaiseException` at `0x18001afe1`
- `RPCRT4!RpcRaiseException` at `0x18001afc3`
- `RPCRT4!RpcRaiseException` at `0x18001afcc`
- `RPCRT4!RpcRaiseException` at `0x18001afe1`
- `RPCRT4!RpcImpersonateClient` at `0x18001afd5`
- `RPCRT4!RpcImpersonateClient` at `0x18001afd5`
- `RPCRT4!RpcRevertToSelf` at `0x18001b000`
- `RPCRT4!RpcRevertToSelf` at `0x18001b000`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001afa8`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001afa8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001af33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001af6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001af33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001af6a`

## pseudocode

```c
__int64 __fastcall SafeBaseRegEnumKey(HANDLE *a1, ULONG a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  HLOCAL v11; // rax
  unsigned int v12; // ebx
  _OWORD *v13; // rax
  _WORD *v14; // rcx
  RPC_STATUS v15; // eax
  RPC_STATUS v16; // eax
  int RpcCallAttributes; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v19[36]; // [rsp+34h] [rbp-D4h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-B0h]

  if ( !a1
    || !a3
    || *(_WORD *)a3
    || (*(_BYTE *)(a3 + 2) & 1) != 0
    || !a4
    || *(_WORD *)a4
    || *(_WORD *)(a4 + 2)
    || *(_QWORD *)(a4 + 8)
    || !a5
    || !a6
    || *(_QWORD *)a6 )
  {
    return 87;
  }
  v11 = LocalAlloc(0x40u, *(unsigned __int16 *)(a3 + 2));
  *(_QWORD *)(a4 + 8) = v11;
  if ( !v11 )
    return 14;
  v13 = LocalAlloc(0x40u, 0x10u);
  *(_QWORD *)a6 = v13;
  if ( !v13 )
  {
LABEL_15:
    LocalFree(*(HLOCAL *)(a4 + 8));
    *(_QWORD *)(a4 + 8) = 0;
    return 14;
  }
  *v13 = 0;
  if ( *(_QWORD *)(a5 + 8) )
  {
    *(_QWORD *)(*(_QWORD *)a6 + 8LL) = LocalAlloc(0x40u, *(unsigned __int16 *)(a5 + 2));
    v14 = *(_WORD **)a6;
    if ( !*(_QWORD *)(*(_QWORD *)a6 + 8LL) )
    {
      LocalFree(v14);
      *(_QWORD *)a6 = 0;
      goto LABEL_15;
    }
    v14[1] = *(_WORD *)(a5 + 2);
  }
  *(_WORD *)a4 = 0;
  *(_WORD *)(a4 + 2) = *(_WORD *)(a3 + 2);
  memset_0(v19, 0, 0x74u);
  RpcCallAttributes = 3;
  v15 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
  if ( v15 != 1746 )
  {
    if ( v15 )
      RpcRaiseException(v15);
    if ( v20 < 6 )
      RpcRaiseException(5);
  }
  v16 = RpcImpersonateClient(0);
  if ( v16 )
    RpcRaiseException(v16);
  v12 = BaseRegEnumKeyOld(*a1, a2, a7);
  RpcRevertToSelf();
  return v12;
}

```

## disassembly

```asm
0x18001ae40  push    rbx
0x18001ae42  push    rbp
0x18001ae43  push    rsi
0x18001ae44  push    rdi
0x18001ae45  push    r12
0x18001ae47  push    r13
0x18001ae49  push    r14
0x18001ae4b  push    r15
0x18001ae4d  sub     rsp, 0C8h
0x18001ae54  mov     rax, cs:__security_cookie
0x18001ae5b  xor     rax, rsp
0x18001ae5e  mov     [rsp+108h+var_58], rax
0x18001ae66  mov     rbp, [rsp+108h+arg_20]
0x18001ae6e  xor     r13d, r13d
0x18001ae71  mov     rdi, [rsp+108h+arg_28]
0x18001ae79  mov     rbx, r9
0x18001ae7c  mov     r12, [rsp+108h+arg_30]
0x18001ae84  mov     rsi, r8
0x18001ae87  mov     r15d, edx
0x18001ae8a  mov     r14, rcx
0x18001ae8d  test    rcx, rcx
0x18001ae90  jz      loc_18001B008
0x18001ae96  test    r8, r8
0x18001ae99  jz      loc_18001B008
0x18001ae9f  cmp     [r8], r13w
0x18001aea3  jnz     loc_18001B008
0x18001aea9  test    byte ptr [r8+2], 1
0x18001aeae  jnz     loc_18001B008
0x18001aeb4  test    rbx, rbx
0x18001aeb7  jz      loc_18001B008
0x18001aebd  cmp     [r9], r13w
0x18001aec1  jnz     loc_18001B008
0x18001aec7  cmp     [r9+2], r13w
0x18001aecc  jnz     loc_18001B008
0x18001aed2  cmp     [r9+8], r13
0x18001aed6  jnz     loc_18001B008
0x18001aedc  test    rbp, rbp
0x18001aedf  jz      loc_18001B008
0x18001aee5  test    rdi, rdi
0x18001aee8  jz      loc_18001B008
0x18001aeee  cmp     [rdi], r13
0x18001aef1  jnz     loc_18001B008
0x18001aef7  movzx   edx, word ptr [r8+2]; uBytes
0x18001aefc  lea     ecx, [r13+40h]; uFlags
0x18001af00  call    cs:__imp_LocalAlloc
0x18001af06  mov     [rbx+8], rax
0x18001af0a  test    rax, rax
0x18001af0d  jnz     short loc_18001AF19
0x18001af0f  mov     ebx, 0Eh
0x18001af14  jmp     loc_18001B00D
0x18001af19  mov     edx, 10h; uBytes
0x18001af1e  lea     ecx, [rdx+30h]; uFlags
0x18001af21  call    cs:__imp_LocalAlloc
0x18001af27  mov     [rdi], rax
0x18001af2a  test    rax, rax
0x18001af2d  jnz     short loc_18001AF3F
0x18001af2f  mov     rcx, [rbx+8]; hMem
0x18001af33  call    cs:__imp_LocalFree
0x18001af39  mov     [rbx+8], r13
0x18001af3d  jmp     short loc_18001AF0F
0x18001af3f  xorps   xmm0, xmm0
0x18001af42  movups  xmmword ptr [rax], xmm0
0x18001af45  cmp     [rbp+8], r13
0x18001af49  jz      short loc_18001AF7D
0x18001af4b  movzx   edx, word ptr [rbp+2]; uBytes
0x18001af4f  mov     ecx, 40h ; '@'; uFlags
0x18001af54  call    cs:__imp_LocalAlloc
0x18001af5a  mov     rcx, [rdi]
0x18001af5d  mov     [rcx+8], rax
0x18001af61  mov     rcx, [rdi]; hMem
0x18001af64  cmp     [rcx+8], r13
0x18001af68  jnz     short loc_18001AF75
0x18001af6a  call    cs:__imp_LocalFree
0x18001af70  mov     [rdi], r13
0x18001af73  jmp     short loc_18001AF2F
0x18001af75  movzx   eax, word ptr [rbp+2]
0x18001af79  mov     [rcx+2], ax
0x18001af7d  xor     edx, edx; Val
0x18001af7f  mov     [rbx], r13w
0x18001af83  movzx   eax, word ptr [rsi+2]
0x18001af87  lea     rcx, [rsp+108h+var_D4]; void *
0x18001af8c  mov     [rbx+2], ax
0x18001af90  lea     r8d, [rdx+74h]; Size
0x18001af94  call    memset_0
0x18001af99  lea     rdx, [rsp+108h+RpcCallAttributes]; RpcCallAttributes
0x18001af9e  mov     [rsp+108h+RpcCallAttributes], 3
0x18001afa6  xor     ecx, ecx; ClientBinding
0x18001afa8  call    cs:__imp_RpcServerInqCallAttributesW
0x18001afae  cmp     eax, 6D2h
0x18001afb3  jz      short loc_18001AFD3
0x18001afb5  test    eax, eax
0x18001afb7  jnz     short loc_18001AFCA
0x18001afb9  cmp     [rsp+108h+var_B0], 6
0x18001afbe  jnb     short loc_18001AFD3
0x18001afc0  lea     ecx, [rax+5]; exception
0x18001afc3  call    cs:__imp_RpcRaiseException
0x18001afc9  int     3; Trap to Debugger
0x18001afca  mov     ecx, eax; exception
0x18001afcc  call    cs:__imp_RpcRaiseException
0x18001afd2  int     3; Trap to Debugger
0x18001afd3  xor     ecx, ecx; BindingHandle
0x18001afd5  call    cs:__imp_RpcImpersonateClient
0x18001afdb  test    eax, eax
0x18001afdd  jz      short loc_18001AFE8
0x18001afdf  mov     ecx, eax; exception
0x18001afe1  call    cs:__imp_RpcRaiseException
0x18001afe7  int     3; Trap to Debugger
0x18001afe8  mov     r9, [rdi]
0x18001afeb  mov     r8, rbx
0x18001afee  mov     rcx, [r14]; KeyHandle
0x18001aff1  mov     edx, r15d; Index
0x18001aff4  mov     [rsp+108h+var_E8], r12; __int64
0x18001aff9  call    BaseRegEnumKeyOld
0x18001affe  mov     ebx, eax
0x18001b000  call    cs:__imp_RpcRevertToSelf
0x18001b006  jmp     short loc_18001B00D
0x18001b008  mov     ebx, 57h ; 'W'
0x18001b00d  mov     eax, ebx
0x18001b00f  mov     rcx, [rsp+108h+var_58]
0x18001b017  xor     rcx, rsp; StackCookie
0x18001b01a  call    __security_check_cookie
0x18001b01f  add     rsp, 0C8h
0x18001b026  pop     r15
0x18001b028  pop     r14
0x18001b02a  pop     r13
0x18001b02c  pop     r12
0x18001b02e  pop     rdi
0x18001b02f  pop     rsi
0x18001b030  pop     rbp
0x18001b031  pop     rbx
0x18001b032  retn
```
