# ___removelocaleref

- ea: `0x1002e6a6`
- end: `0x1002e746`
- name: `___removelocaleref`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1002e7c6`
- `0x1002ef30`

## callees

- `0x1002e6a6`

## pseudocode

```c
int __cdecl __removelocaleref(int a1)
{
  volatile signed __int32 *v1; // ecx
  volatile signed __int32 *v2; // ecx
  volatile signed __int32 *v3; // ecx
  volatile signed __int32 *v4; // ecx
  volatile signed __int32 **v5; // ecx
  int v6; // ebx
  volatile signed __int32 *v7; // edi

  if ( a1 )
  {
    _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF);
    v1 = *(volatile signed __int32 **)(a1 + 120);
    if ( v1 )
      _InterlockedExchangeAdd(v1, 0xFFFFFFFF);
    v2 = *(volatile signed __int32 **)(a1 + 128);
    if ( v2 )
      _InterlockedExchangeAdd(v2, 0xFFFFFFFF);
    v3 = *(volatile signed __int32 **)(a1 + 124);
    if ( v3 )
      _InterlockedExchangeAdd(v3, 0xFFFFFFFF);
    v4 = *(volatile signed __int32 **)(a1 + 136);
    if ( v4 )
      _InterlockedExchangeAdd(v4, 0xFFFFFFFF);
    v5 = (volatile signed __int32 **)(a1 + 28);
    v6 = 6;
    do
    {
      if ( *(v5 - 2) != __wclocalestr && *v5 )
        _InterlockedExchangeAdd(*v5, 0xFFFFFFFF);
      if ( *(v5 - 3) )
      {
        v7 = *(v5 - 1);
        if ( v7 )
          _InterlockedExchangeAdd(v7, 0xFFFFFFFF);
      }
      v5 += 4;
      --v6;
    }
    while ( v6 );
    _InterlockedExchangeAdd((volatile signed __int32 *)(*(_DWORD *)(a1 + 156) + 176), 0xFFFFFFFF);
  }
  return a1;
}

```

## disassembly

```asm
0x1002e6a6  push    ebp
0x1002e6a7  mov     ebp, esp
0x1002e6a9  mov     edx, [ebp+arg_0]
0x1002e6ac  test    edx, edx
0x1002e6ae  jz      loc_1002E742
0x1002e6b4  push    ebx
0x1002e6b5  push    esi
0x1002e6b6  or      esi, 0FFFFFFFFh
0x1002e6b9  push    edi
0x1002e6ba  mov     eax, esi
0x1002e6bc  lock xadd [edx], eax
0x1002e6c0  mov     ecx, [edx+78h]
0x1002e6c3  test    ecx, ecx
0x1002e6c5  jz      short loc_1002E6CD
0x1002e6c7  mov     eax, esi
0x1002e6c9  lock xadd [ecx], eax
0x1002e6cd  mov     ecx, [edx+80h]
0x1002e6d3  test    ecx, ecx
0x1002e6d5  jz      short loc_1002E6DD
0x1002e6d7  mov     eax, esi
0x1002e6d9  lock xadd [ecx], eax
0x1002e6dd  mov     ecx, [edx+7Ch]
0x1002e6e0  test    ecx, ecx
0x1002e6e2  jz      short loc_1002E6EA
0x1002e6e4  mov     eax, esi
0x1002e6e6  lock xadd [ecx], eax
0x1002e6ea  mov     ecx, [edx+88h]
0x1002e6f0  test    ecx, ecx
0x1002e6f2  jz      short loc_1002E6FA
0x1002e6f4  mov     eax, esi
0x1002e6f6  lock xadd [ecx], eax
0x1002e6fa  push    6
0x1002e6fc  lea     ecx, [edx+1Ch]
0x1002e6ff  pop     ebx
0x1002e700  cmp     dword ptr [ecx-8], offset ___wclocalestr
0x1002e707  jz      short loc_1002E715
0x1002e709  mov     edi, [ecx]
0x1002e70b  test    edi, edi
0x1002e70d  jz      short loc_1002E715
0x1002e70f  mov     eax, esi
0x1002e711  lock xadd [edi], eax
0x1002e715  cmp     dword ptr [ecx-0Ch], 0
0x1002e719  jz      short loc_1002E728
0x1002e71b  mov     edi, [ecx-4]
0x1002e71e  test    edi, edi
0x1002e720  jz      short loc_1002E728
0x1002e722  mov     eax, esi
0x1002e724  lock xadd [edi], eax
0x1002e728  add     ecx, 10h
0x1002e72b  dec     ebx
0x1002e72c  jnz     short loc_1002E700
0x1002e72e  mov     ecx, [edx+9Ch]
0x1002e734  add     ecx, 0B0h
0x1002e73a  lock xadd [ecx], esi
0x1002e73e  dec     esi
0x1002e73f  pop     edi
0x1002e740  pop     esi
0x1002e741  pop     ebx
0x1002e742  mov     eax, edx
0x1002e744  pop     ebp
0x1002e745  retn
```
