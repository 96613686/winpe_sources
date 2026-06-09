# Rdp::Avenc::Ic3::CVirtualFrame::GetBuffer(void)

- ea: `0x180059400`
- end: `0x18005996f`
- name: `?GetBuffer@CVirtualFrame@Ic3@Avenc@Rdp@@UEAA?AUBuffer@IVirtualFrame@@XZ`
- size: `1391`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180004e20`
- `0x1800058c8`
- `0x180006580`
- `0x180007018`
- `0x18000ec04`
- `0x1800203d4`
- `0x1800444f0`
- `0x18005418c`
- `0x180059400`
- `0x180059e7c`
- `0x180082e90`
- `0x180089010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059447`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005992a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059447`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005992a`

## string_xrefs

- `0x18005995d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180059668`: `Unable to create staging texture`
- `0x1800596da`: `Unable to map texture for reading`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void **__fastcall Rdp::Avenc::Ic3::CVirtualFrame::GetBuffer(__int64 a1, void **a2)
{
  void **v4; // rdi
  Rdp::Avenc::Ic3::CMonitorContext *v5; // r14
  unsigned __int64 v6; // rbx
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  void (__fastcall *v13)(__int64, __int64 *); // r14
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rbx
  unsigned int (__fastcall *v17)(__int64, _OWORD *, _QWORD, __int64 *); // r14
  __int64 v18; // rcx
  const char *v19; // rbx
  const char *v20; // rbx
  unsigned __int64 v21; // r14
  char *v22; // rdx
  unsigned __int64 v23; // rcx
  char *v24; // rbx
  char *v25; // r12
  int v26; // r9d
  const char *v27; // rcx
  int v28; // r8d
  int v29; // r9d
  unsigned int v30; // r14d
  int v31; // ebx
  int v33; // [rsp+20h] [rbp-B9h]
  char *v34; // [rsp+28h] [rbp-B1h]
  char *v35; // [rsp+28h] [rbp-B1h]
  char v36[4]; // [rsp+50h] [rbp-89h] BYREF
  __int64 v37; // [rsp+58h] [rbp-81h] BYREF
  __int64 v38; // [rsp+60h] [rbp-79h] BYREF
  __int64 v39; // [rsp+68h] [rbp-71h] BYREF
  const char *v40; // [rsp+70h] [rbp-69h] BYREF
  int v41; // [rsp+78h] [rbp-61h] BYREF
  const char *v42; // [rsp+80h] [rbp-59h] BYREF
  const char *v43; // [rsp+88h] [rbp-51h] BYREF
  const char *v44; // [rsp+90h] [rbp-49h] BYREF
  int v45[2]; // [rsp+98h] [rbp-41h] BYREF
  void *Src[2]; // [rsp+A0h] [rbp-39h] BYREF
  GUID ActivityId; // [rsp+B0h] [rbp-29h] BYREF
  _OWORD v48[3]; // [rsp+C0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  ActivityId = *(GUID *)&xmmword_1800C21A0;
  EventActivityIdControl(4u, &ActivityId);
  v4 = (void **)(a1 + 88);
  if ( *(_QWORD *)(a1 + 88) != *(_QWORD *)(a1 + 96) )
    goto LABEL_36;
  v5 = *(Rdp::Avenc::Ic3::CMonitorContext **)(a1 + 144);
  if ( v5 )
  {
    v6 = *(_QWORD *)(a1 + 192);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a1 + 16) + 200LL))(**(_QWORD **)(a1 + 16));
    Rdp::Avenc::Ic3::CMonitorContext::OnFirstGraphicsFrame(v5, *(_QWORD *)(a1 + 80) + v7, v6);
  }
  Rdp::Avenc::Ic3::CVirtualFrame::WaitForFenceReached((Rdp::Avenc::Ic3::CVirtualFrame *)a1);
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v41 = *(_DWORD *)(a1 + 56);
    v42 = (const char *)(*(_QWORD *)(a1 + 80)
                       + (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a1 + 16) + 200LL))(**(_QWORD **)(a1 + 16)));
    v43 = "BufferGet";
    v44 = "Rdp::Avenc::Ic3::CVirtualFrame::GetBuffer";
    *(_DWORD *)v36 = 299;
    *(_QWORD *)v45 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\virtualframe.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)word_1800B3AFA,
      v8,
      v9,
      (__int64)v45,
      (__int64)v36,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v41);
  }
  v39 = 0;
  v38 = 0;
  v37 = 0;
  *(_OWORD *)Src = 0;
  v10 = *(__int64 **)(a1 + 32);
  v11 = *v10;
  v39 = 0;
  (*(void (__fastcall **)(__int64 *, __int64 *))(v11 + 24))(v10, &v39);
  v12 = v39;
  v13 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 320LL);
  v14 = v38;
  v38 = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v13(v12, &v38);
  v40 = 0;
  v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, const char **))v39)(
          v39,
          &GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0,
          &v40);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v15,
      v33);
  if ( v40 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v40 + 24LL))(v40);
  memset(v48, 0, 44);
  (*(void (__fastcall **)(_QWORD, _OWORD *))(**(_QWORD **)(a1 + 32) + 80LL))(*(_QWORD *)(a1 + 32), v48);
  *(_QWORD *)((char *)&v48[1] + 12) = 3;
  *(_QWORD *)((char *)&v48[2] + 4) = 0x20000;
  v16 = v39;
  v17 = *(unsigned int (__fastcall **)(__int64, _OWORD *, _QWORD, __int64 *))(*(_QWORD *)v39 + 40LL);
  v18 = v37;
  v37 = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = (const char *)v17(v16, v48, 0, &v37);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x144,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\virtualframe.cpp",
    v19,
    (int)"Unable to create staging texture",
    v34);
  if ( (int)v19 >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 376LL))(v38, v37, *(_QWORD *)(a1 + 32));
    v20 = (const char *)(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, void **))(*(_QWORD *)v38 + 112LL))(
                          v38,
                          v37,
                          0,
                          1,
                          0,
                          Src);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\virtualframe.cpp",
      v20,
      (int)"Unable to map texture for reading",
      v35);
    if ( (int)v20 >= 0 )
    {
      v21 = (*(_DWORD *)(a1 + 128) * *(unsigned __int16 *)(a1 + 116) * (unsigned int)*(unsigned __int16 *)(a1 + 118)) >> 3;
      v22 = (char *)*v4;
      v23 = *(_QWORD *)(a1 + 96) - *(_QWORD *)(a1 + 88);
      if ( v21 >= v23 )
      {
        if ( v21 <= v23 )
        {
          v24 = *(char **)(a1 + 96);
          goto LABEL_23;
        }
        if ( v21 > *(_QWORD *)(a1 + 104) - (_QWORD)v22 )
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a1 + 88, v21);
          v24 = *(char **)(a1 + 96);
          goto LABEL_23;
        }
        v24 = (char *)(v21 - v23 + *(_QWORD *)(a1 + 96));
        memset_0(*(void **)(a1 + 96), 0, v21 - v23);
      }
      else
      {
        v24 = &v22[v21];
      }
      *(_QWORD *)(a1 + 96) = v24;
LABEL_23:
      v25 = (char *)Src[0];
      v26 = (int)Src[1];
      if ( *(_DWORD *)(a1 + 124) == LODWORD(Src[1]) )
      {
        memcpy_0(*v4, Src[0], v24 - (_BYTE *)*v4);
      }
      else
      {
        v30 = (unsigned int)v21 / *(_DWORD *)(a1 + 124);
        v31 = 0;
        if ( v30 )
        {
          while ( 1 )
          {
            memcpy_0((char *)*v4 + (unsigned int)(v31 * *(_DWORD *)(a1 + 124)), &v25[v26 * v31], *(int *)(a1 + 124));
            if ( ++v31 >= v30 )
              break;
            v26 = (int)Src[1];
          }
        }
      }
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 120LL))(v38, v37, 0);
    }
  }
  v27 = v40;
  if ( v40 )
  {
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v40 + 32LL))(v40);
    v27 = v40;
  }
  if ( v27 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
LABEL_36:
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    *(_QWORD *)v45 = *(_QWORD *)(a1 + 96) - (_QWORD)*v4;
    v44 = (const char *)(*(_QWORD *)(a1 + 80)
                       + (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a1 + 16) + 200LL))(**(_QWORD **)(a1 + 16)));
    v43 = "Provide CPU buffer";
    v42 = "Rdp::Avenc::Ic3::CVirtualFrame::GetBuffer";
    *(_DWORD *)v36 = 365;
    v40 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\virtualframe.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)word_1800B3A9A,
      v28,
      v29,
      (__int64)&v40,
      (__int64)v36,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v44,
      (__int64)v45);
  }
  if ( *(_QWORD *)(a1 + 88) == *(_QWORD *)(a1 + 96) )
  {
    *a2 = 0;
    a2[1] = 0;
  }
  else
  {
    *a2 = *v4;
    a2[1] = (void *)(*(_QWORD *)(a1 + 96) - (_QWORD)*v4);
  }
  EventActivityIdControl(2u, &ActivityId);
  return a2;
}

```

## disassembly

```asm
0x180059400  mov     [rsp-8+arg_10], rbx
0x180059405  push    rbp
0x180059406  push    rsi
0x180059407  push    rdi
0x180059408  push    r12
0x18005940a  push    r13
0x18005940c  push    r14
0x18005940e  push    r15
0x180059410  lea     rbp, [rsp-27h]
0x180059415  sub     rsp, 100h
0x18005941c  mov     rax, cs:__security_cookie
0x180059423  xor     rax, rsp
0x180059426  mov     [rbp+57h+var_40], rax
0x18005942a  mov     r15, rdx
0x18005942d  mov     rsi, rcx
0x180059430  xor     r13d, r13d
0x180059433  movups  xmm0, cs:xmmword_1800C21A0
0x18005943a  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18005943f  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180059443  lea     ecx, [r13+4]; ControlCode
0x180059447  call    cs:__imp_EventActivityIdControl
0x18005944d  nop
0x18005944e  lea     rdi, [rsi+58h]
0x180059452  mov     rax, [rdi+8]
0x180059456  lea     rbx, aRdpAvencIc3Cvi_2; "Rdp::Avenc::Ic3::CVirtualFrame::GetBuff"...
0x18005945d  lea     r12, aOnecoreuapTerm_20; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180059464  cmp     [rdi], rax
0x180059467  jnz     loc_180059822
0x18005946d  mov     r14, [rsi+90h]
0x180059474  test    r14, r14
0x180059477  jz      short loc_1800594AF
0x180059479  mov     rbx, [rsi+0C0h]
0x180059480  mov     rax, [rsi+10h]
0x180059484  mov     rcx, [rax]
0x180059487  mov     rax, [rcx]
0x18005948a  mov     rax, [rax+0C8h]
0x180059491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059496  mov     rdx, rax
0x180059499  add     rdx, [rsi+50h]; unsigned __int64
0x18005949d  mov     r8, rbx; unsigned __int64
0x1800594a0  mov     rcx, r14; this
0x1800594a3  call    ?OnFirstGraphicsFrame@CMonitorContext@Ic3@Avenc@Rdp@@QEAAX_K0@Z; Rdp::Avenc::Ic3::CMonitorContext::OnFirstGraphicsFrame(unsigned __int64,unsigned __int64)
0x1800594a8  lea     rbx, aRdpAvencIc3Cvi_2; "Rdp::Avenc::Ic3::CVirtualFrame::GetBuff"...
0x1800594af  mov     rcx, rsi; this
0x1800594b2  call    ?WaitForFenceReached@CVirtualFrame@Ic3@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::Ic3::CVirtualFrame::WaitForFenceReached(void)
0x1800594b7  mov     eax, cs:dword_1800C1058
0x1800594bd  cmp     eax, 5
0x1800594c0  jbe     loc_18005954F
0x1800594c6  mov     eax, [rsi+38h]
0x1800594c9  mov     [rbp+57h+var_B8], eax
0x1800594cc  mov     rax, [rsi+10h]
0x1800594d0  mov     rcx, [rax]
0x1800594d3  mov     rax, [rcx]
0x1800594d6  mov     rax, [rax+0C8h]
0x1800594dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594e2  add     rax, [rsi+50h]
0x1800594e6  mov     [rbp+57h+var_B0], rax
0x1800594ea  lea     rax, aBufferget; "BufferGet"
0x1800594f1  mov     [rbp+57h+var_A8], rax
0x1800594f5  mov     [rbp+57h+var_A0], rbx
0x1800594f9  mov     dword ptr [rsp+130h+var_E0], 12Bh
0x180059501  mov     qword ptr [rbp+57h+var_98], r12
0x180059505  lea     rax, [rbp+57h+var_B8]
0x180059509  mov     [rsp+130h+var_E8], rax
0x18005950e  lea     rax, [rbp+57h+var_B0]
0x180059512  mov     [rsp+130h+var_F0], rax
0x180059517  lea     rax, [rbp+57h+var_A8]
0x18005951b  mov     [rsp+130h+var_F8], rax
0x180059520  lea     rax, [rbp+57h+var_A0]
0x180059524  mov     [rsp+130h+var_100], rax
0x180059529  lea     rax, [rsp+130h+var_E0]
0x18005952e  mov     [rsp+130h+var_108], rax; char *
0x180059533  lea     rax, [rbp+57h+var_98]
0x180059537  mov     qword ptr [rsp+130h+var_110], rax; int
0x18005953c  lea     rdx, word_1800B3AFA
0x180059543  lea     rcx, dword_1800C1058
0x18005954a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18005954f  mov     [rbp+57h+var_C8], r13
0x180059553  mov     [rbp+57h+var_D0], r13
0x180059557  mov     [rsp+130h+var_D8], r13
0x18005955c  xorps   xmm0, xmm0
0x18005955f  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180059563  mov     rcx, [rsi+20h]
0x180059567  mov     rax, [rcx]
0x18005956a  mov     [rbp+57h+var_C8], r13
0x18005956e  lea     rdx, [rbp+57h+var_C8]
0x180059572  mov     rax, [rax+18h]
0x180059576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005957b  mov     rbx, [rbp+57h+var_C8]
0x18005957f  mov     rax, [rbx]
0x180059582  mov     r14, [rax+140h]
0x180059589  mov     rcx, [rbp+57h+var_D0]
0x18005958d  mov     [rbp+57h+var_D0], r13
0x180059591  test    rcx, rcx
0x180059594  jz      short loc_1800595A3
0x180059596  mov     rax, [rcx]
0x180059599  mov     rax, [rax+10h]
0x18005959d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595a2  nop
0x1800595a3  lea     rdx, [rbp+57h+var_D0]
0x1800595a7  mov     rcx, rbx
0x1800595aa  mov     rax, r14
0x1800595ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595b2  mov     rcx, [rbp+57h+var_C8]
0x1800595b6  mov     [rbp+57h+var_C0], r13
0x1800595ba  mov     rax, [rcx]
0x1800595bd  lea     r8, [rbp+57h+var_C0]
0x1800595c1  lea     rdx, _GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0
0x1800595c8  mov     rax, [rax]
0x1800595cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595d0  mov     rcx, [rbp+5Fh]; this
0x1800595d4  test    eax, eax
0x1800595d6  js      loc_18005995A
0x1800595dc  mov     rcx, [rbp+57h+var_C0]
0x1800595e0  test    rcx, rcx
0x1800595e3  jz      short loc_1800595F1
0x1800595e5  mov     rax, [rcx]
0x1800595e8  mov     rax, [rax+18h]
0x1800595ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595f1  xorps   xmm0, xmm0
0x1800595f4  movups  [rbp+57h+var_70], xmm0
0x1800595f8  movups  [rbp+57h+var_60], xmm0
0x1800595fc  movups  [rbp+57h+var_60+0Ch], xmm0
0x180059600  mov     rcx, [rsi+20h]
0x180059604  mov     rax, [rcx]
0x180059607  lea     rdx, [rbp+57h+var_70]
0x18005960b  mov     rax, [rax+50h]
0x18005960f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059614  mov     qword ptr [rbp+57h+var_60+0Ch], 3
0x18005961c  mov     [rbp+57h+var_4C], 20000h
0x180059624  mov     rbx, [rbp+57h+var_C8]
0x180059628  mov     rax, [rbx]
0x18005962b  mov     r14, [rax+28h]
0x18005962f  mov     rcx, [rsp+130h+var_D8]
0x180059634  mov     [rsp+130h+var_D8], r13
0x180059639  test    rcx, rcx
0x18005963c  jz      short loc_18005964B
0x18005963e  mov     rax, [rcx]
0x180059641  mov     rax, [rax+10h]
0x180059645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005964a  nop
0x18005964b  lea     r9, [rsp+130h+var_D8]
0x180059650  xor     r8d, r8d
0x180059653  lea     rdx, [rbp+57h+var_70]
0x180059657  mov     rcx, rbx
0x18005965a  mov     rax, r14
0x18005965d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059662  mov     ebx, eax
0x180059664  mov     rcx, [rbp+5Fh]; this
0x180059668  lea     rax, aUnableToCreate; "Unable to create staging texture"
0x18005966f  mov     qword ptr [rsp+130h+var_110], rax; int
0x180059674  mov     r9d, ebx; char *
0x180059677  mov     r8, r12; unsigned int
0x18005967a  mov     edx, 144h; void *
0x18005967f  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180059684  test    ebx, ebx
0x180059686  js      loc_1800597AD
0x18005968c  mov     rcx, [rbp+57h+var_D0]
0x180059690  mov     rax, [rcx]
0x180059693  mov     r8, [rsi+20h]
0x180059697  mov     rdx, [rsp+130h+var_D8]
0x18005969c  mov     rax, [rax+178h]
0x1800596a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596a8  mov     rcx, [rbp+57h+var_D0]
0x1800596ac  mov     rax, [rcx]
0x1800596af  lea     rdx, [rbp+57h+Src]
0x1800596b3  mov     [rsp+130h+var_108], rdx; char *
0x1800596b8  mov     [rsp+130h+var_110], r13d
0x1800596bd  mov     r9d, 1
0x1800596c3  xor     r8d, r8d
0x1800596c6  mov     rdx, [rsp+130h+var_D8]
0x1800596cb  mov     rax, [rax+70h]
0x1800596cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596d4  mov     ebx, eax
0x1800596d6  mov     rcx, [rbp+5Fh]; this
0x1800596da  lea     rax, aUnableToMapTex; "Unable to map texture for reading"
0x1800596e1  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800596e6  mov     r9d, ebx; char *
0x1800596e9  mov     r8, r12; unsigned int
0x1800596ec  mov     edx, 14Bh; void *
0x1800596f1  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800596f6  test    ebx, ebx
0x1800596f8  js      loc_1800597AD
0x1800596fe  movzx   r14d, word ptr [rsi+76h]
0x180059703  movzx   eax, word ptr [rsi+74h]
0x180059707  imul    r14d, eax
0x18005970b  imul    r14d, [rsi+80h]
0x180059713  shr     r14d, 3
0x180059717  mov     rdx, [rdi]
0x18005971a  mov     r9, [rdi+8]
0x18005971e  mov     rcx, r9
0x180059721  sub     rcx, rdx
0x180059724  cmp     r14, rcx
0x180059727  jnb     short loc_180059733
0x180059729  lea     rbx, [rdx+r14]
0x18005972d  mov     [rdi+8], rbx
0x180059731  jmp     short loc_18005976B
0x180059733  jbe     short loc_180059768
0x180059735  mov     rax, [rdi+10h]
0x180059739  sub     rax, rdx
0x18005973c  cmp     r14, rax
0x18005973f  jbe     short loc_180059752
0x180059741  mov     rdx, r14
0x180059744  mov     rcx, rdi
0x180059747  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005974c  mov     rbx, [rdi+8]
0x180059750  jmp     short loc_18005976B
0x180059752  mov     r8, r14
0x180059755  sub     r8, rcx; Size
0x180059758  lea     rbx, [r8+r9]
0x18005975c  xor     edx, edx; Val
0x18005975e  mov     rcx, r9; void *
0x180059761  call    memset_0
0x180059766  jmp     short loc_18005972D
0x180059768  mov     rbx, r9
0x18005976b  mov     r12, [rbp+57h+Src]
0x18005976f  mov     r9d, dword ptr [rbp+57h+Src+8]
0x180059773  cmp     [rsi+7Ch], r9d
0x180059777  jnz     loc_1800598D1
0x18005977d  sub     rbx, [rdi]
0x180059780  mov     r8, rbx; Size
0x180059783  mov     rdx, r12; Src
0x180059786  mov     rcx, [rdi]; void *
0x180059789  call    memcpy_0
0x18005978e  mov     rcx, [rbp+57h+var_D0]
0x180059792  mov     rax, [rcx]
0x180059795  xor     r8d, r8d
0x180059798  mov     rdx, [rsp+130h+var_D8]
0x18005979d  mov     rax, [rax+78h]
0x1800597a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597a6  lea     r12, aOnecoreuapTerm_20; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800597ad  mov     rcx, [rbp+57h+var_C0]
0x1800597b1  test    rcx, rcx
0x1800597b4  jz      short loc_1800597C6
0x1800597b6  mov     rax, [rcx]
0x1800597b9  mov     rax, [rax+20h]
0x1800597bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597c2  mov     rcx, [rbp+57h+var_C0]
0x1800597c6  test    rcx, rcx
0x1800597c9  jz      short loc_1800597D8
0x1800597cb  mov     rax, [rcx]
0x1800597ce  mov     rax, [rax+10h]
0x1800597d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597d7  nop
0x1800597d8  mov     rcx, [rsp+130h+var_D8]
0x1800597dd  test    rcx, rcx
0x1800597e0  jz      short loc_1800597EF
0x1800597e2  mov     rax, [rcx]
0x1800597e5  mov     rax, [rax+10h]
0x1800597e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597ee  nop
0x1800597ef  mov     rcx, [rbp+57h+var_D0]
0x1800597f3  test    rcx, rcx
0x1800597f6  jz      short loc_180059805
0x1800597f8  mov     rax, [rcx]
0x1800597fb  mov     rax, [rax+10h]
0x1800597ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059804  nop
0x180059805  mov     rcx, [rbp+57h+var_C8]
0x180059809  test    rcx, rcx
0x18005980c  jz      short loc_18005981B
0x18005980e  mov     rax, [rcx]
0x180059811  mov     rax, [rax+10h]
0x180059815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005981a  nop
0x18005981b  lea     rbx, aRdpAvencIc3Cvi_2; "Rdp::Avenc::Ic3::CVirtualFrame::GetBuff"...
0x180059822  mov     eax, cs:dword_1800C1058
0x180059828  cmp     eax, 5
0x18005982b  jbe     loc_1800598BF
0x180059831  mov     rax, [rdi+8]
0x180059835  sub     rax, [rdi]
0x180059838  mov     qword ptr [rbp+57h+var_98], rax
0x18005983c  mov     rax, [rsi+10h]
0x180059840  mov     rcx, [rax]
0x180059843  mov     rax, [rcx]
0x180059846  mov     rax, [rax+0C8h]
0x18005984d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059852  add     rax, [rsi+50h]
0x180059856  mov     [rbp+57h+var_A0], rax
0x18005985a  lea     rax, aProvideCpuBuff; "Provide CPU buffer"
0x180059861  mov     [rbp+57h+var_A8], rax
0x180059865  mov     [rbp+57h+var_B0], rbx
0x180059869  mov     dword ptr [rsp+130h+var_E0], 16Dh
0x180059871  mov     [rbp+57h+var_C0], r12
0x180059875  lea     rax, [rbp+57h+var_98]
0x180059879  mov     [rsp+130h+var_E8], rax
0x18005987e  lea     rax, [rbp+57h+var_A0]
0x180059882  mov     [rsp+130h+var_F0], rax
0x180059887  lea     rax, [rbp+57h+var_A8]
0x18005988b  mov     [rsp+130h+var_F8], rax
0x180059890  lea     rax, [rbp+57h+var_B0]
0x180059894  mov     [rsp+130h+var_100], rax
0x180059899  lea     rax, [rsp+130h+var_E0]
0x18005989e  mov     [rsp+130h+var_108], rax
0x1800598a3  lea     rax, [rbp+57h+var_C0]
0x1800598a7  mov     qword ptr [rsp+130h+var_110], rax
0x1800598ac  lea     rdx, word_1800B3A9A
0x1800598b3  lea     rcx, dword_1800C1058
0x1800598ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800598bf  mov     rax, [rdi]
  ... truncated ...
```
