# jsonSetFunc

- ea: `0x140036f00`
- end: `0x140037045`
- name: `jsonSetFunc`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x140033fc8`
- `0x140034ef4`
- `0x1400365c0`
- `0x140036e0c`
- `0x140036f00`
- `0x140073758`
- `0x14007c6ac`
- `0x14008ac90`
- `0x14008b8d0`
- `0x14008c3e0`

## string_xrefs

- `0x140036f48`: `json_%s() needs an odd number of arguments`

## pseudocode

```c
void __fastcall jsonSetFunc(__int64 a1, int a2, _QWORD *a3)
{
  __int64 v3; // rax
  __int64 v7; // r15
  const char *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rbx
  unsigned int v15; // ebp
  _BYTE *v16; // rax
  __int64 v17; // rax
  int v18; // [rsp+78h] [rbp+10h] BYREF

  if ( a2 >= 1 )
  {
    v3 = *(_QWORD *)(a1 + 8);
    v18 = 0;
    v7 = *(_QWORD *)(v3 + 8);
    if ( (a2 & 1) != 0 )
    {
      v14 = jsonParseCached(a1, *a3, a1, a2 > 1);
      if ( v14 )
      {
        v15 = 1;
        if ( (unsigned int)a2 <= 1 )
        {
LABEL_15:
          jsonReturnJson(v14, *(_QWORD *)(v14 + 8), a1, 1);
        }
        else
        {
          while ( 1 )
          {
            LOBYTE(v13) = 1;
            v16 = (_BYTE *)sqlite3ValueText(a3[v15], v13);
            v18 = 0;
            *(_BYTE *)(v14 + 54) = 1;
            v17 = jsonLookup(v14, v16, (__int64)&v18, (__int64 *)a1);
            if ( *(_BYTE *)(v14 + 51) )
              break;
            if ( *(_BYTE *)(v14 + 50) )
              return;
            if ( v17 && (v18 || v7) )
              jsonReplaceNode((__int64 *)a1, v14, (v17 - *(_QWORD *)(v14 + 8)) >> 4, a3[v15 + 1]);
            v15 += 2;
            if ( v15 >= a2 )
              goto LABEL_15;
          }
          sqlite3_result_error_nomem(a1);
        }
      }
    }
    else
    {
      v8 = "set";
      if ( !v7 )
        v8 = "insert";
      v9 = sqlite3_mprintf("json_%s() needs an odd number of arguments", v8);
      v10 = *(_QWORD *)a1;
      LOBYTE(v11) = 1;
      *(_DWORD *)(a1 + 36) = 1;
      v12 = v9;
      sqlite3VdbeMemSetStr(v10, v9, -1, v11, -1);
      sqlite3_free(v12);
    }
  }
}

```

## disassembly

```asm
0x140036f00  cmp     edx, 1
0x140036f03  jl      locret_14003703A
0x140036f09  push    rbx
0x140036f0a  push    rbp
0x140036f0b  push    rsi
0x140036f0c  push    rdi
0x140036f0d  push    r14
0x140036f0f  push    r15
0x140036f11  sub     rsp, 38h
0x140036f15  mov     rax, [rcx+8]
0x140036f19  mov     esi, edx
0x140036f1b  mov     [rsp+68h+arg_8], 0
0x140036f23  mov     r14, r8
0x140036f26  mov     rdi, rcx
0x140036f29  mov     r15, [rax+8]
0x140036f2d  test    sil, 1
0x140036f31  jnz     short loc_140036F82
0x140036f33  lea     rax, aInsert_0; "insert"
0x140036f3a  test    r15, r15
0x140036f3d  lea     rdx, aSet; "set"
0x140036f44  cmovz   rdx, rax
0x140036f48  lea     rcx, aJsonSNeedsAnOd; "json_%s() needs an odd number of argume"...
0x140036f4f  call    sqlite3_mprintf
0x140036f54  mov     rcx, [rdi]
0x140036f57  or      r8, 0FFFFFFFFFFFFFFFFh
0x140036f5b  mov     r9b, 1
0x140036f5e  mov     [rsp+68h+var_48], r8
0x140036f63  mov     rdx, rax
0x140036f66  mov     dword ptr [rdi+24h], 1
0x140036f6d  mov     rbx, rax
0x140036f70  call    sqlite3VdbeMemSetStr
0x140036f75  mov     rcx, rbx
0x140036f78  call    sqlite3_free
0x140036f7d  jmp     loc_14003702E
0x140036f82  mov     rdx, [r14]
0x140036f85  xor     r9d, r9d
0x140036f88  cmp     esi, 1
0x140036f8b  mov     r8, rdi
0x140036f8e  setnle  r9b
0x140036f92  call    jsonParseCached
0x140036f97  mov     rbx, rax
0x140036f9a  test    rax, rax
0x140036f9d  jz      loc_14003702E
0x140036fa3  mov     ebp, 1
0x140036fa8  cmp     esi, ebp
0x140036faa  jbe     short loc_140037019
0x140036fac  mov     ecx, ebp
0x140036fae  mov     dl, 1
0x140036fb0  mov     rcx, [r14+rcx*8]
0x140036fb4  call    sqlite3ValueText
0x140036fb9  mov     [rsp+68h+arg_8], 0
0x140036fc1  lea     r8, [rsp+68h+arg_8]
0x140036fc6  mov     r9, rdi
0x140036fc9  mov     byte ptr [rbx+36h], 1
0x140036fcd  mov     rdx, rax
0x140036fd0  mov     rcx, rbx
0x140036fd3  call    jsonLookup
0x140036fd8  cmp     byte ptr [rbx+33h], 0
0x140036fdc  mov     r8, rax
0x140036fdf  jnz     short loc_14003703B
0x140036fe1  cmp     byte ptr [rbx+32h], 0
0x140036fe5  jnz     short loc_14003702E
0x140036fe7  test    rax, rax
0x140036fea  jz      short loc_140037012
0x140036fec  cmp     [rsp+68h+arg_8], 0
0x140036ff1  jnz     short loc_140036FF8
0x140036ff3  test    r15, r15
0x140036ff6  jz      short loc_140037012
0x140036ff8  sub     r8, [rbx+8]
0x140036ffc  lea     eax, [rbp+1]
0x140036fff  mov     r9, [r14+rax*8]
0x140037003  mov     rdx, rbx
0x140037006  sar     r8, 4
0x14003700a  mov     rcx, rdi
0x14003700d  call    jsonReplaceNode
0x140037012  add     ebp, 2
0x140037015  cmp     ebp, esi
0x140037017  jb      short loc_140036FAC
0x140037019  mov     rdx, [rbx+8]
0x14003701d  mov     r9d, 1
0x140037023  mov     r8, rdi
0x140037026  mov     rcx, rbx
0x140037029  call    jsonReturnJson
0x14003702e  add     rsp, 38h
0x140037032  pop     r15
0x140037034  pop     r14
0x140037036  pop     rdi
0x140037037  pop     rsi
0x140037038  pop     rbp
0x140037039  pop     rbx
0x14003703a  retn
0x14003703b  mov     rcx, rdi
0x14003703e  call    sqlite3_result_error_nomem
0x140037043  jmp     short loc_14003702E
```
