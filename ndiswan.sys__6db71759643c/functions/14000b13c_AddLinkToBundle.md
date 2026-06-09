# AddLinkToBundle

- ea: `0x14000b13c`
- end: `0x14000b1f3`
- name: `AddLinkToBundle`
- size: `183`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000a310`
- `0x140024008`
- `0x1400274e0`

## callees

- `0x140007364`
- `0x14000b13c`

## pseudocode

```c
__int64 __fastcall AddLinkToBundle(__int64 a1, __int64 *a2)
{
  __int64 *v2; // r8
  __int64 **v4; // r9
  unsigned int v5; // ecx
  __int64 **v6; // rax
  __int64 *i; // rax
  __int64 result; // rax

  v2 = (__int64 *)(a1 + 48);
  v4 = *(__int64 ***)(a1 + 48);
  if ( v4 == (__int64 **)(a1 + 48) || (v5 = *((_DWORD *)a2 + 34), v5 >= *((_DWORD *)v4 + 34)) )
  {
    if ( v4[1] == v2 )
    {
      *a2 = (__int64)v4;
      a2[1] = (__int64)v2;
      v4[1] = a2;
      *v2 = (__int64)a2;
      goto LABEL_15;
    }
    goto LABEL_13;
  }
  if ( v5 <= *(_DWORD *)(*(_QWORD *)(a1 + 56) + 136LL) )
  {
LABEL_4:
    v6 = (__int64 **)v2[1];
    if ( *v6 == v2 )
    {
      *a2 = (__int64)v2;
      a2[1] = (__int64)v6;
      *v6 = a2;
      v2[1] = (__int64)a2;
      goto LABEL_15;
    }
LABEL_13:
    __fastfail(3u);
  }
  for ( i = *v4; ; i = (__int64 *)*i )
  {
    if ( i == v2 )
      goto LABEL_4;
    if ( v5 <= *((_DWORD *)v4 + 34) && v5 >= *((_DWORD *)i + 34) )
      break;
    v4 = (__int64 **)i;
  }
  *a2 = (__int64)i;
  a2[1] = (__int64)v4;
  i[1] = (__int64)a2;
  *v4 = a2;
LABEL_15:
  ++*(_DWORD *)(a1 + 64);
  a2[10] = a1;
  *((_DWORD *)a2 + 25) = *(_DWORD *)(a1 + 240);
  result = UpdateBundleInfo(a1);
  ++*(_DWORD *)(a1 + 24);
  return result;
}

```

## disassembly

```asm
0x14000b13c  push    rbx
0x14000b13e  sub     rsp, 20h
0x14000b142  lea     r8, [rcx+30h]
0x14000b146  mov     rbx, rcx
0x14000b149  mov     r9, [r8]
0x14000b14c  cmp     r9, r8
0x14000b14f  jz      short loc_14000B1B6
0x14000b151  mov     ecx, [rdx+88h]
0x14000b157  cmp     ecx, [r9+88h]
0x14000b15e  jnb     short loc_14000B1B6
0x14000b160  mov     rax, [rbx+38h]
0x14000b164  cmp     ecx, [rax+88h]
0x14000b16a  ja      short loc_14000B185
0x14000b16c  mov     rax, [r8+8]
0x14000b170  cmp     [rax], r8
0x14000b173  jnz     short loc_14000B1BC
0x14000b175  mov     [rdx], r8
0x14000b178  mov     [rdx+8], rax
0x14000b17c  mov     [rax], rdx
0x14000b17f  mov     [r8+8], rdx
0x14000b183  jmp     short loc_14000B1D1
0x14000b185  mov     rax, [r9]
0x14000b188  cmp     rax, r8
0x14000b18b  jz      short loc_14000B16C
0x14000b18d  cmp     ecx, [r9+88h]
0x14000b194  ja      short loc_14000B19E
0x14000b196  cmp     ecx, [rax+88h]
0x14000b19c  jnb     short loc_14000B1A6
0x14000b19e  mov     r9, rax
0x14000b1a1  mov     rax, [rax]
0x14000b1a4  jmp     short loc_14000B188
0x14000b1a6  mov     [rdx], rax
0x14000b1a9  mov     [rdx+8], r9
0x14000b1ad  mov     [rax+8], rdx
0x14000b1b1  mov     [r9], rdx
0x14000b1b4  jmp     short loc_14000B1D1
0x14000b1b6  cmp     [r9+8], r8
0x14000b1ba  jz      short loc_14000B1C3
0x14000b1bc  mov     ecx, 3
0x14000b1c1  int     29h; Win8: RtlFailFast(ecx)
0x14000b1c3  mov     [rdx], r9
0x14000b1c6  mov     [rdx+8], r8
0x14000b1ca  mov     [r9+8], rdx
0x14000b1ce  mov     [r8], rdx
0x14000b1d1  inc     dword ptr [rbx+40h]
0x14000b1d4  mov     rcx, rbx
0x14000b1d7  mov     [rdx+50h], rbx
0x14000b1db  mov     eax, [rbx+0F0h]
0x14000b1e1  mov     [rdx+64h], eax
0x14000b1e4  call    UpdateBundleInfo
0x14000b1e9  inc     dword ptr [rbx+18h]
0x14000b1ec  add     rsp, 20h
0x14000b1f0  pop     rbx
0x14000b1f1  retn
```
