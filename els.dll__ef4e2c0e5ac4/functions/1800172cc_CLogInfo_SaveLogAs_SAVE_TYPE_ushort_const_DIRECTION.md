# CLogInfo::SaveLogAs(SAVE_TYPE,ushort const *,DIRECTION)

- ea: `0x1800172cc`
- end: `0x180017628`
- name: `?SaveLogAs@CLogInfo@@QEAAJW4SAVE_TYPE@@PEBGW4DIRECTION@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(__int64, int, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005540`
- `0x1800087bc`

## callees

- `0x180001910`
- `0x180002bb8`
- `0x180005274`
- `0x1800152e8`
- `0x1800153ac`
- `0x1800154e8`
- `0x180015684`
- `0x1800156e8`
- `0x180015870`
- `0x1800158c0`
- `0x1800172cc`
- `0x18001766c`
- `0x18001e214`
- `0x18001e8a0`
- `0x18001eef4`
- `0x18001ef94`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800175e4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800175e4`
- `KERNEL32!CreateFileW` at `0x1800174bc`
- `KERNEL32!CreateFileW` at `0x1800174bc`
- `KERNEL32!CloseHandle` at `0x1800175d8`
- `KERNEL32!CloseHandle` at `0x1800175d8`
- `KERNEL32!GetLastError` at `0x1800174cb`
- `KERNEL32!GetLastError` at `0x1800174cb`
- `USER32!SetCursor` at `0x1800175fa`
- `USER32!SetCursor` at `0x1800175fa`

## pseudocode

```c
__int64 __fastcall CLogInfo::SaveLogAs(__int64 a1, int a2, const unsigned __int16 *a3, unsigned int a4)
{
  int v8; // eax
  CSynchWindow *v9; // rcx
  int v10; // edi
  wchar_t **v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  CSynchWindow *v14; // rcx
  HANDLE FileW; // r14
  signed int LastError; // eax
  unsigned __int16 v17; // r15
  bool v18; // zf
  HWND v20; // [rsp+40h] [rbp-C0h] BYREF
  char *v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  HCURSOR hCursor; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t **v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  unsigned __int64 v26; // [rsp+78h] [rbp-88h]
  unsigned int v27[14]; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENTLOGRECORD *v28; // [rsp+B8h] [rbp-48h]
  int v29; // [rsp+C0h] [rbp-40h]
  __int64 v30; // [rsp+308h] [rbp+208h]

  CWaitCursor::CWaitCursor((CWaitCursor *)&hCursor);
  if ( a2 == 1 )
  {
    *(_OWORD *)v21 = 0;
    v8 = CEventLog::Open((CEventLog *)v21, (struct CLogInfo *)a1);
    v10 = v8;
    if ( v8 < 0 )
    {
      if ( v8 == -2147024891 )
      {
        *(_WORD *)(a1 + 24) |= 0x600u;
        CSynchWindow::Post(v9, 0x7E9u, *(_QWORD *)(a1 + 4872), a1);
        ComposeErrorMessgeFromHRESULT(&v23, 2147942405LL);
        v11 = (wchar_t **)&v23;
        if ( v26 >= 8 )
          v11 = v23;
      }
      else
      {
        ComposeErrorMessgeFromHRESULT(&v23, (unsigned int)v8);
        v11 = (wchar_t **)&v23;
        if ( v26 >= 8 )
          v11 = v23;
      }
      ConsoleMsgBox(*(struct IConsole **)(*(_QWORD *)(a1 + 4872) + 1152LL), 0x101u, 0x10u, a3, v11);
      LOBYTE(v12) = 1;
      std::wstring::_Tidy(&v23, v12, 0);
    }
    else
    {
      v20 = 0;
      (*(void (__fastcall **)(_QWORD, HWND *))(**(_QWORD **)(*(_QWORD *)(a1 + 4872) + 1152LL) + 96LL))(
        *(_QWORD *)(*(_QWORD *)(a1 + 4872) + 1152LL),
        &v20);
      v10 = CEventLog::Backup((CEventLog *)v21, a3, v20);
    }
    CEventLog::Close((CEventLog *)v21);
  }
  else
  {
    CLogCache::CLogCache((CLogCache *)v27);
    v30 = *(_QWORD *)(*(_QWORD *)(a1 + 4872) + 1152LL);
    v13 = CLogCache::Open(v27, (unsigned __int16 *)a1, a4);
    if ( v13 < 0 )
    {
      if ( v13 == -2147024891 )
      {
        *(_WORD *)(a1 + 24) |= 0x600u;
        CSynchWindow::Post(v14, 0x7E9u, *(_QWORD *)(a1 + 4872), a1);
        CLogCache::~CLogCache((CLogCache *)v27);
        v10 = -2147024891;
        goto LABEL_34;
      }
    }
    else
    {
      if ( !v29 )
      {
        CLogCache::~CLogCache((CLogCache *)v27);
        v10 = 0;
        goto LABEL_34;
      }
      CLogCache::Next((CLogCache *)v27);
    }
    FileW = CreateFileW(a3, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v17 = 9;
      if ( a2 != 2 )
        v17 = 44;
      v23 = 0;
      v24 = 80;
      v25 = 0;
      v21[0] = 0;
      LODWORD(v20) = 0;
      v23 = (wchar_t **)operator new[](0xA0u);
      if ( v23 )
      {
        v10 = 0;
        CTextBuffer::Empty((CTextBuffer *)&v23);
      }
      else
      {
        LODWORD(v24) = 0;
        v10 = -2147024882;
      }
LABEL_26:
      v18 = v10 == 0;
      while ( v18 )
      {
        if ( !v28 )
        {
          v10 = -2147024882;
          break;
        }
        v10 = WriteRecordAsText(FileW, (struct CLogInfo *)a1, v28, v17, (wchar_t **)&v23, v21, (unsigned int *)&v20);
        CTextBuffer::Empty((CTextBuffer *)&v23);
        v18 = v10 == 0;
        if ( v10 >= 0 )
        {
          v10 = CLogCache::Next((CLogCache *)v27);
          goto LABEL_26;
        }
      }
      CloseHandle(FileW);
      operator delete[](v23);
    }
    CLogCache::~CLogCache((CLogCache *)v27);
  }
LABEL_34:
  SetCursor(hCursor);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800172cc  mov     [rsp-8+arg_8], rbx
0x1800172d1  push    rbp
0x1800172d2  push    rsi
0x1800172d3  push    rdi
0x1800172d4  push    r14
0x1800172d6  push    r15
0x1800172d8  lea     rbp, [rsp-220h]
0x1800172e0  sub     rsp, 320h
0x1800172e7  mov     rax, cs:__security_cookie
0x1800172ee  xor     rax, rsp
0x1800172f1  mov     [rbp+240h+var_30], rax
0x1800172f8  mov     ebx, r9d
0x1800172fb  mov     r15, r8
0x1800172fe  mov     edi, edx
0x180017300  mov     rsi, rcx
0x180017303  lea     rcx, [rsp+340h+hCursor]; this
0x180017308  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18001730d  nop
0x18001730e  cmp     edi, 1
0x180017311  jnz     loc_180017446
0x180017317  xorps   xmm0, xmm0
0x18001731a  movdqu  xmmword ptr [rsp+340h+var_2F8], xmm0
0x180017320  mov     rdx, rsi; struct CLogInfo *
0x180017323  lea     rcx, [rsp+340h+var_2F8]; this
0x180017328  call    ?Open@CEventLog@@QEAAJPEAVCLogInfo@@@Z; CEventLog::Open(CLogInfo *)
0x18001732d  mov     edi, eax
0x18001732f  xor     ebx, ebx
0x180017331  test    eax, eax
0x180017333  js      short loc_180017372
0x180017335  mov     [rsp+340h+var_300], rbx
0x18001733a  mov     rax, [rsi+1308h]
0x180017341  mov     rcx, [rax+480h]
0x180017348  mov     rax, [rcx]
0x18001734b  lea     rdx, [rsp+340h+var_300]
0x180017350  mov     rax, [rax+60h]
0x180017354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017359  mov     r8, [rsp+340h+var_300]; HWND
0x18001735e  mov     rdx, r15; unsigned __int16 *
0x180017361  lea     rcx, [rsp+340h+var_2F8]; this
0x180017366  call    ?Backup@CEventLog@@QEAAJPEBGPEAUHWND__@@@Z; CEventLog::Backup(ushort const *,HWND__ *)
0x18001736b  mov     edi, eax
0x18001736d  jmp     loc_180017437
0x180017372  mov     r14d, 80070005h
0x180017378  cmp     eax, r14d
0x18001737b  jnz     short loc_1800173E2
0x18001737d  mov     eax, 600h
0x180017382  or      [rsi+18h], ax
0x180017386  mov     r9, rsi; __int64
0x180017389  mov     r8, [rsi+1308h]; unsigned __int64
0x180017390  mov     edx, 7E9h; unsigned int
0x180017395  call    ?Post@CSynchWindow@@QEAAJI_K_J@Z; CSynchWindow::Post(uint,unsigned __int64,__int64)
0x18001739a  mov     edx, r14d
0x18001739d  lea     rcx, [rsp+340h+var_2E0]
0x1800173a2  call    ?ComposeErrorMessgeFromHRESULT@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; ComposeErrorMessgeFromHRESULT(long)
0x1800173a7  nop
0x1800173a8  lea     rax, [rsp+340h+var_2E0]
0x1800173ad  cmp     [rsp+340h+var_2C8], 8
0x1800173b3  cmovnb  rax, [rsp+340h+var_2E0]
0x1800173b9  mov     rcx, [rsi+1308h]
0x1800173c0  mov     qword ptr [rsp+340h+dwCreationDisposition], rax
0x1800173c5  mov     r9, r15
0x1800173c8  mov     edx, 101h; unsigned int
0x1800173cd  mov     r8d, 10h; unsigned int
0x1800173d3  mov     rcx, [rcx+480h]; struct IConsole *
0x1800173da  call    ?ConsoleMsgBox@@YAHPEAUIConsole@@KKZZ; ConsoleMsgBox(IConsole *,ulong,ulong,...)
0x1800173df  nop
0x1800173e0  jmp     short loc_180017427
0x1800173e2  mov     edx, eax
0x1800173e4  lea     rcx, [rsp+340h+var_2E0]
0x1800173e9  call    ?ComposeErrorMessgeFromHRESULT@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; ComposeErrorMessgeFromHRESULT(long)
0x1800173ee  nop
0x1800173ef  lea     rax, [rsp+340h+var_2E0]
0x1800173f4  cmp     [rsp+340h+var_2C8], 8
0x1800173fa  cmovnb  rax, [rsp+340h+var_2E0]
0x180017400  mov     rcx, [rsi+1308h]
0x180017407  mov     qword ptr [rsp+340h+dwCreationDisposition], rax
0x18001740c  mov     r9, r15
0x18001740f  mov     edx, 101h; unsigned int
0x180017414  mov     r8d, 10h; unsigned int
0x18001741a  mov     rcx, [rcx+480h]; struct IConsole *
0x180017421  call    ?ConsoleMsgBox@@YAHPEAUIConsole@@KKZZ; ConsoleMsgBox(IConsole *,ulong,ulong,...)
0x180017426  nop
0x180017427  xor     r8d, r8d
0x18001742a  mov     dl, 1
0x18001742c  lea     rcx, [rsp+340h+var_2E0]
0x180017431  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180017436  nop
0x180017437  lea     rcx, [rsp+340h+var_2F8]; this
0x18001743c  call    ?Close@CEventLog@@QEAAXXZ; CEventLog::Close(void)
0x180017441  jmp     loc_1800175F5
0x180017446  lea     rcx, [rbp+240h+var_2C0]; this
0x18001744a  call    ??0CLogCache@@QEAA@XZ; CLogCache::CLogCache(void)
0x18001744f  nop
0x180017450  mov     rax, [rsi+1308h]
0x180017457  mov     rcx, [rax+480h]
0x18001745e  mov     [rbp+240h+var_38], rcx
0x180017465  mov     r8d, ebx
0x180017468  mov     rdx, rsi
0x18001746b  lea     rcx, [rbp+240h+var_2C0]
0x18001746f  call    ?Open@CLogCache@@QEAAJPEAVCLogInfo@@W4DIRECTION@@@Z; CLogCache::Open(CLogInfo *,DIRECTION)
0x180017474  xor     ebx, ebx
0x180017476  test    eax, eax
0x180017478  js      short loc_1800174E9
0x18001747a  cmp     [rbp+240h+var_280], ebx
0x18001747d  jnz     short loc_18001748F
0x18001747f  lea     rcx, [rbp+240h+var_2C0]; this
0x180017483  call    ??1CLogCache@@QEAA@XZ; CLogCache::~CLogCache(void)
0x180017488  mov     edi, ebx
0x18001748a  jmp     loc_1800175F5
0x18001748f  lea     rcx, [rbp+240h+var_2C0]; this
0x180017493  call    ?Next@CLogCache@@QEAAJXZ; CLogCache::Next(void)
0x180017498  mov     [rsp+340h+hTemplateFile], rbx; hTemplateFile
0x18001749d  mov     [rsp+340h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800174a5  mov     [rsp+340h+dwCreationDisposition], 2; dwCreationDisposition
0x1800174ad  xor     r9d, r9d; lpSecurityAttributes
0x1800174b0  mov     edx, 40000000h; dwDesiredAccess
0x1800174b5  lea     r8d, [r9+1]; dwShareMode
0x1800174b9  mov     rcx, r15; lpFileName
0x1800174bc  call    cs:__imp_CreateFileW
0x1800174c2  mov     r14, rax
0x1800174c5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800174c9  jnz     short loc_180017523
0x1800174cb  call    cs:__imp_GetLastError
0x1800174d1  mov     edi, eax
0x1800174d3  test    eax, eax
0x1800174d5  jle     loc_1800175EB
0x1800174db  movzx   edi, ax
0x1800174de  or      edi, 80070000h
0x1800174e4  jmp     loc_1800175EB
0x1800174e9  mov     r14d, 80070005h
0x1800174ef  cmp     eax, r14d
0x1800174f2  jnz     short loc_180017498
0x1800174f4  mov     eax, 600h
0x1800174f9  or      [rsi+18h], ax
0x1800174fd  mov     r9, rsi; __int64
0x180017500  mov     r8, [rsi+1308h]; unsigned __int64
0x180017507  mov     edx, 7E9h; unsigned int
0x18001750c  call    ?Post@CSynchWindow@@QEAAJI_K_J@Z; CSynchWindow::Post(uint,unsigned __int64,__int64)
0x180017511  nop
0x180017512  lea     rcx, [rbp+240h+var_2C0]; this
0x180017516  call    ??1CLogCache@@QEAA@XZ; CLogCache::~CLogCache(void)
0x18001751b  mov     edi, r14d
0x18001751e  jmp     loc_1800175F5
0x180017523  mov     eax, 2Ch ; ','
0x180017528  lea     r15d, [rax-23h]
0x18001752c  cmp     edi, 2
0x18001752f  cmovnz  r15w, ax
0x180017534  mov     [rsp+340h+var_2E0], rbx
0x180017539  mov     [rsp+340h+var_2D8], 50h ; 'P'
0x180017542  mov     [rsp+340h+var_2D0], rbx
0x180017547  mov     [rsp+340h+var_2F8], rbx
0x18001754c  mov     dword ptr [rsp+340h+var_300], ebx
0x180017550  lea     ecx, [rax+74h]; unsigned __int64
0x180017553  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017558  mov     [rsp+340h+var_2E0], rax
0x18001755d  test    rax, rax
0x180017560  jz      short loc_180017570
0x180017562  mov     edi, ebx
0x180017564  lea     rcx, [rsp+340h+var_2E0]; this
0x180017569  call    ?Empty@CTextBuffer@@QEAAXXZ; CTextBuffer::Empty(void)
0x18001756e  jmp     short loc_180017579
0x180017570  mov     dword ptr [rsp+340h+var_2D8], ebx
0x180017574  mov     edi, 8007000Eh
0x180017579  test    edi, edi
0x18001757b  jnz     short loc_1800175D5
0x18001757d  mov     r8, [rbp+240h+var_288]; struct _EVENTLOGRECORD *
0x180017581  test    r8, r8
0x180017584  jz      short loc_1800175D0
0x180017586  lea     rax, [rsp+340h+var_300]
0x18001758b  mov     [rsp+340h+hTemplateFile], rax; unsigned int *
0x180017590  lea     rax, [rsp+340h+var_2F8]
0x180017595  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], rax; char **
0x18001759a  lea     rax, [rsp+340h+var_2E0]
0x18001759f  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; struct CTextBuffer *
0x1800175a4  movzx   r9d, r15w; unsigned __int16
0x1800175a8  mov     rdx, rsi; struct CLogInfo *
0x1800175ab  mov     rcx, r14; void *
0x1800175ae  call    ?WriteRecordAsText@@YAJPEAXPEAVCLogInfo@@PEAU_EVENTLOGRECORD@@GPEAVCTextBuffer@@PEAPEADPEAK@Z; WriteRecordAsText(void *,CLogInfo *,_EVENTLOGRECORD *,ushort,CTextBuffer *,char * *,ulong *)
0x1800175b3  mov     edi, eax
0x1800175b5  lea     rcx, [rsp+340h+var_2E0]; this
0x1800175ba  call    ?Empty@CTextBuffer@@QEAAXXZ; CTextBuffer::Empty(void)
0x1800175bf  test    edi, edi
0x1800175c1  js      short loc_18001757B
0x1800175c3  lea     rcx, [rbp+240h+var_2C0]; this
0x1800175c7  call    ?Next@CLogCache@@QEAAJXZ; CLogCache::Next(void)
0x1800175cc  mov     edi, eax
0x1800175ce  jmp     short loc_180017579
0x1800175d0  mov     edi, 8007000Eh
0x1800175d5  mov     rcx, r14; hObject
0x1800175d8  call    cs:__imp_CloseHandle
0x1800175de  nop
0x1800175df  mov     rcx, [rsp+340h+var_2E0]
0x1800175e4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800175ea  nop
0x1800175eb  lea     rcx, [rbp+240h+var_2C0]; this
0x1800175ef  call    ??1CLogCache@@QEAA@XZ; CLogCache::~CLogCache(void)
0x1800175f4  nop
0x1800175f5  mov     rcx, [rsp+340h+hCursor]; hCursor
0x1800175fa  call    cs:__imp_SetCursor
0x180017600  mov     eax, edi
0x180017602  mov     rcx, [rbp+240h+var_30]
0x180017609  xor     rcx, rsp; StackCookie
0x18001760c  call    __security_check_cookie
0x180017611  mov     rbx, [rsp+340h+arg_8]
0x180017619  add     rsp, 320h
0x180017620  pop     r15
0x180017622  pop     r14
0x180017624  pop     rdi
0x180017625  pop     rsi
0x180017626  pop     rbp
0x180017627  retn
```
