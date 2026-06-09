# CreateSampleFile

- ea: `0x18005e8dc`
- end: `0x18005ea73`
- name: `CreateSampleFile`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005e6d4`

## callees

- `0x18000bb04`
- `0x18000e558`
- `0x180012ea8`
- `0x1800259d4`
- `0x18005e8dc`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005e9aa`
- `KERNEL32!GetLastError` at `0x18005ea0b`
- `KERNEL32!GetLastError` at `0x18005e9aa`
- `KERNEL32!GetLastError` at `0x18005ea0b`
- `KERNEL32!CreateFileW` at `0x18005e996`
- `KERNEL32!CreateFileW` at `0x18005e996`
- `KERNEL32!WriteFile` at `0x18005ea01`
- `KERNEL32!WriteFile` at `0x18005ea01`
- `KERNEL32!SetFilePointer` at `0x18005e9e0`
- `KERNEL32!SetFilePointer` at `0x18005e9e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CreateSampleFile(__int64 a1, wchar_t *a2, const void *a3, DWORD a4)
{
  HANDLE FileW; // rax
  void *v8; // rbx
  char LastError; // r8
  _QWORD *v10; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-258h] BYREF
  HANDLE v12; // [rsp+48h] [rbp-250h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF

  if ( StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a1, a2) >= 0 )
  {
    FileW = CreateFileW(FileName, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
    v8 = FileW;
    v12 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
    }
    else
    {
      SetFilePointer(FileW, 0, 0, 2u);
      NumberOfBytesWritten = a4;
      if ( WriteFile(v8, a3, a4, &NumberOfBytesWritten, 0) )
        goto LABEL_13;
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
    }
    WPP_SF_Sd(v10[2], LastError);
LABEL_13:
    CHandle::~CHandle((CHandle *)&v12);
    return;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), a2);
}

```

## disassembly

```asm
0x18005e8dc  push    rbx
0x18005e8de  push    rbp
0x18005e8df  push    rsi
0x18005e8e0  push    rdi
0x18005e8e1  sub     rsp, 278h
0x18005e8e8  mov     rax, cs:__security_cookie
0x18005e8ef  xor     rax, rsp
0x18005e8f2  mov     [rsp+298h+var_38], rax
0x18005e8fa  mov     esi, r9d
0x18005e8fd  mov     rbp, r8
0x18005e900  mov     rdi, rdx
0x18005e903  mov     rbx, rcx
0x18005e906  mov     qword ptr [rsp+298h+dwCreationDisposition], rdx
0x18005e90b  mov     r9, rcx
0x18005e90e  lea     r8, aSS_3; "%s\\%s"
0x18005e915  mov     edx, 104h; unsigned __int64
0x18005e91a  lea     rcx, [rsp+298h+FileName]; wchar_t *
0x18005e91f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18005e924  test    eax, eax
0x18005e926  jns     short loc_18005E96B
0x18005e928  lea     rax, WPP_GLOBAL_Control
0x18005e92f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e936  cmp     rcx, rax
0x18005e939  jz      loc_18005EA57
0x18005e93f  test    byte ptr [rcx+1Ch], 1
0x18005e943  jz      loc_18005EA57
0x18005e949  mov     edx, 0Ch
0x18005e94e  mov     qword ptr [rsp+298h+dwCreationDisposition], rdi; wchar_t *
0x18005e953  mov     r9, rbx
0x18005e956  lea     r8, WPP_2cd602a534803ca5ae0a778439645e7d_Traceguids
0x18005e95d  mov     rcx, [rcx+10h]; LoggerHandle
0x18005e961  call    WPP_SF_SS
0x18005e966  jmp     loc_18005EA57
0x18005e96b  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x18005e974  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005e97c  mov     edi, 2
0x18005e981  mov     [rsp+298h+dwCreationDisposition], edi; dwCreationDisposition
0x18005e985  xor     r9d, r9d; lpSecurityAttributes
0x18005e988  mov     edx, 40000000h; dwDesiredAccess
0x18005e98d  lea     r8d, [rdi-1]; dwShareMode
0x18005e991  lea     rcx, [rsp+298h+FileName]; lpFileName
0x18005e996  call    cs:__imp_CreateFileW
0x18005e99c  mov     rbx, rax
0x18005e99f  mov     [rsp+298h+var_250], rax
0x18005e9a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005e9a8  jnz     short loc_18005E9D5
0x18005e9aa  call    cs:__imp_GetLastError
0x18005e9b0  mov     r8d, eax
0x18005e9b3  lea     rax, WPP_GLOBAL_Control
0x18005e9ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e9c1  cmp     rcx, rax
0x18005e9c4  jz      loc_18005EA4D
0x18005e9ca  test    byte ptr [rcx+1Ch], 1
0x18005e9ce  jz      short loc_18005EA4D
0x18005e9d0  lea     edx, [rdi+0Bh]
0x18005e9d3  jmp     short loc_18005EA32
0x18005e9d5  mov     r9d, edi; dwMoveMethod
0x18005e9d8  xor     r8d, r8d; lpDistanceToMoveHigh
0x18005e9db  xor     edx, edx; lDistanceToMove
0x18005e9dd  mov     rcx, rbx; hFile
0x18005e9e0  call    cs:__imp_SetFilePointer
0x18005e9e6  mov     [rsp+298h+NumberOfBytesWritten], esi
0x18005e9ea  mov     qword ptr [rsp+298h+dwCreationDisposition], 0; lpOverlapped
0x18005e9f3  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005e9f8  mov     r8d, esi; nNumberOfBytesToWrite
0x18005e9fb  mov     rdx, rbp; lpBuffer
0x18005e9fe  mov     rcx, rbx; hFile
0x18005ea01  call    cs:__imp_WriteFile
0x18005ea07  test    eax, eax
0x18005ea09  jnz     short loc_18005EA4D
0x18005ea0b  call    cs:__imp_GetLastError
0x18005ea11  mov     r8d, eax
0x18005ea14  lea     rax, WPP_GLOBAL_Control
0x18005ea1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ea22  cmp     rcx, rax
0x18005ea25  jz      short loc_18005EA4D
0x18005ea27  test    byte ptr [rcx+1Ch], 1
0x18005ea2b  jz      short loc_18005EA4D
0x18005ea2d  mov     edx, 0Eh
0x18005ea32  mov     [rsp+298h+dwCreationDisposition], r8d; char
0x18005ea37  lea     r9, [rsp+298h+FileName]
0x18005ea3c  lea     r8, WPP_2cd602a534803ca5ae0a778439645e7d_Traceguids
0x18005ea43  mov     rcx, [rcx+10h]; LoggerHandle
0x18005ea47  call    WPP_SF_Sd
0x18005ea4c  nop
0x18005ea4d  lea     rcx, [rsp+298h+var_250]; this
0x18005ea52  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18005ea57  mov     rcx, [rsp+298h+var_38]
0x18005ea5f  xor     rcx, rsp; StackCookie
0x18005ea62  call    __security_check_cookie
0x18005ea67  add     rsp, 278h
0x18005ea6e  pop     rdi
0x18005ea6f  pop     rsi
0x18005ea70  pop     rbp
0x18005ea71  pop     rbx
0x18005ea72  retn
```
