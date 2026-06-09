# destroyRootPage

- ea: `0x140027e14`
- end: `0x140027edc`
- name: `destroyRootPage`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140050a40`
- `0x140055194`

## callees

- `0x140027e14`
- `0x1400560c4`
- `0x14005f5fc`
- `0x14006348c`
- `0x1400738a0`

## string_xrefs

- `0x140027e7f`: `UPDATE %Q.sqlite_master SET rootpage=%d WHERE #%d AND rootpage=#%d`

## pseudocode

```c
__int64 __fastcall destroyRootPage(__int64 a1, int a2, int a3)
{
  __int64 v3; // rbp
  int Vdbe; // eax
  char v7; // cl
  int v8; // r14d
  int v9; // edi
  unsigned __int8 v10; // cl
  __int64 v11; // rcx
  __int64 result; // rax
  __int64 v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  Vdbe = sqlite3GetVdbe(a1);
  v7 = *(_BYTE *)(a1 + 31);
  v8 = Vdbe;
  if ( v7 )
  {
    v10 = v7 - 1;
    *(_BYTE *)(a1 + 31) = v10;
    v9 = *(_DWORD *)(a1 + 4LL * v10 + 224);
  }
  else
  {
    v9 = ++*(_DWORD *)(a1 + 56);
  }
  if ( a2 < 2 )
    sqlite3ErrorMsg(a1, "corrupt schema");
  sqlite3VdbeAddOp3(v8, 144, a2, v9, v3);
  v11 = a1;
  LODWORD(v13) = v9;
  if ( *(_QWORD *)(a1 + 168) )
    v11 = *(_QWORD *)(a1 + 168);
  *(_BYTE *)(v11 + 33) = 1;
  result = sqlite3NestedParse(
             a1,
             "UPDATE %Q.sqlite_master SET rootpage=%d WHERE #%d AND rootpage=#%d",
             *(_QWORD *)(32 * v3 + *(_QWORD *)(*(_QWORD *)a1 + 32LL)),
             (unsigned int)a2,
             v13,
             v9);
  if ( v9 )
  {
    if ( *(_BYTE *)(a1 + 31) < 8u )
    {
      result = *(unsigned __int8 *)(a1 + 31);
      *(_DWORD *)(a1 + 4 * result + 224) = v9;
      ++*(_BYTE *)(a1 + 31);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140027e14  push    rbx
0x140027e16  push    rbp
0x140027e17  push    rsi
0x140027e18  push    rdi
0x140027e19  push    r14
0x140027e1b  sub     rsp, 30h
0x140027e1f  movsxd  rbp, r8d
0x140027e22  mov     esi, edx
0x140027e24  mov     rbx, rcx
0x140027e27  call    sqlite3GetVdbe
0x140027e2c  mov     cl, [rbx+1Fh]
0x140027e2f  mov     r14, rax
0x140027e32  test    cl, cl
0x140027e34  jnz     short loc_140027E3E
0x140027e36  inc     dword ptr [rbx+38h]
0x140027e39  mov     edi, [rbx+38h]
0x140027e3c  jmp     short loc_140027E4D
0x140027e3e  dec     cl
0x140027e40  movzx   eax, cl
0x140027e43  mov     [rbx+1Fh], al
0x140027e46  mov     edi, [rbx+rax*4+0E0h]
0x140027e4d  cmp     esi, 2
0x140027e50  jge     short loc_140027E61
0x140027e52  lea     rdx, aCorruptSchema; "corrupt schema"
0x140027e59  mov     rcx, rbx
0x140027e5c  call    sqlite3ErrorMsg
0x140027e61  mov     r9d, edi
0x140027e64  mov     dword ptr [rsp+58h+var_38], ebp
0x140027e68  mov     r8d, esi
0x140027e6b  mov     edx, 90h
0x140027e70  mov     rcx, r14
0x140027e73  call    sqlite3VdbeAddOp3
0x140027e78  mov     rax, [rbx+0A8h]
0x140027e7f  lea     rdx, aUpdateQSqliteM_1; "UPDATE %Q.sqlite_master SET rootpage=%d"...
0x140027e86  test    rax, rax
0x140027e89  mov     [rsp+58h+var_30], edi
0x140027e8d  mov     rcx, rbx
0x140027e90  mov     dword ptr [rsp+58h+var_38], edi
0x140027e94  cmovnz  rcx, rax
0x140027e98  mov     r9d, esi
0x140027e9b  mov     byte ptr [rcx+21h], 1
0x140027e9f  mov     rcx, rbp
0x140027ea2  mov     rax, [rbx]
0x140027ea5  shl     rcx, 5
0x140027ea9  mov     r8, [rax+20h]
0x140027ead  mov     r8, [rcx+r8]
0x140027eb1  mov     rcx, rbx
0x140027eb4  call    sqlite3NestedParse
0x140027eb9  test    edi, edi
0x140027ebb  jz      short loc_140027ED1
0x140027ebd  cmp     byte ptr [rbx+1Fh], 8
0x140027ec1  jnb     short loc_140027ED1
0x140027ec3  movzx   eax, byte ptr [rbx+1Fh]
0x140027ec7  mov     [rbx+rax*4+0E0h], edi
0x140027ece  inc     byte ptr [rbx+1Fh]
0x140027ed1  add     rsp, 30h
0x140027ed5  pop     r14
0x140027ed7  pop     rdi
0x140027ed8  pop     rsi
0x140027ed9  pop     rbp
0x140027eda  pop     rbx
0x140027edb  retn
```
