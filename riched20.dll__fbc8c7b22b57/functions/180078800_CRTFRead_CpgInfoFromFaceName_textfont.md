# CRTFRead::CpgInfoFromFaceName(_textfont *)

- ea: `0x180078800`
- end: `0x180078926`
- name: `?CpgInfoFromFaceName@CRTFRead@@AEAAHPEAU_textfont@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this, struct _textfont *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003a3a0`

## callees

- `0x18001c1d4`
- `0x18003e56c`
- `0x180078800`
- `0x180079a88`
- `0x180090b14`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180078885`
- `msvcrt!wcscpy_s` at `0x180078885`

## pseudocode

```c
__int64 __fastcall CRTFRead::CpgInfoFromFaceName(CRTFRead *this, struct _textfont *a2)
{
  bool v2; // zf
  HDC v5; // rdi
  int SystemDefaultCodePage; // eax
  BYTE tmCharSet; // cl
  struct tagTEXTMETRICW v9; // [rsp+20h] [rbp-69h] BYREF
  struct tagLOGFONTW v10; // [rsp+60h] [rbp-29h] BYREF

  v2 = *((_BYTE *)a2 + 74) == 0;
  *((_BYTE *)a2 + 75) = 1;
  if ( !v2 )
    return 0;
  v5 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 7) + 48LL) + 24LL))(*(_QWORD *)(*((_QWORD *)this + 7) + 48LL));
  if ( !v5 )
    return 0;
  memset_0(&v10, 0, sizeof(v10));
  memset(&v9, 0, sizeof(v9));
  wcscpy_s(v10.lfFaceName, 0x20u, (const wchar_t *)a2 + 3);
  SystemDefaultCodePage = CW32System::GetSystemDefaultCodePage();
  v10.lfCharSet = CW32System::GetCharSet(SystemDefaultCodePage, 0);
  if ( !(unsigned int)CW32System::GetTextMetrics(v5, &v10, &v9) || v9.tmCharSet != v10.lfCharSet )
  {
    v10.lfCharSet = 1;
    CW32System::GetTextMetrics(v5, &v10, &v9);
  }
  (*(void (__fastcall **)(_QWORD, HDC))(**(_QWORD **)(*((_QWORD *)this + 7) + 48LL) + 32LL))(
    *(_QWORD *)(*((_QWORD *)this + 7) + 48LL),
    v5);
  tmCharSet = v9.tmCharSet;
  if ( v9.tmCharSet == 1 )
    return 0;
  *((_BYTE *)a2 + 2) = v9.tmCharSet;
  *((_WORD *)a2 + 36) = CW32System::GetCodePage(tmCharSet);
  return 1;
}

```

## disassembly

```asm
0x180078800  mov     [rsp-8+arg_10], rbx
0x180078805  push    rbp
0x180078806  push    rsi
0x180078807  push    rdi
0x180078808  lea     rbp, [rsp-47h]
0x18007880d  sub     rsp, 0D0h
0x180078814  mov     rax, cs:__security_cookie
0x18007881b  xor     rax, rsp
0x18007881e  mov     [rbp+57h+var_20], rax
0x180078822  cmp     byte ptr [rdx+4Ah], 0
0x180078826  mov     rbx, rdx
0x180078829  mov     rsi, rcx
0x18007882c  mov     byte ptr [rdx+4Bh], 1
0x180078830  jnz     loc_180078904
0x180078836  mov     rax, [rcx+38h]
0x18007883a  mov     rcx, [rax+30h]
0x18007883e  mov     rax, [rcx]
0x180078841  mov     rax, [rax+18h]
0x180078845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007884a  mov     rdi, rax
0x18007884d  test    rax, rax
0x180078850  jz      loc_180078904
0x180078856  xor     edx, edx; Val
0x180078858  lea     rcx, [rbp+57h+var_80]; void *
0x18007885c  lea     r8d, [rdx+5Ch]; Size
0x180078860  call    memset_0
0x180078865  xorps   xmm0, xmm0
0x180078868  lea     r8, [rbx+6]; Source
0x18007886c  movups  xmmword ptr [rbp+57h+var_C0.tmOverhang], xmm0
0x180078870  mov     edx, 20h ; ' '; SizeInWords
0x180078875  lea     rcx, [rbp+57h+var_80.lfFaceName]; Destination
0x180078879  movups  xmmword ptr [rbp+57h+var_C0.tmFirstChar], xmm0
0x18007887d  movups  xmmword ptr [rbp+57h+var_C0.tmHeight], xmm0
0x180078881  movups  xmmword ptr [rbp+57h+var_C0.tmExternalLeading], xmm0
0x180078885  call    cs:__imp_wcscpy_s
0x18007888c  nop     dword ptr [rax+rax+00h]
0x180078891  call    ?GetSystemDefaultCodePage@CW32System@@SAIXZ; CW32System::GetSystemDefaultCodePage(void)
0x180078896  mov     ecx, eax; int
0x180078898  xor     edx, edx; int *
0x18007889a  call    ?GetCharSet@CW32System@@SAEHPEAH@Z; CW32System::GetCharSet(int,int *)
0x18007889f  lea     r8, [rbp+57h+var_C0]; struct tagTEXTMETRICW *
0x1800788a3  mov     [rbp+57h+var_80.lfCharSet], al
0x1800788a6  lea     rdx, [rbp+57h+var_80]; struct tagLOGFONTW *
0x1800788aa  mov     rcx, rdi; hdc
0x1800788ad  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@AEAUtagLOGFONTW@@AEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagLOGFONTW &,tagTEXTMETRICW &)
0x1800788b2  test    eax, eax
0x1800788b4  jz      short loc_1800788BE
0x1800788b6  mov     al, [rbp+57h+var_80.lfCharSet]
0x1800788b9  cmp     [rbp+57h+var_C0.tmCharSet], al
0x1800788bc  jz      short loc_1800788D2
0x1800788be  lea     r8, [rbp+57h+var_C0]; struct tagTEXTMETRICW *
0x1800788c2  mov     [rbp+57h+var_80.lfCharSet], 1
0x1800788c6  lea     rdx, [rbp+57h+var_80]; struct tagLOGFONTW *
0x1800788ca  mov     rcx, rdi; hdc
0x1800788cd  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@AEAUtagLOGFONTW@@AEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagLOGFONTW &,tagTEXTMETRICW &)
0x1800788d2  mov     rax, [rsi+38h]
0x1800788d6  mov     rdx, rdi
0x1800788d9  mov     rcx, [rax+30h]
0x1800788dd  mov     rax, [rcx]
0x1800788e0  mov     rax, [rax+20h]
0x1800788e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800788e9  mov     cl, [rbp+57h+var_C0.tmCharSet]; unsigned __int8
0x1800788ec  cmp     cl, 1
0x1800788ef  jz      short loc_180078904
0x1800788f1  mov     [rbx+2], cl
0x1800788f4  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x1800788f9  mov     [rbx+48h], ax
0x1800788fd  mov     eax, 1
0x180078902  jmp     short loc_180078906
0x180078904  xor     eax, eax
0x180078906  mov     rcx, [rbp+57h+var_20]
0x18007890a  xor     rcx, rsp; StackCookie
0x18007890d  call    __security_check_cookie
0x180078912  mov     rbx, [rsp+0E0h+arg_10]
0x18007891a  add     rsp, 0D0h
0x180078921  pop     rdi
0x180078922  pop     rsi
0x180078923  pop     rbp
0x180078924  retn
```
