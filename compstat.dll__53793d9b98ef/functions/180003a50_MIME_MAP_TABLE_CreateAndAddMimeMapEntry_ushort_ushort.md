# MIME_MAP_TABLE::CreateAndAddMimeMapEntry(ushort *,ushort *)

- ea: `0x180003a50`
- end: `0x180003b61`
- name: `?CreateAndAddMimeMapEntry@MIME_MAP_TABLE@@AEAAJPEAG0@Z`
- size: `273`
- prototype: `__int64 __fastcall(MIME_MAP_TABLE *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003900`

## callees

- `0x180003a50`
- `0x180003b70`
- `0x180005460`
- `0x180008bf4`
- `0x180008c68`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003adf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003adf`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003aec`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003aec`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003ab6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003ab6`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180003acd`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x180003acd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a95`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003a95`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003a9f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003a9f`

## pseudocode

```c
__int64 __fastcall MIME_MAP_TABLE::CreateAndAddMimeMapEntry(
        MIME_MAP_TABLE *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rdi
  char *v6; // rax
  _DWORD *v7; // rbx
  unsigned int v8; // edx
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  __int64 result; // rax

  v3 = a3;
  if ( *a3 == 46 )
    v3 = a3 + 1;
  v6 = (char *)operator new(0x90u);
  v7 = v6;
  if ( !v6 )
    return 2147942408LL;
  STRU::STRU((STRU *)(v6 + 24));
  STRA::STRA((STRA *)(v7 + 20));
  v7[34] = 1;
  if ( (int)STRU::Copy((STRU *)(v7 + 6), v3) < 0 || (int)STRA::CopyWTruncate((STRA *)(v7 + 20), a2) < 0 )
    v7[34] = 0;
  *(_QWORD *)v7 = STRU::QueryStr((STRU *)(v7 + 6));
  *((_WORD *)v7 + 8) = STRU::QueryCCH((STRU *)(v7 + 6));
  *((_QWORD *)v7 + 1) = 0;
  if ( !v7[34] )
  {
    MIME_MAP_ENTRY::`scalar deleting destructor'((MIME_MAP_ENTRY *)v7, v8);
    return 2147942408LL;
  }
  v9 = *(const unsigned __int16 **)v7;
  if ( *((_DWORD *)this + 264) )
    v10 = HashString(v9, v8) % 0x83;
  else
    v10 = HashStringNoCase(v9, v8) % 0x83;
  *((_QWORD *)v7 + 1) = *((_QWORD *)this + v10 + 1);
  result = 0;
  *((_QWORD *)this + v10 + 1) = v7;
  return result;
}

```

## disassembly

```asm
0x180003a50  mov     [rsp+arg_10], rbx
0x180003a55  push    rbp
0x180003a56  push    rdi
0x180003a57  push    r14
0x180003a59  sub     rsp, 20h
0x180003a5d  cmp     word ptr [r8], 2Eh ; '.'
0x180003a62  mov     rdi, r8
0x180003a65  mov     r14, rdx
0x180003a68  mov     rbp, rcx
0x180003a6b  jnz     short loc_180003A71
0x180003a6d  add     rdi, 2
0x180003a71  mov     ecx, 90h; Size
0x180003a76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a7b  mov     rbx, rax
0x180003a7e  test    rax, rax
0x180003a81  jz      loc_180007246
0x180003a87  mov     [rsp+38h+arg_0], rsi
0x180003a8c  lea     rcx, [rax+18h]
0x180003a90  mov     [rsp+38h+arg_8], r15
0x180003a95  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003a9b  lea     rcx, [rbx+50h]
0x180003a9f  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003aa5  mov     rdx, rdi
0x180003aa8  mov     dword ptr [rbx+88h], 1
0x180003ab2  lea     rcx, [rbx+18h]
0x180003ab6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003abc  xor     edi, edi
0x180003abe  test    eax, eax
0x180003ac0  js      loc_180007212
0x180003ac6  mov     rdx, r14
0x180003ac9  lea     rcx, [rbx+50h]
0x180003acd  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x180003ad3  test    eax, eax
0x180003ad5  js      loc_180007212
0x180003adb  lea     rcx, [rbx+18h]
0x180003adf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003ae5  lea     rcx, [rbx+18h]
0x180003ae9  mov     [rbx], rax
0x180003aec  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180003af2  mov     r15, [rsp+38h+arg_8]
0x180003af7  mov     rsi, [rsp+38h+arg_0]
0x180003afc  mov     [rbx+10h], ax
0x180003b00  mov     [rbx+8], rdi
0x180003b04  cmp     [rbx+88h], edi
0x180003b0a  jz      loc_18000723E
0x180003b10  mov     rcx, [rbx]; unsigned __int16 *
0x180003b13  cmp     [rbp+420h], edi
0x180003b19  jnz     loc_18000721D
0x180003b1f  call    ?HashStringNoCase@@YAKPEBGK@Z; HashStringNoCase(ushort const *,ulong)
0x180003b24  mov     r8d, eax
0x180003b27  mov     eax, 0FA232CF3h
0x180003b2c  mul     r8d
0x180003b2f  shr     edx, 7
0x180003b32  imul    eax, edx, 83h
0x180003b38  sub     r8d, eax
0x180003b3b  lea     rcx, ds:0[r8*8]
0x180003b43  mov     rax, [rcx+rbp+8]
0x180003b48  mov     [rbx+8], rax
0x180003b4c  xor     eax, eax
0x180003b4e  mov     [rcx+rbp+8], rbx
0x180003b53  mov     rbx, [rsp+38h+arg_10]
0x180003b58  add     rsp, 20h
0x180003b5c  pop     r14
0x180003b5e  pop     rdi
0x180003b5f  pop     rbp
0x180003b60  retn
0x180007212  mov     [rbx+88h], edi
0x180007218  jmp     loc_180003ADB
0x18000721d  call    ?HashString@@YAKPEBGK@Z; HashString(ushort const *,ulong)
0x180007222  mov     r8d, eax
0x180007225  mov     eax, 0FA232CF3h
0x18000722a  mul     r8d
0x18000722d  shr     edx, 7
0x180007230  imul    ecx, edx, 83h
0x180007236  sub     r8d, ecx
0x180007239  jmp     loc_180003B3B
0x18000723e  mov     rcx, rbx; this
0x180007241  call    ??_GMIME_MAP_ENTRY@@QEAAPEAXI@Z; MIME_MAP_ENTRY::`scalar deleting destructor'(uint)
0x180007246  mov     eax, 80070008h
0x18000724b  jmp     loc_180003B53
```
