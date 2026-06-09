# _copytlocinfo_nolock

- ea: `0x18002c298`
- end: `0x18002c349`
- name: `_copytlocinfo_nolock`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c350`
- `0x18002d060`

## callees

- `0x18002bd50`
- `0x18002c298`

## pseudocode

```c
void __fastcall copytlocinfo_nolock(_DWORD *a1, _OWORD *a2)
{
  __int64 v2; // r8
  _OWORD *v3; // rax
  __int128 v4; // xmm1

  if ( a2 && a1 && a1 != (_DWORD *)a2 )
  {
    v2 = 2;
    v3 = a1;
    do
    {
      *v3 = *a2;
      v3[1] = a2[1];
      v3[2] = a2[2];
      v3[3] = a2[3];
      v3[4] = a2[4];
      v3[5] = a2[5];
      v3[6] = a2[6];
      v4 = a2[7];
      a2 += 8;
      v3[7] = v4;
      v3 += 8;
      --v2;
    }
    while ( v2 );
    *v3 = *a2;
    v3[1] = a2[1];
    v3[2] = a2[2];
    v3[3] = a2[3];
    v3[4] = a2[4];
    v3[5] = a2[5];
    *a1 = 0;
    _addlocaleref(a1);
  }
}

```

## disassembly

```asm
0x18002c298  sub     rsp, 28h
0x18002c29c  test    rdx, rdx
0x18002c29f  jz      loc_18002C344
0x18002c2a5  test    rcx, rcx
0x18002c2a8  jz      loc_18002C344
0x18002c2ae  cmp     rcx, rdx
0x18002c2b1  jz      loc_18002C344
0x18002c2b7  mov     r8d, 2
0x18002c2bd  mov     rax, rcx
0x18002c2c0  lea     r9d, [r8+7Eh]
0x18002c2c4  movups  xmm0, xmmword ptr [rdx]
0x18002c2c7  movups  xmmword ptr [rax], xmm0
0x18002c2ca  movups  xmm1, xmmword ptr [rdx+10h]
0x18002c2ce  movups  xmmword ptr [rax+10h], xmm1
0x18002c2d2  movups  xmm0, xmmword ptr [rdx+20h]
0x18002c2d6  movups  xmmword ptr [rax+20h], xmm0
0x18002c2da  movups  xmm1, xmmword ptr [rdx+30h]
0x18002c2de  movups  xmmword ptr [rax+30h], xmm1
0x18002c2e2  movups  xmm0, xmmword ptr [rdx+40h]
0x18002c2e6  movups  xmmword ptr [rax+40h], xmm0
0x18002c2ea  movups  xmm1, xmmword ptr [rdx+50h]
0x18002c2ee  movups  xmmword ptr [rax+50h], xmm1
0x18002c2f2  movups  xmm0, xmmword ptr [rdx+60h]
0x18002c2f6  movups  xmmword ptr [rax+60h], xmm0
0x18002c2fa  movups  xmm1, xmmword ptr [rdx+70h]
0x18002c2fe  add     rdx, r9
0x18002c301  movups  xmmword ptr [rax+70h], xmm1
0x18002c305  add     rax, r9
0x18002c308  sub     r8, 1
0x18002c30c  jnz     short loc_18002C2C4
0x18002c30e  movups  xmm0, xmmword ptr [rdx]
0x18002c311  movups  xmmword ptr [rax], xmm0
0x18002c314  movups  xmm1, xmmword ptr [rdx+10h]
0x18002c318  movups  xmmword ptr [rax+10h], xmm1
0x18002c31c  movups  xmm0, xmmword ptr [rdx+20h]
0x18002c320  movups  xmmword ptr [rax+20h], xmm0
0x18002c324  movups  xmm1, xmmword ptr [rdx+30h]
0x18002c328  movups  xmmword ptr [rax+30h], xmm1
0x18002c32c  movups  xmm0, xmmword ptr [rdx+40h]
0x18002c330  movups  xmmword ptr [rax+40h], xmm0
0x18002c334  movups  xmm1, xmmword ptr [rdx+50h]
0x18002c338  movups  xmmword ptr [rax+50h], xmm1
0x18002c33c  mov     [rcx], r8d
0x18002c33f  call    __addlocaleref
0x18002c344  add     rsp, 28h
0x18002c348  retn
```
