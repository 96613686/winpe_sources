# CConnectionFolder::~CConnectionFolder(void)

- ea: `0x180009750`
- end: `0x1800097bc`
- name: `??1CConnectionFolder@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CConnectionFolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180023990`
- `0x180023d14`

## callees

- `0x180009750`
- `0x18001e5b0`

## import_xrefs

- `SHELL32!__imp_SHFree` at `0x180009765`
- `SHELL32!__imp_SHFree` at `0x180009794`
- `SHELL32!__imp_SHFree` at `0x180009765`
- `SHELL32!__imp_SHFree` at `0x180009794`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800097b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800097b0`

## pseudocode

```c
void __fastcall CConnectionFolder::~CConnectionFolder(CConnectionFolder *this)
{
  void *v2; // rcx
  _QWORD *v3; // rcx
  void *v4; // rcx

  v2 = (void *)*((_QWORD *)this + 81);
  if ( v2 )
    SHFree(v2);
  v3 = (_QWORD *)*((_QWORD *)this + 80);
  if ( v3 )
  {
    *v3 = &CNCWebView::`vftable';
    operator delete(v3, 0x10u);
  }
  v4 = (void *)*((_QWORD *)this + 13);
  if ( v4 )
    SHFree(v4);
  *((_QWORD *)this + 13) = 0;
  if ( *((_BYTE *)this + 96) )
  {
    *((_BYTE *)this + 96) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  }
}

```

## disassembly

```asm
0x180009750  push    rbx
0x180009752  sub     rsp, 20h
0x180009756  mov     rbx, rcx
0x180009759  mov     rcx, [rcx+288h]; pv
0x180009760  test    rcx, rcx
0x180009763  jz      short loc_18000976B
0x180009765  call    cs:__imp_SHFree
0x18000976b  mov     rcx, [rbx+280h]; void *
0x180009772  test    rcx, rcx
0x180009775  jz      short loc_18000978B
0x180009777  lea     rax, ??_7CNCWebView@@6B@; const CNCWebView::`vftable'
0x18000977e  mov     edx, 10h; unsigned __int64
0x180009783  mov     [rcx], rax
0x180009786  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000978b  mov     rcx, [rbx+68h]; pv
0x18000978f  test    rcx, rcx
0x180009792  jz      short loc_18000979A
0x180009794  call    cs:__imp_SHFree
0x18000979a  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000979e  mov     qword ptr [rbx+68h], 0
0x1800097a6  cmp     byte ptr [rcx+28h], 0
0x1800097aa  jz      short loc_1800097B6
0x1800097ac  mov     byte ptr [rcx+28h], 0
0x1800097b0  call    cs:__imp_DeleteCriticalSection
0x1800097b6  add     rsp, 20h
0x1800097ba  pop     rbx
0x1800097bb  retn
```
