# STRAU::Copy(char const *,ulong)

- ea: `0x180001870`
- end: `0x180001920`
- name: `?Copy@STRAU@@QEAAHPEBDK@Z`
- size: `176`
- prototype: `int(STRAU *__hidden this, const char *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180013a70`
- `0x180019850`

## callees

- `0x180001870`
- `0x180002470`
- `0x18002c476`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001916`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001916`

## pseudocode

```c
__int64 __fastcall STRAU::Copy(STRAU *this, const char *a2, unsigned int a3)
{
  _BYTE *v3; // rax
  BUFFER *v5; // rcx
  size_t v6; // rbp
  unsigned int v8; // ebx
  unsigned __int64 v9; // rdx
  bool v11; // al

  v3 = (_BYTE *)*((_QWORD *)this + 5);
  v5 = (STRAU *)((char *)this + 8);
  v6 = a3;
  *v3 = 0;
  v8 = 1;
  **((_WORD **)this + 11) = 0;
  *((_DWORD *)this + 27) = 1;
  *((_DWORD *)this + 26) = 1;
  *(_QWORD *)this = 0;
  if ( a2 )
  {
    v8 = *((_DWORD *)this + 28);
    if ( v8 )
    {
      v9 = a3 + 1LL;
      if ( *((unsigned int *)this + 12) >= v9 )
        goto LABEL_4;
      if ( v9 > 0xFFFFFFFF )
      {
        SetLastError(0x216u);
        return 0;
      }
      v11 = BUFFER::Resize(v5, v9);
      v8 = v11;
      if ( v11 )
      {
LABEL_4:
        memcpy_0((void *)(*((_QWORD *)this + 5) + *((unsigned int *)this + 1)), a2, v6);
        *((_DWORD *)this + 1) += v6;
        *(_BYTE *)(*((unsigned int *)this + 1) + *((_QWORD *)this + 5)) = 0;
        *((_QWORD *)this + 13) = 0;
      }
      else
      {
        *((_DWORD *)this + 28) = 0;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180001870  push    rbx
0x180001872  push    rbp
0x180001873  push    rsi
0x180001874  push    rdi
0x180001875  push    r14
0x180001877  sub     rsp, 20h
0x18000187b  mov     rax, [rcx+28h]
0x18000187f  mov     rdi, rcx
0x180001882  add     rcx, 8; this
0x180001886  mov     ebp, r8d
0x180001889  mov     r14, rdx
0x18000188c  mov     byte ptr [rax], 0
0x18000188f  xor     eax, eax
0x180001891  mov     r9, [rdi+58h]
0x180001895  lea     ebx, [rax+1]
0x180001898  mov     [r9], ax
0x18000189c  mov     [rdi+6Ch], ebx
0x18000189f  mov     [rdi+68h], ebx
0x1800018a2  mov     [rdi], rax
0x1800018a5  test    rdx, rdx
0x1800018a8  jz      short loc_1800018E5
0x1800018aa  mov     ebx, [rdi+70h]
0x1800018ad  test    ebx, ebx
0x1800018af  jz      short loc_1800018E5
0x1800018b1  mov     eax, [rdi+30h]
0x1800018b4  lea     rdx, [rbp+1]; unsigned int
0x1800018b8  cmp     rax, rdx
0x1800018bb  jb      short loc_180001907
0x1800018bd  mov     ecx, [rdi+4]
0x1800018c0  mov     r8, rbp; Size
0x1800018c3  add     rcx, [rdi+28h]; void *
0x1800018c7  mov     rdx, r14; Src
0x1800018ca  call    memcpy_0
0x1800018cf  add     [rdi+4], ebp
0x1800018d2  mov     ecx, [rdi+4]
0x1800018d5  mov     rax, [rdi+28h]
0x1800018d9  mov     byte ptr [rcx+rax], 0
0x1800018dd  mov     qword ptr [rdi+68h], 0
0x1800018e5  mov     eax, ebx
0x1800018e7  add     rsp, 20h
0x1800018eb  pop     r14
0x1800018ed  pop     rdi
0x1800018ee  pop     rsi
0x1800018ef  pop     rbp
0x1800018f0  pop     rbx
0x1800018f1  retn
0x1800018f2  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800018f7  movzx   ebx, al
0x1800018fa  test    al, al
0x1800018fc  jnz     short loc_1800018BD
0x1800018fe  mov     dword ptr [rdi+70h], 0
0x180001905  jmp     short loc_1800018E5
0x180001907  mov     eax, 0FFFFFFFFh
0x18000190c  cmp     rdx, rax
0x18000190f  jbe     short loc_1800018F2
0x180001911  mov     ecx, 216h; dwErrCode
0x180001916  call    cs:__imp_SetLastError
0x18000191c  xor     ebx, ebx
0x18000191e  jmp     short loc_1800018E5
```
