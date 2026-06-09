# netDbOpen

- ea: `0x18002947c`
- end: `0x180029633`
- name: `netDbOpen`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002049c`

## callees

- `0x180021438`
- `0x180021c04`
- `0x180026710`
- `0x18002947c`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800295ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800295ea`
- `WS2_32!__imp_closesocket` at `0x18002957c`
- `WS2_32!__imp_closesocket` at `0x1800295a6`
- `WS2_32!__imp_closesocket` at `0x18002957c`
- `WS2_32!__imp_closesocket` at `0x1800295a6`
- `WS2_32!__imp_socket` at `0x180029561`
- `WS2_32!__imp_socket` at `0x18002958b`
- `WS2_32!__imp_socket` at `0x180029561`
- `WS2_32!__imp_socket` at `0x18002958b`
- `WS2_32!__imp_WSAStartup` at `0x180029550`
- `WS2_32!__imp_WSAStartup` at `0x180029550`
- `WS2_32!__imp_WSACleanup` at `0x1800295ac`
- `WS2_32!__imp_WSACleanup` at `0x1800295ac`

## string_xrefs

- `0x1800295b6`: `netDbOpen: WSAStartup failed. %d`
- `0x180029530`: `netDbOpen: StringCchCopyExW 0x%08x`

## pseudocode

```c
__int64 __fastcall netDbOpen(__int64 *a1, const wchar_t *a2)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  wchar_t *v7; // rax
  STRSAFE_LPWSTR *v8; // r9
  HRESULT v9; // eax
  unsigned __int16 v10; // di
  int v11; // eax
  SOCKET v12; // rax
  SOCKET v13; // rax
  LPVOID *v14; // rbx
  HRESULT Instance; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-1D8h]
  WSAData WSAData; // [rsp+30h] [rbp-1C8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( !a1 || !a2 )
    return 87;
  v4 = RassrvAlloc(56, 1);
  if ( !v4 )
    return 8;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( (_DWORD)v6
    && (v7 = (wchar_t *)RassrvAlloc((unsigned int)(2 * v6 + 2), 0), (*(_QWORD *)(v4 + 32) = v7) != 0)
    && (v9 = StringCchCopyExW(v7, (unsigned int)(v6 + 1), a2, v8, (size_t *)ppv, 0x100u), v10 = v9, v9 < 0) )
  {
    DbgOutputTrace("netDbOpen: StringCchCopyExW 0x%08x", v9);
    return v10;
  }
  else
  {
    v11 = WSAStartup(2u, &WSAData);
    if ( v11 )
    {
      DbgOutputTrace("netDbOpen: WSAStartup failed. %d", v11);
    }
    else
    {
      v12 = socket(2, 2, 0);
      if ( v12 == -1 )
      {
        *(_DWORD *)(v4 + 48) = 0;
      }
      else
      {
        *(_DWORD *)(v4 + 48) = 1;
        closesocket(v12);
      }
      v13 = socket(23, 2, 0);
      if ( v13 == -1 )
      {
        *(_DWORD *)(v4 + 52) = 0;
      }
      else
      {
        *(_DWORD *)(v4 + 52) = 1;
        closesocket(v13);
      }
      WSACleanup();
    }
    *(_DWORD *)(v4 + 20) = 0;
    *a1 = v4;
    v14 = (LPVOID *)(v4 + 40);
    if ( !*v14 )
    {
      Instance = CoCreateInstance(&CLSID_NetConnectionUiUtilities, 0, 1u, &IID_INetConnectionUiUtilities, v14);
      if ( Instance < 0 )
        DbgOutputTrace("LoadNetShell: loadlib fial 0x%08x", Instance);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18002947c  mov     [rsp+arg_10], rbx
0x180029481  mov     [rsp+arg_18], rbp
0x180029486  push    rsi
0x180029487  push    rdi
0x180029488  push    r14
0x18002948a  sub     rsp, 1E0h
0x180029491  mov     rax, cs:__security_cookie
0x180029498  xor     rax, rsp
0x18002949b  mov     [rsp+1F8h+var_28], rax
0x1800294a3  mov     rsi, rdx
0x1800294a6  mov     r14, rcx
0x1800294a9  xor     edx, edx; Val
0x1800294ab  lea     rcx, [rsp+1F8h+WSAData]; void *
0x1800294b0  mov     r8d, 198h; Size
0x1800294b6  call    memset_0
0x1800294bb  xor     ebp, ebp
0x1800294bd  test    r14, r14
0x1800294c0  jz      loc_180029606
0x1800294c6  test    rsi, rsi
0x1800294c9  jz      loc_180029606
0x1800294cf  lea     edx, [rbp+1]
0x1800294d2  lea     ecx, [rbp+38h]
0x1800294d5  call    RassrvAlloc
0x1800294da  mov     rbx, rax
0x1800294dd  test    rax, rax
0x1800294e0  jnz     short loc_1800294EA
0x1800294e2  lea     eax, [rbp+8]
0x1800294e5  jmp     loc_18002960B
0x1800294ea  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800294ee  inc     rdi
0x1800294f1  cmp     [rsi+rdi*2], bp
0x1800294f5  jnz     short loc_1800294EE
0x1800294f7  test    edi, edi
0x1800294f9  jz      short loc_180029544
0x1800294fb  lea     ecx, ds:2[rdi*2]
0x180029502  xor     edx, edx
0x180029504  call    RassrvAlloc
0x180029509  mov     [rbx+20h], rax
0x18002950d  test    rax, rax
0x180029510  jz      short loc_180029544
0x180029512  lea     edx, [rdi+1]; cchDest
0x180029515  mov     [rsp+1F8h+dwFlags], 100h; dwFlags
0x18002951d  mov     r8, rsi; pszSrc
0x180029520  mov     rcx, rax; pszDest
0x180029523  call    StringCchCopyExW
0x180029528  mov     edi, eax
0x18002952a  test    eax, eax
0x18002952c  jns     short loc_180029544
0x18002952e  mov     edx, eax
0x180029530  lea     rcx, aNetdbopenStrin; "netDbOpen: StringCchCopyExW 0x%08x"
0x180029537  call    DbgOutputTrace
0x18002953c  movzx   eax, di
0x18002953f  jmp     loc_18002960B
0x180029544  mov     edi, 2
0x180029549  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x18002954e  mov     ecx, edi; wVersionRequested
0x180029550  call    cs:__imp_WSAStartup
0x180029556  test    eax, eax
0x180029558  jnz     short loc_1800295B4
0x18002955a  xor     r8d, r8d; protocol
0x18002955d  mov     edx, edi; type
0x18002955f  mov     ecx, edi; af
0x180029561  call    cs:__imp_socket
0x180029567  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002956b  jnz     short loc_180029572
0x18002956d  mov     [rbx+30h], ebp
0x180029570  jmp     short loc_180029582
0x180029572  mov     rcx, rax; s
0x180029575  mov     dword ptr [rbx+30h], 1
0x18002957c  call    cs:__imp_closesocket
0x180029582  xor     r8d, r8d; protocol
0x180029585  mov     edx, edi; type
0x180029587  lea     ecx, [r8+17h]; af
0x18002958b  call    cs:__imp_socket
0x180029591  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029595  jnz     short loc_18002959C
0x180029597  mov     [rbx+34h], ebp
0x18002959a  jmp     short loc_1800295AC
0x18002959c  mov     rcx, rax; s
0x18002959f  mov     dword ptr [rbx+34h], 1
0x1800295a6  call    cs:__imp_closesocket
0x1800295ac  call    cs:__imp_WSACleanup
0x1800295b2  jmp     short loc_1800295C2
0x1800295b4  mov     edx, eax
0x1800295b6  lea     rcx, aNetdbopenWsast; "netDbOpen: WSAStartup failed. %d"
0x1800295bd  call    DbgOutputTrace
0x1800295c2  mov     [rbx+14h], ebp
0x1800295c5  mov     [r14], rbx
0x1800295c8  add     rbx, 28h ; '('
0x1800295cc  cmp     [rbx], rbp
0x1800295cf  jnz     short loc_180029602
0x1800295d1  xor     edx, edx; pUnkOuter
0x1800295d3  mov     [rsp+1F8h+ppv], rbx; ppv
0x1800295d8  lea     r9, IID_INetConnectionUiUtilities; riid
0x1800295df  lea     rcx, CLSID_NetConnectionUiUtilities; rclsid
0x1800295e6  lea     r8d, [rdx+1]; dwClsContext
0x1800295ea  call    cs:__imp_CoCreateInstance
0x1800295f0  test    eax, eax
0x1800295f2  jns     short loc_180029602
0x1800295f4  mov     edx, eax
0x1800295f6  lea     rcx, aLoadnetshellLo; "LoadNetShell: loadlib fial 0x%08x"
0x1800295fd  call    DbgOutputTrace
0x180029602  xor     eax, eax
0x180029604  jmp     short loc_18002960B
0x180029606  mov     eax, 57h ; 'W'
0x18002960b  mov     rcx, [rsp+1F8h+var_28]
0x180029613  xor     rcx, rsp; StackCookie
0x180029616  call    __security_check_cookie
0x18002961b  lea     r11, [rsp+1F8h+var_18]
0x180029623  mov     rbx, [r11+30h]
0x180029627  mov     rbp, [r11+38h]
0x18002962b  mov     rsp, r11
0x18002962e  pop     r14
0x180029630  pop     rdi
0x180029631  pop     rsi
0x180029632  retn
```
