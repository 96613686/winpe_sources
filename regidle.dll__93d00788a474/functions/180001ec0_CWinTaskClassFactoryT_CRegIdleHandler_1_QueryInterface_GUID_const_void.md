# CWinTaskClassFactoryT<CRegIdleHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180001ec0`
- end: `0x180001f26`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCRegIdleHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001ec0`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CRegIdleHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *a2 == *(_QWORD *)&IID_IClassFactory.Data1 && a2[1] == *(_QWORD *)IID_IClassFactory.Data4
    || *a2 == *(_QWORD *)&IID_IUnknown.Data1 && a2[1] == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
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
0x180001ec0  sub     rsp, 28h
0x180001ec4  test    r8, r8
0x180001ec7  jnz     short loc_180001ED0
0x180001ec9  mov     eax, 80070057h
0x180001ece  jmp     short loc_180001F21
0x180001ed0  mov     rax, [rdx]
0x180001ed3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x180001eda  jnz     short loc_180001EE9
0x180001edc  mov     rax, [rdx+8]
0x180001ee0  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180001ee7  jz      short loc_180001F02
0x180001ee9  mov     rax, [rdx]
0x180001eec  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180001ef3  jnz     short loc_180001F15
0x180001ef5  mov     rax, [rdx+8]
0x180001ef9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180001f00  jnz     short loc_180001F15
0x180001f02  mov     [r8], rcx
0x180001f05  mov     rax, [rcx]
0x180001f08  mov     rax, [rax+8]
0x180001f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f11  xor     eax, eax
0x180001f13  jmp     short loc_180001F21
0x180001f15  mov     qword ptr [r8], 0
0x180001f1c  mov     eax, 80004002h
0x180001f21  add     rsp, 28h
0x180001f25  retn
```
