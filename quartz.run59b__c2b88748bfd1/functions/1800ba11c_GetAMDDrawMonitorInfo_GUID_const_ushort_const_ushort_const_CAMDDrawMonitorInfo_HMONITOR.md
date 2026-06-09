# GetAMDDrawMonitorInfo(_GUID const *,ushort const *,ushort const *,CAMDDrawMonitorInfo *,HMONITOR__ *)

- ea: `0x1800ba11c`
- end: `0x1800ba36f`
- name: `?GetAMDDrawMonitorInfo@@YAHPEBU_GUID@@PEBG1PEAUCAMDDrawMonitorInfo@@PEAUHMONITOR__@@@Z`
- size: `595`
- prototype: `int(const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, struct CAMDDrawMonitorInfo *, HMONITOR)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800ba080`
- `0x1800ba574`

## callees

- `0x1800078b0`
- `0x1800388a0`
- `0x180039250`
- `0x1800ba11c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800ba198`
- `KERNEL32!lstrcmpiW` at `0x1800ba198`
- `GDI32!DeleteObject` at `0x1800ba2a2`
- `GDI32!DeleteObject` at `0x1800ba2a2`
- `GDI32!DeleteDC` at `0x1800ba20f`
- `GDI32!DeleteDC` at `0x1800ba2b1`
- `GDI32!DeleteDC` at `0x1800ba20f`
- `GDI32!DeleteDC` at `0x1800ba2b1`
- `GDI32!GetDIBits` at `0x1800ba265`
- `GDI32!GetDIBits` at `0x1800ba293`
- `GDI32!GetDIBits` at `0x1800ba265`
- `GDI32!GetDIBits` at `0x1800ba293`
- `GDI32!CreateCompatibleBitmap` at `0x1800ba1f8`
- `GDI32!CreateCompatibleBitmap` at `0x1800ba1f8`
- `GDI32!CreateDCW` at `0x1800ba1be`
- `GDI32!CreateDCW` at `0x1800ba1be`
- `USER32!GetSystemMetrics` at `0x1800ba2e1`
- `USER32!GetSystemMetrics` at `0x1800ba2f1`
- `USER32!GetSystemMetrics` at `0x1800ba2e1`
- `USER32!GetSystemMetrics` at `0x1800ba2f1`
- `USER32!SetRect` at `0x1800ba30d`
- `USER32!SetRect` at `0x1800ba30d`
- `USER32!GetMonitorInfoW` at `0x1800ba32f`
- `USER32!GetMonitorInfoW` at `0x1800ba32f`
- `USER32!MonitorFromWindow` at `0x1800ba2c7`
- `USER32!MonitorFromWindow` at `0x1800ba2c7`

## pseudocode

```c
__int64 __fastcall GetAMDDrawMonitorInfo(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CAMDDrawMonitorInfo *a4,
        HMONITOR hMonitor)
{
  const WCHAR *v9; // rdx
  const WCHAR *v10; // rcx
  HDC DCW; // rbx
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v13; // rbp
  HMONITOR v15; // rax
  int SystemMetrics; // ebx
  int v17; // eax
  RECT rcMonitor; // xmm0
  struct tagMONITORINFO mi; // [rsp+40h] [rbp-B8h] BYREF

  memset_0(&mi.rcMonitor, 0, 0x64u);
  mi.cbSize = 104;
  StringCchCopyW((unsigned __int16 *)a4 + 26, 0x20u, a3);
  StringCchCopyW((unsigned __int16 *)a4 + 58, 0x100u, a2);
  if ( lstrcmpiW(a3, L"DISPLAY") )
  {
    v9 = a3;
    v10 = 0;
  }
  else
  {
    v9 = 0;
    v10 = L"DISPLAY";
  }
  DCW = CreateDCW(v10, v9, 0, 0);
  if ( !DCW )
    return 0;
  memset_0((char *)a4 + 1036, 0, 0x434u);
  CompatibleBitmap = CreateCompatibleBitmap(DCW, 1, 1);
  v13 = CompatibleBitmap;
  if ( !CompatibleBitmap )
  {
    DeleteDC(DCW);
    return 0;
  }
  *((_DWORD *)a4 + 259) = 40;
  GetDIBits(DCW, CompatibleBitmap, 0, 1u, 0, (LPBITMAPINFO)((char *)a4 + 1036), 0);
  GetDIBits(DCW, v13, 0, 1u, 0, (LPBITMAPINFO)((char *)a4 + 1036), 0);
  DeleteObject(v13);
  DeleteDC(DCW);
  if ( a1 )
  {
    if ( !GetMonitorInfoW(hMonitor, &mi) )
      return 0;
    rcMonitor = mi.rcMonitor;
    *((_DWORD *)a4 + 12) = mi.dwFlags;
    *(_QWORD *)a4 = (char *)a4 + 8;
    *(RECT *)((char *)a4 + 24) = rcMonitor;
    *((_QWORD *)a4 + 5) = hMonitor;
    *(struct _GUID *)((char *)a4 + 8) = *a1;
  }
  else
  {
    v15 = MonitorFromWindow(0, 1u);
    *((_DWORD *)a4 + 12) = 1;
    *((_QWORD *)a4 + 5) = v15;
    *(_QWORD *)a4 = 0;
    SystemMetrics = GetSystemMetrics(1);
    v17 = GetSystemMetrics(0);
    SetRect((LPRECT)((char *)a4 + 24), 0, 0, v17, SystemMetrics);
    *(GUID *)((char *)a4 + 8) = GUID_NULL;
  }
  return 1;
}

```

## disassembly

```asm
0x1800ba11c  push    rbx
0x1800ba11e  push    rbp
0x1800ba11f  push    rsi
0x1800ba120  push    rdi
0x1800ba121  push    r13
0x1800ba123  push    r14
0x1800ba125  push    r15
0x1800ba127  sub     rsp, 0C0h
0x1800ba12e  mov     rax, cs:__security_cookie
0x1800ba135  xor     rax, rsp
0x1800ba138  mov     [rsp+0F8h+var_48], rax
0x1800ba140  mov     r14, [rsp+0F8h+hMonitor]
0x1800ba148  mov     rbx, rdx
0x1800ba14b  xor     edx, edx; Val
0x1800ba14d  mov     rsi, r8
0x1800ba150  mov     r15, rcx
0x1800ba153  mov     rdi, r9
0x1800ba156  lea     rcx, [rsp+0F8h+mi.rcMonitor]; void *
0x1800ba15b  lea     r8d, [rdx+64h]; Size
0x1800ba15f  call    memset_0
0x1800ba164  lea     rcx, [rdi+34h]; unsigned __int16 *
0x1800ba168  mov     [rsp+0F8h+mi.cbSize], 68h ; 'h'
0x1800ba170  mov     r8, rsi; unsigned __int16 *
0x1800ba173  mov     edx, 20h ; ' '; unsigned __int64
0x1800ba178  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ba17d  lea     rcx, [rdi+74h]; unsigned __int16 *
0x1800ba181  mov     r8, rbx; unsigned __int16 *
0x1800ba184  mov     edx, 100h; unsigned __int64
0x1800ba189  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ba18e  lea     rdx, aDisplay_1; "DISPLAY"
0x1800ba195  mov     rcx, rsi; lpString1
0x1800ba198  call    cs:__imp_lstrcmpiW
0x1800ba19f  nop     dword ptr [rax+rax+00h]
0x1800ba1a4  xor     r9d, r9d; pdm
0x1800ba1a7  xor     r8d, r8d; pszPort
0x1800ba1aa  test    eax, eax
0x1800ba1ac  jnz     short loc_1800BA1B9
0x1800ba1ae  xor     edx, edx
0x1800ba1b0  lea     rcx, aDisplay_1; "DISPLAY"
0x1800ba1b7  jmp     short loc_1800BA1BE
0x1800ba1b9  mov     rdx, rsi; pwszDevice
0x1800ba1bc  xor     ecx, ecx; pwszDriver
0x1800ba1be  call    cs:__imp_CreateDCW
0x1800ba1c5  nop     dword ptr [rax+rax+00h]
0x1800ba1ca  mov     rbx, rax
0x1800ba1cd  test    rax, rax
0x1800ba1d0  jz      short loc_1800BA21B
0x1800ba1d2  lea     rsi, [rdi+40Ch]
0x1800ba1d9  xor     edx, edx; Val
0x1800ba1db  mov     rcx, rsi; void *
0x1800ba1de  mov     r8d, 434h; Size
0x1800ba1e4  call    memset_0
0x1800ba1e9  mov     r13d, 1
0x1800ba1ef  mov     rcx, rbx; hdc
0x1800ba1f2  mov     r8d, r13d; cy
0x1800ba1f5  mov     edx, r13d; cx
0x1800ba1f8  call    cs:__imp_CreateCompatibleBitmap
0x1800ba1ff  nop     dword ptr [rax+rax+00h]
0x1800ba204  mov     rbp, rax
0x1800ba207  mov     rcx, rbx; hdc
0x1800ba20a  test    rax, rax
0x1800ba20d  jnz     short loc_1800BA240
0x1800ba20f  call    cs:__imp_DeleteDC
0x1800ba216  nop     dword ptr [rax+rax+00h]
0x1800ba21b  xor     eax, eax
0x1800ba21d  mov     rcx, [rsp+0F8h+var_48]
0x1800ba225  xor     rcx, rsp; StackCookie
0x1800ba228  call    __security_check_cookie
0x1800ba22d  add     rsp, 0C0h
0x1800ba234  pop     r15
0x1800ba236  pop     r14
0x1800ba238  pop     r13
0x1800ba23a  pop     rdi
0x1800ba23b  pop     rsi
0x1800ba23c  pop     rbp
0x1800ba23d  pop     rbx
0x1800ba23e  retn
0x1800ba240  mov     [rsp+0F8h+usage], 0; usage
0x1800ba248  mov     r9d, r13d; cLines
0x1800ba24b  mov     [rsp+0F8h+lpbmi], rsi; lpbmi
0x1800ba250  xor     r8d, r8d; start
0x1800ba253  mov     rdx, rbp; hbm
0x1800ba256  mov     [rsp+0F8h+lpvBits], 0; lpvBits
0x1800ba25f  mov     dword ptr [rsi], 28h ; '('
0x1800ba265  call    cs:__imp_GetDIBits
0x1800ba26c  nop     dword ptr [rax+rax+00h]
0x1800ba271  mov     [rsp+0F8h+usage], 0; usage
0x1800ba279  mov     r9d, r13d; cLines
0x1800ba27c  mov     [rsp+0F8h+lpbmi], rsi; lpbmi
0x1800ba281  xor     r8d, r8d; start
0x1800ba284  mov     rdx, rbp; hbm
0x1800ba287  mov     [rsp+0F8h+lpvBits], 0; lpvBits
0x1800ba290  mov     rcx, rbx; hdc
0x1800ba293  call    cs:__imp_GetDIBits
0x1800ba29a  nop     dword ptr [rax+rax+00h]
0x1800ba29f  mov     rcx, rbp; ho
0x1800ba2a2  call    cs:__imp_DeleteObject
0x1800ba2a9  nop     dword ptr [rax+rax+00h]
0x1800ba2ae  mov     rcx, rbx; hdc
0x1800ba2b1  call    cs:__imp_DeleteDC
0x1800ba2b8  nop     dword ptr [rax+rax+00h]
0x1800ba2bd  test    r15, r15
0x1800ba2c0  jnz     short loc_1800BA327
0x1800ba2c2  mov     edx, r13d; dwFlags
0x1800ba2c5  xor     ecx, ecx; hwnd
0x1800ba2c7  call    cs:__imp_MonitorFromWindow
0x1800ba2ce  nop     dword ptr [rax+rax+00h]
0x1800ba2d3  mov     ecx, r13d; nIndex
0x1800ba2d6  mov     [rdi+30h], r13d
0x1800ba2da  mov     [rdi+28h], rax
0x1800ba2de  mov     [rdi], r15
0x1800ba2e1  call    cs:__imp_GetSystemMetrics
0x1800ba2e8  nop     dword ptr [rax+rax+00h]
0x1800ba2ed  xor     ecx, ecx; nIndex
0x1800ba2ef  mov     ebx, eax
0x1800ba2f1  call    cs:__imp_GetSystemMetrics
0x1800ba2f8  nop     dword ptr [rax+rax+00h]
0x1800ba2fd  lea     rcx, [rdi+18h]; lprc
0x1800ba301  mov     dword ptr [rsp+0F8h+lpvBits], ebx; yBottom
0x1800ba305  mov     r9d, eax; xRight
0x1800ba308  xor     r8d, r8d; yTop
0x1800ba30b  xor     edx, edx; xLeft
0x1800ba30d  call    cs:__imp_SetRect
0x1800ba314  nop     dword ptr [rax+rax+00h]
0x1800ba319  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800ba320  movdqu  xmmword ptr [rdi+8], xmm0
0x1800ba325  jmp     short loc_1800BA367
0x1800ba327  lea     rdx, [rsp+0F8h+mi]; lpmi
0x1800ba32c  mov     rcx, r14; hMonitor
0x1800ba32f  call    cs:__imp_GetMonitorInfoW
0x1800ba336  nop     dword ptr [rax+rax+00h]
0x1800ba33b  test    eax, eax
0x1800ba33d  jz      loc_1800BA21B
0x1800ba343  mov     ecx, [rsp+0F8h+mi.dwFlags]
0x1800ba347  movups  xmm0, xmmword ptr [rsp+0F8h+mi.rcMonitor.left]
0x1800ba34c  mov     [rdi+30h], ecx
0x1800ba34f  lea     rcx, [rdi+8]
0x1800ba353  mov     [rdi], rcx
0x1800ba356  movdqu  xmmword ptr [rdi+18h], xmm0
0x1800ba35b  mov     [rdi+28h], r14
0x1800ba35f  movups  xmm0, xmmword ptr [r15]
0x1800ba363  movdqu  xmmword ptr [rcx], xmm0
0x1800ba367  mov     eax, r13d
0x1800ba36a  jmp     loc_1800BA21D
```
