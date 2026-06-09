# LRPC_ADDRESS::LRPC_ADDRESS(long *)

- ea: `0x180090180`
- end: `0x180090344`
- name: `??0LRPC_ADDRESS@@QEAA@PEAJ@Z`
- size: `452`
- prototype: `LRPC_ADDRESS *__fastcall(LRPC_ADDRESS *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800900ec`

## callees

- `0x180090180`
- `0x18009034c`
- `0x180099b18`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x1800901dc`
- `ntdll!RtlInitializeSRWLock` at `0x1800901dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180090303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180090303`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090272`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090272`

## pseudocode

```c
LRPC_ADDRESS *__fastcall LRPC_ADDRESS::LRPC_ADDRESS(LRPC_ADDRESS *this, int *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // eax
  HANDLE EventW; // rax
  CellHeap *v8; // rcx
  LRPC_ADDRESS *result; // rax
  struct tagDebugFreeCell *Cell; // rax
  void *v11; // rcx
  __int64 v12; // rax

  RPC_ADDRESS::RPC_ADDRESS(this);
  *(_QWORD *)this = &LRPC_ADDRESS::`vftable';
  *((_QWORD *)this + 28) = 4;
  *((_QWORD *)this + 27) = (char *)this + 232;
  *(_OWORD *)((char *)this + 232) = 0;
  *(_OWORD *)((char *)this + 248) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_DWORD *)this + 84) = 0;
  RtlInitializeSRWLock((char *)this + 424);
  *((_DWORD *)this + 3) = 0x800000;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 73) = 0;
  v4 = gPageSize;
  *((_DWORD *)this + 83) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  v5 = v4 * gNumberOfProcessors;
  v6 = 4 * v4;
  *((_DWORD *)this + 82) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 46) = 0;
  v5 *= 2;
  *(_OWORD *)((char *)this + 312) = 0;
  *((_DWORD *)this + 76) = v5;
  if ( v5 < v6 )
    *((_DWORD *)this + 76) = v6;
  *((_DWORD *)this + 100) = 0;
  *((_DWORD *)this + 101) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 51) = EventW;
  if ( !EventW )
    *a2 = 14;
  if ( g_fServerSideDebugInfoEnabled )
  {
    Cell = CellHeap::AllocateCell(v8, (int *)this + 88);
    *((_QWORD *)this + 45) = Cell;
    if ( Cell )
    {
      *(_DWORD *)Cell = 0;
      **((_BYTE **)this + 45) = 4;
      *(_BYTE *)(*((_QWORD *)this + 45) + 1LL) = 9;
      *(_BYTE *)(*((_QWORD *)this + 45) + 2LL) = 0;
      v12 = *((_QWORD *)this + 45);
      *(_OWORD *)(v12 + 4) = 0;
      *(_OWORD *)(v12 + 16) = 0;
    }
    else
    {
      v11 = (void *)*((_QWORD *)this + 51);
      *a2 = 14;
      CloseHandle(v11);
    }
  }
  else
  {
    *((_QWORD *)this + 45) = 0;
  }
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 33) = LrpcServerIoHandler;
  result = this;
  *((_QWORD *)this + 46) = 0;
  *((_DWORD *)this + 70) = -623191334;
  *((_DWORD *)this + 104) = 4096;
  return result;
}

```

## disassembly

```asm
0x180090180  mov     [rsp+arg_0], rbx
0x180090185  mov     [rsp+arg_8], rsi
0x18009018a  push    rdi
0x18009018b  sub     rsp, 20h
0x18009018f  mov     rdi, rdx
0x180090192  mov     rbx, rcx
0x180090195  call    ??0RPC_ADDRESS@@IEAA@XZ; RPC_ADDRESS::RPC_ADDRESS(void)
0x18009019a  xorps   xmm0, xmm0
0x18009019d  lea     rax, ??_7LRPC_ADDRESS@@6B@; const LRPC_ADDRESS::`vftable'
0x1800901a4  mov     [rbx], rax
0x1800901a7  lea     rcx, [rbx+1A8h]
0x1800901ae  mov     qword ptr [rbx+0E0h], 4
0x1800901b9  lea     rax, [rbx+0E8h]
0x1800901c0  mov     [rbx+0D8h], rax
0x1800901c7  xor     esi, esi
0x1800901c9  movups  xmmword ptr [rax], xmm0
0x1800901cc  movups  xmmword ptr [rax+10h], xmm0
0x1800901d0  mov     [rbx+120h], esi
0x1800901d6  mov     [rbx+150h], esi
0x1800901dc  call    cs:__imp_RtlInitializeSRWLock
0x1800901e2  mov     dword ptr [rbx+0Ch], 800000h
0x1800901e9  mov     eax, 7FFE0320h
0x1800901ee  mov     [rbx+0D0h], rsi
0x1800901f5  xorps   xmm0, xmm0
0x1800901f8  mov     [rbx+128h], rsi
0x1800901ff  mov     [rbx+124h], esi
0x180090205  mov     rax, [rax]
0x180090208  mov     ecx, ds:7FFE0004h
0x18009020f  imul    rcx, rax
0x180090213  mov     eax, cs:?gPageSize@@3KA; ulong gPageSize
0x180090219  shr     rcx, 18h
0x18009021d  mov     [rbx+14Ch], ecx
0x180090223  mov     ecx, cs:?gNumberOfProcessors@@3IA; uint gNumberOfProcessors
0x180090229  imul    ecx, eax
0x18009022c  shl     eax, 2
0x18009022f  mov     [rbx+148h], esi
0x180090235  mov     [rbx+158h], rsi
0x18009023c  mov     [rbx+170h], rsi
0x180090243  add     ecx, ecx
0x180090245  movups  xmmword ptr [rbx+138h], xmm0
0x18009024c  mov     [rbx+130h], ecx
0x180090252  cmp     ecx, eax
0x180090254  jnb     short loc_18009025C
0x180090256  mov     [rbx+130h], eax
0x18009025c  mov     [rbx+190h], esi
0x180090262  xor     r9d, r9d; lpName
0x180090265  xor     r8d, r8d; bInitialState
0x180090268  mov     [rbx+194h], esi
0x18009026e  xor     edx, edx; bManualReset
0x180090270  xor     ecx, ecx; lpEventAttributes
0x180090272  call    cs:__imp_CreateEventW
0x180090278  mov     [rbx+198h], rax
0x18009027f  test    rax, rax
0x180090282  jz      short loc_1800902D6
0x180090284  cmp     cs:?g_fServerSideDebugInfoEnabled@@3HA, esi; int g_fServerSideDebugInfoEnabled
0x18009028a  jnz     short loc_1800902DE
0x18009028c  mov     [rbx+168h], rsi
0x180090293  lea     rax, ?LrpcServerIoHandler@@YAXPEAUtagLRPC_IO_TARGET@@PEAX@Z; LrpcServerIoHandler(tagLRPC_IO_TARGET *,void *)
0x18009029a  mov     [rbx+110h], rsi
0x1800902a1  mov     [rbx+108h], rax
0x1800902a8  mov     rax, rbx
0x1800902ab  mov     [rbx+170h], rsi
0x1800902b2  mov     rsi, [rsp+28h+arg_8]
0x1800902b7  mov     dword ptr [rbx+118h], 0DADADADAh
0x1800902c1  mov     dword ptr [rbx+1A0h], 1000h
0x1800902cb  mov     rbx, [rsp+28h+arg_0]
0x1800902d0  add     rsp, 20h
0x1800902d4  pop     rdi
0x1800902d5  retn
0x1800902d6  mov     dword ptr [rdi], 0Eh
0x1800902dc  jmp     short loc_180090284
0x1800902de  lea     rdx, [rbx+160h]; int *
0x1800902e5  call    ?AllocateCell@CellHeap@@QEAAPEAUtagDebugFreeCell@@PEAH@Z; CellHeap::AllocateCell(int *)
0x1800902ea  mov     [rbx+168h], rax
0x1800902f1  test    rax, rax
0x1800902f4  jnz     short loc_18009030B
0x1800902f6  mov     rcx, [rbx+198h]; hObject
0x1800902fd  mov     dword ptr [rdi], 0Eh
0x180090303  call    cs:__imp_CloseHandle
0x180090309  jmp     short loc_180090293
0x18009030b  mov     [rax], esi
0x18009030d  xorps   xmm0, xmm0
0x180090310  mov     rax, [rbx+168h]
0x180090317  mov     byte ptr [rax], 4
0x18009031a  mov     rax, [rbx+168h]
0x180090321  mov     byte ptr [rax+1], 9
0x180090325  mov     rax, [rbx+168h]
0x18009032c  mov     [rax+2], sil
0x180090330  mov     rax, [rbx+168h]
0x180090337  movups  xmmword ptr [rax+4], xmm0
0x18009033b  movups  xmmword ptr [rax+10h], xmm0
0x18009033f  jmp     loc_180090293
```
