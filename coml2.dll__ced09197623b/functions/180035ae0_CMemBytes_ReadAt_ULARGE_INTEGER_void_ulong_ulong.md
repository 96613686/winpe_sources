# CMemBytes::ReadAt(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x180035ae0`
- end: `0x180035b9d`
- name: `?ReadAt@CMemBytes@@UEAAJT_ULARGE_INTEGER@@PEAXKPEAK@Z`
- size: `189`
- prototype: `int(CMemBytes *__hidden this, union _ULARGE_INTEGER, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180035ae0`
- `0x18003f54c`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180035b2b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180035b2b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180035b4e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180035b4e`

## string_xrefs

- `0x180035b6d`: `onecoreuap\com\coml2\util\memlockbytes.cpp`

## pseudocode

```c
__int64 __fastcall CMemBytes::ReadAt(
        CMemBytes *this,
        union _ULARGE_INTEGER a2,
        void *a3,
        unsigned int a4,
        unsigned int *a5)
{
  DWORD LowPart; // ebx
  __int64 v8; // rcx
  DWORD v9; // edi
  unsigned int v10; // edi
  char *v11; // rax
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  LowPart = a2.LowPart;
  if ( !a3 )
    return 2147942487LL;
  if ( a5 )
    *a5 = 0;
  if ( a2.LowPart + a4 < a4 )
    return 2147942487LL;
  v8 = *((_QWORD *)this + 3);
  v9 = *(_DWORD *)v8;
  if ( a2.LowPart + a4 <= *(_DWORD *)v8 )
  {
    v10 = a4;
    goto LABEL_7;
  }
  if ( a2.LowPart <= v9 )
  {
    v10 = v9 - a2.LowPart;
LABEL_7:
    if ( v10 )
    {
      v11 = (char *)GlobalLock(*(HGLOBAL *)(v8 + 16));
      if ( !v11 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x134,
          (unsigned int)"onecoreuap\\com\\coml2\\util\\memlockbytes.cpp",
          (const char *)0x8003001ELL,
          v13);
        return 2147680286LL;
      }
      memcpy_0(a3, &v11[LowPart], v10);
      GlobalUnlock(*(HGLOBAL *)(*((_QWORD *)this + 3) + 16LL));
    }
    goto LABEL_10;
  }
  v10 = 0;
LABEL_10:
  if ( a5 )
    *a5 = v10;
  return 0;
}

```

## disassembly

```asm
0x180035ae0  push    rbx
0x180035ae2  push    rbp
0x180035ae3  push    rsi
0x180035ae4  push    rdi
0x180035ae5  push    r14; int
0x180035ae7  sub     rsp, 20h
0x180035aeb  mov     r14, r8
0x180035aee  mov     rbx, rdx
0x180035af1  mov     rbp, rcx
0x180035af4  test    r8, r8
0x180035af7  jz      loc_180035B8A
0x180035afd  mov     rsi, [rsp+48h+arg_20]
0x180035b02  test    rsi, rsi
0x180035b05  jz      short loc_180035B0D
0x180035b07  mov     dword ptr [rsi], 0
0x180035b0d  lea     eax, [rdx+r9]
0x180035b11  cmp     eax, r9d
0x180035b14  jb      short loc_180035B8A
0x180035b16  mov     rcx, [rcx+18h]
0x180035b1a  mov     edi, [rcx]
0x180035b1c  cmp     eax, edi
0x180035b1e  ja      short loc_180035B91
0x180035b20  mov     edi, r9d
0x180035b23  test    edi, edi
0x180035b25  jz      short loc_180035B54
0x180035b27  mov     rcx, [rcx+10h]; hMem
0x180035b2b  call    cs:__imp_GlobalLock
0x180035b31  test    rax, rax
0x180035b34  jz      short loc_180035B68
0x180035b36  mov     edx, ebx
0x180035b38  mov     rcx, r14; void *
0x180035b3b  add     rdx, rax; Src
0x180035b3e  mov     r8d, edi; Size
0x180035b41  call    memcpy_0
0x180035b46  mov     rcx, [rbp+18h]
0x180035b4a  mov     rcx, [rcx+10h]; hMem
0x180035b4e  call    cs:__imp_GlobalUnlock
0x180035b54  test    rsi, rsi
0x180035b57  jz      short loc_180035B5B
0x180035b59  mov     [rsi], edi
0x180035b5b  xor     eax, eax
0x180035b5d  add     rsp, 20h
0x180035b61  pop     r14
0x180035b63  pop     rdi
0x180035b64  pop     rsi
0x180035b65  pop     rbp
0x180035b66  pop     rbx
0x180035b67  retn
0x180035b68  mov     rcx, [rsp+48h]; this
0x180035b6d  lea     r8, aOnecoreuapComC_1; "onecoreuap\\com\\coml2\\util\\memlockby"...
0x180035b74  mov     ebx, 8003001Eh
0x180035b79  mov     edx, 134h; void *
0x180035b7e  mov     r9d, ebx; char *
0x180035b81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b86  mov     eax, ebx
0x180035b88  jmp     short loc_180035B5D
0x180035b8a  mov     eax, 80070057h
0x180035b8f  jmp     short loc_180035B5D
0x180035b91  cmp     ebx, edi
0x180035b93  jbe     short loc_180035B99
0x180035b95  xor     edi, edi
0x180035b97  jmp     short loc_180035B54
0x180035b99  sub     edi, ebx
0x180035b9b  jmp     short loc_180035B23
```
