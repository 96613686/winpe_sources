# OpenPrint(ushort const *,void * *,ushort *,int)

- ea: `0x180021900`
- end: `0x180021956`
- name: `?OpenPrint@@YAHPEBGPEAPEAXPEAGH@Z`
- size: `86`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, LPHANDLE phPrinter, LPPRINTER_DEFAULTSW pDefault, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180041d50`
- `0x180041f10`

## callees

- `0x180021900`
- `0x18002fe84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002192d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002192d`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180021940`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180021940`

## pseudocode

```c
BOOL __fastcall OpenPrint(LPWSTR pPrinterName, LPHANDLE phPrinter, LPPRINTER_DEFAULTSW pDefault)
{
  if ( (unsigned __int8)IsClosePrinterPresent() )
    return OpenPrinterW(pPrinterName, phPrinter, pDefault);
  *phPrinter = 0;
  SetLastError(0x78u);
  return 0;
}

```

## disassembly

```asm
0x180021900  mov     [rsp+arg_0], rbx
0x180021905  mov     [rsp+arg_8], rsi
0x18002190a  push    rdi
0x18002190b  sub     rsp, 20h
0x18002190f  mov     rdi, r8
0x180021912  mov     rbx, rdx
0x180021915  mov     rsi, rcx
0x180021918  call    IsClosePrinterPresent
0x18002191d  test    al, al
0x18002191f  jnz     short loc_180021937
0x180021921  mov     ecx, 78h ; 'x'; dwErrCode
0x180021926  mov     qword ptr [rbx], 0
0x18002192d  call    cs:__imp_SetLastError
0x180021933  xor     eax, eax
0x180021935  jmp     short loc_180021946
0x180021937  mov     r8, rdi; pDefault
0x18002193a  mov     rdx, rbx; phPrinter
0x18002193d  mov     rcx, rsi; pPrinterName
0x180021940  call    cs:__imp_OpenPrinterW
0x180021946  mov     rbx, [rsp+28h+arg_0]
0x18002194b  mov     rsi, [rsp+28h+arg_8]
0x180021950  add     rsp, 20h
0x180021954  pop     rdi
0x180021955  retn
```
