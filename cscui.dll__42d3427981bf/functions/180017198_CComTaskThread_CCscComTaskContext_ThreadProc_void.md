# CComTaskThread<CCscComTaskContext>::_ThreadProc(void)

- ea: `0x180017198`
- end: `0x1800172ff`
- name: `?_ThreadProc@?$CComTaskThread@VCCscComTaskContext@@@@AEAAXXZ`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017310`
- `0x180044ff0`

## callees

- `0x180008b40`
- `0x180017198`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800171a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800171a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800171f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800172b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800171f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800172b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800172f8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180017241`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180017241`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001722f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001722f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800172db`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800172db`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800171c5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800171c5`

## pseudocode

```c
BOOL __fastcall CComTaskThread<CCscComTaskContext>::_ThreadProc(__int64 a1)
{
  DWORD CurrentThreadId; // eax
  __int64 v3; // rcx
  DWORD v4; // eax
  HRESULT v5; // eax
  int v6; // eax
  int v7; // ebp
  int v8; // ecx
  int v9; // r14d
  __int64 v10; // rdi
  int v11; // ebx
  void *v12; // rcx
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  v3 = *(_QWORD *)(a1 + 56);
  *(_DWORD *)(a1 + 100) = CurrentThreadId;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v5 = CoInitializeEx(0, v4);
  *(_DWORD *)(a1 + 104) = v5;
  if ( v5 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 56) + 16LL))(*(_QWORD *)(a1 + 56));
    *(_DWORD *)(a1 + 104) = v6;
    if ( v6 >= 0 )
    {
      if ( SetEvent(*(HANDLE *)(a1 + 64)) )
      {
        v7 = 0;
        while ( 1 )
        {
          dwindex = 0;
          if ( CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)(a1 + 72), &dwindex) )
            break;
          ResetEvent(*(HANDLE *)(a1 + 72));
          v8 = *(_DWORD *)(a1 + 108);
          if ( v8 )
          {
            if ( v8 == 1 )
            {
              *(_DWORD *)(a1 + 104) = 0;
              v7 = 1;
            }
          }
          else
          {
            v9 = -2147164120;
            v10 = *(_QWORD *)(a1 + 56);
            v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 48) + 8LL))(*(_QWORD *)(a1 + 48));
            if ( v11 == (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
              v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 48) + 16LL))(
                     *(_QWORD *)(a1 + 48),
                     *(_QWORD *)(a1 + 56));
            *(_DWORD *)(*(_QWORD *)(a1 + 48) + 8LL) = v9;
            *(_DWORD *)(a1 + 104) = v9;
          }
          SetEvent(*(HANDLE *)(a1 + 80));
          if ( v7 )
            goto LABEL_16;
        }
        *(_DWORD *)(a1 + 104) = -2147467259;
      }
      else
      {
        *(_DWORD *)(a1 + 104) = ResultFromLastError();
      }
LABEL_16:
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 56) + 24LL))(*(_QWORD *)(a1 + 56));
    }
    CoUninitialize();
  }
  v12 = *(void **)(a1 + 64);
  *(_DWORD *)(a1 + 100) = 0;
  return SetEvent(v12);
}

```

## disassembly

```asm
0x180017198  push    rbx
0x18001719a  push    rbp
0x18001719b  push    rsi
0x18001719c  push    rdi
0x18001719d  push    r14
0x18001719f  push    r15
0x1800171a1  sub     rsp, 38h
0x1800171a5  mov     rsi, rcx
0x1800171a8  call    cs:__imp_GetCurrentThreadId
0x1800171ae  mov     rcx, [rsi+38h]
0x1800171b2  mov     [rsi+64h], eax
0x1800171b5  mov     rax, [rcx]
0x1800171b8  mov     rax, [rax+8]
0x1800171bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171c1  mov     edx, eax; dwCoInit
0x1800171c3  xor     ecx, ecx; pvReserved
0x1800171c5  call    cs:__imp_CoInitializeEx
0x1800171cb  mov     [rsi+68h], eax
0x1800171ce  test    eax, eax
0x1800171d0  js      loc_1800172E1
0x1800171d6  mov     rcx, [rsi+38h]
0x1800171da  mov     rax, [rcx]
0x1800171dd  mov     rax, [rax+10h]
0x1800171e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e6  mov     [rsi+68h], eax
0x1800171e9  test    eax, eax
0x1800171eb  js      loc_1800172DB
0x1800171f1  mov     rcx, [rsi+40h]; hEvent
0x1800171f5  call    cs:__imp_SetEvent
0x1800171fb  test    eax, eax
0x1800171fd  jnz     short loc_18001720C
0x1800171ff  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180017204  mov     [rsi+68h], eax
0x180017207  jmp     loc_1800172CB
0x18001720c  xor     ebp, ebp
0x18001720e  lea     rax, [rsp+68h+dwindex]
0x180017213  mov     [rsp+68h+dwindex], 0
0x18001721b  lea     r9, [rsi+48h]; pHandles
0x18001721f  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180017224  mov     r8d, 1; cHandles
0x18001722a  or      edx, 0FFFFFFFFh; dwTimeout
0x18001722d  xor     ecx, ecx; dwFlags
0x18001722f  call    cs:__imp_CoWaitForMultipleHandles
0x180017235  test    eax, eax
0x180017237  jnz     loc_1800172C4
0x18001723d  mov     rcx, [rsi+48h]; hEvent
0x180017241  call    cs:__imp_ResetEvent
0x180017247  mov     ecx, [rsi+6Ch]
0x18001724a  test    ecx, ecx
0x18001724c  jz      short loc_18001725E
0x18001724e  cmp     ecx, 1
0x180017251  jnz     short loc_1800172B0
0x180017253  mov     dword ptr [rsi+68h], 0
0x18001725a  mov     ebp, ecx
0x18001725c  jmp     short loc_1800172B0
0x18001725e  mov     rcx, [rsi+30h]
0x180017262  mov     r14d, 8004E028h
0x180017268  mov     rdi, [rsi+38h]
0x18001726c  mov     rax, [rcx]
0x18001726f  mov     rax, [rax+8]
0x180017273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017278  mov     rdx, [rdi]
0x18001727b  mov     ebx, eax
0x18001727d  mov     rcx, rdi
0x180017280  mov     rax, [rdx+8]
0x180017284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017289  cmp     ebx, eax
0x18001728b  jnz     short loc_1800172A4
0x18001728d  mov     rcx, [rsi+30h]
0x180017291  mov     rdx, [rsi+38h]
0x180017295  mov     rax, [rcx]
0x180017298  mov     rax, [rax+10h]
0x18001729c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a1  mov     r14d, eax
0x1800172a4  mov     rcx, [rsi+30h]
0x1800172a8  mov     [rcx+8], r14d
0x1800172ac  mov     [rsi+68h], r14d
0x1800172b0  mov     rcx, [rsi+50h]; hEvent
0x1800172b4  call    cs:__imp_SetEvent
0x1800172ba  test    ebp, ebp
0x1800172bc  jz      loc_18001720E
0x1800172c2  jmp     short loc_1800172CB
0x1800172c4  mov     dword ptr [rsi+68h], 80004005h
0x1800172cb  mov     rcx, [rsi+38h]
0x1800172cf  mov     rax, [rcx]
0x1800172d2  mov     rax, [rax+18h]
0x1800172d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172db  call    cs:__imp_CoUninitialize
0x1800172e1  mov     rcx, [rsi+40h]
0x1800172e5  mov     dword ptr [rsi+64h], 0
0x1800172ec  add     rsp, 38h
0x1800172f0  pop     r15
0x1800172f2  pop     r14
0x1800172f4  pop     rdi
0x1800172f5  pop     rsi
0x1800172f6  pop     rbp
0x1800172f7  pop     rbx
0x1800172f8  jmp     cs:__imp_SetEvent
```
