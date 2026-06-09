# SelectSansSerifFont(tag_STRING_ANALYSIS *,int)

- ea: `0x1800270d8`
- end: `0x18002733d`
- name: `?SelectSansSerifFont@@YAJPEAUtag_STRING_ANALYSIS@@H@Z`
- size: `613`
- prototype: `__int64 __fastcall(struct tag_STRING_ANALYSIS *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007f48`

## callees

- `0x180004c00`
- `0x1800069b0`
- `0x180025cb0`
- `0x1800270d8`
- `0x18002ef90`
- `0x18007f800`

## import_xrefs

- `GDI32!SelectObject` at `0x180027222`
- `GDI32!SelectObject` at `0x18002726f`
- `GDI32!SelectObject` at `0x180027307`
- `GDI32!SelectObject` at `0x180027222`
- `GDI32!SelectObject` at `0x18002726f`
- `GDI32!SelectObject` at `0x180027307`
- `GDI32!DeleteObject` at `0x1800272d9`
- `GDI32!DeleteObject` at `0x1800272f1`
- `GDI32!DeleteObject` at `0x1800272d9`
- `GDI32!DeleteObject` at `0x1800272f1`

## pseudocode

```c
__int64 __fastcall SelectSansSerifFont(struct tag_STRING_ANALYSIS *a1, int a2)
{
  void *v3; // rdx
  __int64 v4; // rdi
  __int64 v5; // rdx
  char v6; // al
  HFONT v7; // rax
  __int64 result; // rax
  int v9; // edi
  HGDIOBJ CurrentObject; // rax
  LOGFONTA lf; // [rsp+20h] [rbp-50h] BYREF

  *(_BYTE *)(a2 + *((_QWORD *)a1 + 27)) = 42;
  if ( *((_DWORD *)a1 + 84) == 42 )
    return 0;
  v3 = (void *)*((_QWORD *)a1 + 156);
  if ( v3 )
  {
    if ( v3 == (void *)-1LL || !SelectObject(*(HDC *)a1, v3) )
      return 2147500037LL;
    *((_DWORD *)a1 + 84) = 42;
    return 0;
  }
  v4 = *((_QWORD *)a1 + 55);
  if ( !v4 || !*(_QWORD *)(v4 + 80) )
    return 2147500037LL;
  if ( !*((_QWORD *)a1 + 114) )
  {
    CurrentObject = GetCurrentObject(*(HDC *)a1, 6u);
    *((_QWORD *)a1 + 114) = CurrentObject;
    if ( !CurrentObject || !GetObjectA(CurrentObject, 60, (char *)a1 + 340) )
    {
      *((_QWORD *)a1 + 156) = -1;
      return 2147500037LL;
    }
  }
  lf.lfHeight = *(_DWORD *)(v4 + 16);
  v5 = 0;
  lf.lfWidth = *((_DWORD *)a1 + 86);
  lf.lfEscapement = *((_DWORD *)a1 + 87);
  lf.lfOrientation = *((_DWORD *)a1 + 88);
  lf.lfWeight = *((_DWORD *)a1 + 89);
  lf.lfItalic = *((_BYTE *)a1 + 360);
  lf.lfOutPrecision = *((_BYTE *)a1 + 364);
  lf.lfClipPrecision = *((_BYTE *)a1 + 365);
  lf.lfQuality = *((_BYTE *)a1 + 366);
  lf.lfPitchAndFamily = *((_BYTE *)a1 + 367);
  memset(lf.lfFaceName, 0, sizeof(lf.lfFaceName));
  *(_WORD *)&lf.lfUnderline = 0;
  lf.lfCharSet = 0;
  do
  {
    v6 = aMicrosoftSansS[v5];
    lf.lfFaceName[v5] = v6;
    if ( !v6 )
      break;
    v5 = (unsigned int)(v5 + 1);
  }
  while ( (int)v5 < 32 );
  v7 = CreateFontIndirectA(&lf);
  *((_QWORD *)a1 + 156) = v7;
  if ( !v7 )
  {
LABEL_10:
    *((_QWORD *)a1 + 156) = -1;
    return 2147746304LL;
  }
  if ( !SelectObject(*(HDC *)a1, v7) )
  {
    DeleteObject(*((HGDIOBJ *)a1 + 156));
    goto LABEL_10;
  }
  *((_DWORD *)a1 + 84) = 42;
  *((_QWORD *)a1 + 97) = 0;
  v9 = ScriptCheckCache((void **)a1 + 97, 0, *(HDC *)a1);
  if ( v9 >= 0 )
    return 0;
  DeleteObject(*((HGDIOBJ *)a1 + 156));
  SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 114));
  *((_QWORD *)a1 + 156) = -(__int64)(v9 != -2147220992);
  result = (unsigned int)v9;
  *((_QWORD *)a1 + 97) = 0;
  *((_DWORD *)a1 + 84) = 0;
  return result;
}

```

## disassembly

```asm
0x1800270d8  mov     [rsp-18h+arg_10], rbx
0x1800270dd  push    rbp
0x1800270de  push    rsi
0x1800270df  push    rdi
0x1800270e0  mov     rbp, rsp
0x1800270e3  sub     rsp, 70h
0x1800270e7  mov     rax, cs:__security_cookie
0x1800270ee  xor     rax, rsp
0x1800270f1  mov     [rbp+var_10], rax
0x1800270f5  mov     rax, [rcx+0D8h]
0x1800270fc  mov     esi, 2Ah ; '*'
0x180027101  movsxd  rdx, edx
0x180027104  mov     rbx, rcx
0x180027107  mov     [rdx+rax], sil
0x18002710b  cmp     [rcx+150h], esi
0x180027111  jz      loc_180027262
0x180027117  mov     rdx, [rcx+4E0h]; h
0x18002711e  test    rdx, rdx
0x180027121  jnz     loc_180027266
0x180027127  mov     rdi, [rcx+1B8h]
0x18002712e  test    rdi, rdi
0x180027131  jz      loc_1800272C8
0x180027137  cmp     [rdi+50h], rdx
0x18002713b  jz      loc_1800272C8
0x180027141  cmp     [rcx+390h], rdx
0x180027148  jz      loc_180027288
0x18002714e  mov     eax, [rdi+10h]
0x180027151  xorps   xmm0, xmm0
0x180027154  mov     [rbp+lf.lfHeight], eax
0x180027157  xorps   xmm1, xmm1
0x18002715a  mov     eax, [rbx+158h]
0x180027160  xor     edx, edx
0x180027162  mov     [rbp+lf.lfWidth], eax
0x180027165  mov     eax, [rbx+15Ch]
0x18002716b  mov     [rbp+lf.lfEscapement], eax
0x18002716e  mov     eax, [rbx+160h]
0x180027174  mov     [rbp+lf.lfOrientation], eax
0x180027177  mov     eax, [rbx+164h]
0x18002717d  mov     [rbp+lf.lfWeight], eax
0x180027180  mov     al, [rbx+168h]
0x180027186  mov     [rbp+lf.lfItalic], al
0x180027189  mov     al, [rbx+16Ch]
0x18002718f  mov     [rbp+lf.lfOutPrecision], al
0x180027192  mov     al, [rbx+16Dh]
0x180027198  mov     [rbp+lf.lfClipPrecision], al
0x18002719b  mov     al, [rbx+16Eh]
0x1800271a1  mov     [rbp+lf.lfQuality], al
0x1800271a4  mov     al, [rbx+16Fh]
0x1800271aa  mov     [rbp+lf.lfPitchAndFamily], al
0x1800271ad  movdqu  xmmword ptr [rbp+lf.lfFaceName], xmm0
0x1800271b2  mov     word ptr [rbp+lf.lfUnderline], 0
0x1800271b8  movdqu  xmmword ptr [rbp+lf.lfFaceName+10h], xmm1
0x1800271bd  mov     [rbp+lf.lfCharSet], 0
0x1800271c1  lea     rax, aMicrosoftSansS; "Microsoft Sans Serif"
0x1800271c8  mov     al, [rdx+rax]
0x1800271cb  mov     [rbp+rdx+lf.lfFaceName], al
0x1800271cf  test    al, al
0x1800271d1  jz      short loc_1800271DA
0x1800271d3  inc     edx
0x1800271d5  cmp     edx, 20h ; ' '
0x1800271d8  jl      short loc_1800271C1
0x1800271da  lea     rcx, [rbp+lf]; lplf
0x1800271de  call    CreateFontIndirectA
0x1800271e3  mov     [rbx+4E0h], rax
0x1800271ea  test    rax, rax
0x1800271ed  jnz     short loc_18002721C
0x1800271ef  mov     qword ptr [rbx+4E0h], 0FFFFFFFFFFFFFFFFh
0x1800271fa  mov     eax, 80040200h
0x1800271ff  mov     rcx, [rbp+var_10]
0x180027203  xor     rcx, rsp; StackCookie
0x180027206  call    __security_check_cookie
0x18002720b  mov     rbx, [rsp+70h+arg_10]
0x180027213  add     rsp, 70h
0x180027217  pop     rdi
0x180027218  pop     rsi
0x180027219  pop     rbp
0x18002721a  retn
0x18002721c  mov     rcx, [rbx]; hdc
0x18002721f  mov     rdx, rax; h
0x180027222  call    cs:__imp_SelectObject
0x180027229  nop     dword ptr [rax+rax+00h]
0x18002722e  test    rax, rax
0x180027231  jz      loc_1800272D2
0x180027237  mov     [rbx+150h], esi
0x18002723d  xor     edx, edx; int
0x18002723f  lea     rsi, [rbx+308h]
0x180027246  mov     qword ptr [rsi], 0
0x18002724d  mov     rcx, rsi; void **
0x180027250  mov     r8, [rbx]; HDC
0x180027253  call    ?ScriptCheckCache@@YAJPEAPEAXHPEAUHDC__@@@Z; ScriptCheckCache(void * *,int,HDC__ *)
0x180027258  mov     edi, eax
0x18002725a  test    eax, eax
0x18002725c  js      loc_1800272EA
0x180027262  xor     eax, eax
0x180027264  jmp     short loc_1800271FF
0x180027266  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18002726a  jz      short loc_1800272C8
0x18002726c  mov     rcx, [rcx]; hdc
0x18002726f  call    cs:__imp_SelectObject
0x180027276  nop     dword ptr [rax+rax+00h]
0x18002727b  test    rax, rax
0x18002727e  jz      short loc_1800272C8
0x180027280  mov     [rbx+150h], esi
0x180027286  jmp     short loc_180027262
0x180027288  mov     rcx, [rcx]; hdc
0x18002728b  mov     edx, 6; type
0x180027290  call    GetCurrentObject
0x180027295  mov     [rbx+390h], rax
0x18002729c  test    rax, rax
0x18002729f  jz      short loc_1800272BD
0x1800272a1  lea     r8, [rbx+154h]; pv
0x1800272a8  mov     edx, 3Ch ; '<'; c
0x1800272ad  mov     rcx, rax; h
0x1800272b0  call    GetObjectA
0x1800272b5  test    eax, eax
0x1800272b7  jnz     loc_18002714E
0x1800272bd  mov     qword ptr [rbx+4E0h], 0FFFFFFFFFFFFFFFFh
0x1800272c8  mov     eax, 80004005h
0x1800272cd  jmp     loc_1800271FF
0x1800272d2  mov     rcx, [rbx+4E0h]; ho
0x1800272d9  call    cs:__imp_DeleteObject
0x1800272e0  nop     dword ptr [rax+rax+00h]
0x1800272e5  jmp     loc_1800271EF
0x1800272ea  mov     rcx, [rbx+4E0h]; ho
0x1800272f1  call    cs:__imp_DeleteObject
0x1800272f8  nop     dword ptr [rax+rax+00h]
0x1800272fd  mov     rdx, [rbx+390h]; h
0x180027304  mov     rcx, [rbx]; hdc
0x180027307  call    cs:__imp_SelectObject
0x18002730e  nop     dword ptr [rax+rax+00h]
0x180027313  lea     ecx, [rdi+7FFBFE00h]
0x180027319  neg     ecx
0x18002731b  sbb     rax, rax
0x18002731e  mov     [rbx+4E0h], rax
0x180027325  mov     eax, edi
0x180027327  mov     qword ptr [rsi], 0
0x18002732e  mov     dword ptr [rbx+150h], 0
0x180027338  jmp     loc_1800271FF
```
