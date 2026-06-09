# CADMCOMSrvFactoryW::QueryInterface(_GUID const &,void * *)

- ea: `0x180009e80`
- end: `0x180009ee6`
- name: `?QueryInterface@CADMCOMSrvFactoryW@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CADMCOMSrvFactoryW *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009e80`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMSrvFactoryW::QueryInterface(CADMCOMSrvFactoryW *this, const struct _GUID *a2, void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IClassFactory.Data4 )
  {
    if ( a3 )
    {
      *a3 = this;
      (*(void (__fastcall **)(CADMCOMSrvFactoryW *))(*(_QWORD *)this + 8LL))(this);
      return 0;
    }
    else
    {
      return 2147942487LL;
    }
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
0x180009e80  sub     rsp, 28h
0x180009e84  mov     rax, [rdx]
0x180009e87  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180009e8e  jnz     short loc_180009E9D
0x180009e90  mov     rax, [rdx+8]
0x180009e94  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180009e9b  jz      short loc_180009EB6
0x180009e9d  mov     rax, [rdx]
0x180009ea0  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x180009ea7  jnz     short loc_180009ED5
0x180009ea9  mov     rax, [rdx+8]
0x180009ead  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180009eb4  jnz     short loc_180009ED5
0x180009eb6  test    r8, r8
0x180009eb9  jnz     short loc_180009EC2
0x180009ebb  mov     eax, 80070057h
0x180009ec0  jmp     short loc_180009EE1
0x180009ec2  mov     [r8], rcx
0x180009ec5  mov     rax, [rcx]
0x180009ec8  mov     rax, [rax+8]
0x180009ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed1  xor     eax, eax
0x180009ed3  jmp     short loc_180009EE1
0x180009ed5  mov     qword ptr [r8], 0
0x180009edc  mov     eax, 80004002h
0x180009ee1  add     rsp, 28h
0x180009ee5  retn
```
