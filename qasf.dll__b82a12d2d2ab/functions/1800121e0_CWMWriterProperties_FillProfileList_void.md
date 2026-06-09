# CWMWriterProperties::FillProfileList(void)

- ea: `0x1800121e0`
- end: `0x18001250c`
- name: `?FillProfileList@CWMWriterProperties@@AEAAXXZ`
- size: `812`
- prototype: `void __fastcall(CWMWriterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180012c00`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001460`
- `0x18000259c`
- `0x180002660`
- `0x1800121e0`
- `0x18001f010`

## import_xrefs

- `WMVCore!WMCreateProfileManager` at `0x180012218`
- `WMVCore!WMCreateProfileManager` at `0x180012218`
- `GDI32!GetTextExtentPointW` at `0x180012422`
- `GDI32!GetTextExtentPointW` at `0x180012422`
- `USER32!GetDC` at `0x18001228d`
- `USER32!GetDC` at `0x18001228d`
- `USER32!SendMessageW` at `0x180012444`
- `USER32!SendMessageW` at `0x1800124b2`
- `USER32!SendMessageW` at `0x1800124c7`
- `USER32!SendMessageW` at `0x180012444`
- `USER32!SendMessageW` at `0x1800124b2`
- `USER32!SendMessageW` at `0x1800124c7`
- `USER32!ReleaseDC` at `0x1800124d4`
- `USER32!ReleaseDC` at `0x1800124d4`

## pseudocode

```c
void __fastcall CWMWriterProperties::FillProfileList(HWND *this)
{
  HRESULT v2; // eax
  IWMProfileManager *v3; // rcx
  HDC DC; // r13
  LONG v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r12
  int v12; // eax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r15
  unsigned __int64 v15; // r14
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rdi
  __int64 v18; // r8
  LONG cx; // eax
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  LONG v23; // [rsp+20h] [rbp-48h]
  unsigned int v24; // [rsp+24h] [rbp-44h] BYREF
  int v25; // [rsp+28h] [rbp-40h] BYREF
  __int64 v26; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+38h] [rbp-30h] BYREF
  IWMProfileManager *ppProfileManager; // [rsp+40h] [rbp-28h] BYREF
  int v29; // [rsp+48h] [rbp-20h] BYREF
  tagSIZE sz; // [rsp+50h] [rbp-18h] BYREF

  sz = 0;
  v29 = 0;
  ppProfileManager = 0;
  v2 = WMCreateProfileManager(&ppProfileManager);
  v3 = ppProfileManager;
  if ( v2 >= 0 )
  {
    v26 = 0;
    if ( ((__int64 (__fastcall *)(IWMProfileManager *, GUID *, __int64 *))ppProfileManager->lpVtbl->QueryInterface)(
           ppProfileManager,
           &IID_IWMProfileManager2,
           &v26) >= 0 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 80LL))(v26, 0x80000);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    if ( ((int (__fastcall *)(IWMProfileManager *, int *))ppProfileManager->lpVtbl->GetSystemProfileCount)(
           ppProfileManager,
           &v29) >= 0 )
    {
      DC = GetDC(this[9]);
      if ( DC )
      {
        v5 = 0;
        v24 = 0;
        v6 = 0;
        v23 = 0;
        v25 = 0;
        if ( v29 > 0 )
        {
          while ( 1 )
          {
            v27 = 0;
            v7 = ((__int64 (__fastcall *)(IWMProfileManager *, _QWORD, __int64 *))ppProfileManager->lpVtbl->LoadSystemProfile)(
                   ppProfileManager,
                   v6,
                   &v27);
            v8 = v27;
            if ( v7 < 0 )
              break;
            if ( (*(int (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v27 + 32LL))(v27, 0, &v24) < 0 )
              goto LABEL_24;
            v9 = v24 + 1;
            if ( (unsigned int)v9 < v24 )
              goto LABEL_24;
            v10 = (unsigned __int16 *)operator new[](saturated_mul(v9, 2u));
            v8 = v27;
            v11 = v10;
            if ( !v10 )
              break;
            v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned int *))(*(_QWORD *)v27 + 32LL))(
                    v27,
                    v10,
                    &v24);
            v8 = v27;
            if ( v12 < 0 )
              break;
            if ( (*(int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v27 + 48LL))(v27, 0, &v25) < 0 )
              goto LABEL_24;
            v13 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)(v25 + 1), 2u));
            v8 = v27;
            v14 = v13;
            if ( !v13 )
              break;
            if ( (*(int (__fastcall **)(__int64, unsigned __int16 *, int *))(*(_QWORD *)v27 + 48LL))(v27, v13, &v25) < 0
              || (v15 = v25 + v24 + 4LL,
                  v16 = (unsigned __int16 *)operator new[](saturated_mul(v15, 2u)),
                  (v17 = v16) == 0) )
            {
LABEL_24:
              v8 = v27;
              break;
            }
            StringCchCopyW(v16, v15, v11);
            StringCchCatW(v17, v15, L" - ");
            StringCchCatW(v17, v15, v14);
            v18 = -1;
            do
              ++v18;
            while ( v17[v18] );
            GetTextExtentPointW(DC, v17, v18, &sz);
            cx = v23;
            if ( sz.cx > v23 )
              cx = sz.cx;
            v23 = cx;
            SendMessageW(this[9], 0x14Au, (int)v6, (LPARAM)v17);
            operator delete(v11, v20);
            operator delete(v14, v21);
            operator delete(v17, v22);
            if ( v27 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            if ( (int)++v6 >= v29 )
              goto LABEL_27;
          }
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_27:
          v5 = v23;
        }
        SendMessageW(this[9], 0x15Eu, v5, 0);
        SendMessageW(this[9], 0x14Eu, 0, 0);
        ReleaseDC(this[9], DC);
      }
    }
    v3 = ppProfileManager;
  }
  if ( v3 )
    ((void (__fastcall *)(IWMProfileManager *))v3->lpVtbl->Release)(v3);
}

```

## disassembly

```asm
0x1800121e0  push    rbp
0x1800121e2  push    rbx
0x1800121e3  push    rsi
0x1800121e4  push    rdi
0x1800121e5  push    r12
0x1800121e7  push    r13
0x1800121e9  push    r14
0x1800121eb  push    r15
0x1800121ed  mov     rbp, rsp
0x1800121f0  sub     rsp, 68h
0x1800121f4  mov     rax, cs:__security_cookie
0x1800121fb  xor     rax, rsp
0x1800121fe  mov     [rbp+var_10], rax
0x180012202  xor     r14d, r14d
0x180012205  mov     rsi, rcx
0x180012208  lea     rcx, [rbp+ppProfileManager]; ppProfileManager
0x18001220c  mov     qword ptr [rbp+sz.cx], r14
0x180012210  mov     [rbp+var_20], r14d
0x180012214  mov     [rbp+ppProfileManager], r14
0x180012218  call    cs:__imp_WMCreateProfileManager
0x18001221e  mov     rcx, [rbp+ppProfileManager]
0x180012222  test    eax, eax
0x180012224  js      loc_1800124DE
0x18001222a  mov     [rbp+var_38], r14
0x18001222e  lea     r8, [rbp+var_38]
0x180012232  mov     rax, [rcx]
0x180012235  lea     rdx, IID_IWMProfileManager2
0x18001223c  mov     rax, [rax]
0x18001223f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012244  test    eax, eax
0x180012246  js      short loc_18001226D
0x180012248  mov     rcx, [rbp+var_38]
0x18001224c  mov     edx, 80000h
0x180012251  mov     rax, [rcx]
0x180012254  mov     rax, [rax+50h]
0x180012258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001225d  mov     rcx, [rbp+var_38]
0x180012261  mov     rax, [rcx]
0x180012264  mov     rax, [rax+10h]
0x180012268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001226d  mov     rcx, [rbp+ppProfileManager]
0x180012271  lea     rdx, [rbp+var_20]
0x180012275  mov     rax, [rcx]
0x180012278  mov     rax, [rax+38h]
0x18001227c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012281  test    eax, eax
0x180012283  js      loc_1800124DA
0x180012289  mov     rcx, [rsi+48h]; hWnd
0x18001228d  call    cs:__imp_GetDC
0x180012293  mov     r13, rax
0x180012296  test    rax, rax
0x180012299  jz      loc_1800124DA
0x18001229f  mov     eax, r14d
0x1800122a2  mov     [rbp+var_44], r14d
0x1800122a6  mov     ebx, r14d
0x1800122a9  mov     [rbp+var_48], eax
0x1800122ac  mov     [rbp+var_40], r14d
0x1800122b0  cmp     [rbp+var_20], r14d
0x1800122b4  jle     loc_1800124A3
0x1800122ba  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800122be  mov     rcx, [rbp+ppProfileManager]
0x1800122c2  lea     r8, [rbp+var_30]
0x1800122c6  mov     [rbp+var_30], r14
0x1800122ca  mov     edx, ebx
0x1800122cc  mov     rax, [rcx]
0x1800122cf  mov     rax, [rax+40h]
0x1800122d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122d8  mov     rcx, [rbp+var_30]
0x1800122dc  test    eax, eax
0x1800122de  js      loc_18001248F
0x1800122e4  mov     rax, [rcx]
0x1800122e7  lea     r8, [rbp+var_44]
0x1800122eb  xor     edx, edx
0x1800122ed  mov     rax, [rax+20h]
0x1800122f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122f6  test    eax, eax
0x1800122f8  js      loc_18001248B
0x1800122fe  mov     eax, [rbp+var_44]
0x180012301  lea     ecx, [rax+1]
0x180012304  cmp     ecx, eax
0x180012306  jb      loc_18001248B
0x18001230c  mov     eax, 2
0x180012311  mul     rcx
0x180012314  cmovb   rax, rdi
0x180012318  mov     rcx, rax; unsigned __int64
0x18001231b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012320  mov     rcx, [rbp+var_30]
0x180012324  mov     r12, rax
0x180012327  test    rax, rax
0x18001232a  jz      loc_18001248F
0x180012330  mov     rdx, [rcx]
0x180012333  lea     r8, [rbp+var_44]
0x180012337  mov     rax, [rdx+20h]
0x18001233b  mov     rdx, r12
0x18001233e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012343  mov     rcx, [rbp+var_30]
0x180012347  test    eax, eax
0x180012349  js      loc_18001248F
0x18001234f  mov     rax, [rcx]
0x180012352  lea     r8, [rbp+var_40]
0x180012356  xor     edx, edx
0x180012358  mov     rax, [rax+30h]
0x18001235c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012361  test    eax, eax
0x180012363  js      loc_18001248B
0x180012369  mov     ecx, [rbp+var_40]
0x18001236c  mov     eax, 2
0x180012371  inc     ecx
0x180012373  mul     rcx
0x180012376  cmovb   rax, rdi
0x18001237a  mov     rcx, rax; unsigned __int64
0x18001237d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012382  mov     rcx, [rbp+var_30]
0x180012386  mov     r15, rax
0x180012389  test    rax, rax
0x18001238c  jz      loc_18001248F
0x180012392  mov     rdx, [rcx]
0x180012395  lea     r8, [rbp+var_40]
0x180012399  mov     rax, [rdx+30h]
0x18001239d  mov     rdx, r15
0x1800123a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123a5  test    eax, eax
0x1800123a7  js      loc_18001248B
0x1800123ad  mov     r14d, [rbp+var_44]
0x1800123b1  mov     eax, 2
0x1800123b6  add     r14d, [rbp+var_40]
0x1800123ba  add     r14, 4
0x1800123be  mul     r14
0x1800123c1  cmovb   rax, rdi
0x1800123c5  mov     rcx, rax; unsigned __int64
0x1800123c8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800123cd  mov     rdi, rax
0x1800123d0  test    rax, rax
0x1800123d3  jz      loc_18001248B
0x1800123d9  mov     r8, r12; unsigned __int16 *
0x1800123dc  mov     rdx, r14; unsigned __int64
0x1800123df  mov     rcx, rax; unsigned __int16 *
0x1800123e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800123e7  lea     r8, asc_180023530; " - "
0x1800123ee  mov     rdx, r14; unsigned __int64
0x1800123f1  mov     rcx, rdi; unsigned __int16 *
0x1800123f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800123f9  mov     r8, r15; unsigned __int16 *
0x1800123fc  mov     rdx, r14; unsigned __int64
0x1800123ff  mov     rcx, rdi; unsigned __int16 *
0x180012402  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012407  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001240b  xor     r14d, r14d
0x18001240e  inc     r8; c
0x180012411  cmp     [rdi+r8*2], r14w
0x180012416  jnz     short loc_18001240E
0x180012418  lea     r9, [rbp+sz]; lpsz
0x18001241c  mov     rdx, rdi; lpString
0x18001241f  mov     rcx, r13; hdc
0x180012422  call    cs:__imp_GetTextExtentPointW
0x180012428  mov     eax, [rbp+var_48]
0x18001242b  mov     r9, rdi; lParam
0x18001242e  cmp     [rbp+sz.cx], eax
0x180012431  mov     edx, 14Ah; Msg
0x180012436  mov     rcx, [rsi+48h]; hWnd
0x18001243a  cmovg   eax, [rbp+sz.cx]
0x18001243e  movsxd  r8, ebx; wParam
0x180012441  mov     [rbp+var_48], eax
0x180012444  call    cs:__imp_SendMessageW
0x18001244a  mov     rcx, r12; void *
0x18001244d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012452  mov     rcx, r15; void *
0x180012455  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001245a  mov     rcx, rdi; void *
0x18001245d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012462  mov     rcx, [rbp+var_30]
0x180012466  test    rcx, rcx
0x180012469  jz      short loc_180012477
0x18001246b  mov     rax, [rcx]
0x18001246e  mov     rax, [rax+10h]
0x180012472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012477  inc     ebx
0x180012479  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180012480  cmp     ebx, [rbp+var_20]
0x180012483  jl      loc_1800122BE
0x180012489  jmp     short loc_1800124A0
0x18001248b  mov     rcx, [rbp+var_30]
0x18001248f  test    rcx, rcx
0x180012492  jz      short loc_1800124A0
0x180012494  mov     rax, [rcx]
0x180012497  mov     rax, [rax+10h]
0x18001249b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124a0  mov     eax, [rbp+var_48]
0x1800124a3  mov     rcx, [rsi+48h]; hWnd
0x1800124a7  xor     r9d, r9d; lParam
0x1800124aa  movsxd  r8, eax; wParam
0x1800124ad  mov     edx, 15Eh; Msg
0x1800124b2  call    cs:__imp_SendMessageW
0x1800124b8  mov     rcx, [rsi+48h]; hWnd
0x1800124bc  xor     r9d, r9d; lParam
0x1800124bf  xor     r8d, r8d; wParam
0x1800124c2  mov     edx, 14Eh; Msg
0x1800124c7  call    cs:__imp_SendMessageW
0x1800124cd  mov     rcx, [rsi+48h]; hWnd
0x1800124d1  mov     rdx, r13; hDC
0x1800124d4  call    cs:__imp_ReleaseDC
0x1800124da  mov     rcx, [rbp+ppProfileManager]
0x1800124de  test    rcx, rcx
0x1800124e1  jz      short loc_1800124EF
0x1800124e3  mov     rax, [rcx]
0x1800124e6  mov     rax, [rax+10h]
0x1800124ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124ef  mov     rcx, [rbp+var_10]
0x1800124f3  xor     rcx, rsp; StackCookie
0x1800124f6  call    __security_check_cookie
0x1800124fb  add     rsp, 68h
0x1800124ff  pop     r15
0x180012501  pop     r14
0x180012503  pop     r13
0x180012505  pop     r12
0x180012507  pop     rdi
0x180012508  pop     rsi
0x180012509  pop     rbx
0x18001250a  pop     rbp
0x18001250b  retn
```
