# BuildApplicationPid

- ea: `0x1800c5a3c`
- end: `0x1800c5b44`
- name: `BuildApplicationPid`
- size: `264`
- prototype: `__int64 __fastcall(LPWSTR lpFilename)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800c7f40`
- `0x1800c8bf4`

## callees

- `0x1800c5a3c`
- `0x1800c7530`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1800c5ada`
- `msvcrt!_ultow_s` at `0x1800c5ada`
- `KERNEL32!GetCurrentProcessId` at `0x1800c5abc`
- `KERNEL32!GetCurrentProcessId` at `0x1800c5abc`
- `KERNEL32!GetModuleFileNameW` at `0x1800c5a6f`
- `KERNEL32!GetModuleFileNameW` at `0x1800c5a6f`

## pseudocode

```c
__int64 __fastcall BuildApplicationPid(LPWSTR lpFilename, __int64 a2, __int64 *a3, _QWORD *a4)
{
  DWORD ModuleFileNameW; // eax
  const unsigned __int16 *v8; // r8
  wchar_t *v9; // rsi
  DWORD CurrentProcessId; // eax
  unsigned int v11; // edx
  wchar_t *v12; // rcx
  wchar_t *v13; // rax
  unsigned int v15; // [rsp+28h] [rbp-20h]
  size_t BufferCount; // [rsp+50h] [rbp+8h] BYREF
  wchar_t *Buffer; // [rsp+60h] [rbp+18h] BYREF

  *lpFilename = 0;
  *a3 = 0;
  *a4 = 0;
  ModuleFileNameW = GetModuleFileNameW(0, lpFilename, 0x112u);
  if ( ModuleFileNameW - 1 > 0x110
    || (*a4 = ModuleFileNameW,
        BufferCount = 274 - ModuleFileNameW,
        v9 = &lpFilename[ModuleFileNameW],
        Buffer = v9,
        (int)StringCchCopyExW(v9, BufferCount, v8, &Buffer, &BufferCount, v15) < 0)
    || (CurrentProcessId = GetCurrentProcessId(), _ultow_s(CurrentProcessId, Buffer, BufferCount, 10)) )
  {
    v11 = 0;
    *lpFilename = 0;
    *a3 = 0;
    *a4 = 0;
  }
  else
  {
    v11 = 1;
    v12 = v9;
    while ( 1 )
    {
      v13 = v12--;
      if ( v12 < lpFilename )
        break;
      if ( *v12 == 92 || *v12 == 47 )
      {
        if ( v13 >= v9 )
          *a3 = 0;
        else
          *a3 = v13 - lpFilename;
        return v11;
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800c5a3c  mov     [rsp+arg_8], rbx
0x1800c5a41  mov     [rsp+arg_18], rbp
0x1800c5a46  push    rsi
0x1800c5a47  push    rdi
0x1800c5a48  push    r14
0x1800c5a4a  sub     rsp, 30h
0x1800c5a4e  xor     eax, eax
0x1800c5a50  mov     rdi, r8
0x1800c5a53  mov     [rcx], ax
0x1800c5a56  mov     rbx, rcx
0x1800c5a59  mov     [r8], rax
0x1800c5a5c  mov     rdx, rcx; lpFilename
0x1800c5a5f  mov     ebp, 112h
0x1800c5a64  mov     [r9], rax
0x1800c5a67  mov     r8d, ebp; nSize
0x1800c5a6a  xor     ecx, ecx; hModule
0x1800c5a6c  mov     r14, r9
0x1800c5a6f  call    cs:__imp_GetModuleFileNameW
0x1800c5a76  nop     dword ptr [rax+rax+00h]
0x1800c5a7b  lea     edx, [rax-1]
0x1800c5a7e  cmp     edx, 110h
0x1800c5a84  ja      loc_1800C5B21
0x1800c5a8a  mov     ecx, eax
0x1800c5a8c  lea     r9, [rsp+48h+Buffer]; unsigned __int16 **
0x1800c5a91  sub     ebp, eax
0x1800c5a93  mov     [r14], rcx
0x1800c5a96  mov     edx, ebp; unsigned __int64
0x1800c5a98  lea     rax, [rsp+48h+BufferCount]
0x1800c5a9d  mov     [rsp+48h+BufferCount], rdx
0x1800c5aa2  lea     rsi, [rbx+rcx*2]
0x1800c5aa6  mov     [rsp+48h+var_28], rax; unsigned __int64 *
0x1800c5aab  mov     rcx, rsi; unsigned __int16 *
0x1800c5aae  mov     [rsp+48h+Buffer], rsi
0x1800c5ab3  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800c5ab8  test    eax, eax
0x1800c5aba  js      short loc_1800C5B21
0x1800c5abc  call    cs:__imp_GetCurrentProcessId
0x1800c5ac3  nop     dword ptr [rax+rax+00h]
0x1800c5ac8  mov     r8, [rsp+48h+BufferCount]; BufferCount
0x1800c5acd  mov     r9d, 0Ah; Radix
0x1800c5ad3  mov     rdx, [rsp+48h+Buffer]; Buffer
0x1800c5ad8  mov     ecx, eax; Value
0x1800c5ada  call    cs:__imp__ultow_s
0x1800c5ae1  nop     dword ptr [rax+rax+00h]
0x1800c5ae6  test    eax, eax
0x1800c5ae8  jnz     short loc_1800C5B21
0x1800c5aea  lea     edx, [rax+1]
0x1800c5aed  mov     rcx, rsi
0x1800c5af0  mov     rax, rcx
0x1800c5af3  sub     rcx, 2
0x1800c5af7  cmp     rcx, rbx
0x1800c5afa  jb      short loc_1800C5B2E
0x1800c5afc  cmp     word ptr [rcx], 5Ch ; '\'
0x1800c5b00  jz      short loc_1800C5B08
0x1800c5b02  cmp     word ptr [rcx], 2Fh ; '/'
0x1800c5b06  jnz     short loc_1800C5AF0
0x1800c5b08  cmp     rax, rsi
0x1800c5b0b  jnb     short loc_1800C5B18
0x1800c5b0d  sub     rax, rbx
0x1800c5b10  sar     rax, 1
0x1800c5b13  mov     [rdi], rax
0x1800c5b16  jmp     short loc_1800C5B2E
0x1800c5b18  mov     qword ptr [rdi], 0
0x1800c5b1f  jmp     short loc_1800C5B2E
0x1800c5b21  xor     edx, edx
0x1800c5b23  xor     ecx, ecx
0x1800c5b25  mov     [rbx], cx
0x1800c5b28  mov     [rdi], rcx
0x1800c5b2b  mov     [r14], rcx
0x1800c5b2e  mov     rbx, [rsp+48h+arg_8]
0x1800c5b33  mov     eax, edx
0x1800c5b35  mov     rbp, [rsp+48h+arg_18]
0x1800c5b3a  add     rsp, 30h
0x1800c5b3e  pop     r14
0x1800c5b40  pop     rdi
0x1800c5b41  pop     rsi
0x1800c5b42  retn
```
