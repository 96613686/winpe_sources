# CVolumeCacheCallBack::QueryInterface(_GUID const &,void * *)

- ea: `0x140005800`
- end: `0x140005860`
- name: `?QueryInterface@CVolumeCacheCallBack@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: `__int64 __fastcall(CVolumeCacheCallBack *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005800`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall CVolumeCacheCallBack::QueryInterface(CVolumeCacheCallBack *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax
  __int64 v5; // rax

  *a3 = 0;
  v3 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v3 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v3 )
  {
    v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IEmptyVolumeCacheCallBack.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IEmptyVolumeCacheCallBack.Data1 )
      v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IEmptyVolumeCacheCallBack.Data4;
    if ( v5 )
      return 2147500034LL;
  }
  *a3 = this;
  (*(void (__fastcall **)(CVolumeCacheCallBack *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x140005800  sub     rsp, 28h
0x140005804  mov     qword ptr [r8], 0
0x14000580b  mov     rax, [rdx]
0x14000580e  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x140005815  jnz     short loc_140005822
0x140005817  mov     rax, [rdx+8]
0x14000581b  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x140005822  test    rax, rax
0x140005825  jnz     short loc_14000583A
0x140005827  mov     [r8], rcx
0x14000582a  mov     rax, [rcx]
0x14000582d  mov     rax, [rax+8]
0x140005831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005836  xor     eax, eax
0x140005838  jmp     short loc_14000585B
0x14000583a  mov     rax, [rdx]
0x14000583d  sub     rax, qword ptr cs:IID_IEmptyVolumeCacheCallBack.Data1
0x140005844  jnz     short loc_140005851
0x140005846  mov     rax, [rdx+8]
0x14000584a  sub     rax, qword ptr cs:IID_IEmptyVolumeCacheCallBack.Data4
0x140005851  test    rax, rax
0x140005854  jz      short loc_140005827
0x140005856  mov     eax, 80004002h
0x14000585b  add     rsp, 28h
0x14000585f  retn
```
