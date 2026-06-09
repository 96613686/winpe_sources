# CSslSerializeHelper::ComputeDeserializeLength(ulong *)

- ea: `0x140003cf0`
- end: `0x140003d89`
- name: `?ComputeDeserializeLength@CSslSerializeHelper@@AEAAJPEAK@Z`
- size: `153`
- prototype: `__int64 __fastcall(CSslSerializeHelper *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003cf0`

## pseudocode

```c
__int64 __fastcall CSslSerializeHelper::ComputeDeserializeLength(CSslSerializeHelper *this, unsigned int *a2)
{
  int *v2; // rax
  unsigned __int64 v3; // r10
  unsigned int v4; // r8d
  unsigned int v5; // r9d
  int v6; // ecx

  v2 = (int *)*((_QWORD *)this + 1);
  v3 = (unsigned __int64)v2 + *((unsigned int *)this + 6);
  *a2 = 0;
  while ( (unsigned __int64)(v2 + 4) <= v3 )
  {
    v4 = v2[1];
    v5 = v2[2];
    if ( v5 > v4 )
      break;
    v6 = *v2;
    if ( *v2 == 17 )
    {
LABEL_7:
      *a2 += (v5 + 7) & 0xFFFFFFF8;
    }
    else if ( v6 != 18 )
    {
      switch ( v6 )
      {
        case 0:
          return 0;
        case 1:
          if ( v4 < 8 )
            return 2148074244LL;
          *a2 = 528;
          v2 = (int *)((char *)v2 + v4 + 16);
          continue;
        case 2:
        case 3:
        case 19:
        case 20:
          break;
        case 4:
        case 5:
        case 6:
        case 7:
        case 8:
        case 9:
        case 10:
        case 11:
        case 12:
        case 13:
        case 14:
        case 15:
        case 16:
        case 21:
          goto LABEL_7;
        default:
          return 2148074244LL;
      }
    }
    v2 = (int *)((char *)v2 + v4 + 16);
  }
  return 2148074244LL;
}

```

## disassembly

```asm
0x140003cf0  mov     [rsp+arg_0], rbx
0x140003cf5  mov     rax, [rcx+8]
0x140003cf9  lea     rbx, cs:140000000h
0x140003d00  mov     r10d, [rcx+18h]
0x140003d04  mov     r11, rdx
0x140003d07  add     r10, rax
0x140003d0a  mov     dword ptr [rdx], 0
0x140003d10  lea     rcx, [rax+10h]
0x140003d14  cmp     rcx, r10
0x140003d17  ja      short def_140003D4A; jumptable 0000000140003D4A default case, cases 17,18
0x140003d19  mov     r8d, [rax+4]
0x140003d1d  mov     r9d, [rax+8]
0x140003d21  cmp     r9d, r8d
0x140003d24  ja      short def_140003D4A; jumptable 0000000140003D4A default case, cases 17,18
0x140003d26  movsxd  rcx, dword ptr [rax]
0x140003d29  cmp     ecx, 11h
0x140003d2c  jz      short loc_140003D50; jumptable 0000000140003D4A cases 4-16,21
0x140003d2e  cmp     ecx, 12h
0x140003d31  jz      short loc_140003D5A; jumptable 0000000140003D4A cases 2,3,19,20
0x140003d33  cmp     ecx, 15h; switch 22 cases
0x140003d36  ja      short def_140003D4A; jumptable 0000000140003D4A default case, cases 17,18
0x140003d38  movzx   ecx, ds:(byte_14001542C - 140000000h)[rbx+rcx]
0x140003d40  mov     edx, ds:(jpt_140003D4A - 140000000h)[rbx+rcx*4]
0x140003d47  add     rdx, rbx
0x140003d4a  jmp     rdx; switch jump
0x140003d50  lea     ecx, [r9+7]; jumptable 0000000140003D4A cases 4-16,21
0x140003d54  and     ecx, 0FFFFFFF8h
0x140003d57  add     [r11], ecx
0x140003d5a  lea     edx, [r8+10h]; jumptable 0000000140003D4A cases 2,3,19,20
0x140003d5e  add     rax, rdx
0x140003d61  jmp     short loc_140003D10
0x140003d63  cmp     r8d, 8; jumptable 0000000140003D4A case 1
0x140003d67  jb      short def_140003D4A; jumptable 0000000140003D4A default case, cases 17,18
0x140003d69  lea     edx, [r8+10h]
0x140003d6d  mov     dword ptr [r11], 210h
0x140003d74  add     rax, rdx
0x140003d77  jmp     short loc_140003D10
0x140003d79  mov     eax, 80090304h; jumptable 0000000140003D4A default case, cases 17,18
0x140003d7e  mov     rbx, [rsp+arg_0]
0x140003d83  retn
0x140003d85  xor     eax, eax; jumptable 0000000140003D4A case 0
0x140003d87  jmp     short loc_140003D7E
```
