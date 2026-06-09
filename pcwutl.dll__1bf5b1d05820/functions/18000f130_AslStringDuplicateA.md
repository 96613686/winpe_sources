# AslStringDuplicateA

- ea: `0x18000f130`
- end: `0x18000f2d4`
- name: `AslStringDuplicateA`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b710`

## callees

- `0x18000e240`
- `0x18000f130`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000f297`
- `ntdll!RtlFreeHeap` at `0x18000f297`
- `ntdll!RtlAllocateHeap` at `0x18000f1c1`
- `ntdll!RtlAllocateHeap` at `0x18000f1c1`

## string_xrefs

- `0x18000f263`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicateA(_QWORD *a1)
{
  char *v2; // r14
  __int64 v3; // r8
  char *v4; // rax
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  const char *v7; // r9
  __int64 v8; // r8
  unsigned __int64 v9; // rdi
  _BYTE *Heap; // rax
  _BYTE *v11; // rsi
  __int64 v12; // rax
  _BYTE *v13; // rcx
  _BYTE *v14; // rax

  *a1 = 0;
  v2 = byte_1800216C9;
  v3 = 0x7FFFFFFF;
  v4 = byte_1800216C9;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0xC000000D : 0;
  v6 = (0x7FFFFFFF - v3) & -(__int64)(v3 != 0);
  if ( !v3 )
  {
    v7 = "RtlStringCchLengthA failed [%x]";
    v8 = 479;
LABEL_23:
    AslLogCallPrintf(1, "AslStringDuplicateA", v8, v7, v5);
    return v5;
  }
  v9 = v6 + 1;
  if ( v6 + 1 < v6 )
  {
    v5 = -1073741675;
    v7 = "SIZE_T arithmetic failed [%x]";
    v8 = 490;
    goto LABEL_23;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v6 + 1);
  v11 = Heap;
  if ( Heap )
  {
    if ( v9 )
    {
      if ( v9 <= 0x7FFFFFFF )
      {
        v12 = 2147483646;
        v13 = v11;
        do
        {
          if ( !v12 )
            break;
          if ( !*v2 )
            break;
          *v13++ = *v2++;
          --v12;
          --v9;
        }
        while ( v9 );
        v14 = v13 - 1;
        v5 = v9 == 0 ? 0x80000005 : 0;
        if ( v9 )
          v14 = v13;
        *v14 = 0;
        if ( v9 )
        {
          *a1 = v11;
          return 0;
        }
      }
      else
      {
        v5 = -1073741811;
        *Heap = 0;
      }
    }
    else
    {
      v5 = -1073741811;
    }
    AslLogCallPrintf(1, "AslStringDuplicateA", 507, "RtlStringCchCopyW failed [%x]", v5);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    return v5;
  }
  v5 = -1073741801;
  AslLogCallPrintf(1, "AslStringDuplicateA", 497, "Out of memory");
  return v5;
}

```

## disassembly

```asm
0x18000f130  push    rbx
0x18000f132  push    rsi
0x18000f133  push    rdi
0x18000f134  push    r14
0x18000f136  push    r15
0x18000f138  sub     rsp, 30h
0x18000f13c  mov     r15, rcx
0x18000f13f  mov     qword ptr [rcx], 0
0x18000f146  mov     ecx, 7FFFFFFFh
0x18000f14b  lea     r14, byte_1800216C9
0x18000f152  mov     r8d, ecx
0x18000f155  mov     rax, r14
0x18000f158  cmp     byte ptr [rax], 0
0x18000f15b  jz      short loc_18000F166
0x18000f15d  inc     rax
0x18000f160  sub     r8, 1
0x18000f164  jnz     short loc_18000F158
0x18000f166  mov     rax, r8
0x18000f169  mov     rdx, rcx
0x18000f16c  neg     rax
0x18000f16f  mov     rax, r8
0x18000f172  sbb     ebx, ebx
0x18000f174  sub     rdx, r8
0x18000f177  not     ebx
0x18000f179  and     ebx, 0C000000Dh
0x18000f17f  neg     rax
0x18000f182  sbb     r9, r9
0x18000f185  and     r9, rdx
0x18000f188  test    r8, r8
0x18000f18b  jnz     short loc_18000F19F
0x18000f18d  lea     r9, aRtlstringcchle_0; "RtlStringCchLengthA failed [%x]"
0x18000f194  mov     r8d, 1DFh
0x18000f19a  jmp     loc_18000F2B1
0x18000f19f  lea     rdi, [r9+1]
0x18000f1a3  cmp     rdi, r9
0x18000f1a6  jb      loc_18000F29F
0x18000f1ac  mov     rcx, gs:60h
0x18000f1b5  mov     r8, rdi; Size
0x18000f1b8  mov     edx, 8; Flags
0x18000f1bd  mov     rcx, [rcx+30h]; HeapHandle
0x18000f1c1  call    cs:__imp_RtlAllocateHeap
0x18000f1c7  mov     rsi, rax
0x18000f1ca  test    rax, rax
0x18000f1cd  jnz     short loc_18000F1F5
0x18000f1cf  lea     r9, aOutOfMemory; "Out of memory"
0x18000f1d6  mov     r8d, 1F1h
0x18000f1dc  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x18000f1e3  mov     ebx, 0C0000017h
0x18000f1e8  lea     ecx, [rax+1]
0x18000f1eb  call    AslLogCallPrintf
0x18000f1f0  jmp     loc_18000F2C6
0x18000f1f5  test    rdi, rdi
0x18000f1f8  jz      short loc_18000F256
0x18000f1fa  cmp     rdi, 7FFFFFFFh
0x18000f201  jbe     short loc_18000F20A
0x18000f203  mov     ebx, 0C000000Dh
0x18000f208  jmp     short loc_18000F260
0x18000f20a  mov     eax, 7FFFFFFEh
0x18000f20f  mov     rcx, rsi
0x18000f212  test    rax, rax
0x18000f215  jz      short loc_18000F22F
0x18000f217  mov     dl, [r14]
0x18000f21a  test    dl, dl
0x18000f21c  jz      short loc_18000F22F
0x18000f21e  mov     [rcx], dl
0x18000f220  inc     r14
0x18000f223  inc     rcx
0x18000f226  dec     rax
0x18000f229  sub     rdi, 1
0x18000f22d  jnz     short loc_18000F212
0x18000f22f  mov     rax, rdi
0x18000f232  neg     rax
0x18000f235  lea     rax, [rcx-1]
0x18000f239  sbb     ebx, ebx
0x18000f23b  not     ebx
0x18000f23d  and     ebx, 80000005h
0x18000f243  test    rdi, rdi
0x18000f246  cmovnz  rax, rcx
0x18000f24a  mov     byte ptr [rax], 0
0x18000f24d  jz      short loc_18000F263
0x18000f24f  mov     [r15], rsi
0x18000f252  xor     ebx, ebx
0x18000f254  jmp     short loc_18000F2C6
0x18000f256  mov     ebx, 0C000000Dh
0x18000f25b  test    rdi, rdi
0x18000f25e  jz      short loc_18000F263
0x18000f260  mov     byte ptr [rax], 0
0x18000f263  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000f26a  mov     [rsp+58h+var_38], ebx
0x18000f26e  mov     r8d, 1FBh
0x18000f274  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x18000f27b  mov     ecx, 1
0x18000f280  call    AslLogCallPrintf
0x18000f285  mov     rcx, gs:60h
0x18000f28e  mov     r8, rsi; P
0x18000f291  xor     edx, edx; Flags
0x18000f293  mov     rcx, [rcx+30h]; HeapHandle
0x18000f297  call    cs:__imp_RtlFreeHeap
0x18000f29d  jmp     short loc_18000F2C6
0x18000f29f  mov     ebx, 0C0000095h
0x18000f2a4  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x18000f2ab  mov     r8d, 1EAh
0x18000f2b1  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x18000f2b8  mov     [rsp+58h+var_38], ebx
0x18000f2bc  mov     ecx, 1
0x18000f2c1  call    AslLogCallPrintf
0x18000f2c6  mov     eax, ebx
0x18000f2c8  add     rsp, 30h
0x18000f2cc  pop     r15
0x18000f2ce  pop     r14
0x18000f2d0  pop     rdi
0x18000f2d1  pop     rsi
0x18000f2d2  pop     rbx
0x18000f2d3  retn
```
