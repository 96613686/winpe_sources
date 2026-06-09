# CModuleFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1400045f0`
- end: `0x140004762`
- name: `?CreateInstance@CModuleFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `370`
- prototype: `__int64 __fastcall(CModuleFactory *this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400045f0`
- `0x140004870`
- `0x140005014`
- `0x1400097e6`
- `0x14000a010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1400046b6`
- `KERNEL32!WaitForSingleObject` at `0x1400046b6`

## pseudocode

```c
__int64 __fastcall CModuleFactory::CreateInstance(
        CModuleFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  signed __int64 v7; // rdi
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v7 = (this - (CModuleFactory *)&g_rgcfModule) >> 3;
  if ( memcmp_0(a3, &IID_IUnknown, 0x10u) && memcmp_0(a3, &rgCLSID + v7, 0x10u) )
    return 2147500034LL;
  _InterlockedIncrement(&g_cInstances);
  if ( g_fWeWantToStop
    || g_hShutdownTimer && (KERNEL32::CancelWaitableTimer(), WaitForSingleObject(g_hShutdownTimer, 0) != 258) )
  {
    *a4 = 0;
    result = 2148007944LL;
    _InterlockedDecrement(&g_cInstances);
  }
  else
  {
    *a4 = (void *)((__int64 (*)(void))(&rgFactory)[v7])();
    _InterlockedDecrement(&g_cInstances);
    if ( *a4 )
    {
      return 0;
    }
    else
    {
      if ( g_hShutdownTimer )
      {
        if ( (unsigned int)FCanStopService() )
        {
          v8 = -3000000000LL;
          ((void (__fastcall *)(HANDLE, __int64 *, _QWORD, _QWORD, _QWORD, _DWORD))KERNEL32::SetWaitableTimer)(
            g_hShutdownTimer,
            &v8,
            0,
            0,
            0,
            0);
        }
      }
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400045f0  mov     [rsp+arg_8], rbx
0x1400045f5  mov     [rsp+arg_10], rsi
0x1400045fa  push    rdi
0x1400045fb  sub     rsp, 40h
0x1400045ff  mov     rbx, r9
0x140004602  mov     rsi, r8
0x140004605  mov     rdi, rcx
0x140004608  test    r9, r9
0x14000460b  jnz     short loc_140004617
0x14000460d  mov     eax, 80070057h
0x140004612  jmp     loc_140004752
0x140004617  mov     qword ptr [r9], 0
0x14000461e  test    rdx, rdx
0x140004621  jz      short loc_14000462D
0x140004623  mov     eax, 80040110h
0x140004628  jmp     loc_140004752
0x14000462d  lea     rax, ?g_rgcfModule@@3PAVCModuleFactory@@A; CModuleFactory near * g_rgcfModule
0x140004634  mov     r8d, 10h; Size
0x14000463a  sub     rdi, rax
0x14000463d  lea     rdx, IID_IUnknown; Buf2
0x140004644  mov     rcx, rsi; Buf1
0x140004647  sar     rdi, 3
0x14000464b  call    memcmp_0
0x140004650  test    eax, eax
0x140004652  jz      short loc_140004681
0x140004654  lea     rax, ?rgCLSID@@3QBU_GUID@@B; _GUID const near * const rgCLSID
0x14000465b  mov     rdx, rdi
0x14000465e  shl     rdx, 4
0x140004662  mov     r8d, 10h; Size
0x140004668  add     rdx, rax; Buf2
0x14000466b  mov     rcx, rsi; Buf1
0x14000466e  call    memcmp_0
0x140004673  test    eax, eax
0x140004675  jz      short loc_140004681
0x140004677  mov     eax, 80004002h
0x14000467c  jmp     loc_140004752
0x140004681  lock inc cs:?g_cInstances@@3JA; long g_cInstances
0x140004688  cmp     cs:?g_fWeWantToStop@@3_NA, 0; bool g_fWeWantToStop
0x14000468f  jnz     loc_14000473F
0x140004695  mov     rcx, cs:?g_hShutdownTimer@@3PEAXEA; void * g_hShutdownTimer
0x14000469c  test    rcx, rcx
0x14000469f  jz      short loc_1400046C3
0x1400046a1  mov     rax, cs:?CancelWaitableTimer@KERNEL32@@3P6AHPEAX@ZEA; int (*KERNEL32::CancelWaitableTimer)(void *)
0x1400046a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046ad  mov     rcx, cs:?g_hShutdownTimer@@3PEAXEA; hHandle
0x1400046b4  xor     edx, edx; dwMilliseconds
0x1400046b6  call    cs:__imp_WaitForSingleObject
0x1400046bc  cmp     eax, 102h
0x1400046c1  jnz     short loc_14000473F
0x1400046c3  lea     rax, ?rgFactory@@3QBQ6APEAUIUnknown@@XZB; IUnknown * (*const near * const rgFactory)(void)
0x1400046ca  mov     rax, ds:(?rgFactory@@3QBQ6APEAUIUnknown@@XZB - 14000B0E8h)[rax+rdi*8]; IUnknown * (*const near * const rgFactory)(void)
0x1400046ce  call    _guard_dispatch_icall$thunk$10345483385596137414; CreateServer(void) ...
0x1400046d3  mov     [rbx], rax
0x1400046d6  lock dec cs:?g_cInstances@@3JA; long g_cInstances
0x1400046dd  cmp     qword ptr [rbx], 0
0x1400046e1  jnz     short loc_14000473B
0x1400046e3  cmp     cs:?g_hShutdownTimer@@3PEAXEA, 0; void * g_hShutdownTimer
0x1400046eb  jz      short loc_140004734
0x1400046ed  call    ?FCanStopService@@YAHXZ; FCanStopService(void)
0x1400046f2  test    eax, eax
0x1400046f4  jz      short loc_140004734
0x1400046f6  mov     rcx, cs:?g_hShutdownTimer@@3PEAXEA; void * g_hShutdownTimer
0x1400046fd  lea     rdx, [rsp+48h+arg_0]
0x140004702  mov     rax, 0FFFFFFFF4D2FA200h
0x14000470c  mov     [rsp+48h+var_20], 0
0x140004714  mov     [rsp+48h+arg_0], rax
0x140004719  xor     r9d, r9d
0x14000471c  mov     rax, cs:?SetWaitableTimer@KERNEL32@@3P6AHPEAXPEBT_LARGE_INTEGER@@JP6AX0KK@Z0H@ZEA; int (*KERNEL32::SetWaitableTimer)(void *,_LARGE_INTEGER const *,long,void (*)(void *,ulong,ulong),void *,int)
0x140004723  xor     r8d, r8d
0x140004726  mov     [rsp+48h+var_28], 0
0x14000472f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004734  mov     eax, 8007000Eh
0x140004739  jmp     short loc_140004752
0x14000473b  xor     eax, eax
0x14000473d  jmp     short loc_140004752
0x14000473f  mov     qword ptr [rbx], 0
0x140004746  mov     eax, 80080008h
0x14000474b  lock dec cs:?g_cInstances@@3JA; long g_cInstances
0x140004752  mov     rbx, [rsp+48h+arg_8]
0x140004757  mov     rsi, [rsp+48h+arg_10]
0x14000475c  add     rsp, 40h
0x140004760  pop     rdi
0x140004761  retn
```
