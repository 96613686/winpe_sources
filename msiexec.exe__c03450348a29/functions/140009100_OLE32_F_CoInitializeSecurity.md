# OLE32::F_CoInitializeSecurity

- ea: `0x140009100`
- end: `0x14000918e`
- name: `OLE32::F_CoInitializeSecurity`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140008e98`
- `0x140009100`
- `0x14000a010`

## string_xrefs

- `0x140009118`: `CoInitializeSecurity`

## pseudocode

```c
__int64 __fastcall OLE32::F_CoInitializeSecurity(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  if ( Bind_OLE32("CoInitializeSecurity", &OLE32::CoInitializeSecurity) )
    return ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, int, int, __int64, int, __int64))OLE32::CoInitializeSecurity)(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8,
             a9);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x140009100  push    rbx
0x140009102  push    rbp
0x140009103  push    rsi
0x140009104  push    rdi
0x140009105  sub     rsp, 58h
0x140009109  mov     esi, edx
0x14000910b  mov     rbp, rcx
0x14000910e  lea     rdx, ?CoInitializeSecurity@OLE32@@3P6AJPEAXJPEAUtagSOLE_AUTHENTICATION_SERVICE@@PEAGKK0K0@ZEA; __int64 (**)(void)
0x140009115  mov     rbx, r9
0x140009118  lea     rcx, aCoinitializese; "CoInitializeSecurity"
0x14000911f  mov     rdi, r8
0x140009122  call    ?Bind_OLE32@@YAP6A_JXZPEBDPEAP6A_JXZ@Z; Bind_OLE32(char const *,__int64 (**)(void))
0x140009127  test    rax, rax
0x14000912a  jz      short loc_140009180
0x14000912c  mov     edx, [rsp+78h+arg_38]
0x140009133  mov     r8, rdi
0x140009136  mov     rcx, [rsp+78h+arg_30]
0x14000913e  mov     r9, [rsp+78h+arg_40]
0x140009146  mov     rax, cs:?CoInitializeSecurity@OLE32@@3P6AJPEAXJPEAUtagSOLE_AUTHENTICATION_SERVICE@@PEAGKK0K0@ZEA; long (*OLE32::CoInitializeSecurity)(void *,long,tagSOLE_AUTHENTICATION_SERVICE *,ushort *,ulong,ulong,void *,ulong,void *)
0x14000914d  mov     [rsp+78h+var_38], r9
0x140009152  mov     r9, rbx
0x140009155  mov     [rsp+78h+var_40], edx
0x140009159  mov     edx, esi
0x14000915b  mov     [rsp+78h+var_48], rcx
0x140009160  mov     ecx, [rsp+78h+arg_28]
0x140009167  mov     [rsp+78h+var_50], ecx
0x14000916b  mov     ecx, [rsp+78h+arg_20]
0x140009172  mov     [rsp+78h+var_58], ecx
0x140009176  mov     rcx, rbp
0x140009179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000917e  jmp     short loc_140009185
0x140009180  mov     eax, 80004005h
0x140009185  add     rsp, 58h
0x140009189  pop     rdi
0x14000918a  pop     rsi
0x14000918b  pop     rbp
0x14000918c  pop     rbx
0x14000918d  retn
```
