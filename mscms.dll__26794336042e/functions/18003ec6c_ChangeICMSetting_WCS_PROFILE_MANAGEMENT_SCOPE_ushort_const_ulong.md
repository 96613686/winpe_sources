# ChangeICMSetting(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong)

- ea: `0x18003ec6c`
- end: `0x18003ef0d`
- name: `?ChangeICMSetting@@YAXW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGK@Z`
- size: `673`
- prototype: `void __fastcall(enum WCS_PROFILE_MANAGEMENT_SCOPE, WCHAR *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180023a78`
- `0x1800412a4`

## callees

- `0x18000b828`
- `0x18000be44`
- `0x18002fce4`
- `0x18002fe84`
- `0x18003ec6c`

## import_xrefs

- `ext-ms-win-printer-winspool-l1-1-0!SetPrinterW` at `0x18003eece`
- `ext-ms-win-printer-winspool-l1-1-0!SetPrinterW` at `0x18003eece`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18003ecec`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x18003ecec`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x18003ed31`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x18003eda7`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x18003ee1e`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x18003ee8a`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x18003ed31`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x18003eda7`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x18003ee1e`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetPrinterW` at `0x18003ee8a`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x18003eed8`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x18003eed8`

## pseudocode

```c
void __fastcall ChangeICMSetting(enum WCS_PROFILE_MANAGEMENT_SCOPE a1, WCHAR *a2, int a3)
{
  DWORD v6; // esi
  void *v7; // rbx
  BYTE *v8; // rdi
  BYTE *v9; // r8
  _PRINTER_DEFAULTSW pDefault; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbBuf; // [rsp+70h] [rbp+20h] BYREF
  HANDLE phPrinter; // [rsp+88h] [rbp+38h] BYREF

  *(&pDefault.DesiredAccess + 1) = 0;
  phPrinter = 0;
  cbBuf = 0;
  pDefault.DesiredAccess = a1 != WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE ? 8 : 12;
  *(_OWORD *)&pDefault.pDatatype = 0;
  if ( !(unsigned __int8)IsClosePrinterPresent()
    || !(unsigned __int8)IsClosePrinterPresent()
    || !(unsigned __int8)IsSetPrinterWPresent()
    || !OpenPrinterW(a2, &phPrinter, &pDefault) )
  {
    return;
  }
  v6 = 8;
  if ( a1 )
  {
    v8 = 0;
    v7 = (void *)MemAlloc(8);
    if ( v7 )
    {
      v6 = 9;
      if ( GetPrinterW(phPrinter, 9u, (LPBYTE)v7, 8u, &cbBuf) && *(_QWORD *)v7 )
      {
        if ( a3 != 1 && a3 != 2 )
          goto LABEL_32;
        *(_DWORD *)(*(_QWORD *)v7 + 72LL) |= 0x800000u;
        *(_DWORD *)(*(_QWORD *)v7 + 188LL) = (a3 == 2) + 1;
      }
      else
      {
        MemFree(v7);
        v7 = (void *)MemAlloc(cbBuf);
        if ( !v7 || !GetPrinterW(phPrinter, 9u, (LPBYTE)v7, cbBuf, &cbBuf) || !*(_QWORD *)v7 || a3 != 1 && a3 != 2 )
          goto LABEL_32;
        *(_DWORD *)(*(_QWORD *)v7 + 72LL) |= 0x800000u;
        *(_DWORD *)(*(_QWORD *)v7 + 188LL) = (a3 == 2) + 1;
      }
      v9 = (BYTE *)v7;
LABEL_31:
      SetPrinterW(phPrinter, v6, v9, 0);
    }
  }
  else
  {
    v7 = 0;
    v8 = (BYTE *)MemAlloc(8);
    if ( v8 )
    {
      if ( GetPrinterW(phPrinter, 8u, v8, 8u, &cbBuf) && *(_QWORD *)v8 )
      {
        if ( a3 != 1 && a3 != 2 )
          goto LABEL_32;
        *(_DWORD *)(*(_QWORD *)v8 + 72LL) |= 0x800000u;
        v9 = v8;
        *(_DWORD *)(*(_QWORD *)v8 + 188LL) = (a3 == 2) + 1;
      }
      else
      {
        MemFree(v8);
        v8 = (BYTE *)MemAlloc(cbBuf);
        if ( v8 || !GetPrinterW(phPrinter, 8u, 0, cbBuf, &cbBuf) || !MEMORY[0] || a3 != 1 && a3 != 2 )
          goto LABEL_32;
        *(_DWORD *)(MEMORY[0] + 72LL) |= 0x800000u;
        *(_DWORD *)(MEMORY[0] + 188LL) = (a3 == 2) + 1;
        v9 = 0;
      }
      goto LABEL_31;
    }
  }
LABEL_32:
  ClosePrinter(phPrinter);
  if ( v8 )
    MemFree(v8);
  if ( v7 )
    MemFree(v7);
}

```

## disassembly

```asm
0x18003ec6c  mov     [rsp-18h+arg_8], rbx
0x18003ec71  mov     [rsp-18h+arg_10], rsi
0x18003ec76  push    rbp
0x18003ec77  push    rdi
0x18003ec78  push    r14
0x18003ec7a  mov     rbp, rsp
0x18003ec7d  sub     rsp, 50h
0x18003ec81  mov     eax, ecx
0x18003ec83  mov     dword ptr [rbp+pDefault+14h], 0
0x18003ec8a  neg     eax
0x18003ec8c  mov     [rbp+phPrinter], 0
0x18003ec94  xorps   xmm0, xmm0
0x18003ec97  mov     [rbp+cbBuf], 0
0x18003ec9e  sbb     r9d, r9d
0x18003eca1  mov     r14d, r8d
0x18003eca4  and     r9d, 0FFFFFFFCh
0x18003eca8  mov     rdi, rdx
0x18003ecab  add     r9d, 0Ch
0x18003ecaf  mov     ebx, ecx
0x18003ecb1  mov     [rbp+pDefault.DesiredAccess], r9d
0x18003ecb5  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x18003ecba  call    IsClosePrinterPresent
0x18003ecbf  test    al, al
0x18003ecc1  jz      loc_18003EEF8
0x18003ecc7  call    IsClosePrinterPresent
0x18003eccc  test    al, al
0x18003ecce  jz      loc_18003EEF8
0x18003ecd4  call    IsSetPrinterWPresent
0x18003ecd9  test    al, al
0x18003ecdb  jz      loc_18003EEF8
0x18003ece1  lea     r8, [rbp+pDefault]; pDefault
0x18003ece5  mov     rcx, rdi; pPrinterName
0x18003ece8  lea     rdx, [rbp+phPrinter]; phPrinter
0x18003ecec  call    cs:__imp_OpenPrinterW
0x18003ecf2  test    eax, eax
0x18003ecf4  jz      loc_18003EEF8
0x18003ecfa  mov     esi, 8
0x18003ecff  mov     ecx, esi
0x18003ed01  test    ebx, ebx
0x18003ed03  jnz     loc_18003EDF3
0x18003ed09  xor     ebx, ebx
0x18003ed0b  call    MemAlloc
0x18003ed10  mov     rdi, rax
0x18003ed13  test    rax, rax
0x18003ed16  jz      loc_18003EED4
0x18003ed1c  mov     rcx, [rbp+phPrinter]; hPrinter
0x18003ed20  lea     rax, [rbp+cbBuf]
0x18003ed24  mov     r9d, esi; cbBuf
0x18003ed27  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x18003ed2c  mov     r8, rdi; pPrinter
0x18003ed2f  mov     edx, esi; Level
0x18003ed31  call    cs:__imp_GetPrinterW
0x18003ed37  test    eax, eax
0x18003ed39  jz      short loc_18003ED75
0x18003ed3b  mov     rcx, [rdi]
0x18003ed3e  test    rcx, rcx
0x18003ed41  jz      short loc_18003ED75
0x18003ed43  mov     eax, r14d
0x18003ed46  sub     eax, 1
0x18003ed49  jz      short loc_18003ED54
0x18003ed4b  cmp     eax, 1
0x18003ed4e  jnz     loc_18003EED4
0x18003ed54  bts     dword ptr [rcx+48h], 17h
0x18003ed59  mov     r8, rdi
0x18003ed5c  mov     rax, [rdi]
0x18003ed5f  xor     ecx, ecx
0x18003ed61  cmp     r14d, 2
0x18003ed65  setz    cl
0x18003ed68  inc     ecx
0x18003ed6a  mov     [rax+0BCh], ecx
0x18003ed70  jmp     loc_18003EEC5
0x18003ed75  mov     rcx, rdi; lpMem
0x18003ed78  call    MemFree
0x18003ed7d  mov     ecx, [rbp+cbBuf]
0x18003ed80  call    MemAlloc
0x18003ed85  mov     rdi, rax
0x18003ed88  test    rax, rax
0x18003ed8b  jnz     loc_18003EED4
0x18003ed91  mov     r9d, [rbp+cbBuf]; cbBuf
0x18003ed95  lea     rax, [rbp+cbBuf]
0x18003ed99  mov     rcx, [rbp+phPrinter]; hPrinter
0x18003ed9d  xor     r8d, r8d; pPrinter
0x18003eda0  mov     edx, esi; Level
0x18003eda2  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x18003eda7  call    cs:__imp_GetPrinterW
0x18003edad  test    eax, eax
0x18003edaf  jz      loc_18003EED4
0x18003edb5  mov     rcx, [rdi]
0x18003edb8  test    rcx, rcx
0x18003edbb  jz      loc_18003EED4
0x18003edc1  mov     eax, r14d
0x18003edc4  sub     eax, 1
0x18003edc7  jz      short loc_18003EDD2
0x18003edc9  cmp     eax, 1
0x18003edcc  jnz     loc_18003EED4
0x18003edd2  bts     dword ptr [rcx+48h], 17h
0x18003edd7  xor     ecx, ecx
0x18003edd9  mov     rax, [rdi]
0x18003eddc  cmp     r14d, 2
0x18003ede0  setz    cl
0x18003ede3  inc     ecx
0x18003ede5  mov     [rax+0BCh], ecx
0x18003edeb  xor     r8d, r8d
0x18003edee  jmp     loc_18003EEC5
0x18003edf3  xor     edi, edi
0x18003edf5  call    MemAlloc
0x18003edfa  mov     rbx, rax
0x18003edfd  test    rax, rax
0x18003ee00  jz      loc_18003EED4
0x18003ee06  mov     rcx, [rbp+phPrinter]; hPrinter
0x18003ee0a  lea     rax, [rbp+cbBuf]
0x18003ee0e  mov     r9d, esi; cbBuf
0x18003ee11  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x18003ee16  lea     esi, [rdi+9]
0x18003ee19  mov     r8, rbx; pPrinter
0x18003ee1c  mov     edx, esi; Level
0x18003ee1e  call    cs:__imp_GetPrinterW
0x18003ee24  test    eax, eax
0x18003ee26  jz      short loc_18003EE5C
0x18003ee28  mov     rcx, [rbx]
0x18003ee2b  test    rcx, rcx
0x18003ee2e  jz      short loc_18003EE5C
0x18003ee30  mov     eax, r14d
0x18003ee33  sub     eax, 1
0x18003ee36  jz      short loc_18003EE41
0x18003ee38  cmp     eax, 1
0x18003ee3b  jnz     loc_18003EED4
0x18003ee41  bts     dword ptr [rcx+48h], 17h
0x18003ee46  xor     ecx, ecx
0x18003ee48  mov     rax, [rbx]
0x18003ee4b  cmp     r14d, 2
0x18003ee4f  setz    cl
0x18003ee52  inc     ecx
0x18003ee54  mov     [rax+0BCh], ecx
0x18003ee5a  jmp     short loc_18003EEC2
0x18003ee5c  mov     rcx, rbx; lpMem
0x18003ee5f  call    MemFree
0x18003ee64  mov     ecx, [rbp+cbBuf]
0x18003ee67  call    MemAlloc
0x18003ee6c  mov     rbx, rax
0x18003ee6f  test    rax, rax
0x18003ee72  jz      short loc_18003EED4
0x18003ee74  mov     r9d, [rbp+cbBuf]; cbBuf
0x18003ee78  lea     rax, [rbp+cbBuf]
0x18003ee7c  mov     rcx, [rbp+phPrinter]; hPrinter
0x18003ee80  mov     r8, rbx; pPrinter
0x18003ee83  mov     edx, esi; Level
0x18003ee85  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x18003ee8a  call    cs:__imp_GetPrinterW
0x18003ee90  test    eax, eax
0x18003ee92  jz      short loc_18003EED4
0x18003ee94  mov     rcx, [rbx]
0x18003ee97  test    rcx, rcx
0x18003ee9a  jz      short loc_18003EED4
0x18003ee9c  mov     eax, r14d
0x18003ee9f  sub     eax, 1
0x18003eea2  jz      short loc_18003EEA9
0x18003eea4  cmp     eax, 1
0x18003eea7  jnz     short loc_18003EED4
0x18003eea9  bts     dword ptr [rcx+48h], 17h
0x18003eeae  xor     edx, edx
0x18003eeb0  mov     rax, [rbx]
0x18003eeb3  cmp     r14d, 2
0x18003eeb7  setz    dl
0x18003eeba  inc     edx
0x18003eebc  mov     [rax+0BCh], edx
0x18003eec2  mov     r8, rbx; pPrinter
0x18003eec5  mov     rcx, [rbp+phPrinter]; hPrinter
0x18003eec9  xor     r9d, r9d; Command
0x18003eecc  mov     edx, esi; Level
0x18003eece  call    cs:__imp_SetPrinterW
0x18003eed4  mov     rcx, [rbp+phPrinter]; hPrinter
0x18003eed8  call    cs:__imp_ClosePrinter
0x18003eede  test    rdi, rdi
0x18003eee1  jz      short loc_18003EEEB
0x18003eee3  mov     rcx, rdi; lpMem
0x18003eee6  call    MemFree
0x18003eeeb  test    rbx, rbx
0x18003eeee  jz      short loc_18003EEF8
0x18003eef0  mov     rcx, rbx; lpMem
0x18003eef3  call    MemFree
0x18003eef8  lea     r11, [rsp+50h+var_s0]
0x18003eefd  mov     rbx, [r11+28h]
0x18003ef01  mov     rsi, [r11+30h]
0x18003ef05  mov     rsp, r11
0x18003ef08  pop     r14
0x18003ef0a  pop     rdi
0x18003ef0b  pop     rbp
0x18003ef0c  retn
```
