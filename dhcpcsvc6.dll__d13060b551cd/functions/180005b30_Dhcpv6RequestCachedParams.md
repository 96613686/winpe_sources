# Dhcpv6RequestCachedParams

- ea: `0x180005b30`
- end: `0x180005eab`
- name: `Dhcpv6RequestCachedParams`
- size: `891`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001e30`
- `0x180001e70`
- `0x180001ff0`
- `0x180004c40`
- `0x180005b30`
- `0x180005ec0`
- `0x1800072fc`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180005d98`
- `RPCRT4!NdrClientCall3` at `0x180005d98`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005d4b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005db4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005de0`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005d4b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005db4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005de0`

## pseudocode

```c
__int64 __fastcall Dhcpv6RequestCachedParams(__int64 a1, const WCHAR *a2, __int64 a3, unsigned int *a4)
{
  int v7; // ebx
  unsigned int Pointer; // ebx
  unsigned int v9; // edx
  unsigned int v10; // r9d
  void **v11; // rsi
  __int64 v12; // r11
  unsigned int v13; // ecx
  __int64 v14; // r10
  __int64 v15; // r8
  char *v16; // r12
  __int64 v17; // r15
  __int64 v18; // rsi
  __int64 v19; // r14
  _DWORD *v20; // r9
  unsigned int i; // r8d
  __int64 v22; // rcx
  __int64 v23; // rdx
  LPWSTR CommandLineW; // rax
  int v25; // ecx
  CLIENT_CALL_RETURN v26; // rax
  LPWSTR v27; // rax
  int v28; // ecx
  int v29; // r8d
  unsigned int v30; // r9d
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rdx
  void **v35; // [rsp+48h] [rbp-70h] BYREF
  NET_LUID v36; // [rsp+50h] [rbp-68h] BYREF
  CLIENT_CALL_RETURN v37; // [rsp+58h] [rbp-60h]
  __int64 v38; // [rsp+60h] [rbp-58h]
  __int128 v39; // [rsp+68h] [rbp-50h] BYREF

  v7 = a1;
  v36.Value = 0;
  v39 = 0;
  v35 = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 81, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a2);
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
  {
    if ( v7 )
    {
LABEL_5:
      Pointer = 87;
      goto LABEL_46;
    }
    Pointer = Dhcpv6RequestCachedParamsEx(0, (_DWORD)a2, a3, (_DWORD)a4, (__int64)&v35);
    if ( !Pointer && v35 )
    {
      v9 = *a4;
      if ( *(_DWORD *)v35 <= *a4 )
      {
        Pointer = 0;
        if ( v9 )
        {
          v10 = 0;
          v11 = v35;
          v12 = 0;
          do
          {
            v13 = 0;
            v14 = 32 * v12;
            while ( v13 < *(_DWORD *)v11 )
            {
              v15 = 32LL * v13;
              v16 = (char *)v11[1];
              v17 = *((_QWORD *)a4 + 1);
              if ( *(_DWORD *)(v14 + v17 + 4) == *(_DWORD *)&v16[v15 + 4] )
              {
                *(_QWORD *)(v14 + v17 + 16) = *(_QWORD *)&v16[v15 + 16];
                *(_QWORD *)((char *)v11[1] + v15 + 16) = 0;
                *(_DWORD *)(v14 + v17 + 24) = *(_DWORD *)((char *)v11[1] + v15 + 24);
                *(_DWORD *)((char *)v11[1] + v15 + 24) = 0;
                break;
              }
              ++v13;
            }
            ++v10;
            ++v12;
          }
          while ( v10 < v9 );
        }
      }
      else
      {
        Pointer = 1359;
      }
    }
  }
  else
  {
    if ( !a2 || v7 || a3 && (*(_DWORD *)a3 || !*(_QWORD *)(a3 + 8) || !*(_DWORD *)(a3 + 16)) )
      goto LABEL_5;
    v18 = *a4;
    if ( !(_DWORD)v18 )
      goto LABEL_5;
    v19 = *((_QWORD *)a4 + 1);
    v38 = v19;
    if ( !v19 )
      goto LABEL_5;
    LODWORD(v39) = v18;
    v20 = DhcpAlloc(24 * v18);
    *((_QWORD *)&v39 + 1) = v20;
    if ( v20 )
    {
      for ( i = 0; i < (unsigned int)v18; ++i )
      {
        v22 = 32LL * i;
        if ( *(_DWORD *)(v22 + v19 + 24) || *(_QWORD *)(v22 + v19 + 16) || *(_DWORD *)(v22 + v19) )
          goto LABEL_5;
        v23 = 3LL * i;
        v20[2 * v23 + 1] = *(_DWORD *)(v22 + v19 + 4);
        *(_DWORD *)(*((_QWORD *)&v39 + 1) + 8 * v23 + 8) = *(_DWORD *)(v22 + v19 + 8);
        v20 = (_DWORD *)*((_QWORD *)&v39 + 1);
      }
      Pointer = Dhcpv6AdapterNameToIfId(a2, &v36);
      if ( !Pointer )
      {
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_SS(
            v25,
            Pointer + 82,
            (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
            (_DWORD)a2,
            (__int64)CommandLineW);
        }
        v37.Simple = 0;
        v26.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xCu, 0).Pointer;
        Pointer = (unsigned int)v26.Pointer;
        v37.Pointer = v26.Pointer;
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          v27 = GetCommandLineW();
          WPP_SF_DSS(v28, 83, v29, Pointer, (__int64)a2, (__int64)v27);
        }
        if ( !Pointer )
        {
          v30 = 0;
          v31 = 0;
          do
          {
            v32 = *(_QWORD *)(*((_QWORD *)&v39 + 1) + 24 * v31 + 16);
            if ( v32 )
            {
              v33 = 32 * v31;
              *(_QWORD *)(v33 + v19 + 16) = v32;
              *(_QWORD *)(*((_QWORD *)&v39 + 1) + 24 * v31 + 16) = 0;
              *(_DWORD *)(v33 + v19 + 24) = *(_DWORD *)(*((_QWORD *)&v39 + 1) + 24 * v31 + 12);
              *(_DWORD *)(*((_QWORD *)&v39 + 1) + 24 * v31 + 12) = 0;
            }
            ++v30;
            ++v31;
          }
          while ( v30 < (unsigned int)v18 );
        }
      }
    }
    else
    {
      Pointer = 8;
    }
  }
LABEL_46:
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
    Dhcpv6FreeCachedParamsDataEx(v35);
  else
    DhcpFree((LPVOID *)&v39 + 1);
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_D(1028, 84, WPP_cb48999f8e5838f952918348529d50de_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180005b30  mov     rax, rsp
0x180005b33  mov     [rax+10h], rdx
0x180005b37  push    rbx
0x180005b38  push    rsi
0x180005b39  push    rdi
0x180005b3a  push    r12
0x180005b3c  push    r14
0x180005b3e  push    r15
0x180005b40  sub     rsp, 88h
0x180005b47  mov     r14, r9
0x180005b4a  mov     r12, r8
0x180005b4d  mov     r15, rdx
0x180005b50  mov     ebx, ecx
0x180005b52  xor     edi, edi
0x180005b54  mov     [rax-68h], rdi
0x180005b58  xorps   xmm0, xmm0
0x180005b5b  movups  xmmword ptr [rax-50h], xmm0
0x180005b5f  mov     [rax-70h], rdi
0x180005b63  test    byte ptr cs:xmmword_18000F160, 10h
0x180005b6a  jz      short loc_180005B7E
0x180005b6c  lea     edx, [rdi+51h]
0x180005b6f  mov     r9, r15
0x180005b72  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005b79  call    WPP_SF_S
0x180005b7e  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, edi
0x180005b84  jz      loc_180005C56
0x180005b8a  test    ebx, ebx
0x180005b8c  jz      short loc_180005B98
0x180005b8e  mov     ebx, 57h ; 'W'
0x180005b93  jmp     loc_180005E58
0x180005b98  lea     rax, [rsp+0B8h+var_70]
0x180005b9d  mov     [rsp+0B8h+var_98], rax
0x180005ba2  mov     r9, r14
0x180005ba5  mov     r8, r12
0x180005ba8  mov     rdx, r15
0x180005bab  xor     ecx, ecx
0x180005bad  call    Dhcpv6RequestCachedParamsEx
0x180005bb2  mov     ebx, eax
0x180005bb4  test    eax, eax
0x180005bb6  jnz     loc_180005E58
0x180005bbc  mov     rax, [rsp+0B8h+var_70]
0x180005bc1  test    rax, rax
0x180005bc4  jz      loc_180005E58
0x180005bca  mov     edx, [r14]
0x180005bcd  cmp     [rax], edx
0x180005bcf  jbe     short loc_180005BDB
0x180005bd1  mov     ebx, 54Fh
0x180005bd6  jmp     loc_180005E58
0x180005bdb  mov     ebx, edi
0x180005bdd  test    edx, edx
0x180005bdf  jz      loc_180005E58
0x180005be5  mov     r9d, edi
0x180005be8  mov     rsi, [rsp+0B8h+var_70]
0x180005bed  mov     r11, rdi
0x180005bf0  mov     ecx, edi
0x180005bf2  mov     r10, r11
0x180005bf5  shl     r10, 5
0x180005bf9  cmp     ecx, [rsi]
0x180005bfb  jnb     short loc_180005C46
0x180005bfd  mov     r8d, ecx
0x180005c00  shl     r8, 5
0x180005c04  mov     r12, [rsi+8]
0x180005c08  mov     r15, [r14+8]
0x180005c0c  mov     eax, [r8+r12+4]
0x180005c11  cmp     [r10+r15+4], eax
0x180005c16  jz      short loc_180005C1C
0x180005c18  inc     ecx
0x180005c1a  jmp     short loc_180005BF9
0x180005c1c  mov     rax, [r8+r12+10h]
0x180005c21  mov     [r10+r15+10h], rax
0x180005c26  mov     rax, [rsi+8]
0x180005c2a  mov     [r8+rax+10h], rdi
0x180005c2f  mov     rax, [rsi+8]
0x180005c33  mov     ecx, [r8+rax+18h]
0x180005c38  mov     [r10+r15+18h], ecx
0x180005c3d  mov     rax, [rsi+8]
0x180005c41  mov     [r8+rax+18h], edi
0x180005c46  inc     r9d
0x180005c49  inc     r11
0x180005c4c  cmp     r9d, edx
0x180005c4f  jb      short loc_180005BF0
0x180005c51  jmp     loc_180005E58
0x180005c56  test    r15, r15
0x180005c59  jz      loc_180005B8E
0x180005c5f  test    ebx, ebx
0x180005c61  jnz     loc_180005B8E
0x180005c67  test    r12, r12
0x180005c6a  jz      short loc_180005C8C
0x180005c6c  cmp     [r12], edi
0x180005c70  jnz     loc_180005B8E
0x180005c76  cmp     [r12+8], rdi
0x180005c7b  jz      loc_180005B8E
0x180005c81  cmp     [r12+10h], edi
0x180005c86  jz      loc_180005B8E
0x180005c8c  mov     esi, [r14]
0x180005c8f  mov     [rsp+0B8h+var_74], esi
0x180005c93  test    esi, esi
0x180005c95  jz      loc_180005B8E
0x180005c9b  mov     r14, [r14+8]
0x180005c9f  mov     [rsp+0B8h+var_58], r14
0x180005ca4  test    r14, r14
0x180005ca7  jz      loc_180005B8E
0x180005cad  mov     [rsp+0B8h+var_50], esi
0x180005cb1  lea     rcx, [rsi+rsi*2]
0x180005cb5  shl     rcx, 3
0x180005cb9  call    DhcpAlloc
0x180005cbe  mov     r9, rax
0x180005cc1  mov     [rsp+0B8h+var_48], rax
0x180005cc6  test    rax, rax
0x180005cc9  jnz     short loc_180005CD3
0x180005ccb  lea     ebx, [rax+8]
0x180005cce  jmp     loc_180005E58
0x180005cd3  mov     r8d, edi
0x180005cd6  cmp     r8d, esi
0x180005cd9  jnb     short loc_180005D2B
0x180005cdb  mov     eax, r8d
0x180005cde  mov     ecx, r8d
0x180005ce1  shl     rcx, 5
0x180005ce5  cmp     [rcx+r14+18h], edi
0x180005cea  jnz     loc_180005B8E
0x180005cf0  cmp     [rcx+r14+10h], rdi
0x180005cf5  jnz     loc_180005B8E
0x180005cfb  cmp     [rcx+r14], edi
0x180005cff  jnz     loc_180005B8E
0x180005d05  lea     rdx, [rax+rax*2]
0x180005d09  mov     eax, [rcx+r14+4]
0x180005d0e  mov     [r9+rdx*8+4], eax
0x180005d13  mov     ecx, [rcx+r14+8]
0x180005d18  mov     rax, [rsp+0B8h+var_48]
0x180005d1d  mov     [rax+rdx*8+8], ecx
0x180005d21  inc     r8d
0x180005d24  mov     r9, [rsp+0B8h+var_48]
0x180005d29  jmp     short loc_180005CD6
0x180005d2b  lea     rdx, [rsp+0B8h+var_68]
0x180005d30  mov     rcx, r15
0x180005d33  call    Dhcpv6AdapterNameToIfId
0x180005d38  mov     ebx, eax
0x180005d3a  test    eax, eax
0x180005d3c  jnz     loc_180005E58
0x180005d42  test    byte ptr cs:xmmword_18000F160, 10h
0x180005d49  jz      short loc_180005D69
0x180005d4b  call    cs:__imp_GetCommandLineW
0x180005d51  lea     edx, [rbx+52h]
0x180005d54  mov     [rsp+0B8h+var_98], rax
0x180005d59  mov     r9, r15
0x180005d5c  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005d63  call    WPP_SF_SS
0x180005d68  nop
0x180005d69  mov     [rsp+0B8h+var_60], rdi
0x180005d6e  lea     rax, [rsp+0B8h+var_50]
0x180005d73  mov     [rsp+0B8h+var_88], rax
0x180005d78  mov     [rsp+0B8h+var_90], r12
0x180005d7d  lea     rax, [rsp+0B8h+var_68]
0x180005d82  mov     [rsp+0B8h+var_98], rax
0x180005d87  xor     r9d, r9d
0x180005d8a  xor     r8d, r8d; pReturnValue
0x180005d8d  lea     edx, [r9+0Ch]; nProcNum
0x180005d91  lea     rcx, pProxyInfo; pProxyInfo
0x180005d98  call    cs:__imp_NdrClientCall3
0x180005d9e  mov     rbx, rax
0x180005da1  mov     [rsp+0B8h+var_60], rax
0x180005da6  mov     [rsp+0B8h+var_78], eax
0x180005daa  jmp     short loc_180005DD7
0x180005dac  mov     edi, eax
0x180005dae  mov     ebx, eax
0x180005db0  mov     [rsp+0B8h+var_78], eax
0x180005db4  call    cs:__imp_GetCommandLineW
0x180005dba  mov     rdx, rax
0x180005dbd  mov     ecx, ebx
0x180005dbf  call    TraceRpcException
0x180005dc4  xor     edi, edi
0x180005dc6  mov     r15, [rsp+0B8h+arg_8]
0x180005dce  mov     esi, [rsp+0B8h+var_74]
0x180005dd2  mov     r14, [rsp+0B8h+var_58]
0x180005dd7  test    byte ptr cs:xmmword_18000F160, 10h
0x180005dde  jz      short loc_180005DFD
0x180005de0  call    cs:__imp_GetCommandLineW
0x180005de6  mov     edx, 53h ; 'S'
0x180005deb  mov     [rsp+0B8h+var_90], rax
0x180005df0  mov     [rsp+0B8h+var_98], r15
0x180005df5  mov     r9d, ebx
0x180005df8  call    WPP_SF_DSS
0x180005dfd  test    ebx, ebx
0x180005dff  jnz     short loc_180005E58
0x180005e01  mov     r9d, edi
0x180005e04  test    esi, esi
0x180005e06  jz      short loc_180005E58
0x180005e08  mov     r8, rdi
0x180005e0b  lea     r10, [r8+r8*2]
0x180005e0f  mov     rax, [rsp+0B8h+var_48]
0x180005e14  mov     rcx, [rax+r10*8+10h]
0x180005e19  test    rcx, rcx
0x180005e1c  jz      short loc_180005E4D
0x180005e1e  mov     rdx, r8
0x180005e21  shl     rdx, 5
0x180005e25  mov     [rdx+r14+10h], rcx
0x180005e2a  mov     rax, [rsp+0B8h+var_48]
0x180005e2f  mov     [rax+r10*8+10h], rdi
0x180005e34  mov     rax, [rsp+0B8h+var_48]
0x180005e39  mov     ecx, [rax+r10*8+0Ch]
0x180005e3e  mov     [rdx+r14+18h], ecx
0x180005e43  mov     rax, [rsp+0B8h+var_48]
0x180005e48  mov     [rax+r10*8+0Ch], edi
0x180005e4d  inc     r9d
0x180005e50  inc     r8
0x180005e53  cmp     r9d, esi
0x180005e56  jb      short loc_180005E0B
0x180005e58  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, edi
0x180005e5e  jz      short loc_180005E6C
0x180005e60  mov     rcx, [rsp+0B8h+var_70]
0x180005e65  call    Dhcpv6FreeCachedParamsDataEx
0x180005e6a  jmp     short loc_180005E76
0x180005e6c  lea     rcx, [rsp+0B8h+var_48]
0x180005e71  call    DhcpFree
0x180005e76  test    byte ptr cs:xmmword_18000F160, 10h
0x180005e7d  jz      short loc_180005E98
0x180005e7f  mov     edx, 54h ; 'T'
0x180005e84  mov     ecx, 404h
0x180005e89  mov     r9d, ebx
0x180005e8c  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005e93  call    WPP_SF_D
0x180005e98  mov     eax, ebx
0x180005e9a  add     rsp, 88h
0x180005ea1  pop     r15
0x180005ea3  pop     r14
0x180005ea5  pop     r12
0x180005ea7  pop     rdi
0x180005ea8  pop     rsi
0x180005ea9  pop     rbx
0x180005eaa  retn
0x180007a72  push    rbp
0x180007a74  sub     rsp, 40h
0x180007a78  mov     rbp, rdx
0x180007a7b  mov     rcx, [rcx]
0x180007a7e  mov     ecx, [rcx]; ExceptionCode
0x180007a80  call    cs:__imp_I_RpcExceptionFilter
0x180007a86  nop
0x180007a87  add     rsp, 40h
0x180007a8b  pop     rbp
0x180007a8c  retn
```
