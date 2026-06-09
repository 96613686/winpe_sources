# CMFTSimpleBase::~CMFTSimpleBase(void)

- ea: `0x18001c8d4`
- end: `0x18001c958`
- name: `??1CMFTSimpleBase@@UEAA@XZ`
- size: `132`
- prototype: `void __fastcall(CMFTSimpleBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c860`

## callees

- `0x18001c8d4`
- `0x18001f56c`
- `0x18001f620`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c8e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c8e1`

## pseudocode

```c
void __fastcall CMFTSimpleBase::~CMFTSimpleBase(CMFTSimpleBase *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  CMFTSimpleBase::_InitAvailableInputTypeArray(this, 0);
  CMFTSimpleBase::_InitAvailableOutputTypeArray(this, 0);
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 10) = 0;
  }
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x18001c8d4  push    rbx
0x18001c8d6  sub     rsp, 20h
0x18001c8da  mov     rbx, rcx
0x18001c8dd  add     rcx, 68h ; 'h'; lpCriticalSection
0x18001c8e1  call    cs:__imp_DeleteCriticalSection
0x18001c8e7  xor     edx, edx; unsigned int
0x18001c8e9  mov     rcx, rbx; this
0x18001c8ec  call    ?_InitAvailableInputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableInputTypeArray(ulong)
0x18001c8f1  xor     edx, edx; unsigned int
0x18001c8f3  mov     rcx, rbx; this
0x18001c8f6  call    ?_InitAvailableOutputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableOutputTypeArray(ulong)
0x18001c8fb  mov     rcx, [rbx+28h]
0x18001c8ff  test    rcx, rcx
0x18001c902  jz      short loc_18001C918
0x18001c904  mov     rax, [rcx]
0x18001c907  mov     rax, [rax+10h]
0x18001c90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c910  mov     qword ptr [rbx+28h], 0
0x18001c918  mov     rcx, [rbx+50h]
0x18001c91c  test    rcx, rcx
0x18001c91f  jz      short loc_18001C935
0x18001c921  mov     rax, [rcx]
0x18001c924  mov     rax, [rax+10h]
0x18001c928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c92d  mov     qword ptr [rbx+50h], 0
0x18001c935  mov     rcx, [rbx+48h]
0x18001c939  test    rcx, rcx
0x18001c93c  jz      short loc_18001C952
0x18001c93e  mov     rax, [rcx]
0x18001c941  mov     rax, [rax+10h]
0x18001c945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c94a  mov     qword ptr [rbx+48h], 0
0x18001c952  add     rsp, 20h
0x18001c956  pop     rbx
0x18001c957  retn
```
