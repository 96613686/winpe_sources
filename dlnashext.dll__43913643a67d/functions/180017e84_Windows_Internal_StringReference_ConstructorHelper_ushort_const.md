# Windows::Internal::StringReference::_ConstructorHelper(ushort const *)

- ea: `0x180017e84`
- end: `0x180017ee9`
- name: `?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z`
- size: `101`
- prototype: `void __fastcall(Windows::Internal::StringReference *__hidden this, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180010af0`
- `0x1800195d4`
- `0x18001d4e0`
- `0x180024784`
- `0x180026830`
- `0x180027840`
- `0x1800281a0`
- `0x18002c844`
- `0x18002f378`
- `0x18002f5d0`
- `0x18002f720`

## callees

- `0x18000aea4`
- `0x180017e84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017ec4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017ec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017ee2`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::_ConstructorHelper(
        Windows::Internal::StringReference *this,
        const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rcx
  const ULONG_PTR *v5; // r9
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( (int)ULongLongToUInt(v3, &v6) < 0 )
    RaiseException(0xC000000D, 1u, 0, v5);
  WindowsCreateStringReference(a2, v6, (HSTRING_HEADER *)((char *)this + 8), (HSTRING *)this);
}

```

## disassembly

```asm
0x180017e84  mov     [rsp+arg_8], rbx
0x180017e89  push    rdi
0x180017e8a  sub     rsp, 20h
0x180017e8e  xor     r9d, r9d
0x180017e91  mov     rbx, rcx
0x180017e94  mov     [rsp+28h+arg_0], r9d
0x180017e99  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180017e9d  mov     rdi, rdx
0x180017ea0  inc     rcx; unsigned __int64
0x180017ea3  cmp     [rdx+rcx*2], r9w
0x180017ea8  jnz     short loc_180017EA0
0x180017eaa  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x180017eaf  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180017eb4  test    eax, eax
0x180017eb6  jns     short loc_180017ECA
0x180017eb8  xor     r8d, r8d; nNumberOfArguments
0x180017ebb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180017ec0  lea     edx, [r8+1]; dwExceptionFlags
0x180017ec4  call    cs:__imp_RaiseException
0x180017eca  mov     edx, [rsp+28h+arg_0]
0x180017ece  lea     r8, [rbx+8]
0x180017ed2  mov     r9, rbx
0x180017ed5  mov     rcx, rdi
0x180017ed8  mov     rbx, [rsp+28h+arg_8]
0x180017edd  add     rsp, 20h
0x180017ee1  pop     rdi
0x180017ee2  jmp     cs:__imp_WindowsCreateStringReference
```
