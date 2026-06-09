# Dhcpv6RequestCachedParamsEx

- ea: `0x180005ec0`
- end: `0x1800062e3`
- name: `Dhcpv6RequestCachedParamsEx`
- size: `1059`
- prototype: `__int64 __fastcall(int, const WCHAR *, __int64, unsigned int *, void ***)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180001e30`
- `0x180001e70`
- `0x180001ff0`
- `0x180002650`
- `0x180004c40`
- `0x180005ec0`
- `0x1800072fc`
- `0x180008008`
- `0x18000809c`
- `0x1800080e4`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006084`
- `RPCRT4!NdrClientCall3` at `0x180006084`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006025`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800060a0`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800060cd`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006025`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800060a0`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800060cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006104`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006124`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006104`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006124`

## pseudocode

```c
__int64 __fastcall Dhcpv6RequestCachedParamsEx(int a1, const WCHAR *a2, __int64 a3, unsigned int *a4, void ***a5)
{
  unsigned int v8; // edi
  void **v10; // rsi
  unsigned int Pointer; // ebx
  __int64 v12; // rax
  _DWORD *v13; // r9
  unsigned int i; // r8d
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  LPWSTR CommandLineW; // rax
  int v19; // ecx
  CLIENT_CALL_RETURN v20; // rax
  LPWSTR v21; // rax
  int v22; // ecx
  int v23; // r8d
  unsigned int v24; // eax
  HLOCAL v25; // rax
  char *v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  unsigned int j; // r13d
  __int64 v30; // r14
  __int64 v31; // r15
  NET_LUID *v32; // [rsp+20h] [rbp-98h]
  __int64 v33; // [rsp+30h] [rbp-88h]
  __int128 *v34; // [rsp+40h] [rbp-78h]
  NET_LUID v35; // [rsp+58h] [rbp-60h] BYREF
  CLIENT_CALL_RETURN v36; // [rsp+60h] [rbp-58h]
  __int128 v37; // [rsp+70h] [rbp-48h] BYREF
  __int128 v38; // [rsp+80h] [rbp-38h] BYREF

  v8 = 0;
  v35.Value = 0;
  v38 = 0;
  v37 = 0;
  if ( !g_fVelocityDhcpv6MultiRecordOptionSupport )
    return 50;
  v10 = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SDq(a1, (_DWORD)a2, a3, (_DWORD)a2, a1, a3);
  if ( a5 )
    *a5 = 0;
  if ( a2
    && a5
    && (!a3 || !*(_DWORD *)a3 && *(_QWORD *)(a3 + 8) && *(_DWORD *)(a3 + 16))
    && a4
    && (v12 = *a4, (_DWORD)v12)
    && *((_QWORD *)a4 + 1) )
  {
    LODWORD(v38) = *a4;
    v13 = DhcpAlloc(24 * v12);
    *((_QWORD *)&v38 + 1) = v13;
    if ( !v13 )
      goto LABEL_18;
    for ( i = 0; i < *a4; ++i )
    {
      v15 = 32LL * i;
      v16 = *((_QWORD *)a4 + 1);
      if ( *(_DWORD *)(v15 + v16 + 24) || *(_QWORD *)(v15 + v16 + 16) || *(_DWORD *)(v15 + v16) )
        goto LABEL_8;
      v17 = 3LL * i;
      v13[2 * v17 + 1] = *(_DWORD *)(v15 + v16 + 4);
      *(_DWORD *)(*((_QWORD *)&v38 + 1) + 8 * v17 + 8) = *(_DWORD *)(v15 + *((_QWORD *)a4 + 1) + 8);
      v13 = (_DWORD *)*((_QWORD *)&v38 + 1);
    }
    Pointer = Dhcpv6AdapterNameToIfId(a2, &v35);
    if ( Pointer )
      goto LABEL_41;
    if ( (xmmword_18000F160 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_SS(
        v19,
        Pointer + 86,
        (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
        (_DWORD)a2,
        (__int64)CommandLineW);
    }
    v36.Simple = 0;
    v34 = &v37;
    HIDWORD(v33) = HIDWORD(a3);
    v32 = &v35;
    v20.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xDu, 0).Pointer;
    Pointer = (unsigned int)v20.Pointer;
    v36.Pointer = v20.Pointer;
    if ( (xmmword_18000F160 & 0x10) != 0 )
    {
      v21 = GetCommandLineW();
      WPP_SF_DSS(v22, 87, v23, Pointer, (__int64)a2, (__int64)v21);
    }
    if ( Pointer || !(_DWORD)v37 )
      goto LABEL_41;
    v10 = (void **)LocalAlloc(0x40u, 0x10u);
    if ( v10 && (v24 = v37, *(_DWORD *)v10 = v37, v25 = LocalAlloc(0x40u, 32LL * v24), (v10[1] = v25) != 0) )
    {
      Pointer = 0;
      if ( (xmmword_18000F160 & 0x10) != 0 )
        WPP_SF_dd(v27, 88, WPP_cb48999f8e5838f952918348529d50de_Traceguids, (unsigned int)v38, v37);
      for ( j = 0; j < (unsigned int)v37; ++j )
      {
        v30 = 24LL * j;
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          LODWORD(v34) = *(_DWORD *)(24LL * j + *((_QWORD *)&v37 + 1) + 12);
          LODWORD(v33) = *(_DWORD *)(24LL * j + *((_QWORD *)&v37 + 1));
          LODWORD(v32) = *(_DWORD *)(24LL * j + *((_QWORD *)&v37 + 1) + 4);
          WPP_SF_ddlDqd(
            *((_QWORD *)&v37 + 1),
            v26,
            v28,
            j,
            v32,
            *(_DWORD *)(24LL * j + *((_QWORD *)&v37 + 1) + 8),
            v33,
            *(_QWORD *)(24LL * j + *((_QWORD *)&v37 + 1) + 16),
            v34);
        }
        v31 = 32LL * j;
        *(_DWORD *)((char *)v10[1] + v31 + 4) = *(_DWORD *)(v30 + *((_QWORD *)&v37 + 1) + 4);
        *(_DWORD *)((char *)v10[1] + v31 + 8) = *(_DWORD *)(v30 + *((_QWORD *)&v37 + 1) + 8);
        *(_DWORD *)((char *)v10[1] + v31) = *(_DWORD *)(v30 + *((_QWORD *)&v37 + 1));
        *(_QWORD *)((char *)v10[1] + v31 + 16) = *(_QWORD *)(v30 + *((_QWORD *)&v37 + 1) + 16);
        *(_QWORD *)(v30 + *((_QWORD *)&v37 + 1) + 16) = 0;
        v26 = (char *)v10[1];
        *(_DWORD *)&v26[v31 + 24] = *(_DWORD *)(v30 + *((_QWORD *)&v37 + 1) + 12);
        *(_DWORD *)(v30 + *((_QWORD *)&v37 + 1) + 12) = 0;
      }
      *a5 = v10;
      v10 = 0;
    }
    else
    {
LABEL_18:
      Pointer = 8;
    }
  }
  else
  {
LABEL_8:
    Pointer = 87;
  }
LABEL_41:
  if ( *((_QWORD *)&v37 + 1) && (_DWORD)v37 )
  {
    do
      DhcpMidlUserFree((void **)(*((_QWORD *)&v37 + 1) + 8 * (3LL * v8++ + 2)));
    while ( v8 < (unsigned int)v37 );
  }
  DhcpMidlUserFree((void **)&v37 + 1);
  Dhcpv6FreeCachedParamsDataEx(v10);
  DhcpFree((LPVOID *)&v38 + 1);
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_D(1028, 90, WPP_cb48999f8e5838f952918348529d50de_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180005ec0  mov     rax, rsp
0x180005ec3  mov     [rax+8], rbx
0x180005ec7  mov     [rax+18h], rsi
0x180005ecb  mov     [rax+10h], rdx
0x180005ecf  push    rdi
0x180005ed0  push    r12
0x180005ed2  push    r13
0x180005ed4  push    r14
0x180005ed6  push    r15
0x180005ed8  sub     rsp, 90h
0x180005edf  mov     rbx, r9
0x180005ee2  mov     r15, r8
0x180005ee5  mov     r14, rdx
0x180005ee8  mov     r13d, ecx
0x180005eeb  xor     edi, edi
0x180005eed  mov     [rax-60h], rdi
0x180005ef1  xorps   xmm0, xmm0
0x180005ef4  movups  xmmword ptr [rax-38h], xmm0
0x180005ef8  xorps   xmm1, xmm1
0x180005efb  movups  xmmword ptr [rax-48h], xmm1
0x180005eff  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, edi
0x180005f05  jnz     short loc_180005F0F
0x180005f07  lea     eax, [rdi+32h]
0x180005f0a  jmp     loc_1800062C6
0x180005f0f  mov     rsi, rdi
0x180005f12  test    byte ptr cs:xmmword_18000F160, 10h
0x180005f19  jz      short loc_180005F2D
0x180005f1b  mov     [rsp+0B8h+var_90], r15
0x180005f20  mov     dword ptr [rsp+0B8h+var_98], r13d
0x180005f25  mov     r9, r14
0x180005f28  call    WPP_SF_SDq
0x180005f2d  mov     r12, [rsp+0B8h+arg_20]
0x180005f35  test    r12, r12
0x180005f38  jz      short loc_180005F3E
0x180005f3a  mov     [r12], rdi
0x180005f3e  test    r14, r14
0x180005f41  jnz     short loc_180005F4D
0x180005f43  mov     ebx, 57h ; 'W'
0x180005f48  jmp     loc_180006256
0x180005f4d  test    r12, r12
0x180005f50  jz      short loc_180005F43
0x180005f52  test    r15, r15
0x180005f55  jz      short loc_180005F68
0x180005f57  cmp     [r15], edi
0x180005f5a  jnz     short loc_180005F43
0x180005f5c  cmp     [r15+8], rdi
0x180005f60  jz      short loc_180005F43
0x180005f62  cmp     [r15+10h], edi
0x180005f66  jz      short loc_180005F43
0x180005f68  test    rbx, rbx
0x180005f6b  jz      short loc_180005F43
0x180005f6d  mov     eax, [rbx]
0x180005f6f  test    eax, eax
0x180005f71  jz      short loc_180005F43
0x180005f73  cmp     [rbx+8], rdi
0x180005f77  jz      short loc_180005F43
0x180005f79  mov     [rsp+0B8h+var_38], eax
0x180005f80  lea     rcx, [rax+rax*2]
0x180005f84  shl     rcx, 3
0x180005f88  call    DhcpAlloc
0x180005f8d  mov     r9, rax
0x180005f90  mov     [rsp+0B8h+var_30], rax
0x180005f98  test    rax, rax
0x180005f9b  jnz     short loc_180005FA7
0x180005f9d  mov     ebx, 8
0x180005fa2  jmp     loc_180006256
0x180005fa7  mov     r8d, edi
0x180005faa  cmp     r8d, [rbx]
0x180005fad  jnb     short loc_180006005
0x180005faf  mov     edx, r8d
0x180005fb2  mov     ecx, r8d
0x180005fb5  shl     rcx, 5
0x180005fb9  mov     rax, [rbx+8]
0x180005fbd  cmp     [rcx+rax+18h], edi
0x180005fc1  jnz     short loc_180005F43
0x180005fc3  cmp     [rcx+rax+10h], rdi
0x180005fc8  jnz     loc_180005F43
0x180005fce  cmp     [rcx+rax], edi
0x180005fd1  jnz     loc_180005F43
0x180005fd7  lea     rdx, [rdx+rdx*2]
0x180005fdb  mov     eax, [rcx+rax+4]
0x180005fdf  mov     [r9+rdx*8+4], eax
0x180005fe4  mov     rax, [rbx+8]
0x180005fe8  mov     ecx, [rcx+rax+8]
0x180005fec  mov     rax, [rsp+0B8h+var_30]
0x180005ff4  mov     [rax+rdx*8+8], ecx
0x180005ff8  inc     r8d
0x180005ffb  mov     r9, [rsp+0B8h+var_30]
0x180006003  jmp     short loc_180005FAA
0x180006005  lea     rdx, [rsp+0B8h+var_60]
0x18000600a  mov     rcx, r14
0x18000600d  call    Dhcpv6AdapterNameToIfId
0x180006012  mov     ebx, eax
0x180006014  test    eax, eax
0x180006016  jnz     loc_180006256
0x18000601c  test    byte ptr cs:xmmword_18000F160, 10h
0x180006023  jz      short loc_180006043
0x180006025  call    cs:__imp_GetCommandLineW
0x18000602b  lea     edx, [rbx+56h]
0x18000602e  mov     [rsp+0B8h+var_98], rax
0x180006033  mov     r9, r14
0x180006036  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x18000603d  call    WPP_SF_SS
0x180006042  nop
0x180006043  mov     [rsp+0B8h+var_58], rdi
0x180006048  lea     rax, [rsp+0B8h+var_48]
0x18000604d  mov     [rsp+0B8h+var_78], rax
0x180006052  lea     rax, [rsp+0B8h+var_38]
0x18000605a  mov     [rsp+0B8h+var_80], rax
0x18000605f  mov     [rsp+0B8h+var_88], r15
0x180006064  mov     dword ptr [rsp+0B8h+var_90], r13d
0x180006069  lea     rax, [rsp+0B8h+var_60]
0x18000606e  mov     [rsp+0B8h+var_98], rax
0x180006073  xor     r9d, r9d
0x180006076  xor     r8d, r8d; pReturnValue
0x180006079  lea     edx, [r9+0Dh]; nProcNum
0x18000607d  lea     rcx, pProxyInfo; pProxyInfo
0x180006084  call    cs:__imp_NdrClientCall3
0x18000608a  mov     rbx, rax
0x18000608d  mov     [rsp+0B8h+var_58], rax
0x180006092  mov     [rsp+0B8h+var_68], eax
0x180006096  jmp     short loc_1800060C4
0x180006098  mov     edi, eax
0x18000609a  mov     ebx, eax
0x18000609c  mov     [rsp+0B8h+var_68], eax
0x1800060a0  call    cs:__imp_GetCommandLineW
0x1800060a6  mov     rdx, rax
0x1800060a9  mov     ecx, ebx
0x1800060ab  call    TraceRpcException
0x1800060b0  xor     edi, edi
0x1800060b2  mov     r12, [rsp+0B8h+arg_20]
0x1800060ba  mov     r14, [rsp+0B8h+arg_8]
0x1800060c2  mov     esi, edi
0x1800060c4  test    byte ptr cs:xmmword_18000F160, 10h
0x1800060cb  jz      short loc_1800060EA
0x1800060cd  call    cs:__imp_GetCommandLineW
0x1800060d3  mov     edx, 57h ; 'W'
0x1800060d8  mov     [rsp+0B8h+var_90], rax
0x1800060dd  mov     [rsp+0B8h+var_98], r14
0x1800060e2  mov     r9d, ebx
0x1800060e5  call    WPP_SF_DSS
0x1800060ea  test    ebx, ebx
0x1800060ec  jnz     loc_180006256
0x1800060f2  cmp     [rsp+0B8h+var_48], edi
0x1800060f6  jz      loc_180006256
0x1800060fc  lea     edx, [rbx+10h]; uBytes
0x1800060ff  lea     ebx, [rdx+30h]
0x180006102  mov     ecx, ebx; uFlags
0x180006104  call    cs:__imp_LocalAlloc
0x18000610a  mov     rsi, rax
0x18000610d  test    rax, rax
0x180006110  jz      loc_180005F9D
0x180006116  mov     eax, [rsp+0B8h+var_48]
0x18000611a  mov     [rsi], eax
0x18000611c  mov     edx, eax
0x18000611e  shl     rdx, 5; uBytes
0x180006122  mov     ecx, ebx; uFlags
0x180006124  call    cs:__imp_LocalAlloc
0x18000612a  mov     [rsi+8], rax
0x18000612e  test    rax, rax
0x180006131  jz      loc_180005F9D
0x180006137  mov     ebx, edi
0x180006139  test    byte ptr cs:xmmword_18000F160, 10h
0x180006140  jz      short loc_180006163
0x180006142  mov     edx, 58h ; 'X'
0x180006147  mov     eax, [rsp+0B8h+var_48]
0x18000614b  mov     dword ptr [rsp+0B8h+var_98], eax
0x18000614f  mov     r9d, [rsp+0B8h+var_38]
0x180006157  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x18000615e  call    WPP_SF_dd
0x180006163  mov     r13d, edi
0x180006166  cmp     [rsp+0B8h+var_48], edi
0x18000616a  jbe     loc_18000624F
0x180006170  mov     r15d, r13d
0x180006173  test    byte ptr cs:xmmword_18000F160, 10h
0x18000617a  jz      short loc_1800061C4
0x18000617c  lea     rax, [r15+r15*2]
0x180006180  lea     r14, ds:0[rax*8]
0x180006188  mov     rcx, [rsp+0B8h+var_40]
0x18000618d  mov     eax, [r14+rcx+0Ch]
0x180006192  mov     dword ptr [rsp+0B8h+var_78], eax
0x180006196  mov     rax, [r14+rcx+10h]
0x18000619b  mov     [rsp+0B8h+var_80], rax
0x1800061a0  mov     eax, [r14+rcx]
0x1800061a4  mov     dword ptr [rsp+0B8h+var_88], eax
0x1800061a8  mov     eax, [r14+rcx+8]
0x1800061ad  mov     dword ptr [rsp+0B8h+var_90], eax
0x1800061b1  mov     eax, [r14+rcx+4]
0x1800061b6  mov     dword ptr [rsp+0B8h+var_98], eax
0x1800061ba  mov     r9d, r13d
0x1800061bd  call    WPP_SF_ddlDqd
0x1800061c2  jmp     short loc_1800061CC
0x1800061c4  lea     r14, [r15+r15*2]
0x1800061c8  shl     r14, 3
0x1800061cc  shl     r15, 5
0x1800061d0  mov     rdx, [rsi+8]
0x1800061d4  mov     rax, [rsp+0B8h+var_40]
0x1800061d9  mov     ecx, [r14+rax+4]
0x1800061de  mov     [r15+rdx+4], ecx
0x1800061e3  mov     rdx, [rsi+8]
0x1800061e7  mov     rax, [rsp+0B8h+var_40]
0x1800061ec  mov     ecx, [r14+rax+8]
0x1800061f1  mov     [r15+rdx+8], ecx
0x1800061f6  mov     rdx, [rsi+8]
0x1800061fa  mov     rax, [rsp+0B8h+var_40]
0x1800061ff  mov     ecx, [r14+rax]
0x180006203  mov     [r15+rdx], ecx
0x180006207  mov     rdx, [rsi+8]
0x18000620b  mov     rax, [rsp+0B8h+var_40]
0x180006210  mov     rcx, [r14+rax+10h]
0x180006215  mov     [r15+rdx+10h], rcx
0x18000621a  mov     rax, [rsp+0B8h+var_40]
0x18000621f  mov     [r14+rax+10h], rdi
0x180006224  mov     rdx, [rsi+8]
0x180006228  mov     rax, [rsp+0B8h+var_40]
0x18000622d  mov     ecx, [r14+rax+0Ch]
0x180006232  mov     [r15+rdx+18h], ecx
0x180006237  mov     rax, [rsp+0B8h+var_40]
0x18000623c  mov     [r14+rax+0Ch], edi
0x180006241  inc     r13d
0x180006244  cmp     r13d, [rsp+0B8h+var_48]
0x180006249  jb      loc_180006170
0x18000624f  mov     [r12], rsi
0x180006253  mov     rsi, rdi
0x180006256  cmp     [rsp+0B8h+var_40], rdi
0x18000625b  jz      short loc_180006283
0x18000625d  cmp     [rsp+0B8h+var_48], edi
0x180006261  jbe     short loc_180006283
0x180006263  mov     eax, edi
0x180006265  lea     rdx, [rax+rax*2]
0x180006269  mov     rax, [rsp+0B8h+var_40]
0x18000626e  lea     rdx, [rdx+2]
0x180006272  lea     rcx, [rax+rdx*8]
0x180006276  call    DhcpMidlUserFree
0x18000627b  inc     edi
0x18000627d  cmp     edi, [rsp+0B8h+var_48]
0x180006281  jb      short loc_180006263
0x180006283  lea     rcx, [rsp+0B8h+var_40]
0x180006288  call    DhcpMidlUserFree
0x18000628d  mov     rcx, rsi
0x180006290  call    Dhcpv6FreeCachedParamsDataEx
0x180006295  lea     rcx, [rsp+0B8h+var_30]
0x18000629d  call    DhcpFree
0x1800062a2  test    byte ptr cs:xmmword_18000F160, 10h
0x1800062a9  jz      short loc_1800062C4
0x1800062ab  mov     edx, 5Ah ; 'Z'
0x1800062b0  mov     ecx, 404h
0x1800062b5  mov     r9d, ebx
0x1800062b8  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800062bf  call    WPP_SF_D
0x1800062c4  mov     eax, ebx
0x1800062c6  lea     r11, [rsp+0B8h+var_28]
0x1800062ce  mov     rbx, [r11+30h]
0x1800062d2  mov     rsi, [r11+40h]
0x1800062d6  mov     rsp, r11
0x1800062d9  pop     r15
0x1800062db  pop     r14
0x1800062dd  pop     r13
0x1800062df  pop     r12
0x1800062e1  pop     rdi
0x1800062e2  retn
0x180007a2e  push    rbp
0x180007a30  sub     rsp, 50h
0x180007a34  mov     rbp, rdx
0x180007a37  mov     rcx, [rcx]
0x180007a3a  mov     ecx, [rcx]; ExceptionCode
0x180007a3c  call    cs:__imp_I_RpcExceptionFilter
0x180007a42  nop
0x180007a43  add     rsp, 50h
0x180007a47  pop     rbp
0x180007a48  retn
```
