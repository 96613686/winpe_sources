# RtlpInsertAssemblyStorageMapEntry

- ea: `0x1800d1024`
- end: `0x1800d11ac`
- name: `RtlpInsertAssemblyStorageMapEntry`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800d0560`

## callees

- `0x18001861c`
- `0x18001a080`
- `0x18001b984`
- `0x1800d1024`
- `0x180164280`

## string_xrefs

- `0x1800d1167`: `SXS: %s() bad parameters\nSXS:  Map                    : %p\nSXS:  AssemblyRosterIndex    : 0x%lx\nSXS:  Map->AssemblyCount     : 0x%lx\nSXS:  StorageLocation        : %p\nSXS:  StorageLocation->Length: 0x%x\nSXS:  StorageLocation->Buffer: %p\nSXS:  OpenDirectoryHandle    : %p\n`

## pseudocode

```c
__int64 __fastcall RtlpInsertAssemblyStorageMapEntry(__int64 a1, unsigned int a2, const void **a3, _QWORD *a4)
{
  __int64 v4; // rbp
  __int64 v8; // r8
  __int64 Heap_0; // rax
  signed __int64 v10; // rdi
  __int64 result; // rax
  const void *v12; // rax
  int v13; // edx
  int v14; // ecx

  v4 = a2;
  if ( !a1 || !a2 || a2 > *(_DWORD *)(a1 + 4) )
  {
    if ( a3 )
    {
LABEL_16:
      v12 = a3[1];
      v13 = *(unsigned __int16 *)a3;
      goto LABEL_19;
    }
LABEL_17:
    v12 = 0;
    v13 = 0;
LABEL_19:
    if ( a1 )
      v14 = *(_DWORD *)(a1 + 4);
    else
      v14 = 0;
    DbgPrintEx(
      51,
      0,
      "SXS: %s() bad parameters\n"
      "SXS:  Map                    : %p\n"
      "SXS:  AssemblyRosterIndex    : 0x%lx\n"
      "SXS:  Map->AssemblyCount     : 0x%lx\n"
      "SXS:  StorageLocation        : %p\n"
      "SXS:  StorageLocation->Length: 0x%x\n"
      "SXS:  StorageLocation->Buffer: %p\n"
      "SXS:  OpenDirectoryHandle    : %p\n",
      "RtlpInsertAssemblyStorageMapEntry",
      (const void *)a1,
      v4,
      v14,
      a3,
      v13,
      v12,
      a4);
    return 3221225485LL;
  }
  if ( !a3 )
    goto LABEL_17;
  if ( *(_WORD *)a3 < 2u || !a3[1] || !a4 )
    goto LABEL_16;
  v8 = *(unsigned __int16 *)a3;
  if ( (unsigned __int64)(v8 + 2) > 0xFFFE )
    return 3221225734LL;
  Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v8 + 34);
  v10 = Heap_0;
  if ( !Heap_0 )
    return 3221225495LL;
  *(_DWORD *)Heap_0 = 0;
  *(_WORD *)(Heap_0 + 8) = *(_WORD *)a3;
  *(_QWORD *)(Heap_0 + 16) = Heap_0 + 32;
  *(_WORD *)(Heap_0 + 10) = *(_WORD *)a3 + 2;
  memmove((void *)(Heap_0 + 32), a3[1], *(unsigned __int16 *)a3);
  *(_WORD *)(*(_QWORD *)(v10 + 16) + 2 * ((unsigned __int64)*(unsigned __int16 *)(v10 + 8) >> 1)) = 0;
  *(_QWORD *)(v10 + 24) = *a4;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(a1 + 8) + 8 * v4), v10, 0) )
  {
    v10 = 0;
    *a4 = 0;
  }
  result = 0;
  if ( v10 )
  {
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v10);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800d1024  push    rbx
0x1800d1026  push    rbp
0x1800d1027  push    rsi
0x1800d1028  push    rdi
0x1800d1029  push    r14
0x1800d102b  sub     rsp, 60h
0x1800d102f  mov     ebp, edx
0x1800d1031  mov     r14, r9
0x1800d1034  mov     rbx, r8
0x1800d1037  mov     rsi, rcx
0x1800d103a  test    rcx, rcx
0x1800d103d  jz      loc_1800D1139
0x1800d1043  cmp     ebp, 1
0x1800d1046  jb      loc_1800D1139
0x1800d104c  cmp     ebp, [rcx+4]
0x1800d104f  ja      loc_1800D1139
0x1800d1055  test    rbx, rbx
0x1800d1058  jz      loc_1800D1144
0x1800d105e  cmp     word ptr [r8], 2
0x1800d1063  jb      loc_1800D113E
0x1800d1069  cmp     qword ptr [r8+8], 0
0x1800d106e  jz      loc_1800D113E
0x1800d1074  test    r9, r9
0x1800d1077  jz      loc_1800D113E
0x1800d107d  movzx   r8d, word ptr [r8]
0x1800d1081  lea     rax, [r8+2]
0x1800d1085  cmp     rax, 0FFFEh
0x1800d108b  ja      loc_1800D11A5
0x1800d1091  mov     rcx, gs:60h
0x1800d109a  add     r8, 22h ; '"'
0x1800d109e  xor     edx, edx
0x1800d10a0  mov     rcx, [rcx+30h]
0x1800d10a4  call    RtlAllocateHeap_0
0x1800d10a9  mov     rdi, rax
0x1800d10ac  test    rax, rax
0x1800d10af  jz      loc_1800D119E
0x1800d10b5  mov     dword ptr [rax], 0
0x1800d10bb  lea     rcx, [rdi+20h]; void *
0x1800d10bf  movzx   eax, word ptr [rbx]
0x1800d10c2  mov     [rdi+8], ax
0x1800d10c6  mov     [rdi+10h], rcx
0x1800d10ca  movzx   eax, word ptr [rbx]
0x1800d10cd  add     ax, 2
0x1800d10d1  mov     [rdi+0Ah], ax
0x1800d10d5  movzx   r8d, word ptr [rbx]; Size
0x1800d10d9  mov     rdx, [rbx+8]; Src
0x1800d10dd  call    memmove
0x1800d10e2  movzx   edx, word ptr [rdi+8]
0x1800d10e6  xor     eax, eax
0x1800d10e8  mov     rcx, [rdi+10h]
0x1800d10ec  shr     rdx, 1
0x1800d10ef  mov     [rcx+rdx*2], ax
0x1800d10f3  mov     rax, [r14]
0x1800d10f6  mov     [rdi+18h], rax
0x1800d10fa  xor     eax, eax
0x1800d10fc  mov     rcx, [rsi+8]
0x1800d1100  lock cmpxchg [rcx+rbp*8], rdi
0x1800d1106  jnz     short loc_1800D110D
0x1800d1108  xor     edi, edi
0x1800d110a  mov     [r14], rdi
0x1800d110d  xor     eax, eax
0x1800d110f  test    rdi, rdi
0x1800d1112  jz      short loc_1800D112D
0x1800d1114  mov     rcx, gs:60h
0x1800d111d  mov     r8, rdi
0x1800d1120  xor     edx, edx
0x1800d1122  mov     rcx, [rcx+30h]
0x1800d1126  call    RtlFreeHeap_0
0x1800d112b  xor     eax, eax
0x1800d112d  add     rsp, 60h
0x1800d1131  pop     r14
0x1800d1133  pop     rdi
0x1800d1134  pop     rsi
0x1800d1135  pop     rbp
0x1800d1136  pop     rbx
0x1800d1137  retn
0x1800d1139  test    rbx, rbx
0x1800d113c  jz      short loc_1800D1144
0x1800d113e  mov     rax, [r8+8]
0x1800d1142  jmp     short loc_1800D114B
0x1800d1144  xor     eax, eax
0x1800d1146  test    rbx, rbx
0x1800d1149  jz      short loc_1800D119A
0x1800d114b  movzx   edx, word ptr [r8]
0x1800d114f  test    rsi, rsi
0x1800d1152  jnz     short loc_1800D1195
0x1800d1154  xor     ecx, ecx
0x1800d1156  mov     [rsp+88h+var_38], r14
0x1800d115b  lea     r9, aRtlpinsertasse; "RtlpInsertAssemblyStorageMapEntry"
0x1800d1162  mov     [rsp+88h+var_40], rax
0x1800d1167  lea     r8, aSxsSBadParamet_1; "SXS: %s() bad parameters\nSXS:  Map    "...
0x1800d116e  mov     [rsp+88h+var_48], edx
0x1800d1172  xor     edx, edx
0x1800d1174  mov     [rsp+88h+var_50], rbx
0x1800d1179  mov     [rsp+88h+var_58], ecx
0x1800d117d  mov     [rsp+88h+var_60], ebp
0x1800d1181  lea     ecx, [rdx+33h]
0x1800d1184  mov     [rsp+88h+var_68], rsi
0x1800d1189  call    DbgPrintEx
0x1800d118e  mov     eax, 0C000000Dh
0x1800d1193  jmp     short loc_1800D112D
0x1800d1195  mov     ecx, [rcx+4]
0x1800d1198  jmp     short loc_1800D1156
0x1800d119a  xor     edx, edx
0x1800d119c  jmp     short loc_1800D114F
0x1800d119e  mov     eax, 0C0000017h
0x1800d11a3  jmp     short loc_1800D112D
0x1800d11a5  mov     eax, 0C0000106h
0x1800d11aa  jmp     short loc_1800D112D
```
