# ProcessRecvFromSocket

- ea: `0x1800267b4`
- end: `0x180026a37`
- name: `ProcessRecvFromSocket`
- size: `643`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180026494`

## callees

- `0x18000bc40`
- `0x180026050`
- `0x1800267b4`
- `0x180045f90`
- `0x180047e30`
- `0x18004d1a0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002694c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002694c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800268c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800268c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800267da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180026867`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800267da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180026867`
- `WS2_32!WSASetEvent` at `0x18002693f`
- `WS2_32!WSASetEvent` at `0x18002693f`
- `WS2_32!WSACloseEvent` at `0x1800268f7`
- `WS2_32!WSACloseEvent` at `0x1800268f7`
- `WS2_32!__imp_ntohl` at `0x18002691c`
- `WS2_32!__imp_ntohl` at `0x1800269b5`
- `WS2_32!__imp_ntohl` at `0x1800269ee`
- `WS2_32!__imp_ntohl` at `0x18002691c`
- `WS2_32!__imp_ntohl` at `0x1800269b5`
- `WS2_32!__imp_ntohl` at `0x1800269ee`

## pseudocode

```c
__int64 __fastcall ProcessRecvFromSocket(__int64 *a1)
{
  __int64 v1; // rsi
  unsigned int v3; // edi
  ULONGLONG TickCount64; // rax
  __int64 v5; // rcx
  ULONGLONG v6; // r15
  __int64 v7; // r14
  SOCKET v8; // r12
  unsigned __int64 v9; // rax
  u_long v10; // ebp
  _BYTE *v11; // rcx
  char v12; // al
  __int64 *v13; // rcx
  __int64 **v14; // rax
  HANDLE *v15; // rbx
  u_long v16; // eax
  u_long v18; // eax
  u_long v19; // eax
  u_long netlong; // [rsp+90h] [rbp+8h] BYREF

  v1 = a1[2];
  netlong = 0;
  v3 = 121;
  TickCount64 = GetTickCount64();
  v5 = a1[2];
  v6 = TickCount64;
  v7 = *(_QWORD *)(v5 + 64);
  if ( v7 == -1 )
    v8 = *(_QWORD *)(v5 + 72);
  else
    v8 = *(_QWORD *)(v5 + 64);
  while ( v6 <= a1[6] )
  {
    *(_DWORD *)a1[4] = *((_DWORD *)a1 + 6);
    v9 = a1[6] - v6;
    if ( v9 > 0xFFFFFFFF )
    {
      v3 = 121;
      break;
    }
    v3 = TryReceive(v8, (__int64)&netlong, v9, v7 != -1);
    v6 = GetTickCount64();
    if ( (v7 == -1 || v3 != 13) && v3 != 10054 )
    {
      if ( v3 )
        break;
      v10 = netlong;
      if ( netlong == *((_DWORD *)a1 + 10) )
      {
        v11 = *(_BYTE **)(v1 + 752);
        v12 = v11[1];
        if ( v12 == 24 )
        {
          if ( *(_BYTE *)(v1 + 84) == 24 )
            break;
        }
        else if ( v12 == *(_BYTE *)(v1 + 84)
               && (unsigned __int8)v11[2] == *(_DWORD *)(v1 + 96)
               && !memcmp_0(v11 + 28, *(const void **)(v1 + 88), *(unsigned int *)(v1 + 96)) )
        {
          if ( (xmmword_1800616A0 & 0x10) != 0 )
          {
            v19 = ntohl(v10);
            WPP_SF_d(1028, 48, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v19);
          }
          DhcpLogMessageBytes(*(_QWORD *)(v1 + 752), *(unsigned int *)a1[4]);
          break;
        }
      }
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        v18 = ntohl(v10);
        WPP_SF_d(1028, 49, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v18);
      }
      DispatchPkt(a1, v10);
    }
  }
  if ( v6 > a1[6] )
    v3 = 121;
  EnterCriticalSection(&DhcpGlobalRecvFromCritSect);
  v13 = (__int64 *)*a1;
  if ( *(__int64 **)(*a1 + 8) != a1 || (v14 = (__int64 **)a1[1], *v14 != a1) )
    __fastfail(3u);
  *v14 = v13;
  v13[1] = (__int64)v14;
  a1[1] = (__int64)a1;
  *a1 = (__int64)a1;
  WSACloseEvent((HANDLE)a1[7]);
  v15 = (HANDLE *)DhcpGlobalRecvFromList;
  if ( DhcpGlobalRecvFromList != (_UNKNOWN *)&DhcpGlobalRecvFromList )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      v16 = ntohl(*((_DWORD *)DhcpGlobalRecvFromList + 10));
      WPP_SF_d(1028, 50, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v16);
    }
    WSASetEvent(v15[7]);
  }
  LeaveCriticalSection(&DhcpGlobalRecvFromCritSect);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 51, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800267b4  mov     rax, rsp
0x1800267b7  push    rbx
0x1800267b8  push    rbp
0x1800267b9  push    rsi
0x1800267ba  push    rdi
0x1800267bb  push    r12
0x1800267bd  push    r13
0x1800267bf  push    r14
0x1800267c1  push    r15
0x1800267c3  sub     rsp, 48h
0x1800267c7  mov     rsi, [rcx+10h]
0x1800267cb  mov     rbx, rcx
0x1800267ce  mov     dword ptr [rax+8], 0
0x1800267d5  mov     edi, 79h ; 'y'
0x1800267da  call    cs:__imp_GetTickCount64
0x1800267e0  mov     rcx, [rbx+10h]
0x1800267e4  mov     r15, rax
0x1800267e7  mov     r14, [rcx+40h]
0x1800267eb  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800267ef  jnz     short loc_1800267F7
0x1800267f1  mov     r12, [rcx+48h]
0x1800267f5  jmp     short loc_1800267FA
0x1800267f7  mov     r12, r14
0x1800267fa  xor     r13d, r13d
0x1800267fd  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180026801  setnz   r13b
0x180026805  cmp     r15, [rbx+30h]
0x180026809  ja      loc_1800268B2
0x18002680f  mov     rax, [rbx+10h]
0x180026813  mov     rcx, [rbx+20h]
0x180026817  mov     r8, [rax+2F0h]
0x18002681e  mov     eax, [rbx+18h]
0x180026821  mov     [rcx], eax
0x180026823  mov     ecx, 0FFFFFFFFh
0x180026828  mov     rax, [rbx+30h]
0x18002682c  sub     rax, r15
0x18002682f  cmp     rax, rcx
0x180026832  ja      loc_180026A24
0x180026838  mov     rdx, [rbx+10h]
0x18002683c  mov     rcx, r12; s
0x18002683f  mov     r9, [rbx+20h]
0x180026843  mov     [rsp+88h+var_58], r13d; int
0x180026848  mov     [rsp+88h+var_60], eax; int
0x18002684c  lea     rax, [rsp+88h+netlong]
0x180026854  mov     rdx, [rdx+340h]
0x18002685b  mov     [rsp+88h+var_68], rax; __int64
0x180026860  call    TryReceive
0x180026865  mov     edi, eax
0x180026867  call    cs:__imp_GetTickCount64
0x18002686d  mov     r15, rax
0x180026870  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180026874  jz      short loc_18002687B
0x180026876  cmp     edi, 0Dh
0x180026879  jz      short loc_180026805
0x18002687b  cmp     edi, 2746h
0x180026881  jz      short loc_180026805
0x180026883  test    edi, edi
0x180026885  jnz     short loc_1800268B2
0x180026887  mov     ebp, [rsp+88h+netlong]
0x18002688e  cmp     ebp, [rbx+28h]
0x180026891  jnz     loc_1800269AA
0x180026897  mov     rcx, [rsi+2F0h]
0x18002689e  mov     al, [rcx+1]
0x1800268a1  cmp     al, 18h
0x1800268a3  jnz     loc_180026987
0x1800268a9  cmp     [rsi+54h], al
0x1800268ac  jnz     loc_1800269AA
0x1800268b2  mov     eax, 79h ; 'y'
0x1800268b7  cmp     r15, [rbx+30h]
0x1800268bb  lea     rcx, DhcpGlobalRecvFromCritSect; lpCriticalSection
0x1800268c2  cmova   edi, eax
0x1800268c5  call    cs:__imp_EnterCriticalSection
0x1800268cb  mov     rcx, [rbx]
0x1800268ce  cmp     [rcx+8], rbx
0x1800268d2  jnz     loc_180026A30
0x1800268d8  mov     rax, [rbx+8]
0x1800268dc  cmp     [rax], rbx
0x1800268df  jnz     loc_180026A30
0x1800268e5  mov     [rax], rcx
0x1800268e8  mov     [rcx+8], rax
0x1800268ec  mov     [rbx+8], rbx
0x1800268f0  mov     [rbx], rbx
0x1800268f3  mov     rcx, [rbx+38h]; hEvent
0x1800268f7  call    cs:__imp_WSACloseEvent
0x1800268fd  mov     rbx, cs:DhcpGlobalRecvFromList
0x180026904  lea     rax, DhcpGlobalRecvFromList
0x18002690b  cmp     rbx, rax
0x18002690e  jz      short loc_180026945
0x180026910  test    byte ptr cs:xmmword_1800616A0, 10h
0x180026917  jz      short loc_18002693B
0x180026919  mov     ecx, [rbx+28h]; netlong
0x18002691c  call    cs:__imp_ntohl
0x180026922  mov     edx, 32h ; '2'
0x180026927  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18002692e  mov     r9d, eax
0x180026931  mov     ecx, 404h
0x180026936  call    WPP_SF_d
0x18002693b  mov     rcx, [rbx+38h]; hEvent
0x18002693f  call    cs:__imp_WSASetEvent
0x180026945  lea     rcx, DhcpGlobalRecvFromCritSect; lpCriticalSection
0x18002694c  call    cs:__imp_LeaveCriticalSection
0x180026952  test    byte ptr cs:xmmword_1800616A0, 10h
0x180026959  jz      short loc_180026974
0x18002695b  mov     edx, 33h ; '3'
0x180026960  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x180026967  mov     ecx, 404h
0x18002696c  mov     r9d, edi
0x18002696f  call    WPP_SF_D
0x180026974  mov     eax, edi
0x180026976  add     rsp, 48h
0x18002697a  pop     r15
0x18002697c  pop     r14
0x18002697e  pop     r13
0x180026980  pop     r12
0x180026982  pop     rdi
0x180026983  pop     rsi
0x180026984  pop     rbp
0x180026985  pop     rbx
0x180026986  retn
0x180026987  cmp     al, [rsi+54h]
0x18002698a  jnz     short loc_1800269AA
0x18002698c  movzx   eax, byte ptr [rcx+2]
0x180026990  cmp     eax, [rsi+60h]
0x180026993  jnz     short loc_1800269AA
0x180026995  mov     r8d, [rsi+60h]; Size
0x180026999  add     rcx, 1Ch; Buf1
0x18002699d  mov     rdx, [rsi+58h]; Buf2
0x1800269a1  call    memcmp_0
0x1800269a6  test    eax, eax
0x1800269a8  jz      short loc_1800269E3
0x1800269aa  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800269b1  jz      short loc_1800269D4
0x1800269b3  mov     ecx, ebp; netlong
0x1800269b5  call    cs:__imp_ntohl
0x1800269bb  mov     edx, 31h ; '1'
0x1800269c0  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x1800269c7  mov     r9d, eax
0x1800269ca  mov     ecx, 404h
0x1800269cf  call    WPP_SF_d
0x1800269d4  mov     edx, ebp
0x1800269d6  mov     rcx, rbx
0x1800269d9  call    DispatchPkt
0x1800269de  jmp     loc_180026805
0x1800269e3  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800269ea  jz      short loc_180026A0D
0x1800269ec  mov     ecx, ebp; netlong
0x1800269ee  call    cs:__imp_ntohl
0x1800269f4  mov     edx, 30h ; '0'
0x1800269f9  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x180026a00  mov     r9d, eax
0x180026a03  mov     ecx, 404h
0x180026a08  call    WPP_SF_d
0x180026a0d  mov     rdx, [rbx+20h]
0x180026a11  mov     rcx, [rsi+2F0h]
0x180026a18  mov     edx, [rdx]
0x180026a1a  call    DhcpLogMessageBytes
0x180026a1f  jmp     loc_1800268B2
0x180026a24  mov     eax, 79h ; 'y'
0x180026a29  mov     edi, eax
0x180026a2b  jmp     loc_1800268B7
0x180026a30  mov     ecx, 3
0x180026a35  int     29h; Win8: RtlFailFast(ecx)
```
