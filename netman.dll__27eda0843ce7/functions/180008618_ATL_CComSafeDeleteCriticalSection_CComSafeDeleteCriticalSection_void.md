# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180008618`
- end: `0x180008631`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `36`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007238`
- `0x1800072c0`
- `0x180007428`
- `0x1800074f4`
- `0x1800075c4`
- `0x180007678`
- `0x180007700`
- `0x180007748`
- `0x180007790`
- `0x1800077d8`
- `0x180007820`
- `0x180007868`
- `0x1800078b0`
- `0x1800078f8`
- `0x180007928`
- `0x180007aec`
- `0x180007b70`
- `0x180007d58`
- `0x180007e40`
- `0x180007f2c`
- `0x180007fdc`
- `0x18000812c`
- `0x18000814c`
- `0x18000867c`
- `0x1800086b4`
- `0x1800086f4`
- `0x18000871c`
- `0x18001e24c`
- `0x18001f040`
- `0x180020f30`
- `0x1800216d8`
- `0x180021d68`
- `0x1800244e0`
- `0x180026224`
- `0x180027288`
- `0x180029cf8`

## callees

- `0x180008618`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008626`
- `KERNEL32!DeleteCriticalSection` at `0x180008626`

## pseudocode

```c
void __fastcall ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(
        ATL::CComSafeDeleteCriticalSection *this)
{
  if ( *((_BYTE *)this + 40) )
  {
    *((_BYTE *)this + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)this);
  }
}

```

## disassembly

```asm
0x180008618  sub     rsp, 28h
0x18000861c  cmp     byte ptr [rcx+28h], 0
0x180008620  jz      short loc_18000862C
0x180008622  mov     byte ptr [rcx+28h], 0
0x180008626  call    cs:__imp_DeleteCriticalSection
0x18000862c  add     rsp, 28h
0x180008630  retn
```
