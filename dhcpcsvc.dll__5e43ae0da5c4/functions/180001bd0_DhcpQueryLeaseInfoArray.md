# DhcpQueryLeaseInfoArray

- ea: `0x180001bd0`
- end: `0x180001f86`
- name: `DhcpQueryLeaseInfoArray`
- size: `950`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001bd0`
- `0x180001f90`
- `0x180001fe0`
- `0x180002160`
- `0x180002620`
- `0x180002810`
- `0x180002880`
- `0x180005162`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012a40`
- `0x180012df0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001c9b`
- `RPCRT4!NdrClientCall3` at `0x180001c9b`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010bce`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010bce`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001cba`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001f39`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001f5d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001cba`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001f39`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001f5d`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x180001e33`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x180001e33`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapAlloc` at `0x180001d4e`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapAlloc` at `0x180001d97`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapAlloc` at `0x180001d4e`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapAlloc` at `0x180001d97`

## pseudocode

```c
__int64 __fastcall DhcpQueryLeaseInfoArray(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned int v4; // edi
  unsigned int v6; // r14d
  char *v7; // rsi
  char *v8; // rax
  unsigned int i; // r13d
  CLIENT_CALL_RETURN v10; // rdx
  CLIENT_CALL_RETURN v11; // rbx
  CLIENT_CALL_RETURN v12; // r8
  LPVOID v14; // rax
  LPVOID v15; // rax
  __int64 v16; // r9
  __int64 v17; // r15
  __int64 v18; // rcx
  unsigned int j; // r10d
  __int64 v20; // rdx
  __int64 v21; // rax
  LPWSTR CommandLineW; // rax
  LPWSTR v23; // rax
  char *v24; // [rsp+38h] [rbp-60h]
  __int128 v25; // [rsp+48h] [rbp-50h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+8h] BYREF
  int v27; // [rsp+A8h] [rbp+10h]
  __int64 *v28; // [rsp+B0h] [rbp+18h]
  CLIENT_CALL_RETURN v29; // [rsp+B8h] [rbp+20h]

  v28 = a3;
  v27 = a2;
  v4 = a2;
  v25 = 0;
  v6 = 0;
  v7 = 0;
  v26 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_q(a1, 139, a3, a1);
  *a3 = 0;
  if ( a1 )
  {
    if ( v4 )
    {
      v8 = (char *)DhcpAlloc(24 * v4, a2, a3);
      v7 = v8;
      if ( v8 )
      {
        v24 = v8;
        memset_0(v8, 0, 24 * v4);
        for ( i = 0; i < v4; ++i )
        {
          v29.Simple = (LONG_PTR)&v7[24 * i];
          *(_BYTE *)v29.Pointer = 0;
          v14 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, 8u);
          *(_QWORD *)(v29.Simple + 8) = v14;
          if ( !v14 )
            goto LABEL_31;
          LODWORD(v11.Pointer) = DhcpAdapterNameToIfId(*(_QWORD *)(a1 + 8LL * i), v14);
          if ( LODWORD(v11.Pointer) )
            goto LABEL_13;
          v15 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, 0x78u);
          *(_QWORD *)(v29.Simple + 16) = v15;
          if ( !v15 )
            goto LABEL_31;
        }
        LODWORD(v25) = v4;
        *((_QWORD *)&v25 + 1) = v7;
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_S(1028, 140, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
        }
        v29.Simple = 0;
        v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x12u, 0, 0, &v25).Pointer;
        v29.Pointer = v11.Pointer;
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          v23 = GetCommandLineW();
          WPP_SF_DS(1028, 141, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v11.Pointer, (__int64)v23);
        }
        if ( !LODWORD(v11.Pointer) )
        {
          v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))DhcpAlloc)(
                  120LL * v4,
                  (CLIENT_CALL_RETURN)v10.Simple,
                  (CLIENT_CALL_RETURN)v12.Simple);
          v26 = v16;
          if ( v16 )
          {
            LODWORD(v11.Pointer) = 0;
            for ( j = 0; j < v4; ++j )
            {
              v20 = *(_QWORD *)&v24[24 * j + 16];
              v21 = 120LL * j;
              *(_OWORD *)(v21 + v16) = *(_OWORD *)v20;
              *(_OWORD *)(v21 + v16 + 16) = *(_OWORD *)(v20 + 16);
              *(_OWORD *)(v21 + v16 + 32) = *(_OWORD *)(v20 + 32);
              *(_OWORD *)(v21 + v16 + 48) = *(_OWORD *)(v20 + 48);
              *(_OWORD *)(v21 + v16 + 64) = *(_OWORD *)(v20 + 64);
              *(_OWORD *)(v21 + v16 + 80) = *(_OWORD *)(v20 + 80);
              *(_OWORD *)(v21 + v16 + 96) = *(_OWORD *)(v20 + 96);
              *(_QWORD *)(v21 + v16 + 112) = *(_QWORD *)(v20 + 112);
              *(_OWORD *)(v20 + 32) = 0;
              *(_OWORD *)(v20 + 48) = 0;
              *(_QWORD *)(v20 + 64) = 0;
              *(_OWORD *)(v20 + 72) = 0;
              *(_OWORD *)(v20 + 88) = 0;
              *(_OWORD *)(v20 + 104) = 0;
            }
            *a3 = v16;
            v26 = 0;
          }
          else
          {
            LODWORD(v11.Pointer) = 8;
          }
        }
      }
      else
      {
LABEL_31:
        LODWORD(v11.Pointer) = 8;
      }
    }
    else
    {
      LODWORD(v11.Pointer) = 87;
    }
  }
  else
  {
    LODWORD(v11.Pointer) = 87;
  }
LABEL_13:
  DhcpFreeLeaseInfoArray(v4, &v26);
  if ( v7 )
  {
    if ( v4 )
    {
      do
      {
        v17 = 24LL * v6;
        v18 = *(_QWORD *)&v7[v17 + 16];
        if ( v18 )
        {
          CleanupNetBTParam(v18 + 32);
          CleanupDNSParam(*(_QWORD *)&v7[v17 + 16] + 72LL);
          DhcpFree(&v7[v17 + 16]);
        }
        DhcpFree(&v7[v17 + 8]);
        ++v6;
      }
      while ( v6 < v4 );
    }
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v7);
  }
  return LODWORD(v11.Pointer);
}

```

## disassembly

```asm
0x180001bd0  mov     rax, rsp
0x180001bd3  mov     [rax+18h], r8
0x180001bd7  mov     [rax+10h], edx
0x180001bda  push    rbx
0x180001bdb  push    rsi
0x180001bdc  push    rdi
0x180001bdd  push    r12
0x180001bdf  push    r13
0x180001be1  push    r14
0x180001be3  push    r15
0x180001be5  sub     rsp, 60h
0x180001be9  mov     r15, r8
0x180001bec  mov     edi, edx
0x180001bee  mov     r12, rcx
0x180001bf1  xorps   xmm0, xmm0
0x180001bf4  movups  xmmword ptr [rax-50h], xmm0
0x180001bf8  xor     r14d, r14d
0x180001bfb  mov     esi, r14d
0x180001bfe  mov     [rax+8], r14
0x180001c02  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180001c09  jnz     loc_180001F13
0x180001c0f  mov     [r15], r14
0x180001c12  test    r12, r12
0x180001c15  jz      loc_180001F09
0x180001c1b  test    edi, edi
0x180001c1d  jz      loc_180001F25
0x180001c23  lea     eax, [rdi+rdi*2]
0x180001c26  shl     eax, 3
0x180001c29  mov     ebx, eax
0x180001c2b  mov     ecx, eax
0x180001c2d  call    DhcpAlloc
0x180001c32  mov     rsi, rax
0x180001c35  mov     [rsp+98h+var_58], rax
0x180001c3a  test    rax, rax
0x180001c3d  jz      loc_180001F2F
0x180001c43  mov     [rsp+98h+var_60], rax
0x180001c48  mov     r8d, ebx; Size
0x180001c4b  xor     edx, edx; Val
0x180001c4d  mov     rcx, rax; void *
0x180001c50  call    memset_0
0x180001c55  mov     r13d, r14d
0x180001c58  cmp     r13d, edi
0x180001c5b  jb      loc_180001D20
0x180001c61  mov     [rsp+98h+var_50], edi
0x180001c65  mov     [rsp+98h+var_48], rsi
0x180001c6a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180001c71  jnz     loc_180001F39
0x180001c77  mov     [rsp+98h+arg_18], r14
0x180001c7f  lea     rax, [rsp+98h+var_50]
0x180001c84  mov     [rsp+98h+var_78], rax
0x180001c89  xor     r9d, r9d
0x180001c8c  xor     r8d, r8d; pReturnValue
0x180001c8f  mov     edx, 12h; nProcNum
0x180001c94  lea     rcx, pProxyInfo; pProxyInfo
0x180001c9b  call    cs:__imp_NdrClientCall3
0x180001ca1  mov     rbx, rax
0x180001ca4  mov     [rsp+98h+arg_18], rax
0x180001cac  mov     [rsp+98h+var_68], eax
0x180001cb0  jmp     short loc_180001CE1
0x180001cb2  mov     edi, eax
0x180001cb4  mov     ebx, eax
0x180001cb6  mov     [rsp+98h+var_68], eax
0x180001cba  call    cs:__imp_GetCommandLineW
0x180001cc0  mov     rdx, rax
0x180001cc3  mov     ecx, ebx
0x180001cc5  call    TraceRpcException
0x180001cca  xor     r14d, r14d
0x180001ccd  mov     r15, [rsp+98h+arg_10]
0x180001cd5  mov     edi, [rsp+98h+arg_8]
0x180001cdc  mov     rsi, [rsp+98h+var_58]
0x180001ce1  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180001ce8  jnz     loc_180001F5D
0x180001cee  test    ebx, ebx
0x180001cf0  jz      loc_180001DBA
0x180001cf6  lea     rdx, [rsp+98h+arg_0]
0x180001cfe  mov     ecx, edi
0x180001d00  call    DhcpFreeLeaseInfoArray
0x180001d05  test    rsi, rsi
0x180001d08  jnz     loc_180001DE3
0x180001d0e  mov     eax, ebx
0x180001d10  add     rsp, 60h
0x180001d14  pop     r15
0x180001d16  pop     r14
0x180001d18  pop     r13
0x180001d1a  pop     r12
0x180001d1c  pop     rdi
0x180001d1d  pop     rsi
0x180001d1e  pop     rbx
0x180001d1f  retn
0x180001d20  mov     ebx, r13d
0x180001d23  lea     rax, [rbx+rbx*2]
0x180001d27  mov     rcx, rsi
0x180001d2a  lea     rax, [rcx+rax*8]
0x180001d2e  mov     [rsp+98h+arg_18], rax
0x180001d36  mov     [rax], r14b
0x180001d39  mov     rcx, gs:60h
0x180001d42  mov     edx, 8; dwFlags
0x180001d47  mov     r8d, edx; dwBytes
0x180001d4a  mov     rcx, [rcx+30h]; hHeap
0x180001d4e  call    cs:__imp_HeapAlloc
0x180001d54  mov     rcx, [rsp+98h+arg_18]
0x180001d5c  mov     [rcx+8], rax
0x180001d60  test    rax, rax
0x180001d63  jz      loc_180001F2F
0x180001d69  mov     rdx, rax
0x180001d6c  mov     rcx, [r12+rbx*8]
0x180001d70  call    DhcpAdapterNameToIfId
0x180001d75  mov     ebx, eax
0x180001d77  test    eax, eax
0x180001d79  jnz     loc_180001CF6
0x180001d7f  mov     rcx, gs:60h
0x180001d88  mov     edx, 8; dwFlags
0x180001d8d  mov     r8d, 78h ; 'x'; dwBytes
0x180001d93  mov     rcx, [rcx+30h]; hHeap
0x180001d97  call    cs:__imp_HeapAlloc
0x180001d9d  mov     rcx, [rsp+98h+arg_18]
0x180001da5  mov     [rcx+10h], rax
0x180001da9  test    rax, rax
0x180001dac  jz      loc_180001F2F
0x180001db2  inc     r13d
0x180001db5  jmp     loc_180001C58
0x180001dba  mov     eax, edi
0x180001dbc  imul    rcx, rax, 78h ; 'x'
0x180001dc0  call    DhcpAlloc
0x180001dc5  mov     r9, rax
0x180001dc8  mov     [rsp+98h+arg_0], rax
0x180001dd0  test    rax, rax
0x180001dd3  jnz     loc_180001E61
0x180001dd9  mov     ebx, 8
0x180001dde  jmp     loc_180001CF6
0x180001de3  test    edi, edi
0x180001de5  jz      short loc_180001E21
0x180001de7  nop     word ptr [rax+rax+00000000h]
0x180001df0  mov     eax, r14d
0x180001df3  lea     rcx, [rax+rax*2]
0x180001df7  lea     r15, ds:0[rcx*8]
0x180001dff  lea     r12, [r15+rsi]
0x180001e03  mov     rcx, [r12+10h]
0x180001e08  test    rcx, rcx
0x180001e0b  jnz     short loc_180001E3E
0x180001e0d  lea     rcx, [rsi+8]
0x180001e11  add     rcx, r15
0x180001e14  call    DhcpFree
0x180001e19  inc     r14d
0x180001e1c  cmp     r14d, edi
0x180001e1f  jb      short loc_180001DF0
0x180001e21  mov     rcx, gs:60h
0x180001e2a  mov     r8, rsi; lpMem
0x180001e2d  xor     edx, edx; dwFlags
0x180001e2f  mov     rcx, [rcx+30h]; hHeap
0x180001e33  call    cs:__imp_HeapFree
0x180001e39  jmp     loc_180001D0E
0x180001e3e  add     rcx, 20h ; ' '
0x180001e42  call    CleanupNetBTParam
0x180001e47  mov     rcx, [r15+rsi+10h]
0x180001e4c  add     rcx, 48h ; 'H'
0x180001e50  call    CleanupDNSParam
0x180001e55  lea     rcx, [r12+10h]
0x180001e5a  call    DhcpFree
0x180001e5f  jmp     short loc_180001E0D
0x180001e61  mov     ebx, r14d
0x180001e64  mov     r10d, r14d
0x180001e67  mov     r8, [rsp+98h+var_60]
0x180001e6c  nop     dword ptr [rax+00h]
0x180001e70  mov     ecx, r10d
0x180001e73  lea     rax, [rcx+rcx*2]
0x180001e77  mov     rdx, [r8+rax*8+10h]
0x180001e7c  imul    rax, rcx, 78h ; 'x'
0x180001e80  movups  xmm0, xmmword ptr [rdx]
0x180001e83  movups  xmmword ptr [rax+r9], xmm0
0x180001e88  movups  xmm1, xmmword ptr [rdx+10h]
0x180001e8c  movups  xmmword ptr [rax+r9+10h], xmm1
0x180001e92  movups  xmm0, xmmword ptr [rdx+20h]
0x180001e96  movups  xmmword ptr [rax+r9+20h], xmm0
0x180001e9c  movups  xmm1, xmmword ptr [rdx+30h]
0x180001ea0  movups  xmmword ptr [rax+r9+30h], xmm1
0x180001ea6  movups  xmm0, xmmword ptr [rdx+40h]
0x180001eaa  movups  xmmword ptr [rax+r9+40h], xmm0
0x180001eb0  movups  xmm1, xmmword ptr [rdx+50h]
0x180001eb4  movups  xmmword ptr [rax+r9+50h], xmm1
0x180001eba  movups  xmm0, xmmword ptr [rdx+60h]
0x180001ebe  movups  xmmword ptr [rax+r9+60h], xmm0
0x180001ec4  movsd   xmm1, qword ptr [rdx+70h]
0x180001ec9  movsd   qword ptr [rax+r9+70h], xmm1
0x180001ed0  xorps   xmm0, xmm0
0x180001ed3  xor     eax, eax
0x180001ed5  movups  xmmword ptr [rdx+20h], xmm0
0x180001ed9  movups  xmmword ptr [rdx+30h], xmm0
0x180001edd  mov     [rdx+40h], rax
0x180001ee1  movups  xmmword ptr [rdx+48h], xmm0
0x180001ee5  movups  xmmword ptr [rdx+58h], xmm0
0x180001ee9  movups  xmmword ptr [rdx+68h], xmm0
0x180001eed  inc     r10d
0x180001ef0  cmp     r10d, edi
0x180001ef3  jb      loc_180001E70
0x180001ef9  mov     [r15], r9
0x180001efc  mov     [rsp+98h+arg_0], r14
0x180001f04  jmp     loc_180001CF6
0x180001f09  mov     ebx, 57h ; 'W'
0x180001f0e  jmp     loc_180001CF6
0x180001f13  mov     edx, 8Bh
0x180001f18  mov     r9, r12
0x180001f1b  call    WPP_SF_q
0x180001f20  jmp     loc_180001C0F
0x180001f25  mov     ebx, 57h ; 'W'
0x180001f2a  jmp     loc_180001CF6
0x180001f2f  mov     ebx, 8
0x180001f34  jmp     loc_180001CF6
0x180001f39  call    cs:__imp_GetCommandLineW
0x180001f3f  mov     r9, rax
0x180001f42  mov     edx, 8Ch
0x180001f47  mov     ecx, 404h
0x180001f4c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180001f53  call    WPP_SF_S
0x180001f58  jmp     loc_180001C77
0x180001f5d  call    cs:__imp_GetCommandLineW
0x180001f63  mov     edx, 8Dh
0x180001f68  mov     ecx, 404h
0x180001f6d  mov     [rsp+98h+var_78], rax
0x180001f72  mov     r9d, ebx
0x180001f75  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180001f7c  call    WPP_SF_DS
0x180001f81  jmp     loc_180001CEE
0x180010bc0  push    rbp
0x180010bc2  sub     rsp, 30h
0x180010bc6  mov     rbp, rdx
0x180010bc9  mov     rcx, [rcx]
0x180010bcc  mov     ecx, [rcx]; ExceptionCode
0x180010bce  call    cs:__imp_I_RpcExceptionFilter
0x180010bd4  nop
0x180010bd5  add     rsp, 30h
0x180010bd9  pop     rbp
0x180010bda  retn
```
