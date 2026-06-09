# PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)

- ea: `0x18000abe8`
- end: `0x18000acd1`
- name: `?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(const struct tagRepairInfoMap *, struct tagRepairInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a208`

## callees

- `0x1800026e6`
- `0x18000abe8`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000ac37`
- `msvcrt!wcsnlen` at `0x18000ac37`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ac96`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ac96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aca0`

## pseudocode

```c
__int64 __fastcall PopulateRepairInfo(const struct tagRepairInfoMap *a1, struct tagRepairInfo *a2)
{
  SIZE_T v4; // rbp
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  unsigned int v7; // ebx
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  signed int LastError; // eax

  *a2 = *(struct tagRepairInfo *)((char *)a1 + 8);
  v4 = 2 * wcsnlen(*((const wchar_t **)a1 + 3), 0x100u) + 2;
  v5 = (WCHAR *)CoTaskMemAlloc(v4);
  v6 = v5;
  if ( v5
    && (memcpy_0(v5, *((const void **)a1 + 3), v4),
        a2->pwszClassName = v6,
        v8 = (WCHAR *)CoTaskMemAlloc(0x800u),
        (v9 = v8) != 0) )
  {
    if ( LoadStringW(lpSource, *((_DWORD *)a1 + 1), v8, 1024) )
    {
      v7 = 0;
      a2->pwszDescription = v9;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      CoTaskMemFree(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x18000abe8  push    rbx
0x18000abea  push    rbp
0x18000abeb  push    rsi
0x18000abec  push    rdi
0x18000abed  sub     rsp, 28h
0x18000abf1  movups  xmm0, xmmword ptr [rcx+8]
0x18000abf5  mov     rsi, rdx
0x18000abf8  mov     rbx, rcx
0x18000abfb  movups  xmmword ptr [rdx], xmm0
0x18000abfe  movups  xmm1, xmmword ptr [rcx+18h]
0x18000ac02  movups  xmmword ptr [rdx+10h], xmm1
0x18000ac06  movups  xmm0, xmmword ptr [rcx+28h]
0x18000ac0a  movups  xmmword ptr [rdx+20h], xmm0
0x18000ac0e  movups  xmm1, xmmword ptr [rcx+38h]
0x18000ac12  movups  xmmword ptr [rdx+30h], xmm1
0x18000ac16  movups  xmm0, xmmword ptr [rcx+48h]
0x18000ac1a  movups  xmmword ptr [rdx+40h], xmm0
0x18000ac1e  movups  xmm1, xmmword ptr [rcx+58h]
0x18000ac22  movups  xmmword ptr [rdx+50h], xmm1
0x18000ac26  movups  xmm0, xmmword ptr [rcx+68h]
0x18000ac2a  movups  xmmword ptr [rdx+60h], xmm0
0x18000ac2e  mov     rcx, [rcx+18h]; Source
0x18000ac32  mov     edx, 100h; MaxCount
0x18000ac37  call    cs:__imp_wcsnlen
0x18000ac3d  lea     rbp, ds:2[rax*2]
0x18000ac45  mov     rcx, rbp; cb
0x18000ac48  call    cs:__imp_CoTaskMemAlloc
0x18000ac4e  mov     rdi, rax
0x18000ac51  test    rax, rax
0x18000ac54  jnz     short loc_18000AC5D
0x18000ac56  mov     ebx, 8007000Eh
0x18000ac5b  jmp     short loc_18000ACC6
0x18000ac5d  mov     rdx, [rbx+18h]; Src
0x18000ac61  mov     r8, rbp; Size
0x18000ac64  mov     rcx, rdi; void *
0x18000ac67  call    memcpy_0
0x18000ac6c  mov     ecx, 800h; cb
0x18000ac71  mov     [rsi+10h], rdi
0x18000ac75  call    cs:__imp_CoTaskMemAlloc
0x18000ac7b  mov     rdi, rax
0x18000ac7e  test    rax, rax
0x18000ac81  jz      short loc_18000AC56
0x18000ac83  mov     edx, [rbx+4]; uID
0x18000ac86  mov     r9d, 400h; cchBufferMax
0x18000ac8c  mov     rcx, cs:lpSource; hInstance
0x18000ac93  mov     r8, rax; lpBuffer
0x18000ac96  call    cs:__imp_LoadStringW
0x18000ac9c  test    eax, eax
0x18000ac9e  jnz     short loc_18000ACC0
0x18000aca0  call    cs:__imp_GetLastError
0x18000aca6  mov     ebx, eax
0x18000aca8  test    eax, eax
0x18000acaa  jle     short loc_18000ACB5
0x18000acac  movzx   ebx, ax
0x18000acaf  or      ebx, 80070000h
0x18000acb5  mov     rcx, rdi; pv
0x18000acb8  call    cs:__imp_CoTaskMemFree
0x18000acbe  jmp     short loc_18000ACC6
0x18000acc0  xor     ebx, ebx
0x18000acc2  mov     [rsi+18h], rdi
0x18000acc6  mov     eax, ebx
0x18000acc8  add     rsp, 28h
0x18000accc  pop     rdi
0x18000accd  pop     rsi
0x18000acce  pop     rbp
0x18000accf  pop     rbx
0x18000acd0  retn
```
