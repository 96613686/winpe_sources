# RdpDWMDirectWindowContext::CreateMemoryMappedDibSection(uint,uint)

- ea: `0x18000d788`
- end: `0x18000dbfe`
- name: `?CreateMemoryMappedDibSection@RdpDWMDirectWindowContext@@IEAAJII@Z`
- size: `1142`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *this, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e0e8`

## callees

- `0x18000160c`
- `0x180001724`
- `0x18000c4ec`
- `0x18000d788`
- `0x18000e014`
- `0x18000f08c`
- `0x18002b93a`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d90a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d90a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d993`
- `USER32!GetWindowLongPtrW` at `0x18000db76`
- `USER32!GetWindowLongPtrW` at `0x18000db76`
- `GDI32!SelectObject` at `0x18000da38`
- `GDI32!SelectObject` at `0x18000da53`
- `GDI32!SelectObject` at `0x18000da38`
- `GDI32!SelectObject` at `0x18000da53`
- `GDI32!CreateDIBSection` at `0x18000d984`
- `GDI32!CreateDIBSection` at `0x18000d984`
- `GDI32!CreateCompatibleDC` at `0x18000d8fc`
- `GDI32!CreateCompatibleDC` at `0x18000d8fc`
- `GDI32!DeleteDC` at `0x18000da6b`
- `GDI32!DeleteDC` at `0x18000dbb8`
- `GDI32!DeleteDC` at `0x18000da6b`
- `GDI32!DeleteDC` at `0x18000dbb8`
- `GDI32!DeleteObject` at `0x18000da61`
- `GDI32!DeleteObject` at `0x18000dbc6`
- `GDI32!DeleteObject` at `0x18000da61`
- `GDI32!DeleteObject` at `0x18000dbc6`

## string_xrefs

- `0x18000d8e0`: `Failed to create the file mapping`
- `0x18000d836`: `Failed to create shared memory object`
- `0x18000d84f`: `CreateMemoryMappedDibSection`
- `0x18000d938`: `CreateMemoryMappedDibSection`
- `0x18000d9c1`: `CreateMemoryMappedDibSection`
- `0x18000dad2`: `CreateMemoryMappedDibSection`
- `0x18000d95c`: `Failed to create the memory DC`
- `0x18000d9e5`: `Failed to create the DIB section`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::CreateMemoryMappedDibSection(
        RdpDWMDirectWindowContext *this,
        int a2,
        int a3)
{
  unsigned int v4; // r13d
  int v5; // r12d
  __int64 v6; // rdx
  LONG v7; // r12d
  void *v8; // r15
  HDC CompatibleDC; // rsi
  __int64 v10; // rcx
  __int64 v11; // rcx
  signed int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  const char *v18; // rax
  __int16 *v19; // rdx
  signed int LastError; // eax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rdx
  const char *v25; // rax
  HBITMAP v26; // rax
  signed int v27; // eax
  HGDIOBJ v28; // rax
  HDC v29; // rcx
  void *v30; // rdx
  HGDIOBJ v31; // rax
  void *v32; // rcx
  const unsigned __int16 *v33; // rax
  HANDLE v34; // rax
  HWND v35; // rcx
  int v36; // edx
  int v38; // [rsp+50h] [rbp-59h] BYREF
  int v39; // [rsp+54h] [rbp-55h] BYREF
  const char *v40; // [rsp+58h] [rbp-51h] BYREF
  const char *v41; // [rsp+60h] [rbp-49h] BYREF
  const char *v42; // [rsp+68h] [rbp-41h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-39h] BYREF
  const char *v44; // [rsp+78h] [rbp-31h] BYREF
  __int64 v45; // [rsp+80h] [rbp-29h] BYREF
  void *ppvBits; // [rsp+88h] [rbp-21h] BYREF
  BITMAPINFO pbmi; // [rsp+90h] [rbp-19h] BYREF

  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  hObject = 0;
  ppvBits = 0;
  v4 = (a3 + 63) & 0xFFFFFFC0;
  v45 = 0;
  v5 = a2 + 63;
  v6 = *((_QWORD *)this + 8);
  v7 = v5 & 0xFFFFFFC0;
  v8 = 0;
  CompatibleDC = 0;
  pbmi.bmiHeader.biWidth = v7;
  v10 = *((_QWORD *)this + 82);
  pbmi.bmiHeader.biHeight = -v4;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v10 + 96LL))(v10, v6, &v45);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v38 = 879;
      v44 = "Failed to create shared memory object";
      v39 = v12;
      v40 = "CreateMemoryMappedDibSection";
      v41 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      v42 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (__int64)&byte_180038DFF,
        v13,
        v14,
        (const unsigned __int16 **)&v42,
        (__int64)&v39,
        (const unsigned __int16 **)&v41,
        (__int64)&v38,
        (const unsigned __int16 **)&v40,
        (const unsigned __int16 **)&v44);
    }
    goto LABEL_34;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, HANDLE *))(*(_QWORD *)v45 + 48LL))(v45, 4 * v7 * v4, &hObject);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v18 = "Failed to create the file mapping";
      v39 = 884;
      v19 = word_180038DB2;
LABEL_33:
      v42 = v18;
      v41 = "CreateMemoryMappedDibSection";
      v40 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      v44 = "Error HResult failed";
      v38 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v15,
        (__int64)v19,
        v16,
        v17,
        (const unsigned __int16 **)&v44,
        (__int64)&v38,
        (const unsigned __int16 **)&v40,
        (__int64)&v39,
        (const unsigned __int16 **)&v41,
        (const unsigned __int16 **)&v42);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  CompatibleDC = CreateCompatibleDC(0);
  if ( !CompatibleDC )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    if ( (unsigned int)dword_180044008 <= 2 )
      goto LABEL_34;
    v39 = 887;
    v42 = "CreateMemoryMappedDibSection";
    v24 = (__int64 *)byte_180038D6D;
    v41 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
    v25 = "Failed to create the memory DC";
    goto LABEL_21;
  }
  v26 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, hObject, 0);
  if ( !v26 )
  {
    v27 = GetLastError();
    v12 = v27;
    if ( v27 > 0 )
      v12 = (unsigned __int16)v27 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    if ( (unsigned int)dword_180044008 <= 2 )
      goto LABEL_34;
    v39 = 895;
    v42 = "CreateMemoryMappedDibSection";
    v24 = qword_180038D28;
    v41 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
    v25 = "Failed to create the DIB section";
LABEL_21:
    v40 = v25;
    v38 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v21,
      (__int64)v24,
      v22,
      v23,
      (const unsigned __int16 **)&v40,
      (__int64)&v38,
      (const unsigned __int16 **)&v41,
      (__int64)&v39,
      (const unsigned __int16 **)&v42);
    goto LABEL_34;
  }
  v28 = SelectObject(CompatibleDC, v26);
  v29 = (HDC)*((_QWORD *)this + 7);
  v8 = v28;
  if ( v29 )
  {
    v30 = (void *)*((_QWORD *)this + 10);
    if ( v30 )
    {
      v31 = SelectObject(v29, v30);
      if ( v31 )
        DeleteObject(v31);
    }
    DeleteDC(*((HDC *)this + 7));
  }
  v32 = (void *)*((_QWORD *)this + 12);
  if ( v32 )
    CloseHandle(v32);
  v33 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 40LL))(v45);
  v12 = StringCchCopyW((unsigned __int16 *)this + 64, 0x104u, v33);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v18 = "Failed to store current surface name";
      v39 = 937;
      v19 = (__int16 *)byte_180038CDB;
      goto LABEL_33;
    }
LABEL_34:
    *((_WORD *)this + 64) = 0;
    goto LABEL_40;
  }
  v34 = hObject;
  v35 = (HWND)*((_QWORD *)this + 8);
  *((_QWORD *)this + 7) = CompatibleDC;
  CompatibleDC = 0;
  *((_QWORD *)this + 12) = v34;
  *((_QWORD *)this + 14) = ppvBits;
  *((_QWORD *)this + 10) = v8;
  *((_DWORD *)this + 18) = v7;
  *((_DWORD *)this + 19) = v4;
  *((_DWORD *)this + 30) = 4 * v7 * v4;
  hObject = 0;
  if ( v35 && (GetWindowLongPtrW(v35, -20) & 0x80000) != 0 )
    v36 = 0;
  else
    v36 = 255;
  memset_0(*((void **)this + 14), v36, *((unsigned int *)this + 30));
  RdpDWMDirectWindowContext::DrawUnInitializedSurfaceDebugRects(this);
LABEL_40:
  if ( hObject )
    CloseHandle(hObject);
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  if ( v8 )
    DeleteObject(v8);
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v45);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d788  mov     [rsp-8+arg_18], rbx
0x18000d78d  push    rbp
0x18000d78e  push    rsi
0x18000d78f  push    rdi
0x18000d790  push    r12
0x18000d792  push    r13
0x18000d794  push    r14
0x18000d796  push    r15
0x18000d798  lea     rbp, [rsp-27h]
0x18000d79d  sub     rsp, 0D0h
0x18000d7a4  mov     rax, cs:__security_cookie
0x18000d7ab  xor     rax, rsp
0x18000d7ae  mov     [rbp+57h+var_40], rax
0x18000d7b2  mov     rdi, rcx
0x18000d7b5  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18000d7bc  xor     ecx, ecx
0x18000d7be  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18000d7c6  mov     eax, 0FFFFFFC0h
0x18000d7cb  mov     [rbp+57h+hObject], rcx
0x18000d7cf  lea     r13d, [r8+3Fh]
0x18000d7d3  mov     [rbp+57h+ppvBits], rcx
0x18000d7d7  and     r13d, eax
0x18000d7da  mov     [rbp+57h+var_80], rcx
0x18000d7de  lea     r12d, [rdx+3Fh]
0x18000d7e2  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rcx
0x18000d7e6  mov     rdx, [rdi+40h]
0x18000d7ea  lea     r8, [rbp+57h+var_80]
0x18000d7ee  and     r12d, eax
0x18000d7f1  mov     r15d, ecx
0x18000d7f4  mov     esi, ecx
0x18000d7f6  mov     [rbp+57h+pbmi.bmiHeader.biWidth], r12d
0x18000d7fa  mov     rcx, [rdi+290h]
0x18000d801  mov     eax, r13d
0x18000d804  neg     eax
0x18000d806  xorps   xmm0, xmm0
0x18000d809  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18000d80c  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x18000d811  mov     rax, [rcx]
0x18000d814  mov     rax, [rax+60h]
0x18000d818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d81d  mov     ebx, eax
0x18000d81f  test    eax, eax
0x18000d821  jns     loc_18000D8A9
0x18000d827  mov     eax, cs:dword_180044008
0x18000d82d  cmp     eax, 2
0x18000d830  jbe     loc_18000DB31
0x18000d836  lea     rax, aFailedToCreate_13; "Failed to create shared memory object"
0x18000d83d  mov     [rbp+57h+var_B0], 36Fh
0x18000d844  mov     [rbp+57h+var_88], rax
0x18000d848  lea     rdx, byte_180038DFF
0x18000d84f  lea     rax, aCreatememoryma; "CreateMemoryMappedDibSection"
0x18000d856  mov     [rbp+57h+var_AC], ebx
0x18000d859  mov     [rbp+57h+var_A8], rax
0x18000d85d  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000d864  mov     [rbp+57h+var_A0], rax
0x18000d868  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000d86f  mov     [rbp+57h+var_98], rax
0x18000d873  lea     rax, [rbp+57h+var_88]
0x18000d877  mov     [rsp+100h+var_B8], rax
0x18000d87c  lea     rax, [rbp+57h+var_A8]
0x18000d880  mov     [rsp+100h+var_C0], rax
0x18000d885  lea     rax, [rbp+57h+var_B0]
0x18000d889  mov     [rsp+100h+var_C8], rax
0x18000d88e  lea     rax, [rbp+57h+var_A0]
0x18000d892  mov     [rsp+100h+var_D0], rax
0x18000d897  lea     rax, [rbp+57h+var_AC]
0x18000d89b  mov     qword ptr [rsp+100h+offset], rax
0x18000d8a0  lea     rax, [rbp+57h+var_98]
0x18000d8a4  jmp     loc_18000DB27
0x18000d8a9  mov     rcx, [rbp+57h+var_80]
0x18000d8ad  lea     r8, [rbp+57h+hObject]
0x18000d8b1  mov     r14d, r13d
0x18000d8b4  imul    r14d, r12d
0x18000d8b8  mov     rax, [rcx]
0x18000d8bb  shl     r14d, 2
0x18000d8bf  mov     rax, [rax+30h]
0x18000d8c3  mov     edx, r14d
0x18000d8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8cb  mov     ebx, eax
0x18000d8cd  test    eax, eax
0x18000d8cf  jns     short loc_18000D8FA
0x18000d8d1  mov     eax, cs:dword_180044008
0x18000d8d7  cmp     eax, 2
0x18000d8da  jbe     loc_18000DB31
0x18000d8e0  lea     rax, aFailedToCreate_0; "Failed to create the file mapping"
0x18000d8e7  mov     [rbp+57h+var_AC], 374h
0x18000d8ee  lea     rdx, word_180038DB2
0x18000d8f5  jmp     loc_18000DACE
0x18000d8fa  xor     ecx, ecx; hdc
0x18000d8fc  call    cs:__imp_CreateCompatibleDC
0x18000d902  mov     rsi, rax
0x18000d905  test    rax, rax
0x18000d908  jnz     short loc_18000D968
0x18000d90a  call    cs:__imp_GetLastError
0x18000d910  mov     ebx, eax
0x18000d912  test    eax, eax
0x18000d914  jle     short loc_18000D91F
0x18000d916  movzx   ebx, ax
0x18000d919  or      ebx, 80070000h
0x18000d91f  test    ebx, ebx
0x18000d921  mov     eax, 80004005h
0x18000d926  cmovns  ebx, eax
0x18000d929  mov     eax, cs:dword_180044008
0x18000d92f  cmp     eax, 2
0x18000d932  jbe     loc_18000DB31
0x18000d938  lea     rax, aCreatememoryma; "CreateMemoryMappedDibSection"
0x18000d93f  mov     [rbp+57h+var_AC], 377h
0x18000d946  mov     [rbp+57h+var_98], rax
0x18000d94a  lea     rdx, byte_180038D6D
0x18000d951  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000d958  mov     [rbp+57h+var_A0], rax
0x18000d95c  lea     rax, aFailedToCreate_4; "Failed to create the memory DC"
0x18000d963  jmp     loc_18000D9EC
0x18000d968  mov     rax, [rbp+57h+hObject]
0x18000d96c  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x18000d970  mov     [rsp+100h+offset], r15d; offset
0x18000d975  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18000d979  xor     r8d, r8d; usage
0x18000d97c  mov     [rsp+100h+hSection], rax; hSection
0x18000d981  mov     rcx, rsi; hdc
0x18000d984  call    cs:__imp_CreateDIBSection
0x18000d98a  test    rax, rax
0x18000d98d  jnz     loc_18000DA32
0x18000d993  call    cs:__imp_GetLastError
0x18000d999  mov     ebx, eax
0x18000d99b  test    eax, eax
0x18000d99d  jle     short loc_18000D9A8
0x18000d99f  movzx   ebx, ax
0x18000d9a2  or      ebx, 80070000h
0x18000d9a8  test    ebx, ebx
0x18000d9aa  mov     eax, 80004005h
0x18000d9af  cmovns  ebx, eax
0x18000d9b2  mov     eax, cs:dword_180044008
0x18000d9b8  cmp     eax, 2
0x18000d9bb  jbe     loc_18000DB31
0x18000d9c1  lea     rax, aCreatememoryma; "CreateMemoryMappedDibSection"
0x18000d9c8  mov     [rbp+57h+var_AC], 37Fh
0x18000d9cf  mov     [rbp+57h+var_98], rax
0x18000d9d3  lea     rdx, qword_180038D28
0x18000d9da  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000d9e1  mov     [rbp+57h+var_A0], rax
0x18000d9e5  lea     rax, aFailedToCreate_10; "Failed to create the DIB section"
0x18000d9ec  mov     [rbp+57h+var_A8], rax
0x18000d9f0  lea     rax, [rbp+57h+var_98]
0x18000d9f4  mov     [rsp+100h+var_C0], rax
0x18000d9f9  lea     rax, [rbp+57h+var_AC]
0x18000d9fd  mov     [rsp+100h+var_C8], rax
0x18000da02  lea     rax, [rbp+57h+var_A0]
0x18000da06  mov     [rsp+100h+var_D0], rax
0x18000da0b  lea     rax, [rbp+57h+var_B0]
0x18000da0f  mov     qword ptr [rsp+100h+offset], rax
0x18000da14  lea     rax, [rbp+57h+var_A8]
0x18000da18  mov     [rsp+100h+hSection], rax
0x18000da1d  mov     [rbp+57h+var_B0], ebx
0x18000da20  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000da25  test    ebx, ebx
0x18000da27  jns     loc_18000DBA1
0x18000da2d  jmp     loc_18000DB31
0x18000da32  mov     rdx, rax; h
0x18000da35  mov     rcx, rsi; hdc
0x18000da38  call    cs:__imp_SelectObject
0x18000da3e  mov     rcx, [rdi+38h]; hdc
0x18000da42  mov     r15, rax
0x18000da45  test    rcx, rcx
0x18000da48  jz      short loc_18000DA71
0x18000da4a  mov     rdx, [rdi+50h]; h
0x18000da4e  test    rdx, rdx
0x18000da51  jz      short loc_18000DA67
0x18000da53  call    cs:__imp_SelectObject
0x18000da59  test    rax, rax
0x18000da5c  jz      short loc_18000DA67
0x18000da5e  mov     rcx, rax; ho
0x18000da61  call    cs:__imp_DeleteObject
0x18000da67  mov     rcx, [rdi+38h]; hdc
0x18000da6b  call    cs:__imp_DeleteDC
0x18000da71  mov     rcx, [rdi+60h]; hObject
0x18000da75  test    rcx, rcx
0x18000da78  jz      short loc_18000DA80
0x18000da7a  call    cs:__imp_CloseHandle
0x18000da80  mov     rcx, [rbp+57h+var_80]
0x18000da84  mov     rax, [rcx]
0x18000da87  mov     rax, [rax+28h]
0x18000da8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da90  mov     r8, rax; unsigned __int16 *
0x18000da93  lea     rcx, [rdi+80h]; unsigned __int16 *
0x18000da9a  mov     edx, 104h; unsigned __int64
0x18000da9f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000daa4  mov     ebx, eax
0x18000daa6  test    eax, eax
0x18000daa8  jns     loc_18000DB3C
0x18000daae  mov     eax, cs:dword_180044008
0x18000dab4  cmp     eax, 2
0x18000dab7  jbe     short loc_18000DB31
0x18000dab9  lea     rax, aFailedToStoreC; "Failed to store current surface name"
0x18000dac0  mov     [rbp+57h+var_AC], 3A9h
0x18000dac7  lea     rdx, byte_180038CDB
0x18000dace  mov     [rbp+57h+var_98], rax
0x18000dad2  lea     rax, aCreatememoryma; "CreateMemoryMappedDibSection"
0x18000dad9  mov     [rbp+57h+var_A0], rax
0x18000dadd  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000dae4  mov     [rbp+57h+var_A8], rax
0x18000dae8  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000daef  mov     [rbp+57h+var_88], rax
0x18000daf3  lea     rax, [rbp+57h+var_98]
0x18000daf7  mov     [rsp+100h+var_B8], rax
0x18000dafc  lea     rax, [rbp+57h+var_A0]
0x18000db00  mov     [rsp+100h+var_C0], rax
0x18000db05  lea     rax, [rbp+57h+var_AC]
0x18000db09  mov     [rsp+100h+var_C8], rax
0x18000db0e  lea     rax, [rbp+57h+var_A8]
0x18000db12  mov     [rsp+100h+var_D0], rax
0x18000db17  lea     rax, [rbp+57h+var_B0]
0x18000db1b  mov     qword ptr [rsp+100h+offset], rax
0x18000db20  lea     rax, [rbp+57h+var_88]
0x18000db24  mov     [rbp+57h+var_B0], ebx
0x18000db27  mov     [rsp+100h+hSection], rax
0x18000db2c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000db31  xor     eax, eax
0x18000db33  mov     [rdi+80h], ax
0x18000db3a  jmp     short loc_18000DBA1
0x18000db3c  mov     rax, [rbp+57h+hObject]
0x18000db40  mov     rcx, [rdi+40h]; hWnd
0x18000db44  mov     [rdi+38h], rsi
0x18000db48  xor     esi, esi
0x18000db4a  mov     [rdi+60h], rax
0x18000db4e  mov     rax, [rbp+57h+ppvBits]
0x18000db52  mov     [rdi+70h], rax
0x18000db56  mov     [rdi+50h], r15
0x18000db5a  mov     [rdi+48h], r12d
0x18000db5e  mov     [rdi+4Ch], r13d
0x18000db62  mov     [rdi+78h], r14d
0x18000db66  mov     [rbp+57h+hObject], 0
0x18000db6e  test    rcx, rcx
0x18000db71  jz      short loc_18000DB87
0x18000db73  lea     edx, [rsi-14h]; nIndex
0x18000db76  call    cs:__imp_GetWindowLongPtrW
0x18000db7c  bt      rax, 13h
0x18000db81  jnb     short loc_18000DB87
0x18000db83  xor     edx, edx
0x18000db85  jmp     short loc_18000DB8C
0x18000db87  mov     edx, 0FFh; Val
0x18000db8c  mov     r8d, [rdi+78h]; Size
0x18000db90  mov     rcx, [rdi+70h]; void *
0x18000db94  call    memset_0
0x18000db99  mov     rcx, rdi; this
0x18000db9c  call    ?DrawUnInitializedSurfaceDebugRects@RdpDWMDirectWindowContext@@IEAAXXZ; RdpDWMDirectWindowContext::DrawUnInitializedSurfaceDebugRects(void)
0x18000dba1  mov     rcx, [rbp+57h+hObject]; hObject
0x18000dba5  test    rcx, rcx
0x18000dba8  jz      short loc_18000DBB0
0x18000dbaa  call    cs:__imp_CloseHandle
0x18000dbb0  test    rsi, rsi
0x18000dbb3  jz      short loc_18000DBBE
0x18000dbb5  mov     rcx, rsi; hdc
0x18000dbb8  call    cs:__imp_DeleteDC
0x18000dbbe  test    r15, r15
0x18000dbc1  jz      short loc_18000DBCC
0x18000dbc3  mov     rcx, r15; ho
0x18000dbc6  call    cs:__imp_DeleteObject
0x18000dbcc  lea     rcx, [rbp+57h+var_80]
0x18000dbd0  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18000dbd5  mov     eax, ebx
0x18000dbd7  mov     rcx, [rbp+57h+var_40]
0x18000dbdb  xor     rcx, rsp; StackCookie
0x18000dbde  call    __security_check_cookie
0x18000dbe3  mov     rbx, [rsp+100h+arg_18]
0x18000dbeb  add     rsp, 0D0h
0x18000dbf2  pop     r15
0x18000dbf4  pop     r14
0x18000dbf6  pop     r13
0x18000dbf8  pop     r12
0x18000dbfa  pop     rdi
0x18000dbfb  pop     rsi
0x18000dbfc  pop     rbp
0x18000dbfd  retn
```
