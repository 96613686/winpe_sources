# CTxtEdit::Open(tagVARIANT *,long,long)

- ea: `0x180086110`
- end: `0x180086453`
- name: `?Open@CTxtEdit@@UEAAJPEAUtagVARIANT@@JJ@Z`
- size: `835`
- prototype: `int(CTxtEdit *__hidden this, struct tagVARIANT *, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002d8e4`
- `0x180042fd0`
- `0x180046fd8`
- `0x180086110`
- `0x18008ff5c`
- `0x1800921c0`
- `0x18009366c`
- `0x180093758`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180086334`
- `KERNEL32!SetFilePointer` at `0x180086334`
- `KERNEL32!GetFileType` at `0x180086260`
- `KERNEL32!GetFileType` at `0x180086260`
- `KERNEL32!IsValidCodePage` at `0x180086178`
- `KERNEL32!IsValidCodePage` at `0x180086178`
- `KERNEL32!GetLastError` at `0x1800863e8`
- `KERNEL32!GetLastError` at `0x1800863e8`
- `KERNEL32!CloseHandle` at `0x1800863b0`
- `KERNEL32!CloseHandle` at `0x180086400`
- `KERNEL32!CloseHandle` at `0x1800863b0`
- `KERNEL32!CloseHandle` at `0x180086400`
- `USER32!SetCursor` at `0x18008634f`
- `USER32!SetCursor` at `0x180086396`
- `USER32!SetCursor` at `0x18008634f`
- `USER32!SetCursor` at `0x180086396`

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
0x180086110  push    rbp
0x180086112  push    rbx
0x180086113  push    rsi
0x180086114  push    rdi
0x180086115  push    r12
0x180086117  push    r13
0x180086119  push    r14
0x18008611b  push    r15
0x18008611d  lea     rbp, [rsp-1Fh]
0x180086122  sub     rsp, 98h
0x180086129  mov     rax, cs:__security_cookie
0x180086130  xor     rax, rsp
0x180086133  mov     [rbp+57h+var_48], rax
0x180086137  xor     esi, esi
0x180086139  lea     rax, ?MyRead@@YAK_KPEAEJPEAJ@Z; MyRead(unsigned __int64,uchar *,long,long *)
0x180086140  mov     [rbp+57h+var_90], esi
0x180086143  mov     edi, r9d
0x180086146  mov     [rbp+57h+hFile], rsi
0x18008614a  mov     ebx, r8d
0x18008614d  mov     [rbp+57h+var_80], esi
0x180086150  mov     r13, rdx
0x180086153  mov     [rbp+57h+var_7C], rax
0x180086157  mov     r14, rcx
0x18008615a  mov     [rbp+57h+var_68], rsi
0x18008615e  test    rdx, rdx
0x180086161  jz      loc_18008642D
0x180086167  test    r9d, r9d
0x18008616a  jz      short loc_18008618C
0x18008616c  cmp     r9d, 4B0h
0x180086173  jz      short loc_18008618C
0x180086175  mov     ecx, r9d; CodePage
0x180086178  call    cs:__imp_IsValidCodePage
0x18008617f  nop     dword ptr [rax+rax+00h]
0x180086184  test    eax, eax
0x180086186  jz      loc_18008642D
0x18008618c  mov     r12d, ebx
0x18008618f  and     r12d, 0Fh
0x180086193  cmp     r12d, 3
0x180086197  jb      short loc_1800861A3
0x180086199  mov     eax, 80004001h
0x18008619e  jmp     loc_180086432
0x1800861a3  mov     esi, ebx
0x1800861a5  and     esi, 1000h
0x1800861ab  jnz     short loc_1800861BC
0x1800861ad  mov     rax, [r14]
0x1800861b0  mov     rcx, r14
0x1800861b3  mov     rax, [rax+78h]
0x1800861b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800861bc  lea     rcx, [r14-10h]; this
0x1800861c0  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x1800861c5  mov     r15, rax
0x1800861c8  test    rax, rax
0x1800861cb  jz      loc_180086426
0x1800861d1  movzx   ecx, bx
0x1800861d4  mov     eax, 0FF0Fh
0x1800861d9  and     cx, ax
0x1800861dc  mov     eax, ebx
0x1800861de  shl     eax, 16h
0x1800861e1  mov     [r15+10h], cx
0x1800861e6  not     eax
0x1800861e8  and     eax, 0C0000000h
0x1800861ed  mov     ecx, ebx
0x1800861ef  shr     ecx, 9
0x1800861f2  bts     eax, 1Fh
0x1800861f6  not     ecx
0x1800861f8  mov     [rbp+57h+dwDesiredAccess], eax
0x1800861fb  and     ecx, 1
0x1800861fe  mov     eax, 4
0x180086203  or      ecx, 2
0x180086206  mov     edx, ecx
0x180086208  and     edx, 0FFFFFFFDh
0x18008620b  bt      ebx, 0Ah
0x18008620f  cmovnb  edx, ecx
0x180086212  sar     ebx, 4
0x180086215  and     ebx, 0Fh
0x180086218  mov     [rbp+57h+dwShareMode], edx
0x18008621b  cmovz   ebx, eax
0x18008621e  cmp     word ptr [r13+0], 8
0x180086224  jnz     loc_18008642D
0x18008622a  mov     rcx, [r13+8]; unsigned __int16 *
0x18008622e  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x180086233  test    eax, eax
0x180086235  jz      loc_18008642D
0x18008623b  mov     r8d, [rbp+57h+dwShareMode]; dwShareMode
0x18008623f  mov     edx, [rbp+57h+dwDesiredAccess]; dwDesiredAccess
0x180086242  mov     rcx, [r13+8]; unsigned __int16 *
0x180086246  mov     [rsp+0D0h+var_B0], ebx; unsigned int
0x18008624a  call    ?CreateFile@CW32System@@SAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CW32System::CreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18008624f  mov     [rbp+57h+hFile], rax
0x180086253  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180086257  jz      loc_1800863E8
0x18008625d  mov     rcx, rax; hFile
0x180086260  call    cs:__imp_GetFileType
0x180086267  nop     dword ptr [rax+rax+00h]
0x18008626c  mov     ebx, 1
0x180086271  cmp     eax, ebx
0x180086273  jnz     loc_1800863E8
0x180086279  test    esi, esi
0x18008627b  jnz     short loc_1800862A0
0x18008627d  mov     rcx, [r13+8]; unsigned __int16 *
0x180086281  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x180086286  mov     [r15], rax
0x180086289  test    rax, rax
0x18008628c  jz      loc_180086426
0x180086292  mov     rax, [rbp+57h+hFile]
0x180086296  or      word ptr [r15+10h], 50h
0x18008629c  mov     [r15+8], rax
0x1800862a0  mov     rcx, [rbp+57h+hFile]
0x1800862a4  lea     r9, [rbp+57h+var_90]
0x1800862a8  mov     rax, [rbp+57h+var_7C]
0x1800862ac  lea     rdx, [rbp+57h+var_60]
0x1800862b0  mov     r8d, 0Ah
0x1800862b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800862bb  cmp     r12d, ebx
0x1800862be  ja      short loc_1800862D4
0x1800862c0  lea     rcx, [rbp+57h+var_60]; char *
0x1800862c4  call    ?IsRTF@@YAHPEAD@Z; IsRTF(char *)
0x1800862c9  test    eax, eax
0x1800862cb  jz      short loc_1800862D4
0x1800862cd  xor     edx, edx
0x1800862cf  lea     edi, [rdx+2]
0x1800862d2  jmp     short loc_18008632A
0x1800862d4  cmp     [rbp+57h+var_90], ebx
0x1800862d7  jle     short loc_1800862EE
0x1800862d9  mov     eax, 0FEFFh
0x1800862de  cmp     word ptr [rbp+57h+var_60], ax
0x1800862e2  jnz     short loc_1800862EE
0x1800862e4  mov     edi, 11h
0x1800862e9  lea     edx, [rdi-0Fh]
0x1800862ec  jmp     short loc_18008632A
0x1800862ee  cmp     [rbp+57h+var_90], 2
0x1800862f2  jle     short loc_18008630D
0x1800862f4  lea     rcx, [rbp+57h+var_60]; unsigned __int8 *
0x1800862f8  call    ?IsUTF8BOM@CW32System@@SAHPEAE@Z; CW32System::IsUTF8BOM(uchar *)
0x1800862fd  test    eax, eax
0x1800862ff  jz      short loc_18008630D
0x180086301  mov     edi, 0FDE90021h
0x180086306  mov     edx, 3
0x18008630b  jmp     short loc_18008632A
0x18008630d  xor     edx, edx; lDistanceToMove
0x18008630f  cmp     edi, 4B0h
0x180086315  jnz     short loc_18008631C
0x180086317  lea     edi, [rdx+11h]
0x18008631a  jmp     short loc_18008632A
0x18008631c  test    edi, edi
0x18008631e  jz      short loc_180086328
0x180086320  shl     edi, 10h
0x180086323  or      edi, 21h
0x180086326  jmp     short loc_18008632A
0x180086328  mov     edi, ebx
0x18008632a  mov     rcx, [rbp+57h+hFile]; hFile
0x18008632e  xor     r9d, r9d; dwMoveMethod
0x180086331  xor     r8d, r8d; lpDistanceToMoveHigh
0x180086334  call    cs:__imp_SetFilePointer
0x18008633b  nop     dword ptr [rax+rax+00h]
0x180086340  mov     edx, 7F02h; unsigned __int16 *
0x180086345  xor     ecx, ecx; HINSTANCE
0x180086347  call    ?LoadCursor@CW32System@@SAPEAUHICON__@@PEAUHINSTANCE__@@PEBG@Z; CW32System::LoadCursor(HINSTANCE__ *,ushort const *)
0x18008634c  mov     rcx, rax; hCursor
0x18008634f  call    cs:__imp_SetCursor
0x180086356  nop     dword ptr [rax+rax+00h]
0x18008635b  mov     edx, edi
0x18008635d  lea     rcx, [r14-10h]
0x180086361  bts     edx, 0Fh
0x180086365  lea     r9, [rbp+57h+hFile]
0x180086369  mov     rbx, rax
0x18008636c  test    esi, esi
0x18008636e  mov     rax, [rcx]
0x180086371  cmovz   edx, edi
0x180086374  movsxd  r8, edx
0x180086377  lea     rdx, [rbp+57h+var_68]
0x18008637b  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x180086380  bts     r8, 0Ch
0x180086385  mov     rax, [rax+18h]
0x180086389  mov     edx, 449h
0x18008638e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086393  mov     rcx, rbx; hCursor
0x180086396  call    cs:__imp_SetCursor
0x18008639d  nop     dword ptr [rax+rax+00h]
0x1800863a2  cmp     [rbp+57h+dwShareMode], 3
0x1800863a6  jz      short loc_1800863AC
0x1800863a8  test    esi, esi
0x1800863aa  jz      short loc_1800863C8
0x1800863ac  mov     rcx, [rbp+57h+hFile]; hObject
0x1800863b0  call    cs:__imp_CloseHandle
0x1800863b7  nop     dword ptr [rax+rax+00h]
0x1800863bc  test    esi, esi
0x1800863be  jnz     short loc_1800863C8
0x1800863c0  mov     qword ptr [r15+8], 0
0x1800863c8  btr     dword ptr [r14+0A4h], 1Ah
0x1800863d1  neg     esi
0x1800863d3  sbb     eax, eax
0x1800863d5  not     eax
0x1800863d7  and     eax, 4000000h
0x1800863dc  or      [r14+0A4h], eax
0x1800863e3  mov     eax, [rbp+57h+var_80]
0x1800863e6  jmp     short loc_180086432
0x1800863e8  call    cs:__imp_GetLastError
0x1800863ef  nop     dword ptr [rax+rax+00h]
0x1800863f4  mov     rcx, [rbp+57h+hFile]; hObject
0x1800863f8  mov     ebx, eax
0x1800863fa  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800863fe  jz      short loc_18008640C
0x180086400  call    cs:__imp_CloseHandle
0x180086407  nop     dword ptr [rax+rax+00h]
0x18008640c  test    ebx, ebx
0x18008640e  jnz     short loc_180086417
0x180086410  mov     ebx, 80070057h
0x180086415  jmp     short loc_180086422
0x180086417  jle     short loc_180086422
0x180086419  movzx   ebx, bx
0x18008641c  or      ebx, 80070000h
0x180086422  mov     eax, ebx
0x180086424  jmp     short loc_180086432
0x180086426  mov     eax, 8007000Eh
0x18008642b  jmp     short loc_180086432
0x18008642d  mov     eax, 80070057h
0x180086432  mov     rcx, [rbp+57h+var_48]
0x180086436  xor     rcx, rsp; StackCookie
0x180086439  call    __security_check_cookie
0x18008643e  add     rsp, 98h
0x180086445  pop     r15
0x180086447  pop     r14
0x180086449  pop     r13
0x18008644b  pop     r12
0x18008644d  pop     rdi
0x18008644e  pop     rsi
0x18008644f  pop     rbx
0x180086450  pop     rbp
0x180086451  retn
```
