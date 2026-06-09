# _CEventSource<CComObjectObserver>::CleanupDeleted(void)

- ea: `0x18000566c`
- end: `0x1800056bb`
- name: `?CleanupDeleted@?$_CEventSource@VCComObjectObserver@@@@AEAAXXZ`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005590`
- `0x180005620`

## callees

- `0x18000566c`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1800056a1`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1800056a1`

## pseudocode

```c
void __fastcall _CEventSource<CComObjectObserver>::CleanupDeleted(__int64 a1)
{
  _QWORD **i; // rcx
  _QWORD **v3; // rdi

  for ( i = **(_QWORD ****)(a1 + 8); i != *(_QWORD ***)(a1 + 8); i = v3 )
  {
    v3 = (_QWORD **)*i;
    if ( *((_BYTE *)i + 24) )
    {
      *i[1] = v3;
      (*i)[1] = i[1];
      operator delete(i);
      --*(_QWORD *)(a1 + 16);
    }
  }
}

```

## disassembly

```asm
0x18000566c  mov     [rsp+arg_0], rbx
0x180005671  push    rdi
0x180005672  sub     rsp, 20h
0x180005676  mov     rbx, rcx
0x180005679  mov     rcx, [rcx+8]
0x18000567d  mov     rcx, [rcx]
0x180005680  cmp     rcx, [rbx+8]
0x180005684  jz      short loc_1800056B0
0x180005686  cmp     byte ptr [rcx+18h], 0
0x18000568a  mov     rdi, [rcx]
0x18000568d  jz      short loc_1800056AB
0x18000568f  mov     rax, [rcx+8]
0x180005693  mov     [rax], rdi
0x180005696  mov     rdx, [rcx]
0x180005699  mov     rax, [rcx+8]
0x18000569d  mov     [rdx+8], rax
0x1800056a1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800056a7  dec     qword ptr [rbx+10h]
0x1800056ab  mov     rcx, rdi
0x1800056ae  jmp     short loc_180005680
0x1800056b0  mov     rbx, [rsp+28h+arg_0]
0x1800056b5  add     rsp, 20h
0x1800056b9  pop     rdi
0x1800056ba  retn
```
