# CLogIocb::GetLastRecord(_CLFS_RECORD_HEADER * &)

- ea: `0x1800106f8`
- end: `0x180010838`
- name: `?GetLastRecord@CLogIocb@@QEAAKAEAPEAU_CLFS_RECORD_HEADER@@@Z`
- size: `320`
- prototype: `unsigned int __fastcall(CLogIocb *__hidden this, struct _CLFS_RECORD_HEADER **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e8e4`
- `0x1800124f0`
- `0x180012e18`
- `0x180013178`
- `0x180014328`

## callees

- `0x1800106f8`

## pseudocode

```c
__int64 __fastcall CLogIocb::GetLastRecord(CLogIocb *this, struct _CLFS_RECORD_HEADER **a2)
{
  __int64 v3; // r9
  unsigned __int16 i; // cx
  unsigned int v6; // edx
  __int64 v7; // rdx
  char v8; // al
  unsigned int v9; // r10d
  unsigned int v10; // r8d
  unsigned int v11; // r11d
  char v12; // al

  *a2 = 0;
  v3 = *((_QWORD *)this + 8);
  if ( !*(_DWORD *)(v3 + 40) )
    return 1168;
  for ( i = 1; i < 0x10u; ++i )
  {
    v6 = *(_DWORD *)(v3 + 4LL * i + 40);
    if ( !v6 )
      break;
    if ( v6 > *(unsigned __int16 *)(v3 + 4) << 9 )
      return 6609;
  }
  v7 = v3 + *(unsigned int *)(v3 + 4LL * i + 36);
  if ( !v7 )
    return 6609;
  if ( (*(_DWORD *)v7 & 0x1FF) == 0x1FF )
    return 6609;
  v8 = *(_BYTE *)(v7 + 36);
  if ( (v8 & 0x3F) == 0 )
    return 6609;
  if ( (v8 & 0xC0) != 0 )
    return 6609;
  if ( *(_WORD *)(v7 + 34) < 0x28u )
    return 6609;
  if ( (unsigned int)*(unsigned __int16 *)(v7 + 34) > *(_DWORD *)(v7 + 24) )
    return 6609;
  if ( (v7 + (unsigned __int64)*(unsigned int *)(v7 + 24) - v3) >> 32 )
    return 6609;
  v9 = *(unsigned __int16 *)(v3 + 4) << 9;
  if ( (int)v7 + *(_DWORD *)(v7 + 24) - (int)v3 > v9 )
    return 6609;
  v10 = 0;
  v11 = 0;
  while ( (*(_BYTE *)(v7 + 36) & 0x20) == 0 )
  {
    if ( v11 >= 0x1FF )
    {
      v10 = 6609;
      break;
    }
    v7 += (*(_DWORD *)(v7 + 24) + 7) & 0xFFFFFFF8;
    if ( !v7 )
      return 6609;
    if ( (*(_DWORD *)v7 & 0x1FF) == 0x1FF )
      return 6609;
    v12 = *(_BYTE *)(v7 + 36);
    if ( (v12 & 0x3F) == 0
      || (v12 & 0xC0) != 0
      || *(_WORD *)(v7 + 34) < 0x28u
      || (unsigned int)*(unsigned __int16 *)(v7 + 34) > *(_DWORD *)(v7 + 24)
      || v7 + (unsigned __int64)*(unsigned int *)(v7 + 24) - v3 > v9 )
    {
      return 6609;
    }
    ++v11;
  }
  *a2 = (struct _CLFS_RECORD_HEADER *)v7;
  return v10;
}

```

## disassembly

```asm
0x1800106f8  push    rbx
0x1800106fa  push    rsi
0x1800106fb  push    rdi
0x1800106fc  mov     qword ptr [rdx], 0
0x180010703  mov     rbx, rdx
0x180010706  mov     r9, [rcx+40h]
0x18001070a  cmp     dword ptr [r9+28h], 0
0x18001070f  jnz     short loc_18001071B
0x180010711  mov     eax, 490h
0x180010716  jmp     loc_180010833
0x18001071b  mov     esi, 1
0x180010720  movzx   ecx, si
0x180010723  movzx   eax, cx
0x180010726  mov     edx, [r9+rax*4+28h]
0x18001072b  test    edx, edx
0x18001072d  jz      short loc_180010748
0x18001072f  movzx   eax, word ptr [r9+4]
0x180010734  shl     eax, 9
0x180010737  cmp     edx, eax
0x180010739  ja      loc_18001082E
0x18001073f  add     cx, si
0x180010742  cmp     cx, 10h
0x180010746  jb      short loc_180010723
0x180010748  movzx   eax, cx
0x18001074b  mov     edx, [r9+rax*4+24h]
0x180010750  add     rdx, r9
0x180010753  jz      loc_18001082E
0x180010759  mov     eax, [rdx]
0x18001075b  mov     edi, 1FFh
0x180010760  and     eax, edi
0x180010762  cmp     eax, edi
0x180010764  jnb     loc_18001082E
0x18001076a  mov     al, [rdx+24h]
0x18001076d  test    al, 3Fh
0x18001076f  jz      loc_18001082E
0x180010775  test    al, 0C0h
0x180010777  jnz     loc_18001082E
0x18001077d  cmp     word ptr [rdx+22h], 28h ; '('
0x180010782  jb      loc_18001082E
0x180010788  movzx   eax, word ptr [rdx+22h]
0x18001078c  cmp     eax, [rdx+18h]
0x18001078f  ja      loc_18001082E
0x180010795  mov     eax, [rdx+18h]
0x180010798  sub     rax, r9
0x18001079b  add     rax, rdx
0x18001079e  mov     rcx, rax
0x1800107a1  shr     rcx, 20h
0x1800107a5  test    ecx, ecx
0x1800107a7  jnz     loc_18001082E
0x1800107ad  movzx   r10d, word ptr [r9+4]
0x1800107b2  shl     r10d, 9
0x1800107b6  cmp     eax, r10d
0x1800107b9  ja      short loc_18001082E
0x1800107bb  xor     r8d, r8d
0x1800107be  xor     r11d, r11d
0x1800107c1  test    byte ptr [rdx+24h], 20h
0x1800107c5  jnz     short loc_180010826
0x1800107c7  cmp     r11d, edi
0x1800107ca  jnb     short loc_180010820
0x1800107cc  mov     eax, [rdx+18h]
0x1800107cf  mov     ecx, 0FFFFFFF8h
0x1800107d4  add     eax, 7
0x1800107d7  and     rax, rcx
0x1800107da  add     rdx, rax
0x1800107dd  jz      short loc_18001082E
0x1800107df  mov     eax, [rdx]
0x1800107e1  and     eax, edi
0x1800107e3  cmp     eax, edi
0x1800107e5  jnb     short loc_18001082E
0x1800107e7  mov     al, [rdx+24h]
0x1800107ea  test    al, 3Fh
0x1800107ec  jz      short loc_18001082E
0x1800107ee  test    al, 0C0h
0x1800107f0  jnz     short loc_18001082E
0x1800107f2  cmp     word ptr [rdx+22h], 28h ; '('
0x1800107f7  jb      short loc_18001082E
0x1800107f9  movzx   eax, word ptr [rdx+22h]
0x1800107fd  cmp     eax, [rdx+18h]
0x180010800  ja      short loc_18001082E
0x180010802  mov     eax, [rdx+18h]
0x180010805  sub     rax, r9
0x180010808  add     rax, rdx
0x18001080b  mov     rcx, rax
0x18001080e  shr     rcx, 20h
0x180010812  test    ecx, ecx
0x180010814  jnz     short loc_18001082E
0x180010816  cmp     eax, r10d
0x180010819  ja      short loc_18001082E
0x18001081b  add     r11d, esi
0x18001081e  jmp     short loc_1800107C1
0x180010820  mov     r8d, 19D1h
0x180010826  mov     [rbx], rdx
0x180010829  mov     eax, r8d
0x18001082c  jmp     short loc_180010833
0x18001082e  mov     eax, 19D1h
0x180010833  pop     rdi
0x180010834  pop     rsi
0x180010835  pop     rbx
0x180010836  retn
```
