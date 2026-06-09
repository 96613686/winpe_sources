# CNovInterDlg::RefreshStatusBar(int,int,uint)

- ea: `0x140023f14`
- end: `0x1400240f7`
- name: `?RefreshStatusBar@CNovInterDlg@@AEAAJHHI@Z`
- size: `483`
- prototype: `__int64 __fastcall(CNovInterDlg *__hidden this, int, int, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x14001fca0`
- `0x140022c68`
- `0x1400244dc`
- `0x140024734`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x140023f14`
- `0x140034ce4`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140023f85`
- `KERNEL32!GetModuleHandleW` at `0x140024062`
- `KERNEL32!GetModuleHandleW` at `0x140023f85`
- `KERNEL32!GetModuleHandleW` at `0x140024062`
- `GDI32!DeleteObject` at `0x1400240ca`
- `GDI32!DeleteObject` at `0x1400240ca`
- `USER32!SendMessageW` at `0x14002404d`
- `USER32!SendMessageW` at `0x1400240bb`
- `USER32!SendMessageW` at `0x14002404d`
- `USER32!SendMessageW` at `0x1400240bb`
- `USER32!LoadStringW` at `0x140023fa3`
- `USER32!LoadStringW` at `0x140023fa3`
- `USER32!LoadImageW` at `0x14002408a`
- `USER32!LoadImageW` at `0x14002408a`

## pseudocode

```c
__int64 __fastcall CNovInterDlg::RefreshStatusBar(HWND *this, UINT a2, int a3, unsigned int a4)
{
  unsigned int v8; // edi
  HMODULE ModuleHandleW; // rax
  CEventLogger *v10; // rcx
  unsigned int v11; // r9d
  signed int v12; // eax
  CEventLogger *v13; // rcx
  HMODULE v14; // rax
  HANDLE ImageW; // rax
  void *v16; // rbx
  WCHAR Buffer[1024]; // [rsp+30h] [rbp-1038h] BYREF
  unsigned __int16 lParam[1024]; // [rsp+830h] [rbp-838h] BYREF

  v8 = 0;
  memset_0(lParam, 0, sizeof(lParam));
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( this[22] )
  {
    if ( a2 )
    {
      ModuleHandleW = GetModuleHandleW(0);
      if ( !LoadStringW(ModuleHandleW, a2, Buffer, 1024) )
      {
        v11 = 4697;
LABEL_5:
        CEventLogger::LogError(
          v10,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
          v11,
          L"CNovInterDlg::RefreshStatusBar",
          0);
        return (unsigned int)-2147467259;
      }
      v12 = StringCchPrintfW(lParam, 0x400u, Buffer, a4);
      v8 = v12;
      if ( v12 < 0 )
      {
        CEventLogger::LogError(
          v13,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
          0x125Fu,
          L"CNovInterDlg::RefreshStatusBar",
          v12);
        return v8;
      }
      SendMessageW(this[22], 0x40Bu, 0, (LPARAM)lParam);
    }
    if ( !a3 )
      return v8;
    v14 = GetModuleHandleW(0);
    ImageW = LoadImageW(v14, (LPCWSTR)(unsigned __int16)a3, 1u, 16, 16, 0x20u);
    v16 = ImageW;
    if ( ImageW )
    {
      SendMessageW(this[22], 0x40Fu, 0, (LPARAM)ImageW);
      DeleteObject(v16);
      return v8;
    }
    v11 = 4726;
    goto LABEL_5;
  }
  return v8;
}

```

## disassembly

```asm
0x140023f14  push    rbx
0x140023f16  push    rbp
0x140023f17  push    rsi
0x140023f18  push    rdi
0x140023f19  push    r14
0x140023f1b  mov     eax, 1040h
0x140023f20  call    _alloca_probe
0x140023f25  sub     rsp, rax
0x140023f28  mov     rax, cs:__security_cookie
0x140023f2f  xor     rax, rsp
0x140023f32  mov     [rsp+1068h+var_38], rax
0x140023f3a  mov     ebp, r8d
0x140023f3d  mov     ebx, edx
0x140023f3f  mov     rsi, rcx
0x140023f42  xor     edx, edx; Val
0x140023f44  mov     r8d, 800h; Size
0x140023f4a  lea     rcx, [rsp+1068h+lParam]; void *
0x140023f52  mov     r14d, r9d
0x140023f55  xor     edi, edi
0x140023f57  call    memset_0
0x140023f5c  xor     edx, edx; Val
0x140023f5e  lea     rcx, [rsp+1068h+Buffer]; void *
0x140023f63  mov     r8d, 800h; Size
0x140023f69  call    memset_0
0x140023f6e  cmp     [rsi+0B0h], rdi
0x140023f75  jz      loc_1400240D6
0x140023f7b  test    ebx, ebx
0x140023f7d  jz      loc_140024059
0x140023f83  xor     ecx, ecx; lpModuleName
0x140023f85  call    cs:__imp_GetModuleHandleW
0x140023f8c  nop     dword ptr [rax+rax+00h]
0x140023f91  mov     edi, 400h
0x140023f96  lea     r8, [rsp+1068h+Buffer]; lpBuffer
0x140023f9b  mov     rcx, rax; hInstance
0x140023f9e  mov     r9d, edi; cchBufferMax
0x140023fa1  mov     edx, ebx; uID
0x140023fa3  call    cs:__imp_LoadStringW
0x140023faa  nop     dword ptr [rax+rax+00h]
0x140023faf  test    eax, eax
0x140023fb1  jnz     short loc_140023FEA
0x140023fb3  mov     r9d, 1259h; unsigned int
0x140023fb9  lea     rax, aCnovinterdlgRe; "CNovInterDlg::RefreshStatusBar"
0x140023fc0  mov     [rsp+1068h+fuLoad], 0; unsigned int
0x140023fc8  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x140023fcf  mov     qword ptr [rsp+1068h+cy], rax; unsigned __int16 *
0x140023fd4  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140023fdb  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140023fe0  mov     edi, 80004005h
0x140023fe5  jmp     loc_1400240D6
0x140023fea  mov     r9d, r14d
0x140023fed  lea     r8, [rsp+1068h+Buffer]; unsigned __int16 *
0x140023ff2  mov     rdx, rdi; unsigned __int64
0x140023ff5  lea     rcx, [rsp+1068h+lParam]; unsigned __int16 *
0x140023ffd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140024002  mov     edi, eax
0x140024004  test    eax, eax
0x140024006  jns     short loc_140024036
0x140024008  mov     [rsp+1068h+fuLoad], eax; unsigned int
0x14002400c  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x140024013  lea     rax, aCnovinterdlgRe; "CNovInterDlg::RefreshStatusBar"
0x14002401a  mov     r9d, 125Fh; unsigned int
0x140024020  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140024027  mov     qword ptr [rsp+1068h+cy], rax; unsigned __int16 *
0x14002402c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140024031  jmp     loc_1400240D6
0x140024036  mov     rcx, [rsi+0B0h]; hWnd
0x14002403d  lea     r9, [rsp+1068h+lParam]; lParam
0x140024045  xor     r8d, r8d; wParam
0x140024048  mov     edx, 40Bh; Msg
0x14002404d  call    cs:__imp_SendMessageW
0x140024054  nop     dword ptr [rax+rax+00h]
0x140024059  test    ebp, ebp
0x14002405b  jz      short loc_1400240D6
0x14002405d  xor     ecx, ecx; lpModuleName
0x14002405f  movzx   ebx, bp
0x140024062  call    cs:__imp_GetModuleHandleW
0x140024069  nop     dword ptr [rax+rax+00h]
0x14002406e  mov     r9d, 10h; cx
0x140024074  mov     [rsp+1068h+fuLoad], 20h ; ' '; fuLoad
0x14002407c  mov     rcx, rax; hInst
0x14002407f  mov     [rsp+1068h+cy], r9d; cy
0x140024084  mov     edx, ebx; name
0x140024086  lea     r8d, [r9-0Fh]; type
0x14002408a  call    cs:__imp_LoadImageW
0x140024091  nop     dword ptr [rax+rax+00h]
0x140024096  mov     rbx, rax
0x140024099  test    rax, rax
0x14002409c  jnz     short loc_1400240A9
0x14002409e  mov     r9d, 1276h
0x1400240a4  jmp     loc_140023FB9
0x1400240a9  mov     rcx, [rsi+0B0h]; hWnd
0x1400240b0  mov     r9, rbx; lParam
0x1400240b3  xor     r8d, r8d; wParam
0x1400240b6  mov     edx, 40Fh; Msg
0x1400240bb  call    cs:__imp_SendMessageW
0x1400240c2  nop     dword ptr [rax+rax+00h]
0x1400240c7  mov     rcx, rbx; ho
0x1400240ca  call    cs:__imp_DeleteObject
0x1400240d1  nop     dword ptr [rax+rax+00h]
0x1400240d6  mov     eax, edi
0x1400240d8  mov     rcx, [rsp+1068h+var_38]
0x1400240e0  xor     rcx, rsp; StackCookie
0x1400240e3  call    __security_check_cookie
0x1400240e8  add     rsp, 1040h
0x1400240ef  pop     r14
0x1400240f1  pop     rdi
0x1400240f2  pop     rsi
0x1400240f3  pop     rbp
0x1400240f4  pop     rbx
0x1400240f5  retn
```
