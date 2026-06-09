# CLstBxWinHost::Init(HWND__ *,tagCREATESTRUCTW const *)

- ea: `0x180068690`
- end: `0x18006897a`
- name: `?Init@CLstBxWinHost@@UEAAHPEAUHWND__@@PEBUtagCREATESTRUCTW@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, HWND hWnd, const struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18005d7c8`
- `0x1800616e8`
- `0x180068690`
- `0x1800932f4`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x1800686d9`
- `USER32!SetWindowLongPtrW` at `0x1800686d9`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::Init(CLstBxWinHost *this, HWND hWnd, const struct tagCREATESTRUCTW *a3)
{
  LONG style; // eax
  LPVOID lpCreateParams; // rcx
  int *v8; // rdi
  int v9; // ecx
  __int64 result; // rax
  int v11; // r8d
  HWND v12; // rcx
  int v13; // r8d
  unsigned int v14; // edx
  int v15; // ecx
  unsigned int v16; // ecx
  int v17; // eax
  unsigned int v18; // edx
  int v19; // eax
  CTxtEdit *v20; // rcx
  bool v21; // zf
  int v22; // eax
  __int64 v23; // rcx
  int v24; // [rsp+30h] [rbp-C8h] BYREF
  int v25; // [rsp+34h] [rbp-C4h]
  __int16 v26; // [rsp+3Ah] [rbp-BEh]
  __int16 v27; // [rsp+48h] [rbp-B0h]

  if ( !a3->lpszClass )
    return 0;
  if ( hWnd )
    SetWindowLongPtrW(hWnd, 0, (LONG_PTR)this);
  *((_DWORD *)this + 13) |= 0x20u;
  *((_QWORD *)this + 2) = hWnd;
  *((_QWORD *)this + 3) = a3->hwndParent;
  *((_DWORD *)this + 12) = a3->dwExStyle;
  style = a3->style;
  *((_DWORD *)this + 11) = style;
  if ( (style & 0x8000) != 0 )
  {
    if ( a3->hMenu != (HMENU)1000 )
      return 0xFFFFFFFFLL;
    lpCreateParams = a3->lpCreateParams;
    if ( !a3->lpCreateParams )
      return 0xFFFFFFFFLL;
    *((_QWORD *)this + 286) = lpCreateParams;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpCreateParams + 8LL))(lpCreateParams);
    v8 = (int *)((char *)this + 128);
    *((_DWORD *)this + 33) = 8;
    *((_DWORD *)this + 32) |= 0x20u;
    v9 = *((_DWORD *)this + 32);
  }
  else
  {
    v8 = (int *)((char *)this + 128);
    *((_DWORD *)this + 32) &= ~0x20u;
    v9 = *((_DWORD *)this + 32);
    if ( (style & 0x800) != 0 )
    {
      *((_DWORD *)this + 33) = 3;
    }
    else if ( (style & 8) != 0 )
    {
      *((_DWORD *)this + 33) = 2;
    }
    else
    {
      v9 |= 0x20u;
      *((_DWORD *)this + 33) = 1;
      *v8 = v9;
    }
  }
  v11 = *((_DWORD *)this + 11);
  *v8 = v9 ^ ((unsigned __int8)v9 ^ (unsigned __int8)(16 * v11)) & 0x10;
  if ( (v11 & 0x40) == 0 )
  {
    v12 = (HWND)*((_QWORD *)this + 2);
    v13 = v11 | 0x40;
    *((_DWORD *)this + 11) = v13;
    CW32System::SetWindowLong(v12, (int)hWnd, v13);
  }
  *v8 &= ~8u;
  v14 = *((_DWORD *)this + 11);
  v15 = *v8;
  if ( (v14 & 0x1000) != 0 )
  {
    v15 |= 8u;
    *v8 = v15;
    v14 |= 0x2000u;
  }
  *((_DWORD *)this + 13) &= ~1u;
  v16 = v15 & 0xFFFFFFFA | (v14 >> 6) & 4 | (v14 >> 4) & 1;
  v17 = v14 & 2;
  v18 = v14 & 0xFFEFFFFF;
  *((_DWORD *)this + 11) = v18;
  *v8 = v17 | v16 & 0xFFFFFFFD;
  *((_DWORD *)this + 13) |= (v18 >> 23) & 1;
  v19 = *((_DWORD *)this + 13);
  if ( (*((_DWORD *)this + 12) & 0x200) != 0 )
  {
    v19 |= 1u;
    *((_DWORD *)this + 13) = v19;
  }
  if ( (v18 & 0x8000000) != 0 )
    *((_DWORD *)this + 13) = v19 | 0x800;
  if ( (int)CTxtWinHost::CreateTextServices(this) < 0 )
    return 0;
  v20 = (CTxtEdit *)*((_QWORD *)this + 4);
  *((_WORD *)this + 51) = 0;
  CTxtEdit::HandleSetUndoLimit(v20, 0);
  memset_0(&v24, 0, 0x9Cu);
  v21 = (*((_DWORD *)this + 12) & 0x1000) == 0;
  v22 = 0;
  v25 = 0;
  if ( !v21 )
  {
    v22 = 8;
    v27 = 2;
    v25 = 8;
  }
  if ( (*((_DWORD *)this + 12) & 0x2000) != 0 )
  {
    v22 |= 0x10000u;
    v26 = 1;
    v25 = v22;
  }
  if ( v22 )
  {
    v23 = *((_QWORD *)this + 4);
    v24 = 188;
    (*(void (__fastcall **)(__int64, __int64, __int64, int *, _QWORD))(*(_QWORD *)v23 + 24LL))(v23, 1095, 4, &v24, 0);
  }
  (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1228,
    4,
    4,
    0);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1228,
    0,
    128,
    0);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1144,
    0,
    50,
    0);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1192,
    0,
    0,
    0);
  result = 1;
  *(_QWORD *)((char *)this + 60) = 0;
  *(_QWORD *)((char *)this + 68) = 0;
  return result;
}

```

## disassembly

```asm
0x180068690  mov     [rsp+arg_10], rbx
0x180068695  mov     [rsp+arg_18], rbp
0x18006869a  push    rsi
0x18006869b  push    rdi
0x18006869c  push    r13
0x18006869e  sub     rsp, 0E0h
0x1800686a5  mov     rax, cs:__security_cookie
0x1800686ac  xor     rax, rsp
0x1800686af  mov     [rsp+0F8h+var_28], rax
0x1800686b7  xor     ebp, ebp
0x1800686b9  mov     rdi, r8
0x1800686bc  mov     rsi, rdx
0x1800686bf  mov     rbx, rcx
0x1800686c2  cmp     [r8+40h], rbp
0x1800686c6  jz      loc_18006894F
0x1800686cc  test    rdx, rdx
0x1800686cf  jz      short loc_1800686E5
0x1800686d1  mov     r8, rcx; dwNewLong
0x1800686d4  xor     edx, edx; nIndex
0x1800686d6  mov     rcx, rsi; hWnd
0x1800686d9  call    cs:__imp_SetWindowLongPtrW
0x1800686e0  nop     dword ptr [rax+rax+00h]
0x1800686e5  or      dword ptr [rbx+34h], 20h
0x1800686e9  mov     [rbx+10h], rsi
0x1800686ed  mov     esi, 1
0x1800686f2  mov     rax, [rdi+18h]
0x1800686f6  mov     [rbx+18h], rax
0x1800686fa  mov     eax, [rdi+48h]
0x1800686fd  mov     [rbx+30h], eax
0x180068700  lea     r13d, [rsi+1]
0x180068704  mov     eax, [rdi+30h]
0x180068707  mov     [rbx+2Ch], eax
0x18006870a  bt      eax, 0Fh
0x18006870e  jnb     short loc_180068755
0x180068710  cmp     qword ptr [rdi+10h], 3E8h
0x180068718  jnz     short loc_18006874D
0x18006871a  mov     rcx, [rdi]
0x18006871d  test    rcx, rcx
0x180068720  jz      short loc_18006874D
0x180068722  mov     [rbx+8F0h], rcx
0x180068729  mov     rax, [rcx]
0x18006872c  mov     rax, [rax+8]
0x180068730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068735  lea     rdi, [rbx+80h]
0x18006873c  mov     dword ptr [rbx+84h], 8
0x180068746  or      dword ptr [rdi], 20h
0x180068749  mov     ecx, [rdi]
0x18006874b  jmp     short loc_18006878B
0x18006874d  or      eax, 0FFFFFFFFh
0x180068750  jmp     loc_180068951
0x180068755  lea     rdi, [rbx+80h]
0x18006875c  and     dword ptr [rdi], 0FFFFFFDFh
0x18006875f  mov     ecx, [rdi]
0x180068761  bt      eax, 0Bh
0x180068765  jnb     short loc_180068773
0x180068767  mov     dword ptr [rbx+84h], 3
0x180068771  jmp     short loc_18006878B
0x180068773  test    al, 8
0x180068775  jz      short loc_180068780
0x180068777  mov     [rbx+84h], r13d
0x18006877e  jmp     short loc_18006878B
0x180068780  or      ecx, 20h
0x180068783  mov     [rbx+84h], esi
0x180068789  mov     [rdi], ecx
0x18006878b  mov     r8d, [rbx+2Ch]
0x18006878f  mov     eax, r8d
0x180068792  shl     eax, 4
0x180068795  xor     eax, ecx
0x180068797  and     eax, 10h
0x18006879a  xor     eax, ecx
0x18006879c  mov     [rdi], eax
0x18006879e  test    r8b, 40h
0x1800687a2  jnz     short loc_1800687B5
0x1800687a4  mov     rcx, [rbx+10h]; HWND
0x1800687a8  or      r8d, 40h; int
0x1800687ac  mov     [rbx+2Ch], r8d
0x1800687b0  call    ?SetWindowLong@CW32System@@SAJPEAUHWND__@@HJ@Z; CW32System::SetWindowLong(HWND__ *,int,long)
0x1800687b5  and     dword ptr [rdi], 0FFFFFFF7h
0x1800687b8  mov     edx, [rbx+2Ch]
0x1800687bb  mov     ecx, [rdi]
0x1800687bd  bt      edx, 0Ch
0x1800687c1  jnb     short loc_1800687CC
0x1800687c3  or      ecx, 8
0x1800687c6  mov     [rdi], ecx
0x1800687c8  bts     edx, 0Dh
0x1800687cc  and     ecx, 0FFFFFFFBh
0x1800687cf  mov     eax, edx
0x1800687d1  shr     eax, 6
0x1800687d4  mov     r8d, 0FFFFFFFEh
0x1800687da  and     [rbx+34h], r8d
0x1800687de  and     eax, 4
0x1800687e1  or      eax, ecx
0x1800687e3  mov     ecx, edx
0x1800687e5  and     eax, r8d
0x1800687e8  shr     ecx, 4
0x1800687eb  and     ecx, esi
0x1800687ed  or      ecx, eax
0x1800687ef  mov     eax, edx
0x1800687f1  and     eax, r13d
0x1800687f4  btr     edx, 14h
0x1800687f8  and     ecx, 0FFFFFFFDh
0x1800687fb  mov     [rbx+2Ch], edx
0x1800687fe  or      ecx, eax
0x180068800  mov     eax, edx
0x180068802  shr     eax, 17h
0x180068805  and     eax, esi
0x180068807  mov     [rdi], ecx
0x180068809  or      [rbx+34h], eax
0x18006880c  test    dword ptr [rbx+30h], 200h
0x180068813  mov     eax, [rbx+34h]
0x180068816  jz      short loc_18006881D
0x180068818  or      eax, esi
0x18006881a  mov     [rbx+34h], eax
0x18006881d  bt      edx, 1Bh
0x180068821  jnb     short loc_18006882A
0x180068823  bts     eax, 0Bh
0x180068827  mov     [rbx+34h], eax
0x18006882a  mov     rcx, rbx; this
0x18006882d  call    ?CreateTextServices@CTxtWinHost@@QEAAJXZ; CTxtWinHost::CreateTextServices(void)
0x180068832  test    eax, eax
0x180068834  js      loc_18006894F
0x18006883a  mov     rcx, [rbx+20h]; this
0x18006883e  xor     edx, edx; int
0x180068840  mov     [rbx+66h], bp
0x180068844  call    ?HandleSetUndoLimit@CTxtEdit@@QEAA_JJ@Z; CTxtEdit::HandleSetUndoLimit(long)
0x180068849  xor     edx, edx; Val
0x18006884b  lea     rcx, [rsp+0F8h+var_C8]; void *
0x180068850  mov     r8d, 9Ch; Size
0x180068856  call    memset_0
0x18006885b  test    dword ptr [rbx+30h], 1000h
0x180068862  mov     eax, ebp
0x180068864  mov     [rsp+0F8h+var_C4], eax
0x180068868  jz      short loc_180068879
0x18006886a  mov     eax, 8
0x18006886f  mov     [rsp+0F8h+var_B0], r13w
0x180068875  mov     [rsp+0F8h+var_C4], eax
0x180068879  test    dword ptr [rbx+30h], 2000h
0x180068880  jz      short loc_18006888F
0x180068882  bts     eax, 10h
0x180068886  mov     [rsp+0F8h+var_BE], si
0x18006888b  mov     [rsp+0F8h+var_C4], eax
0x18006888f  mov     edi, 4
0x180068894  test    eax, eax
0x180068896  jz      short loc_1800688C2
0x180068898  mov     rcx, [rbx+20h]
0x18006889c  lea     r9, [rsp+0F8h+var_C8]
0x1800688a1  mov     [rsp+0F8h+var_C8], 0BCh
0x1800688a9  mov     r8d, edi
0x1800688ac  mov     edx, 447h
0x1800688b1  mov     [rsp+0F8h+var_D8], rbp
0x1800688b6  mov     rax, [rcx]
0x1800688b9  mov     rax, [rax+18h]
0x1800688bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688c2  mov     rcx, [rbx+20h]
0x1800688c6  mov     r9, rdi
0x1800688c9  mov     r8, rdi
0x1800688cc  mov     [rsp+0F8h+var_D8], rbp
0x1800688d1  mov     edi, 4CCh
0x1800688d6  mov     edx, edi
0x1800688d8  mov     rax, [rcx]
0x1800688db  mov     rax, [rax+18h]
0x1800688df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688e4  mov     rcx, [rbx+20h]
0x1800688e8  mov     r9d, 80h
0x1800688ee  xor     r8d, r8d
0x1800688f1  mov     [rsp+0F8h+var_D8], rbp
0x1800688f6  mov     edx, edi
0x1800688f8  mov     rax, [rcx]
0x1800688fb  mov     rax, [rax+18h]
0x1800688ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068904  mov     rcx, [rbx+20h]
0x180068908  lea     edx, [rdi-54h]
0x18006890b  mov     r9d, 32h ; '2'
0x180068911  mov     [rsp+0F8h+var_D8], rbp
0x180068916  xor     r8d, r8d
0x180068919  mov     rax, [rcx]
0x18006891c  mov     rax, [rax+18h]
0x180068920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068925  mov     rcx, [rbx+20h]
0x180068929  xor     r9d, r9d
0x18006892c  xor     r8d, r8d
0x18006892f  mov     [rsp+0F8h+var_D8], rbp
0x180068934  mov     rdx, [rcx]
0x180068937  mov     rax, [rdx+18h]
0x18006893b  lea     edx, [rdi-24h]
0x18006893e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068943  mov     eax, esi
0x180068945  mov     [rbx+3Ch], rbp
0x180068949  mov     [rbx+44h], rbp
0x18006894d  jmp     short loc_180068951
0x18006894f  xor     eax, eax
0x180068951  mov     rcx, [rsp+0F8h+var_28]
0x180068959  xor     rcx, rsp; StackCookie
0x18006895c  call    __security_check_cookie
0x180068961  lea     r11, [rsp+0F8h+var_18]
0x180068969  mov     rbx, [r11+30h]
0x18006896d  mov     rbp, [r11+38h]
0x180068971  mov     rsp, r11
0x180068974  pop     r13
0x180068976  pop     rdi
0x180068977  pop     rsi
0x180068978  retn
```
