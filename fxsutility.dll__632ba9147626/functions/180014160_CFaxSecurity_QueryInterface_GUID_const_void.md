# CFaxSecurity::QueryInterface(_GUID const &,void * *)

- ea: `0x180014160`
- end: `0x1800141ba`
- name: `?QueryInterface@CFaxSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(CFaxSecurity *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014160`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::QueryInterface(CFaxSecurity *this, const struct _GUID *a2, void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISecurityInformation.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISecurityInformation.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CFaxSecurity *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180014160  sub     rsp, 28h
0x180014164  mov     rax, [rdx]
0x180014167  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18001416e  jnz     short loc_18001417D
0x180014170  mov     rax, [rdx+8]
0x180014174  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18001417b  jz      short loc_180014196
0x18001417d  mov     rax, [rdx]
0x180014180  cmp     rax, qword ptr cs:IID_ISecurityInformation.Data1
0x180014187  jnz     short loc_1800141A9
0x180014189  mov     rax, [rdx+8]
0x18001418d  cmp     rax, qword ptr cs:IID_ISecurityInformation.Data4
0x180014194  jnz     short loc_1800141A9
0x180014196  mov     [r8], rcx
0x180014199  mov     rax, [rcx]
0x18001419c  mov     rax, [rax+8]
0x1800141a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141a5  xor     eax, eax
0x1800141a7  jmp     short loc_1800141B5
0x1800141a9  mov     qword ptr [r8], 0
0x1800141b0  mov     eax, 80004002h
0x1800141b5  add     rsp, 28h
0x1800141b9  retn
```
