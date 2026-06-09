# GlobalPortInit

- ea: `0x180012054`
- end: `0x18001225b`
- name: `GlobalPortInit`
- size: `519`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002670`
- `0x180002d00`
- `0x180002dc0`
- `0x180004dd0`
- `0x180005b20`
- `0x1800064e0`
- `0x1800078d0`
- `0x180007f30`
- `0x1800082b0`
- `0x18000fea0`

## callees

- `0x180012054`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012190`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012088`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012243`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012243`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800121f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001221a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800121f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001221a`
- `FLTLIB!FilterConnectCommunicationPort` at `0x1800120e9`
- `FLTLIB!FilterConnectCommunicationPort` at `0x18001215f`
- `FLTLIB!FilterConnectCommunicationPort` at `0x1800120e9`
- `FLTLIB!FilterConnectCommunicationPort` at `0x18001215f`

## pseudocode

```c
__int64 __fastcall GlobalPortInit(char a1)
{
  int v1; // ebx
  int v3; // edi
  char v4; // bp
  signed int LastError; // eax
  __int64 Context; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  Context = 0;
  v3 = a1 != 0 ? 4 : 2;
  if ( (dword_18002ABE8 & v3) == 0 )
  {
    EnterCriticalSection(&_G);
    v4 = dword_18002ABE8;
    if ( (dword_18002ABE8 & v3) != 0 )
    {
LABEL_24:
      LeaveCriticalSection(&_G);
      return (unsigned int)v1;
    }
    if ( (dword_18002ABE8 & 2) == 0 )
    {
      Context = 0x163706C43LL;
      v1 = FilterConnectCommunicationPort(L"\\CLDMSGPORT", 0, &Context, 8u, 0, &hPort);
      if ( v1 < 0 )
      {
        if ( !a1 )
        {
LABEL_20:
          if ( (v4 & 2) == 0 )
          {
            if ( hPort != (HANDLE)-1LL )
            {
              CloseHandle(hPort);
              hPort = (HANDLE)-1LL;
            }
            dword_18002ABE8 &= ~2u;
          }
          goto LABEL_24;
        }
LABEL_17:
        if ( (v4 & 4) == 0 && *(&hPort + 1) != (HANDLE)-1LL )
        {
          CloseHandle(*(&hPort + 1));
          *(&hPort + 1) = (HANDLE)-1LL;
        }
        goto LABEL_20;
      }
      dword_18002ABE8 |= 2u;
    }
    if ( !a1 || (dword_18002ABE8 & 4) != 0 )
      goto LABEL_24;
    Context = 0x263706C43LL;
    v1 = FilterConnectCommunicationPort(L"\\CLDMSGPORT", 0, &Context, 8u, 0, &hPort + 1);
    if ( v1 >= 0 )
    {
      qword_18002AC08 = (__int64)CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SyncMessageThread, 0, 0, 0);
      if ( qword_18002AC08 )
      {
        v1 = 0;
      }
      else
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v1 >= 0 )
      {
        dword_18002ABE8 |= 4u;
        goto LABEL_24;
      }
    }
    goto LABEL_17;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180012054  push    rbx
0x180012056  push    rbp
0x180012057  push    rsi
0x180012058  push    rdi
0x180012059  sub     rsp, 38h
0x18001205d  xor     ebx, ebx
0x18001205f  mov     al, cl
0x180012061  neg     al
0x180012063  mov     [rsp+58h+Context], rbx
0x180012068  mov     eax, cs:dword_18002ABE8
0x18001206e  mov     sil, cl
0x180012071  sbb     edi, edi
0x180012073  and     edi, 2
0x180012076  add     edi, 2
0x180012079  test    edi, eax
0x18001207b  jnz     loc_18001224F
0x180012081  lea     rcx, __G; lpCriticalSection
0x180012088  call    cs:__imp_EnterCriticalSection
0x18001208f  nop     dword ptr [rax+rax+00h]
0x180012094  mov     ebp, cs:dword_18002ABE8
0x18001209a  mov     eax, cs:dword_18002ABE8
0x1800120a0  test    edi, eax
0x1800120a2  jnz     loc_18001223C
0x1800120a8  mov     eax, cs:dword_18002ABE8
0x1800120ae  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800120b2  test    al, 2
0x1800120b4  jnz     short loc_18001210E
0x1800120b6  lea     rax, hPort
0x1800120bd  mov     dword ptr [rsp+58h+Context], 63706C43h
0x1800120c5  mov     [rsp+58h+hPort], rax; hPort
0x1800120ca  lea     r9d, [rbx+8]; wSizeOfContext
0x1800120ce  lea     r8, [rsp+58h+Context]; lpContext
0x1800120d3  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800120d8  xor     edx, edx; dwOptions
0x1800120da  mov     dword ptr [rsp+58h+Context+4], 1
0x1800120e2  lea     rcx, PortName; "\\CLDMSGPORT"
0x1800120e9  call    cs:__imp_FilterConnectCommunicationPort
0x1800120f0  nop     dword ptr [rax+rax+00h]
0x1800120f5  mov     ebx, eax
0x1800120f7  test    eax, eax
0x1800120f9  js      loc_1800121DE
0x1800120ff  mov     ecx, cs:dword_18002ABE8
0x180012105  or      ecx, 2
0x180012108  mov     cs:dword_18002ABE8, ecx
0x18001210e  test    sil, sil
0x180012111  jz      loc_1800121DA
0x180012117  mov     edx, cs:dword_18002ABE8
0x18001211d  test    dl, 4
0x180012120  jnz     loc_1800121DA
0x180012126  lea     rax, hPort+8
0x18001212d  mov     dword ptr [rsp+58h+Context], 63706C43h
0x180012135  mov     [rsp+58h+hPort], rax; hPort
0x18001213a  lea     r8, [rsp+58h+Context]; lpContext
0x18001213f  mov     r9d, 8; wSizeOfContext
0x180012145  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001214e  xor     edx, edx; dwOptions
0x180012150  mov     dword ptr [rsp+58h+Context+4], 2
0x180012158  lea     rcx, PortName; "\\CLDMSGPORT"
0x18001215f  call    cs:__imp_FilterConnectCommunicationPort
0x180012166  nop     dword ptr [rax+rax+00h]
0x18001216b  mov     ebx, eax
0x18001216d  test    eax, eax
0x18001216f  js      short loc_1800121E3
0x180012171  mov     [rsp+58h+hPort], 0; lpThreadId
0x18001217a  lea     r8, SyncMessageThread; lpStartAddress
0x180012181  xor     r9d, r9d; lpParameter
0x180012184  mov     dword ptr [rsp+58h+lpSecurityAttributes], 0; dwCreationFlags
0x18001218c  xor     edx, edx; dwStackSize
0x18001218e  xor     ecx, ecx; lpThreadAttributes
0x180012190  call    cs:__imp_CreateThread
0x180012197  nop     dword ptr [rax+rax+00h]
0x18001219c  mov     cs:qword_18002AC08, rax
0x1800121a3  test    rax, rax
0x1800121a6  jz      short loc_1800121AC
0x1800121a8  xor     ebx, ebx
0x1800121aa  jmp     short loc_1800121C7
0x1800121ac  call    cs:__imp_GetLastError
0x1800121b3  nop     dword ptr [rax+rax+00h]
0x1800121b8  mov     ebx, eax
0x1800121ba  test    eax, eax
0x1800121bc  jle     short loc_1800121C7
0x1800121be  movzx   ebx, ax
0x1800121c1  or      ebx, 80070000h
0x1800121c7  test    ebx, ebx
0x1800121c9  js      short loc_1800121E3
0x1800121cb  mov     eax, cs:dword_18002ABE8
0x1800121d1  or      eax, 4
0x1800121d4  mov     cs:dword_18002ABE8, eax
0x1800121da  test    ebx, ebx
0x1800121dc  jns     short loc_18001223C
0x1800121de  test    sil, sil
0x1800121e1  jz      short loc_180012208
0x1800121e3  test    bpl, 4
0x1800121e7  jnz     short loc_180012208
0x1800121e9  mov     rcx, qword ptr cs:hPort+8; hObject
0x1800121f0  cmp     rcx, rdi
0x1800121f3  jz      short loc_180012208
0x1800121f5  call    cs:__imp_CloseHandle
0x1800121fc  nop     dword ptr [rax+rax+00h]
0x180012201  mov     qword ptr cs:hPort+8, rdi
0x180012208  test    bpl, 2
0x18001220c  jnz     short loc_18001223C
0x18001220e  mov     rcx, qword ptr cs:hPort; hObject
0x180012215  cmp     rcx, rdi
0x180012218  jz      short loc_18001222D
0x18001221a  call    cs:__imp_CloseHandle
0x180012221  nop     dword ptr [rax+rax+00h]
0x180012226  mov     qword ptr cs:hPort, rdi
0x18001222d  mov     eax, cs:dword_18002ABE8
0x180012233  and     eax, 0FFFFFFFDh
0x180012236  mov     cs:dword_18002ABE8, eax
0x18001223c  lea     rcx, __G; lpCriticalSection
0x180012243  call    cs:__imp_LeaveCriticalSection
0x18001224a  nop     dword ptr [rax+rax+00h]
0x18001224f  mov     eax, ebx
0x180012251  add     rsp, 38h
0x180012255  pop     rdi
0x180012256  pop     rsi
0x180012257  pop     rbp
0x180012258  pop     rbx
0x180012259  retn
```
