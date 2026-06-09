# CUACCheck::s_InitalizeWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180003cd0`
- end: `0x180003daa`
- name: `?s_InitalizeWorkCallback@CUACCheck@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `218`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cd0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003d05`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003d05`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003ce0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003ce0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003d8a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003d8a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003d7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003d7e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180003d46`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180003d46`
- `SHELL32!SHEnableServiceObject` at `0x180003d29`
- `SHELL32!SHEnableServiceObject` at `0x180003d29`

## pseudocode

```c
void __fastcall CUACCheck::s_InitalizeWorkCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  HANDLE EventW; // rax
  PTP_WAIT ThreadpoolWait; // rax

  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, L"{43a2b8d7-6fed-4c18-bd36-b4630d61afb5}");
    *((_QWORD *)Context + 28) = EventW;
    if ( EventW )
    {
      if ( (int)SHEnableServiceObject(qword_18000D690, 1) >= 0 )
      {
        ThreadpoolWait = CreateThreadpoolWait(CUACCheck::s_WaitCallback, Context, 0);
        *((_QWORD *)Context + 29) = ThreadpoolWait;
        if ( ThreadpoolWait )
        {
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Context + 8LL))(Context);
          SetThreadpoolWait(*((PTP_WAIT *)Context + 29), *((HANDLE *)Context + 28), 0);
        }
      }
    }
    CoUninitialize();
  }
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)Context + 16LL))(Context);
}

```

## disassembly

```asm
0x180003cd0  push    rbx
0x180003cd2  sub     rsp, 20h
0x180003cd6  mov     rbx, rdx
0x180003cd9  xor     ecx, ecx; pvReserved
0x180003cdb  mov     edx, 6; dwCoInit
0x180003ce0  call    cs:__imp_CoInitializeEx
0x180003ce7  nop     dword ptr [rax+rax+00h]
0x180003cec  test    eax, eax
0x180003cee  js      loc_180003D96
0x180003cf4  lea     r9, Name; "{43a2b8d7-6fed-4c18-bd36-b4630d61afb5}"
0x180003cfb  xor     r8d, r8d; bInitialState
0x180003cfe  mov     edx, 1; bManualReset
0x180003d03  xor     ecx, ecx; lpEventAttributes
0x180003d05  call    cs:__imp_CreateEventW
0x180003d0c  nop     dword ptr [rax+rax+00h]
0x180003d11  mov     [rbx+0E0h], rax
0x180003d18  test    rax, rax
0x180003d1b  jz      short loc_180003D8A
0x180003d1d  mov     edx, 1
0x180003d22  lea     rcx, qword_18000D690
0x180003d29  call    cs:__imp_SHEnableServiceObject
0x180003d30  nop     dword ptr [rax+rax+00h]
0x180003d35  test    eax, eax
0x180003d37  js      short loc_180003D8A
0x180003d39  xor     r8d, r8d; pcbe
0x180003d3c  lea     rcx, ?s_WaitCallback@CUACCheck@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180003d43  mov     rdx, rbx; pv
0x180003d46  call    cs:__imp_CreateThreadpoolWait
0x180003d4d  nop     dword ptr [rax+rax+00h]
0x180003d52  mov     [rbx+0E8h], rax
0x180003d59  test    rax, rax
0x180003d5c  jz      short loc_180003D8A
0x180003d5e  mov     rax, [rbx]
0x180003d61  mov     rcx, rbx
0x180003d64  mov     rax, [rax+8]
0x180003d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d6d  mov     rdx, [rbx+0E0h]; h
0x180003d74  xor     r8d, r8d; pftTimeout
0x180003d77  mov     rcx, [rbx+0E8h]; pwa
0x180003d7e  call    cs:__imp_SetThreadpoolWait
0x180003d85  nop     dword ptr [rax+rax+00h]
0x180003d8a  call    cs:__imp_CoUninitialize
0x180003d91  nop     dword ptr [rax+rax+00h]
0x180003d96  mov     rax, [rbx]
0x180003d99  mov     rcx, rbx
0x180003d9c  mov     rax, [rax+10h]
0x180003da0  add     rsp, 20h
0x180003da4  pop     rbx
0x180003da5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
