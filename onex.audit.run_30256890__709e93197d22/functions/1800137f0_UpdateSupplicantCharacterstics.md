# UpdateSupplicantCharacterstics

- ea: `0x1800137f0`
- end: `0x180013a1f`
- name: `UpdateSupplicantCharacterstics`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180013560`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180008bd0`
- `0x180010ae0`
- `0x1800137f0`
- `0x18001b5ec`
- `0x1800214f0`

## pseudocode

```c
__int64 __fastcall UpdateSupplicantCharacterstics(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v5; // r14d
  unsigned int v7; // ebp
  int v8; // esi
  __int64 result; // rax
  unsigned int v10; // esi
  _QWORD *v11; // rcx
  __int64 v12; // rdx

  v3 = *a1;
  v5 = a2;
  v7 = *(_DWORD *)(*a1 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
  if ( (*(_BYTE *)(a3 + 8) & 1) != 0 )
    *((_DWORD *)a1 + 100) = *(_DWORD *)(a3 + 12) | *(_DWORD *)(v3 + 2784) & 0x20;
  v8 = *(_DWORD *)(a1[1] + 200);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
  if ( (*(_BYTE *)(a3 + 8) & 4) != 0 )
    *((_DWORD *)a1 + 16) = *(_DWORD *)(a3 + 20);
  if ( (*(_BYTE *)(a3 + 8) & 8) != 0 )
    *((_DWORD *)a1 + 5) = *(_DWORD *)(a3 + 24);
  if ( *(char *)(a3 + 8) < 0 )
    *((_DWORD *)a1 + 8) = *(_DWORD *)(a3 + 40);
  if ( (*(_BYTE *)(a3 + 8) & 0x40) != 0 )
    *((_DWORD *)a1 + 7) = *(_DWORD *)(a3 + 36);
  if ( (*(_BYTE *)(a3 + 8) & 0x20) != 0 )
    *((_DWORD *)a1 + 6) = *(_DWORD *)(a3 + 32);
  if ( v8 == 1 && (*(_BYTE *)(a3 + 8) & 2) != 0 )
    *((_DWORD *)a1 + 15) = *(_DWORD *)(a3 + 16);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, 0);
  result = UpdateSBackendCharacterstics(a1 + 10, a2, a3);
  v10 = result;
  if ( (_DWORD)result )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return result;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_42;
    v12 = 60;
    goto LABEL_29;
  }
  result = SupplicantSetConnProfile(a1, v5, a3);
  v10 = result;
  if ( !(_DWORD)result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v7);
    *((_DWORD *)a1 + 71) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 63, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v7);
    *((_DWORD *)a1 + 73) = 0;
    goto LABEL_41;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v12 = 61;
LABEL_29:
    WPP_SF_dd(v11[7], v12, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v7, result);
LABEL_41:
    v11 = WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_D(v11[7], 64, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x1800137f0  push    rbx
0x1800137f2  push    rbp
0x1800137f3  push    rsi
0x1800137f4  push    rdi
0x1800137f5  push    r14
0x1800137f7  push    r15
0x1800137f9  sub     rsp, 38h
0x1800137fd  mov     rsi, [rcx]
0x180013800  mov     rbx, r8
0x180013803  mov     r14d, edx
0x180013806  mov     rdi, rcx
0x180013809  mov     ebp, [rsi+14h]
0x18001380c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013813  lea     r15, WPP_GLOBAL_Control
0x18001381a  cmp     rcx, r15
0x18001381d  jz      short loc_18001383D
0x18001381f  test    dword ptr [rcx+44h], 800h
0x180013826  jz      short loc_18001383D
0x180013828  mov     rcx, [rcx+38h]
0x18001382c  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180013833  mov     edx, 3Ah ; ':'
0x180013838  call    WPP_SF_
0x18001383d  test    byte ptr [rbx+8], 1
0x180013841  jz      short loc_180013855
0x180013843  mov     eax, [rsi+0AE0h]
0x180013849  and     eax, 20h
0x18001384c  or      eax, [rbx+0Ch]
0x18001384f  mov     [rdi+190h], eax
0x180013855  mov     rax, [rdi+8]
0x180013859  mov     esi, [rax+0C8h]
0x18001385f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013866  cmp     rcx, r15
0x180013869  jz      short loc_180013889
0x18001386b  test    dword ptr [rcx+44h], 800h
0x180013872  jz      short loc_180013889
0x180013874  mov     rcx, [rcx+38h]
0x180013878  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18001387f  mov     edx, 35h ; '5'
0x180013884  call    WPP_SF_
0x180013889  test    byte ptr [rbx+8], 4
0x18001388d  jz      short loc_180013895
0x18001388f  mov     eax, [rbx+14h]
0x180013892  mov     [rdi+40h], eax
0x180013895  test    byte ptr [rbx+8], 8
0x180013899  jz      short loc_1800138A1
0x18001389b  mov     eax, [rbx+18h]
0x18001389e  mov     [rdi+14h], eax
0x1800138a1  test    byte ptr [rbx+8], 80h
0x1800138a5  jz      short loc_1800138AD
0x1800138a7  mov     eax, [rbx+28h]
0x1800138aa  mov     [rdi+20h], eax
0x1800138ad  test    byte ptr [rbx+8], 40h
0x1800138b1  jz      short loc_1800138B9
0x1800138b3  mov     eax, [rbx+24h]
0x1800138b6  mov     [rdi+1Ch], eax
0x1800138b9  test    byte ptr [rbx+8], 20h
0x1800138bd  jz      short loc_1800138C5
0x1800138bf  mov     eax, [rbx+20h]
0x1800138c2  mov     [rdi+18h], eax
0x1800138c5  cmp     esi, 1
0x1800138c8  jnz     short loc_1800138D6
0x1800138ca  test    byte ptr [rbx+8], 2
0x1800138ce  jz      short loc_1800138D6
0x1800138d0  mov     eax, [rbx+10h]
0x1800138d3  mov     [rdi+3Ch], eax
0x1800138d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138dd  cmp     rcx, r15
0x1800138e0  jz      short loc_180013903
0x1800138e2  test    dword ptr [rcx+44h], 800h
0x1800138e9  jz      short loc_180013903
0x1800138eb  mov     rcx, [rcx+38h]
0x1800138ef  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x1800138f6  mov     edx, 36h ; '6'
0x1800138fb  xor     r9d, r9d
0x1800138fe  call    WPP_SF_D
0x180013903  lea     rcx, [rdi+50h]
0x180013907  mov     r8, rbx
0x18001390a  call    UpdateSBackendCharacterstics
0x18001390f  mov     esi, eax
0x180013911  test    eax, eax
0x180013913  jz      short loc_180013950
0x180013915  mov     rcx, cs:WPP_GLOBAL_Control
0x18001391c  cmp     rcx, r15
0x18001391f  jz      loc_180013A12
0x180013925  test    byte ptr [rcx+44h], 1
0x180013929  jz      loc_1800139EA
0x18001392f  mov     edx, 3Ch ; '<'
0x180013934  mov     rcx, [rcx+38h]
0x180013938  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18001393f  mov     r9d, ebp
0x180013942  mov     [rsp+68h+var_48], eax
0x180013946  call    WPP_SF_dd
0x18001394b  jmp     loc_1800139E3
0x180013950  mov     r8, rbx
0x180013953  mov     edx, r14d
0x180013956  mov     rcx, rdi
0x180013959  call    SupplicantSetConnProfile
0x18001395e  mov     esi, eax
0x180013960  test    eax, eax
0x180013962  jz      short loc_180013981
0x180013964  mov     rcx, cs:WPP_GLOBAL_Control
0x18001396b  cmp     rcx, r15
0x18001396e  jz      loc_180013A12
0x180013974  test    byte ptr [rcx+44h], 1
0x180013978  jz      short loc_1800139EA
0x18001397a  mov     edx, 3Dh ; '='
0x18001397f  jmp     short loc_180013934
0x180013981  mov     rcx, cs:WPP_GLOBAL_Control
0x180013988  cmp     rcx, r15
0x18001398b  jz      short loc_1800139AB
0x18001398d  test    byte ptr [rcx+44h], 4
0x180013991  jz      short loc_1800139AB
0x180013993  mov     rcx, [rcx+38h]
0x180013997  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18001399e  mov     edx, 3Eh ; '>'
0x1800139a3  mov     r9d, ebp
0x1800139a6  call    WPP_SF_d
0x1800139ab  xor     ebx, ebx
0x1800139ad  mov     [rdi+11Ch], ebx
0x1800139b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139ba  cmp     rcx, r15
0x1800139bd  jz      short loc_1800139DD
0x1800139bf  test    byte ptr [rcx+44h], 4
0x1800139c3  jz      short loc_1800139DD
0x1800139c5  mov     rcx, [rcx+38h]
0x1800139c9  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x1800139d0  mov     edx, 3Fh ; '?'
0x1800139d5  mov     r9d, ebp
0x1800139d8  call    WPP_SF_d
0x1800139dd  mov     [rdi+124h], ebx
0x1800139e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139ea  cmp     rcx, r15
0x1800139ed  jz      short loc_180013A10
0x1800139ef  test    dword ptr [rcx+44h], 800h
0x1800139f6  jz      short loc_180013A10
0x1800139f8  mov     rcx, [rcx+38h]
0x1800139fc  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180013a03  mov     edx, 40h ; '@'
0x180013a08  mov     r9d, esi
0x180013a0b  call    WPP_SF_D
0x180013a10  mov     eax, esi
0x180013a12  add     rsp, 38h
0x180013a16  pop     r15
0x180013a18  pop     r14
0x180013a1a  pop     rdi
0x180013a1b  pop     rsi
0x180013a1c  pop     rbp
0x180013a1d  pop     rbx
0x180013a1e  retn
```
