# CLCEntry::~CLCEntry(void)

- ea: `0x1800087bc`
- end: `0x18000881e`
- name: `??1CLCEntry@@UEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CLCEntry *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008d70`

## callees

- `0x1800087bc`
- `0x18001eba0`
- `0x18001ffd8`
- `0x18004d920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008801`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008801`

## pseudocode

```c
void __fastcall CLCEntry::~CLCEntry(CLCEntry *this)
{
  CDRMCBase *v2; // rcx
  DRMHANDLE v3; // ecx

  *(_QWORD *)this = &CLCEntry::`vftable';
  v2 = (CDRMCBase *)*((_QWORD *)this + 17);
  if ( v2 )
  {
    CDRMCBase::Release(v2);
    *((_QWORD *)this + 17) = 0;
  }
  v3 = *((_DWORD *)this + 46);
  if ( v3 )
    DRMCloseHandle(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  *(_QWORD *)this = &Entry::`vftable';
  CDRMCBase::~CDRMCBase(this);
}

```

## disassembly

```asm
0x1800087bc  push    rbx
0x1800087be  sub     rsp, 20h
0x1800087c2  lea     rax, ??_7CLCEntry@@6B@; const CLCEntry::`vftable'
0x1800087c9  mov     rbx, rcx
0x1800087cc  mov     [rcx], rax
0x1800087cf  mov     rcx, [rcx+88h]; this
0x1800087d6  test    rcx, rcx
0x1800087d9  jz      short loc_1800087EB
0x1800087db  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x1800087e0  mov     qword ptr [rbx+88h], 0
0x1800087eb  mov     ecx, [rbx+0B8h]; handle
0x1800087f1  test    ecx, ecx
0x1800087f3  jz      short loc_1800087FA
0x1800087f5  call    DRMCloseHandle
0x1800087fa  lea     rcx, [rbx+90h]; lpCriticalSection
0x180008801  call    cs:__imp_DeleteCriticalSection
0x180008807  lea     rax, ??_7Entry@@6B@; const Entry::`vftable'
0x18000880e  mov     rcx, rbx; this
0x180008811  mov     [rbx], rax
0x180008814  add     rsp, 20h
0x180008818  pop     rbx
0x180008819  jmp     ??1CDRMCBase@@UEAA@XZ; CDRMCBase::~CDRMCBase(void)
```
