# CFileContentsFileReader::ValidateData(long,unsigned __int64)

- ea: `0x140068850`
- end: `0x140068a73`
- name: `?ValidateData@CFileContentsFileReader@@UEAAJJ_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(CFileContentsFileReader *__hidden this, int, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x1400451e8`
- `0x140068850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400688ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140068a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400688ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140068a27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400688c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140068a4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400688c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140068a4f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140068a18`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140068a18`

## pseudocode

```c
__int64 __fastcall CFileContentsFileReader::ValidateData(CFileContentsFileReader *this, int a2, int a3)
{
  __int64 v3; // r14
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int Fgd; // ebx
  HANDLE *v7; // rdi
  void *v8; // rcx
  _DWORD **v9; // r15
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]

  v3 = a2;
  if ( a2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    Fgd = -2147024809;
    v7 = (HANDLE *)((char *)this + 32);
LABEL_31:
    if ( *v7 )
      CloseHandle(*v7);
    *v7 = 0;
    return (unsigned int)Fgd;
  }
  v7 = (HANDLE *)((char *)this + 32);
  v8 = (void *)*((_QWORD *)this + 4);
  if ( v8 )
  {
    if ( !CloseHandle(v8) )
      GetLastError();
    *v7 = 0;
  }
  v9 = (_DWORD **)((char *)this + 40);
  if ( !*((_QWORD *)this + 5) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids, v10);
    }
    Fgd = CHdropToFgdConverter::GetFgd(
            *((CHdropToFgdConverter **)this + 6),
            (struct _FILEGROUPDESCRIPTORW **)this + 5,
            a3);
    if ( Fgd < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        dwFlagsAndAttributes = Fgd;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          (unsigned int)&WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids,
          v11,
          (__int64)"GetFgd failed!",
          dwFlagsAndAttributes);
      }
      goto LABEL_31;
    }
  }
  if ( (unsigned int)v3 >= **v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids, v12);
    }
    Fgd = -2147467259;
    goto LABEL_31;
  }
  FileW = CreateFileW((LPCWSTR)&(*v9)[148 * v3 + 19], 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  *v7 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    *((_DWORD *)this + 6) = v3;
    return 0;
  }
  LastError = GetLastError();
  Fgd = LastError;
  if ( LastError > 0 )
    Fgd = (unsigned __int16)LastError | 0x80070000;
  *v7 = 0;
  if ( Fgd < 0 )
    goto LABEL_31;
  return (unsigned int)Fgd;
}

```

## disassembly

```asm
0x140068850  push    rbx
0x140068852  push    rbp
0x140068853  push    rsi
0x140068854  push    rdi
0x140068855  push    r14
0x140068857  push    r15
0x140068859  sub     rsp, 48h
0x14006885d  movsxd  r14, edx
0x140068860  mov     rbp, rcx
0x140068863  test    edx, edx
0x140068865  jns     short loc_1400688B8
0x140068867  mov     rax, cs:WPP_GLOBAL_Control
0x14006886e  lea     rsi, WPP_GLOBAL_Control
0x140068875  cmp     rax, rsi
0x140068878  jz      short loc_1400688AA
0x14006887a  test    byte ptr [rax+1Ch], 1
0x14006887e  jz      short loc_1400688AA
0x140068880  cmp     byte ptr [rax+19h], 2
0x140068884  jb      short loc_1400688AA
0x140068886  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006888b  mov     rcx, cs:WPP_GLOBAL_Control
0x140068892  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x140068899  mov     edx, 3Bh ; ';'
0x14006889e  mov     r9d, eax
0x1400688a1  mov     rcx, [rcx+10h]
0x1400688a5  call    WPP_SF_d
0x1400688aa  mov     ebx, 80070057h
0x1400688af  lea     rdi, [rbp+20h]
0x1400688b3  jmp     loc_140068A47
0x1400688b8  lea     rdi, [rcx+20h]
0x1400688bc  mov     rcx, [rdi]; hObject
0x1400688bf  test    rcx, rcx
0x1400688c2  jz      short loc_1400688DB
0x1400688c4  call    cs:__imp_CloseHandle
0x1400688ca  test    eax, eax
0x1400688cc  jnz     short loc_1400688D4
0x1400688ce  call    cs:__imp_GetLastError
0x1400688d4  mov     qword ptr [rdi], 0
0x1400688db  lea     r15, [rbp+28h]
0x1400688df  cmp     qword ptr [r15], 0
0x1400688e3  lea     rsi, WPP_GLOBAL_Control
0x1400688ea  jnz     loc_14006899B
0x1400688f0  mov     rax, cs:WPP_GLOBAL_Control
0x1400688f7  cmp     rax, rsi
0x1400688fa  jz      short loc_14006892C
0x1400688fc  test    byte ptr [rax+1Ch], 1
0x140068900  jz      short loc_14006892C
0x140068902  cmp     byte ptr [rax+19h], 5
0x140068906  jb      short loc_14006892C
0x140068908  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006890d  mov     rcx, cs:WPP_GLOBAL_Control
0x140068914  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x14006891b  mov     edx, 3Ch ; '<'
0x140068920  mov     r9d, eax
0x140068923  mov     rcx, [rcx+10h]
0x140068927  call    WPP_SF_d
0x14006892c  mov     rcx, [rbp+30h]; this
0x140068930  mov     rdx, r15; struct _FILEGROUPDESCRIPTORW **
0x140068933  call    ?GetFgd@CHdropToFgdConverter@@QEAAJPEAPEAU_FILEGROUPDESCRIPTORW@@H@Z; CHdropToFgdConverter::GetFgd(_FILEGROUPDESCRIPTORW * *,int)
0x140068938  mov     ebx, eax
0x14006893a  test    eax, eax
0x14006893c  jns     short loc_14006899B
0x14006893e  mov     rax, cs:WPP_GLOBAL_Control
0x140068945  cmp     rax, rsi
0x140068948  jz      loc_140068A47
0x14006894e  test    byte ptr [rax+1Ch], 8
0x140068952  jz      loc_140068A47
0x140068958  cmp     byte ptr [rax+19h], 2
0x14006895c  jb      loc_140068A47
0x140068962  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140068967  lea     rcx, aGetfgdFailed; "GetFgd failed!"
0x14006896e  mov     [rsp+78h+dwFlagsAndAttributes], ebx
0x140068972  mov     qword ptr [rsp+78h+dwCreationDisposition], rcx
0x140068977  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x14006897e  mov     rcx, cs:WPP_GLOBAL_Control
0x140068985  mov     edx, 3Dh ; '='
0x14006898a  mov     r9d, eax
0x14006898d  mov     rcx, [rcx+10h]
0x140068991  call    WPP_SF_DsD
0x140068996  jmp     loc_140068A47
0x14006899b  mov     rdx, [r15]
0x14006899e  cmp     r14d, [rdx]
0x1400689a1  jb      short loc_1400689E6
0x1400689a3  mov     rax, cs:WPP_GLOBAL_Control
0x1400689aa  cmp     rax, rsi
0x1400689ad  jz      short loc_1400689DF
0x1400689af  test    byte ptr [rax+1Ch], 1
0x1400689b3  jz      short loc_1400689DF
0x1400689b5  cmp     byte ptr [rax+19h], 2
0x1400689b9  jb      short loc_1400689DF
0x1400689bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400689c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400689c7  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x1400689ce  mov     edx, 3Eh ; '>'
0x1400689d3  mov     r9d, eax
0x1400689d6  mov     rcx, [rcx+10h]
0x1400689da  call    WPP_SF_d
0x1400689df  mov     ebx, 80004005h
0x1400689e4  jmp     short loc_140068A47
0x1400689e6  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1400689ef  mov     r8d, 3; dwShareMode
0x1400689f5  imul    rcx, r14, 250h
0x1400689fc  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x140068a04  xor     r9d, r9d; lpSecurityAttributes
0x140068a07  add     rcx, 4Ch ; 'L'
0x140068a0b  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x140068a10  add     rcx, rdx; lpFileName
0x140068a13  mov     edx, 80000000h; dwDesiredAccess
0x140068a18  call    cs:__imp_CreateFileW
0x140068a1e  mov     [rdi], rax
0x140068a21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140068a25  jnz     short loc_140068A5E
0x140068a27  call    cs:__imp_GetLastError
0x140068a2d  mov     ebx, eax
0x140068a2f  test    eax, eax
0x140068a31  jle     short loc_140068A3C
0x140068a33  movzx   ebx, ax
0x140068a36  or      ebx, 80070000h
0x140068a3c  mov     qword ptr [rdi], 0
0x140068a43  test    ebx, ebx
0x140068a45  jns     short loc_140068A64
0x140068a47  mov     rcx, [rdi]; hObject
0x140068a4a  test    rcx, rcx
0x140068a4d  jz      short loc_140068A55
0x140068a4f  call    cs:__imp_CloseHandle
0x140068a55  mov     qword ptr [rdi], 0
0x140068a5c  jmp     short loc_140068A64
0x140068a5e  mov     [rbp+18h], r14d
0x140068a62  xor     ebx, ebx
0x140068a64  mov     eax, ebx
0x140068a66  add     rsp, 48h
0x140068a6a  pop     r15
0x140068a6c  pop     r14
0x140068a6e  pop     rdi
0x140068a6f  pop     rsi
0x140068a70  pop     rbp
0x140068a71  pop     rbx
0x140068a72  retn
```
