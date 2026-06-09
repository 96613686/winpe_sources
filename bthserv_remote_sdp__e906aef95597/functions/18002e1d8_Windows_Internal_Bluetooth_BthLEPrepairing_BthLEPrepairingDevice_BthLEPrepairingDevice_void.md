# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::~BthLEPrepairingDevice(void)

- ea: `0x18002e1d8`
- end: `0x18002e3d3`
- name: `??1BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ`
- size: `507`
- prototype: `void __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18002b310`
- `0x18002cf9c`

## callees

- `0x180001b94`
- `0x180012384`
- `0x18002e1d8`
- `0x180030c38`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002e355`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002e355`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002e346`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002e346`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e332`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e312`
- `deviceassociation!DafMemFree` at `0x18002e370`
- `deviceassociation!DafMemFree` at `0x18002e370`
- `deviceassociation!DafCloseAssociationContext` at `0x18002e2e6`
- `deviceassociation!DafCloseAssociationContext` at `0x18002e2e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::~BthLEPrepairingDevice(
        PTP_TIMER *this)
{
  bool v2; // dl
  const struct std::nothrow_t *v3; // rdx
  __int64 v4; // r8
  PTP_TIMER v5; // rcx
  PTP_TIMER v6; // rcx
  PTP_TIMER v7; // rcx
  PTP_TIMER v8; // rcx
  PTP_TIMER v9; // rcx
  struct _TP_TIMER *v10; // rdi
  PTP_TIMER v11; // rcx
  volatile signed __int32 *v12; // rbx

  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)this);
  LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_BYTE)v3,
      (_BYTE)v4,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v5 = this[257];
  if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  v6 = this[256];
  if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  v7 = this[255];
  if ( v7 )
    DafCloseAssociationContext(v7, v3, v4);
  v8 = this[16];
  if ( v8 )
    operator delete(v8, v3);
  v9 = this[15];
  if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  v10 = this[9];
  if ( v10 )
  {
    SetThreadpoolTimer(this[9], 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
  v11 = this[8];
  this[8] = 0;
  if ( v11 )
    DafMemFree(v11, v3, v4);
  v12 = (volatile signed __int32 *)this[1];
  if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *, const struct std::nothrow_t *, __int64))v12)(v12, v3, v4);
    if ( !_InterlockedDecrement(v12 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
  }
}

```

## disassembly

```asm
0x18002e1d8  mov     [rsp+arg_0], rbx
0x18002e1dd  mov     [rsp+arg_8], rbp
0x18002e1e2  mov     [rsp+arg_10], rsi
0x18002e1e7  push    rdi
0x18002e1e8  sub     rsp, 50h
0x18002e1ec  mov     rbx, rcx
0x18002e1ef  lea     rdi, WPP_GLOBAL_Control
0x18002e1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1fd  cmp     rcx, rdi
0x18002e200  jz      short loc_18002E20C
0x18002e202  cmp     byte ptr [rcx+19h], 5
0x18002e206  jb      short loc_18002E20C
0x18002e208  mov     dl, 1
0x18002e20a  jmp     short loc_18002E20E
0x18002e20c  xor     dl, dl
0x18002e20e  lea     rsi, WPP_RECORDER_INITIALIZED
0x18002e215  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18002e21c  setnz   r8b
0x18002e220  lea     rbp, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e227  test    dl, dl
0x18002e229  jnz     short loc_18002E230
0x18002e22b  test    r8b, r8b
0x18002e22e  jz      short loc_18002E24E
0x18002e230  mov     [rsp+58h+var_10], rbx
0x18002e235  mov     [rsp+58h+var_20], rbp
0x18002e23a  mov     [rsp+58h+var_28], 0Ah
0x18002e241  mov     r9, [rcx+28h]
0x18002e245  mov     rcx, [rcx+10h]
0x18002e249  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002e24e  mov     rcx, rbx; this
0x18002e251  call    ?Stop@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(void)
0x18002e256  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e25d  cmp     rcx, rdi
0x18002e260  jz      short loc_18002E26C
0x18002e262  cmp     byte ptr [rcx+19h], 5
0x18002e266  jb      short loc_18002E26C
0x18002e268  mov     dl, 1
0x18002e26a  jmp     short loc_18002E26E
0x18002e26c  xor     dl, dl
0x18002e26e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18002e275  setnz   r8b
0x18002e279  test    dl, dl
0x18002e27b  jnz     short loc_18002E282
0x18002e27d  test    r8b, r8b
0x18002e280  jz      short loc_18002E2A0
0x18002e282  mov     [rsp+58h+var_10], rbx
0x18002e287  mov     [rsp+58h+var_20], rbp
0x18002e28c  mov     [rsp+58h+var_28], 0Bh
0x18002e293  mov     r9, [rcx+28h]
0x18002e297  mov     rcx, [rcx+10h]
0x18002e29b  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002e2a0  mov     rcx, [rbx+808h]; hObject
0x18002e2a7  lea     rax, [rcx-1]
0x18002e2ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e2af  ja      short loc_18002E2BD
0x18002e2b1  call    cs:__imp_CloseHandle
0x18002e2b8  nop     dword ptr [rax+rax+00h]
0x18002e2bd  mov     rcx, [rbx+800h]; hObject
0x18002e2c4  lea     rax, [rcx-1]
0x18002e2c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e2cc  ja      short loc_18002E2DA
0x18002e2ce  call    cs:__imp_CloseHandle
0x18002e2d5  nop     dword ptr [rax+rax+00h]
0x18002e2da  mov     rcx, [rbx+7F8h]
0x18002e2e1  test    rcx, rcx
0x18002e2e4  jz      short loc_18002E2F3
0x18002e2e6  call    cs:__imp_DafCloseAssociationContext
0x18002e2ed  nop     dword ptr [rax+rax+00h]
0x18002e2f2  nop
0x18002e2f3  mov     rcx, [rbx+80h]; void *
0x18002e2fa  test    rcx, rcx
0x18002e2fd  jz      short loc_18002E304
0x18002e2ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e304  mov     rcx, [rbx+78h]; hObject
0x18002e308  lea     rax, [rcx-1]
0x18002e30c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e310  ja      short loc_18002E31E
0x18002e312  call    cs:__imp_CloseHandle
0x18002e319  nop     dword ptr [rax+rax+00h]
0x18002e31e  mov     rdi, [rbx+48h]
0x18002e322  test    rdi, rdi
0x18002e325  jz      short loc_18002E362
0x18002e327  xor     r9d, r9d; msWindowLength
0x18002e32a  xor     r8d, r8d; msPeriod
0x18002e32d  xor     edx, edx; pftDueTime
0x18002e32f  mov     rcx, rdi; pti
0x18002e332  call    cs:__imp_SetThreadpoolTimer
0x18002e339  nop     dword ptr [rax+rax+00h]
0x18002e33e  mov     edx, 1; fCancelPendingCallbacks
0x18002e343  mov     rcx, rdi; pti
0x18002e346  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002e34d  nop     dword ptr [rax+rax+00h]
0x18002e352  mov     rcx, rdi; pti
0x18002e355  call    cs:__imp_CloseThreadpoolTimer
0x18002e35c  nop     dword ptr [rax+rax+00h]
0x18002e361  nop
0x18002e362  mov     rcx, [rbx+40h]
0x18002e366  and     qword ptr [rbx+40h], 0
0x18002e36b  test    rcx, rcx
0x18002e36e  jz      short loc_18002E37D
0x18002e370  call    cs:__imp_DafMemFree
0x18002e377  nop     dword ptr [rax+rax+00h]
0x18002e37c  nop
0x18002e37d  mov     rbx, [rbx+8]
0x18002e381  test    rbx, rbx
0x18002e384  jz      short loc_18002E3BD
0x18002e386  or      edi, 0FFFFFFFFh
0x18002e389  mov     eax, edi
0x18002e38b  lock xadd [rbx+8], eax
0x18002e390  add     eax, edi
0x18002e392  jnz     short loc_18002E3BD
0x18002e394  mov     rax, [rbx]
0x18002e397  mov     rcx, rbx
0x18002e39a  mov     rax, [rax]
0x18002e39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3a2  mov     eax, edi
0x18002e3a4  lock xadd [rbx+0Ch], eax
0x18002e3a9  add     eax, edi
0x18002e3ab  jnz     short loc_18002E3BD
0x18002e3ad  mov     rax, [rbx]
0x18002e3b0  mov     rcx, rbx
0x18002e3b3  mov     rax, [rax+8]
0x18002e3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3bc  nop
0x18002e3bd  mov     rbx, [rsp+58h+arg_0]
0x18002e3c2  mov     rbp, [rsp+58h+arg_8]
0x18002e3c7  mov     rsi, [rsp+58h+arg_10]
0x18002e3cc  add     rsp, 50h
0x18002e3d0  pop     rdi
0x18002e3d1  retn
```
