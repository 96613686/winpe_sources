# BthRegisterIoCaps(BTHSERV_AUTHENTICATION_CLIENT *)

- ea: `0x180018304`
- end: `0x1800185ed`
- name: `?BthRegisterIoCaps@@YAHPEAUBTHSERV_AUTHENTICATION_CLIENT@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(struct BTHSERV_AUTHENTICATION_CLIENT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b498`
- `0x1800185f4`

## callees

- `0x1800017a0`
- `0x180010128`
- `0x1800120b8`
- `0x180012190`
- `0x180018304`
- `0x180019fe4`
- `0x1800348d4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001834b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001834b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001844c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001844c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800184ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800184ae`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001843c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001843c`

## pseudocode

```c
__int64 __fastcall BthRegisterIoCaps(struct _OVERLAPPED *a1, __int64 a2, __int64 a3)
{
  HANDLE EventW; // rax
  int v5; // edx
  int v6; // r8d
  char v7; // si
  __int64 v8; // rdx
  __int64 v9; // r8
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v12; // rbx
  int lpOutBuffer; // [rsp+28h] [rbp-39h]
  int nOutBufferSize; // [rsp+30h] [rbp-31h]
  HANDLE *v15; // [rsp+78h] [rbp+17h] BYREF
  volatile signed __int32 *v16; // [rsp+80h] [rbp+1Fh]
  _DWORD InBuffer[2]; // [rsp+88h] [rbp+27h] BYREF
  PVOID Pointer; // [rsp+90h] [rbp+2Fh]
  int hEvent_high; // [rsp+98h] [rbp+37h]

  if ( a1[3].hEvent )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
  EventW = CreateEventW(0, 0, 0, 0);
  a1[3].hEvent = EventW;
  if ( !EventW )
    return 0;
  v7 = 1;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (LOBYTE(v5) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(v5) = 0;
  }
  if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDDiD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  InBuffer[0] = a1[2].Offset;
  InBuffer[1] = a1[2].OffsetHigh;
  Pointer = a1[1].Pointer;
  hEvent_high = HIDWORD(a1[2].hEvent);
  BthServGlobals::GetSafeRadioHandle(&Globals, &v15);
  if ( !v15 || (char *)*v15 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      v7 = 0;
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v7;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    goto LABEL_31;
  }
  if ( DeviceIoControl(*v15, 0x4111CCu, InBuffer, 0x14u, 0, 0, 0, a1 + 3) || GetLastError() != 997 )
  {
    CloseHandle(a1[3].hEvent);
    a1[3].hEvent = 0;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v7 = 0;
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v7;
      WPP_RECORDER_AND_TRACE_SF_sDDi(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        v9,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        lpOutBuffer,
        nOutBufferSize,
        12,
        (__int64)WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids);
    }
LABEL_31:
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        v12 = v16;
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v16)(v16, v8, v9);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    return 0;
  }
  if ( v16 && _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
  {
    v10 = v16;
    (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
    if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
  }
  return 1;
}

```

## disassembly

```asm
0x180018304  mov     rax, rsp
0x180018307  mov     [rax+10h], rbx
0x18001830b  mov     [rax+18h], rsi
0x18001830f  mov     [rax+20h], rdi
0x180018313  push    rbp
0x180018314  push    r14
0x180018316  push    r15
0x180018318  lea     rbp, [rax-5Fh]
0x18001831c  sub     rsp, 0A0h
0x180018323  mov     rax, cs:__security_cookie
0x18001832a  xor     rax, rsp
0x18001832d  mov     [rbp+57h+var_18], rax
0x180018331  xor     edi, edi
0x180018333  mov     rbx, rcx
0x180018336  cmp     [rcx+78h], rdi
0x18001833a  jz      short loc_180018341
0x18001833c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018341  xor     r9d, r9d; lpName
0x180018344  xor     r8d, r8d; bInitialState
0x180018347  xor     edx, edx; bManualReset
0x180018349  xor     ecx, ecx; lpEventAttributes
0x18001834b  call    cs:__imp_CreateEventW
0x180018352  nop     dword ptr [rax+rax+00h]
0x180018357  mov     [rbx+78h], rax
0x18001835b  test    rax, rax
0x18001835e  jz      loc_1800185C1
0x180018364  mov     rcx, cs:WPP_GLOBAL_Control
0x18001836b  lea     r14, WPP_GLOBAL_Control
0x180018372  mov     esi, 1
0x180018377  cmp     rcx, r14
0x18001837a  jz      short loc_180018385
0x18001837c  cmp     byte ptr [rcx+19h], 5
0x180018380  mov     dl, sil
0x180018383  jnb     short loc_180018388
0x180018385  mov     dl, dil
0x180018388  lea     r15, WPP_RECORDER_INITIALIZED
0x18001838f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180018396  setnz   r8b
0x18001839a  test    dl, dl
0x18001839c  jnz     short loc_1800183A3
0x18001839e  test    r8b, r8b
0x1800183a1  jz      short loc_1800183CE
0x1800183a3  mov     eax, [rbx+5Ch]
0x1800183a6  mov     r9, [rcx+28h]
0x1800183aa  mov     rcx, [rcx+10h]
0x1800183ae  mov     [rsp+0B0h+var_50], eax
0x1800183b2  mov     rax, [rbx+30h]
0x1800183b6  mov     qword ptr [rsp+0B0h+var_58], rax
0x1800183bb  mov     eax, [rbx+50h]
0x1800183be  mov     dword ptr [rsp+0B0h+var_60], eax
0x1800183c2  mov     eax, [rbx+54h]
0x1800183c5  mov     [rsp+0B0h+var_68], eax
0x1800183c9  call    WPP_RECORDER_AND_TRACE_SF_sDDiD
0x1800183ce  mov     eax, [rbx+50h]
0x1800183d1  lea     rdx, [rbp+57h+var_40]
0x1800183d5  mov     [rbp+57h+InBuffer], eax
0x1800183d8  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x1800183df  mov     eax, [rbx+54h]
0x1800183e2  mov     [rbp+57h+var_2C], eax
0x1800183e5  mov     rax, [rbx+30h]
0x1800183e9  mov     [rbp+57h+var_28], rax
0x1800183ed  mov     eax, [rbx+5Ch]
0x1800183f0  mov     [rbp+57h+var_20], eax
0x1800183f3  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x1800183f8  mov     rax, [rbp+57h+var_40]
0x1800183fc  test    rax, rax
0x1800183ff  jz      loc_180018528
0x180018405  mov     rcx, [rax]; hDevice
0x180018408  lea     rax, [rcx-1]
0x18001840c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018410  ja      loc_180018528
0x180018416  lea     rax, [rbx+60h]
0x18001841a  mov     r9d, 14h; nInBufferSize
0x180018420  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x180018425  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180018429  mov     [rsp+0B0h+lpBytesReturned], rdi; lpBytesReturned
0x18001842e  mov     edx, 4111CCh; dwIoControlCode
0x180018433  mov     [rsp+0B0h+nOutBufferSize], edi; nOutBufferSize
0x180018437  mov     [rsp+0B0h+lpOutBuffer], rdi; lpOutBuffer
0x18001843c  call    cs:__imp_DeviceIoControl
0x180018443  nop     dword ptr [rax+rax+00h]
0x180018448  test    eax, eax
0x18001844a  jnz     short loc_1800184AA
0x18001844c  call    cs:__imp_GetLastError
0x180018453  nop     dword ptr [rax+rax+00h]
0x180018458  cmp     eax, 3E5h
0x18001845d  jnz     short loc_1800184AA
0x18001845f  mov     rcx, [rbp+57h+var_38]
0x180018463  test    rcx, rcx
0x180018466  jz      short loc_1800184A3
0x180018468  or      edi, 0FFFFFFFFh
0x18001846b  mov     eax, edi
0x18001846d  lock xadd [rcx+8], eax
0x180018472  add     eax, edi
0x180018474  jnz     short loc_1800184A3
0x180018476  mov     rbx, [rbp+57h+var_38]
0x18001847a  mov     rcx, rbx
0x18001847d  mov     rax, [rbx]
0x180018480  mov     rax, [rax]
0x180018483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018488  mov     ecx, edi
0x18001848a  lock xadd [rbx+0Ch], ecx
0x18001848f  add     ecx, edi
0x180018491  jnz     short loc_1800184A3
0x180018493  mov     rcx, [rbp+57h+var_38]
0x180018497  mov     rdx, [rcx]
0x18001849a  mov     rax, [rdx+8]
0x18001849e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184a3  mov     eax, esi
0x1800184a5  jmp     loc_1800185C3
0x1800184aa  mov     rcx, [rbx+78h]; hObject
0x1800184ae  call    cs:__imp_CloseHandle
0x1800184b5  nop     dword ptr [rax+rax+00h]
0x1800184ba  mov     [rbx+78h], rdi
0x1800184be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184c5  cmp     rcx, r14
0x1800184c8  jz      short loc_1800184D0
0x1800184ca  cmp     byte ptr [rcx+19h], 2
0x1800184ce  jnb     short loc_1800184D3
0x1800184d0  mov     sil, dil
0x1800184d3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800184da  setnz   r8b
0x1800184de  test    sil, sil
0x1800184e1  jnz     short loc_1800184EC
0x1800184e3  test    r8b, r8b
0x1800184e6  jz      loc_18001857D
0x1800184ec  mov     rax, [rbx+30h]
0x1800184f0  mov     dl, sil
0x1800184f3  mov     r9, [rcx+28h]
0x1800184f7  mov     rcx, [rcx+10h]
0x1800184fb  mov     qword ptr [rsp+0B0h+var_58], rax
0x180018500  mov     eax, [rbx+50h]
0x180018503  mov     dword ptr [rsp+0B0h+var_60], eax
0x180018507  mov     eax, [rbx+54h]
0x18001850a  mov     [rsp+0B0h+var_68], eax
0x18001850e  lea     rax, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180018515  mov     [rsp+0B0h+lpOverlapped], rax
0x18001851a  mov     word ptr [rsp+0B0h+lpBytesReturned], 0Ch
0x180018521  call    WPP_RECORDER_AND_TRACE_SF_sDDi
0x180018526  jmp     short loc_18001857D
0x180018528  mov     rcx, cs:WPP_GLOBAL_Control
0x18001852f  cmp     rcx, r14
0x180018532  jz      short loc_18001853A
0x180018534  cmp     byte ptr [rcx+19h], 3
0x180018538  jnb     short loc_18001853D
0x18001853a  mov     sil, dil
0x18001853d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180018544  setnz   r8b
0x180018548  test    sil, sil
0x18001854b  jnz     short loc_180018552
0x18001854d  test    r8b, r8b
0x180018550  jz      short loc_18001857D
0x180018552  mov     r9, [rcx+28h]
0x180018556  lea     rax, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x18001855d  mov     rcx, [rcx+10h]
0x180018561  mov     dl, sil
0x180018564  mov     [rsp+0B0h+var_68], 6
0x18001856c  mov     [rsp+0B0h+lpOverlapped], rax
0x180018571  mov     word ptr [rsp+0B0h+lpBytesReturned], 0Dh
0x180018578  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001857d  mov     rcx, [rbp+57h+var_38]
0x180018581  test    rcx, rcx
0x180018584  jz      short loc_1800185C1
0x180018586  or      edi, 0FFFFFFFFh
0x180018589  mov     eax, edi
0x18001858b  lock xadd [rcx+8], eax
0x180018590  add     eax, edi
0x180018592  jnz     short loc_1800185C1
0x180018594  mov     rbx, [rbp+57h+var_38]
0x180018598  mov     rcx, rbx
0x18001859b  mov     rax, [rbx]
0x18001859e  mov     rax, [rax]
0x1800185a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185a6  mov     eax, edi
0x1800185a8  lock xadd [rbx+0Ch], eax
0x1800185ad  add     eax, edi
0x1800185af  jnz     short loc_1800185C1
0x1800185b1  mov     rcx, [rbp+57h+var_38]
0x1800185b5  mov     rax, [rcx]
0x1800185b8  mov     rax, [rax+8]
0x1800185bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185c1  xor     eax, eax
0x1800185c3  mov     rcx, [rbp+57h+var_18]
0x1800185c7  xor     rcx, rsp; StackCookie
0x1800185ca  call    __security_check_cookie
0x1800185cf  lea     r11, [rsp+0B0h+var_10]
0x1800185d7  mov     rbx, [r11+28h]
0x1800185db  mov     rsi, [r11+30h]
0x1800185df  mov     rdi, [r11+38h]
0x1800185e3  mov     rsp, r11
0x1800185e6  pop     r15
0x1800185e8  pop     r14
0x1800185ea  pop     rbp
0x1800185eb  retn
```
