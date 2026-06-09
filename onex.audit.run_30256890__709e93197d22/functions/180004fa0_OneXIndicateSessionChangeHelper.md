# OneXIndicateSessionChangeHelper

- ea: `0x180004fa0`
- end: `0x1800053d8`
- name: `OneXIndicateSessionChangeHelper`
- size: `1080`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004b40`

## callees

- `0x180004fa0`
- `0x1800053e0`
- `0x180005440`
- `0x180005470`
- `0x180007f60`
- `0x18000eab4`
- `0x18001c80c`
- `0x180020250`
- `0x1800214f0`
- `0x18002bf98`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180005118`
- `MobileNetworking!ReleaseWriteLock` at `0x180005146`
- `MobileNetworking!ReleaseWriteLock` at `0x180005118`
- `MobileNetworking!ReleaseWriteLock` at `0x180005146`
- `MobileNetworking!AcquireWriteLock` at `0x1800050b3`
- `MobileNetworking!AcquireWriteLock` at `0x1800050f1`
- `MobileNetworking!AcquireWriteLock` at `0x1800050b3`
- `MobileNetworking!AcquireWriteLock` at `0x1800050f1`

## string_xrefs

- `0x1800052e1`: `Session CREATE`

## pseudocode

```c
__int64 __fastcall OneXIndicateSessionChangeHelper(unsigned int a1, __int16 *a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int16 *v4; // rbp
  _DWORD *v6; // rcx
  __int64 i; // rdi
  int v9; // eax
  const wchar_t *v10; // rdi
  __int16 *v11; // kr00_8
  __int64 v12; // r9
  unsigned int SessionNotificationEvent; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v17[16]; // [rsp+48h] [rbp-50h] BYREF
  int *v18; // [rsp+58h] [rbp-40h]
  __int64 v19; // [rsp+60h] [rbp-38h]

  v3 = 0;
  v4 = a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != (_DWORD *)&WPP_GLOBAL_Control )
    {
      v9 = v6[17];
      if ( (v9 & 4) != 0 )
      {
        if ( (v9 & 0x800) != 0 )
        {
          WPP_SF_(*((_QWORD *)v6 + 7), 52, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids);
          v6 = WPP_GLOBAL_Control;
        }
        if ( a1 == 1 )
        {
          v10 = L"Console connect";
        }
        else if ( a1 == 8 )
        {
          v10 = L"Session unlock";
        }
        else
        {
          v11 = a2;
          a2 = &_ImageBase;
          switch ( a1 )
          {
            case 2u:
              v10 = L"Console disconnect";
              break;
            case 3u:
              v10 = L"Remote connect";
              break;
            case 4u:
              v10 = L"Remote disconnect";
              break;
            case 5u:
              v10 = L"Session logon";
              break;
            case 6u:
              v10 = L"Session logoff";
              break;
            case 7u:
              v10 = L"Session lock";
              break;
            case 9u:
              v10 = L"Remote control";
              break;
            case 0xAu:
              v10 = L"Session CREATE";
              break;
            case 0xBu:
              v10 = L"Session Terminate";
              break;
            default:
              a2 = v11;
              v10 = L"Unknown";
              break;
          }
        }
        if ( v6 != (_DWORD *)&WPP_GLOBAL_Control && (v6[17] & 0x800) != 0 )
        {
          WPP_SF_D(*((_QWORD *)v6 + 7), 53, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, 0);
          v6 = WPP_GLOBAL_Control;
        }
        WPP_SF_S(*((_QWORD *)v6 + 7), a2, a3, v10);
        v6 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( (byte_18003DF41 & 0x10) != 0 )
  {
    v16 = a1;
    v18 = (int *)&v16;
    v19 = 4;
    McGenEventWrite_EtwEventWriteTransfer((_DWORD)v6, (unsigned int)"#", a3, 2, (__int64)v17);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !dword_18003DE08 )
  {
    AcquireWriteLock(g_OneXInfo, qword_18003DD98, "OneXIndicateSessionChangeHelper", 279);
    if ( a1 == 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          35,
          WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids,
          (unsigned int)dword_18003DE0C,
          *((_DWORD *)v4 + 1));
      dword_18003DE0C = *((_DWORD *)v4 + 1);
    }
    for ( i = qword_18003DD68; (__int64 *)i != &qword_18003DD68; i = *(_QWORD *)i )
    {
      AcquireWriteLock(i, i + 2896, "OneXIndicateSessionChangeHelper", 302);
      if ( *(int *)(i + 24) >= 0 )
      {
        v12 = *(unsigned int *)(i + 2448);
        if ( (_DWORD)v12 == 1 || (unsigned int)SupplicantIsUsingExplicitCreds(i + 2384) || (_DWORD)v12 == 3 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              36,
              WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids,
              v12,
              *(_DWORD *)(i + 2828));
        }
        else
        {
          SessionNotificationEvent = GenerateSessionNotificationEvent(i, a1, v4);
          v3 = SessionNotificationEvent;
          if ( SessionNotificationEvent )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              WPP_SF_ddqd(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                v14,
                v15,
                *(unsigned int *)(i + 20),
                a1,
                i,
                SessionNotificationEvent);
            v3 = 0;
          }
        }
      }
      ReleaseWriteLock(i, i + 2896, "OneXIndicateSessionChangeHelper", 339);
    }
    ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "OneXIndicateSessionChangeHelper", 355);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (_DWORD *)&WPP_GLOBAL_Control && (v6[17] & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v6 + 7), 38, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180004fa0  mov     r11, rsp
0x180004fa3  push    rbx
0x180004fa4  sub     rsp, 90h
0x180004fab  mov     rax, cs:__security_cookie
0x180004fb2  xor     rax, rsp
0x180004fb5  mov     [rsp+98h+var_30], rax
0x180004fba  mov     [r11+18h], rbp
0x180004fbe  xor     ebx, ebx
0x180004fc0  mov     [r11+20h], rsi
0x180004fc4  mov     rbp, rdx
0x180004fc7  mov     [r11-10h], rdi
0x180004fcb  mov     esi, ecx
0x180004fcd  mov     [r11-28h], r15
0x180004fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fd8  lea     r15, WPP_GLOBAL_Control
0x180004fdf  cmp     rcx, r15
0x180004fe2  jnz     loc_180005160
0x180004fe8  test    cs:byte_18003DF41, 10h
0x180004fef  jz      short loc_18000502B
0x180004ff1  lea     rax, [rsp+98h+var_58]
0x180004ff6  mov     [rsp+98h+var_58], esi
0x180004ffa  mov     [rsp+98h+var_40], rax
0x180004fff  lea     rdx, SessionChangeEventReceived; "#"
0x180005006  lea     rax, [rsp+98h+var_50]
0x18000500b  mov     [rsp+98h+var_38], 4
0x180005014  mov     r9d, 2
0x18000501a  mov     [rsp+98h+var_78], rax
0x18000501f  call    McGenEventWrite_EtwEventWriteTransfer
0x180005024  mov     rcx, cs:WPP_GLOBAL_Control
0x18000502b  cmp     cs:dword_18003DE08, ebx
0x180005031  jz      short loc_180005090
0x180005033  mov     rdi, [rsp+98h+var_10]
0x18000503b  cmp     rcx, r15
0x18000503e  mov     r15, [rsp+98h+var_28]
0x180005043  mov     rsi, [rsp+98h+arg_18]
0x18000504b  mov     rbp, [rsp+98h+arg_10]
0x180005053  jnz     short loc_18000506D
0x180005055  mov     eax, ebx
0x180005057  mov     rcx, [rsp+98h+var_30]
0x18000505c  xor     rcx, rsp; StackCookie
0x18000505f  call    __security_check_cookie
0x180005064  add     rsp, 90h
0x18000506b  pop     rbx
0x18000506c  retn
0x18000506d  test    dword ptr [rcx+44h], 800h
0x180005074  jz      short loc_180005055
0x180005076  mov     rcx, [rcx+38h]
0x18000507a  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x180005081  mov     edx, 26h ; '&'
0x180005086  mov     r9d, ebx
0x180005089  call    WPP_SF_D
0x18000508e  jmp     short loc_180005055
0x180005090  mov     r9d, 117h
0x180005096  mov     [rsp+98h+var_18], r12
0x18000509e  lea     r8, aOnexindicatese_0; "OneXIndicateSessionChangeHelper"
0x1800050a5  lea     rdx, qword_18003DD98
0x1800050ac  lea     rcx, g_OneXInfo
0x1800050b3  call    cs:__imp_AcquireWriteLock
0x1800050b9  cmp     esi, 1
0x1800050bc  jz      loc_180005214
0x1800050c2  mov     rdi, cs:qword_18003DD68
0x1800050c9  lea     r12, qword_18003DD68
0x1800050d0  cmp     rdi, r12
0x1800050d3  jz      short loc_18000512B
0x1800050d5  mov     [rsp+98h+var_20], r14
0x1800050da  mov     r9d, 12Eh
0x1800050e0  lea     r8, aOnexindicatese_0; "OneXIndicateSessionChangeHelper"
0x1800050e7  lea     rdx, [rdi+0B50h]
0x1800050ee  mov     rcx, rdi
0x1800050f1  call    cs:__imp_AcquireWriteLock
0x1800050f7  cmp     dword ptr [rdi+18h], 0
0x1800050fb  jge     loc_180005305
0x180005101  mov     r9d, 153h
0x180005107  lea     r8, aOnexindicatese_0; "OneXIndicateSessionChangeHelper"
0x18000510e  lea     rdx, [rdi+0B50h]
0x180005115  mov     rcx, rdi
0x180005118  call    cs:__imp_ReleaseWriteLock
0x18000511e  mov     rdi, [rdi]
0x180005121  cmp     rdi, r12
0x180005124  jnz     short loc_1800050DA
0x180005126  mov     r14, [rsp+98h+var_20]
0x18000512b  mov     r9d, 163h
0x180005131  lea     r8, aOnexindicatese_0; "OneXIndicateSessionChangeHelper"
0x180005138  lea     rdx, qword_18003DD98
0x18000513f  lea     rcx, g_OneXInfo
0x180005146  call    cs:__imp_ReleaseWriteLock
0x18000514c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005153  mov     r12, [rsp+98h+var_18]
0x18000515b  jmp     loc_180005033
0x180005160  test    dword ptr [rcx+44h], 800h
0x180005167  jnz     loc_180005263
0x18000516d  cmp     rcx, r15
0x180005170  jz      loc_180004FE8
0x180005176  mov     eax, [rcx+44h]
0x180005179  test    al, 4
0x18000517b  jz      loc_180004FE8
0x180005181  bt      eax, 0Bh
0x180005185  jb      loc_180005284
0x18000518b  cmp     esi, 1
0x18000518e  jnz     short loc_1800051B4
0x180005190  lea     rdi, aConsoleConnect; "Console connect"
0x180005197  cmp     rcx, r15
0x18000519a  jnz     short loc_1800051C2
0x18000519c  mov     rcx, [rcx+38h]
0x1800051a0  mov     r9, rdi
0x1800051a3  call    WPP_SF_S
0x1800051a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051af  jmp     loc_180004FE8
0x1800051b4  cmp     esi, 8
0x1800051b7  jnz     short loc_1800051EC
0x1800051b9  lea     rdi, aSessionUnlock; "Session unlock"
0x1800051c0  jmp     short loc_180005197
0x1800051c2  test    dword ptr [rcx+44h], 800h
0x1800051c9  jz      short loc_18000519C
0x1800051cb  mov     rcx, [rcx+38h]
0x1800051cf  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x1800051d6  mov     edx, 35h ; '5'
0x1800051db  xor     r9d, r9d
0x1800051de  call    WPP_SF_D
0x1800051e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051ea  jmp     short loc_18000519C
0x1800051ec  lea     eax, [rsi-2]; switch 10 cases
0x1800051ef  cmp     eax, 9
0x1800051f2  ja      def_180005209; jumptable 0000000180005209 default case, case 8
0x1800051f8  lea     rdx, __ImageBase
0x1800051ff  mov     eax, ds:(jpt_180005209 - 180000000h)[rdx+rax*4]
0x180005206  add     rax, rdx
0x180005209  jmp     rax; switch jump
0x18000520b  lea     rdi, aSessionLock; jumptable 0000000180005209 case 7
0x180005212  jmp     short loc_180005197
0x180005214  mov     rcx, cs:WPP_GLOBAL_Control
0x18000521b  cmp     rcx, r15
0x18000521e  jz      short loc_180005249
0x180005220  test    byte ptr [rcx+44h], 8
0x180005224  jz      short loc_180005249
0x180005226  mov     eax, [rbp+4]
0x180005229  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x180005230  mov     r9d, cs:dword_18003DE0C
0x180005237  mov     edx, 23h ; '#'
0x18000523c  mov     rcx, [rcx+38h]
0x180005240  mov     dword ptr [rsp+98h+var_78], eax
0x180005244  call    WPP_SF_dd
0x180005249  mov     eax, [rbp+4]
0x18000524c  mov     cs:dword_18003DE0C, eax
0x180005252  jmp     loc_1800050C2
0x180005257  lea     rdi, aRemoteDisconne; jumptable 0000000180005209 case 4
0x18000525e  jmp     loc_180005197
0x180005263  mov     rcx, [rcx+38h]
0x180005267  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18000526e  mov     edx, 21h ; '!'
0x180005273  call    WPP_SF_
0x180005278  mov     rcx, cs:WPP_GLOBAL_Control
0x18000527f  jmp     loc_18000516D
0x180005284  mov     rcx, [rcx+38h]
0x180005288  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x18000528f  mov     edx, 34h ; '4'
0x180005294  call    WPP_SF_
0x180005299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052a0  jmp     loc_18000518B
0x1800052a5  lea     rdi, aConsoleDisconn; jumptable 0000000180005209 case 2
0x1800052ac  jmp     loc_180005197
0x1800052b1  lea     rdi, aRemoteConnect; jumptable 0000000180005209 case 3
0x1800052b8  jmp     loc_180005197
0x1800052bd  lea     rdi, aSessionLogon; jumptable 0000000180005209 case 5
0x1800052c4  jmp     loc_180005197
0x1800052c9  lea     rdi, aSessionLogoff; jumptable 0000000180005209 case 6
0x1800052d0  jmp     loc_180005197
0x1800052d5  lea     rdi, aRemoteControl; jumptable 0000000180005209 case 9
0x1800052dc  jmp     loc_180005197
0x1800052e1  lea     rdi, aSessionCreate; jumptable 0000000180005209 case 10
0x1800052e8  jmp     loc_180005197
0x1800052ed  lea     rdi, aSessionTermina; jumptable 0000000180005209 case 11
0x1800052f4  jmp     loc_180005197
0x1800052f9  lea     rdi, aUnknown; jumptable 0000000180005209 default case, case 8
0x180005300  jmp     loc_180005197
0x180005305  mov     r9d, [rdi+990h]
0x18000530c  cmp     r9d, 1
0x180005310  jz      short loc_180005372
0x180005312  lea     rcx, [rdi+950h]
0x180005319  call    SupplicantIsUsingExplicitCreds
0x18000531e  test    eax, eax
0x180005320  jnz     short loc_180005372
0x180005322  cmp     r9d, 3
0x180005326  jz      short loc_180005372
0x180005328  mov     r8, rbp
0x18000532b  mov     edx, esi
0x18000532d  mov     rcx, rdi
0x180005330  call    GenerateSessionNotificationEvent
0x180005335  mov     ebx, eax
0x180005337  test    eax, eax
0x180005339  jz      loc_180005101
0x18000533f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005346  cmp     rcx, r15
0x180005349  jz      short loc_18000536B
0x18000534b  test    byte ptr [rcx+44h], 1
0x18000534f  jz      short loc_18000536B
0x180005351  mov     r9d, [rdi+14h]
0x180005355  mov     rcx, [rcx+38h]
0x180005359  mov     [rsp+98h+var_68], eax
0x18000535d  mov     [rsp+98h+var_70], rdi
0x180005362  mov     dword ptr [rsp+98h+var_78], esi
0x180005366  call    WPP_SF_ddqd
0x18000536b  xor     ebx, ebx
0x18000536d  jmp     loc_180005101
0x180005372  mov     rcx, cs:WPP_GLOBAL_Control
0x180005379  cmp     rcx, r15
0x18000537c  jz      loc_180005101
0x180005382  test    byte ptr [rcx+44h], 4
0x180005386  jz      loc_180005101
0x18000538c  mov     eax, [rdi+0B0Ch]
0x180005392  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x180005399  mov     rcx, [rcx+38h]
0x18000539d  mov     edx, 24h ; '$'
0x1800053a2  mov     dword ptr [rsp+98h+var_78], eax
0x1800053a6  call    WPP_SF_dd
0x1800053ab  jmp     loc_180005101
```
