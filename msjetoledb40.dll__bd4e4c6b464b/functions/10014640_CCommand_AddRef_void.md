# CCommand::AddRef(void)

- ea: `0x10014640`
- end: `0x10014677`
- name: `?AddRef@CCommand@@UAGKXZ`
- size: `55`
- prototype: `unsigned int __stdcall(CCommand *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10014640`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10014668`
- `KERNEL32!LeaveCriticalSection` at `0x10014668`
- `KERNEL32!EnterCriticalSection` at `0x10014652`
- `KERNEL32!EnterCriticalSection` at `0x10014652`

## pseudocode

```c
signed __int32 __stdcall CCommand::AddRef(CCommand *this)
{
  signed __int32 v1; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  v1 = _InterlockedIncrement((volatile signed __int32 *)this + 1);
  if ( this != (CCommand *)-248 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  return v1;
}

```

## disassembly

```asm
0x10014640  mov     edi, edi
0x10014642  push    ebp
0x10014643  mov     ebp, esp
0x10014645  push    ebx
0x10014646  push    esi
0x10014647  push    edi
0x10014648  mov     edi, [ebp+this]
0x1001464b  lea     esi, [edi+0F8h]
0x10014651  push    esi; lpCriticalSection
0x10014652  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10014658  mov     ebx, 1
0x1001465d  lock xadd [edi+4], ebx
0x10014662  inc     ebx
0x10014663  test    esi, esi
0x10014665  jz      short loc_1001466E
0x10014667  push    esi; lpCriticalSection
0x10014668  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001466e  pop     edi
0x1001466f  pop     esi
0x10014670  mov     eax, ebx
0x10014672  pop     ebx
0x10014673  pop     ebp
0x10014674  retn    4
```
