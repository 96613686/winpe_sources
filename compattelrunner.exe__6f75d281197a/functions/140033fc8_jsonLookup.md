# jsonLookup

- ea: `0x140033fc8`
- end: `0x140034060`
- name: `jsonLookup`
- size: `152`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140032d10`
- `0x1400339a0`
- `0x1400360c0`
- `0x1400364c0`
- `0x140036f00`
- `0x140037050`

## callees

- `0x140033fc8`
- `0x140034114`
- `0x14007c6ac`
- `0x14008ac90`
- `0x14008b8d0`
- `0x14008c3e0`

## string_xrefs

- `0x14003400f`: `JSON path error near '%q'`

## pseudocode

```c
__int64 __fastcall jsonLookup(__int64 a1, _BYTE *a2, __int64 a3, __int64 *a4)
{
  __int64 v5; // r9
  __int64 result; // rax
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 v11; // rcx
  _BYTE *v12; // [rsp+48h] [rbp+10h] BYREF

  v12 = 0;
  v5 = a3;
  if ( !a2 )
    return 0;
  if ( *a2 != 36 || (result = jsonLookupStep(a1, 0, (int)a2 + 1, a3, (__int64)&v12), (a2 = v12) != 0) )
  {
    ++*(_BYTE *)(a1 + 50);
    v8 = sqlite3_mprintf("JSON path error near '%q'", a2, a3, v5);
    v10 = v8;
    if ( v8 )
    {
      v11 = *a4;
      LOBYTE(v9) = 1;
      *((_DWORD *)a4 + 9) = 1;
      sqlite3VdbeMemSetStr(v11, v8, -1, v9, -1);
      sqlite3_free(v10);
    }
    else
    {
      sqlite3_result_error_nomem(a4);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140033fc8  mov     r11, rsp
0x140033fcb  mov     [r11+8], rbx
0x140033fcf  push    rdi
0x140033fd0  sub     rsp, 30h
0x140033fd4  mov     qword ptr [r11+10h], 0
0x140033fdc  mov     rbx, r9
0x140033fdf  mov     r9, r8
0x140033fe2  mov     rdi, rcx
0x140033fe5  test    rdx, rdx
0x140033fe8  jz      short loc_140034053
0x140033fea  cmp     byte ptr [rdx], 24h ; '$'
0x140033fed  jnz     short loc_14003400C
0x140033fef  lea     r8, [rdx+1]
0x140033ff3  xor     edx, edx
0x140033ff5  lea     rax, [r11+10h]
0x140033ff9  mov     [r11-18h], rax
0x140033ffd  call    jsonLookupStep
0x140034002  mov     rdx, [rsp+38h+arg_8]
0x140034007  test    rdx, rdx
0x14003400a  jz      short loc_140034055
0x14003400c  inc     byte ptr [rdi+32h]
0x14003400f  lea     rcx, aJsonPathErrorN; "JSON path error near '%q'"
0x140034016  call    sqlite3_mprintf
0x14003401b  mov     rdi, rax
0x14003401e  test    rax, rax
0x140034021  jz      short loc_14003404B
0x140034023  mov     rcx, [rbx]
0x140034026  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003402a  mov     r9b, 1
0x14003402d  mov     [rsp+38h+var_18], r8
0x140034032  mov     rdx, rax
0x140034035  mov     dword ptr [rbx+24h], 1
0x14003403c  call    sqlite3VdbeMemSetStr
0x140034041  mov     rcx, rdi
0x140034044  call    sqlite3_free
0x140034049  jmp     short loc_140034053
0x14003404b  mov     rcx, rbx
0x14003404e  call    sqlite3_result_error_nomem
0x140034053  xor     eax, eax
0x140034055  mov     rbx, [rsp+38h+arg_0]
0x14003405a  add     rsp, 30h
0x14003405e  pop     rdi
0x14003405f  retn
```
