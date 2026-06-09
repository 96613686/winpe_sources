# CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005670`
- end: `0x1800056d6`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCMapsUpdateTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180005670`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180005670  sub     rsp, 28h
0x180005674  test    r8, r8
0x180005677  jnz     short loc_180005680
0x180005679  mov     eax, 80070057h
0x18000567e  jmp     short loc_1800056D1
0x180005680  mov     rax, [rdx]
0x180005683  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000568a  jnz     short loc_180005699
0x18000568c  mov     rax, [rdx+8]
0x180005690  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180005697  jz      short loc_1800056B2
0x180005699  mov     rax, [rdx]
0x18000569c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800056a3  jnz     short loc_1800056C5
0x1800056a5  mov     rax, [rdx+8]
0x1800056a9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800056b0  jnz     short loc_1800056C5
0x1800056b2  mov     [r8], rcx
0x1800056b5  mov     rax, [rcx]
0x1800056b8  mov     rax, [rax+8]
0x1800056bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c1  xor     eax, eax
0x1800056c3  jmp     short loc_1800056D1
0x1800056c5  mov     qword ptr [r8], 0
0x1800056cc  mov     eax, 80004002h
0x1800056d1  add     rsp, 28h
0x1800056d5  retn
```
