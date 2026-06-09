# NTDomain::createInstance(ushort const *)

- ea: `0x18001f708`
- end: `0x18001f7ad`
- name: `?createInstance@NTDomain@@SAPEAV1@PEBG@Z`
- size: `165`
- prototype: `struct NTDomain *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001dddc`

## callees

- `0x18000342c`
- `0x18001e11c`
- `0x18001f708`
- `0x180026c9c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001f72a`
- `KERNEL32!InitializeCriticalSection` at `0x18001f72a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _RTL_CRITICAL_SECTION *__fastcall NTDomain::createInstance(
        const unsigned __int16 *a1,
        const struct std::nothrow_t *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdi

  v2 = (struct _RTL_CRITICAL_SECTION *)operator new[](0xF0u, a2);
  v3 = v2;
  if ( !v2 )
    return 0;
  InitializeCriticalSection(v2);
  LODWORD(v3[1].DebugInfo) = 1;
  std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>(&v3[1].LockCount);
  v3[2].LockSemaphore = HANDLE_FLAG_PROTECT_FROM_CLOSE|HANDLE_FLAG_INHERIT|0x4;
  v3[2].OwningThread = 0;
  LOWORD(v3[2].DebugInfo) = 0;
  LODWORD(v3[2].SpinCount) = 0;
  v3[3].DebugInfo = 0;
  v3[3].LockCount = 0;
  v3[3].OwningThread = 0;
  HashTableBase::HashTableBase(&v3[3].LockSemaphore);
  *(_QWORD *)&v3[5].LockCount = (char *)v3 + 192;
  v3[5].OwningThread = &v3[4].SpinCount;
  v3[5].LockSemaphore = (HANDLE)600000000;
  LODWORD(v3[5].SpinCount) = 100;
  BYTE4(v3[5].SpinCount) = 0;
  return v3;
}

```

## disassembly

```asm
0x18001f708  mov     [rsp+arg_0], rbx
0x18001f70d  push    rdi
0x18001f70e  sub     rsp, 20h
0x18001f712  mov     rbx, rcx
0x18001f715  mov     ecx, 0F0h; Size
0x18001f71a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f71f  mov     rdi, rax
0x18001f722  test    rax, rax
0x18001f725  jz      short loc_18001F79D
0x18001f727  mov     rcx, rax; lpCriticalSection
0x18001f72a  call    cs:__imp_InitializeCriticalSection
0x18001f730  mov     dword ptr [rdi+28h], 1
0x18001f737  lea     rcx, [rdi+30h]; void *
0x18001f73b  mov     rdx, rbx
0x18001f73e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAA@PEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>(ushort const *)
0x18001f743  mov     qword ptr [rdi+68h], 7
0x18001f74b  mov     qword ptr [rdi+60h], 0
0x18001f753  xor     eax, eax
0x18001f755  mov     [rdi+50h], ax
0x18001f759  mov     [rdi+70h], eax
0x18001f75c  mov     [rdi+78h], rax
0x18001f760  mov     [rdi+80h], eax
0x18001f766  mov     [rdi+88h], rax
0x18001f76d  lea     rbx, [rdi+90h]
0x18001f774  mov     rcx, rbx
0x18001f777  call    ??0HashTableBase@@QEAA@P6AKPEBX@_EK@Z; HashTableBase::HashTableBase(ulong (*)(void const *),...)
0x18001f77c  lea     rax, [rbx+30h]
0x18001f780  mov     [rbx+40h], rax
0x18001f784  mov     [rbx+48h], rax
0x18001f788  mov     qword ptr [rbx+50h], 23C34600h
0x18001f790  mov     dword ptr [rbx+58h], 64h ; 'd'
0x18001f797  mov     byte ptr [rbx+5Ch], 0
0x18001f79b  jmp     short loc_18001F79F
0x18001f79d  xor     edi, edi
0x18001f79f  mov     rax, rdi
0x18001f7a2  mov     rbx, [rsp+28h+arg_0]
0x18001f7a7  add     rsp, 20h
0x18001f7ab  pop     rdi
0x18001f7ac  retn
```
