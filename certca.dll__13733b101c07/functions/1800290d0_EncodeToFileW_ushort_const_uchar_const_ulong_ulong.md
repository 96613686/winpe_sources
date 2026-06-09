# EncodeToFileW(ushort const *,uchar const *,ulong,ulong)

- ea: `0x1800290d0`
- end: `0x18002935c`
- name: `?EncodeToFileW@@YAJPEBGPEBEKK@Z`
- size: `652`
- prototype: `__int64 __fastcall(const unsigned __int16 *, BYTE *pbBinary, DWORD cbBinary, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180008400`
- `0x180008610`
- `0x1800123b0`
- `0x180012450`
- `0x180015c20`
- `0x1800290d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029335`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029343`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029335`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029343`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800292b8`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800292b8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800292ec`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800292ec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002924a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002928a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002924a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002928a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029327`

## pseudocode

```c
__int64 __fastcall EncodeToFileW(const unsigned __int16 *a1, BYTE *pbBinary, DWORD cbBinary, int a4)
{
  unsigned __int64 v4; // rbx
  DWORD v5; // r8d
  int v6; // r12d
  BYTE *v7; // r14
  HLOCAL v9; // rbp
  BYTE *v10; // rdi
  unsigned int v11; // ebx
  int v12; // eax
  BYTE *i; // rdx
  int v14; // eax
  HANDLE FileW; // rsi
  int v16; // eax
  unsigned int v17; // ecx
  int v18; // edx
  HLOCAL v20; // [rsp+40h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-50h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp+20h] BYREF

  LODWORD(v4) = cbBinary;
  NumberOfBytesWritten = 0;
  hMem = 0;
  v5 = a4 & 0xFFFFFCFF;
  v20 = 0;
  v6 = a4 & 0x100;
  v7 = pbBinary;
  v9 = 0;
  v10 = 0;
  if ( (_BYTE)a4 == 2 )
  {
    if ( v5 != 2 )
    {
      v11 = -2147024809;
      CSPrintErrorLineFile(0xC70327u, -2147024809);
      return v11;
    }
    goto LABEL_22;
  }
  if ( (a4 & 0x200) == 0 )
  {
    v14 = myCryptBinaryToStringA(pbBinary, v4, v5, (char **)&hMem);
    v11 = v14;
    if ( v14 )
    {
      CSPrintErrorLineFile(0xEA0327u, v14);
      v9 = hMem;
      goto LABEL_37;
    }
    v9 = hMem;
    v4 = -1;
    do
      ++v4;
    while ( *((_BYTE *)hMem + v4) );
    if ( v4 > 0x61A8000 )
    {
      v11 = -2147024362;
      CSPrintErrorLineFile(0xF00327u, -2147024362);
      goto LABEL_37;
    }
    v7 = (BYTE *)hMem;
LABEL_22:
    FileW = CreateFileW(a1, 0x40000000u, 0, 0, 1u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v16 = myHLastError();
      if ( !v6 || v16 != -2147024816 || (FileW = CreateFileW(a1, 0x40000000u, 0, 0, 2u, 0, 0), FileW == (HANDLE)-1LL) )
      {
        v11 = myHLastError();
        CSPrintErrorLineFileData2(a1, 0x1120327u, v11, 0);
        goto LABEL_37;
      }
    }
    if ( GetFileType(FileW) == 1 )
    {
      if ( !WriteFile(FileW, v7, v4, &NumberOfBytesWritten, 0) )
      {
        v11 = myHLastError();
        v18 = v11;
        v17 = 18744103;
        goto LABEL_30;
      }
      if ( NumberOfBytesWritten == (_DWORD)v4 )
      {
        v11 = 0;
        goto LABEL_36;
      }
      v11 = -2147024858;
      v17 = 19399463;
    }
    else
    {
      v11 = -2147024894;
      v17 = 18350887;
    }
    v18 = v11;
LABEL_30:
    CSPrintErrorLineFile(v17, v18);
LABEL_36:
    CloseHandle(FileW);
LABEL_37:
    if ( v9 )
      LocalFree(v9);
    goto LABEL_39;
  }
  v12 = myCryptBinaryToString(pbBinary, v4, v5, (unsigned __int16 **)&v20);
  v11 = v12;
  if ( v12 )
  {
    CSPrintErrorLineFile(0xCF0327u, v12);
    v10 = (BYTE *)v20;
  }
  else
  {
    v10 = (BYTE *)v20;
    v4 = -1;
    do
      ++v4;
    while ( *((_WORD *)v20 + v4) );
    if ( v4 <= 0x61A8000 )
    {
      for ( i = (BYTE *)v20 + 2 * (unsigned int)(v4 - 1); i >= v10; i -= 2 )
        *((_WORD *)i + 1) = *(_WORD *)i;
      *((_WORD *)i + 1) = -257;
      LODWORD(v4) = 2 * v4 + 2;
      v7 = v10;
      goto LABEL_22;
    }
    v11 = -2147024362;
    CSPrintErrorLineFile(0xD80327u, -2147024362);
  }
LABEL_39:
  if ( v10 )
    LocalFree(v10);
  return v11;
}

```

## disassembly

```asm
0x1800290d0  mov     rax, rsp
0x1800290d3  push    rbx
0x1800290d4  push    rbp
0x1800290d5  push    rsi
0x1800290d6  push    rdi
0x1800290d7  push    r12
0x1800290d9  push    r13
0x1800290db  push    r14
0x1800290dd  push    r15
0x1800290df  sub     rsp, 58h
0x1800290e3  xor     r13d, r13d
0x1800290e6  mov     ebx, r8d
0x1800290e9  mov     r8d, r9d
0x1800290ec  mov     [rax+20h], r13d
0x1800290f0  mov     r12d, r9d
0x1800290f3  mov     [rax-50h], r13
0x1800290f7  and     r8d, 0FFFFFCFFh; dwFlags
0x1800290fe  mov     [rax-58h], r13
0x180029102  and     r12d, 100h
0x180029109  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002910d  mov     r14, rdx
0x180029110  mov     r15, rcx
0x180029113  mov     ebp, r13d
0x180029116  mov     edi, r13d
0x180029119  cmp     r8b, 2
0x18002911d  jnz     short loc_18002913F
0x18002911f  cmp     r8d, 2
0x180029123  jz      loc_18002922A
0x180029129  mov     ebx, 80070057h
0x18002912e  mov     ecx, 0C70327h; unsigned int
0x180029133  mov     edx, ebx; int
0x180029135  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002913a  jmp     loc_180029349
0x18002913f  mov     edx, ebx; cbBinary
0x180029141  mov     rcx, r14; pbBinary
0x180029144  bt      r9d, 9
0x180029149  jnb     loc_1800291D1
0x18002914f  lea     r9, [rsp+98h+var_58]; unsigned __int16 **
0x180029154  call    ?myCryptBinaryToString@@YAJPEBEKKPEAPEAG@Z; myCryptBinaryToString(uchar const *,ulong,ulong,ushort * *)
0x180029159  mov     ebx, eax
0x18002915b  test    eax, eax
0x18002915d  jz      short loc_180029175
0x18002915f  mov     edx, eax; int
0x180029161  mov     ecx, 0CF0327h; unsigned int
0x180029166  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002916b  mov     rdi, [rsp+98h+var_58]
0x180029170  jmp     loc_18002933B
0x180029175  mov     rdi, [rsp+98h+var_58]
0x18002917a  mov     rbx, rsi
0x18002917d  inc     rbx
0x180029180  cmp     [rdi+rbx*2], r13w
0x180029185  jnz     short loc_18002917D
0x180029187  cmp     rbx, 61A8000h
0x18002918e  jbe     short loc_1800291A6
0x180029190  mov     edx, 80070216h; int
0x180029195  mov     ecx, 0D80327h; unsigned int
0x18002919a  mov     ebx, edx
0x18002919c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800291a1  jmp     loc_18002933B
0x1800291a6  lea     eax, [rbx-1]
0x1800291a9  lea     rdx, [rdi+rax*2]
0x1800291ad  jmp     short loc_1800291BA
0x1800291af  movzx   eax, word ptr [rdx]
0x1800291b2  mov     [rdx+2], ax
0x1800291b6  sub     rdx, 2
0x1800291ba  cmp     rdx, rdi
0x1800291bd  jnb     short loc_1800291AF
0x1800291bf  mov     word ptr [rdx+2], 0FEFFh
0x1800291c5  lea     ebx, ds:2[rbx*2]
0x1800291cc  mov     r14, rdi
0x1800291cf  jmp     short loc_18002922A
0x1800291d1  lea     r9, [rsp+98h+hMem]; char **
0x1800291d6  call    ?myCryptBinaryToStringA@@YAJPEBEKKPEAPEAD@Z; myCryptBinaryToStringA(uchar const *,ulong,ulong,char * *)
0x1800291db  mov     ebx, eax
0x1800291dd  test    eax, eax
0x1800291df  jz      short loc_1800291F7
0x1800291e1  mov     edx, eax; int
0x1800291e3  mov     ecx, 0EA0327h; unsigned int
0x1800291e8  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800291ed  mov     rbp, [rsp+98h+hMem]
0x1800291f2  jmp     loc_18002932D
0x1800291f7  mov     rbp, [rsp+98h+hMem]
0x1800291fc  mov     rbx, rsi
0x1800291ff  inc     rbx
0x180029202  cmp     [rbx+rbp], r13b
0x180029206  jnz     short loc_1800291FF
0x180029208  cmp     rbx, 61A8000h
0x18002920f  jbe     short loc_180029227
0x180029211  mov     edx, 80070216h; int
0x180029216  mov     ecx, 0F00327h; unsigned int
0x18002921b  mov     ebx, edx
0x18002921d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180029222  jmp     loc_18002932D
0x180029227  mov     r14, rbp
0x18002922a  mov     [rsp+98h+hTemplateFile], r13; hTemplateFile
0x18002922f  xor     r9d, r9d; lpSecurityAttributes
0x180029232  mov     [rsp+98h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180029237  xor     r8d, r8d; dwShareMode
0x18002923a  mov     edx, 40000000h; dwDesiredAccess
0x18002923f  mov     [rsp+98h+dwCreationDisposition], 1; dwCreationDisposition
0x180029247  mov     rcx, r15; lpFileName
0x18002924a  call    cs:__imp_CreateFileW
0x180029250  mov     rsi, rax
0x180029253  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029257  jnz     short loc_1800292B5
0x180029259  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002925e  test    r12d, r12d
0x180029261  jz      short loc_180029299
0x180029263  cmp     eax, 80070050h
0x180029268  jnz     short loc_180029299
0x18002926a  mov     [rsp+98h+hTemplateFile], r13; hTemplateFile
0x18002926f  xor     r9d, r9d; lpSecurityAttributes
0x180029272  mov     [rsp+98h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180029277  xor     r8d, r8d; dwShareMode
0x18002927a  mov     edx, 40000000h; dwDesiredAccess
0x18002927f  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x180029287  mov     rcx, r15; lpFileName
0x18002928a  call    cs:__imp_CreateFileW
0x180029290  mov     rsi, rax
0x180029293  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029297  jnz     short loc_1800292B5
0x180029299  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002929e  xor     r9d, r9d; int
0x1800292a1  mov     r8d, eax; int
0x1800292a4  mov     edx, 1120327h; unsigned int
0x1800292a9  mov     rcx, r15; unsigned __int16 *
0x1800292ac  mov     ebx, eax
0x1800292ae  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800292b3  jmp     short loc_18002932D
0x1800292b5  mov     rcx, rsi; hFile
0x1800292b8  call    cs:__imp_GetFileType
0x1800292be  cmp     eax, 1
0x1800292c1  jz      short loc_1800292D6
0x1800292c3  mov     ebx, 80070002h
0x1800292c8  mov     ecx, 1180327h; unsigned int
0x1800292cd  mov     edx, ebx; int
0x1800292cf  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800292d4  jmp     short loc_18002931E
0x1800292d6  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800292de  mov     qword ptr [rsp+98h+dwCreationDisposition], r13; lpOverlapped
0x1800292e3  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800292e6  mov     rdx, r14; lpBuffer
0x1800292e9  mov     rcx, rsi; hFile
0x1800292ec  call    cs:__imp_WriteFile
0x1800292f2  test    eax, eax
0x1800292f4  jnz     short loc_180029306
0x1800292f6  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800292fb  mov     ebx, eax
0x1800292fd  mov     edx, eax
0x1800292ff  mov     ecx, 11E0327h
0x180029304  jmp     short loc_1800292CF
0x180029306  cmp     [rsp+98h+NumberOfBytesWritten], ebx
0x18002930d  jz      short loc_18002931B
0x18002930f  mov     ebx, 80070026h
0x180029314  mov     ecx, 1280327h
0x180029319  jmp     short loc_1800292CD
0x18002931b  mov     ebx, r13d
0x18002931e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180029322  jz      short loc_18002932D
0x180029324  mov     rcx, rsi; hObject
0x180029327  call    cs:__imp_CloseHandle
0x18002932d  test    rbp, rbp
0x180029330  jz      short loc_18002933B
0x180029332  mov     rcx, rbp; hMem
0x180029335  call    cs:__imp_LocalFree
0x18002933b  test    rdi, rdi
0x18002933e  jz      short loc_180029349
0x180029340  mov     rcx, rdi; hMem
0x180029343  call    cs:__imp_LocalFree
0x180029349  mov     eax, ebx
0x18002934b  add     rsp, 58h
0x18002934f  pop     r15
0x180029351  pop     r14
0x180029353  pop     r13
0x180029355  pop     r12
0x180029357  pop     rdi
0x180029358  pop     rsi
0x180029359  pop     rbp
0x18002935a  pop     rbx
0x18002935b  retn
```
