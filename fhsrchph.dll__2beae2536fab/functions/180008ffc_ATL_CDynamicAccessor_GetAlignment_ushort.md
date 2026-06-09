# ATL::CDynamicAccessor::GetAlignment(ushort)

- ea: `0x180008ffc`
- end: `0x1800090c1`
- name: `?GetAlignment@CDynamicAccessor@ATL@@SA_KG@Z`
- size: `197`
- prototype: `unsigned __int64 __fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007dac`

## callees

- `0x180008ffc`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CDynamicAccessor::GetAlignment(unsigned __int16 a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx

  if ( (a1 & 0x4000) != 0 || (a1 & 0x2000) != 0 || (a1 & 0x1000) != 0 )
    return 8;
  if ( a1 > 0x48u )
  {
    v17 = a1 - 128;
    if ( !v17 )
      return 1;
    v18 = v17 - 1;
    if ( !v18 )
      return 1;
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
        return 1;
      v21 = v20 - 2;
      if ( v21 )
      {
        v8 = v21 - 1;
        if ( v8 )
          goto LABEL_16;
      }
    }
    return 2;
  }
  if ( a1 == 72 )
    return 4;
  if ( a1 > 0xBu )
  {
    v10 = a1 - 12;
    if ( !v10 )
      return 8;
    v11 = v10 - 1;
    if ( !v11 )
      return 8;
    v12 = v11 - 1;
    if ( !v12 )
      return 8;
    v13 = v12 - 2;
    if ( !v13 )
      return 1;
    v14 = v13 - 1;
    if ( !v14 )
      return 1;
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( !v16 )
        return 4;
      if ( (unsigned int)(v16 - 1) > 1 )
        return 8;
      return 1;
    }
    return 2;
  }
  if ( a1 == 11 )
    return 2;
  v1 = a1 - 2;
  if ( !v1 )
    return 2;
  v2 = v1 - 1;
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( !v4 )
        return 8;
      v5 = v4 - 1;
      if ( !v5 )
        return 8;
      v6 = v5 - 1;
      if ( !v6 )
        return 8;
      v7 = v6 - 1;
      if ( !v7 )
        return 8;
      v8 = v7 - 1;
      if ( !v8 )
        return 8;
LABEL_16:
      if ( v8 != 1 )
        return 8;
    }
  }
  return 4;
}

```

## disassembly

```asm
0x180008ffc  bt      cx, 0Eh
0x180009001  jb      short loc_18000905F
0x180009003  bt      cx, 0Dh
0x180009008  jb      short loc_18000905F
0x18000900a  bt      cx, 0Ch
0x18000900f  jb      short loc_18000905F
0x180009011  movzx   ecx, cx
0x180009014  mov     edx, 2
0x180009019  cmp     ecx, 48h ; 'H'
0x18000901c  ja      short loc_180009097
0x18000901e  jz      loc_1800090BB
0x180009024  cmp     ecx, 0Bh
0x180009027  ja      short loc_180009065
0x180009029  jz      loc_1800090B7
0x18000902f  sub     ecx, edx
0x180009031  jz      loc_1800090B7
0x180009037  sub     ecx, 1
0x18000903a  jz      short loc_1800090BB
0x18000903c  sub     ecx, 1
0x18000903f  jz      short loc_1800090BB
0x180009041  sub     ecx, 1
0x180009044  jz      short loc_18000905F
0x180009046  sub     ecx, 1
0x180009049  jz      short loc_18000905F
0x18000904b  sub     ecx, 1
0x18000904e  jz      short loc_18000905F
0x180009050  sub     ecx, 1
0x180009053  jz      short loc_18000905F
0x180009055  sub     ecx, 1
0x180009058  jz      short loc_18000905F
0x18000905a  cmp     ecx, 1
0x18000905d  jz      short loc_1800090BB
0x18000905f  mov     eax, 8
0x180009064  retn
0x180009065  sub     ecx, 0Ch
0x180009068  jz      short loc_18000905F
0x18000906a  sub     ecx, 1
0x18000906d  jz      short loc_18000905F
0x18000906f  sub     ecx, 1
0x180009072  jz      short loc_18000905F
0x180009074  sub     ecx, edx
0x180009076  jz      short loc_180009091
0x180009078  sub     ecx, 1
0x18000907b  jz      short loc_180009091
0x18000907d  sub     ecx, 1
0x180009080  jz      short loc_1800090B7
0x180009082  sub     ecx, 1
0x180009085  jz      short loc_1800090BB
0x180009087  sub     ecx, 1
0x18000908a  jz      short loc_180009091
0x18000908c  cmp     ecx, 1
0x18000908f  jnz     short loc_18000905F
0x180009091  mov     eax, 1
0x180009096  retn
0x180009097  sub     ecx, 80h
0x18000909d  jz      short loc_180009091
0x18000909f  sub     ecx, 1
0x1800090a2  jz      short loc_180009091
0x1800090a4  sub     ecx, 1
0x1800090a7  jz      short loc_1800090B7
0x1800090a9  sub     ecx, 1
0x1800090ac  jz      short loc_180009091
0x1800090ae  sub     ecx, edx
0x1800090b0  jz      short loc_1800090B7
0x1800090b2  sub     ecx, 1
0x1800090b5  jnz     short loc_18000905A
0x1800090b7  mov     rax, rdx
0x1800090ba  retn
0x1800090bb  mov     eax, 4
0x1800090c0  retn
```
