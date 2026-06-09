# Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::SetApiSamplingStopTimerMinutes(ulong)

- ea: `0x1800c9df8`
- end: `0x1800c9eb3`
- name: `?SetApiSamplingStopTimerMinutes@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAXK@Z`
- size: `187`
- prototype: `void __fastcall(Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c9788`

## callees

- `0x1800152d0`
- `0x1800c9df8`
- `0x1800ca0cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9e6f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800c9e29`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800c9e29`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800c9e65`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800c9e65`

## string_xrefs

- `0x1800c9e82`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::SetApiSamplingStopTimerMinutes`
- `0x1800c9e75`: `Failed to create counter timer [%d]`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::SetApiSamplingStopTimerMinutes(
        Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *this,
        int a2)
{
  void **v4; // rdi
  void *v5; // rdx
  DWORD LastError; // eax

  if ( a2 != dword_1800FF890 )
  {
    v4 = (void **)((char *)this + 16);
    v5 = (void *)*((_QWORD *)this + 2);
    if ( v5 )
    {
      DeleteTimerQueueTimer(0, v5, 0);
      *v4 = 0;
    }
    dword_1800FF890 = a2;
    if ( !CreateTimerQueueTimer(
            v4,
            0,
            Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::TimeredCounterCallback,
            this,
            60000 * a2,
            0,
            8u) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::SetApiSamplingStopTimerMinutes",
        303,
        "Failed to create counter timer [%d]",
        LastError);
    }
    *((_BYTE *)this + 46) = 0;
    Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::UpdateApiSamplingState(this);
  }
}

```

## disassembly

```asm
0x1800c9df8  mov     [rsp+arg_0], rbx
0x1800c9dfd  mov     [rsp+arg_8], rsi
0x1800c9e02  push    rdi
0x1800c9e03  sub     rsp, 40h
0x1800c9e07  cmp     edx, cs:dword_1800FF890
0x1800c9e0d  mov     esi, edx
0x1800c9e0f  mov     rbx, rcx
0x1800c9e12  jz      loc_1800C9EA3
0x1800c9e18  lea     rdi, [rcx+10h]
0x1800c9e1c  mov     rdx, [rdi]; Timer
0x1800c9e1f  test    rdx, rdx
0x1800c9e22  jz      short loc_1800C9E36
0x1800c9e24  xor     r8d, r8d; CompletionEvent
0x1800c9e27  xor     ecx, ecx; TimerQueue
0x1800c9e29  call    cs:__imp_DeleteTimerQueueTimer
0x1800c9e2f  mov     qword ptr [rdi], 0
0x1800c9e36  imul    eax, esi, 0EA60h
0x1800c9e3c  lea     r8, ?TimeredCounterCallback@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@CAXPEAXE@Z; Callback
0x1800c9e43  mov     [rsp+48h+Flags], 8; Flags
0x1800c9e4b  mov     r9, rbx; Parameter
0x1800c9e4e  mov     [rsp+48h+Period], 0; Period
0x1800c9e56  xor     edx, edx; TimerQueue
0x1800c9e58  mov     rcx, rdi; phNewTimer
0x1800c9e5b  mov     cs:dword_1800FF890, esi
0x1800c9e61  mov     [rsp+48h+DueTime], eax; DueTime
0x1800c9e65  call    cs:__imp_CreateTimerQueueTimer
0x1800c9e6b  test    eax, eax
0x1800c9e6d  jnz     short loc_1800C9E97
0x1800c9e6f  call    cs:__imp_GetLastError
0x1800c9e75  lea     r9, aFailedToCreate; "Failed to create counter timer [%d]"
0x1800c9e7c  mov     r8d, 12Fh
0x1800c9e82  lea     rdx, aWindowsCompatI_76; "Windows::Compat::Inventory::ApiSampling"...
0x1800c9e89  mov     [rsp+48h+DueTime], eax
0x1800c9e8d  mov     ecx, 1
0x1800c9e92  call    AslLogCallPrintf
0x1800c9e97  mov     rcx, rbx; this
0x1800c9e9a  mov     byte ptr [rbx+2Eh], 0
0x1800c9e9e  call    ?UpdateApiSamplingState@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAXXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::UpdateApiSamplingState(void)
0x1800c9ea3  mov     rbx, [rsp+48h+arg_0]
0x1800c9ea8  mov     rsi, [rsp+48h+arg_8]
0x1800c9ead  add     rsp, 40h
0x1800c9eb1  pop     rdi
0x1800c9eb2  retn
```
