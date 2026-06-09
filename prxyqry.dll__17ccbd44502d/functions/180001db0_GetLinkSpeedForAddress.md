# GetLinkSpeedForAddress

- ea: `0x180001db0`
- end: `0x1800021ba`
- name: `GetLinkSpeedForAddress`
- size: `1034`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001db0`
- `0x180002f68`
- `0x180002fa0`
- `0x180003098`
- `0x180003201`
- `0x180003220`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ec6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001f45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ec6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001f45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001eaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001f2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000212d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001eaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001f2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000212d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002141`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002141`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180001eec`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180001ffa`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180001eec`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180001ffa`
- `IPHLPAPI!GetIfEntry2` at `0x1800020d6`
- `IPHLPAPI!GetIfEntry2` at `0x1800020d6`
- `WS2_32!__imp_WSAStartup` at `0x180001e37`
- `WS2_32!__imp_WSAStartup` at `0x180001e37`
- `WS2_32!__imp_WSACleanup` at `0x180002181`
- `WS2_32!__imp_WSACleanup` at `0x180002181`

## pseudocode

```c
__int64 __fastcall GetLinkSpeedForAddress(unsigned __int16 *a1, ULONG64 *a2, ULONG64 *a3)
{
  unsigned int v6; // eax
  __int64 v7; // r8
  ULONG IfEntry2; // edi
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
  __int64 v24; // r8
  ULONG64 *v25; // rcx
  HANDLE v26; // rax
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  ULONG64 *v29; // [rsp+38h] [rbp-C8h]
  WSAData WSAData; // [rsp+40h] [rbp-C0h] BYREF
  _MIB_IF_ROW2 Row; // [rsp+1E0h] [rbp+E0h] BYREF

  LODWORD(dwBytes) = 15360;
  v29 = a3;
  memset_0(&Row, 0, sizeof(Row));
  memset_0(&WSAData, 0, sizeof(WSAData));
  *a2 = 0;
  *a3 = 0;
  v6 = WSAStartup(2u, &WSAData);
  IfEntry2 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v7, v6, v6);
    }
    return IfEntry2;
  }
  if ( WSAData.wVersion != 2 )
  {
    IfEntry2 = 10092;
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
  IfEntry2 = AdaptersAddresses;
  if ( AdaptersAddresses == 111 )
  {
    if ( v11 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v11);
    }
    v15 = dwBytes;
    v16 = GetProcessHeap();
    IfEntry2 = 8;
    v11 = (IP_ADAPTER_ADDRESSES_LH *)HeapAlloc(v16, 8u, v15);
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v17);
      }
      return IfEntry2;
    }
  }
  else if ( AdaptersAddresses )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return IfEntry2;
    }
    v19 = 44;
LABEL_20:
    WPP_SF_d(v18[2], v19, v13);
    return IfEntry2;
  }
  IfEntry2 = GetAdaptersAddresses(v9, 0xEu, 0, v11, (PULONG)&dwBytes);
  if ( IfEntry2 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return IfEntry2;
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, 2);
        }
        Row.InterfaceIndex = v20->IfIndex;
        IfEntry2 = GetIfEntry2(&Row);
        if ( IfEntry2 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, v24);
          }
        }
        else
        {
          v25 = v29;
          *a2 = Row.TransmitLinkSpeed;
          *v25 = Row.ReceiveLinkSpeed;
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
  v26 = GetProcessHeap();
  HeapFree(v26, 0, v11);
LABEL_53:
  WSACleanup();
  return IfEntry2;
}

```

## disassembly

```asm
0x180001db0  mov     [rsp-8+arg_18], rbx
0x180001db5  push    rbp
0x180001db6  push    rsi
0x180001db7  push    rdi
0x180001db8  push    r12
0x180001dba  push    r13
0x180001dbc  push    r14
0x180001dbe  push    r15
0x180001dc0  lea     rbp, [rsp-640h]
0x180001dc8  sub     rsp, 740h
0x180001dcf  mov     rax, cs:__security_cookie
0x180001dd6  xor     rax, rsp
0x180001dd9  mov     [rbp+670h+var_40], rax
0x180001de0  mov     rbx, r8
0x180001de3  mov     dword ptr [rsp+770h+dwBytes], 3C00h
0x180001deb  mov     r13, rdx
0x180001dee  mov     [rsp+770h+var_738], rbx
0x180001df3  mov     r15, rcx
0x180001df6  xor     edx, edx; Val
0x180001df8  mov     r8d, 548h; Size
0x180001dfe  lea     rcx, [rbp+670h+Row]; void *
0x180001e05  call    memset_0
0x180001e0a  xor     edx, edx; Val
0x180001e0c  lea     rcx, [rsp+770h+WSAData]; void *
0x180001e11  mov     r8d, 198h; Size
0x180001e17  call    memset_0
0x180001e1c  mov     qword ptr [r13+0], 0
0x180001e24  lea     rdx, [rsp+770h+WSAData]; lpWSAData
0x180001e29  mov     qword ptr [rbx], 0
0x180001e30  mov     ebx, 2
0x180001e35  mov     ecx, ebx; wVersionRequested
0x180001e37  call    cs:__imp_WSAStartup
0x180001e3e  nop     dword ptr [rax+rax+00h]
0x180001e43  mov     edi, eax
0x180001e45  test    eax, eax
0x180001e47  jz      short loc_180001E8E
0x180001e49  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e50  lea     rbx, WPP_GLOBAL_Control
0x180001e57  cmp     rcx, rbx
0x180001e5a  jz      loc_18000218D
0x180001e60  test    byte ptr [rcx+1Ch], 40h
0x180001e64  jz      loc_18000218D
0x180001e6a  cmp     byte ptr [rcx+19h], 1
0x180001e6e  jb      loc_18000218D
0x180001e74  mov     rcx, [rcx+10h]
0x180001e78  mov     edx, 29h ; ')'
0x180001e7d  mov     r9d, eax
0x180001e80  mov     dword ptr [rsp+770h+SizePointer], eax
0x180001e84  call    WPP_SF_dD
0x180001e89  jmp     loc_18000218D
0x180001e8e  movzx   eax, [rsp+770h+WSAData.wVersion]
0x180001e93  cmp     al, bl
0x180001e95  jnz     loc_18000214F
0x180001e9b  shr     ax, 8
0x180001e9f  test    al, al
0x180001ea1  jnz     loc_18000214F
0x180001ea7  movzx   r12d, word ptr [r15]
0x180001eab  mov     ebx, dword ptr [rsp+770h+dwBytes]
0x180001eaf  call    cs:__imp_GetProcessHeap
0x180001eb6  nop     dword ptr [rax+rax+00h]
0x180001ebb  mov     r8d, ebx; dwBytes
0x180001ebe  mov     edx, 8; dwFlags
0x180001ec3  mov     rcx, rax; hHeap
0x180001ec6  call    cs:__imp_HeapAlloc
0x180001ecd  nop     dword ptr [rax+rax+00h]
0x180001ed2  xor     r8d, r8d; Reserved
0x180001ed5  mov     ecx, r12d; Family
0x180001ed8  mov     rsi, rax
0x180001edb  lea     rax, [rsp+770h+dwBytes]
0x180001ee0  mov     r9, rsi; AdapterAddresses
0x180001ee3  mov     [rsp+770h+SizePointer], rax; SizePointer
0x180001ee8  lea     edx, [r8+0Eh]; Flags
0x180001eec  call    cs:__imp_GetAdaptersAddresses
0x180001ef3  nop     dword ptr [rax+rax+00h]
0x180001ef8  mov     edi, eax
0x180001efa  cmp     eax, 6Fh ; 'o'
0x180001efd  jnz     loc_180001F9E
0x180001f03  test    rsi, rsi
0x180001f06  jz      short loc_180001F28
0x180001f08  call    cs:__imp_GetProcessHeap
0x180001f0f  nop     dword ptr [rax+rax+00h]
0x180001f14  mov     r8, rsi; lpMem
0x180001f17  xor     edx, edx; dwFlags
0x180001f19  mov     rcx, rax; hHeap
0x180001f1c  call    cs:__imp_HeapFree
0x180001f23  nop     dword ptr [rax+rax+00h]
0x180001f28  mov     ebx, dword ptr [rsp+770h+dwBytes]
0x180001f2c  call    cs:__imp_GetProcessHeap
0x180001f33  nop     dword ptr [rax+rax+00h]
0x180001f38  mov     edi, 8
0x180001f3d  mov     r8d, ebx; dwBytes
0x180001f40  mov     rcx, rax; hHeap
0x180001f43  mov     edx, edi; dwFlags
0x180001f45  call    cs:__imp_HeapAlloc
0x180001f4c  nop     dword ptr [rax+rax+00h]
0x180001f51  mov     rsi, rax
0x180001f54  test    rax, rax
0x180001f57  jnz     loc_180001FE3
0x180001f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f64  lea     rbx, WPP_GLOBAL_Control
0x180001f6b  cmp     rcx, rbx
0x180001f6e  jz      loc_18000218D
0x180001f74  test    byte ptr [rcx+1Ch], 40h
0x180001f78  jz      loc_18000218D
0x180001f7e  cmp     byte ptr [rcx+19h], 1
0x180001f82  jb      loc_18000218D
0x180001f88  mov     r9d, dword ptr [rsp+770h+dwBytes]
0x180001f8d  lea     edx, [rdi+23h]
0x180001f90  mov     rcx, [rcx+10h]
0x180001f94  call    WPP_SF_d
0x180001f99  jmp     loc_18000218D
0x180001f9e  test    eax, eax
0x180001fa0  jz      short loc_180001FE3
0x180001fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fa9  lea     rbx, WPP_GLOBAL_Control
0x180001fb0  cmp     rcx, rbx
0x180001fb3  jz      loc_18000218D
0x180001fb9  test    byte ptr [rcx+1Ch], 40h
0x180001fbd  jz      loc_18000218D
0x180001fc3  cmp     byte ptr [rcx+19h], 1
0x180001fc7  jb      loc_18000218D
0x180001fcd  mov     edx, 2Ch ; ','
0x180001fd2  mov     rcx, [rcx+10h]
0x180001fd6  mov     r9d, eax
0x180001fd9  call    WPP_SF_d
0x180001fde  jmp     loc_18000218D
0x180001fe3  xor     r8d, r8d; Reserved
0x180001fe6  lea     rax, [rsp+770h+dwBytes]
0x180001feb  mov     r9, rsi; AdapterAddresses
0x180001fee  mov     [rsp+770h+SizePointer], rax; SizePointer
0x180001ff3  mov     ecx, r12d; Family
0x180001ff6  lea     edx, [r8+0Eh]; Flags
0x180001ffa  call    cs:__imp_GetAdaptersAddresses
0x180002001  nop     dword ptr [rax+rax+00h]
0x180002006  mov     edi, eax
0x180002008  test    eax, eax
0x18000200a  jz      short loc_18000203E
0x18000200c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002013  lea     rbx, WPP_GLOBAL_Control
0x18000201a  cmp     rcx, rbx
0x18000201d  jz      loc_18000218D
0x180002023  test    byte ptr [rcx+1Ch], 40h
0x180002027  jz      loc_18000218D
0x18000202d  cmp     byte ptr [rcx+19h], 1
0x180002031  jb      loc_18000218D
0x180002037  mov     edx, 2Dh ; '-'
0x18000203c  jmp     short loc_180001FD2
0x18000203e  test    rsi, rsi
0x180002041  jz      loc_180002181
0x180002047  mov     r14, rsi
0x18000204a  mov     r8d, 2
0x180002050  mov     rcx, [r14+18h]
0x180002054  jmp     short loc_180002081
0x180002056  mov     rdx, [rcx+10h]
0x18000205a  cmp     r12w, r8w
0x18000205e  jnz     short loc_180002069
0x180002060  mov     eax, [r15+4]
0x180002064  cmp     [rdx+4], eax
0x180002067  jmp     short loc_18000207B
0x180002069  mov     rax, [rdx+8]
0x18000206d  cmp     rax, [r15+8]
0x180002071  jnz     short loc_18000207D
0x180002073  mov     rax, [rdx+10h]
0x180002077  cmp     rax, [r15+10h]
0x18000207b  jz      short loc_180002094
0x18000207d  mov     rcx, [rcx+8]
0x180002081  test    rcx, rcx
0x180002084  jnz     short loc_180002056
0x180002086  mov     r14, [r14+8]
0x18000208a  test    r14, r14
0x18000208d  jnz     short loc_180002050
0x18000208f  jmp     loc_18000212D
0x180002094  mov     rcx, cs:WPP_GLOBAL_Control
0x18000209b  lea     rbx, WPP_GLOBAL_Control
0x1800020a2  cmp     rcx, rbx
0x1800020a5  jz      short loc_1800020C5
0x1800020a7  test    byte ptr [rcx+1Ch], 40h
0x1800020ab  jz      short loc_1800020C5
0x1800020ad  cmp     [rcx+19h], r8b
0x1800020b1  jb      short loc_1800020C5
0x1800020b3  mov     r9d, [rsi+4]
0x1800020b7  mov     edx, 2Eh ; '.'
0x1800020bc  mov     rcx, [rcx+10h]
0x1800020c0  call    WPP_SF_d
0x1800020c5  mov     eax, [r14+4]
0x1800020c9  lea     rcx, [rbp+670h+Row]; Row
0x1800020d0  mov     [rbp+670h+Row.InterfaceIndex], eax
0x1800020d6  call    cs:__imp_GetIfEntry2
0x1800020dd  nop     dword ptr [rax+rax+00h]
0x1800020e2  mov     edi, eax
0x1800020e4  test    eax, eax
0x1800020e6  jnz     short loc_180002104
0x1800020e8  mov     rax, [rbp+670h+Row.TransmitLinkSpeed]
0x1800020ef  mov     rcx, [rsp+770h+var_738]
0x1800020f4  mov     [r13+0], rax
0x1800020f8  mov     rax, [rbp+670h+Row.ReceiveLinkSpeed]
0x1800020ff  mov     [rcx], rax
0x180002102  jmp     short loc_18000212D
0x180002104  mov     rcx, cs:WPP_GLOBAL_Control
0x18000210b  cmp     rcx, rbx
0x18000210e  jz      short loc_18000212D
0x180002110  test    byte ptr [rcx+1Ch], 40h
0x180002114  jz      short loc_18000212D
0x180002116  cmp     byte ptr [rcx+19h], 1
0x18000211a  jb      short loc_18000212D
0x18000211c  mov     rcx, [rcx+10h]
0x180002120  mov     edx, 2Fh ; '/'
0x180002125  mov     r9d, eax
0x180002128  call    WPP_SF_d
0x18000212d  call    cs:__imp_GetProcessHeap
0x180002134  nop     dword ptr [rax+rax+00h]
0x180002139  mov     r8, rsi; lpMem
0x18000213c  xor     edx, edx; dwFlags
0x18000213e  mov     rcx, rax; hHeap
0x180002141  call    cs:__imp_HeapFree
0x180002148  nop     dword ptr [rax+rax+00h]
0x18000214d  jmp     short loc_180002181
0x18000214f  mov     edi, 276Ch
0x180002154  mov     rcx, cs:WPP_GLOBAL_Control
0x18000215b  lea     rbx, WPP_GLOBAL_Control
0x180002162  cmp     rcx, rbx
0x180002165  jz      short loc_180002181
0x180002167  test    byte ptr [rcx+1Ch], 40h
0x18000216b  jz      short loc_180002181
0x18000216d  cmp     byte ptr [rcx+19h], 1
0x180002171  jb      short loc_180002181
0x180002173  mov     rcx, [rcx+10h]
0x180002177  mov     edx, 2Ah ; '*'
0x18000217c  call    WPP_SF_
0x180002181  call    cs:__imp_WSACleanup
0x180002188  nop     dword ptr [rax+rax+00h]
0x18000218d  mov     eax, edi
0x18000218f  mov     rcx, [rbp+670h+var_40]
0x180002196  xor     rcx, rsp; StackCookie
0x180002199  call    __security_check_cookie
0x18000219e  mov     rbx, [rsp+770h+arg_18]
0x1800021a6  add     rsp, 740h
0x1800021ad  pop     r15
0x1800021af  pop     r14
0x1800021b1  pop     r13
0x1800021b3  pop     r12
0x1800021b5  pop     rdi
0x1800021b6  pop     rsi
0x1800021b7  pop     rbp
0x1800021b8  retn
```
