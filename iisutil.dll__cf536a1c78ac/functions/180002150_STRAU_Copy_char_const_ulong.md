# STRAU::Copy(char const *,ulong)

- ea: `0x180002150`
- end: `0x180002207`
- name: `?Copy@STRAU@@QEAAHPEBDK@Z`
- size: `183`
- prototype: `int(STRAU *__hidden this, const char *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800144c0`
- `0x18001a6c0`

## callees

- `0x180002150`
- `0x180002da0`
- `0x18002e516`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021f7`

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
0x180002150  push    rbx
0x180002152  push    rbp
0x180002153  push    rsi
0x180002154  push    rdi
0x180002155  push    r14
0x180002157  sub     rsp, 20h
0x18000215b  mov     rax, [rcx+28h]
0x18000215f  mov     rdi, rcx
0x180002162  add     rcx, 8; this
0x180002166  mov     ebp, r8d
0x180002169  mov     r14, rdx
0x18000216c  mov     byte ptr [rax], 0
0x18000216f  xor     eax, eax
0x180002171  mov     r9, [rdi+58h]
0x180002175  lea     ebx, [rax+1]
0x180002178  mov     [r9], ax
0x18000217c  mov     [rdi+6Ch], ebx
0x18000217f  mov     [rdi+68h], ebx
0x180002182  mov     [rdi], rax
0x180002185  test    rdx, rdx
0x180002188  jz      short loc_1800021C5
0x18000218a  mov     ebx, [rdi+70h]
0x18000218d  test    ebx, ebx
0x18000218f  jz      short loc_1800021C5
0x180002191  mov     eax, [rdi+30h]
0x180002194  lea     rdx, [rbp+1]; unsigned int
0x180002198  cmp     rax, rdx
0x18000219b  jb      short loc_1800021E8
0x18000219d  mov     ecx, [rdi+4]
0x1800021a0  mov     r8, rbp; Size
0x1800021a3  add     rcx, [rdi+28h]; void *
0x1800021a7  mov     rdx, r14; Src
0x1800021aa  call    memcpy_0
0x1800021af  add     [rdi+4], ebp
0x1800021b2  mov     ecx, [rdi+4]
0x1800021b5  mov     rax, [rdi+28h]
0x1800021b9  mov     byte ptr [rcx+rax], 0
0x1800021bd  mov     qword ptr [rdi+68h], 0
0x1800021c5  mov     eax, ebx
0x1800021c7  add     rsp, 20h
0x1800021cb  pop     r14
0x1800021cd  pop     rdi
0x1800021ce  pop     rsi
0x1800021cf  pop     rbp
0x1800021d0  pop     rbx
0x1800021d1  retn
0x1800021d3  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800021d8  movzx   ebx, al
0x1800021db  test    al, al
0x1800021dd  jnz     short loc_18000219D
0x1800021df  mov     dword ptr [rdi+70h], 0
0x1800021e6  jmp     short loc_1800021C5
0x1800021e8  mov     eax, 0FFFFFFFFh
0x1800021ed  cmp     rdx, rax
0x1800021f0  jbe     short loc_1800021D3
0x1800021f2  mov     ecx, 216h; dwErrCode
0x1800021f7  call    cs:__imp_SetLastError
0x1800021fe  nop     dword ptr [rax+rax+00h]
0x180002203  xor     ebx, ebx
0x180002205  jmp     short loc_1800021C5
```
