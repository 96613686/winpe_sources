# CTxtEdit::Open(tagVARIANT *,long,long)

- ea: `0x18018a790`
- end: `0x18018ab0e`
- name: `?Open@CTxtEdit@@UEAAJPEAUtagVARIANT@@JJ@Z`
- size: `894`
- prototype: `int(CTxtEdit *__hidden this, struct tagVARIANT *, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800441ac`
- `0x18008b170`
- `0x180098b04`
- `0x180138ae4`
- `0x18018a068`
- `0x18018a790`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018a931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018a931`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18018a7f2`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18018a7f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018a949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018aab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018a949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018aab0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18018aa0c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18018aa0c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18018a8f0`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18018a8f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18018a8d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18018a8d7`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18018aa2c`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18018aa2c`

## pseudocode

```c
__int64 __fastcall CTxtEdit::Open(CTxtEdit *this, struct tagVARIANT *a2, int a3, UINT a4)
{
  DWORD v8; // r13d
  __int64 result; // rax
  int v10; // edi
  struct CDocInfo *DocInfo; // rax
  struct CDocInfo *v12; // r15
  int v13; // edx
  DWORD dwCreationDisposition; // ebx
  HANDLE FileW; // rax
  unsigned __int16 *v16; // rax
  DWORD_PTR dwCookie; // rax
  signed int LastError; // ebx
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, DWORD_PTR *); // rcx
  LONG StreamFlags; // eax
  signed int v21; // r12d
  HCURSOR CursorW; // rax
  int v23; // r8d
  HICON v24; // rbx
  int v25; // r8d
  DWORD_PTR v26; // [rsp+40h] [rbp-29h] BYREF
  __int64 v27; // [rsp+48h] [rbp-21h] BYREF
  struct _editstream hObject; // [rsp+50h] [rbp-19h] BYREF
  struct _editstream v29; // [rsp+70h] [rbp+7h] BYREF
  DWORD dwShareMode; // [rsp+D8h] [rbp+6Fh]
  DWORD dwDesiredAccess; // [rsp+E0h] [rbp+77h] BYREF

  hObject.dwCookie = 0;
  hObject.dwError = 0;
  hObject.pfnCallback = (EDITSTREAMCALLBACK)MyRead;
  v26 = 0;
  v27 = 0;
  if ( !a2 || a4 && (a4 & 0xFFFFFFFE) != 0x4B0 && !IsValidCodePage(a4) )
    return 2147942487LL;
  v8 = a3 & 0xF;
  if ( v8 >= 3 )
    return 2147500033LL;
  v10 = a3 & 0x1000;
  if ( (a3 & 0x1000) == 0 )
    (*(void (__fastcall **)(CTxtEdit *))(*(_QWORD *)this + 120LL))(this);
  DocInfo = CTxtEdit::GetDocInfo((CTxtEdit *)((char *)this - 16));
  v12 = DocInfo;
  if ( !DocInfo )
    return 2147942414LL;
  *((_WORD *)DocInfo + 56) = a3 & 0xFF0F;
  dwDesiredAccess = ~(a3 << 22) & 0x40000000 | 0x80000000;
  v13 = (a3 & 0x200) == 0;
  if ( (a3 & 0x400) == 0 )
    v13 = ((a3 & 0x200) == 0) | 2;
  dwCreationDisposition = (a3 >> 4) & 0xF;
  dwShareMode = v13;
  if ( !dwCreationDisposition )
    dwCreationDisposition = 4;
  if ( a2->vt != 8 || !CW32System::SysStringLen(a2->bstrVal) )
  {
    if ( a2->vt != 13 )
    {
LABEL_32:
      dwDesiredAccess = v8;
      v29 = hObject;
      StreamFlags = GetStreamFlags(&v29, (int *)&dwDesiredAccess, a4);
      if ( a2->vt == 13 && v26 )
        (*(void (__fastcall **)(DWORD_PTR, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v26 + 40LL))(v26, StreamFlags, 0, 0);
      else
        SetFilePointer((HANDLE)hObject.dwCookie, StreamFlags, 0, 0);
      v21 = dwDesiredAccess;
      if ( v10 )
        v21 = dwDesiredAccess | 0x8000;
      CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
      v24 = CTxtEdit::TxSetCursor((CTxtEdit *)((char *)this - 16), CursorW, v23);
      (*(void (__fastcall **)(char *, __int64, __int64, struct _editstream *, __int64 *))(*((_QWORD *)this - 2) + 24LL))(
        (char *)this - 16,
        1097,
        v21 | 0x1000LL,
        &hObject,
        &v27);
      CTxtEdit::TxSetCursor((CTxtEdit *)((char *)this - 16), v24, v25);
      if ( v26 )
      {
        (*(void (__fastcall **)(DWORD_PTR))(*(_QWORD *)v26 + 16LL))(v26);
      }
      else if ( dwShareMode == 3 || v10 )
      {
        if ( a2->vt != 13 && hObject.dwCookie )
          CloseHandle((HANDLE)hObject.dwCookie);
        if ( !v10 )
          *((_QWORD *)v12 + 3) = 0;
      }
      *((_DWORD *)this + 40) &= ~0x4000000u;
      *((_DWORD *)this + 40) |= v10 == 0 ? 0x4000000 : 0;
      return hObject.dwError;
    }
    llVal = (__int64 (__fastcall ***)(_QWORD, GUID *, DWORD_PTR *))a2->llVal;
    if ( llVal )
    {
      result = (**llVal)(llVal, &IID_IStream, &v26);
      if ( (_DWORD)result )
        return result;
      hObject.dwCookie = v26;
      hObject.pfnCallback = (EDITSTREAMCALLBACK)MyStreamRead;
      goto LABEL_32;
    }
    return 2147942487LL;
  }
  FileW = CreateFileW(a2->bstrVal, dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, 0x110000u, 0);
  hObject.dwCookie = (DWORD_PTR)FileW;
  if ( FileW != (HANDLE)-1LL && GetFileType(FileW) == 1 )
  {
    if ( v10 )
      goto LABEL_32;
    v16 = CW32System::SysAllocString(a2->bstrVal);
    *(_QWORD *)v12 = v16;
    if ( v16 )
    {
      dwCookie = hObject.dwCookie;
      *((_WORD *)v12 + 56) |= 0x50u;
      *((_QWORD *)v12 + 3) = dwCookie;
      goto LABEL_32;
    }
    return 2147942414LL;
  }
  LastError = GetLastError();
  if ( hObject.dwCookie != -1 )
    CloseHandle((HANDLE)hObject.dwCookie);
  if ( LastError )
  {
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18018a790  mov     [rsp-8+arg_0], rbx
0x18018a795  push    rbp
0x18018a796  push    rsi
0x18018a797  push    rdi
0x18018a798  push    r12
0x18018a79a  push    r13
0x18018a79c  push    r14
0x18018a79e  push    r15
0x18018a7a0  lea     rbp, [rsp-27h]
0x18018a7a5  sub     rsp, 90h
0x18018a7ac  xor     edi, edi
0x18018a7ae  lea     rax, ?MyRead@@YAK_KPEAEJPEAJ@Z; MyRead(unsigned __int64,uchar *,long,long *)
0x18018a7b5  mov     [rbp+57h+hObject], rdi
0x18018a7b9  mov     r12d, r9d
0x18018a7bc  mov     dword ptr [rbp+57h+hObject+8], edi
0x18018a7bf  mov     ebx, r8d
0x18018a7c2  mov     [rbp+57h+hObject+0Ch], rax
0x18018a7c6  mov     r14, rdx
0x18018a7c9  mov     [rbp+57h+var_80], rdi
0x18018a7cd  mov     rsi, rcx
0x18018a7d0  mov     [rbp+57h+var_78], rdi
0x18018a7d4  test    rdx, rdx
0x18018a7d7  jz      loc_18018AAED
0x18018a7dd  test    r9d, r9d
0x18018a7e0  jz      short loc_18018A806
0x18018a7e2  mov     eax, r9d
0x18018a7e5  and     eax, 0FFFFFFFEh
0x18018a7e8  cmp     eax, 4B0h
0x18018a7ed  jz      short loc_18018A806
0x18018a7ef  mov     ecx, r9d; CodePage
0x18018a7f2  call    cs:__imp_IsValidCodePage
0x18018a7f9  nop     dword ptr [rax+rax+00h]
0x18018a7fe  test    eax, eax
0x18018a800  jz      loc_18018AAED
0x18018a806  mov     r13d, ebx
0x18018a809  and     r13d, 0Fh
0x18018a80d  cmp     r13d, 3
0x18018a811  jb      short loc_18018A81D
0x18018a813  mov     eax, 80004001h
0x18018a818  jmp     loc_18018AAF2
0x18018a81d  mov     edi, ebx
0x18018a81f  and     edi, 1000h
0x18018a825  jnz     short loc_18018A836
0x18018a827  mov     rax, [rsi]
0x18018a82a  mov     rcx, rsi
0x18018a82d  mov     rax, [rax+78h]
0x18018a831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018a836  lea     rcx, [rsi-10h]; this
0x18018a83a  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18018a83f  mov     r15, rax
0x18018a842  test    rax, rax
0x18018a845  jz      loc_18018AAE6
0x18018a84b  movzx   ecx, bx
0x18018a84e  mov     eax, 0FF0Fh
0x18018a853  and     cx, ax
0x18018a856  mov     eax, ebx
0x18018a858  shl     eax, 16h
0x18018a85b  mov     [r15+70h], cx
0x18018a860  not     eax
0x18018a862  and     eax, 0C0000000h
0x18018a867  mov     ecx, ebx
0x18018a869  shr     ecx, 9
0x18018a86c  bts     eax, 1Fh
0x18018a870  not     ecx
0x18018a872  mov     [rbp+57h+dwDesiredAccess], eax
0x18018a875  and     ecx, 1
0x18018a878  mov     eax, 4
0x18018a87d  or      ecx, 2
0x18018a880  mov     edx, ecx
0x18018a882  and     edx, 0FFFFFFFDh
0x18018a885  bt      ebx, 0Ah
0x18018a889  cmovnb  edx, ecx
0x18018a88c  sar     ebx, 4
0x18018a88f  and     ebx, 0Fh
0x18018a892  mov     [rbp+57h+dwShareMode], edx
0x18018a895  cmovz   ebx, eax
0x18018a898  cmp     word ptr [r14], 8
0x18018a89d  jnz     loc_18018A972
0x18018a8a3  mov     rcx, [r14+8]; unsigned __int16 *
0x18018a8a7  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x18018a8ac  test    eax, eax
0x18018a8ae  jz      loc_18018A972
0x18018a8b4  mov     r8d, [rbp+57h+dwShareMode]; dwShareMode
0x18018a8b8  xor     r9d, r9d; lpSecurityAttributes
0x18018a8bb  mov     edx, [rbp+57h+dwDesiredAccess]; dwDesiredAccess
0x18018a8be  mov     rcx, [r14+8]; lpFileName
0x18018a8c2  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18018a8cb  mov     [rsp+0C0h+dwFlagsAndAttributes], 110000h; dwFlagsAndAttributes
0x18018a8d3  mov     [rsp+0C0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18018a8d7  call    cs:__imp_CreateFileW
0x18018a8de  nop     dword ptr [rax+rax+00h]
0x18018a8e3  mov     [rbp+57h+hObject], rax
0x18018a8e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018a8eb  jz      short loc_18018A931
0x18018a8ed  mov     rcx, rax; hFile
0x18018a8f0  call    cs:__imp_GetFileType
0x18018a8f7  nop     dword ptr [rax+rax+00h]
0x18018a8fc  cmp     eax, 1
0x18018a8ff  jnz     short loc_18018A931
0x18018a901  test    edi, edi
0x18018a903  jnz     loc_18018A9B7
0x18018a909  mov     rcx, [r14+8]; unsigned __int16 *
0x18018a90d  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x18018a912  mov     [r15], rax
0x18018a915  test    rax, rax
0x18018a918  jz      loc_18018AAE6
0x18018a91e  mov     rax, [rbp+57h+hObject]
0x18018a922  or      word ptr [r15+70h], 50h
0x18018a928  mov     [r15+18h], rax
0x18018a92c  jmp     loc_18018A9B7
0x18018a931  call    cs:__imp_GetLastError
0x18018a938  nop     dword ptr [rax+rax+00h]
0x18018a93d  mov     rcx, [rbp+57h+hObject]; hObject
0x18018a941  mov     ebx, eax
0x18018a943  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018a947  jz      short loc_18018A955
0x18018a949  call    cs:__imp_CloseHandle
0x18018a950  nop     dword ptr [rax+rax+00h]
0x18018a955  test    ebx, ebx
0x18018a957  jnz     short loc_18018A960
0x18018a959  mov     ebx, 80070057h
0x18018a95e  jmp     short loc_18018A96B
0x18018a960  jle     short loc_18018A96B
0x18018a962  movzx   ebx, bx
0x18018a965  or      ebx, 80070000h
0x18018a96b  mov     eax, ebx
0x18018a96d  jmp     loc_18018AAF2
0x18018a972  cmp     word ptr [r14], 0Dh
0x18018a977  jnz     short loc_18018A9B7
0x18018a979  mov     rcx, [r14+8]
0x18018a97d  test    rcx, rcx
0x18018a980  jz      loc_18018AAED
0x18018a986  mov     rax, [rcx]
0x18018a989  lea     r8, [rbp+57h+var_80]
0x18018a98d  lea     rdx, IID_IStream
0x18018a994  mov     rax, [rax]
0x18018a997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018a99c  test    eax, eax
0x18018a99e  jnz     loc_18018AAF2
0x18018a9a4  mov     rax, [rbp+57h+var_80]
0x18018a9a8  mov     [rbp+57h+hObject], rax
0x18018a9ac  lea     rax, ?MyStreamRead@@YAK_KPEAEJPEAJ@Z; MyStreamRead(unsigned __int64,uchar *,long,long *)
0x18018a9b3  mov     [rbp+57h+hObject+0Ch], rax
0x18018a9b7  movups  xmm0, xmmword ptr [rbp+57h+hObject]
0x18018a9bb  mov     eax, [rbp+57h+var_60]
0x18018a9be  lea     rdx, [rbp+57h+dwDesiredAccess]; int *
0x18018a9c2  mov     r8d, r12d; int
0x18018a9c5  mov     [rbp+57h+dwDesiredAccess], r13d
0x18018a9c9  lea     rcx, [rbp+57h+var_50]; struct _editstream
0x18018a9cd  movaps  xmmword ptr [rbp+57h+var_50.dwCookie], xmm0
0x18018a9d1  mov     dword ptr [rbp+57h+var_50.pfnCallback+4], eax
0x18018a9d4  call    ?GetStreamFlags@@YAJU_editstream@@AEAJJ@Z; GetStreamFlags(_editstream,long &,long)
0x18018a9d9  cmp     word ptr [r14], 0Dh
0x18018a9de  jnz     short loc_18018AA00
0x18018a9e0  mov     rcx, [rbp+57h+var_80]
0x18018a9e4  test    rcx, rcx
0x18018a9e7  jz      short loc_18018AA00
0x18018a9e9  movsxd  rdx, eax
0x18018a9ec  xor     r9d, r9d
0x18018a9ef  mov     rax, [rcx]
0x18018a9f2  xor     r8d, r8d
0x18018a9f5  mov     rax, [rax+28h]
0x18018a9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018a9fe  jmp     short loc_18018AA18
0x18018aa00  mov     rcx, [rbp+57h+hObject]; hFile
0x18018aa04  xor     r9d, r9d; dwMoveMethod
0x18018aa07  xor     r8d, r8d; lpDistanceToMoveHigh
0x18018aa0a  mov     edx, eax; lDistanceToMove
0x18018aa0c  call    cs:__imp_SetFilePointer
0x18018aa13  nop     dword ptr [rax+rax+00h]
0x18018aa18  mov     r12d, [rbp+57h+dwDesiredAccess]
0x18018aa1c  test    edi, edi
0x18018aa1e  jz      short loc_18018AA25
0x18018aa20  bts     r12d, 0Fh
0x18018aa25  mov     edx, 7F02h; lpCursorName
0x18018aa2a  xor     ecx, ecx; hInstance
0x18018aa2c  call    cs:__imp_LoadCursorW
0x18018aa33  nop     dword ptr [rax+rax+00h]
0x18018aa38  lea     r13, [rsi-10h]
0x18018aa3c  mov     rdx, rax; HICON
0x18018aa3f  mov     rcx, r13; this
0x18018aa42  call    ?TxSetCursor@CTxtEdit@@QEAAPEAUHICON__@@PEAU2@H@Z; CTxtEdit::TxSetCursor(HICON__ *,int)
0x18018aa47  mov     rdx, [rsi-10h]
0x18018aa4b  lea     rcx, [rbp+57h+var_78]
0x18018aa4f  mov     rbx, rax
0x18018aa52  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx
0x18018aa57  movsxd  r8, r12d
0x18018aa5a  lea     r9, [rbp+57h+hObject]
0x18018aa5e  bts     r8, 0Ch
0x18018aa63  mov     rcx, r13
0x18018aa66  mov     rax, [rdx+18h]
0x18018aa6a  mov     edx, 449h
0x18018aa6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018aa74  mov     rdx, rbx; HICON
0x18018aa77  mov     rcx, r13; this
0x18018aa7a  call    ?TxSetCursor@CTxtEdit@@QEAAPEAUHICON__@@PEAU2@H@Z; CTxtEdit::TxSetCursor(HICON__ *,int)
0x18018aa7f  mov     rcx, [rbp+57h+var_80]
0x18018aa83  test    rcx, rcx
0x18018aa86  jz      short loc_18018AA96
0x18018aa88  mov     rax, [rcx]
0x18018aa8b  mov     rax, [rax+10h]
0x18018aa8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018aa94  jmp     short loc_18018AAC8
0x18018aa96  cmp     [rbp+57h+dwShareMode], 3
0x18018aa9a  jz      short loc_18018AAA0
0x18018aa9c  test    edi, edi
0x18018aa9e  jz      short loc_18018AAC8
0x18018aaa0  cmp     word ptr [r14], 0Dh
0x18018aaa5  jz      short loc_18018AABC
0x18018aaa7  mov     rcx, [rbp+57h+hObject]; hObject
0x18018aaab  test    rcx, rcx
0x18018aaae  jz      short loc_18018AABC
0x18018aab0  call    cs:__imp_CloseHandle
0x18018aab7  nop     dword ptr [rax+rax+00h]
0x18018aabc  test    edi, edi
0x18018aabe  jnz     short loc_18018AAC8
0x18018aac0  mov     qword ptr [r15+18h], 0
0x18018aac8  btr     dword ptr [rsi+0A0h], 1Ah
0x18018aad0  neg     edi
0x18018aad2  sbb     eax, eax
0x18018aad4  not     eax
0x18018aad6  and     eax, 4000000h
0x18018aadb  or      [rsi+0A0h], eax
0x18018aae1  mov     eax, dword ptr [rbp+57h+hObject+8]
0x18018aae4  jmp     short loc_18018AAF2
0x18018aae6  mov     eax, 8007000Eh
0x18018aaeb  jmp     short loc_18018AAF2
0x18018aaed  mov     eax, 80070057h
0x18018aaf2  mov     rbx, [rsp+0C0h+arg_0]
0x18018aafa  add     rsp, 90h
0x18018ab01  pop     r15
0x18018ab03  pop     r14
0x18018ab05  pop     r13
0x18018ab07  pop     r12
0x18018ab09  pop     rdi
0x18018ab0a  pop     rsi
0x18018ab0b  pop     rbp
0x18018ab0c  retn
```
