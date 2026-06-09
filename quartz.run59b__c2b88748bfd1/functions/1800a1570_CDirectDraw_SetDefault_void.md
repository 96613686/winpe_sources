# CDirectDraw::SetDefault(void)

- ea: `0x1800a1570`
- end: `0x1800a16f3`
- name: `?SetDefault@CDirectDraw@@UEAAJXZ`
- size: `387`
- prototype: `__int64 __fastcall(CDirectDraw *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004924`
- `0x1800388a0`

## import_xrefs

- `KERNEL32!WriteProfileStringW` at `0x1800a15fb`
- `KERNEL32!WriteProfileStringW` at `0x1800a1635`
- `KERNEL32!WriteProfileStringW` at `0x1800a166f`
- `KERNEL32!WriteProfileStringW` at `0x1800a16a9`
- `KERNEL32!WriteProfileStringW` at `0x1800a15fb`
- `KERNEL32!WriteProfileStringW` at `0x1800a1635`
- `KERNEL32!WriteProfileStringW` at `0x1800a166f`
- `KERNEL32!WriteProfileStringW` at `0x1800a16a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800a16b8`
- `KERNEL32!LeaveCriticalSection` at `0x1800a16c7`
- `KERNEL32!LeaveCriticalSection` at `0x1800a16b8`
- `KERNEL32!LeaveCriticalSection` at `0x1800a16c7`
- `KERNEL32!EnterCriticalSection` at `0x1800a159c`
- `KERNEL32!EnterCriticalSection` at `0x1800a15bb`
- `KERNEL32!EnterCriticalSection` at `0x1800a159c`
- `KERNEL32!EnterCriticalSection` at `0x1800a15bb`

## pseudocode

```c
__int64 __fastcall CDirectDraw::SetDefault(CDirectDraw *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  WCHAR String[128]; // [rsp+20h] [rbp-138h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 116);
  EnterCriticalSection(v1);
  EnterCriticalSection((LPCRITICAL_SECTION)(((unsigned __int64)this + 32) & -(__int64)(this != 0)));
  StringCchPrintfW(String, 0x80u, L"%d", *((unsigned int *)this + 256));
  WriteProfileStringW(L"DrawDib", L"AMovieDraw", String);
  StringCchPrintfW(String, 0x80u, L"%d", *((unsigned int *)this + 269));
  WriteProfileStringW(L"DrawDib", L"ScanLine", String);
  StringCchPrintfW(String, 0x80u, L"%d", *((unsigned int *)this + 270));
  WriteProfileStringW(L"DrawDib", L"Stretch", String);
  StringCchPrintfW(String, 0x80u, L"%d", *((unsigned int *)this + 271));
  WriteProfileStringW(L"DrawDib", L"FullScreen", String);
  LeaveCriticalSection((LPCRITICAL_SECTION)(((unsigned __int64)this + 32) & -(__int64)(this != 0)));
  LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x1800a1570  push    rbx
0x1800a1572  push    rsi
0x1800a1573  push    rdi
0x1800a1574  push    r14
0x1800a1576  sub     rsp, 138h
0x1800a157d  mov     rax, cs:__security_cookie
0x1800a1584  xor     rax, rsp
0x1800a1587  mov     [rsp+158h+var_38], rax
0x1800a158f  mov     rsi, [rcx+3A0h]
0x1800a1596  mov     rdi, rcx
0x1800a1599  mov     rcx, rsi; lpCriticalSection
0x1800a159c  call    cs:__imp_EnterCriticalSection
0x1800a15a3  nop     dword ptr [rax+rax+00h]
0x1800a15a8  lea     rcx, [rdi+20h]
0x1800a15ac  mov     rax, rdi
0x1800a15af  neg     rax
0x1800a15b2  sbb     rbx, rbx
0x1800a15b5  and     rbx, rcx
0x1800a15b8  mov     rcx, rbx; lpCriticalSection
0x1800a15bb  call    cs:__imp_EnterCriticalSection
0x1800a15c2  nop     dword ptr [rax+rax+00h]
0x1800a15c7  mov     r9d, [rdi+400h]
0x1800a15ce  lea     r8, aD; "%d"
0x1800a15d5  mov     r14d, 80h
0x1800a15db  lea     rcx, [rsp+158h+String]; Buffer
0x1800a15e0  mov     edx, r14d; unsigned __int64
0x1800a15e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a15e8  lea     r8, [rsp+158h+String]; lpString
0x1800a15ed  lea     rdx, aAmoviedraw; "AMovieDraw"
0x1800a15f4  lea     rcx, aDrawdib; "DrawDib"
0x1800a15fb  call    cs:__imp_WriteProfileStringW
0x1800a1602  nop     dword ptr [rax+rax+00h]
0x1800a1607  mov     r9d, [rdi+434h]
0x1800a160e  lea     r8, aD; "%d"
0x1800a1615  mov     edx, r14d; unsigned __int64
0x1800a1618  lea     rcx, [rsp+158h+String]; Buffer
0x1800a161d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1622  lea     r8, [rsp+158h+String]; lpString
0x1800a1627  lea     rdx, aScanline; "ScanLine"
0x1800a162e  lea     rcx, aDrawdib; "DrawDib"
0x1800a1635  call    cs:__imp_WriteProfileStringW
0x1800a163c  nop     dword ptr [rax+rax+00h]
0x1800a1641  mov     r9d, [rdi+438h]
0x1800a1648  lea     r8, aD; "%d"
0x1800a164f  mov     edx, r14d; unsigned __int64
0x1800a1652  lea     rcx, [rsp+158h+String]; Buffer
0x1800a1657  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a165c  lea     r8, [rsp+158h+String]; lpString
0x1800a1661  lea     rdx, aStretch; "Stretch"
0x1800a1668  lea     rcx, aDrawdib; "DrawDib"
0x1800a166f  call    cs:__imp_WriteProfileStringW
0x1800a1676  nop     dword ptr [rax+rax+00h]
0x1800a167b  mov     r9d, [rdi+43Ch]
0x1800a1682  lea     r8, aD; "%d"
0x1800a1689  mov     edx, r14d; unsigned __int64
0x1800a168c  lea     rcx, [rsp+158h+String]; Buffer
0x1800a1691  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1696  lea     r8, [rsp+158h+String]; lpString
0x1800a169b  lea     rdx, aFullscreen; "FullScreen"
0x1800a16a2  lea     rcx, aDrawdib; "DrawDib"
0x1800a16a9  call    cs:__imp_WriteProfileStringW
0x1800a16b0  nop     dword ptr [rax+rax+00h]
0x1800a16b5  mov     rcx, rbx; lpCriticalSection
0x1800a16b8  call    cs:__imp_LeaveCriticalSection
0x1800a16bf  nop     dword ptr [rax+rax+00h]
0x1800a16c4  mov     rcx, rsi; lpCriticalSection
0x1800a16c7  call    cs:__imp_LeaveCriticalSection
0x1800a16ce  nop     dword ptr [rax+rax+00h]
0x1800a16d3  xor     eax, eax
0x1800a16d5  mov     rcx, [rsp+158h+var_38]
0x1800a16dd  xor     rcx, rsp; StackCookie
0x1800a16e0  call    __security_check_cookie
0x1800a16e5  add     rsp, 138h
0x1800a16ec  pop     r14
0x1800a16ee  pop     rdi
0x1800a16ef  pop     rsi
0x1800a16f0  pop     rbx
0x1800a16f1  retn
```
