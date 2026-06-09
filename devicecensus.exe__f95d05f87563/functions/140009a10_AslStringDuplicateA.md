# AslStringDuplicateA

- ea: `0x140009a10`
- end: `0x140009bb4`
- name: `AslStringDuplicateA`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140009504`

## callees

- `0x140007074`
- `0x140009a10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140009b77`
- `ntdll!RtlFreeHeap` at `0x140009b77`
- `ntdll!RtlAllocateHeap` at `0x140009aa1`
- `ntdll!RtlAllocateHeap` at `0x140009aa1`

## string_xrefs

- `0x140009b43`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicateA(_QWORD *a1)
{
  __int64 *v2; // r14
  __int64 v3; // r8
  __int64 *v4; // rax
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
  v2 = &qword_1400157F8;
  v3 = 0x7FFFFFFF;
  v4 = &qword_1400157F8;
  do
  {
    if ( !*(_BYTE *)v4 )
      break;
    v4 = (__int64 *)((char *)v4 + 1);
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
          if ( !*(_BYTE *)v2 )
            break;
          *v13 = *(_BYTE *)v2;
          v2 = (__int64 *)((char *)v2 + 1);
          ++v13;
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
0x140009a10  push    rbx
0x140009a12  push    rsi
0x140009a13  push    rdi
0x140009a14  push    r14
0x140009a16  push    r15
0x140009a18  sub     rsp, 30h
0x140009a1c  mov     r15, rcx
0x140009a1f  mov     qword ptr [rcx], 0
0x140009a26  mov     ecx, 7FFFFFFFh
0x140009a2b  lea     r14, qword_1400157F8
0x140009a32  mov     r8d, ecx
0x140009a35  mov     rax, r14
0x140009a38  cmp     byte ptr [rax], 0
0x140009a3b  jz      short loc_140009A46
0x140009a3d  inc     rax
0x140009a40  sub     r8, 1
0x140009a44  jnz     short loc_140009A38
0x140009a46  mov     rax, r8
0x140009a49  mov     rdx, rcx
0x140009a4c  neg     rax
0x140009a4f  mov     rax, r8
0x140009a52  sbb     ebx, ebx
0x140009a54  sub     rdx, r8
0x140009a57  not     ebx
0x140009a59  and     ebx, 0C000000Dh
0x140009a5f  neg     rax
0x140009a62  sbb     r9, r9
0x140009a65  and     r9, rdx
0x140009a68  test    r8, r8
0x140009a6b  jnz     short loc_140009A7F
0x140009a6d  lea     r9, aRtlstringcchle_0; "RtlStringCchLengthA failed [%x]"
0x140009a74  mov     r8d, 1DFh
0x140009a7a  jmp     loc_140009B91
0x140009a7f  lea     rdi, [r9+1]
0x140009a83  cmp     rdi, r9
0x140009a86  jb      loc_140009B7F
0x140009a8c  mov     rcx, gs:60h
0x140009a95  mov     r8, rdi; Size
0x140009a98  mov     edx, 8; Flags
0x140009a9d  mov     rcx, [rcx+30h]; HeapHandle
0x140009aa1  call    cs:__imp_RtlAllocateHeap
0x140009aa7  mov     rsi, rax
0x140009aaa  test    rax, rax
0x140009aad  jnz     short loc_140009AD5
0x140009aaf  lea     r9, aOutOfMemory; "Out of memory"
0x140009ab6  mov     r8d, 1F1h
0x140009abc  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x140009ac3  mov     ebx, 0C0000017h
0x140009ac8  lea     ecx, [rax+1]
0x140009acb  call    AslLogCallPrintf
0x140009ad0  jmp     loc_140009BA6
0x140009ad5  test    rdi, rdi
0x140009ad8  jz      short loc_140009B36
0x140009ada  cmp     rdi, 7FFFFFFFh
0x140009ae1  jbe     short loc_140009AEA
0x140009ae3  mov     ebx, 0C000000Dh
0x140009ae8  jmp     short loc_140009B40
0x140009aea  mov     eax, 7FFFFFFEh
0x140009aef  mov     rcx, rsi
0x140009af2  test    rax, rax
0x140009af5  jz      short loc_140009B0F
0x140009af7  mov     dl, [r14]
0x140009afa  test    dl, dl
0x140009afc  jz      short loc_140009B0F
0x140009afe  mov     [rcx], dl
0x140009b00  inc     r14
0x140009b03  inc     rcx
0x140009b06  dec     rax
0x140009b09  sub     rdi, 1
0x140009b0d  jnz     short loc_140009AF2
0x140009b0f  mov     rax, rdi
0x140009b12  neg     rax
0x140009b15  lea     rax, [rcx-1]
0x140009b19  sbb     ebx, ebx
0x140009b1b  not     ebx
0x140009b1d  and     ebx, 80000005h
0x140009b23  test    rdi, rdi
0x140009b26  cmovnz  rax, rcx
0x140009b2a  mov     byte ptr [rax], 0
0x140009b2d  jz      short loc_140009B43
0x140009b2f  mov     [r15], rsi
0x140009b32  xor     ebx, ebx
0x140009b34  jmp     short loc_140009BA6
0x140009b36  mov     ebx, 0C000000Dh
0x140009b3b  test    rdi, rdi
0x140009b3e  jz      short loc_140009B43
0x140009b40  mov     byte ptr [rax], 0
0x140009b43  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x140009b4a  mov     [rsp+58h+var_38], ebx
0x140009b4e  mov     r8d, 1FBh
0x140009b54  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x140009b5b  mov     ecx, 1
0x140009b60  call    AslLogCallPrintf
0x140009b65  mov     rcx, gs:60h
0x140009b6e  mov     r8, rsi; P
0x140009b71  xor     edx, edx; Flags
0x140009b73  mov     rcx, [rcx+30h]; HeapHandle
0x140009b77  call    cs:__imp_RtlFreeHeap
0x140009b7d  jmp     short loc_140009BA6
0x140009b7f  mov     ebx, 0C0000095h
0x140009b84  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x140009b8b  mov     r8d, 1EAh
0x140009b91  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x140009b98  mov     [rsp+58h+var_38], ebx
0x140009b9c  mov     ecx, 1
0x140009ba1  call    AslLogCallPrintf
0x140009ba6  mov     eax, ebx
0x140009ba8  add     rsp, 30h
0x140009bac  pop     r15
0x140009bae  pop     r14
0x140009bb0  pop     rdi
0x140009bb1  pop     rsi
0x140009bb2  pop     rbx
0x140009bb3  retn
```
