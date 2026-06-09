# Windows::Internal::SvcHostModule::DecrementObjectCount(void)

- ea: `0x1800051b0`
- end: `0x1800051e9`
- name: `?DecrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800051f0`

## callees

- `0x1800051b0`
- `0x180012010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x1800051c0`
- `combase!__imp_CoReleaseSharedService` at `0x1800051c0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::SvcHostModule::DecrementObjectCount(Windows::Internal::SvcHostModule *this)
{
  unsigned int v2; // ebx

  v2 = CoReleaseSharedService(*((unsigned int *)this + 14));
  if ( !v2 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
  return v2;
}

```

## disassembly

```asm
0x1800051b0  mov     [rsp+arg_0], rbx
0x1800051b5  push    rdi
0x1800051b6  sub     rsp, 20h
0x1800051ba  mov     rdi, rcx
0x1800051bd  mov     ecx, [rcx+38h]
0x1800051c0  call    cs:__imp_CoReleaseSharedService
0x1800051c6  mov     ebx, eax
0x1800051c8  test    eax, eax
0x1800051ca  jnz     short loc_1800051DC
0x1800051cc  mov     rcx, [rdi+30h]
0x1800051d0  mov     rdx, [rcx]
0x1800051d3  mov     rax, [rdx+8]
0x1800051d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051dc  mov     eax, ebx
0x1800051de  mov     rbx, [rsp+28h+arg_0]
0x1800051e3  add     rsp, 20h
0x1800051e7  pop     rdi
0x1800051e8  retn
```
