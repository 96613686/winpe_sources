# PrjfPreSetSecurity

- ea: `0x140036f10`
- end: `0x140036f55`
- name: `PrjfPreSetSecurity`
- size: `69`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140036f10`
- `0x14003df88`

## pseudocode

```c
__int64 __fastcall PrjfPreSetSecurity(struct _FLT_CALLBACK_DATA *a1, __int64 a2)
{
  unsigned int v2; // edi
  int v4; // eax

  v2 = 1;
  v4 = PrjfSetPlaceHolderFlagsSynchronized(a1, *(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
  if ( v4 < 0 )
  {
    a1->IoStatus.Status = v4;
    v2 = 4;
    a1->IoStatus.Information = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x140036f10  mov     [rsp+arg_0], rbx
0x140036f15  push    rdi
0x140036f16  sub     rsp, 20h
0x140036f1a  mov     r8, [rdx+20h]; FileObject
0x140036f1e  mov     edi, 1
0x140036f23  mov     rdx, [rdx+18h]; Instance
0x140036f27  mov     rbx, rcx
0x140036f2a  lea     r9d, [rdi+1]
0x140036f2e  call    PrjfSetPlaceHolderFlagsSynchronized
0x140036f33  test    eax, eax
0x140036f35  jns     short loc_140036F47
0x140036f37  mov     [rbx+18h], eax
0x140036f3a  mov     edi, 4
0x140036f3f  mov     qword ptr [rbx+20h], 0
0x140036f47  mov     rbx, [rsp+28h+arg_0]
0x140036f4c  mov     eax, edi
0x140036f4e  add     rsp, 20h
0x140036f52  pop     rdi
0x140036f53  retn
```
