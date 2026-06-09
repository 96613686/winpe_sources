# SEARCH_RESULT::Create(ushort const *,ushort const *,long,MULTISZ *)

- ea: `0x1800466e8`
- end: `0x180046827`
- name: `?Create@SEARCH_RESULT@@QEAAJPEBG0JPEAVMULTISZ@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(SEARCH_RESULT *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180046f0c`

## callees

- `0x18001c250`
- `0x18002d938`
- `0x1800466e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046783`
- `iisutil!?QueryStringCount@MULTISZ@@QEBAKXZ` at `0x18004675c`
- `iisutil!?QueryStringCount@MULTISZ@@QEBAKXZ` at `0x18004675c`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800467fa`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800467fa`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800467e7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800467e7`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180046779`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180046779`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046714`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004672b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800467d8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046714`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004672b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800467d8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800467c4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800467c4`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800467a4`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800467a4`

## pseudocode

```c
__int64 __fastcall SEARCH_RESULT::Create(
        SEARCH_RESULT *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        struct MULTISZ *a5)
{
  int v8; // ebx
  unsigned int StringCount; // eax
  BUFFER *v10; // r15
  signed int LastError; // eax
  __int64 v12; // r14
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v14; // rbp
  STRU *v15; // rax
  STRU *v16; // rax
  STRU *v17; // rdi
  unsigned int v18; // edx

  if ( a2 && a3 )
  {
    v8 = STRU::Copy((SEARCH_RESULT *)((char *)this + 24), a2);
    if ( v8 >= 0 )
    {
      v8 = STRU::Copy((SEARCH_RESULT *)((char *)this + 80), a3);
      if ( v8 >= 0 )
      {
        *((_DWORD *)this + 34) = a4;
        if ( a5 )
        {
          StringCount = MULTISZ::QueryStringCount(a5);
          v10 = (SEARCH_RESULT *)((char *)this + 144);
          *((_DWORD *)this + 35) = StringCount;
          if ( BUFFER::Resize((SEARCH_RESULT *)((char *)this + 144), 8 * StringCount) )
          {
            v12 = 0;
            for ( i = MULTISZ::First(a5); ; i = MULTISZ::Next(a5, v14) )
            {
              v14 = i;
              if ( !i )
                break;
              v15 = (STRU *)operator new(0x38u);
              if ( !v15 )
                return (unsigned int)-2147024888;
              v16 = STRU::STRU(v15);
              if ( (v17 = v16) == 0 )
                return (unsigned int)-2147024888;
              v8 = STRU::Copy(v16, v14);
              if ( v8 < 0 )
              {
                STRU::`scalar deleting destructor'(v17, v18);
                return (unsigned int)v8;
              }
              *((_QWORD *)BUFFER::QueryPtr(v10) + v12) = v17;
              v12 = (unsigned int)(v12 + 1);
            }
          }
          else
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              return (unsigned __int16)LastError | 0x80070000;
          }
        }
        else
        {
          *((_DWORD *)this + 35) = 0;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800466e8  push    rbx
0x1800466ea  push    rbp
0x1800466eb  push    rsi
0x1800466ec  push    rdi
0x1800466ed  push    r14
0x1800466ef  push    r15
0x1800466f1  sub     rsp, 28h
0x1800466f5  mov     ebp, r9d
0x1800466f8  mov     rsi, r8
0x1800466fb  mov     rdi, rcx
0x1800466fe  test    rdx, rdx
0x180046701  jz      loc_180046813
0x180046707  test    r8, r8
0x18004670a  jz      loc_180046813
0x180046710  add     rcx, 18h
0x180046714  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004671a  mov     ebx, eax
0x18004671c  test    eax, eax
0x18004671e  js      loc_180046818
0x180046724  lea     rcx, [rdi+50h]
0x180046728  mov     rdx, rsi
0x18004672b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180046731  mov     ebx, eax
0x180046733  test    eax, eax
0x180046735  js      loc_180046818
0x18004673b  mov     rsi, [rsp+58h+arg_20]
0x180046743  mov     [rdi+88h], ebp
0x180046749  test    rsi, rsi
0x18004674c  jnz     short loc_180046759
0x18004674e  mov     [rdi+8Ch], esi
0x180046754  jmp     loc_180046818
0x180046759  mov     rcx, rsi
0x18004675c  call    cs:__imp_?QueryStringCount@MULTISZ@@QEBAKXZ; MULTISZ::QueryStringCount(void)
0x180046762  lea     r15, [rdi+90h]
0x180046769  mov     [rdi+8Ch], eax
0x18004676f  mov     rcx, r15
0x180046772  lea     edx, ds:0[rax*8]
0x180046779  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18004677f  test    al, al
0x180046781  jnz     short loc_18004679E
0x180046783  call    cs:__imp_GetLastError
0x180046789  mov     ebx, eax
0x18004678b  test    eax, eax
0x18004678d  jle     loc_180046818
0x180046793  movzx   ebx, ax
0x180046796  or      ebx, 80070000h
0x18004679c  jmp     short loc_180046818
0x18004679e  xor     r14d, r14d
0x1800467a1  mov     rcx, rsi
0x1800467a4  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x1800467aa  mov     rbp, rax
0x1800467ad  test    rax, rax
0x1800467b0  jz      short loc_180046818
0x1800467b2  mov     ecx, 38h ; '8'; Size
0x1800467b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800467bc  test    rax, rax
0x1800467bf  jz      short loc_18004680C
0x1800467c1  mov     rcx, rax
0x1800467c4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800467ca  mov     rdi, rax
0x1800467cd  test    rax, rax
0x1800467d0  jz      short loc_18004680C
0x1800467d2  mov     rdx, rbp
0x1800467d5  mov     rcx, rax
0x1800467d8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800467de  mov     ebx, eax
0x1800467e0  test    eax, eax
0x1800467e2  js      short loc_180046802
0x1800467e4  mov     rcx, r15
0x1800467e7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800467ed  mov     rdx, rbp
0x1800467f0  mov     rcx, rsi
0x1800467f3  mov     [rax+r14*8], rdi
0x1800467f7  inc     r14d
0x1800467fa  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x180046800  jmp     short loc_1800467AA
0x180046802  mov     rcx, rdi; this
0x180046805  call    ??_GSTRU@@QEAAPEAXI@Z; STRU::`scalar deleting destructor'(uint)
0x18004680a  jmp     short loc_180046818
0x18004680c  mov     ebx, 80070008h
0x180046811  jmp     short loc_180046818
0x180046813  mov     ebx, 80070057h
0x180046818  mov     eax, ebx
0x18004681a  add     rsp, 28h
0x18004681e  pop     r15
0x180046820  pop     r14
0x180046822  pop     rdi
0x180046823  pop     rsi
0x180046824  pop     rbp
0x180046825  pop     rbx
0x180046826  retn
```
