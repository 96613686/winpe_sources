# ISAPI_REQUEST::AppendLog(char *,ushort)

- ea: `0x18000c530`
- end: `0x18000c5e1`
- name: `?AppendLog@ISAPI_REQUEST@@UEAAJPEADG@Z`
- size: `177`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, char *, unsigned __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c530`
- `0x180013010`

## import_xrefs

- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x18000c569`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x18000c569`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x18000c5b9`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x18000c5b9`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000c5cc`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000c5cc`

## pseudocode

```c
int __fastcall ISAPI_REQUEST::AppendLog(ISAPI_REQUEST *this, char *a2, __int16 a3)
{
  char *v3; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  int result; // eax

  v3 = (char *)this + 32;
  if ( a3 )
    *(_WORD *)(*(_QWORD *)v3 + 400LL) = a3;
  if ( !*a2 )
    return 0;
  if ( !STRA::IsEmpty((STRA *)(*(_QWORD *)v3 + 216LL)) )
    return STRA::Append((STRA *)(*(_QWORD *)v3 + 216LL), a2);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  v8 = *(_QWORD *)(v7 + 96);
  if ( !v8 )
    return STRA::Append((STRA *)(*(_QWORD *)v3 + 216LL), a2);
  if ( !*(_WORD *)(v7 + 70) )
    return STRA::Append((STRA *)(*(_QWORD *)v3 + 216LL), a2);
  result = STRA::CopyWTruncate(
             (STRA *)(*(_QWORD *)v3 + 216LL),
             (const unsigned __int16 *)(v8 + 2),
             (*(unsigned __int16 *)(v7 + 70) >> 1) - 1);
  if ( result >= 0 )
    return STRA::Append((STRA *)(*(_QWORD *)v3 + 216LL), a2);
  return result;
}

```

## disassembly

```asm
0x18000c530  push    rbx
0x18000c532  push    rbp
0x18000c533  push    rsi
0x18000c534  push    rdi
0x18000c535  push    r14
0x18000c537  sub     rsp, 20h
0x18000c53b  xor     ebp, ebp
0x18000c53d  lea     rbx, [rcx+20h]
0x18000c541  mov     rdi, rdx
0x18000c544  mov     rsi, rcx
0x18000c547  test    r8w, r8w
0x18000c54b  jz      short loc_18000C558
0x18000c54d  mov     rax, [rbx]
0x18000c550  mov     [rax+190h], r8w
0x18000c558  cmp     [rdx], bpl
0x18000c55b  jz      short loc_18000C5D4
0x18000c55d  mov     rcx, [rbx]
0x18000c560  mov     r14d, 0D8h
0x18000c566  add     rcx, r14
0x18000c569  call    cs:__imp_?IsEmpty@STRA@@QEBA_NXZ; STRA::IsEmpty(void)
0x18000c56f  test    al, al
0x18000c571  jz      short loc_18000C5C3
0x18000c573  mov     rcx, [rsi+18h]
0x18000c577  mov     rax, [rcx]
0x18000c57a  mov     rax, [rax+18h]
0x18000c57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c583  mov     rdx, rax
0x18000c586  mov     rcx, [rax]
0x18000c589  mov     rax, [rcx+8]
0x18000c58d  mov     rcx, rdx
0x18000c590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c595  mov     rdx, [rax+60h]
0x18000c599  test    rdx, rdx
0x18000c59c  jz      short loc_18000C5C3
0x18000c59e  cmp     [rax+46h], bp
0x18000c5a2  jz      short loc_18000C5C3
0x18000c5a4  movzx   r8d, word ptr [rax+46h]
0x18000c5a9  add     rdx, 2
0x18000c5ad  mov     rcx, [rbx]
0x18000c5b0  shr     r8d, 1
0x18000c5b3  add     rcx, r14
0x18000c5b6  dec     r8d
0x18000c5b9  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBGK@Z; STRA::CopyWTruncate(ushort const *,ulong)
0x18000c5bf  test    eax, eax
0x18000c5c1  js      short loc_18000C5D6
0x18000c5c3  mov     rcx, [rbx]
0x18000c5c6  mov     rdx, rdi
0x18000c5c9  add     rcx, r14
0x18000c5cc  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000c5d2  jmp     short loc_18000C5D6
0x18000c5d4  xor     eax, eax
0x18000c5d6  add     rsp, 20h
0x18000c5da  pop     r14
0x18000c5dc  pop     rdi
0x18000c5dd  pop     rsi
0x18000c5de  pop     rbp
0x18000c5df  pop     rbx
0x18000c5e0  retn
```
