# RdpRemoteAppGfxRedirectionHandler::OnGfxStartOfFrame(HDC__ *,uint,__int64,_RDSDWMDR_DRIVER_IO_PROBE_MODE_ENUM)

- ea: `0x1800154f0`
- end: `0x1800157b6`
- name: `?OnGfxStartOfFrame@RdpRemoteAppGfxRedirectionHandler@@UEAAJPEAUHDC__@@I_JW4_RDSDWMDR_DRIVER_IO_PROBE_MODE_ENUM@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x1800010f8`
- `0x180001724`
- `0x180013850`
- `0x1800154f0`
- `0x180017350`
- `0x1800196a4`

## string_xrefs

- `0x180015558`: `Channel not initialized. Dropping PRDPXREMOTEAPPGFXREDIRECTION_CREATE_SURFACE_PDU`
- `0x1800155ff`: `WaitForUpdateAck failed`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::OnGfxStartOfFrame(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdx
  int updated; // edi
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  char *v10; // rdx
  const unsigned __int16 **v11; // rax
  __int64 v12; // rdx
  __int64 CurrentMsTime; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // r8
  __int64 v17; // r9
  float v18; // xmm1_4
  __int64 v19; // rax
  float v20; // xmm1_4
  float v21; // xmm0_4
  __int64 v22; // r8
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  __int64 v25; // rdx
  const char **v27; // [rsp+30h] [rbp-50h]
  const char **v28; // [rsp+40h] [rbp-40h]
  const unsigned __int16 **v29; // [rsp+48h] [rbp-38h]
  int v30; // [rsp+50h] [rbp-30h] BYREF
  const char *v31; // [rsp+58h] [rbp-28h] BYREF
  const char *v32; // [rsp+60h] [rbp-20h] BYREF
  const char *v33; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v34[2]; // [rsp+70h] [rbp-10h] BYREF
  const char *v35; // [rsp+A0h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180044008 > 5 )
  {
    v35 = "OnGfxStartOfFrame";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      a1,
      (__int64)byte_18003CD39,
      a3,
      a4,
      (const unsigned __int16 **)&v35);
  }
  updated = RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized((RdpRemoteAppGfxRedirectionHandler *)(a1 - 48));
  if ( updated >= 0 )
  {
    *(_QWORD *)(a1 + 160) = RDSDWMDirectTraceLogging::GetCurrentMsTime(*(RDSDWMDirectTraceLogging **)(a1 + 144), v5);
    updated = RdpRemoteAppGfxRedirectionHandler::WaitForUpdateAck((RdpRemoteAppGfxRedirectionHandler *)(a1 - 48));
    if ( updated < 0 )
    {
      if ( (unsigned int)dword_180044008 <= 2 )
        return (unsigned int)updated;
      v33 = "OnGfxStartOfFrame";
      v34[0] = "WaitForUpdateAck failed";
      v10 = byte_18003CC75;
      LODWORD(v35) = 742;
      v32 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v31 = "Error HResult failed";
      v29 = (const unsigned __int16 **)v34;
      v28 = &v33;
      v27 = &v32;
      v11 = (const unsigned __int16 **)&v31;
      goto LABEL_6;
    }
    CurrentMsTime = RDSDWMDirectTraceLogging::GetCurrentMsTime(*(RDSDWMDirectTraceLogging **)(a1 + 144), v12);
    v14 = *(_QWORD *)(a1 + 176);
    v15 = *(_QWORD *)(a1 + 160);
    v16 = CurrentMsTime - v15;
    v17 = v14 + 1;
    if ( v14 < 0 )
    {
      v19 = *(_QWORD *)(a1 + 176) & 1LL | (*(_QWORD *)(a1 + 176) >> 1);
      v18 = (float)(int)v19 + (float)(int)v19;
    }
    else
    {
      v18 = (float)(int)v14;
    }
    v20 = (float)(v18 * *(float *)(a1 + 224)) + (float)(int)v16;
    if ( v17 < 0 )
      v21 = (float)(v17 & 1 | (unsigned int)((unsigned __int64)v17 >> 1))
          + (float)(v17 & 1 | (unsigned int)((unsigned __int64)v17 >> 1));
    else
      v21 = (float)(int)v17;
    *(float *)(a1 + 224) = v20 / v21;
    if ( v16 > *(_QWORD *)(a1 + 232) )
      *(_QWORD *)(a1 + 232) = v16;
    v22 = *(_QWORD *)(a1 + 168);
    if ( !v22 )
    {
      *(_QWORD *)(a1 + 168) = v15;
      v22 = v15;
    }
    v23 = *(_QWORD *)(a1 + 184);
    if ( v15 - v22 >= 1000 )
    {
      if ( v23 <= 0x14 )
      {
        if ( v23 <= 0xA )
          ++*(_QWORD *)(a1 + 216);
        else
          ++*(_QWORD *)(a1 + 208);
      }
      else
      {
        ++*(_QWORD *)(a1 + 200);
      }
      *(_QWORD *)(a1 + 168) = v15;
      v24 = 0;
    }
    else
    {
      v24 = v23 + 1;
    }
    v25 = (unsigned __int128)((v15 - *(_QWORD *)(a1 + 152)) * (__int128)0x20C49BA5E353F7CFLL) >> 64;
    *(_QWORD *)(a1 + 184) = v24;
    *(_QWORD *)(a1 + 176) = v17;
    *(_QWORD *)(a1 + 192) = ((unsigned __int64)v25 >> 63) + (v25 >> 7);
  }
  else
  {
    v9 = (unsigned int)dword_180044008;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v32 = "OnGfxStartOfFrame";
      v31 = "Channel not initialized. Dropping PRDPXREMOTEAPPGFXREDIRECTION_CREATE_SURFACE_PDU";
      v10 = &byte_18003CCD7;
      LODWORD(v35) = 734;
      v33 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v34[0] = "Error HResult failed";
      v29 = (const unsigned __int16 **)&v31;
      v28 = &v32;
      v27 = &v33;
      v11 = (const unsigned __int16 **)v34;
LABEL_6:
      v30 = updated;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (__int64)v10,
        v7,
        v8,
        v11,
        (__int64)&v30,
        (const unsigned __int16 **)v27,
        (__int64)&v35,
        (const unsigned __int16 **)v28,
        v29);
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800154f0  mov     [rsp-18h+arg_8], rbx
0x1800154f5  mov     [rsp-18h+arg_10], rsi
0x1800154fa  push    rbp
0x1800154fb  push    rdi
0x1800154fc  push    r14
0x1800154fe  mov     rbp, rsp
0x180015501  sub     rsp, 80h
0x180015508  mov     eax, cs:dword_180044008
0x18001550e  lea     r14, aOngfxstartoffr; "OnGfxStartOfFrame"
0x180015515  mov     rbx, rcx
0x180015518  cmp     eax, 5
0x18001551b  jbe     short loc_180015536
0x18001551d  lea     rax, [rbp+arg_0]
0x180015521  mov     [rbp+arg_0], r14
0x180015525  lea     rdx, byte_18003CD39
0x18001552c  mov     [rsp+80h+var_60], rax
0x180015531  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180015536  lea     rcx, [rbx-30h]; this
0x18001553a  call    ?EnsureChannelInitialized@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ; RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(void)
0x18001553f  mov     edi, eax
0x180015541  test    eax, eax
0x180015543  jns     loc_1800155CE
0x180015549  mov     ecx, cs:dword_180044008
0x18001554f  cmp     ecx, 2
0x180015552  jbe     loc_18001579C
0x180015558  lea     rax, aChannelNotInit_5; "Channel not initialized. Dropping PRDPX"...
0x18001555f  mov     [rbp+var_20], r14
0x180015563  mov     [rbp+var_28], rax
0x180015567  lea     rdx, byte_18003CCD7
0x18001556e  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015575  mov     dword ptr [rbp+arg_0], 2DEh
0x18001557c  mov     [rbp+var_18], rax
0x180015580  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180015587  mov     [rbp+var_10], rax
0x18001558b  lea     rax, [rbp+var_28]
0x18001558f  mov     [rsp+80h+var_38], rax
0x180015594  lea     rax, [rbp+var_20]
0x180015598  mov     [rsp+80h+var_40], rax
0x18001559d  lea     rax, [rbp+arg_0]
0x1800155a1  mov     [rsp+80h+var_48], rax
0x1800155a6  lea     rax, [rbp+var_18]
0x1800155aa  mov     [rsp+80h+var_50], rax
0x1800155af  lea     rax, [rbp+var_30]
0x1800155b3  mov     [rsp+80h+var_58], rax
0x1800155b8  lea     rax, [rbp+var_10]
0x1800155bc  mov     [rsp+80h+var_60], rax
0x1800155c1  mov     [rbp+var_30], edi
0x1800155c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800155c9  jmp     loc_18001579C
0x1800155ce  mov     rcx, [rbx+90h]; this
0x1800155d5  call    ?GetCurrentMsTime@RDSDWMDirectTraceLogging@@YA_J_J@Z; RDSDWMDirectTraceLogging::GetCurrentMsTime(__int64)
0x1800155da  lea     rcx, [rbx-30h]; this
0x1800155de  mov     [rbx+0A0h], rax
0x1800155e5  call    ?WaitForUpdateAck@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ; RdpRemoteAppGfxRedirectionHandler::WaitForUpdateAck(void)
0x1800155ea  mov     edi, eax
0x1800155ec  test    eax, eax
0x1800155ee  jns     short loc_180015668
0x1800155f0  mov     eax, cs:dword_180044008
0x1800155f6  cmp     eax, 2
0x1800155f9  jbe     loc_18001579C
0x1800155ff  lea     rax, aWaitforupdatea; "WaitForUpdateAck failed"
0x180015606  mov     [rbp+var_18], r14
0x18001560a  mov     [rbp+var_10], rax
0x18001560e  lea     rdx, byte_18003CC75
0x180015615  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001561c  mov     dword ptr [rbp+arg_0], 2E6h
0x180015623  mov     [rbp+var_20], rax
0x180015627  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001562e  mov     [rbp+var_28], rax
0x180015632  lea     rax, [rbp+var_10]
0x180015636  mov     [rsp+80h+var_38], rax
0x18001563b  lea     rax, [rbp+var_18]
0x18001563f  mov     [rsp+80h+var_40], rax
0x180015644  lea     rax, [rbp+arg_0]
0x180015648  mov     [rsp+80h+var_48], rax
0x18001564d  lea     rax, [rbp+var_20]
0x180015651  mov     [rsp+80h+var_50], rax
0x180015656  lea     rax, [rbp+var_30]
0x18001565a  mov     [rsp+80h+var_58], rax
0x18001565f  lea     rax, [rbp+var_28]
0x180015663  jmp     loc_1800155BC
0x180015668  mov     rcx, [rbx+90h]; this
0x18001566f  call    ?GetCurrentMsTime@RDSDWMDirectTraceLogging@@YA_J_J@Z; RDSDWMDirectTraceLogging::GetCurrentMsTime(__int64)
0x180015674  mov     rcx, [rbx+0B0h]
0x18001567b  mov     r8, rax
0x18001567e  mov     rdx, [rbx+0A0h]
0x180015685  xorps   xmm1, xmm1
0x180015688  sub     r8, rdx
0x18001568b  lea     r9, [rcx+1]
0x18001568f  test    rcx, rcx
0x180015692  js      short loc_18001569B
0x180015694  cvtsi2ss xmm1, rcx
0x180015699  jmp     short loc_1800156B0
0x18001569b  mov     rax, rcx
0x18001569e  and     ecx, 1
0x1800156a1  shr     rax, 1
0x1800156a4  or      rax, rcx
0x1800156a7  cvtsi2ss xmm1, rax
0x1800156ac  addss   xmm1, xmm1
0x1800156b0  mulss   xmm1, dword ptr [rbx+0E0h]
0x1800156b8  xorps   xmm0, xmm0
0x1800156bb  cvtsi2ss xmm0, r8
0x1800156c0  addss   xmm1, xmm0
0x1800156c4  xorps   xmm0, xmm0
0x1800156c7  test    r9, r9
0x1800156ca  js      short loc_1800156D3
0x1800156cc  cvtsi2ss xmm0, r9
0x1800156d1  jmp     short loc_1800156EB
0x1800156d3  mov     rax, r9
0x1800156d6  mov     rcx, r9
0x1800156d9  shr     rcx, 1
0x1800156dc  and     eax, 1
0x1800156df  or      rcx, rax
0x1800156e2  cvtsi2ss xmm0, rcx
0x1800156e7  addss   xmm0, xmm0
0x1800156eb  divss   xmm1, xmm0
0x1800156ef  movss   dword ptr [rbx+0E0h], xmm1
0x1800156f7  cmp     r8, [rbx+0E8h]
0x1800156fe  jbe     short loc_180015707
0x180015700  mov     [rbx+0E8h], r8
0x180015707  mov     r8, [rbx+0A8h]
0x18001570e  test    r8, r8
0x180015711  jnz     short loc_18001571D
0x180015713  mov     [rbx+0A8h], rdx
0x18001571a  mov     r8, rdx
0x18001571d  mov     rcx, [rbx+0B8h]
0x180015724  mov     rax, rdx
0x180015727  sub     rax, r8
0x18001572a  cmp     rax, 3E8h
0x180015730  jge     short loc_180015737
0x180015732  inc     rcx
0x180015735  jmp     short loc_180015765
0x180015737  cmp     rcx, 14h
0x18001573b  jbe     short loc_180015746
0x18001573d  inc     qword ptr [rbx+0C8h]
0x180015744  jmp     short loc_18001575C
0x180015746  cmp     rcx, 0Ah
0x18001574a  jbe     short loc_180015755
0x18001574c  inc     qword ptr [rbx+0D0h]
0x180015753  jmp     short loc_18001575C
0x180015755  inc     qword ptr [rbx+0D8h]
0x18001575c  mov     [rbx+0A8h], rdx
0x180015763  xor     ecx, ecx
0x180015765  sub     rdx, [rbx+98h]
0x18001576c  mov     rax, 20C49BA5E353F7CFh
0x180015776  imul    rdx
0x180015779  mov     [rbx+0B8h], rcx
0x180015780  sar     rdx, 7
0x180015784  mov     rax, rdx
0x180015787  mov     [rbx+0B0h], r9
0x18001578e  shr     rax, 3Fh
0x180015792  add     rdx, rax
0x180015795  mov     [rbx+0C0h], rdx
0x18001579c  lea     r11, [rsp+80h+var_s0]
0x1800157a4  mov     eax, edi
0x1800157a6  mov     rbx, [r11+28h]
0x1800157aa  mov     rsi, [r11+30h]
0x1800157ae  mov     rsp, r11
0x1800157b1  pop     r14
0x1800157b3  pop     rdi
0x1800157b4  pop     rbp
0x1800157b5  retn
```
