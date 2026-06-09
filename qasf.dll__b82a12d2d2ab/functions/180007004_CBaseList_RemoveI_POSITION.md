# CBaseList::RemoveI(__POSITION *)

- ea: `0x180007004`
- end: `0x180007082`
- name: `?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z`
- size: `126`
- prototype: `void *(CBaseList *__hidden this, struct __POSITION *)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008028`
- `0x18000ab04`
- `0x18000c9e4`
- `0x18000e238`
- `0x18000e444`
- `0x18000ea00`
- `0x18000f594`
- `0x180013510`
- `0x18001c28c`
- `0x18001c39c`
- `0x18001c730`

## callees

- `0x180001008`
- `0x180007004`

## pseudocode

```c
__int64 __fastcall CBaseList::RemoveI(CBaseList *this, struct __POSITION *a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi

  if ( !a2 )
    return 0;
  v4 = *((_QWORD *)a2 + 1);
  if ( *(_QWORD *)a2 )
    *(_QWORD *)(*(_QWORD *)a2 + 8LL) = v4;
  else
    *(_QWORD *)this = v4;
  v5 = (_QWORD *)*((_QWORD *)a2 + 1);
  v6 = *(_QWORD *)a2;
  if ( v5 )
    *v5 = v6;
  else
    *((_QWORD *)this + 1) = v6;
  v7 = *((_QWORD *)a2 + 2);
  if ( *((_DWORD *)this + 7) >= *((_DWORD *)this + 6) )
  {
    operator delete(a2);
  }
  else
  {
    *((_QWORD *)a2 + 1) = *((_QWORD *)this + 4);
    ++*((_DWORD *)this + 7);
    *((_QWORD *)this + 4) = a2;
  }
  --*((_DWORD *)this + 4);
  return v7;
}

```

## disassembly

```asm
0x180007004  mov     [rsp+arg_0], rbx
0x180007009  push    rdi
0x18000700a  sub     rsp, 20h
0x18000700e  mov     r8, rdx
0x180007011  mov     rbx, rcx
0x180007014  test    rdx, rdx
0x180007017  jnz     short loc_18000701D
0x180007019  xor     eax, eax
0x18000701b  jmp     short loc_180007077
0x18000701d  mov     rcx, [rdx]
0x180007020  mov     rax, [rdx+8]
0x180007024  test    rcx, rcx
0x180007027  jnz     short loc_18000702E
0x180007029  mov     [rbx], rax
0x18000702c  jmp     short loc_180007032
0x18000702e  mov     [rcx+8], rax
0x180007032  mov     rcx, [rdx+8]
0x180007036  mov     rax, [rdx]
0x180007039  test    rcx, rcx
0x18000703c  jnz     short loc_180007044
0x18000703e  mov     [rbx+8], rax
0x180007042  jmp     short loc_180007047
0x180007044  mov     [rcx], rax
0x180007047  mov     eax, [rbx+18h]
0x18000704a  mov     rdi, [rdx+10h]
0x18000704e  cmp     [rbx+1Ch], eax
0x180007051  jge     short loc_180007064
0x180007053  mov     rax, [rbx+20h]
0x180007057  mov     [rdx+8], rax
0x18000705b  inc     dword ptr [rbx+1Ch]
0x18000705e  mov     [rbx+20h], r8
0x180007062  jmp     short loc_180007071
0x180007064  mov     edx, 18h; unsigned __int64
0x180007069  mov     rcx, r8; void *
0x18000706c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007071  dec     dword ptr [rbx+10h]
0x180007074  mov     rax, rdi
0x180007077  mov     rbx, [rsp+28h+arg_0]
0x18000707c  add     rsp, 20h
0x180007080  pop     rdi
0x180007081  retn
```
