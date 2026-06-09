# IsStringProperty(ushort const *)

- ea: `0x180004f7c`
- end: `0x18000500a`
- name: `?IsStringProperty@@YAHPEBG@Z`
- size: `142`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ef0`
- `0x180032ec0`

## callees

- `0x180004f7c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004fdb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004fdb`

## pseudocode

```c
__int64 __fastcall IsStringProperty(PCNZWCH lpString1)
{
  unsigned int v2; // ebx
  __int64 v3; // rbp
  unsigned __int64 i; // rsi

  v2 = 1;
  v3 = 0;
LABEL_2:
  if ( *(&g_CTProperties + 2 * v3) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= (unsigned __int64)*(&g_CTProperties + 2 * v3 + 1) )
      {
        ++v3;
        goto LABEL_2;
      }
      if ( CompareStringW(0x7Fu, 1u, lpString1, -1, *((PCNZWCH *)*(&g_CTProperties + 2 * v3) + 2 * i), -1) == 2 )
        break;
    }
    return *((unsigned int *)*(&g_CTProperties + 2 * v3) + 4 * i + 2);
  }
  return v2;
}

```

## disassembly

```asm
0x180004f7c  push    rbx
0x180004f7e  push    rbp
0x180004f7f  push    rsi
0x180004f80  push    rdi
0x180004f81  push    r12
0x180004f83  push    r14
0x180004f85  push    r15
0x180004f87  sub     rsp, 30h
0x180004f8b  mov     r15, rcx
0x180004f8e  lea     r12, ?g_CTProperties@@3PAUCTPropInfo@@A; CTPropInfo near * g_CTProperties
0x180004f95  mov     ebx, 1
0x180004f9a  xor     ebp, ebp
0x180004f9c  mov     rdi, rbp
0x180004f9f  add     rdi, rdi
0x180004fa2  cmp     qword ptr [r12+rdi*8], 0
0x180004fa7  jz      short loc_180004FF9
0x180004fa9  xor     esi, esi
0x180004fab  cmp     rsi, [r12+rdi*8+8]
0x180004fb0  jnb     short loc_180004FEB
0x180004fb2  mov     rax, [r12+rdi*8]
0x180004fb6  mov     r14, rsi
0x180004fb9  add     r14, r14
0x180004fbc  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180004fc4  or      r9d, 0FFFFFFFFh; cchCount1
0x180004fc8  mov     r8, r15; lpString1
0x180004fcb  mov     edx, ebx; dwCmpFlags
0x180004fcd  mov     ecx, 7Fh; Locale
0x180004fd2  mov     rax, [rax+r14*8]
0x180004fd6  mov     [rsp+68h+lpString2], rax; lpString2
0x180004fdb  call    cs:__imp_CompareStringW
0x180004fe1  cmp     eax, 2
0x180004fe4  jz      short loc_180004FF0
0x180004fe6  add     rsi, rbx
0x180004fe9  jmp     short loc_180004FAB
0x180004feb  add     rbp, rbx
0x180004fee  jmp     short loc_180004F9C
0x180004ff0  mov     rax, [r12+rdi*8]
0x180004ff4  mov     ebx, [rax+r14*8+8]
0x180004ff9  mov     eax, ebx
0x180004ffb  add     rsp, 30h
0x180004fff  pop     r15
0x180005001  pop     r14
0x180005003  pop     r12
0x180005005  pop     rdi
0x180005006  pop     rsi
0x180005007  pop     rbp
0x180005008  pop     rbx
0x180005009  retn
```
