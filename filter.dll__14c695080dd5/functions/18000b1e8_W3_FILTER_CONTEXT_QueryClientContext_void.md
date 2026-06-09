# W3_FILTER_CONTEXT::QueryClientContext(void *)

- ea: `0x18000b1e8`
- end: `0x18000b227`
- name: `?QueryClientContext@W3_FILTER_CONTEXT@@QEAAPEAXPEAX@Z`
- size: `63`
- prototype: `void *__fastcall(W3_FILTER_CONTEXT *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a20`
- `0x18000af48`

## callees

- `0x18000b1e8`
- `0x18000b230`

## pseudocode

```c
void *__fastcall W3_FILTER_CONTEXT::QueryClientContext(W3_FILTER_CONTEXT *this, void *a2)
{
  struct W3_FILTER_CONNECTION_CONTEXT *ConnectionContext; // rax
  __int64 i; // rcx
  void *v5; // rdx

  ConnectionContext = W3_FILTER_CONTEXT::QueryConnectionContext(this);
  if ( ConnectionContext )
  {
    for ( i = 0; (unsigned int)i < 0x32; i = (unsigned int)(i + 1) )
    {
      v5 = (void *)*((_QWORD *)ConnectionContext + i + 52);
      if ( v5 == a2 )
        return (void *)*((_QWORD *)ConnectionContext + i + 2);
      if ( !v5 )
        return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b1e8  push    rbx
0x18000b1ea  sub     rsp, 20h
0x18000b1ee  mov     rbx, rdx
0x18000b1f1  call    ?QueryConnectionContext@W3_FILTER_CONTEXT@@QEAAPEAVW3_FILTER_CONNECTION_CONTEXT@@XZ; W3_FILTER_CONTEXT::QueryConnectionContext(void)
0x18000b1f6  test    rax, rax
0x18000b1f9  jz      short loc_18000B21F
0x18000b1fb  xor     ecx, ecx
0x18000b1fd  cmp     ecx, 32h ; '2'
0x18000b200  jnb     short loc_18000B21F
0x18000b202  mov     rdx, [rax+rcx*8+1A0h]
0x18000b20a  cmp     rdx, rbx
0x18000b20d  jz      short loc_18000B218
0x18000b20f  test    rdx, rdx
0x18000b212  jz      short loc_18000B21F
0x18000b214  inc     ecx
0x18000b216  jmp     short loc_18000B1FD
0x18000b218  mov     rax, [rax+rcx*8+10h]
0x18000b21d  jmp     short loc_18000B221
0x18000b21f  xor     eax, eax
0x18000b221  add     rsp, 20h
0x18000b225  pop     rbx
0x18000b226  retn
```
