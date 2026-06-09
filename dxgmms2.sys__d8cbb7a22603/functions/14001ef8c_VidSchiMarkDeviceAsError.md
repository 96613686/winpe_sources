# VidSchiMarkDeviceAsError

- ea: `0x14001ef8c`
- end: `0x14001f297`
- name: `VidSchiMarkDeviceAsError`
- size: `779`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000c0b4`
- `0x140018014`
- `0x14001e960`
- `0x14003fdb8`
- `0x140054c50`

## callees

- `0x14001ef8c`
- `0x140031c60`
- `0x1400335e8`
- `0x14003793c`
- `0x14003a550`
- `0x1400403fc`
- `0x140056544`
- `0x140058f50`
- `0x140059030`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14001f004`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14001f004`
- `ntoskrnl!DbgPrintEx` at `0x14001f043`
- `ntoskrnl!DbgPrintEx` at `0x14001f043`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001f0e9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001f0e9`
- `ntoskrnl!KeSetEvent` at `0x14001f247`
- `ntoskrnl!KeSetEvent` at `0x14001f247`
- `dxgkrnl!DxgKrnlTelemetryGlobal_LogTelemetryEvent` at `0x14001f126`
- `dxgkrnl!DxgKrnlTelemetryGlobal_LogTelemetryEvent` at `0x14001f126`
- `dxgkrnl!DxgCoreInterface` at `0x14001f0fe`

## string_xrefs

- `0x14001f024`: `\nA GPU Scheduler device 0x%p from process %s has been put in error due to Reason %d.\nWe broke into the debugger to allow a chance for debugging this issue.\nTo disable debug breaks when device is put in error, run "?? dxgmms2!g_ErrorDeviceDebugMode=1" command,\nor "ed 0x%p 1"\n\n`

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
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rdi
  _QWORD *i; // rbx
  int v22; // [rsp+60h] [rbp-19h] BYREF
  int v23; // [rsp+64h] [rbp-15h] BYREF
  __int128 *v24; // [rsp+68h] [rbp-11h] BYREF
  __int64 v25; // [rsp+70h] [rbp-9h] BYREF
  __int64 v26; // [rsp+78h] [rbp-1h] BYREF
  __int64 v27; // [rsp+80h] [rbp+7h] BYREF
  __int64 v28; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v29; // [rsp+90h] [rbp+17h] BYREF
  __int128 v30; // [rsp+98h] [rbp+1Fh] BYREF

  v8 = a3;
  if ( (byte_140087201 & 1) != 0 )
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
      RtlCopyUnicodeString((PUNICODE_STRING)(v11 + 2880), *(PCUNICODE_STRING *)(v12 + 2056));
    }
    v13 = *(_QWORD *)(a2 + 72);
    if ( v13 )
      ((void (__fastcall *)(__int64, _QWORD))DxgCoreInterface[73])(v13, *(unsigned int *)(a2 + 208));
    if ( (*(_DWORD *)(a2 + 56) & 0x20) != 0 )
      VidSchiNotifyDeviceRemoved(a2);
    if ( DxgKrnlTelemetryGlobal_LogTelemetryEvent() )
    {
      v15 = *(_QWORD *)(a2 + 48);
      v30 = 0;
      v30 = *(_OWORD *)(*(_QWORD *)(v15 + 16) + 144LL);
      if ( (unsigned int)dword_140087048 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087048, 0x400000000010LL, v14) )
        {
          v17 = *(_QWORD *)(a2 + 48);
          v24 = &v30;
          v22 = a3;
          v25 = *(_QWORD *)(v17 + 2648);
          v26 = *(_QWORD *)(v17 + 2640);
          v18 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 16LL);
          v27 = *(_QWORD *)(v18 + 2056);
          v28 = *(_QWORD *)(v18 + 412);
          v23 = 2;
          v29 = 1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v18,
            (unsigned int)byte_14007DC89,
            v16,
            (unsigned int)&v29,
            (__int64)&v23,
            (__int64)&v28,
            (__int64)&v27,
            (__int64)&v26,
            (__int64)&v25,
            (__int64)&v22,
            (__int64)&v24);
        }
      }
    }
  }
  v19 = *(_QWORD *)(a2 + 40);
  *(_QWORD *)(v19 + 1576) = MEMORY[0xFFFFF78000000320];
  KeSetEvent((PRKEVENT)(v19 + 1544), 0, 0);
  v20 = (_QWORD *)(a2 + 96);
  for ( i = *(_QWORD **)(a2 + 96); i != v20; i = (_QWORD *)*i )
    VidSchiRundownHardwareContext(a1, (struct VIDSCH_HW_CONTEXT *)(i - 33));
}

```

## disassembly

```asm
0x14001ef8c  mov     [rsp-8+arg_18], rbx
0x14001ef91  push    rbp
0x14001ef92  push    rsi
0x14001ef93  push    rdi
0x14001ef94  push    r14
0x14001ef96  push    r15
0x14001ef98  lea     rbp, [rsp-37h]
0x14001ef9d  sub     rsp, 0B0h
0x14001efa4  mov     rax, cs:__security_cookie
0x14001efab  xor     rax, rsp
0x14001efae  mov     [rbp+57h+var_28], rax
0x14001efb2  test    cs:byte_140087201, 1
0x14001efb9  mov     rsi, r9
0x14001efbc  mov     edi, r8d
0x14001efbf  mov     rbx, rdx
0x14001efc2  mov     r15, rcx
0x14001efc5  mov     eax, r8d
0x14001efc8  jz      short loc_14001EFE7
0x14001efca  mov     r9, [rdx+8]
0x14001efce  mov     ecx, r8d
0x14001efd1  btr     ecx, 1Fh
0x14001efd5  shr     eax, 1Fh
0x14001efd8  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x14001efdc  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14001efe0  call    McTemplateK0ptq_EtwWriteTransfer
0x14001efe5  mov     eax, edi
0x14001efe7  cmp     edi, 0Eh
0x14001efea  ja      short loc_14001EFF6
0x14001efec  mov     ecx, 4280h
0x14001eff1  bt      ecx, edi
0x14001eff4  jb      short loc_14001F050
0x14001eff6  test    eax, eax
0x14001eff8  js      short loc_14001F050
0x14001effa  mov     eax, cs:?g_ErrorDeviceDebugMode@@3JC; long volatile g_ErrorDeviceDebugMode
0x14001f000  test    eax, eax
0x14001f002  jnz     short loc_14001F050
0x14001f004  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14001f00b  nop     dword ptr [rax+rax+00h]
0x14001f010  test    al, al
0x14001f012  jnz     short loc_14001F050
0x14001f014  mov     rax, [rbx+30h]
0x14001f018  lea     rcx, ?g_ErrorDeviceDebugMode@@3JC; long volatile g_ErrorDeviceDebugMode
0x14001f01f  mov     [rsp+0D0h+var_A0], rcx
0x14001f024  lea     r8, aAGpuSchedulerD; "\nA GPU Scheduler device 0x%p from proc"...
0x14001f02b  xor     edx, edx; Level
0x14001f02d  mov     dword ptr [rsp+0D0h+var_A8], edi
0x14001f031  mov     r9, rbx
0x14001f034  mov     rax, [rax+0A58h]
0x14001f03b  mov     [rsp+0D0h+var_B0], rax
0x14001f040  lea     ecx, [rdx+65h]; ComponentId
0x14001f043  call    cs:__imp_DbgPrintEx
0x14001f04a  nop     dword ptr [rax+rax+00h]
0x14001f04f  int     3; Trap to Debugger
0x14001f050  xor     eax, eax
0x14001f052  lock cmpxchg [rbx+0D0h], edi
0x14001f05a  mov     rdx, rbx
0x14001f05d  mov     rcx, r15
0x14001f060  mov     r14d, eax
0x14001f063  call    VidSchiSignalRegisteredSyncObjects
0x14001f068  test    rsi, rsi
0x14001f06b  jz      short loc_14001F082
0x14001f06d  movups  xmm0, xmmword ptr [rsi]
0x14001f070  movups  xmmword ptr [rbx+0D8h], xmm0
0x14001f077  movups  xmm1, xmmword ptr [rsi+10h]
0x14001f07b  movups  xmmword ptr [rbx+0E8h], xmm1
0x14001f082  test    r14d, r14d
0x14001f085  jnz     loc_14001F223
0x14001f08b  cmp     edi, 0Eh
0x14001f08e  jz      loc_14001F223
0x14001f094  cmp     edi, 7
0x14001f097  jz      short loc_14001F09E
0x14001f099  cmp     edi, 16h
0x14001f09c  jnz     short loc_14001F0F5
0x14001f09e  mov     rcx, [rbx+30h]
0x14001f0a2  mov     rax, [rbx+28h]
0x14001f0a6  mov     rdx, [rax+10h]
0x14001f0aa  mov     rax, [rcx+0B18h]
0x14001f0b1  mov     [rcx+0B28h], rax
0x14001f0b8  mov     rax, [rcx+0B20h]
0x14001f0bf  mov     [rcx+0B30h], rax
0x14001f0c6  mov     byte ptr [rcx+0B10h], 1
0x14001f0cd  mov     rax, [rdx+19Ch]
0x14001f0d4  mov     [rcx+0B38h], rax
0x14001f0db  add     rcx, 0B40h; DestinationString
0x14001f0e2  mov     rdx, [rdx+808h]; SourceString
0x14001f0e9  call    cs:__imp_RtlCopyUnicodeString
0x14001f0f0  nop     dword ptr [rax+rax+00h]
0x14001f0f5  mov     rcx, [rbx+48h]
0x14001f0f9  test    rcx, rcx
0x14001f0fc  jz      short loc_14001F117
0x14001f0fe  mov     rax, cs:DxgCoreInterface
0x14001f105  mov     edx, [rbx+0D0h]
0x14001f10b  mov     rax, [rax+248h]
0x14001f112  call    _guard_dispatch_icall
0x14001f117  mov     eax, [rbx+38h]
0x14001f11a  test    al, 20h
0x14001f11c  jz      short loc_14001F126
0x14001f11e  mov     rcx, rbx
0x14001f121  call    VidSchiNotifyDeviceRemoved
0x14001f126  call    cs:__imp_?DxgKrnlTelemetryGlobal_LogTelemetryEvent@@YA_NXZ; DxgKrnlTelemetryGlobal_LogTelemetryEvent(void)
0x14001f12d  nop     dword ptr [rax+rax+00h]
0x14001f132  test    al, al
0x14001f134  jz      loc_14001F223
0x14001f13a  mov     rax, [rbx+30h]
0x14001f13e  xorps   xmm0, xmm0
0x14001f141  movups  [rbp+57h+var_38], xmm0
0x14001f145  mov     rcx, [rax+10h]
0x14001f149  mov     eax, cs:dword_140087048
0x14001f14f  movups  xmm0, xmmword ptr [rcx+90h]
0x14001f156  movdqu  [rbp+57h+var_38], xmm0
0x14001f15b  cmp     eax, 5
0x14001f15e  jbe     loc_14001F223
0x14001f164  mov     rdx, 400000000010h
0x14001f16e  lea     rcx, dword_140087048
0x14001f175  call    _tlgKeywordOn
0x14001f17a  test    al, al
0x14001f17c  jz      loc_14001F223
0x14001f182  mov     rcx, [rbx+30h]
0x14001f186  lea     rax, [rbp+57h+var_38]
0x14001f18a  mov     [rbp+57h+var_68], rax
0x14001f18e  lea     r9, [rbp+57h+var_40]
0x14001f192  mov     [rbp+57h+var_70], edi
0x14001f195  lea     rdx, byte_14007DC89
0x14001f19c  mov     rax, [rcx+0A58h]
0x14001f1a3  mov     [rbp+57h+var_60], rax
0x14001f1a7  mov     rax, [rcx+0A50h]
0x14001f1ae  mov     [rbp+57h+var_58], rax
0x14001f1b2  mov     rax, [rbx+28h]
0x14001f1b6  mov     rcx, [rax+10h]
0x14001f1ba  mov     rax, [rcx+808h]
0x14001f1c1  mov     [rbp+57h+var_50], rax
0x14001f1c5  mov     rax, [rcx+19Ch]
0x14001f1cc  mov     [rbp+57h+var_48], rax
0x14001f1d0  lea     rax, [rbp+57h+var_68]
0x14001f1d4  mov     [rsp+0D0h+var_80], rax
0x14001f1d9  lea     rax, [rbp+57h+var_70]
0x14001f1dd  mov     [rsp+0D0h+var_88], rax
0x14001f1e2  lea     rax, [rbp+57h+var_60]
0x14001f1e6  mov     [rsp+0D0h+var_90], rax
0x14001f1eb  lea     rax, [rbp+57h+var_58]
0x14001f1ef  mov     [rsp+0D0h+var_98], rax
0x14001f1f4  lea     rax, [rbp+57h+var_50]
0x14001f1f8  mov     [rsp+0D0h+var_A0], rax
0x14001f1fd  lea     rax, [rbp+57h+var_48]
0x14001f201  mov     [rsp+0D0h+var_A8], rax
0x14001f206  lea     rax, [rbp+57h+var_6C]
0x14001f20a  mov     [rsp+0D0h+var_B0], rax
0x14001f20f  mov     [rbp+57h+var_6C], 2
0x14001f216  mov     [rbp+57h+var_40], 1
0x14001f21e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U1@U?$_tlgWrapSz@D@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x14001f223  mov     rcx, [rbx+28h]
0x14001f227  mov     rax, 0FFFFF78000000320h
0x14001f231  xor     r8d, r8d; Wait
0x14001f234  xor     edx, edx; Increment
0x14001f236  mov     rax, [rax]
0x14001f239  mov     [rcx+628h], rax
0x14001f240  add     rcx, 608h; Event
0x14001f247  call    cs:__imp_KeSetEvent
0x14001f24e  nop     dword ptr [rax+rax+00h]
0x14001f253  lea     rdi, [rbx+60h]
0x14001f257  mov     rbx, [rdi]
0x14001f25a  jmp     short loc_14001F26E
0x14001f25c  lea     rdx, [rbx-108h]; struct VIDSCH_HW_CONTEXT *
0x14001f263  mov     rcx, r15; struct HwQueueStagingList *
0x14001f266  call    ?VidSchiRundownHardwareContext@@YAXPEAVHwQueueStagingList@@PEAUVIDSCH_HW_CONTEXT@@@Z; VidSchiRundownHardwareContext(HwQueueStagingList *,VIDSCH_HW_CONTEXT *)
0x14001f26b  mov     rbx, [rbx]
0x14001f26e  cmp     rbx, rdi
0x14001f271  jnz     short loc_14001F25C
0x14001f273  mov     rcx, [rbp+57h+var_28]
0x14001f277  xor     rcx, rsp; StackCookie
0x14001f27a  call    __security_check_cookie
0x14001f27f  mov     rbx, [rsp+0D0h+arg_18]
0x14001f287  add     rsp, 0B0h
0x14001f28e  pop     r15
0x14001f290  pop     r14
0x14001f292  pop     rdi
0x14001f293  pop     rsi
0x14001f294  pop     rbp
0x14001f295  retn
```
