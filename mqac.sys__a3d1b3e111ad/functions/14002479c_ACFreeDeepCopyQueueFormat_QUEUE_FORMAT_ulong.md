# ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)

- ea: `0x14002479c`
- end: `0x1400247f4`
- name: `?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z`
- size: `88`
- prototype: `void __fastcall(struct QUEUE_FORMAT *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140004d64`
- `0x14000533c`
- `0x1400058fc`
- `0x14000881c`
- `0x14002186c`

## callees

- `0x1400010a4`
- `0x14002479c`

## pseudocode

```c
void __fastcall ACFreeDeepCopyQueueFormat(struct QUEUE_FORMAT *a1, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 v5; // rsi
  __int64 v6; // rcx
  char v7; // al
  void *v8; // rcx

  v2 = 0;
  if ( a2 )
  {
    v5 = 0;
    while ( 1 )
    {
      v6 = 32 * v5;
      v7 = *((_BYTE *)a1 + 32 * v5);
      if ( v7 == 3 )
        break;
      if ( v7 == 6 )
      {
        v8 = *(void **)((char *)a1 + v6 + 24);
        goto LABEL_7;
      }
      if ( v7 == 8 )
        break;
LABEL_8:
      ++v2;
      ++v5;
      if ( v2 >= a2 )
        goto LABEL_9;
    }
    v8 = *(void **)((char *)a1 + v6 + 8);
LABEL_7:
    operator delete(v8);
    goto LABEL_8;
  }
LABEL_9:
  operator delete(a1);
}

```

## disassembly

```asm
0x14002479c  push    rbx
0x14002479e  push    rbp
0x14002479f  push    rsi
0x1400247a0  push    rdi
0x1400247a1  sub     rsp, 28h
0x1400247a5  xor     edi, edi
0x1400247a7  mov     ebp, edx
0x1400247a9  mov     rbx, rcx
0x1400247ac  test    edx, edx
0x1400247ae  jz      short loc_1400247DB
0x1400247b0  xor     esi, esi
0x1400247b2  mov     rcx, rsi
0x1400247b5  shl     rcx, 5
0x1400247b9  mov     al, [rcx+rbx]
0x1400247bc  cmp     al, 3
0x1400247be  jz      short loc_1400247C8
0x1400247c0  cmp     al, 6
0x1400247c2  jz      short loc_1400247ED
0x1400247c4  cmp     al, 8
0x1400247c6  jnz     short loc_1400247D2
0x1400247c8  mov     rcx, [rcx+rbx+8]; void *
0x1400247cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400247d2  inc     edi
0x1400247d4  inc     rsi
0x1400247d7  cmp     edi, ebp
0x1400247d9  jb      short loc_1400247B2
0x1400247db  mov     rcx, rbx; void *
0x1400247de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400247e3  add     rsp, 28h
0x1400247e7  pop     rdi
0x1400247e8  pop     rsi
0x1400247e9  pop     rbp
0x1400247ea  pop     rbx
0x1400247eb  retn
0x1400247ed  mov     rcx, [rcx+rbx+18h]
0x1400247f2  jmp     short loc_1400247CD
```
