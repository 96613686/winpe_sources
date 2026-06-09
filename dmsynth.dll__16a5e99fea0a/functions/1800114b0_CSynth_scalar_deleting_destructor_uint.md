# CSynth::`scalar deleting destructor'(uint)

- ea: `0x1800114b0`
- end: `0x18001159a`
- name: `??_GCSynth@@QEAAPEAXI@Z`
- size: `234`
- prototype: `void *__fastcall(CSynth *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000e5c0`
- `0x1800117f0`
- `0x180012460`

## callees

- `0x180001514`
- `0x1800061a0`
- `0x180007a00`
- `0x18000b070`
- `0x1800114b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011568`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011568`

## pseudocode

```c
CSynth *__fastcall CSynth::`scalar deleting destructor'(CSynth *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rdi
  _QWORD *v4; // rdi

  if ( *((_DWORD *)this + 272) )
  {
    CSynth::Close(this);
    while ( 1 )
    {
      v2 = (_QWORD *)*((_QWORD *)this + 8);
      if ( !v2 )
        break;
      *((_QWORD *)this + 8) = *v2;
      *v2 = 0;
      CDigitalAudio::~CDigitalAudio((CDigitalAudio *)(v2 + 31));
      operator delete(v2, 0x4F0u);
    }
    while ( 1 )
    {
      v3 = (_QWORD *)*((_QWORD *)this + 6);
      if ( !v3 )
        break;
      *((_QWORD *)this + 6) = *v3;
      *v3 = 0;
      CDigitalAudio::~CDigitalAudio((CDigitalAudio *)(v3 + 31));
      operator delete(v3, 0x4F0u);
    }
    while ( 1 )
    {
      v4 = (_QWORD *)*((_QWORD *)this + 7);
      if ( !v4 )
        break;
      *((_QWORD *)this + 7) = *v4;
      *v4 = 0;
      CDigitalAudio::~CDigitalAudio((CDigitalAudio *)(v4 + 31));
      operator delete(v4, 0x4F0u);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  }
  CInstManager::~CInstManager((CSynth *)((char *)this + 216));
  operator delete(this, 0x448u);
  return this;
}

```

## disassembly

```asm
0x1800114b0  push    rbx
0x1800114b2  sub     rsp, 20h
0x1800114b6  cmp     dword ptr [rcx+440h], 0
0x1800114bd  mov     rbx, rcx
0x1800114c0  jz      loc_180011578
0x1800114c6  mov     [rsp+28h+arg_0], rsi
0x1800114cb  mov     [rsp+28h+arg_8], rdi
0x1800114d0  call    ?Close@CSynth@@QEAAJXZ; CSynth::Close(void)
0x1800114d5  xor     esi, esi
0x1800114d7  mov     rdi, [rbx+40h]
0x1800114db  test    rdi, rdi
0x1800114de  jz      short loc_180011505
0x1800114e0  mov     rax, [rdi]
0x1800114e3  lea     rcx, [rdi+0F8h]; this
0x1800114ea  mov     [rbx+40h], rax
0x1800114ee  mov     [rdi], rsi
0x1800114f1  call    ??1CDigitalAudio@@QEAA@XZ; CDigitalAudio::~CDigitalAudio(void)
0x1800114f6  mov     edx, 4F0h; unsigned __int64
0x1800114fb  mov     rcx, rdi; void *
0x1800114fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011503  jmp     short loc_1800114D7
0x180011505  mov     rdi, [rbx+30h]
0x180011509  test    rdi, rdi
0x18001150c  jz      short loc_180011533
0x18001150e  mov     rax, [rdi]
0x180011511  lea     rcx, [rdi+0F8h]; this
0x180011518  mov     [rbx+30h], rax
0x18001151c  mov     [rdi], rsi
0x18001151f  call    ??1CDigitalAudio@@QEAA@XZ; CDigitalAudio::~CDigitalAudio(void)
0x180011524  mov     edx, 4F0h; unsigned __int64
0x180011529  mov     rcx, rdi; void *
0x18001152c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011531  jmp     short loc_180011505
0x180011533  mov     rdi, [rbx+38h]
0x180011537  test    rdi, rdi
0x18001153a  jz      short loc_180011561
0x18001153c  mov     rax, [rdi]
0x18001153f  lea     rcx, [rdi+0F8h]; this
0x180011546  mov     [rbx+38h], rax
0x18001154a  mov     [rdi], rsi
0x18001154d  call    ??1CDigitalAudio@@QEAA@XZ; CDigitalAudio::~CDigitalAudio(void)
0x180011552  mov     edx, 4F0h; unsigned __int64
0x180011557  mov     rcx, rdi; void *
0x18001155a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001155f  jmp     short loc_180011533
0x180011561  lea     rcx, [rbx+418h]; lpCriticalSection
0x180011568  call    cs:__imp_DeleteCriticalSection
0x18001156e  mov     rdi, [rsp+28h+arg_8]
0x180011573  mov     rsi, [rsp+28h+arg_0]
0x180011578  lea     rcx, [rbx+0D8h]; this
0x18001157f  call    ??1CInstManager@@QEAA@XZ; CInstManager::~CInstManager(void)
0x180011584  mov     edx, 448h; unsigned __int64
0x180011589  mov     rcx, rbx; void *
0x18001158c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011591  mov     rax, rbx
0x180011594  add     rsp, 20h
0x180011598  pop     rbx
0x180011599  retn
```
