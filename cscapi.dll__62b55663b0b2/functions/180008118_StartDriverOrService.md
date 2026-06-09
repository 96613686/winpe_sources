# _StartDriverOrService

- ea: `0x180008118`
- end: `0x1800082d6`
- name: `_StartDriverOrService`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800073f0`

## callees

- `0x180004f10`
- `0x180007c34`
- `0x180007dd4`
- `0x180008118`
- `0x180009490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008276`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800081f3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800081f3`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180008167`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180008167`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800082b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800082b7`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800081dd`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800081dd`

## string_xrefs

- `0x180008131`: `CscService`

## pseudocode

```c
__int64 StartDriverOrService()
{
  unsigned int v0; // ebx
  __int64 v1; // r8
  unsigned int i; // esi
  DWORD LastError; // eax
  _QWORD *v4; // rcx
  DWORD v5; // eax
  int v6; // r8d
  DWORD pcbBytesNeeded; // [rsp+38h] [rbp-60h] BYREF
  BYTE Buffer[16]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v10; // [rsp+50h] [rbp-48h]
  int v11; // [rsp+60h] [rbp-38h]

  v0 = OpenDriverOrService(L"CscService", 0x80000010);
  if ( !v0 )
  {
    if ( StartServiceW(0, 0, 0) )
    {
      pcbBytesNeeded = 0;
      *(_OWORD *)Buffer = 0;
      v11 = 0;
      v10 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 22), 16, v1, L"CscService");
      for ( i = 0; ; ++i )
      {
        if ( i >= 0x1E )
        {
LABEL_16:
          v4 = WPP_GLOBAL_Control;
LABEL_17:
          if ( *(_DWORD *)&Buffer[4] != 4 )
          {
            v0 = 1062;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 188) & 1) != 0 )
              WPP_SF_S(v4[22], 18, v1, L"CscService");
          }
          goto LABEL_24;
        }
        if ( !QueryServiceStatusEx(0, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
          break;
        if ( *(_DWORD *)&Buffer[4] != 2 )
          goto LABEL_16;
        Sleep(0x3E8u);
      }
      LastError = GetLastError();
      v0 = LastError;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      {
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), 17, v1, (unsigned int)L"CscService", LastError);
        v4 = WPP_GLOBAL_Control;
      }
      if ( !v0 )
        goto LABEL_17;
    }
    else
    {
      v5 = GetLastError();
      v0 = v5;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), 19, v6, (unsigned int)L"CscService", v5);
    }
LABEL_24:
    CloseServiceHandle(0);
  }
  return v0;
}

```

## disassembly

```asm
0x180008118  push    rbx
0x18000811a  push    rsi
0x18000811b  push    rdi
0x18000811c  push    r14
0x18000811e  sub     rsp, 78h
0x180008122  mov     rax, cs:__security_cookie
0x180008129  xor     rax, rsp
0x18000812c  mov     [rsp+98h+var_30], rax
0x180008131  lea     r14, g_szCscServiceName; "CscService"
0x180008138  mov     [rsp+98h+hService], 0
0x180008141  mov     rcx, r14; lpServiceName
0x180008144  lea     r8, [rsp+98h+hService]
0x180008149  mov     edx, 80000010h; dwDesiredAccess
0x18000814e  call    _OpenDriverOrService
0x180008153  mov     ebx, eax
0x180008155  test    eax, eax
0x180008157  jnz     loc_1800082BD
0x18000815d  mov     rcx, [rsp+98h+hService]; hService
0x180008162  xor     r8d, r8d; lpServiceArgVectors
0x180008165  xor     edx, edx; dwNumServiceArgs
0x180008167  call    cs:__imp_StartServiceW
0x18000816d  test    eax, eax
0x18000816f  jz      loc_180008276
0x180008175  xorps   xmm0, xmm0
0x180008178  mov     [rsp+98h+var_60], ebx
0x18000817c  xor     eax, eax
0x18000817e  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x180008183  mov     [rsp+98h+var_38], eax
0x180008187  movups  [rsp+98h+var_48], xmm0
0x18000818c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008193  lea     rdi, WPP_GLOBAL_Control
0x18000819a  cmp     rcx, rdi
0x18000819d  jz      short loc_1800081BA
0x18000819f  test    byte ptr [rcx+0BCh], 1
0x1800081a6  jz      short loc_1800081BA
0x1800081a8  mov     rcx, [rcx+0B0h]
0x1800081af  lea     edx, [rbx+10h]
0x1800081b2  mov     r9, r14
0x1800081b5  call    WPP_SF_S
0x1800081ba  xor     esi, esi
0x1800081bc  cmp     esi, 1Eh
0x1800081bf  jnb     short loc_18000823F
0x1800081c1  mov     rcx, [rsp+98h+hService]; hService
0x1800081c6  lea     rax, [rsp+98h+var_60]
0x1800081cb  mov     r9d, 24h ; '$'; cbBufSize
0x1800081d1  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800081d6  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x1800081db  xor     edx, edx; InfoLevel
0x1800081dd  call    cs:__imp_QueryServiceStatusEx
0x1800081e3  test    eax, eax
0x1800081e5  jz      short loc_1800081FD
0x1800081e7  cmp     dword ptr [rsp+98h+Buffer+4], 2
0x1800081ec  jnz     short loc_18000823F
0x1800081ee  mov     ecx, 3E8h; dwMilliseconds
0x1800081f3  call    cs:__imp_Sleep
0x1800081f9  inc     esi
0x1800081fb  jmp     short loc_1800081BC
0x1800081fd  call    cs:__imp_GetLastError
0x180008203  mov     ebx, eax
0x180008205  mov     rcx, cs:WPP_GLOBAL_Control
0x18000820c  cmp     rcx, rdi
0x18000820f  jz      short loc_180008239
0x180008211  test    byte ptr [rcx+0BCh], 1
0x180008218  jz      short loc_180008239
0x18000821a  mov     rcx, [rcx+0B0h]
0x180008221  mov     edx, 11h
0x180008226  mov     r9, r14
0x180008229  mov     dword ptr [rsp+98h+pcbBytesNeeded], eax
0x18000822d  call    WPP_SF_Sd
0x180008232  mov     rcx, cs:WPP_GLOBAL_Control
0x180008239  test    ebx, ebx
0x18000823b  jnz     short loc_1800082B2
0x18000823d  jmp     short loc_180008246
0x18000823f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008246  cmp     dword ptr [rsp+98h+Buffer+4], 4
0x18000824b  jz      short loc_1800082B2
0x18000824d  mov     ebx, 426h
0x180008252  cmp     rcx, rdi
0x180008255  jz      short loc_1800082B2
0x180008257  test    byte ptr [rcx+0BCh], 1
0x18000825e  jz      short loc_1800082B2
0x180008260  mov     rcx, [rcx+0B0h]
0x180008267  mov     edx, 12h
0x18000826c  mov     r9, r14
0x18000826f  call    WPP_SF_S
0x180008274  jmp     short loc_1800082B2
0x180008276  call    cs:__imp_GetLastError
0x18000827c  mov     ebx, eax
0x18000827e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008285  lea     rdi, WPP_GLOBAL_Control
0x18000828c  cmp     rcx, rdi
0x18000828f  jz      short loc_1800082B2
0x180008291  test    byte ptr [rcx+0BCh], 1
0x180008298  jz      short loc_1800082B2
0x18000829a  mov     rcx, [rcx+0B0h]
0x1800082a1  mov     edx, 13h
0x1800082a6  mov     r9, r14
0x1800082a9  mov     dword ptr [rsp+98h+pcbBytesNeeded], eax
0x1800082ad  call    WPP_SF_Sd
0x1800082b2  mov     rcx, [rsp+98h+hService]; hSCObject
0x1800082b7  call    cs:__imp_CloseServiceHandle
0x1800082bd  mov     eax, ebx
0x1800082bf  mov     rcx, [rsp+98h+var_30]
0x1800082c4  xor     rcx, rsp; StackCookie
0x1800082c7  call    __security_check_cookie
0x1800082cc  add     rsp, 78h
0x1800082d0  pop     r14
0x1800082d2  pop     rdi
0x1800082d3  pop     rsi
0x1800082d4  pop     rbx
0x1800082d5  retn
```
