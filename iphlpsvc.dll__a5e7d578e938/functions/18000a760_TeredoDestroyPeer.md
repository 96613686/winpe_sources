# TeredoDestroyPeer

- ea: `0x18000a760`
- end: `0x18000a8aa`
- name: `TeredoDestroyPeer`
- size: `330`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `13`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009910`
- `0x180009eb0`
- `0x18000a150`
- `0x18000a360`
- `0x18000a5a0`
- `0x18000afb0`
- `0x18000cb90`
- `0x18000fd90`
- `0x180010160`
- `0x1800102e0`
- `0x180016ee0`
- `0x18001b598`
- `0x180032420`

## callees

- `0x18000a760`
- `0x18000d7c0`
- `0x180051eec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a825`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a806`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a806`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a7d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a7d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a7c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a7c7`

## string_xrefs

- `0x18000a834`: `onecoreuap\net\netio\iphlpsvc\service\peer.c`
- `0x18000a7e2`: `CloseThreadpoolWait complete`

## pseudocode

```c
__int64 __fastcall TeredoDestroyPeer(LPVOID lpMem)
{
  volatile signed __int32 *v1; // rsi
  void *v3; // rcx
  void *v4; // rcx
  struct _TP_WAIT *v5; // rdi
  void *v6; // rcx
  volatile signed __int32 v7; // edx
  __int64 v8; // rax
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-38h]

  v1 = (volatile signed __int32 *)*((_QWORD *)lpMem + 132);
  v3 = (void *)*((_QWORD *)lpMem + 135);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)lpMem + 135) = 0;
  }
  v4 = (void *)*((_QWORD *)lpMem + 211);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)lpMem + 211) = 0;
  }
  v5 = (struct _TP_WAIT *)*((_QWORD *)lpMem + 108);
  if ( v5 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)lpMem + 108), 0, 0);
    CloseThreadpoolWait(v5);
    EventWrite0(0x100000, L"CloseThreadpoolWait complete");
    *((_QWORD *)lpMem + 108) = 0;
  }
  v6 = (void *)*((_QWORD *)lpMem + 107);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)lpMem + 107) = 0;
  }
  HeapFree(*((HANDLE *)v1 + 1101), 0, lpMem);
  v10 = 384;
  EventWrite0(
    0x100000,
    L"TeredoDereferenceClient: --%d @ %ls:%u",
    *(unsigned int *)v1,
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\peer.c",
    v10);
  v7 = *v1;
  v8 = 5LL * (_InterlockedExchangeAdd(v1 + 2, 1u) & 0x3F);
  v1[2 * v8 + 4] = v7;
  v1[2 * v8 + 8] = 384;
  *(_QWORD *)&v1[2 * v8 + 6] = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\peer.c";
  v1[2 * v8 + 12] = 1;
  *(_QWORD *)&v1[2 * v8 + 10] = 0;
  result = (unsigned int)_InterlockedExchangeAdd(v1, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return TeredoCleanupClient(v1);
  return result;
}

```

## disassembly

```asm
0x18000a760  push    rbx
0x18000a762  push    rbp
0x18000a763  push    rsi
0x18000a764  push    rdi
0x18000a765  sub     rsp, 38h
0x18000a769  mov     rsi, [rcx+420h]
0x18000a770  mov     rbx, rcx
0x18000a773  mov     rcx, [rcx+438h]; hObject
0x18000a77a  xor     ebp, ebp
0x18000a77c  test    rcx, rcx
0x18000a77f  jz      short loc_18000A794
0x18000a781  call    cs:__imp_CloseHandle
0x18000a788  nop     dword ptr [rax+rax+00h]
0x18000a78d  mov     [rbx+438h], rbp
0x18000a794  mov     rcx, [rbx+698h]; hObject
0x18000a79b  test    rcx, rcx
0x18000a79e  jz      short loc_18000A7B3
0x18000a7a0  call    cs:__imp_CloseHandle
0x18000a7a7  nop     dword ptr [rax+rax+00h]
0x18000a7ac  mov     [rbx+698h], rbp
0x18000a7b3  mov     rdi, [rbx+360h]
0x18000a7ba  test    rdi, rdi
0x18000a7bd  jz      short loc_18000A7FA
0x18000a7bf  xor     r8d, r8d; pftTimeout
0x18000a7c2  xor     edx, edx; h
0x18000a7c4  mov     rcx, rdi; pwa
0x18000a7c7  call    cs:__imp_SetThreadpoolWait
0x18000a7ce  nop     dword ptr [rax+rax+00h]
0x18000a7d3  mov     rcx, rdi; pwa
0x18000a7d6  call    cs:__imp_CloseThreadpoolWait
0x18000a7dd  nop     dword ptr [rax+rax+00h]
0x18000a7e2  lea     rdx, aClosethreadpoo; "CloseThreadpoolWait complete"
0x18000a7e9  mov     ecx, 100000h
0x18000a7ee  call    EventWrite0
0x18000a7f3  mov     [rbx+360h], rbp
0x18000a7fa  mov     rcx, [rbx+358h]; hObject
0x18000a801  test    rcx, rcx
0x18000a804  jz      short loc_18000A819
0x18000a806  call    cs:__imp_CloseHandle
0x18000a80d  nop     dword ptr [rax+rax+00h]
0x18000a812  mov     [rbx+358h], rbp
0x18000a819  mov     rcx, [rsi+2268h]; hHeap
0x18000a820  mov     r8, rbx; lpMem
0x18000a823  xor     edx, edx; dwFlags
0x18000a825  call    cs:__imp_HeapFree
0x18000a82c  nop     dword ptr [rax+rax+00h]
0x18000a831  mov     r8d, [rsi]
0x18000a834  lea     rbx, aOnecoreuapNetN_24; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000a83b  mov     r9, rbx
0x18000a83e  mov     [rsp+58h+var_38], 180h
0x18000a846  lea     rdx, aTeredoderefere; "TeredoDereferenceClient: --%d @ %ls:%u"
0x18000a84d  mov     ecx, 100000h
0x18000a852  call    EventWrite0
0x18000a857  mov     edx, [rsi]
0x18000a859  mov     eax, 1
0x18000a85e  lock xadd [rsi+8], eax
0x18000a863  and     eax, 3Fh
0x18000a866  lea     rax, [rax+rax*4]
0x18000a86a  mov     [rsi+rax*8+10h], edx
0x18000a86e  mov     dword ptr [rsi+rax*8+20h], 180h
0x18000a876  mov     [rsi+rax*8+18h], rbx
0x18000a87b  mov     dword ptr [rsi+rax*8+30h], 1
0x18000a883  mov     [rsi+rax*8+28h], rbp
0x18000a888  mov     eax, 0FFFFFFFFh
0x18000a88d  lock xadd [rsi], eax
0x18000a891  cmp     eax, 1
0x18000a894  jz      short loc_18000A8A0
0x18000a896  add     rsp, 38h
0x18000a89a  pop     rdi
0x18000a89b  pop     rsi
0x18000a89c  pop     rbp
0x18000a89d  pop     rbx
0x18000a89e  retn
0x18000a8a0  mov     rcx, rsi
0x18000a8a3  call    TeredoCleanupClient
0x18000a8a8  jmp     short loc_18000A896
```
