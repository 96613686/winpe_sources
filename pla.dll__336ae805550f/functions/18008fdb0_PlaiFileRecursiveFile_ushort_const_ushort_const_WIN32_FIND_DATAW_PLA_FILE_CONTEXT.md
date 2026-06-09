# PlaiFileRecursiveFile(ushort const *,ushort const *,_WIN32_FIND_DATAW *,_PLA_FILE_CONTEXT *)

- ea: `0x18008fdb0`
- end: `0x1800904cf`
- name: `?PlaiFileRecursiveFile@@YAJPEBG0PEAU_WIN32_FIND_DATAW@@PEAU_PLA_FILE_CONTEXT@@@Z`
- size: `1823`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, struct _PLA_FILE_CONTEXT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180015f98`
- `0x18001b4fc`
- `0x18001cbe0`
- `0x18002b3a0`
- `0x18008fdb0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009009d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009009d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008fe0c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008fe0c`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18009008e`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18009008e`

## string_xrefs

- `0x1800901e3`: `configurationFilesFrom`
- `0x1800902cf`: `configurationFilesTo`
- `0x1800903f0`: `configurationFilesCopyResult`

## pseudocode

```c
__int64 __fastcall PlaiFileRecursiveFile(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _WIN32_FIND_DATAW *a3,
        struct _PLA_FILE_CONTEXT *a4)
{
  DWORD dwFileAttributes; // eax
  struct IXMLDOMElement *v8; // r14
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rax
  WCHAR *v11; // r15
  __int64 v12; // rax
  _DWORD *v13; // rcx
  int v14; // edx
  int v15; // eax
  __int64 v16; // rax
  bool v17; // cf
  int v18; // eax
  bool v19; // zf
  int v20; // esi
  DWORD LastError; // eax
  int v22; // eax
  struct IXMLDOMElement *v23; // rdx
  struct IXMLDOMDocument *v24; // rcx
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  int pbCancel; // [rsp+20h] [rbp-E0h]
  LPBOOL pbCancela; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL v40; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMElement *v41; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v42[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v43[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v44[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v45[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v46[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v47[64]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v48[64]; // [rsp+390h] [rbp+290h] BYREF

  dwFileAttributes = a3->dwFileAttributes;
  v40 = 0;
  v41 = 0;
  v8 = 0;
  if ( (dwFileAttributes & 0x10) != 0 )
    return 0;
  if ( WaitForSingleObject(*((HANDLE *)a4 + 8), 0) != 258 )
    return (unsigned int)PlaiHResultFromWin32(0x4D3u);
  v10 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, pbCancel);
  v11 = v10;
  if ( !v10 )
  {
    v9 = -2147024882;
    v39 = -2147024882;
    v38 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v42, 0x4000000000000800uLL);
      v12 = -1;
      do
        ++v12;
      while ( v42[v12] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v39, 4, byte_180147320, 1, &v38, 4);
    }
    return v9;
  }
  v13 = (_DWORD *)*((_QWORD *)a4 + 10);
  v14 = (*v13)++;
  LODWORD(pbCancela) = *((_DWORD *)a4 + 22);
  v15 = StringCchPrintfW(v10, 0x400u, L"%s\\[%d_%u]%s", *(_QWORD *)a4, pbCancela, v14, a3->cFileName);
  v9 = v15;
  if ( v15 < 0 )
  {
    v39 = 0;
    v38 = v15;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v43, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v43[v16] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v38, 4, byte_180147320, 1, &v39, 4);
    }
    goto LABEL_70;
  }
  if ( !**((_DWORD **)a4 + 3) )
  {
    v17 = *((_DWORD *)a4 + 24) != 0;
    v40 = 1;
    v18 = PlaiHResultFromWin32(v17 ? 4 : 18);
LABEL_29:
    v20 = v18;
    goto LABEL_30;
  }
  v19 = *((_DWORD *)a4 + 23) == 0;
  *((_DWORD *)a4 + 18) = 0;
  if ( CopyFileExW(a2, v11, PlaiFileRecursiveStopCallback, a4, &v40, v19) )
  {
    v20 = 0;
LABEL_25:
    --**((_DWORD **)a4 + 3);
    goto LABEL_30;
  }
  LastError = GetLastError();
  v22 = PlaiHResultFromWin32(LastError);
  v20 = v22;
  if ( v22 >= 0 )
    goto LABEL_25;
  if ( v22 == -2147023661 && *((_DWORD *)a4 + 18) == 1 )
  {
    v18 = PlaiHResultFromWin32(0xDFu);
    v40 = 1;
    goto LABEL_29;
  }
LABEL_30:
  v23 = (struct IXMLDOMElement *)*((_QWORD *)a4 + 7);
  v24 = (struct IXMLDOMDocument *)*((_QWORD *)a4 + 6);
  *((_DWORD *)a4 + 10) = 1;
  v25 = PlaiAddItemToReport(v24, v23, &v41);
  v9 = v25;
  if ( v25 < 0 )
  {
    v39 = 0;
    v38 = v25;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v44, 0x4000000000000800uLL);
      v26 = -1;
      do
        ++v26;
      while ( v44[v26] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v38, 4, byte_180147320, 1, &v39, 4);
    }
    v8 = v41;
    goto LABEL_70;
  }
  v8 = v41;
  v27 = PlaiAddDataToReportItem(*((struct IXMLDOMDocument **)a4 + 6), v41, L"configurationFilesFrom", a2);
  v9 = v27;
  if ( v27 >= 0 )
  {
    if ( v20 < 0 )
      *v11 = 0;
    v29 = PlaiAddDataToReportItem(*((struct IXMLDOMDocument **)a4 + 6), v8, L"configurationFilesTo", v11);
    v9 = v29;
    if ( v29 >= 0 )
    {
      v31 = StringCchPrintfW(v11, 0x400u, L"0x%x", (unsigned int)v20);
      v9 = v31;
      if ( v31 >= 0 )
      {
        v33 = PlaiAddDataToReportItem(*((struct IXMLDOMDocument **)a4 + 6), v8, L"configurationFilesCopyResult", v11);
        v9 = v33;
        if ( v33 >= 0 )
        {
          if ( v40 == 1 )
            v9 = 1;
          goto LABEL_70;
        }
        v39 = 0;
        v38 = v33;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v48, 0x4000000000000800uLL);
          v34 = -1;
          do
            ++v34;
          while ( v48[v34] );
          goto LABEL_44;
        }
      }
      else
      {
        v39 = 0;
        v38 = v31;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v47, 0x4000000000000800uLL);
          v32 = -1;
          do
            ++v32;
          while ( v47[v32] );
          goto LABEL_44;
        }
      }
    }
    else
    {
      v39 = 0;
      v38 = v29;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v46, 0x4000000000000800uLL);
        v30 = -1;
        do
          ++v30;
        while ( v46[v30] );
        goto LABEL_44;
      }
    }
  }
  else
  {
    v39 = 0;
    v38 = v27;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v45, 0x4000000000000800uLL);
      v28 = -1;
      do
        ++v28;
      while ( v45[v28] );
LABEL_44:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v38, 4, byte_180147320, 1, &v39, 4);
    }
  }
LABEL_70:
  PlaiFree(v11, 1);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v8->lpVtbl->Release)(v8);
  return v9;
}

```

## disassembly

```asm
0x18008fdb0  mov     [rsp-8+arg_0], rbx
0x18008fdb5  push    rbp
0x18008fdb6  push    rsi
0x18008fdb7  push    rdi
0x18008fdb8  push    r12
0x18008fdba  push    r13
0x18008fdbc  push    r14
0x18008fdbe  push    r15
0x18008fdc0  lea     rbp, [rsp-320h]
0x18008fdc8  sub     rsp, 420h
0x18008fdcf  mov     rax, cs:__security_cookie
0x18008fdd6  xor     rax, rsp
0x18008fdd9  mov     [rbp+350h+var_40], rax
0x18008fde0  mov     eax, [r8]
0x18008fde3  xor     r13d, r13d
0x18008fde6  mov     [rbp+350h+var_3D0], r13d
0x18008fdea  mov     rdi, r9
0x18008fded  mov     [rbp+350h+var_3C8], r13
0x18008fdf1  mov     rbx, r8
0x18008fdf4  mov     r12, rdx
0x18008fdf7  mov     r14d, r13d
0x18008fdfa  test    al, 10h
0x18008fdfc  jz      short loc_18008FE06
0x18008fdfe  mov     ebx, r13d
0x18008fe01  jmp     loc_1800904A3
0x18008fe06  mov     rcx, [r9+40h]; hHandle
0x18008fe0a  xor     edx, edx; dwMilliseconds
0x18008fe0c  call    cs:__imp_WaitForSingleObject
0x18008fe12  cmp     eax, 102h
0x18008fe17  jz      short loc_18008FE2A
0x18008fe19  mov     ecx, 4D3h; unsigned int
0x18008fe1e  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18008fe23  mov     ebx, eax
0x18008fe25  jmp     loc_1800904A3
0x18008fe2a  xor     r8d, r8d; int
0x18008fe2d  lea     rsi, byte_180147320
0x18008fe34  mov     r9, rsi; char *
0x18008fe37  mov     ecx, 800h; dwBytes
0x18008fe3c  lea     edx, [r8+1]; int
0x18008fe40  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18008fe45  mov     r15, rax
0x18008fe48  test    rax, rax
0x18008fe4b  jnz     loc_18008FF27
0x18008fe51  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008fe58  mov     ebx, 8007000Eh
0x18008fe5d  mov     [rsp+450h+var_3D8], ebx
0x18008fe61  mov     [rsp+450h+var_3E0], r13d
0x18008fe66  jz      loc_1800904A3
0x18008fe6c  mov     rdx, 4000000000000800h; unsigned __int64
0x18008fe76  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008fe7d  jz      loc_1800904A3
0x18008fe83  mov     rax, cs:qword_180169748
0x18008fe8a  and     rax, rdx
0x18008fe8d  cmp     cs:qword_180169748, rax
0x18008fe94  jnz     loc_1800904A3
0x18008fe9a  lea     rcx, [rbp+350h+var_3C0]; unsigned __int16 *
0x18008fe9e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008fea3  lea     rcx, [rbp+350h+var_3C0]
0x18008fea7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008feab  inc     rax
0x18008feae  cmp     [rcx+rax*2], r13w
0x18008feb3  jnz     short loc_18008FEAB
0x18008feb5  lea     ecx, [rax+rax]
0x18008feb8  add     rcx, 2
0x18008febc  lea     rax, [rbp+350h+var_3C0]
0x18008fec0  mov     [rsp+450h+var_3F0], rcx
0x18008fec5  lea     r9, [rsp+450h+var_3D8]
0x18008feca  mov     [rsp+450h+var_3F8], rax
0x18008fecf  lea     rcx, [rsp+450h+var_3E0]
0x18008fed4  mov     [rsp+450h+var_400], 16h
0x18008fedd  lea     rax, aPlaifilerecurs_1; "PlaiFileRecursiveFile"
0x18008fee4  mov     [rsp+450h+var_408], rax
0x18008fee9  lea     rdx, PLA_EVENT_ERROR
0x18008fef0  mov     eax, 4
0x18008fef5  mov     [rsp+450h+var_410], rax
0x18008fefa  mov     [rsp+450h+var_418], rcx
0x18008feff  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18008ff06  mov     [rsp+450h+var_420], 1
0x18008ff0f  mov     qword ptr [rsp+450h+dwCopyFlags], rsi
0x18008ff14  lea     r8d, [rax+1]
0x18008ff18  mov     [rsp+450h+pbCancel], rax
0x18008ff1d  call    EventingWriteEvent
0x18008ff22  jmp     loc_1800904A3
0x18008ff27  mov     rcx, [rdi+50h]
0x18008ff2b  lea     r8, aSDUS; "%s\\[%d_%u]%s"
0x18008ff32  mov     edx, [rcx]
0x18008ff34  lea     eax, [rdx+1]
0x18008ff37  mov     [rcx], eax
0x18008ff39  lea     rax, [rbx+2Ch]
0x18008ff3d  mov     r9, [rdi]
0x18008ff40  mov     rcx, r15; unsigned __int16 *
0x18008ff43  mov     [rsp+450h+var_420], rax
0x18008ff48  mov     eax, [rdi+58h]
0x18008ff4b  mov     [rsp+450h+dwCopyFlags], edx
0x18008ff4f  mov     edx, 400h; unsigned __int64
0x18008ff54  mov     dword ptr [rsp+450h+pbCancel], eax
0x18008ff58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008ff5d  mov     ebx, eax
0x18008ff5f  test    eax, eax
0x18008ff61  jns     loc_18009003F
0x18008ff67  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008ff6e  mov     [rsp+450h+var_3D8], r13d
0x18008ff73  mov     [rsp+450h+var_3E0], eax
0x18008ff77  jz      loc_180090035
0x18008ff7d  mov     rdx, 4000000000000800h; unsigned __int64
0x18008ff87  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008ff8e  jz      loc_180090035
0x18008ff94  mov     rax, cs:qword_180169748
0x18008ff9b  and     rax, rdx
0x18008ff9e  cmp     cs:qword_180169748, rax
0x18008ffa5  jnz     loc_180090035
0x18008ffab  lea     rcx, [rbp+350h+var_340]; unsigned __int16 *
0x18008ffaf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008ffb4  lea     rcx, [rbp+350h+var_340]
0x18008ffb8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008ffbc  inc     rax
0x18008ffbf  cmp     [rcx+rax*2], r13w
0x18008ffc4  jnz     short loc_18008FFBC
0x18008ffc6  lea     ecx, [rax+rax]
0x18008ffc9  add     rcx, 2
0x18008ffcd  lea     rax, [rbp+350h+var_340]
0x18008ffd1  mov     [rsp+450h+var_3F0], rcx
0x18008ffd6  lea     rcx, [rsp+450h+var_3D8]
0x18008ffdb  mov     [rsp+450h+var_3F8], rax
0x18008ffe0  lea     rax, aPlaifilerecurs_1; "PlaiFileRecursiveFile"
0x18008ffe7  mov     [rsp+450h+var_400], 16h
0x18008fff0  mov     [rsp+450h+var_408], rax
0x18008fff5  mov     eax, 4
0x18008fffa  mov     [rsp+450h+var_410], rax
0x18008ffff  mov     [rsp+450h+var_418], rcx
0x180090004  mov     [rsp+450h+var_420], 1
0x18009000d  mov     qword ptr [rsp+450h+dwCopyFlags], rsi
0x180090012  lea     r9, [rsp+450h+var_3E0]
0x180090017  mov     [rsp+450h+pbCancel], rax
0x18009001c  mov     r8d, 5
0x180090022  lea     rdx, PLA_EVENT_ERROR
0x180090029  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180090030  call    EventingWriteEvent
0x180090035  mov     edx, 1
0x18009003a  jmp     loc_180090487
0x18009003f  mov     rax, [rdi+18h]
0x180090043  cmp     [rax], r13d
0x180090046  jnz     short loc_180090063
0x180090048  mov     eax, [rdi+60h]
0x18009004b  neg     eax
0x18009004d  mov     [rbp+350h+var_3D0], 1
0x180090054  sbb     ecx, ecx
0x180090056  and     ecx, 0FFFFFFF2h
0x180090059  add     ecx, 12h; unsigned int
0x18009005c  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180090061  jmp     short loc_1800900D6
0x180090063  cmp     [rdi+5Ch], r13d
0x180090067  lea     r8, ?PlaiFileRecursiveStopCallback@@YAKT_LARGE_INTEGER@@000KKPEAX11@Z; lpProgressRoutine
0x18009006e  mov     eax, r13d
0x180090071  mov     [rdi+48h], r13d
0x180090075  setz    al
0x180090078  mov     r9, rdi; lpData
0x18009007b  mov     [rsp+450h+dwCopyFlags], eax; dwCopyFlags
0x18009007f  mov     rdx, r15; lpNewFileName
0x180090082  lea     rax, [rbp+350h+var_3D0]
0x180090086  mov     rcx, r12; lpExistingFileName
0x180090089  mov     [rsp+450h+pbCancel], rax; pbCancel
0x18009008e  call    cs:__imp_CopyFileExW
0x180090094  test    eax, eax
0x180090096  jz      short loc_18009009D
0x180090098  mov     esi, r13d
0x18009009b  jmp     short loc_1800900B0
0x18009009d  call    cs:__imp_GetLastError
0x1800900a3  mov     ecx, eax; unsigned int
0x1800900a5  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800900aa  mov     esi, eax
0x1800900ac  test    eax, eax
0x1800900ae  js      short loc_1800900B8
0x1800900b0  mov     rax, [rdi+18h]
0x1800900b4  dec     dword ptr [rax]
0x1800900b6  jmp     short loc_1800900D8
0x1800900b8  cmp     eax, 800704D3h
0x1800900bd  jnz     short loc_1800900D8
0x1800900bf  cmp     dword ptr [rdi+48h], 1
0x1800900c3  jnz     short loc_1800900D8
0x1800900c5  mov     ecx, 0DFh; unsigned int
0x1800900ca  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800900cf  mov     [rbp+350h+var_3D0], 1
0x1800900d6  mov     esi, eax
0x1800900d8  mov     rdx, [rdi+38h]; struct IXMLDOMElement *
0x1800900dc  lea     r8, [rbp+350h+var_3C8]; struct IXMLDOMElement **
0x1800900e0  mov     rcx, [rdi+30h]; struct IXMLDOMDocument *
0x1800900e4  mov     dword ptr [rdi+28h], 1
0x1800900eb  call    ?PlaiAddItemToReport@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEAPEAU2@@Z; PlaiAddItemToReport(IXMLDOMDocument *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800900f0  mov     ebx, eax
0x1800900f2  test    eax, eax
0x1800900f4  jns     loc_1800901DF
0x1800900fa  cmp     dword ptr cs:xmmword_180169738, r13d
0x180090101  mov     [rsp+450h+var_3D8], r13d
0x180090106  mov     [rsp+450h+var_3E0], eax
0x18009010a  jz      loc_1800901D6
0x180090110  mov     rdx, 4000000000000800h; unsigned __int64
0x18009011a  test    qword ptr cs:xmmword_180169738+8, rdx
0x180090121  jz      loc_1800901D6
0x180090127  mov     rax, cs:qword_180169748
0x18009012e  and     rax, rdx
0x180090131  cmp     cs:qword_180169748, rax
0x180090138  jnz     loc_1800901D6
0x18009013e  lea     rcx, [rbp+350h+var_2C0]; unsigned __int16 *
0x180090145  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009014a  lea     rcx, [rbp+350h+var_2C0]
0x180090151  or      rax, 0FFFFFFFFFFFFFFFFh
0x180090155  inc     rax
0x180090158  cmp     [rcx+rax*2], r13w
0x18009015d  jnz     short loc_180090155
0x18009015f  lea     ecx, [rax+rax]
0x180090162  add     rcx, 2
0x180090166  lea     rax, [rbp+350h+var_2C0]
0x18009016d  mov     [rsp+450h+var_3F0], rcx
0x180090172  lea     r9, [rsp+450h+var_3E0]
0x180090177  mov     [rsp+450h+var_3F8], rax
0x18009017c  lea     rcx, [rsp+450h+var_3D8]
0x180090181  mov     [rsp+450h+var_400], 16h
0x18009018a  lea     rax, aPlaifilerecurs_1; "PlaiFileRecursiveFile"
0x180090191  mov     [rsp+450h+var_408], rax
0x180090196  lea     rdx, PLA_EVENT_ERROR
0x18009019d  mov     eax, 4
0x1800901a2  mov     [rsp+450h+var_410], rax
0x1800901a7  mov     [rsp+450h+var_418], rcx
0x1800901ac  lea     rcx, byte_180147320
0x1800901b3  mov     [rsp+450h+var_420], 1
0x1800901bc  mov     qword ptr [rsp+450h+dwCopyFlags], rcx
0x1800901c1  lea     r8d, [rax+1]
0x1800901c5  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800901cc  mov     [rsp+450h+pbCancel], rax
0x1800901d1  call    EventingWriteEvent
0x1800901d6  mov     r14, [rbp+350h+var_3C8]
0x1800901da  jmp     loc_180090035
0x1800901df  mov     r14, [rbp+350h+var_3C8]
0x1800901e3  lea     r8, aConfigurationf_2; "configurationFilesFrom"
0x1800901ea  mov     rcx, [rdi+30h]; struct IXMLDOMDocument *
0x1800901ee  mov     rdx, r14; struct IXMLDOMElement *
0x1800901f1  mov     r9, r12; unsigned __int16 *
0x1800901f4  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800901f9  mov     ebx, eax
0x1800901fb  test    eax, eax
0x1800901fd  jns     loc_1800902C3
0x180090203  cmp     dword ptr cs:xmmword_180169738, r13d
0x18009020a  mov     [rsp+450h+var_3D8], r13d
0x18009020f  mov     [rsp+450h+var_3E0], eax
0x180090213  jz      loc_180090035
0x180090219  mov     rdx, 4000000000000800h; unsigned __int64
0x180090223  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009022a  jz      loc_180090035
0x180090230  mov     rax, cs:qword_180169748
0x180090237  and     rax, rdx
0x18009023a  cmp     cs:qword_180169748, rax
0x180090241  jnz     loc_180090035
0x180090247  lea     rcx, [rbp+350h+var_240]; unsigned __int16 *
0x18009024e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180090253  lea     rcx, [rbp+350h+var_240]
0x18009025a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009025e  inc     rax
0x180090261  cmp     [rcx+rax*2], r13w
0x180090266  jnz     short loc_18009025E
0x180090268  lea     ecx, [rax+rax]
0x18009026b  lea     rax, [rbp+350h+var_240]
0x180090272  add     rcx, 2
0x180090276  mov     [rsp+450h+var_3F0], rcx
0x18009027b  lea     rcx, [rsp+450h+var_3D8]
0x180090280  mov     [rsp+450h+var_3F8], rax
0x180090285  lea     rax, aPlaifilerecurs_1; "PlaiFileRecursiveFile"
0x18009028c  mov     [rsp+450h+var_400], 16h
0x180090295  mov     [rsp+450h+var_408], rax
0x18009029a  mov     eax, 4
0x18009029f  mov     [rsp+450h+var_410], rax
0x1800902a4  mov     [rsp+450h+var_418], rcx
0x1800902a9  lea     rcx, byte_180147320
0x1800902b0  mov     [rsp+450h+var_420], 1
0x1800902b9  mov     qword ptr [rsp+450h+dwCopyFlags], rcx
0x1800902be  jmp     loc_180090012
0x1800902c3  test    esi, esi
0x1800902c5  jns     short loc_1800902CB
0x1800902c7  mov     [r15], r13w
0x1800902cb  mov     rcx, [rdi+30h]; struct IXMLDOMDocument *
0x1800902cf  lea     r8, aConfigurationf_1; "configurationFilesTo"
0x1800902d6  mov     r9, r15; unsigned __int16 *
0x1800902d9  mov     rdx, r14; struct IXMLDOMElement *
0x1800902dc  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800902e1  mov     ebx, eax
0x1800902e3  test    eax, eax
0x1800902e5  jns     short loc_18009035B
0x1800902e7  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800902ee  mov     [rsp+450h+var_3D8], r13d
0x1800902f3  mov     [rsp+450h+var_3E0], eax
0x1800902f7  jz      loc_180090035
0x1800902fd  mov     rdx, 4000000000000800h; unsigned __int64
0x180090307  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009030e  jz      loc_180090035
0x180090314  mov     rax, cs:qword_180169748
0x18009031b  and     rax, rdx
0x18009031e  cmp     cs:qword_180169748, rax
0x180090325  jnz     loc_180090035
0x18009032b  lea     rcx, [rbp+350h+var_1C0]; unsigned __int16 *
0x180090332  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
  ... truncated ...
```
