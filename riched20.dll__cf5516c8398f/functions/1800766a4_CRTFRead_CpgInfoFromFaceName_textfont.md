# CRTFRead::CpgInfoFromFaceName(_textfont *)

- ea: `0x1800766a4`
- end: `0x1800767c3`
- name: `?CpgInfoFromFaceName@CRTFRead@@AEAAHPEAU_textfont@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this, struct _textfont *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002a7d0`

## callees

- `0x18002a144`
- `0x18003dc58`
- `0x1800766a4`
- `0x180077830`
- `0x18008e290`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180076729`
- `msvcrt!wcscpy_s` at `0x180076729`

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
0x1800766a4  mov     [rsp-8+arg_10], rbx
0x1800766a9  push    rbp
0x1800766aa  push    rsi
0x1800766ab  push    rdi
0x1800766ac  lea     rbp, [rsp-47h]
0x1800766b1  sub     rsp, 0D0h
0x1800766b8  mov     rax, cs:__security_cookie
0x1800766bf  xor     rax, rsp
0x1800766c2  mov     [rbp+57h+var_20], rax
0x1800766c6  cmp     byte ptr [rdx+4Ah], 0
0x1800766ca  mov     rbx, rdx
0x1800766cd  mov     rsi, rcx
0x1800766d0  mov     byte ptr [rdx+4Bh], 1
0x1800766d4  jnz     loc_1800767A2
0x1800766da  mov     rax, [rcx+38h]
0x1800766de  mov     rcx, [rax+30h]
0x1800766e2  mov     rax, [rcx]
0x1800766e5  mov     rax, [rax+18h]
0x1800766e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800766ee  mov     rdi, rax
0x1800766f1  test    rax, rax
0x1800766f4  jz      loc_1800767A2
0x1800766fa  xor     edx, edx; Val
0x1800766fc  lea     rcx, [rbp+57h+var_80]; void *
0x180076700  lea     r8d, [rdx+5Ch]; Size
0x180076704  call    memset_0
0x180076709  xorps   xmm0, xmm0
0x18007670c  lea     r8, [rbx+6]; Source
0x180076710  movups  xmmword ptr [rbp+57h+var_C0.tmOverhang], xmm0
0x180076714  mov     edx, 20h ; ' '; SizeInWords
0x180076719  lea     rcx, [rbp+57h+var_80.lfFaceName]; Destination
0x18007671d  movups  xmmword ptr [rbp+57h+var_C0.tmFirstChar], xmm0
0x180076721  movups  xmmword ptr [rbp+57h+var_C0.tmHeight], xmm0
0x180076725  movups  xmmword ptr [rbp+57h+var_C0.tmExternalLeading], xmm0
0x180076729  call    cs:__imp_wcscpy_s
0x18007672f  call    ?GetSystemDefaultCodePage@CW32System@@SAIXZ; CW32System::GetSystemDefaultCodePage(void)
0x180076734  mov     ecx, eax; int
0x180076736  xor     edx, edx; int *
0x180076738  call    ?GetCharSet@CW32System@@SAEHPEAH@Z; CW32System::GetCharSet(int,int *)
0x18007673d  lea     r8, [rbp+57h+var_C0]; struct tagTEXTMETRICW *
0x180076741  mov     [rbp+57h+var_80.lfCharSet], al
0x180076744  lea     rdx, [rbp+57h+var_80]; struct tagLOGFONTW *
0x180076748  mov     rcx, rdi; hdc
0x18007674b  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@AEAUtagLOGFONTW@@AEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagLOGFONTW &,tagTEXTMETRICW &)
0x180076750  test    eax, eax
0x180076752  jz      short loc_18007675C
0x180076754  mov     al, [rbp+57h+var_80.lfCharSet]
0x180076757  cmp     [rbp+57h+var_C0.tmCharSet], al
0x18007675a  jz      short loc_180076770
0x18007675c  lea     r8, [rbp+57h+var_C0]; struct tagTEXTMETRICW *
0x180076760  mov     [rbp+57h+var_80.lfCharSet], 1
0x180076764  lea     rdx, [rbp+57h+var_80]; struct tagLOGFONTW *
0x180076768  mov     rcx, rdi; hdc
0x18007676b  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@AEAUtagLOGFONTW@@AEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagLOGFONTW &,tagTEXTMETRICW &)
0x180076770  mov     rax, [rsi+38h]
0x180076774  mov     rdx, rdi
0x180076777  mov     rcx, [rax+30h]
0x18007677b  mov     rax, [rcx]
0x18007677e  mov     rax, [rax+20h]
0x180076782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076787  mov     cl, [rbp+57h+var_C0.tmCharSet]; unsigned __int8
0x18007678a  cmp     cl, 1
0x18007678d  jz      short loc_1800767A2
0x18007678f  mov     [rbx+2], cl
0x180076792  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x180076797  mov     [rbx+48h], ax
0x18007679b  mov     eax, 1
0x1800767a0  jmp     short loc_1800767A4
0x1800767a2  xor     eax, eax
0x1800767a4  mov     rcx, [rbp+57h+var_20]
0x1800767a8  xor     rcx, rsp; StackCookie
0x1800767ab  call    __security_check_cookie
0x1800767b0  mov     rbx, [rsp+0E0h+arg_10]
0x1800767b8  add     rsp, 0D0h
0x1800767bf  pop     rdi
0x1800767c0  pop     rsi
0x1800767c1  pop     rbp
0x1800767c2  retn
```
