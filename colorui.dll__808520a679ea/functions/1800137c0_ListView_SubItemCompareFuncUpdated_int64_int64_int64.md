# ListView::SubItemCompareFuncUpdated(__int64,__int64,__int64)

- ea: `0x1800137c0`
- end: `0x180013899`
- name: `?SubItemCompareFuncUpdated@ListView@@CAH_J00@Z`
- size: `217`
- prototype: `__int64 __fastcall(_DWORD *, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800137c0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18001388a`
- `KERNEL32!CompareStringOrdinal` at `0x18001388a`

## pseudocode

```c
__int64 __fastcall ListView::SubItemCompareFuncUpdated(_DWORD *a1, int *a2)
{
  int v2; // ebx
  int v5; // r8d
  int v6; // r9d
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  int v10; // ecx
  unsigned int v11; // edx
  __int64 v13; // rcx
  __int64 v14; // r8

  v2 = a1[264];
  v5 = v2 != 0 ? 4 : 0;
  if ( *a1 )
  {
    switch ( *a1 )
    {
      case 1:
        ++v5;
        break;
      case 2:
        v5 += 2;
        break;
      case 3:
        v5 += 3;
        break;
      default:
        v5 = -1;
        break;
    }
  }
  v6 = a2[264];
  v7 = *a2;
  v8 = v6 != 0 ? 4 : 0;
  if ( v7 )
  {
    v9 = v7 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 == 1 )
          v8 += 3;
        else
          v8 = -1;
      }
      else
      {
        v8 += 2;
      }
    }
    else
    {
      ++v8;
    }
  }
  if ( v5 == v8 )
  {
    v13 = (__int64)(a1 + 3);
    if ( a1 == (_DWORD *)-12LL )
      v13 = 520;
    v14 = (__int64)(a2 + 3);
    if ( a2 == (int *)-12LL )
      v14 = 520;
    return (unsigned int)(CompareStringOrdinal((LPCWCH)v13, -1, (LPCWCH)v14, -1, 1) - 2);
  }
  else
  {
    v11 = v8 - v5;
    if ( v2 != v6 )
      return (unsigned int)(v2 - v6);
    return v11;
  }
}

```

## disassembly

```asm
0x1800137c0  push    rbx
0x1800137c2  sub     rsp, 30h
0x1800137c6  mov     ebx, [rcx+420h]
0x1800137cc  mov     r10, rdx
0x1800137cf  mov     r9d, [rcx]
0x1800137d2  mov     eax, ebx
0x1800137d4  neg     eax
0x1800137d6  mov     r11, rcx
0x1800137d9  sbb     r8d, r8d
0x1800137dc  and     r8d, 4
0x1800137e0  test    r9d, r9d
0x1800137e3  jz      short loc_18001380C
0x1800137e5  sub     r9d, 1
0x1800137e9  jz      short loc_180013809
0x1800137eb  sub     r9d, 1
0x1800137ef  jz      short loc_180013803
0x1800137f1  cmp     r9d, 1
0x1800137f5  jz      short loc_1800137FD
0x1800137f7  or      r8d, 0FFFFFFFFh
0x1800137fb  jmp     short loc_18001380C
0x1800137fd  add     r8d, 3
0x180013801  jmp     short loc_18001380C
0x180013803  add     r8d, 2
0x180013807  jmp     short loc_18001380C
0x180013809  inc     r8d
0x18001380c  mov     r9d, [rdx+420h]
0x180013813  mov     eax, r9d
0x180013816  mov     ecx, [r10]
0x180013819  neg     eax
0x18001381b  sbb     edx, edx
0x18001381d  and     edx, 4
0x180013820  test    ecx, ecx
0x180013822  jz      short loc_180013844
0x180013824  sub     ecx, 1
0x180013827  jz      short loc_180013842
0x180013829  sub     ecx, 1
0x18001382c  jz      short loc_18001383D
0x18001382e  cmp     ecx, 1
0x180013831  jz      short loc_180013838
0x180013833  or      edx, 0FFFFFFFFh
0x180013836  jmp     short loc_180013844
0x180013838  add     edx, 3
0x18001383b  jmp     short loc_180013844
0x18001383d  add     edx, 2
0x180013840  jmp     short loc_180013844
0x180013842  inc     edx
0x180013844  cmp     r8d, edx
0x180013847  jz      short loc_18001385B
0x180013849  sub     edx, r8d
0x18001384c  mov     ecx, ebx
0x18001384e  sub     ecx, r9d
0x180013851  cmp     ebx, r9d
0x180013854  cmovnz  edx, ecx
0x180013857  mov     eax, edx
0x180013859  jmp     short loc_180013893
0x18001385b  lea     rcx, [r11+0Ch]
0x18001385f  test    rcx, rcx
0x180013862  jnz     short loc_18001386B
0x180013864  lea     rcx, [r11+214h]; lpString1
0x18001386b  lea     r8, [r10+0Ch]
0x18001386f  test    r8, r8
0x180013872  jnz     short loc_18001387B
0x180013874  lea     r8, [r10+214h]; lpString2
0x18001387b  or      r9d, 0FFFFFFFFh; cchCount2
0x18001387f  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180013887  or      edx, r9d; cchCount1
0x18001388a  call    cs:__imp_CompareStringOrdinal
0x180013890  sub     eax, 2
0x180013893  add     rsp, 30h
0x180013897  pop     rbx
0x180013898  retn
```
