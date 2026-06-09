# McastEnumerateScopes

- ea: `0x18000c540`
- end: `0x18000c7c2`
- name: `McastEnumerateScopes`
- size: `642`
- prototype: `DWORD __stdcall(IP_ADDR_FAMILY AddrFamily, BOOL ReQuery, PMCAST_SCOPE_ENTRY pScopeList, PDWORD pScopeLen, PDWORD pScopeCount)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002c50`
- `0x18000c540`
- `0x18000d5c8`
- `0x18000f4ec`
- `0x180010154`
- `0x1800111e4`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c66c`
- `RPCRT4!NdrClientCall3` at `0x18000c66c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c615`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c688`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c6bf`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c615`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c688`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c6bf`

## pseudocode

```c
DWORD __stdcall McastEnumerateScopes(
        IP_ADDR_FAMILY AddrFamily,
        BOOL ReQuery,
        PMCAST_SCOPE_ENTRY pScopeList,
        PDWORD pScopeLen,
        PDWORD pScopeCount)
{
  int v8; // esi
  DWORD Pointer; // ebx
  __int64 v10; // rdx
  bool v11; // zf
  LPWSTR CommandLineW; // rax
  LPWSTR v13; // rax
  unsigned int v14; // eax
  DWORD i; // ecx
  __int64 v16; // rdx
  __int128 v18; // [rsp+60h] [rbp-38h] BYREF

  v18 = 0;
  v8 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Dlqqq(AddrFamily, ReQuery, pScopeList, AddrFamily, ReQuery, pScopeList, pScopeLen, pScopeCount);
  if ( pScopeCount )
    *pScopeCount = 0;
  if ( !pScopeLen )
  {
    Pointer = 87;
    if ( (xmmword_18001E1E0 & 2) != 0 )
    {
      v10 = 266;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  if ( pScopeList && !pScopeCount )
  {
    Pointer = 87;
    if ( (xmmword_18001E1E0 & 2) != 0 )
    {
      v10 = 267;
LABEL_31:
      WPP_SF_d(1025, v10, WPP_e15037783097355a5233924022d92169_Traceguids, 87);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( ReQuery )
  {
    v11 = pScopeList == 0;
    goto LABEL_15;
  }
  v11 = pScopeList == 0;
  if ( pScopeList )
  {
LABEL_15:
    LOBYTE(v8) = !v11;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_S(1028, 269, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
    }
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x27u, 0).Pointer;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v13 = GetCommandLineW();
      WPP_SF_DS(1028, 270, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v13);
    }
    if ( !Pointer )
    {
      if ( pScopeList )
      {
        if ( DWORD1(v18) )
        {
          if ( *((_QWORD *)&v18 + 1) )
          {
            v14 = memcpy_s(pScopeList, *pScopeLen, *((const void *const *)&v18 + 1), DWORD1(v18));
            Pointer = Win32FromErrno(v14);
            if ( !Pointer )
            {
              for ( i = 0; i < *pScopeCount; ++i )
              {
                v16 = i;
                if ( pScopeList[v16].ScopeDesc.Length )
                  pScopeList[v16].ScopeDesc.Buffer = (PWSTR)((char *)pScopeList[v16].ScopeDesc.Buffer
                                                           + (unsigned __int64)pScopeList);
              }
            }
          }
        }
      }
    }
    goto LABEL_32;
  }
  Pointer = 87;
  if ( (xmmword_18001E1E0 & 2) != 0 )
  {
    v10 = 268;
    goto LABEL_31;
  }
LABEL_32:
  if ( v8 && DWORD1(v18) && *((_QWORD *)&v18 + 1) )
    DhcpMidlUserFree((char *)&v18 + 8);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 271, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000c540  mov     rax, rsp
0x18000c543  mov     [rax+8], rbx
0x18000c547  mov     [rax+10h], rsi
0x18000c54b  mov     [rax+20h], r9
0x18000c54f  mov     [rax+18h], r8
0x18000c553  push    rdi
0x18000c554  push    r12
0x18000c556  push    r13
0x18000c558  push    r14
0x18000c55a  push    r15
0x18000c55c  sub     rsp, 70h
0x18000c560  mov     r12, r9
0x18000c563  mov     r14, r8
0x18000c566  mov     ebx, edx
0x18000c568  movzx   r13d, cx
0x18000c56c  xorps   xmm0, xmm0
0x18000c56f  movups  xmmword ptr [rax-38h], xmm0
0x18000c573  xor     edi, edi
0x18000c575  mov     esi, edi
0x18000c577  mov     r15, [rsp+98h+pScopeCount]
0x18000c57f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c586  jz      short loc_18000C59F
0x18000c588  mov     r9d, r13d
0x18000c58b  mov     [rax-60h], r15
0x18000c58f  mov     [rax-68h], r12
0x18000c593  mov     [rax-70h], r8
0x18000c597  mov     [rax-78h], edx
0x18000c59a  call    WPP_SF_Dlqqq
0x18000c59f  test    r15, r15
0x18000c5a2  jz      short loc_18000C5A9
0x18000c5a4  xor     eax, eax
0x18000c5a6  mov     [r15], eax
0x18000c5a9  test    r12, r12
0x18000c5ac  jz      loc_18000C73D
0x18000c5b2  test    r14, r14
0x18000c5b5  jz      short loc_18000C5DA
0x18000c5b7  test    r15, r15
0x18000c5ba  jnz     short loc_18000C5DA
0x18000c5bc  lea     r9d, [r15+57h]
0x18000c5c0  mov     ebx, r9d
0x18000c5c3  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000c5ca  jz      loc_18000C765
0x18000c5d0  mov     edx, 10Bh
0x18000c5d5  jmp     loc_18000C754
0x18000c5da  test    ebx, ebx
0x18000c5dc  jnz     short loc_18000C601
0x18000c5de  test    r14, r14
0x18000c5e1  jnz     short loc_18000C604
0x18000c5e3  lea     r9d, [rbx+57h]
0x18000c5e7  mov     ebx, r9d
0x18000c5ea  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000c5f1  jz      loc_18000C765
0x18000c5f7  mov     edx, 10Ch
0x18000c5fc  jmp     loc_18000C754
0x18000c601  test    r14, r14
0x18000c604  setnz   sil
0x18000c608  mov     [rsp+98h+var_44], esi
0x18000c60c  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c613  jz      short loc_18000C635
0x18000c615  call    cs:__imp_GetCommandLineW
0x18000c61b  mov     r9, rax
0x18000c61e  mov     edx, 10Dh
0x18000c623  mov     ecx, 404h
0x18000c628  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c62f  call    WPP_SF_S
0x18000c634  nop
0x18000c635  mov     [rsp+98h+var_40], rdi
0x18000c63a  mov     [rsp+98h+var_50], r15
0x18000c63f  mov     [rsp+98h+var_58], r12
0x18000c644  lea     rcx, [rsp+98h+var_38]
0x18000c649  mov     [rsp+98h+var_60], rcx
0x18000c64e  mov     [rsp+98h+var_68], esi
0x18000c652  mov     [rsp+98h+var_70], ebx
0x18000c656  mov     dword ptr [rsp+98h+var_78], r13d
0x18000c65b  xor     r9d, r9d
0x18000c65e  xor     r8d, r8d; pReturnValue
0x18000c661  lea     edx, [r9+27h]; nProcNum
0x18000c665  lea     rcx, pProxyInfo; pProxyInfo
0x18000c66c  call    cs:__imp_NdrClientCall3
0x18000c672  mov     rbx, rax
0x18000c675  mov     [rsp+98h+var_40], rax
0x18000c67a  mov     [rsp+98h+var_48], eax
0x18000c67e  jmp     short loc_18000C6B6
0x18000c680  mov     edi, eax
0x18000c682  mov     ebx, eax
0x18000c684  mov     [rsp+98h+var_48], eax
0x18000c688  call    cs:__imp_GetCommandLineW
0x18000c68e  mov     rdx, rax
0x18000c691  mov     ecx, ebx
0x18000c693  call    TraceRpcException
0x18000c698  xor     edi, edi
0x18000c69a  mov     r15, [rsp+98h+pScopeCount]
0x18000c6a2  mov     r12, [rsp+98h+arg_18]
0x18000c6aa  mov     r14, [rsp+98h+arg_10]
0x18000c6b2  mov     esi, [rsp+98h+var_44]
0x18000c6b6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c6bd  jz      short loc_18000C6E3
0x18000c6bf  call    cs:__imp_GetCommandLineW
0x18000c6c5  mov     edx, 10Eh
0x18000c6ca  mov     ecx, 404h
0x18000c6cf  mov     [rsp+98h+var_78], rax
0x18000c6d4  mov     r9d, ebx
0x18000c6d7  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c6de  call    WPP_SF_DS
0x18000c6e3  test    ebx, ebx
0x18000c6e5  jnz     short loc_18000C765
0x18000c6e7  test    r14, r14
0x18000c6ea  jz      short loc_18000C765
0x18000c6ec  cmp     dword ptr [rsp+98h+SourceSize], edi
0x18000c6f0  jz      short loc_18000C765
0x18000c6f2  mov     r8, [rsp+98h+SourceSize+4]; Source
0x18000c6f7  test    r8, r8
0x18000c6fa  jz      short loc_18000C765
0x18000c6fc  mov     r9d, dword ptr [rsp+98h+SourceSize]; SourceSize
0x18000c701  mov     edx, [r12]; DestinationSize
0x18000c705  mov     rcx, r14; Destination
0x18000c708  call    memcpy_s
0x18000c70d  mov     ecx, eax
0x18000c70f  call    Win32FromErrno
0x18000c714  mov     ebx, eax
0x18000c716  test    eax, eax
0x18000c718  jnz     short loc_18000C765
0x18000c71a  mov     ecx, edi
0x18000c71c  cmp     [r15], edi
0x18000c71f  jbe     short loc_18000C765
0x18000c721  mov     eax, ecx
0x18000c723  imul    rdx, rax, 58h ; 'X'
0x18000c727  cmp     [rdx+r14+48h], di
0x18000c72d  jz      short loc_18000C734
0x18000c72f  add     [rdx+r14+50h], r14
0x18000c734  inc     ecx
0x18000c736  cmp     ecx, [r15]
0x18000c739  jb      short loc_18000C721
0x18000c73b  jmp     short loc_18000C765
0x18000c73d  mov     r9d, 57h ; 'W'
0x18000c743  mov     ebx, r9d
0x18000c746  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000c74d  jz      short loc_18000C765
0x18000c74f  mov     edx, 10Ah
0x18000c754  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c75b  mov     ecx, 401h
0x18000c760  call    WPP_SF_d
0x18000c765  test    esi, esi
0x18000c767  jz      short loc_18000C784
0x18000c769  cmp     dword ptr [rsp+98h+SourceSize], edi
0x18000c76d  jbe     short loc_18000C784
0x18000c76f  cmp     [rsp+98h+SourceSize+4], rdi
0x18000c774  jz      short loc_18000C784
0x18000c776  lea     rcx, [rsp+98h+SourceSize+4]
0x18000c77b  call    DhcpMidlUserFree
0x18000c780  mov     dword ptr [rsp+98h+SourceSize], edi
0x18000c784  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c78b  jz      short loc_18000C7A6
0x18000c78d  mov     edx, 10Fh
0x18000c792  mov     ecx, 404h
0x18000c797  mov     r9d, ebx
0x18000c79a  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c7a1  call    WPP_SF_d
0x18000c7a6  mov     eax, ebx
0x18000c7a8  lea     r11, [rsp+98h+var_28]
0x18000c7ad  mov     rbx, [r11+30h]
0x18000c7b1  mov     rsi, [r11+38h]
0x18000c7b5  mov     rsp, r11
0x18000c7b8  pop     r15
0x18000c7ba  pop     r14
0x18000c7bc  pop     r13
0x18000c7be  pop     r12
0x18000c7c0  pop     rdi
0x18000c7c1  retn
0x180010cec  push    rbp
0x180010cee  sub     rsp, 50h
0x180010cf2  mov     rbp, rdx
0x180010cf5  mov     rcx, [rcx]
0x180010cf8  mov     ecx, [rcx]; ExceptionCode
0x180010cfa  call    cs:__imp_I_RpcExceptionFilter
0x180010d00  nop
0x180010d01  add     rsp, 50h
0x180010d05  pop     rbp
0x180010d06  retn
```
