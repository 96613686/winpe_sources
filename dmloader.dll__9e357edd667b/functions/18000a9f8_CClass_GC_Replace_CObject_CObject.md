# CClass::GC_Replace(CObject *,CObject *)

- ea: `0x18000a9f8`
- end: `0x18000aa67`
- name: `?GC_Replace@CClass@@QEAAXPEAVCObject@@0@Z`
- size: `111`
- prototype: `void __fastcall(CClass *__hidden this, struct CObject *, struct CObject *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a958`

## callees

- `0x18000a9f8`

## pseudocode

```c
void __fastcall CClass::GC_Replace(CClass *this, struct CObject *a2, struct CObject *a3)
{
  struct CObject *v4; // rax
  struct CObject *v5; // rdx
  struct CObject *v6; // r11
  struct CObject *v7; // r10

  if ( a2 )
  {
    v4 = (struct CObject *)*((_QWORD *)this + 25);
    if ( a2 == v4 )
    {
      v5 = *(struct CObject **)v4;
      *(_QWORD *)v4 = 0;
    }
    else
    {
      v6 = 0;
      v5 = (struct CObject *)*((_QWORD *)this + 25);
      if ( v4 )
      {
        while ( 1 )
        {
          v7 = *(struct CObject **)v4;
          if ( v4 == a2 )
            break;
          v6 = v4;
          v4 = *(struct CObject **)v4;
          if ( !v7 )
            goto LABEL_9;
        }
        *(_QWORD *)v6 = v7;
        *(_QWORD *)v4 = 0;
        *(_QWORD *)a2 = 0;
      }
    }
LABEL_9:
    *((_QWORD *)this + 25) = v5;
  }
  if ( a3 )
  {
    *(_QWORD *)a3 = *((_QWORD *)this + 25);
    *((_QWORD *)this + 25) = a3;
  }
}

```

## disassembly

```asm
0x18000a9f8  mov     r9, rdx
0x18000a9fb  test    rdx, rdx
0x18000a9fe  jz      short loc_18000AA50
0x18000aa00  mov     rax, [rcx+0C8h]
0x18000aa07  cmp     rdx, rax
0x18000aa0a  jnz     short loc_18000AA18
0x18000aa0c  mov     rdx, [rax]
0x18000aa0f  mov     qword ptr [rax], 0
0x18000aa16  jmp     short loc_18000AA49
0x18000aa18  xor     r11d, r11d
0x18000aa1b  mov     rdx, rax
0x18000aa1e  test    rax, rax
0x18000aa21  jz      short loc_18000AA49
0x18000aa23  mov     r10, [rax]
0x18000aa26  cmp     rax, r9
0x18000aa29  jz      short loc_18000AA38
0x18000aa2b  mov     r11, rax
0x18000aa2e  mov     rax, r10
0x18000aa31  test    r10, r10
0x18000aa34  jnz     short loc_18000AA23
0x18000aa36  jmp     short loc_18000AA49
0x18000aa38  mov     [r11], r10
0x18000aa3b  mov     qword ptr [rax], 0
0x18000aa42  mov     qword ptr [r9], 0
0x18000aa49  mov     [rcx+0C8h], rdx
0x18000aa50  test    r8, r8
0x18000aa53  jz      short locret_18000AA66
0x18000aa55  mov     rax, [rcx+0C8h]
0x18000aa5c  mov     [r8], rax
0x18000aa5f  mov     [rcx+0C8h], r8
0x18000aa66  retn
```
