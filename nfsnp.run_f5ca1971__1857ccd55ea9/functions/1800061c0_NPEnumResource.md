# NPEnumResource

- ea: `0x1800061c0`
- end: `0x180006533`
- name: `NPEnumResource`
- size: `883`
- prototype: `DWORD __stdcall(HANDLE hEnum, LPDWORD lpcCount, LPVOID lpBuffer, LPDWORD lpBufferSize)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation`

## callees

- `0x1800031a4`
- `0x1800034ec`
- `0x180003884`
- `0x180003b6c`
- `0x180003cf0`
- `0x1800061c0`
- `0x180008d00`
- `0x18000937c`
- `0x180009b60`
- `0x18000bb40`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800063b4`
- `msvcrt!_wcsicmp` at `0x1800063b4`
- `WSOCK32!__imp_WSAStartup` at `0x180006341`
- `WSOCK32!__imp_WSAStartup` at `0x180006341`
- `WSOCK32!__imp_WSACleanup` at `0x180006495`
- `WSOCK32!__imp_WSACleanup` at `0x180006495`

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
0x1800061c0  push    rbp
0x1800061c2  push    rbx
0x1800061c3  push    rsi
0x1800061c4  push    rdi
0x1800061c5  push    r12
0x1800061c7  push    r14
0x1800061c9  push    r15
0x1800061cb  lea     rbp, [rsp-100h]
0x1800061d3  sub     rsp, 200h
0x1800061da  mov     rax, cs:__security_cookie
0x1800061e1  xor     rax, rsp
0x1800061e4  mov     [rbp+130h+var_40], rax
0x1800061eb  mov     eax, dword ptr cs:aNpenumresource_0+8; "source"
0x1800061f1  mov     r14, r9
0x1800061f4  movsd   xmm0, qword ptr cs:aNpenumresource_0; "NPEnumResource"
0x1800061fc  mov     rsi, r8
0x1800061ff  mov     dword ptr [rbp+130h+var_50+8], eax
0x180006205  mov     rdi, rdx
0x180006208  movzx   eax, word ptr cs:aNpenumresource_0+0Ch; "ce"
0x18000620f  mov     rbx, rcx
0x180006212  mov     word ptr [rbp+130h+var_50+0Ch], ax
0x180006219  mov     al, byte ptr cs:aNpenumresource_0+0Eh; ""
0x18000621f  mov     [rbp+130h+var_50+0Eh], al
0x180006225  movsd   qword ptr [rbp+130h+var_50], xmm0
0x18000622d  mov     [rsp+230h+var_200], 0
0x180006235  mov     rcx, cs:WPP_GLOBAL_Control
0x18000623c  lea     r15, WPP_GLOBAL_Control
0x180006243  lea     r12, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000624a  cmp     rcx, r15
0x18000624d  jz      short loc_180006272
0x18000624f  test    byte ptr [rcx+1Ch], 1
0x180006253  jz      short loc_180006272
0x180006255  mov     rcx, [rcx+10h]
0x180006259  lea     r9, [rbp+130h+var_50]
0x180006260  mov     edx, 64h ; 'd'
0x180006265  mov     [rsp+230h+var_210], rbx
0x18000626a  mov     r8, r12
0x18000626d  call    WPP_SF_sq
0x180006272  lea     rcx, [rsp+230h+var_200]
0x180006277  call    NfsNpIsClientRunning
0x18000627c  test    eax, eax
0x18000627e  js      loc_1800064E2
0x180006284  cmp     [rsp+230h+var_200], 0
0x180006289  jz      loc_1800064E2
0x18000628f  test    rbx, rbx
0x180006292  jnz     short loc_1800062C6
0x180006294  mov     rcx, cs:WPP_GLOBAL_Control
0x18000629b  cmp     rcx, r15
0x18000629e  jz      short loc_1800062BC
0x1800062a0  test    byte ptr [rcx+1Ch], 2
0x1800062a4  jz      short loc_1800062BC
0x1800062a6  mov     rcx, [rcx+10h]
0x1800062aa  lea     edx, [rbx+66h]
0x1800062ad  lea     r9, [rbp+130h+var_50]
0x1800062b4  mov     r8, r12
0x1800062b7  call    WPP_SF_s
0x1800062bc  mov     eax, 6
0x1800062c1  jmp     loc_180006511
0x1800062c6  mov     ecx, [rbx]
0x1800062c8  sub     ecx, 1
0x1800062cb  jz      loc_1800064A5
0x1800062d1  sub     ecx, 1
0x1800062d4  jz      short loc_180006325
0x1800062d6  cmp     ecx, 3
0x1800062d9  jz      short loc_1800062E5
0x1800062db  mov     eax, 103h
0x1800062e0  jmp     loc_180006511
0x1800062e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062ec  cmp     rcx, r15
0x1800062ef  jz      short loc_18000630F
0x1800062f1  test    byte ptr [rcx+1Ch], 1
0x1800062f5  jz      short loc_18000630F
0x1800062f7  mov     rcx, [rcx+10h]
0x1800062fb  lea     r9, [rbp+130h+var_50]
0x180006302  mov     edx, 68h ; 'h'
0x180006307  mov     r8, r12
0x18000630a  call    WPP_SF_s
0x18000630f  mov     r9, r14
0x180006312  mov     r8, rsi
0x180006315  mov     rdx, rdi
0x180006318  mov     rcx, rbx
0x18000631b  call    EnumProvider
0x180006320  jmp     loc_180006511
0x180006325  xor     edx, edx; Val
0x180006327  lea     rcx, [rsp+230h+WSAData]; void *
0x18000632c  mov     r8d, 198h; Size
0x180006332  call    memset_0
0x180006337  mov     ecx, 101h; wVersionRequested
0x18000633c  lea     rdx, [rsp+230h+WSAData]; lpWSAData
0x180006341  call    cs:__imp_WSAStartup
0x180006348  nop     dword ptr [rax+rax+00h]
0x18000634d  test    eax, eax
0x18000634f  jnz     loc_18000650C
0x180006355  mov     rax, [rbx+68h]
0x180006359  test    rax, rax
0x18000635c  jnz     short loc_18000639C
0x18000635e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006365  cmp     rcx, r15
0x180006368  jz      short loc_180006386
0x18000636a  test    byte ptr [rcx+1Ch], 1
0x18000636e  jz      short loc_180006386
0x180006370  lea     edx, [rax+69h]
0x180006373  mov     rcx, [rcx+10h]
0x180006377  lea     r9, [rbp+130h+var_50]
0x18000637e  mov     r8, r12
0x180006381  call    WPP_SF_s
0x180006386  mov     r9, r14
0x180006389  mov     r8, rsi
0x18000638c  mov     rdx, rdi
0x18000638f  mov     rcx, rbx
0x180006392  call    EnumNetwork
0x180006397  jmp     loc_180006462
0x18000639c  mov     rcx, [rax+18h]; String1
0x1800063a0  test    rcx, rcx
0x1800063a3  jz      loc_180006466
0x1800063a9  mov     rdx, cs:pGlobalNPCB
0x1800063b0  mov     rdx, [rdx+28h]; String2
0x1800063b4  call    cs:__imp__wcsicmp
0x1800063bb  nop     dword ptr [rax+rax+00h]
0x1800063c0  test    eax, eax
0x1800063c2  jnz     short loc_1800063DB
0x1800063c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063cb  cmp     rcx, r15
0x1800063ce  jz      short loc_180006386
0x1800063d0  test    byte ptr [rcx+1Ch], 1
0x1800063d4  jz      short loc_180006386
0x1800063d6  lea     edx, [rax+6Ah]
0x1800063d9  jmp     short loc_180006373
0x1800063db  mov     rcx, [rbx+68h]
0x1800063df  mov     rcx, [rcx+18h]
0x1800063e3  call    IsLanName
0x1800063e8  cmp     eax, 1
0x1800063eb  jnz     short loc_180006427
0x1800063ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063f4  cmp     rcx, r15
0x1800063f7  jz      short loc_180006414
0x1800063f9  test    [rcx+1Ch], al
0x1800063fc  jz      short loc_180006414
0x1800063fe  mov     rcx, [rcx+10h]
0x180006402  lea     edx, [rax+6Ah]
0x180006405  lea     r9, [rbp+130h+var_50]
0x18000640c  mov     r8, r12
0x18000640f  call    WPP_SF_s
0x180006414  mov     r9, r14
0x180006417  mov     r8, rsi
0x18000641a  mov     rdx, rdi
0x18000641d  mov     rcx, rbx
0x180006420  call    EnumLan
0x180006425  jmp     short loc_180006462
0x180006427  mov     rcx, cs:WPP_GLOBAL_Control
0x18000642e  cmp     rcx, r15
0x180006431  jz      short loc_180006451
0x180006433  test    byte ptr [rcx+1Ch], 1
0x180006437  jz      short loc_180006451
0x180006439  mov     rcx, [rcx+10h]
0x18000643d  lea     r9, [rbp+130h+var_50]
0x180006444  mov     edx, 6Ch ; 'l'
0x180006449  mov     r8, r12
0x18000644c  call    WPP_SF_s
0x180006451  mov     r9, r14
0x180006454  mov     r8, rsi
0x180006457  mov     rdx, rdi
0x18000645a  mov     rcx, rbx
0x18000645d  call    EnumShowMount
0x180006462  mov     ebx, eax
0x180006464  jmp     short loc_180006495
0x180006466  mov     rcx, cs:WPP_GLOBAL_Control
0x18000646d  cmp     rcx, r15
0x180006470  jz      short loc_180006490
0x180006472  test    byte ptr [rcx+1Ch], 1
0x180006476  jz      short loc_180006490
0x180006478  mov     rcx, [rcx+10h]
0x18000647c  lea     r9, [rbp+130h+var_50]
0x180006483  mov     edx, 6Dh ; 'm'
0x180006488  mov     r8, r12
0x18000648b  call    WPP_SF_s
0x180006490  mov     ebx, 103h
0x180006495  call    cs:__imp_WSACleanup
0x18000649c  nop     dword ptr [rax+rax+00h]
0x1800064a1  mov     eax, ebx
0x1800064a3  jmp     short loc_180006511
0x1800064a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064ac  cmp     rcx, r15
0x1800064af  jz      short loc_1800064CF
0x1800064b1  test    byte ptr [rcx+1Ch], 1
0x1800064b5  jz      short loc_1800064CF
0x1800064b7  mov     rcx, [rcx+10h]
0x1800064bb  lea     r9, [rbp+130h+var_50]
0x1800064c2  mov     edx, 67h ; 'g'
0x1800064c7  mov     r8, r12
0x1800064ca  call    WPP_SF_s
0x1800064cf  mov     r9, r14
0x1800064d2  mov     r8, rsi
0x1800064d5  mov     rdx, rdi
0x1800064d8  mov     rcx, rbx
0x1800064db  call    EnumConnectedDevices
0x1800064e0  jmp     short loc_180006511
0x1800064e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064e9  cmp     rcx, r15
0x1800064ec  jz      short loc_18000650C
0x1800064ee  test    byte ptr [rcx+1Ch], 2
0x1800064f2  jz      short loc_18000650C
0x1800064f4  mov     rcx, [rcx+10h]
0x1800064f8  lea     r9, [rbp+130h+var_50]
0x1800064ff  mov     edx, 65h ; 'e'
0x180006504  mov     r8, r12
0x180006507  call    WPP_SF_s
0x18000650c  mov     eax, 4C6h
0x180006511  mov     rcx, [rbp+130h+var_40]
0x180006518  xor     rcx, rsp; StackCookie
0x18000651b  call    __security_check_cookie
0x180006520  add     rsp, 200h
0x180006527  pop     r15
0x180006529  pop     r14
0x18000652b  pop     r12
0x18000652d  pop     rdi
0x18000652e  pop     rsi
0x18000652f  pop     rbx
0x180006530  pop     rbp
0x180006531  retn
```
