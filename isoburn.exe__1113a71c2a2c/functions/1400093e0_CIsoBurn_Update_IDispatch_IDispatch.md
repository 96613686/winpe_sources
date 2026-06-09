# CIsoBurn::Update(IDispatch *,IDispatch *)

- ea: `0x1400093e0`
- end: `0x14000963f`
- name: `?Update@CIsoBurn@@UEAAXPEAUIDispatch@@0@Z`
- size: `607`
- prototype: `void __fastcall(CIsoBurn *__hidden this, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1400093e0`
- `0x140010010`

## pseudocode

```c
void __fastcall CIsoBurn::Update(CIsoBurn *this, struct IDispatch *a2, struct IDispatch *a3)
{
  HRESULT (__stdcall *QueryInterface)(IDispatch *, const IID *const, void **); // rax
  __int64 v6; // rdx
  int v7; // r9d
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  struct IDispatchVtbl *lpVtbl; // rax
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-10h] BYREF
  int v14; // [rsp+24h] [rbp-Ch] BYREF
  __int64 v15; // [rsp+28h] [rbp-8h] BYREF
  int v16; // [rsp+60h] [rbp+30h] BYREF
  __int64 v17; // [rsp+68h] [rbp+38h] BYREF

  QueryInterface = a3->lpVtbl->QueryInterface;
  v13 = 0;
  v15 = 0;
  if ( ((int (__fastcall *)(struct IDispatch *, GUID *, __int64 *))QueryInterface)(
         a3,
         &GUID_2735413d_7f64_5b0f_8f00_5d77afbe261e,
         &v15) < 0
    || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 136LL))(v15, &v13) < 0 )
  {
    goto LABEL_25;
  }
  if ( v13 != 4 )
  {
    if ( v13 == 5 )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 19) + 24LL))(*((_QWORD *)this + 19), 3);
      *((_DWORD *)this + 40) = 0;
      goto LABEL_20;
    }
    if ( v13 != 7 )
      goto LABEL_20;
    LODWORD(v17) = 0;
    v16 = 0;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 112LL))(v15, &v16);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 128LL))(v15, &v17);
    if ( *((_DWORD *)this + 40) )
    {
      v7 = v16;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 19) + 24LL))(*((_QWORD *)this + 19), 4);
      v7 = v16;
      *((_DWORD *)this + 41) = v16;
      *((_DWORD *)this + 40) = 1;
    }
    v8 = *((_DWORD *)this + 41);
    v9 = v17 - v8;
    if ( (int)v17 - v8 <= 0 )
      goto LABEL_20;
    v10 = v7 - v8;
    LODWORD(v17) = v17 - v8;
    v16 = v10;
    if ( v10 >= v9 - (v9 + 99) / 100 )
    {
      v10 = v9 - (v9 + 99) / 100;
      v16 = v10;
    }
    v6 = (unsigned int)v10;
    goto LABEL_19;
  }
  v14 = 0;
  LODWORD(v17) = 0;
  v16 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 56LL))(v15, &v14) < 0
    || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 80LL))(v15, &v17) < 0
    || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 64LL))(v15, &v16) < 0 )
  {
    goto LABEL_25;
  }
  if ( v16 > 0 )
  {
    v6 = (unsigned int)(v17 - v14 + 1);
LABEL_19:
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 19) + 32LL))(*((_QWORD *)this + 19), v6);
  }
LABEL_20:
  lpVtbl = a2->lpVtbl;
  v17 = 0;
  if ( ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &GUID_27354153_9f64_5b0f_8f00_5d77afbe261e,
         &v17) >= 0 )
  {
    v12 = *((_QWORD *)this + 19);
    v16 = 0;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 48LL))(v12, &v16);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 336LL))(v17);
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_25:
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
}

```

## disassembly

```asm
0x1400093e0  mov     [rsp-18h+arg_0], rbx
0x1400093e5  push    rbp
0x1400093e6  push    rsi
0x1400093e7  push    rdi
0x1400093e8  mov     rbp, rsp
0x1400093eb  sub     rsp, 30h
0x1400093ef  mov     rax, [r8]
0x1400093f2  mov     r9, r8
0x1400093f5  mov     rdi, rdx
0x1400093f8  lea     r8, [rbp+var_8]
0x1400093fc  mov     rbx, rcx
0x1400093ff  lea     rdx, _GUID_2735413d_7f64_5b0f_8f00_5d77afbe261e
0x140009406  xor     esi, esi
0x140009408  mov     rcx, r9
0x14000940b  mov     rax, [rax]
0x14000940e  mov     [rbp+var_10], esi
0x140009411  mov     [rbp+var_8], rsi
0x140009415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000941a  test    eax, eax
0x14000941c  js      loc_14000961D
0x140009422  mov     rcx, [rbp+var_8]
0x140009426  lea     rdx, [rbp+var_10]
0x14000942a  mov     rax, [rcx]
0x14000942d  mov     rax, [rax+88h]
0x140009434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009439  test    eax, eax
0x14000943b  js      loc_14000961D
0x140009441  mov     eax, [rbp+var_10]
0x140009444  cmp     eax, 4
0x140009447  jnz     short loc_1400094C0
0x140009449  mov     rcx, [rbp+var_8]
0x14000944d  lea     rdx, [rbp+var_C]
0x140009451  mov     [rbp+var_C], esi
0x140009454  mov     dword ptr [rbp+arg_18], esi
0x140009457  mov     [rbp+arg_10], esi
0x14000945a  mov     rax, [rcx]
0x14000945d  mov     rax, [rax+38h]
0x140009461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009466  test    eax, eax
0x140009468  js      loc_14000961D
0x14000946e  mov     rcx, [rbp+var_8]
0x140009472  lea     rdx, [rbp+arg_18]
0x140009476  mov     rax, [rcx]
0x140009479  mov     rax, [rax+50h]
0x14000947d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009482  test    eax, eax
0x140009484  js      loc_14000961D
0x14000948a  mov     rcx, [rbp+var_8]
0x14000948e  lea     rdx, [rbp+arg_10]
0x140009492  mov     rax, [rcx]
0x140009495  mov     rax, [rax+40h]
0x140009499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000949e  test    eax, eax
0x1400094a0  js      loc_14000961D
0x1400094a6  mov     r8d, [rbp+arg_10]
0x1400094aa  test    r8d, r8d
0x1400094ad  jle     loc_1400095B5
0x1400094b3  mov     edx, dword ptr [rbp+arg_18]
0x1400094b6  sub     edx, [rbp+var_C]
0x1400094b9  inc     edx
0x1400094bb  jmp     loc_1400095A2
0x1400094c0  cmp     eax, 5
0x1400094c3  jnz     short loc_1400094E8
0x1400094c5  mov     rcx, [rbx+98h]
0x1400094cc  mov     edx, 3
0x1400094d1  mov     rax, [rcx]
0x1400094d4  mov     rax, [rax+18h]
0x1400094d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094dd  mov     [rbx+0A0h], esi
0x1400094e3  jmp     loc_1400095B5
0x1400094e8  cmp     eax, 7
0x1400094eb  jnz     loc_1400095B5
0x1400094f1  mov     rcx, [rbp+var_8]
0x1400094f5  lea     rdx, [rbp+arg_10]
0x1400094f9  mov     dword ptr [rbp+arg_18], esi
0x1400094fc  mov     [rbp+arg_10], esi
0x1400094ff  mov     rax, [rcx]
0x140009502  mov     rax, [rax+70h]
0x140009506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000950b  mov     rcx, [rbp+var_8]
0x14000950f  lea     rdx, [rbp+arg_18]
0x140009513  mov     rax, [rcx]
0x140009516  mov     rax, [rax+80h]
0x14000951d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009522  cmp     [rbx+0A0h], esi
0x140009528  jnz     short loc_140009559
0x14000952a  mov     rcx, [rbx+98h]
0x140009531  mov     edx, 4
0x140009536  mov     rax, [rcx]
0x140009539  mov     rax, [rax+18h]
0x14000953d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009542  mov     r9d, [rbp+arg_10]
0x140009546  mov     [rbx+0A4h], r9d
0x14000954d  mov     dword ptr [rbx+0A0h], 1
0x140009557  jmp     short loc_14000955D
0x140009559  mov     r9d, [rbp+arg_10]
0x14000955d  mov     r8d, dword ptr [rbp+arg_18]
0x140009561  mov     eax, [rbx+0A4h]
0x140009567  sub     r8d, eax
0x14000956a  test    r8d, r8d
0x14000956d  jle     short loc_1400095B5
0x14000956f  sub     r9d, eax
0x140009572  mov     dword ptr [rbp+arg_18], r8d
0x140009576  mov     eax, 51EB851Fh
0x14000957b  mov     [rbp+arg_10], r9d
0x14000957f  lea     ecx, [r8+63h]
0x140009583  imul    ecx
0x140009585  sar     edx, 5
0x140009588  mov     eax, edx
0x14000958a  shr     eax, 1Fh
0x14000958d  add     edx, eax
0x14000958f  mov     eax, r8d
0x140009592  sub     eax, edx
0x140009594  cmp     r9d, eax
0x140009597  jl      short loc_14000959F
0x140009599  mov     r9d, eax
0x14000959c  mov     [rbp+arg_10], eax
0x14000959f  mov     edx, r9d
0x1400095a2  mov     rcx, [rbx+98h]
0x1400095a9  mov     rax, [rcx]
0x1400095ac  mov     rax, [rax+20h]
0x1400095b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095b5  mov     rax, [rdi]
0x1400095b8  lea     r8, [rbp+arg_18]
0x1400095bc  lea     rdx, _GUID_27354153_9f64_5b0f_8f00_5d77afbe261e
0x1400095c3  mov     [rbp+arg_18], rsi
0x1400095c7  mov     rcx, rdi
0x1400095ca  mov     rax, [rax]
0x1400095cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095d2  test    eax, eax
0x1400095d4  js      short loc_140009608
0x1400095d6  mov     rcx, [rbx+98h]
0x1400095dd  lea     rdx, [rbp+arg_10]
0x1400095e1  mov     [rbp+arg_10], esi
0x1400095e4  mov     rax, [rcx]
0x1400095e7  mov     rax, [rax+30h]
0x1400095eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095f0  cmp     [rbp+arg_10], esi
0x1400095f3  jz      short loc_140009608
0x1400095f5  mov     rcx, [rbp+arg_18]
0x1400095f9  mov     rax, [rcx]
0x1400095fc  mov     rax, [rax+150h]
0x140009603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009608  mov     rcx, [rbp+arg_18]
0x14000960c  test    rcx, rcx
0x14000960f  jz      short loc_14000961D
0x140009611  mov     rax, [rcx]
0x140009614  mov     rax, [rax+10h]
0x140009618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000961d  mov     rcx, [rbp+var_8]
0x140009621  test    rcx, rcx
0x140009624  jz      short loc_140009632
0x140009626  mov     rax, [rcx]
0x140009629  mov     rax, [rax+10h]
0x14000962d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009632  mov     rbx, [rsp+30h+arg_0]
0x140009637  add     rsp, 30h
0x14000963b  pop     rdi
0x14000963c  pop     rsi
0x14000963d  pop     rbp
0x14000963e  retn
```
