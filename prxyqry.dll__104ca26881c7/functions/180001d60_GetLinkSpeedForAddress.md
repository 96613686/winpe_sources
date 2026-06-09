# GetLinkSpeedForAddress

- ea: `0x180001d60`
- end: `0x18000211b`
- name: `GetLinkSpeedForAddress`
- size: `955`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001d60`
- `0x180002dd4`
- `0x180002e04`
- `0x180002eec`
- `0x180003041`
- `0x180003060`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001e6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ecb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001e6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ecb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ea0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001eb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800020a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ea0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001eb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800020a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001eae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800020af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001eae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800020af`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180001e8a`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180001f7a`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180001e8a`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180001f7a`
- `IPHLPAPI!GetIfEntry2` at `0x180002050`
- `IPHLPAPI!GetIfEntry2` at `0x180002050`
- `WS2_32!__imp_WSAStartup` at `0x180001de7`
- `WS2_32!__imp_WSAStartup` at `0x180001de7`
- `WS2_32!__imp_WSACleanup` at `0x1800020e9`
- `WS2_32!__imp_WSACleanup` at `0x1800020e9`

## pseudocode

```c
__int64 __fastcall GetLinkSpeedForAddress(unsigned __int16 *a1, ULONG64 *a2, ULONG64 *a3)
{
  unsigned int v6; // eax
  __int64 v7; // r8
  unsigned int v8; // edi
  ULONG v9; // r12d
  HANDLE ProcessHeap; // rax
  IP_ADAPTER_ADDRESSES_LH *v11; // rsi
  ULONG AdaptersAddresses; // eax
  __int64 v13; // r8
  HANDLE v14; // rax
  unsigned int v15; // ebx
  HANDLE v16; // rax
  __int64 v17; // r8
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  IP_ADAPTER_ADDRESSES_LH *v20; // r14
  PIP_ADAPTER_UNICAST_ADDRESS_LH i; // rcx
  LPSOCKADDR lpSockaddr; // rdx
  bool v23; // zf
  unsigned int IfEntry2; // eax
  __int64 v25; // r8
  ULONG64 *v26; // rcx
  HANDLE v27; // rax
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  ULONG64 *v30; // [rsp+38h] [rbp-C8h]
  WSAData WSAData; // [rsp+40h] [rbp-C0h] BYREF
  _MIB_IF_ROW2 Row; // [rsp+1E0h] [rbp+E0h] BYREF

  LODWORD(dwBytes) = 15360;
  v30 = a3;
  memset_0(&Row, 0, sizeof(Row));
  memset_0(&WSAData, 0, sizeof(WSAData));
  *a2 = 0;
  *a3 = 0;
  v6 = WSAStartup(2u, &WSAData);
  v8 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v7, v6, v6);
    }
    return v8;
  }
  if ( WSAData.wVersion != 2 )
  {
    v8 = 10092;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42);
    }
    goto LABEL_53;
  }
  v9 = *a1;
  ProcessHeap = GetProcessHeap();
  v11 = (IP_ADAPTER_ADDRESSES_LH *)HeapAlloc(ProcessHeap, 8u, (unsigned int)dwBytes);
  AdaptersAddresses = GetAdaptersAddresses(v9, 0xEu, 0, v11, (PULONG)&dwBytes);
  v8 = AdaptersAddresses;
  if ( AdaptersAddresses == 111 )
  {
    if ( v11 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v11);
    }
    v15 = dwBytes;
    v16 = GetProcessHeap();
    v8 = 8;
    v11 = (IP_ADAPTER_ADDRESSES_LH *)HeapAlloc(v16, 8u, v15);
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v17, (unsigned int)dwBytes);
      }
      return v8;
    }
  }
  else if ( AdaptersAddresses )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return v8;
    }
    v19 = 44;
LABEL_20:
    WPP_SF_d(v18[2], v19, v13, AdaptersAddresses);
    return v8;
  }
  AdaptersAddresses = GetAdaptersAddresses(v9, 0xEu, 0, v11, (PULONG)&dwBytes);
  v8 = AdaptersAddresses;
  if ( AdaptersAddresses )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return v8;
    }
    v19 = 45;
    goto LABEL_20;
  }
  if ( !v11 )
    goto LABEL_53;
  v20 = v11;
  while ( 2 )
  {
    for ( i = v20->FirstUnicastAddress; i; i = i->Next )
    {
      lpSockaddr = i->Address.lpSockaddr;
      if ( (_WORD)v9 == 2 )
      {
        v23 = *(_DWORD *)&lpSockaddr->sa_data[2] == *((_DWORD *)a1 + 1);
      }
      else
      {
        if ( *(_QWORD *)&lpSockaddr->sa_data[6] != *((_QWORD *)a1 + 1) )
          continue;
        v23 = *(_QWORD *)&lpSockaddr[1].sa_family == *((_QWORD *)a1 + 2);
      }
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, 2, v11->IfIndex);
        }
        Row.InterfaceIndex = v20->IfIndex;
        IfEntry2 = GetIfEntry2(&Row);
        v8 = IfEntry2;
        if ( IfEntry2 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, v25, IfEntry2);
          }
        }
        else
        {
          v26 = v30;
          *a2 = Row.TransmitLinkSpeed;
          *v26 = Row.ReceiveLinkSpeed;
        }
        goto LABEL_48;
      }
    }
    v20 = v20->Next;
    if ( v20 )
      continue;
    break;
  }
LABEL_48:
  v27 = GetProcessHeap();
  HeapFree(v27, 0, v11);
LABEL_53:
  WSACleanup();
  return v8;
}

```

## disassembly

```asm
0x180001d60  mov     [rsp-8+arg_18], rbx
0x180001d65  push    rbp
0x180001d66  push    rsi
0x180001d67  push    rdi
0x180001d68  push    r12
0x180001d6a  push    r13
0x180001d6c  push    r14
0x180001d6e  push    r15
0x180001d70  lea     rbp, [rsp-640h]
0x180001d78  sub     rsp, 740h
0x180001d7f  mov     rax, cs:__security_cookie
0x180001d86  xor     rax, rsp
0x180001d89  mov     [rbp+670h+var_40], rax
0x180001d90  mov     rbx, r8
0x180001d93  mov     dword ptr [rsp+770h+dwBytes], 3C00h
0x180001d9b  mov     r13, rdx
0x180001d9e  mov     [rsp+770h+var_738], rbx
0x180001da3  mov     r15, rcx
0x180001da6  xor     edx, edx; Val
0x180001da8  mov     r8d, 548h; Size
0x180001dae  lea     rcx, [rbp+670h+Row]; void *
0x180001db5  call    memset_0
0x180001dba  xor     edx, edx; Val
0x180001dbc  lea     rcx, [rsp+770h+WSAData]; void *
0x180001dc1  mov     r8d, 198h; Size
0x180001dc7  call    memset_0
0x180001dcc  mov     qword ptr [r13+0], 0
0x180001dd4  lea     rdx, [rsp+770h+WSAData]; lpWSAData
0x180001dd9  mov     qword ptr [rbx], 0
0x180001de0  mov     ebx, 2
0x180001de5  mov     ecx, ebx; wVersionRequested
0x180001de7  call    cs:__imp_WSAStartup
0x180001ded  mov     edi, eax
0x180001def  test    eax, eax
0x180001df1  jz      short loc_180001E38
0x180001df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001dfa  lea     rbx, WPP_GLOBAL_Control
0x180001e01  cmp     rcx, rbx
0x180001e04  jz      loc_1800020EF
0x180001e0a  test    byte ptr [rcx+1Ch], 40h
0x180001e0e  jz      loc_1800020EF
0x180001e14  cmp     byte ptr [rcx+19h], 1
0x180001e18  jb      loc_1800020EF
0x180001e1e  mov     rcx, [rcx+10h]
0x180001e22  mov     edx, 29h ; ')'
0x180001e27  mov     r9d, eax
0x180001e2a  mov     dword ptr [rsp+770h+SizePointer], eax
0x180001e2e  call    WPP_SF_dD
0x180001e33  jmp     loc_1800020EF
0x180001e38  movzx   eax, [rsp+770h+WSAData.wVersion]
0x180001e3d  cmp     al, bl
0x180001e3f  jnz     loc_1800020B7
0x180001e45  shr     ax, 8
0x180001e49  test    al, al
0x180001e4b  jnz     loc_1800020B7
0x180001e51  movzx   r12d, word ptr [r15]
0x180001e55  mov     ebx, dword ptr [rsp+770h+dwBytes]
0x180001e59  call    cs:__imp_GetProcessHeap
0x180001e5f  mov     r8d, ebx; dwBytes
0x180001e62  mov     edx, 8; dwFlags
0x180001e67  mov     rcx, rax; hHeap
0x180001e6a  call    cs:__imp_HeapAlloc
0x180001e70  xor     r8d, r8d; Reserved
0x180001e73  mov     ecx, r12d; Family
0x180001e76  mov     rsi, rax
0x180001e79  lea     rax, [rsp+770h+dwBytes]
0x180001e7e  mov     r9, rsi; AdapterAddresses
0x180001e81  mov     [rsp+770h+SizePointer], rax; SizePointer
0x180001e86  lea     edx, [r8+0Eh]; Flags
0x180001e8a  call    cs:__imp_GetAdaptersAddresses
0x180001e90  mov     edi, eax
0x180001e92  cmp     eax, 6Fh ; 'o'
0x180001e95  jnz     loc_180001F1E
0x180001e9b  test    rsi, rsi
0x180001e9e  jz      short loc_180001EB4
0x180001ea0  call    cs:__imp_GetProcessHeap
0x180001ea6  mov     r8, rsi; lpMem
0x180001ea9  xor     edx, edx; dwFlags
0x180001eab  mov     rcx, rax; hHeap
0x180001eae  call    cs:__imp_HeapFree
0x180001eb4  mov     ebx, dword ptr [rsp+770h+dwBytes]
0x180001eb8  call    cs:__imp_GetProcessHeap
0x180001ebe  mov     edi, 8
0x180001ec3  mov     r8d, ebx; dwBytes
0x180001ec6  mov     rcx, rax; hHeap
0x180001ec9  mov     edx, edi; dwFlags
0x180001ecb  call    cs:__imp_HeapAlloc
0x180001ed1  mov     rsi, rax
0x180001ed4  test    rax, rax
0x180001ed7  jnz     loc_180001F63
0x180001edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ee4  lea     rbx, WPP_GLOBAL_Control
0x180001eeb  cmp     rcx, rbx
0x180001eee  jz      loc_1800020EF
0x180001ef4  test    byte ptr [rcx+1Ch], 40h
0x180001ef8  jz      loc_1800020EF
0x180001efe  cmp     byte ptr [rcx+19h], 1
0x180001f02  jb      loc_1800020EF
0x180001f08  mov     r9d, dword ptr [rsp+770h+dwBytes]
0x180001f0d  lea     edx, [rdi+23h]
0x180001f10  mov     rcx, [rcx+10h]
0x180001f14  call    WPP_SF_d
0x180001f19  jmp     loc_1800020EF
0x180001f1e  test    eax, eax
0x180001f20  jz      short loc_180001F63
0x180001f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f29  lea     rbx, WPP_GLOBAL_Control
0x180001f30  cmp     rcx, rbx
0x180001f33  jz      loc_1800020EF
0x180001f39  test    byte ptr [rcx+1Ch], 40h
0x180001f3d  jz      loc_1800020EF
0x180001f43  cmp     byte ptr [rcx+19h], 1
0x180001f47  jb      loc_1800020EF
0x180001f4d  mov     edx, 2Ch ; ','
0x180001f52  mov     rcx, [rcx+10h]
0x180001f56  mov     r9d, eax
0x180001f59  call    WPP_SF_d
0x180001f5e  jmp     loc_1800020EF
0x180001f63  xor     r8d, r8d; Reserved
0x180001f66  lea     rax, [rsp+770h+dwBytes]
0x180001f6b  mov     r9, rsi; AdapterAddresses
0x180001f6e  mov     [rsp+770h+SizePointer], rax; SizePointer
0x180001f73  mov     ecx, r12d; Family
0x180001f76  lea     edx, [r8+0Eh]; Flags
0x180001f7a  call    cs:__imp_GetAdaptersAddresses
0x180001f80  mov     edi, eax
0x180001f82  test    eax, eax
0x180001f84  jz      short loc_180001FB8
0x180001f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f8d  lea     rbx, WPP_GLOBAL_Control
0x180001f94  cmp     rcx, rbx
0x180001f97  jz      loc_1800020EF
0x180001f9d  test    byte ptr [rcx+1Ch], 40h
0x180001fa1  jz      loc_1800020EF
0x180001fa7  cmp     byte ptr [rcx+19h], 1
0x180001fab  jb      loc_1800020EF
0x180001fb1  mov     edx, 2Dh ; '-'
0x180001fb6  jmp     short loc_180001F52
0x180001fb8  test    rsi, rsi
0x180001fbb  jz      loc_1800020E9
0x180001fc1  mov     r14, rsi
0x180001fc4  mov     r8d, 2
0x180001fca  mov     rcx, [r14+18h]
0x180001fce  jmp     short loc_180001FFB
0x180001fd0  mov     rdx, [rcx+10h]
0x180001fd4  cmp     r12w, r8w
0x180001fd8  jnz     short loc_180001FE3
0x180001fda  mov     eax, [r15+4]
0x180001fde  cmp     [rdx+4], eax
0x180001fe1  jmp     short loc_180001FF5
0x180001fe3  mov     rax, [rdx+8]
0x180001fe7  cmp     rax, [r15+8]
0x180001feb  jnz     short loc_180001FF7
0x180001fed  mov     rax, [rdx+10h]
0x180001ff1  cmp     rax, [r15+10h]
0x180001ff5  jz      short loc_18000200E
0x180001ff7  mov     rcx, [rcx+8]
0x180001ffb  test    rcx, rcx
0x180001ffe  jnz     short loc_180001FD0
0x180002000  mov     r14, [r14+8]
0x180002004  test    r14, r14
0x180002007  jnz     short loc_180001FCA
0x180002009  jmp     loc_1800020A1
0x18000200e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002015  lea     rbx, WPP_GLOBAL_Control
0x18000201c  cmp     rcx, rbx
0x18000201f  jz      short loc_18000203F
0x180002021  test    byte ptr [rcx+1Ch], 40h
0x180002025  jz      short loc_18000203F
0x180002027  cmp     [rcx+19h], r8b
0x18000202b  jb      short loc_18000203F
0x18000202d  mov     r9d, [rsi+4]
0x180002031  mov     edx, 2Eh ; '.'
0x180002036  mov     rcx, [rcx+10h]
0x18000203a  call    WPP_SF_d
0x18000203f  mov     eax, [r14+4]
0x180002043  lea     rcx, [rbp+670h+Row]; Row
0x18000204a  mov     [rbp+670h+Row.InterfaceIndex], eax
0x180002050  call    cs:__imp_GetIfEntry2
0x180002056  mov     edi, eax
0x180002058  test    eax, eax
0x18000205a  jnz     short loc_180002078
0x18000205c  mov     rax, [rbp+670h+Row.TransmitLinkSpeed]
0x180002063  mov     rcx, [rsp+770h+var_738]
0x180002068  mov     [r13+0], rax
0x18000206c  mov     rax, [rbp+670h+Row.ReceiveLinkSpeed]
0x180002073  mov     [rcx], rax
0x180002076  jmp     short loc_1800020A1
0x180002078  mov     rcx, cs:WPP_GLOBAL_Control
0x18000207f  cmp     rcx, rbx
0x180002082  jz      short loc_1800020A1
0x180002084  test    byte ptr [rcx+1Ch], 40h
0x180002088  jz      short loc_1800020A1
0x18000208a  cmp     byte ptr [rcx+19h], 1
0x18000208e  jb      short loc_1800020A1
0x180002090  mov     rcx, [rcx+10h]
0x180002094  mov     edx, 2Fh ; '/'
0x180002099  mov     r9d, eax
0x18000209c  call    WPP_SF_d
0x1800020a1  call    cs:__imp_GetProcessHeap
0x1800020a7  mov     r8, rsi; lpMem
0x1800020aa  xor     edx, edx; dwFlags
0x1800020ac  mov     rcx, rax; hHeap
0x1800020af  call    cs:__imp_HeapFree
0x1800020b5  jmp     short loc_1800020E9
0x1800020b7  mov     edi, 276Ch
0x1800020bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020c3  lea     rbx, WPP_GLOBAL_Control
0x1800020ca  cmp     rcx, rbx
0x1800020cd  jz      short loc_1800020E9
0x1800020cf  test    byte ptr [rcx+1Ch], 40h
0x1800020d3  jz      short loc_1800020E9
0x1800020d5  cmp     byte ptr [rcx+19h], 1
0x1800020d9  jb      short loc_1800020E9
0x1800020db  mov     rcx, [rcx+10h]
0x1800020df  mov     edx, 2Ah ; '*'
0x1800020e4  call    WPP_SF_
0x1800020e9  call    cs:__imp_WSACleanup
0x1800020ef  mov     eax, edi
0x1800020f1  mov     rcx, [rbp+670h+var_40]
0x1800020f8  xor     rcx, rsp; StackCookie
0x1800020fb  call    __security_check_cookie
0x180002100  mov     rbx, [rsp+770h+arg_18]
0x180002108  add     rsp, 740h
0x18000210f  pop     r15
0x180002111  pop     r14
0x180002113  pop     r13
0x180002115  pop     r12
0x180002117  pop     rdi
0x180002118  pop     rsi
0x180002119  pop     rbp
0x18000211a  retn
```
