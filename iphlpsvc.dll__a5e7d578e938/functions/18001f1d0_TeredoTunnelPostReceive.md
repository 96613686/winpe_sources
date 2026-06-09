# TeredoTunnelPostReceive

- ea: `0x18001f1d0`
- end: `0x18001f3fb`
- name: `TeredoTunnelPostReceive`
- size: `555`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001e370`
- `0x1800562a0`

## callees

- `0x18000d7c0`
- `0x180010160`
- `0x1800190f0`
- `0x18001f1d0`
- `0x18002e0d0`
- `0x18002ec50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f306`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f284`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f263`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f263`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001f2ac`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001f2ac`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001f22a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001f22a`

## string_xrefs

- `0x18001f1f5`: `onecoreuap\net\netio\iphlpsvc\service\io.c`
- `0x18001f297`: `Teredo tunnel posting a recv: ReadFile failed`

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
0x18001f1d0  push    rbx
0x18001f1d2  push    rbp
0x18001f1d3  push    rsi
0x18001f1d4  push    rdi
0x18001f1d5  push    r14
0x18001f1d7  sub     rsp, 30h
0x18001f1db  mov     rbp, [rcx]
0x18001f1de  mov     rbx, rdx
0x18001f1e1  mov     rsi, rcx
0x18001f1e4  lea     rdx, aTeredoTunnelPo; "Teredo tunnel posting a recv"
0x18001f1eb  mov     ecx, 100000h
0x18001f1f0  call    EventWrite0
0x18001f1f5  lea     r14, aOnecoreuapNetN_22; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18001f1fc  test    rbx, rbx
0x18001f1ff  jz      loc_18001F2E8
0x18001f205  mov     dword ptr [rbx+1E8h], 0Ch
0x18001f20f  cmp     byte ptr [rbp+0B40h], 0
0x18001f216  jnz     loc_18001F3E5
0x18001f21c  mov     dword ptr [rbx+120h], 3
0x18001f226  mov     rcx, [rsi+10h]; pio
0x18001f22a  call    cs:__imp_StartThreadpoolIo
0x18001f231  nop     dword ptr [rax+rax+00h]
0x18001f236  mov     ecx, [rbx+198h]
0x18001f23c  lea     r9, [rbx+100h]
0x18001f243  mov     r8d, [rbx+1E8h]
0x18001f24a  lea     rdx, [rbx+1B0h]; lpBuffer
0x18001f251  add     ecx, 50h ; 'P'
0x18001f254  mov     [rsp+58h+lpOverlapped], r9; lpOverlapped
0x18001f259  add     r8d, ecx; nNumberOfBytesToRead
0x18001f25c  xor     r9d, r9d; lpNumberOfBytesRead
0x18001f25f  mov     rcx, [rsi+18h]; hFile
0x18001f263  call    cs:__imp_ReadFile
0x18001f26a  nop     dword ptr [rax+rax+00h]
0x18001f26f  test    eax, eax
0x18001f271  jz      short loc_18001F284
0x18001f273  mov     eax, 1
0x18001f278  add     rsp, 30h
0x18001f27c  pop     r14
0x18001f27e  pop     rdi
0x18001f27f  pop     rsi
0x18001f280  pop     rbp
0x18001f281  pop     rbx
0x18001f282  retn
0x18001f284  call    cs:__imp_GetLastError
0x18001f28b  nop     dword ptr [rax+rax+00h]
0x18001f290  cmp     eax, 3E5h
0x18001f295  jz      short loc_18001F273
0x18001f297  lea     rdx, aTeredoTunnelPo_0; "Teredo tunnel posting a recv: ReadFile "...
0x18001f29e  mov     ecx, 100000h
0x18001f2a3  call    EventWriteError0
0x18001f2a8  mov     rcx, [rsi+10h]; pio
0x18001f2ac  call    cs:__imp_CancelThreadpoolIo
0x18001f2b3  nop     dword ptr [rax+rax+00h]
0x18001f2b8  mov     rcx, rbx; lpMem
0x18001f2bb  call    TeredoDestroyPacket
0x18001f2c0  cmp     byte ptr [rbp+0B40h], 0
0x18001f2c7  jz      short loc_18001F2DA
0x18001f2c9  mov     r8d, 0A60h
0x18001f2cf  mov     rdx, r14
0x18001f2d2  mov     rcx, rbp
0x18001f2d5  call    TeredoDereferenceIoEx
0x18001f2da  xor     eax, eax
0x18001f2dc  add     rsp, 30h
0x18001f2e0  pop     r14
0x18001f2e2  pop     rdi
0x18001f2e3  pop     rsi
0x18001f2e4  pop     rbp
0x18001f2e5  pop     rbx
0x18001f2e6  retn
0x18001f2e8  mov     rdi, [rsi]
0x18001f2eb  cmp     byte ptr [rdi+0B40h], 0
0x18001f2f2  jnz     short loc_18001F2DA
0x18001f2f4  mov     rcx, [rdi+0A10h]; hHeap
0x18001f2fb  mov     edx, 8; dwFlags
0x18001f300  mov     r8d, 7CEh; dwBytes
0x18001f306  call    cs:__imp_HeapAlloc
0x18001f30d  nop     dword ptr [rax+rax+00h]
0x18001f312  mov     rbx, rax
0x18001f315  test    rax, rax
0x18001f318  jz      short loc_18001F2DA
0x18001f31a  mov     [rax+10h], rdi
0x18001f31e  xor     edx, edx
0x18001f320  mov     [rax+8], rdx
0x18001f324  xorps   xmm0, xmm0
0x18001f327  mov     [rax], rdx
0x18001f32a  mov     [rax+18h], rdx
0x18001f32e  lea     rax, DeviceReceiveComplete
0x18001f335  mov     [rbx+20h], rax
0x18001f339  xor     eax, eax
0x18001f33b  mov     [rbx+28h], rsi
0x18001f33f  mov     byte ptr [rbx+30h], 1
0x18001f343  mov     dword ptr [rbx+1E8h], 0Ch
0x18001f34d  movups  xmmword ptr [rbx+100h], xmm0
0x18001f354  movups  xmmword ptr [rbx+110h], xmm0
0x18001f35b  mov     [rbx+120h], rax
0x18001f362  mov     [rbx+128h], eax
0x18001f368  mov     eax, 1
0x18001f36d  movups  xmmword ptr [rbx+178h], xmm0
0x18001f374  movups  xmmword ptr [rbx+188h], xmm0
0x18001f37b  mov     ecx, [rdi]
0x18001f37d  lock xadd [rdi+8], eax
0x18001f382  and     eax, 3Fh
0x18001f385  mov     dword ptr [rsp+58h+lpOverlapped], 174h
0x18001f38d  mov     r9, r14
0x18001f390  lea     rax, [rax+rax*4]
0x18001f394  mov     [rdi+rax*8+10h], ecx
0x18001f398  mov     ecx, 100000h
0x18001f39d  mov     [rdi+rax*8+30h], edx
0x18001f3a1  mov     [rdi+rax*8+28h], rdx
0x18001f3a6  lea     rdx, aIoRefRefDFileS; "io ref, ref %d, file %s  line %d"
0x18001f3ad  mov     dword ptr [rdi+rax*8+20h], 174h
0x18001f3b5  mov     [rdi+rax*8+18h], r14
0x18001f3ba  mov     r8d, [rdi]
0x18001f3bd  inc     r8d
0x18001f3c0  call    EventWrite0
0x18001f3c5  lock inc dword ptr [rdi]
0x18001f3c8  lea     rax, [rbx+20Ch]
0x18001f3cf  mov     dword ptr [rbx+198h], 5C0h
0x18001f3d9  mov     [rbx+1A0h], rax
0x18001f3e0  jmp     loc_18001F205
0x18001f3e5  mov     r8d, 0A45h
0x18001f3eb  mov     rdx, r14
0x18001f3ee  mov     rcx, rbp
0x18001f3f1  call    TeredoReferenceIoEx
0x18001f3f6  jmp     loc_18001F21C
```
