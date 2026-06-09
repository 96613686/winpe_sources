# GetFontInfFilename

- ea: `0x1800077dc`
- end: `0x180007933`
- name: `GetFontInfFilename`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180007adc`

## callees

- `0x18000626c`
- `0x1800077dc`
- `0x18000800c`
- `0x180008074`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000781c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007902`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000781c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007902`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007830`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007830`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007910`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007916`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800078e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800078e6`

## pseudocode

```c
DWORD __fastcall GetFontInfFilename(unsigned __int16 **a1, const wchar_t *a2)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rbx
  DWORD result; // eax
  __int64 v8; // r11
  HANDLE FileW; // rax
  HANDLE v10; // rax
  size_t v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  if ( !a2 || StringCchLengthW(a2, 0x104u, &v11) < 0 )
    return 87;
  ProcessHeap = GetProcessHeap();
  v5 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
  v6 = v5;
  if ( !v5 )
    return 14;
  if ( StringCchCopyW(v5, v11 + 1, a2) < 0 )
    goto LABEL_16;
  if ( v6[v8 - 1] == 92 )
    v6[v8 - 1] = 0;
  if ( v6[v8 - 8] != 92 )
  {
    if ( v6[v8 - 9] == 92 )
    {
      v6[v8 - 9] = 0;
    }
    else if ( v6[v8 - 11] == 92 )
    {
      *(_DWORD *)&v6[v8 - 10] = 3014702;
      v6[v8 - 8] = 0;
    }
  }
  if ( StringCchCatW(v6, 0x104u, L"\\inf\\fontsetup.inf") < 0
    || (FileW = CreateFileW(v6, 0, 1u, 0, 3u, 0, 0), FileW == (HANDLE)-1LL) )
  {
LABEL_16:
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v6);
    return GetLastError();
  }
  else
  {
    CloseHandle(FileW);
    result = 0;
    *a1 = v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800077dc  mov     rax, rsp
0x1800077df  mov     [rax+8], rbx
0x1800077e3  mov     [rax+18h], rsi
0x1800077e7  push    rdi
0x1800077e8  sub     rsp, 40h
0x1800077ec  mov     qword ptr [rax+10h], 0
0x1800077f4  mov     rdi, rdx
0x1800077f7  mov     rsi, rcx
0x1800077fa  test    rdx, rdx
0x1800077fd  jz      loc_18000791E
0x180007803  lea     r8, [rax+10h]; pcchLength
0x180007807  mov     edx, 104h; cchMax
0x18000780c  mov     rcx, rdi; psz
0x18000780f  call    StringCchLengthW
0x180007814  test    eax, eax
0x180007816  js      loc_18000791E
0x18000781c  call    cs:__imp_GetProcessHeap
0x180007822  mov     edx, 8; dwFlags
0x180007827  mov     r8d, 208h; dwBytes
0x18000782d  mov     rcx, rax; hHeap
0x180007830  call    cs:__imp_HeapAlloc
0x180007836  mov     rbx, rax
0x180007839  test    rax, rax
0x18000783c  jnz     short loc_180007846
0x18000783e  lea     eax, [rbx+0Eh]
0x180007841  jmp     loc_180007923
0x180007846  mov     r11, [rsp+48h+arg_8]
0x18000784b  mov     r8, rdi; unsigned __int16 *
0x18000784e  mov     rcx, rbx; unsigned __int16 *
0x180007851  lea     rdx, [r11+1]; unsigned __int64
0x180007855  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000785a  test    eax, eax
0x18000785c  js      loc_180007902
0x180007862  mov     cx, 5Ch ; '\'
0x180007866  cmp     [rbx+r11*2-2], cx
0x18000786c  jnz     short loc_180007876
0x18000786e  xor     eax, eax
0x180007870  mov     [rbx+r11*2-2], ax
0x180007876  cmp     [rbx+r11*2-10h], cx
0x18000787c  jz      short loc_1800078A9
0x18000787e  cmp     [rbx+r11*2-12h], cx
0x180007884  jnz     short loc_180007890
0x180007886  xor     eax, eax
0x180007888  mov     [rbx+r11*2-12h], ax
0x18000788e  jmp     short loc_1800078A9
0x180007890  cmp     [rbx+r11*2-16h], cx
0x180007896  jnz     short loc_1800078A9
0x180007898  xor     eax, eax
0x18000789a  mov     dword ptr [rbx+r11*2-14h], 2E002Eh
0x1800078a3  mov     [rbx+r11*2-10h], ax
0x1800078a9  lea     r8, aInfFontsetupIn; "\\inf\\fontsetup.inf"
0x1800078b0  mov     edx, 104h; cchDest
0x1800078b5  mov     rcx, rbx; pszDest
0x1800078b8  call    StringCchCatW
0x1800078bd  test    eax, eax
0x1800078bf  js      short loc_180007902
0x1800078c1  xor     r9d, r9d; lpSecurityAttributes
0x1800078c4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800078cd  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800078d5  xor     edx, edx; dwDesiredAccess
0x1800078d7  mov     rcx, rbx; lpFileName
0x1800078da  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800078e2  lea     r8d, [r9+1]; dwShareMode
0x1800078e6  call    cs:__imp_CreateFileW
0x1800078ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800078f0  jz      short loc_180007902
0x1800078f2  mov     rcx, rax; hObject
0x1800078f5  call    cs:__imp_CloseHandle
0x1800078fb  xor     eax, eax
0x1800078fd  mov     [rsi], rbx
0x180007900  jmp     short loc_180007923
0x180007902  call    cs:__imp_GetProcessHeap
0x180007908  mov     r8, rbx; lpMem
0x18000790b  xor     edx, edx; dwFlags
0x18000790d  mov     rcx, rax; hHeap
0x180007910  call    cs:__imp_HeapFree
0x180007916  call    cs:__imp_GetLastError
0x18000791c  jmp     short loc_180007923
0x18000791e  mov     eax, 57h ; 'W'
0x180007923  mov     rbx, [rsp+48h+arg_0]
0x180007928  mov     rsi, [rsp+48h+arg_10]
0x18000792d  add     rsp, 40h
0x180007931  pop     rdi
0x180007932  retn
```
