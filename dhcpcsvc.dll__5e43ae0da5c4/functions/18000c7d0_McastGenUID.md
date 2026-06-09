# McastGenUID

- ea: `0x18000c7d0`
- end: `0x18000c97e`
- name: `McastGenUID`
- size: `430`
- prototype: `DWORD __stdcall(LPMCAST_CLIENT_UID pRequestID)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002760`
- `0x180002c50`
- `0x18000c7d0`
- `0x18000f4ec`
- `0x180010aac`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c8a2`
- `RPCRT4!NdrClientCall3` at `0x18000c8a2`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010c2e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010c2e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c85e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c8be`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c8dc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c85e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c8be`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c8dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000c83d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000c83d`

## pseudocode

```c
DWORD __stdcall McastGenUID(LPMCAST_CLIENT_UID pRequestID)
{
  DWORD Pointer; // ebx
  DWORD ClientUIDLength; // eax
  LPWSTR CommandLineW; // rax
  LPWSTR v5; // rax
  size_t Size[2]; // [rsp+38h] [rbp-20h] BYREF

  *(_OWORD *)Size = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 272, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 273, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else if ( pRequestID && pRequestID->ClientUID && (ClientUIDLength = pRequestID->ClientUIDLength) != 0 )
  {
    LODWORD(Size[1]) = pRequestID->ClientUIDLength;
    Size[0] = (size_t)LocalAlloc(0x40u, ClientUIDLength);
    if ( Size[0] )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_S(1028, 274, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
      }
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x28u, 0).Pointer;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v5 = GetCommandLineW();
        WPP_SF_DS(1028, 275, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v5);
      }
      if ( !Pointer )
        memcpy_0(pRequestID->ClientUID, (const void *)Size[0], LODWORD(Size[1]));
    }
    else
    {
      Pointer = 8;
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpMidlUserFree(Size);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 276, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000c7d0  mov     [rsp+arg_10], rbx
0x18000c7d5  mov     [rsp+arg_0], rcx
0x18000c7da  push    rdi
0x18000c7db  sub     rsp, 50h
0x18000c7df  mov     rdi, rcx
0x18000c7e2  xorps   xmm0, xmm0
0x18000c7e5  movups  xmmword ptr [rsp+58h+Size], xmm0
0x18000c7ea  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c7f1  jz      short loc_18000C809
0x18000c7f3  mov     edx, 110h
0x18000c7f8  mov     ecx, 404h
0x18000c7fd  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c804  call    WPP_SF_
0x18000c809  call    DhcpIsFSEGuestSystem
0x18000c80e  test    eax, eax
0x18000c810  jnz     loc_18000C91D
0x18000c816  test    rdi, rdi
0x18000c819  jnz     short loc_18000C825
0x18000c81b  mov     ebx, 57h ; 'W'
0x18000c820  jmp     loc_18000C945
0x18000c825  cmp     qword ptr [rdi], 0
0x18000c829  jz      short loc_18000C81B
0x18000c82b  mov     eax, [rdi+8]
0x18000c82e  test    eax, eax
0x18000c830  jz      short loc_18000C81B
0x18000c832  mov     dword ptr [rsp+58h+Size+8], eax
0x18000c836  mov     edx, eax; uBytes
0x18000c838  mov     ecx, 40h ; '@'; uFlags
0x18000c83d  call    cs:__imp_LocalAlloc
0x18000c843  mov     [rsp+58h+Size], rax
0x18000c848  test    rax, rax
0x18000c84b  jnz     short loc_18000C855
0x18000c84d  lea     ebx, [rax+8]
0x18000c850  jmp     loc_18000C945
0x18000c855  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c85c  jz      short loc_18000C87E
0x18000c85e  call    cs:__imp_GetCommandLineW
0x18000c864  mov     r9, rax
0x18000c867  mov     edx, 112h
0x18000c86c  mov     ecx, 404h
0x18000c871  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c878  call    WPP_SF_S
0x18000c87d  nop
0x18000c87e  mov     [rsp+58h+arg_8], 0
0x18000c887  lea     rax, [rsp+58h+Size]
0x18000c88c  mov     [rsp+58h+var_38], rax
0x18000c891  xor     r9d, r9d
0x18000c894  xor     r8d, r8d; pReturnValue
0x18000c897  lea     edx, [r9+28h]; nProcNum
0x18000c89b  lea     rcx, pProxyInfo; pProxyInfo
0x18000c8a2  call    cs:__imp_NdrClientCall3
0x18000c8a8  mov     rbx, rax
0x18000c8ab  mov     [rsp+58h+arg_8], rax
0x18000c8b0  mov     [rsp+58h+var_28], eax
0x18000c8b4  jmp     short loc_18000C8D3
0x18000c8b6  mov     edi, eax
0x18000c8b8  mov     ebx, eax
0x18000c8ba  mov     [rsp+58h+var_28], eax
0x18000c8be  call    cs:__imp_GetCommandLineW
0x18000c8c4  mov     rdx, rax
0x18000c8c7  mov     ecx, ebx
0x18000c8c9  call    TraceRpcException
0x18000c8ce  mov     rdi, [rsp+58h+arg_0]
0x18000c8d3  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c8da  jz      short loc_18000C900
0x18000c8dc  call    cs:__imp_GetCommandLineW
0x18000c8e2  mov     edx, 113h
0x18000c8e7  mov     ecx, 404h
0x18000c8ec  mov     [rsp+58h+var_38], rax
0x18000c8f1  mov     r9d, ebx
0x18000c8f4  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c8fb  call    WPP_SF_DS
0x18000c900  test    ebx, ebx
0x18000c902  jnz     short loc_18000C945
0x18000c904  mov     rdx, [rsp+58h+Size]; Src
0x18000c909  test    rdx, rdx
0x18000c90c  jz      short loc_18000C945
0x18000c90e  mov     r8d, dword ptr [rsp+58h+Size+8]; Size
0x18000c913  mov     rcx, [rdi]; void *
0x18000c916  call    memcpy_0
0x18000c91b  jmp     short loc_18000C945
0x18000c91d  mov     r9d, 32h ; '2'
0x18000c923  mov     ebx, r9d
0x18000c926  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000c92d  jz      short loc_18000C945
0x18000c92f  mov     edx, 111h
0x18000c934  mov     ecx, 401h
0x18000c939  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c940  call    WPP_SF_d
0x18000c945  lea     rcx, [rsp+58h+Size]
0x18000c94a  call    DhcpMidlUserFree
0x18000c94f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c956  jz      short loc_18000C971
0x18000c958  mov     edx, 114h
0x18000c95d  mov     ecx, 404h
0x18000c962  mov     r9d, ebx
0x18000c965  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c96c  call    WPP_SF_d
0x18000c971  mov     eax, ebx
0x18000c973  mov     rbx, [rsp+58h+arg_10]
0x18000c978  add     rsp, 50h
0x18000c97c  pop     rdi
0x18000c97d  retn
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
