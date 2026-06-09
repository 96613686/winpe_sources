# hCreateClientObjLink

- ea: `0x180029150`
- end: `0x1800291d2`
- name: `hCreateClientObjLink`
- size: `130`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180028ae0`
- `0x180028f18`
- `0x18002a8b0`
- `0x18002ba30`
- `0x18002bbc8`
- `0x180067300`
- `0x18006c640`

## callees

- `0x1800242f0`
- `0x180029150`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180029182`
- `ntdll!RtlEnterCriticalSection` at `0x180029182`
- `ntdll!RtlLeaveCriticalSection` at `0x18002919f`
- `ntdll!RtlLeaveCriticalSection` at `0x18002919f`
- `win32u!NtGdiDeleteClientObj` at `0x1800291c8`
- `win32u!NtGdiDeleteClientObj` at `0x1800291c8`
- `win32u!NtGdiCreateClientObj` at `0x18002916d`
- `win32u!NtGdiCreateClientObj` at `0x18002916d`

## pseudocode

```c
__int64 __fastcall hCreateClientObjLink(__int64 a1, unsigned int a2)
{
  __int64 ClientObj; // rbx
  __int64 v4; // rdi

  if ( gbDisableMetaFiles )
    return 0;
  ClientObj = NtGdiCreateClientObj(a2);
  if ( ClientObj )
  {
    RtlEnterCriticalSection(&semLocal);
    v4 = plinkCreate(ClientObj, 40);
    RtlLeaveCriticalSection(&semLocal);
    if ( v4 )
    {
      *(_QWORD *)(v4 + 32) = a1;
    }
    else
    {
      NtGdiDeleteClientObj(ClientObj);
      return 0;
    }
  }
  return ClientObj;
}

```

## disassembly

```asm
0x180029150  mov     [rsp+arg_0], rbx
0x180029155  mov     [rsp+arg_8], rsi
0x18002915a  push    rdi
0x18002915b  sub     rsp, 20h
0x18002915f  cmp     cs:gbDisableMetaFiles, 0
0x180029166  mov     rsi, rcx
0x180029169  jnz     short loc_1800291C1
0x18002916b  mov     ecx, edx
0x18002916d  call    cs:__imp_NtGdiCreateClientObj
0x180029173  mov     rbx, rax
0x180029176  test    rax, rax
0x180029179  jz      short loc_1800291AE
0x18002917b  lea     rcx, semLocal; CriticalSection
0x180029182  call    cs:__imp_RtlEnterCriticalSection
0x180029188  mov     edx, 28h ; '('
0x18002918d  mov     rcx, rbx
0x180029190  call    plinkCreate
0x180029195  lea     rcx, semLocal; CriticalSection
0x18002919c  mov     rdi, rax
0x18002919f  call    cs:__imp_RtlLeaveCriticalSection
0x1800291a5  test    rdi, rdi
0x1800291a8  jz      short loc_1800291C5
0x1800291aa  mov     [rdi+20h], rsi
0x1800291ae  mov     rax, rbx
0x1800291b1  mov     rbx, [rsp+28h+arg_0]
0x1800291b6  mov     rsi, [rsp+28h+arg_8]
0x1800291bb  add     rsp, 20h
0x1800291bf  pop     rdi
0x1800291c0  retn
0x1800291c1  xor     eax, eax
0x1800291c3  jmp     short loc_1800291B1
0x1800291c5  mov     rcx, rbx
0x1800291c8  call    cs:__imp_NtGdiDeleteClientObj
0x1800291ce  xor     ebx, ebx
0x1800291d0  jmp     short loc_1800291AE
```
