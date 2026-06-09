# AslpImageRvaToVa

- ea: `0x1400101cc`
- end: `0x1400102f7`
- name: `AslpImageRvaToVa`
- size: `299`
- prototype: `unsigned __int64 __fastcall(unsigned __int64, __int64, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000c110`
- `0x14000cfe8`
- `0x14000dd40`
- `0x14000eab4`
- `0x14000f1f4`
- `0x14000f7ac`

## callees

- `0x140007074`
- `0x14000dc74`
- `0x1400101cc`

## string_xrefs

- `0x140010272`: `AslpFileGetImageNtHeader failed [%x]`

## pseudocode

```c
unsigned __int64 __fastcall AslpImageRvaToVa(unsigned __int64 a1, __int64 a2, unsigned int a3)
{
  unsigned __int64 v5; // r9
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rdx
  int ImageNtHeader; // eax
  _DWORD *v12; // rdx
  int v13; // r8d
  unsigned int v14; // ecx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a1;
  if ( !a3 )
    return 0;
  if ( *(_BYTE *)(a2 + 51) )
  {
    if ( (unsigned __int64)a3 < *(_QWORD *)(a2 + 40) )
      return a3 + *(_QWORD *)(a2 + 32);
    return 0;
  }
  v7 = *(_QWORD *)(a2 + 32);
  v16 = a1;
  if ( a1 < v7
    || (v8 = a1 + 264, v5 > v8)
    || (v9 = *(_QWORD *)(a2 + 40), v10 = v7 + v9, v5 > v7 + v9)
    || v8 < v7
    || v8 > v10
    || v7 > v10
    || v9 < 0x108 )
  {
    AslLogCallPrintf(
      2,
      "AslpImageRvaToVa",
      5477,
      "AslpImageRvaToVa called with headers not contained in the file view.");
    ImageNtHeader = AslpFileGetImageNtHeader(&v16, a2);
    if ( ImageNtHeader < 0 )
    {
      AslLogCallPrintf(1, "AslpImageRvaToVa", 5481, "AslpFileGetImageNtHeader failed [%x]", ImageNtHeader);
      return 0;
    }
    v5 = v16;
  }
  v12 = (_DWORD *)(*(unsigned __int16 *)(v5 + 20) + v5 + 24);
  v13 = 0;
  if ( !*(_WORD *)(v5 + 6) )
    return 0;
  while ( 1 )
  {
    v14 = v12[3];
    if ( a3 >= v14 && a3 < v12[4] + v14 )
      break;
    v12 += 10;
    if ( ++v13 >= (unsigned int)*(unsigned __int16 *)(v5 + 6) )
      return 0;
  }
  if ( !v12 )
    return 0;
  v15 = a3 + v12[5] - v12[3];
  if ( v15 >= *(_QWORD *)(a2 + 24) )
    return 0;
  return v15 + *(_QWORD *)(a2 + 32);
}

```

## disassembly

```asm
0x1400101cc  mov     [rsp+arg_0], rbx
0x1400101d1  push    rdi
0x1400101d2  sub     rsp, 30h
0x1400101d6  mov     edi, r8d
0x1400101d9  mov     rbx, rdx
0x1400101dc  mov     r9, rcx
0x1400101df  test    r8d, r8d
0x1400101e2  jz      loc_140010294
0x1400101e8  cmp     byte ptr [rdx+33h], 0
0x1400101ec  jz      short loc_140010204
0x1400101ee  cmp     rdi, [rdx+28h]
0x1400101f2  jnb     loc_140010294
0x1400101f8  mov     rax, [rdx+20h]
0x1400101fc  add     rax, rdi
0x1400101ff  jmp     loc_140010296
0x140010204  mov     rax, [rdx+20h]
0x140010208  mov     [rsp+38h+arg_18], r9
0x14001020d  cmp     r9, rax
0x140010210  jb      short loc_140010243
0x140010212  add     rcx, 108h
0x140010219  cmp     r9, rcx
0x14001021c  ja      short loc_140010243
0x14001021e  mov     r8, [rdx+28h]
0x140010222  lea     rdx, [rax+r8]
0x140010226  cmp     r9, rdx
0x140010229  ja      short loc_140010243
0x14001022b  cmp     rcx, rax
0x14001022e  jb      short loc_140010243
0x140010230  cmp     rcx, rdx
0x140010233  ja      short loc_140010243
0x140010235  cmp     rax, rdx
0x140010238  ja      short loc_140010243
0x14001023a  cmp     r8, 108h
0x140010241  jnb     short loc_1400102A6
0x140010243  lea     r9, aAslpimagervato_0; "AslpImageRvaToVa called with headers no"...
0x14001024a  mov     r8d, 1565h
0x140010250  lea     rdx, aAslpimagervato; "AslpImageRvaToVa"
0x140010257  mov     ecx, 2
0x14001025c  call    AslLogCallPrintf
0x140010261  mov     rdx, rbx
0x140010264  lea     rcx, [rsp+38h+arg_18]
0x140010269  call    AslpFileGetImageNtHeader
0x14001026e  test    eax, eax
0x140010270  jns     short loc_1400102A1
0x140010272  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x140010279  mov     [rsp+38h+var_18], eax
0x14001027d  mov     r8d, 1569h
0x140010283  lea     rdx, aAslpimagervato; "AslpImageRvaToVa"
0x14001028a  mov     ecx, 1
0x14001028f  call    AslLogCallPrintf
0x140010294  xor     eax, eax
0x140010296  mov     rbx, [rsp+38h+arg_0]
0x14001029b  add     rsp, 30h
0x14001029f  pop     rdi
0x1400102a0  retn
0x1400102a1  mov     r9, [rsp+38h+arg_18]
0x1400102a6  movzx   eax, word ptr [r9+14h]
0x1400102ab  lea     rdx, [r9+18h]
0x1400102af  movzx   r10d, word ptr [r9+6]
0x1400102b4  add     rdx, rax
0x1400102b7  xor     r8d, r8d
0x1400102ba  test    r10d, r10d
0x1400102bd  jz      short loc_140010294
0x1400102bf  mov     ecx, [rdx+0Ch]
0x1400102c2  cmp     edi, ecx
0x1400102c4  jb      short loc_1400102CD
0x1400102c6  add     ecx, [rdx+10h]
0x1400102c9  cmp     edi, ecx
0x1400102cb  jb      short loc_1400102DB
0x1400102cd  add     rdx, 28h ; '('
0x1400102d1  inc     r8d
0x1400102d4  cmp     r8d, r10d
0x1400102d7  jb      short loc_1400102BF
0x1400102d9  jmp     short loc_140010294
0x1400102db  test    rdx, rdx
0x1400102de  jz      short loc_140010294
0x1400102e0  mov     ecx, [rdx+14h]
0x1400102e3  sub     ecx, [rdx+0Ch]
0x1400102e6  add     ecx, edi
0x1400102e8  cmp     rcx, [rbx+18h]
0x1400102ec  jnb     short loc_140010294
0x1400102ee  mov     rax, [rbx+20h]
0x1400102f2  add     rax, rcx
0x1400102f5  jmp     short loc_140010296
```
