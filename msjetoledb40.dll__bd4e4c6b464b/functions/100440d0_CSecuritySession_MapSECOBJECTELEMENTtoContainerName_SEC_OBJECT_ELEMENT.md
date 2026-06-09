# CSecuritySession::MapSECOBJECTELEMENTtoContainerName(_SEC_OBJECT_ELEMENT &)

- ea: `0x100440d0`
- end: `0x10044120`
- name: `?MapSECOBJECTELEMENTtoContainerName@CSecuritySession@@QBEPBGAAU_SEC_OBJECT_ELEMENT@@@Z`
- size: `80`
- prototype: `const unsigned __int16 *__thiscall(CSecuritySession *__hidden this, struct _SEC_OBJECT_ELEMENT *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10042630`
- `0x100429a0`
- `0x10042c60`
- `0x10042ed0`
- `0x10043310`
- `0x10044130`

## callees

- `0x100440d0`

## pseudocode

```c
wchar_t *__thiscall CSecuritySession::MapSECOBJECTELEMENTtoContainerName(
        CSecuritySession *this,
        struct _SEC_OBJECT_ELEMENT *a2)
{
  unsigned int i; // edi
  struct _SEC_OBJECT_ELEMENT *v3; // eax
  _DWORD *v4; // edx
  unsigned int v5; // esi
  bool v6; // cf

  for ( i = 0; i < 9; ++i )
  {
    v3 = a2;
    v4 = (_DWORD *)*((_DWORD *)&rgSecObjectMap + 3 * i);
    v5 = 12;
    while ( *v4 == v3->guidObjectType.Data1 )
    {
      ++v4;
      v3 = (struct _SEC_OBJECT_ELEMENT *)((char *)v3 + 4);
      v6 = v5 < 4;
      v5 -= 4;
      if ( v6 )
        return (&off_10003784)[3 * i];
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100440d0  mov     edi, edi
0x100440d2  push    ebp
0x100440d3  mov     ebp, esp
0x100440d5  push    ebx
0x100440d6  push    esi
0x100440d7  push    edi
0x100440d8  xor     edi, edi
0x100440da  nop     word ptr [eax+eax+00h]
0x100440e0  mov     eax, [ebp+arg_0]
0x100440e3  lea     ebx, [edi+edi*2]
0x100440e6  mov     edx, ds:?rgSecObjectMap@@3QBUjetsecobjectmap@@B[ebx*4]; jetsecobjectmap const * const rgSecObjectMap
0x100440ed  mov     esi, 0Ch
0x100440f2  mov     ecx, [edx]
0x100440f4  cmp     ecx, [eax]
0x100440f6  jnz     short loc_10044111
0x100440f8  add     edx, 4
0x100440fb  add     eax, 4
0x100440fe  sub     esi, 4
0x10044101  jnb     short loc_100440F2
0x10044103  mov     eax, ds:off_10003784[ebx*4]; "Tables"
0x1004410a  pop     edi
0x1004410b  pop     esi
0x1004410c  pop     ebx
0x1004410d  pop     ebp
0x1004410e  retn    4
0x10044111  inc     edi
0x10044112  cmp     edi, 9
0x10044115  jb      short loc_100440E0
0x10044117  pop     edi
0x10044118  pop     esi
0x10044119  xor     eax, eax
0x1004411b  pop     ebx
0x1004411c  pop     ebp
0x1004411d  retn    4
```
