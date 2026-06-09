# CircularLog::CheckForLogReset(int)

- ea: `0x140010c68`
- end: `0x140010e45`
- name: `?CheckForLogReset@CircularLog@@IEAAXH@Z`
- size: `477`
- prototype: `void __fastcall(CircularLog *this, int, void *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14001070c`
- `0x140010938`

## callees

- `0x14000a148`
- `0x14000b010`
- `0x14000ec88`
- `0x140010ba8`
- `0x140010c68`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x140010d7e`
- `KERNEL32!MoveFileExW` at `0x140010d7e`
- `KERNEL32!GetFileAttributesExW` at `0x140010d09`
- `KERNEL32!GetFileAttributesExW` at `0x140010d09`
- `KERNEL32!GetLastError` at `0x140010d88`
- `KERNEL32!GetLastError` at `0x140010d88`
- `KERNEL32!CloseHandle` at `0x140010d9c`
- `KERNEL32!CloseHandle` at `0x140010ddd`
- `KERNEL32!CloseHandle` at `0x140010e11`
- `KERNEL32!CloseHandle` at `0x140010d9c`
- `KERNEL32!CloseHandle` at `0x140010ddd`
- `KERNEL32!CloseHandle` at `0x140010e11`

## pseudocode

```c
void __fastcall CircularLog::CheckForLogReset(CircularLog *this, int a2, void *a3, int *a4)
{
  int v6; // r14d
  SString *v7; // r15
  const unsigned __int16 *v8; // rdx
  const WCHAR *v9; // rcx
  int v10; // edx
  const WCHAR *v11; // rsi
  const WCHAR *v12; // rcx
  struct IExecutionEngine *ExecutionEngine; // rax
  void **v14; // [rsp+20h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-38h]
  _BYTE FileInformation[28]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v17; // [rsp+4Ch] [rbp-14h]
  unsigned int v18; // [rsp+50h] [rbp-10h]

  if ( *((_DWORD *)this + 26) )
  {
    v6 = 0;
    v7 = (CircularLog *)((char *)this + 80);
    while ( 1 )
    {
      v14 = &FileLockHolder::`vftable';
      hObject = (HANDLE)-1LL;
      if ( v7 )
      {
        SString::ConvertToUnicode(v7);
        v8 = (const unsigned __int16 *)*((_QWORD *)v7 + 2);
      }
      else
      {
        v8 = 0;
      }
      if ( (int)FileLockHolder::AcquireNoThrow((FileLockHolder *)&v14, v8, a3, a4) < 0 )
        break;
      if ( a2 )
      {
        if ( this == (CircularLog *)-8LL )
        {
          v9 = 0;
        }
        else
        {
          SString::ConvertToUnicode((CircularLog *)((char *)this + 8));
          v9 = (const WCHAR *)*((_QWORD *)this + 3);
        }
        if ( !GetFileAttributesExW(v9, GetFileExInfoStandard, FileInformation) )
          break;
        v10 = (v18 | ((unsigned __int64)v17 << 32)) > *((unsigned int *)this + 26);
      }
      else
      {
        v10 = CircularLog::CheckLogHeader(this);
      }
      if ( !v10 )
        break;
      if ( this == (CircularLog *)-56LL )
      {
        v11 = 0;
      }
      else
      {
        SString::ConvertToUnicode((CircularLog *)((char *)this + 56));
        v11 = (const WCHAR *)*((_QWORD *)this + 9);
      }
      if ( this == (CircularLog *)-8LL )
      {
        v12 = 0;
      }
      else
      {
        SString::ConvertToUnicode((CircularLog *)((char *)this + 8));
        v12 = (const WCHAR *)*((_QWORD *)this + 3);
      }
      if ( MoveFileExW(v12, v11, 3u) || GetLastError() != 32 )
        break;
      if ( hObject != (HANDLE)-1LL )
      {
        CloseHandle(hObject);
        hObject = (HANDLE)-1LL;
      }
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 224LL))(
        ExecutionEngine,
        100);
      v14 = &FileLockHolder::`vftable';
      if ( hObject != (HANDLE)-1LL )
      {
        CloseHandle(hObject);
        hObject = (HANDLE)-1LL;
      }
      if ( ++v6 >= 10 )
        return;
    }
    v14 = &FileLockHolder::`vftable';
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
  }
}

```

## disassembly

```asm
0x140010c68  mov     [rsp-28h+arg_8], rbx
0x140010c6d  mov     [rsp-28h+arg_10], rsi
0x140010c72  mov     [rsp-28h+arg_18], rdi
0x140010c77  push    rbp
0x140010c78  push    r12
0x140010c7a  push    r13
0x140010c7c  push    r14
0x140010c7e  push    r15
0x140010c80  mov     rbp, rsp
0x140010c83  sub     rsp, 60h
0x140010c87  mov     rax, cs:__security_cookie
0x140010c8e  xor     rax, rsp
0x140010c91  mov     [rbp+var_8], rax
0x140010c95  mov     r12d, edx
0x140010c98  mov     rbx, rcx
0x140010c9b  cmp     dword ptr [rcx+68h], 0
0x140010c9f  jz      loc_140010E1B
0x140010ca5  xor     r14d, r14d
0x140010ca8  lea     r15, [rcx+50h]
0x140010cac  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x140010cb3  or      r13, 0FFFFFFFFFFFFFFFFh
0x140010cb7  mov     [rbp+var_40], rax
0x140010cbb  mov     [rbp+hObject], r13
0x140010cbf  test    r15, r15
0x140010cc2  jnz     short loc_140010CC8
0x140010cc4  xor     edx, edx
0x140010cc6  jmp     short loc_140010CD4
0x140010cc8  mov     rcx, r15; this
0x140010ccb  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140010cd0  mov     rdx, [r15+10h]; unsigned __int16 *
0x140010cd4  lea     rcx, [rbp+var_40]; this
0x140010cd8  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x140010cdd  test    eax, eax
0x140010cdf  js      loc_140010DFD
0x140010ce5  test    r12d, r12d
0x140010ce8  jz      short loc_140010D31
0x140010cea  lea     rdi, [rbx+8]
0x140010cee  test    rdi, rdi
0x140010cf1  jnz     short loc_140010CF7
0x140010cf3  xor     ecx, ecx
0x140010cf5  jmp     short loc_140010D03
0x140010cf7  mov     rcx, rdi; this
0x140010cfa  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140010cff  mov     rcx, [rdi+10h]; lpFileName
0x140010d03  lea     r8, [rbp+FileInformation]; lpFileInformation
0x140010d07  xor     edx, edx; fInfoLevelId
0x140010d09  call    cs:__imp_GetFileAttributesExW
0x140010d0f  test    eax, eax
0x140010d11  jz      loc_140010DFD
0x140010d17  mov     ecx, [rbp+var_14]
0x140010d1a  shl     rcx, 20h
0x140010d1e  mov     eax, [rbp+var_10]
0x140010d21  or      rcx, rax
0x140010d24  mov     eax, [rbx+68h]
0x140010d27  xor     edx, edx
0x140010d29  cmp     rcx, rax
0x140010d2c  setnbe  dl
0x140010d2f  jmp     short loc_140010D3B
0x140010d31  mov     rcx, rbx; this
0x140010d34  call    ?CheckLogHeader@CircularLog@@IEAAHXZ; CircularLog::CheckLogHeader(void)
0x140010d39  mov     edx, eax
0x140010d3b  test    edx, edx
0x140010d3d  jz      loc_140010DFD
0x140010d43  lea     rdi, [rbx+38h]
0x140010d47  test    rdi, rdi
0x140010d4a  jnz     short loc_140010D50
0x140010d4c  xor     esi, esi
0x140010d4e  jmp     short loc_140010D5C
0x140010d50  mov     rcx, rdi; this
0x140010d53  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140010d58  mov     rsi, [rdi+10h]
0x140010d5c  lea     rdi, [rbx+8]
0x140010d60  test    rdi, rdi
0x140010d63  jnz     short loc_140010D69
0x140010d65  xor     ecx, ecx
0x140010d67  jmp     short loc_140010D75
0x140010d69  mov     rcx, rdi; this
0x140010d6c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140010d71  mov     rcx, [rdi+10h]; lpExistingFileName
0x140010d75  mov     r8d, 3; dwFlags
0x140010d7b  mov     rdx, rsi; lpNewFileName
0x140010d7e  call    cs:__imp_MoveFileExW
0x140010d84  test    eax, eax
0x140010d86  jnz     short loc_140010DFD
0x140010d88  call    cs:__imp_GetLastError
0x140010d8e  cmp     eax, 20h ; ' '
0x140010d91  jnz     short loc_140010DFD
0x140010d93  mov     rcx, [rbp+hObject]; hObject
0x140010d97  cmp     rcx, r13
0x140010d9a  jz      short loc_140010DA6
0x140010d9c  call    cs:__imp_CloseHandle
0x140010da2  mov     [rbp+hObject], r13
0x140010da6  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x140010dab  mov     r9, rax
0x140010dae  mov     rcx, [rax]
0x140010db1  mov     rax, [rcx+0E0h]
0x140010db8  xor     r8d, r8d
0x140010dbb  lea     edx, [r8+64h]
0x140010dbf  mov     rcx, r9
0x140010dc2  call    cs:__guard_dispatch_icall_fptr
0x140010dc8  nop
0x140010dc9  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x140010dd0  mov     [rbp+var_40], rax
0x140010dd4  mov     rcx, [rbp+hObject]; hObject
0x140010dd8  cmp     rcx, r13
0x140010ddb  jz      short loc_140010DEE
0x140010ddd  call    cs:__imp_CloseHandle
0x140010de3  mov     [rbp+hObject], r13
0x140010de7  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x140010dee  inc     r14d
0x140010df1  cmp     r14d, 0Ah
0x140010df5  jl      loc_140010CB7
0x140010dfb  jmp     short loc_140010E1B
0x140010dfd  lea     rax, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x140010e04  mov     [rbp+var_40], rax
0x140010e08  mov     rcx, [rbp+hObject]; hObject
0x140010e0c  cmp     rcx, r13
0x140010e0f  jz      short loc_140010E1B
0x140010e11  call    cs:__imp_CloseHandle
0x140010e17  mov     [rbp+hObject], r13
0x140010e1b  mov     rcx, [rbp+var_8]
0x140010e1f  xor     rcx, rsp; StackCookie
0x140010e22  call    __security_check_cookie
0x140010e27  lea     r11, [rsp+60h+var_s0]
0x140010e2c  mov     rbx, [r11+38h]
0x140010e30  mov     rsi, [r11+40h]
0x140010e34  mov     rdi, [r11+48h]
0x140010e38  mov     rsp, r11
0x140010e3b  pop     r15
0x140010e3d  pop     r14
0x140010e3f  pop     r13
0x140010e41  pop     r12
0x140010e43  pop     rbp
0x140010e44  retn
```
