# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x140008e6c`
- end: `0x140008ed8`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400093b0`

## callees

- `0x140002114`
- `0x140008e6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008ea1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008ea1`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( this && *(_DWORD *)this == 72 )
  {
    v2 = (void *)*((_QWORD *)this + 7);
    if ( v2 )
    {
      free(v2);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 7);
  if ( v3 )
  {
    free(v3);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x140008e6c  push    rbx
0x140008e6e  sub     rsp, 20h
0x140008e72  mov     rbx, rcx
0x140008e75  test    rcx, rcx
0x140008e78  jz      short loc_140008EB3
0x140008e7a  cmp     dword ptr [rcx], 48h ; 'H'
0x140008e7d  jnz     short loc_140008EB3
0x140008e7f  mov     rcx, [rcx+38h]; Block
0x140008e83  test    rcx, rcx
0x140008e86  jz      short loc_140008E95
0x140008e88  call    free
0x140008e8d  mov     qword ptr [rbx+38h], 0
0x140008e95  lea     rcx, [rbx+8]; lpCriticalSection
0x140008e99  mov     qword ptr [rbx+40h], 0
0x140008ea1  call    cs:__imp_DeleteCriticalSection
0x140008ea8  nop     dword ptr [rax+rax+00h]
0x140008ead  mov     dword ptr [rbx], 0
0x140008eb3  mov     rcx, [rbx+38h]; Block
0x140008eb7  test    rcx, rcx
0x140008eba  jz      short loc_140008EC9
0x140008ebc  call    free
0x140008ec1  mov     qword ptr [rbx+38h], 0
0x140008ec9  mov     qword ptr [rbx+40h], 0
0x140008ed1  add     rsp, 20h
0x140008ed5  pop     rbx
0x140008ed6  retn
```
