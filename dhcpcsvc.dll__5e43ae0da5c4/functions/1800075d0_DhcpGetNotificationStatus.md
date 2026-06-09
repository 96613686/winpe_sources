# DhcpGetNotificationStatus

- ea: `0x1800075d0`
- end: `0x180007949`
- name: `DhcpGetNotificationStatus`
- size: `889`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001f90`
- `0x180002c50`
- `0x180003110`
- `0x180003210`
- `0x1800075d0`
- `0x18000f4ec`
- `0x180010aac`
- `0x1800127f0`
- `0x180012850`
- `0x180012a40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180007696`
- `RPCRT4!NdrClientCall3` at `0x180007696`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000764e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800076b5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800076e8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000764e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800076b5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800076e8`

## pseudocode

```c
__int64 __fastcall DhcpGetNotificationStatus(__int64 a1, __int64 *a2)
{
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  CLIENT_CALL_RETURN v6; // rax
  CLIENT_CALL_RETURN v7; // rdx
  CLIENT_CALL_RETURN v8; // r8
  LPWSTR v9; // rax
  __int64 v10; // rax
  __int64 v11; // r8
  unsigned int i; // r15d
  __int64 v13; // r14
  __int64 v14; // rdx
  size_t v15; // rdx
  unsigned int j; // r13d
  const wchar_t *v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  HRESULT v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  size_t v23; // rcx
  __int64 v24; // rbx
  void *v25; // rcx
  unsigned int k; // esi
  unsigned int m; // r15d
  __int128 v29; // [rsp+38h] [rbp-50h] BYREF
  int Size; // [rsp+90h] [rbp+8h]
  size_t Sizea; // [rsp+90h] [rbp+8h]
  size_t pcbLength; // [rsp+A0h] [rbp+18h] BYREF
  __int64 *v33; // [rsp+A8h] [rbp+20h]

  v29 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 198, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( !a1 || !a2 || (v33 = a2 + 1, *((_DWORD *)a2 + 2)) || *a2 )
  {
    Pointer = 87;
  }
  else
  {
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_S(1028, 199, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
    }
    pcbLength = 0;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Du, 0).Pointer;
    Pointer = (unsigned int)v6.Pointer;
    pcbLength = v6.Simple;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v9 = GetCommandLineW();
      WPP_SF_DS(1028, 200, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v9);
    }
    if ( !Pointer && DWORD2(v29) )
    {
      v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))DhcpAlloc)(
              24LL * DWORD2(v29),
              (CLIENT_CALL_RETURN)v7.Simple,
              (CLIENT_CALL_RETURN)v8.Simple);
      *a2 = v10;
      if ( v10 )
      {
        *((_DWORD *)a2 + 2) = DWORD2(v29);
        for ( i = 0; ; ++i )
        {
          Pointer = 0;
          if ( i >= DWORD2(v29) )
            goto LABEL_33;
          v13 = 3LL * i;
          *(_WORD *)(*a2 + 8 * v13) = *(_WORD *)(v29 + 24LL * i);
          v14 = *a2;
          *(_DWORD *)(*a2 + 8 * v13 + 16) = *(_DWORD *)(v29 + 24LL * i + 16);
          if ( *(_QWORD *)(v29 + 24LL * i + 8) )
            break;
          *(_QWORD *)(*a2 + 24LL * i + 8) = 0;
LABEL_19:
          ;
        }
        *(_QWORD *)(*a2 + 24LL * i + 8) = DhcpAlloc(8LL * *(unsigned int *)(v29 + 24LL * i + 16), v14, v11);
        if ( *(_QWORD *)(*a2 + 24LL * i + 8) )
        {
          for ( j = 0; ; ++j )
          {
            if ( j >= *(_DWORD *)(v29 + 24LL * i + 16) )
              goto LABEL_19;
            v17 = *(const wchar_t **)(*(_QWORD *)(v29 + 24LL * i + 8) + 8LL * j);
            pcbLength = 0;
            if ( !v17 )
              break;
            v20 = StringCbLengthW(v17, v15, &pcbLength);
            v18 = (unsigned int)v20;
            if ( v20 < 0 )
            {
              HIDWORD(pcbLength) = 108;
              goto LABEL_25;
            }
            v19 = pcbLength;
LABEL_29:
            Size = v19;
            Pointer = WX_WIN32_FROM_HR(v18);
            if ( Pointer )
              goto LABEL_33;
            v23 = (unsigned int)(Size + 2);
            Sizea = v23;
            v24 = *(_QWORD *)(*a2 + 24LL * i + 8);
            *(_QWORD *)(v24 + 8LL * j) = DhcpAlloc(v23, v21, v22);
            v25 = *(void **)(*(_QWORD *)(*a2 + 24LL * i + 8) + 8LL * j);
            if ( !v25 )
              goto LABEL_32;
            memcpy_0(v25, *(const void **)(*(_QWORD *)(v29 + 24LL * i + 8) + 8LL * j), Sizea);
          }
          v18 = 2147942487LL;
          HIDWORD(pcbLength) = 104;
LABEL_25:
          v19 = 0;
          goto LABEL_29;
        }
      }
LABEL_32:
      Pointer = 8;
    }
  }
LABEL_33:
  if ( (_QWORD)v29 )
  {
    for ( k = 0; k < DWORD2(v29); ++k )
    {
      for ( m = 0; m < *(_DWORD *)(v29 + 24LL * k + 16); ++m )
        DhcpMidlUserFree(*(_QWORD *)(v29 + 24LL * k + 8) + 8LL * m);
      DhcpMidlUserFree(v29 + 8 + 24LL * k);
    }
    DhcpMidlUserFree(&v29);
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 201, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x1800075d0  mov     [rsp+arg_8], rdx
0x1800075d5  mov     [rsp+Size], rcx
0x1800075da  push    rbx
0x1800075db  push    rsi
0x1800075dc  push    rdi
0x1800075dd  push    r12
0x1800075df  push    r13
0x1800075e1  push    r14
0x1800075e3  push    r15
0x1800075e5  sub     rsp, 50h
0x1800075e9  mov     rsi, rdx
0x1800075ec  mov     r12, rcx
0x1800075ef  xorps   xmm0, xmm0
0x1800075f2  movups  [rsp+88h+var_50], xmm0
0x1800075f7  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800075fe  jz      short loc_180007619
0x180007600  mov     edx, 0C6h
0x180007605  mov     ecx, 404h
0x18000760a  mov     r9, r12
0x18000760d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007614  call    WPP_SF_S
0x180007619  xor     edi, edi
0x18000761b  test    r12, r12
0x18000761e  jnz     short loc_18000762A
0x180007620  mov     ebx, 57h ; 'W'
0x180007625  jmp     loc_1800078A4
0x18000762a  test    rsi, rsi
0x18000762d  jz      short loc_180007620
0x18000762f  lea     r14, [rsi+8]
0x180007633  mov     [rsp+88h+arg_18], r14
0x18000763b  cmp     [r14], edi
0x18000763e  jnz     short loc_180007620
0x180007640  cmp     [rsi], rdi
0x180007643  jnz     short loc_180007620
0x180007645  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000764c  jz      short loc_18000766E
0x18000764e  call    cs:__imp_GetCommandLineW
0x180007654  mov     r9, rax
0x180007657  mov     edx, 0C7h
0x18000765c  mov     ecx, 404h
0x180007661  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007668  call    WPP_SF_S
0x18000766d  nop
0x18000766e  mov     [rsp+88h+pcbLength], rdi
0x180007676  lea     rax, [rsp+88h+var_50]
0x18000767b  mov     [rsp+88h+var_60], rax
0x180007680  mov     [rsp+88h+var_68], r12
0x180007685  xor     r9d, r9d
0x180007688  xor     r8d, r8d; pReturnValue
0x18000768b  lea     edx, [r9+1Dh]; nProcNum
0x18000768f  lea     rcx, pProxyInfo; pProxyInfo
0x180007696  call    cs:__imp_NdrClientCall3
0x18000769c  mov     rbx, rax
0x18000769f  mov     [rsp+88h+pcbLength], rax
0x1800076a7  mov     [rsp+88h+var_58], eax
0x1800076ab  jmp     short loc_1800076DF
0x1800076ad  mov     edi, eax
0x1800076af  mov     ebx, eax
0x1800076b1  mov     [rsp+88h+var_58], eax
0x1800076b5  call    cs:__imp_GetCommandLineW
0x1800076bb  mov     rdx, rax
0x1800076be  mov     ecx, ebx
0x1800076c0  call    TraceRpcException
0x1800076c5  xor     edi, edi
0x1800076c7  mov     rsi, [rsp+88h+arg_8]
0x1800076cf  mov     r12, [rsp+88h+Size]
0x1800076d7  mov     r14, [rsp+88h+arg_18]
0x1800076df  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800076e6  jz      short loc_18000770C
0x1800076e8  call    cs:__imp_GetCommandLineW
0x1800076ee  mov     edx, 0C8h
0x1800076f3  mov     ecx, 404h
0x1800076f8  mov     [rsp+88h+var_68], rax
0x1800076fd  mov     r9d, ebx
0x180007700  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007707  call    WPP_SF_DS
0x18000770c  test    ebx, ebx
0x18000770e  jnz     loc_1800078A4
0x180007714  cmp     dword ptr [rsp+88h+var_50+8], edi
0x180007718  jz      loc_1800078A4
0x18000771e  mov     eax, dword ptr [rsp+88h+var_50+8]
0x180007722  lea     rcx, [rax+rax*2]
0x180007726  shl     rcx, 3
0x18000772a  call    DhcpAlloc
0x18000772f  mov     [rsi], rax
0x180007732  test    rax, rax
0x180007735  jz      loc_18000789F
0x18000773b  mov     eax, dword ptr [rsp+88h+var_50+8]
0x18000773f  mov     [r14], eax
0x180007742  mov     r15d, edi
0x180007745  mov     ebx, edi
0x180007747  cmp     r15d, dword ptr [rsp+88h+var_50+8]
0x18000774c  jnb     loc_1800078A4
0x180007752  mov     eax, r15d
0x180007755  lea     r14, [rax+rax*2]
0x180007759  mov     rdx, [rsi]
0x18000775c  mov     rax, qword ptr [rsp+88h+var_50]
0x180007761  movzx   ecx, word ptr [rax+r14*8]
0x180007766  mov     [rdx+r14*8], cx
0x18000776b  mov     rdx, [rsi]
0x18000776e  mov     rax, qword ptr [rsp+88h+var_50]
0x180007773  mov     ecx, [rax+r14*8+10h]
0x180007778  mov     [rdx+r14*8+10h], ecx
0x18000777d  mov     rax, qword ptr [rsp+88h+var_50]
0x180007782  cmp     [rax+r14*8+8], rdi
0x180007787  jnz     short loc_180007796
0x180007789  mov     rax, [rsi]
0x18000778c  mov     [rax+r14*8+8], rdi
0x180007791  inc     r15d
0x180007794  jmp     short loc_180007745
0x180007796  mov     ecx, [rax+r14*8+10h]
0x18000779b  shl     rcx, 3
0x18000779f  call    DhcpAlloc
0x1800077a4  mov     rcx, [rsi]
0x1800077a7  mov     [rcx+r14*8+8], rax
0x1800077ac  mov     rax, [rsi]
0x1800077af  cmp     [rax+r14*8+8], rdi
0x1800077b4  jz      loc_18000789F
0x1800077ba  mov     r13d, edi
0x1800077bd  mov     rax, qword ptr [rsp+88h+var_50]
0x1800077c2  cmp     r13d, [rax+r14*8+10h]
0x1800077c7  jnb     short loc_180007791
0x1800077c9  mov     ecx, r13d
0x1800077cc  mov     rax, [rax+r14*8+8]
0x1800077d1  mov     rcx, [rax+rcx*8]; psz
0x1800077d5  mov     dword ptr [rsp+88h+pcbLength+4], edi
0x1800077dc  mov     [rsp+88h+pcbLength], rdi
0x1800077e4  mov     dword ptr [rsp+88h+Size], edi
0x1800077eb  test    rcx, rcx
0x1800077ee  jnz     short loc_180007809
0x1800077f0  mov     ecx, 80070057h
0x1800077f5  mov     dword ptr [rsp+88h+pcbLength+4], 68h ; 'h'
0x180007800  mov     eax, dword ptr [rsp+88h+Size]
0x180007807  jmp     short loc_180007831
0x180007809  lea     r8, [rsp+88h+pcbLength]; pcbLength
0x180007811  call    StringCbLengthW
0x180007816  mov     ecx, eax
0x180007818  test    eax, eax
0x18000781a  jns     short loc_180007829
0x18000781c  mov     dword ptr [rsp+88h+pcbLength+4], 6Ch ; 'l'
0x180007827  jmp     short loc_180007800
0x180007829  mov     rax, [rsp+88h+pcbLength]
0x180007831  mov     [rsp+88h+Size], rax
0x180007839  call    WX_WIN32_FROM_HR
0x18000783e  mov     ebx, eax
0x180007840  test    eax, eax
0x180007842  jnz     short loc_1800078A4
0x180007844  mov     rcx, [rsp+88h+Size]
0x18000784c  add     ecx, 2
0x18000784f  mov     [rsp+88h+Size], rcx
0x180007857  mov     rax, [rsi]
0x18000785a  mov     rbx, [rax+r14*8+8]
0x18000785f  call    DhcpAlloc
0x180007864  mov     r9d, r13d
0x180007867  mov     [rbx+r9*8], rax
0x18000786b  mov     rax, [rsi]
0x18000786e  mov     rcx, [rax+r14*8+8]
0x180007873  mov     rcx, [rcx+r9*8]; void *
0x180007877  test    rcx, rcx
0x18000787a  jz      short loc_18000789F
0x18000787c  mov     rax, qword ptr [rsp+88h+var_50]
0x180007881  mov     rdx, [rax+r14*8+8]
0x180007886  mov     r8, [rsp+88h+Size]; Size
0x18000788e  mov     rdx, [rdx+r9*8]; Src
0x180007892  call    memcpy_0
0x180007897  inc     r13d
0x18000789a  jmp     loc_1800077BD
0x18000789f  mov     ebx, 8
0x1800078a4  cmp     qword ptr [rsp+88h+var_50], rdi
0x1800078a9  jz      short loc_180007911
0x1800078ab  mov     esi, edi
0x1800078ad  cmp     dword ptr [rsp+88h+var_50+8], edi
0x1800078b1  jbe     short loc_180007907
0x1800078b3  mov     r15d, edi
0x1800078b6  mov     eax, esi
0x1800078b8  lea     r14, [rax+rax*2]
0x1800078bc  mov     rax, qword ptr [rsp+88h+var_50]
0x1800078c1  cmp     [rax+r14*8+10h], edi
0x1800078c6  jbe     short loc_1800078ED
0x1800078c8  mov     edx, r15d
0x1800078cb  mov     rax, qword ptr [rsp+88h+var_50]
0x1800078d0  mov     rcx, [rax+r14*8+8]
0x1800078d5  lea     rcx, [rcx+rdx*8]
0x1800078d9  call    DhcpMidlUserFree
0x1800078de  inc     r15d
0x1800078e1  mov     rax, qword ptr [rsp+88h+var_50]
0x1800078e6  cmp     r15d, [rax+r14*8+10h]
0x1800078eb  jb      short loc_1800078C8
0x1800078ed  mov     rcx, qword ptr [rsp+88h+var_50]
0x1800078f2  add     rcx, 8
0x1800078f6  lea     rcx, [rcx+r14*8]
0x1800078fa  call    DhcpMidlUserFree
0x1800078ff  inc     esi
0x180007901  cmp     esi, dword ptr [rsp+88h+var_50+8]
0x180007905  jb      short loc_1800078B3
0x180007907  lea     rcx, [rsp+88h+var_50]
0x18000790c  call    DhcpMidlUserFree
0x180007911  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007918  jz      short loc_180007937
0x18000791a  mov     edx, 0C9h
0x18000791f  mov     ecx, 404h
0x180007924  mov     dword ptr [rsp+88h+var_68], ebx
0x180007928  mov     r9, r12
0x18000792b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007932  call    WPP_SF_SD
0x180007937  mov     eax, ebx
0x180007939  add     rsp, 50h
0x18000793d  pop     r15
0x18000793f  pop     r14
0x180007941  pop     r13
0x180007943  pop     r12
0x180007945  pop     rdi
0x180007946  pop     rsi
0x180007947  pop     rbx
0x180007948  retn
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
