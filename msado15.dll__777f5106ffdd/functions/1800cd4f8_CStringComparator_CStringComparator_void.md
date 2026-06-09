# CStringComparator::~CStringComparator(void)

- ea: `0x1800cd4f8`
- end: `0x1800cd533`
- name: `??1CStringComparator@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(CStringComparator *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800c8970`

## callees

- `0x1800cd4f8`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800cd519`
- `KERNEL32!FreeLibrary` at `0x1800cd519`
- `KERNEL32!DeleteCriticalSection` at `0x1800cd505`
- `KERNEL32!DeleteCriticalSection` at `0x1800cd505`

## pseudocode

```c
void __fastcall CStringComparator::~CStringComparator(CStringComparator *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *(_QWORD *)this )
  {
    FreeLibrary(*(HMODULE *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800cd4f8  push    rbx
0x1800cd4fa  sub     rsp, 20h
0x1800cd4fe  mov     rbx, rcx
0x1800cd501  add     rcx, 20h ; ' '; lpCriticalSection
0x1800cd505  call    cs:__imp_DeleteCriticalSection
0x1800cd50c  nop     dword ptr [rax+rax+00h]
0x1800cd511  mov     rcx, [rbx]; hLibModule
0x1800cd514  test    rcx, rcx
0x1800cd517  jz      short loc_1800CD52C
0x1800cd519  call    cs:__imp_FreeLibrary
0x1800cd520  nop     dword ptr [rax+rax+00h]
0x1800cd525  mov     qword ptr [rbx], 0
0x1800cd52c  add     rsp, 20h
0x1800cd530  pop     rbx
0x1800cd531  retn
```
