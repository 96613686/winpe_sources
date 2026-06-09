# CJob::BeginDownload(void)

- ea: `0x1800138c0`
- end: `0x180013b67`
- name: `?BeginDownload@CJob@@MEAAXXZ`
- size: `679`
- prototype: `void __fastcall(CJob *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180006640`
- `0x1800138c0`
- `0x180013b70`
- `0x180014310`
- `0x180063740`
- `0x18007c07c`
- `0x18009d04c`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a7558`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180013a28`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180013a28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180013af3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180013af3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180013a4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180013a4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800139e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800139e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CJob::BeginDownload(CJob *this)
{
  _DWORD *v2; // rax
  __int64 v3; // rax
  void *v4; // rbx
  __int64 v5; // rax
  struct _TP_WAIT *v6; // rcx
  __int64 v7; // rcx
  unsigned int LastError; // eax
  void *v9; // rax
  unsigned int v10; // edx
  CJobManager *v11; // rcx
  unsigned int v12; // r8d
  ComError *v13; // rax
  int v14; // r8d
  CJob *v15; // r14
  __int64 v16; // rax
  __int64 v17; // rsi
  int v18; // edi
  int v19; // ebx
  unsigned int v20; // edx
  CJob::TRANSFER_GLOB *v21; // rcx
  char v22; // [rsp+30h] [rbp-1A8h]
  void *v23; // [rsp+50h] [rbp-188h] BYREF
  __int64 v24; // [rsp+58h] [rbp-180h] BYREF
  __int16 v25; // [rsp+60h] [rbp-178h]
  CJob *v26; // [rsp+68h] [rbp-170h] BYREF
  int v27; // [rsp+70h] [rbp-168h]
  int v28; // [rsp+74h] [rbp-164h]
  __int64 v29; // [rsp+78h] [rbp-160h]
  void **pExceptionObject; // [rsp+80h] [rbp-158h] BYREF
  __int128 v31; // [rsp+88h] [rbp-150h]
  unsigned int v32; // [rsp+98h] [rbp-140h]
  int v33; // [rsp+9Ch] [rbp-13Ch]
  int v34; // [rsp+A0h] [rbp-138h]
  __int64 v35; // [rsp+E0h] [rbp-F8h] BYREF
  void **v36; // [rsp+140h] [rbp-98h] BYREF
  __int64 v37; // [rsp+148h] [rbp-90h] BYREF
  int v38; // [rsp+158h] [rbp-80h]

  v26 = this;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
      this,
      *((_DWORD *)this + 210));
  *((_QWORD *)this + 81) = 0;
  try
  {
    v2 = operator new(0x10u);
    v23 = v2;
    v2[2] = 1;
    *(_QWORD *)v2 = 0;
    if ( CJob::GetToken(this, (struct TokenHandle *)&v23) )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          123,
          &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
          *((_DWORD *)this + 164) != 0);
      v3 = *(_QWORD *)this;
      v4 = v23;
      v24 = (__int64)v23;
      _InterlockedIncrement((volatile signed __int32 *)v23 + 2);
      v5 = (*(__int64 (__fastcall **)(CJob *, __int64 *))(v3 + 280))(this, &v24);
      if ( v5 )
      {
        *((_QWORD *)this + 81) = v5;
        *((_BYTE *)this + 1269) = 0;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 32) + 48LL))(*(_QWORD *)(v5 + 32));
        v6 = *(struct _TP_WAIT **)(*((_QWORD *)this + 81) + 48LL);
        if ( v6 )
          CloseThreadpoolWait(v6);
        *(_QWORD *)(*((_QWORD *)this + 81) + 48LL) = CreateThreadpoolWait(
                                                       CJob::StaticOnTransferComplete,
                                                       *((PVOID *)this + 81),
                                                       (PTP_CALLBACK_ENVIRON)((char *)g_Manager + 992));
        v7 = *((_QWORD *)this + 81);
        if ( !*(_QWORD *)(v7 + 48) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0x80070000;
          else
            LastError = GetLastError();
          v31 = 0;
          pExceptionObject = &ComError::`vftable';
          v32 = LastError;
          v33 = 4965;
          v34 = 1;
          throw (ComError *)&pExceptionObject;
        }
        v9 = (void *)(***(__int64 (__fastcall ****)(_QWORD))(v7 + 32))(*(_QWORD *)(v7 + 32));
        SetThreadpoolWait(*(PTP_WAIT *)(*((_QWORD *)this + 81) + 48LL), v9, 0);
        *((struct _FILETIME *)this + 124) = GetUtcTime();
        v10 = *((_DWORD *)this + 304);
        if ( v10 != -1 )
        {
          v11 = (CJobManager *)*((unsigned int *)this + 305);
          v12 = 0;
          if ( (unsigned int)v11 <= v10 )
            v12 = v10 - (_DWORD)v11;
          CJobManager::ScheduleDelayedTask(v11, (CJob *)((char *)this + 400), v12);
        }
        RefCountedObject::AddRef((CJob *)((char *)this + 600));
        TokenHandle::Decrement((TokenHandle *)&v23);
      }
      else if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( (unsigned __int64)(*(_QWORD *)v4 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v4);
          *(_QWORD *)v4 = 0;
        }
        operator delete(v4, 0x10u);
      }
    }
    else
    {
      TokenHandle::Decrement((TokenHandle *)&v23);
    }
  }
  catch ( ComError v36 )
  {
    v13 = ComError::ComError((ComError *)&v35, (const struct ComError *)&v36);
    LogException(v13);
    v15 = v26;
    if ( *((_QWORD *)v26 + 81) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v26 + 81) + 32LL) + 16LL))(*(_QWORD *)(*((_QWORD *)v26 + 81) + 32LL));
      v24 = -1;
      v25 = 0;
      (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)v15 + 81) + 32LL) + 160LL))(
        *(_QWORD *)(*((_QWORD *)v15 + 81) + 32LL),
        &v24);
      v26 = 0;
      LOWORD(v27) = 0;
      BYTE2(v27) = 0;
      (*(void (__fastcall **)(_QWORD, CJob **))(**(_QWORD **)(*((_QWORD *)v15 + 81) + 32LL) + 208LL))(
        *(_QWORD *)(*((_QWORD *)v15 + 81) + 32LL),
        &v26);
      v16 = *((_QWORD *)v15 + 81);
      v17 = *(_QWORD *)(v16 + 8);
      v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v16 + 32) + 152LL))(*(_QWORD *)(v16 + 32));
      v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v15 + 81) + 32LL) + 144LL))(*(_QWORD *)(*((_QWORD *)v15 + 81) + 32LL));
      v22 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v15 + 81) + 32LL) + 136LL))(*(_QWORD *)(*((_QWORD *)v15 + 81) + 32LL));
      CFile::ReportTransferAttemptStop(
        v17,
        *((_QWORD *)v15 + 81) + 56LL,
        *((_QWORD *)v15 + 87) + 12LL,
        (char *)v15 + 676,
        3,
        v38,
        v22,
        v19,
        v18,
        &v24);
      v21 = (CJob::TRANSFER_GLOB *)*((_QWORD *)v15 + 81);
      if ( v21 )
        CJob::TRANSFER_GLOB::`scalar deleting destructor'(v21, v20);
      *((_QWORD *)v15 + 81) = 0;
    }
    LODWORD(v26) = 2;
    v29 = 0;
    v28 = 2;
    v27 = 1;
    HIDWORD(v26) = v38;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_llDDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&qword_18011AC70,
        v14,
        2,
        1,
        v38,
        2,
        (__int64)&qword_18011AC70);
    CJob::SetTransientError(v15, (struct QMErrInfo *)&v26, *((_DWORD *)v15 + 210), 1, 1);
    v36 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(&v37);
  }
}

```

## disassembly

```asm
0x1800138c0  push    rbx
0x1800138c2  push    rsi
0x1800138c3  push    rdi
0x1800138c4  push    r14
0x1800138c6  sub     rsp, 1B8h
0x1800138cd  mov     rax, cs:__security_cookie
0x1800138d4  xor     rax, rsp
0x1800138d7  mov     [rsp+1D8h+var_38], rax
0x1800138df  mov     rdi, rcx
0x1800138e2  mov     [rsp+1D8h+var_170], rcx
0x1800138e7  lea     rbx, WPP_GLOBAL_Control
0x1800138ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138f5  cmp     rcx, rbx
0x1800138f8  jz      short loc_180013922
0x1800138fa  test    byte ptr [rcx+1Ch], 1
0x1800138fe  jz      short loc_180013922
0x180013900  mov     edx, 7Ah ; 'z'
0x180013905  mov     eax, [rdi+348h]
0x18001390b  mov     [rsp+1D8h+var_1B8], eax
0x18001390f  mov     r9, rdi
0x180013912  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x180013919  mov     rcx, [rcx+10h]
0x18001391d  call    WPP_SF_qD
0x180013922  xor     esi, esi
0x180013924  mov     [rdi+288h], rsi
0x18001392b  lea     r14d, [rsi+10h]
0x18001392f  mov     ecx, r14d; dwBytes
0x180013932  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013937  mov     [rsp+1D8h+var_188], rax
0x18001393c  mov     dword ptr [rax+8], 1
0x180013943  mov     [rax], rsi
0x180013946  lea     rdx, [rsp+1D8h+var_188]; struct TokenHandle *
0x18001394b  mov     rcx, rdi; this
0x18001394e  call    ?GetToken@CJob@@IEAA_NPEAVTokenHandle@@@Z; CJob::GetToken(TokenHandle *)
0x180013953  test    al, al
0x180013955  jnz     short loc_180013966
0x180013957  lea     rcx, [rsp+1D8h+var_188]; this
0x18001395c  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x180013961  jmp     loc_180013B49
0x180013966  mov     rcx, cs:WPP_GLOBAL_Control
0x18001396d  cmp     rcx, rbx
0x180013970  jz      short loc_18001399D
0x180013972  test    dword ptr [rcx+1Ch], 800h
0x180013979  jz      short loc_18001399D
0x18001397b  mov     r9d, esi
0x18001397e  cmp     [rdi+290h], esi
0x180013984  setnz   r9b
0x180013988  mov     edx, 7Bh ; '{'
0x18001398d  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x180013994  mov     rcx, [rcx+10h]
0x180013998  call    WPP_SF_d
0x18001399d  mov     rax, [rdi]
0x1800139a0  mov     rbx, [rsp+1D8h+var_188]
0x1800139a5  mov     [rsp+1D8h+var_180], rbx
0x1800139aa  lock inc dword ptr [rbx+8]
0x1800139ae  lea     rdx, [rsp+1D8h+var_180]
0x1800139b3  mov     rcx, rdi
0x1800139b6  mov     rax, [rax+118h]
0x1800139bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139c2  test    rax, rax
0x1800139c5  jnz     short loc_1800139FA
0x1800139c7  or      eax, 0FFFFFFFFh
0x1800139ca  lock xadd [rbx+8], eax
0x1800139cf  cmp     eax, 1
0x1800139d2  jnz     short loc_1800139F5
0x1800139d4  mov     rcx, [rbx]; hObject
0x1800139d7  lea     rax, [rcx-1]
0x1800139db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800139df  ja      short loc_1800139EA
0x1800139e1  call    cs:__imp_CloseHandle
0x1800139e7  mov     [rbx], rsi
0x1800139ea  mov     rdx, r14; unsigned __int64
0x1800139ed  mov     rcx, rbx; void *
0x1800139f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800139f5  jmp     loc_180013B49
0x1800139fa  mov     [rdi+288h], rax
0x180013a01  mov     [rdi+4F5h], sil
0x180013a08  mov     rcx, [rax+20h]
0x180013a0c  mov     rax, [rcx]
0x180013a0f  mov     rax, [rax+30h]
0x180013a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a18  mov     rax, [rdi+288h]
0x180013a1f  mov     rcx, [rax+30h]; pwa
0x180013a23  test    rcx, rcx
0x180013a26  jz      short loc_180013A2E
0x180013a28  call    cs:__imp_CloseThreadpoolWait
0x180013a2e  mov     r8, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180013a35  add     r8, 3E0h; pcbe
0x180013a3c  mov     rdx, [rdi+288h]; pv
0x180013a43  lea     rcx, ?StaticOnTransferComplete@CJob@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180013a4a  call    cs:__imp_CreateThreadpoolWait
0x180013a50  mov     rcx, [rdi+288h]
0x180013a57  mov     [rcx+30h], rax
0x180013a5b  mov     rcx, [rdi+288h]
0x180013a62  cmp     [rcx+30h], rsi
0x180013a66  jnz     short loc_180013AD3
0x180013a68  call    cs:__imp_GetLastError
0x180013a6e  test    eax, eax
0x180013a70  jg      short loc_180013A7A
0x180013a72  call    cs:__imp_GetLastError
0x180013a78  jmp     short loc_180013A88
0x180013a7a  call    cs:__imp_GetLastError
0x180013a80  movzx   eax, ax
0x180013a83  or      eax, 80070000h
0x180013a88  xorps   xmm0, xmm0
0x180013a8b  movups  [rsp+1D8h+var_150], xmm0
0x180013a93  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180013a9a  mov     [rsp+1D8h+pExceptionObject], rcx
0x180013aa2  mov     [rsp+1D8h+var_140], eax
0x180013aa9  mov     [rsp+1D8h+var_13C], 1365h
0x180013ab4  mov     [rsp+1D8h+var_138], 1
0x180013abf  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180013ac6  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x180013ace  call    _CxxThrowException_0
0x180013ad3  mov     rcx, [rcx+20h]
0x180013ad7  mov     rax, [rcx]
0x180013ada  mov     rax, [rax]
0x180013add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ae2  mov     rcx, [rdi+288h]
0x180013ae9  xor     r8d, r8d; pftTimeout
0x180013aec  mov     rdx, rax; h
0x180013aef  mov     rcx, [rcx+30h]; pwa
0x180013af3  call    cs:__imp_SetThreadpoolWait
0x180013af9  call    ?GetUtcTime@@YA?AU_FILETIME@@XZ; GetUtcTime(void)
0x180013afe  mov     [rdi+3E0h], rax
0x180013b05  mov     edx, [rdi+4C0h]
0x180013b0b  cmp     edx, 0FFFFFFFFh
0x180013b0e  jz      short loc_180013B2F
0x180013b10  mov     ecx, [rdi+4C4h]; this
0x180013b16  mov     eax, edx
0x180013b18  sub     eax, ecx
0x180013b1a  mov     r8d, esi
0x180013b1d  cmp     ecx, edx
0x180013b1f  cmovbe  r8d, eax; unsigned int
0x180013b23  lea     rdx, [rdi+190h]; struct TaskSchedulerWorkItem *
0x180013b2a  call    ?ScheduleDelayedTask@CJobManager@@QEAAXPEAVTaskSchedulerWorkItem@@K@Z; CJobManager::ScheduleDelayedTask(TaskSchedulerWorkItem *,ulong)
0x180013b2f  lea     rcx, [rdi+258h]; this
0x180013b36  call    ?AddRef@RefCountedObject@@QEAAKXZ; RefCountedObject::AddRef(void)
0x180013b3b  nop
0x180013b3c  lea     rcx, [rsp+1D8h+var_188]; this
0x180013b41  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x180013b46  nop
0x180013b47  jmp     short $+2
0x180013b49  mov     rcx, [rsp+1D8h+var_38]
0x180013b51  xor     rcx, rsp; StackCookie
0x180013b54  call    __security_check_cookie
0x180013b59  add     rsp, 1B8h
0x180013b60  pop     r14
0x180013b62  pop     rdi
0x180013b63  pop     rsi
0x180013b64  pop     rbx
0x180013b65  retn
```
