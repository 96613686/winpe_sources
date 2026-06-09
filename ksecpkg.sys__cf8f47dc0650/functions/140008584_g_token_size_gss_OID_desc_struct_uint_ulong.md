# g_token_size(gss_OID_desc_struct *,uint,ulong *)

- ea: `0x140008584`
- end: `0x1400085d3`
- name: `?g_token_size@@YAJPEAUgss_OID_desc_struct@@IPEAK@Z`
- size: `79`
- prototype: `__int64 __fastcall(struct gss_OID_desc_struct *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400263c0`
- `0x140027324`

## callees

- `0x140008404`
- `0x140008584`

## pseudocode

```c
__int64 __fastcall g_token_size(struct gss_OID_desc_struct *a1, int a2, unsigned int *a3)
{
  unsigned int v3; // eax
  unsigned int v5; // edx
  int v6; // eax
  unsigned int v7; // edx
  int *v8; // r8
  unsigned int v9; // ecx
  int v10; // eax

  *a3 = 0;
  v3 = *(_DWORD *)a1 + 4;
  if ( *(_DWORD *)a1 >= 0xFFFFFFFC || (v5 = v3 + a2, v5 < v3) )
  {
    *a3 = -1;
    return 3221225621LL;
  }
  else
  {
    v6 = der_length_size(v5);
    v9 = v6 + v7 + 1;
    v10 = -1;
    if ( v9 >= v7 )
      v10 = v9;
    *v8 = v10;
    return v9 < v7 ? 0xC0000095 : 0;
  }
}

```

## disassembly

```asm
0x140008584  sub     rsp, 28h
0x140008588  mov     dword ptr [r8], 0
0x14000858f  mov     eax, [rcx]
0x140008591  add     eax, 4
0x140008594  cmp     eax, 4
0x140008597  jnb     short loc_1400085A7
0x140008599  mov     dword ptr [r8], 0FFFFFFFFh
0x1400085a0  mov     eax, 0C0000095h
0x1400085a5  jmp     short loc_1400085CD
0x1400085a7  add     edx, eax
0x1400085a9  cmp     edx, eax
0x1400085ab  jb      short loc_140008599
0x1400085ad  mov     ecx, edx; int
0x1400085af  call    ?der_length_size@@YAHH@Z; der_length_size(int)
0x1400085b4  lea     ecx, [rdx+1]
0x1400085b7  add     ecx, eax
0x1400085b9  or      eax, 0FFFFFFFFh
0x1400085bc  cmp     ecx, edx
0x1400085be  cmovnb  eax, ecx
0x1400085c1  sbb     ecx, ecx
0x1400085c3  mov     [r8], eax
0x1400085c6  mov     eax, 0C0000095h
0x1400085cb  and     eax, ecx
0x1400085cd  add     rsp, 28h
0x1400085d1  retn
```
