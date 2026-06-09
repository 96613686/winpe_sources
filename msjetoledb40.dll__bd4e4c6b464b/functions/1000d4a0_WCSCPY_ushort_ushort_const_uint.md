# WCSCPY(ushort *,ushort const *,uint)

- ea: `0x1000d4a0`
- end: `0x1000d507`
- name: `?WCSCPY@@YGPAGPAGPBGI@Z`
- size: `103`
- prototype: `unsigned __int16 *__userpurge@<eax>(unsigned __int16 *@<edx>, unsigned __int16 *@<ecx>, unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x1000ddb0`
- `0x10010b50`
- `0x10011d40`
- `0x100122c0`
- `0x10012470`
- `0x100124f0`
- `0x100132e0`
- `0x100155d0`
- `0x1001d7f0`
- `0x100255a0`
- `0x1002ef90`
- `0x1002ff00`
- `0x1003b4c0`
- `0x1003c980`
- `0x1003f730`
- `0x1003fea0`
- `0x10041890`
- `0x10041f50`
- `0x10043a70`
- `0x10044460`
- `0x10044ee0`
- `0x100461f0`
- `0x10047070`
- `0x10048dd0`
- `0x100495d0`
- `0x10049980`
- `0x1004ab50`
- `0x1004b470`
- `0x1004bc60`

## callees

- `0x1000d4a0`

## pseudocode

```c
unsigned __int16 *__userpurge WCSCPY@<eax>(
        unsigned __int16 *a1@<edx>,
        unsigned __int16 *a2@<ecx>,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned __int16 *v5; // esi
  unsigned __int16 *result; // eax
  int v8; // edx
  unsigned __int16 *v9; // eax
  unsigned __int16 *v10; // [esp+8h] [ebp-4h]

  v5 = a3;
  result = a2;
  v10 = a2;
  if ( a3 )
  {
    if ( (unsigned int)a3 <= 0x7FFFFFFF )
    {
      v8 = 2147483646;
      do
      {
        if ( !v8 )
          break;
        if ( !*a1 )
          break;
        *a2++ = *a1++;
        --v8;
        v5 = (unsigned __int16 *)((char *)v5 - 1);
      }
      while ( v5 );
      v9 = a2 - 1;
      if ( v5 )
        v9 = a2;
      *v9 = 0;
      return v10;
    }
    else
    {
      *a2 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000d4a0  mov     edi, edi
0x1000d4a2  push    ebp
0x1000d4a3  mov     ebp, esp
0x1000d4a5  push    ecx
0x1000d4a6  push    esi
0x1000d4a7  mov     esi, [ebp+arg_0]
0x1000d4aa  mov     eax, ecx
0x1000d4ac  mov     [ebp+var_4], eax
0x1000d4af  push    edi
0x1000d4b0  mov     edi, edx
0x1000d4b2  test    esi, esi
0x1000d4b4  jz      short loc_1000D4FF
0x1000d4b6  cmp     esi, 7FFFFFFFh
0x1000d4bc  jbe     short loc_1000D4CB
0x1000d4be  xor     ecx, ecx
0x1000d4c0  pop     edi
0x1000d4c1  mov     [eax], cx
0x1000d4c4  pop     esi
0x1000d4c5  mov     esp, ebp
0x1000d4c7  pop     ebp
0x1000d4c8  retn    4
0x1000d4cb  mov     edx, 7FFFFFFEh
0x1000d4d0  push    ebx
0x1000d4d1  test    edx, edx
0x1000d4d3  jz      short loc_1000D4EE
0x1000d4d5  movzx   eax, word ptr [edi]
0x1000d4d8  mov     ebx, eax
0x1000d4da  test    ax, ax
0x1000d4dd  jz      short loc_1000D4EE
0x1000d4df  mov     [ecx], bx
0x1000d4e2  add     edi, 2
0x1000d4e5  add     ecx, 2
0x1000d4e8  dec     edx
0x1000d4e9  sub     esi, 1
0x1000d4ec  jnz     short loc_1000D4D1
0x1000d4ee  test    esi, esi
0x1000d4f0  lea     eax, [ecx-2]
0x1000d4f3  pop     ebx
0x1000d4f4  cmovnz  eax, ecx
0x1000d4f7  xor     ecx, ecx
0x1000d4f9  mov     [eax], cx
0x1000d4fc  mov     eax, [ebp+var_4]
0x1000d4ff  pop     edi
0x1000d500  pop     esi
0x1000d501  mov     esp, ebp
0x1000d503  pop     ebp
0x1000d504  retn    4
```
