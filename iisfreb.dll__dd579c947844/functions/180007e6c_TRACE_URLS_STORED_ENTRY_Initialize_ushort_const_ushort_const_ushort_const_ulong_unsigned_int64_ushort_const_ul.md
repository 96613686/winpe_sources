# TRACE_URLS_STORED_ENTRY::Initialize(ushort const *,ushort const *,ushort const *,ulong,unsigned __int64,ushort const *,ulong,ushort const *,FREB_FAILURE_POINT *,int)

- ea: `0x180007e6c`
- end: `0x180007f6a`
- name: `?Initialize@TRACE_URLS_STORED_ENTRY@@QEAAJPEBG00K_K0K0PEAW4FREB_FAILURE_POINT@@H@Z`
- size: `254`
- prototype: `__int64 __fastcall(TRACE_URLS_STORED_ENTRY *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int64, unsigned __int16 *, unsigned int, unsigned __int16 *, enum FREB_FAILURE_POINT *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005b28`

## callees

- `0x1800075d4`
- `0x180007e6c`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180007f05`
- `msvcrt!_wcsupr` at `0x180007f05`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007e96`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007ed3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007ee7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007e96`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007ed3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007ee7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007ebb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007ebb`

## pseudocode

```c
__int64 __fastcall TRACE_URLS_STORED_ENTRY::Initialize(
        TRACE_URLS_STORED_ENTRY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int64 a6,
        unsigned __int16 *a7,
        unsigned int a8,
        unsigned __int16 *a9,
        enum FREB_FAILURE_POINT *a10,
        int a11)
{
  int v15; // r9d
  wchar_t *v16; // rcx

  if ( *a2 == 42 || *a2 == 47 )
  {
    **((_WORD **)this + 4) = 0;
    *((_DWORD *)this + 12) = 0;
  }
  else
  {
    v15 = STRU::Copy(this, L"*/");
    if ( v15 < 0 )
      return (unsigned int)v15;
  }
  v15 = STRU::Append(this, a2);
  if ( v15 >= 0 )
  {
    v15 = STRU::Copy((TRACE_URLS_STORED_ENTRY *)((char *)this + 56), a3);
    if ( v15 >= 0 )
    {
      v15 = STRU::Copy((TRACE_URLS_STORED_ENTRY *)((char *)this + 112), a4);
      if ( v15 >= 0 )
      {
        v16 = (wchar_t *)*((_QWORD *)this + 4);
        *((_DWORD *)this + 42) = a5;
        _wcsupr(v16);
        v15 = FAILURE_DEFINITIONS_STORED_ELEMENT::Initialize(
                (TRACE_URLS_STORED_ENTRY *)((char *)this + 176),
                a6,
                a7,
                a8,
                a9,
                a11);
        if ( v15 < 0 )
          *(_DWORD *)a10 = 3;
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180007e6c  push    rbx
0x180007e6e  push    rbp
0x180007e6f  push    rsi
0x180007e70  push    rdi
0x180007e71  push    r14
0x180007e73  sub     rsp, 30h
0x180007e77  cmp     word ptr [rdx], 2Ah ; '*'
0x180007e7b  mov     r14, r9
0x180007e7e  mov     rbp, r8
0x180007e81  mov     rsi, rdx
0x180007e84  mov     rdi, rcx
0x180007e87  jz      short loc_180007EA9
0x180007e89  cmp     word ptr [rdx], 2Fh ; '/'
0x180007e8d  jz      short loc_180007EA9
0x180007e8f  lea     rdx, asc_18000E4E0; "*/"
0x180007e96  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007e9c  mov     r9d, eax
0x180007e9f  test    eax, eax
0x180007ea1  js      loc_180007F5C
0x180007ea7  jmp     short loc_180007EB5
0x180007ea9  mov     rax, [rcx+20h]
0x180007ead  xor     ebx, ebx
0x180007eaf  mov     [rax], bx
0x180007eb2  mov     [rcx+30h], ebx
0x180007eb5  mov     rdx, rsi
0x180007eb8  mov     rcx, rdi
0x180007ebb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180007ec1  mov     r9d, eax
0x180007ec4  test    eax, eax
0x180007ec6  js      loc_180007F5C
0x180007ecc  lea     rcx, [rdi+38h]
0x180007ed0  mov     rdx, rbp
0x180007ed3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007ed9  mov     r9d, eax
0x180007edc  test    eax, eax
0x180007ede  js      short loc_180007F5C
0x180007ee0  lea     rcx, [rdi+70h]
0x180007ee4  mov     rdx, r14
0x180007ee7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007eed  mov     r9d, eax
0x180007ef0  test    eax, eax
0x180007ef2  js      short loc_180007F5C
0x180007ef4  mov     eax, [rsp+58h+arg_20]
0x180007efb  mov     rcx, [rdi+20h]; String
0x180007eff  mov     [rdi+0A8h], eax
0x180007f05  call    cs:__imp__wcsupr
0x180007f0b  mov     eax, [rsp+58h+arg_50]
0x180007f12  lea     rcx, [rdi+0B0h]; this
0x180007f19  mov     r9d, [rsp+58h+arg_38]; unsigned int
0x180007f21  mov     r8, [rsp+58h+arg_30]; unsigned __int16 *
0x180007f29  mov     rdx, [rsp+58h+arg_28]; unsigned __int64
0x180007f31  mov     [rsp+58h+var_30], eax; int
0x180007f35  mov     rax, [rsp+58h+arg_40]
0x180007f3d  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180007f42  call    ?Initialize@FAILURE_DEFINITIONS_STORED_ELEMENT@@QEAAJ_KPEBGK1H@Z; FAILURE_DEFINITIONS_STORED_ELEMENT::Initialize(unsigned __int64,ushort const *,ulong,ushort const *,int)
0x180007f47  mov     r9d, eax
0x180007f4a  test    eax, eax
0x180007f4c  jns     short loc_180007F5C
0x180007f4e  mov     rax, [rsp+58h+arg_48]
0x180007f56  mov     dword ptr [rax], 3
0x180007f5c  mov     eax, r9d
0x180007f5f  add     rsp, 30h
0x180007f63  pop     r14
0x180007f65  pop     rdi
0x180007f66  pop     rsi
0x180007f67  pop     rbp
0x180007f68  pop     rbx
0x180007f69  retn
```
