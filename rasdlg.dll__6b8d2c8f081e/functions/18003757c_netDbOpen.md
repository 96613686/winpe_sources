# netDbOpen

- ea: `0x18003757c`
- end: `0x18003773b`
- name: `netDbOpen`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e918`

## callees

- `0x18001e944`
- `0x180033a4c`
- `0x1800348f0`
- `0x18003757c`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800376f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800376f2`
- `WS2_32!__imp_closesocket` at `0x180037684`
- `WS2_32!__imp_closesocket` at `0x1800376ae`
- `WS2_32!__imp_closesocket` at `0x180037684`
- `WS2_32!__imp_closesocket` at `0x1800376ae`
- `WS2_32!__imp_socket` at `0x180037669`
- `WS2_32!__imp_socket` at `0x180037693`
- `WS2_32!__imp_socket` at `0x180037669`
- `WS2_32!__imp_socket` at `0x180037693`
- `WS2_32!__imp_WSAStartup` at `0x180037658`
- `WS2_32!__imp_WSAStartup` at `0x180037658`
- `WS2_32!__imp_WSACleanup` at `0x1800376b4`
- `WS2_32!__imp_WSACleanup` at `0x1800376b4`

## string_xrefs

- `0x180037638`: `netDbOpen: StringCchCopyExW 0x%08x`
- `0x1800376be`: `netDbOpen: WSAStartup failed. %d`

## pseudocode

```c
__int64 __fastcall netDbOpen(__int64 *a1, const wchar_t *a2)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  wchar_t *v7; // rax
  HRESULT v8; // eax
  unsigned __int16 v9; // di
  int v10; // eax
  SOCKET v11; // rax
  SOCKET v12; // rax
  LPVOID *v13; // rbx
  HRESULT Instance; // eax
  struct WSAData WSAData; // [rsp+30h] [rbp-1C8h] BYREF

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
    && (v8 = StringCchCopyExW(v7, (unsigned int)(v6 + 1), a2, 0, 0, 0x100u), v9 = v8, v8 < 0) )
  {
    DbgOutputTrace("netDbOpen: StringCchCopyExW 0x%08x", v8);
    return v9;
  }
  else
  {
    v10 = WSAStartup(2u, &WSAData);
    if ( v10 )
    {
      DbgOutputTrace("netDbOpen: WSAStartup failed. %d", v10);
    }
    else
    {
      v11 = socket(2, 2, 0);
      if ( v11 == -1 )
      {
        *(_DWORD *)(v4 + 48) = 0;
      }
      else
      {
        *(_DWORD *)(v4 + 48) = 1;
        closesocket(v11);
      }
      v12 = socket(23, 2, 0);
      if ( v12 == -1 )
      {
        *(_DWORD *)(v4 + 52) = 0;
      }
      else
      {
        *(_DWORD *)(v4 + 52) = 1;
        closesocket(v12);
      }
      WSACleanup();
    }
    *(_DWORD *)(v4 + 20) = 0;
    *a1 = v4;
    v13 = (LPVOID *)(v4 + 40);
    if ( !*v13 )
    {
      Instance = CoCreateInstance(&CLSID_NetConnectionUiUtilities, 0, 1u, &IID_INetConnectionUiUtilities, v13);
      if ( Instance < 0 )
        DbgOutputTrace("LoadNetShell: loadlib fial 0x%08x", Instance);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18003757c  mov     [rsp+arg_10], rbx
0x180037581  mov     [rsp+arg_18], rbp
0x180037586  push    rsi
0x180037587  push    rdi
0x180037588  push    r14
0x18003758a  sub     rsp, 1E0h
0x180037591  mov     rax, cs:__security_cookie
0x180037598  xor     rax, rsp
0x18003759b  mov     [rsp+1F8h+var_28], rax
0x1800375a3  mov     rsi, rdx
0x1800375a6  mov     r14, rcx
0x1800375a9  xor     edx, edx; Val
0x1800375ab  lea     rcx, [rsp+1F8h+WSAData]; void *
0x1800375b0  mov     r8d, 198h; Size
0x1800375b6  call    memset_0
0x1800375bb  xor     ebp, ebp
0x1800375bd  test    r14, r14
0x1800375c0  jz      loc_18003770E
0x1800375c6  test    rsi, rsi
0x1800375c9  jz      loc_18003770E
0x1800375cf  lea     edx, [rbp+1]
0x1800375d2  lea     ecx, [rbp+38h]
0x1800375d5  call    RassrvAlloc
0x1800375da  mov     rbx, rax
0x1800375dd  test    rax, rax
0x1800375e0  jnz     short loc_1800375EA
0x1800375e2  lea     eax, [rbp+8]
0x1800375e5  jmp     loc_180037713
0x1800375ea  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800375ee  inc     rdi
0x1800375f1  cmp     [rsi+rdi*2], bp
0x1800375f5  jnz     short loc_1800375EE
0x1800375f7  test    edi, edi
0x1800375f9  jz      short loc_18003764C
0x1800375fb  lea     ecx, ds:2[rdi*2]
0x180037602  xor     edx, edx
0x180037604  call    RassrvAlloc
0x180037609  mov     [rbx+20h], rax
0x18003760d  test    rax, rax
0x180037610  jz      short loc_18003764C
0x180037612  lea     edx, [rdi+1]; cchDest
0x180037615  mov     [rsp+1F8h+dwFlags], 100h; dwFlags
0x18003761d  xor     r9d, r9d; ppszDestEnd
0x180037620  mov     [rsp+1F8h+pcchRemaining], rbp; pcchRemaining
0x180037625  mov     r8, rsi; pszSrc
0x180037628  mov     rcx, rax; pszDest
0x18003762b  call    StringCchCopyExW
0x180037630  mov     edi, eax
0x180037632  test    eax, eax
0x180037634  jns     short loc_18003764C
0x180037636  mov     edx, eax
0x180037638  lea     rcx, aNetdbopenStrin; "netDbOpen: StringCchCopyExW 0x%08x"
0x18003763f  call    DbgOutputTrace
0x180037644  movzx   eax, di
0x180037647  jmp     loc_180037713
0x18003764c  mov     edi, 2
0x180037651  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x180037656  mov     ecx, edi; wVersionRequested
0x180037658  call    cs:__imp_WSAStartup
0x18003765e  test    eax, eax
0x180037660  jnz     short loc_1800376BC
0x180037662  xor     r8d, r8d; protocol
0x180037665  mov     edx, edi; type
0x180037667  mov     ecx, edi; af
0x180037669  call    cs:__imp_socket
0x18003766f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037673  jnz     short loc_18003767A
0x180037675  mov     [rbx+30h], ebp
0x180037678  jmp     short loc_18003768A
0x18003767a  mov     rcx, rax; s
0x18003767d  mov     dword ptr [rbx+30h], 1
0x180037684  call    cs:__imp_closesocket
0x18003768a  xor     r8d, r8d; protocol
0x18003768d  mov     edx, edi; type
0x18003768f  lea     ecx, [r8+17h]; af
0x180037693  call    cs:__imp_socket
0x180037699  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003769d  jnz     short loc_1800376A4
0x18003769f  mov     [rbx+34h], ebp
0x1800376a2  jmp     short loc_1800376B4
0x1800376a4  mov     rcx, rax; s
0x1800376a7  mov     dword ptr [rbx+34h], 1
0x1800376ae  call    cs:__imp_closesocket
0x1800376b4  call    cs:__imp_WSACleanup
0x1800376ba  jmp     short loc_1800376CA
0x1800376bc  mov     edx, eax
0x1800376be  lea     rcx, aNetdbopenWsast; "netDbOpen: WSAStartup failed. %d"
0x1800376c5  call    DbgOutputTrace
0x1800376ca  mov     [rbx+14h], ebp
0x1800376cd  mov     [r14], rbx
0x1800376d0  add     rbx, 28h ; '('
0x1800376d4  cmp     [rbx], rbp
0x1800376d7  jnz     short loc_18003770A
0x1800376d9  xor     edx, edx; pUnkOuter
0x1800376db  mov     [rsp+1F8h+pcchRemaining], rbx; ppv
0x1800376e0  lea     r9, IID_INetConnectionUiUtilities; riid
0x1800376e7  lea     rcx, CLSID_NetConnectionUiUtilities; rclsid
0x1800376ee  lea     r8d, [rdx+1]; dwClsContext
0x1800376f2  call    cs:__imp_CoCreateInstance
0x1800376f8  test    eax, eax
0x1800376fa  jns     short loc_18003770A
0x1800376fc  mov     edx, eax
0x1800376fe  lea     rcx, aLoadnetshellLo; "LoadNetShell: loadlib fial 0x%08x"
0x180037705  call    DbgOutputTrace
0x18003770a  xor     eax, eax
0x18003770c  jmp     short loc_180037713
0x18003770e  mov     eax, 57h ; 'W'
0x180037713  mov     rcx, [rsp+1F8h+var_28]
0x18003771b  xor     rcx, rsp; StackCookie
0x18003771e  call    __security_check_cookie
0x180037723  lea     r11, [rsp+1F8h+var_18]
0x18003772b  mov     rbx, [r11+30h]
0x18003772f  mov     rbp, [r11+38h]
0x180037733  mov     rsp, r11
0x180037736  pop     r14
0x180037738  pop     rdi
0x180037739  pop     rsi
0x18003773a  retn
```
