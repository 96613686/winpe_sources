# TeredoPeerCompletePacket

- ea: `0x1800263c0`
- end: `0x1800265b8`
- name: `TeredoPeerCompletePacket`
- size: `504`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d7b0`
- `0x1800263c0`
- `0x180051f2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002652c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002652c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026483`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002650d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026483`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800264a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002650d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800264d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800264d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800264c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800264c9`

## string_xrefs

- `0x18002653b`: `onecoreuap\net\netio\iphlpsvc\service\peer.c`
- `0x1800264e4`: `CloseThreadpoolWait complete`
- `0x1800263ce`: `Teredo has completed a packet on the peer socket`
- `0x18002640b`: `TeredoPeerCompletePacket`

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
0x1800263c0  mov     [rsp+arg_18], rbx
0x1800263c5  push    rbp
0x1800263c6  sub     rsp, 30h
0x1800263ca  mov     rbx, [rcx+28h]
0x1800263ce  lea     rdx, aTeredoHasCompl_0; "Teredo has completed a packet on the pe"...
0x1800263d5  mov     ecx, 100000h
0x1800263da  call    EventWrite0
0x1800263df  lock dec dword ptr [rbx+440h]
0x1800263e6  mov     eax, 1
0x1800263eb  mov     rcx, [rbx+420h]
0x1800263f2  mov     edx, [rbx+10h]
0x1800263f5  add     rcx, 0A10h
0x1800263fc  lock xadd [rcx], eax
0x180026400  and     eax, 3Fh
0x180026403  mov     [rsp+38h+var_18], 60h ; '`'
0x18002640b  lea     r9, aTeredopeercomp; "TeredoPeerCompletePacket"
0x180026412  lea     rax, [rax+rax*4]
0x180026416  mov     [rcx+rax*8+8], edx
0x18002641a  lea     rdx, aTeredoderefere_0; "TeredoDereferencePeerEx: --%d @ %ls:%u"
0x180026421  mov     dword ptr [rcx+rax*8+18h], 60h ; '`'
0x180026429  mov     [rcx+rax*8+10h], r9
0x18002642e  mov     dword ptr [rcx+rax*8+28h], 1
0x180026436  mov     [rcx+rax*8+20h], rbx
0x18002643b  mov     ecx, 100000h
0x180026440  mov     r8d, [rbx+10h]
0x180026444  call    EventWrite0
0x180026449  mov     ebp, 0FFFFFFFFh
0x18002644e  mov     eax, ebp
0x180026450  lock xadd [rbx+10h], eax
0x180026455  cmp     eax, 1
0x180026458  jnz     loc_1800265A2
0x18002645e  mov     rcx, [rbx+438h]; hObject
0x180026465  mov     [rsp+38h+arg_0], rsi
0x18002646a  mov     rsi, [rbx+420h]
0x180026471  mov     [rsp+38h+arg_8], rdi
0x180026476  mov     [rsp+38h+arg_10], r14
0x18002647b  xor     r14d, r14d
0x18002647e  test    rcx, rcx
0x180026481  jz      short loc_180026496
0x180026483  call    cs:__imp_CloseHandle
0x18002648a  nop     dword ptr [rax+rax+00h]
0x18002648f  mov     [rbx+438h], r14
0x180026496  mov     rcx, [rbx+698h]; hObject
0x18002649d  test    rcx, rcx
0x1800264a0  jz      short loc_1800264B5
0x1800264a2  call    cs:__imp_CloseHandle
0x1800264a9  nop     dword ptr [rax+rax+00h]
0x1800264ae  mov     [rbx+698h], r14
0x1800264b5  mov     rdi, [rbx+360h]
0x1800264bc  test    rdi, rdi
0x1800264bf  jz      short loc_1800264FC
0x1800264c1  xor     r8d, r8d; pftTimeout
0x1800264c4  xor     edx, edx; h
0x1800264c6  mov     rcx, rdi; pwa
0x1800264c9  call    cs:__imp_SetThreadpoolWait
0x1800264d0  nop     dword ptr [rax+rax+00h]
0x1800264d5  mov     rcx, rdi; pwa
0x1800264d8  call    cs:__imp_CloseThreadpoolWait
0x1800264df  nop     dword ptr [rax+rax+00h]
0x1800264e4  lea     rdx, aClosethreadpoo; "CloseThreadpoolWait complete"
0x1800264eb  mov     ecx, 100000h
0x1800264f0  call    EventWrite0
0x1800264f5  mov     [rbx+360h], r14
0x1800264fc  mov     rcx, [rbx+358h]; hObject
0x180026503  mov     rdi, [rsp+38h+arg_8]
0x180026508  test    rcx, rcx
0x18002650b  jz      short loc_180026520
0x18002650d  call    cs:__imp_CloseHandle
0x180026514  nop     dword ptr [rax+rax+00h]
0x180026519  mov     [rbx+358h], r14
0x180026520  mov     rcx, [rsi+2268h]; hHeap
0x180026527  mov     r8, rbx; lpMem
0x18002652a  xor     edx, edx; dwFlags
0x18002652c  call    cs:__imp_HeapFree
0x180026533  nop     dword ptr [rax+rax+00h]
0x180026538  mov     r8d, [rsi]
0x18002653b  lea     rbx, aOnecoreuapNetN_24; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180026542  mov     r9, rbx
0x180026545  mov     [rsp+38h+var_18], 180h
0x18002654d  lea     rdx, aTeredoderefere; "TeredoDereferenceClient: --%d @ %ls:%u"
0x180026554  mov     ecx, 100000h
0x180026559  call    EventWrite0
0x18002655e  mov     edx, [rsi]
0x180026560  mov     eax, 1
0x180026565  lock xadd [rsi+8], eax
0x18002656a  and     eax, 3Fh
0x18002656d  lea     rax, [rax+rax*4]
0x180026571  mov     [rsi+rax*8+10h], edx
0x180026575  mov     dword ptr [rsi+rax*8+20h], 180h
0x18002657d  mov     [rsi+rax*8+18h], rbx
0x180026582  mov     dword ptr [rsi+rax*8+30h], 1
0x18002658a  mov     [rsi+rax*8+28h], r14
0x18002658f  lock xadd [rsi], ebp
0x180026593  mov     r14, [rsp+38h+arg_10]
0x180026598  cmp     ebp, 1
0x18002659b  jz      short loc_1800265AE
0x18002659d  mov     rsi, [rsp+38h+arg_0]
0x1800265a2  mov     rbx, [rsp+38h+arg_18]
0x1800265a7  add     rsp, 30h
0x1800265ab  pop     rbp
0x1800265ac  retn
0x1800265ae  mov     rcx, rsi
0x1800265b1  call    TeredoCleanupClient
0x1800265b6  jmp     short loc_18002659D
```
