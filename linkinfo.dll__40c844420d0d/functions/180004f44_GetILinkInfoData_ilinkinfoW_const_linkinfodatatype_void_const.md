# GetILinkInfoData(_ilinkinfoW const *,_linkinfodatatype,void const * *)

- ea: `0x180004f44`
- end: `0x180005106`
- name: `?GetILinkInfoData@@YAHPEBU_ilinkinfoW@@W4_linkinfodatatype@@PEAPEBX@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005570`

## callees

- `0x180004f44`

## pseudocode

```c
__int64 __fastcall GetILinkInfoData(__int64 a1, int a2, _QWORD *a3)
{
  unsigned int v3; // r9d
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  char *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  _DWORD *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax

  v3 = 0;
  if ( a2 <= 6 )
  {
    if ( a2 != 6 )
    {
      if ( a2 )
      {
        v4 = a2 - 1;
        if ( v4 )
        {
          v5 = v4 - 1;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
            {
              v7 = v6 - 1;
              if ( v7 )
              {
                if ( v7 == 1 && (*(_BYTE *)(a1 + 8) & 2) != 0 )
                {
                  v8 = a1 + *(unsigned int *)(a1 + 20);
                  if ( (*(_BYTE *)(v8 + 4) & 1) != 0 )
                  {
                    v9 = *(unsigned int *)(v8 + 12);
                    v3 = 1;
LABEL_12:
                    v10 = v8 + v9;
LABEL_55:
                    *a3 = v10;
                    return v3;
                  }
                }
                return v3;
              }
              if ( (*(_BYTE *)(a1 + 8) & 2) == 0 )
                return v3;
              a1 += *(unsigned int *)(a1 + 20);
              v11 = *(unsigned int *)(a1 + 8);
            }
            else
            {
              if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
                return v3;
              v11 = *(unsigned int *)(a1 + 16);
            }
          }
          else
          {
            if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
              return v3;
            a1 += *(unsigned int *)(a1 + 12);
            v11 = *(unsigned int *)(a1 + 12);
          }
          goto LABEL_19;
        }
        if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
          return v3;
        v13 = *(unsigned int *)(a1 + 12);
        v14 = a1 + 4;
      }
      else
      {
        if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
          return v3;
        v13 = *(unsigned int *)(a1 + 12);
        v14 = a1 + 8;
      }
      *a3 = v13 + v14;
      return 1;
    }
    v11 = *(unsigned int *)(a1 + 24);
LABEL_19:
    v12 = (char *)(a1 + v11);
LABEL_20:
    *a3 = v12;
    return 1;
  }
  v15 = a2 - 7;
  if ( !v15 )
  {
    if ( (*(_BYTE *)(a1 + 8) & 2) != 0 )
    {
      v22 = *(unsigned int *)(a1 + 20);
      if ( (*(_BYTE *)(v22 + a1 + 4) & 2) != 0 )
      {
        v3 = 1;
        v10 = a1 + v22 + 16;
        goto LABEL_55;
      }
    }
    return v3;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
      return v3;
    v20 = (_DWORD *)(a1 + *(unsigned int *)(a1 + 12));
    if ( v20[3] == 16 )
      goto LABEL_51;
    v21 = (unsigned int)v20[4];
LABEL_50:
    v12 = (char *)v20 + v21;
    goto LABEL_20;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    if ( (*(_BYTE *)(a1 + 8) & 2) == 0 )
      return v3;
    v20 = (_DWORD *)(a1 + *(unsigned int *)(a1 + 20));
    if ( v20[2] == 20 )
      goto LABEL_51;
    v21 = (unsigned int)v20[5];
    goto LABEL_50;
  }
  v18 = v17 - 1;
  if ( v18 )
  {
    v19 = v18 - 1;
    if ( v19 )
    {
      if ( v19 != 1 )
        return v3;
      if ( *(_DWORD *)(a1 + 4) != 28 )
      {
        v11 = *(unsigned int *)(a1 + 32);
        goto LABEL_19;
      }
    }
    else
    {
      if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
        return v3;
      if ( *(_DWORD *)(a1 + 4) != 28 )
      {
        v11 = *(unsigned int *)(a1 + 28);
        goto LABEL_19;
      }
    }
LABEL_51:
    v12 = 0;
    goto LABEL_20;
  }
  if ( (*(_BYTE *)(a1 + 8) & 2) != 0 )
  {
    v8 = a1 + *(unsigned int *)(a1 + 20);
    if ( (*(_BYTE *)(v8 + 4) & 1) != 0 )
    {
      v3 = 1;
      if ( *(_DWORD *)(v8 + 8) != 20 )
      {
        v9 = *(unsigned int *)(v8 + 24);
        goto LABEL_12;
      }
      *a3 = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180004f44  xor     r9d, r9d
0x180004f47  cmp     edx, 6
0x180004f4a  jg      loc_180005023
0x180004f50  jz      loc_18000501E
0x180004f56  test    edx, edx
0x180004f58  jz      loc_180004FFC
0x180004f5e  sub     edx, 1
0x180004f61  jz      loc_180004FE9
0x180004f67  sub     edx, 1
0x180004f6a  jz      short loc_180004FCE
0x180004f6c  sub     edx, 1
0x180004f6f  jz      short loc_180004FBF
0x180004f71  sub     edx, 1
0x180004f74  jz      short loc_180004FAA
0x180004f76  cmp     edx, 1
0x180004f79  jnz     loc_180005102
0x180004f7f  test    byte ptr [rcx+8], 2
0x180004f83  jz      loc_180005102
0x180004f89  mov     edx, [rcx+14h]
0x180004f8c  add     rdx, rcx
0x180004f8f  test    byte ptr [rdx+4], 1
0x180004f93  jz      loc_180005102
0x180004f99  mov     eax, [rdx+0Ch]
0x180004f9c  mov     r9d, 1
0x180004fa2  add     rax, rdx
0x180004fa5  jmp     loc_1800050FF
0x180004faa  test    byte ptr [rcx+8], 2
0x180004fae  jz      loc_180005102
0x180004fb4  mov     eax, [rcx+14h]
0x180004fb7  add     rcx, rax
0x180004fba  mov     eax, [rcx+8]
0x180004fbd  jmp     short loc_180004FE1
0x180004fbf  test    byte ptr [rcx+8], 1
0x180004fc3  jz      loc_180005102
0x180004fc9  mov     eax, [rcx+10h]
0x180004fcc  jmp     short loc_180004FE1
0x180004fce  test    byte ptr [rcx+8], 1
0x180004fd2  jz      loc_180005102
0x180004fd8  mov     eax, [rcx+0Ch]
0x180004fdb  add     rcx, rax
0x180004fde  mov     eax, [rcx+0Ch]
0x180004fe1  add     rax, rcx
0x180004fe4  mov     [r8], rax
0x180004fe7  jmp     short loc_180005013
0x180004fe9  test    byte ptr [rcx+8], 1
0x180004fed  jz      loc_180005102
0x180004ff3  mov     eax, [rcx+0Ch]
0x180004ff6  add     rcx, 4
0x180004ffa  jmp     short loc_18000500D
0x180004ffc  test    byte ptr [rcx+8], 1
0x180005000  jz      loc_180005102
0x180005006  mov     eax, [rcx+0Ch]
0x180005009  add     rcx, 8
0x18000500d  add     rcx, rax
0x180005010  mov     [r8], rcx
0x180005013  mov     r9d, 1
0x180005019  jmp     loc_180005102
0x18000501e  mov     eax, [rcx+18h]
0x180005021  jmp     short loc_180004FE1
0x180005023  sub     edx, 7
0x180005026  jz      loc_1800050E2
0x18000502c  sub     edx, 1
0x18000502f  jz      loc_1800050BE
0x180005035  sub     edx, 1
0x180005038  jz      short loc_1800050A7
0x18000503a  sub     edx, 1
0x18000503d  jz      short loc_180005074
0x18000503f  sub     edx, 1
0x180005042  jz      short loc_18000505C
0x180005044  cmp     edx, 1
0x180005047  jnz     loc_180005102
0x18000504d  cmp     dword ptr [rcx+4], 1Ch
0x180005051  jz      loc_1800050DB
0x180005057  mov     eax, [rcx+20h]
0x18000505a  jmp     short loc_180004FE1
0x18000505c  test    byte ptr [rcx+8], 1
0x180005060  jz      loc_180005102
0x180005066  cmp     dword ptr [rcx+4], 1Ch
0x18000506a  jz      short loc_1800050DB
0x18000506c  mov     eax, [rcx+1Ch]
0x18000506f  jmp     loc_180004FE1
0x180005074  test    byte ptr [rcx+8], 2
0x180005078  jz      loc_180005102
0x18000507e  mov     edx, [rcx+14h]
0x180005081  add     rdx, rcx
0x180005084  test    byte ptr [rdx+4], 1
0x180005088  jz      short loc_180005102
0x18000508a  cmp     dword ptr [rdx+8], 14h
0x18000508e  mov     r9d, 1
0x180005094  jnz     short loc_18000509F
0x180005096  mov     qword ptr [r8], 0
0x18000509d  jmp     short loc_180005102
0x18000509f  mov     eax, [rdx+18h]
0x1800050a2  jmp     loc_180004FA2
0x1800050a7  test    byte ptr [rcx+8], 2
0x1800050ab  jz      short loc_180005102
0x1800050ad  mov     edx, [rcx+14h]
0x1800050b0  add     rdx, rcx
0x1800050b3  cmp     dword ptr [rdx+8], 14h
0x1800050b7  jz      short loc_1800050DB
0x1800050b9  mov     eax, [rdx+14h]
0x1800050bc  jmp     short loc_1800050D3
0x1800050be  test    byte ptr [rcx+8], 1
0x1800050c2  jz      short loc_180005102
0x1800050c4  mov     edx, [rcx+0Ch]
0x1800050c7  add     rdx, rcx
0x1800050ca  cmp     dword ptr [rdx+0Ch], 10h
0x1800050ce  jz      short loc_1800050DB
0x1800050d0  mov     eax, [rdx+10h]
0x1800050d3  add     rax, rdx
0x1800050d6  jmp     loc_180004FE4
0x1800050db  xor     eax, eax
0x1800050dd  jmp     loc_180004FE4
0x1800050e2  test    byte ptr [rcx+8], 2
0x1800050e6  jz      short loc_180005102
0x1800050e8  mov     eax, [rcx+14h]
0x1800050eb  test    byte ptr [rax+rcx+4], 2
0x1800050f0  jz      short loc_180005102
0x1800050f2  add     rax, 10h
0x1800050f6  mov     r9d, 1
0x1800050fc  add     rax, rcx
0x1800050ff  mov     [r8], rax
0x180005102  mov     eax, r9d
0x180005105  retn
```
