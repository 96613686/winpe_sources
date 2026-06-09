# PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)

- ea: `0x180018124`
- end: `0x18001820d`
- name: `?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(const struct tagRepairInfoMap *, struct tagRepairInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180017ac4`

## callees

- `0x1800021c6`
- `0x180018124`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180018173`
- `msvcrt!wcsnlen` at `0x180018173`
- `USER32!LoadStringW` at `0x1800181d2`
- `USER32!LoadStringW` at `0x1800181d2`
- `KERNEL32!GetLastError` at `0x1800181dc`
- `KERNEL32!GetLastError` at `0x1800181dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800181b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800181b1`

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
    if ( LoadStringW(hInstance, *((_DWORD *)a1 + 1), v8, 1024) )
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
0x180018124  push    rbx
0x180018126  push    rbp
0x180018127  push    rsi
0x180018128  push    rdi
0x180018129  sub     rsp, 28h
0x18001812d  movups  xmm0, xmmword ptr [rcx+8]
0x180018131  mov     rsi, rdx
0x180018134  mov     rbx, rcx
0x180018137  movups  xmmword ptr [rdx], xmm0
0x18001813a  movups  xmm1, xmmword ptr [rcx+18h]
0x18001813e  movups  xmmword ptr [rdx+10h], xmm1
0x180018142  movups  xmm0, xmmword ptr [rcx+28h]
0x180018146  movups  xmmword ptr [rdx+20h], xmm0
0x18001814a  movups  xmm1, xmmword ptr [rcx+38h]
0x18001814e  movups  xmmword ptr [rdx+30h], xmm1
0x180018152  movups  xmm0, xmmword ptr [rcx+48h]
0x180018156  movups  xmmword ptr [rdx+40h], xmm0
0x18001815a  movups  xmm1, xmmword ptr [rcx+58h]
0x18001815e  movups  xmmword ptr [rdx+50h], xmm1
0x180018162  movups  xmm0, xmmword ptr [rcx+68h]
0x180018166  movups  xmmword ptr [rdx+60h], xmm0
0x18001816a  mov     rcx, [rcx+18h]; Source
0x18001816e  mov     edx, 100h; MaxCount
0x180018173  call    cs:__imp_wcsnlen
0x180018179  lea     rbp, ds:2[rax*2]
0x180018181  mov     rcx, rbp; cb
0x180018184  call    cs:__imp_CoTaskMemAlloc
0x18001818a  mov     rdi, rax
0x18001818d  test    rax, rax
0x180018190  jnz     short loc_180018199
0x180018192  mov     ebx, 8007000Eh
0x180018197  jmp     short loc_180018202
0x180018199  mov     rdx, [rbx+18h]; Src
0x18001819d  mov     r8, rbp; Size
0x1800181a0  mov     rcx, rdi; void *
0x1800181a3  call    memcpy_0
0x1800181a8  mov     ecx, 800h; cb
0x1800181ad  mov     [rsi+10h], rdi
0x1800181b1  call    cs:__imp_CoTaskMemAlloc
0x1800181b7  mov     rdi, rax
0x1800181ba  test    rax, rax
0x1800181bd  jz      short loc_180018192
0x1800181bf  mov     edx, [rbx+4]; uID
0x1800181c2  mov     r9d, 400h; cchBufferMax
0x1800181c8  mov     rcx, cs:hInstance; hInstance
0x1800181cf  mov     r8, rax; lpBuffer
0x1800181d2  call    cs:__imp_LoadStringW
0x1800181d8  test    eax, eax
0x1800181da  jnz     short loc_1800181FC
0x1800181dc  call    cs:__imp_GetLastError
0x1800181e2  mov     ebx, eax
0x1800181e4  test    eax, eax
0x1800181e6  jle     short loc_1800181F1
0x1800181e8  movzx   ebx, ax
0x1800181eb  or      ebx, 80070000h
0x1800181f1  mov     rcx, rdi; pv
0x1800181f4  call    cs:__imp_CoTaskMemFree
0x1800181fa  jmp     short loc_180018202
0x1800181fc  xor     ebx, ebx
0x1800181fe  mov     [rsi+18h], rdi
0x180018202  mov     eax, ebx
0x180018204  add     rsp, 28h
0x180018208  pop     rdi
0x180018209  pop     rsi
0x18001820a  pop     rbp
0x18001820b  pop     rbx
0x18001820c  retn
```
