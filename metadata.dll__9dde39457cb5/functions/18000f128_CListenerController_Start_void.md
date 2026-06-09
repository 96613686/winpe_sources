# CListenerController::Start(void)

- ea: `0x18000f128`
- end: `0x18000f2c7`
- name: `?Start@CListenerController@@QEAAJXZ`
- size: `415`
- prototype: `__int64 __fastcall(CListenerController *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f3dc`
- `0x18001fa58`
- `0x180023548`

## callees

- `0x180008718`
- `0x1800089c8`
- `0x18000974c`
- `0x18000ba98`
- `0x18000eba4`
- `0x18000eea0`
- `0x18000f128`
- `0x18002056c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000f2a0`
- `KERNEL32!SetEvent` at `0x18000f2a0`
- `KERNEL32!ResetEvent` at `0x18000f1f1`
- `KERNEL32!ResetEvent` at `0x18000f1f1`
- `KERNEL32!WaitForSingleObject` at `0x18000f173`
- `KERNEL32!WaitForSingleObject` at `0x18000f173`
- `KERNEL32!EnterCriticalSection` at `0x18000f14a`
- `KERNEL32!EnterCriticalSection` at `0x18000f14a`
- `KERNEL32!GetLastError` at `0x18000f1ff`
- `KERNEL32!GetLastError` at `0x18000f1ff`
- `IisRTL!PuDbgPrintW` at `0x18000f25d`
- `IisRTL!PuDbgPrintW` at `0x18000f25d`

## string_xrefs

- `0x18000f239`: `Unable to create listener object. hr = 0x%x\n`

## pseudocode

```c
__int64 __fastcall CListenerController::Start(CListenerController *this)
{
  HANDLE *v2; // rsi
  __int64 v3; // rcx
  struct ICatalogErrorLogger2 *v4; // rbx
  CFileListener *v5; // rax
  __int64 v6; // r9
  CFileListener *v7; // rax
  HANDLE *v8; // r14
  int v9; // ebx
  signed int LastError; // eax
  int v12; // [rsp+28h] [rbp-60h]
  int v13; // [rsp+50h] [rbp-38h] BYREF
  char *v14; // [rsp+58h] [rbp-30h]

  v13 = 1;
  v14 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( (unsigned int)(*((_DWORD *)this + 2) - 1) <= 1 )
  {
    v9 = 1;
    goto LABEL_20;
  }
  if ( *((_QWORD *)this + 10) )
    goto LABEL_18;
  v2 = (HANDLE *)((char *)this + 96);
  WaitForSingleObject(*((HANDLE *)this + 12), 0xFFFFFFFF);
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    *((_QWORD *)this + 10) = 0;
  }
  v4 = (struct ICatalogErrorLogger2 *)*((_QWORD *)this + 9);
  *((_DWORD *)this + 2) = 2;
  *((_QWORD *)this + 10) = 0;
  v5 = (CFileListener *)operator new(0x268u);
  if ( v5 && (v7 = CFileListener::CFileListener(v5), (v8 = (HANDLE *)v7) != 0) )
  {
    v9 = CFileListener::Init(v7, this, v4);
    if ( v9 >= 0 )
    {
      *((_QWORD *)this + 10) = v8;
      v9 = CFileListener::Subscribe(v8);
      if ( v9 < 0 )
      {
LABEL_17:
        LogEvent(*((struct ICatalogErrorLogger2 **)this + 9), -1073559528, 1, v6, v9, 0, 0);
        v9 = CListenerController::ReportListenerFailure(this, v9);
        SetEvent(*v2);
        goto LABEL_20;
      }
      if ( !ResetEvent(*v2) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_16;
      }
LABEL_18:
      v9 = 0;
      goto LABEL_20;
    }
    (*((void (__fastcall **)(HANDLE *))*v8 + 1))(v8);
  }
  else
  {
    v9 = -2147024882;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v12 = v9;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listenercontroller.cpp",
      310,
      "CListenerController::Start",
      L"Unable to create listener object. hr = 0x%x\n",
      v12);
  }
LABEL_16:
  if ( v9 < 0 )
    goto LABEL_17;
LABEL_20:
  CLock::~CLock((CLock *)&v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f128  push    rbx
0x18000f12a  push    rsi
0x18000f12b  push    rdi
0x18000f12c  push    r14
0x18000f12e  sub     rsp, 68h
0x18000f132  mov     rdi, rcx
0x18000f135  mov     [rsp+88h+var_38], 1
0x18000f13d  add     rcx, 10h
0x18000f141  mov     [rsp+88h+var_30], rcx
0x18000f146  add     rcx, 8; lpCriticalSection
0x18000f14a  call    cs:__imp_EnterCriticalSection
0x18000f150  mov     eax, [rdi+8]
0x18000f153  dec     eax
0x18000f155  cmp     eax, 1
0x18000f158  jbe     loc_18000F2AC
0x18000f15e  cmp     qword ptr [rdi+50h], 0
0x18000f163  jnz     loc_18000F2A8
0x18000f169  lea     rsi, [rdi+60h]
0x18000f16d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f170  mov     rcx, [rsi]; hHandle
0x18000f173  call    cs:__imp_WaitForSingleObject
0x18000f179  mov     rcx, [rdi+50h]
0x18000f17d  test    rcx, rcx
0x18000f180  jz      short loc_18000F196
0x18000f182  mov     rax, [rcx]
0x18000f185  mov     rax, [rax+8]
0x18000f189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f18e  mov     qword ptr [rdi+50h], 0
0x18000f196  mov     rbx, [rdi+48h]
0x18000f19a  mov     ecx, 268h; Size
0x18000f19f  mov     dword ptr [rdi+8], 2
0x18000f1a6  mov     qword ptr [rdi+50h], 0
0x18000f1ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f1b3  test    rax, rax
0x18000f1b6  jz      short loc_18000F224
0x18000f1b8  mov     rcx, rax; this
0x18000f1bb  call    ??0CFileListener@@AEAA@XZ; CFileListener::CFileListener(void)
0x18000f1c0  mov     r14, rax
0x18000f1c3  test    rax, rax
0x18000f1c6  jz      short loc_18000F224
0x18000f1c8  mov     r8, rbx; struct ICatalogErrorLogger2 *
0x18000f1cb  mov     rdx, rdi; struct CListenerController *
0x18000f1ce  mov     rcx, rax; this
0x18000f1d1  call    ?Init@CFileListener@@AEAAJPEAVCListenerController@@PEAUICatalogErrorLogger2@@@Z; CFileListener::Init(CListenerController *,ICatalogErrorLogger2 *)
0x18000f1d6  mov     ebx, eax
0x18000f1d8  mov     rcx, r14; this
0x18000f1db  test    eax, eax
0x18000f1dd  js      short loc_18000F216
0x18000f1df  mov     [rdi+50h], r14
0x18000f1e3  call    ?Subscribe@CFileListener@@QEAAJXZ; CFileListener::Subscribe(void)
0x18000f1e8  mov     ebx, eax
0x18000f1ea  test    eax, eax
0x18000f1ec  js      short loc_18000F267
0x18000f1ee  mov     rcx, [rsi]; hEvent
0x18000f1f1  call    cs:__imp_ResetEvent
0x18000f1f7  test    eax, eax
0x18000f1f9  jnz     loc_18000F2A8
0x18000f1ff  call    cs:__imp_GetLastError
0x18000f205  mov     ebx, eax
0x18000f207  test    eax, eax
0x18000f209  jle     short loc_18000F263
0x18000f20b  movzx   ebx, ax
0x18000f20e  or      ebx, 80070000h
0x18000f214  jmp     short loc_18000F263
0x18000f216  mov     rax, [r14]
0x18000f219  mov     rax, [rax+8]
0x18000f21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f222  jmp     short loc_18000F229
0x18000f224  mov     ebx, 8007000Eh
0x18000f229  test    byte ptr cs:g_dwDebugFlags, 3
0x18000f230  jz      short loc_18000F263
0x18000f232  mov     rcx, cs:g_pDebug
0x18000f239  lea     rax, aUnableToCreate_0; "Unable to create listener object. hr = "...
0x18000f240  mov     dword ptr [rsp+88h+var_60], ebx
0x18000f244  lea     r9, aClistenercontr; "CListenerController::Start"
0x18000f24b  mov     r8d, 136h
0x18000f251  mov     qword ptr [rsp+88h+var_68], rax
0x18000f256  lea     rdx, aInetsrvIisMbMe_7; "inetsrv\\iis\\mb\\metadata\\listenercon"...
0x18000f25d  call    cs:__imp_PuDbgPrintW
0x18000f263  test    ebx, ebx
0x18000f265  jns     short loc_18000F2B1
0x18000f267  mov     rcx, [rdi+48h]; struct ICatalogErrorLogger2 *
0x18000f26b  mov     edx, 0C002C818h; unsigned int
0x18000f270  mov     [rsp+88h+var_58], 0; unsigned __int16 *
0x18000f279  mov     r8d, 1; unsigned int
0x18000f27f  mov     [rsp+88h+var_60], 0; unsigned __int16 *
0x18000f288  mov     dword ptr [rsp+88h+var_68], ebx; char
0x18000f28c  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000f291  mov     edx, ebx; int
0x18000f293  mov     rcx, rdi; this
0x18000f296  call    ?ReportListenerFailure@CListenerController@@QEAAJJ@Z; CListenerController::ReportListenerFailure(long)
0x18000f29b  mov     rcx, [rsi]; hEvent
0x18000f29e  mov     ebx, eax
0x18000f2a0  call    cs:__imp_SetEvent
0x18000f2a6  jmp     short loc_18000F2B1
0x18000f2a8  xor     ebx, ebx
0x18000f2aa  jmp     short loc_18000F2B1
0x18000f2ac  mov     ebx, 1
0x18000f2b1  lea     rcx, [rsp+88h+var_38]; this
0x18000f2b6  call    ??1CLock@@QEAA@XZ; CLock::~CLock(void)
0x18000f2bb  mov     eax, ebx
0x18000f2bd  add     rsp, 68h
0x18000f2c1  pop     r14
0x18000f2c3  pop     rdi
0x18000f2c4  pop     rsi
0x18000f2c5  pop     rbx
0x18000f2c6  retn
```
