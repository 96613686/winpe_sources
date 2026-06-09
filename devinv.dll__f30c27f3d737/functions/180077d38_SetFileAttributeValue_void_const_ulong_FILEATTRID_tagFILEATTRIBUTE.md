# _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)

- ea: `0x180077d38`
- end: `0x180077fb5`
- name: `?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z`
- size: `637`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180074370`
- `0x180076830`
- `0x180077c64`

## callees

- `0x180006e94`
- `0x180066c10`
- `0x180077d38`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180077e12`
- `ntdll!RtlAllocateHeap` at `0x180077e12`
- `ntdll!RtlFreeHeap` at `0x180077ec1`
- `ntdll!RtlFreeHeap` at `0x180077ec1`

## string_xrefs

- `0x180077ddc`: `_SetFileAttributeValue`
- `0x180077e43`: `_SetFileAttributeValue`
- `0x180077e91`: `_SetFileAttributeValue`
- `0x180077e7f`: `Failed to copy attribute value (index %d) [%x]`
- `0x180077f55`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _SetFileAttributeValue(const wchar_t *a1, unsigned int a2, int a3, __int64 a4)
{
  __int64 v4; // r15
  const wchar_t *v6; // rsi
  unsigned int v7; // ebx
  unsigned int v8; // r12d
  rsize_t v9; // rbp
  const char *v10; // r9
  __int64 v11; // r8
  wchar_t *Heap; // rcx
  __int64 v13; // rdi
  errno_t v14; // eax
  void *v15; // r8
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // r8
  _WORD *v19; // rcx
  unsigned int v21; // [rsp+28h] [rbp-50h]

  v4 = a3;
  v6 = a1;
  v7 = -2147024809;
  if ( !a4 )
    return v7;
  if ( !a1 )
    return 0;
  v8 = dword_180155384[6 * a3];
  if ( v8 <= 2 )
  {
    v13 = a4 + 544LL * a3;
    *(_DWORD *)v13 = *(_DWORD *)a1;
    goto LABEL_30;
  }
  if ( v8 == 3 )
  {
    v13 = a4 + 544LL * a3;
    *(_QWORD *)v13 = *(_QWORD *)a1;
    goto LABEL_30;
  }
  if ( v8 != 4 )
    return v7;
  v9 = a2 >> 1;
  if ( (unsigned int)v9 <= 0x103 )
  {
    v13 = a4 + 544LL * a3;
    v16 = (unsigned __int64)a2 >> 1;
    if ( v16 <= 0x7FFFFFFE )
    {
      v17 = 260;
      v18 = (_WORD *)(a4 + 544LL * a3);
      do
      {
        if ( !v16 )
          break;
        if ( !*v6 )
          break;
        *v18++ = *v6++;
        --v16;
        --v17;
      }
      while ( v17 );
      v7 = v17 == 0 ? 0x8007007A : 0;
      v19 = v18 - 1;
      if ( v17 )
        v19 = v18;
      *v19 = 0;
      if ( v17 )
        goto LABEL_30;
    }
    else
    {
      *(_WORD *)v13 = 0;
    }
    v21 = v7;
    v10 = "StringCbCopy failed to copy string attribute (index %d) [%x]";
    v11 = 3178;
    goto LABEL_9;
  }
  if ( (unsigned int)v9 > 0x1000 )
  {
    v7 = -2147024774;
    v21 = a2;
    v10 = "Attribute (index %d) was too large. Size was %x bytes";
    v11 = 3132;
LABEL_9:
    AslLogCallPrintf(1, "_SetFileAttributeValue", v11, v10, v4, v21);
    return v7;
  }
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v9 + 1));
  v13 = a4 + 544 * v4;
  *(_QWORD *)(v13 + 536) = Heap;
  if ( !Heap )
  {
    v7 = -2147024882;
    AslLogCallPrintf(1, "_SetFileAttributeValue", 3144, "Failed to alloc memory for string value (index %d)", v4);
    return v7;
  }
  v14 = o_wmemcpy_s_0(Heap, (unsigned int)(v9 + 1), v6, v9);
  v7 = v14;
  if ( !v14 )
  {
    *(_WORD *)(*(_QWORD *)(v13 + 536) + 2 * v9) = 0;
    *(_WORD *)v13 = 0;
LABEL_30:
    *(_DWORD *)(v13 + 520) = v4;
    *(_DWORD *)(v13 + 524) = v8;
    *(_DWORD *)(v13 + 528) = 1;
    return 0;
  }
  if ( v14 > 0 )
    v7 = (unsigned __int16)v14 | 0x80070000;
  AslLogCallPrintf(1, "_SetFileAttributeValue", 3156, "Failed to copy attribute value (index %d) [%x]", v4, v7);
  v15 = *(void **)(v13 + 536);
  if ( v15 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    *(_QWORD *)(v13 + 536) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180077d38  push    rbx
0x180077d3a  push    rbp
0x180077d3b  push    rsi
0x180077d3c  push    rdi
0x180077d3d  push    r12
0x180077d3f  push    r13
0x180077d41  push    r14
0x180077d43  push    r15
0x180077d45  sub     rsp, 38h
0x180077d49  xor     r13d, r13d
0x180077d4c  movsxd  r15, r8d
0x180077d4f  mov     r14, r9
0x180077d52  mov     rsi, rcx
0x180077d55  mov     ebx, 80070057h
0x180077d5a  test    r9, r9
0x180077d5d  jz      loc_180077FA2
0x180077d63  test    rcx, rcx
0x180077d66  jz      loc_180077F9F
0x180077d6c  lea     rax, [r15+r15*2]
0x180077d70  mov     rdi, r15
0x180077d73  lea     r12, dword_180155384
0x180077d7a  mov     r12d, [r12+rax*8]
0x180077d7e  mov     ecx, r12d
0x180077d81  test    r12d, r12d
0x180077d84  jz      loc_180077F79
0x180077d8a  sub     ecx, 1
0x180077d8d  jz      loc_180077F79
0x180077d93  sub     ecx, 1
0x180077d96  jz      loc_180077F79
0x180077d9c  sub     ecx, 1
0x180077d9f  jz      loc_180077F67
0x180077da5  cmp     ecx, 1
0x180077da8  jnz     loc_180077FA2
0x180077dae  mov     ebp, edx
0x180077db0  shr     ebp, 1
0x180077db2  cmp     ebp, 103h
0x180077db8  jbe     loc_180077EE8
0x180077dbe  cmp     ebp, 1000h
0x180077dc4  jbe     short loc_180077DF7
0x180077dc6  mov     ebx, 8007007Ah
0x180077dcb  mov     [rsp+78h+var_50], edx
0x180077dcf  lea     r9, aAttributeIndex; "Attribute (index %d) was too large. Siz"...
0x180077dd6  mov     r8d, 0C3Ch
0x180077ddc  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180077de3  mov     [rsp+78h+var_58], r15d
0x180077de8  mov     ecx, 1
0x180077ded  call    AslLogCallPrintf
0x180077df2  jmp     loc_180077FA2
0x180077df7  mov     rcx, gs:60h
0x180077e00  lea     eax, [rbp+1]
0x180077e03  lea     r8, [rax+rax]; Size
0x180077e07  mov     ebx, eax
0x180077e09  mov     edx, 8; Flags
0x180077e0e  mov     rcx, [rcx+30h]; HeapHandle
0x180077e12  call    cs:__imp_RtlAllocateHeap
0x180077e18  imul    rdi, 220h
0x180077e1f  mov     rcx, rax; S1
0x180077e22  add     rdi, r14
0x180077e25  mov     [rdi+218h], rax
0x180077e2c  test    rax, rax
0x180077e2f  jnz     short loc_180077E5C
0x180077e31  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x180077e38  mov     [rsp+78h+var_58], r15d
0x180077e3d  mov     r8d, 0C48h
0x180077e43  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180077e4a  lea     ecx, [rax+1]
0x180077e4d  mov     ebx, 8007000Eh
0x180077e52  call    AslLogCallPrintf
0x180077e57  jmp     loc_180077FA2
0x180077e5c  mov     r9, rbp; N
0x180077e5f  mov     r8, rsi; S2
0x180077e62  mov     rdx, rbx; N1
0x180077e65  call    _o_wmemcpy_s_0
0x180077e6a  mov     ebx, eax
0x180077e6c  test    eax, eax
0x180077e6e  jz      short loc_180077ED3
0x180077e70  jle     short loc_180077E7B
0x180077e72  movzx   ebx, ax
0x180077e75  or      ebx, 80070000h
0x180077e7b  mov     [rsp+78h+var_50], ebx
0x180077e7f  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x180077e86  mov     r8d, 0C54h
0x180077e8c  mov     [rsp+78h+var_58], r15d
0x180077e91  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180077e98  mov     ecx, 1
0x180077e9d  call    AslLogCallPrintf
0x180077ea2  mov     r8, [rdi+218h]; P
0x180077ea9  test    r8, r8
0x180077eac  jz      loc_180077FA2
0x180077eb2  mov     rcx, gs:60h
0x180077ebb  xor     edx, edx; Flags
0x180077ebd  mov     rcx, [rcx+30h]; HeapHandle
0x180077ec1  call    cs:__imp_RtlFreeHeap
0x180077ec7  mov     [rdi+218h], r13
0x180077ece  jmp     loc_180077FA2
0x180077ed3  mov     rcx, [rdi+218h]
0x180077eda  mov     [rcx+rbp*2], r13w
0x180077edf  mov     [rdi], r13w
0x180077ee3  jmp     loc_180077F87
0x180077ee8  imul    rdi, 220h
0x180077eef  mov     eax, edx
0x180077ef1  add     rdi, r14
0x180077ef4  shr     rax, 1
0x180077ef7  cmp     rax, 7FFFFFFEh
0x180077efd  jbe     short loc_180077F05
0x180077eff  mov     [rdi], r13w
0x180077f03  jmp     short loc_180077F51
0x180077f05  mov     edx, 104h
0x180077f0a  mov     r8, rdi
0x180077f0d  test    rax, rax
0x180077f10  jz      short loc_180077F2F
0x180077f12  movzx   ecx, word ptr [rsi]
0x180077f15  test    cx, cx
0x180077f18  jz      short loc_180077F2F
0x180077f1a  mov     [r8], cx
0x180077f1e  add     rsi, 2
0x180077f22  add     r8, 2
0x180077f26  dec     rax
0x180077f29  sub     rdx, 1
0x180077f2d  jnz     short loc_180077F0D
0x180077f2f  mov     rax, rdx
0x180077f32  mov     ebx, 8007007Ah
0x180077f37  neg     rax
0x180077f3a  sbb     ecx, ecx
0x180077f3c  not     ecx
0x180077f3e  and     ebx, ecx
0x180077f40  lea     rcx, [r8-2]
0x180077f44  test    rdx, rdx
0x180077f47  cmovnz  rcx, r8
0x180077f4b  mov     [rcx], r13w
0x180077f4f  jnz     short loc_180077F87
0x180077f51  mov     [rsp+78h+var_50], ebx
0x180077f55  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x180077f5c  mov     r8d, 0C6Ah
0x180077f62  jmp     loc_180077DDC
0x180077f67  mov     rax, [rsi]
0x180077f6a  imul    rdi, 220h
0x180077f71  add     rdi, r14
0x180077f74  mov     [rdi], rax
0x180077f77  jmp     short loc_180077F87
0x180077f79  mov     eax, [rsi]
0x180077f7b  imul    rdi, 220h
0x180077f82  add     rdi, r14
0x180077f85  mov     [rdi], eax
0x180077f87  mov     [rdi+208h], r15d
0x180077f8e  mov     [rdi+20Ch], r12d
0x180077f95  mov     dword ptr [rdi+210h], 1
0x180077f9f  mov     ebx, r13d
0x180077fa2  mov     eax, ebx
0x180077fa4  add     rsp, 38h
0x180077fa8  pop     r15
0x180077faa  pop     r14
0x180077fac  pop     r13
0x180077fae  pop     r12
0x180077fb0  pop     rdi
0x180077fb1  pop     rsi
0x180077fb2  pop     rbp
0x180077fb3  pop     rbx
0x180077fb4  retn
```
