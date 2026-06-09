# ISAMDBDeleteDatabase(x,x)

- ea: `0x1002a907`
- end: `0x1002a9bd`
- name: `_ISAMDBDeleteDatabase@8`
- size: `182`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x10007090`
- `0x10026c60`
- `0x100279f0`

## callees

- `0x10025ab7`
- `0x1002a907`
- `0x1002aa6e`
- `0x1002ab35`

## pseudocode

```c
void __fastcall ISAMDBDeleteDatabase(int a1, _DWORD *a2)
{
  _DWORD *i; // edi
  _DWORD *v3; // edx
  _DWORD *v4; // esi
  _DWORD *v5; // edx
  _DWORD *v6; // esi
  _DWORD *v7; // ecx
  _DWORD *v8; // esi
  _DWORD *v9; // ebx
  _DWORD *v10; // ecx
  _DWORD *v11; // esi
  _DWORD *v12; // esi
  _DWORD *v13; // eax
  _DWORD *v15; // [esp+8h] [ebp-4h]

  v15 = 0;
  for ( i = *(_DWORD **)(a1 + 8); i; i = (_DWORD *)*i )
  {
    if ( i == a2 )
    {
      v3 = (_DWORD *)i[12];
      if ( v3 )
      {
        do
        {
          v4 = (_DWORD *)*v3;
          ISAMDBDeleteTable((int)i, v3);
          v3 = v4;
        }
        while ( v4 );
      }
      v5 = (_DWORD *)i[11];
      if ( v5 )
      {
        do
        {
          v6 = (_DWORD *)*v5;
          ISAMDBDeleteDatabaseUser(i, v5);
          v5 = v6;
        }
        while ( v6 );
      }
      v7 = (_DWORD *)i[13];
      if ( v7 )
      {
        do
        {
          v8 = (_DWORD *)*v7;
          MemFree(v7);
          v7 = v8;
        }
        while ( v8 );
      }
      v9 = (_DWORD *)i[14];
      if ( v9 )
      {
        do
        {
          v10 = (_DWORD *)v9[1];
          if ( v10 )
          {
            do
            {
              v11 = (_DWORD *)*v10;
              MemFree(v10);
              v10 = v11;
            }
            while ( v11 );
          }
          v12 = (_DWORD *)*v9;
          MemFree(v9);
          v9 = v12;
        }
        while ( v12 );
      }
      v13 = (_DWORD *)*i;
      if ( v15 )
        *v15 = v13;
      else
        *(_DWORD *)(a1 + 8) = v13;
      MemFree(i);
      return;
    }
    v15 = i;
  }
}

```

## disassembly

```asm
0x1002a907  mov     edi, edi
0x1002a909  push    ebp
0x1002a90a  mov     ebp, esp
0x1002a90c  push    ecx
0x1002a90d  push    ecx
0x1002a90e  mov     eax, ecx
0x1002a910  mov     [ebp+var_4], 0
0x1002a917  push    edi
0x1002a918  mov     [ebp+var_8], eax
0x1002a91b  mov     edi, [eax+8]
0x1002a91e  jmp     short loc_1002A929
0x1002a920  cmp     edi, edx
0x1002a922  jz      short loc_1002A932
0x1002a924  mov     [ebp+var_4], edi
0x1002a927  mov     edi, [edi]
0x1002a929  test    edi, edi
0x1002a92b  jnz     short loc_1002A920
0x1002a92d  jmp     loc_1002A9BA
0x1002a932  mov     edx, [edi+30h]
0x1002a935  push    ebx
0x1002a936  push    esi
0x1002a937  test    edx, edx
0x1002a939  jz      short loc_1002A94A
0x1002a93b  mov     esi, [edx]
0x1002a93d  mov     ecx, edi
0x1002a93f  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x1002a944  mov     edx, esi
0x1002a946  test    esi, esi
0x1002a948  jnz     short loc_1002A93B
0x1002a94a  mov     edx, [edi+2Ch]
0x1002a94d  test    edx, edx
0x1002a94f  jz      short loc_1002A960
0x1002a951  mov     esi, [edx]
0x1002a953  mov     ecx, edi
0x1002a955  call    _ISAMDBDeleteDatabaseUser@8; ISAMDBDeleteDatabaseUser(x,x)
0x1002a95a  mov     edx, esi
0x1002a95c  test    esi, esi
0x1002a95e  jnz     short loc_1002A951
0x1002a960  mov     ecx, [edi+34h]
0x1002a963  test    ecx, ecx
0x1002a965  jz      short loc_1002A974
0x1002a967  mov     esi, [ecx]
0x1002a969  call    _MemFree@4; MemFree(x)
0x1002a96e  mov     ecx, esi
0x1002a970  test    esi, esi
0x1002a972  jnz     short loc_1002A967
0x1002a974  mov     ebx, [edi+38h]
0x1002a977  test    ebx, ebx
0x1002a979  jz      short loc_1002A99E
0x1002a97b  mov     ecx, [ebx+4]
0x1002a97e  test    ecx, ecx
0x1002a980  jz      short loc_1002A98F
0x1002a982  mov     esi, [ecx]
0x1002a984  call    _MemFree@4; MemFree(x)
0x1002a989  mov     ecx, esi
0x1002a98b  test    esi, esi
0x1002a98d  jnz     short loc_1002A982
0x1002a98f  mov     esi, [ebx]
0x1002a991  mov     ecx, ebx
0x1002a993  call    _MemFree@4; MemFree(x)
0x1002a998  mov     ebx, esi
0x1002a99a  test    esi, esi
0x1002a99c  jnz     short loc_1002A97B
0x1002a99e  mov     ecx, [ebp+var_4]
0x1002a9a1  mov     eax, [edi]
0x1002a9a3  pop     esi
0x1002a9a4  pop     ebx
0x1002a9a5  test    ecx, ecx
0x1002a9a7  jnz     short loc_1002A9B1
0x1002a9a9  mov     ecx, [ebp+var_8]
0x1002a9ac  mov     [ecx+8], eax
0x1002a9af  jmp     short loc_1002A9B3
0x1002a9b1  mov     [ecx], eax
0x1002a9b3  mov     ecx, edi
0x1002a9b5  call    _MemFree@4; MemFree(x)
0x1002a9ba  pop     edi
0x1002a9bb  leave
0x1002a9bc  retn
```
