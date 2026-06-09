# W3_FILTER_CONTEXT::SetClientContext(void *,void *)

- ea: `0x18000c648`
- end: `0x18000c69a`
- name: `?SetClientContext@W3_FILTER_CONTEXT@@QEAAXPEAX0@Z`
- size: `82`
- prototype: `void __fastcall(W3_FILTER_CONTEXT *__hidden this, void *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a20`
- `0x18000af48`
- `0x18000c6a0`

## callees

- `0x18000b230`
- `0x18000c648`

## pseudocode

```c
void __fastcall W3_FILTER_CONTEXT::SetClientContext(W3_FILTER_CONTEXT *this, void *a2, void *a3)
{
  struct W3_FILTER_CONNECTION_CONTEXT *ConnectionContext; // rax
  __int64 i; // r9
  void *v7; // rdx

  ConnectionContext = W3_FILTER_CONTEXT::QueryConnectionContext(this);
  if ( ConnectionContext )
  {
    for ( i = 0; (unsigned int)i < 0x32; i = (unsigned int)(i + 1) )
    {
      v7 = (void *)*((_QWORD *)ConnectionContext + i + 52);
      if ( v7 == a2 )
        goto LABEL_8;
      if ( !v7 )
      {
        *((_QWORD *)ConnectionContext + i + 52) = a2;
LABEL_8:
        *((_QWORD *)ConnectionContext + i + 2) = a3;
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x18000c648  mov     [rsp+arg_0], rbx
0x18000c64d  push    rdi
0x18000c64e  sub     rsp, 20h
0x18000c652  mov     rbx, r8
0x18000c655  mov     rdi, rdx
0x18000c658  call    ?QueryConnectionContext@W3_FILTER_CONTEXT@@QEAAPEAVW3_FILTER_CONNECTION_CONTEXT@@XZ; W3_FILTER_CONTEXT::QueryConnectionContext(void)
0x18000c65d  test    rax, rax
0x18000c660  jz      short loc_18000C68F
0x18000c662  xor     r9d, r9d
0x18000c665  cmp     r9d, 32h ; '2'
0x18000c669  jnb     short loc_18000C68F
0x18000c66b  mov     rdx, [rax+r9*8+1A0h]
0x18000c673  cmp     rdx, rdi
0x18000c676  jz      short loc_18000C68A
0x18000c678  test    rdx, rdx
0x18000c67b  jz      short loc_18000C682
0x18000c67d  inc     r9d
0x18000c680  jmp     short loc_18000C665
0x18000c682  mov     [rax+r9*8+1A0h], rdi
0x18000c68a  mov     [rax+r9*8+10h], rbx
0x18000c68f  mov     rbx, [rsp+28h+arg_0]
0x18000c694  add     rsp, 20h
0x18000c698  pop     rdi
0x18000c699  retn
```
