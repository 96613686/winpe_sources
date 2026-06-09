# std::list<PIXEventsThreadInfo,std::allocator<PIXEventsThreadInfo>>::_Tidy(void)

- ea: `0x180006dd4`
- end: `0x180006e25`
- name: `?_Tidy@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@AEAAXXZ`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006dc0`

## callees

- `0x180006dd4`
- `0x180006e2c`

## pseudocode

```c
void __fastcall std::list<PIXEventsThreadInfo>::_Tidy(void **a1)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v1 = (_QWORD **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      std::_Deallocate<16>(v3, 0x28u);
      v3 = v4;
    }
    while ( v4 );
  }
  std::_Deallocate<16>(*a1, 0x28u);
}

```

## disassembly

```asm
0x180006dd4  mov     [rsp+arg_0], rbx
0x180006dd9  push    rdi
0x180006dda  sub     rsp, 20h
0x180006dde  mov     rdx, [rcx]
0x180006de1  mov     rdi, rcx
0x180006de4  mov     rax, [rdx+8]
0x180006de8  mov     qword ptr [rax], 0
0x180006def  mov     rcx, [rdx]
0x180006df2  test    rcx, rcx
0x180006df5  jnz     short loc_180006E0E
0x180006df7  mov     rcx, [rdi]
0x180006dfa  mov     edx, 28h ; '('
0x180006dff  mov     rbx, [rsp+28h+arg_0]
0x180006e04  add     rsp, 20h
0x180006e08  pop     rdi
0x180006e09  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006e0e  mov     rbx, [rcx]
0x180006e11  mov     edx, 28h ; '('
0x180006e16  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006e1b  mov     rcx, rbx
0x180006e1e  test    rbx, rbx
0x180006e21  jnz     short loc_180006E0E
0x180006e23  jmp     short loc_180006DF7
```
