# CMapiPreviewer::DoPreview(void)

- ea: `0x180023020`
- end: `0x1800232fb`
- name: `?DoPreview@CMapiPreviewer@@UEAAJXZ`
- size: `731`
- prototype: `__int64 __fastcall(CMapiPreviewer *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000557c`
- `0x180008c80`
- `0x180008d2c`
- `0x18001d404`
- `0x180022e14`
- `0x180023020`
- `0x180023304`
- `0x180026bfc`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800231f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800231f3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180023241`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180023241`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18002312c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18002314d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023164`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023190`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800232e7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18002312c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18002314d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023164`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023190`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800232e7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18002310d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18002310d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiPreviewer::DoPreview(CMapiPreviewer *this)
{
  CMapiPreviewer *v2; // rbp
  int Error; // ebx
  __int64 v5; // rcx
  HWND Window; // rax
  HWND v7; // rsi
  _QWORD *v8; // rbx
  FARPROC ProcAddress; // rax
  int v10; // eax
  WPARAM p_wParam; // r8
  const WCHAR *v12; // r9
  UINT v13; // edx
  CMapiPreviewer *v14; // [rsp+60h] [rbp-48h] BYREF
  int v15; // [rsp+68h] [rbp-40h]
  unsigned int (__fastcall *v16)(unsigned __int64, unsigned __int8 *, int, int *); // [rsp+6Ch] [rbp-3Ch]
  WPARAM wParam; // [rsp+B0h] [rbp+8h] BYREF

  v2 = (CMapiPreviewer *)((char *)this - 16);
  if ( !*((_QWORD *)this + 25) )
    return 2147500037LL;
  Error = CMapiPreviewer::DrawHeader((CMapiPreviewer *)((char *)this - 16));
  if ( Error >= 0 )
  {
    Error = CMapiPreviewer::SetupWindowSizes(v2, (const struct tagRECT *)this + 7, 1);
    if ( Error >= 0 )
    {
      v5 = *((_QWORD *)this + 11);
      if ( v5 )
        return (unsigned int)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 40LL))(v5);
      if ( *((_QWORD *)this + 20) )
      {
LABEL_23:
        if ( *((_QWORD *)this + 30) )
        {
          v15 = 0;
          v14 = v2;
          v16 = CMapiPreviewer::StreamInCallback;
          v10 = *((_DWORD *)this + 48);
          p_wParam = 2;
          if ( v10 != 2 )
          {
            p_wParam = 1;
            if ( v10 == 1 )
              p_wParam = 17;
          }
          v12 = (const WCHAR *)&v14;
          v13 = 1097;
        }
        else
        {
          wParam = 0x4B000000000LL;
          v12 = &lParam;
          p_wParam = (WPARAM)&wParam;
          v13 = 1121;
        }
        SendMessageW(*((HWND *)this + 20), v13, p_wParam, (LPARAM)v12);
        return (unsigned int)Error;
      }
      Window = CreateWindowExW(
                 0,
                 L"RICHEDIT50W",
                 0,
                 0x50200804u,
                 *((_DWORD *)this + 32),
                 *((_DWORD *)this + 33),
                 *((_DWORD *)this + 34) - *((_DWORD *)this + 32),
                 *((_DWORD *)this + 35) - *((_DWORD *)this + 33),
                 *((HWND *)this + 19),
                 (HMENU)0xFFFFFFFFFFFFFFFFLL,
                 off_180053498,
                 0);
      v7 = Window;
      if ( Window )
      {
        SendMessageW(Window, 0x435u, 0, 0x100000);
        SendMessageW(v7, 0x446u, 0, ((unsigned __int64)this + 16) & -(__int64)(v2 != 0));
        SendMessageW(v7, 0x445u, 0, 0x4000000);
      }
      else
      {
        Error = ResultFromLastError();
        if ( Error < 0 )
          return (unsigned int)Error;
      }
      v8 = (_QWORD *)((char *)this + 1184);
      if ( !SendMessageW(v7, 0x43Cu, 0, (LPARAM)this + 1184) || !*v8 )
        goto LABEL_19;
      Error = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v8)(
                *v8,
                &GUID_8cc497c0_a1df_11ce_8098_00aa0047be5d,
                (char *)this + 1192);
      if ( Error < 0 )
        goto LABEL_20;
      if ( AutoLibrary::valid((AutoLibrary *)&g_comctl32Helper)
        && (AutoLibrary::load((AutoLibrary *)&g_comctl32Helper),
            (ProcAddress = GetProcAddress(qword_1800533F8, (LPCSTR)0x19A)) != 0)
        && ((unsigned int (__fastcall *)(HWND, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, POINT), __int64, CMapiPreviewer *))ProcAddress)(
             v7,
             CMapiPreviewer::EditSubclassWndProc,
             1,
             v2) )
      {
        Error = CMapiPreviewer::CreateTooltip(v2, v7);
        if ( Error >= 0 )
        {
          *((_QWORD *)this + 20) = v7;
          goto LABEL_23;
        }
      }
      else
      {
LABEL_19:
        Error = -2147467259;
      }
LABEL_20:
      if ( v7 )
      {
        DestroyWindow(v7);
        ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1184);
        ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1192);
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180023020  push    rbx
0x180023022  push    rbp
0x180023023  push    rsi
0x180023024  push    rdi
0x180023025  sub     rsp, 88h
0x18002302c  mov     rdi, rcx
0x18002302f  lea     rbp, [rcx-10h]
0x180023033  cmp     qword ptr [rbp+0D8h], 0
0x18002303b  jnz     short loc_180023047
0x18002303d  mov     eax, 80004005h
0x180023042  jmp     loc_1800232EF
0x180023047  mov     rcx, rbp; this
0x18002304a  call    ?DrawHeader@CMapiPreviewer@@AEAAJXZ; CMapiPreviewer::DrawHeader(void)
0x18002304f  mov     ebx, eax
0x180023051  test    eax, eax
0x180023053  js      loc_1800232ED
0x180023059  lea     rdx, [rdi+70h]; struct tagRECT *
0x18002305d  mov     r8d, 1; int
0x180023063  mov     rcx, rbp; this
0x180023066  call    ?SetupWindowSizes@CMapiPreviewer@@AEAAJPEBUtagRECT@@H@Z; CMapiPreviewer::SetupWindowSizes(tagRECT const *,int)
0x18002306b  mov     ebx, eax
0x18002306d  test    eax, eax
0x18002306f  js      loc_1800232ED
0x180023075  mov     rcx, [rdi+58h]
0x180023079  test    rcx, rcx
0x18002307c  jz      short loc_180023091
0x18002307e  mov     rax, [rcx]
0x180023081  mov     rax, [rax+28h]
0x180023085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002308a  mov     ebx, eax
0x18002308c  jmp     loc_1800232ED
0x180023091  cmp     qword ptr [rdi+0A0h], 0
0x180023099  jnz     loc_180023267
0x18002309f  mov     rax, cs:off_180053498
0x1800230a6  mov     r8d, [rdi+84h]
0x1800230ad  mov     r9d, [rdi+80h]
0x1800230b4  mov     edx, [rdi+8Ch]
0x1800230ba  sub     edx, r8d
0x1800230bd  mov     ecx, [rdi+88h]
0x1800230c3  sub     ecx, r9d
0x1800230c6  mov     [rsp+0A8h+lpParam], 0; lpParam
0x1800230cf  mov     [rsp+0A8h+hInstance], rax; hInstance
0x1800230d4  mov     [rsp+0A8h+hMenu], 0FFFFFFFFFFFFFFFFh; hMenu
0x1800230dd  mov     rax, [rdi+98h]
0x1800230e4  mov     [rsp+0A8h+hWndParent], rax; hWndParent
0x1800230e9  mov     [rsp+0A8h+nHeight], edx; nHeight
0x1800230ed  mov     [rsp+0A8h+nWidth], ecx; nWidth
0x1800230f1  mov     [rsp+0A8h+Y], r8d; Y
0x1800230f6  mov     [rsp+0A8h+X], r9d; X
0x1800230fb  mov     r9d, 50200804h; dwStyle
0x180023101  xor     r8d, r8d; lpWindowName
0x180023104  lea     rdx, aRichedit50w; "RICHEDIT50W"
0x18002310b  xor     ecx, ecx; dwExStyle
0x18002310d  call    cs:__imp_CreateWindowExW
0x180023113  mov     rsi, rax
0x180023116  test    rax, rax
0x180023119  jz      short loc_18002316C
0x18002311b  mov     r9d, 100000h; lParam
0x180023121  xor     r8d, r8d; wParam
0x180023124  mov     edx, 435h; Msg
0x180023129  mov     rcx, rax; hWnd
0x18002312c  call    cs:__imp_SendMessageW
0x180023132  mov     rcx, rbp
0x180023135  lea     rdx, [rdi+10h]
0x180023139  neg     rcx
0x18002313c  sbb     r9, r9
0x18002313f  and     r9, rdx; lParam
0x180023142  xor     r8d, r8d; wParam
0x180023145  mov     edx, 446h; Msg
0x18002314a  mov     rcx, rsi; hWnd
0x18002314d  call    cs:__imp_SendMessageW
0x180023153  mov     r9d, 4000000h; lParam
0x180023159  xor     r8d, r8d; wParam
0x18002315c  mov     edx, 445h; Msg
0x180023161  mov     rcx, rsi; hWnd
0x180023164  call    cs:__imp_SendMessageW
0x18002316a  jmp     short loc_18002317B
0x18002316c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180023171  mov     ebx, eax
0x180023173  test    eax, eax
0x180023175  js      loc_18002325F
0x18002317b  lea     rbx, [rdi+4A0h]
0x180023182  mov     r9, rbx; lParam
0x180023185  xor     r8d, r8d; wParam
0x180023188  mov     edx, 43Ch; Msg
0x18002318d  mov     rcx, rsi; hWnd
0x180023190  call    cs:__imp_SendMessageW
0x180023196  test    rax, rax
0x180023199  jz      loc_180023234
0x18002319f  cmp     qword ptr [rbx], 0
0x1800231a3  jz      loc_180023234
0x1800231a9  mov     rcx, [rbx]
0x1800231ac  mov     rax, [rcx]
0x1800231af  lea     r8, [rdi+4A8h]
0x1800231b6  lea     rdx, _GUID_8cc497c0_a1df_11ce_8098_00aa0047be5d
0x1800231bd  mov     rax, [rax]
0x1800231c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231c5  mov     ebx, eax
0x1800231c7  test    eax, eax
0x1800231c9  js      short loc_180023239
0x1800231cb  lea     rcx, ?g_comctl32Helper@@3UAutoLibrary@@A; this
0x1800231d2  call    ?valid@AutoLibrary@@QEAA_NXZ; AutoLibrary::valid(void)
0x1800231d7  test    al, al
0x1800231d9  jz      short loc_180023234
0x1800231db  lea     rcx, ?g_comctl32Helper@@3UAutoLibrary@@A; this
0x1800231e2  call    ?load@AutoLibrary@@AEAAXXZ; AutoLibrary::load(void)
0x1800231e7  mov     edx, 19Ah; lpProcName
0x1800231ec  mov     rcx, cs:qword_1800533F8; hModule
0x1800231f3  call    cs:__imp_GetProcAddress
0x1800231f9  test    rax, rax
0x1800231fc  jz      short loc_180023234
0x1800231fe  mov     r9, rbp
0x180023201  mov     r8d, 1
0x180023207  lea     rdx, ?EditSubclassWndProc@CMapiPreviewer@@CA_JPEAUHWND__@@I_K_J11@Z; CMapiPreviewer::EditSubclassWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x18002320e  mov     rcx, rsi
0x180023211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023216  test    eax, eax
0x180023218  jz      short loc_180023234
0x18002321a  mov     rdx, rsi; HWND
0x18002321d  mov     rcx, rbp; this
0x180023220  call    ?CreateTooltip@CMapiPreviewer@@AEAAJPEAUHWND__@@@Z; CMapiPreviewer::CreateTooltip(HWND__ *)
0x180023225  mov     ebx, eax
0x180023227  test    eax, eax
0x180023229  js      short loc_180023239
0x18002322b  mov     [rdi+0A0h], rsi
0x180023232  jmp     short loc_180023267
0x180023234  mov     ebx, 80004005h
0x180023239  test    rsi, rsi
0x18002323c  jz      short loc_18002325F
0x18002323e  mov     rcx, rsi; hWnd
0x180023241  call    cs:__imp_DestroyWindow
0x180023247  lea     rcx, [rdi+4A0h]
0x18002324e  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180023253  lea     rcx, [rdi+4A8h]
0x18002325a  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x18002325f  test    ebx, ebx
0x180023261  js      loc_1800232ED
0x180023267  cmp     qword ptr [rdi+0F0h], 0
0x18002326f  jz      short loc_1800232B6
0x180023271  mov     [rsp+0A8h+var_40], 0
0x180023279  mov     [rsp+0A8h+var_48], rbp
0x18002327e  lea     rax, ?StreamInCallback@CMapiPreviewer@@CAK_KPEAEJPEAJ@Z; CMapiPreviewer::StreamInCallback(unsigned __int64,uchar *,long,long *)
0x180023285  mov     [rsp+0A8h+var_3C], rax
0x18002328a  mov     eax, [rdi+0C0h]
0x180023290  mov     r8d, 2
0x180023296  cmp     eax, r8d
0x180023299  jz      short loc_1800232AA
0x18002329b  lea     ecx, [r8+0Fh]
0x18002329f  lea     r8d, [rcx-10h]
0x1800232a3  cmp     eax, r8d
0x1800232a6  cmovz   r8d, ecx
0x1800232aa  lea     r9, [rsp+0A8h+var_48]
0x1800232af  mov     edx, 449h
0x1800232b4  jmp     short loc_1800232E0
0x1800232b6  mov     dword ptr [rsp+0A8h+wParam], 0
0x1800232c1  mov     dword ptr [rsp+0A8h+wParam+4], 4B0h
0x1800232cc  lea     r9, lParam; lParam
0x1800232d3  lea     r8, [rsp+0A8h+wParam]; wParam
0x1800232db  mov     edx, 461h; Msg
0x1800232e0  mov     rcx, [rdi+0A0h]; hWnd
0x1800232e7  call    cs:__imp_SendMessageW
0x1800232ed  mov     eax, ebx
0x1800232ef  add     rsp, 88h
0x1800232f6  pop     rdi
0x1800232f7  pop     rsi
0x1800232f8  pop     rbp
0x1800232f9  pop     rbx
0x1800232fa  retn
```
