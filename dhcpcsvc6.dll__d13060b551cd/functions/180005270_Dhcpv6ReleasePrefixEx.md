# Dhcpv6ReleasePrefixEx

- ea: `0x180005270`
- end: `0x180005579`
- name: `Dhcpv6ReleasePrefixEx`
- size: `777`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800051b0`

## callees

- `0x180001e30`
- `0x180001e70`
- `0x180001ff0`
- `0x180002650`
- `0x180003650`
- `0x180005270`
- `0x1800072fc`
- `0x180007891`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000549c`
- `RPCRT4!NdrClientCall3` at `0x18000549c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000543a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800054b8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800054d9`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000543a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800054b8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800054d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005396`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005396`

## pseudocode

```c
__int64 __fastcall Dhcpv6ReleasePrefixEx(const WCHAR *a1, __int64 a2, __int64 a3)
{
  unsigned int Pointer; // ebx
  void *v6; // rax
  unsigned __int16 i; // r8
  __int64 v8; // rdx
  LPWSTR CommandLineW; // rax
  int v10; // ecx
  CLIENT_CALL_RETURN v11; // rax
  LPWSTR v12; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // ecx
  NET_LUID v17; // [rsp+58h] [rbp-70h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+60h] [rbp-68h]
  __int128 v19; // [rsp+68h] [rbp-60h] BYREF
  __int128 v20; // [rsp+78h] [rbp-50h]
  void *v21[5]; // [rsp+88h] [rbp-40h] BYREF

  v17.Value = 0;
  v20 = 0;
  memset(v21, 0, 32);
  v19 = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 36, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 37, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
  }
  else if ( a1 && a3 && *(_QWORD *)(a3 + 8) && *(_DWORD *)a3 && *(_QWORD *)(a3 + 64) && *(_DWORD *)(a3 + 72) )
  {
    Pointer = Dhcpv6AdapterNameToIfId(a1, &v17);
    if ( !Pointer )
    {
      v6 = DhcpAlloc(*(unsigned int *)(a3 + 72));
      *((_QWORD *)&v19 + 1) = v6;
      if ( v6
        && (memcpy_0(v6, *(const void **)(a3 + 64), *(unsigned int *)(a3 + 72)),
            LOWORD(v19) = *(_WORD *)(a3 + 72),
            LODWORD(v20) = *(_DWORD *)(a3 + 16),
            DWORD1(v20) = *(_DWORD *)(a3 + 24),
            *((_QWORD *)&v20 + 1) = *(unsigned int *)(a3 + 32),
            LODWORD(v21[0]) = *(_DWORD *)a3,
            (v21[1] = LocalAlloc(0x40u, 32LL * LODWORD(v21[0]))) != 0) )
      {
        for ( i = 0; (unsigned int)i < LODWORD(v21[0]); ++i )
        {
          v8 = 32LL * i;
          *(_DWORD *)((char *)v21[1] + v8 + 16) = *(unsigned __int8 *)(v8 + *(_QWORD *)(a3 + 8) + 16);
          *(_DWORD *)((char *)v21[1] + v8 + 20) = *(_DWORD *)(v8 + *(_QWORD *)(a3 + 8) + 20);
          *(_QWORD *)((char *)v21[1] + v8 + 24) = *(unsigned int *)(v8 + *(_QWORD *)(a3 + 8) + 24);
          *(_OWORD *)((char *)v21[1] + v8) = *(_OWORD *)(v8 + *(_QWORD *)(a3 + 8));
        }
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_SS(
            v10,
            38,
            (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
            (_DWORD)a1,
            (__int64)CommandLineW);
        }
        v18.Simple = 0;
        v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0).Pointer;
        Pointer = (unsigned int)v11.Pointer;
        v18.Pointer = v11.Pointer;
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          v12 = GetCommandLineW();
          WPP_SF_DSS(v13, 39, v14, Pointer, (__int64)a1, (__int64)v12);
        }
      }
      else
      {
        Pointer = 8;
      }
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpMidlUserFree(&v21[1]);
  DhcpFree((LPVOID *)&v19 + 1);
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v15, 40, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180005270  mov     rax, rsp
0x180005273  mov     [rax+10h], rbx
0x180005277  mov     [rax+18h], rsi
0x18000527b  mov     [rax+8], rcx
0x18000527f  push    rdi
0x180005280  push    r14
0x180005282  push    r15
0x180005284  sub     rsp, 0B0h
0x18000528b  mov     r14d, r9d
0x18000528e  mov     rdi, r8
0x180005291  mov     r15, rdx
0x180005294  mov     rsi, rcx
0x180005297  mov     qword ptr [rax-70h], 0
0x18000529f  xorps   xmm0, xmm0
0x1800052a2  movups  xmmword ptr [rax-50h], xmm0
0x1800052a6  movups  xmmword ptr [rax-40h], xmm0
0x1800052aa  movups  xmmword ptr [rax-30h], xmm0
0x1800052ae  movups  xmmword ptr [rax-60h], xmm0
0x1800052b2  test    byte ptr cs:xmmword_18000F160, 10h
0x1800052b9  jz      short loc_1800052CF
0x1800052bb  mov     edx, 24h ; '$'
0x1800052c0  mov     r9, rcx
0x1800052c3  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800052ca  call    WPP_SF_S
0x1800052cf  call    DhcpIsFSEGuestSystem
0x1800052d4  test    eax, eax
0x1800052d6  jnz     loc_1800054FF
0x1800052dc  test    rsi, rsi
0x1800052df  jz      loc_1800054F8
0x1800052e5  test    rdi, rdi
0x1800052e8  jz      loc_1800054F8
0x1800052ee  cmp     qword ptr [rdi+8], 0
0x1800052f3  jz      loc_1800054F8
0x1800052f9  cmp     [rdi], eax
0x1800052fb  jz      loc_1800054F8
0x180005301  cmp     qword ptr [rdi+40h], 0
0x180005306  jz      loc_1800054F8
0x18000530c  cmp     [rdi+48h], eax
0x18000530f  jz      loc_1800054F8
0x180005315  lea     rdx, [rsp+0C8h+var_70]
0x18000531a  mov     rcx, rsi
0x18000531d  call    Dhcpv6AdapterNameToIfId
0x180005322  mov     ebx, eax
0x180005324  test    eax, eax
0x180005326  jnz     loc_180005526
0x18000532c  mov     ecx, [rdi+48h]
0x18000532f  call    DhcpAlloc
0x180005334  mov     [rsp+0C8h+var_58], rax
0x180005339  test    rax, rax
0x18000533c  jnz     short loc_180005348
0x18000533e  mov     ebx, 8
0x180005343  jmp     loc_180005526
0x180005348  mov     r8d, [rdi+48h]; Size
0x18000534c  mov     rdx, [rdi+40h]; Src
0x180005350  mov     rcx, rax; void *
0x180005353  call    memcpy_0
0x180005358  movzx   eax, word ptr [rdi+48h]
0x18000535c  mov     [rsp+0C8h+var_60], ax
0x180005361  mov     eax, [rdi+10h]
0x180005364  mov     [rsp+0C8h+var_50], eax
0x180005368  mov     eax, [rdi+18h]
0x18000536b  mov     [rsp+0C8h+var_4C], eax
0x18000536f  mov     eax, [rdi+20h]
0x180005372  mov     [rsp+0C8h+var_48], eax
0x180005379  mov     [rsp+0C8h+var_44], 0
0x180005384  mov     edx, [rdi]
0x180005386  mov     [rsp+0C8h+var_40], edx
0x18000538d  shl     rdx, 5; uBytes
0x180005391  mov     ecx, 40h ; '@'; uFlags
0x180005396  call    cs:__imp_LocalAlloc
0x18000539c  mov     [rsp+0C8h+var_38], rax
0x1800053a4  test    rax, rax
0x1800053a7  jz      short loc_18000533E
0x1800053a9  xor     r8d, r8d
0x1800053ac  cmp     [rsp+0C8h+var_40], r8d
0x1800053b4  jbe     short loc_180005431
0x1800053b6  movzx   edx, r8w
0x1800053ba  shl     rdx, 5
0x1800053be  mov     rax, [rdi+8]
0x1800053c2  movzx   ecx, byte ptr [rdx+rax+10h]
0x1800053c7  mov     rax, [rsp+0C8h+var_38]
0x1800053cf  mov     [rdx+rax+10h], ecx
0x1800053d3  mov     rax, [rdi+8]
0x1800053d7  mov     ecx, [rdx+rax+14h]
0x1800053db  mov     rax, [rsp+0C8h+var_38]
0x1800053e3  mov     [rdx+rax+14h], ecx
0x1800053e7  mov     rax, [rdi+8]
0x1800053eb  mov     ecx, [rdx+rax+18h]
0x1800053ef  mov     rax, [rsp+0C8h+var_38]
0x1800053f7  mov     [rdx+rax+18h], ecx
0x1800053fb  mov     rax, [rsp+0C8h+var_38]
0x180005403  mov     dword ptr [rdx+rax+1Ch], 0
0x18000540b  mov     rax, [rdi+8]
0x18000540f  movups  xmm0, xmmword ptr [rdx+rax]
0x180005413  mov     rax, [rsp+0C8h+var_38]
0x18000541b  movdqu  xmmword ptr [rdx+rax], xmm0
0x180005420  inc     r8w
0x180005424  movzx   eax, r8w
0x180005428  cmp     eax, [rsp+0C8h+var_40]
0x18000542f  jb      short loc_1800053B6
0x180005431  test    byte ptr cs:xmmword_18000F160, 10h
0x180005438  jz      short loc_18000545A
0x18000543a  call    cs:__imp_GetCommandLineW
0x180005440  mov     edx, 26h ; '&'
0x180005445  mov     [rsp+0C8h+var_A8], rax
0x18000544a  mov     r9, rsi
0x18000544d  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005454  call    WPP_SF_SS
0x180005459  nop
0x18000545a  mov     [rsp+0C8h+var_68], 0
0x180005463  mov     [rsp+0C8h+var_88], r14d
0x180005468  lea     rax, [rsp+0C8h+var_60]
0x18000546d  mov     [rsp+0C8h+var_90], rax
0x180005472  lea     rax, [rsp+0C8h+var_50]
0x180005477  mov     [rsp+0C8h+var_98], rax
0x18000547c  mov     [rsp+0C8h+var_A0], r15
0x180005481  lea     rax, [rsp+0C8h+var_70]
0x180005486  mov     [rsp+0C8h+var_A8], rax
0x18000548b  xor     r9d, r9d
0x18000548e  xor     r8d, r8d; pReturnValue
0x180005491  lea     edx, [r9+2]; nProcNum
0x180005495  lea     rcx, pProxyInfo; pProxyInfo
0x18000549c  call    cs:__imp_NdrClientCall3
0x1800054a2  mov     rbx, rax
0x1800054a5  mov     [rsp+0C8h+var_68], rax
0x1800054aa  mov     [rsp+0C8h+var_78], eax
0x1800054ae  jmp     short loc_1800054D0
0x1800054b0  mov     edi, eax
0x1800054b2  mov     ebx, eax
0x1800054b4  mov     [rsp+0C8h+var_78], eax
0x1800054b8  call    cs:__imp_GetCommandLineW
0x1800054be  mov     rdx, rax
0x1800054c1  mov     ecx, ebx
0x1800054c3  call    TraceRpcException
0x1800054c8  mov     rsi, [rsp+0C8h+arg_0]
0x1800054d0  test    byte ptr cs:xmmword_18000F160, 10h
0x1800054d7  jz      short loc_180005526
0x1800054d9  call    cs:__imp_GetCommandLineW
0x1800054df  mov     edx, 27h ; '''
0x1800054e4  mov     [rsp+0C8h+var_A0], rax
0x1800054e9  mov     [rsp+0C8h+var_A8], rsi
0x1800054ee  mov     r9d, ebx
0x1800054f1  call    WPP_SF_DSS
0x1800054f6  jmp     short loc_180005526
0x1800054f8  mov     ebx, 57h ; 'W'
0x1800054fd  jmp     short loc_180005526
0x1800054ff  mov     r9d, 32h ; '2'
0x180005505  mov     ebx, r9d
0x180005508  test    byte ptr cs:xmmword_18000F160, 2
0x18000550f  jz      short loc_180005526
0x180005511  lea     edx, [r9-0Dh]
0x180005515  mov     ecx, 401h
0x18000551a  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005521  call    WPP_SF_D
0x180005526  lea     rcx, [rsp+0C8h+var_38]
0x18000552e  call    DhcpMidlUserFree
0x180005533  lea     rcx, [rsp+0C8h+var_58]
0x180005538  call    DhcpFree
0x18000553d  test    byte ptr cs:xmmword_18000F160, 10h
0x180005544  jz      short loc_18000555E
0x180005546  mov     edx, 28h ; '('
0x18000554b  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x18000554f  mov     r9, rsi
0x180005552  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005559  call    WPP_SF_SD
0x18000555e  mov     eax, ebx
0x180005560  lea     r11, [rsp+0C8h+var_18]
0x180005568  mov     rbx, [r11+28h]
0x18000556c  mov     rsi, [r11+30h]
0x180005570  mov     rsp, r11
0x180005573  pop     r15
0x180005575  pop     r14
0x180005577  pop     rdi
0x180005578  retn
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
