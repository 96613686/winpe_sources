# StartLPDFamily

- ea: `0x180009c18`
- end: `0x180009eb2`
- name: `StartLPDFamily`
- size: `666`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009ae4`

## callees

- `0x180001ce0`
- `0x180002616`
- `0x180002e7c`
- `0x180002ea4`
- `0x180009c18`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180009e48`
- `KERNEL32!CreateThread` at `0x180009e48`
- `KERNEL32!GetLastError` at `0x180009e58`
- `KERNEL32!GetLastError` at `0x180009e58`
- `WS2_32!__imp_bind` at `0x180009d9e`
- `WS2_32!__imp_bind` at `0x180009d9e`
- `WS2_32!__imp_closesocket` at `0x180009ddc`
- `WS2_32!__imp_closesocket` at `0x180009ddc`
- `WS2_32!__imp_htons` at `0x180009d74`
- `WS2_32!__imp_htons` at `0x180009d74`
- `WS2_32!__imp_listen` at `0x180009dfc`
- `WS2_32!__imp_listen` at `0x180009dfc`
- `WS2_32!__imp_setsockopt` at `0x180009d17`
- `WS2_32!__imp_setsockopt` at `0x180009d17`
- `WS2_32!__imp_socket` at `0x180009cb1`
- `WS2_32!__imp_socket` at `0x180009cb1`
- `WS2_32!__imp_getservbyname` at `0x180009d64`
- `WS2_32!__imp_getservbyname` at `0x180009d64`
- `WS2_32!__imp_WSAGetLastError` at `0x180009cc2`
- `WS2_32!__imp_WSAGetLastError` at `0x180009da9`
- `WS2_32!__imp_WSAGetLastError` at `0x180009e07`
- `WS2_32!__imp_WSAGetLastError` at `0x180009cc2`
- `WS2_32!__imp_WSAGetLastError` at `0x180009da9`
- `WS2_32!__imp_WSAGetLastError` at `0x180009e07`

## pseudocode

```c
__int64 __fastcall StartLPDFamily(int a1)
{
  void *v1; // rbx
  void *v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rax
  unsigned int v5; // ebx
  __int64 result; // rax
  struct servent *v7; // rax
  u_short s_port; // ax
  SOCKET v9; // rcx
  unsigned int Error; // eax
  unsigned int v11; // esi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD LastError; // eax
  HANDLE Thread; // rax
  char optval[4]; // [rsp+30h] [rbp-B8h] BYREF
  DWORD ThreadId[3]; // [rsp+34h] [rbp-B4h] BYREF
  struct sockaddr name; // [rsp+40h] [rbp-A8h] BYREF

  v1 = (void *)a1;
  memset_0(&name, 0, 0x80u);
  *(_DWORD *)optval = 0;
  ThreadId[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids,
      (unsigned int)v1);
  v2 = v1;
  v3 = 4LL * (_QWORD)v1;
  v4 = socket(family[v3], 1, 0);
  family[v3 + 2] = v4;
  if ( v4 != -1 )
  {
    *(_DWORD *)optval = 1;
    if ( setsockopt(v4, 0xFFFF, -5, optval, 4)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
    }
    memset_0(&name, 0, 0x80u);
    v7 = getservbyname("printer", "tcp");
    if ( v7 )
      s_port = v7->s_port;
    else
      s_port = htons(0x203u);
    v9 = family[v3 + 2];
    *(_WORD *)name.sa_data = s_port;
    name.sa_family = family[v3];
    if ( bind(v9, &name, 128) == -1 )
    {
      Error = WSAGetLastError();
      v11 = Error;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_21;
      v13 = 13;
      v14 = Error;
    }
    else
    {
      if ( listen(family[v3 + 2], 50) == -1 )
      {
        LastError = WSAGetLastError();
        v11 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_21;
        v13 = 14;
      }
      else
      {
        Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)LoopOnAccept, v2, 0, ThreadId);
        family[v3 + 1] = (__int64)Thread;
        if ( Thread )
          return 0;
        LastError = GetLastError();
        v11 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
LABEL_21:
          closesocket(family[v3 + 2]);
          result = v11;
          family[v3 + 2] = -1;
          return result;
        }
        v13 = 15;
      }
      v14 = LastError;
    }
    WPP_SF_d(v12[2], v13, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids, v14);
    goto LABEL_21;
  }
  v5 = WSAGetLastError();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x180009c18  mov     [rsp+arg_8], rbx
0x180009c1d  mov     [rsp+arg_10], rbp
0x180009c22  push    rsi
0x180009c23  push    r14
0x180009c25  push    r15
0x180009c27  sub     rsp, 0D0h
0x180009c2e  mov     rax, cs:__security_cookie
0x180009c35  xor     rax, rsp
0x180009c38  mov     [rsp+0E8h+var_28], rax
0x180009c40  movsxd  rbx, ecx
0x180009c43  xor     edx, edx; Val
0x180009c45  lea     rcx, [rsp+0E8h+name]; void *
0x180009c4a  mov     r8d, 80h; Size
0x180009c50  call    memset_0
0x180009c55  mov     dword ptr [rsp+0E8h+optval], 0
0x180009c5d  mov     [rsp+0E8h+ThreadId], 0
0x180009c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c6c  lea     r14, WPP_GLOBAL_Control
0x180009c73  lea     r15, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180009c7a  cmp     rcx, r14
0x180009c7d  jz      short loc_180009C99
0x180009c7f  test    byte ptr [rcx+1Ch], 1
0x180009c83  jz      short loc_180009C99
0x180009c85  mov     rcx, [rcx+10h]
0x180009c89  mov     edx, 0Ah
0x180009c8e  mov     r9d, ebx
0x180009c91  mov     r8, r15
0x180009c94  call    WPP_SF_d
0x180009c99  xor     r8d, r8d; protocol
0x180009c9c  lea     rbp, family
0x180009ca3  mov     rsi, rbx
0x180009ca6  shl     rbx, 5
0x180009caa  lea     edx, [r8+1]; type
0x180009cae  mov     ecx, [rbx+rbp]; af
0x180009cb1  call    cs:__imp_socket
0x180009cb7  mov     [rbx+rbp+10h], rax
0x180009cbc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009cc0  jnz     short loc_180009CF4
0x180009cc2  call    cs:__imp_WSAGetLastError
0x180009cc8  mov     ebx, eax
0x180009cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cd1  cmp     rcx, r14
0x180009cd4  jz      short loc_180009CED
0x180009cd6  test    byte ptr [rcx+1Ch], 8
0x180009cda  jz      short loc_180009CED
0x180009cdc  mov     rcx, [rcx+10h]
0x180009ce0  mov     edx, 0Bh
0x180009ce5  mov     r8, r15
0x180009ce8  call    WPP_SF_
0x180009ced  mov     eax, ebx
0x180009cef  jmp     loc_180009E89
0x180009cf4  lea     r9, [rsp+0E8h+optval]; optval
0x180009cf9  mov     dword ptr [rsp+0E8h+optval], 1
0x180009d01  mov     edx, 0FFFFh; level
0x180009d06  mov     [rsp+0E8h+optlen], 4; optlen
0x180009d0e  mov     r8d, 0FFFFFFFBh; optname
0x180009d14  mov     rcx, rax; s
0x180009d17  call    cs:__imp_setsockopt
0x180009d1d  test    eax, eax
0x180009d1f  jz      short loc_180009D44
0x180009d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d28  cmp     rcx, r14
0x180009d2b  jz      short loc_180009D44
0x180009d2d  test    byte ptr [rcx+1Ch], 8
0x180009d31  jz      short loc_180009D44
0x180009d33  mov     rcx, [rcx+10h]
0x180009d37  mov     edx, 0Ch
0x180009d3c  mov     r8, r15
0x180009d3f  call    WPP_SF_
0x180009d44  xor     edx, edx; Val
0x180009d46  lea     rcx, [rsp+0E8h+name]; void *
0x180009d4b  mov     r8d, 80h; Size
0x180009d51  call    memset_0
0x180009d56  lea     rdx, proto; "tcp"
0x180009d5d  lea     rcx, name; "printer"
0x180009d64  call    cs:__imp_getservbyname
0x180009d6a  test    rax, rax
0x180009d6d  jnz     short loc_180009D7C
0x180009d6f  mov     ecx, 203h; hostshort
0x180009d74  call    cs:__imp_htons
0x180009d7a  jmp     short loc_180009D80
0x180009d7c  movzx   eax, word ptr [rax+18h]
0x180009d80  mov     rcx, [rbx+rbp+10h]; s
0x180009d85  lea     rdx, [rsp+0E8h+name]; name
0x180009d8a  mov     word ptr [rsp+0E8h+name.sa_data], ax
0x180009d8f  mov     r8d, 80h; namelen
0x180009d95  movzx   eax, word ptr [rbx+rbp]
0x180009d99  mov     [rsp+0E8h+name.sa_family], ax
0x180009d9e  call    cs:__imp_bind
0x180009da4  cmp     eax, 0FFFFFFFFh
0x180009da7  jnz     short loc_180009DF2
0x180009da9  call    cs:__imp_WSAGetLastError
0x180009daf  mov     esi, eax
0x180009db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009db8  cmp     rcx, r14
0x180009dbb  jz      short loc_180009DD7
0x180009dbd  test    byte ptr [rcx+1Ch], 8
0x180009dc1  jz      short loc_180009DD7
0x180009dc3  mov     edx, 0Dh
0x180009dc8  mov     r9d, eax
0x180009dcb  mov     rcx, [rcx+10h]
0x180009dcf  mov     r8, r15
0x180009dd2  call    WPP_SF_d
0x180009dd7  mov     rcx, [rbx+rbp+10h]; s
0x180009ddc  call    cs:__imp_closesocket
0x180009de2  mov     eax, esi
0x180009de4  mov     qword ptr [rbx+rbp+10h], 0FFFFFFFFFFFFFFFFh
0x180009ded  jmp     loc_180009E89
0x180009df2  mov     rcx, [rbx+rbp+10h]; s
0x180009df7  mov     edx, 32h ; '2'; backlog
0x180009dfc  call    cs:__imp_listen
0x180009e02  cmp     eax, 0FFFFFFFFh
0x180009e05  jnz     short loc_180009E28
0x180009e07  call    cs:__imp_WSAGetLastError
0x180009e0d  mov     esi, eax
0x180009e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e16  cmp     rcx, r14
0x180009e19  jz      short loc_180009DD7
0x180009e1b  test    byte ptr [rcx+1Ch], 8
0x180009e1f  jz      short loc_180009DD7
0x180009e21  mov     edx, 0Eh
0x180009e26  jmp     short loc_180009E7F
0x180009e28  lea     rax, [rsp+0E8h+ThreadId]
0x180009e2d  mov     r9, rsi; lpParameter
0x180009e30  mov     [rsp+0E8h+lpThreadId], rax; lpThreadId
0x180009e35  lea     r8, LoopOnAccept; lpStartAddress
0x180009e3c  xor     edx, edx; dwStackSize
0x180009e3e  mov     [rsp+0E8h+optlen], 0; dwCreationFlags
0x180009e46  xor     ecx, ecx; lpThreadAttributes
0x180009e48  call    cs:__imp_CreateThread
0x180009e4e  mov     [rbx+rbp+8], rax
0x180009e53  test    rax, rax
0x180009e56  jnz     short loc_180009E87
0x180009e58  call    cs:__imp_GetLastError
0x180009e5e  mov     esi, eax
0x180009e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e67  cmp     rcx, r14
0x180009e6a  jz      loc_180009DD7
0x180009e70  test    byte ptr [rcx+1Ch], 8
0x180009e74  jz      loc_180009DD7
0x180009e7a  mov     edx, 0Fh
0x180009e7f  mov     r9d, eax
0x180009e82  jmp     loc_180009DCB
0x180009e87  xor     eax, eax
0x180009e89  mov     rcx, [rsp+0E8h+var_28]
0x180009e91  xor     rcx, rsp; StackCookie
0x180009e94  call    __security_check_cookie
0x180009e99  lea     r11, [rsp+0E8h+var_18]
0x180009ea1  mov     rbx, [r11+28h]
0x180009ea5  mov     rbp, [r11+30h]
0x180009ea9  mov     rsp, r11
0x180009eac  pop     r15
0x180009eae  pop     r14
0x180009eb0  pop     rsi
0x180009eb1  retn
```
