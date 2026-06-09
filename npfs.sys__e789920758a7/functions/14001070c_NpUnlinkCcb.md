# NpUnlinkCcb

- ea: `0x14001070c`
- end: `0x1400107b7`
- name: `NpUnlinkCcb`
- size: `171`
- prototype: `void __fastcall(int, __int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000b030`
- `0x14000e980`

## callees

- `0x14000172c`
- `0x14000fb00`
- `0x14001070c`
- `0x140010d18`

## pseudocode

```c
void __fastcall NpUnlinkCcb(int a1, __int64 a2, int a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  _QWORD *v7; // rdx
  char *v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rdx

  v3 = a2 + 24;
  v4 = *(_QWORD *)(a2 + 24);
  if ( *(_QWORD *)(v4 + 8) != a2 + 24 )
    goto LABEL_10;
  v7 = *(_QWORD **)(a2 + 32);
  if ( *v7 != v3 )
    goto LABEL_10;
  *v7 = v4;
  *(_QWORD *)(v4 + 8) = v7;
  --*(_DWORD *)(*(_QWORD *)(a2 + 40) + 120LL);
  if ( *(_BYTE *)(a2 + 8) != 2 )
    goto LABEL_4;
  v9 = *(_QWORD *)(a2 + 288);
  if ( *(_QWORD *)(v9 + 8) != a2 + 288 || (v10 = *(_QWORD **)(a2 + 296), *v10 != a2 + 288) )
LABEL_10:
    __fastfail(3u);
  *v10 = v9;
  *(_QWORD *)(v9 + 8) = v10;
LABEL_4:
  if ( *(_QWORD *)(a2 + 448) )
    NpCheckForNotifyWithFilter(a1, a3, 16, *(_QWORD *)(a2 + 40) + 160, 3);
  v8 = (char *)NpClearSecurity(a2);
  NpFreeClientSecurityContext(v8);
}

```

## disassembly

```asm
0x14001070c  push    rbx
0x14001070e  sub     rsp, 30h
0x140010712  lea     rax, [rdx+18h]
0x140010716  mov     r10, r8
0x140010719  mov     r9, [rax]
0x14001071c  mov     rbx, rdx
0x14001071f  mov     r11, rcx
0x140010722  cmp     [r9+8], rax
0x140010726  jnz     loc_1400107B0
0x14001072c  mov     rdx, [rax+8]
0x140010730  cmp     [rdx], rax
0x140010733  jnz     short loc_1400107B0
0x140010735  mov     [rdx], r9
0x140010738  mov     [r9+8], rdx
0x14001073c  mov     rax, [rbx+28h]
0x140010740  dec     dword ptr [rax+78h]
0x140010743  cmp     byte ptr [rbx+8], 2
0x140010747  jz      short loc_14001078E
0x140010749  cmp     qword ptr [rbx+1C0h], 0
0x140010751  jz      short loc_140010777
0x140010753  mov     r9, [rbx+28h]
0x140010757  mov     r8d, 10h
0x14001075d  add     r9, 0A0h
0x140010764  mov     [rsp+38h+var_18], 3
0x14001076c  mov     rdx, r10
0x14001076f  mov     rcx, r11
0x140010772  call    NpCheckForNotifyWithFilter
0x140010777  mov     rcx, rbx
0x14001077a  call    NpClearSecurity
0x14001077f  mov     rcx, rax; P
0x140010782  call    NpFreeClientSecurityContext
0x140010787  add     rsp, 30h
0x14001078b  pop     rbx
0x14001078c  retn
0x14001078e  lea     rax, [rbx+120h]
0x140010795  mov     rcx, [rax]
0x140010798  cmp     [rcx+8], rax
0x14001079c  jnz     short loc_1400107B0
0x14001079e  mov     rdx, [rax+8]
0x1400107a2  cmp     [rdx], rax
0x1400107a5  jnz     short loc_1400107B0
0x1400107a7  mov     [rdx], rcx
0x1400107aa  mov     [rcx+8], rdx
0x1400107ae  jmp     short loc_140010749
0x1400107b0  mov     ecx, 3
0x1400107b5  int     29h; Win8: RtlFailFast(ecx)
```
