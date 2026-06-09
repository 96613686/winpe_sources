# CCommunityRatings::Initialize(HWND__ *,IMimeMessage *,IOleCommandTarget *,int)

- ea: `0x180082a04`
- end: `0x180082dbf`
- name: `?Initialize@CCommunityRatings@@QEAAJPEAUHWND__@@PEAUIMimeMessage@@PEAUIOleCommandTarget@@H@Z`
- size: `955`
- prototype: `__int64 __fastcall(CCommunityRatings *__hidden this, HWND, struct IMimeMessage *, struct IOleCommandTarget *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180082728`

## callees

- `0x180002098`
- `0x180034288`
- `0x180082330`
- `0x180082a04`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `USER32!IsWindow` at `0x180082d5a`
- `USER32!IsWindow` at `0x180082d5a`
- `USER32!SendMessageA` at `0x180082cf3`
- `USER32!SendMessageA` at `0x180082d4b`
- `USER32!SendMessageA` at `0x180082d7b`
- `USER32!SendMessageA` at `0x180082cf3`
- `USER32!SendMessageA` at `0x180082d4b`
- `USER32!SendMessageA` at `0x180082d7b`
- `USER32!CreateWindowExW` at `0x180082c97`
- `USER32!CreateWindowExW` at `0x180082c97`

## string_xrefs

- `0x180082c4d`: `OE_CommunityVoteWndClass`

## pseudocode

```c
__int64 __fastcall CCommunityRatings::Initialize(
        CCommunityRatings *this,
        HWND a2,
        struct IMimeMessage *a3,
        struct IOleCommandTarget *a4)
{
  _QWORD *v6; // r15
  __int64 *v7; // r14
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  int v11; // esi
  __int64 v12; // rcx
  __int64 v13; // rcx
  HWND Window; // rax
  WPARAM v15; // r8
  HWND v16; // rcx
  LPARAM v17; // r9
  HWND v18; // rcx
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+6Ch] [rbp-94h] BYREF
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  __int128 v25; // [rsp+88h] [rbp-78h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h]
  _BYTE v27[512]; // [rsp+A0h] [rbp-60h] BYREF
  char v28; // [rsp+2A0h] [rbp+1A0h]

  if ( a2 && a3 && a4 )
  {
    *((_QWORD *)this + 2) = a2;
    v6 = (_QWORD *)((char *)this + 344);
    *((_DWORD *)this + 14) = 754;
    ReplaceInterface<IOleClientSite>((char *)this + 344, a3);
    v7 = (__int64 *)((char *)this + 336);
    ReplaceInterface<IOleClientSite>((char *)this + 336, a4);
    *((_DWORD *)this + 82) = 0;
    if ( (int)CCommunityRatings::CheckForCommunities(this) >= 0 )
    {
      if ( !*((_DWORD *)this + 8) )
        goto LABEL_22;
      if ( !*((_DWORD *)this + 9) )
        goto LABEL_22;
      v8 = (_QWORD *)((char *)this + 40);
      if ( *((_QWORD *)this + 5) )
        goto LABEL_22;
      v9 = *v7;
      v26 = 0;
      v25 = 0xDu;
      if ( (*(int (__fastcall **)(__int64, __int64 *, __int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v9 + 32LL))(
             v9,
             &CMDSETID_MimeEditHost,
             35,
             0,
             0,
             &v25) < 0
        || (***((int (__fastcall ****)(_QWORD, GUID *, char *))&v25 + 1))(
             *((_QWORD *)&v25 + 1),
             &GUID_b5c2c92f_69dd_4673_becb_946b2e38b918,
             (char *)this + 40) < 0 )
      {
        goto LABEL_25;
      }
      v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v8;
      v20 = 0;
      v11 = (**v10)(v10, &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352, &v20);
      if ( v11 >= 0 )
      {
        v12 = *v7;
        v24 = 0;
        v23 = 0xDu;
        v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v12 + 32LL))(
                v12,
                &CMDSETID_MimeEditHost,
                33,
                0,
                0,
                &v23);
        if ( v11 >= 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 24LL))(v20, *((_QWORD *)&v23 + 1));
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)&v23 + 8);
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v20);
      }
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)&v25 + 8);
      if ( v11 < 0 )
        goto LABEL_25;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v8 + 112LL))(*v8, *v6) < 0 )
        goto LABEL_25;
      v13 = *v8;
      v22 = 5;
      LODWORD(v20) = 0;
      v21 = 0;
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 120LL))(v13, &v21);
      if ( (*(int (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v8 + 168LL))(*v8, (char *)this + 328) < 0 )
        goto LABEL_25;
      if ( v21
        || (Window = CreateWindowExW(
                       4u,
                       L"OE_CommunityVoteWndClass",
                       0,
                       0x56010000u,
                       0,
                       0,
                       120,
                       45,
                       *((HWND *)this + 2),
                       (HMENU)0x2F2,
                       g_hInst,
                       0),
            (*((_QWORD *)this + 6) = Window) == 0) )
      {
LABEL_22:
        v18 = (HWND)*((_QWORD *)this + 6);
        if ( v18 )
        {
          if ( IsWindow(v18) )
            SendMessageA(*((HWND *)this + 6), 0xDC6u, *((int *)this + 80), *((int *)this + 81));
        }
        return 0;
      }
      (*(void (__fastcall **)(_QWORD, HWND))(*(_QWORD *)*v8 + 96LL))(*v8, Window);
      if ( (*(int (__fastcall **)(_QWORD, __int64 *, int *))(*(_QWORD *)*v8 + 56LL))(*v8, &v20, &v22) >= 0 )
      {
        SendMessageA(*((HWND *)this + 6), 0xDD1u, (int)v20, v22);
        memset_0(v27, 0, 0x234u);
        if ( (*(int (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v8 + 152LL))(*v8, v27) >= 0 )
        {
          v15 = *((int *)this + 80);
          v16 = (HWND)*((_QWORD *)this + 6);
          v17 = v28 != 0;
          *((_DWORD *)this + 81) = v28 != 0;
          SendMessageA(v16, 0xDC6u, v15, v17);
          goto LABEL_22;
        }
      }
    }
LABEL_25:
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 40);
    return 0;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180082a04  mov     [rsp-8+arg_8], rbx
0x180082a09  push    rbp
0x180082a0a  push    rsi
0x180082a0b  push    rdi
0x180082a0c  push    r12
0x180082a0e  push    r13
0x180082a10  push    r14
0x180082a12  push    r15
0x180082a14  lea     rbp, [rsp-1F0h]
0x180082a1c  sub     rsp, 2F0h
0x180082a23  mov     rax, cs:__security_cookie
0x180082a2a  xor     rax, rsp
0x180082a2d  mov     [rbp+220h+var_40], rax
0x180082a34  xor     r13d, r13d
0x180082a37  mov     rdi, r9
0x180082a3a  mov     rbx, rcx
0x180082a3d  test    rdx, rdx
0x180082a40  jz      loc_180082D90
0x180082a46  test    r8, r8
0x180082a49  jz      loc_180082D90
0x180082a4f  test    r9, r9
0x180082a52  jz      loc_180082D90
0x180082a58  mov     [rcx+10h], rdx
0x180082a5c  lea     r15, [rcx+158h]
0x180082a63  mov     dword ptr [rcx+38h], 2F2h
0x180082a6a  mov     rdx, r8
0x180082a6d  mov     rcx, r15
0x180082a70  call    ??$ReplaceInterface@UIOleClientSite@@@@YAXAEAPEAUIOleClientSite@@PEAU0@@Z; ReplaceInterface<IOleClientSite>(IOleClientSite * &,IOleClientSite *)
0x180082a75  lea     r14, [rbx+150h]
0x180082a7c  mov     rdx, rdi
0x180082a7f  mov     rcx, r14
0x180082a82  call    ??$ReplaceInterface@UIOleClientSite@@@@YAXAEAPEAUIOleClientSite@@PEAU0@@Z; ReplaceInterface<IOleClientSite>(IOleClientSite * &,IOleClientSite *)
0x180082a87  lea     r12, [rbx+148h]
0x180082a8e  mov     rcx, rbx; this
0x180082a91  mov     [r12], r13d
0x180082a95  call    ?CheckForCommunities@CCommunityRatings@@QEAAJXZ; CCommunityRatings::CheckForCommunities(void)
0x180082a9a  test    eax, eax
0x180082a9c  js      loc_180082D83
0x180082aa2  cmp     [rbx+20h], r13d
0x180082aa6  jz      loc_180082D51
0x180082aac  cmp     [rbx+24h], r13d
0x180082ab0  jz      loc_180082D51
0x180082ab6  lea     rdi, [rbx+28h]
0x180082aba  cmp     [rdi], r13
0x180082abd  jnz     loc_180082D51
0x180082ac3  mov     rcx, [r14]
0x180082ac6  lea     rdx, [rbp+220h+var_298]
0x180082aca  xor     eax, eax
0x180082acc  mov     qword ptr [rsp+320h+Y], rdx
0x180082ad1  mov     [rbp+220h+var_288], rax
0x180082ad5  lea     r8d, [r13+23h]
0x180082ad9  xorps   xmm0, xmm0
0x180082adc  mov     qword ptr [rsp+320h+X], r13
0x180082ae1  movups  [rbp+220h+var_298], xmm0
0x180082ae5  lea     eax, [r13+0Dh]
0x180082ae9  mov     qword ptr [rbp+220h+var_298+8], r13
0x180082aed  mov     word ptr [rbp+220h+var_298], ax
0x180082af1  lea     rdx, CMDSETID_MimeEditHost
0x180082af8  mov     rax, [rcx]
0x180082afb  xor     r9d, r9d
0x180082afe  mov     rax, [rax+20h]
0x180082b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b07  test    eax, eax
0x180082b09  js      loc_180082D83
0x180082b0f  mov     rcx, qword ptr [rbp+220h+var_298+8]
0x180082b13  lea     rdx, _GUID_b5c2c92f_69dd_4673_becb_946b2e38b918
0x180082b1a  mov     r8, rdi
0x180082b1d  mov     rax, [rcx]
0x180082b20  mov     rax, [rax]
0x180082b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b28  test    eax, eax
0x180082b2a  js      loc_180082D83
0x180082b30  mov     rcx, [rdi]
0x180082b33  lea     r8, [rsp+320h+var_2C0]
0x180082b38  mov     [rsp+320h+var_2C0], r13
0x180082b3d  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x180082b44  mov     rax, [rcx]
0x180082b47  mov     rax, [rax]
0x180082b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b4f  mov     esi, eax
0x180082b51  test    eax, eax
0x180082b53  js      short loc_180082BCD
0x180082b55  mov     rcx, [r14]
0x180082b58  lea     r8, [rsp+320h+var_2B0]
0x180082b5d  xor     eax, eax
0x180082b5f  mov     qword ptr [rsp+320h+Y], r8
0x180082b64  mov     [rbp+220h+var_2A0], rax
0x180082b68  lea     r8d, [r13+21h]
0x180082b6c  xorps   xmm0, xmm0
0x180082b6f  mov     qword ptr [rsp+320h+X], r13
0x180082b74  movups  [rsp+320h+var_2B0], xmm0
0x180082b79  lea     eax, [r13+0Dh]
0x180082b7d  mov     qword ptr [rsp+320h+var_2B0+8], r13
0x180082b82  mov     word ptr [rsp+320h+var_2B0], ax
0x180082b87  lea     rdx, CMDSETID_MimeEditHost
0x180082b8e  mov     rax, [rcx]
0x180082b91  xor     r9d, r9d
0x180082b94  mov     rax, [rax+20h]
0x180082b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b9d  mov     esi, eax
0x180082b9f  test    eax, eax
0x180082ba1  js      short loc_180082BC3
0x180082ba3  mov     rcx, [rsp+320h+var_2C0]
0x180082ba8  mov     rdx, qword ptr [rsp+320h+var_2B0+8]
0x180082bad  mov     rax, [rcx]
0x180082bb0  mov     rax, [rax+18h]
0x180082bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082bb9  lea     rcx, [rsp+320h+var_2B0+8]
0x180082bbe  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180082bc3  lea     rcx, [rsp+320h+var_2C0]
0x180082bc8  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180082bcd  lea     rcx, [rbp+220h+var_298+8]
0x180082bd1  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180082bd6  test    esi, esi
0x180082bd8  js      loc_180082D83
0x180082bde  mov     rcx, [rdi]
0x180082be1  mov     rdx, [r15]
0x180082be4  mov     rax, [rcx]
0x180082be7  mov     rax, [rax+70h]
0x180082beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082bf0  test    eax, eax
0x180082bf2  js      loc_180082D83
0x180082bf8  mov     rcx, [rdi]
0x180082bfb  lea     rdx, [rsp+320h+var_2B8]
0x180082c00  mov     [rsp+320h+var_2B4], 5
0x180082c08  mov     dword ptr [rsp+320h+var_2C0], r13d
0x180082c0d  mov     [rsp+320h+var_2B8], r13d
0x180082c12  mov     rax, [rcx]
0x180082c15  mov     rax, [rax+78h]
0x180082c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c1e  mov     rcx, [rdi]
0x180082c21  mov     rdx, r12
0x180082c24  mov     rax, [rcx]
0x180082c27  mov     rax, [rax+0A8h]
0x180082c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c33  test    eax, eax
0x180082c35  js      loc_180082D83
0x180082c3b  cmp     [rsp+320h+var_2B8], r13d
0x180082c40  jnz     loc_180082D51
0x180082c46  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180082c4d  lea     rdx, c_wszVoteWndClass; "OE_CommunityVoteWndClass"
0x180082c54  mov     [rsp+320h+lpParam], r13; lpParam
0x180082c59  xor     r8d, r8d; lpWindowName
0x180082c5c  mov     [rsp+320h+hInstance], rax; hInstance
0x180082c61  mov     r9d, 56010000h; dwStyle
0x180082c67  mov     rax, [rbx+10h]
0x180082c6b  mov     [rsp+320h+hMenu], 2F2h; hMenu
0x180082c74  mov     [rsp+320h+hWndParent], rax; hWndParent
0x180082c79  lea     ecx, [r8+4]; dwExStyle
0x180082c7d  mov     [rsp+320h+nHeight], 2Dh ; '-'; nHeight
0x180082c85  mov     [rsp+320h+nWidth], 78h ; 'x'; nWidth
0x180082c8d  mov     [rsp+320h+Y], r13d; Y
0x180082c92  mov     [rsp+320h+X], r13d; X
0x180082c97  call    cs:__imp_CreateWindowExW
0x180082c9d  mov     [rbx+30h], rax
0x180082ca1  mov     r8, rax
0x180082ca4  test    rax, rax
0x180082ca7  jz      loc_180082D51
0x180082cad  mov     rcx, [rdi]
0x180082cb0  mov     rdx, [rcx]
0x180082cb3  mov     rax, [rdx+60h]
0x180082cb7  mov     rdx, r8
0x180082cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082cbf  mov     rcx, [rdi]
0x180082cc2  lea     r8, [rsp+320h+var_2B4]
0x180082cc7  lea     rdx, [rsp+320h+var_2C0]
0x180082ccc  mov     rax, [rcx]
0x180082ccf  mov     rax, [rax+38h]
0x180082cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082cd8  test    eax, eax
0x180082cda  js      loc_180082D83
0x180082ce0  movsxd  r9, [rsp+320h+var_2B4]; lParam
0x180082ce5  mov     edx, 0DD1h; Msg
0x180082cea  movsxd  r8, dword ptr [rsp+320h+var_2C0]; wParam
0x180082cef  mov     rcx, [rbx+30h]; hWnd
0x180082cf3  call    cs:__imp_SendMessageA
0x180082cf9  xor     edx, edx; Val
0x180082cfb  lea     rcx, [rbp+220h+var_280]; void *
0x180082cff  mov     r8d, 234h; Size
0x180082d05  call    memset_0
0x180082d0a  mov     rcx, [rdi]
0x180082d0d  lea     rdx, [rbp+220h+var_280]
0x180082d11  mov     rax, [rcx]
0x180082d14  mov     rax, [rax+98h]
0x180082d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d20  test    eax, eax
0x180082d22  js      short loc_180082D83
0x180082d24  cmp     [rbp+220h+var_80], r13b
0x180082d2b  mov     eax, r13d
0x180082d2e  movsxd  r8, dword ptr [rbx+140h]; wParam
0x180082d35  mov     edx, 0DC6h; Msg
0x180082d3a  mov     rcx, [rbx+30h]; hWnd
0x180082d3e  setnz   al
0x180082d41  mov     r9d, eax; lParam
0x180082d44  mov     [rbx+144h], r9d
0x180082d4b  call    cs:__imp_SendMessageA
0x180082d51  mov     rcx, [rbx+30h]; hWnd
0x180082d55  test    rcx, rcx
0x180082d58  jz      short loc_180082D8C
0x180082d5a  call    cs:__imp_IsWindow
0x180082d60  test    eax, eax
0x180082d62  jz      short loc_180082D8C
0x180082d64  movsxd  r9, dword ptr [rbx+144h]; lParam
0x180082d6b  mov     edx, 0DC6h; Msg
0x180082d70  movsxd  r8, dword ptr [rbx+140h]; wParam
0x180082d77  mov     rcx, [rbx+30h]; hWnd
0x180082d7b  call    cs:__imp_SendMessageA
0x180082d81  jmp     short loc_180082D8C
0x180082d83  lea     rcx, [rbx+28h]
0x180082d87  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180082d8c  xor     eax, eax
0x180082d8e  jmp     short loc_180082D95
0x180082d90  mov     eax, 80070057h
0x180082d95  mov     rcx, [rbp+220h+var_40]
0x180082d9c  xor     rcx, rsp; StackCookie
0x180082d9f  call    __security_check_cookie
0x180082da4  mov     rbx, [rsp+320h+arg_8]
0x180082dac  add     rsp, 2F0h
0x180082db3  pop     r15
0x180082db5  pop     r14
0x180082db7  pop     r13
0x180082db9  pop     r12
0x180082dbb  pop     rdi
0x180082dbc  pop     rsi
0x180082dbd  pop     rbp
0x180082dbe  retn
```
