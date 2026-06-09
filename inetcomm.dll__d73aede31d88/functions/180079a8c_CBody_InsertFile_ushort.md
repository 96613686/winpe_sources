# CBody::InsertFile(ushort *)

- ea: `0x180079a8c`
- end: `0x180079dc7`
- name: `?InsertFile@CBody@@AEAAJPEAG@Z`
- size: `827`
- prototype: `__int64 __fastcall(CBody *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180023d04`

## callees

- `0x1800055bc`
- `0x180005748`
- `0x18002a0d8`
- `0x180078f60`
- `0x180079a8c`
- `0x180079dd0`
- `0x1800cb8d0`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cca90`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!FIsHTMLFileW` at `0x180079b90`
- `MSOERT2!FIsHTMLFileW` at `0x180079b90`
- `MSOERT2!MessageBoxInstW` at `0x180079d71`
- `MSOERT2!MessageBoxInstW` at `0x180079d71`
- `MSOERT2!ReplaceCharsW` at `0x180079c62`
- `MSOERT2!ReplaceCharsW` at `0x180079c62`
- `MSOERT2!OpenFileStreamW` at `0x180079b6e`
- `MSOERT2!OpenFileStreamW` at `0x180079b6e`
- `MSOERT2!HrIsStreamUnicode` at `0x180079c09`
- `MSOERT2!HrIsStreamUnicode` at `0x180079c09`
- `SHLWAPI!StrStrIW` at `0x180079c25`
- `SHLWAPI!StrStrIW` at `0x180079c25`
- `SHLWAPI!StrStrIA` at `0x180079d1b`
- `SHLWAPI!StrStrIA` at `0x180079d1b`
- `USER32!MessageBoxW` at `0x180079d26`
- `USER32!LoadStringW` at `0x180079c51`
- `USER32!LoadStringW` at `0x180079c7e`
- `USER32!LoadStringW` at `0x180079c9d`
- `USER32!LoadStringW` at `0x180079c51`
- `USER32!LoadStringW` at `0x180079c7e`
- `USER32!LoadStringW` at `0x180079c9d`
- `USER32!LoadStringW` at `0x180079d5b`

## pseudocode

```c
BOOL __fastcall CBody::InsertFile(CBody *this, unsigned __int16 *a2)
{
  int inserted; // ebx
  int v5; // esi
  unsigned int v6; // eax
  __int64 v7; // rax
  IStream *v8; // rcx
  void *v9; // rax
  BOOL result; // eax
  unsigned int v11; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v12; // [rsp+64h] [rbp-9Ch] BYREF
  IStream *pstm; // [rsp+68h] [rbp-98h] BYREF
  tagOFNW v14; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v15[32]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Buffer[104]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v17[264]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR v18[512]; // [rsp+430h] [rbp+330h] BYREF
  WCHAR pszFirst[2048]; // [rsp+830h] [rbp+730h] BYREF

  memset_0(&v14, 0, sizeof(v14));
  pstm = 0;
  v11 = 0;
  v12 = 0;
  if ( !*((_QWORD *)this + 11) )
    goto LABEL_2;
  v17[0] = 0;
  v18[0] = 0;
  Buffer[0] = 0;
  v15[0] = 0;
  CBody::GetHostFlags(this, &v11);
  v5 = 1;
  if ( a2 )
  {
    inserted = StringCchCopyW(v17, 0x104u, a2);
    if ( inserted < 0 )
      goto LABEL_22;
LABEL_5:
    if ( v17[0] )
    {
      inserted = OpenFileStreamW(v17, 3, 0x80000000LL, &pstm);
      if ( inserted >= 0 )
      {
        if ( (v11 & 2) != 0 && (unsigned int)FIsHTMLFileW(v17) )
        {
          v11 = 0;
          inserted = ((__int64 (__fastcall *)(IStream *, WCHAR *, __int64, unsigned int *))pstm->lpVtbl->Read)(
                       pstm,
                       pszFirst,
                       4094,
                       &v12);
          if ( inserted < 0 )
            goto LABEL_22;
          v6 = v12;
          if ( v12 >= 0x1000uLL || (*((_BYTE *)pszFirst + v12) = 0, v7 = v6 + 1, (unsigned int)v7 >= 0x1000uLL) )
            _report_rangecheckfailure();
          v8 = pstm;
          *((_BYTE *)pszFirst + v7) = 0;
          if ( (unsigned int)HrIsStreamUnicode(v8, &v11) )
            v9 = StrStrIA((PCSTR)pszFirst, "<FRAMESET");
          else
            v9 = StrStrIW(pszFirst, L"<FRAMESET");
          if ( v9 )
            MessageBoxInstW(g_hLocRes, *((_QWORD *)this + 13), 1270, 1295, 0, 0, LoadStringW, MessageBoxW, 0, 0, 0, 0);
        }
        else
        {
          v5 = 0;
        }
        inserted = CBody::InsertStreamAtCaret(this, pstm, v5);
      }
LABEL_22:
      OE_SafeReleaseAndNullPtr<IStream>(&pstm);
      return inserted;
    }
LABEL_2:
    inserted = -2147467259;
    goto LABEL_22;
  }
  LoadStringW(g_hLocRes, 1268 - ((v11 & 2) != 0), Buffer, 100);
  ReplaceCharsW(Buffer, 124);
  LoadStringW(g_hLocRes, 0x4F5u, v15, 30);
  LoadStringW(g_hLocRes, 0x4F6u, v18, 512);
  memset_0(&v14, 0, sizeof(v14));
  v14.hwndOwner = (HWND)*((_QWORD *)this + 13);
  v14.lpstrFilter = Buffer;
  v14.lpstrFile = v17;
  v14.lpstrTitle = v18;
  v14.lpstrDefExt = v15;
  v14.lStructSize = 152;
  v14.nFilterIndex = 1;
  v14.nMaxFile = 260;
  v14.Flags = 4108;
  result = GetOpenFileNameW(&v14);
  if ( result )
    goto LABEL_5;
  return result;
}

```

## disassembly

```asm
0x180079a8c  mov     [rsp-8+arg_10], rbx
0x180079a91  mov     [rsp-8+arg_18], rsi
0x180079a96  push    rbp
0x180079a97  push    rdi
0x180079a98  push    r14
0x180079a9a  lea     rbp, [rsp-1740h]
0x180079aa2  mov     eax, 1840h
0x180079aa7  call    _alloca_probe
0x180079aac  sub     rsp, rax
0x180079aaf  mov     rax, cs:__security_cookie
0x180079ab6  xor     rax, rsp
0x180079ab9  mov     [rbp+1750h+var_20], rax
0x180079ac0  mov     rbx, rdx
0x180079ac3  mov     rdi, rcx
0x180079ac6  xor     edx, edx; Val
0x180079ac8  lea     rcx, [rsp+1850h+var_17E0]; void *
0x180079acd  mov     r8d, 98h; Size
0x180079ad3  call    memset_0
0x180079ad8  xor     r14d, r14d
0x180079adb  mov     [rsp+1850h+pstm], r14
0x180079ae0  mov     [rsp+1850h+var_17F0], r14d
0x180079ae5  mov     [rsp+1850h+var_17EC], r14d
0x180079aea  cmp     [rdi+58h], r14
0x180079aee  jnz     short loc_180079AFA
0x180079af0  mov     ebx, 80004005h
0x180079af5  jmp     loc_180079D94
0x180079afa  lea     rdx, [rsp+1850h+var_17F0]; unsigned int *
0x180079aff  mov     [rbp+1750h+var_1630], r14w
0x180079b07  mov     rcx, rdi; this
0x180079b0a  mov     [rbp+1750h+var_1420], r14w
0x180079b12  mov     [rbp+1750h+Buffer], r14w
0x180079b17  mov     [rbp+1750h+var_1740], r14w
0x180079b1c  call    ?GetHostFlags@CBody@@AEAAJPEAK@Z; CBody::GetHostFlags(ulong *)
0x180079b21  mov     esi, 1
0x180079b26  test    rbx, rbx
0x180079b29  jz      loc_180079C30
0x180079b2f  mov     r8, rbx; unsigned __int16 *
0x180079b32  lea     rcx, [rbp+1750h+var_1630]; unsigned __int16 *
0x180079b39  mov     edx, 104h; unsigned __int64
0x180079b3e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180079b43  mov     ebx, eax
0x180079b45  test    eax, eax
0x180079b47  js      loc_180079D94
0x180079b4d  cmp     [rbp+1750h+var_1630], r14w
0x180079b55  jz      short loc_180079AF0
0x180079b57  lea     r9, [rsp+1850h+pstm]
0x180079b5c  mov     edx, 3
0x180079b61  mov     r8d, 80000000h
0x180079b67  lea     rcx, [rbp+1750h+var_1630]
0x180079b6e  call    cs:__imp_OpenFileStreamW
0x180079b74  mov     ebx, eax
0x180079b76  test    eax, eax
0x180079b78  js      loc_180079D94
0x180079b7e  test    byte ptr [rsp+1850h+var_17F0], 2
0x180079b83  jz      loc_180079D7F
0x180079b89  lea     rcx, [rbp+1750h+var_1630]
0x180079b90  call    cs:__imp_FIsHTMLFileW
0x180079b96  test    eax, eax
0x180079b98  jz      loc_180079D7F
0x180079b9e  mov     rcx, [rsp+1850h+pstm]
0x180079ba3  lea     r9, [rsp+1850h+var_17EC]
0x180079ba8  mov     [rsp+1850h+var_17F0], r14d
0x180079bad  lea     rdx, [rbp+1750h+pszFirst]
0x180079bb4  mov     r8d, 0FFEh
0x180079bba  mov     rax, [rcx]
0x180079bbd  mov     rax, [rax+18h]
0x180079bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079bc6  mov     ebx, eax
0x180079bc8  test    eax, eax
0x180079bca  js      loc_180079D94
0x180079bd0  mov     eax, [rsp+1850h+var_17EC]
0x180079bd4  mov     edx, 1000h
0x180079bd9  cmp     rax, rdx
0x180079bdc  jnb     loc_180079D79
0x180079be2  mov     byte ptr [rbp+rax+1750h+pszFirst], r14b
0x180079bea  inc     eax
0x180079bec  mov     ecx, eax
0x180079bee  cmp     rcx, rdx
0x180079bf1  jnb     loc_180079D79
0x180079bf7  mov     rcx, [rsp+1850h+pstm]
0x180079bfc  lea     rdx, [rsp+1850h+var_17F0]
0x180079c01  mov     byte ptr [rbp+rax+1750h+pszFirst], r14b
0x180079c09  call    cs:__imp_HrIsStreamUnicode
0x180079c0f  lea     rcx, [rbp+1750h+pszFirst]; pszFirst
0x180079c16  test    eax, eax
0x180079c18  jnz     loc_180079D14
0x180079c1e  lea     rdx, pszSrch; "<FRAMESET"
0x180079c25  call    cs:__imp_StrStrIW
0x180079c2b  jmp     loc_180079D21
0x180079c30  mov     eax, [rsp+1850h+var_17F0]
0x180079c34  lea     r8, [rbp+1750h+Buffer]; lpBuffer
0x180079c38  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180079c3f  and     al, 2
0x180079c41  neg     al
0x180079c43  mov     r9d, 64h ; 'd'; cchBufferMax
0x180079c49  sbb     edx, edx
0x180079c4b  add     edx, 4F4h; uID
0x180079c51  call    cs:__imp_LoadStringW
0x180079c57  xor     r8d, r8d
0x180079c5a  lea     rcx, [rbp+1750h+Buffer]
0x180079c5e  lea     edx, [r8+7Ch]
0x180079c62  call    cs:__imp_ReplaceCharsW
0x180079c68  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180079c6f  lea     r8, [rbp+1750h+var_1740]; lpBuffer
0x180079c73  mov     r9d, 1Eh; cchBufferMax
0x180079c79  mov     edx, 4F5h; uID
0x180079c7e  call    cs:__imp_LoadStringW
0x180079c84  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180079c8b  lea     r8, [rbp+1750h+var_1420]; lpBuffer
0x180079c92  mov     r9d, 200h; cchBufferMax
0x180079c98  mov     edx, 4F6h; uID
0x180079c9d  call    cs:__imp_LoadStringW
0x180079ca3  xor     edx, edx; Val
0x180079ca5  lea     rcx, [rsp+1850h+var_17E0]; void *
0x180079caa  mov     r8d, 98h; Size
0x180079cb0  call    memset_0
0x180079cb5  mov     rax, [rdi+68h]
0x180079cb9  lea     rcx, [rsp+1850h+var_17E0]; LPOPENFILENAMEW
0x180079cbe  mov     [rsp+1850h+var_17E0.hwndOwner], rax
0x180079cc3  lea     rax, [rbp+1750h+Buffer]
0x180079cc7  mov     [rbp+1750h+var_17E0.lpstrFilter], rax
0x180079ccb  lea     rax, [rbp+1750h+var_1630]
0x180079cd2  mov     [rbp+1750h+var_17E0.lpstrFile], rax
0x180079cd6  lea     rax, [rbp+1750h+var_1420]
0x180079cdd  mov     [rbp+1750h+var_17E0.lpstrTitle], rax
0x180079ce1  lea     rax, [rbp+1750h+var_1740]
0x180079ce5  mov     [rbp+1750h+var_17E0.lpstrDefExt], rax
0x180079ce9  mov     [rsp+1850h+var_17E0.lStructSize], 98h
0x180079cf1  mov     [rbp+1750h+var_17E0.nFilterIndex], esi
0x180079cf4  mov     [rbp+1750h+var_17E0.nMaxFile], 104h
0x180079cfb  mov     [rbp+1750h+var_17E0.Flags], 100Ch
0x180079d02  call    GetOpenFileNameW
0x180079d07  test    eax, eax
0x180079d09  jnz     loc_180079B4D
0x180079d0f  jmp     loc_180079DA0
0x180079d14  lea     rdx, aFrameset_0; "<FRAMESET"
0x180079d1b  call    cs:__imp_StrStrIA
0x180079d21  test    rax, rax
0x180079d24  jz      short loc_180079D82
0x180079d26  mov     rax, cs:__imp_MessageBoxW
0x180079d2d  mov     r9d, 50Fh
0x180079d33  mov     rdx, [rdi+68h]
0x180079d37  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x180079d3e  mov     [rsp+1850h+var_17F8], r14d
0x180079d43  mov     [rsp+1850h+var_1800], r14
0x180079d48  lea     r8d, [r9-19h]
0x180079d4c  mov     [rsp+1850h+var_1808], r14
0x180079d51  mov     [rsp+1850h+var_1810], r14
0x180079d56  mov     [rsp+1850h+var_1818], rax
0x180079d5b  mov     rax, cs:__imp_LoadStringW
0x180079d62  mov     [rsp+1850h+var_1820], rax
0x180079d67  mov     [rsp+1850h+var_1828], r14d
0x180079d6c  mov     [rsp+1850h+var_1830], r14
0x180079d71  call    cs:__imp_MessageBoxInstW
0x180079d77  jmp     short loc_180079D82
0x180079d79  call    __report_rangecheckfailure
0x180079d7f  mov     esi, r14d
0x180079d82  mov     rdx, [rsp+1850h+pstm]; pstm
0x180079d87  mov     r8d, esi; int
0x180079d8a  mov     rcx, rdi; this
0x180079d8d  call    ?InsertStreamAtCaret@CBody@@AEAAJPEAUIStream@@H@Z; CBody::InsertStreamAtCaret(IStream *,int)
0x180079d92  mov     ebx, eax
0x180079d94  lea     rcx, [rsp+1850h+pstm]
0x180079d99  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x180079d9e  mov     eax, ebx
0x180079da0  mov     rcx, [rbp+1750h+var_20]
0x180079da7  xor     rcx, rsp; StackCookie
0x180079daa  call    __security_check_cookie
0x180079daf  lea     r11, [rsp+1850h+var_10]
0x180079db7  mov     rbx, [r11+30h]
0x180079dbb  mov     rsi, [r11+38h]
0x180079dbf  mov     rsp, r11
0x180079dc2  pop     r14
0x180079dc4  pop     rdi
0x180079dc5  pop     rbp
0x180079dc6  retn
```
