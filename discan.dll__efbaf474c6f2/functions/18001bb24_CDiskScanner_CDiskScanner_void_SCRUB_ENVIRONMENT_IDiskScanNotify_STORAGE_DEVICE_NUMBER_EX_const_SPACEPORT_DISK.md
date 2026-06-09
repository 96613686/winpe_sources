# CDiskScanner::CDiskScanner(void *,_SCRUB_ENVIRONMENT *,IDiskScanNotify *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *,__POSITION *,ulong)

- ea: `0x18001bb24`
- end: `0x18001be59`
- name: `??0CDiskScanner@@QEAA@PEAXPEAU_SCRUB_ENVIRONMENT@@PEAUIDiskScanNotify@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@PEAU__POSITION@@K@Z`
- size: `821`
- prototype: `CDiskScanner *__fastcall(_OWORD *pv, HANDLE hSourceHandle, struct _SCRUB_ENVIRONMENT *, struct IDiskScanNotify *, _OWORD *TargetHandle, const struct SPACEPORT_DISK_INFO *, struct __POSITION *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800148f4`
- `0x18001548c`

## callees

- `0x180003180`
- `0x1800032f8`
- `0x180003640`
- `0x1800064d8`
- `0x180006688`
- `0x180006b80`
- `0x18001bb24`

## import_xrefs

- `msvcrt!malloc` at `0x18001bcc3`
- `msvcrt!malloc` at `0x18001bce1`
- `msvcrt!malloc` at `0x18001bcc3`
- `msvcrt!malloc` at `0x18001bce1`
- `KERNEL32!DuplicateHandle` at `0x18001bd2e`
- `KERNEL32!DuplicateHandle` at `0x18001bd2e`
- `KERNEL32!GetLastError` at `0x18001bdbf`
- `KERNEL32!GetLastError` at `0x18001bdbf`
- `KERNEL32!CreateThreadpoolWork` at `0x18001bd5d`
- `KERNEL32!CreateThreadpoolWork` at `0x18001bd5d`
- `KERNEL32!GetCurrentProcess` at `0x18001bd00`
- `KERNEL32!GetCurrentProcess` at `0x18001bd09`
- `KERNEL32!GetCurrentProcess` at `0x18001bd00`
- `KERNEL32!GetCurrentProcess` at `0x18001bd09`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CDiskScanner *__fastcall CDiskScanner::CDiskScanner(
        _OWORD *pv,
        HANDLE hSourceHandle,
        struct _SCRUB_ENVIRONMENT *a3,
        struct IDiskScanNotify *a4,
        _OWORD *TargetHandle,
        const struct SPACEPORT_DISK_INFO *a6,
        struct __POSITION *a7,
        unsigned int a8)
{
  _OWORD *v10; // rax
  const struct SPACEPORT_DISK_INFO *v11; // rax
  __int64 v12; // rdx
  USHORT v13; // dx
  USHORT Length; // cx
  USHORT v15; // ax
  void *v16; // rax
  void *v17; // rax
  HANDLE CurrentProcess; // rbx
  HANDLE v19; // rax
  PTP_WORK ThreadpoolWork; // rax
  int Error; // eax
  int v22; // ebx
  signed int LastError; // eax
  signed int v24; // ebx
  const char *v26; // [rsp+40h] [rbp-28h] BYREF
  signed int v27; // [rsp+48h] [rbp-20h]
  PTP_WORK v28; // [rsp+50h] [rbp-18h] BYREF
  char *v29; // [rsp+58h] [rbp-10h]

  v10 = TargetHandle;
  *pv = *TargetHandle;
  pv[1] = v10[1];
  *((_QWORD *)pv + 4) = *((_QWORD *)v10 + 4);
  v11 = a6;
  *(_OWORD *)((char *)pv + 40) = *(_OWORD *)a6;
  *(_OWORD *)((char *)pv + 56) = *((_OWORD *)v11 + 1);
  *((_QWORD *)pv + 9) = a7;
  *((_QWORD *)pv + 10) = a3;
  *((_QWORD *)pv + 11) = a4;
  *((_DWORD *)pv + 26) = a8;
  *((_QWORD *)pv + 14) = 0;
  *((_QWORD *)pv + 15) = 0;
  *((_QWORD *)pv + 16) = 0;
  *((_QWORD *)pv + 17) = 0;
  *((_QWORD *)pv + 18) = 0;
  *((_DWORD *)pv + 38) = 10;
  *((_QWORD *)pv + 21) = pv + 10;
  *((_QWORD *)pv + 20) = pv + 10;
  pv[11] = EmptyUnicodeString;
  *((_QWORD *)pv + 24) = 0;
  *((_QWORD *)pv + 25) = 0;
  *((_QWORD *)pv + 26) = 0;
  *((_QWORD *)pv + 27) = 0;
  *((_QWORD *)pv + 28) = 0;
  *((_QWORD *)pv + 29) = -1;
  *((_DWORD *)pv + 60) = 0;
  *((_BYTE *)pv + 244) = 0;
  *((_QWORD *)pv + 31) = 0;
  *((_DWORD *)pv + 64) = 0;
  *((_BYTE *)pv + 260) = 0;
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v12 + 16) = "CDiskScanner::CDiskScanner";
  v26 = "CDiskScanner::CDiskScanner";
  v27 = 0;
  v13 = ++*(_WORD *)(v12 + 8);
  Length = GlobalIndentString.Length;
  v15 = GlobalIndentString.Length;
  if ( v13 < GlobalIndentString.Length )
    v15 = v13;
  LOWORD(v28) = v15;
  if ( v13 < GlobalIndentString.Length )
    Length = v13;
  WORD1(v28) = Length;
  HIDWORD(v28) = 0;
  v29 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskScanner::CDiskScanner");
  }
  *((_DWORD *)pv + 50) = 192;
  v16 = malloc(0xC0u);
  *((_QWORD *)pv + 26) = v16;
  if ( !v16 || (*((_DWORD *)pv + 54) = 192, v17 = malloc(0xC0u), (*((_QWORD *)pv + 28) = v17) == 0) )
    ATL::AtlThrowImpl(-2147024882);
  if ( hSourceHandle )
  {
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    v19 = GetCurrentProcess();
    if ( !DuplicateHandle(v19, hSourceHandle, CurrentProcess, (LPHANDLE)&TargetHandle, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v24 = LastError;
      if ( LastError > 0 )
        v24 = (unsigned __int16)LastError | 0x80070000;
      if ( v24 >= 0 )
        v24 = -2147467259;
      v27 = v24;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          *((unsigned int *)pv + 4),
          v24);
      }
      ATL::AtlThrowImpl(v24);
    }
    v27 = 0;
    *((_QWORD *)pv + 29) = TargetHandle;
  }
  ThreadpoolWork = CreateThreadpoolWork(
                     CDiskScanner::ScanWorkCallback,
                     pv,
                     *(PTP_CALLBACK_ENVIRON *)(*((_QWORD *)pv + 10) + 72LL));
  v28 = ThreadpoolWork;
  LODWORD(v29) = 0;
  BYTE4(v29) = 0;
  if ( !ThreadpoolWork )
  {
    Error = ATL::AtlHresultFromLastError();
    v22 = Error;
    v27 = Error;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
        *((unsigned int *)pv + 4),
        Error);
    }
    ATL::AtlThrowImpl(v22);
  }
  v28 = 0;
  *((_QWORD *)pv + 31) = ThreadpoolWork;
  CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(&v28);
  CHResultImp::~CHResultImp((CHResultImp *)&v26);
  return (CDiskScanner *)pv;
}

```

## disassembly

```asm
0x18001bb24  mov     [rsp-30h+arg_0], rcx
0x18001bb29  push    rbp
0x18001bb2a  push    rbx
0x18001bb2b  push    rsi
0x18001bb2c  push    rdi
0x18001bb2d  push    r12
0x18001bb2f  push    r14
0x18001bb31  mov     rbp, rsp
0x18001bb34  sub     rsp, 68h
0x18001bb38  mov     rsi, rdx
0x18001bb3b  mov     rdi, rcx
0x18001bb3e  mov     rax, [rbp+TargetHandle]
0x18001bb42  movups  xmm0, xmmword ptr [rax]
0x18001bb45  movups  xmmword ptr [rcx], xmm0
0x18001bb48  movups  xmm1, xmmword ptr [rax+10h]
0x18001bb4c  movups  xmmword ptr [rcx+10h], xmm1
0x18001bb50  movsd   xmm0, qword ptr [rax+20h]
0x18001bb55  movsd   qword ptr [rcx+20h], xmm0
0x18001bb5a  mov     rax, [rbp+arg_28]
0x18001bb5e  movups  xmm0, xmmword ptr [rax]
0x18001bb61  movups  xmmword ptr [rcx+28h], xmm0
0x18001bb65  movups  xmm1, xmmword ptr [rax+10h]
0x18001bb69  movups  xmmword ptr [rcx+38h], xmm1
0x18001bb6d  mov     rax, [rbp+arg_30]
0x18001bb71  mov     [rcx+48h], rax
0x18001bb75  mov     [rcx+50h], r8
0x18001bb79  mov     [rcx+58h], r9
0x18001bb7d  mov     eax, [rbp+arg_38]
0x18001bb80  mov     [rcx+68h], eax
0x18001bb83  xor     r14d, r14d
0x18001bb86  mov     [rcx+70h], r14
0x18001bb8a  mov     [rcx+78h], r14
0x18001bb8e  mov     [rcx+80h], r14
0x18001bb95  mov     [rcx+88h], r14
0x18001bb9c  mov     [rcx+90h], r14
0x18001bba3  mov     dword ptr [rcx+98h], 0Ah
0x18001bbad  lea     rax, [rcx+0A0h]
0x18001bbb4  mov     [rax+8], rax
0x18001bbb8  mov     [rax], rax
0x18001bbbb  movups  xmm0, xmmword ptr cs:?EmptyUnicodeString@@3U_UNICODE_STRING@@B.Length; _UNICODE_STRING const EmptyUnicodeString ...
0x18001bbc2  movdqu  xmmword ptr [rcx+0B0h], xmm0
0x18001bbca  mov     [rcx+0C0h], r14
0x18001bbd1  mov     [rcx+0C8h], r14
0x18001bbd8  mov     [rcx+0D0h], r14
0x18001bbdf  mov     [rcx+0D8h], r14
0x18001bbe6  mov     [rcx+0E0h], r14
0x18001bbed  mov     qword ptr [rcx+0E8h], 0FFFFFFFFFFFFFFFFh
0x18001bbf8  mov     [rcx+0F0h], r14d
0x18001bbff  mov     [rcx+0F4h], r14b
0x18001bc06  mov     [rcx+0F8h], r14
0x18001bc0d  mov     [rcx+100h], r14d
0x18001bc14  mov     [rcx+104h], r14b
0x18001bc1b  mov     ecx, cs:_tls_index
0x18001bc21  mov     rax, gs:58h
0x18001bc2a  mov     rdx, [rax+rcx*8]
0x18001bc2e  mov     eax, 10h
0x18001bc33  lea     r8, aCdiskscannerCd; "CDiskScanner::CDiskScanner"
0x18001bc3a  mov     [rax+rdx], r8
0x18001bc3e  mov     [rbp+var_28], r8
0x18001bc42  mov     [rbp+var_20], r14d
0x18001bc46  mov     eax, 8
0x18001bc4b  inc     word ptr [rax+rdx]
0x18001bc4f  movzx   edx, word ptr [rax+rdx]
0x18001bc53  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001bc5a  movzx   eax, cx
0x18001bc5d  cmp     dx, cx
0x18001bc60  cmovb   ax, dx
0x18001bc64  mov     word ptr [rbp+var_18], ax
0x18001bc68  cmovb   cx, dx
0x18001bc6c  mov     word ptr [rbp+var_18+2], cx
0x18001bc70  xor     eax, eax
0x18001bc72  mov     dword ptr [rbp+var_18+4], eax
0x18001bc75  mov     rax, cs:off_180047060; "                                       "...
0x18001bc7c  mov     [rbp+var_10], rax
0x18001bc80  lea     r12, WPP_GLOBAL_Control
0x18001bc87  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc8e  cmp     rcx, r12
0x18001bc91  jz      short loc_18001BCB6
0x18001bc93  test    byte ptr [rcx+1Ch], 1
0x18001bc97  jz      short loc_18001BCB6
0x18001bc99  cmp     byte ptr [rcx+19h], 5
0x18001bc9d  jb      short loc_18001BCB6
0x18001bc9f  lea     edx, [r14+0Dh]
0x18001bca3  mov     qword ptr [rsp+68h+dwDesiredAccess], r8; __int64
0x18001bca8  lea     r9, [rbp+var_18]
0x18001bcac  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bcb0  call    WPP_SF_aZs
0x18001bcb5  nop
0x18001bcb6  mov     ebx, 0C0h
0x18001bcbb  mov     [rdi+0C8h], ebx
0x18001bcc1  mov     ecx, ebx; Size
0x18001bcc3  call    cs:__imp_malloc
0x18001bcc9  mov     [rdi+0D0h], rax
0x18001bcd0  test    rax, rax
0x18001bcd3  jz      loc_18001BE4E
0x18001bcd9  mov     [rdi+0D8h], ebx
0x18001bcdf  mov     ecx, ebx; Size
0x18001bce1  call    cs:__imp_malloc
0x18001bce7  mov     [rdi+0E0h], rax
0x18001bcee  test    rax, rax
0x18001bcf1  jz      loc_18001BE4E
0x18001bcf7  test    rsi, rsi
0x18001bcfa  jz      short loc_18001BD4B
0x18001bcfc  mov     [rbp+TargetHandle], r14
0x18001bd00  call    cs:__imp_GetCurrentProcess
0x18001bd06  mov     rbx, rax
0x18001bd09  call    cs:__imp_GetCurrentProcess
0x18001bd0f  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18001bd17  mov     [rsp+68h+bInheritHandle], r14d; bInheritHandle
0x18001bd1c  mov     [rsp+68h+dwDesiredAccess], r14d; dwDesiredAccess
0x18001bd21  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18001bd25  mov     r8, rbx; hTargetProcessHandle
0x18001bd28  mov     rdx, rsi; hSourceHandle
0x18001bd2b  mov     rcx, rax; hSourceProcessHandle
0x18001bd2e  call    cs:__imp_DuplicateHandle
0x18001bd34  test    eax, eax
0x18001bd36  jz      loc_18001BDBF
0x18001bd3c  mov     [rbp+var_20], r14d
0x18001bd40  mov     rax, [rbp+TargetHandle]
0x18001bd44  mov     [rdi+0E8h], rax
0x18001bd4b  mov     r8, [rdi+50h]
0x18001bd4f  mov     r8, [r8+48h]; pcbe
0x18001bd53  mov     rdx, rdi; pv
0x18001bd56  lea     rcx, ?ScanWorkCallback@CDiskScanner@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001bd5d  call    cs:__imp_CreateThreadpoolWork
0x18001bd63  mov     [rbp+var_18], rax
0x18001bd67  mov     dword ptr [rbp+var_10], r14d
0x18001bd6b  mov     byte ptr [rbp+var_10+4], r14b
0x18001bd6f  test    rax, rax
0x18001bd72  jnz     loc_18001BE1F
0x18001bd78  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001bd7d  mov     ebx, eax
0x18001bd7f  mov     [rbp+var_20], eax
0x18001bd82  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd89  cmp     rcx, r12
0x18001bd8c  jz      short loc_18001BDB7
0x18001bd8e  test    byte ptr [rcx+1Ch], 1
0x18001bd92  jz      short loc_18001BDB7
0x18001bd94  cmp     byte ptr [rcx+19h], 2
0x18001bd98  jb      short loc_18001BDB7
0x18001bd9a  mov     edx, 0Bh
0x18001bd9f  mov     [rsp+68h+dwDesiredAccess], eax
0x18001bda3  mov     r9d, [rdi+10h]
0x18001bda7  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001bdae  mov     rcx, [rcx+10h]
0x18001bdb2  call    WPP_SF_Dd
0x18001bdb7  mov     ecx, ebx; int
0x18001bdb9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001bdbf  call    cs:__imp_GetLastError
0x18001bdc5  mov     ebx, eax
0x18001bdc7  test    eax, eax
0x18001bdc9  jle     short loc_18001BDD4
0x18001bdcb  movzx   ebx, ax
0x18001bdce  or      ebx, 80070000h
0x18001bdd4  test    ebx, ebx
0x18001bdd6  js      short loc_18001BDDD
0x18001bdd8  mov     ebx, 80004005h
0x18001bddd  mov     eax, ebx
0x18001bddf  mov     [rbp+var_20], ebx
0x18001bde2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bde9  cmp     rcx, r12
0x18001bdec  jz      short loc_18001BE17
0x18001bdee  test    byte ptr [rcx+1Ch], 1
0x18001bdf2  jz      short loc_18001BE17
0x18001bdf4  cmp     byte ptr [rcx+19h], 2
0x18001bdf8  jb      short loc_18001BE17
0x18001bdfa  mov     edx, 0Ah
0x18001bdff  mov     [rsp+68h+dwDesiredAccess], ebx
0x18001be03  mov     r9d, [rdi+10h]
0x18001be07  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001be0e  mov     rcx, [rcx+10h]
0x18001be12  call    WPP_SF_Dd
0x18001be17  mov     ecx, ebx; int
0x18001be19  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001be1f  mov     [rbp+var_18], r14
0x18001be23  mov     [rdi+0F8h], rax
0x18001be2a  lea     rcx, [rbp+var_18]; void *
0x18001be2e  call    ??1?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAA@XZ; CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(void)
0x18001be33  nop
0x18001be34  lea     rcx, [rbp+var_28]; this
0x18001be38  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001be3d  nop
0x18001be3e  mov     rax, rdi
0x18001be41  add     rsp, 68h
0x18001be45  pop     r14
0x18001be47  pop     r12
0x18001be49  pop     rdi
0x18001be4a  pop     rsi
0x18001be4b  pop     rbx
0x18001be4c  pop     rbp
0x18001be4d  retn
0x18001be4e  mov     ecx, 8007000Eh; int
0x18001be53  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
