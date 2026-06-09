# CTxtEdit::Open(tagVARIANT *,long,long)

- ea: `0x180083b80`
- end: `0x180083e92`
- name: `?Open@CTxtEdit@@UEAAJPEAUtagVARIANT@@JJ@Z`
- size: `786`
- prototype: `int(CTxtEdit *__hidden this, struct tagVARIANT *, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180032c68`
- `0x180041c60`
- `0x180045f54`
- `0x180083b80`
- `0x18008d778`
- `0x18008f890`
- `0x180090c0c`
- `0x180090cf8`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180083d98`
- `KERNEL32!SetFilePointer` at `0x180083d98`
- `KERNEL32!GetFileType` at `0x180083cca`
- `KERNEL32!GetFileType` at `0x180083cca`
- `KERNEL32!IsValidCodePage` at `0x180083be8`
- `KERNEL32!IsValidCodePage` at `0x180083be8`
- `KERNEL32!GetLastError` at `0x180083e34`
- `KERNEL32!GetLastError` at `0x180083e34`
- `KERNEL32!CloseHandle` at `0x180083e02`
- `KERNEL32!CloseHandle` at `0x180083e46`
- `KERNEL32!CloseHandle` at `0x180083e02`
- `KERNEL32!CloseHandle` at `0x180083e46`
- `USER32!SetCursor` at `0x180083dad`
- `USER32!SetCursor` at `0x180083dee`
- `USER32!SetCursor` at `0x180083dad`
- `USER32!SetCursor` at `0x180083dee`

## pseudocode

```c
__int64 __fastcall CTxtEdit::Open(CTxtEdit *this, struct tagVARIANT *a2, int a3, UINT a4)
{
  unsigned int v8; // r12d
  int v10; // esi
  struct CDocInfo *DocInfo; // rax
  struct CDocInfo *v12; // r15
  DWORD v13; // edx
  DWORD v14; // ebx
  struct _SECURITY_ATTRIBUTES *v15; // r9
  HANDLE File; // rax
  unsigned __int16 *v17; // rax
  HANDLE v18; // rax
  LONG v19; // edx
  int v20; // edi
  HCURSOR Cursor; // rax
  HCURSOR v22; // rax
  int v23; // edx
  HCURSOR v24; // rbx
  signed int LastError; // ebx
  int v26; // [rsp+40h] [rbp-39h] BYREF
  DWORD dwShareMode; // [rsp+44h] [rbp-35h]
  HANDLE hFile; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-29h]
  unsigned int (__fastcall *v30)(unsigned __int64, unsigned __int8 *, int, int *); // [rsp+54h] [rbp-25h]
  DWORD dwDesiredAccess; // [rsp+60h] [rbp-19h]
  __int64 v32; // [rsp+68h] [rbp-11h] BYREF
  char v33[24]; // [rsp+70h] [rbp-9h] BYREF

  v26 = 0;
  hFile = 0;
  v29 = 0;
  v30 = MyRead;
  v32 = 0;
  if ( !a2 || a4 && a4 != 1200 && !IsValidCodePage(a4) )
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
  *((_WORD *)DocInfo + 8) = a3 & 0xFF0F;
  dwDesiredAccess = ~(a3 << 22) & 0x40000000 | 0x80000000;
  v13 = (a3 & 0x200) == 0;
  if ( (a3 & 0x400) == 0 )
    v13 = ((a3 & 0x200) == 0) | 2;
  v14 = (a3 >> 4) & 0xF;
  dwShareMode = v13;
  if ( !v14 )
    v14 = 4;
  if ( a2->vt != 8 || !CW32System::SysStringLen(a2->bstrVal) )
    return 2147942487LL;
  File = CW32System::CreateFile(a2->bstrVal, dwDesiredAccess, dwShareMode, v15, v14);
  hFile = File;
  if ( File != (HANDLE)-1LL && GetFileType(File) == 1 )
  {
    if ( v10 )
      goto LABEL_21;
    v17 = CW32System::SysAllocString(a2->bstrVal);
    *(_QWORD *)v12 = v17;
    if ( v17 )
    {
      v18 = hFile;
      *((_WORD *)v12 + 8) |= 0x50u;
      *((_QWORD *)v12 + 1) = v18;
LABEL_21:
      v30((unsigned __int64)hFile, (unsigned __int8 *)v33, 10, &v26);
      if ( v8 <= 1 && (unsigned int)IsRTF(v33) )
      {
        v19 = 0;
        v20 = 2;
      }
      else if ( v26 > 1 && *(_WORD *)v33 == 0xFEFF )
      {
        v20 = 17;
        v19 = 2;
      }
      else if ( v26 > 2 && (unsigned int)CW32System::IsUTF8BOM((unsigned __int8 *)v33) )
      {
        v20 = -35061727;
        v19 = 3;
      }
      else
      {
        v19 = 0;
        if ( a4 == 1200 )
        {
          v20 = 17;
        }
        else if ( a4 )
        {
          v20 = (a4 << 16) | 0x21;
        }
        else
        {
          v20 = 1;
        }
      }
      SetFilePointer(hFile, v19, 0, 0);
      Cursor = CW32System::LoadCursor(0, (const unsigned __int16 *)0x7F02);
      v22 = SetCursor(Cursor);
      v23 = v20 | 0x8000;
      v24 = v22;
      if ( !v10 )
        v23 = v20;
      (*(void (__fastcall **)(char *, __int64, __int64, HANDLE *, __int64 *))(*((_QWORD *)this - 2) + 24LL))(
        (char *)this - 16,
        1097,
        v23 | 0x1000LL,
        &hFile,
        &v32);
      SetCursor(v24);
      if ( dwShareMode == 3 || v10 )
      {
        CloseHandle(hFile);
        if ( !v10 )
          *((_QWORD *)v12 + 1) = 0;
      }
      *((_DWORD *)this + 41) &= ~0x4000000u;
      *((_DWORD *)this + 41) |= v10 == 0 ? 0x4000000 : 0;
      return v29;
    }
    return 2147942414LL;
  }
  LastError = GetLastError();
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
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
0x180083b80  push    rbp
0x180083b82  push    rbx
0x180083b83  push    rsi
0x180083b84  push    rdi
0x180083b85  push    r12
0x180083b87  push    r13
0x180083b89  push    r14
0x180083b8b  push    r15
0x180083b8d  lea     rbp, [rsp-1Fh]
0x180083b92  sub     rsp, 98h
0x180083b99  mov     rax, cs:__security_cookie
0x180083ba0  xor     rax, rsp
0x180083ba3  mov     [rbp+57h+var_48], rax
0x180083ba7  xor     esi, esi
0x180083ba9  lea     rax, ?MyRead@@YAK_KPEAEJPEAJ@Z; MyRead(unsigned __int64,uchar *,long,long *)
0x180083bb0  mov     [rbp+57h+var_90], esi
0x180083bb3  mov     edi, r9d
0x180083bb6  mov     [rbp+57h+hFile], rsi
0x180083bba  mov     ebx, r8d
0x180083bbd  mov     [rbp+57h+var_80], esi
0x180083bc0  mov     r13, rdx
0x180083bc3  mov     [rbp+57h+var_7C], rax
0x180083bc7  mov     r14, rcx
0x180083bca  mov     [rbp+57h+var_68], rsi
0x180083bce  test    rdx, rdx
0x180083bd1  jz      loc_180083E6D
0x180083bd7  test    r9d, r9d
0x180083bda  jz      short loc_180083BF6
0x180083bdc  cmp     r9d, 4B0h
0x180083be3  jz      short loc_180083BF6
0x180083be5  mov     ecx, r9d; CodePage
0x180083be8  call    cs:__imp_IsValidCodePage
0x180083bee  test    eax, eax
0x180083bf0  jz      loc_180083E6D
0x180083bf6  mov     r12d, ebx
0x180083bf9  and     r12d, 0Fh
0x180083bfd  cmp     r12d, 3
0x180083c01  jb      short loc_180083C0D
0x180083c03  mov     eax, 80004001h
0x180083c08  jmp     loc_180083E72
0x180083c0d  mov     esi, ebx
0x180083c0f  and     esi, 1000h
0x180083c15  jnz     short loc_180083C26
0x180083c17  mov     rax, [r14]
0x180083c1a  mov     rcx, r14
0x180083c1d  mov     rax, [rax+78h]
0x180083c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c26  lea     rcx, [r14-10h]; this
0x180083c2a  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x180083c2f  mov     r15, rax
0x180083c32  test    rax, rax
0x180083c35  jz      loc_180083E66
0x180083c3b  movzx   ecx, bx
0x180083c3e  mov     eax, 0FF0Fh
0x180083c43  and     cx, ax
0x180083c46  mov     eax, ebx
0x180083c48  shl     eax, 16h
0x180083c4b  mov     [r15+10h], cx
0x180083c50  not     eax
0x180083c52  and     eax, 0C0000000h
0x180083c57  mov     ecx, ebx
0x180083c59  shr     ecx, 9
0x180083c5c  bts     eax, 1Fh
0x180083c60  not     ecx
0x180083c62  mov     [rbp+57h+dwDesiredAccess], eax
0x180083c65  and     ecx, 1
0x180083c68  mov     eax, 4
0x180083c6d  or      ecx, 2
0x180083c70  mov     edx, ecx
0x180083c72  and     edx, 0FFFFFFFDh
0x180083c75  bt      ebx, 0Ah
0x180083c79  cmovnb  edx, ecx
0x180083c7c  sar     ebx, 4
0x180083c7f  and     ebx, 0Fh
0x180083c82  mov     [rbp+57h+dwShareMode], edx
0x180083c85  cmovz   ebx, eax
0x180083c88  cmp     word ptr [r13+0], 8
0x180083c8e  jnz     loc_180083E6D
0x180083c94  mov     rcx, [r13+8]; unsigned __int16 *
0x180083c98  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x180083c9d  test    eax, eax
0x180083c9f  jz      loc_180083E6D
0x180083ca5  mov     r8d, [rbp+57h+dwShareMode]; dwShareMode
0x180083ca9  mov     edx, [rbp+57h+dwDesiredAccess]; dwDesiredAccess
0x180083cac  mov     rcx, [r13+8]; unsigned __int16 *
0x180083cb0  mov     [rsp+0D0h+var_B0], ebx; unsigned int
0x180083cb4  call    ?CreateFile@CW32System@@SAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CW32System::CreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180083cb9  mov     [rbp+57h+hFile], rax
0x180083cbd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180083cc1  jz      loc_180083E34
0x180083cc7  mov     rcx, rax; hFile
0x180083cca  call    cs:__imp_GetFileType
0x180083cd0  mov     ebx, 1
0x180083cd5  cmp     eax, ebx
0x180083cd7  jnz     loc_180083E34
0x180083cdd  test    esi, esi
0x180083cdf  jnz     short loc_180083D04
0x180083ce1  mov     rcx, [r13+8]; unsigned __int16 *
0x180083ce5  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x180083cea  mov     [r15], rax
0x180083ced  test    rax, rax
0x180083cf0  jz      loc_180083E66
0x180083cf6  mov     rax, [rbp+57h+hFile]
0x180083cfa  or      word ptr [r15+10h], 50h
0x180083d00  mov     [r15+8], rax
0x180083d04  mov     rcx, [rbp+57h+hFile]
0x180083d08  lea     r9, [rbp+57h+var_90]
0x180083d0c  mov     rax, [rbp+57h+var_7C]
0x180083d10  lea     rdx, [rbp+57h+var_60]
0x180083d14  mov     r8d, 0Ah
0x180083d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083d1f  cmp     r12d, ebx
0x180083d22  ja      short loc_180083D38
0x180083d24  lea     rcx, [rbp+57h+var_60]; char *
0x180083d28  call    ?IsRTF@@YAHPEAD@Z; IsRTF(char *)
0x180083d2d  test    eax, eax
0x180083d2f  jz      short loc_180083D38
0x180083d31  xor     edx, edx
0x180083d33  lea     edi, [rdx+2]
0x180083d36  jmp     short loc_180083D8E
0x180083d38  cmp     [rbp+57h+var_90], ebx
0x180083d3b  jle     short loc_180083D52
0x180083d3d  mov     eax, 0FEFFh
0x180083d42  cmp     word ptr [rbp+57h+var_60], ax
0x180083d46  jnz     short loc_180083D52
0x180083d48  mov     edi, 11h
0x180083d4d  lea     edx, [rdi-0Fh]
0x180083d50  jmp     short loc_180083D8E
0x180083d52  cmp     [rbp+57h+var_90], 2
0x180083d56  jle     short loc_180083D71
0x180083d58  lea     rcx, [rbp+57h+var_60]; unsigned __int8 *
0x180083d5c  call    ?IsUTF8BOM@CW32System@@SAHPEAE@Z; CW32System::IsUTF8BOM(uchar *)
0x180083d61  test    eax, eax
0x180083d63  jz      short loc_180083D71
0x180083d65  mov     edi, 0FDE90021h
0x180083d6a  mov     edx, 3
0x180083d6f  jmp     short loc_180083D8E
0x180083d71  xor     edx, edx; lDistanceToMove
0x180083d73  cmp     edi, 4B0h
0x180083d79  jnz     short loc_180083D80
0x180083d7b  lea     edi, [rdx+11h]
0x180083d7e  jmp     short loc_180083D8E
0x180083d80  test    edi, edi
0x180083d82  jz      short loc_180083D8C
0x180083d84  shl     edi, 10h
0x180083d87  or      edi, 21h
0x180083d8a  jmp     short loc_180083D8E
0x180083d8c  mov     edi, ebx
0x180083d8e  mov     rcx, [rbp+57h+hFile]; hFile
0x180083d92  xor     r9d, r9d; dwMoveMethod
0x180083d95  xor     r8d, r8d; lpDistanceToMoveHigh
0x180083d98  call    cs:__imp_SetFilePointer
0x180083d9e  mov     edx, 7F02h; unsigned __int16 *
0x180083da3  xor     ecx, ecx; HINSTANCE
0x180083da5  call    ?LoadCursor@CW32System@@SAPEAUHICON__@@PEAUHINSTANCE__@@PEBG@Z; CW32System::LoadCursor(HINSTANCE__ *,ushort const *)
0x180083daa  mov     rcx, rax; hCursor
0x180083dad  call    cs:__imp_SetCursor
0x180083db3  mov     edx, edi
0x180083db5  lea     rcx, [r14-10h]
0x180083db9  bts     edx, 0Fh
0x180083dbd  lea     r9, [rbp+57h+hFile]
0x180083dc1  mov     rbx, rax
0x180083dc4  test    esi, esi
0x180083dc6  mov     rax, [rcx]
0x180083dc9  cmovz   edx, edi
0x180083dcc  movsxd  r8, edx
0x180083dcf  lea     rdx, [rbp+57h+var_68]
0x180083dd3  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x180083dd8  bts     r8, 0Ch
0x180083ddd  mov     rax, [rax+18h]
0x180083de1  mov     edx, 449h
0x180083de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083deb  mov     rcx, rbx; hCursor
0x180083dee  call    cs:__imp_SetCursor
0x180083df4  cmp     [rbp+57h+dwShareMode], 3
0x180083df8  jz      short loc_180083DFE
0x180083dfa  test    esi, esi
0x180083dfc  jz      short loc_180083E14
0x180083dfe  mov     rcx, [rbp+57h+hFile]; hObject
0x180083e02  call    cs:__imp_CloseHandle
0x180083e08  test    esi, esi
0x180083e0a  jnz     short loc_180083E14
0x180083e0c  mov     qword ptr [r15+8], 0
0x180083e14  btr     dword ptr [r14+0A4h], 1Ah
0x180083e1d  neg     esi
0x180083e1f  sbb     eax, eax
0x180083e21  not     eax
0x180083e23  and     eax, 4000000h
0x180083e28  or      [r14+0A4h], eax
0x180083e2f  mov     eax, [rbp+57h+var_80]
0x180083e32  jmp     short loc_180083E72
0x180083e34  call    cs:__imp_GetLastError
0x180083e3a  mov     rcx, [rbp+57h+hFile]; hObject
0x180083e3e  mov     ebx, eax
0x180083e40  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180083e44  jz      short loc_180083E4C
0x180083e46  call    cs:__imp_CloseHandle
0x180083e4c  test    ebx, ebx
0x180083e4e  jnz     short loc_180083E57
0x180083e50  mov     ebx, 80070057h
0x180083e55  jmp     short loc_180083E62
0x180083e57  jle     short loc_180083E62
0x180083e59  movzx   ebx, bx
0x180083e5c  or      ebx, 80070000h
0x180083e62  mov     eax, ebx
0x180083e64  jmp     short loc_180083E72
0x180083e66  mov     eax, 8007000Eh
0x180083e6b  jmp     short loc_180083E72
0x180083e6d  mov     eax, 80070057h
0x180083e72  mov     rcx, [rbp+57h+var_48]
0x180083e76  xor     rcx, rsp; StackCookie
0x180083e79  call    __security_check_cookie
0x180083e7e  add     rsp, 98h
0x180083e85  pop     r15
0x180083e87  pop     r14
0x180083e89  pop     r13
0x180083e8b  pop     r12
0x180083e8d  pop     rdi
0x180083e8e  pop     rsi
0x180083e8f  pop     rbx
0x180083e90  pop     rbp
0x180083e91  retn
```
