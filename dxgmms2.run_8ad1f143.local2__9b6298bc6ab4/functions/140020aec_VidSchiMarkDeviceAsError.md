# VidSchiMarkDeviceAsError

- ea: `0x140020aec`
- end: `0x140020df7`
- name: `VidSchiMarkDeviceAsError`
- size: `779`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000c364`
- `0x14001d344`
- `0x1400204c0`
- `0x140041438`
- `0x140054378`

## callees

- `0x140020aec`
- `0x140033870`
- `0x140034cf8`
- `0x1400388dc`
- `0x14003b840`
- `0x1400416d8`
- `0x140055c74`
- `0x140058680`
- `0x140058760`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140020b64`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140020b64`
- `ntoskrnl!DbgPrintEx` at `0x140020ba3`
- `ntoskrnl!DbgPrintEx` at `0x140020ba3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140020c49`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140020c49`
- `ntoskrnl!KeSetEvent` at `0x140020da7`
- `ntoskrnl!KeSetEvent` at `0x140020da7`
- `dxgkrnl!DxgKrnlTelemetryGlobal_LogTelemetryEvent` at `0x140020c86`
- `dxgkrnl!DxgKrnlTelemetryGlobal_LogTelemetryEvent` at `0x140020c86`
- `dxgkrnl!DxgCoreInterface` at `0x140020c5e`

## string_xrefs

- `0x140020b84`: `\nA GPU Scheduler device 0x%p from process %s has been put in error due to Reason %d.\nWe broke into the debugger to allow a chance for debugging this issue.\nTo disable debug breaks when device is put in error, run "?? dxgmms2!g_ErrorDeviceDebugMode=1" command,\nor "ed 0x%p 1"\n\n`

## pseudocode

```c
void __fastcall VidSchiMarkDeviceAsError(struct HwQueueStagingList *a1, __int64 a2, int a3, _OWORD *a4)
{
  int v8; // eax
  int v9; // ecx
  signed __int32 v10; // r14d
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // r8d
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rdi
  _QWORD *i; // rbx
  int v21; // [rsp+60h] [rbp-19h] BYREF
  int v22; // [rsp+64h] [rbp-15h] BYREF
  __int128 *v23; // [rsp+68h] [rbp-11h] BYREF
  __int64 v24; // [rsp+70h] [rbp-9h] BYREF
  __int64 v25; // [rsp+78h] [rbp-1h] BYREF
  __int64 v26; // [rsp+80h] [rbp+7h] BYREF
  __int64 v27; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v28; // [rsp+90h] [rbp+17h] BYREF
  __int128 v29; // [rsp+98h] [rbp+1Fh] BYREF

  v8 = a3;
  if ( (byte_140086201 & 1) != 0 )
  {
    McTemplateK0ptq_EtwWriteTransfer(a3 & 0x7FFFFFFF, a2, a3, *(_QWORD *)(a2 + 8), a3 < 0, a3);
    v8 = a3;
  }
  if ( (unsigned int)a3 > 0xE || (v9 = 17024, !_bittest(&v9, a3)) )
  {
    if ( v8 >= 0 && !g_ErrorDeviceDebugMode && !KdRefreshDebuggerNotPresent() )
    {
      DbgPrintEx(
        0x65u,
        0,
        "\n"
        "A GPU Scheduler device 0x%p from process %s has been put in error due to Reason %d.\n"
        "We broke into the debugger to allow a chance for debugging this issue.\n"
        "To disable debug breaks when device is put in error, run \"?? dxgmms2!g_ErrorDeviceDebugMode=1\" command,\n"
        "or \"ed 0x%p 1\"\n"
        "\n",
        (const void *)a2,
        *(const char **)(*(_QWORD *)(a2 + 48) + 2648LL),
        a3,
        (const void *)&g_ErrorDeviceDebugMode);
      __debugbreak();
    }
  }
  v10 = _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 208), a3, 0);
  VidSchiSignalRegisteredSyncObjects(a1);
  if ( a4 )
  {
    *(_OWORD *)(a2 + 216) = *a4;
    *(_OWORD *)(a2 + 232) = a4[1];
  }
  if ( !v10 && a3 != 14 )
  {
    if ( a3 == 7 || a3 == 22 )
    {
      v11 = *(_QWORD *)(a2 + 48);
      v12 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 16LL);
      *(_QWORD *)(v11 + 2856) = *(_QWORD *)(v11 + 2840);
      *(_QWORD *)(v11 + 2864) = *(_QWORD *)(v11 + 2848);
      *(_BYTE *)(v11 + 2832) = 1;
      *(_QWORD *)(v11 + 2872) = *(_QWORD *)(v12 + 412);
      RtlCopyUnicodeString((PUNICODE_STRING)(v11 + 2880), *(PCUNICODE_STRING *)(v12 + 2040));
    }
    v13 = *(_QWORD *)(a2 + 72);
    if ( v13 )
      ((void (__fastcall *)(__int64, _QWORD))DxgCoreInterface[73])(v13, *(unsigned int *)(a2 + 208));
    if ( (*(_DWORD *)(a2 + 56) & 0x20) != 0 )
      VidSchiNotifyDeviceRemoved(a2);
    if ( DxgKrnlTelemetryGlobal_LogTelemetryEvent() )
    {
      v14 = *(_QWORD *)(a2 + 48);
      v29 = 0;
      v29 = *(_OWORD *)(*(_QWORD *)(v14 + 16) + 144LL);
      if ( (unsigned int)dword_140086048 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140086048, 0x400000000010LL) )
        {
          v16 = *(_QWORD *)(a2 + 48);
          v23 = &v29;
          v21 = a3;
          v24 = *(_QWORD *)(v16 + 2648);
          v25 = *(_QWORD *)(v16 + 2640);
          v17 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 16LL);
          v26 = *(_QWORD *)(v17 + 2040);
          v27 = *(_QWORD *)(v17 + 412);
          v22 = 2;
          v28 = 1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v17,
            (unsigned int)byte_14007C409,
            v15,
            (unsigned int)&v28,
            (__int64)&v22,
            (__int64)&v27,
            (__int64)&v26,
            (__int64)&v25,
            (__int64)&v24,
            (__int64)&v21,
            (__int64)&v23);
        }
      }
    }
  }
  v18 = *(_QWORD *)(a2 + 40);
  *(_QWORD *)(v18 + 1576) = MEMORY[0xFFFFF78000000320];
  KeSetEvent((PRKEVENT)(v18 + 1544), 0, 0);
  v19 = (_QWORD *)(a2 + 96);
  for ( i = *(_QWORD **)(a2 + 96); i != v19; i = (_QWORD *)*i )
    VidSchiRundownHardwareContext(a1, (struct VIDSCH_HW_CONTEXT *)(i - 33));
}

```

## disassembly

```asm
0x140020aec  mov     [rsp-8+arg_18], rbx
0x140020af1  push    rbp
0x140020af2  push    rsi
0x140020af3  push    rdi
0x140020af4  push    r14
0x140020af6  push    r15
0x140020af8  lea     rbp, [rsp-37h]
0x140020afd  sub     rsp, 0B0h
0x140020b04  mov     rax, cs:__security_cookie
0x140020b0b  xor     rax, rsp
0x140020b0e  mov     [rbp+57h+var_28], rax
0x140020b12  test    cs:byte_140086201, 1
0x140020b19  mov     rsi, r9
0x140020b1c  mov     edi, r8d
0x140020b1f  mov     rbx, rdx
0x140020b22  mov     r15, rcx
0x140020b25  mov     eax, r8d
0x140020b28  jz      short loc_140020B47
0x140020b2a  mov     r9, [rdx+8]
0x140020b2e  mov     ecx, r8d
0x140020b31  btr     ecx, 1Fh
0x140020b35  shr     eax, 1Fh
0x140020b38  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x140020b3c  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140020b40  call    McTemplateK0ptq_EtwWriteTransfer
0x140020b45  mov     eax, edi
0x140020b47  cmp     edi, 0Eh
0x140020b4a  ja      short loc_140020B56
0x140020b4c  mov     ecx, 4280h
0x140020b51  bt      ecx, edi
0x140020b54  jb      short loc_140020BB0
0x140020b56  test    eax, eax
0x140020b58  js      short loc_140020BB0
0x140020b5a  mov     eax, cs:?g_ErrorDeviceDebugMode@@3JC; long volatile g_ErrorDeviceDebugMode
0x140020b60  test    eax, eax
0x140020b62  jnz     short loc_140020BB0
0x140020b64  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140020b6b  nop     dword ptr [rax+rax+00h]
0x140020b70  test    al, al
0x140020b72  jnz     short loc_140020BB0
0x140020b74  mov     rax, [rbx+30h]
0x140020b78  lea     rcx, ?g_ErrorDeviceDebugMode@@3JC; long volatile g_ErrorDeviceDebugMode
0x140020b7f  mov     [rsp+0D0h+var_A0], rcx
0x140020b84  lea     r8, aAGpuSchedulerD; "\nA GPU Scheduler device 0x%p from proc"...
0x140020b8b  xor     edx, edx; Level
0x140020b8d  mov     dword ptr [rsp+0D0h+var_A8], edi
0x140020b91  mov     r9, rbx
0x140020b94  mov     rax, [rax+0A58h]
0x140020b9b  mov     [rsp+0D0h+var_B0], rax
0x140020ba0  lea     ecx, [rdx+65h]; ComponentId
0x140020ba3  call    cs:__imp_DbgPrintEx
0x140020baa  nop     dword ptr [rax+rax+00h]
0x140020baf  int     3; Trap to Debugger
0x140020bb0  xor     eax, eax
0x140020bb2  lock cmpxchg [rbx+0D0h], edi
0x140020bba  mov     rdx, rbx
0x140020bbd  mov     rcx, r15
0x140020bc0  mov     r14d, eax
0x140020bc3  call    VidSchiSignalRegisteredSyncObjects
0x140020bc8  test    rsi, rsi
0x140020bcb  jz      short loc_140020BE2
0x140020bcd  movups  xmm0, xmmword ptr [rsi]
0x140020bd0  movups  xmmword ptr [rbx+0D8h], xmm0
0x140020bd7  movups  xmm1, xmmword ptr [rsi+10h]
0x140020bdb  movups  xmmword ptr [rbx+0E8h], xmm1
0x140020be2  test    r14d, r14d
0x140020be5  jnz     loc_140020D83
0x140020beb  cmp     edi, 0Eh
0x140020bee  jz      loc_140020D83
0x140020bf4  cmp     edi, 7
0x140020bf7  jz      short loc_140020BFE
0x140020bf9  cmp     edi, 16h
0x140020bfc  jnz     short loc_140020C55
0x140020bfe  mov     rcx, [rbx+30h]
0x140020c02  mov     rax, [rbx+28h]
0x140020c06  mov     rdx, [rax+10h]
0x140020c0a  mov     rax, [rcx+0B18h]
0x140020c11  mov     [rcx+0B28h], rax
0x140020c18  mov     rax, [rcx+0B20h]
0x140020c1f  mov     [rcx+0B30h], rax
0x140020c26  mov     byte ptr [rcx+0B10h], 1
0x140020c2d  mov     rax, [rdx+19Ch]
0x140020c34  mov     [rcx+0B38h], rax
0x140020c3b  add     rcx, 0B40h; DestinationString
0x140020c42  mov     rdx, [rdx+7F8h]; SourceString
0x140020c49  call    cs:__imp_RtlCopyUnicodeString
0x140020c50  nop     dword ptr [rax+rax+00h]
0x140020c55  mov     rcx, [rbx+48h]
0x140020c59  test    rcx, rcx
0x140020c5c  jz      short loc_140020C77
0x140020c5e  mov     rax, cs:DxgCoreInterface
0x140020c65  mov     edx, [rbx+0D0h]
0x140020c6b  mov     rax, [rax+248h]
0x140020c72  call    _guard_dispatch_icall
0x140020c77  mov     eax, [rbx+38h]
0x140020c7a  test    al, 20h
0x140020c7c  jz      short loc_140020C86
0x140020c7e  mov     rcx, rbx
0x140020c81  call    VidSchiNotifyDeviceRemoved
0x140020c86  call    cs:__imp_?DxgKrnlTelemetryGlobal_LogTelemetryEvent@@YA_NXZ; DxgKrnlTelemetryGlobal_LogTelemetryEvent(void)
0x140020c8d  nop     dword ptr [rax+rax+00h]
0x140020c92  test    al, al
0x140020c94  jz      loc_140020D83
0x140020c9a  mov     rax, [rbx+30h]
0x140020c9e  xorps   xmm0, xmm0
0x140020ca1  movups  [rbp+57h+var_38], xmm0
0x140020ca5  mov     rcx, [rax+10h]
0x140020ca9  mov     eax, cs:dword_140086048
0x140020caf  movups  xmm0, xmmword ptr [rcx+90h]
0x140020cb6  movdqu  [rbp+57h+var_38], xmm0
0x140020cbb  cmp     eax, 5
0x140020cbe  jbe     loc_140020D83
0x140020cc4  mov     rdx, 400000000010h
0x140020cce  lea     rcx, dword_140086048
0x140020cd5  call    _tlgKeywordOn
0x140020cda  test    al, al
0x140020cdc  jz      loc_140020D83
0x140020ce2  mov     rcx, [rbx+30h]
0x140020ce6  lea     rax, [rbp+57h+var_38]
0x140020cea  mov     [rbp+57h+var_68], rax
0x140020cee  lea     r9, [rbp+57h+var_40]
0x140020cf2  mov     [rbp+57h+var_70], edi
0x140020cf5  lea     rdx, byte_14007C409
0x140020cfc  mov     rax, [rcx+0A58h]
0x140020d03  mov     [rbp+57h+var_60], rax
0x140020d07  mov     rax, [rcx+0A50h]
0x140020d0e  mov     [rbp+57h+var_58], rax
0x140020d12  mov     rax, [rbx+28h]
0x140020d16  mov     rcx, [rax+10h]
0x140020d1a  mov     rax, [rcx+7F8h]
0x140020d21  mov     [rbp+57h+var_50], rax
0x140020d25  mov     rax, [rcx+19Ch]
0x140020d2c  mov     [rbp+57h+var_48], rax
0x140020d30  lea     rax, [rbp+57h+var_68]
0x140020d34  mov     [rsp+0D0h+var_80], rax
0x140020d39  lea     rax, [rbp+57h+var_70]
0x140020d3d  mov     [rsp+0D0h+var_88], rax
0x140020d42  lea     rax, [rbp+57h+var_60]
0x140020d46  mov     [rsp+0D0h+var_90], rax
0x140020d4b  lea     rax, [rbp+57h+var_58]
0x140020d4f  mov     [rsp+0D0h+var_98], rax
0x140020d54  lea     rax, [rbp+57h+var_50]
0x140020d58  mov     [rsp+0D0h+var_A0], rax
0x140020d5d  lea     rax, [rbp+57h+var_48]
0x140020d61  mov     [rsp+0D0h+var_A8], rax
0x140020d66  lea     rax, [rbp+57h+var_6C]
0x140020d6a  mov     [rsp+0D0h+var_B0], rax
0x140020d6f  mov     [rbp+57h+var_6C], 2
0x140020d76  mov     [rbp+57h+var_40], 1
0x140020d7e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U1@U?$_tlgWrapSz@D@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x140020d83  mov     rcx, [rbx+28h]
0x140020d87  mov     rax, 0FFFFF78000000320h
0x140020d91  xor     r8d, r8d; Wait
0x140020d94  xor     edx, edx; Increment
0x140020d96  mov     rax, [rax]
0x140020d99  mov     [rcx+628h], rax
0x140020da0  add     rcx, 608h; Event
0x140020da7  call    cs:__imp_KeSetEvent
0x140020dae  nop     dword ptr [rax+rax+00h]
0x140020db3  lea     rdi, [rbx+60h]
0x140020db7  mov     rbx, [rdi]
0x140020dba  jmp     short loc_140020DCE
0x140020dbc  lea     rdx, [rbx-108h]; struct VIDSCH_HW_CONTEXT *
0x140020dc3  mov     rcx, r15; struct HwQueueStagingList *
0x140020dc6  call    ?VidSchiRundownHardwareContext@@YAXPEAVHwQueueStagingList@@PEAUVIDSCH_HW_CONTEXT@@@Z; VidSchiRundownHardwareContext(HwQueueStagingList *,VIDSCH_HW_CONTEXT *)
0x140020dcb  mov     rbx, [rbx]
0x140020dce  cmp     rbx, rdi
0x140020dd1  jnz     short loc_140020DBC
0x140020dd3  mov     rcx, [rbp+57h+var_28]
0x140020dd7  xor     rcx, rsp; StackCookie
0x140020dda  call    __security_check_cookie
0x140020ddf  mov     rbx, [rsp+0D0h+arg_18]
0x140020de7  add     rsp, 0B0h
0x140020dee  pop     r15
0x140020df0  pop     r14
0x140020df2  pop     rdi
0x140020df3  pop     rsi
0x140020df4  pop     rbp
0x140020df5  retn
```
