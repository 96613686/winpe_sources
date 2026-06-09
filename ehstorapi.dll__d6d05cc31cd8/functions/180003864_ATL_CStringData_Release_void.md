# ATL::CStringData::Release(void)

- ea: `0x180003864`
- end: `0x18000388c`
- name: `?Release@CStringData@ATL@@QEAAXXZ`
- size: `40`
- prototype: `void __fastcall(ATL::CStringData *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180002128`
- `0x18000215c`
- `0x180002660`
- `0x18000394c`
- `0x180004068`
- `0x18000408c`
- `0x1800046b4`
- `0x18000521c`
- `0x180005960`
- `0x180006400`
- `0x18000649c`
- `0x18000664c`
- `0x1800079d0`

## callees

- `0x180003864`
- `0x18000d010`

## pseudocode

```c
void __fastcall ATL::CStringData::Release(ATL::CStringData *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, ATL::CStringData *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, this);
}

```

## disassembly

```asm
0x180003864  sub     rsp, 28h
0x180003868  mov     rdx, rcx
0x18000386b  or      eax, 0FFFFFFFFh
0x18000386e  lock xadd [rcx+10h], eax
0x180003873  sub     eax, 1
0x180003876  jg      short loc_180003887
0x180003878  mov     rcx, [rcx]
0x18000387b  mov     rax, [rcx]
0x18000387e  mov     rax, [rax+8]
0x180003882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003887  add     rsp, 28h
0x18000388b  retn
```
