# CClass::RemoveObject(CObject *)

- ea: `0x18000b9b0`
- end: `0x18000ba4c`
- name: `?RemoveObject@CClass@@QEAAXPEAVCObject@@@Z`
- size: `156`
- prototype: `void __fastcall(CClass *__hidden this, struct CObject *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008bc0`
- `0x180009550`
- `0x18000a1e4`

## callees

- `0x1800019a0`
- `0x18000a178`
- `0x18000b9b0`

## pseudocode

```c
void __fastcall CClass::RemoveObject(CClass *this, struct CObject *a2)
{
  struct CObject *v4; // rbx
  struct CObject *v5; // rdi
  struct CObject *v6; // rcx

  v4 = 0;
  while ( 1 )
  {
    v5 = (struct CObject *)*((_QWORD *)this + 25);
    if ( !v5 )
      break;
    *((_QWORD *)this + 25) = *(_QWORD *)v5;
    *(_QWORD *)v5 = 0;
    if ( v5 != a2 && (a2 || (*((_DWORD *)v5 + 4) & 0xC14) != 0) )
    {
      *(_QWORD *)v5 = v4;
      v4 = v5;
    }
    else
    {
      CObject::~CObject(v5);
      operator delete(v5);
      if ( a2 )
        break;
    }
  }
  while ( v4 )
  {
    v6 = v4;
    v4 = *(struct CObject **)v4;
    *(_QWORD *)v6 = 0;
    *(_QWORD *)v6 = *((_QWORD *)this + 25);
    *((_QWORD *)this + 25) = v6;
  }
  *((_QWORD *)this + 27) = 0;
}

```

## disassembly

```asm
0x18000b9b0  push    rbx
0x18000b9b2  push    rbp
0x18000b9b3  push    rsi
0x18000b9b4  push    rdi
0x18000b9b5  sub     rsp, 28h
0x18000b9b9  mov     rbp, rdx
0x18000b9bc  mov     rsi, rcx
0x18000b9bf  xor     ebx, ebx
0x18000b9c1  mov     rdi, [rsi+0C8h]
0x18000b9c8  test    rdi, rdi
0x18000b9cb  jz      short loc_18000BA13
0x18000b9cd  mov     rax, [rdi]
0x18000b9d0  mov     [rsi+0C8h], rax
0x18000b9d7  mov     qword ptr [rdi], 0
0x18000b9de  cmp     rdi, rbp
0x18000b9e1  jz      short loc_18000B9F9
0x18000b9e3  test    rbp, rbp
0x18000b9e6  jnz     short loc_18000B9F1
0x18000b9e8  test    dword ptr [rdi+10h], 0C14h
0x18000b9ef  jz      short loc_18000B9F9
0x18000b9f1  mov     [rdi], rbx
0x18000b9f4  mov     rbx, rdi
0x18000b9f7  jmp     short loc_18000B9C1
0x18000b9f9  mov     rcx, rdi; this
0x18000b9fc  call    ??1CObject@@QEAA@XZ; CObject::~CObject(void)
0x18000ba01  mov     edx, 0D8h; unsigned __int64
0x18000ba06  mov     rcx, rdi; void *
0x18000ba09  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba0e  test    rbp, rbp
0x18000ba11  jz      short loc_18000B9C1
0x18000ba13  test    rbx, rbx
0x18000ba16  jz      short loc_18000BA38
0x18000ba18  mov     rcx, rbx
0x18000ba1b  mov     rbx, [rbx]
0x18000ba1e  mov     qword ptr [rcx], 0
0x18000ba25  mov     rax, [rsi+0C8h]
0x18000ba2c  mov     [rcx], rax
0x18000ba2f  mov     [rsi+0C8h], rcx
0x18000ba36  jmp     short loc_18000BA13
0x18000ba38  mov     qword ptr [rsi+0D8h], 0
0x18000ba43  add     rsp, 28h
0x18000ba47  pop     rdi
0x18000ba48  pop     rsi
0x18000ba49  pop     rbp
0x18000ba4a  pop     rbx
0x18000ba4b  retn
```
