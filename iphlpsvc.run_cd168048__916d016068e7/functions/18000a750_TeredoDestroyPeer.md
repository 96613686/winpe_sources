# TeredoDestroyPeer

- ea: `0x18000a750`
- end: `0x18000a89a`
- name: `TeredoDestroyPeer`
- size: `330`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `13`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009900`
- `0x180009ea0`
- `0x18000a140`
- `0x18000a350`
- `0x18000a590`
- `0x18000afa0`
- `0x18000cb80`
- `0x18000fd80`
- `0x180010150`
- `0x1800102d0`
- `0x180016ed0`
- `0x18001b588`
- `0x180032410`

## callees

- `0x18000a750`
- `0x18000d7b0`
- `0x180051f2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a815`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a790`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a790`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a7c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a7c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a7b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a7b7`

## string_xrefs

- `0x18000a824`: `onecoreuap\net\netio\iphlpsvc\service\peer.c`
- `0x18000a7d2`: `CloseThreadpoolWait complete`

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
0x18000a750  push    rbx
0x18000a752  push    rbp
0x18000a753  push    rsi
0x18000a754  push    rdi
0x18000a755  sub     rsp, 38h
0x18000a759  mov     rsi, [rcx+420h]
0x18000a760  mov     rbx, rcx
0x18000a763  mov     rcx, [rcx+438h]; hObject
0x18000a76a  xor     ebp, ebp
0x18000a76c  test    rcx, rcx
0x18000a76f  jz      short loc_18000A784
0x18000a771  call    cs:__imp_CloseHandle
0x18000a778  nop     dword ptr [rax+rax+00h]
0x18000a77d  mov     [rbx+438h], rbp
0x18000a784  mov     rcx, [rbx+698h]; hObject
0x18000a78b  test    rcx, rcx
0x18000a78e  jz      short loc_18000A7A3
0x18000a790  call    cs:__imp_CloseHandle
0x18000a797  nop     dword ptr [rax+rax+00h]
0x18000a79c  mov     [rbx+698h], rbp
0x18000a7a3  mov     rdi, [rbx+360h]
0x18000a7aa  test    rdi, rdi
0x18000a7ad  jz      short loc_18000A7EA
0x18000a7af  xor     r8d, r8d; pftTimeout
0x18000a7b2  xor     edx, edx; h
0x18000a7b4  mov     rcx, rdi; pwa
0x18000a7b7  call    cs:__imp_SetThreadpoolWait
0x18000a7be  nop     dword ptr [rax+rax+00h]
0x18000a7c3  mov     rcx, rdi; pwa
0x18000a7c6  call    cs:__imp_CloseThreadpoolWait
0x18000a7cd  nop     dword ptr [rax+rax+00h]
0x18000a7d2  lea     rdx, aClosethreadpoo; "CloseThreadpoolWait complete"
0x18000a7d9  mov     ecx, 100000h
0x18000a7de  call    EventWrite0
0x18000a7e3  mov     [rbx+360h], rbp
0x18000a7ea  mov     rcx, [rbx+358h]; hObject
0x18000a7f1  test    rcx, rcx
0x18000a7f4  jz      short loc_18000A809
0x18000a7f6  call    cs:__imp_CloseHandle
0x18000a7fd  nop     dword ptr [rax+rax+00h]
0x18000a802  mov     [rbx+358h], rbp
0x18000a809  mov     rcx, [rsi+2268h]; hHeap
0x18000a810  mov     r8, rbx; lpMem
0x18000a813  xor     edx, edx; dwFlags
0x18000a815  call    cs:__imp_HeapFree
0x18000a81c  nop     dword ptr [rax+rax+00h]
0x18000a821  mov     r8d, [rsi]
0x18000a824  lea     rbx, aOnecoreuapNetN_24; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000a82b  mov     r9, rbx
0x18000a82e  mov     [rsp+58h+var_38], 180h
0x18000a836  lea     rdx, aTeredoderefere; "TeredoDereferenceClient: --%d @ %ls:%u"
0x18000a83d  mov     ecx, 100000h
0x18000a842  call    EventWrite0
0x18000a847  mov     edx, [rsi]
0x18000a849  mov     eax, 1
0x18000a84e  lock xadd [rsi+8], eax
0x18000a853  and     eax, 3Fh
0x18000a856  lea     rax, [rax+rax*4]
0x18000a85a  mov     [rsi+rax*8+10h], edx
0x18000a85e  mov     dword ptr [rsi+rax*8+20h], 180h
0x18000a866  mov     [rsi+rax*8+18h], rbx
0x18000a86b  mov     dword ptr [rsi+rax*8+30h], 1
0x18000a873  mov     [rsi+rax*8+28h], rbp
0x18000a878  mov     eax, 0FFFFFFFFh
0x18000a87d  lock xadd [rsi], eax
0x18000a881  cmp     eax, 1
0x18000a884  jz      short loc_18000A890
0x18000a886  add     rsp, 38h
0x18000a88a  pop     rdi
0x18000a88b  pop     rsi
0x18000a88c  pop     rbp
0x18000a88d  pop     rbx
0x18000a88e  retn
0x18000a890  mov     rcx, rsi
0x18000a893  call    TeredoCleanupClient
0x18000a898  jmp     short loc_18000A886
```
