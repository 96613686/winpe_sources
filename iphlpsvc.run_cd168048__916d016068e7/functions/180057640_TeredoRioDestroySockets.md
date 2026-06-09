# TeredoRioDestroySockets

- ea: `0x180057640`
- end: `0x1800577fc`
- name: `TeredoRioDestroySockets`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180046ddc`
- `0x180056c18`

## callees

- `0x180008200`
- `0x180024240`
- `0x18002e0c0`
- `0x180057640`
- `0x180057804`
- `0x180057f30`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005778e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005778e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057733`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057743`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057753`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057733`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057743`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800576f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800577b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800576f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800577b1`
- `WS2_32!__imp_closesocket` at `0x1800576ab`
- `WS2_32!__imp_closesocket` at `0x1800576ab`

## string_xrefs

- `0x1800577ce`: `onecoreuap\net\netio\iphlpsvc\service\io.c`

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
0x180057640  push    rbx
0x180057642  push    rbp
0x180057643  push    rsi
0x180057644  push    rdi
0x180057645  push    r14
0x180057647  push    r15
0x180057649  sub     rsp, 28h
0x18005764d  mov     rsi, [rcx]
0x180057650  lea     rdx, aTeredoriodestr_0; "TeredoRioDestroySockets"
0x180057657  mov     rdi, rcx
0x18005765a  mov     ecx, 100000h
0x18005765f  call    EventWriteEnterEx
0x180057664  test    rsi, rsi
0x180057667  jz      loc_1800577EE
0x18005766d  cmp     qword ptr [rdi+88h], 0
0x180057675  jz      loc_1800577A5
0x18005767b  mov     r14d, [rsi+0B44h]
0x180057682  xor     ebp, ebp
0x180057684  test    r14d, r14d
0x180057687  jz      loc_18005777E
0x18005768d  mov     rax, [rdi+88h]
0x180057694  mov     rbx, [rax+rbp*8]
0x180057698  test    rbx, rbx
0x18005769b  jz      loc_180057773
0x1800576a1  mov     rcx, [rbx+8]; s
0x1800576a5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800576a9  jz      short loc_1800576BF
0x1800576ab  call    cs:__imp_closesocket
0x1800576b2  nop     dword ptr [rax+rax+00h]
0x1800576b7  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800576bf  mov     rcx, rbx
0x1800576c2  call    TeredoRioRestorePacketsToTunnel
0x1800576c7  mov     rcx, [rbx+98h]
0x1800576ce  test    rcx, rcx
0x1800576d1  jz      short loc_1800576EA
0x1800576d3  mov     rax, [rsi+0AF8h]
0x1800576da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576df  mov     qword ptr [rbx+98h], 0
0x1800576ea  mov     rcx, [rbx+0A8h]; hObject
0x1800576f1  test    rcx, rcx
0x1800576f4  jz      short loc_18005770D
0x1800576f6  call    cs:__imp_CloseHandle
0x1800576fd  nop     dword ptr [rax+rax+00h]
0x180057702  mov     qword ptr [rbx+0A8h], 0
0x18005770d  mov     rcx, [rbx+0A0h]; lpAddress
0x180057714  test    rcx, rcx
0x180057717  jz      short loc_180057729
0x180057719  call    TeredoRioFreeNumaMemory
0x18005771e  mov     qword ptr [rbx+0A0h], 0
0x180057729  cmp     byte ptr [rbx+14h], 1
0x18005772d  jnz     short loc_180057763
0x18005772f  lea     rcx, [rbx+18h]; lpCriticalSection
0x180057733  call    cs:__imp_DeleteCriticalSection
0x18005773a  nop     dword ptr [rax+rax+00h]
0x18005773f  lea     rcx, [rbx+40h]; lpCriticalSection
0x180057743  call    cs:__imp_DeleteCriticalSection
0x18005774a  nop     dword ptr [rax+rax+00h]
0x18005774f  lea     rcx, [rbx+68h]; lpCriticalSection
0x180057753  call    cs:__imp_DeleteCriticalSection
0x18005775a  nop     dword ptr [rax+rax+00h]
0x18005775f  mov     byte ptr [rbx+14h], 0
0x180057763  mov     rcx, [rdi+88h]
0x18005776a  mov     rcx, [rcx+rbp*8]; lpAddress
0x18005776e  call    TeredoRioFreeNumaMemory
0x180057773  inc     ebp
0x180057775  cmp     ebp, r14d
0x180057778  jb      loc_18005768D
0x18005777e  mov     r8, [rdi+88h]; lpMem
0x180057785  xor     edx, edx; dwFlags
0x180057787  mov     rcx, [rsi+0A10h]; hHeap
0x18005778e  call    cs:__imp_HeapFree
0x180057795  nop     dword ptr [rax+rax+00h]
0x18005779a  mov     qword ptr [rdi+88h], 0
0x1800577a5  mov     rcx, [rdi+98h]; hObject
0x1800577ac  test    rcx, rcx
0x1800577af  jz      short loc_1800577C8
0x1800577b1  call    cs:__imp_CloseHandle
0x1800577b8  nop     dword ptr [rax+rax+00h]
0x1800577bd  mov     qword ptr [rdi+98h], 0
0x1800577c8  mov     r8d, 123Eh
0x1800577ce  lea     rdx, aOnecoreuapNetN_22; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800577d5  mov     rcx, rsi
0x1800577d8  call    TeredoDereferenceIoEx
0x1800577dd  lea     rdx, aTeredoriodestr_0; "TeredoRioDestroySockets"
0x1800577e4  mov     ecx, 100000h
0x1800577e9  call    EventWriteLeaveEx
0x1800577ee  add     rsp, 28h
0x1800577f2  pop     r15
0x1800577f4  pop     r14
0x1800577f6  pop     rdi
0x1800577f7  pop     rsi
0x1800577f8  pop     rbp
0x1800577f9  pop     rbx
0x1800577fa  retn
```
