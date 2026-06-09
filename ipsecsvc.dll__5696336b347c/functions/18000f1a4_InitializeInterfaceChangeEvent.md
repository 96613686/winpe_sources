# InitializeInterfaceChangeEvent

- ea: `0x18000f1a4`
- end: `0x18000f36e`
- name: `InitializeInterfaceChangeEvent`
- size: `458`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a60c`

## callees

- `0x18000b47c`
- `0x18000e510`
- `0x18000f1a4`
- `0x18004d05e`
- `0x18004d090`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x18000f2aa`
- `WS2_32!WSACreateEvent` at `0x18000f2aa`
- `WS2_32!__imp_WSAGetLastError` at `0x18000f2c0`
- `WS2_32!__imp_WSAGetLastError` at `0x18000f2c0`
- `WS2_32!__imp_WSAStartup` at `0x18000f1e6`
- `WS2_32!__imp_WSAStartup` at `0x18000f1e6`

## pseudocode

```c
__int64 InitializeInterfaceChangeEvent()
{
  unsigned int Error; // eax
  unsigned int v1; // edi
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r9
  BOOL v5; // ebx
  int v6; // eax
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  Error = WSAStartup(2u, &WSAData);
  v1 = Error;
  if ( Error )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v3 = 31;
    goto LABEL_5;
  }
  gbwsaStarted = 1;
  if ( WSAData.wVersion != 2 )
  {
    v1 = 10092;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v3 = 32;
    goto LABEL_23;
  }
  v5 = CreateIfChangeEventSocket(2, (HANDLE *)&gIfChangeEventSocket4) == 0;
  v1 = CreateIfChangeEventSocket(23, (HANDLE *)&gIfChangeEventSocket6);
  v6 = v5 + 1;
  if ( v1 )
    v6 = v5;
  if ( v6 )
  {
    v1 = 0;
  }
  else if ( v1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v3 = 33;
LABEL_23:
    v4 = v1;
    goto LABEL_24;
  }
  ghIfChangeEvent = WSACreateEvent();
  if ( ghIfChangeEvent )
    return v1;
  Error = WSAGetLastError();
  v1 = Error;
  if ( !Error )
    return v1;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v3 = 34;
LABEL_5:
    v4 = Error;
LABEL_24:
    WPP_SF_d(v2[2], v3, WPP_e9479874f405377c737bad9289013c01_Traceguids, v4);
    v2 = WPP_GLOBAL_Control;
  }
LABEL_25:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x10) != 0 )
    WPP_SF_d(v2[2], 35, WPP_e9479874f405377c737bad9289013c01_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18000f1a4  mov     [rsp+arg_0], rbx
0x18000f1a9  mov     [rsp+arg_8], rsi
0x18000f1ae  push    rdi
0x18000f1af  sub     rsp, 1D0h
0x18000f1b6  mov     rax, cs:__security_cookie
0x18000f1bd  xor     rax, rsp
0x18000f1c0  mov     [rsp+1D8h+var_18], rax
0x18000f1c8  xor     edx, edx; Val
0x18000f1ca  lea     rcx, [rsp+1D8h+WSAData]; void *
0x18000f1cf  mov     r8d, 198h; Size
0x18000f1d5  call    memset_0
0x18000f1da  mov     ebx, 2
0x18000f1df  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x18000f1e4  mov     ecx, ebx; wVersionRequested
0x18000f1e6  call    cs:__imp_WSAStartup
0x18000f1ec  lea     rsi, WPP_e9479874f405377c737bad9289013c01_Traceguids
0x18000f1f3  mov     edi, eax
0x18000f1f5  test    eax, eax
0x18000f1f7  jz      short loc_18000F227
0x18000f1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f200  lea     rbx, WPP_GLOBAL_Control
0x18000f207  cmp     rcx, rbx
0x18000f20a  jz      loc_18000F347
0x18000f210  test    byte ptr [rcx+1Ch], 10h
0x18000f214  jz      loc_18000F328
0x18000f21a  mov     edx, 1Fh
0x18000f21f  mov     r9d, eax
0x18000f222  jmp     loc_18000F315
0x18000f227  movzx   eax, [rsp+1D8h+WSAData.wVersion]
0x18000f22c  mov     cs:gbwsaStarted, 1
0x18000f236  cmp     al, bl
0x18000f238  jnz     loc_18000F2EF
0x18000f23e  shr     ax, 8
0x18000f242  test    al, al
0x18000f244  jnz     loc_18000F2EF
0x18000f24a  lea     rdx, gIfChangeEventSocket4
0x18000f251  mov     ecx, ebx
0x18000f253  call    CreateIfChangeEventSocket
0x18000f258  xor     ebx, ebx
0x18000f25a  lea     rdx, gIfChangeEventSocket6
0x18000f261  test    eax, eax
0x18000f263  mov     ecx, 17h
0x18000f268  setz    bl
0x18000f26b  call    CreateIfChangeEventSocket
0x18000f270  mov     edi, eax
0x18000f272  lea     eax, [rbx+1]
0x18000f275  test    edi, edi
0x18000f277  cmovnz  eax, ebx
0x18000f27a  test    eax, eax
0x18000f27c  jnz     short loc_18000F2A8
0x18000f27e  test    edi, edi
0x18000f280  jz      short loc_18000F2AA
0x18000f282  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f289  lea     rbx, WPP_GLOBAL_Control
0x18000f290  cmp     rcx, rbx
0x18000f293  jz      loc_18000F347
0x18000f299  test    byte ptr [rcx+1Ch], 10h
0x18000f29d  jz      loc_18000F328
0x18000f2a3  lea     edx, [rax+21h]
0x18000f2a6  jmp     short loc_18000F312
0x18000f2a8  xor     edi, edi
0x18000f2aa  call    cs:__imp_WSACreateEvent
0x18000f2b0  mov     cs:ghIfChangeEvent, rax
0x18000f2b7  test    rax, rax
0x18000f2ba  jnz     loc_18000F347
0x18000f2c0  call    cs:__imp_WSAGetLastError
0x18000f2c6  mov     edi, eax
0x18000f2c8  test    eax, eax
0x18000f2ca  jz      short loc_18000F347
0x18000f2cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2d3  lea     rbx, WPP_GLOBAL_Control
0x18000f2da  cmp     rcx, rbx
0x18000f2dd  jz      short loc_18000F347
0x18000f2df  test    byte ptr [rcx+1Ch], 10h
0x18000f2e3  jz      short loc_18000F328
0x18000f2e5  mov     edx, 22h ; '"'
0x18000f2ea  jmp     loc_18000F21F
0x18000f2ef  mov     edi, 276Ch
0x18000f2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2fb  lea     rbx, WPP_GLOBAL_Control
0x18000f302  cmp     rcx, rbx
0x18000f305  jz      short loc_18000F347
0x18000f307  test    byte ptr [rcx+1Ch], 10h
0x18000f30b  jz      short loc_18000F328
0x18000f30d  mov     edx, 20h ; ' '
0x18000f312  mov     r9d, edi
0x18000f315  mov     rcx, [rcx+10h]
0x18000f319  mov     r8, rsi
0x18000f31c  call    WPP_SF_d
0x18000f321  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f328  cmp     rcx, rbx
0x18000f32b  jz      short loc_18000F347
0x18000f32d  test    byte ptr [rcx+1Ch], 10h
0x18000f331  jz      short loc_18000F347
0x18000f333  mov     rcx, [rcx+10h]
0x18000f337  mov     edx, 23h ; '#'
0x18000f33c  mov     r9d, edi
0x18000f33f  mov     r8, rsi
0x18000f342  call    WPP_SF_d
0x18000f347  mov     eax, edi
0x18000f349  mov     rcx, [rsp+1D8h+var_18]
0x18000f351  xor     rcx, rsp; StackCookie
0x18000f354  call    __security_check_cookie
0x18000f359  lea     r11, [rsp+1D8h+var_8]
0x18000f361  mov     rbx, [r11+10h]
0x18000f365  mov     rsi, [r11+18h]
0x18000f369  mov     rsp, r11
0x18000f36c  pop     rdi
0x18000f36d  retn
```
