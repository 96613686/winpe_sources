# ColorDataProxy::Initialize(ulong *)

- ea: `0x1800127b0`
- end: `0x1800127dd`
- name: `?Initialize@ColorDataProxy@@UEAAJPEAK@Z`
- size: `45`
- prototype: `__int64 __fastcall(ColorDataProxy *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800127b0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800127c9`
- `KERNEL32!GetCurrentProcessId` at `0x1800127c9`
- `mscms!ColorCplInitialize` at `0x1800127d6`

## pseudocode

```c
__int64 __fastcall ColorDataProxy::Initialize(ColorDataProxy *this, unsigned int *a2)
{
  if ( !a2 )
    return 2147942487LL;
  *a2 = GetCurrentProcessId();
  return ColorCplInitialize();
}

```

## disassembly

```asm
0x1800127b0  push    rbx
0x1800127b2  sub     rsp, 20h
0x1800127b6  mov     rbx, rdx
0x1800127b9  test    rdx, rdx
0x1800127bc  jnz     short loc_1800127C9
0x1800127be  mov     eax, 80070057h
0x1800127c3  add     rsp, 20h
0x1800127c7  pop     rbx
0x1800127c8  retn
0x1800127c9  call    cs:__imp_GetCurrentProcessId
0x1800127cf  mov     [rbx], eax
0x1800127d1  add     rsp, 20h
0x1800127d5  pop     rbx
0x1800127d6  jmp     cs:__imp_ColorCplInitialize
```
