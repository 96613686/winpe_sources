# wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)

- ea: `0x18000ef6c`
- end: `0x18000ef93`
- name: `?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008bc4`
- `0x180009b9c`
- `0x180009e70`
- `0x18000a2ac`

## callees

- `0x18000ef6c`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
        __int64 (__fastcall ****a1)(_QWORD, __int64),
        __int64 (__fastcall ***a2)(_QWORD, __int64))
{
  __int64 (__fastcall ***v2)(_QWORD, __int64); // r8
  __int64 result; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    return (**v2)(v2, 1);
  return result;
}

```

## disassembly

```asm
0x18000ef6c  sub     rsp, 28h
0x18000ef70  mov     r8, [rcx]
0x18000ef73  mov     [rcx], rdx
0x18000ef76  test    r8, r8
0x18000ef79  jz      short loc_18000EF8E
0x18000ef7b  mov     rax, [r8]
0x18000ef7e  mov     edx, 1
0x18000ef83  mov     rcx, r8
0x18000ef86  mov     rax, [rax]
0x18000ef89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef8e  add     rsp, 28h
0x18000ef92  retn
```
