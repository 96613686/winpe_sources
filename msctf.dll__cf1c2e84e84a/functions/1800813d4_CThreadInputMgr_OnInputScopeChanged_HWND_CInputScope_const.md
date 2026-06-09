# CThreadInputMgr::OnInputScopeChanged(HWND__ *,CInputScope const *)

- ea: `0x1800813d4`
- end: `0x1800815f1`
- name: `?OnInputScopeChanged@CThreadInputMgr@@QEAAXPEAUHWND__@@PEBVCInputScope@@@Z`
- size: `541`
- prototype: `void(CThreadInputMgr *__hidden this, HWND, const struct CInputScope *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008a554`

## callees

- `0x180002014`
- `0x1800071e0`
- `0x18000ccac`
- `0x180080430`
- `0x1800813d4`
- `0x180094808`
- `0x1800a4f60`
- `0x18010a010`

## import_xrefs

- `USER32!IsTopLevelWindow` at `0x180081481`
- `USER32!IsTopLevelWindow` at `0x180081481`
- `USER32!IsChild` at `0x180081512`
- `USER32!IsChild` at `0x180081512`
- `USER32!IsWindow` at `0x180081404`
- `USER32!IsWindow` at `0x180081404`
- `USER32!GetWindowThreadProcessId` at `0x180081421`
- `USER32!GetWindowThreadProcessId` at `0x180081421`

## pseudocode

```c
void __fastcall CThreadInputMgr::OnInputScopeChanged(CThreadInputMgr *this, HWND a2, const struct CInputScope *a3)
{
  __int64 v6; // rdi
  int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  int v10; // eax
  bool IsPrivate; // bl
  __int64 v12; // r8
  HWND v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // edx
  __int64 v16; // rcx
  int v17; // eax
  char v18; // al
  int v19; // [rsp+20h] [rbp-38h]
  HWND v20[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  BOOL v22; // [rsp+60h] [rbp+8h] BYREF
  __int64 v23; // [rsp+78h] [rbp+20h] BYREF

  if ( *(_QWORD *)(*((_QWORD *)this + 26) + 96LL) )
  {
    if ( IsWindow(a2) )
    {
      v6 = *((_QWORD *)this + 26);
      v7 = *(_DWORD *)(v6 + 104);
      if ( GetWindowThreadProcessId(a2, 0) == v7 )
      {
        v23 = 0;
        v8 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v6 + 96);
        v9 = **v8;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
        v10 = v9(v8, &GUID_6b0ac07c_c7a9_43d7_ba71_c9965e3d1917, &v23);
        if ( v10 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x1716,
            (unsigned int)"clientcore\\windows\\advcore\\ctf\\uim\\tim.cpp",
            (const char *)(unsigned int)v10,
            v19);
        if ( a3 )
          IsPrivate = CInputScope::IsPrivate(a3);
        else
          IsPrivate = 0;
        if ( (unsigned int)IsTopLevelWindow(a2) )
        {
          if ( (unsigned int)dword_18013D0D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D0D8, 0x80000) )
          {
            v22 = IsPrivate;
            v20[0] = a2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18013D0D8,
              (unsigned int)&byte_180127D3F,
              0,
              0,
              (__int64)v20,
              (__int64)&v22);
          }
          LOBYTE(v12) = IsPrivate;
          (*(void (__fastcall **)(__int64, HWND, __int64))(*(_QWORD *)v23 + 192LL))(v23, a2, v12);
        }
        v13 = (HWND)*((_QWORD *)this + 372);
        if ( v13 && v13 == a2 || IsChild(a2, v13) )
        {
          LOBYTE(v13) = IsPrivate;
          (*(void (__fastcall **)(__int64, HWND, __int64))(*(_QWORD *)v23 + 224LL))(v23, v13, 2);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      }
    }
  }
  if ( *((HWND *)this + 372) == a2 )
  {
    v14 = *((_QWORD *)this + 368);
    if ( !v14 || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 120LL))(v14) )
    {
      if ( a3 && (v15 = *((_DWORD *)a3 + 10)) != 0 )
      {
        v16 = 0;
        while ( 1 )
        {
          v17 = *(_DWORD *)(*((_QWORD *)a3 + 4) + 4 * v16);
          if ( v17 == 31 || (unsigned int)(v17 - 63) <= 3 )
            break;
          v16 = (unsigned int)(v16 + 1);
          if ( (unsigned int)v16 >= v15 )
            goto LABEL_27;
        }
        v18 = 1;
      }
      else
      {
LABEL_27:
        v18 = 0;
      }
      if ( *((_BYTE *)this + 3049) != v18 )
      {
        *((_BYTE *)this + 3049) = v18;
        *((_BYTE *)this + 3048) = v18;
        *((_BYTE *)this + 3050) = 0;
        *((_BYTE *)this + 3051) = v18 ^ 1;
        CThreadInputMgr::SendImmersiveFocusTracking(this, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x1800813d4  mov     [rsp+arg_8], rbx
0x1800813d9  mov     [rsp+arg_10], rbp
0x1800813de  push    rsi
0x1800813df  push    rdi
0x1800813e0  push    r14
0x1800813e2  sub     rsp, 40h
0x1800813e6  mov     rax, [rcx+0D0h]
0x1800813ed  mov     r14, r8
0x1800813f0  mov     rbp, rdx
0x1800813f3  mov     rsi, rcx
0x1800813f6  cmp     qword ptr [rax+60h], 0
0x1800813fb  jz      loc_180081542
0x180081401  mov     rcx, rdx; hWnd
0x180081404  call    cs:__imp_IsWindow
0x18008140a  test    eax, eax
0x18008140c  jz      loc_180081542
0x180081412  mov     rdi, [rsi+0D0h]
0x180081419  xor     edx, edx; lpdwProcessId
0x18008141b  mov     rcx, rbp; hWnd
0x18008141e  mov     ebx, [rdi+68h]
0x180081421  call    cs:__imp_GetWindowThreadProcessId
0x180081427  cmp     eax, ebx
0x180081429  jnz     loc_180081542
0x18008142f  mov     [rsp+58h+arg_18], 0
0x180081438  lea     rcx, [rsp+58h+arg_18]
0x18008143d  mov     rdi, [rdi+60h]
0x180081441  mov     rax, [rdi]
0x180081444  mov     rbx, [rax]
0x180081447  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008144c  lea     r8, [rsp+58h+arg_18]
0x180081451  mov     rcx, rdi
0x180081454  lea     rdx, _GUID_6b0ac07c_c7a9_43d7_ba71_c9965e3d1917
0x18008145b  mov     rax, rbx
0x18008145e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081463  test    eax, eax
0x180081465  js      loc_1800815D7
0x18008146b  test    r14, r14
0x18008146e  jz      short loc_18008147C
0x180081470  mov     rcx, r14; this
0x180081473  call    ?IsPrivate@CInputScope@@QEBA_NXZ; CInputScope::IsPrivate(void)
0x180081478  mov     bl, al
0x18008147a  jmp     short loc_18008147E
0x18008147c  xor     bl, bl
0x18008147e  mov     rcx, rbp
0x180081481  call    cs:__imp_IsTopLevelWindow
0x180081487  test    eax, eax
0x180081489  jz      short loc_1800814FE
0x18008148b  mov     eax, cs:dword_18013D0D8
0x180081491  cmp     eax, 5
0x180081494  jbe     short loc_1800814E4
0x180081496  mov     edx, 80000h
0x18008149b  lea     rcx, dword_18013D0D8
0x1800814a2  call    _tlgKeywordOn
0x1800814a7  test    al, al
0x1800814a9  jz      short loc_1800814E4
0x1800814ab  movzx   eax, bl
0x1800814ae  lea     rdx, byte_180127D3F
0x1800814b5  mov     [rsp+58h+arg_0], eax
0x1800814b9  lea     rcx, dword_18013D0D8
0x1800814c0  lea     rax, [rsp+58h+arg_0]
0x1800814c5  mov     [rsp+58h+var_28], rbp
0x1800814ca  mov     [rsp+58h+var_30], rax
0x1800814cf  xor     r9d, r9d
0x1800814d2  lea     rax, [rsp+58h+var_28]
0x1800814d7  xor     r8d, r8d
0x1800814da  mov     [rsp+58h+var_38], rax
0x1800814df  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800814e4  mov     rcx, [rsp+58h+arg_18]
0x1800814e9  mov     r8b, bl
0x1800814ec  mov     rdx, rbp
0x1800814ef  mov     rax, [rcx]
0x1800814f2  mov     rax, [rax+0C0h]
0x1800814f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800814fe  mov     rdx, [rsi+0BA0h]; hWnd
0x180081505  test    rdx, rdx
0x180081508  jz      short loc_18008150F
0x18008150a  cmp     rdx, rbp
0x18008150d  jz      short loc_18008151C
0x18008150f  mov     rcx, rbp; hWndParent
0x180081512  call    cs:__imp_IsChild
0x180081518  test    eax, eax
0x18008151a  jz      short loc_180081538
0x18008151c  mov     rcx, [rsp+58h+arg_18]
0x180081521  mov     r8d, 2
0x180081527  mov     dl, bl
0x180081529  mov     rax, [rcx]
0x18008152c  mov     rax, [rax+0E0h]
0x180081533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081538  lea     rcx, [rsp+58h+arg_18]
0x18008153d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180081542  cmp     [rsi+0BA0h], rbp
0x180081549  jnz     short loc_1800815C0
0x18008154b  mov     rcx, [rsi+0B80h]
0x180081552  test    rcx, rcx
0x180081555  jz      short loc_180081567
0x180081557  mov     rax, [rcx]
0x18008155a  mov     rax, [rax+78h]
0x18008155e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081563  test    al, al
0x180081565  jz      short loc_1800815C0
0x180081567  test    r14, r14
0x18008156a  jz      short loc_180081591
0x18008156c  mov     edx, [r14+28h]
0x180081570  test    edx, edx
0x180081572  jz      short loc_180081591
0x180081574  mov     r8, [r14+20h]
0x180081578  xor     ecx, ecx
0x18008157a  mov     eax, [r8+rcx*4]
0x18008157e  cmp     eax, 1Fh
0x180081581  jz      short loc_1800815D3
0x180081583  add     eax, 0FFFFFFC1h
0x180081586  cmp     eax, 3
0x180081589  jbe     short loc_1800815D3
0x18008158b  inc     ecx
0x18008158d  cmp     ecx, edx
0x18008158f  jb      short loc_18008157A
0x180081591  xor     al, al
0x180081593  cmp     [rsi+0BE9h], al
0x180081599  jz      short loc_1800815C0
0x18008159b  mov     [rsi+0BE9h], al
0x1800815a1  xor     edx, edx
0x1800815a3  mov     [rsi+0BE8h], al
0x1800815a9  mov     rcx, rsi
0x1800815ac  xor     al, 1
0x1800815ae  mov     byte ptr [rsi+0BEAh], 0
0x1800815b5  mov     [rsi+0BEBh], al
0x1800815bb  call    ?SendImmersiveFocusTracking@CThreadInputMgr@@QEAA_NW4FocusTrackingEventType@@@Z; CThreadInputMgr::SendImmersiveFocusTracking(FocusTrackingEventType)
0x1800815c0  mov     rbx, [rsp+58h+arg_8]
0x1800815c5  mov     rbp, [rsp+58h+arg_10]
0x1800815ca  add     rsp, 40h
0x1800815ce  pop     r14
0x1800815d0  pop     rdi
0x1800815d1  pop     rsi
0x1800815d2  retn
0x1800815d3  mov     al, 1
0x1800815d5  jmp     short loc_180081593
0x1800815d7  mov     rcx, [rsp+58h]; this
0x1800815dc  lea     r8, aClientcoreWind_9; "clientcore\\windows\\advcore\\ctf\\uim"...
0x1800815e3  mov     r9d, eax; char *
0x1800815e6  mov     edx, 1716h; void *
0x1800815eb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
