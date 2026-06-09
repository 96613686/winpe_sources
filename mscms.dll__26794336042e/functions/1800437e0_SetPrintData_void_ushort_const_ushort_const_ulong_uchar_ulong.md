# SetPrintData(void *,ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x1800437e0`
- end: `0x180043875`
- name: `?SetPrintData@@YAKPEAXPEBG1KPEAEK@Z`
- size: `149`
- prototype: `unsigned int __fastcall(HANDLE hPrinter, LPCWSTR pKeyName, LPCWSTR pValueName, DWORD Type, LPBYTE, DWORD)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002fc90`
- `0x1800437e0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004380e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004380e`
- `ext-ms-win-printer-winspool-l1-1-1!SetPrinterDataExW` at `0x180043864`
- `ext-ms-win-printer-winspool-l1-1-1!SetPrinterDataExW` at `0x180043864`
- `ext-ms-win-printer-winspool-l1-1-1!DeletePrinterDataExW` at `0x18004382f`
- `ext-ms-win-printer-winspool-l1-1-1!DeletePrinterDataExW` at `0x18004382f`

## pseudocode

```c
DWORD __fastcall SetPrintData(
        HANDLE hPrinter,
        LPCWSTR pKeyName,
        LPCWSTR pValueName,
        DWORD Type,
        LPBYTE pData,
        DWORD cbData)
{
  if ( Type == 7 && !lstrcmpiW(pValueName, gszFiles) && cbData <= 4 )
  {
    if ( (unsigned __int8)IsDeletePrinterDataExWPresent() )
      return DeletePrinterDataExW(hPrinter, pKeyName, pValueName);
    return 120;
  }
  if ( !(unsigned __int8)IsDeletePrinterDataExWPresent() )
    return 120;
  return SetPrinterDataExW(hPrinter, pKeyName, pValueName, Type, pData, cbData);
}

```

## disassembly

```asm
0x1800437e0  push    rbx
0x1800437e2  push    rbp
0x1800437e3  push    rsi
0x1800437e4  push    rdi
0x1800437e5  push    r14
0x1800437e7  sub     rsp, 30h
0x1800437eb  mov     edi, [rsp+58h+arg_28]
0x1800437f2  mov     r14d, r9d
0x1800437f5  mov     rbx, r8
0x1800437f8  mov     rsi, rdx
0x1800437fb  mov     rbp, rcx
0x1800437fe  cmp     r9d, 7
0x180043802  jnz     short loc_180043837
0x180043804  lea     rdx, gszFiles; "Files"
0x18004380b  mov     rcx, rbx; lpString1
0x18004380e  call    cs:__imp_lstrcmpiW
0x180043814  test    eax, eax
0x180043816  jnz     short loc_180043837
0x180043818  cmp     edi, 4
0x18004381b  ja      short loc_180043837
0x18004381d  call    IsDeletePrinterDataExWPresent
0x180043822  test    al, al
0x180043824  jz      short loc_180043840
0x180043826  mov     r8, rbx; pValueName
0x180043829  mov     rdx, rsi; pKeyName
0x18004382c  mov     rcx, rbp; hPrinter
0x18004382f  call    cs:__imp_DeletePrinterDataExW
0x180043835  jmp     short loc_18004386A
0x180043837  call    IsDeletePrinterDataExWPresent
0x18004383c  test    al, al
0x18004383e  jnz     short loc_180043847
0x180043840  mov     eax, 78h ; 'x'
0x180043845  jmp     short loc_18004386A
0x180043847  mov     rax, [rsp+58h+arg_20]
0x18004384f  mov     r9d, r14d; Type
0x180043852  mov     [rsp+58h+cbData], edi; cbData
0x180043856  mov     r8, rbx; pValueName
0x180043859  mov     rdx, rsi; pKeyName
0x18004385c  mov     [rsp+58h+pData], rax; pData
0x180043861  mov     rcx, rbp; hPrinter
0x180043864  call    cs:__imp_SetPrinterDataExW
0x18004386a  add     rsp, 30h
0x18004386e  pop     r14
0x180043870  pop     rdi
0x180043871  pop     rsi
0x180043872  pop     rbp
0x180043873  pop     rbx
0x180043874  retn
```
