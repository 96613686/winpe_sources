# DiskQuotaMsgBox(HWND__ *,uint,uint,uint)

- ea: `0x18001ab24`
- end: `0x18001abb0`
- name: `?DiskQuotaMsgBox@@YAHPEAUHWND__@@III@Z`
- size: `140`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned int, unsigned int)`
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006c54`
- `0x18000b52c`
- `0x18000c01c`
- `0x18000c8c4`
- `0x18000d138`
- `0x180013d44`
- `0x1800170dc`
- `0x1800180a8`
- `0x1800196b0`
- `0x18001d0cb`
- `0x18001d536`
- `0x18001da4e`
- `0x18001db06`

## callees

- `0x180019d24`
- `0x180019ee0`

## import_xrefs

- `USER32!MessageBoxW` at `0x18001ab81`
- `USER32!MessageBoxW` at `0x18001ab81`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiskQuotaMsgBox(HWND hWnd, DWORD a2, __int64 a3, int a4)
{
  unsigned int v7; // ebx
  _BYTE v9[8]; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR *v10; // [rsp+28h] [rbp-20h]
  _BYTE v11[8]; // [rsp+30h] [rbp-18h] BYREF
  LPCWSTR *v12; // [rsp+38h] [rbp-10h]

  CString::CString((CString *)v11, g_hInstDll, 0x9E53u);
  CString::CString((CString *)v9, g_hInstDll, a2);
  v7 = MessageBoxW(hWnd, *v10, *v12, a4 | 0x10000);
  CString::~CString((CString *)v9);
  CString::~CString((CString *)v11);
  return v7;
}

```

## disassembly

```asm
0x18001ab24  mov     [rsp+arg_0], rbx
0x18001ab29  mov     [rsp+arg_8], rsi
0x18001ab2e  push    rdi
0x18001ab2f  sub     rsp, 40h
0x18001ab33  mov     edi, r9d
0x18001ab36  mov     ebx, edx
0x18001ab38  mov     rsi, rcx
0x18001ab3b  mov     r8d, 9E53h; int
0x18001ab41  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18001ab48  lea     rcx, [rsp+48h+var_18]; this
0x18001ab4d  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x18001ab52  nop
0x18001ab53  mov     r8d, ebx; int
0x18001ab56  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18001ab5d  lea     rcx, [rsp+48h+var_28]; this
0x18001ab62  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x18001ab67  bts     edi, 10h
0x18001ab6b  mov     r9d, edi; uType
0x18001ab6e  mov     r8, [rsp+48h+var_10]
0x18001ab73  mov     r8, [r8]; lpCaption
0x18001ab76  mov     rdx, [rsp+48h+var_20]
0x18001ab7b  mov     rdx, [rdx]; lpText
0x18001ab7e  mov     rcx, rsi; hWnd
0x18001ab81  call    cs:__imp_MessageBoxW
0x18001ab87  mov     ebx, eax
0x18001ab89  lea     rcx, [rsp+48h+var_28]; this
0x18001ab8e  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001ab93  nop
0x18001ab94  lea     rcx, [rsp+48h+var_18]; this
0x18001ab99  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001ab9e  mov     eax, ebx
0x18001aba0  mov     rbx, [rsp+48h+arg_0]
0x18001aba5  mov     rsi, [rsp+48h+arg_8]
0x18001abaa  add     rsp, 40h
0x18001abae  pop     rdi
0x18001abaf  retn
```
