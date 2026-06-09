# LOCATOR::NotifyOpenPDB(wchar_t const *,PDBErrors,wchar_t const *)

- ea: `0x180087d40`
- end: `0x180087ee7`
- name: `?NotifyOpenPDB@LOCATOR@@AEAAXPEB_WW4PDBErrors@@0@Z`
- size: `423`
- prototype: `void __high(const wchar_t *, enum PDBErrors, const wchar_t *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180086bc0`
- `0x180086cd0`
- `0x180087080`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x180087d40`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180087de1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180087e7b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180087de1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180087e7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LOCATOR::NotifyOpenPDB(__int64 a1, const WCHAR *a2, unsigned int a3, __int64 a4)
{
  WCHAR *v8; // rbx
  __int64 (__fastcall *v9)(_QWORD, __int64); // rax
  __int64 v10; // rax
  DWORD FullPathNameW; // eax
  DWORD v12; // esi
  __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  PSGSI1::EnumPubsByAddr *v15; // rax
  PSGSI1::EnumPubsByAddr *v16; // rbx
  PSGSI1::EnumPubsByAddr *v17; // rcx
  void **v18; // [rsp+40h] [rbp-468h] BYREF
  __int64 v19; // [rsp+48h] [rbp-460h]
  PSGSI1::EnumPubsByAddr *v20; // [rsp+50h] [rbp-458h]
  _BYTE v21[1032]; // [rsp+58h] [rbp-450h] BYREF

  v8 = 0;
  if ( !*(_BYTE *)(a1 + 2120) )
  {
    *(_BYTE *)(a1 + 2120) = 1;
    v9 = *(__int64 (__fastcall **)(_QWORD, __int64))(a1 + 2064);
    if ( v9 )
      v10 = v9(*(_QWORD *)(a1 + 2056), 2);
    else
      v10 = 0;
    *(_QWORD *)(a1 + 2128) = v10;
  }
  if ( *(_QWORD *)(a1 + 2128) )
  {
    v18 = &SafeStackAllocator<1024>::`vftable';
    v20 = 0;
    v19 = 0;
    FullPathNameW = GetFullPathNameW(a2, 0, 0, 0);
    v12 = FullPathNameW;
    if ( !FullPathNameW )
      goto LABEL_16;
    v13 = 2LL * FullPathNameW;
    if ( *v18 == SafeStackAllocator<1024>::AllocBytes )
    {
      v14 = (v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( 1024 - v19 < v14 )
      {
        v15 = (PSGSI1::EnumPubsByAddr *)operator new[](v14 + 8, (const struct std::nothrow_t *)&std::nothrow);
        if ( v15 )
        {
          *(_QWORD *)v15 = v20;
          v20 = v15;
          v8 = (WCHAR *)((char *)v15 + 8);
        }
      }
      else
      {
        v8 = (WCHAR *)&v21[v19];
        v19 += v14;
      }
    }
    else
    {
      v8 = (WCHAR *)((__int64 (__fastcall *)(void ***, __int64))*v18)(&v18, v13);
    }
    if ( !v8 || !GetFullPathNameW(a2, v12, v8, 0) )
LABEL_16:
      v8 = (WCHAR *)a2;
    (*(void (__fastcall **)(_QWORD, WCHAR *, _QWORD, __int64))(a1 + 2128))(*(_QWORD *)(a1 + 2056), v8, a3, a4);
    v18 = &SafeStackAllocator<1024>::`vftable';
    v16 = v20;
    while ( v16 )
    {
      v17 = v16;
      v16 = *(PSGSI1::EnumPubsByAddr **)v16;
      PSGSI1::EnumPubsByAddr::release(v17);
    }
  }
}

```

## disassembly

```asm
0x180087d40  push    rbx
0x180087d42  push    rbp
0x180087d43  push    rsi
0x180087d44  push    rdi
0x180087d45  push    r12
0x180087d47  push    r14
0x180087d49  push    r15
0x180087d4b  sub     rsp, 470h
0x180087d52  mov     [rsp+4A8h+var_478], 0FFFFFFFFFFFFFFFEh
0x180087d5b  mov     rax, cs:__security_cookie
0x180087d62  xor     rax, rsp
0x180087d65  mov     [rsp+4A8h+var_48], rax
0x180087d6d  mov     r15, r9
0x180087d70  mov     r14d, r8d
0x180087d73  mov     rbp, rdx
0x180087d76  mov     rdi, rcx
0x180087d79  xor     ebx, ebx
0x180087d7b  cmp     [rcx+848h], bl
0x180087d81  jnz     short loc_180087DB3
0x180087d83  mov     byte ptr [rcx+848h], 1
0x180087d8a  mov     rax, [rcx+810h]
0x180087d91  test    rax, rax
0x180087d94  jnz     short loc_180087D9A
0x180087d96  mov     eax, ebx
0x180087d98  jmp     short loc_180087DAC
0x180087d9a  mov     edx, 2
0x180087d9f  mov     rcx, [rcx+808h]
0x180087da6  call    cs:__guard_dispatch_icall_fptr
0x180087dac  mov     [rdi+850h], rax
0x180087db3  cmp     [rdi+850h], rbx
0x180087dba  jz      loc_180087EC5
0x180087dc0  lea     r12, ??_7?$SafeStackAllocator@$0EAA@@@6B@; const SafeStackAllocator<1024>::`vftable'
0x180087dc7  mov     [rsp+4A8h+var_468], r12
0x180087dcc  mov     [rsp+4A8h+var_458], rbx
0x180087dd1  mov     [rsp+4A8h+var_460], rbx
0x180087dd6  xor     r9d, r9d; lpFilePart
0x180087dd9  xor     r8d, r8d; lpBuffer
0x180087ddc  xor     edx, edx; nBufferLength
0x180087dde  mov     rcx, rbp; lpFileName
0x180087de1  call    cs:__imp_GetFullPathNameW
0x180087de7  mov     esi, eax
0x180087de9  test    eax, eax
0x180087deb  jz      loc_180087E85
0x180087df1  mov     rcx, [rsp+4A8h+var_468]
0x180087df6  mov     rax, [rcx]
0x180087df9  lea     rdx, [rsi+rsi]
0x180087dfd  lea     rcx, ?AllocBytes@?$SafeStackAllocator@$0EAA@@@UEAAPEAX_K@Z; SafeStackAllocator<1024>::AllocBytes(unsigned __int64)
0x180087e04  cmp     rax, rcx
0x180087e07  jnz     short loc_180087E5D
0x180087e09  add     rdx, 7
0x180087e0d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180087e11  mov     eax, 400h
0x180087e16  mov     rcx, [rsp+4A8h+var_460]
0x180087e1b  sub     rax, rcx
0x180087e1e  cmp     rax, rdx
0x180087e21  jb      short loc_180087E35
0x180087e23  lea     rbx, [rsp+4A8h+var_450]
0x180087e28  add     rbx, rcx
0x180087e2b  add     rcx, rdx
0x180087e2e  mov     [rsp+4A8h+var_460], rcx
0x180087e33  jmp     short loc_180087E6B
0x180087e35  lea     rcx, [rdx+8]; unsigned __int64
0x180087e39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180087e40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180087e45  test    rax, rax
0x180087e48  jz      short loc_180087E6B
0x180087e4a  mov     rcx, [rsp+4A8h+var_458]
0x180087e4f  mov     [rax], rcx
0x180087e52  mov     [rsp+4A8h+var_458], rax
0x180087e57  lea     rbx, [rax+8]
0x180087e5b  jmp     short loc_180087E6B
0x180087e5d  lea     rcx, [rsp+4A8h+var_468]
0x180087e62  call    cs:__guard_dispatch_icall_fptr
0x180087e68  mov     rbx, rax
0x180087e6b  test    rbx, rbx
0x180087e6e  jz      short loc_180087E85
0x180087e70  xor     r9d, r9d; lpFilePart
0x180087e73  mov     r8, rbx; lpBuffer
0x180087e76  mov     edx, esi; nBufferLength
0x180087e78  mov     rcx, rbp; lpFileName
0x180087e7b  call    cs:__imp_GetFullPathNameW
0x180087e81  test    eax, eax
0x180087e83  jnz     short loc_180087E88
0x180087e85  mov     rbx, rbp
0x180087e88  mov     r9, r15
0x180087e8b  mov     r8d, r14d
0x180087e8e  mov     rdx, rbx
0x180087e91  mov     rcx, [rdi+808h]
0x180087e98  mov     rax, [rdi+850h]
0x180087e9f  call    cs:__guard_dispatch_icall_fptr
0x180087ea5  nop
0x180087ea6  mov     [rsp+4A8h+var_468], r12
0x180087eab  mov     rbx, [rsp+4A8h+var_458]
0x180087eb0  test    rbx, rbx
0x180087eb3  jz      short loc_180087EC5
0x180087eb5  mov     rcx, rbx; this
0x180087eb8  mov     rbx, [rbx]
0x180087ebb  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180087ec0  test    rbx, rbx
0x180087ec3  jnz     short loc_180087EB5
0x180087ec5  mov     rcx, [rsp+4A8h+var_48]
0x180087ecd  xor     rcx, rsp; StackCookie
0x180087ed0  call    __security_check_cookie
0x180087ed5  add     rsp, 470h
0x180087edc  pop     r15
0x180087ede  pop     r14
0x180087ee0  pop     r12
0x180087ee2  pop     rdi
0x180087ee3  pop     rsi
0x180087ee4  pop     rbp
0x180087ee5  pop     rbx
0x180087ee6  retn
```
