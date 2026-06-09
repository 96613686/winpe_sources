# BuildApplicationPid

- ea: `0x1800194ec`
- end: `0x1800195f4`
- name: `BuildApplicationPid`
- size: `264`
- prototype: `__int64 __fastcall(LPWSTR lpFilename)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001a0fc`
- `0x18001acc4`

## callees

- `0x1800194ec`
- `0x180019dc4`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18001958a`
- `msvcrt!_ultow_s` at `0x18001958a`
- `KERNEL32!GetCurrentProcessId` at `0x18001956c`
- `KERNEL32!GetCurrentProcessId` at `0x18001956c`
- `KERNEL32!GetModuleFileNameW` at `0x18001951f`
- `KERNEL32!GetModuleFileNameW` at `0x18001951f`

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
0x1800194ec  mov     [rsp+arg_8], rbx
0x1800194f1  mov     [rsp+arg_18], rbp
0x1800194f6  push    rsi
0x1800194f7  push    rdi
0x1800194f8  push    r14
0x1800194fa  sub     rsp, 30h
0x1800194fe  xor     eax, eax
0x180019500  mov     rdi, r8
0x180019503  mov     [rcx], ax
0x180019506  mov     rbx, rcx
0x180019509  mov     [r8], rax
0x18001950c  mov     rdx, rcx; lpFilename
0x18001950f  mov     ebp, 112h
0x180019514  mov     [r9], rax
0x180019517  mov     r8d, ebp; nSize
0x18001951a  xor     ecx, ecx; hModule
0x18001951c  mov     r14, r9
0x18001951f  call    cs:__imp_GetModuleFileNameW
0x180019526  nop     dword ptr [rax+rax+00h]
0x18001952b  lea     edx, [rax-1]
0x18001952e  cmp     edx, 110h
0x180019534  ja      loc_1800195D1
0x18001953a  mov     ecx, eax
0x18001953c  lea     r9, [rsp+48h+Buffer]; unsigned __int16 **
0x180019541  sub     ebp, eax
0x180019543  mov     [r14], rcx
0x180019546  mov     edx, ebp; unsigned __int64
0x180019548  lea     rax, [rsp+48h+BufferCount]
0x18001954d  mov     [rsp+48h+BufferCount], rdx
0x180019552  lea     rsi, [rbx+rcx*2]
0x180019556  mov     [rsp+48h+var_28], rax; unsigned __int64 *
0x18001955b  mov     rcx, rsi; unsigned __int16 *
0x18001955e  mov     [rsp+48h+Buffer], rsi
0x180019563  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180019568  test    eax, eax
0x18001956a  js      short loc_1800195D1
0x18001956c  call    cs:__imp_GetCurrentProcessId
0x180019573  nop     dword ptr [rax+rax+00h]
0x180019578  mov     r8, [rsp+48h+BufferCount]; BufferCount
0x18001957d  mov     r9d, 0Ah; Radix
0x180019583  mov     rdx, [rsp+48h+Buffer]; Buffer
0x180019588  mov     ecx, eax; Value
0x18001958a  call    cs:__imp__ultow_s
0x180019591  nop     dword ptr [rax+rax+00h]
0x180019596  test    eax, eax
0x180019598  jnz     short loc_1800195D1
0x18001959a  lea     edx, [rax+1]
0x18001959d  mov     rcx, rsi
0x1800195a0  mov     rax, rcx
0x1800195a3  sub     rcx, 2
0x1800195a7  cmp     rcx, rbx
0x1800195aa  jb      short loc_1800195DE
0x1800195ac  cmp     word ptr [rcx], 5Ch ; '\'
0x1800195b0  jz      short loc_1800195B8
0x1800195b2  cmp     word ptr [rcx], 2Fh ; '/'
0x1800195b6  jnz     short loc_1800195A0
0x1800195b8  cmp     rax, rsi
0x1800195bb  jnb     short loc_1800195C8
0x1800195bd  sub     rax, rbx
0x1800195c0  sar     rax, 1
0x1800195c3  mov     [rdi], rax
0x1800195c6  jmp     short loc_1800195DE
0x1800195c8  mov     qword ptr [rdi], 0
0x1800195cf  jmp     short loc_1800195DE
0x1800195d1  xor     edx, edx
0x1800195d3  xor     ecx, ecx
0x1800195d5  mov     [rbx], cx
0x1800195d8  mov     [rdi], rcx
0x1800195db  mov     [r14], rcx
0x1800195de  mov     rbx, [rsp+48h+arg_8]
0x1800195e3  mov     eax, edx
0x1800195e5  mov     rbp, [rsp+48h+arg_18]
0x1800195ea  add     rsp, 30h
0x1800195ee  pop     r14
0x1800195f0  pop     rdi
0x1800195f1  pop     rsi
0x1800195f2  retn
```
