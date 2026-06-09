# TeredoCreateSecondarySocket

- ea: `0x18001df50`
- end: `0x18001e1e2`
- name: `TeredoCreateSecondarySocket`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009010`
- `0x18000d7c0`
- `0x18001cab8`
- `0x18001ce10`
- `0x18001df50`
- `0x18001efd0`
- `0x18004b5f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e19f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e19f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1ab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001e086`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001e086`
- `WS2_32!WSASocketW` at `0x18001dfe2`
- `WS2_32!WSASocketW` at `0x18001dfe2`
- `WS2_32!__imp_bind` at `0x18001e05c`
- `WS2_32!__imp_bind` at `0x18001e05c`
- `WS2_32!__imp_htonl` at `0x18001dfa9`
- `WS2_32!__imp_htonl` at `0x18001dfa9`
- `WS2_32!__imp_setsockopt` at `0x18001e02a`
- `WS2_32!__imp_setsockopt` at `0x18001e0ca`
- `WS2_32!__imp_setsockopt` at `0x18001e127`
- `WS2_32!__imp_setsockopt` at `0x18001e02a`
- `WS2_32!__imp_setsockopt` at `0x18001e0ca`
- `WS2_32!__imp_setsockopt` at `0x18001e127`

## string_xrefs

- `0x18001e17c`: `Created Secondary Socket.`

## pseudocode

```c
DWORD __fastcall TeredoCreateSecondarySocket(__int64 *a1)
{
  __int64 v1; // rbx
  struct sockaddr *v3; // rax
  SOCKET v4; // rax
  PTP_IO ThreadpoolIo; // rax
  SOCKET v7; // rcx
  DWORD LastError; // eax
  SOCKET v9; // rcx
  DWORD v10; // eax
  unsigned int i; // ebx
  DWORD v12; // ebx
  char optval[4]; // [rsp+30h] [rbp-30h] BYREF
  char v14[4]; // [rsp+34h] [rbp-2Ch] BYREF
  char v15[8]; // [rsp+38h] [rbp-28h] BYREF
  struct sockaddr name; // [rsp+40h] [rbp-20h] BYREF

  v1 = *a1;
  name = 0;
  *(_DWORD *)v14 = 0;
  *(_DWORD *)optval = 0;
  *(_QWORD *)v15 = 0;
  v3 = *(struct sockaddr **)(v1 + 2680);
  if ( v3 )
  {
    name = *v3;
    *(_DWORD *)&name.sa_data[2] = htonl(0);
  }
  else
  {
    name = *(struct sockaddr *)(v1 + 2628);
  }
  v4 = WSASocketW(2, 2, 0, 0, 0, 1u);
  a1[3] = v4;
  if ( v4 == -1 )
    return GetLastError();
  *(_DWORD *)optval = 1;
  if ( setsockopt(v4, 0xFFFF, 4, optval, 4) == -1 )
    goto LABEL_23;
  if ( (unsigned int)TeredoEnableRealArrivalIf(a1[3]) )
    goto LABEL_23;
  if ( bind(a1[3], &name, 16) == -1 )
    goto LABEL_23;
  ThreadpoolIo = CreateThreadpoolIo((HANDLE)a1[3], TeredoSecondaryIoComplete, 0, &CallbackEnvironment);
  a1[2] = (__int64)ThreadpoolIo;
  if ( !ThreadpoolIo )
    goto LABEL_23;
  if ( *(_QWORD *)(v1 + 2680) )
  {
    v7 = a1[3];
    *(_DWORD *)v14 = 0;
    if ( setsockopt(v7, 0, 11, v14, 4) == -1 )
    {
      LastError = GetLastError();
      EventWrite0(0x100000, L"IP_MULTICAST_LOOP: %u", LastError);
    }
    *(_DWORD *)v15 = *(_DWORD *)(*(_QWORD *)(v1 + 2680) + 4LL);
    v9 = a1[3];
    *(_DWORD *)&v15[4] = *(_DWORD *)(v1 + 2664);
    if ( setsockopt(v9, 0, 12, v15, 8) == -1 )
    {
      v10 = GetLastError();
      EventWrite0(0x100000, L"IP_ADD_MEMBERSHIP: %u", v10);
    }
  }
  for ( i = 0; i < 5; ++i )
  {
    if ( !(unsigned int)TeredoSecondaryPostReceive((__int64)a1, 0) )
      break;
  }
  if ( !i )
  {
    SetLastError(0x1Eu);
LABEL_23:
    v12 = GetLastError();
    TeredoDestroySecondarySocket(a1);
    return v12;
  }
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_IO,
      L"Created Secondary Socket.");
  return 0;
}

```

## disassembly

```asm
0x18001df50  mov     [rsp-8+arg_8], rbx
0x18001df55  mov     [rsp-8+arg_10], rdi
0x18001df5a  push    rbp
0x18001df5b  mov     rbp, rsp
0x18001df5e  sub     rsp, 60h
0x18001df62  mov     rax, cs:__security_cookie
0x18001df69  xor     rax, rsp
0x18001df6c  mov     [rbp+var_10], rax
0x18001df70  mov     rbx, [rcx]
0x18001df73  xorps   xmm0, xmm0
0x18001df76  movups  xmmword ptr [rbp+name.sa_family], xmm0
0x18001df7a  mov     dword ptr [rbp+var_2C], 0
0x18001df81  mov     rdi, rcx
0x18001df84  mov     dword ptr [rbp+optval], 0
0x18001df8b  mov     qword ptr [rbp+var_28], 0
0x18001df93  mov     rax, [rbx+0A78h]
0x18001df9a  test    rax, rax
0x18001df9d  jz      short loc_18001DFBA
0x18001df9f  movups  xmm0, xmmword ptr [rax]
0x18001dfa2  xor     ecx, ecx; hostlong
0x18001dfa4  movdqu  xmmword ptr [rbp+name.sa_family], xmm0
0x18001dfa9  call    cs:__imp_htonl
0x18001dfb0  nop     dword ptr [rax+rax+00h]
0x18001dfb5  mov     dword ptr [rbp+name.sa_data+2], eax
0x18001dfb8  jmp     short loc_18001DFC6
0x18001dfba  movups  xmm0, xmmword ptr [rbx+0A44h]
0x18001dfc1  movdqu  xmmword ptr [rbp+name.sa_family], xmm0
0x18001dfc6  xor     r9d, r9d; lpProtocolInfo
0x18001dfc9  mov     [rsp+60h+dwFlags], 1; dwFlags
0x18001dfd1  xor     r8d, r8d; protocol
0x18001dfd4  mov     [rsp+60h+g], 0; g
0x18001dfdc  lea     ecx, [r9+2]; af
0x18001dfe0  mov     edx, ecx; type
0x18001dfe2  call    cs:__imp_WSASocketW
0x18001dfe9  nop     dword ptr [rax+rax+00h]
0x18001dfee  mov     [rdi+18h], rax
0x18001dff2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001dff6  jnz     short loc_18001E009
0x18001dff8  call    cs:__imp_GetLastError
0x18001dfff  nop     dword ptr [rax+rax+00h]
0x18001e004  jmp     loc_18001E1C3
0x18001e009  lea     r9, [rbp+optval]; optval
0x18001e00d  mov     dword ptr [rbp+optval], 1
0x18001e014  mov     edx, 0FFFFh; level
0x18001e019  mov     [rsp+60h+g], 4; optlen
0x18001e021  mov     r8d, 4; optname
0x18001e027  mov     rcx, rax; s
0x18001e02a  call    cs:__imp_setsockopt
0x18001e031  nop     dword ptr [rax+rax+00h]
0x18001e036  cmp     eax, 0FFFFFFFFh
0x18001e039  jz      loc_18001E1AB
0x18001e03f  mov     rcx, [rdi+18h]
0x18001e043  call    TeredoEnableRealArrivalIf
0x18001e048  test    eax, eax
0x18001e04a  jnz     loc_18001E1AB
0x18001e050  mov     rcx, [rdi+18h]; s
0x18001e054  lea     r8d, [rax+10h]; namelen
0x18001e058  lea     rdx, [rbp+name]; name
0x18001e05c  call    cs:__imp_bind
0x18001e063  nop     dword ptr [rax+rax+00h]
0x18001e068  cmp     eax, 0FFFFFFFFh
0x18001e06b  jz      loc_18001E1AB
0x18001e071  mov     rcx, [rdi+18h]; fl
0x18001e075  lea     r9, CallbackEnvironment; pcbe
0x18001e07c  xor     r8d, r8d; pv
0x18001e07f  lea     rdx, TeredoSecondaryIoComplete; pfnio
0x18001e086  call    cs:__imp_CreateThreadpoolIo
0x18001e08d  nop     dword ptr [rax+rax+00h]
0x18001e092  mov     [rdi+10h], rax
0x18001e096  test    rax, rax
0x18001e099  jz      loc_18001E1AB
0x18001e09f  cmp     qword ptr [rbx+0A78h], 0
0x18001e0a7  jz      loc_18001E158
0x18001e0ad  mov     rcx, [rdi+18h]; s
0x18001e0b1  lea     r9, [rbp+var_2C]; optval
0x18001e0b5  xor     edx, edx; level
0x18001e0b7  mov     dword ptr [rbp+var_2C], 0
0x18001e0be  mov     [rsp+60h+g], 4; optlen
0x18001e0c6  lea     r8d, [rdx+0Bh]; optname
0x18001e0ca  call    cs:__imp_setsockopt
0x18001e0d1  nop     dword ptr [rax+rax+00h]
0x18001e0d6  cmp     eax, 0FFFFFFFFh
0x18001e0d9  jnz     short loc_18001E0FB
0x18001e0db  call    cs:__imp_GetLastError
0x18001e0e2  nop     dword ptr [rax+rax+00h]
0x18001e0e7  lea     rdx, aIpMulticastLoo; "IP_MULTICAST_LOOP: %u"
0x18001e0ee  mov     ecx, 100000h
0x18001e0f3  mov     r8d, eax
0x18001e0f6  call    EventWrite0
0x18001e0fb  mov     rax, [rbx+0A78h]
0x18001e102  lea     r9, [rbp+var_28]; optval
0x18001e106  xor     edx, edx; level
0x18001e108  mov     [rsp+60h+g], 8; optlen
0x18001e110  mov     ecx, [rax+4]
0x18001e113  mov     dword ptr [rbp+var_28], ecx
0x18001e116  lea     r8d, [rdx+0Ch]; optname
0x18001e11a  mov     eax, [rbx+0A68h]
0x18001e120  mov     rcx, [rdi+18h]; s
0x18001e124  mov     dword ptr [rbp+var_28+4], eax
0x18001e127  call    cs:__imp_setsockopt
0x18001e12e  nop     dword ptr [rax+rax+00h]
0x18001e133  cmp     eax, 0FFFFFFFFh
0x18001e136  jnz     short loc_18001E158
0x18001e138  call    cs:__imp_GetLastError
0x18001e13f  nop     dword ptr [rax+rax+00h]
0x18001e144  lea     rdx, aIpAddMembershi; "IP_ADD_MEMBERSHIP: %u"
0x18001e14b  mov     ecx, 100000h
0x18001e150  mov     r8d, eax
0x18001e153  call    EventWrite0
0x18001e158  xor     ebx, ebx
0x18001e15a  xor     edx, edx
0x18001e15c  mov     rcx, rdi
0x18001e15f  call    TeredoSecondaryPostReceive
0x18001e164  test    eax, eax
0x18001e166  jz      short loc_18001E16F
0x18001e168  inc     ebx
0x18001e16a  cmp     ebx, 5
0x18001e16d  jb      short loc_18001E15A
0x18001e16f  test    ebx, ebx
0x18001e171  jz      short loc_18001E19A
0x18001e173  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001e17a  jz      short loc_18001E196
0x18001e17c  lea     r8, aCreatedSeconda; "Created Secondary Socket."
0x18001e183  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18001e18a  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001e191  call    McTemplateU0z_EventWriteTransfer
0x18001e196  xor     eax, eax
0x18001e198  jmp     short loc_18001E1C3
0x18001e19a  mov     ecx, 1Eh; dwErrCode
0x18001e19f  call    cs:__imp_SetLastError
0x18001e1a6  nop     dword ptr [rax+rax+00h]
0x18001e1ab  call    cs:__imp_GetLastError
0x18001e1b2  nop     dword ptr [rax+rax+00h]
0x18001e1b7  mov     rcx, rdi
0x18001e1ba  mov     ebx, eax
0x18001e1bc  call    TeredoDestroySecondarySocket
0x18001e1c1  mov     eax, ebx
0x18001e1c3  mov     rcx, [rbp+var_10]
0x18001e1c7  xor     rcx, rsp; StackCookie
0x18001e1ca  call    __security_check_cookie
0x18001e1cf  lea     r11, [rsp+60h+var_s0]
0x18001e1d4  mov     rbx, [r11+18h]
0x18001e1d8  mov     rdi, [r11+20h]
0x18001e1dc  mov     rsp, r11
0x18001e1df  pop     rbp
0x18001e1e0  retn
```
