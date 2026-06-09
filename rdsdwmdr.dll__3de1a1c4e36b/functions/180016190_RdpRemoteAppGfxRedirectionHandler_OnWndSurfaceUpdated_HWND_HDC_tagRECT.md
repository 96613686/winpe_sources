# RdpRemoteAppGfxRedirectionHandler::OnWndSurfaceUpdated(HWND__ *,HDC__ *,tagRECT *)

- ea: `0x180016190`
- end: `0x180016348`
- name: `?OnWndSurfaceUpdated@RdpRemoteAppGfxRedirectionHandler@@UEAAJPEAUHWND__@@PEAUHDC__@@PEAUtagRECT@@@Z`
- size: `440`
- prototype: `int(RdpRemoteAppGfxRedirectionHandler *__hidden this, HWND, HDC, struct tagRECT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180001724`
- `0x180001bfc`
- `0x180005f9c`
- `0x1800139a8`
- `0x180016190`
- `0x18002c010`

## string_xrefs

- `0x1800161af`: `OnWndSurfaceUpdated`
- `0x180016215`: `Failed to retrieve or create a dirty surface context`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::OnWndSurfaceUpdated(
        RdpRemoteAppGfxRedirectionHandler *this,
        HWND a2,
        __int64 a3,
        struct tagRECT *a4)
{
  int DirtySurface; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  __int16 *v11; // rdx
  const char **v12; // rax
  const char **v14; // [rsp+30h] [rbp-50h]
  const char **v15; // [rsp+40h] [rbp-40h]
  const char **v16; // [rsp+48h] [rbp-38h]
  const char *v17; // [rsp+50h] [rbp-30h] BYREF
  struct RdpRemoteAppGfxRedirectionHandler::DirtySurface *v18; // [rsp+58h] [rbp-28h] BYREF
  const char *v19; // [rsp+60h] [rbp-20h] BYREF
  const char *v20; // [rsp+68h] [rbp-18h] BYREF
  const char *v21; // [rsp+70h] [rbp-10h] BYREF
  const char *v22; // [rsp+78h] [rbp-8h] BYREF
  HWND v23; // [rsp+A0h] [rbp+20h] BYREF

  v18 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v23 = a2;
    v17 = "OnWndSurfaceUpdated";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)&dword_18003C72C,
      a3,
      (__int64)a4,
      (const unsigned __int16 **)&v17,
      (__int64)&v23);
  }
  DirtySurface = RdpRemoteAppGfxRedirectionHandler::GetDirtySurface((__int64)this - 48, a2, &v18, (__int64)a4);
  if ( DirtySurface >= 0 )
  {
    DirtySurface = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, LONG))(**((_QWORD **)v18 + 6) + 32LL))(
                     *((_QWORD *)v18 + 6),
                     (unsigned int)a4->left,
                     (unsigned int)a4->top,
                     (unsigned int)a4->right,
                     a4->bottom);
    if ( DirtySurface < 0 && (unsigned int)dword_180044008 > 2 )
    {
      v21 = "OnWndSurfaceUpdated";
      v22 = "Failed to add dirty rectange to bounds accumulator";
      v11 = (__int16 *)&unk_18003C668;
      LODWORD(v23) = 1043;
      v20 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v19 = "Error HResult failed";
      v16 = &v22;
      v15 = &v21;
      v14 = &v20;
      v12 = &v19;
      goto LABEL_9;
    }
  }
  else
  {
    v10 = (unsigned int)dword_180044008;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v20 = "OnWndSurfaceUpdated";
      v19 = "Failed to retrieve or create a dirty surface context";
      v11 = word_18003C6CA;
      LODWORD(v23) = 1033;
      v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v22 = "Error HResult failed";
      v16 = &v19;
      v15 = &v20;
      v14 = &v21;
      v12 = &v22;
LABEL_9:
      LODWORD(v17) = DirtySurface;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v10,
        (__int64)v11,
        v8,
        v9,
        (const unsigned __int16 **)v12,
        (__int64)&v17,
        (const unsigned __int16 **)v14,
        (__int64)&v23,
        (const unsigned __int16 **)v15,
        (const unsigned __int16 **)v16);
    }
  }
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v18);
  return (unsigned int)DirtySurface;
}

```

## disassembly

```asm
0x180016190  mov     r11, rsp
0x180016193  mov     [r11+10h], rbx
0x180016197  mov     [r11+18h], rsi
0x18001619b  push    rbp
0x18001619c  push    rdi
0x18001619d  push    r14
0x18001619f  mov     rbp, rsp
0x1800161a2  sub     rsp, 80h
0x1800161a9  mov     eax, cs:dword_180044008
0x1800161af  lea     r14, aOnwndsurfaceup; "OnWndSurfaceUpdated"
0x1800161b6  mov     [rbp+var_28], 0
0x1800161be  mov     rdi, r9
0x1800161c1  mov     rbx, rdx
0x1800161c4  mov     rsi, rcx
0x1800161c7  cmp     eax, 5
0x1800161ca  jbe     short loc_1800161F0
0x1800161cc  lea     rax, [rbp+arg_0]
0x1800161d0  mov     [rbp+arg_0], rdx
0x1800161d4  mov     [r11-70h], rax
0x1800161d8  lea     rdx, dword_18003C72C
0x1800161df  lea     rax, [rbp+var_30]
0x1800161e3  mov     [rbp+var_30], r14
0x1800161e7  mov     [r11-78h], rax
0x1800161eb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800161f0  lea     rcx, [rsi-30h]; this
0x1800161f4  mov     rdx, rbx; HWND
0x1800161f7  lea     r8, [rbp+var_28]; struct RdpRemoteAppGfxRedirectionHandler::DirtySurface **
0x1800161fb  call    ?GetDirtySurface@RdpRemoteAppGfxRedirectionHandler@@AEAAJPEAUHWND__@@PEAPEAVDirtySurface@1@@Z; RdpRemoteAppGfxRedirectionHandler::GetDirtySurface(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface * *)
0x180016200  mov     ebx, eax
0x180016202  test    eax, eax
0x180016204  jns     short loc_18001627E
0x180016206  mov     ecx, cs:dword_180044008
0x18001620c  cmp     ecx, 2
0x18001620f  jbe     loc_180016325
0x180016215  lea     rax, aFailedToRetrie; "Failed to retrieve or create a dirty su"...
0x18001621c  mov     [rbp+var_18], r14
0x180016220  mov     [rbp+var_20], rax
0x180016224  lea     rdx, word_18003C6CA
0x18001622b  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180016232  mov     dword ptr [rbp+arg_0], 409h
0x180016239  mov     [rbp+var_10], rax
0x18001623d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180016244  mov     [rbp+var_8], rax
0x180016248  lea     rax, [rbp+var_20]
0x18001624c  mov     [rsp+80h+var_38], rax
0x180016251  lea     rax, [rbp+var_18]
0x180016255  mov     [rsp+80h+var_40], rax
0x18001625a  lea     rax, [rbp+arg_0]
0x18001625e  mov     [rsp+80h+var_48], rax
0x180016263  lea     rax, [rbp+var_10]
0x180016267  mov     [rsp+80h+var_50], rax
0x18001626c  lea     rax, [rbp+var_30]
0x180016270  mov     [rsp+80h+var_58], rax
0x180016275  lea     rax, [rbp+var_8]
0x180016279  jmp     loc_180016318
0x18001627e  mov     edx, [rdi+0Ch]
0x180016281  mov     rax, [rbp+var_28]
0x180016285  mov     r9d, [rdi+8]
0x180016289  mov     r8d, [rdi+4]
0x18001628d  mov     dword ptr [rsp+80h+var_60], edx
0x180016291  mov     rcx, [rax+30h]
0x180016295  mov     edx, [rdi]
0x180016297  mov     rax, [rcx]
0x18001629a  mov     rax, [rax+20h]
0x18001629e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162a3  mov     ebx, eax
0x1800162a5  test    eax, eax
0x1800162a7  jns     short loc_180016325
0x1800162a9  mov     eax, cs:dword_180044008
0x1800162af  cmp     eax, 2
0x1800162b2  jbe     short loc_180016325
0x1800162b4  lea     rax, aFailedToAddDir; "Failed to add dirty rectange to bounds "...
0x1800162bb  mov     [rbp+var_10], r14
0x1800162bf  mov     [rbp+var_8], rax
0x1800162c3  lea     rdx, unk_18003C668
0x1800162ca  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800162d1  mov     dword ptr [rbp+arg_0], 413h
0x1800162d8  mov     [rbp+var_18], rax
0x1800162dc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800162e3  mov     [rbp+var_20], rax
0x1800162e7  lea     rax, [rbp+var_8]
0x1800162eb  mov     [rsp+80h+var_38], rax
0x1800162f0  lea     rax, [rbp+var_10]
0x1800162f4  mov     [rsp+80h+var_40], rax
0x1800162f9  lea     rax, [rbp+arg_0]
0x1800162fd  mov     [rsp+80h+var_48], rax
0x180016302  lea     rax, [rbp+var_18]
0x180016306  mov     [rsp+80h+var_50], rax
0x18001630b  lea     rax, [rbp+var_30]
0x18001630f  mov     [rsp+80h+var_58], rax
0x180016314  lea     rax, [rbp+var_20]
0x180016318  mov     [rsp+80h+var_60], rax
0x18001631d  mov     dword ptr [rbp+var_30], ebx
0x180016320  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180016325  lea     rcx, [rbp+var_28]
0x180016329  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x18001632e  lea     r11, [rsp+80h+var_s0]
0x180016336  mov     eax, ebx
0x180016338  mov     rbx, [r11+28h]
0x18001633c  mov     rsi, [r11+30h]
0x180016340  mov     rsp, r11
0x180016343  pop     r14
0x180016345  pop     rdi
0x180016346  pop     rbp
0x180016347  retn
```
