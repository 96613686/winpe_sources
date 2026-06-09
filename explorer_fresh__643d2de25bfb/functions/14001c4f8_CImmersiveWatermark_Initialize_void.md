# CImmersiveWatermark::Initialize(void)

- ea: `0x14001c4f8`
- end: `0x14001c633`
- name: `?Initialize@CImmersiveWatermark@@QEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400a3f04`

## callees

- `0x14001c330`
- `0x14001c4f8`
- `0x14001c63c`
- `0x14001d214`
- `0x140089e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001c5da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001c5da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14001c5a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14001c5a7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14001c5c4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14001c5c4`
- `USER32!CreateWindowInBand` at `0x14001c56a`
- `USER32!CreateWindowInBand` at `0x14001c56a`
- `USER32!__imp_SetBrokeredForeground` at `0x14001c58e`
- `USER32!__imp_SetBrokeredForeground` at `0x14001c58e`

## pseudocode

```c
__int64 __fastcall CImmersiveWatermark::Initialize(CImmersiveWatermark *pv)
{
  __int64 WindowInBand; // rax
  int Error; // ebx
  struct _TP_WORK *ThreadpoolWork; // rsi
  HANDLE EventW; // rax

  CImmersiveWatermark::_RegisterWindowClass(pv);
  WindowInBand = CreateWindowInBand(8, *(unsigned __int16 *)pv, 0, 0x80000000LL, 0, 0, 0, 0, 0, 0, &_ImageBase, pv, 14);
  *((_QWORD *)pv + 5) = WindowInBand;
  if ( WindowInBand || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    SetBrokeredForeground(*((_QWORD *)pv + 5));
    ThreadpoolWork = CreateThreadpoolWork(CImmersiveWatermark::_s_RegisterLicensingPolicyChangeEvent, pv, 0);
    if ( ThreadpoolWork )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    if ( Error >= 0 )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)pv + 36) = EventW;
      if ( EventW || (Error = ResultFromKnownLastError(), Error >= 0) )
        Error = CImmersiveWatermark::_LaunchKernelThread(pv);
    }
  }
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14024D5A8);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x14001c4f8  mov     [rsp+arg_0], rbx
0x14001c4fd  mov     [rsp+arg_8], rsi
0x14001c502  push    rdi
0x14001c503  sub     rsp, 70h
0x14001c507  mov     rdi, rcx
0x14001c50a  call    ?_RegisterWindowClass@CImmersiveWatermark@@AEAAXXZ; CImmersiveWatermark::_RegisterWindowClass(void)
0x14001c50f  movzx   edx, word ptr [rdi]
0x14001c512  lea     rax, __ImageBase
0x14001c519  mov     [rsp+78h+var_18], 0Eh
0x14001c521  xor     r8d, r8d
0x14001c524  mov     [rsp+78h+var_20], rdi
0x14001c529  mov     r9d, 80000000h
0x14001c52f  mov     [rsp+78h+var_28], rax
0x14001c534  mov     [rsp+78h+var_30], 0
0x14001c53d  mov     [rsp+78h+var_38], 0
0x14001c546  lea     ecx, [r8+8]
0x14001c54a  mov     [rsp+78h+var_40], 0
0x14001c552  mov     [rsp+78h+var_48], 0
0x14001c55a  mov     [rsp+78h+var_50], 0
0x14001c562  mov     [rsp+78h+var_58], 0
0x14001c56a  call    cs:__imp_CreateWindowInBand
0x14001c571  nop     dword ptr [rax+rax+00h]
0x14001c576  mov     [rdi+28h], rax
0x14001c57a  test    rax, rax
0x14001c57d  jnz     short loc_14001C58A
0x14001c57f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001c584  mov     ebx, eax
0x14001c586  test    eax, eax
0x14001c588  js      short loc_14001C5FC
0x14001c58a  mov     rcx, [rdi+28h]
0x14001c58e  call    cs:__imp_SetBrokeredForeground
0x14001c595  nop     dword ptr [rax+rax+00h]
0x14001c59a  xor     r8d, r8d; pcbe
0x14001c59d  lea     rcx, ?_s_RegisterLicensingPolicyChangeEvent@CImmersiveWatermark@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14001c5a4  mov     rdx, rdi; pv
0x14001c5a7  call    cs:__imp_CreateThreadpoolWork
0x14001c5ae  nop     dword ptr [rax+rax+00h]
0x14001c5b3  mov     rsi, rax
0x14001c5b6  test    rax, rax
0x14001c5b9  jz      short loc_14001C62A
0x14001c5bb  xor     ebx, ebx
0x14001c5bd  test    ebx, ebx
0x14001c5bf  js      short loc_14001C5FC
0x14001c5c1  mov     rcx, rsi; pwk
0x14001c5c4  call    cs:__imp_SubmitThreadpoolWork
0x14001c5cb  nop     dword ptr [rax+rax+00h]
0x14001c5d0  xor     r9d, r9d; lpName
0x14001c5d3  xor     r8d, r8d; bInitialState
0x14001c5d6  xor     edx, edx; bManualReset
0x14001c5d8  xor     ecx, ecx; lpEventAttributes
0x14001c5da  call    cs:__imp_CreateEventW
0x14001c5e1  nop     dword ptr [rax+rax+00h]
0x14001c5e6  mov     [rdi+120h], rax
0x14001c5ed  test    rax, rax
0x14001c5f0  jz      short loc_14001C61D
0x14001c5f2  mov     rcx, rdi; pv
0x14001c5f5  call    ?_LaunchKernelThread@CImmersiveWatermark@@AEAAJXZ; CImmersiveWatermark::_LaunchKernelThread(void)
0x14001c5fa  mov     ebx, eax
0x14001c5fc  lea     rcx, dword_14024D5A8; CallbackContext
0x14001c603  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14001c608  lea     r11, [rsp+78h+var_8]
0x14001c60d  mov     eax, ebx
0x14001c60f  mov     rbx, [r11+10h]
0x14001c613  mov     rsi, [r11+18h]
0x14001c617  mov     rsp, r11
0x14001c61a  pop     rdi
0x14001c61b  retn
0x14001c61d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001c622  mov     ebx, eax
0x14001c624  test    eax, eax
0x14001c626  js      short loc_14001C5FC
0x14001c628  jmp     short loc_14001C5F2
0x14001c62a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001c62f  mov     ebx, eax
0x14001c631  jmp     short loc_14001C5BD
```
