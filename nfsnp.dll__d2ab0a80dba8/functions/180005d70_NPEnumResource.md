# NPEnumResource

- ea: `0x180005d70`
- end: `0x1800060d0`
- name: `NPEnumResource`
- size: `864`
- prototype: `DWORD __stdcall(HANDLE hEnum, LPDWORD lpcCount, LPVOID lpBuffer, LPDWORD lpBufferSize)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation`

## callees

- `0x180002ffc`
- `0x180003344`
- `0x1800036d4`
- `0x1800039bc`
- `0x180003b40`
- `0x180005d70`
- `0x180008730`
- `0x180008d20`
- `0x1800094bc`
- `0x18000b314`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005f5e`
- `msvcrt!_wcsicmp` at `0x180005f5e`
- `WSOCK32!__imp_WSAStartup` at `0x180005ef1`
- `WSOCK32!__imp_WSAStartup` at `0x180005ef1`
- `WSOCK32!__imp_WSACleanup` at `0x180006039`
- `WSOCK32!__imp_WSACleanup` at `0x180006039`

## pseudocode

```c
DWORD __stdcall NPEnumResource(HANDLE hEnum, LPDWORD lpcCount, LPVOID lpBuffer, LPDWORD lpBufferSize)
{
  __int64 v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  DWORD v12; // eax
  const wchar_t *v13; // rcx
  DWORD v14; // ebx
  _DWORD v15[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct WSAData WSAData; // [rsp+40h] [rbp-C0h] BYREF
  char v17[16]; // [rsp+1E0h] [rbp+E0h] BYREF

  strcpy(v17, "NPEnumResource");
  v15[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v17,
      (char)hEnum);
  if ( (int)NfsNpIsClientRunning(v15) < 0 || !v15[0] )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v17);
    return 1222;
  }
  if ( !hEnum )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v17);
    return 6;
  }
  if ( *(_DWORD *)hEnum != 1 )
  {
    if ( *(_DWORD *)hEnum != 2 )
    {
      if ( *(_DWORD *)hEnum != 5 )
        return 259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v17);
      return EnumProvider(hEnum, lpcCount, lpBuffer, lpBufferSize);
    }
    memset_0(&WSAData, 0, sizeof(WSAData));
    if ( !WSAStartup(0x101u, &WSAData) )
    {
      v9 = *((_QWORD *)hEnum + 13);
      if ( v9 )
      {
        v13 = *(const wchar_t **)(v9 + 24);
        if ( !v13 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v17);
          v14 = 259;
          goto LABEL_45;
        }
        if ( _wcsicmp(v13, *((const wchar_t **)pGlobalNPCB + 5)) )
        {
          if ( (unsigned int)IsLanName(*(_QWORD *)(*((_QWORD *)hEnum + 13) + 24LL)) == 1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v17);
            v12 = EnumLan(hEnum, lpcCount, lpBuffer, lpBufferSize);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v17);
            v12 = EnumShowMount(hEnum, lpcCount, lpBuffer, lpBufferSize);
          }
          goto LABEL_40;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_25:
          v12 = EnumNetwork(hEnum, lpcCount, lpBuffer, lpBufferSize);
LABEL_40:
          v14 = v12;
LABEL_45:
          WSACleanup();
          return v14;
        }
        v11 = 106;
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        v11 = 105;
      }
      WPP_SF_s(v10[2], v11, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v17);
      goto LABEL_25;
    }
    return 1222;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v17);
  return EnumConnectedDevices(hEnum, lpcCount, lpBuffer, lpBufferSize);
}

```

## disassembly

```asm
0x180005d70  push    rbp
0x180005d72  push    rbx
0x180005d73  push    rsi
0x180005d74  push    rdi
0x180005d75  push    r12
0x180005d77  push    r14
0x180005d79  push    r15
0x180005d7b  lea     rbp, [rsp-100h]
0x180005d83  sub     rsp, 200h
0x180005d8a  mov     rax, cs:__security_cookie
0x180005d91  xor     rax, rsp
0x180005d94  mov     [rbp+130h+var_40], rax
0x180005d9b  mov     eax, dword ptr cs:aNpenumresource_0+8; "source"
0x180005da1  mov     r14, r9
0x180005da4  movsd   xmm0, qword ptr cs:aNpenumresource_0; "NPEnumResource"
0x180005dac  mov     rsi, r8
0x180005daf  mov     dword ptr [rbp+130h+var_50+8], eax
0x180005db5  mov     rdi, rdx
0x180005db8  movzx   eax, word ptr cs:aNpenumresource_0+0Ch; "ce"
0x180005dbf  mov     rbx, rcx
0x180005dc2  mov     word ptr [rbp+130h+var_50+0Ch], ax
0x180005dc9  mov     al, byte ptr cs:aNpenumresource_0+0Eh; ""
0x180005dcf  mov     [rbp+130h+var_50+0Eh], al
0x180005dd5  movsd   qword ptr [rbp+130h+var_50], xmm0
0x180005ddd  mov     [rsp+230h+var_200], 0
0x180005de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dec  lea     r15, WPP_GLOBAL_Control
0x180005df3  lea     r12, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180005dfa  cmp     rcx, r15
0x180005dfd  jz      short loc_180005E22
0x180005dff  test    byte ptr [rcx+1Ch], 1
0x180005e03  jz      short loc_180005E22
0x180005e05  mov     rcx, [rcx+10h]
0x180005e09  lea     r9, [rbp+130h+var_50]
0x180005e10  mov     edx, 64h ; 'd'
0x180005e15  mov     [rsp+230h+var_210], rbx
0x180005e1a  mov     r8, r12
0x180005e1d  call    WPP_SF_sq
0x180005e22  lea     rcx, [rsp+230h+var_200]
0x180005e27  call    NfsNpIsClientRunning
0x180005e2c  test    eax, eax
0x180005e2e  js      loc_180006080
0x180005e34  cmp     [rsp+230h+var_200], 0
0x180005e39  jz      loc_180006080
0x180005e3f  test    rbx, rbx
0x180005e42  jnz     short loc_180005E76
0x180005e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e4b  cmp     rcx, r15
0x180005e4e  jz      short loc_180005E6C
0x180005e50  test    byte ptr [rcx+1Ch], 2
0x180005e54  jz      short loc_180005E6C
0x180005e56  mov     rcx, [rcx+10h]
0x180005e5a  lea     edx, [rbx+66h]
0x180005e5d  lea     r9, [rbp+130h+var_50]
0x180005e64  mov     r8, r12
0x180005e67  call    WPP_SF_s
0x180005e6c  mov     eax, 6
0x180005e71  jmp     loc_1800060AF
0x180005e76  mov     ecx, [rbx]
0x180005e78  sub     ecx, 1
0x180005e7b  jz      loc_180006043
0x180005e81  sub     ecx, 1
0x180005e84  jz      short loc_180005ED5
0x180005e86  cmp     ecx, 3
0x180005e89  jz      short loc_180005E95
0x180005e8b  mov     eax, 103h
0x180005e90  jmp     loc_1800060AF
0x180005e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e9c  cmp     rcx, r15
0x180005e9f  jz      short loc_180005EBF
0x180005ea1  test    byte ptr [rcx+1Ch], 1
0x180005ea5  jz      short loc_180005EBF
0x180005ea7  mov     rcx, [rcx+10h]
0x180005eab  lea     r9, [rbp+130h+var_50]
0x180005eb2  mov     edx, 68h ; 'h'
0x180005eb7  mov     r8, r12
0x180005eba  call    WPP_SF_s
0x180005ebf  mov     r9, r14
0x180005ec2  mov     r8, rsi
0x180005ec5  mov     rdx, rdi
0x180005ec8  mov     rcx, rbx
0x180005ecb  call    EnumProvider
0x180005ed0  jmp     loc_1800060AF
0x180005ed5  xor     edx, edx; Val
0x180005ed7  lea     rcx, [rsp+230h+WSAData]; void *
0x180005edc  mov     r8d, 198h; Size
0x180005ee2  call    memset_0
0x180005ee7  mov     ecx, 101h; wVersionRequested
0x180005eec  lea     rdx, [rsp+230h+WSAData]; lpWSAData
0x180005ef1  call    cs:__imp_WSAStartup
0x180005ef7  test    eax, eax
0x180005ef9  jnz     loc_1800060AA
0x180005eff  mov     rax, [rbx+68h]
0x180005f03  test    rax, rax
0x180005f06  jnz     short loc_180005F46
0x180005f08  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f0f  cmp     rcx, r15
0x180005f12  jz      short loc_180005F30
0x180005f14  test    byte ptr [rcx+1Ch], 1
0x180005f18  jz      short loc_180005F30
0x180005f1a  lea     edx, [rax+69h]
0x180005f1d  mov     rcx, [rcx+10h]
0x180005f21  lea     r9, [rbp+130h+var_50]
0x180005f28  mov     r8, r12
0x180005f2b  call    WPP_SF_s
0x180005f30  mov     r9, r14
0x180005f33  mov     r8, rsi
0x180005f36  mov     rdx, rdi
0x180005f39  mov     rcx, rbx
0x180005f3c  call    EnumNetwork
0x180005f41  jmp     loc_180006006
0x180005f46  mov     rcx, [rax+18h]; String1
0x180005f4a  test    rcx, rcx
0x180005f4d  jz      loc_18000600A
0x180005f53  mov     rdx, cs:pGlobalNPCB
0x180005f5a  mov     rdx, [rdx+28h]; String2
0x180005f5e  call    cs:__imp__wcsicmp
0x180005f64  test    eax, eax
0x180005f66  jnz     short loc_180005F7F
0x180005f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f6f  cmp     rcx, r15
0x180005f72  jz      short loc_180005F30
0x180005f74  test    byte ptr [rcx+1Ch], 1
0x180005f78  jz      short loc_180005F30
0x180005f7a  lea     edx, [rax+6Ah]
0x180005f7d  jmp     short loc_180005F1D
0x180005f7f  mov     rcx, [rbx+68h]
0x180005f83  mov     rcx, [rcx+18h]
0x180005f87  call    IsLanName
0x180005f8c  cmp     eax, 1
0x180005f8f  jnz     short loc_180005FCB
0x180005f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f98  cmp     rcx, r15
0x180005f9b  jz      short loc_180005FB8
0x180005f9d  test    [rcx+1Ch], al
0x180005fa0  jz      short loc_180005FB8
0x180005fa2  mov     rcx, [rcx+10h]
0x180005fa6  lea     edx, [rax+6Ah]
0x180005fa9  lea     r9, [rbp+130h+var_50]
0x180005fb0  mov     r8, r12
0x180005fb3  call    WPP_SF_s
0x180005fb8  mov     r9, r14
0x180005fbb  mov     r8, rsi
0x180005fbe  mov     rdx, rdi
0x180005fc1  mov     rcx, rbx
0x180005fc4  call    EnumLan
0x180005fc9  jmp     short loc_180006006
0x180005fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fd2  cmp     rcx, r15
0x180005fd5  jz      short loc_180005FF5
0x180005fd7  test    byte ptr [rcx+1Ch], 1
0x180005fdb  jz      short loc_180005FF5
0x180005fdd  mov     rcx, [rcx+10h]
0x180005fe1  lea     r9, [rbp+130h+var_50]
0x180005fe8  mov     edx, 6Ch ; 'l'
0x180005fed  mov     r8, r12
0x180005ff0  call    WPP_SF_s
0x180005ff5  mov     r9, r14
0x180005ff8  mov     r8, rsi
0x180005ffb  mov     rdx, rdi
0x180005ffe  mov     rcx, rbx
0x180006001  call    EnumShowMount
0x180006006  mov     ebx, eax
0x180006008  jmp     short loc_180006039
0x18000600a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006011  cmp     rcx, r15
0x180006014  jz      short loc_180006034
0x180006016  test    byte ptr [rcx+1Ch], 1
0x18000601a  jz      short loc_180006034
0x18000601c  mov     rcx, [rcx+10h]
0x180006020  lea     r9, [rbp+130h+var_50]
0x180006027  mov     edx, 6Dh ; 'm'
0x18000602c  mov     r8, r12
0x18000602f  call    WPP_SF_s
0x180006034  mov     ebx, 103h
0x180006039  call    cs:__imp_WSACleanup
0x18000603f  mov     eax, ebx
0x180006041  jmp     short loc_1800060AF
0x180006043  mov     rcx, cs:WPP_GLOBAL_Control
0x18000604a  cmp     rcx, r15
0x18000604d  jz      short loc_18000606D
0x18000604f  test    byte ptr [rcx+1Ch], 1
0x180006053  jz      short loc_18000606D
0x180006055  mov     rcx, [rcx+10h]
0x180006059  lea     r9, [rbp+130h+var_50]
0x180006060  mov     edx, 67h ; 'g'
0x180006065  mov     r8, r12
0x180006068  call    WPP_SF_s
0x18000606d  mov     r9, r14
0x180006070  mov     r8, rsi
0x180006073  mov     rdx, rdi
0x180006076  mov     rcx, rbx
0x180006079  call    EnumConnectedDevices
0x18000607e  jmp     short loc_1800060AF
0x180006080  mov     rcx, cs:WPP_GLOBAL_Control
0x180006087  cmp     rcx, r15
0x18000608a  jz      short loc_1800060AA
0x18000608c  test    byte ptr [rcx+1Ch], 2
0x180006090  jz      short loc_1800060AA
0x180006092  mov     rcx, [rcx+10h]
0x180006096  lea     r9, [rbp+130h+var_50]
0x18000609d  mov     edx, 65h ; 'e'
0x1800060a2  mov     r8, r12
0x1800060a5  call    WPP_SF_s
0x1800060aa  mov     eax, 4C6h
0x1800060af  mov     rcx, [rbp+130h+var_40]
0x1800060b6  xor     rcx, rsp; StackCookie
0x1800060b9  call    __security_check_cookie
0x1800060be  add     rsp, 200h
0x1800060c5  pop     r15
0x1800060c7  pop     r14
0x1800060c9  pop     r12
0x1800060cb  pop     rdi
0x1800060cc  pop     rsi
0x1800060cd  pop     rbx
0x1800060ce  pop     rbp
0x1800060cf  retn
```
