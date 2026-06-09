# TeredoRioDestroySockets

- ea: `0x180057660`
- end: `0x18005781c`
- name: `TeredoRioDestroySockets`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180046d9c`
- `0x180056c38`

## callees

- `0x180008210`
- `0x180024250`
- `0x18002e0d0`
- `0x180057660`
- `0x180057824`
- `0x180057f50`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800577ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800577ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057753`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057763`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057773`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057753`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057763`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057773`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800577d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800577d1`
- `WS2_32!__imp_closesocket` at `0x1800576cb`
- `WS2_32!__imp_closesocket` at `0x1800576cb`

## string_xrefs

- `0x1800577ee`: `onecoreuap\net\netio\iphlpsvc\service\io.c`

## pseudocode

```c
__int64 __fastcall TeredoRioDestroySockets(__int64 *a1)
{
  __int64 v1; // rsi
  __int64 result; // rax
  unsigned int v4; // r14d
  __int64 i; // rbp
  __int64 v6; // rbx
  SOCKET v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  v1 = *a1;
  result = EventWriteEnterEx(0x100000, L"TeredoRioDestroySockets");
  if ( v1 )
  {
    if ( a1[17] )
    {
      v4 = *(_DWORD *)(v1 + 2884);
      for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
      {
        v6 = *(_QWORD *)(a1[17] + 8 * i);
        if ( v6 )
        {
          v7 = *(_QWORD *)(v6 + 8);
          if ( v7 != -1 )
          {
            closesocket(v7);
            *(_QWORD *)(v6 + 8) = -1;
          }
          TeredoRioRestorePacketsToTunnel(v6);
          if ( *(_QWORD *)(v6 + 152) )
          {
            (*(void (**)(void))(v1 + 2808))();
            *(_QWORD *)(v6 + 152) = 0;
          }
          v8 = *(void **)(v6 + 168);
          if ( v8 )
          {
            CloseHandle(v8);
            *(_QWORD *)(v6 + 168) = 0;
          }
          v9 = *(void **)(v6 + 160);
          if ( v9 )
          {
            TeredoRioFreeNumaMemory(v9);
            *(_QWORD *)(v6 + 160) = 0;
          }
          if ( *(_BYTE *)(v6 + 20) == 1 )
          {
            DeleteCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
            DeleteCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
            DeleteCriticalSection((LPCRITICAL_SECTION)(v6 + 104));
            *(_BYTE *)(v6 + 20) = 0;
          }
          TeredoRioFreeNumaMemory(*(LPVOID *)(a1[17] + 8 * i));
        }
      }
      HeapFree(*(HANDLE *)(v1 + 2576), 0, (LPVOID)a1[17]);
      a1[17] = 0;
    }
    v10 = (void *)a1[19];
    if ( v10 )
    {
      CloseHandle(v10);
      a1[19] = 0;
    }
    TeredoDereferenceIoEx(v1, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\io.c", 4670);
    return EventWriteLeaveEx(0x100000, L"TeredoRioDestroySockets");
  }
  return result;
}

```

## disassembly

```asm
0x180057660  push    rbx
0x180057662  push    rbp
0x180057663  push    rsi
0x180057664  push    rdi
0x180057665  push    r14
0x180057667  push    r15
0x180057669  sub     rsp, 28h
0x18005766d  mov     rsi, [rcx]
0x180057670  lea     rdx, aTeredoriodestr_0; "TeredoRioDestroySockets"
0x180057677  mov     rdi, rcx
0x18005767a  mov     ecx, 100000h
0x18005767f  call    EventWriteEnterEx
0x180057684  test    rsi, rsi
0x180057687  jz      loc_18005780E
0x18005768d  cmp     qword ptr [rdi+88h], 0
0x180057695  jz      loc_1800577C5
0x18005769b  mov     r14d, [rsi+0B44h]
0x1800576a2  xor     ebp, ebp
0x1800576a4  test    r14d, r14d
0x1800576a7  jz      loc_18005779E
0x1800576ad  mov     rax, [rdi+88h]
0x1800576b4  mov     rbx, [rax+rbp*8]
0x1800576b8  test    rbx, rbx
0x1800576bb  jz      loc_180057793
0x1800576c1  mov     rcx, [rbx+8]; s
0x1800576c5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800576c9  jz      short loc_1800576DF
0x1800576cb  call    cs:__imp_closesocket
0x1800576d2  nop     dword ptr [rax+rax+00h]
0x1800576d7  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800576df  mov     rcx, rbx
0x1800576e2  call    TeredoRioRestorePacketsToTunnel
0x1800576e7  mov     rcx, [rbx+98h]
0x1800576ee  test    rcx, rcx
0x1800576f1  jz      short loc_18005770A
0x1800576f3  mov     rax, [rsi+0AF8h]
0x1800576fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576ff  mov     qword ptr [rbx+98h], 0
0x18005770a  mov     rcx, [rbx+0A8h]; hObject
0x180057711  test    rcx, rcx
0x180057714  jz      short loc_18005772D
0x180057716  call    cs:__imp_CloseHandle
0x18005771d  nop     dword ptr [rax+rax+00h]
0x180057722  mov     qword ptr [rbx+0A8h], 0
0x18005772d  mov     rcx, [rbx+0A0h]; lpAddress
0x180057734  test    rcx, rcx
0x180057737  jz      short loc_180057749
0x180057739  call    TeredoRioFreeNumaMemory
0x18005773e  mov     qword ptr [rbx+0A0h], 0
0x180057749  cmp     byte ptr [rbx+14h], 1
0x18005774d  jnz     short loc_180057783
0x18005774f  lea     rcx, [rbx+18h]; lpCriticalSection
0x180057753  call    cs:__imp_DeleteCriticalSection
0x18005775a  nop     dword ptr [rax+rax+00h]
0x18005775f  lea     rcx, [rbx+40h]; lpCriticalSection
0x180057763  call    cs:__imp_DeleteCriticalSection
0x18005776a  nop     dword ptr [rax+rax+00h]
0x18005776f  lea     rcx, [rbx+68h]; lpCriticalSection
0x180057773  call    cs:__imp_DeleteCriticalSection
0x18005777a  nop     dword ptr [rax+rax+00h]
0x18005777f  mov     byte ptr [rbx+14h], 0
0x180057783  mov     rcx, [rdi+88h]
0x18005778a  mov     rcx, [rcx+rbp*8]; lpAddress
0x18005778e  call    TeredoRioFreeNumaMemory
0x180057793  inc     ebp
0x180057795  cmp     ebp, r14d
0x180057798  jb      loc_1800576AD
0x18005779e  mov     r8, [rdi+88h]; lpMem
0x1800577a5  xor     edx, edx; dwFlags
0x1800577a7  mov     rcx, [rsi+0A10h]; hHeap
0x1800577ae  call    cs:__imp_HeapFree
0x1800577b5  nop     dword ptr [rax+rax+00h]
0x1800577ba  mov     qword ptr [rdi+88h], 0
0x1800577c5  mov     rcx, [rdi+98h]; hObject
0x1800577cc  test    rcx, rcx
0x1800577cf  jz      short loc_1800577E8
0x1800577d1  call    cs:__imp_CloseHandle
0x1800577d8  nop     dword ptr [rax+rax+00h]
0x1800577dd  mov     qword ptr [rdi+98h], 0
0x1800577e8  mov     r8d, 123Eh
0x1800577ee  lea     rdx, aOnecoreuapNetN_22; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800577f5  mov     rcx, rsi
0x1800577f8  call    TeredoDereferenceIoEx
0x1800577fd  lea     rdx, aTeredoriodestr_0; "TeredoRioDestroySockets"
0x180057804  mov     ecx, 100000h
0x180057809  call    EventWriteLeaveEx
0x18005780e  add     rsp, 28h
0x180057812  pop     r15
0x180057814  pop     r14
0x180057816  pop     rdi
0x180057817  pop     rsi
0x180057818  pop     rbp
0x180057819  pop     rbx
0x18005781a  retn
```
