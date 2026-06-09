# DhcpGetTraceArray

- ea: `0x180007aa0`
- end: `0x180007bf6`
- name: `DhcpGetTraceArray`
- size: `342`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002c50`
- `0x180007aa0`
- `0x18000f4ec`
- `0x180010aac`
- `0x180011f08`
- `0x1800127f0`
- `0x180012a40`
- `0x180012df0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180007b34`
- `RPCRT4!NdrClientCall3` at `0x180007b34`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007af0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007b50`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007b6e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007af0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007b50`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007b6e`

## pseudocode

```c
__int64 __fastcall DhcpGetTraceArray(__int64 a1, __int64 a2, __int64 a3)
{
  char v4; // al
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  LPWSTR v7; // rax
  __int64 v8; // rcx
  void **v10; // [rsp+20h] [rbp-38h]
  void *Src[2]; // [rsp+38h] [rbp-20h] BYREF

  *(_OWORD *)Src = 0;
  v4 = xmmword_18001E1E0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    WPP_SF_q(a1, 213, a3, a1);
    v4 = xmmword_18001E1E0;
  }
  if ( a1 && *(_QWORD *)a1 )
  {
    if ( (v4 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_S(1028, 214, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
    }
    v10 = Src;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Fu, 0).Pointer;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v7 = GetCommandLineW();
      WPP_SF_DS(1028, 215, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v7);
    }
    if ( !Pointer && LODWORD(Src[1]) && Src[0] )
    {
      memcpy_0(*(void **)a1, Src[0], 224LL * LODWORD(Src[1]));
      *(_DWORD *)(a1 + 8) = Src[1];
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpMidlUserFree(Src);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    LODWORD(v10) = Pointer;
    WPP_SF_qD(v8, 216, WPP_e15037783097355a5233924022d92169_Traceguids, a1, v10);
  }
  return Pointer;
}

```

## disassembly

```asm
0x180007aa0  mov     [rsp+arg_10], rbx
0x180007aa5  mov     [rsp+arg_0], rcx
0x180007aaa  push    rdi
0x180007aab  sub     rsp, 50h
0x180007aaf  mov     rdi, rcx
0x180007ab2  xorps   xmm0, xmm0
0x180007ab5  movups  xmmword ptr [rsp+58h+Src], xmm0
0x180007aba  mov     al, byte ptr cs:xmmword_18001E1E0
0x180007ac0  test    al, 10h
0x180007ac2  jz      short loc_180007AD7
0x180007ac4  mov     edx, 0D5h
0x180007ac9  mov     r9, rcx
0x180007acc  call    WPP_SF_q
0x180007ad1  mov     al, byte ptr cs:xmmword_18001E1E0
0x180007ad7  test    rdi, rdi
0x180007ada  jnz     short loc_180007AE6
0x180007adc  mov     ebx, 57h ; 'W'
0x180007ae1  jmp     loc_180007BBE
0x180007ae6  cmp     qword ptr [rdi], 0
0x180007aea  jz      short loc_180007ADC
0x180007aec  test    al, 10h
0x180007aee  jz      short loc_180007B10
0x180007af0  call    cs:__imp_GetCommandLineW
0x180007af6  mov     r9, rax
0x180007af9  mov     edx, 0D6h
0x180007afe  mov     ecx, 404h
0x180007b03  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007b0a  call    WPP_SF_S
0x180007b0f  nop
0x180007b10  mov     [rsp+58h+arg_8], 0
0x180007b19  lea     rax, [rsp+58h+Src]
0x180007b1e  mov     [rsp+58h+var_38], rax
0x180007b23  xor     r9d, r9d
0x180007b26  xor     r8d, r8d; pReturnValue
0x180007b29  lea     edx, [r9+1Fh]; nProcNum
0x180007b2d  lea     rcx, pProxyInfo; pProxyInfo
0x180007b34  call    cs:__imp_NdrClientCall3
0x180007b3a  mov     rbx, rax
0x180007b3d  mov     [rsp+58h+arg_8], rax
0x180007b42  mov     [rsp+58h+var_28], eax
0x180007b46  jmp     short loc_180007B65
0x180007b48  mov     edi, eax
0x180007b4a  mov     ebx, eax
0x180007b4c  mov     [rsp+58h+var_28], eax
0x180007b50  call    cs:__imp_GetCommandLineW
0x180007b56  mov     rdx, rax
0x180007b59  mov     ecx, ebx
0x180007b5b  call    TraceRpcException
0x180007b60  mov     rdi, [rsp+58h+arg_0]
0x180007b65  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007b6c  jz      short loc_180007B92
0x180007b6e  call    cs:__imp_GetCommandLineW
0x180007b74  mov     edx, 0D7h
0x180007b79  mov     ecx, 404h
0x180007b7e  mov     [rsp+58h+var_38], rax
0x180007b83  mov     r9d, ebx
0x180007b86  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007b8d  call    WPP_SF_DS
0x180007b92  test    ebx, ebx
0x180007b94  jnz     short loc_180007BBE
0x180007b96  mov     eax, dword ptr [rsp+58h+Src+8]
0x180007b9a  test    eax, eax
0x180007b9c  jz      short loc_180007BBE
0x180007b9e  mov     rdx, [rsp+58h+Src]; Src
0x180007ba3  test    rdx, rdx
0x180007ba6  jz      short loc_180007BBE
0x180007ba8  imul    r8, rax, 0E0h; Size
0x180007baf  mov     rcx, [rdi]; void *
0x180007bb2  call    memcpy_0
0x180007bb7  mov     eax, dword ptr [rsp+58h+Src+8]
0x180007bbb  mov     [rdi+8], eax
0x180007bbe  lea     rcx, [rsp+58h+Src]
0x180007bc3  call    DhcpMidlUserFree
0x180007bc8  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007bcf  jz      short loc_180007BE9
0x180007bd1  mov     edx, 0D8h
0x180007bd6  mov     dword ptr [rsp+58h+var_38], ebx
0x180007bda  mov     r9, rdi
0x180007bdd  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007be4  call    WPP_SF_qD
0x180007be9  mov     eax, ebx
0x180007beb  mov     rbx, [rsp+58h+arg_10]
0x180007bf0  add     rsp, 50h
0x180007bf4  pop     rdi
0x180007bf5  retn
0x180010c20  push    rbp
0x180010c22  sub     rsp, 30h
0x180010c26  mov     rbp, rdx
0x180010c29  mov     rcx, [rcx]
0x180010c2c  mov     ecx, [rcx]; ExceptionCode
0x180010c2e  call    cs:__imp_I_RpcExceptionFilter
0x180010c34  nop
0x180010c35  add     rsp, 30h
0x180010c39  pop     rbp
0x180010c3a  retn
```
