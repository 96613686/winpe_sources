# EfspGenerateKey

- ea: `0x18000ce5c`
- end: `0x18000d034`
- name: `EfspGenerateKey`
- size: `472`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000c7c0`
- `0x18000c930`

## callees

- `0x18000ce5c`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf15`
- `RPCRT4!RpcRevertToSelf` at `0x18000d00f`
- `RPCRT4!RpcRevertToSelf` at `0x18000d00f`
- `RPCRT4!RpcImpersonateClient` at `0x18000cedf`
- `RPCRT4!RpcImpersonateClient` at `0x18000cedf`
- `EFSCORE!EfsDllConstructEFS` at `0x18000cf7e`
- `EFSCORE!EfsDllConstructEFS` at `0x18000cf7e`
- `EFSCORE!EfsDllValidateEfsStream` at `0x18000cebb`
- `EFSCORE!EfsDllValidateEfsStream` at `0x18000cebb`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000cf28`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000cf28`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000cfea`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000cfea`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000cfff`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000cfff`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000cf05`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000cf05`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000cf4b`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000cf4b`
- `EFSCORE!EfsDllFreeHeap` at `0x18000cfc0`
- `EFSCORE!EfsDllFreeHeap` at `0x18000cfd5`
- `EFSCORE!EfsDllFreeHeap` at `0x18000cfc0`
- `EFSCORE!EfsDllFreeHeap` at `0x18000cfd5`

## pseudocode

```c
__int64 __fastcall EfspGenerateKey(__int64 a1, unsigned int a2, char a3, __int64 a4, _QWORD *a5, _QWORD *a6)
{
  int v9; // ebx
  int v11; // r14d
  int v12; // r15d
  DWORD LastError; // eax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v18; // [rsp+30h] [rbp-89h] BYREF
  __int64 v19; // [rsp+38h] [rbp-81h] BYREF
  __int64 v20; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v21[176]; // [rsp+50h] [rbp-69h] BYREF
  char v22; // [rsp+110h] [rbp+57h] BYREF

  v18 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  memset_0(v21, 0, 0x70u);
  v19 = 0;
  v20 = 0;
  v22 = 0;
  if ( a1 && ((unsigned int)EfsDllValidateEfsStream(a1, a2, &v22) || !v22) )
  {
    v18 = -1073741811;
  }
  else if ( RpcImpersonateClient(0) )
  {
    v18 = -1073741790;
  }
  else
  {
    v9 = 1;
    if ( (unsigned __int8)EfsDllGetUserInfo(v21)
      && (v11 = 1, (unsigned int)EfsDllLoadUserProfile(v21, 0))
      && (LOBYTE(v14) = a3, v12 = 1, (unsigned __int8)EfsDllConstructEFS(v21, a1, v14, a4, &v19, &v20)) )
    {
      v15 = v20;
      v20 = 0;
      *a6 = v15;
      v16 = v19;
      v19 = 0;
      *a5 = v16;
    }
    else
    {
      LastError = GetLastError();
      if ( !(unsigned int)EfsDllErrorToNtStatus(LastError, &v18) )
        v18 = -1073741823;
    }
  }
  if ( v19 )
    EfsDllFreeHeap();
  if ( v20 )
    EfsDllFreeHeap();
  if ( v12 )
    EfsDllUnloadUserProfile(v21);
  if ( v11 )
    EfsDllFreeUserInfo(v21);
  if ( v9 )
    RpcRevertToSelf();
  return v18;
}

```

## disassembly

```asm
0x18000ce5c  push    rbp
0x18000ce5e  push    rbx
0x18000ce5f  push    rsi
0x18000ce60  push    rdi
0x18000ce61  push    r12
0x18000ce63  push    r13
0x18000ce65  push    r14
0x18000ce67  push    r15
0x18000ce69  lea     rbp, [rsp-0Fh]
0x18000ce6e  sub     rsp, 0C8h
0x18000ce75  mov     r13b, r8b
0x18000ce78  mov     [rsp+100h+var_D0], 0
0x18000ce80  mov     esi, edx
0x18000ce82  mov     rdi, rcx
0x18000ce85  xor     ebx, ebx
0x18000ce87  lea     rcx, [rbp+47h+var_B0]; void *
0x18000ce8b  xor     edx, edx; Val
0x18000ce8d  mov     r12, r9
0x18000ce90  xor     r14d, r14d
0x18000ce93  xor     r15d, r15d
0x18000ce96  lea     r8d, [rbx+70h]; Size
0x18000ce9a  call    memset_0
0x18000ce9f  xor     eax, eax
0x18000cea1  mov     [rsp+100h+var_C8], rax
0x18000cea6  mov     [rbp+47h+var_C0], rax
0x18000ceaa  mov     [rbp+47h+arg_0], al
0x18000cead  test    rdi, rdi
0x18000ceb0  jz      short loc_18000CEDD
0x18000ceb2  lea     r8, [rbp+47h+arg_0]
0x18000ceb6  mov     edx, esi
0x18000ceb8  mov     rcx, rdi
0x18000cebb  call    cs:__imp_EfsDllValidateEfsStream
0x18000cec2  nop     dword ptr [rax+rax+00h]
0x18000cec7  test    eax, eax
0x18000cec9  jnz     short loc_18000CED0
0x18000cecb  cmp     [rbp+47h+arg_0], bl
0x18000cece  jnz     short loc_18000CEDD
0x18000ced0  mov     [rsp+100h+var_D0], 0C000000Dh
0x18000ced8  jmp     loc_18000CFB6
0x18000cedd  xor     ecx, ecx; BindingHandle
0x18000cedf  call    cs:__imp_RpcImpersonateClient
0x18000cee6  nop     dword ptr [rax+rax+00h]
0x18000ceeb  test    eax, eax
0x18000ceed  jz      short loc_18000CEFC
0x18000ceef  mov     [rsp+100h+var_D0], 0C0000022h
0x18000cef7  jmp     loc_18000CFB6
0x18000cefc  lea     rcx, [rbp+47h+var_B0]
0x18000cf00  mov     ebx, 1
0x18000cf05  call    cs:__imp_EfsDllGetUserInfo
0x18000cf0c  nop     dword ptr [rax+rax+00h]
0x18000cf11  test    al, al
0x18000cf13  jnz     short loc_18000CF42
0x18000cf15  call    cs:__imp_GetLastError
0x18000cf1c  nop     dword ptr [rax+rax+00h]
0x18000cf21  mov     ecx, eax
0x18000cf23  lea     rdx, [rsp+100h+var_D0]
0x18000cf28  call    cs:__imp_EfsDllErrorToNtStatus
0x18000cf2f  nop     dword ptr [rax+rax+00h]
0x18000cf34  test    eax, eax
0x18000cf36  jnz     short loc_18000CFB6
0x18000cf38  mov     [rsp+100h+var_D0], 0C0000001h
0x18000cf40  jmp     short loc_18000CFB6
0x18000cf42  xor     edx, edx
0x18000cf44  lea     rcx, [rbp+47h+var_B0]
0x18000cf48  mov     r14d, ebx
0x18000cf4b  call    cs:__imp_EfsDllLoadUserProfile
0x18000cf52  nop     dword ptr [rax+rax+00h]
0x18000cf57  test    eax, eax
0x18000cf59  jz      short loc_18000CF15
0x18000cf5b  lea     rax, [rbp+47h+var_C0]
0x18000cf5f  mov     r9, r12
0x18000cf62  mov     [rsp+100h+var_D8], rax
0x18000cf67  lea     rcx, [rbp+47h+var_B0]
0x18000cf6b  lea     rax, [rsp+100h+var_C8]
0x18000cf70  mov     r8b, r13b
0x18000cf73  mov     rdx, rdi
0x18000cf76  mov     [rsp+100h+var_E0], rax
0x18000cf7b  mov     r15d, ebx
0x18000cf7e  call    cs:__imp_EfsDllConstructEFS
0x18000cf85  nop     dword ptr [rax+rax+00h]
0x18000cf8a  test    al, al
0x18000cf8c  jz      short loc_18000CF15
0x18000cf8e  mov     rax, [rbp+47h+var_C0]
0x18000cf92  mov     rcx, [rbp+47h+arg_28]
0x18000cf96  mov     [rbp+47h+var_C0], 0
0x18000cf9e  mov     [rcx], rax
0x18000cfa1  mov     rax, [rsp+100h+var_C8]
0x18000cfa6  mov     rcx, [rbp+47h+arg_20]
0x18000cfaa  mov     [rsp+100h+var_C8], 0
0x18000cfb3  mov     [rcx], rax
0x18000cfb6  mov     rcx, [rsp+100h+var_C8]
0x18000cfbb  test    rcx, rcx
0x18000cfbe  jz      short loc_18000CFCC
0x18000cfc0  call    cs:__imp_EfsDllFreeHeap
0x18000cfc7  nop     dword ptr [rax+rax+00h]
0x18000cfcc  mov     rcx, [rbp+47h+var_C0]
0x18000cfd0  test    rcx, rcx
0x18000cfd3  jz      short loc_18000CFE1
0x18000cfd5  call    cs:__imp_EfsDllFreeHeap
0x18000cfdc  nop     dword ptr [rax+rax+00h]
0x18000cfe1  test    r15d, r15d
0x18000cfe4  jz      short loc_18000CFF6
0x18000cfe6  lea     rcx, [rbp+47h+var_B0]
0x18000cfea  call    cs:__imp_EfsDllUnloadUserProfile
0x18000cff1  nop     dword ptr [rax+rax+00h]
0x18000cff6  test    r14d, r14d
0x18000cff9  jz      short loc_18000D00B
0x18000cffb  lea     rcx, [rbp+47h+var_B0]
0x18000cfff  call    cs:__imp_EfsDllFreeUserInfo
0x18000d006  nop     dword ptr [rax+rax+00h]
0x18000d00b  test    ebx, ebx
0x18000d00d  jz      short loc_18000D01B
0x18000d00f  call    cs:__imp_RpcRevertToSelf
0x18000d016  nop     dword ptr [rax+rax+00h]
0x18000d01b  mov     eax, [rsp+100h+var_D0]
0x18000d01f  add     rsp, 0C8h
0x18000d026  pop     r15
0x18000d028  pop     r14
0x18000d02a  pop     r13
0x18000d02c  pop     r12
0x18000d02e  pop     rdi
0x18000d02f  pop     rsi
0x18000d030  pop     rbx
0x18000d031  pop     rbp
0x18000d032  retn
```
