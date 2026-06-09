# WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)

- ea: `0x18000bd54`
- end: `0x18000bdf1`
- name: `?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z`
- size: `157`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, unsigned int, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bdf8`

## callees

- `0x180001710`
- `0x18000bd54`
- `0x18002c010`

## string_xrefs

- `0x18000bdba`: `WriteDirectoryEntry.Write(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall WriteDirectoryEntry(struct _MINIDUMP_STATE *a1, int a2, int a3, unsigned __int64 a4)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  _DWORD v8[4]; // [rsp+30h] [rbp-38h] BYREF

  if ( !a4 )
    return 0;
  if ( a4 > 0xFFFFFFFF )
    return 2147942487LL;
  v6 = *((_QWORD *)a1 + 3);
  v8[0] = a2;
  v8[2] = a3;
  v8[1] = a4;
  v7 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v6 + 32LL))(v6, v8, 12);
  if ( v7 )
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "WriteDirectoryEntry.Write(0x%x) failed, 0x%08x");
  return v7;
}

```

## disassembly

```asm
0x18000bd54  push    rbx
0x18000bd56  push    rdi
0x18000bd57  sub     rsp, 58h
0x18000bd5b  mov     rax, cs:__security_cookie
0x18000bd62  xor     rax, rsp
0x18000bd65  mov     [rsp+68h+var_28], rax
0x18000bd6a  mov     rdi, rcx
0x18000bd6d  test    r9, r9
0x18000bd70  jnz     short loc_18000BD76
0x18000bd72  xor     eax, eax
0x18000bd74  jmp     short loc_18000BDDD
0x18000bd76  mov     eax, 0FFFFFFFFh
0x18000bd7b  cmp     r9, rax
0x18000bd7e  jbe     short loc_18000BD87
0x18000bd80  mov     eax, 80070057h
0x18000bd85  jmp     short loc_18000BDDD
0x18000bd87  mov     rcx, [rcx+18h]
0x18000bd8b  mov     [rsp+68h+var_38], edx
0x18000bd8f  lea     rdx, [rsp+68h+var_38]
0x18000bd94  mov     [rsp+68h+var_30], r8d
0x18000bd99  mov     r8d, 0Ch
0x18000bd9f  mov     [rsp+68h+var_34], r9d
0x18000bda4  mov     rax, [rcx]
0x18000bda7  mov     rax, [rax+20h]
0x18000bdab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb0  mov     ebx, eax
0x18000bdb2  test    eax, eax
0x18000bdb4  jz      short loc_18000BDDB
0x18000bdb6  mov     rcx, [rdi+28h]
0x18000bdba  lea     r8, aWritedirectory_0; "WriteDirectoryEntry.Write(0x%x) failed,"...
0x18000bdc1  mov     r9d, 0Ch
0x18000bdc7  mov     [rsp+68h+var_48], ebx
0x18000bdcb  mov     rdx, [rcx]
0x18000bdce  mov     rax, [rdx+8]
0x18000bdd2  lea     edx, [r9-8]
0x18000bdd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bddb  mov     eax, ebx
0x18000bddd  mov     rcx, [rsp+68h+var_28]
0x18000bde2  xor     rcx, rsp; StackCookie
0x18000bde5  call    __security_check_cookie
0x18000bdea  add     rsp, 58h
0x18000bdee  pop     rdi
0x18000bdef  pop     rbx
0x18000bdf0  retn
```
