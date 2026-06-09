# renameParseSql

- ea: `0x140043994`
- end: `0x140043a7b`
- name: `renameParseSql`
- size: `231`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1400284f0`
- `0x140042df0`
- `0x140043ac0`
- `0x140044150`
- `0x140044690`

## callees

- `0x140043994`
- `0x1400525bc`
- `0x14005a5b4`
- `0x14006561c`
- `0x14006c1ac`
- `0x14008eb20`

## string_xrefs

- `0x1400439c7`: `CREATE `

## pseudocode

```c
__int64 __fastcall renameParseSql(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  unsigned int v10; // ebx
  char DbName; // al
  unsigned int v12; // eax

  sqlite3ParseObjectInit(a1, a3);
  if ( !a4 )
    return 7;
  v10 = 7;
  if ( (unsigned int)sqlite3_strnicmp(a4, "CREATE ", 7) )
    return sqlite3CorruptError(115330);
  if ( a5 )
    DbName = 1;
  else
    DbName = sqlite3FindDbName(a3, a2);
  *(_BYTE *)(a3 + 196) = DbName;
  *(_BYTE *)(a1 + 300) = 2;
  *(_QWORD *)a1 = a3;
  *(_WORD *)(a1 + 216) = 1;
  v12 = sqlite3RunParser(a1, a4);
  if ( !*(_BYTE *)(a3 + 103) )
  {
    v10 = v12;
    if ( !v12 && !*(_QWORD *)(a1 + 344) && !*(_QWORD *)(a1 + 352) && !*(_QWORD *)(a1 + 360) )
      v10 = sqlite3CorruptError(115341);
  }
  *(_BYTE *)(a3 + 196) = 0;
  return v10;
}

```

## disassembly

```asm
0x140043994  push    rbx
0x140043996  push    rbp
0x140043997  push    rsi
0x140043998  push    rdi
0x140043999  push    r12
0x14004399b  push    r14
0x14004399d  sub     rsp, 28h
0x1400439a1  mov     r14, rdx
0x1400439a4  mov     rbp, r9
0x1400439a7  mov     rdx, r8
0x1400439aa  mov     rsi, r8
0x1400439ad  mov     rdi, rcx
0x1400439b0  call    sqlite3ParseObjectInit
0x1400439b5  test    rbp, rbp
0x1400439b8  jnz     short loc_1400439C2
0x1400439ba  lea     eax, [rbp+7]
0x1400439bd  jmp     loc_140043A6E
0x1400439c2  mov     ebx, 7
0x1400439c7  lea     rdx, aCreate; "CREATE "
0x1400439ce  mov     r8d, ebx
0x1400439d1  mov     rcx, rbp
0x1400439d4  call    sqlite3_strnicmp
0x1400439d9  test    eax, eax
0x1400439db  jz      short loc_1400439EC
0x1400439dd  mov     ecx, 1C282h
0x1400439e2  call    sqlite3CorruptError
0x1400439e7  jmp     loc_140043A6E
0x1400439ec  cmp     [rsp+58h+arg_20], 0
0x1400439f4  mov     r12d, 1
0x1400439fa  jz      short loc_140043A01
0x1400439fc  mov     eax, r12d
0x1400439ff  jmp     short loc_140043A0C
0x140043a01  mov     rdx, r14
0x140043a04  mov     rcx, rsi
0x140043a07  call    sqlite3FindDbName
0x140043a0c  mov     [rsi+0C4h], al
0x140043a12  mov     rdx, rbp
0x140043a15  mov     rcx, rdi
0x140043a18  mov     byte ptr [rdi+12Ch], 2
0x140043a1f  mov     [rdi], rsi
0x140043a22  mov     [rdi+0D8h], r12w
0x140043a2a  call    sqlite3RunParser
0x140043a2f  cmp     byte ptr [rsi+67h], 0
0x140043a33  jnz     short loc_140043A65
0x140043a35  mov     ebx, eax
0x140043a37  test    eax, eax
0x140043a39  jnz     short loc_140043A65
0x140043a3b  cmp     qword ptr [rdi+158h], 0
0x140043a43  jnz     short loc_140043A65
0x140043a45  cmp     qword ptr [rdi+160h], 0
0x140043a4d  jnz     short loc_140043A65
0x140043a4f  cmp     qword ptr [rdi+168h], 0
0x140043a57  jnz     short loc_140043A65
0x140043a59  mov     ecx, 1C28Dh
0x140043a5e  call    sqlite3CorruptError
0x140043a63  mov     ebx, eax
0x140043a65  mov     byte ptr [rsi+0C4h], 0
0x140043a6c  mov     eax, ebx
0x140043a6e  add     rsp, 28h
0x140043a72  pop     r14
0x140043a74  pop     r12
0x140043a76  pop     rdi
0x140043a77  pop     rsi
0x140043a78  pop     rbp
0x140043a79  pop     rbx
0x140043a7a  retn
```
