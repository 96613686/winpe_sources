# jsonAppendValue

- ea: `0x1400329e4`
- end: `0x140032b12`
- name: `jsonAppendValue`
- size: `302`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140032c20`
- `0x140032df0`
- `0x140034930`
- `0x140034b00`
- `0x140035fa0`

## callees

- `0x14003275c`
- `0x1400327ac`
- `0x140032830`
- `0x1400329e4`
- `0x140035f10`
- `0x1400367dc`
- `0x140073758`
- `0x14007c6ac`
- `0x14007d3c4`
- `0x14008f900`

## string_xrefs

- `0x140032a39`: `JSON cannot hold BLOB values`

## pseudocode

```c
__int64 __fastcall jsonAppendValue(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rbx
  unsigned int v9; // eax
  double v10; // xmm0_8

  result = *(_WORD *)(a2 + 20) & 0x3F;
  v6 = a2;
  switch ( *((_BYTE *)qword_1400B5170 + result) )
  {
    case 1:
      LOBYTE(a2) = 1;
      v8 = sqlite3ValueText(v6, a2);
      v9 = sqlite3_value_bytes(v6);
      return jsonAppendRaw(a1, v8, v9);
    case 2:
      v10 = sqlite3VdbeRealValue(a2);
      return jsonPrintf(100, a1, "%!0.15g", v10);
    case 3:
      LOBYTE(a2) = 1;
      v8 = sqlite3ValueText(v6, a2);
      v9 = sqlite3_value_bytes(v6);
      if ( (*(_WORD *)(v6 + 20) & 0x800) == 0 || *(_BYTE *)(v6 + 23) != 74 )
        return jsonAppendString(a1, v8, v9);
      return jsonAppendRaw(a1, v8, v9);
    case 5:
      return jsonAppendRawNZ(a1, "null", 4);
  }
  if ( !*((_BYTE *)a1 + 33) )
  {
    v7 = *a1;
    LOBYTE(a4) = 1;
    *(_DWORD *)(v7 + 36) = 1;
    sqlite3VdbeMemSetStr(*(_QWORD *)v7, "JSON cannot hold BLOB values", -1, a4, -1);
    *((_BYTE *)a1 + 33) = 2;
    return jsonReset(a1);
  }
  return result;
}

```

## disassembly

```asm
0x1400329e4  mov     [rsp+arg_0], rbx
0x1400329e9  mov     [rsp+arg_8], rsi
0x1400329ee  push    rdi
0x1400329ef  sub     rsp, 30h
0x1400329f3  movzx   eax, word ptr [rdx+14h]
0x1400329f7  mov     rdi, rcx
0x1400329fa  and     eax, 3Fh
0x1400329fd  lea     rcx, qword_1400B5170
0x140032a04  mov     rsi, rdx
0x140032a07  movzx   r8d, byte ptr [rax+rcx]
0x140032a0c  sub     r8d, 1
0x140032a10  jz      loc_140032ADF
0x140032a16  sub     r8d, 1
0x140032a1a  jz      loc_140032AB9
0x140032a20  sub     r8d, 1
0x140032a24  jz      short loc_140032A83
0x140032a26  cmp     r8d, 2
0x140032a2a  jz      short loc_140032A6C
0x140032a2c  cmp     byte ptr [rdi+21h], 0
0x140032a30  jnz     loc_140032B02
0x140032a36  mov     rcx, [rdi]
0x140032a39  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x140032a40  or      r8, 0FFFFFFFFFFFFFFFFh
0x140032a44  mov     r9b, 1
0x140032a47  mov     [rsp+38h+var_18], r8
0x140032a4c  mov     dword ptr [rcx+24h], 1
0x140032a53  mov     rcx, [rcx]
0x140032a56  call    sqlite3VdbeMemSetStr
0x140032a5b  mov     rcx, rdi
0x140032a5e  mov     byte ptr [rdi+21h], 2
0x140032a62  call    jsonReset
0x140032a67  jmp     loc_140032B02
0x140032a6c  mov     r8d, 4
0x140032a72  lea     rdx, aNull_3; "null"
0x140032a79  mov     rcx, rdi
0x140032a7c  call    jsonAppendRawNZ
0x140032a81  jmp     short loc_140032B02
0x140032a83  mov     dl, 1
0x140032a85  mov     rcx, rsi
0x140032a88  call    sqlite3ValueText
0x140032a8d  mov     rcx, rsi
0x140032a90  mov     rbx, rax
0x140032a93  call    sqlite3_value_bytes
0x140032a98  mov     ecx, 800h
0x140032a9d  test    [rsi+14h], cx
0x140032aa1  jz      short loc_140032AA9
0x140032aa3  cmp     byte ptr [rsi+17h], 4Ah ; 'J'
0x140032aa7  jz      short loc_140032AF4
0x140032aa9  mov     r8d, eax
0x140032aac  mov     rdx, rbx
0x140032aaf  mov     rcx, rdi
0x140032ab2  call    jsonAppendString
0x140032ab7  jmp     short loc_140032B02
0x140032ab9  mov     rcx, rsi
0x140032abc  call    sqlite3VdbeRealValue
0x140032ac1  movaps  xmm3, xmm0
0x140032ac4  lea     r8, a015g; "%!0.15g"
0x140032acb  movq    r9, xmm0
0x140032ad0  mov     rdx, rdi
0x140032ad3  mov     ecx, 64h ; 'd'
0x140032ad8  call    jsonPrintf
0x140032add  jmp     short loc_140032B02
0x140032adf  mov     dl, 1
0x140032ae1  mov     rcx, rsi
0x140032ae4  call    sqlite3ValueText
0x140032ae9  mov     rcx, rsi
0x140032aec  mov     rbx, rax
0x140032aef  call    sqlite3_value_bytes
0x140032af4  mov     r8d, eax
0x140032af7  mov     rdx, rbx
0x140032afa  mov     rcx, rdi
0x140032afd  call    jsonAppendRaw
0x140032b02  mov     rbx, [rsp+38h+arg_0]
0x140032b07  mov     rsi, [rsp+38h+arg_8]
0x140032b0c  add     rsp, 30h
0x140032b10  pop     rdi
0x140032b11  retn
```
