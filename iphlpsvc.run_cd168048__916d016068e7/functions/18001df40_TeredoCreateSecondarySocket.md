# TeredoCreateSecondarySocket

- ea: `0x18001df40`
- end: `0x18001e1d2`
- name: `TeredoCreateSecondarySocket`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180009000`
- `0x18000d7b0`
- `0x18001caa8`
- `0x18001ce00`
- `0x18001df40`
- `0x18001efc0`
- `0x18004b630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e18f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e18f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e19b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e19b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001e076`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001e076`
- `WS2_32!WSASocketW` at `0x18001dfd2`
- `WS2_32!WSASocketW` at `0x18001dfd2`
- `WS2_32!__imp_bind` at `0x18001e04c`
- `WS2_32!__imp_bind` at `0x18001e04c`
- `WS2_32!__imp_htonl` at `0x18001df99`
- `WS2_32!__imp_htonl` at `0x18001df99`
- `WS2_32!__imp_setsockopt` at `0x18001e01a`
- `WS2_32!__imp_setsockopt` at `0x18001e0ba`
- `WS2_32!__imp_setsockopt` at `0x18001e117`
- `WS2_32!__imp_setsockopt` at `0x18001e01a`
- `WS2_32!__imp_setsockopt` at `0x18001e0ba`
- `WS2_32!__imp_setsockopt` at `0x18001e117`

## string_xrefs

- `0x18001e16c`: `Created Secondary Socket.`

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
0x18001df40  mov     [rsp-8+arg_8], rbx
0x18001df45  mov     [rsp-8+arg_10], rdi
0x18001df4a  push    rbp
0x18001df4b  mov     rbp, rsp
0x18001df4e  sub     rsp, 60h
0x18001df52  mov     rax, cs:__security_cookie
0x18001df59  xor     rax, rsp
0x18001df5c  mov     [rbp+var_10], rax
0x18001df60  mov     rbx, [rcx]
0x18001df63  xorps   xmm0, xmm0
0x18001df66  movups  xmmword ptr [rbp+name.sa_family], xmm0
0x18001df6a  mov     dword ptr [rbp+var_2C], 0
0x18001df71  mov     rdi, rcx
0x18001df74  mov     dword ptr [rbp+optval], 0
0x18001df7b  mov     qword ptr [rbp+var_28], 0
0x18001df83  mov     rax, [rbx+0A78h]
0x18001df8a  test    rax, rax
0x18001df8d  jz      short loc_18001DFAA
0x18001df8f  movups  xmm0, xmmword ptr [rax]
0x18001df92  xor     ecx, ecx; hostlong
0x18001df94  movdqu  xmmword ptr [rbp+name.sa_family], xmm0
0x18001df99  call    cs:__imp_htonl
0x18001dfa0  nop     dword ptr [rax+rax+00h]
0x18001dfa5  mov     dword ptr [rbp+name.sa_data+2], eax
0x18001dfa8  jmp     short loc_18001DFB6
0x18001dfaa  movups  xmm0, xmmword ptr [rbx+0A44h]
0x18001dfb1  movdqu  xmmword ptr [rbp+name.sa_family], xmm0
0x18001dfb6  xor     r9d, r9d; lpProtocolInfo
0x18001dfb9  mov     [rsp+60h+dwFlags], 1; dwFlags
0x18001dfc1  xor     r8d, r8d; protocol
0x18001dfc4  mov     [rsp+60h+g], 0; g
0x18001dfcc  lea     ecx, [r9+2]; af
0x18001dfd0  mov     edx, ecx; type
0x18001dfd2  call    cs:__imp_WSASocketW
0x18001dfd9  nop     dword ptr [rax+rax+00h]
0x18001dfde  mov     [rdi+18h], rax
0x18001dfe2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001dfe6  jnz     short loc_18001DFF9
0x18001dfe8  call    cs:__imp_GetLastError
0x18001dfef  nop     dword ptr [rax+rax+00h]
0x18001dff4  jmp     loc_18001E1B3
0x18001dff9  lea     r9, [rbp+optval]; optval
0x18001dffd  mov     dword ptr [rbp+optval], 1
0x18001e004  mov     edx, 0FFFFh; level
0x18001e009  mov     [rsp+60h+g], 4; optlen
0x18001e011  mov     r8d, 4; optname
0x18001e017  mov     rcx, rax; s
0x18001e01a  call    cs:__imp_setsockopt
0x18001e021  nop     dword ptr [rax+rax+00h]
0x18001e026  cmp     eax, 0FFFFFFFFh
0x18001e029  jz      loc_18001E19B
0x18001e02f  mov     rcx, [rdi+18h]
0x18001e033  call    TeredoEnableRealArrivalIf
0x18001e038  test    eax, eax
0x18001e03a  jnz     loc_18001E19B
0x18001e040  mov     rcx, [rdi+18h]; s
0x18001e044  lea     r8d, [rax+10h]; namelen
0x18001e048  lea     rdx, [rbp+name]; name
0x18001e04c  call    cs:__imp_bind
0x18001e053  nop     dword ptr [rax+rax+00h]
0x18001e058  cmp     eax, 0FFFFFFFFh
0x18001e05b  jz      loc_18001E19B
0x18001e061  mov     rcx, [rdi+18h]; fl
0x18001e065  lea     r9, CallbackEnvironment; pcbe
0x18001e06c  xor     r8d, r8d; pv
0x18001e06f  lea     rdx, TeredoSecondaryIoComplete; pfnio
0x18001e076  call    cs:__imp_CreateThreadpoolIo
0x18001e07d  nop     dword ptr [rax+rax+00h]
0x18001e082  mov     [rdi+10h], rax
0x18001e086  test    rax, rax
0x18001e089  jz      loc_18001E19B
0x18001e08f  cmp     qword ptr [rbx+0A78h], 0
0x18001e097  jz      loc_18001E148
0x18001e09d  mov     rcx, [rdi+18h]; s
0x18001e0a1  lea     r9, [rbp+var_2C]; optval
0x18001e0a5  xor     edx, edx; level
0x18001e0a7  mov     dword ptr [rbp+var_2C], 0
0x18001e0ae  mov     [rsp+60h+g], 4; optlen
0x18001e0b6  lea     r8d, [rdx+0Bh]; optname
0x18001e0ba  call    cs:__imp_setsockopt
0x18001e0c1  nop     dword ptr [rax+rax+00h]
0x18001e0c6  cmp     eax, 0FFFFFFFFh
0x18001e0c9  jnz     short loc_18001E0EB
0x18001e0cb  call    cs:__imp_GetLastError
0x18001e0d2  nop     dword ptr [rax+rax+00h]
0x18001e0d7  lea     rdx, aIpMulticastLoo; "IP_MULTICAST_LOOP: %u"
0x18001e0de  mov     ecx, 100000h
0x18001e0e3  mov     r8d, eax
0x18001e0e6  call    EventWrite0
0x18001e0eb  mov     rax, [rbx+0A78h]
0x18001e0f2  lea     r9, [rbp+var_28]; optval
0x18001e0f6  xor     edx, edx; level
0x18001e0f8  mov     [rsp+60h+g], 8; optlen
0x18001e100  mov     ecx, [rax+4]
0x18001e103  mov     dword ptr [rbp+var_28], ecx
0x18001e106  lea     r8d, [rdx+0Ch]; optname
0x18001e10a  mov     eax, [rbx+0A68h]
0x18001e110  mov     rcx, [rdi+18h]; s
0x18001e114  mov     dword ptr [rbp+var_28+4], eax
0x18001e117  call    cs:__imp_setsockopt
0x18001e11e  nop     dword ptr [rax+rax+00h]
0x18001e123  cmp     eax, 0FFFFFFFFh
0x18001e126  jnz     short loc_18001E148
0x18001e128  call    cs:__imp_GetLastError
0x18001e12f  nop     dword ptr [rax+rax+00h]
0x18001e134  lea     rdx, aIpAddMembershi; "IP_ADD_MEMBERSHIP: %u"
0x18001e13b  mov     ecx, 100000h
0x18001e140  mov     r8d, eax
0x18001e143  call    EventWrite0
0x18001e148  xor     ebx, ebx
0x18001e14a  xor     edx, edx
0x18001e14c  mov     rcx, rdi
0x18001e14f  call    TeredoSecondaryPostReceive
0x18001e154  test    eax, eax
0x18001e156  jz      short loc_18001E15F
0x18001e158  inc     ebx
0x18001e15a  cmp     ebx, 5
0x18001e15d  jb      short loc_18001E14A
0x18001e15f  test    ebx, ebx
0x18001e161  jz      short loc_18001E18A
0x18001e163  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001e16a  jz      short loc_18001E186
0x18001e16c  lea     r8, aCreatedSeconda; "Created Secondary Socket."
0x18001e173  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18001e17a  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001e181  call    McTemplateU0z_EventWriteTransfer
0x18001e186  xor     eax, eax
0x18001e188  jmp     short loc_18001E1B3
0x18001e18a  mov     ecx, 1Eh; dwErrCode
0x18001e18f  call    cs:__imp_SetLastError
0x18001e196  nop     dword ptr [rax+rax+00h]
0x18001e19b  call    cs:__imp_GetLastError
0x18001e1a2  nop     dword ptr [rax+rax+00h]
0x18001e1a7  mov     rcx, rdi
0x18001e1aa  mov     ebx, eax
0x18001e1ac  call    TeredoDestroySecondarySocket
0x18001e1b1  mov     eax, ebx
0x18001e1b3  mov     rcx, [rbp+var_10]
0x18001e1b7  xor     rcx, rsp; StackCookie
0x18001e1ba  call    __security_check_cookie
0x18001e1bf  lea     r11, [rsp+60h+var_s0]
0x18001e1c4  mov     rbx, [r11+18h]
0x18001e1c8  mov     rdi, [r11+20h]
0x18001e1cc  mov     rsp, r11
0x18001e1cf  pop     rbp
0x18001e1d0  retn
```
