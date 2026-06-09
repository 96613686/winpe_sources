# DhcpGetDhcpServicedConnections

- ea: `0x180007200`
- end: `0x18000746c`
- name: `DhcpGetDhcpServicedConnections`
- size: `620`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001f90`
- `0x180002c50`
- `0x180003110`
- `0x180003210`
- `0x180007200`
- `0x18000f4ec`
- `0x180010aac`
- `0x180011298`
- `0x1800112d0`
- `0x1800127f0`
- `0x180012a40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800072c0`
- `RPCRT4!NdrClientCall3` at `0x1800072c0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007273`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800072dc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007307`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007273`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800072dc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007307`

## pseudocode

```c
__int64 __fastcall DhcpGetDhcpServicedConnections(_DWORD *a1, __int64 *a2, _DWORD *a3)
{
  unsigned int v5; // r12d
  CLIENT_CALL_RETURN v6; // rbx
  LPWSTR CommandLineW; // rax
  LPWSTR v8; // rax
  __int64 v9; // rax
  __int64 *v11; // [rsp+20h] [rbp-68h]
  __int64 v12; // [rsp+38h] [rbp-50h] BYREF
  size_t pcbLength; // [rsp+40h] [rbp-48h]

  v5 = (unsigned int)a1;
  v12 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_l(1028, 206, WPP_e15037783097355a5233924022d92169_Traceguids, (unsigned int)a1);
  if ( a3 && a2 && !v5 )
  {
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_S(1028, 207, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
    }
    pcbLength = 0;
    v11 = &v12;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Eu, 0).Pointer;
    pcbLength = v6.Simple;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v8 = GetCommandLineW();
      WPP_SF_DS(1028, 208, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v6.Pointer, (__int64)v8);
    }
    if ( !LODWORD(v6.Pointer) )
    {
      v9 = DhcpAlloc(0, a2, a3);
      *a2 = v9;
      if ( v9 )
      {
        a1 = a3;
        *a3 = 0;
        LODWORD(v6.Pointer) = 0;
      }
      else
      {
        LODWORD(v6.Pointer) = 8;
      }
    }
  }
  else
  {
    LODWORD(v6.Pointer) = 87;
  }
  if ( v12 )
    DhcpMidlUserFree(&v12);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    LODWORD(v11) = v6.Pointer;
    WPP_SF_LD(a1, a2, a3, v5, v11);
  }
  return LODWORD(v6.Pointer);
}

```

## disassembly

```asm
0x180007200  mov     rax, rsp
0x180007203  mov     [rax+18h], r8
0x180007207  mov     [rax+10h], rdx
0x18000720b  mov     [rax+8], ecx
0x18000720e  push    rbx
0x18000720f  push    rsi
0x180007210  push    rdi
0x180007211  push    r12
0x180007213  push    r13
0x180007215  push    r14
0x180007217  push    r15
0x180007219  sub     rsp, 50h
0x18000721d  mov     r14, r8
0x180007220  mov     r15, rdx
0x180007223  mov     r12d, ecx
0x180007226  xor     edi, edi
0x180007228  mov     [rax-50h], rdi
0x18000722c  mov     [rax+20h], edi
0x18000722f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007236  jz      short loc_180007251
0x180007238  mov     edx, 0CEh
0x18000723d  mov     ecx, 404h
0x180007242  mov     r9d, r12d
0x180007245  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000724c  call    WPP_SF_l
0x180007251  test    r14, r14
0x180007254  jnz     short loc_180007260
0x180007256  mov     ebx, 57h ; 'W'
0x18000725b  jmp     loc_180007410
0x180007260  test    r15, r15
0x180007263  jz      short loc_180007256
0x180007265  test    r12d, r12d
0x180007268  jnz     short loc_180007256
0x18000726a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007271  jz      short loc_180007293
0x180007273  call    cs:__imp_GetCommandLineW
0x180007279  mov     r9, rax
0x18000727c  mov     edx, 0CFh
0x180007281  mov     ecx, 404h
0x180007286  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000728d  call    WPP_SF_S
0x180007292  nop
0x180007293  mov     [rsp+88h+pcbLength], rdi
0x180007298  lea     rax, [rsp+88h+arg_18]
0x1800072a0  mov     [rsp+88h+var_60], rax
0x1800072a5  lea     rax, [rsp+88h+var_50]
0x1800072aa  mov     [rsp+88h+var_68], rax
0x1800072af  xor     r9d, r9d
0x1800072b2  xor     r8d, r8d; pReturnValue
0x1800072b5  lea     edx, [r9+1Eh]; nProcNum
0x1800072b9  lea     rcx, pProxyInfo; pProxyInfo
0x1800072c0  call    cs:__imp_NdrClientCall3
0x1800072c6  mov     rbx, rax
0x1800072c9  mov     [rsp+88h+pcbLength], rax
0x1800072ce  mov     [rsp+88h+var_54], eax
0x1800072d2  jmp     short loc_1800072FE
0x1800072d4  mov     edi, eax
0x1800072d6  mov     ebx, eax
0x1800072d8  mov     [rsp+88h+var_54], eax
0x1800072dc  call    cs:__imp_GetCommandLineW
0x1800072e2  mov     rdx, rax
0x1800072e5  mov     ecx, ebx
0x1800072e7  call    TraceRpcException
0x1800072ec  xor     edi, edi
0x1800072ee  mov     r15, [rsp+88h+arg_8]
0x1800072f6  mov     r12d, [rsp+88h+arg_0]
0x1800072fe  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007305  jz      short loc_18000732B
0x180007307  call    cs:__imp_GetCommandLineW
0x18000730d  mov     edx, 0D0h
0x180007312  mov     ecx, 404h
0x180007317  mov     [rsp+88h+var_68], rax
0x18000731c  mov     r9d, ebx
0x18000731f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007326  call    WPP_SF_DS
0x18000732b  test    ebx, ebx
0x18000732d  jnz     loc_180007410
0x180007333  mov     ecx, [rsp+88h+arg_18]
0x18000733a  shl     rcx, 3
0x18000733e  call    DhcpAlloc
0x180007343  mov     [r15], rax
0x180007346  test    rax, rax
0x180007349  jnz     short loc_180007355
0x18000734b  mov     ebx, 8
0x180007350  jmp     loc_180007410
0x180007355  mov     esi, edi
0x180007357  cmp     esi, [rsp+88h+arg_18]
0x18000735e  jnb     loc_1800073FD
0x180007364  mov     r13d, esi
0x180007367  mov     rax, [rsp+88h+var_50]
0x18000736c  mov     rcx, [rax+r13*8]; psz
0x180007370  mov     dword ptr [rsp+88h+pcbLength+4], edi
0x180007374  mov     [rsp+88h+pcbLength], rdi
0x180007379  mov     [rsp+88h+var_58], edi
0x18000737d  test    rcx, rcx
0x180007380  jnz     short loc_180007396
0x180007382  mov     eax, 80070057h
0x180007387  mov     dword ptr [rsp+88h+pcbLength+4], 68h ; 'h'
0x18000738f  mov     r14d, [rsp+88h+var_58]
0x180007394  jmp     short loc_1800073B3
0x180007396  lea     r8, [rsp+88h+pcbLength]; pcbLength
0x18000739b  call    StringCbLengthW
0x1800073a0  test    eax, eax
0x1800073a2  jns     short loc_1800073AE
0x1800073a4  mov     dword ptr [rsp+88h+pcbLength+4], 6Ch ; 'l'
0x1800073ac  jmp     short loc_18000738F
0x1800073ae  mov     r14, [rsp+88h+pcbLength]
0x1800073b3  mov     ecx, eax
0x1800073b5  call    WX_WIN32_FROM_HR
0x1800073ba  mov     ebx, eax
0x1800073bc  test    eax, eax
0x1800073be  jnz     short loc_180007410
0x1800073c0  lea     eax, [r14+2]
0x1800073c4  mov     r14d, eax
0x1800073c7  mov     rbx, [r15]
0x1800073ca  mov     ecx, eax
0x1800073cc  call    DhcpAlloc
0x1800073d1  mov     [rbx+r13*8], rax
0x1800073d5  mov     rax, [r15]
0x1800073d8  mov     rcx, [rax+r13*8]; void *
0x1800073dc  test    rcx, rcx
0x1800073df  jz      loc_18000734B
0x1800073e5  mov     r8d, r14d; Size
0x1800073e8  mov     rdx, [rsp+88h+var_50]
0x1800073ed  mov     rdx, [rdx+r13*8]; Src
0x1800073f1  call    memcpy_0
0x1800073f6  inc     esi
0x1800073f8  jmp     loc_180007357
0x1800073fd  mov     eax, [rsp+88h+arg_18]
0x180007404  mov     rcx, [rsp+88h+arg_10]
0x18000740c  mov     [rcx], eax
0x18000740e  mov     ebx, edi
0x180007410  cmp     [rsp+88h+var_50], rdi
0x180007415  jz      short loc_180007445
0x180007417  cmp     [rsp+88h+arg_18], edi
0x18000741e  jbe     short loc_18000743B
0x180007420  mov     ecx, edi
0x180007422  mov     rax, [rsp+88h+var_50]
0x180007427  lea     rcx, [rax+rcx*8]
0x18000742b  call    DhcpMidlUserFree
0x180007430  inc     edi
0x180007432  cmp     edi, [rsp+88h+arg_18]
0x180007439  jb      short loc_180007420
0x18000743b  lea     rcx, [rsp+88h+var_50]
0x180007440  call    DhcpMidlUserFree
0x180007445  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000744c  jz      short loc_18000745A
0x18000744e  mov     dword ptr [rsp+88h+var_68], ebx
0x180007452  mov     r9d, r12d
0x180007455  call    WPP_SF_LD
0x18000745a  mov     eax, ebx
0x18000745c  add     rsp, 50h
0x180007460  pop     r15
0x180007462  pop     r14
0x180007464  pop     r13
0x180007466  pop     r12
0x180007468  pop     rdi
0x180007469  pop     rsi
0x18000746a  pop     rbx
0x18000746b  retn
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
