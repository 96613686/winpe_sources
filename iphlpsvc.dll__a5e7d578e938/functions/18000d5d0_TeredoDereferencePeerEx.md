# TeredoDereferencePeerEx

- ea: `0x18000d5d0`
- end: `0x18000d7ac`
- name: `TeredoDereferencePeerEx`
- size: `476`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000afb0`
- `0x18000f840`
- `0x18000fd90`
- `0x180016ee0`
- `0x18001cfa0`
- `0x18003a900`
- `0x18003ef7c`

## callees

- `0x18000d5d0`
- `0x18000d7c0`
- `0x180051eec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d71a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d71a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d6c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d6c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d6b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d6b7`

## string_xrefs

- `0x18000d729`: `onecoreuap\net\netio\iphlpsvc\service\peer.c`
- `0x18000d6d2`: `CloseThreadpoolWait complete`

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
0x18000d5d0  mov     [rsp+arg_18], rbx
0x18000d5d5  push    rsi
0x18000d5d6  sub     rsp, 30h
0x18000d5da  mov     r9d, [rcx+10h]
0x18000d5de  mov     rbx, rcx
0x18000d5e1  mov     rcx, [rcx+420h]
0x18000d5e8  mov     eax, 1
0x18000d5ed  add     rcx, 0A10h
0x18000d5f4  lock xadd [rcx], eax
0x18000d5f8  and     eax, 3Fh
0x18000d5fb  mov     dword ptr [rsp+38h+var_18], r8d
0x18000d600  lea     rax, [rax+rax*4]
0x18000d604  mov     [rcx+rax*8+8], r9d
0x18000d609  mov     r9, rdx
0x18000d60c  mov     [rcx+rax*8+10h], rdx
0x18000d611  lea     rdx, aTeredoderefere_0; "TeredoDereferencePeerEx: --%d @ %ls:%u"
0x18000d618  mov     [rcx+rax*8+18h], r8d
0x18000d61d  mov     dword ptr [rcx+rax*8+28h], 1
0x18000d625  mov     [rcx+rax*8+20h], rbx
0x18000d62a  mov     ecx, 100000h
0x18000d62f  mov     r8d, [rbx+10h]
0x18000d633  call    EventWrite0
0x18000d638  mov     esi, 0FFFFFFFFh
0x18000d63d  mov     eax, esi
0x18000d63f  lock xadd [rbx+10h], eax
0x18000d644  cmp     eax, 1
0x18000d647  jnz     loc_18000D796
0x18000d64d  mov     rcx, [rbx+438h]; hObject
0x18000d654  mov     [rsp+38h+arg_0], rbp
0x18000d659  xor     ebp, ebp
0x18000d65b  mov     [rsp+38h+arg_8], rdi
0x18000d660  mov     [rsp+38h+arg_10], r14
0x18000d665  mov     r14, [rbx+420h]
0x18000d66c  test    rcx, rcx
0x18000d66f  jz      short loc_18000D684
0x18000d671  call    cs:__imp_CloseHandle
0x18000d678  nop     dword ptr [rax+rax+00h]
0x18000d67d  mov     [rbx+438h], rbp
0x18000d684  mov     rcx, [rbx+698h]; hObject
0x18000d68b  test    rcx, rcx
0x18000d68e  jz      short loc_18000D6A3
0x18000d690  call    cs:__imp_CloseHandle
0x18000d697  nop     dword ptr [rax+rax+00h]
0x18000d69c  mov     [rbx+698h], rbp
0x18000d6a3  mov     rdi, [rbx+360h]
0x18000d6aa  test    rdi, rdi
0x18000d6ad  jz      short loc_18000D6EA
0x18000d6af  xor     r8d, r8d; pftTimeout
0x18000d6b2  xor     edx, edx; h
0x18000d6b4  mov     rcx, rdi; pwa
0x18000d6b7  call    cs:__imp_SetThreadpoolWait
0x18000d6be  nop     dword ptr [rax+rax+00h]
0x18000d6c3  mov     rcx, rdi; pwa
0x18000d6c6  call    cs:__imp_CloseThreadpoolWait
0x18000d6cd  nop     dword ptr [rax+rax+00h]
0x18000d6d2  lea     rdx, aClosethreadpoo; "CloseThreadpoolWait complete"
0x18000d6d9  mov     ecx, 100000h
0x18000d6de  call    EventWrite0
0x18000d6e3  mov     [rbx+360h], rbp
0x18000d6ea  mov     rcx, [rbx+358h]; hObject
0x18000d6f1  mov     rdi, [rsp+38h+arg_8]
0x18000d6f6  test    rcx, rcx
0x18000d6f9  jz      short loc_18000D70E
0x18000d6fb  call    cs:__imp_CloseHandle
0x18000d702  nop     dword ptr [rax+rax+00h]
0x18000d707  mov     [rbx+358h], rbp
0x18000d70e  mov     rcx, [r14+2268h]; hHeap
0x18000d715  mov     r8, rbx; lpMem
0x18000d718  xor     edx, edx; dwFlags
0x18000d71a  call    cs:__imp_HeapFree
0x18000d721  nop     dword ptr [rax+rax+00h]
0x18000d726  mov     r8d, [r14]
0x18000d729  lea     rbx, aOnecoreuapNetN_24; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000d730  mov     r9, rbx
0x18000d733  mov     dword ptr [rsp+38h+var_18], 180h
0x18000d73b  lea     rdx, aTeredoderefere; "TeredoDereferenceClient: --%d @ %ls:%u"
0x18000d742  mov     ecx, 100000h
0x18000d747  call    EventWrite0
0x18000d74c  mov     edx, [r14]
0x18000d74f  mov     eax, 1
0x18000d754  lock xadd [r14+8], eax
0x18000d75a  and     eax, 3Fh
0x18000d75d  lea     rax, [rax+rax*4]
0x18000d761  mov     [r14+rax*8+10h], edx
0x18000d766  mov     dword ptr [r14+rax*8+20h], 180h
0x18000d76f  mov     [r14+rax*8+18h], rbx
0x18000d774  mov     dword ptr [r14+rax*8+30h], 1
0x18000d77d  mov     [r14+rax*8+28h], rbp
0x18000d782  lock xadd [r14], esi
0x18000d787  mov     rbp, [rsp+38h+arg_0]
0x18000d78c  cmp     esi, 1
0x18000d78f  jz      short loc_18000D7A2
0x18000d791  mov     r14, [rsp+38h+arg_10]
0x18000d796  mov     rbx, [rsp+38h+arg_18]
0x18000d79b  add     rsp, 30h
0x18000d79f  pop     rsi
0x18000d7a0  retn
0x18000d7a2  mov     rcx, r14
0x18000d7a5  call    TeredoCleanupClient
0x18000d7aa  jmp     short loc_18000D791
```
