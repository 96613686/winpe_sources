# SelectSansSerifFont(tag_STRING_ANALYSIS *,int)

- ea: `0x1800532d4`
- end: `0x180053516`
- name: `?SelectSansSerifFont@@YAJPEAUtag_STRING_ANALYSIS@@H@Z`
- size: `578`
- prototype: `__int64 __fastcall(struct tag_STRING_ANALYSIS *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b0d4`

## callees

- `0x18000d650`
- `0x18000e5a0`
- `0x180011380`
- `0x180025fb0`
- `0x1800532d4`
- `0x18007ac50`

## import_xrefs

- `GDI32!SelectObject` at `0x18005341d`
- `GDI32!SelectObject` at `0x180053460`
- `GDI32!SelectObject` at `0x1800534e6`
- `GDI32!SelectObject` at `0x18005341d`
- `GDI32!SelectObject` at `0x180053460`
- `GDI32!SelectObject` at `0x1800534e6`
- `GDI32!DeleteObject` at `0x1800534c4`
- `GDI32!DeleteObject` at `0x1800534d6`
- `GDI32!DeleteObject` at `0x1800534c4`
- `GDI32!DeleteObject` at `0x1800534d6`

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
0x1800532d4  mov     [rsp-18h+arg_10], rbx
0x1800532d9  push    rbp
0x1800532da  push    rsi
0x1800532db  push    rdi
0x1800532dc  mov     rbp, rsp
0x1800532df  sub     rsp, 70h
0x1800532e3  mov     rax, cs:__security_cookie
0x1800532ea  xor     rax, rsp
0x1800532ed  mov     [rbp+var_10], rax
0x1800532f1  mov     rax, [rcx+0D8h]
0x1800532f8  mov     esi, 2Ah ; '*'
0x1800532fd  movsxd  rdx, edx
0x180053300  mov     rbx, rcx
0x180053303  mov     [rdx+rax], sil
0x180053307  cmp     [rcx+150h], esi
0x18005330d  jz      loc_180053453
0x180053313  mov     rdx, [rcx+4E0h]; h
0x18005331a  test    rdx, rdx
0x18005331d  jnz     loc_180053457
0x180053323  mov     rdi, [rcx+1B8h]
0x18005332a  test    rdi, rdi
0x18005332d  jz      loc_1800534B3
0x180053333  cmp     [rdi+50h], rdx
0x180053337  jz      loc_1800534B3
0x18005333d  cmp     [rcx+390h], rdx
0x180053344  jz      loc_180053473
0x18005334a  mov     eax, [rdi+10h]
0x18005334d  xorps   xmm0, xmm0
0x180053350  mov     [rbp+lf.lfHeight], eax
0x180053353  xorps   xmm1, xmm1
0x180053356  mov     eax, [rbx+158h]
0x18005335c  xor     edx, edx
0x18005335e  mov     [rbp+lf.lfWidth], eax
0x180053361  mov     eax, [rbx+15Ch]
0x180053367  mov     [rbp+lf.lfEscapement], eax
0x18005336a  mov     eax, [rbx+160h]
0x180053370  mov     [rbp+lf.lfOrientation], eax
0x180053373  mov     eax, [rbx+164h]
0x180053379  mov     [rbp+lf.lfWeight], eax
0x18005337c  mov     al, [rbx+168h]
0x180053382  mov     [rbp+lf.lfItalic], al
0x180053385  mov     al, [rbx+16Ch]
0x18005338b  mov     [rbp+lf.lfOutPrecision], al
0x18005338e  mov     al, [rbx+16Dh]
0x180053394  mov     [rbp+lf.lfClipPrecision], al
0x180053397  mov     al, [rbx+16Eh]
0x18005339d  mov     [rbp+lf.lfQuality], al
0x1800533a0  mov     al, [rbx+16Fh]
0x1800533a6  mov     [rbp+lf.lfPitchAndFamily], al
0x1800533a9  movdqu  xmmword ptr [rbp+lf.lfFaceName], xmm0
0x1800533ae  mov     word ptr [rbp+lf.lfUnderline], 0
0x1800533b4  movdqu  xmmword ptr [rbp+lf.lfFaceName+10h], xmm1
0x1800533b9  mov     [rbp+lf.lfCharSet], 0
0x1800533bd  lea     rax, aMicrosoftSansS; "Microsoft Sans Serif"
0x1800533c4  mov     al, [rdx+rax]
0x1800533c7  mov     [rbp+rdx+lf.lfFaceName], al
0x1800533cb  test    al, al
0x1800533cd  jz      short loc_1800533D6
0x1800533cf  inc     edx
0x1800533d1  cmp     edx, 20h ; ' '
0x1800533d4  jl      short loc_1800533BD
0x1800533d6  lea     rcx, [rbp+lf]; lplf
0x1800533da  call    CreateFontIndirectA
0x1800533df  mov     [rbx+4E0h], rax
0x1800533e6  test    rax, rax
0x1800533e9  jnz     short loc_180053417
0x1800533eb  mov     qword ptr [rbx+4E0h], 0FFFFFFFFFFFFFFFFh
0x1800533f6  mov     eax, 80040200h
0x1800533fb  mov     rcx, [rbp+var_10]
0x1800533ff  xor     rcx, rsp; StackCookie
0x180053402  call    __security_check_cookie
0x180053407  mov     rbx, [rsp+70h+arg_10]
0x18005340f  add     rsp, 70h
0x180053413  pop     rdi
0x180053414  pop     rsi
0x180053415  pop     rbp
0x180053416  retn
0x180053417  mov     rcx, [rbx]; hdc
0x18005341a  mov     rdx, rax; h
0x18005341d  call    cs:__imp_SelectObject
0x180053423  test    rax, rax
0x180053426  jz      loc_1800534BD
0x18005342c  mov     [rbx+150h], esi
0x180053432  xor     edx, edx; int
0x180053434  lea     rsi, [rbx+308h]
0x18005343b  mov     qword ptr [rsi], 0
0x180053442  mov     rcx, rsi; void **
0x180053445  mov     r8, [rbx]; HDC
0x180053448  call    ?ScriptCheckCache@@YAJPEAPEAXHPEAUHDC__@@@Z; ScriptCheckCache(void * *,int,HDC__ *)
0x18005344d  mov     edi, eax
0x18005344f  test    eax, eax
0x180053451  js      short loc_1800534CF
0x180053453  xor     eax, eax
0x180053455  jmp     short loc_1800533FB
0x180053457  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18005345b  jz      short loc_1800534B3
0x18005345d  mov     rcx, [rcx]; hdc
0x180053460  call    cs:__imp_SelectObject
0x180053466  test    rax, rax
0x180053469  jz      short loc_1800534B3
0x18005346b  mov     [rbx+150h], esi
0x180053471  jmp     short loc_180053453
0x180053473  mov     rcx, [rcx]; hdc
0x180053476  mov     edx, 6; type
0x18005347b  call    GetCurrentObject
0x180053480  mov     [rbx+390h], rax
0x180053487  test    rax, rax
0x18005348a  jz      short loc_1800534A8
0x18005348c  lea     r8, [rbx+154h]; pv
0x180053493  mov     edx, 3Ch ; '<'; c
0x180053498  mov     rcx, rax; h
0x18005349b  call    GetObjectA
0x1800534a0  test    eax, eax
0x1800534a2  jnz     loc_18005334A
0x1800534a8  mov     qword ptr [rbx+4E0h], 0FFFFFFFFFFFFFFFFh
0x1800534b3  mov     eax, 80004005h
0x1800534b8  jmp     loc_1800533FB
0x1800534bd  mov     rcx, [rbx+4E0h]; ho
0x1800534c4  call    cs:__imp_DeleteObject
0x1800534ca  jmp     loc_1800533EB
0x1800534cf  mov     rcx, [rbx+4E0h]; ho
0x1800534d6  call    cs:__imp_DeleteObject
0x1800534dc  mov     rdx, [rbx+390h]; h
0x1800534e3  mov     rcx, [rbx]; hdc
0x1800534e6  call    cs:__imp_SelectObject
0x1800534ec  lea     ecx, [rdi+7FFBFE00h]
0x1800534f2  neg     ecx
0x1800534f4  sbb     rax, rax
0x1800534f7  mov     [rbx+4E0h], rax
0x1800534fe  mov     eax, edi
0x180053500  mov     qword ptr [rsi], 0
0x180053507  mov     dword ptr [rbx+150h], 0
0x180053511  jmp     loc_1800533FB
```
