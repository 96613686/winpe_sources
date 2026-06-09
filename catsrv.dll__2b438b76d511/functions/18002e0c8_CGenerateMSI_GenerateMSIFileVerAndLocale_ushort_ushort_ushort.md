# CGenerateMSI::GenerateMSIFileVerAndLocale(ushort *,ushort * *,ushort * *)

- ea: `0x18002e0c8`
- end: `0x18002e211`
- name: `?GenerateMSIFileVerAndLocale@CGenerateMSI@@AEAAJPEAGPEAPEAG1@Z`
- size: `329`
- prototype: `int(CGenerateMSI *__hidden this, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002b820`
- `0x18002c300`
- `0x18002cef0`

## callees

- `0x18002e0c8`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e14d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e14d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e158`
- `msi!__imp_MsiGetFileVersionW` at `0x18002e117`
- `msi!__imp_MsiGetFileVersionW` at `0x18002e19d`
- `msi!__imp_MsiGetFileVersionW` at `0x18002e117`
- `msi!__imp_MsiGetFileVersionW` at `0x18002e19d`

## pseudocode

```c
int __fastcall CGenerateMSI::GenerateMSIFileVerAndLocale(
        CGenerateMSI *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int result; // eax
  DWORD v8; // ebx
  DWORD v9; // ebp
  void *v10; // rsi
  LPVOID v11; // rax
  void *v12; // rdi
  signed int FileVersionW; // ebx
  DWORD pcchLangBuf; // [rsp+60h] [rbp+8h] BYREF
  int v15; // [rsp+64h] [rbp+Ch]
  DWORD pcchVersionBuf; // [rsp+70h] [rbp+18h] BYREF

  v15 = HIDWORD(this);
  pcchVersionBuf = 0;
  pcchLangBuf = 0;
  *a3 = 0;
  result = MsiGetFileVersionW(a2, 0, &pcchVersionBuf, 0, &pcchLangBuf);
  if ( result == 1006 )
    return 0;
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v8 = 2 * pcchLangBuf + 2;
    v9 = 2 * pcchVersionBuf + 2;
    v10 = CoTaskMemAlloc(v9);
    v11 = CoTaskMemAlloc(v8);
    v12 = v11;
    if ( v10 && v11 )
    {
      memset_0(v10, 0, v9);
      memset_0(v12, 0, v8);
      FileVersionW = MsiGetFileVersionW(a2, (LPWSTR)v10, &pcchVersionBuf, (LPWSTR)v12, &pcchLangBuf);
      if ( !FileVersionW )
      {
        *a3 = (unsigned __int16 *)v10;
        *a4 = (unsigned __int16 *)v12;
        return 0;
      }
      CoTaskMemFree(v10);
      CoTaskMemFree(v12);
      if ( FileVersionW > 0 )
        return (unsigned __int16)FileVersionW | 0x80070000;
      return FileVersionW;
    }
    else
    {
      CoTaskMemFree(v10);
      CoTaskMemFree(v12);
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002e0c8  mov     rax, rsp
0x18002e0cb  mov     [rax+10h], rbx
0x18002e0cf  mov     [rax+20h], rbp
0x18002e0d3  mov     [rax+8], rcx
0x18002e0d7  push    rsi
0x18002e0d8  push    rdi
0x18002e0d9  push    r12
0x18002e0db  push    r14
0x18002e0dd  push    r15
0x18002e0df  sub     rsp, 30h
0x18002e0e3  mov     r12, rdx
0x18002e0e6  mov     dword ptr [rax+18h], 0
0x18002e0ed  mov     dword ptr [rax+8], 0
0x18002e0f4  lea     rax, [rax+8]
0x18002e0f8  mov     r15, r9
0x18002e0fb  mov     qword ptr [r8], 0
0x18002e102  mov     r14, r8
0x18002e105  mov     [rsp+58h+pcchLangBuf], rax; pcchLangBuf
0x18002e10a  mov     rcx, r12; szFilePath
0x18002e10d  lea     r8, [rsp+58h+pcchVersionBuf]; pcchVersionBuf
0x18002e112  xor     r9d, r9d; lpLangBuf
0x18002e115  xor     edx, edx; lpVersionBuf
0x18002e117  call    cs:__imp_MsiGetFileVersionW
0x18002e11d  cmp     eax, 3EEh
0x18002e122  jnz     short loc_18002E12B
0x18002e124  xor     eax, eax
0x18002e126  jmp     loc_18002E1FA
0x18002e12b  test    eax, eax
0x18002e12d  jnz     loc_18002E1F0
0x18002e133  mov     eax, [rsp+58h+arg_0]
0x18002e137  lea     ebx, ds:2[rax*2]
0x18002e13e  mov     eax, [rsp+58h+pcchVersionBuf]
0x18002e142  lea     eax, ds:2[rax*2]
0x18002e149  mov     ecx, eax; cb
0x18002e14b  mov     ebp, eax
0x18002e14d  call    cs:__imp_CoTaskMemAlloc
0x18002e153  mov     ecx, ebx; cb
0x18002e155  mov     rsi, rax
0x18002e158  call    cs:__imp_CoTaskMemAlloc
0x18002e15e  mov     rdi, rax
0x18002e161  test    rsi, rsi
0x18002e164  jz      short loc_18002E1D7
0x18002e166  test    rax, rax
0x18002e169  jz      short loc_18002E1D7
0x18002e16b  mov     r8d, ebp; Size
0x18002e16e  xor     edx, edx; Val
0x18002e170  mov     rcx, rsi; void *
0x18002e173  call    memset_0
0x18002e178  mov     r8d, ebx; Size
0x18002e17b  xor     edx, edx; Val
0x18002e17d  mov     rcx, rdi; void *
0x18002e180  call    memset_0
0x18002e185  lea     rax, [rsp+58h+arg_0]
0x18002e18a  mov     r9, rdi; lpLangBuf
0x18002e18d  lea     r8, [rsp+58h+pcchVersionBuf]; pcchVersionBuf
0x18002e192  mov     [rsp+58h+pcchLangBuf], rax; pcchLangBuf
0x18002e197  mov     rdx, rsi; lpVersionBuf
0x18002e19a  mov     rcx, r12; szFilePath
0x18002e19d  call    cs:__imp_MsiGetFileVersionW
0x18002e1a3  mov     ebx, eax
0x18002e1a5  test    eax, eax
0x18002e1a7  jnz     short loc_18002E1B4
0x18002e1a9  mov     [r14], rsi
0x18002e1ac  mov     [r15], rdi
0x18002e1af  jmp     loc_18002E124
0x18002e1b4  mov     rcx, rsi; pv
0x18002e1b7  call    cs:__imp_CoTaskMemFree
0x18002e1bd  mov     rcx, rdi; pv
0x18002e1c0  call    cs:__imp_CoTaskMemFree
0x18002e1c6  test    ebx, ebx
0x18002e1c8  jle     short loc_18002E1D3
0x18002e1ca  movzx   ebx, bx
0x18002e1cd  or      ebx, 80070000h
0x18002e1d3  mov     eax, ebx
0x18002e1d5  jmp     short loc_18002E1FA
0x18002e1d7  mov     rcx, rsi; pv
0x18002e1da  call    cs:__imp_CoTaskMemFree
0x18002e1e0  mov     rcx, rdi; pv
0x18002e1e3  call    cs:__imp_CoTaskMemFree
0x18002e1e9  mov     eax, 8007000Eh
0x18002e1ee  jmp     short loc_18002E1FA
0x18002e1f0  jle     short loc_18002E1FA
0x18002e1f2  movzx   eax, ax
0x18002e1f5  or      eax, 80070000h
0x18002e1fa  mov     rbx, [rsp+58h+arg_8]
0x18002e1ff  mov     rbp, [rsp+58h+arg_18]
0x18002e204  add     rsp, 30h
0x18002e208  pop     r15
0x18002e20a  pop     r14
0x18002e20c  pop     r12
0x18002e20e  pop     rdi
0x18002e20f  pop     rsi
0x18002e210  retn
```
