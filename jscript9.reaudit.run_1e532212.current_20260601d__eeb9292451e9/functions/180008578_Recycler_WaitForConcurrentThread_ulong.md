# Recycler::WaitForConcurrentThread(ulong)

- ea: `0x180008578`
- end: `0x1800085f5`
- name: `?WaitForConcurrentThread@Recycler@@AEAAHK@Z`
- size: `125`
- prototype: `__int64 __fastcall(Recycler *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ac0`
- `0x180008030`
- `0x180008454`

## callees

- `0x180008578`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x1800085c3`
- `KERNEL32!SetThreadPriority` at `0x1800085e4`
- `KERNEL32!SetThreadPriority` at `0x1800085c3`
- `KERNEL32!SetThreadPriority` at `0x1800085e4`
- `KERNEL32!WaitForSingleObject` at `0x1800085a5`
- `KERNEL32!WaitForSingleObject` at `0x1800085a5`

## pseudocode

```c
_BOOL8 __fastcall Recycler::WaitForConcurrentThread(Recycler *this, DWORD a2)
{
  void *v3; // rcx
  DWORD v4; // eax
  void *v5; // rcx
  DWORD v6; // edi

  v3 = (void *)*((_QWORD *)this + 1619);
  if ( v3 )
    SetThreadPriority(v3, 0);
  v4 = WaitForSingleObject(*((HANDLE *)this + 1618), a2);
  v5 = (void *)*((_QWORD *)this + 1619);
  v6 = v4;
  if ( v5 )
  {
    if ( v4 == 258 )
    {
      *((_BYTE *)this + 12910) = 1;
    }
    else
    {
      SetThreadPriority(v5, -1);
      *((_BYTE *)this + 12910) = 0;
    }
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x180008578  mov     rax, rsp
0x18000857b  mov     [rax+18h], rbx
0x18000857f  mov     [rax+10h], edx
0x180008582  mov     [rax+8], rcx
0x180008586  push    rdi
0x180008587  sub     rsp, 20h
0x18000858b  mov     rbx, rcx
0x18000858e  mov     rcx, [rcx+3298h]; hThread
0x180008595  test    rcx, rcx
0x180008598  jnz     short loc_1800085E2
0x18000859a  mov     edx, [rsp+28h+dwMilliseconds]; dwMilliseconds
0x18000859e  mov     rcx, [rbx+3290h]; hHandle
0x1800085a5  call    cs:__imp_WaitForSingleObject
0x1800085ab  mov     rcx, [rbx+3298h]; hThread
0x1800085b2  mov     edi, eax
0x1800085b4  test    rcx, rcx
0x1800085b7  jz      short loc_1800085D0
0x1800085b9  cmp     eax, 102h
0x1800085be  jz      short loc_1800085EC
0x1800085c0  or      edx, 0FFFFFFFFh; nPriority
0x1800085c3  call    cs:__imp_SetThreadPriority
0x1800085c9  mov     byte ptr [rbx+326Eh], 0
0x1800085d0  mov     rbx, [rsp+28h+arg_10]
0x1800085d5  xor     eax, eax
0x1800085d7  test    edi, edi
0x1800085d9  setz    al
0x1800085dc  add     rsp, 20h
0x1800085e0  pop     rdi
0x1800085e1  retn
0x1800085e2  xor     edx, edx; nPriority
0x1800085e4  call    cs:__imp_SetThreadPriority
0x1800085ea  jmp     short loc_18000859A
0x1800085ec  mov     byte ptr [rbx+326Eh], 1
0x1800085f3  jmp     short loc_1800085D0
```
