# CWaveObj::~CWaveObj(void)

- ea: `0x180014034`
- end: `0x18001409d`
- name: `??1CWaveObj@@AEAA@XZ`
- size: `105`
- prototype: `void __fastcall(CWaveObj *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000bf60`
- `0x18000ebdc`
- `0x18000ec80`

## callees

- `0x1800012c4`
- `0x180014034`
- `0x180014438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014050`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014050`

## pseudocode

```c
void __fastcall CWaveObj::~CWaveObj(CWaveObj *this, unsigned __int64 a2)
{
  _QWORD *v3; // rdi
  void *v4; // rcx

  if ( *((_DWORD *)this + 12) )
  {
    CWaveObj::Cleanup(this);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  }
  while ( 1 )
  {
    v3 = (_QWORD *)*((_QWORD *)this + 15);
    if ( !v3 )
      break;
    *((_QWORD *)this + 15) = *v3;
    *v3 = 0;
    v4 = (void *)v3[1];
    if ( v4 )
    {
      operator delete(v4, a2);
      v3[1] = 0;
    }
    operator delete(v3, 0x18u);
  }
}

```

## disassembly

```asm
0x180014034  mov     [rsp+arg_0], rbx
0x180014039  push    rdi
0x18001403a  sub     rsp, 20h
0x18001403e  cmp     dword ptr [rcx+30h], 0
0x180014042  mov     rbx, rcx
0x180014045  jz      short loc_180014056
0x180014047  call    ?Cleanup@CWaveObj@@AEAAXXZ; CWaveObj::Cleanup(void)
0x18001404c  lea     rcx, [rbx+8]; lpCriticalSection
0x180014050  call    cs:__imp_DeleteCriticalSection
0x180014056  mov     rdi, [rbx+78h]
0x18001405a  test    rdi, rdi
0x18001405d  jz      short loc_180014092
0x18001405f  mov     rax, [rdi]
0x180014062  mov     [rbx+78h], rax
0x180014066  mov     qword ptr [rdi], 0
0x18001406d  mov     rcx, [rdi+8]; void *
0x180014071  test    rcx, rcx
0x180014074  jz      short loc_180014083
0x180014076  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001407b  mov     qword ptr [rdi+8], 0
0x180014083  mov     edx, 18h; unsigned __int64
0x180014088  mov     rcx, rdi; void *
0x18001408b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014090  jmp     short loc_180014056
0x180014092  mov     rbx, [rsp+28h+arg_0]
0x180014097  add     rsp, 20h
0x18001409b  pop     rdi
0x18001409c  retn
```
