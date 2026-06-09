# RouterIdentityObjectUpdateAttributes(void *,uchar)

- ea: `0x1800182a0`
- end: `0x180018464`
- name: `?RouterIdentityObjectUpdateAttributes@@YAXPEAXE@Z`
- size: `452`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800033c8`
- `0x1800057f0`
- `0x180006fac`
- `0x18000dbf4`
- `0x180018470`
- `0x18002de10`

## callees

- `0x1800056c4`
- `0x18000def0`
- `0x180017988`
- `0x180017eb8`
- `0x1800182a0`
- `0x180045d7c`
- `0x180046e70`

## import_xrefs

- `ntdll!RtlCreateTimer` at `0x180018428`
- `ntdll!RtlCreateTimer` at `0x180018428`
- `ntdll!RtlDeleteTimer` at `0x1800182f2`
- `ntdll!RtlDeleteTimer` at `0x180018321`
- `ntdll!RtlDeleteTimer` at `0x1800182f2`
- `ntdll!RtlDeleteTimer` at `0x180018321`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800183a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800183a2`

## string_xrefs

- `0x1800183d9`: `Could not access DC, will set router attributes later`

## pseudocode

```c
void __fastcall RouterIdentityObjectUpdateAttributes(PVOID a1)
{
  int v1; // esi
  int v2; // edi
  unsigned __int16 *v3; // rcx
  ULONG DueTime; // ecx
  GUID ActivityId; // [rsp+48h] [rbp-20h] BYREF

  v1 = (int)a1;
  ActivityId = 0;
  v2 = SetRasServerActivityId(&ActivityId);
  if ( (_DWORD)qword_180070F24 != 4 )
  {
    if ( v1 )
    {
      RtlDeleteTimer(TimerQueue, phNewTimer, 0);
      phNewTimer = 0;
    }
    goto LABEL_18;
  }
  if ( !v1 )
  {
    if ( !qword_180070F60 )
      goto LABEL_18;
    goto LABEL_8;
  }
  RtlDeleteTimer(TimerQueue, phNewTimer, 0);
  phNewTimer = 0;
  if ( !(unsigned int)RouterIdentityObjectOpen(v3, gblDIMConfigInfo, &qword_180070F60) && qword_180070F60 )
  {
    if ( (_DWORD)qword_180070F24 != 4 )
      goto LABEL_18;
LABEL_8:
    EnterCriticalSection(&stru_180070F88);
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasDimTraceError,
        L"Setting router attributes in the identity object");
    RouterIdentityObjectSetAttributes(qword_180070F60);
    LeaveCriticalSection(&stru_180070F88);
    goto LABEL_18;
  }
  if ( (_DWORD)qword_180070F24 == 4 )
  {
    DueTime = ::DueTime;
    if ( ::DueTime < 0x5265C00 )
    {
      DueTime = 2 * ::DueTime;
      ::DueTime *= 2;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasDimTraceError,
        L"Could not access DC, will set router attributes later");
      DueTime = ::DueTime;
    }
    RtlCreateTimer(TimerQueue, &phNewTimer, RouterIdentityObjectUpdateAttributes, (PVOID)1, DueTime, 0, 0);
  }
LABEL_18:
  if ( v2 )
    ReSetActivityId(&ActivityId);
}

```

## disassembly

```asm
0x1800182a0  mov     [rsp+arg_0], rsi
0x1800182a5  push    rdi
0x1800182a6  sub     rsp, 60h
0x1800182aa  mov     rax, cs:__security_cookie
0x1800182b1  xor     rax, rsp
0x1800182b4  mov     [rsp+68h+var_10], rax
0x1800182b9  mov     rsi, rcx
0x1800182bc  xorps   xmm0, xmm0
0x1800182bf  lea     rcx, [rsp+68h+ActivityId]; ActivityId
0x1800182c4  movups  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x1800182c9  call    SetRasServerActivityId
0x1800182ce  cmp     dword ptr cs:qword_180070F24, 4
0x1800182d5  mov     edi, eax
0x1800182d7  jz      short loc_180018308
0x1800182d9  test    esi, esi
0x1800182db  jz      loc_18001843E
0x1800182e1  mov     rdx, cs:phNewTimer; Timer
0x1800182e8  xor     r8d, r8d; CompletionEvent
0x1800182eb  mov     rcx, cs:TimerQueue; TimerQueue
0x1800182f2  call    cs:__imp_RtlDeleteTimer
0x1800182f8  mov     cs:phNewTimer, 0
0x180018303  jmp     loc_18001843E
0x180018308  test    esi, esi
0x18001830a  jz      loc_180018430
0x180018310  mov     rdx, cs:phNewTimer; Timer
0x180018317  xor     r8d, r8d; CompletionEvent
0x18001831a  mov     rcx, cs:TimerQueue; TimerQueue
0x180018321  call    cs:__imp_RtlDeleteTimer
0x180018327  mov     edx, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; unsigned int
0x18001832d  lea     r8, qword_180070F60; void **
0x180018334  mov     cs:phNewTimer, 0
0x18001833f  call    ?RouterIdentityObjectOpen@@YAKPEAGKPEAPEAX@Z; RouterIdentityObjectOpen(ushort *,ulong,void * *)
0x180018344  test    eax, eax
0x180018346  jnz     short loc_1800183AD
0x180018348  cmp     cs:qword_180070F60, 0
0x180018350  jz      short loc_1800183AD
0x180018352  cmp     dword ptr cs:qword_180070F24, 4
0x180018359  jnz     loc_18001843E
0x18001835f  lea     rcx, stru_180070F88; lpCriticalSection
0x180018366  call    cs:__imp_EnterCriticalSection
0x18001836c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180018373  jz      short loc_18001838F
0x180018375  lea     r8, aSettingRouterA; "Setting router attributes in the identi"...
0x18001837c  lea     rdx, RasDimTraceError
0x180018383  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001838a  call    McTemplateU0z_EventWriteTransfer
0x18001838f  mov     rcx, cs:qword_180070F60; void *
0x180018396  call    ?RouterIdentityObjectSetAttributes@@YAKPEAX@Z; RouterIdentityObjectSetAttributes(void *)
0x18001839b  lea     rcx, stru_180070F88; lpCriticalSection
0x1800183a2  call    cs:__imp_LeaveCriticalSection
0x1800183a8  jmp     loc_18001843E
0x1800183ad  cmp     dword ptr cs:qword_180070F24, 4
0x1800183b4  jnz     loc_18001843E
0x1800183ba  mov     ecx, cs:DueTime
0x1800183c0  cmp     ecx, 5265C00h
0x1800183c6  jnb     short loc_1800183D0
0x1800183c8  add     ecx, ecx
0x1800183ca  mov     cs:DueTime, ecx
0x1800183d0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800183d7  jz      short loc_1800183F9
0x1800183d9  lea     r8, aCouldNotAccess; "Could not access DC, will set router at"...
0x1800183e0  lea     rdx, RasDimTraceError
0x1800183e7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800183ee  call    McTemplateU0z_EventWriteTransfer
0x1800183f3  mov     ecx, cs:DueTime
0x1800183f9  mov     [rsp+68h+Flags], 0; Flags
0x180018401  lea     r8, ?RouterIdentityObjectUpdateAttributes@@YAXPEAXE@Z; Callback
0x180018408  mov     [rsp+68h+Period], 0; Period
0x180018410  lea     rdx, phNewTimer; phNewTimer
0x180018417  mov     [rsp+68h+DueTime], ecx; DueTime
0x18001841b  mov     r9d, 1; Parameter
0x180018421  mov     rcx, cs:TimerQueue; TimerQueue
0x180018428  call    cs:__imp_RtlCreateTimer
0x18001842e  jmp     short loc_18001843E
0x180018430  cmp     cs:qword_180070F60, 0
0x180018438  jnz     loc_18001835F
0x18001843e  test    edi, edi
0x180018440  jz      short loc_18001844C
0x180018442  lea     rcx, [rsp+68h+ActivityId]; ActivityId
0x180018447  call    ReSetActivityId
0x18001844c  mov     rcx, [rsp+68h+var_10]
0x180018451  xor     rcx, rsp; StackCookie
0x180018454  call    __security_check_cookie
0x180018459  mov     rsi, [rsp+68h+arg_0]
0x18001845e  add     rsp, 60h
0x180018462  pop     rdi
0x180018463  retn
```
