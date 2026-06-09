# PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)

- ea: `0x18000d864`
- end: `0x18000d975`
- name: `?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(const struct tagRepairInfoMap *, struct tagRepairInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180009250`
- `0x18000cf64`

## callees

- `0x180002676`
- `0x18000d864`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000d8b3`
- `msvcrt!wcsnlen` at `0x18000d8b3`
- `KERNEL32!GetLastError` at `0x18000d937`
- `KERNEL32!GetLastError` at `0x18000d937`
- `USER32!LoadStringW` at `0x18000d927`
- `USER32!LoadStringW` at `0x18000d927`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d8ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d8ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d955`

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
0x18000d864  push    rbx
0x18000d866  push    rbp
0x18000d867  push    rsi
0x18000d868  push    rdi
0x18000d869  sub     rsp, 28h
0x18000d86d  movups  xmm0, xmmword ptr [rcx+8]
0x18000d871  mov     rsi, rdx
0x18000d874  mov     rbx, rcx
0x18000d877  movups  xmmword ptr [rdx], xmm0
0x18000d87a  movups  xmm1, xmmword ptr [rcx+18h]
0x18000d87e  movups  xmmword ptr [rdx+10h], xmm1
0x18000d882  movups  xmm0, xmmword ptr [rcx+28h]
0x18000d886  movups  xmmword ptr [rdx+20h], xmm0
0x18000d88a  movups  xmm1, xmmword ptr [rcx+38h]
0x18000d88e  movups  xmmword ptr [rdx+30h], xmm1
0x18000d892  movups  xmm0, xmmword ptr [rcx+48h]
0x18000d896  movups  xmmword ptr [rdx+40h], xmm0
0x18000d89a  movups  xmm1, xmmword ptr [rcx+58h]
0x18000d89e  movups  xmmword ptr [rdx+50h], xmm1
0x18000d8a2  movups  xmm0, xmmword ptr [rcx+68h]
0x18000d8a6  movups  xmmword ptr [rdx+60h], xmm0
0x18000d8aa  mov     rcx, [rcx+18h]; Source
0x18000d8ae  mov     edx, 100h; MaxCount
0x18000d8b3  call    cs:__imp_wcsnlen
0x18000d8ba  nop     dword ptr [rax+rax+00h]
0x18000d8bf  lea     rbp, ds:2[rax*2]
0x18000d8c7  mov     rcx, rbp; cb
0x18000d8ca  call    cs:__imp_CoTaskMemAlloc
0x18000d8d1  nop     dword ptr [rax+rax+00h]
0x18000d8d6  mov     rdi, rax
0x18000d8d9  test    rax, rax
0x18000d8dc  jnz     short loc_18000D8E8
0x18000d8de  mov     ebx, 8007000Eh
0x18000d8e3  jmp     loc_18000D969
0x18000d8e8  mov     rdx, [rbx+18h]; Src
0x18000d8ec  mov     r8, rbp; Size
0x18000d8ef  mov     rcx, rdi; void *
0x18000d8f2  call    memcpy_0
0x18000d8f7  mov     ecx, 800h; cb
0x18000d8fc  mov     [rsi+10h], rdi
0x18000d900  call    cs:__imp_CoTaskMemAlloc
0x18000d907  nop     dword ptr [rax+rax+00h]
0x18000d90c  mov     rdi, rax
0x18000d90f  test    rax, rax
0x18000d912  jz      short loc_18000D8DE
0x18000d914  mov     edx, [rbx+4]; uID
0x18000d917  mov     r9d, 400h; cchBufferMax
0x18000d91d  mov     rcx, cs:hInstance; hInstance
0x18000d924  mov     r8, rax; lpBuffer
0x18000d927  call    cs:__imp_LoadStringW
0x18000d92e  nop     dword ptr [rax+rax+00h]
0x18000d933  test    eax, eax
0x18000d935  jnz     short loc_18000D963
0x18000d937  call    cs:__imp_GetLastError
0x18000d93e  nop     dword ptr [rax+rax+00h]
0x18000d943  mov     ebx, eax
0x18000d945  test    eax, eax
0x18000d947  jle     short loc_18000D952
0x18000d949  movzx   ebx, ax
0x18000d94c  or      ebx, 80070000h
0x18000d952  mov     rcx, rdi; pv
0x18000d955  call    cs:__imp_CoTaskMemFree
0x18000d95c  nop     dword ptr [rax+rax+00h]
0x18000d961  jmp     short loc_18000D969
0x18000d963  xor     ebx, ebx
0x18000d965  mov     [rsi+18h], rdi
0x18000d969  mov     eax, ebx
0x18000d96b  add     rsp, 28h
0x18000d96f  pop     rdi
0x18000d970  pop     rsi
0x18000d971  pop     rbp
0x18000d972  pop     rbx
0x18000d973  retn
```
