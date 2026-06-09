# Collate::Order(ushort,ushort,ushort)

- ea: `0x10046940`
- end: `0x100469e3`
- name: `?Order@Collate@@SG?AW4SortOrder@@GGG@Z`
- size: `163`
- prototype: `int __stdcall(_DWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10013330`
- `0x10013730`
- `0x10013ff0`
- `0x1001fe30`
- `0x10021d70`
- `0x10028030`
- `0x100341f0`

## callees

- `0x10046940`

## import_xrefs

- `mswstr10!__imp__DBCompareStringW@24` at `0x100469c2`
- `mswstr10!__imp__DBCompareStringW@24` at `0x100469c2`

## pseudocode

```c
int __fastcall Collate::Order(unsigned __int16 a1, __int16 a2, int a3)
{
  int v4; // esi
  int *v5; // edx
  unsigned int v6; // ecx
  unsigned int v7; // eax
  int v8; // eax
  int v9; // ecx

  v4 = a1;
  switch ( a2 )
  {
    case 1250:
      v5 = dword_10004088;
      v6 = 3;
      goto LABEL_10;
    case 1251:
      v5 = dword_10006C50;
      goto LABEL_9;
    case 1252:
      v6 = 36;
      v5 = dword_100040D0;
      goto LABEL_10;
    case 1253:
      v5 = dword_10006C58;
      goto LABEL_9;
    case 1254:
      v5 = dword_100040A0;
      goto LABEL_9;
    case 1255:
      v5 = dword_10006C60;
      goto LABEL_9;
    case 1256:
      v5 = dword_1000422C;
LABEL_9:
      v6 = 1;
LABEL_10:
      v7 = 0;
      break;
    default:
      goto LABEL_13;
  }
  do
  {
    if ( v5[2 * v7] == v4 )
      return v5[2 * v7 + 1];
    ++v7;
  }
  while ( v7 < v6 );
LABEL_13:
  v8 = DBCompareStringW(a1, 0, L"a", 1, L"a", 1);
  v9 = 256;
  if ( v8 )
    return a1;
  return v9;
}

```

## disassembly

```asm
0x10046940  mov     edi, edi
0x10046942  push    ebx
0x10046943  movzx   eax, dx
0x10046946  mov     bx, cx
0x10046949  push    esi
0x1004694a  add     eax, 0FFFFFB1Eh; switch 7 cases
0x1004694f  movzx   esi, bx
0x10046952  push    edi
0x10046953  cmp     eax, 6
0x10046956  ja      short def_10046958; jumptable 10046958 default case
0x10046958  jmp     ds:jpt_10046958[eax*4]; switch jump
0x1004695f  mov     edx, offset dword_10004088; jumptable 10046958 case 1250
0x10046964  mov     ecx, 3
0x10046969  jmp     short loc_1004699D
0x1004696b  mov     edx, offset dword_10006C50; jumptable 10046958 case 1251
0x10046970  jmp     short loc_10046998
0x10046972  mov     ecx, 24h ; '$'; jumptable 10046958 case 1252
0x10046977  mov     edx, offset dword_100040D0
0x1004697c  jmp     short loc_1004699D
0x1004697e  mov     edx, offset dword_10006C58; jumptable 10046958 case 1253
0x10046983  jmp     short loc_10046998
0x10046985  mov     edx, offset dword_100040A0; jumptable 10046958 case 1254
0x1004698a  jmp     short loc_10046998
0x1004698c  mov     edx, offset dword_10006C60; jumptable 10046958 case 1255
0x10046991  jmp     short loc_10046998
0x10046993  mov     edx, offset dword_1000422C; jumptable 10046958 case 1256
0x10046998  mov     ecx, 1
0x1004699d  xor     eax, eax
0x1004699f  mov     edi, esi
0x100469a1  cmp     [edx+eax*8], edi
0x100469a4  lea     esi, [edx+eax*8]
0x100469a7  jz      short loc_100469DA
0x100469a9  inc     eax
0x100469aa  cmp     eax, ecx
0x100469ac  jb      short loc_100469A1
0x100469ae  push    1; jumptable 10046958 default case
0x100469b0  push    offset aA; "a"
0x100469b5  push    1
0x100469b7  push    offset aA; "a"
0x100469bc  push    0
0x100469be  movzx   esi, bx
0x100469c1  push    esi
0x100469c2  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x100469c8  test    eax, eax
0x100469ca  mov     ecx, 100h
0x100469cf  pop     edi
0x100469d0  cmovnz  ecx, esi
0x100469d3  pop     esi
0x100469d4  mov     eax, ecx
0x100469d6  pop     ebx
0x100469d7  retn    4
0x100469da  mov     eax, [esi+4]
0x100469dd  pop     edi
0x100469de  pop     esi
0x100469df  pop     ebx
0x100469e0  retn    4
```
