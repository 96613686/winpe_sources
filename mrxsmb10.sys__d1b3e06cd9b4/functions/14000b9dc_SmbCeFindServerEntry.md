# SmbCeFindServerEntry

- ea: `0x14000b9dc`
- end: `0x14000bab6`
- name: `SmbCeFindServerEntry`
- size: `218`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400012b4`

## callees

- `0x140001e40`
- `0x140002470`
- `0x14000b9dc`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000ba2a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000ba2a`

## pseudocode

```c
__int64 *__fastcall SmbCeFindServerEntry(PCUNICODE_STRING String1, __int64 a2, __int128 *a3)
{
  __int128 *v3; // rdi
  __int64 *v5; // rbx
  bool v6; // zf
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rcx
  __int64 *v10; // rbx
  __int128 v12; // [rsp+20h] [rbp-38h] BYREF

  v3 = &v12;
  if ( a3 )
    v3 = a3;
  v5 = 0;
  v6 = s_DbServers == (_QWORD)&s_DbServers;
  v7 = s_DbServers - 32;
  v12 = 0;
LABEL_4:
  if ( !v6 )
    v5 = (__int64 *)v7;
  while ( v5 )
  {
    if ( !RtlCompareUnicodeString(String1, (PCUNICODE_STRING)v5 + 5, 1u) )
    {
      v8 = *(_QWORD *)v3 - v5[95];
      if ( *(_QWORD *)v3 == v5[95] )
        v8 = *((_QWORD *)v3 + 1) - v5[96];
      if ( v8 )
      {
        v9 = (__int64 *)v5[4];
        v5 = 0;
        v6 = v9 == &s_DbServers;
        v7 = (__int64)(v9 - 4);
        goto LABEL_4;
      }
      MRxSmbTrackRefCount(v5, "SmbCeFindServerEntry", 176);
      SmbReferenceRecord(v5 + 99, "SmbCeFindServerEntry", 176);
      _InterlockedIncrement((volatile signed __int32 *)v5 + 2);
      return v5;
    }
    v10 = (__int64 *)v5[4];
    if ( v10 == &s_DbServers )
      v5 = 0;
    else
      v5 = v10 - 4;
  }
  return v5;
}

```

## disassembly

```asm
0x14000b9dc  push    rbx
0x14000b9de  push    rbp
0x14000b9df  push    rsi
0x14000b9e0  push    rdi
0x14000b9e1  sub     rsp, 38h
0x14000b9e5  mov     rdx, cs:s_DbServers
0x14000b9ec  lea     rdi, [rsp+58h+var_38]
0x14000b9f1  test    r8, r8
0x14000b9f4  lea     rbp, s_DbServers
0x14000b9fb  xorps   xmm0, xmm0
0x14000b9fe  mov     rsi, rcx
0x14000ba01  cmovnz  rdi, r8
0x14000ba05  xor     ebx, ebx
0x14000ba07  cmp     rdx, rbp
0x14000ba0a  lea     rax, [rdx-20h]
0x14000ba0e  movups  [rsp+58h+var_38], xmm0
0x14000ba13  cmovnz  rbx, rax
0x14000ba17  test    rbx, rbx
0x14000ba1a  jz      loc_14000BAA9
0x14000ba20  lea     rdx, [rbx+50h]; String2
0x14000ba24  mov     r8b, 1; CaseInSensitive
0x14000ba27  mov     rcx, rsi; String1
0x14000ba2a  call    cs:__imp_RtlCompareUnicodeString
0x14000ba31  nop     dword ptr [rax+rax+00h]
0x14000ba36  test    eax, eax
0x14000ba38  jnz     short loc_14000BA65
0x14000ba3a  mov     rcx, [rdi]
0x14000ba3d  sub     rcx, [rbx+2F8h]
0x14000ba44  jnz     short loc_14000BA51
0x14000ba46  mov     rcx, [rdi+8]
0x14000ba4a  sub     rcx, [rbx+300h]
0x14000ba51  test    rcx, rcx
0x14000ba54  jz      short loc_14000BA78
0x14000ba56  mov     rcx, [rbx+20h]
0x14000ba5a  xor     ebx, ebx
0x14000ba5c  cmp     rcx, rbp
0x14000ba5f  lea     rax, [rcx-20h]
0x14000ba63  jmp     short loc_14000BA13
0x14000ba65  mov     rbx, [rbx+20h]
0x14000ba69  cmp     rbx, rbp
0x14000ba6c  jnz     short loc_14000BA72
0x14000ba6e  xor     ebx, ebx
0x14000ba70  jmp     short loc_14000BA17
0x14000ba72  add     rbx, 0FFFFFFFFFFFFFFE0h
0x14000ba76  jmp     short loc_14000BA17
0x14000ba78  mov     edi, 0B0h
0x14000ba7d  lea     rdx, aSmbcefindserve; "SmbCeFindServerEntry"
0x14000ba84  mov     r8d, edi
0x14000ba87  mov     rcx, rbx
0x14000ba8a  call    MRxSmbTrackRefCount
0x14000ba8f  lea     rcx, [rbx+318h]
0x14000ba96  mov     r8d, edi
0x14000ba99  lea     rdx, aSmbcefindserve; "SmbCeFindServerEntry"
0x14000baa0  call    SmbReferenceRecord
0x14000baa5  lock inc dword ptr [rbx+8]
0x14000baa9  mov     rax, rbx
0x14000baac  add     rsp, 38h
0x14000bab0  pop     rdi
0x14000bab1  pop     rsi
0x14000bab2  pop     rbp
0x14000bab3  pop     rbx
0x14000bab4  retn
```
