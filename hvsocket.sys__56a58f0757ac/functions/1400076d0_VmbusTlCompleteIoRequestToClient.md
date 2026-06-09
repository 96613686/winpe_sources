# VmbusTlCompleteIoRequestToClient

- ea: `0x1400076d0`
- end: `0x14000778d`
- name: `VmbusTlCompleteIoRequestToClient`
- size: `189`
- prototype: `char *__fastcall(__int64, _OWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007794`

## callees

- `0x1400076d0`
- `0x14000bfe0`

## pseudocode

```c
char *__fastcall VmbusTlCompleteIoRequestToClient(__int64 a1, _OWORD *a2, unsigned int a3)
{
  __int64 v3; // rcx
  char *result; // rax
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  char v12; // [rsp+30h] [rbp-118h] BYREF
  int v13; // [rsp+A8h] [rbp-A0h]
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64); // [rsp+B8h] [rbp-90h]
  __int64 v15; // [rsp+C0h] [rbp-88h]
  __int64 v16; // [rsp+C8h] [rbp-80h]
  __int64 v17; // [rsp+E8h] [rbp-60h]
  __int64 v18; // [rsp+F0h] [rbp-58h]
  __int64 v19; // [rsp+F8h] [rbp-50h]
  char v20; // [rsp+128h] [rbp-20h]

  v3 = 2;
  result = &v12;
  do
  {
    v5 = a2[1];
    *(_OWORD *)result = *a2;
    v6 = a2[2];
    *((_OWORD *)result + 1) = v5;
    v7 = a2[3];
    *((_OWORD *)result + 2) = v6;
    v8 = a2[4];
    *((_OWORD *)result + 3) = v7;
    v9 = a2[5];
    *((_OWORD *)result + 4) = v8;
    v10 = a2[6];
    *((_OWORD *)result + 5) = v9;
    v11 = a2[7];
    a2 += 8;
    *((_OWORD *)result + 6) = v10;
    *((_OWORD *)result + 7) = v11;
    result += 128;
    --v3;
  }
  while ( v3 );
  if ( !v20 )
  {
    if ( v13 == 1 )
      return (char *)v14(v16, a3, v19);
    else
      return (char *)((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64))v14)(v15, a3, v17, v18);
  }
  return result;
}

```

## disassembly

```asm
0x1400076d0  sub     rsp, 148h
0x1400076d7  mov     ecx, 2
0x1400076dc  lea     rax, [rsp+148h+var_118]
0x1400076e1  mov     r10d, r8d
0x1400076e4  lea     r8d, [rcx+7Eh]
0x1400076e8  movups  xmm0, xmmword ptr [rdx]
0x1400076eb  movups  xmm1, xmmword ptr [rdx+10h]
0x1400076ef  movups  xmmword ptr [rax], xmm0
0x1400076f2  movups  xmm0, xmmword ptr [rdx+20h]
0x1400076f6  movups  xmmword ptr [rax+10h], xmm1
0x1400076fa  movups  xmm1, xmmword ptr [rdx+30h]
0x1400076fe  movups  xmmword ptr [rax+20h], xmm0
0x140007702  movups  xmm0, xmmword ptr [rdx+40h]
0x140007706  movups  xmmword ptr [rax+30h], xmm1
0x14000770a  movups  xmm1, xmmword ptr [rdx+50h]
0x14000770e  movups  xmmword ptr [rax+40h], xmm0
0x140007712  movups  xmm0, xmmword ptr [rdx+60h]
0x140007716  movups  xmmword ptr [rax+50h], xmm1
0x14000771a  movups  xmm1, xmmword ptr [rdx+70h]
0x14000771e  add     rdx, r8
0x140007721  movups  xmmword ptr [rax+60h], xmm0
0x140007725  movups  xmmword ptr [rax+70h], xmm1
0x140007729  add     rax, r8
0x14000772c  sub     rcx, 1
0x140007730  jnz     short loc_1400076E8
0x140007732  cmp     [rsp+148h+var_20], cl
0x140007739  jnz     short loc_140007784
0x14000773b  cmp     [rsp+148h+var_A0], 1
0x140007743  mov     edx, r10d
0x140007746  mov     rax, [rsp+148h+var_90]
0x14000774e  jnz     short loc_140007767
0x140007750  mov     r8, [rsp+148h+var_50]
0x140007758  mov     rcx, [rsp+148h+var_80]
0x140007760  call    _guard_dispatch_icall
0x140007765  jmp     short loc_140007784
0x140007767  mov     r9, [rsp+148h+var_58]
0x14000776f  mov     r8, [rsp+148h+var_60]
0x140007777  mov     rcx, [rsp+148h+var_88]
0x14000777f  call    _guard_dispatch_icall
0x140007784  add     rsp, 148h
0x14000778b  retn
```
