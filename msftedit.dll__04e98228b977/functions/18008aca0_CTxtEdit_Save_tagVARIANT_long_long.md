# CTxtEdit::Save(tagVARIANT *,long,long)

- ea: `0x18008aca0`
- end: `0x18008b16a`
- name: `?Save@CTxtEdit@@UEAAJPEAUtagVARIANT@@JJ@Z`
- size: `1226`
- prototype: `int(CTxtEdit *__hidden this, struct tagVARIANT *, int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800441ac`
- `0x18008aca0`
- `0x18008b170`
- `0x180098b04`
- `0x1800de04c`
- `0x1800fee8c`
- `0x180138ae4`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b11c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b11c`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18008aec9`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18008aec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ae94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008afb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ae94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008afb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b134`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18008b00f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18008b00f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008aff2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008aff2`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18008b0c0`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18008b0c0`

## pseudocode

```c
__int64 __fastcall CTxtEdit::Save(CTxtEdit *this, struct tagVARIANT *a2, unsigned int a3, UINT a4)
{
  struct CDocInfo *DocInfo; // rsi
  int v9; // edx
  int v10; // r14d
  int v11; // ecx
  __int64 result; // rax
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, void **); // rcx
  int v14; // ebx
  unsigned __int16 *bstrVal; // rcx
  unsigned __int16 *v16; // rax
  unsigned int v17; // r13d
  DWORD v18; // edx
  void *v19; // rcx
  DWORD dwCreationDisposition; // eax
  HANDLE FileW; // rax
  int v22; // edi
  __int16 *v23; // rdx
  HCURSOR CursorW; // rax
  int v25; // r8d
  HICON v26; // rbx
  int v27; // r8d
  signed int LastError; // ebx
  __int16 v29; // [rsp+40h] [rbp-30h] BYREF
  CTxtEdit *v30; // [rsp+48h] [rbp-28h]
  int v31; // [rsp+50h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v33; // [rsp+60h] [rbp-10h]
  signed int (__fastcall *v34)(void *, unsigned __int8 *, DWORD, DWORD *); // [rsp+64h] [rbp-Ch]
  void *v36; // [rsp+B8h] [rbp+48h] BYREF

  hObject = 0;
  v33 = 0;
  v34 = MyWrite;
  if ( !a2 || a2->vt != 13 )
  {
    v31 = 0;
    v30 = (CTxtEdit *)((char *)this - 16);
    DocInfo = CTxtEdit::GetDocInfo((CTxtEdit *)((char *)this - 16));
    if ( a4 && (a4 & 0xFFFFFFFE) != 0x4B0 && !IsValidCodePage(a4) || a3 > 0x1FFF || (a3 & 0x100) != 0 )
      return 2147942487LL;
    if ( (a3 & 0xF) >= 3 )
      return 2147500033LL;
    if ( !DocInfo )
      return 2147942414LL;
    v9 = 0;
    v10 = 1;
    LODWORD(v36) = 0;
    if ( a2 )
    {
      if ( a2->vt == 8 )
      {
        bstrVal = a2->bstrVal;
        if ( bstrVal )
        {
          if ( CW32System::SysStringLen(bstrVal)
            && (!*(_QWORD *)DocInfo || (unsigned int)CW32System::wcscmp(
                                                       a2->bstrVal,
                                                       *(const unsigned __int16 **)DocInfo)) )
          {
            CTxtEdit::CloseFile(v30, 0);
            v16 = CW32System::SysAllocString(a2->bstrVal);
            *(_QWORD *)DocInfo = v16;
            if ( v16 )
            {
              v9 = 1;
              *((_WORD *)DocInfo + 56) &= 0xFF0Fu;
              goto LABEL_8;
            }
            return 2147942414LL;
          }
          v9 = (int)v36;
        }
      }
    }
LABEL_8:
    v11 = *((unsigned __int16 *)DocInfo + 56);
    if ( (a3 & 0xF) == 0 )
      a3 |= v11 & 0xF;
    if ( (a3 & 0xF0) == 0 )
      a3 |= v11 & 0xF0;
    if ( (a3 & 0xF00) == 0 )
      a3 |= v11 & 0xF00;
    if ( !a4 )
      a4 = *((unsigned __int16 *)DocInfo + 57);
    if ( a3 != v11 || (_WORD)a4 != *((_WORD *)DocInfo + 57) )
      v9 = 1;
    *((_WORD *)DocInfo + 56) = a3;
    if ( !**((_QWORD **)this + 30) )
      return 2147500037LL;
    if ( (*((_DWORD *)this + 40) & 0x4000000) != 0 && !v9 )
      return 0;
    v17 = 2;
    v18 = ((a3 >> 9) & 1) == 0;
    if ( (a3 & 0x400) == 0 )
      v18 = (((a3 >> 9) & 1) == 0) | 2;
    v19 = (void *)*((_QWORD *)DocInfo + 3);
    dwCreationDisposition = ((int)a3 >> 4) & 0xF;
    LODWORD(v30) = v18;
    if ( !dwCreationDisposition )
      dwCreationDisposition = 1;
    LODWORD(v36) = dwCreationDisposition;
    if ( v19 )
    {
      CloseHandle(v19);
      dwCreationDisposition = (unsigned int)v36;
      v18 = (unsigned int)v30;
      *((_QWORD *)DocInfo + 3) = 0;
    }
    FileW = CreateFileW(*(LPCWSTR *)DocInfo, 0xC0000000, v18, 0, dwCreationDisposition, 0x80u, 0);
    hObject = FileW;
    if ( FileW == (HANDLE)-1LL || GetFileType(FileW) != 1 )
    {
      LastError = GetLastError();
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
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
    v22 = a3 & 0xF;
    *((_QWORD *)DocInfo + 3) = hObject;
    if ( v22 == 1 )
    {
      v10 = 2;
    }
    else
    {
      if ( v22 == 3 )
      {
        v10 = 1572872;
LABEL_74:
        CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
        v26 = CTxtEdit::TxSetCursor((CTxtEdit *)((char *)this - 16), CursorW, v25);
        (*(void (__fastcall **)(char *, __int64, _QWORD, HANDLE *, _QWORD))(*((_QWORD *)this - 2) + 24LL))(
          (char *)this - 16,
          1098,
          v10,
          &hObject,
          0);
        CTxtEdit::TxSetCursor((CTxtEdit *)((char *)this - 16), v26, v27);
        if ( (_DWORD)v30 == 3 )
        {
          CloseHandle(*((HANDLE *)DocInfo + 3));
          *((_QWORD *)DocInfo + 3) = 0;
        }
        *((_DWORD *)this + 40) |= 0x4000000u;
        return v33;
      }
      if ( (a4 & 0xFFFFFFFE) == 0x4B0 || a4 == 65001 )
      {
        LOWORD(v36) = -257;
        v29 = -2;
        if ( a4 == 65001 )
        {
          v17 = 3;
          v23 = (__int16 *)&szUTF8BOM;
        }
        else if ( a4 == 1200 )
        {
          v10 = 17;
          v23 = (__int16 *)&v36;
        }
        else
        {
          v23 = &v29;
        }
        v34(hObject, (unsigned __int8 *)v23, v17, (DWORD *)&v31);
      }
    }
    if ( a4 && a4 != 1200 )
      v10 |= (a4 << 16) | 0x20;
    goto LABEL_74;
  }
  llVal = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))a2->llVal;
  if ( !llVal )
    return 2147942487LL;
  v36 = 0;
  result = (**llVal)(llVal, &IID_IStream, &v36);
  if ( !(_DWORD)result )
  {
    hObject = v36;
    v34 = (signed int (__fastcall *)(void *, unsigned __int8 *, DWORD, DWORD *))MyStreamWrite;
    if ( !a4 || a4 == 1200 )
      v14 = ((a3 & 0xF) == 1) + 1;
    else
      v14 = (((a3 & 0xF) == 1) + 1) | (a4 << 16) | 0x20;
    (*(void (__fastcall **)(char *, __int64, _QWORD, HANDLE *, _QWORD))(*((_QWORD *)this - 2) + 24LL))(
      (char *)this - 16,
      1098,
      v14,
      &hObject,
      0);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
    return v33;
  }
  return result;
}

```

## disassembly

```asm
0x18008aca0  mov     [rsp-38h+arg_10], rbx
0x18008aca5  mov     [rsp-38h+arg_0], rcx
0x18008acaa  push    rbp
0x18008acab  push    rsi
0x18008acac  push    rdi
0x18008acad  push    r12
0x18008acaf  push    r13
0x18008acb1  push    r14
0x18008acb3  push    r15
0x18008acb5  mov     rbp, rsp
0x18008acb8  sub     rsp, 70h
0x18008acbc  xor     r14d, r14d
0x18008acbf  lea     rax, ?MyWrite@@YAK_KPEAEJPEAJ@Z; MyWrite(unsigned __int64,uchar *,long,long *)
0x18008acc6  mov     [rbp+hObject], r14
0x18008acca  mov     ebx, r9d
0x18008accd  mov     [rbp+var_10], r14d
0x18008acd1  mov     edi, r8d
0x18008acd4  mov     [rbp+var_C], rax
0x18008acd8  mov     r15, rdx
0x18008acdb  mov     rsi, rcx
0x18008acde  test    rdx, rdx
0x18008ace1  jnz     loc_18008ADD3
0x18008ace7  lea     rax, [rcx-10h]
0x18008aceb  mov     [rbp+var_20], r14d
0x18008acef  mov     rcx, rax; this
0x18008acf2  mov     [rbp+var_28], rax
0x18008acf6  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18008acfb  mov     rsi, rax
0x18008acfe  mov     r12d, 4B0h
0x18008ad04  test    ebx, ebx
0x18008ad06  jnz     loc_18008AEB9
0x18008ad0c  cmp     edi, 1FFFh
0x18008ad12  ja      loc_18008ADE6
0x18008ad18  bt      edi, 8
0x18008ad1c  jb      loc_18008ADE6
0x18008ad22  mov     r13d, edi
0x18008ad25  and     r13d, 0Fh
0x18008ad29  cmp     r13d, 3
0x18008ad2d  jnb     loc_18008AEE2
0x18008ad33  test    rsi, rsi
0x18008ad36  jz      loc_18008B160
0x18008ad3c  mov     edx, r14d
0x18008ad3f  mov     r14d, 1
0x18008ad45  mov     dword ptr [rbp+arg_8], edx
0x18008ad48  test    r15, r15
0x18008ad4b  jnz     loc_18008AEEC
0x18008ad51  movzx   ecx, word ptr [rsi+70h]
0x18008ad55  test    r13d, r13d
0x18008ad58  jnz     short loc_18008AD61
0x18008ad5a  mov     eax, ecx
0x18008ad5c  and     eax, 0Fh
0x18008ad5f  or      edi, eax
0x18008ad61  test    dil, 0F0h
0x18008ad65  jnz     short loc_18008AD70
0x18008ad67  mov     eax, ecx
0x18008ad69  and     eax, 0F0h
0x18008ad6e  or      edi, eax
0x18008ad70  mov     r8d, 0F00h
0x18008ad76  test    r8d, edi
0x18008ad79  jnz     short loc_18008AD82
0x18008ad7b  mov     eax, ecx
0x18008ad7d  and     eax, r8d
0x18008ad80  or      edi, eax
0x18008ad82  test    ebx, ebx
0x18008ad84  jnz     short loc_18008AD8A
0x18008ad86  movzx   ebx, word ptr [rsi+72h]
0x18008ad8a  cmp     edi, ecx
0x18008ad8c  jnz     loc_18008AF5B
0x18008ad92  cmp     bx, [rsi+72h]
0x18008ad96  jnz     loc_18008AF5B
0x18008ad9c  mov     r15, [rbp+arg_0]
0x18008ada0  mov     [rsi+70h], di
0x18008ada4  mov     rax, [r15+0F0h]
0x18008adab  cmp     qword ptr [rax], 0
0x18008adaf  jnz     loc_18008AF63
0x18008adb5  mov     eax, 80004005h
0x18008adba  mov     rbx, [rsp+70h+arg_10]
0x18008adc2  add     rsp, 70h
0x18008adc6  pop     r15
0x18008adc8  pop     r14
0x18008adca  pop     r13
0x18008adcc  pop     r12
0x18008adce  pop     rdi
0x18008adcf  pop     rsi
0x18008add0  pop     rbp
0x18008add1  retn
0x18008add3  cmp     word ptr [rdx], 0Dh
0x18008add7  jnz     loc_18008ACE7
0x18008addd  mov     rcx, [rdx+8]
0x18008ade1  test    rcx, rcx
0x18008ade4  jnz     short loc_18008ADF7
0x18008ade6  mov     eax, 80070057h
0x18008adeb  jmp     short loc_18008ADBA
0x18008aded  jg      loc_18008B152
0x18008adf3  mov     eax, ebx
0x18008adf5  jmp     short loc_18008ADBA
0x18008adf7  mov     [rbp+arg_8], r14
0x18008adfb  lea     r8, [rbp+arg_8]
0x18008adff  mov     rax, [rcx]
0x18008ae02  lea     rdx, IID_IStream
0x18008ae09  mov     rax, [rax]
0x18008ae0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae11  test    eax, eax
0x18008ae13  jnz     short loc_18008ADBA
0x18008ae15  mov     rax, [rbp+arg_8]
0x18008ae19  and     dil, 0Fh
0x18008ae1d  mov     [rbp+hObject], rax
0x18008ae21  lea     rax, ?MyStreamWrite@@YAK_KPEAEJPEAJ@Z; MyStreamWrite(unsigned __int64,uchar *,long,long *)
0x18008ae28  mov     [rbp+var_C], rax
0x18008ae2c  mov     eax, r14d
0x18008ae2f  mov     r14d, 1
0x18008ae35  cmp     dil, r14b
0x18008ae38  setz    al
0x18008ae3b  add     eax, r14d
0x18008ae3e  test    ebx, ebx
0x18008ae40  jz      short loc_18008AE57
0x18008ae42  mov     r12d, 4B0h
0x18008ae48  cmp     ebx, r12d
0x18008ae4b  jz      short loc_18008AE57
0x18008ae4d  shl     ebx, 10h
0x18008ae50  or      ebx, eax
0x18008ae52  or      ebx, 20h
0x18008ae55  jmp     short loc_18008AE59
0x18008ae57  mov     ebx, eax
0x18008ae59  lea     rcx, [rsi-10h]
0x18008ae5d  movsxd  r8, ebx
0x18008ae60  mov     rax, [rcx]
0x18008ae63  lea     r9, [rbp+hObject]
0x18008ae67  mov     edx, 44Ah
0x18008ae6c  mov     qword ptr [rsp+70h+dwCreationDisposition], 0
0x18008ae75  mov     rax, [rax+18h]
0x18008ae79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae7e  mov     rcx, [rbp+arg_8]
0x18008ae82  mov     rax, [rcx]
0x18008ae85  mov     rax, [rax+10h]
0x18008ae89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae8e  jmp     short loc_18008AEB1
0x18008ae90  mov     rcx, [rsi+18h]; hObject
0x18008ae94  call    cs:__imp_CloseHandle
0x18008ae9b  nop     dword ptr [rax+rax+00h]
0x18008aea0  mov     qword ptr [rsi+18h], 0
0x18008aea8  bts     dword ptr [r15+0A0h], 1Ah
0x18008aeb1  mov     eax, [rbp+var_10]
0x18008aeb4  jmp     loc_18008ADBA
0x18008aeb9  mov     ecx, ebx
0x18008aebb  and     ecx, 0FFFFFFFEh
0x18008aebe  cmp     ecx, r12d
0x18008aec1  jz      loc_18008AD0C
0x18008aec7  mov     ecx, ebx; CodePage
0x18008aec9  call    cs:__imp_IsValidCodePage
0x18008aed0  nop     dword ptr [rax+rax+00h]
0x18008aed5  test    eax, eax
0x18008aed7  jz      loc_18008ADE6
0x18008aedd  jmp     loc_18008AD0C
0x18008aee2  mov     eax, 80004001h
0x18008aee7  jmp     loc_18008ADBA
0x18008aeec  cmp     word ptr [r15], 8
0x18008aef1  jnz     loc_18008AD51
0x18008aef7  mov     rcx, [r15+8]; unsigned __int16 *
0x18008aefb  test    rcx, rcx
0x18008aefe  jz      loc_18008AD51
0x18008af04  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x18008af09  test    eax, eax
0x18008af0b  jz      short loc_18008AF53
0x18008af0d  mov     rdx, [rsi]; unsigned __int16 *
0x18008af10  test    rdx, rdx
0x18008af13  jz      short loc_18008AF22
0x18008af15  mov     rcx, [r15+8]; unsigned __int16 *
0x18008af19  call    ?wcscmp@CW32System@@SAHPEBG0@Z; CW32System::wcscmp(ushort const *,ushort const *)
0x18008af1e  test    eax, eax
0x18008af20  jz      short loc_18008AF53
0x18008af22  mov     rcx, [rbp+var_28]; this
0x18008af26  xor     edx, edx; int
0x18008af28  call    ?CloseFile@CTxtEdit@@QEAAJH@Z; CTxtEdit::CloseFile(int)
0x18008af2d  mov     rcx, [r15+8]; unsigned __int16 *
0x18008af31  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x18008af36  mov     [rsi], rax
0x18008af39  test    rax, rax
0x18008af3c  jz      loc_18008B160
0x18008af42  mov     eax, 0FF0Fh
0x18008af47  mov     edx, r14d
0x18008af4a  and     [rsi+70h], ax
0x18008af4e  jmp     loc_18008AD51
0x18008af53  mov     edx, dword ptr [rbp+arg_8]
0x18008af56  jmp     loc_18008AD51
0x18008af5b  mov     edx, r14d
0x18008af5e  jmp     loc_18008AD9C
0x18008af63  test    dword ptr [r15+0A0h], 4000000h
0x18008af6e  jz      short loc_18008AF7B
0x18008af70  test    edx, edx
0x18008af72  jnz     short loc_18008AF7B
0x18008af74  xor     eax, eax
0x18008af76  jmp     loc_18008ADBA
0x18008af7b  mov     ecx, edi
0x18008af7d  mov     r13d, 2
0x18008af83  shr     ecx, 9
0x18008af86  mov     eax, edi
0x18008af88  not     ecx
0x18008af8a  and     ecx, r14d
0x18008af8d  or      ecx, r13d
0x18008af90  mov     edx, ecx
0x18008af92  and     edx, 0FFFFFFFDh
0x18008af95  bt      edi, 0Ah
0x18008af99  cmovnb  edx, ecx
0x18008af9c  mov     rcx, [rsi+18h]; hObject
0x18008afa0  sar     eax, 4
0x18008afa3  and     eax, 0Fh
0x18008afa6  mov     dword ptr [rbp+var_28], edx
0x18008afa9  cmovz   eax, r14d
0x18008afad  mov     dword ptr [rbp+arg_8], eax
0x18008afb0  test    rcx, rcx
0x18008afb3  jz      short loc_18008AFCF
0x18008afb5  call    cs:__imp_CloseHandle
0x18008afbc  nop     dword ptr [rax+rax+00h]
0x18008afc1  mov     eax, dword ptr [rbp+arg_8]
0x18008afc4  mov     edx, dword ptr [rbp+var_28]
0x18008afc7  mov     qword ptr [rsi+18h], 0
0x18008afcf  mov     rcx, [rsi]; lpFileName
0x18008afd2  mov     r8d, edx; dwShareMode
0x18008afd5  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18008afde  mov     edx, 0C0000000h; dwDesiredAccess
0x18008afe3  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008afeb  xor     r9d, r9d; lpSecurityAttributes
0x18008afee  mov     [rsp+70h+dwCreationDisposition], eax; dwCreationDisposition
0x18008aff2  call    cs:__imp_CreateFileW
0x18008aff9  nop     dword ptr [rax+rax+00h]
0x18008affe  mov     [rbp+hObject], rax
0x18008b002  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008b006  jz      loc_18008B11C
0x18008b00c  mov     rcx, rax; hFile
0x18008b00f  call    cs:__imp_GetFileType
0x18008b016  nop     dword ptr [rax+rax+00h]
0x18008b01b  cmp     eax, r14d
0x18008b01e  jnz     loc_18008B11C
0x18008b024  mov     rax, [rbp+hObject]
0x18008b028  and     edi, 0Fh
0x18008b02b  mov     [rsi+18h], rax
0x18008b02f  cmp     edi, r14d
0x18008b032  jnz     short loc_18008B039
0x18008b034  mov     r14d, r13d
0x18008b037  jmp     short loc_18008B0A7
0x18008b039  cmp     edi, 3
0x18008b03c  jnz     short loc_18008B046
0x18008b03e  mov     r14d, 180008h
0x18008b044  jmp     short loc_18008B0B9
0x18008b046  mov     eax, ebx
0x18008b048  mov     ecx, 0FDE9h
0x18008b04d  and     eax, 0FFFFFFFEh
0x18008b050  cmp     eax, r12d
0x18008b053  jz      short loc_18008B059
0x18008b055  cmp     ebx, ecx
0x18008b057  jnz     short loc_18008B0A7
0x18008b059  mov     eax, 0FEFFh
0x18008b05e  mov     word ptr [rbp+arg_8], ax
0x18008b062  mov     eax, 0FFFEh
0x18008b067  mov     [rbp+var_30], ax
0x18008b06b  cmp     ebx, ecx
0x18008b06d  jnz     short loc_18008B07E
0x18008b06f  mov     r13d, 3
0x18008b075  lea     rdx, ?szUTF8BOM@@3QBEB; uchar const near * const szUTF8BOM
0x18008b07c  jmp     short loc_18008B093
0x18008b07e  cmp     ebx, r12d
0x18008b081  jnz     short loc_18008B08F
0x18008b083  mov     r14d, 11h
0x18008b089  lea     rdx, [rbp+arg_8]
0x18008b08d  jmp     short loc_18008B093
0x18008b08f  lea     rdx, [rbp+var_30]
0x18008b093  mov     rcx, [rbp+hObject]
0x18008b097  lea     r9, [rbp+var_20]
0x18008b09b  mov     rax, [rbp+var_C]
0x18008b09f  mov     r8d, r13d
0x18008b0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b0a7  test    ebx, ebx
0x18008b0a9  jz      short loc_18008B0B9
0x18008b0ab  cmp     ebx, r12d
0x18008b0ae  jz      short loc_18008B0B9
0x18008b0b0  shl     ebx, 10h
0x18008b0b3  or      ebx, 20h
0x18008b0b6  or      r14d, ebx
0x18008b0b9  mov     edx, 7F02h; lpCursorName
0x18008b0be  xor     ecx, ecx; hInstance
0x18008b0c0  call    cs:__imp_LoadCursorW
0x18008b0c7  nop     dword ptr [rax+rax+00h]
0x18008b0cc  lea     rdi, [r15-10h]
0x18008b0d0  mov     rdx, rax; HICON
0x18008b0d3  mov     rcx, rdi; this
0x18008b0d6  call    ?TxSetCursor@CTxtEdit@@QEAAPEAUHICON__@@PEAU2@H@Z; CTxtEdit::TxSetCursor(HICON__ *,int)
0x18008b0db  mov     rdx, [rdi]
0x18008b0de  lea     r9, [rbp+hObject]
0x18008b0e2  mov     rbx, rax
0x18008b0e5  movsxd  r8, r14d
0x18008b0e8  mov     rcx, rdi
0x18008b0eb  mov     qword ptr [rsp+70h+dwCreationDisposition], 0
0x18008b0f4  mov     rax, [rdx+18h]
0x18008b0f8  mov     edx, 44Ah
0x18008b0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b102  mov     rdx, rbx; HICON
0x18008b105  mov     rcx, rdi; this
0x18008b108  call    ?TxSetCursor@CTxtEdit@@QEAAPEAUHICON__@@PEAU2@H@Z; CTxtEdit::TxSetCursor(HICON__ *,int)
0x18008b10d  cmp     dword ptr [rbp+var_28], 3
  ... truncated ...
```
