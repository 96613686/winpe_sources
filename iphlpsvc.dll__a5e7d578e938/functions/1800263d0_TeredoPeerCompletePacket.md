# TeredoPeerCompletePacket

- ea: `0x1800263d0`
- end: `0x1800265c8`
- name: `TeredoPeerCompletePacket`
- size: `504`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d7c0`
- `0x1800263d0`
- `0x180051eec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002653c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002653c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002651d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002651d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800264e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800264e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800264d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800264d9`

## string_xrefs

- `0x18002654b`: `onecoreuap\net\netio\iphlpsvc\service\peer.c`
- `0x1800264f4`: `CloseThreadpoolWait complete`
- `0x1800263de`: `Teredo has completed a packet on the peer socket`
- `0x18002641b`: `TeredoPeerCompletePacket`

## pseudocode

```c
__int64 __fastcall TeredoPeerCompletePacket(__int64 a1)
{
  __int64 v1; // rbx
  volatile signed __int32 v2; // edx
  volatile signed __int32 *v3; // roff
  __int64 v4; // rax
  __int64 result; // rax
  void *v6; // rcx
  volatile signed __int32 *v7; // rsi
  void *v8; // rcx
  struct _TP_WAIT *v9; // rdi
  void *v10; // rcx
  volatile signed __int32 v11; // edx

  v1 = *(_QWORD *)(a1 + 40);
  EventWrite0(0x100000, L"Teredo has completed a packet on the peer socket");
  _InterlockedDecrement((volatile signed __int32 *)(v1 + 1088));
  v2 = *(_DWORD *)(v1 + 16);
  v3 = (volatile signed __int32 *)(*(_QWORD *)(v1 + 1056) + 2576LL);
  v4 = 5LL * (_InterlockedExchangeAdd(v3, 1u) & 0x3F);
  v3[2 * v4 + 2] = v2;
  v3[2 * v4 + 6] = 96;
  *(_QWORD *)&v3[2 * v4 + 4] = L"TeredoPeerCompletePacket";
  v3[2 * v4 + 10] = 1;
  *(_QWORD *)&v3[2 * v4 + 8] = v1;
  EventWrite0(0x100000, L"TeredoDereferencePeerEx: --%d @ %ls:%u", *(unsigned int *)(v1 + 16));
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    v6 = *(void **)(v1 + 1080);
    v7 = *(volatile signed __int32 **)(v1 + 1056);
    if ( v6 )
    {
      CloseHandle(v6);
      *(_QWORD *)(v1 + 1080) = 0;
    }
    v8 = *(void **)(v1 + 1688);
    if ( v8 )
    {
      CloseHandle(v8);
      *(_QWORD *)(v1 + 1688) = 0;
    }
    v9 = *(struct _TP_WAIT **)(v1 + 864);
    if ( v9 )
    {
      SetThreadpoolWait(*(PTP_WAIT *)(v1 + 864), 0, 0);
      CloseThreadpoolWait(v9);
      EventWrite0(0x100000, L"CloseThreadpoolWait complete");
      *(_QWORD *)(v1 + 864) = 0;
    }
    v10 = *(void **)(v1 + 856);
    if ( v10 )
    {
      CloseHandle(v10);
      *(_QWORD *)(v1 + 856) = 0;
    }
    HeapFree(*((HANDLE *)v7 + 1101), 0, (LPVOID)v1);
    EventWrite0(
      0x100000,
      L"TeredoDereferenceClient: --%d @ %ls:%u",
      *(unsigned int *)v7,
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\peer.c",
      384);
    v11 = *v7;
    result = 5LL * (_InterlockedExchangeAdd(v7 + 2, 1u) & 0x3F);
    v7[2 * result + 4] = v11;
    v7[2 * result + 8] = 384;
    *(_QWORD *)&v7[2 * result + 6] = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\peer.c";
    v7[2 * result + 12] = 1;
    *(_QWORD *)&v7[2 * result + 10] = 0;
    if ( _InterlockedExchangeAdd(v7, 0xFFFFFFFF) == 1 )
      return TeredoCleanupClient(v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800263d0  mov     [rsp+arg_18], rbx
0x1800263d5  push    rbp
0x1800263d6  sub     rsp, 30h
0x1800263da  mov     rbx, [rcx+28h]
0x1800263de  lea     rdx, aTeredoHasCompl_0; "Teredo has completed a packet on the pe"...
0x1800263e5  mov     ecx, 100000h
0x1800263ea  call    EventWrite0
0x1800263ef  lock dec dword ptr [rbx+440h]
0x1800263f6  mov     eax, 1
0x1800263fb  mov     rcx, [rbx+420h]
0x180026402  mov     edx, [rbx+10h]
0x180026405  add     rcx, 0A10h
0x18002640c  lock xadd [rcx], eax
0x180026410  and     eax, 3Fh
0x180026413  mov     [rsp+38h+var_18], 60h ; '`'
0x18002641b  lea     r9, aTeredopeercomp; "TeredoPeerCompletePacket"
0x180026422  lea     rax, [rax+rax*4]
0x180026426  mov     [rcx+rax*8+8], edx
0x18002642a  lea     rdx, aTeredoderefere_0; "TeredoDereferencePeerEx: --%d @ %ls:%u"
0x180026431  mov     dword ptr [rcx+rax*8+18h], 60h ; '`'
0x180026439  mov     [rcx+rax*8+10h], r9
0x18002643e  mov     dword ptr [rcx+rax*8+28h], 1
0x180026446  mov     [rcx+rax*8+20h], rbx
0x18002644b  mov     ecx, 100000h
0x180026450  mov     r8d, [rbx+10h]
0x180026454  call    EventWrite0
0x180026459  mov     ebp, 0FFFFFFFFh
0x18002645e  mov     eax, ebp
0x180026460  lock xadd [rbx+10h], eax
0x180026465  cmp     eax, 1
0x180026468  jnz     loc_1800265B2
0x18002646e  mov     rcx, [rbx+438h]; hObject
0x180026475  mov     [rsp+38h+arg_0], rsi
0x18002647a  mov     rsi, [rbx+420h]
0x180026481  mov     [rsp+38h+arg_8], rdi
0x180026486  mov     [rsp+38h+arg_10], r14
0x18002648b  xor     r14d, r14d
0x18002648e  test    rcx, rcx
0x180026491  jz      short loc_1800264A6
0x180026493  call    cs:__imp_CloseHandle
0x18002649a  nop     dword ptr [rax+rax+00h]
0x18002649f  mov     [rbx+438h], r14
0x1800264a6  mov     rcx, [rbx+698h]; hObject
0x1800264ad  test    rcx, rcx
0x1800264b0  jz      short loc_1800264C5
0x1800264b2  call    cs:__imp_CloseHandle
0x1800264b9  nop     dword ptr [rax+rax+00h]
0x1800264be  mov     [rbx+698h], r14
0x1800264c5  mov     rdi, [rbx+360h]
0x1800264cc  test    rdi, rdi
0x1800264cf  jz      short loc_18002650C
0x1800264d1  xor     r8d, r8d; pftTimeout
0x1800264d4  xor     edx, edx; h
0x1800264d6  mov     rcx, rdi; pwa
0x1800264d9  call    cs:__imp_SetThreadpoolWait
0x1800264e0  nop     dword ptr [rax+rax+00h]
0x1800264e5  mov     rcx, rdi; pwa
0x1800264e8  call    cs:__imp_CloseThreadpoolWait
0x1800264ef  nop     dword ptr [rax+rax+00h]
0x1800264f4  lea     rdx, aClosethreadpoo; "CloseThreadpoolWait complete"
0x1800264fb  mov     ecx, 100000h
0x180026500  call    EventWrite0
0x180026505  mov     [rbx+360h], r14
0x18002650c  mov     rcx, [rbx+358h]; hObject
0x180026513  mov     rdi, [rsp+38h+arg_8]
0x180026518  test    rcx, rcx
0x18002651b  jz      short loc_180026530
0x18002651d  call    cs:__imp_CloseHandle
0x180026524  nop     dword ptr [rax+rax+00h]
0x180026529  mov     [rbx+358h], r14
0x180026530  mov     rcx, [rsi+2268h]; hHeap
0x180026537  mov     r8, rbx; lpMem
0x18002653a  xor     edx, edx; dwFlags
0x18002653c  call    cs:__imp_HeapFree
0x180026543  nop     dword ptr [rax+rax+00h]
0x180026548  mov     r8d, [rsi]
0x18002654b  lea     rbx, aOnecoreuapNetN_24; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180026552  mov     r9, rbx
0x180026555  mov     [rsp+38h+var_18], 180h
0x18002655d  lea     rdx, aTeredoderefere; "TeredoDereferenceClient: --%d @ %ls:%u"
0x180026564  mov     ecx, 100000h
0x180026569  call    EventWrite0
0x18002656e  mov     edx, [rsi]
0x180026570  mov     eax, 1
0x180026575  lock xadd [rsi+8], eax
0x18002657a  and     eax, 3Fh
0x18002657d  lea     rax, [rax+rax*4]
0x180026581  mov     [rsi+rax*8+10h], edx
0x180026585  mov     dword ptr [rsi+rax*8+20h], 180h
0x18002658d  mov     [rsi+rax*8+18h], rbx
0x180026592  mov     dword ptr [rsi+rax*8+30h], 1
0x18002659a  mov     [rsi+rax*8+28h], r14
0x18002659f  lock xadd [rsi], ebp
0x1800265a3  mov     r14, [rsp+38h+arg_10]
0x1800265a8  cmp     ebp, 1
0x1800265ab  jz      short loc_1800265BE
0x1800265ad  mov     rsi, [rsp+38h+arg_0]
0x1800265b2  mov     rbx, [rsp+38h+arg_18]
0x1800265b7  add     rsp, 30h
0x1800265bb  pop     rbp
0x1800265bc  retn
0x1800265be  mov     rcx, rsi
0x1800265c1  call    TeredoCleanupClient
0x1800265c6  jmp     short loc_1800265AD
```
