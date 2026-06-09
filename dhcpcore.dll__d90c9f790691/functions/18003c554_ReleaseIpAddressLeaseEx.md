# ReleaseIpAddressLeaseEx

- ea: `0x18003c554`
- end: `0x18003c9d2`
- name: `ReleaseIpAddressLeaseEx`
- size: `1150`
- prototype: `__int64 __usercall@<rax>(u_long hostlong@<ecx>, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18002b830`
- `0x18002bb00`

## callees

- `0x1800057f0`
- `0x1800077ac`
- `0x18000a738`
- `0x18000f3e0`
- `0x180012b90`
- `0x18001cef0`
- `0x180020e78`
- `0x18003b988`
- `0x18003bf98`
- `0x18003c554`
- `0x180041484`
- `0x180047e3c`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c68c`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c6df`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c732`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c785`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c93b`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c68c`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c6df`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c732`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c785`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18003c93b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c978`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c978`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c695`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c6e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c73b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c78e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c695`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c6e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c73b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c78e`
- `WS2_32!__imp_closesocket` at `0x18003c987`
- `WS2_32!__imp_closesocket` at `0x18003c987`
- `WS2_32!__imp_htonl` at `0x18003c644`
- `WS2_32!__imp_htonl` at `0x18003c650`
- `WS2_32!__imp_htonl` at `0x18003c65c`
- `WS2_32!__imp_htonl` at `0x18003c8b9`
- `WS2_32!__imp_htonl` at `0x18003c644`
- `WS2_32!__imp_htonl` at `0x18003c650`
- `WS2_32!__imp_htonl` at `0x18003c65c`
- `WS2_32!__imp_htonl` at `0x18003c8b9`
- `WS2_32!__imp_inet_addr` at `0x18003c813`
- `WS2_32!__imp_inet_addr` at `0x18003c826`
- `WS2_32!__imp_inet_addr` at `0x18003c813`
- `WS2_32!__imp_inet_addr` at `0x18003c826`

## pseudocode

```c
__int64 __fastcall ReleaseIpAddressLeaseEx(u_long hostlong, u_long *a2, unsigned int *a3, __int64 a4, unsigned int a5)
{
  __int64 result; // rax
  unsigned int v10; // ebx
  _BYTE *v11; // rdi
  __int64 v12; // rbp
  __int64 v13; // rax
  __time64_t v14; // rbx
  ULONGLONG TickCount64; // r8
  __int64 v16; // r8
  __int64 v17; // rbp
  __int64 v18; // rax
  __time64_t v19; // rbx
  ULONGLONG v20; // r8
  __int64 v21; // r8
  __int64 v22; // rbp
  __int64 v23; // rax
  __time64_t v24; // rbx
  ULONGLONG v25; // r8
  __int64 v26; // r8
  __int64 v27; // rbp
  __int64 v28; // rax
  __time64_t v29; // rbx
  ULONGLONG v30; // r8
  __int64 v31; // r8
  int Seed; // eax
  __int64 v33; // rcx
  __int64 v34; // rdx
  unsigned int ClientId; // ebx
  u_long v36; // eax
  unsigned int v37; // eax
  u_long v38; // eax
  SOCKET v39; // rcx
  size_t Size; // [rsp+20h] [rbp-128h] BYREF
  _BYTE *v41; // [rsp+28h] [rbp-120h] BYREF
  _BYTE Src[208]; // [rsp+30h] [rbp-118h] BYREF

  v41 = 0;
  result = DhcpCommonInit();
  if ( !(_DWORD)result )
  {
    if ( a2[6] == -1 )
      return 0;
    if ( !hostlong
      || hostlong == 2130706433
      || (LODWORD(Size) = 200, GetHardwareAddressForIpAddress(hostlong, Src, (unsigned int *)&Size), (v10 = Size) == 0) )
    {
      v10 = *a3;
      if ( *a3 > 0xC8 )
        return 13;
      memcpy_0(Src, (char *)a3 + 5, *a3);
    }
    result = CreateDhcpContext(&v41, v10);
    if ( !(_DWORD)result )
    {
      v11 = v41;
      v41[84] = 1;
      *((_DWORD *)v11 + 24) = v10;
      memcpy_0(*((void **)v11 + 11), Src, v10);
      *((_DWORD *)v11 + 4) = 1;
      *((_DWORD *)v11 + 210) = 0;
      *((_DWORD *)v11 + 30) = htonl(a2[4]);
      *((_DWORD *)v11 + 31) = htonl(a2[5]);
      *((_DWORD *)v11 + 32) = htonl(a2[6]);
      *((_DWORD *)v11 + 33) = *((_DWORD *)v11 + 30);
      *((_DWORD *)v11 + 110) = a2[7];
      v12 = a2[8];
      if ( (_DWORD)v12 == -1 )
      {
        v13 = 0xFFFFFFFFLL;
      }
      else
      {
        v14 = _time64(0);
        TickCount64 = GetTickCount64();
        v13 = 0;
        v16 = v12 + TickCount64 / 0x3E8 - v14;
        if ( v16 >= 0 )
          v13 = v16;
      }
      *((_QWORD *)v11 + 56) = v13;
      v17 = a2[9];
      if ( (_DWORD)v17 == -1 )
      {
        v18 = 0xFFFFFFFFLL;
      }
      else
      {
        v19 = _time64(0);
        v20 = GetTickCount64();
        v18 = 0;
        v21 = v17 + v20 / 0x3E8 - v19;
        if ( v21 >= 0 )
          v18 = v21;
      }
      *((_QWORD *)v11 + 57) = v18;
      v22 = a2[10];
      if ( (_DWORD)v22 == -1 )
      {
        v23 = 0xFFFFFFFFLL;
      }
      else
      {
        v24 = _time64(0);
        v25 = GetTickCount64();
        v23 = 0;
        v26 = v22 + v25 / 0x3E8 - v24;
        if ( v26 >= 0 )
          v23 = v26;
      }
      *((_QWORD *)v11 + 58) = v23;
      v27 = a2[11];
      if ( (_DWORD)v27 == -1 )
      {
        v28 = 0xFFFFFFFFLL;
      }
      else
      {
        v29 = _time64(0);
        v30 = GetTickCount64();
        v28 = 0;
        v31 = v27 + v30 / 0x3E8 - v29;
        if ( v31 >= 0 )
          v28 = v31;
      }
      *((_QWORD *)v11 + 59) = v28;
      *((_DWORD *)v11 + 211) = 1;
      *((_DWORD *)v11 + 212) = 1;
      *((_DWORD *)v11 + 194) = 0;
      *((_DWORD *)v11 + 196) = 0;
      *((_DWORD *)v11 + 197) = 0;
      *((_DWORD *)v11 + 198) = 1;
      *((_DWORD *)v11 + 199) = 0;
      *((_DWORD *)v11 + 200) = 0;
      *((_DWORD *)v11 + 204) = 1;
      *((_DWORD *)v11 + 104) = 0;
      *((_DWORD *)v11 + 105) = inet_addr("169.254.0.0");
      *((_DWORD *)v11 + 106) = inet_addr("255.255.0.0");
      Seed = GetSeed();
      v33 = a5;
      *((_DWORD *)v11 + 107) = Seed;
      *((_QWORD *)v11 + 88) = v11 + 696;
      *((_QWORD *)v11 + 87) = v11 + 696;
      *((_QWORD *)v11 + 86) = v11 + 680;
      *((_QWORD *)v11 + 85) = v11 + 680;
      if ( a5 )
        *((_QWORD *)v11 + 92) = a4 + 4;
      else
        *((_QWORD *)v11 + 92) = 0;
      v34 = *a3;
      *((_DWORD *)v11 + 186) = a5;
      LOBYTE(v33) = 1;
      ClientId = DhcpMakeClientId(v33, v34, (char *)a3 + 5, v11 + 432);
      if ( ClientId
        || (*((_QWORD *)v11 + 7) = 0,
            *((_QWORD *)v11 + 9) = -1,
            *((_QWORD *)v11 + 8) = -1,
            v36 = htonl(hostlong),
            (ClientId = InitializeDhcpSocket(v11 + 72, v36)) != 0) )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_D(1025, 42, WPP_c84194e7b785338e3b207dae288fd792_Traceguids, ClientId);
      }
      else
      {
        v37 = SendDhcpRelease(v11);
        ClientId = v37;
        if ( v37 )
        {
          if ( (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_D(1025, 40, WPP_c84194e7b785338e3b207dae288fd792_Traceguids, v37);
        }
        else if ( (xmmword_1800616A0 & 0x10) != 0 )
        {
          WPP_SF_(1028, 41, WPP_c84194e7b785338e3b207dae288fd792_Traceguids);
        }
        a2[4] = 0;
        a2[5] = DhcpDefaultSubnetMask(0);
        a2[6] = -1;
        a2[7] = 0;
        v38 = _time64(0);
        a2[11] = v38;
        a2[10] = v38;
        a2[9] = v38;
        a2[8] = v38;
      }
      DeleteCriticalSection((LPCRITICAL_SECTION)(v11 + 592));
      v39 = *((_QWORD *)v11 + 9);
      if ( v39 != -1 )
        closesocket(v39);
      if ( *((_QWORD *)v11 + 54) )
        DhcpPunycodeFree((LPVOID *)v11 + 54);
      DhcpPunycodeFree((LPVOID *)&v41);
      return ClientId;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003c554  mov     [rsp+arg_18], rbx
0x18003c559  push    rbp
0x18003c55a  push    rsi
0x18003c55b  push    rdi
0x18003c55c  push    r12
0x18003c55e  push    r13
0x18003c560  push    r14
0x18003c562  push    r15
0x18003c564  sub     rsp, 110h
0x18003c56b  mov     rax, cs:__security_cookie
0x18003c572  xor     rax, rsp
0x18003c575  mov     [rsp+148h+var_48], rax
0x18003c57d  xor     r12d, r12d
0x18003c580  mov     r13, r9
0x18003c583  mov     [rsp+148h+var_120], r12
0x18003c588  mov     r15, r8
0x18003c58b  mov     rsi, rdx
0x18003c58e  mov     r14d, ecx
0x18003c591  call    DhcpCommonInit
0x18003c596  test    eax, eax
0x18003c598  jnz     loc_18003C9A7
0x18003c59e  mov     eax, 0FFFFFFFFh
0x18003c5a3  cmp     [rsi+18h], eax
0x18003c5a6  jnz     short loc_18003C5AF
0x18003c5a8  xor     eax, eax
0x18003c5aa  jmp     loc_18003C9A7
0x18003c5af  mov     edi, 0C8h
0x18003c5b4  test    r14d, r14d
0x18003c5b7  jz      short loc_18003C5E0
0x18003c5b9  cmp     r14d, 7F000001h
0x18003c5c0  jz      short loc_18003C5E0
0x18003c5c2  lea     r8, [rsp+148h+Size]
0x18003c5c7  mov     dword ptr [rsp+148h+Size], edi
0x18003c5cb  lea     rdx, [rsp+148h+Src]
0x18003c5d0  mov     ecx, r14d
0x18003c5d3  call    GetHardwareAddressForIpAddress
0x18003c5d8  mov     ebx, dword ptr [rsp+148h+Size]
0x18003c5dc  test    ebx, ebx
0x18003c5de  jnz     short loc_18003C602
0x18003c5e0  mov     ebx, [r15]
0x18003c5e3  cmp     ebx, edi
0x18003c5e5  jbe     short loc_18003C5F1
0x18003c5e7  mov     eax, 0Dh
0x18003c5ec  jmp     loc_18003C9A7
0x18003c5f1  mov     r8, rbx; Size
0x18003c5f4  lea     rdx, [r15+5]; Src
0x18003c5f8  lea     rcx, [rsp+148h+Src]; void *
0x18003c5fd  call    memcpy_0
0x18003c602  mov     edx, ebx
0x18003c604  lea     rcx, [rsp+148h+var_120]
0x18003c609  call    CreateDhcpContext
0x18003c60e  test    eax, eax
0x18003c610  jnz     loc_18003C9A7
0x18003c616  mov     rdi, [rsp+148h+var_120]
0x18003c61b  lea     rdx, [rsp+148h+Src]; Src
0x18003c620  mov     r8d, ebx; Size
0x18003c623  mov     byte ptr [rdi+54h], 1
0x18003c627  mov     [rdi+60h], ebx
0x18003c62a  mov     rcx, [rdi+58h]; void *
0x18003c62e  call    memcpy_0
0x18003c633  mov     dword ptr [rdi+10h], 1
0x18003c63a  mov     [rdi+348h], r12d
0x18003c641  mov     ecx, [rsi+10h]; hostlong
0x18003c644  call    cs:__imp_htonl
0x18003c64a  mov     [rdi+78h], eax
0x18003c64d  mov     ecx, [rsi+14h]; hostlong
0x18003c650  call    cs:__imp_htonl
0x18003c656  mov     [rdi+7Ch], eax
0x18003c659  mov     ecx, [rsi+18h]; hostlong
0x18003c65c  call    cs:__imp_htonl
0x18003c662  mov     [rdi+80h], eax
0x18003c668  mov     ecx, 0FFFFFFFFh
0x18003c66d  mov     eax, [rdi+78h]
0x18003c670  mov     [rdi+84h], eax
0x18003c676  mov     eax, [rsi+1Ch]
0x18003c679  mov     [rdi+1B8h], eax
0x18003c67f  mov     ebp, [rsi+20h]
0x18003c682  cmp     ebp, ecx
0x18003c684  jnz     short loc_18003C68A
0x18003c686  mov     eax, ecx
0x18003c688  jmp     short loc_18003C6CA
0x18003c68a  xor     ecx, ecx; Time
0x18003c68c  call    cs:__imp__time64
0x18003c692  mov     rbx, rax
0x18003c695  call    cs:__imp_GetTickCount64
0x18003c69b  mov     r8, rax
0x18003c69e  mov     ecx, 0FFFFFFFFh
0x18003c6a3  mov     rax, 624DD2F1A9FBE77h
0x18003c6ad  mul     r8
0x18003c6b0  mov     rax, r12
0x18003c6b3  sub     r8, rdx
0x18003c6b6  shr     r8, 1
0x18003c6b9  add     r8, rdx
0x18003c6bc  shr     r8, 9
0x18003c6c0  add     r8, rbp
0x18003c6c3  sub     r8, rbx
0x18003c6c6  cmovns  rax, r8
0x18003c6ca  mov     [rdi+1C0h], rax
0x18003c6d1  mov     ebp, [rsi+24h]
0x18003c6d4  cmp     ebp, ecx
0x18003c6d6  jnz     short loc_18003C6DD
0x18003c6d8  mov     rax, rcx
0x18003c6db  jmp     short loc_18003C71D
0x18003c6dd  xor     ecx, ecx; Time
0x18003c6df  call    cs:__imp__time64
0x18003c6e5  mov     rbx, rax
0x18003c6e8  call    cs:__imp_GetTickCount64
0x18003c6ee  mov     r8, rax
0x18003c6f1  mov     ecx, 0FFFFFFFFh
0x18003c6f6  mov     rax, 624DD2F1A9FBE77h
0x18003c700  mul     r8
0x18003c703  mov     rax, r12
0x18003c706  sub     r8, rdx
0x18003c709  shr     r8, 1
0x18003c70c  add     r8, rdx
0x18003c70f  shr     r8, 9
0x18003c713  add     r8, rbp
0x18003c716  sub     r8, rbx
0x18003c719  cmovns  rax, r8
0x18003c71d  mov     [rdi+1C8h], rax
0x18003c724  mov     ebp, [rsi+28h]
0x18003c727  cmp     ebp, ecx
0x18003c729  jnz     short loc_18003C730
0x18003c72b  mov     rax, rcx
0x18003c72e  jmp     short loc_18003C770
0x18003c730  xor     ecx, ecx; Time
0x18003c732  call    cs:__imp__time64
0x18003c738  mov     rbx, rax
0x18003c73b  call    cs:__imp_GetTickCount64
0x18003c741  mov     r8, rax
0x18003c744  mov     ecx, 0FFFFFFFFh
0x18003c749  mov     rax, 624DD2F1A9FBE77h
0x18003c753  mul     r8
0x18003c756  mov     rax, r12
0x18003c759  sub     r8, rdx
0x18003c75c  shr     r8, 1
0x18003c75f  add     r8, rdx
0x18003c762  shr     r8, 9
0x18003c766  add     r8, rbp
0x18003c769  sub     r8, rbx
0x18003c76c  cmovns  rax, r8
0x18003c770  mov     [rdi+1D0h], rax
0x18003c777  mov     ebp, [rsi+2Ch]
0x18003c77a  cmp     ebp, ecx
0x18003c77c  jnz     short loc_18003C783
0x18003c77e  mov     rax, rcx
0x18003c781  jmp     short loc_18003C7BE
0x18003c783  xor     ecx, ecx; Time
0x18003c785  call    cs:__imp__time64
0x18003c78b  mov     rbx, rax
0x18003c78e  call    cs:__imp_GetTickCount64
0x18003c794  mov     r8, rax
0x18003c797  mov     rax, 624DD2F1A9FBE77h
0x18003c7a1  mul     r8
0x18003c7a4  mov     rax, r12
0x18003c7a7  sub     r8, rdx
0x18003c7aa  shr     r8, 1
0x18003c7ad  add     r8, rdx
0x18003c7b0  shr     r8, 9
0x18003c7b4  add     r8, rbp
0x18003c7b7  sub     r8, rbx
0x18003c7ba  cmovns  rax, r8
0x18003c7be  mov     [rdi+1D8h], rax
0x18003c7c5  lea     rcx, cp; "169.254.0.0"
0x18003c7cc  mov     ebx, 1
0x18003c7d1  mov     [rdi+34Ch], ebx
0x18003c7d7  mov     [rdi+350h], ebx
0x18003c7dd  mov     [rdi+308h], r12d
0x18003c7e4  mov     [rdi+310h], r12d
0x18003c7eb  mov     [rdi+314h], r12d
0x18003c7f2  mov     [rdi+318h], ebx
0x18003c7f8  mov     [rdi+31Ch], r12d
0x18003c7ff  mov     [rdi+320h], r12d
0x18003c806  mov     [rdi+330h], ebx
0x18003c80c  mov     [rdi+1A0h], r12d
0x18003c813  call    cs:__imp_inet_addr
0x18003c819  lea     rcx, a25525500; "255.255.0.0"
0x18003c820  mov     [rdi+1A4h], eax
0x18003c826  call    cs:__imp_inet_addr
0x18003c82c  mov     [rdi+1A8h], eax
0x18003c832  call    GetSeed
0x18003c837  mov     ecx, [rsp+148h+arg_20]
0x18003c83e  mov     [rdi+1ACh], eax
0x18003c844  lea     rax, [rdi+2B8h]
0x18003c84b  mov     [rax+8], rax
0x18003c84f  mov     [rax], rax
0x18003c852  lea     rax, [rdi+2A8h]
0x18003c859  mov     [rax+8], rax
0x18003c85d  mov     [rax], rax
0x18003c860  test    ecx, ecx
0x18003c862  jnz     short loc_18003C86D
0x18003c864  mov     [rdi+2E0h], r12
0x18003c86b  jmp     short loc_18003C878
0x18003c86d  lea     rax, [r13+4]
0x18003c871  mov     [rdi+2E0h], rax
0x18003c878  mov     edx, [r15]
0x18003c87b  lea     rbp, [rdi+1B0h]
0x18003c882  mov     [rdi+2E8h], ecx
0x18003c888  lea     r8, [r15+5]
0x18003c88c  mov     r9, rbp
0x18003c88f  mov     cl, bl
0x18003c891  call    DhcpMakeClientId
0x18003c896  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003c89a  mov     ebx, eax
0x18003c89c  test    eax, eax
0x18003c89e  jnz     loc_18003C94F
0x18003c8a4  mov     [rdi+38h], r12
0x18003c8a8  mov     ecx, r14d; hostlong
0x18003c8ab  mov     [rdi+48h], r15
0x18003c8af  mov     [rdi+40h], r15
0x18003c8b3  mov     eax, [rdi+330h]
0x18003c8b9  call    cs:__imp_htonl
0x18003c8bf  mov     edx, eax
0x18003c8c1  lea     rcx, [rdi+48h]
0x18003c8c5  call    InitializeDhcpSocket
0x18003c8ca  mov     ebx, eax
0x18003c8cc  test    eax, eax
0x18003c8ce  jnz     short loc_18003C94F
0x18003c8d0  mov     rcx, rdi
0x18003c8d3  call    SendDhcpRelease
0x18003c8d8  mov     ebx, eax
0x18003c8da  test    eax, eax
0x18003c8dc  jz      short loc_18003C901
0x18003c8de  test    byte ptr cs:xmmword_1800616A0, 2
0x18003c8e5  jz      short loc_18003C920
0x18003c8e7  lea     edx, [r15+29h]
0x18003c8eb  mov     ecx, 401h
0x18003c8f0  mov     r9d, eax
0x18003c8f3  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003c8fa  call    WPP_SF_D
0x18003c8ff  jmp     short loc_18003C920
0x18003c901  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003c908  jz      short loc_18003C920
0x18003c90a  mov     edx, 29h ; ')'
0x18003c90f  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003c916  mov     ecx, 404h
0x18003c91b  call    WPP_SF_
0x18003c920  xor     ecx, ecx
0x18003c922  mov     [rsi+10h], r12d
0x18003c926  call    DhcpDefaultSubnetMask
0x18003c92b  xor     ecx, ecx; Time
0x18003c92d  mov     [rsi+14h], eax
0x18003c930  mov     dword ptr [rsi+18h], 0FFFFFFFFh
0x18003c937  mov     [rsi+1Ch], r12d
0x18003c93b  call    cs:__imp__time64
0x18003c941  mov     [rsi+2Ch], eax
0x18003c944  mov     [rsi+28h], eax
0x18003c947  mov     [rsi+24h], eax
0x18003c94a  mov     [rsi+20h], eax
0x18003c94d  jmp     short loc_18003C971
0x18003c94f  test    byte ptr cs:xmmword_1800616A0, 2
0x18003c956  jz      short loc_18003C971
0x18003c958  mov     edx, 2Ah ; '*'
0x18003c95d  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003c964  mov     ecx, 401h
0x18003c969  mov     r9d, ebx
0x18003c96c  call    WPP_SF_D
0x18003c971  lea     rcx, [rdi+250h]; lpCriticalSection
0x18003c978  call    cs:__imp_DeleteCriticalSection
0x18003c97e  mov     rcx, [rdi+48h]; s
0x18003c982  cmp     rcx, r15
0x18003c985  jz      short loc_18003C98D
0x18003c987  call    cs:__imp_closesocket
0x18003c98d  cmp     [rbp+0], r12
0x18003c991  jz      short loc_18003C99B
0x18003c993  mov     rcx, rbp
0x18003c996  call    DhcpPunycodeFree
0x18003c99b  lea     rcx, [rsp+148h+var_120]
0x18003c9a0  call    DhcpPunycodeFree
0x18003c9a5  mov     eax, ebx
0x18003c9a7  mov     rcx, [rsp+148h+var_48]
0x18003c9af  xor     rcx, rsp; StackCookie
0x18003c9b2  call    __security_check_cookie
0x18003c9b7  mov     rbx, [rsp+148h+arg_18]
0x18003c9bf  add     rsp, 110h
0x18003c9c6  pop     r15
0x18003c9c8  pop     r14
0x18003c9ca  pop     r13
0x18003c9cc  pop     r12
0x18003c9ce  pop     rdi
0x18003c9cf  pop     rsi
0x18003c9d0  pop     rbp
0x18003c9d1  retn
```
