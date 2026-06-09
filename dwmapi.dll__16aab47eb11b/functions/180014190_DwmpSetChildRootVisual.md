# DwmpSetChildRootVisual

- ea: `0x180014190`
- end: `0x1800143ae`
- name: `DwmpSetChildRootVisual`
- size: `542`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001520`
- `0x180001684`
- `0x18000352c`
- `0x180014190`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001439d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001439d`
- `win32u!NtDCompositionSetChildRootVisual` at `0x180014324`
- `win32u!NtDCompositionSetChildRootVisual` at `0x180014324`

## pseudocode

```c
__int64 __fastcall DwmpSetChildRootVisual(HWND a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 (__fastcall **v8)(_QWORD *, GUID *, __int64); // rdx
  int v9; // eax
  __int64 v10; // rax
  __int64 (__fastcall **v11)(_QWORD *, GUID *, __int64); // rdx
  int v12; // r9d
  int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-38h]
  void *v16; // [rsp+28h] [rbp-30h]
  __int64 v17; // [rsp+30h] [rbp-28h] BYREF
  __int64 v18; // [rsp+38h] [rbp-20h] BYREF
  HANDLE hObject[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v20; // [rsp+98h] [rbp+40h] BYREF

  v20 = 0;
  v17 = 0;
  v18 = 0;
  hObject[0] = 0;
  if ( !IsHwndInProcess(a1) )
  {
    v6 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A160, 2u, -2147024809, 0x441u, v16);
    goto LABEL_23;
  }
  if ( a3 )
  {
    v7 = IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(&v20, *a2);
    v9 = (*v8)(a2, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, v7);
    v6 = v9;
    if ( v9 < 0 )
    {
      v15 = 1099;
      goto LABEL_14;
    }
    if ( !v20 )
    {
      v6 = -2147024809;
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A160, 2u, -2147024809, 0x44Eu, v16);
      goto LABEL_23;
    }
    v10 = IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(&v18, *a3);
    v9 = (*v11)(a3, &GUID_e8de1639_4331_4b26_bc5f_6a321d347a85, v10);
    v6 = v9;
    if ( v9 < 0 )
    {
      v15 = 1106;
      goto LABEL_14;
    }
    if ( !v18 )
    {
      v6 = -2147024809;
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A160, 2u, -2147024809, 0x455u, v16);
      goto LABEL_23;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v20 + 216LL))(
           v20,
           &GUID_e8de1639_4331_4b26_bc5f_6a321d347a85,
           &v17);
    v6 = v9;
    if ( v9 < 0 )
    {
      v15 = 1115;
      goto LABEL_14;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, HANDLE *))(*(_QWORD *)v20 + 224LL))(v20, v17, hObject);
    v6 = v9;
    if ( v9 < 0 )
    {
      v15 = 1118;
      goto LABEL_14;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 128LL))(v18, v17, 1);
    v6 = v9;
    if ( v9 < 0 )
    {
      v15 = 1121;
LABEL_14:
      v12 = v9;
      goto LABEL_22;
    }
  }
  else
  {
    v6 = 0;
  }
  v13 = NtDCompositionSetChildRootVisual(a1, hObject[0]);
  if ( v13 >= 0 )
    goto LABEL_23;
  v15 = 1125;
  v6 = v13 | 0x10000000;
  v12 = v13 | 0x10000000;
LABEL_22:
  MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A160, 2u, v12, v15, v16);
LABEL_23:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  return v6;
}

```

## disassembly

```asm
0x180014190  push    rbp
0x180014192  push    rbx
0x180014193  push    rsi
0x180014194  push    rdi
0x180014195  mov     rbp, rsp
0x180014198  sub     rsp, 58h
0x18001419c  mov     rdi, r8
0x18001419f  mov     [rbp+arg_18], 0
0x1800141a7  mov     rbx, rdx
0x1800141aa  mov     [rbp+var_28], 0
0x1800141b2  mov     rsi, rcx
0x1800141b5  mov     [rbp+var_20], 0
0x1800141bd  mov     [rbp+hObject], 0
0x1800141c5  call    ?IsHwndInProcess@@YA_NPEAUHWND__@@@Z; IsHwndInProcess(HWND__ *)
0x1800141ca  test    al, al
0x1800141cc  jnz     short loc_1800141E4
0x1800141ce  mov     r9d, 80070057h
0x1800141d4  mov     [rsp+58h+var_38], 441h
0x1800141dc  mov     ebx, r9d
0x1800141df  jmp     loc_18001433F
0x1800141e4  test    rdi, rdi
0x1800141e7  jz      loc_18001431B
0x1800141ed  mov     rdx, [rbx]
0x1800141f0  lea     rcx, [rbp+arg_18]
0x1800141f4  call    ??$IID_PPV_ARGS_Helper@UICompositorInternal@Internal@Composition@UI@Windows@@@@YAPEAPEAXPEAPEAUICompositorInternal@Internal@Composition@UI@Windows@@@Z; IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(Windows::UI::Composition::Internal::ICompositorInternal * *)
0x1800141f9  mov     r8, rax
0x1800141fc  mov     rcx, rbx
0x1800141ff  mov     rax, [rdx]
0x180014202  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x180014209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001420e  mov     ebx, eax
0x180014210  test    eax, eax
0x180014212  js      loc_180014311
0x180014218  cmp     [rbp+arg_18], 0
0x18001421d  jnz     short loc_180014235
0x18001421f  mov     r9d, 80070057h
0x180014225  mov     [rsp+58h+var_38], 44Eh
0x18001422d  mov     ebx, r9d
0x180014230  jmp     loc_18001433F
0x180014235  mov     rdx, [rdi]
0x180014238  lea     rcx, [rbp+var_20]
0x18001423c  call    ??$IID_PPV_ARGS_Helper@UICompositorInternal@Internal@Composition@UI@Windows@@@@YAPEAPEAXPEAPEAUICompositorInternal@Internal@Composition@UI@Windows@@@Z; IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(Windows::UI::Composition::Internal::ICompositorInternal * *)
0x180014241  mov     r8, rax
0x180014244  mov     rcx, rdi
0x180014247  mov     rax, [rdx]
0x18001424a  lea     rdx, _GUID_e8de1639_4331_4b26_bc5f_6a321d347a85
0x180014251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014256  mov     ebx, eax
0x180014258  test    eax, eax
0x18001425a  js      loc_180014307
0x180014260  cmp     [rbp+var_20], 0
0x180014265  jnz     short loc_18001427D
0x180014267  mov     r9d, 80070057h
0x18001426d  mov     [rsp+58h+var_38], 455h
0x180014275  mov     ebx, r9d
0x180014278  jmp     loc_18001433F
0x18001427d  mov     rcx, [rbp+arg_18]
0x180014281  lea     r8, [rbp+var_28]
0x180014285  lea     rdx, _GUID_e8de1639_4331_4b26_bc5f_6a321d347a85
0x18001428c  mov     rax, [rcx]
0x18001428f  mov     rax, [rax+0D8h]
0x180014296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001429b  mov     ebx, eax
0x18001429d  test    eax, eax
0x18001429f  js      short loc_1800142FD
0x1800142a1  mov     rcx, [rbp+arg_18]
0x1800142a5  lea     r8, [rbp+hObject]
0x1800142a9  mov     rdx, [rbp+var_28]
0x1800142ad  mov     rax, [rcx]
0x1800142b0  mov     rax, [rax+0E0h]
0x1800142b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142bc  mov     ebx, eax
0x1800142be  test    eax, eax
0x1800142c0  js      short loc_1800142F3
0x1800142c2  mov     rcx, [rbp+var_20]
0x1800142c6  xor     r9d, r9d
0x1800142c9  mov     rdx, [rbp+var_28]
0x1800142cd  mov     rax, [rcx]
0x1800142d0  lea     r8d, [r9+1]
0x1800142d4  mov     rax, [rax+80h]
0x1800142db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e0  mov     ebx, eax
0x1800142e2  test    eax, eax
0x1800142e4  jns     short loc_18001431D
0x1800142e6  mov     [rsp+58h+var_38], 461h
0x1800142ee  mov     r9d, eax
0x1800142f1  jmp     short loc_18001433F
0x1800142f3  mov     [rsp+58h+var_38], 45Eh
0x1800142fb  jmp     short loc_1800142EE
0x1800142fd  mov     [rsp+58h+var_38], 45Bh
0x180014305  jmp     short loc_1800142EE
0x180014307  mov     [rsp+58h+var_38], 452h
0x18001430f  jmp     short loc_1800142EE
0x180014311  mov     [rsp+58h+var_38], 44Bh
0x180014319  jmp     short loc_1800142EE
0x18001431b  xor     ebx, ebx
0x18001431d  mov     rdx, [rbp+hObject]
0x180014321  mov     rcx, rsi
0x180014324  call    cs:__imp_NtDCompositionSetChildRootVisual
0x18001432a  test    eax, eax
0x18001432c  jns     short loc_180014355
0x18001432e  mov     ebx, eax
0x180014330  mov     [rsp+58h+var_38], 465h; unsigned int
0x180014338  bts     ebx, 1Ch
0x18001433c  mov     r9d, ebx; int
0x18001433f  mov     r8d, 2; unsigned int
0x180014345  lea     rdx, qword_18001A160; int *
0x18001434c  lea     ecx, [r8+2]; unsigned int
0x180014350  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180014355  mov     rcx, [rbp+var_28]
0x180014359  test    rcx, rcx
0x18001435c  jz      short loc_18001436A
0x18001435e  mov     rax, [rcx]
0x180014361  mov     rax, [rax+10h]
0x180014365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001436a  mov     rcx, [rbp+var_20]
0x18001436e  test    rcx, rcx
0x180014371  jz      short loc_18001437F
0x180014373  mov     rax, [rcx]
0x180014376  mov     rax, [rax+10h]
0x18001437a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001437f  mov     rcx, [rbp+arg_18]
0x180014383  test    rcx, rcx
0x180014386  jz      short loc_180014394
0x180014388  mov     rax, [rcx]
0x18001438b  mov     rax, [rax+10h]
0x18001438f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014394  mov     rcx, [rbp+hObject]; hObject
0x180014398  test    rcx, rcx
0x18001439b  jz      short loc_1800143A3
0x18001439d  call    cs:__imp_CloseHandle
0x1800143a3  mov     eax, ebx
0x1800143a5  add     rsp, 58h
0x1800143a9  pop     rdi
0x1800143aa  pop     rsi
0x1800143ab  pop     rbx
0x1800143ac  pop     rbp
0x1800143ad  retn
```
