# TeredoDereferencePeerEx

- ea: `0x18000d5c0`
- end: `0x18000d79c`
- name: `TeredoDereferencePeerEx`
- size: `476`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000afa0`
- `0x18000f830`
- `0x18000fd80`
- `0x180016ed0`
- `0x18001cf90`
- `0x18003a8f0`
- `0x18003efbc`

## callees

- `0x18000d5c0`
- `0x18000d7b0`
- `0x180051f2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d70a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d70a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d6b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d6b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d6a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d6a7`

## string_xrefs

- `0x18000d719`: `onecoreuap\net\netio\iphlpsvc\service\peer.c`
- `0x18000d6c2`: `CloseThreadpoolWait complete`

## pseudocode

```c
__int64 __fastcall TeredoDereferencePeerEx(unsigned int *lpMem, __int64 a2, volatile signed __int32 a3)
{
  unsigned int v3; // r9d
  volatile signed __int32 *v5; // roff
  __int64 v6; // rax
  __int64 result; // rax
  void *v8; // rcx
  volatile signed __int32 *v9; // r14
  void *v10; // rcx
  struct _TP_WAIT *v11; // rdi
  void *v12; // rcx
  volatile signed __int32 v13; // edx
  __int64 v14; // [rsp+20h] [rbp-18h]

  v3 = lpMem[4];
  v5 = (volatile signed __int32 *)(*((_QWORD *)lpMem + 132) + 2576LL);
  v6 = 5LL * (_InterlockedExchangeAdd(v5, 1u) & 0x3F);
  v5[2 * v6 + 2] = v3;
  *(_QWORD *)&v5[2 * v6 + 4] = a2;
  v5[2 * v6 + 6] = a3;
  v5[2 * v6 + 10] = 1;
  *(_QWORD *)&v5[2 * v6 + 8] = lpMem;
  EventWrite0(0x100000, L"TeredoDereferencePeerEx: --%d @ %ls:%u", lpMem[4], a2, a3);
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 4, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    v8 = (void *)*((_QWORD *)lpMem + 135);
    v9 = (volatile signed __int32 *)*((_QWORD *)lpMem + 132);
    if ( v8 )
    {
      CloseHandle(v8);
      *((_QWORD *)lpMem + 135) = 0;
    }
    v10 = (void *)*((_QWORD *)lpMem + 211);
    if ( v10 )
    {
      CloseHandle(v10);
      *((_QWORD *)lpMem + 211) = 0;
    }
    v11 = (struct _TP_WAIT *)*((_QWORD *)lpMem + 108);
    if ( v11 )
    {
      SetThreadpoolWait(*((PTP_WAIT *)lpMem + 108), 0, 0);
      CloseThreadpoolWait(v11);
      EventWrite0(0x100000, L"CloseThreadpoolWait complete");
      *((_QWORD *)lpMem + 108) = 0;
    }
    v12 = (void *)*((_QWORD *)lpMem + 107);
    if ( v12 )
    {
      CloseHandle(v12);
      *((_QWORD *)lpMem + 107) = 0;
    }
    HeapFree(*((HANDLE *)v9 + 1101), 0, lpMem);
    LODWORD(v14) = 384;
    EventWrite0(
      0x100000,
      L"TeredoDereferenceClient: --%d @ %ls:%u",
      *(unsigned int *)v9,
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\peer.c",
      v14);
    v13 = *v9;
    result = 5LL * (_InterlockedExchangeAdd(v9 + 2, 1u) & 0x3F);
    v9[2 * result + 4] = v13;
    v9[2 * result + 8] = 384;
    *(_QWORD *)&v9[2 * result + 6] = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\peer.c";
    v9[2 * result + 12] = 1;
    *(_QWORD *)&v9[2 * result + 10] = 0;
    if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
      return TeredoCleanupClient(v9);
  }
  return result;
}

```

## disassembly

```asm
0x18000d5c0  mov     [rsp+arg_18], rbx
0x18000d5c5  push    rsi
0x18000d5c6  sub     rsp, 30h
0x18000d5ca  mov     r9d, [rcx+10h]
0x18000d5ce  mov     rbx, rcx
0x18000d5d1  mov     rcx, [rcx+420h]
0x18000d5d8  mov     eax, 1
0x18000d5dd  add     rcx, 0A10h
0x18000d5e4  lock xadd [rcx], eax
0x18000d5e8  and     eax, 3Fh
0x18000d5eb  mov     dword ptr [rsp+38h+var_18], r8d
0x18000d5f0  lea     rax, [rax+rax*4]
0x18000d5f4  mov     [rcx+rax*8+8], r9d
0x18000d5f9  mov     r9, rdx
0x18000d5fc  mov     [rcx+rax*8+10h], rdx
0x18000d601  lea     rdx, aTeredoderefere_0; "TeredoDereferencePeerEx: --%d @ %ls:%u"
0x18000d608  mov     [rcx+rax*8+18h], r8d
0x18000d60d  mov     dword ptr [rcx+rax*8+28h], 1
0x18000d615  mov     [rcx+rax*8+20h], rbx
0x18000d61a  mov     ecx, 100000h
0x18000d61f  mov     r8d, [rbx+10h]
0x18000d623  call    EventWrite0
0x18000d628  mov     esi, 0FFFFFFFFh
0x18000d62d  mov     eax, esi
0x18000d62f  lock xadd [rbx+10h], eax
0x18000d634  cmp     eax, 1
0x18000d637  jnz     loc_18000D786
0x18000d63d  mov     rcx, [rbx+438h]; hObject
0x18000d644  mov     [rsp+38h+arg_0], rbp
0x18000d649  xor     ebp, ebp
0x18000d64b  mov     [rsp+38h+arg_8], rdi
0x18000d650  mov     [rsp+38h+arg_10], r14
0x18000d655  mov     r14, [rbx+420h]
0x18000d65c  test    rcx, rcx
0x18000d65f  jz      short loc_18000D674
0x18000d661  call    cs:__imp_CloseHandle
0x18000d668  nop     dword ptr [rax+rax+00h]
0x18000d66d  mov     [rbx+438h], rbp
0x18000d674  mov     rcx, [rbx+698h]; hObject
0x18000d67b  test    rcx, rcx
0x18000d67e  jz      short loc_18000D693
0x18000d680  call    cs:__imp_CloseHandle
0x18000d687  nop     dword ptr [rax+rax+00h]
0x18000d68c  mov     [rbx+698h], rbp
0x18000d693  mov     rdi, [rbx+360h]
0x18000d69a  test    rdi, rdi
0x18000d69d  jz      short loc_18000D6DA
0x18000d69f  xor     r8d, r8d; pftTimeout
0x18000d6a2  xor     edx, edx; h
0x18000d6a4  mov     rcx, rdi; pwa
0x18000d6a7  call    cs:__imp_SetThreadpoolWait
0x18000d6ae  nop     dword ptr [rax+rax+00h]
0x18000d6b3  mov     rcx, rdi; pwa
0x18000d6b6  call    cs:__imp_CloseThreadpoolWait
0x18000d6bd  nop     dword ptr [rax+rax+00h]
0x18000d6c2  lea     rdx, aClosethreadpoo; "CloseThreadpoolWait complete"
0x18000d6c9  mov     ecx, 100000h
0x18000d6ce  call    EventWrite0
0x18000d6d3  mov     [rbx+360h], rbp
0x18000d6da  mov     rcx, [rbx+358h]; hObject
0x18000d6e1  mov     rdi, [rsp+38h+arg_8]
0x18000d6e6  test    rcx, rcx
0x18000d6e9  jz      short loc_18000D6FE
0x18000d6eb  call    cs:__imp_CloseHandle
0x18000d6f2  nop     dword ptr [rax+rax+00h]
0x18000d6f7  mov     [rbx+358h], rbp
0x18000d6fe  mov     rcx, [r14+2268h]; hHeap
0x18000d705  mov     r8, rbx; lpMem
0x18000d708  xor     edx, edx; dwFlags
0x18000d70a  call    cs:__imp_HeapFree
0x18000d711  nop     dword ptr [rax+rax+00h]
0x18000d716  mov     r8d, [r14]
0x18000d719  lea     rbx, aOnecoreuapNetN_24; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000d720  mov     r9, rbx
0x18000d723  mov     dword ptr [rsp+38h+var_18], 180h
0x18000d72b  lea     rdx, aTeredoderefere; "TeredoDereferenceClient: --%d @ %ls:%u"
0x18000d732  mov     ecx, 100000h
0x18000d737  call    EventWrite0
0x18000d73c  mov     edx, [r14]
0x18000d73f  mov     eax, 1
0x18000d744  lock xadd [r14+8], eax
0x18000d74a  and     eax, 3Fh
0x18000d74d  lea     rax, [rax+rax*4]
0x18000d751  mov     [r14+rax*8+10h], edx
0x18000d756  mov     dword ptr [r14+rax*8+20h], 180h
0x18000d75f  mov     [r14+rax*8+18h], rbx
0x18000d764  mov     dword ptr [r14+rax*8+30h], 1
0x18000d76d  mov     [r14+rax*8+28h], rbp
0x18000d772  lock xadd [r14], esi
0x18000d777  mov     rbp, [rsp+38h+arg_0]
0x18000d77c  cmp     esi, 1
0x18000d77f  jz      short loc_18000D792
0x18000d781  mov     r14, [rsp+38h+arg_10]
0x18000d786  mov     rbx, [rsp+38h+arg_18]
0x18000d78b  add     rsp, 30h
0x18000d78f  pop     rsi
0x18000d790  retn
0x18000d792  mov     rcx, r14
0x18000d795  call    TeredoCleanupClient
0x18000d79a  jmp     short loc_18000D781
```
