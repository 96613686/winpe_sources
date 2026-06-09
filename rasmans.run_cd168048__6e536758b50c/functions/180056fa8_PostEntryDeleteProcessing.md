# PostEntryDeleteProcessing

- ea: `0x180056fa8`
- end: `0x180057383`
- name: `PostEntryDeleteProcessing`
- size: `987`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800615c0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180056fa8`
- `0x180057e10`
- `0x18005f6f4`
- `0x180066ca4`
- `0x180068464`
- `0x180069be0`
- `0x1800b3138`
- `0x1800e8e96`
- `0x1800e8ec6`
- `0x1800e8ef0`
- `0x1800e8fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057025`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057323`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057323`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180057083`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180057128`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180057083`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180057128`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005713c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005713c`

## pseudocode

```c
__int64 __fastcall PostEntryDeleteProcessing(wchar_t *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  HKEY v8; // rdi
  struct _LIST_ENTRY *v9; // rcx
  int v10; // eax
  HKEY v11; // rdi
  unsigned int v12; // eax
  unsigned int v13; // eax
  _BYTE *v14; // rax
  wchar_t *v15; // rcx
  unsigned int TriggerProfile; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String1[792]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v20; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v21[9998]; // [rsp+672h] [rbp+572h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 67, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids);
  }
  v6 = 0;
  EnterCriticalSection(&g_csSubmitRequest);
  memset_0(String1, 0, 0x202u);
  hKey[0] = 0;
  if ( !(unsigned int)RasGetDefIntConnName(0, String1, hKey) )
  {
    v7 = wcsncmp_0(String1, a1, 0x101u);
    v8 = hKey[0];
    if ( !v7 )
      RegDeleteValueA(hKey[0], "DefaultInternet");
    if ( v8 )
      RegCloseKey(v8);
    goto LABEL_15;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 68, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids);
LABEL_15:
    v9 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(a2 + 8) )
    goto LABEL_27;
  if ( !(unsigned int)RasGetDefIntConnName(1, String1, hKey) )
  {
    v10 = wcsncmp_0(String1, a1, 0x101u);
    v11 = hKey[0];
    if ( !v10 )
      RegDeleteValueA(hKey[0], "DefaultInternet");
    if ( v11 )
      RegCloseKey(v11);
    goto LABEL_26;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 69, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids);
LABEL_26:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_27:
  if ( (*(_DWORD *)(a2 + 32) & 0x400) == 0 )
  {
    v20 = 0;
    memset_0(v21, 0, sizeof(v21));
    memset_0(String1, 0, sizeof(String1));
    GetUserSid(&v20);
    v12 = SetEntryDialParams((unsigned int)&v20, *(_DWORD *)(a3 + 456), -1073741824, 0, (__int64)String1);
    if ( v12
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 70, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids, v12);
    }
    v13 = RasSetKey(*(_QWORD *)(a3 + 464));
    v6 = v13;
    if ( !v13 )
      goto LABEL_38;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 71, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids, v13);
LABEL_38:
      v9 = WPP_GLOBAL_Control;
    }
  }
  v14 = *(_BYTE **)(a3 + 448);
  if ( v14
    && *v14
    && v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v9[1].Blink) & 0x2000) != 0
    && BYTE1(v9[1].Blink) >= 2u )
  {
    WPP_SF_(v9[1].Flink, 72, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids);
  }
  if ( *(_DWORD *)(a3 + 704) )
  {
    v15 = *(wchar_t **)a2;
    LODWORD(hKey[0]) = 0;
    IsActiveAutoTriggerConnectionInternal(v15, a1);
    if ( LODWORD(hKey[0]) )
    {
      TriggerProfile = RasSelectNextTriggerProfile();
      if ( TriggerProfile )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 73, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids, TriggerProfile);
        }
      }
    }
    v6 = 0;
  }
  LeaveCriticalSection(&g_csSubmitRequest);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 74, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180056fa8  push    rbp
0x180056faa  push    rbx
0x180056fab  push    rsi
0x180056fac  push    rdi
0x180056fad  push    r13
0x180056faf  push    r14
0x180056fb1  push    r15
0x180056fb3  lea     rbp, [rsp-2C90h]
0x180056fbb  mov     eax, 2D90h
0x180056fc0  call    _alloca_probe
0x180056fc5  sub     rsp, rax
0x180056fc8  mov     rax, cs:__security_cookie
0x180056fcf  xor     rax, rsp
0x180056fd2  mov     [rbp+2CC0h+var_40], rax
0x180056fd9  mov     rsi, r8
0x180056fdc  mov     r14, rdx
0x180056fdf  mov     r15, rcx
0x180056fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fe9  lea     rdi, WPP_GLOBAL_Control
0x180056ff0  mov     r13d, 2000h
0x180056ff6  cmp     rcx, rdi
0x180056ff9  jz      short loc_18005701C
0x180056ffb  test    [rcx+1Ch], r13d
0x180056fff  jz      short loc_18005701C
0x180057001  cmp     byte ptr [rcx+19h], 6
0x180057005  jb      short loc_18005701C
0x180057007  mov     rcx, [rcx+10h]
0x18005700b  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x180057012  mov     edx, 43h ; 'C'
0x180057017  call    WPP_SF_
0x18005701c  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x180057023  xor     ebx, ebx
0x180057025  call    cs:__imp_EnterCriticalSection
0x18005702c  nop     dword ptr [rax+rax+00h]
0x180057031  xor     edx, edx; Val
0x180057033  lea     rcx, [rsp+2DC0h+String1]; void *
0x180057038  mov     r8d, 202h; Size
0x18005703e  call    memset_0
0x180057043  lea     r8, [rsp+2DC0h+hKey]
0x180057048  mov     [rsp+2DC0h+hKey], rbx
0x18005704d  lea     rdx, [rsp+2DC0h+String1]
0x180057052  xor     ecx, ecx
0x180057054  call    RasGetDefIntConnName
0x180057059  test    eax, eax
0x18005705b  jnz     short loc_1800570AC
0x18005705d  mov     r8d, 101h; MaxCount
0x180057063  lea     rcx, [rsp+2DC0h+String1]; String1
0x180057068  mov     rdx, r15; String2
0x18005706b  call    wcsncmp_0
0x180057070  mov     rdi, [rsp+2DC0h+hKey]
0x180057075  test    eax, eax
0x180057077  jnz     short loc_18005708F
0x180057079  lea     rdx, aDefaultinterne_0; "DefaultInternet"
0x180057080  mov     rcx, rdi; hKey
0x180057083  call    cs:__imp_RegDeleteValueA
0x18005708a  nop     dword ptr [rax+rax+00h]
0x18005708f  test    rdi, rdi
0x180057092  jz      short loc_1800570A3
0x180057094  mov     rcx, rdi; hKey
0x180057097  call    cs:__imp_RegCloseKey
0x18005709e  nop     dword ptr [rax+rax+00h]
0x1800570a3  lea     rdi, WPP_GLOBAL_Control
0x1800570aa  jmp     short loc_1800570D9
0x1800570ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800570b3  cmp     rcx, rdi
0x1800570b6  jz      short loc_1800570E0
0x1800570b8  test    [rcx+1Ch], r13d
0x1800570bc  jz      short loc_1800570E0
0x1800570be  cmp     byte ptr [rcx+19h], 3
0x1800570c2  jb      short loc_1800570E0
0x1800570c4  mov     rcx, [rcx+10h]
0x1800570c8  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x1800570cf  mov     edx, 44h ; 'D'
0x1800570d4  call    WPP_SF_
0x1800570d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800570e0  cmp     [r14+8], ebx
0x1800570e4  jnz     loc_18005717E
0x1800570ea  lea     r8, [rsp+2DC0h+hKey]
0x1800570ef  mov     ecx, 1
0x1800570f4  lea     rdx, [rsp+2DC0h+String1]
0x1800570f9  call    RasGetDefIntConnName
0x1800570fe  test    eax, eax
0x180057100  jnz     short loc_18005714A
0x180057102  mov     r8d, 101h; MaxCount
0x180057108  lea     rcx, [rsp+2DC0h+String1]; String1
0x18005710d  mov     rdx, r15; String2
0x180057110  call    wcsncmp_0
0x180057115  mov     rdi, [rsp+2DC0h+hKey]
0x18005711a  test    eax, eax
0x18005711c  jnz     short loc_180057134
0x18005711e  lea     rdx, aDefaultinterne_0; "DefaultInternet"
0x180057125  mov     rcx, rdi; hKey
0x180057128  call    cs:__imp_RegDeleteValueA
0x18005712f  nop     dword ptr [rax+rax+00h]
0x180057134  test    rdi, rdi
0x180057137  jz      short loc_180057177
0x180057139  mov     rcx, rdi; hKey
0x18005713c  call    cs:__imp_RegCloseKey
0x180057143  nop     dword ptr [rax+rax+00h]
0x180057148  jmp     short loc_180057177
0x18005714a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057151  cmp     rcx, rdi
0x180057154  jz      short loc_18005717E
0x180057156  test    [rcx+1Ch], r13d
0x18005715a  jz      short loc_18005717E
0x18005715c  cmp     byte ptr [rcx+19h], 3
0x180057160  jb      short loc_18005717E
0x180057162  mov     rcx, [rcx+10h]
0x180057166  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x18005716d  mov     edx, 45h ; 'E'
0x180057172  call    WPP_SF_
0x180057177  mov     rcx, cs:WPP_GLOBAL_Control
0x18005717e  test    dword ptr [r14+20h], 400h
0x180057186  jnz     loc_18005727B
0x18005718c  xor     eax, eax
0x18005718e  lea     rcx, [rbp+2CC0h+var_274E]; void *
0x180057195  xor     edx, edx; Val
0x180057197  mov     [rbp+2CC0h+var_2750], ax
0x18005719e  mov     r8d, 270Eh; Size
0x1800571a4  call    memset_0
0x1800571a9  xor     edx, edx; Val
0x1800571ab  lea     rcx, [rsp+2DC0h+String1]; void *
0x1800571b0  mov     r8d, 630h; Size
0x1800571b6  call    memset_0
0x1800571bb  lea     rcx, [rbp+2CC0h+var_2750]
0x1800571c2  call    GetUserSid
0x1800571c7  mov     edx, [rsi+1C8h]
0x1800571cd  lea     rax, [rsp+2DC0h+String1]
0x1800571d2  xor     r9d, r9d
0x1800571d5  mov     [rsp+2DC0h+var_2DA0], rax
0x1800571da  mov     r8d, 0C0000000h
0x1800571e0  lea     rcx, [rbp+2CC0h+var_2750]
0x1800571e7  call    SetEntryDialParams
0x1800571ec  test    eax, eax
0x1800571ee  jz      short loc_180057229
0x1800571f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800571f7  lea     rdi, WPP_GLOBAL_Control
0x1800571fe  cmp     rcx, rdi
0x180057201  jz      short loc_180057230
0x180057203  test    [rcx+1Ch], r13d
0x180057207  jz      short loc_180057230
0x180057209  cmp     byte ptr [rcx+19h], 2
0x18005720d  jb      short loc_180057230
0x18005720f  mov     rcx, [rcx+10h]
0x180057213  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x18005721a  mov     edx, 46h ; 'F'
0x18005721f  mov     r9d, eax
0x180057222  call    WPP_SF_d
0x180057227  jmp     short loc_180057230
0x180057229  lea     rdi, WPP_GLOBAL_Control
0x180057230  mov     rcx, [rsi+1D0h]
0x180057237  call    RasSetKey
0x18005723c  mov     ebx, eax
0x18005723e  test    eax, eax
0x180057240  jz      short loc_180057272
0x180057242  mov     rcx, cs:WPP_GLOBAL_Control
0x180057249  cmp     rcx, rdi
0x18005724c  jz      short loc_180057282
0x18005724e  test    [rcx+1Ch], r13d
0x180057252  jz      short loc_180057282
0x180057254  cmp     byte ptr [rcx+19h], 2
0x180057258  jb      short loc_180057282
0x18005725a  mov     rcx, [rcx+10h]
0x18005725e  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x180057265  mov     edx, 47h ; 'G'
0x18005726a  mov     r9d, eax
0x18005726d  call    WPP_SF_d
0x180057272  mov     rcx, cs:WPP_GLOBAL_Control
0x180057279  jmp     short loc_180057282
0x18005727b  lea     rdi, WPP_GLOBAL_Control
0x180057282  mov     rax, [rsi+1C0h]
0x180057289  test    rax, rax
0x18005728c  jz      short loc_1800572B9
0x18005728e  cmp     byte ptr [rax], 0
0x180057291  jz      short loc_1800572B9
0x180057293  cmp     rcx, rdi
0x180057296  jz      short loc_1800572B9
0x180057298  test    [rcx+1Ch], r13d
0x18005729c  jz      short loc_1800572B9
0x18005729e  cmp     byte ptr [rcx+19h], 2
0x1800572a2  jb      short loc_1800572B9
0x1800572a4  mov     rcx, [rcx+10h]
0x1800572a8  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x1800572af  mov     edx, 48h ; 'H'
0x1800572b4  call    WPP_SF_
0x1800572b9  cmp     dword ptr [rsi+2C0h], 0
0x1800572c0  jz      short loc_18005731C
0x1800572c2  mov     rcx, [r14]; String1
0x1800572c5  lea     r9, [rsp+2DC0h+hKey]
0x1800572ca  mov     rdx, r15; wchar_t *
0x1800572cd  mov     dword ptr [rsp+2DC0h+hKey], 0
0x1800572d5  call    IsActiveAutoTriggerConnectionInternal
0x1800572da  cmp     dword ptr [rsp+2DC0h+hKey], 0
0x1800572df  jz      short loc_18005731A
0x1800572e1  call    RasSelectNextTriggerProfile
0x1800572e6  test    eax, eax
0x1800572e8  jz      short loc_18005731A
0x1800572ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800572f1  cmp     rcx, rdi
0x1800572f4  jz      short loc_18005731A
0x1800572f6  test    [rcx+1Ch], r13d
0x1800572fa  jz      short loc_18005731A
0x1800572fc  cmp     byte ptr [rcx+19h], 2
0x180057300  jb      short loc_18005731A
0x180057302  mov     rcx, [rcx+10h]
0x180057306  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x18005730d  mov     edx, 49h ; 'I'
0x180057312  mov     r9d, eax
0x180057315  call    WPP_SF_d
0x18005731a  xor     ebx, ebx
0x18005731c  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x180057323  call    cs:__imp_LeaveCriticalSection
0x18005732a  nop     dword ptr [rax+rax+00h]
0x18005732f  mov     rcx, cs:WPP_GLOBAL_Control
0x180057336  cmp     rcx, rdi
0x180057339  jz      short loc_18005735F
0x18005733b  test    [rcx+1Ch], r13d
0x18005733f  jz      short loc_18005735F
0x180057341  cmp     byte ptr [rcx+19h], 6
0x180057345  jb      short loc_18005735F
0x180057347  mov     rcx, [rcx+10h]
0x18005734b  lea     r8, WPP_22f25982ed5f39ad54055096f8711a60_Traceguids
0x180057352  mov     edx, 4Ah ; 'J'
0x180057357  mov     r9d, ebx
0x18005735a  call    WPP_SF_d
0x18005735f  mov     eax, ebx
0x180057361  mov     rcx, [rbp+2CC0h+var_40]
0x180057368  xor     rcx, rsp; StackCookie
0x18005736b  call    __security_check_cookie
0x180057370  add     rsp, 2D90h
0x180057377  pop     r15
0x180057379  pop     r14
0x18005737b  pop     r13
0x18005737d  pop     rdi
0x18005737e  pop     rsi
0x18005737f  pop     rbx
0x180057380  pop     rbp
0x180057381  retn
```
