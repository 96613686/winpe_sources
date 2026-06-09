# DhcpRegisterConnectionStateNotification

- ea: `0x180008700`
- end: `0x1800088c6`
- name: `DhcpRegisterConnectionStateNotification`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001f90`
- `0x180002c50`
- `0x180008700`
- `0x18000c2c4`
- `0x18000f4ec`
- `0x180010aac`
- `0x180011298`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800087af`
- `RPCRT4!NdrClientCall3` at `0x1800087af`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000876b`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800087cb`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800087f0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000876b`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800087cb`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800087f0`
- `api-ms-win-downlevel-kernel32-l1-1-0!OpenEventW` at `0x180008824`
- `api-ms-win-downlevel-kernel32-l1-1-0!OpenEventW` at `0x180008824`

## pseudocode

```c
__int64 __fastcall DhcpRegisterConnectionStateNotification(unsigned int a1, _QWORD *a2, _QWORD *a3)
{
  char v5; // bl
  char v6; // al
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  LPWSTR v9; // rax
  HANDLE v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rsi
  __int64 v14; // rcx
  void *v15; // rax
  LPCWSTR lpName; // [rsp+78h] [rbp+20h] BYREF

  v5 = a1;
  lpName = 0;
  v6 = xmmword_18001E1E0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    WPP_SF_l(1028, 194, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
    v6 = xmmword_18001E1E0;
  }
  if ( a2 && a3 && (v5 & 0xF) != 0 )
  {
    if ( (v6 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_S(1028, 195, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
    }
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Bu, 0).Pointer;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v9 = GetCommandLineW();
      WPP_SF_DS(1028, 196, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v9);
    }
    if ( !Pointer )
    {
      v10 = OpenEventW(0x100000u, 0, lpName);
      *a2 = v10;
      if ( v10 )
      {
        v13 = -1;
        v14 = -1;
        do
          ++v14;
        while ( lpName[v14] );
        v15 = (void *)DhcpAlloc(2 * v14 + 2, v11, v12);
        *a3 = v15;
        if ( v15 )
        {
          Pointer = 0;
          do
            ++v13;
          while ( lpName[v13] );
          memcpy_0(v15, lpName, 2 * v13 + 2);
        }
        else
        {
          Pointer = 8;
        }
      }
      else
      {
        Pointer = GetLastErrorOrUnknown();
      }
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpMidlUserFree(&lpName);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 197, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180008700  mov     rax, rsp
0x180008703  mov     [rax+8], rbx
0x180008707  mov     [rax+18h], r8
0x18000870b  mov     [rax+10h], rdx
0x18000870f  push    rsi
0x180008710  push    rdi
0x180008711  push    r14
0x180008713  sub     rsp, 40h
0x180008717  mov     r14, r8
0x18000871a  mov     rsi, rdx
0x18000871d  mov     ebx, ecx
0x18000871f  xor     edi, edi
0x180008721  mov     [rax+20h], rdi
0x180008725  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000872b  test    al, 10h
0x18000872d  jz      short loc_18000874E
0x18000872f  mov     edx, 0C2h
0x180008734  mov     ecx, 404h
0x180008739  mov     r9d, ebx
0x18000873c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008743  call    WPP_SF_l
0x180008748  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000874e  test    rsi, rsi
0x180008751  jnz     short loc_18000875D
0x180008753  mov     ebx, 57h ; 'W'
0x180008758  jmp     loc_18000888A
0x18000875d  test    r14, r14
0x180008760  jz      short loc_180008753
0x180008762  test    bl, 0Fh
0x180008765  jz      short loc_180008753
0x180008767  test    al, 10h
0x180008769  jz      short loc_18000878B
0x18000876b  call    cs:__imp_GetCommandLineW
0x180008771  mov     r9, rax
0x180008774  mov     edx, 0C3h
0x180008779  mov     ecx, 404h
0x18000877e  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008785  call    WPP_SF_S
0x18000878a  nop
0x18000878b  mov     [rsp+58h+var_20], rdi
0x180008790  lea     rax, [rsp+58h+lpName]
0x180008795  mov     [rsp+58h+var_30], rax
0x18000879a  mov     dword ptr [rsp+58h+var_38], ebx
0x18000879e  xor     r9d, r9d
0x1800087a1  xor     r8d, r8d; pReturnValue
0x1800087a4  lea     edx, [r9+1Bh]; nProcNum
0x1800087a8  lea     rcx, pProxyInfo; pProxyInfo
0x1800087af  call    cs:__imp_NdrClientCall3
0x1800087b5  mov     rbx, rax
0x1800087b8  mov     [rsp+58h+var_20], rax
0x1800087bd  mov     [rsp+58h+var_28], eax
0x1800087c1  jmp     short loc_1800087E7
0x1800087c3  mov     edi, eax
0x1800087c5  mov     ebx, eax
0x1800087c7  mov     [rsp+58h+var_28], eax
0x1800087cb  call    cs:__imp_GetCommandLineW
0x1800087d1  mov     rdx, rax
0x1800087d4  mov     ecx, ebx
0x1800087d6  call    TraceRpcException
0x1800087db  xor     edi, edi
0x1800087dd  mov     r14, [rsp+58h+arg_10]
0x1800087e2  mov     rsi, [rsp+58h+arg_8]
0x1800087e7  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800087ee  jz      short loc_180008814
0x1800087f0  call    cs:__imp_GetCommandLineW
0x1800087f6  mov     edx, 0C4h
0x1800087fb  mov     ecx, 404h
0x180008800  mov     [rsp+58h+var_38], rax
0x180008805  mov     r9d, ebx
0x180008808  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000880f  call    WPP_SF_DS
0x180008814  test    ebx, ebx
0x180008816  jnz     short loc_18000888A
0x180008818  mov     r8, [rsp+58h+lpName]; lpName
0x18000881d  xor     edx, edx; bInheritHandle
0x18000881f  mov     ecx, 100000h; dwDesiredAccess
0x180008824  call    cs:__imp_OpenEventW
0x18000882a  mov     [rsi], rax
0x18000882d  test    rax, rax
0x180008830  jnz     short loc_18000883B
0x180008832  call    GetLastErrorOrUnknown
0x180008837  mov     ebx, eax
0x180008839  jmp     short loc_18000888A
0x18000883b  mov     rax, [rsp+58h+lpName]
0x180008840  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008844  mov     rcx, rsi
0x180008847  inc     rcx
0x18000884a  cmp     [rax+rcx*2], di
0x18000884e  jnz     short loc_180008847
0x180008850  lea     rcx, ds:2[rcx*2]
0x180008858  call    DhcpAlloc
0x18000885d  mov     [r14], rax
0x180008860  test    rax, rax
0x180008863  jnz     short loc_18000886A
0x180008865  lea     ebx, [rax+8]
0x180008868  jmp     short loc_18000888A
0x18000886a  mov     ebx, edi
0x18000886c  mov     rdx, [rsp+58h+lpName]; Src
0x180008871  inc     rsi
0x180008874  cmp     [rdx+rsi*2], di
0x180008878  jnz     short loc_180008871
0x18000887a  lea     r8, ds:2[rsi*2]; Size
0x180008882  mov     rcx, rax; void *
0x180008885  call    memcpy_0
0x18000888a  lea     rcx, [rsp+58h+lpName]
0x18000888f  call    DhcpMidlUserFree
0x180008894  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000889b  jz      short loc_1800088B6
0x18000889d  mov     edx, 0C5h
0x1800088a2  mov     ecx, 404h
0x1800088a7  mov     r9d, ebx
0x1800088aa  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800088b1  call    WPP_SF_d
0x1800088b6  mov     eax, ebx
0x1800088b8  mov     rbx, [rsp+58h+arg_0]
0x1800088bd  add     rsp, 40h
0x1800088c1  pop     r14
0x1800088c3  pop     rdi
0x1800088c4  pop     rsi
0x1800088c5  retn
0x180010c20  push    rbp
0x180010c22  sub     rsp, 30h
0x180010c26  mov     rbp, rdx
0x180010c29  mov     rcx, [rcx]
0x180010c2c  mov     ecx, [rcx]; ExceptionCode
0x180010c2e  call    cs:__imp_I_RpcExceptionFilter
0x180010c34  nop
0x180010c35  add     rsp, 30h
0x180010c39  pop     rbp
0x180010c3a  retn
```
