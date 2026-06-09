# CUACCheck::~CUACCheck(void)

- ea: `0x180003990`
- end: `0x1800039e2`
- name: `??1CUACCheck@@MEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CUACCheck *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003950`

## callees

- `0x180003990`
- `0x1800039f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800039d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800039d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039bb`

## pseudocode

```c
void __fastcall CUACCheck::~CUACCheck(CUACCheck *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CObjectFactory<HCCHECK const *,CUACCheck>::`vftable';
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 29);
  if ( v2 )
    CloseThreadpoolWait(v2);
  v3 = (void *)*((_QWORD *)this + 28);
  if ( v3 )
    CloseHandle(v3);
  CCheckBase::~CCheckBase(this);
}

```

## disassembly

```asm
0x180003990  push    rbx
0x180003992  sub     rsp, 20h
0x180003996  lea     rax, ??_7?$CObjectFactory@PEBUHCCHECK@@VCUACCheck@@@@6B@; const CObjectFactory<HCCHECK const *,CUACCheck>::`vftable'
0x18000399d  mov     rbx, rcx
0x1800039a0  mov     [rcx], rax
0x1800039a3  mov     rcx, [rcx+0E8h]; pwa
0x1800039aa  test    rcx, rcx
0x1800039ad  jnz     short loc_1800039D4
0x1800039af  mov     rcx, [rbx+0E0h]; hObject
0x1800039b6  test    rcx, rcx
0x1800039b9  jz      short loc_1800039C7
0x1800039bb  call    cs:__imp_CloseHandle
0x1800039c2  nop     dword ptr [rax+rax+00h]
0x1800039c7  mov     rcx, rbx; this
0x1800039ca  add     rsp, 20h
0x1800039ce  pop     rbx
0x1800039cf  jmp     ??1CCheckBase@@MEAA@XZ; CCheckBase::~CCheckBase(void)
0x1800039d4  call    cs:__imp_CloseThreadpoolWait
0x1800039db  nop     dword ptr [rax+rax+00h]
0x1800039e0  jmp     short loc_1800039AF
```
