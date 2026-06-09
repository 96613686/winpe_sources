# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180021d40`
- end: `0x180021da2`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021db0`

## callees

- `0x180021d40`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 11);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 11, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 32LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x180021d40  push    rbx
0x180021d42  sub     rsp, 20h
0x180021d46  mov     r9d, 7FFFFFFFh
0x180021d4c  jmp     short loc_180021D5C
0x180021d4e  lea     edx, [r8-1]
0x180021d52  mov     eax, r8d
0x180021d55  lock cmpxchg [rcx+2Ch], edx
0x180021d5a  jz      short loc_180021D65
0x180021d5c  mov     r8d, [rcx+2Ch]
0x180021d60  cmp     r8d, r9d
0x180021d63  jnz     short loc_180021D4E
0x180021d65  lea     ebx, [r8-1]
0x180021d69  test    ebx, ebx
0x180021d6b  jnz     short loc_180021D99
0x180021d6d  test    rcx, rcx
0x180021d70  jz      short loc_180021D81
0x180021d72  mov     rax, [rcx]
0x180021d75  lea     edx, [rbx+1]
0x180021d78  mov     rax, [rax+20h]
0x180021d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d81  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180021d88  test    rcx, rcx
0x180021d8b  jz      short loc_180021D99
0x180021d8d  mov     rdx, [rcx]
0x180021d90  mov     rax, [rdx+10h]
0x180021d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d99  mov     eax, ebx
0x180021d9b  add     rsp, 20h
0x180021d9f  pop     rbx
0x180021da0  retn
```
