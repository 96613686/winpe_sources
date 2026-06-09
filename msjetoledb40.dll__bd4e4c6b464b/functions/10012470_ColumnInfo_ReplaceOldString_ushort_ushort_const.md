# ColumnInfo::ReplaceOldString(ushort * *,ushort const *)

- ea: `0x10012470`
- end: `0x100124e2`
- name: `?ReplaceOldString@ColumnInfo@@AAEJPAPAGPBG@Z`
- size: `114`
- prototype: `int __thiscall(ColumnInfo *__hidden this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100123d0`
- `0x100131d0`

## callees

- `0x1000d4a0`
- `0x10012470`
- `0x1004ce5d`
- `0x1004cea1`

## pseudocode

```c
int __userpurge ColumnInfo::ReplaceOldString@<eax>(
        const unsigned __int16 *a1@<esi>,
        unsigned __int16 **a2,
        unsigned __int16 *a3)
{
  unsigned __int16 *v4; // eax
  unsigned __int16 *v6; // esi
  unsigned __int16 *v7; // eax
  unsigned int v10; // [esp+0h] [ebp-8h]

  if ( *a2 )
  {
    operator delete(*a2);
    *a2 = 0;
  }
  if ( a3 )
  {
    v4 = a3;
    while ( *v4++ )
      ;
    v6 = (unsigned __int16 *)(v4 - (a3 + 1) + 1);
    v7 = (unsigned __int16 *)operator new(saturated_mul(2u, (unsigned int)v6));
    *a2 = v7;
    WCSCPY(a3, v7, v6, a1, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x10012470  mov     edi, edi
0x10012472  push    ebp
0x10012473  mov     ebp, esp
0x10012475  push    ebx
0x10012476  push    edi; unsigned int
0x10012477  mov     edi, [ebp+arg_0]
0x1001247a  mov     eax, [edi]
0x1001247c  test    eax, eax
0x1001247e  jz      short loc_1001248F
0x10012480  push    eax; Block
0x10012481  call    ??3@YAXPAX@Z; operator delete(void *)
0x10012486  add     esp, 4
0x10012489  mov     dword ptr [edi], 0
0x1001248f  mov     ebx, [ebp+arg_4]
0x10012492  test    ebx, ebx
0x10012494  jz      short loc_100124DA
0x10012496  mov     eax, ebx
0x10012498  lea     edx, [eax+2]
0x1001249b  nop     dword ptr [eax+eax+00h]
0x100124a0  mov     cx, [eax]
0x100124a3  add     eax, 2
0x100124a6  test    cx, cx
0x100124a9  jnz     short loc_100124A0
0x100124ab  sub     eax, edx
0x100124ad  mov     ecx, 2
0x100124b2  sar     eax, 1
0x100124b4  push    esi; unsigned __int16 *
0x100124b5  lea     esi, [eax+1]
0x100124b8  mov     eax, esi
0x100124ba  mul     ecx
0x100124bc  mov     ecx, 0FFFFFFFFh
0x100124c1  cmovb   eax, ecx
0x100124c4  push    eax; Size
0x100124c5  call    ??2@YAPAXI@Z; operator new(uint)
0x100124ca  add     esp, 4
0x100124cd  mov     [edi], eax
0x100124cf  mov     edx, ebx
0x100124d1  mov     ecx, eax
0x100124d3  push    esi; unsigned __int16 *
0x100124d4  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x100124d9  pop     esi
0x100124da  xor     eax, eax
0x100124dc  pop     edi
0x100124dd  pop     ebx
0x100124de  pop     ebp
0x100124df  retn    8
```
