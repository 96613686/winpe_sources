# BuildApplicationPid

- ea: `0x180026154`
- end: `0x180026250`
- name: `BuildApplicationPid`
- size: `252`
- prototype: `__int64 __fastcall(LPWSTR lpFilename)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003bb34`

## callees

- `0x180026154`
- `0x18003af88`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1800261ed`
- `msvcrt!_ultow_s` at `0x1800261ed`
- `KERNEL32!GetCurrentProcessId` at `0x1800261d5`
- `KERNEL32!GetCurrentProcessId` at `0x1800261d5`
- `KERNEL32!GetModuleFileNameW` at `0x180026187`
- `KERNEL32!GetModuleFileNameW` at `0x180026187`

## pseudocode

```c
__int64 __fastcall BuildApplicationPid(LPWSTR lpFilename, __int64 a2, __int64 *a3, _QWORD *a4)
{
  DWORD ModuleFileNameW; // eax
  wchar_t *v8; // rsi
  DWORD CurrentProcessId; // eax
  unsigned int v10; // edx
  wchar_t *v11; // rcx
  wchar_t *v12; // rax
  unsigned int v14; // [rsp+28h] [rbp-20h]
  size_t BufferCount; // [rsp+50h] [rbp+8h] BYREF
  wchar_t *Buffer; // [rsp+60h] [rbp+18h] BYREF

  *lpFilename = 0;
  *a3 = 0;
  *a4 = 0;
  ModuleFileNameW = GetModuleFileNameW(0, lpFilename, 0x112u);
  if ( ModuleFileNameW - 1 > 0x110
    || (*a4 = ModuleFileNameW,
        BufferCount = 274 - ModuleFileNameW,
        v8 = &lpFilename[ModuleFileNameW],
        Buffer = v8,
        StringCchCopyExW(v8, BufferCount, L":", &Buffer, &BufferCount, v14) < 0)
    || (CurrentProcessId = GetCurrentProcessId(), _ultow_s(CurrentProcessId, Buffer, BufferCount, 10)) )
  {
    v10 = 0;
    *lpFilename = 0;
    *a3 = 0;
    *a4 = 0;
  }
  else
  {
    v10 = 1;
    v11 = v8;
    while ( 1 )
    {
      v12 = v11--;
      if ( v11 < lpFilename )
        break;
      if ( *v11 == 92 || *v11 == 47 )
      {
        if ( v12 >= v8 )
          *a3 = 0;
        else
          *a3 = v12 - lpFilename;
        return v10;
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180026154  mov     [rsp+arg_8], rbx
0x180026159  mov     [rsp+arg_18], rbp
0x18002615e  push    rsi
0x18002615f  push    rdi
0x180026160  push    r14
0x180026162  sub     rsp, 30h
0x180026166  xor     eax, eax
0x180026168  mov     rdi, r8
0x18002616b  mov     [rcx], ax
0x18002616e  mov     rbx, rcx
0x180026171  mov     [r8], rax
0x180026174  mov     rdx, rcx; lpFilename
0x180026177  mov     ebp, 112h
0x18002617c  mov     [r9], rax
0x18002617f  mov     r8d, ebp; nSize
0x180026182  xor     ecx, ecx; hModule
0x180026184  mov     r14, r9
0x180026187  call    cs:__imp_GetModuleFileNameW
0x18002618d  lea     edx, [rax-1]
0x180026190  cmp     edx, 110h
0x180026196  ja      loc_18002622E
0x18002619c  mov     ecx, eax
0x18002619e  lea     r9, [rsp+48h+Buffer]; unsigned __int16 **
0x1800261a3  sub     ebp, eax
0x1800261a5  mov     [r14], rcx
0x1800261a8  mov     edx, ebp; unsigned __int64
0x1800261aa  lea     rax, [rsp+48h+BufferCount]
0x1800261af  lea     r8, asc_1800915AC; ":"
0x1800261b6  mov     [rsp+48h+BufferCount], rdx
0x1800261bb  lea     rsi, [rbx+rcx*2]
0x1800261bf  mov     [rsp+48h+var_28], rax; unsigned __int64 *
0x1800261c4  mov     rcx, rsi; unsigned __int16 *
0x1800261c7  mov     [rsp+48h+Buffer], rsi
0x1800261cc  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800261d1  test    eax, eax
0x1800261d3  js      short loc_18002622E
0x1800261d5  call    cs:__imp_GetCurrentProcessId
0x1800261db  mov     r8, [rsp+48h+BufferCount]; BufferCount
0x1800261e0  mov     r9d, 0Ah; Radix
0x1800261e6  mov     rdx, [rsp+48h+Buffer]; Buffer
0x1800261eb  mov     ecx, eax; Value
0x1800261ed  call    cs:__imp__ultow_s
0x1800261f3  test    eax, eax
0x1800261f5  jnz     short loc_18002622E
0x1800261f7  lea     edx, [rax+1]
0x1800261fa  mov     rcx, rsi
0x1800261fd  mov     rax, rcx
0x180026200  sub     rcx, 2
0x180026204  cmp     rcx, rbx
0x180026207  jb      short loc_18002623B
0x180026209  cmp     word ptr [rcx], 5Ch ; '\'
0x18002620d  jz      short loc_180026215
0x18002620f  cmp     word ptr [rcx], 2Fh ; '/'
0x180026213  jnz     short loc_1800261FD
0x180026215  cmp     rax, rsi
0x180026218  jnb     short loc_180026225
0x18002621a  sub     rax, rbx
0x18002621d  sar     rax, 1
0x180026220  mov     [rdi], rax
0x180026223  jmp     short loc_18002623B
0x180026225  mov     qword ptr [rdi], 0
0x18002622c  jmp     short loc_18002623B
0x18002622e  xor     edx, edx
0x180026230  xor     ecx, ecx
0x180026232  mov     [rbx], cx
0x180026235  mov     [rdi], rcx
0x180026238  mov     [r14], rcx
0x18002623b  mov     rbx, [rsp+48h+arg_8]
0x180026240  mov     eax, edx
0x180026242  mov     rbp, [rsp+48h+arg_18]
0x180026247  add     rsp, 30h
0x18002624b  pop     r14
0x18002624d  pop     rdi
0x18002624e  pop     rsi
0x18002624f  retn
```
