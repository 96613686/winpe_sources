# TeredoTunnelPostReceive

- ea: `0x18001f1c0`
- end: `0x18001f3eb`
- name: `TeredoTunnelPostReceive`
- size: `555`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001e360`
- `0x180056280`

## callees

- `0x18000d7b0`
- `0x180010150`
- `0x1800190e0`
- `0x18001f1c0`
- `0x18002e0c0`
- `0x18002ec40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f2f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f274`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f253`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f253`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001f29c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001f29c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001f21a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001f21a`

## string_xrefs

- `0x18001f1e5`: `onecoreuap\net\netio\iphlpsvc\service\io.c`
- `0x18001f287`: `Teredo tunnel posting a recv: ReadFile failed`

## pseudocode

```c
__int64 __fastcall TeredoTunnelPostReceive(__int64 *a1, struct _OVERLAPPED *a2)
{
  __int64 v2; // rbp
  __int64 v6; // rdi
  char *v7; // rax
  volatile signed __int32 v8; // ecx
  __int64 v9; // rax

  v2 = *a1;
  EventWrite0(0x100000, L"Teredo tunnel posting a recv");
  if ( !a2 )
  {
    v6 = *a1;
    if ( *(_BYTE *)(*a1 + 2880) )
      return 0;
    v7 = (char *)HeapAlloc(*(HANDLE *)(v6 + 2576), 8u, 0x7CEu);
    a2 = (struct _OVERLAPPED *)v7;
    if ( !v7 )
      return 0;
    *((_QWORD *)v7 + 2) = v6;
    *((_QWORD *)v7 + 1) = 0;
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = DeviceReceiveComplete;
    *((_QWORD *)v7 + 5) = a1;
    v7[48] = 1;
    *((_DWORD *)v7 + 122) = 12;
    *((_OWORD *)v7 + 16) = 0;
    *((_OWORD *)v7 + 17) = 0;
    *((_QWORD *)v7 + 36) = 0;
    *((_DWORD *)v7 + 74) = 0;
    *(_OWORD *)(v7 + 376) = 0;
    *(_OWORD *)(v7 + 392) = 0;
    v8 = *(_DWORD *)v6;
    v9 = 5LL * (_InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 8), 1u) & 0x3F);
    *(_DWORD *)(v6 + 8 * v9 + 16) = v8;
    *(_DWORD *)(v6 + 8 * v9 + 48) = 0;
    *(_QWORD *)(v6 + 8 * v9 + 40) = 0;
    *(_DWORD *)(v6 + 8 * v9 + 32) = 372;
    *(_QWORD *)(v6 + 8 * v9 + 24) = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\io.c";
    EventWrite0(
      0x100000,
      L"io ref, ref %d, file %s  line %d",
      (unsigned int)(*(_DWORD *)v6 + 1),
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\io.c",
      372);
    _InterlockedIncrement((volatile signed __int32 *)v6);
    LODWORD(a2[12].hEvent) = 1472;
    a2[13].Internal = (ULONG_PTR)&a2[16].InternalHigh + 4;
  }
  LODWORD(a2[15].InternalHigh) = 12;
  if ( *(_BYTE *)(v2 + 2880) )
    TeredoReferenceIoEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\io.c", 2629);
  LODWORD(a2[9].Internal) = 3;
  StartThreadpoolIo((PTP_IO)a1[2]);
  if ( ReadFile((HANDLE)a1[3], &a2[13].16, LODWORD(a2[12].hEvent) + 80 + LODWORD(a2[15].InternalHigh), 0, a2 + 8)
    || GetLastError() == 997 )
  {
    return 1;
  }
  EventWriteError0(0x100000, L"Teredo tunnel posting a recv: ReadFile failed");
  CancelThreadpoolIo((PTP_IO)a1[2]);
  TeredoDestroyPacket(a2);
  if ( *(_BYTE *)(v2 + 2880) )
    TeredoDereferenceIoEx(v2, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\io.c", 2656);
  return 0;
}

```

## disassembly

```asm
0x18001f1c0  push    rbx
0x18001f1c2  push    rbp
0x18001f1c3  push    rsi
0x18001f1c4  push    rdi
0x18001f1c5  push    r14
0x18001f1c7  sub     rsp, 30h
0x18001f1cb  mov     rbp, [rcx]
0x18001f1ce  mov     rbx, rdx
0x18001f1d1  mov     rsi, rcx
0x18001f1d4  lea     rdx, aTeredoTunnelPo; "Teredo tunnel posting a recv"
0x18001f1db  mov     ecx, 100000h
0x18001f1e0  call    EventWrite0
0x18001f1e5  lea     r14, aOnecoreuapNetN_22; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18001f1ec  test    rbx, rbx
0x18001f1ef  jz      loc_18001F2D8
0x18001f1f5  mov     dword ptr [rbx+1E8h], 0Ch
0x18001f1ff  cmp     byte ptr [rbp+0B40h], 0
0x18001f206  jnz     loc_18001F3D5
0x18001f20c  mov     dword ptr [rbx+120h], 3
0x18001f216  mov     rcx, [rsi+10h]; pio
0x18001f21a  call    cs:__imp_StartThreadpoolIo
0x18001f221  nop     dword ptr [rax+rax+00h]
0x18001f226  mov     ecx, [rbx+198h]
0x18001f22c  lea     r9, [rbx+100h]
0x18001f233  mov     r8d, [rbx+1E8h]
0x18001f23a  lea     rdx, [rbx+1B0h]; lpBuffer
0x18001f241  add     ecx, 50h ; 'P'
0x18001f244  mov     [rsp+58h+lpOverlapped], r9; lpOverlapped
0x18001f249  add     r8d, ecx; nNumberOfBytesToRead
0x18001f24c  xor     r9d, r9d; lpNumberOfBytesRead
0x18001f24f  mov     rcx, [rsi+18h]; hFile
0x18001f253  call    cs:__imp_ReadFile
0x18001f25a  nop     dword ptr [rax+rax+00h]
0x18001f25f  test    eax, eax
0x18001f261  jz      short loc_18001F274
0x18001f263  mov     eax, 1
0x18001f268  add     rsp, 30h
0x18001f26c  pop     r14
0x18001f26e  pop     rdi
0x18001f26f  pop     rsi
0x18001f270  pop     rbp
0x18001f271  pop     rbx
0x18001f272  retn
0x18001f274  call    cs:__imp_GetLastError
0x18001f27b  nop     dword ptr [rax+rax+00h]
0x18001f280  cmp     eax, 3E5h
0x18001f285  jz      short loc_18001F263
0x18001f287  lea     rdx, aTeredoTunnelPo_0; "Teredo tunnel posting a recv: ReadFile "...
0x18001f28e  mov     ecx, 100000h
0x18001f293  call    EventWriteError0
0x18001f298  mov     rcx, [rsi+10h]; pio
0x18001f29c  call    cs:__imp_CancelThreadpoolIo
0x18001f2a3  nop     dword ptr [rax+rax+00h]
0x18001f2a8  mov     rcx, rbx; lpMem
0x18001f2ab  call    TeredoDestroyPacket
0x18001f2b0  cmp     byte ptr [rbp+0B40h], 0
0x18001f2b7  jz      short loc_18001F2CA
0x18001f2b9  mov     r8d, 0A60h
0x18001f2bf  mov     rdx, r14
0x18001f2c2  mov     rcx, rbp
0x18001f2c5  call    TeredoDereferenceIoEx
0x18001f2ca  xor     eax, eax
0x18001f2cc  add     rsp, 30h
0x18001f2d0  pop     r14
0x18001f2d2  pop     rdi
0x18001f2d3  pop     rsi
0x18001f2d4  pop     rbp
0x18001f2d5  pop     rbx
0x18001f2d6  retn
0x18001f2d8  mov     rdi, [rsi]
0x18001f2db  cmp     byte ptr [rdi+0B40h], 0
0x18001f2e2  jnz     short loc_18001F2CA
0x18001f2e4  mov     rcx, [rdi+0A10h]; hHeap
0x18001f2eb  mov     edx, 8; dwFlags
0x18001f2f0  mov     r8d, 7CEh; dwBytes
0x18001f2f6  call    cs:__imp_HeapAlloc
0x18001f2fd  nop     dword ptr [rax+rax+00h]
0x18001f302  mov     rbx, rax
0x18001f305  test    rax, rax
0x18001f308  jz      short loc_18001F2CA
0x18001f30a  mov     [rax+10h], rdi
0x18001f30e  xor     edx, edx
0x18001f310  mov     [rax+8], rdx
0x18001f314  xorps   xmm0, xmm0
0x18001f317  mov     [rax], rdx
0x18001f31a  mov     [rax+18h], rdx
0x18001f31e  lea     rax, DeviceReceiveComplete
0x18001f325  mov     [rbx+20h], rax
0x18001f329  xor     eax, eax
0x18001f32b  mov     [rbx+28h], rsi
0x18001f32f  mov     byte ptr [rbx+30h], 1
0x18001f333  mov     dword ptr [rbx+1E8h], 0Ch
0x18001f33d  movups  xmmword ptr [rbx+100h], xmm0
0x18001f344  movups  xmmword ptr [rbx+110h], xmm0
0x18001f34b  mov     [rbx+120h], rax
0x18001f352  mov     [rbx+128h], eax
0x18001f358  mov     eax, 1
0x18001f35d  movups  xmmword ptr [rbx+178h], xmm0
0x18001f364  movups  xmmword ptr [rbx+188h], xmm0
0x18001f36b  mov     ecx, [rdi]
0x18001f36d  lock xadd [rdi+8], eax
0x18001f372  and     eax, 3Fh
0x18001f375  mov     dword ptr [rsp+58h+lpOverlapped], 174h
0x18001f37d  mov     r9, r14
0x18001f380  lea     rax, [rax+rax*4]
0x18001f384  mov     [rdi+rax*8+10h], ecx
0x18001f388  mov     ecx, 100000h
0x18001f38d  mov     [rdi+rax*8+30h], edx
0x18001f391  mov     [rdi+rax*8+28h], rdx
0x18001f396  lea     rdx, aIoRefRefDFileS; "io ref, ref %d, file %s  line %d"
0x18001f39d  mov     dword ptr [rdi+rax*8+20h], 174h
0x18001f3a5  mov     [rdi+rax*8+18h], r14
0x18001f3aa  mov     r8d, [rdi]
0x18001f3ad  inc     r8d
0x18001f3b0  call    EventWrite0
0x18001f3b5  lock inc dword ptr [rdi]
0x18001f3b8  lea     rax, [rbx+20Ch]
0x18001f3bf  mov     dword ptr [rbx+198h], 5C0h
0x18001f3c9  mov     [rbx+1A0h], rax
0x18001f3d0  jmp     loc_18001F1F5
0x18001f3d5  mov     r8d, 0A45h
0x18001f3db  mov     rdx, r14
0x18001f3de  mov     rcx, rbp
0x18001f3e1  call    TeredoReferenceIoEx
0x18001f3e6  jmp     loc_18001F20C
```
