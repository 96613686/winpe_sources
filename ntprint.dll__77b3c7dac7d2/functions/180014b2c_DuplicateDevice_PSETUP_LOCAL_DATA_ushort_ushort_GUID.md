# DuplicateDevice(_PSETUP_LOCAL_DATA *,ushort *,ushort *,_GUID *)

- ea: `0x180014b2c`
- end: `0x180014c3e`
- name: `?DuplicateDevice@@YAHPEAU_PSETUP_LOCAL_DATA@@PEAG1PEAU_GUID@@@Z`
- size: `274`
- prototype: `int(struct _PSETUP_LOCAL_DATA *, unsigned __int16 *, unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180013804`

## callees

- `0x180014b2c`
- `0x180015904`
- `0x18001598c`
- `0x180016ce4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c1d`
- `KERNEL32!lstrcmpiW` at `0x180014b9e`
- `KERNEL32!lstrcmpiW` at `0x180014b9e`
- `WINSPOOL!OpenPrinterW` at `0x180014be2`
- `WINSPOOL!OpenPrinterW` at `0x180014be2`
- `WINSPOOL!ClosePrinter` at `0x180014c13`
- `WINSPOOL!ClosePrinter` at `0x180014c13`

## pseudocode

```c
__int64 __fastcall DuplicateDevice(struct _PSETUP_LOCAL_DATA *a1, unsigned __int16 *a2, BYTE *a3, BYTE *a4)
{
  const WCHAR *v4; // r12
  unsigned int v7; // r14d
  unsigned int v9; // eax
  unsigned int v10; // edi
  struct _PRINTER_INFO_2W *v11; // rbx
  HANDLE phPrinter; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+A0h] [rbp+40h] BYREF
  LPBYTE pData; // [rsp+B0h] [rbp+50h]

  pData = a3;
  v4 = (const WCHAR *)*((_QWORD *)a1 + 1);
  hMem = 0;
  v16 = 0;
  phPrinter = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v7 = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  if ( PrinterInfo2s((struct _PRINTER_INFO_2W **)&hMem, &v16) )
  {
    v9 = v16;
    v10 = 0;
    v11 = (struct _PRINTER_INFO_2W *)hMem;
    if ( v16 )
    {
      while ( lstrcmpiW(v4, v11->pDriverName) || !PrinterGoingToPort(v11, a2) )
      {
        v9 = v16;
        ++v10;
        ++v11;
        if ( v10 >= v16 )
          goto LABEL_8;
      }
      v9 = v16;
    }
LABEL_8:
    if ( v10 != v9 )
    {
      v7 = 1;
      if ( OpenPrinterW(v11->pPrinterName, &phPrinter, &pDefault) )
      {
        SetPnPInfoForPrinter(phPrinter, pData, *((LPBYTE *)a1 + 4), *((LPBYTE *)a1 + 5), *((LPBYTE *)a1 + 6), a4);
        ClosePrinter(phPrinter);
      }
    }
  }
  LocalFree(hMem);
  return v7;
}

```

## disassembly

```asm
0x180014b2c  mov     [rsp-38h+arg_8], rbx
0x180014b31  mov     [rsp-38h+pData], r8
0x180014b36  push    rbp
0x180014b37  push    rsi
0x180014b38  push    rdi
0x180014b39  push    r12
0x180014b3b  push    r13
0x180014b3d  push    r14
0x180014b3f  push    r15
0x180014b41  mov     rbp, rsp
0x180014b44  sub     rsp, 60h
0x180014b48  mov     r12, [rcx+8]
0x180014b4c  xor     ebx, ebx
0x180014b4e  mov     r15, rdx
0x180014b51  mov     [rbp+hMem], rbx
0x180014b55  mov     rsi, rcx
0x180014b58  mov     [rbp+arg_0], ebx
0x180014b5b  xorps   xmm0, xmm0
0x180014b5e  mov     [rbp+phPrinter], rbx
0x180014b62  lea     rdx, [rbp+arg_0]; unsigned int *
0x180014b66  mov     qword ptr [rbp+pDefault.DesiredAccess], 0F000Ch
0x180014b6e  lea     rcx, [rbp+hMem]; struct _PRINTER_INFO_2W **
0x180014b72  mov     r14d, ebx
0x180014b75  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x180014b7a  mov     r13, r9
0x180014b7d  call    ?PrinterInfo2s@@YAHPEAPEAU_PRINTER_INFO_2W@@PEAK@Z; PrinterInfo2s(_PRINTER_INFO_2W * *,ulong *)
0x180014b82  test    eax, eax
0x180014b84  jz      loc_180014C19
0x180014b8a  mov     eax, [rbp+arg_0]
0x180014b8d  mov     edi, ebx
0x180014b8f  mov     rbx, [rbp+hMem]
0x180014b93  test    eax, eax
0x180014b95  jz      short loc_180014BCC
0x180014b97  mov     rdx, [rbx+20h]; lpString2
0x180014b9b  mov     rcx, r12; lpString1
0x180014b9e  call    cs:__imp_lstrcmpiW
0x180014ba4  test    eax, eax
0x180014ba6  jnz     short loc_180014BB7
0x180014ba8  mov     rdx, r15; unsigned __int16 *
0x180014bab  mov     rcx, rbx; struct _PRINTER_INFO_2W *
0x180014bae  call    ?PrinterGoingToPort@@YAHPEAU_PRINTER_INFO_2W@@PEBG@Z; PrinterGoingToPort(_PRINTER_INFO_2W *,ushort const *)
0x180014bb3  test    eax, eax
0x180014bb5  jnz     short loc_180014BC9
0x180014bb7  mov     eax, [rbp+arg_0]
0x180014bba  inc     edi
0x180014bbc  add     rbx, 88h
0x180014bc3  cmp     edi, eax
0x180014bc5  jb      short loc_180014B97
0x180014bc7  jmp     short loc_180014BCC
0x180014bc9  mov     eax, [rbp+arg_0]
0x180014bcc  cmp     edi, eax
0x180014bce  jz      short loc_180014C19
0x180014bd0  mov     rcx, [rbx+8]; pPrinterName
0x180014bd4  lea     r8, [rbp+pDefault]; pDefault
0x180014bd8  lea     rdx, [rbp+phPrinter]; phPrinter
0x180014bdc  mov     r14d, 1
0x180014be2  call    cs:__imp_OpenPrinterW
0x180014be8  test    eax, eax
0x180014bea  jz      short loc_180014C19
0x180014bec  mov     rdx, [rsi+30h]
0x180014bf0  mov     r9, [rsi+28h]; LPBYTE
0x180014bf4  mov     r8, [rsi+20h]; LPBYTE
0x180014bf8  mov     rcx, [rbp+phPrinter]; hPrinter
0x180014bfc  mov     [rsp+60h+var_38], r13; LPBYTE
0x180014c01  mov     [rsp+60h+var_40], rdx; LPBYTE
0x180014c06  mov     rdx, [rbp+pData]; pData
0x180014c0a  call    SetPnPInfoForPrinter
0x180014c0f  mov     rcx, [rbp+phPrinter]; hPrinter
0x180014c13  call    cs:__imp_ClosePrinter
0x180014c19  mov     rcx, [rbp+hMem]; hMem
0x180014c1d  call    cs:__imp_LocalFree
0x180014c23  mov     rbx, [rsp+60h+arg_8]
0x180014c2b  mov     eax, r14d
0x180014c2e  add     rsp, 60h
0x180014c32  pop     r15
0x180014c34  pop     r14
0x180014c36  pop     r13
0x180014c38  pop     r12
0x180014c3a  pop     rdi
0x180014c3b  pop     rsi
0x180014c3c  pop     rbp
0x180014c3d  retn
```
