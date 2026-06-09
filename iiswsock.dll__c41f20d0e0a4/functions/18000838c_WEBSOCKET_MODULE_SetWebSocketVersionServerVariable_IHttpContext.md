# WEBSOCKET_MODULE::SetWebSocketVersionServerVariable(IHttpContext *)

- ea: `0x18000838c`
- end: `0x180008514`
- name: `?SetWebSocketVersionServerVariable@WEBSOCKET_MODULE@@AEAAJPEAVIHttpContext@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(WEBSOCKET_MODULE *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800079b0`

## callees

- `0x18000838c`
- `0x180008600`
- `0x180009010`

## import_xrefs

- `msvcrt!_itow` at `0x180008485`
- `msvcrt!_itow` at `0x180008485`
- `websocket!WebSocketGetGlobalProperty` at `0x1800083e7`
- `websocket!WebSocketGetGlobalProperty` at `0x180008430`
- `websocket!WebSocketGetGlobalProperty` at `0x1800083e7`
- `websocket!WebSocketGetGlobalProperty` at `0x180008430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008401`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008401`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000840f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000840f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000846b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008493`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000846b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008493`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800084e4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800084e4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800083cb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800083cb`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_MODULE::SetWebSocketVersionServerVariable(WEBSOCKET_MODULE *this, struct IHttpContext *a2)
{
  int GlobalProperty; // eax
  int v4; // ebx
  unsigned int v5; // ebx
  HANDLE ProcessHeap; // rax
  char *v7; // rax
  char *v8; // rdi
  char *v9; // r15
  unsigned int v10; // esi
  __int64 v11; // r14
  HANDLE v12; // rax
  SIZE_T dwBytes; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v15[32]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h]
  wchar_t Buffer[12]; // [rsp+60h] [rbp-20h] BYREF

  STRU::STRU((STRU *)v15);
  dwBytes = 4;
  GlobalProperty = WebSocketGetGlobalProperty(6, (char *)&dwBytes + 4, &dwBytes);
  v4 = GlobalProperty;
  if ( GlobalProperty >= 0 )
  {
    v8 = 0;
    v9 = (char *)&dwBytes + 4;
    v10 = 1;
  }
  else
  {
    if ( GlobalProperty != -2147024774 )
      goto LABEL_16;
    v5 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v7 = (char *)HeapAlloc(ProcessHeap, 0, v5);
    v8 = v7;
    if ( !v7 )
    {
      v4 = -2147024882;
      goto LABEL_16;
    }
    v4 = WebSocketGetGlobalProperty(6, v7, &dwBytes);
    if ( v4 < 0 )
    {
LABEL_15:
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v8);
      goto LABEL_16;
    }
    v9 = v8;
    v10 = (unsigned int)dwBytes >> 2;
  }
  v11 = 0;
  if ( v10 )
  {
    while ( 1 )
    {
      if ( (_DWORD)v11 )
      {
        v4 = STRU::Append((STRU *)v15, L", ");
        if ( v4 < 0 )
          break;
      }
      _itow(*(_DWORD *)&v9[4 * v11], Buffer, 10);
      v4 = STRU::Append((STRU *)v15, Buffer);
      if ( v4 < 0 )
        break;
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= v10 )
        goto LABEL_13;
    }
  }
  else
  {
LABEL_13:
    v4 = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, __int64))(*(_QWORD *)a2 + 136LL))(
           a2,
           "WEBSOCKET_VERSION",
           v16);
  }
  if ( v8 )
    goto LABEL_15;
LABEL_16:
  STRU::~STRU((STRU *)v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000838c  mov     [rsp-28h+arg_0], rbx
0x180008391  mov     [rsp-28h+arg_10], rsi
0x180008396  push    rbp
0x180008397  push    rdi
0x180008398  push    r12
0x18000839a  push    r14
0x18000839c  push    r15
0x18000839e  mov     rbp, rsp
0x1800083a1  sub     rsp, 80h
0x1800083a8  mov     rax, cs:__security_cookie
0x1800083af  xor     rax, rsp
0x1800083b2  mov     [rbp+var_8], rax
0x1800083b6  lea     rcx, [rbp+var_58]
0x1800083ba  mov     dword ptr [rbp+dwBytes+4], 0
0x1800083c1  mov     r12, rdx
0x1800083c4  mov     dword ptr [rbp+dwBytes], 0
0x1800083cb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800083d1  mov     esi, 6
0x1800083d6  mov     dword ptr [rbp+dwBytes], 4
0x1800083dd  mov     ecx, esi
0x1800083df  lea     r8, [rbp+dwBytes]
0x1800083e3  lea     rdx, [rbp+dwBytes+4]
0x1800083e7  call    cs:__imp_WebSocketGetGlobalProperty
0x1800083ed  mov     ebx, eax
0x1800083ef  test    eax, eax
0x1800083f1  jns     short loc_18000844B
0x1800083f3  cmp     eax, 8007007Ah
0x1800083f8  jnz     loc_1800084E0
0x1800083fe  mov     ebx, dword ptr [rbp+dwBytes]
0x180008401  call    cs:__imp_GetProcessHeap
0x180008407  mov     r8d, ebx; dwBytes
0x18000840a  xor     edx, edx; dwFlags
0x18000840c  mov     rcx, rax; hHeap
0x18000840f  call    cs:__imp_HeapAlloc
0x180008415  mov     rdi, rax
0x180008418  test    rax, rax
0x18000841b  jnz     short loc_180008427
0x18000841d  mov     ebx, 8007000Eh
0x180008422  jmp     loc_1800084E0
0x180008427  lea     r8, [rbp+dwBytes]
0x18000842b  mov     rdx, rdi
0x18000842e  mov     ecx, esi
0x180008430  call    cs:__imp_WebSocketGetGlobalProperty
0x180008436  mov     ebx, eax
0x180008438  test    eax, eax
0x18000843a  js      loc_1800084CC
0x180008440  mov     esi, dword ptr [rbp+dwBytes]
0x180008443  mov     r15, rdi
0x180008446  shr     esi, 2
0x180008449  jmp     short loc_180008454
0x18000844b  xor     edi, edi
0x18000844d  lea     r15, [rbp+dwBytes+4]
0x180008451  lea     esi, [rdi+1]
0x180008454  xor     r14d, r14d
0x180008457  test    esi, esi
0x180008459  jz      short loc_1800084A7
0x18000845b  test    r14d, r14d
0x18000845e  jz      short loc_180008477
0x180008460  lea     rdx, asc_18000BE68; ", "
0x180008467  lea     rcx, [rbp+var_58]
0x18000846b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180008471  mov     ebx, eax
0x180008473  test    eax, eax
0x180008475  js      short loc_1800084C7
0x180008477  mov     ecx, [r15+r14*4]; Value
0x18000847b  lea     rdx, [rbp+Buffer]; Buffer
0x18000847f  mov     r8d, 0Ah; Radix
0x180008485  call    cs:__imp__itow
0x18000848b  lea     rdx, [rbp+Buffer]
0x18000848f  lea     rcx, [rbp+var_58]
0x180008493  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180008499  mov     ebx, eax
0x18000849b  test    eax, eax
0x18000849d  js      short loc_1800084C7
0x18000849f  inc     r14d
0x1800084a2  cmp     r14d, esi
0x1800084a5  jb      short loc_18000845B
0x1800084a7  mov     rax, [r12]
0x1800084ab  lea     rdx, aWebsocketVersi; "WEBSOCKET_VERSION"
0x1800084b2  mov     r8, [rbp+var_38]
0x1800084b6  mov     rcx, r12
0x1800084b9  mov     rax, [rax+88h]
0x1800084c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084c5  mov     ebx, eax
0x1800084c7  test    rdi, rdi
0x1800084ca  jz      short loc_1800084E0
0x1800084cc  call    cs:__imp_GetProcessHeap
0x1800084d2  mov     r8, rdi; lpMem
0x1800084d5  xor     edx, edx; dwFlags
0x1800084d7  mov     rcx, rax; hHeap
0x1800084da  call    cs:__imp_HeapFree
0x1800084e0  lea     rcx, [rbp+var_58]
0x1800084e4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800084ea  mov     eax, ebx
0x1800084ec  mov     rcx, [rbp+var_8]
0x1800084f0  xor     rcx, rsp; StackCookie
0x1800084f3  call    __security_check_cookie
0x1800084f8  lea     r11, [rsp+80h+var_s0]
0x180008500  mov     rbx, [r11+30h]
0x180008504  mov     rsi, [r11+40h]
0x180008508  mov     rsp, r11
0x18000850b  pop     r15
0x18000850d  pop     r14
0x18000850f  pop     r12
0x180008511  pop     rdi
0x180008512  pop     rbp
0x180008513  retn
```
