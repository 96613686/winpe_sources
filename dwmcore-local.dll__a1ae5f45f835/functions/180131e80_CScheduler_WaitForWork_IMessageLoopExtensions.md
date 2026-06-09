# CScheduler::WaitForWork(IMessageLoopExtensions *)

- ea: `0x180131e80`
- end: `0x1801323da`
- name: `?WaitForWork@CScheduler@@QEAAXPEAUIMessageLoopExtensions@@@Z`
- size: `1370`
- prototype: `void __fastcall(CScheduler *__hidden this, struct IMessageLoopExtensions *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801308e0`

## callees

- `0x180050270`
- `0x180131dc0`
- `0x180131e80`
- `0x1801323e0`
- `0x18015ab80`
- `0x18015adb4`
- `0x180188558`
- `0x180204120`
- `0x18020e32c`
- `0x1802284b0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1801320bc`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1801320bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180132059`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180132059`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180131eec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180131eec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801323a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801323a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18013215b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18013215b`
- `ext-ms-win-ntuser-private-l1-1-1!DwmGetRemoteSessionOcclusionEvent` at `0x1801323ac`
- `ext-ms-win-ntuser-private-l1-1-1!DwmGetRemoteSessionOcclusionEvent` at `0x1801323ac`

## pseudocode

```c
void __fastcall CScheduler::WaitForWork(CScheduler *this, struct IMessageLoopExtensions *a2)
{
  __int64 v3; // rcx
  char *EventW; // rdi
  unsigned int v6; // r14d
  __int64 v7; // r8
  int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rbx
  DWORD v13; // eax
  bool v14; // r12
  unsigned __int8 v15; // r15
  unsigned __int8 v16; // r14
  unsigned __int8 v17; // di
  unsigned __int8 v18; // bl
  CDisplayManager *v19; // rcx
  __int64 v20; // r8
  int v21; // eax
  signed int LastError; // eax
  __int64 RemoteSessionOcclusionEvent; // rax
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  BOOL v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  ULONGLONG *v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  int v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+84h] [rbp-7Ch]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+90h] [rbp-70h] BYREF
  int *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  BOOL *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  int *v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  int *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  void *retaddr; // [rsp+138h] [rbp+38h]

  *((_QWORD *)this + 6) = qword_1803BB0C8;
  v3 = qword_1803BB0D0;
  if ( (unsigned __int64)(qword_1803BB0D0 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( qword_1803BB0B8 )
    {
      if ( byte_1803BB0E2 )
      {
        RemoteSessionOcclusionEvent = DwmGetRemoteSessionOcclusionEvent();
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &qword_1803BB0D0,
          RemoteSessionOcclusionEvent);
      }
      else
      {
        EventW = (char *)CreateEventW(0, 0, 0, 0);
        v30 = (__int64)EventW;
        if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL
          && (*(int (__fastcall **)(CDisplayManager *, char *, char *))(*(_QWORD *)qword_1803BB0B8 + 176LL))(
               qword_1803BB0B8,
               EventW,
               (char *)&qword_1803BB0D8 + 4) >= 0 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
            &qword_1803BB0D0,
            &v30);
          EventW = (char *)v30;
        }
        if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(EventW);
      }
      v3 = qword_1803BB0D0;
    }
    else
    {
      v3 = 0;
    }
  }
  *((_QWORD *)this + 7) = v3;
  v6 = (v3 != 0) + 4;
  CRenderThreadWaitTick::CRenderThreadWaitTick((CRenderThreadWaitTick *)&v29, (volatile unsigned __int64 *)a2);
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      (const EVENT_DESCRIPTOR *)EVTDESC_SCHEDULE_WFW_Start,
      v7,
      1u,
      (PEVENT_DATA_DESCRIPTOR)&v30);
  if ( (Microsoft_Windows_Dwm_CompositorEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)Microsoft_Windows_Dwm_Compositor_Context,
      (const EVENT_DESCRIPTOR *)WaitForWork_Start,
      v7,
      1u,
      (PEVENT_DATA_DESCRIPTOR)&v30);
  v24 = 0;
  while ( 1 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IMessageLoopExtensions *, _QWORD, char *, __int64, _DWORD, int *))(*(_QWORD *)a2 + 32LL))(
           a2,
           v6,
           (char *)this + 24,
           0xFFFFFFFFLL,
           0,
           &v24);
    if ( v8 >= 0 )
    {
      v9 = v24;
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x82u, 0);
      v9 = -1;
      v24 = -1;
    }
    if ( v9 < v6 )
      break;
    v10 = (*(__int64 (__fastcall **)(struct IMessageLoopExtensions *, __int64))(*(_QWORD *)a2 + 24LL))(a2, 3);
    if ( v10 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0x91u, 0);
  }
  v30 = 0x10200000102LL;
  v11 = 0;
  v31 = 258;
  v32 = 258;
  do
  {
    v12 = v11;
    v13 = WaitForSingleObject(*((HANDLE *)this + v11++ + 3), 0);
    *((_DWORD *)&v30 + v12) = v13;
  }
  while ( v11 < v6 );
  v14 = !v24 || !(_DWORD)v30;
  v15 = v24 == 1 || !HIDWORD(v30);
  v16 = v24 == 2 || !v31;
  v17 = v24 == 3 || !(_DWORD)v32;
  v18 = v24 == 4 || !HIDWORD(v32);
  if ( !CancelWaitableTimer(*((HANDLE *)this + 1)) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2003304445;
    ModuleFailFastForHRESULT(LastError, retaddr);
  }
  *((_DWORD *)this + 4) = -1;
  if ( v17 )
    CDisplayManager::IsCurrent(v19, 1);
  if ( v18 )
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Dwm_Core_Provider_Context,
        (const EVENT_DESCRIPTOR *)EVTDESC_SCHEDULE_DXGI_OCCLUSION_EVENT,
        v20,
        1u,
        (PEVENT_DATA_DESCRIPTOR)&v30);
    *(_BYTE *)(*((_QWORD *)g_pComposition + 77) + 754LL) = 1;
  }
  if ( (Microsoft_Windows_Dwm_CompositorEnableBits & 1) != 0 )
    McTemplateU0qttttt_EventWriteTransfer(v17, v16, v24, v14, v15, v16, v17, v18);
  v21 = dword_1803BB2E4;
  if ( v14 )
  {
    v21 = dword_1803BB2E4 | 8;
    dword_1803BB2E4 |= 8u;
  }
  if ( v14 & 2 | (2 * v15) & 2 )
  {
    v21 |= 0x10u;
    dword_1803BB2E4 = v21;
  }
  if ( v14 & 4 | ((unsigned __int8)(2 * v15) | (unsigned __int8)(4 * v16)) & 4 )
  {
    v21 |= 2u;
    dword_1803BB2E4 = v21;
  }
  if ( ((v14 | (unsigned __int8)((8 * v18) | (2 * v15) | (4 * v16))) & 8) != 0 )
    dword_1803BB2E4 = v21 | 4;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 4) != 0 )
  {
    v28 = v16;
    v27 = v15;
    v26 = v14;
    v25 = v24;
    v34 = &v25;
    v36 = &v26;
    v38 = &v27;
    v40 = &v28;
    v42 = &v30;
    LODWORD(v30) = v18;
    v35 = 4;
    v37 = 4;
    v39 = 4;
    v41 = 4;
    v43 = 4;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      (const EVENT_DESCRIPTOR *)EVTDESC_SCHEDULE_WFW_Stop,
      v20,
      6u,
      &v33);
  }
  *v29 = GetTickCount64();
}

```

## disassembly

```asm
0x180131e80  push    rbp
0x180131e82  push    rbx
0x180131e83  push    rsi
0x180131e84  push    rdi
0x180131e85  push    r13
0x180131e87  push    r14
0x180131e89  lea     rbp, [rsp-8]
0x180131e8e  sub     rsp, 108h
0x180131e95  mov     rax, cs:__security_cookie
0x180131e9c  xor     rax, rsp
0x180131e9f  mov     [rbp+30h+var_40], rax
0x180131ea3  mov     rax, cs:qword_1803BB0C8
0x180131eaa  mov     rsi, rcx
0x180131ead  mov     [rcx+30h], rax
0x180131eb1  xor     r13d, r13d
0x180131eb4  mov     rcx, cs:qword_1803BB0D0
0x180131ebb  mov     rbx, rdx
0x180131ebe  lea     rax, [rcx-1]
0x180131ec2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180131ec6  jbe     short loc_180131F1C
0x180131ec8  cmp     cs:qword_1803BB0B8, r13
0x180131ecf  jz      loc_1801323C6
0x180131ed5  cmp     cs:byte_1803BB0E2, r13b
0x180131edc  jnz     loc_1801323AC
0x180131ee2  xor     r9d, r9d; lpName
0x180131ee5  xor     r8d, r8d; bInitialState
0x180131ee8  xor     edx, edx; bManualReset
0x180131eea  xor     ecx, ecx; lpEventAttributes
0x180131eec  call    cs:__imp_CreateEventW
0x180131ef2  mov     rdi, rax
0x180131ef5  mov     [rsp+130h+var_B8], rax
0x180131efa  dec     rax
0x180131efd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180131f01  jbe     loc_18013235B
0x180131f07  lea     rax, [rdi-1]
0x180131f0b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180131f0f  jbe     loc_18013239E
0x180131f15  mov     rcx, cs:qword_1803BB0D0
0x180131f1c  test    rcx, rcx
0x180131f1f  mov     [rsi+38h], rcx
0x180131f23  mov     r14d, r13d
0x180131f26  lea     rcx, [rsp+130h+var_C8]; this
0x180131f2b  setnz   r14b
0x180131f2f  add     r14d, 4
0x180131f33  call    ??0CRenderThreadWaitTick@@QEAA@PEC_K@Z; CRenderThreadWaitTick::CRenderThreadWaitTick(unsigned __int64 volatile *)
0x180131f38  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 4
0x180131f3f  jnz     loc_180131FF3
0x180131f45  test    byte ptr cs:Microsoft_Windows_Dwm_CompositorEnableBits, 1
0x180131f4c  jnz     loc_180132300
0x180131f52  mov     [rsp+130h+var_F0], r13d
0x180131f57  mov     rax, [rbx]
0x180131f5a  lea     rcx, [rsp+130h+var_F0]
0x180131f5f  mov     [rsp+130h+var_108], rcx
0x180131f64  lea     r8, [rsi+18h]
0x180131f68  mov     r9d, 0FFFFFFFFh
0x180131f6e  mov     [rsp+130h+var_110], r13d
0x180131f73  mov     edx, r14d
0x180131f76  mov     rcx, rbx
0x180131f79  mov     rax, [rax+20h]
0x180131f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131f82  test    eax, eax
0x180131f84  jns     loc_18013201B
0x180131f8a  mov     [rsp+130h+var_108], r13; void *
0x180131f8f  mov     r9d, eax; int
0x180131f92  xor     r8d, r8d; unsigned int
0x180131f95  mov     [rsp+130h+var_110], 82h; unsigned int
0x180131f9d  xor     edx, edx; int *
0x180131f9f  mov     ecx, 14h; unsigned int
0x180131fa4  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180131fa9  mov     eax, 0FFFFFFFFh
0x180131fae  mov     [rsp+130h+var_F0], eax
0x180131fb2  cmp     eax, r14d
0x180131fb5  jb      short loc_180132021
0x180131fb7  mov     rax, [rbx]
0x180131fba  mov     edx, 3
0x180131fbf  mov     rcx, rbx
0x180131fc2  mov     rax, [rax+18h]
0x180131fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131fcb  test    eax, eax
0x180131fcd  jns     short loc_180131F57
0x180131fcf  mov     [rsp+130h+var_108], r13; void *
0x180131fd4  mov     r9d, eax; int
0x180131fd7  xor     r8d, r8d; unsigned int
0x180131fda  mov     [rsp+130h+var_110], 91h; unsigned int
0x180131fe2  xor     edx, edx; int *
0x180131fe4  mov     ecx, 14h; unsigned int
0x180131fe9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180131fee  jmp     loc_180131F57
0x180131ff3  lea     rax, [rsp+130h+var_B8]
0x180131ff8  mov     r9d, 1
0x180131ffe  lea     rdx, EVTDESC_SCHEDULE_WFW_Start
0x180132005  mov     qword ptr [rsp+130h+var_110], rax
0x18013200a  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180132011  call    McGenEventWrite_EventWriteTransfer
0x180132016  jmp     loc_180131F45
0x18013201b  mov     eax, [rsp+130h+var_F0]
0x18013201f  jmp     short loc_180131FB2
0x180132021  mov     dword ptr [rsp+130h+var_B8], 102h
0x180132029  mov     edi, r13d
0x18013202c  mov     dword ptr [rsp+130h+var_B8+4], 102h
0x180132034  mov     [rbp+30h+var_B0], 102h
0x18013203b  mov     [rbp+30h+var_AC], 102h
0x180132043  nop     dword ptr [rax+00h]
0x180132047  nop     word ptr [rax+rax+00000000h]
0x180132050  mov     ebx, edi
0x180132052  xor     edx, edx; dwMilliseconds
0x180132054  mov     rcx, [rsi+rbx*8+18h]; hHandle
0x180132059  call    cs:__imp_WaitForSingleObject
0x18013205f  inc     edi
0x180132061  mov     dword ptr [rsp+rbx*4+130h+var_B8], eax
0x180132065  cmp     edi, r14d
0x180132068  jb      short loc_180132050
0x18013206a  mov     eax, [rsp+130h+var_F0]
0x18013206e  mov     [rsp+130h+arg_10], r12
0x180132076  test    eax, eax
0x180132078  jnz     loc_180132205
0x18013207e  mov     r12b, 1
0x180132081  mov     [rsp+130h+var_30], r15
0x180132089  cmp     eax, 1
0x18013208c  jnz     loc_1801321F2
0x180132092  mov     r15b, 1
0x180132095  cmp     eax, 2
0x180132098  jnz     loc_1801321E0
0x18013209e  mov     r14b, 1
0x1801320a1  cmp     eax, 3
0x1801320a4  jnz     loc_1801321BD
0x1801320aa  mov     dil, 1
0x1801320ad  cmp     eax, 4
0x1801320b0  jnz     loc_1801321CF
0x1801320b6  mov     bl, 1
0x1801320b8  mov     rcx, [rsi+8]; hTimer
0x1801320bc  call    cs:__imp_CancelWaitableTimer
0x1801320c2  test    eax, eax
0x1801320c4  jz      loc_180132195
0x1801320ca  mov     dword ptr [rsi+10h], 0FFFFFFFFh
0x1801320d1  test    dil, dil
0x1801320d4  jnz     loc_1801323CE
0x1801320da  test    bl, bl
0x1801320dc  jnz     loc_1801322B8
0x1801320e2  test    byte ptr cs:Microsoft_Windows_Dwm_CompositorEnableBits, 1
0x1801320e9  jnz     loc_180132328
0x1801320ef  movzx   edx, bl
0x1801320f2  movzx   ecx, r14b
0x1801320f6  shl     ecx, 2
0x1801320f9  movzx   eax, r15b
0x1801320fd  add     eax, eax
0x1801320ff  or      ecx, eax
0x180132101  lea     eax, ds:0[rdx*8]
0x180132108  or      ecx, eax
0x18013210a  movzx   eax, r12b
0x18013210e  or      ecx, eax
0x180132110  mov     eax, cs:dword_1803BB2E4
0x180132116  test    cl, 1
0x180132119  jz      short loc_180132124
0x18013211b  or      eax, 8
0x18013211e  mov     cs:dword_1803BB2E4, eax
0x180132124  test    cl, 2
0x180132127  jz      short loc_180132132
0x180132129  or      eax, 10h
0x18013212c  mov     cs:dword_1803BB2E4, eax
0x180132132  test    cl, 4
0x180132135  jz      short loc_180132140
0x180132137  or      eax, 2
0x18013213a  mov     cs:dword_1803BB2E4, eax
0x180132140  test    cl, 8
0x180132143  jz      short loc_18013214E
0x180132145  or      eax, 4
0x180132148  mov     cs:dword_1803BB2E4, eax
0x18013214e  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 4
0x180132155  jnz     loc_180132218
0x18013215b  call    cs:__imp_GetTickCount64
0x180132161  mov     rcx, [rsp+130h+var_C8]
0x180132166  mov     r15, [rsp+130h+var_30]
0x18013216e  mov     r12, [rsp+130h+arg_10]
0x180132176  mov     [rcx], rax
0x180132179  mov     rcx, [rbp+30h+var_40]
0x18013217d  xor     rcx, rsp; StackCookie
0x180132180  call    __security_check_cookie
0x180132185  add     rsp, 108h
0x18013218c  pop     r14
0x18013218e  pop     r13
0x180132190  pop     rdi
0x180132191  pop     rsi
0x180132192  pop     rbx
0x180132193  pop     rbp
0x180132194  retn
0x180132195  call    cs:__imp_GetLastError
0x18013219b  test    eax, eax
0x18013219d  jle     short loc_1801321A7
0x18013219f  movzx   eax, ax
0x1801321a2  or      eax, 80070000h
0x1801321a7  mov     rdx, [rbp+38h]; void *
0x1801321ab  mov     ecx, 88980003h
0x1801321b0  test    eax, eax
0x1801321b2  cmovns  eax, ecx
0x1801321b5  mov     ecx, eax; int
0x1801321b7  call    ModuleFailFastForHRESULT
0x1801321bd  cmp     dword ptr [rbp+30h+var_AC], r13d
0x1801321c1  jz      loc_1801320AA
0x1801321c7  xor     dil, dil
0x1801321ca  jmp     loc_1801320AD
0x1801321cf  cmp     dword ptr [rbp+30h+var_AC+4], r13d
0x1801321d3  jz      loc_1801320B6
0x1801321d9  xor     bl, bl
0x1801321db  jmp     loc_1801320B8
0x1801321e0  cmp     [rbp+30h+var_B0], r13d
0x1801321e4  jz      loc_18013209E
0x1801321ea  xor     r14b, r14b
0x1801321ed  jmp     loc_1801320A1
0x1801321f2  cmp     dword ptr [rsp+130h+var_B8+4], r13d
0x1801321f7  jz      loc_180132092
0x1801321fd  xor     r15b, r15b
0x180132200  jmp     loc_180132095
0x180132205  cmp     dword ptr [rsp+130h+var_B8], r13d
0x18013220a  jz      loc_18013207E
0x180132210  xor     r12b, r12b
0x180132213  jmp     loc_180132081
0x180132218  movzx   eax, r14b
0x18013221c  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180132223  mov     [rsp+130h+var_D0], eax
0x180132227  mov     r9d, 6
0x18013222d  movzx   eax, r15b
0x180132231  mov     [rsp+130h+var_D8], eax
0x180132235  movzx   eax, r12b
0x180132239  mov     [rsp+130h+var_E0], eax
0x18013223d  mov     eax, [rsp+130h+var_F0]
0x180132241  mov     [rsp+130h+var_E8], eax
0x180132245  lea     rax, [rsp+130h+var_E8]
0x18013224a  mov     [rbp+30h+var_90], rax
0x18013224e  lea     rax, [rsp+130h+var_E0]
0x180132253  mov     [rbp+30h+var_80], rax
0x180132257  lea     rax, [rsp+130h+var_D8]
0x18013225c  mov     [rbp+30h+var_70], rax
0x180132260  lea     rax, [rsp+130h+var_D0]
0x180132265  mov     [rbp+30h+var_60], rax
0x180132269  lea     rax, [rsp+130h+var_B8]
0x18013226e  mov     [rbp+30h+var_50], rax
0x180132272  lea     rax, [rbp+30h+var_A0]
0x180132276  mov     dword ptr [rsp+130h+var_B8], edx
0x18013227a  lea     rdx, EVTDESC_SCHEDULE_WFW_Stop
0x180132281  mov     qword ptr [rsp+130h+var_110], rax
0x180132286  mov     [rbp+30h+var_88], 4
0x18013228e  mov     [rbp+30h+var_78], 4
0x180132296  mov     [rbp+30h+var_68], 4
0x18013229e  mov     [rbp+30h+var_58], 4
0x1801322a6  mov     [rbp+30h+var_48], 4
0x1801322ae  call    McGenEventWrite_EventWriteTransfer
0x1801322b3  jmp     loc_18013215B
0x1801322b8  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x1801322bf  jnz     short loc_1801322DB
0x1801322c1  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1801322c8  mov     rcx, [rax+268h]
0x1801322cf  mov     byte ptr [rcx+2F2h], 1
0x1801322d6  jmp     loc_1801320E2
0x1801322db  lea     rax, [rsp+130h+var_B8]
0x1801322e0  mov     r9d, 1
0x1801322e6  lea     rdx, EVTDESC_SCHEDULE_DXGI_OCCLUSION_EVENT
0x1801322ed  mov     qword ptr [rsp+130h+var_110], rax
0x1801322f2  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801322f9  call    McGenEventWrite_EventWriteTransfer
0x1801322fe  jmp     short loc_1801322C1
0x180132300  lea     rax, [rsp+130h+var_B8]
0x180132305  mov     r9d, 1
0x18013230b  lea     rdx, WaitForWork_Start
0x180132312  mov     qword ptr [rsp+130h+var_110], rax
0x180132317  lea     rcx, Microsoft_Windows_Dwm_Compositor_Context
0x18013231e  call    McGenEventWrite_EventWriteTransfer
0x180132323  jmp     loc_180131F52
0x180132328  movzx   r8d, r15b
0x18013232c  movzx   eax, bl
0x18013232f  mov     [rsp+130h+var_F8], eax
0x180132333  movzx   ecx, dil
0x180132337  mov     [rsp+130h+var_100], ecx
0x18013233b  movzx   edx, r14b
0x18013233f  mov     dword ptr [rsp+130h+var_108], edx
0x180132343  mov     [rsp+130h+var_110], r8d
0x180132348  mov     r8d, [rsp+130h+var_F0]
0x18013234d  movzx   r9d, r12b
0x180132351  call    McTemplateU0qttttt_EventWriteTransfer
0x180132356  jmp     loc_1801320EF
0x18013235b  mov     rcx, cs:qword_1803BB0B8
0x180132362  lea     r8, qword_1803BB0D8+4
0x180132369  mov     rdx, rdi
0x18013236c  mov     rax, [rcx]
0x18013236f  mov     rax, [rax+0B0h]
0x180132376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013237b  test    eax, eax
0x18013237d  js      loc_180131F07
0x180132383  lea     rdx, [rsp+130h+var_B8]
0x180132388  lea     rcx, qword_1803BB0D0
0x18013238f  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180132394  mov     rdi, [rsp+130h+var_B8]
0x180132399  jmp     loc_180131F07
0x18013239e  mov     rcx, rdi; hObject
0x1801323a1  call    cs:__imp_CloseHandle
0x1801323a7  jmp     loc_180131F15
0x1801323ac  call    cs:__imp_DwmGetRemoteSessionOcclusionEvent
0x1801323b2  mov     rdx, rax
0x1801323b5  lea     rcx, qword_1803BB0D0
0x1801323bc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
  ... truncated ...
```
