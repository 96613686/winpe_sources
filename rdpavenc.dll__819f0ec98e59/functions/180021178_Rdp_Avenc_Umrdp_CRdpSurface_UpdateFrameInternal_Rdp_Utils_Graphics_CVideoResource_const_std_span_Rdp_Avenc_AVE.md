# Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal(Rdp::Utils::Graphics::CVideoResource const &,std::span<Rdp::Avenc::AVENC_MOVEREGION const,-1> const &,std::span<tagRECT const,-1> const &,uint)

- ea: `0x180021178`
- end: `0x1800218c8`
- name: `?UpdateFrameInternal@CRdpSurface@Umrdp@Avenc@Rdp@@AEAAIAEBVCVideoResource@Graphics@Utils@4@AEBV?$span@$$CBUAVENC_MOVEREGION@Avenc@Rdp@@$0?0@std@@AEBV?$span@$$CBUtagRECT@@$0?0@9@I@Z`
- size: `1872`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180020ea4`
- `0x180020f98`

## callees

- `0x180001008`
- `0x1800021e4`
- `0x180007248`
- `0x18000d4bc`
- `0x180013b4c`
- `0x180017c70`
- `0x180021178`
- `0x180021994`
- `0x180089010`

## string_xrefs

- `0x18002127a`: `MonitorIndex %d, Copy %zu move regions`
- `0x180021242`: `Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal`
- `0x1800214e0`: `Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal`
- `0x180021564`: `Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal`
- `0x180021575`: `Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal`
- `0x1800216af`: `Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal`
- `0x180021804`: `Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal`
- `0x18002136e`: `MonitorIndex %d, MoveRgn: SrcRect(%d,%d) -> DestRect(%d-%d, %d-%d)`
- `0x1800214d5`: `Failed to copy move region`
- `0x1800215ad`: `MonitorIndex %d, Copy %zu dirty rects`
- `0x1800217f9`: `Failed to copy dirty rect`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        int a5)
{
  _QWORD *v5; // r12
  __int64 v8; // r10
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  char *v11; // rbx
  int v12; // r8d
  int v13; // r9d
  _DWORD *v14; // rsi
  __int64 v15; // r13
  int v16; // r8d
  int v17; // r9d
  int v18; // r15d
  int v19; // r10d
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rdx
  signed __int32 v23; // eax
  signed __int32 v24; // ett
  char *v25; // rcx
  __int64 v26; // rdi
  __int64 v27; // r8
  __int64 v28; // rax
  char v29; // al
  int v30; // r8d
  int v31; // r9d
  char v32; // r15
  int v33; // r8d
  int v34; // r9d
  _DWORD *v35; // rdi
  __int64 v36; // r15
  int v37; // r13d
  int v38; // r8d
  int v39; // r12d
  int v40; // r9d
  int v41; // r8d
  int v42; // r9d
  __int64 v43; // rdx
  signed __int32 v44; // eax
  signed __int32 v45; // ett
  char *v46; // rcx
  __int64 v47; // rsi
  __int64 v48; // r8
  __int64 v49; // rax
  char v50; // al
  int v51; // r8d
  int v52; // r9d
  char v53; // r12
  int v55; // [rsp+68h] [rbp-61h] BYREF
  char *v56; // [rsp+70h] [rbp-59h] BYREF
  char *v57; // [rsp+78h] [rbp-51h] BYREF
  const char *v58; // [rsp+80h] [rbp-49h] BYREF
  int v59; // [rsp+88h] [rbp-41h] BYREF
  int v60; // [rsp+8Ch] [rbp-3Dh] BYREF
  int v61; // [rsp+90h] [rbp-39h] BYREF
  char *Buffer[2]; // [rsp+98h] [rbp-31h] BYREF
  const char *v63; // [rsp+B0h] [rbp-19h] BYREF
  const char *v64; // [rsp+B8h] [rbp-11h] BYREF
  char *v65; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-1h]
  char *v67; // [rsp+D8h] [rbp+Fh]
  unsigned int v68; // [rsp+128h] [rbp+5Fh]

  v5 = a4;
  *(_OWORD *)Buffer = 0;
  v8 = *(_QWORD *)(a1 + 16);
  if ( !v8 )
LABEL_65:
    std::_Throw_bad_weak_ptr();
  v9 = *(_DWORD *)(v8 + 8);
  do
  {
    if ( !v9 )
      goto LABEL_65;
    v10 = v9;
    v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
  }
  while ( v10 != v9 );
  v11 = *(char **)(a1 + 8);
  Buffer[0] = v11;
  Buffer[1] = *(char **)(a1 + 16);
  v68 = 0;
  v67 = v11;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
  if ( Buffer[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Buffer[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(char *))Buffer[1])(Buffer[1]);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Buffer[1] + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)Buffer[1] + 8LL))(Buffer[1]);
    }
  }
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    std::vector<char>::vector<char>(Buffer);
    snprintf(Buffer[0], Buffer[1] - Buffer[0], "MonitorIndex %d, Copy %zu move regions", *(_DWORD *)(a1 + 56), a3[1]);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v56 = Buffer[0];
      v64 = "Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal";
      v59 = 137;
      v63 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&byte_1800ADCB7,
        v12,
        v13,
        (__int64)&v63,
        (__int64)&v59,
        (__int64)&v64,
        (__int64)&v56);
    }
    std::vector<char>::~vector<char>(Buffer);
  }
  v14 = (_DWORD *)*a3;
  v15 = *a3 + 28LL * a3[1];
  if ( *a3 != v15 )
  {
    do
    {
      v16 = v14[6];
      v60 = v16;
      v17 = v14[4];
      v61 = v17;
      v18 = v14[5];
      v19 = v14[3];
      v55 = v19;
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        std::vector<char>::vector<char>(&v65);
        snprintf(
          v65,
          v66 - (_QWORD)v65,
          "MonitorIndex %d, MoveRgn: SrcRect(%d,%d) -> DestRect(%d-%d, %d-%d)",
          *(_DWORD *)(a1 + 56),
          v14[1],
          v14[2],
          v14[3],
          v14[4],
          v14[5],
          v14[6]);
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v57 = v65;
          v58 = "Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal";
          v59 = 150;
          Buffer[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&dword_1800ADC7C,
            v20,
            v21,
            (__int64)Buffer,
            (__int64)&v59,
            (__int64)&v58,
            (__int64)&v57);
        }
        std::vector<char>::~vector<char>(&v65);
        v16 = v60;
        v17 = v61;
        v19 = v55;
      }
      *(_OWORD *)Buffer = 0;
      v22 = *(_QWORD *)(a1 + 16);
      if ( !v22 )
LABEL_66:
        std::_Throw_bad_weak_ptr();
      v23 = *(_DWORD *)(v22 + 8);
      do
      {
        if ( !v23 )
          goto LABEL_66;
        v24 = v23;
        v23 = _InterlockedCompareExchange((volatile signed __int32 *)(v22 + 8), v23 + 1, v23);
      }
      while ( v24 != v23 );
      v25 = *(char **)(a1 + 8);
      Buffer[0] = v25;
      v26 = *(_QWORD *)(a1 + 16);
      Buffer[1] = (char *)v26;
      v68 += (v16 - v17) * (v18 - v19);
      v27 = *(_QWORD *)(a2 + 16);
      v28 = *(_QWORD *)v25;
      if ( v27 )
        v29 = (*(__int64 (__fastcall **)(char *, _DWORD *, __int64))(v28 + 40))(v25, v14 + 3, v27);
      else
        v29 = (*(__int64 (__fastcall **)(char *, _DWORD *, __int64))(v28 + 48))(v25, v14 + 3, a2);
      v32 = v29;
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(__int64))v26)(v26);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 12), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
      if ( !v32 )
      {
        if ( (unsigned int)dword_1800C1058 > 2 )
        {
          v55 = a5;
          LODWORD(v63) = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 196LL);
          LODWORD(v64) = *(_DWORD *)(a1 + 56);
          Buffer[0] = "Failed to copy move region";
          v58 = "Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal";
          LODWORD(v56) = 158;
          v57 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&byte_1800ADC1F,
            v30,
            v31,
            (__int64)&v57,
            (__int64)&v56,
            (__int64)&v58,
            (__int64)Buffer,
            (__int64)&v64,
            (__int64)&v63,
            (__int64)&v55);
        }
        Rdp::Avenc::Umrdp::CUmrdpProcessor::ReportCriticalError(
          *(Rdp::Avenc::Umrdp::CUmrdpProcessor **)(a1 + 48),
          1u,
          v30);
      }
      v14 += 7;
    }
    while ( v14 != (_DWORD *)v15 );
    v5 = a4;
  }
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    std::vector<char>::vector<char>(&v65);
    snprintf(v65, v66 - (_QWORD)v65, "MonitorIndex %d, Copy %zu dirty rects", *(_DWORD *)(a1 + 56), v5[1]);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      Buffer[0] = v65;
      v58 = "Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal";
      LODWORD(v56) = 174;
      v57 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&dword_1800ADBE4,
        v33,
        v34,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v58,
        (__int64)Buffer);
    }
    std::vector<char>::~vector<char>(&v65);
  }
  v35 = (_DWORD *)*v5;
  v36 = *v5 + 16LL * v5[1];
  while ( v35 != (_DWORD *)v36 )
  {
    v37 = v35[3];
    v38 = v35[1];
    LODWORD(v64) = v38;
    v39 = v35[2];
    v40 = *v35;
    LODWORD(v63) = *v35;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      std::vector<char>::vector<char>(&v65);
      snprintf(
        v65,
        v66 - (_QWORD)v65,
        "MonitorIndex %d, DirtyRect(%d-%d, %d-%d)",
        *(_DWORD *)(a1 + 56),
        *v35,
        v35[1],
        v35[2],
        v35[3]);
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        Buffer[0] = v65;
        v58 = "Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal";
        LODWORD(v56) = 186;
        v57 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)byte_1800ADBA9,
          v41,
          v42,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)&v58,
          (__int64)Buffer);
      }
      std::vector<char>::~vector<char>(&v65);
      v38 = (int)v64;
      v40 = (int)v63;
    }
    *(_OWORD *)Buffer = 0;
    v43 = *(_QWORD *)(a1 + 16);
    if ( !v43 )
      goto LABEL_66;
    v44 = *(_DWORD *)(v43 + 8);
    do
    {
      if ( !v44 )
        goto LABEL_66;
      v45 = v44;
      v44 = _InterlockedCompareExchange((volatile signed __int32 *)(v43 + 8), v44 + 1, v44);
    }
    while ( v45 != v44 );
    v46 = *(char **)(a1 + 8);
    Buffer[0] = v46;
    v47 = *(_QWORD *)(a1 + 16);
    Buffer[1] = (char *)v47;
    v68 += (v37 - v38) * (v39 - v40);
    v48 = *(_QWORD *)(a2 + 16);
    v49 = *(_QWORD *)v46;
    if ( v48 )
      v50 = (*(__int64 (__fastcall **)(char *, _DWORD *, __int64))(v49 + 40))(v46, v35, v48);
    else
      v50 = (*(__int64 (__fastcall **)(char *, _DWORD *, __int64))(v49 + 48))(v46, v35, a2);
    v53 = v50;
    if ( v47 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v47 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(__int64))v47)(v47);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v47 + 12), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
      }
    }
    if ( !v53 )
    {
      if ( (unsigned int)dword_1800C1058 > 2 )
      {
        LODWORD(v56) = a5;
        v55 = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 196LL);
        v61 = *(_DWORD *)(a1 + 56);
        Buffer[0] = "Failed to copy dirty rect";
        v58 = "Rdp::Avenc::Umrdp::CRdpSurface::UpdateFrameInternal";
        v60 = 194;
        v57 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&dword_1800ADB4C,
          v51,
          v52,
          (__int64)&v57,
          (__int64)&v60,
          (__int64)&v58,
          (__int64)Buffer,
          (__int64)&v61,
          (__int64)&v55,
          (__int64)&v56);
      }
      Rdp::Avenc::Umrdp::CUmrdpProcessor::ReportCriticalError(
        *(Rdp::Avenc::Umrdp::CUmrdpProcessor **)(a1 + 48),
        2u,
        v51);
    }
    v35 += 4;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
  return v68;
}

```

## disassembly

```asm
0x180021178  mov     rax, rsp
0x18002117b  mov     [rax+18h], rbx
0x18002117f  mov     [rax+20h], r9
0x180021183  mov     [rax+10h], rdx
0x180021187  push    rbp
0x180021188  push    rsi
0x180021189  push    rdi
0x18002118a  push    r12
0x18002118c  push    r13
0x18002118e  push    r14
0x180021190  push    r15
0x180021192  lea     rbp, [rax-57h]
0x180021196  sub     rsp, 0E0h
0x18002119d  mov     r12, r9
0x1800211a0  mov     r15, r8
0x1800211a3  mov     r14, rcx
0x1800211a6  xorps   xmm0, xmm0
0x1800211a9  movdqu  xmmword ptr [rbp+4Fh+Buffer], xmm0
0x1800211ae  mov     r10, [rcx+10h]
0x1800211b2  test    r10, r10
0x1800211b5  jz      loc_1800218BC
0x1800211bb  mov     eax, [r10+8]
0x1800211bf  jmp     short loc_1800211CC
0x1800211c1  lea     ecx, [rax+1]
0x1800211c4  lock cmpxchg [r10+8], ecx
0x1800211ca  jz      short loc_1800211D6
0x1800211cc  test    eax, eax
0x1800211ce  jz      loc_1800218BC
0x1800211d4  jmp     short loc_1800211C1
0x1800211d6  mov     rbx, [r14+8]
0x1800211da  mov     [rbp+4Fh+Buffer], rbx
0x1800211de  mov     rdi, [r14+10h]
0x1800211e2  mov     [rbp+4Fh+Buffer+8], rdi
0x1800211e6  mov     [rbp+4Fh+arg_0], 0
0x1800211ed  mov     [rbp+4Fh+var_40], rbx
0x1800211f1  mov     rax, [rbx]
0x1800211f4  mov     rcx, rbx
0x1800211f7  mov     rax, [rax+8]
0x1800211fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021200  nop
0x180021201  or      esi, 0FFFFFFFFh
0x180021204  test    rdi, rdi
0x180021207  jz      short loc_18002123C
0x180021209  mov     eax, esi
0x18002120b  lock xadd [rdi+8], eax
0x180021210  add     eax, esi
0x180021212  jnz     short loc_18002123C
0x180021214  mov     rax, [rdi]
0x180021217  mov     rcx, rdi
0x18002121a  mov     rax, [rax]
0x18002121d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021222  mov     eax, esi
0x180021224  lock xadd [rdi+0Ch], eax
0x180021229  add     eax, esi
0x18002122b  jnz     short loc_18002123C
0x18002122d  mov     rax, [rdi]
0x180021230  mov     rcx, rdi
0x180021233  mov     rax, [rax+8]
0x180021237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002123c  mov     eax, cs:dword_1800C1058
0x180021242  lea     rdi, aRdpAvencUmrdpC_2; "Rdp::Avenc::Umrdp::CRdpSurface::UpdateF"...
0x180021249  lea     rsi, aOnecoreuapTerm_28; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180021250  cmp     eax, 5
0x180021253  jbe     loc_1800212E8
0x180021259  lea     rcx, [rbp+4Fh+Buffer]
0x18002125d  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x180021262  mov     rdx, [rbp+4Fh+Buffer+8]
0x180021266  mov     rcx, [rbp+4Fh+Buffer]; Buffer
0x18002126a  sub     rdx, rcx; BufferCount
0x18002126d  mov     rax, [r15+8]
0x180021271  mov     [rsp+110h+var_F0], rax
0x180021276  mov     r9d, [r14+38h]
0x18002127a  lea     r8, aMonitorindexDC; "MonitorIndex %d, Copy %zu move regions"
0x180021281  call    snprintf
0x180021286  mov     eax, cs:dword_1800C1058
0x18002128c  cmp     eax, 5
0x18002128f  jbe     short loc_1800212DF
0x180021291  mov     rax, [rbp+4Fh+Buffer]
0x180021295  mov     [rbp+4Fh+var_A8], rax
0x180021299  mov     [rbp+4Fh+var_60], rdi
0x18002129d  mov     [rbp+4Fh+var_90], 89h
0x1800212a4  mov     [rbp+4Fh+var_68], rsi
0x1800212a8  lea     rax, [rbp+4Fh+var_A8]
0x1800212ac  mov     [rsp+110h+var_D8], rax
0x1800212b1  lea     rax, [rbp+4Fh+var_60]
0x1800212b5  mov     [rsp+110h+var_E0], rax
0x1800212ba  lea     rax, [rbp+4Fh+var_90]
0x1800212be  mov     [rsp+110h+var_E8], rax
0x1800212c3  lea     rax, [rbp+4Fh+var_68]
0x1800212c7  mov     [rsp+110h+var_F0], rax
0x1800212cc  lea     rdx, byte_1800ADCB7
0x1800212d3  lea     rcx, dword_1800C1058
0x1800212da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800212df  lea     rcx, [rbp+4Fh+Buffer]
0x1800212e3  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800212e8  mov     rsi, [r15]
0x1800212eb  imul    r13, [r15+8], 1Ch
0x1800212f0  add     r13, rsi
0x1800212f3  cmp     rsi, r13
0x1800212f6  jz      loc_18002157C
0x1800212fc  mov     r8d, [rsi+18h]
0x180021300  mov     [rbp+4Fh+var_8C], r8d
0x180021304  mov     r9d, [rsi+10h]
0x180021308  mov     [rbp+4Fh+var_88], r9d
0x18002130c  mov     r15d, [rsi+14h]
0x180021310  lea     r12, [rsi+0Ch]
0x180021314  mov     r10d, [r12]
0x180021318  mov     [rbp+4Fh+var_B0], r10d
0x18002131c  mov     eax, cs:dword_1800C1058
0x180021322  cmp     eax, 5
0x180021325  jbe     loc_1800213EF
0x18002132b  lea     rcx, [rbp+4Fh+var_58]
0x18002132f  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x180021334  mov     rdx, [rbp+4Fh+var_50]
0x180021338  mov     rcx, [rbp+4Fh+var_58]; Buffer
0x18002133c  sub     rdx, rcx; BufferCount
0x18002133f  mov     eax, [rsi+18h]
0x180021342  mov     dword ptr [rsp+110h+var_C8], eax
0x180021346  mov     eax, [rsi+14h]
0x180021349  mov     dword ptr [rsp+110h+var_D0], eax
0x18002134d  mov     eax, [rsi+10h]
0x180021350  mov     dword ptr [rsp+110h+var_D8], eax
0x180021354  mov     eax, [r12]
0x180021358  mov     dword ptr [rsp+110h+var_E0], eax
0x18002135c  mov     eax, [rsi+8]
0x18002135f  mov     dword ptr [rsp+110h+var_E8], eax
0x180021363  mov     eax, [rsi+4]
0x180021366  mov     dword ptr [rsp+110h+var_F0], eax
0x18002136a  mov     r9d, [r14+38h]
0x18002136e  lea     r8, aMonitorindexDM; "MonitorIndex %d, MoveRgn: SrcRect(%d,%d"...
0x180021375  call    snprintf
0x18002137a  mov     eax, cs:dword_1800C1058
0x180021380  cmp     eax, 5
0x180021383  jbe     short loc_1800213DA
0x180021385  mov     rax, [rbp+4Fh+var_58]
0x180021389  mov     [rbp+4Fh+var_A0], rax
0x18002138d  mov     [rbp+4Fh+var_98], rdi
0x180021391  mov     [rbp+4Fh+var_90], 96h
0x180021398  lea     rax, aOnecoreuapTerm_28; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002139f  mov     [rbp+4Fh+Buffer], rax
0x1800213a3  lea     rax, [rbp+4Fh+var_A0]
0x1800213a7  mov     [rsp+110h+var_D8], rax
0x1800213ac  lea     rax, [rbp+4Fh+var_98]
0x1800213b0  mov     [rsp+110h+var_E0], rax
0x1800213b5  lea     rax, [rbp+4Fh+var_90]
0x1800213b9  mov     [rsp+110h+var_E8], rax
0x1800213be  lea     rax, [rbp+4Fh+Buffer]
0x1800213c2  mov     [rsp+110h+var_F0], rax
0x1800213c7  lea     rdx, dword_1800ADC7C
0x1800213ce  lea     rcx, dword_1800C1058
0x1800213d5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800213da  lea     rcx, [rbp+4Fh+var_58]
0x1800213de  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800213e3  mov     r8d, [rbp+4Fh+var_8C]
0x1800213e7  mov     r9d, [rbp+4Fh+var_88]
0x1800213eb  mov     r10d, [rbp+4Fh+var_B0]
0x1800213ef  xorps   xmm0, xmm0
0x1800213f2  movdqu  xmmword ptr [rbp+4Fh+Buffer], xmm0
0x1800213f7  mov     rdx, [r14+10h]
0x1800213fb  test    rdx, rdx
0x1800213fe  jz      loc_1800218C2
0x180021404  mov     eax, [rdx+8]
0x180021407  jmp     short loc_180021413
0x180021409  lea     ecx, [rax+1]
0x18002140c  lock cmpxchg [rdx+8], ecx
0x180021411  jz      short loc_18002141D
0x180021413  test    eax, eax
0x180021415  jz      loc_1800218C2
0x18002141b  jmp     short loc_180021409
0x18002141d  mov     rcx, [r14+8]
0x180021421  mov     [rbp+4Fh+Buffer], rcx
0x180021425  mov     rdi, [r14+10h]
0x180021429  mov     [rbp+4Fh+Buffer+8], rdi
0x18002142d  sub     r15d, r10d
0x180021430  sub     r8d, r9d
0x180021433  imul    r15d, r8d
0x180021437  add     [rbp+4Fh+arg_0], r15d
0x18002143b  mov     rdx, [rbp+4Fh+arg_8]
0x18002143f  mov     r8, [rdx+10h]
0x180021443  mov     rax, [rcx]
0x180021446  test    r8, r8
0x180021449  jz      short loc_180021451
0x18002144b  mov     rax, [rax+28h]
0x18002144f  jmp     short loc_180021458
0x180021451  mov     r8, rdx
0x180021454  mov     rax, [rax+30h]
0x180021458  mov     rdx, r12
0x18002145b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021460  mov     r15b, al
0x180021463  test    rdi, rdi
0x180021466  jz      short loc_1800214A3
0x180021468  or      r12d, 0FFFFFFFFh
0x18002146c  mov     eax, r12d
0x18002146f  lock xadd [rdi+8], eax
0x180021474  add     eax, r12d
0x180021477  jnz     short loc_1800214A3
0x180021479  mov     rax, [rdi]
0x18002147c  mov     rcx, rdi
0x18002147f  mov     rax, [rax]
0x180021482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021487  mov     eax, r12d
0x18002148a  lock xadd [rdi+0Ch], eax
0x18002148f  add     eax, r12d
0x180021492  jnz     short loc_1800214A3
0x180021494  mov     rax, [rdi]
0x180021497  mov     rcx, rdi
0x18002149a  mov     rax, [rax+8]
0x18002149e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214a3  test    r15b, r15b
0x1800214a6  jnz     loc_18002155D
0x1800214ac  mov     eax, cs:dword_1800C1058
0x1800214b2  cmp     eax, 2
0x1800214b5  jbe     loc_18002154F
0x1800214bb  mov     eax, [rbp+4Fh+arg_20]
0x1800214be  mov     [rbp+4Fh+var_B0], eax
0x1800214c1  mov     rax, [r14+30h]
0x1800214c5  mov     ecx, [rax+0C4h]
0x1800214cb  mov     dword ptr [rbp+4Fh+var_68], ecx
0x1800214ce  mov     eax, [r14+38h]
0x1800214d2  mov     dword ptr [rbp+4Fh+var_60], eax
0x1800214d5  lea     rax, aFailedToCopyMo; "Failed to copy move region"
0x1800214dc  mov     [rbp+4Fh+Buffer], rax
0x1800214e0  lea     rax, aRdpAvencUmrdpC_2; "Rdp::Avenc::Umrdp::CRdpSurface::UpdateF"...
0x1800214e7  mov     [rbp+4Fh+var_98], rax
0x1800214eb  mov     dword ptr [rbp+4Fh+var_A8], 9Eh
0x1800214f2  lea     rax, aOnecoreuapTerm_28; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800214f9  mov     [rbp+4Fh+var_A0], rax
0x1800214fd  lea     rax, [rbp+4Fh+var_B0]
0x180021501  mov     [rsp+50h], rax
0x180021506  lea     rax, [rbp+4Fh+var_68]
0x18002150a  mov     [rsp+110h+var_C8], rax
0x18002150f  lea     rax, [rbp+4Fh+var_60]
0x180021513  mov     [rsp+110h+var_D0], rax
0x180021518  lea     rax, [rbp+4Fh+Buffer]
0x18002151c  mov     [rsp+110h+var_D8], rax
0x180021521  lea     rax, [rbp+4Fh+var_98]
0x180021525  mov     [rsp+110h+var_E0], rax
0x18002152a  lea     rax, [rbp+4Fh+var_A8]
0x18002152e  mov     [rsp+110h+var_E8], rax
0x180021533  lea     rax, [rbp+4Fh+var_A0]
0x180021537  mov     [rsp+110h+var_F0], rax
0x18002153c  lea     rdx, byte_1800ADC1F
0x180021543  lea     rcx, dword_1800C1058
0x18002154a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002154f  mov     edx, 1; unsigned int
0x180021554  mov     rcx, [r14+30h]; this
0x180021558  call    ?ReportCriticalError@CUmrdpProcessor@Umrdp@Avenc@Rdp@@QEAAXIJ@Z; Rdp::Avenc::Umrdp::CUmrdpProcessor::ReportCriticalError(uint,long)
0x18002155d  add     rsi, 1Ch
0x180021561  cmp     rsi, r13
0x180021564  lea     rdi, aRdpAvencUmrdpC_2; "Rdp::Avenc::Umrdp::CRdpSurface::UpdateF"...
0x18002156b  jnz     loc_1800212FC
0x180021571  mov     r12, [rbp+4Fh+arg_18]
0x180021575  lea     rdi, aRdpAvencUmrdpC_2; "Rdp::Avenc::Umrdp::CRdpSurface::UpdateF"...
0x18002157c  mov     eax, cs:dword_1800C1058
0x180021582  cmp     eax, 5
0x180021585  jbe     loc_180021622
0x18002158b  lea     rcx, [rbp+4Fh+var_58]
0x18002158f  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x180021594  mov     rdx, [rbp+4Fh+var_50]
0x180021598  mov     rcx, [rbp+4Fh+var_58]; Buffer
0x18002159c  sub     rdx, rcx; BufferCount
0x18002159f  mov     rax, [r12+8]
0x1800215a4  mov     [rsp+110h+var_F0], rax
0x1800215a9  mov     r9d, [r14+38h]
0x1800215ad  lea     r8, aMonitorindexDC_0; "MonitorIndex %d, Copy %zu dirty rects"
0x1800215b4  call    snprintf
0x1800215b9  mov     eax, cs:dword_1800C1058
0x1800215bf  cmp     eax, 5
0x1800215c2  jbe     short loc_180021619
0x1800215c4  mov     rax, [rbp+4Fh+var_58]
0x1800215c8  mov     [rbp+4Fh+Buffer], rax
0x1800215cc  mov     [rbp+4Fh+var_98], rdi
0x1800215d0  mov     dword ptr [rbp+4Fh+var_A8], 0AEh
0x1800215d7  lea     rax, aOnecoreuapTerm_28; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800215de  mov     [rbp+4Fh+var_A0], rax
0x1800215e2  lea     rax, [rbp+4Fh+Buffer]
0x1800215e6  mov     [rsp+110h+var_D8], rax
0x1800215eb  lea     rax, [rbp+4Fh+var_98]
0x1800215ef  mov     [rsp+110h+var_E0], rax
0x1800215f4  lea     rax, [rbp+4Fh+var_A8]
0x1800215f8  mov     [rsp+110h+var_E8], rax
0x1800215fd  lea     rax, [rbp+4Fh+var_A0]
0x180021601  mov     [rsp+110h+var_F0], rax
0x180021606  lea     rdx, dword_1800ADBE4
0x18002160d  lea     rcx, dword_1800C1058
0x180021614  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180021619  lea     rcx, [rbp+4Fh+var_58]
0x18002161d  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180021622  mov     rdi, [r12]
0x180021626  mov     r15, [r12+8]
0x18002162b  shl     r15, 4
0x18002162f  add     r15, rdi
0x180021632  jmp     loc_180021885
0x180021637  mov     r13d, [rdi+0Ch]
0x18002163b  mov     r8d, [rdi+4]
0x18002163f  mov     dword ptr [rbp+4Fh+var_60], r8d
0x180021643  mov     r12d, [rdi+8]
0x180021647  mov     r9d, [rdi]
0x18002164a  mov     dword ptr [rbp+4Fh+var_68], r9d
0x18002164e  mov     eax, cs:dword_1800C1058
  ... truncated ...
```
