# SplPipeline::ProcessBranchOfficeLogging(wchar_t const *,ulong,wchar_t const *,wchar_t const *)

- ea: `0x140011f64`
- end: `0x140012194`
- name: `?ProcessBranchOfficeLogging@SplPipeline@@YAXPEB_WK00@Z`
- size: `560`
- prototype: `void __fastcall(SplPipeline *__hidden this, const wchar_t *, unsigned int, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140011af8`
- `0x14005dba3`

## callees

- `0x140002070`
- `0x14000219c`
- `0x140002c68`
- `0x140009848`
- `0x14000d494`
- `0x140010180`
- `0x140011f64`
- `0x1400123ac`
- `0x1400134d0`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140011fe5`
- `KERNEL32!GetLastError` at `0x140011fe5`
- `KERNEL32!GetProcAddress` at `0x1400120f4`
- `KERNEL32!GetProcAddress` at `0x1400120f4`
- `KERNEL32!LoadLibraryExW` at `0x1400120d2`
- `KERNEL32!LoadLibraryExW` at `0x1400120d2`
- `WINSPOOL!ClosePrinter` at `0x140012144`
- `WINSPOOL!ClosePrinter` at `0x140012164`
- `WINSPOOL!ClosePrinter` at `0x140012144`
- `WINSPOOL!ClosePrinter` at `0x140012164`
- `WINSPOOL!OpenPrinter2W` at `0x140011fad`
- `WINSPOOL!OpenPrinter2W` at `0x14001206b`
- `WINSPOOL!OpenPrinter2W` at `0x140011fad`
- `WINSPOOL!OpenPrinter2W` at `0x14001206b`
- `WINSPOOL!GetPrinterW` at `0x140011fd9`
- `WINSPOOL!GetPrinterW` at `0x140012037`
- `WINSPOOL!GetPrinterW` at `0x140011fd9`
- `WINSPOOL!GetPrinterW` at `0x140012037`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SplPipeline::ProcessBranchOfficeLogging(
        const WCHAR *this,
        const wchar_t *a2,
        __int64 a3,
        const wchar_t *a4)
{
  int v6; // r15d
  int v7; // r12d
  int v8; // esi
  BOOL PrinterW; // ebx
  DWORD v10; // ebx
  void *v11; // rax
  LPBYTE v12; // rdi
  const WCHAR *v13; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v16; // eax
  int v17; // r8d
  DWORD cbBuf; // [rsp+30h] [rbp-99h] BYREF
  HANDLE phPrinter; // [rsp+38h] [rbp-91h] BYREF
  HANDLE hPrinter; // [rsp+40h] [rbp-89h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-81h] BYREF
  LPBYTE pPrinter[2]; // [rsp+50h] [rbp-79h] BYREF
  _DWORD v23[4]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v24; // [rsp+70h] [rbp-59h]
  __int64 v25; // [rsp+78h] [rbp-51h]
  const wchar_t *v26; // [rsp+80h] [rbp-49h]

  v6 = (int)a2;
  v7 = (int)this;
  phPrinter = (HANDLE)-1LL;
  v8 = 0;
  PrinterW = OpenPrinter2W(this, &phPrinter, 0, 0);
  cbBuf = 0;
  if ( PrinterW )
  {
    v8 = 1;
    PrinterW = GetPrinterW(phPrinter, 1u, 0, 0, &cbBuf);
    if ( !PrinterW )
      PrinterW = GetLastError() == 122;
  }
  pPrinter[0] = 0;
  if ( !PrinterW
    || ((v10 = cbBuf,
         v11 = operator new[](cbBuf),
         NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(pPrinter, v11),
         (v12 = pPrinter[0]) == 0)
      ? (PrinterW = 0)
      : (PrinterW = GetPrinterW(phPrinter, 1u, pPrinter[0], v10, &cbBuf)),
        !v12) )
  {
    v12 = 0;
  }
  hPrinter = (HANDLE)-1LL;
  if ( PrinterW )
  {
    v13 = (const WCHAR *)*((_QWORD *)v12 + 3);
    if ( v13 )
      PrinterW = OpenPrinter2W(v13, &hPrinter, 0, 0);
  }
  memset_0(v23, 0, 0x68u);
  if ( PrinterW )
  {
    v23[0] = 1;
    v23[2] = 4;
    v23[3] = v6;
    v25 = *((_QWORD *)v12 + 3);
    v24 = a3;
    if ( !a4 )
      a4 = (const wchar_t *)&dword_14006A39C;
    v26 = a4;
    hModule = 0;
    Library = LoadLibraryExW(L"winspool.drv", 0, 0x800u);
    if ( NCoreLibrary::TAutoHandleHMODULE::operator=(&hModule, Library) )
    {
      ProcAddress = GetProcAddress(hModule, (LPCSTR)0x106);
      if ( ProcAddress )
      {
        v16 = ((__int64 (__fastcall *)(HANDLE, _DWORD *))ProcAddress)(hPrinter, v23);
        if ( v16 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SdD(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&WPP_GLOBAL_Control, v17, v7, v6, v16);
        }
      }
    }
    ClosePrinter(hPrinter);
    NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(&hModule);
  }
  if ( v8 && phPrinter != (HANDLE)-1LL )
    ClosePrinter(phPrinter);
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(pPrinter);
}

```

## disassembly

```asm
0x140011f64  push    rbp
0x140011f66  push    rbx
0x140011f67  push    rsi
0x140011f68  push    rdi
0x140011f69  push    r12
0x140011f6b  push    r13
0x140011f6d  push    r14
0x140011f6f  push    r15
0x140011f71  lea     rbp, [rsp-1Fh]
0x140011f76  sub     rsp, 0E8h
0x140011f7d  mov     rax, cs:__security_cookie
0x140011f84  xor     rax, rsp
0x140011f87  mov     [rbp+57h+var_50], rax
0x140011f8b  mov     r14, r9
0x140011f8e  mov     r13, r8
0x140011f91  mov     r15d, edx
0x140011f94  mov     r12, rcx
0x140011f97  mov     [rsp+120h+phPrinter], 0FFFFFFFFFFFFFFFFh
0x140011fa0  xor     esi, esi
0x140011fa2  xor     r9d, r9d; pOptions
0x140011fa5  xor     r8d, r8d; pDefault
0x140011fa8  lea     rdx, [rsp+120h+phPrinter]; phPrinter
0x140011fad  call    cs:__imp_OpenPrinter2W
0x140011fb3  mov     ebx, eax
0x140011fb5  mov     [rsp+120h+cbBuf], esi
0x140011fb9  lea     ecx, [rsi+1]
0x140011fbc  test    eax, eax
0x140011fbe  jz      short loc_140011FF1
0x140011fc0  mov     esi, ecx
0x140011fc2  lea     rax, [rsp+120h+cbBuf]
0x140011fc7  mov     [rsp+120h+pcbNeeded], rax; pcbNeeded
0x140011fcc  xor     r9d, r9d; cbBuf
0x140011fcf  xor     r8d, r8d; pPrinter
0x140011fd2  mov     edx, ecx; Level
0x140011fd4  mov     rcx, [rsp+120h+phPrinter]; hPrinter
0x140011fd9  call    cs:__imp_GetPrinterW
0x140011fdf  mov     ebx, eax
0x140011fe1  test    eax, eax
0x140011fe3  jnz     short loc_140011FF1
0x140011fe5  call    cs:__imp_GetLastError
0x140011feb  cmp     eax, 7Ah ; 'z'
0x140011fee  setz    bl
0x140011ff1  mov     [rbp+57h+pPrinter], 0
0x140011ff9  test    ebx, ebx
0x140011ffb  jz      short loc_140012048
0x140011ffd  mov     ebx, [rsp+120h+cbBuf]
0x140012001  mov     ecx, ebx; unsigned __int64
0x140012003  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140012008  mov     rdx, rax
0x14001200b  lea     rcx, [rbp+57h+pPrinter]
0x14001200f  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x140012014  mov     rdi, [rbp+57h+pPrinter]
0x140012018  test    rdi, rdi
0x14001201b  jz      short loc_140012041
0x14001201d  lea     rax, [rsp+120h+cbBuf]
0x140012022  mov     [rsp+120h+pcbNeeded], rax; pcbNeeded
0x140012027  mov     r9d, ebx; cbBuf
0x14001202a  mov     r8, rdi; pPrinter
0x14001202d  mov     edx, 1; Level
0x140012032  mov     rcx, [rsp+120h+phPrinter]; hPrinter
0x140012037  call    cs:__imp_GetPrinterW
0x14001203d  mov     ebx, eax
0x14001203f  jmp     short loc_140012043
0x140012041  xor     ebx, ebx
0x140012043  test    rdi, rdi
0x140012046  jnz     short loc_14001204A
0x140012048  xor     edi, edi
0x14001204a  mov     [rsp+120h+hPrinter], 0FFFFFFFFFFFFFFFFh
0x140012053  test    ebx, ebx
0x140012055  jz      short loc_140012073
0x140012057  mov     rcx, [rdi+18h]; pPrinterName
0x14001205b  test    rcx, rcx
0x14001205e  jz      short loc_140012073
0x140012060  xor     r9d, r9d; pOptions
0x140012063  xor     r8d, r8d; pDefault
0x140012066  lea     rdx, [rsp+120h+hPrinter]; phPrinter
0x14001206b  call    cs:__imp_OpenPrinter2W
0x140012071  mov     ebx, eax
0x140012073  xor     edx, edx; Val
0x140012075  lea     r8d, [rdx+68h]; Size
0x140012079  lea     rcx, [rbp+57h+var_C0]; void *
0x14001207d  call    memset_0
0x140012082  test    ebx, ebx
0x140012084  jz      loc_140012155
0x14001208a  mov     [rbp+57h+var_C0], 1
0x140012091  mov     [rbp+57h+var_B8], 4
0x140012098  mov     [rbp+57h+var_B4], r15d
0x14001209c  mov     rax, [rdi+18h]
0x1400120a0  mov     [rbp+57h+var_A8], rax
0x1400120a4  mov     [rbp+57h+var_B0], r13
0x1400120a8  lea     rax, dword_14006A39C
0x1400120af  test    r14, r14
0x1400120b2  cmovz   r14, rax
0x1400120b6  mov     [rbp+57h+var_A0], r14
0x1400120ba  mov     [rsp+120h+hModule], 0
0x1400120c3  xor     edx, edx; hFile
0x1400120c5  mov     r8d, 800h; dwFlags
0x1400120cb  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x1400120d2  call    cs:__imp_LoadLibraryExW
0x1400120d8  mov     rdx, rax
0x1400120db  lea     rcx, [rsp+120h+hModule]
0x1400120e0  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x1400120e5  test    rax, rax
0x1400120e8  jz      short loc_14001213F
0x1400120ea  mov     edx, 106h; lpProcName
0x1400120ef  mov     rcx, [rsp+120h+hModule]; hModule
0x1400120f4  call    cs:__imp_GetProcAddress
0x1400120fa  test    rax, rax
0x1400120fd  jz      short loc_14001213F
0x1400120ff  lea     rdx, [rbp+57h+var_C0]
0x140012103  mov     rcx, [rsp+120h+hPrinter]
0x140012108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001210d  test    eax, eax
0x14001210f  jz      short loc_14001213F
0x140012111  lea     rdx, WPP_GLOBAL_Control
0x140012118  mov     rcx, cs:WPP_GLOBAL_Control
0x14001211f  cmp     rcx, rdx
0x140012122  jz      short loc_14001213F
0x140012124  test    byte ptr [rcx+1Ch], 2
0x140012128  jz      short loc_14001213F
0x14001212a  mov     [rsp+120h+var_F8], eax
0x14001212e  mov     dword ptr [rsp+120h+pcbNeeded], r15d
0x140012133  mov     r9, r12
0x140012136  mov     rcx, [rcx+10h]
0x14001213a  call    WPP_SF_SdD
0x14001213f  mov     rcx, [rsp+120h+hPrinter]; hPrinter
0x140012144  call    cs:__imp_ClosePrinter
0x14001214a  nop
0x14001214b  lea     rcx, [rsp+120h+hModule]
0x140012150  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x140012155  test    esi, esi
0x140012157  jz      short loc_14001216B
0x140012159  mov     rcx, [rsp+120h+phPrinter]; hPrinter
0x14001215e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140012162  jz      short loc_14001216B
0x140012164  call    cs:__imp_ClosePrinter
0x14001216a  nop
0x14001216b  lea     rcx, [rbp+57h+pPrinter]
0x14001216f  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x140012174  mov     rcx, [rbp+57h+var_50]
0x140012178  xor     rcx, rsp; StackCookie
0x14001217b  call    __security_check_cookie
0x140012180  add     rsp, 0E8h
0x140012187  pop     r15
0x140012189  pop     r14
0x14001218b  pop     r13
0x14001218d  pop     r12
0x14001218f  pop     rdi
0x140012190  pop     rsi
0x140012191  pop     rbx
0x140012192  pop     rbp
0x140012193  retn
```
