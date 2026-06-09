# CLoader::~CLoader(void)

- ea: `0x180007fcc`
- end: `0x180008099`
- name: `??1CLoader@@QEAA@XZ`
- size: `205`
- prototype: `void __fastcall(CLoader *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003bd0`
- `0x1800094c0`
- `0x1800096c0`

## callees

- `0x1800019a0`
- `0x180007fcc`
- `0x18000a0e4`
- `0x18000a178`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008060`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008060`

## pseudocode

```c
void __fastcall CLoader::~CLoader(CLoader *this)
{
  bool v1; // zf
  _QWORD *v3; // rdi
  CClass *v4; // rcx
  _QWORD *v5; // rdi
  CObject *v6; // rcx
  CObject *v7; // rbx

  v1 = *((_DWORD *)this + 152) == 0;
  *(_QWORD *)this = &CLoader::`vftable'{for `IDirectMusicLoader8'};
  *((_QWORD *)this + 1) = &CLoader::`vftable'{for `IDirectMusicLoader8P'};
  if ( !v1 )
  {
    while ( 1 )
    {
      v3 = (_QWORD *)*((_QWORD *)this + 3);
      if ( !v3 )
        break;
      v4 = (CClass *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = *v3;
      *v3 = 0;
      CClass::~CClass(v4);
      operator delete(v3, 0xE8u);
    }
    while ( 1 )
    {
      v5 = (_QWORD *)*((_QWORD *)this + 79);
      if ( !v5 )
        break;
      v6 = (CObject *)*((_QWORD *)this + 79);
      *((_QWORD *)this + 79) = *v5;
      *v5 = 0;
      CObject::~CObject(v6);
      operator delete(v5, 0xD8u);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  }
  v7 = (CObject *)*((_QWORD *)this + 77);
  if ( v7 )
  {
    CObject::~CObject(v7);
    operator delete(v7, 0xD8u);
  }
  _InterlockedDecrement(&g_cLoaderComponent);
}

```

## disassembly

```asm
0x180007fcc  mov     [rsp+arg_0], rbx
0x180007fd1  push    rdi
0x180007fd2  sub     rsp, 20h
0x180007fd6  cmp     dword ptr [rcx+260h], 0
0x180007fdd  lea     rax, ??_7CLoader@@6BIDirectMusicLoader8@@@; const CLoader::`vftable'{for `IDirectMusicLoader8'}
0x180007fe4  mov     [rcx], rax
0x180007fe7  mov     rbx, rcx
0x180007fea  lea     rax, ??_7CLoader@@6BIDirectMusicLoader8P@@@; const CLoader::`vftable'{for `IDirectMusicLoader8P'}
0x180007ff1  mov     [rcx+8], rax
0x180007ff5  jz      short loc_180008066
0x180007ff7  mov     rdi, [rbx+18h]
0x180007ffb  test    rdi, rdi
0x180007ffe  jz      short loc_180008025
0x180008000  mov     rax, [rdi]
0x180008003  mov     rcx, rdi; this
0x180008006  mov     [rbx+18h], rax
0x18000800a  mov     qword ptr [rdi], 0
0x180008011  call    ??1CClass@@QEAA@XZ; CClass::~CClass(void)
0x180008016  mov     edx, 0E8h; unsigned __int64
0x18000801b  mov     rcx, rdi; void *
0x18000801e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008023  jmp     short loc_180007FF7
0x180008025  mov     rdi, [rbx+278h]
0x18000802c  test    rdi, rdi
0x18000802f  jz      short loc_180008059
0x180008031  mov     rax, [rdi]
0x180008034  mov     rcx, rdi; this
0x180008037  mov     [rbx+278h], rax
0x18000803e  mov     qword ptr [rdi], 0
0x180008045  call    ??1CObject@@QEAA@XZ; CObject::~CObject(void)
0x18000804a  mov     edx, 0D8h; unsigned __int64
0x18000804f  mov     rcx, rdi; void *
0x180008052  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008057  jmp     short loc_180008025
0x180008059  lea     rcx, [rbx+238h]; lpCriticalSection
0x180008060  call    cs:__imp_DeleteCriticalSection
0x180008066  mov     rbx, [rbx+268h]
0x18000806d  test    rbx, rbx
0x180008070  jz      short loc_180008087
0x180008072  mov     rcx, rbx; this
0x180008075  call    ??1CObject@@QEAA@XZ; CObject::~CObject(void)
0x18000807a  mov     edx, 0D8h; unsigned __int64
0x18000807f  mov     rcx, rbx; void *
0x180008082  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008087  lock dec cs:?g_cLoaderComponent@@3JA; long g_cLoaderComponent
0x18000808e  mov     rbx, [rsp+28h+arg_0]
0x180008093  add     rsp, 20h
0x180008097  pop     rdi
0x180008098  retn
```
