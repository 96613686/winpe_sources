# IIS_CONFIG_RECORD::~IIS_CONFIG_RECORD(void)

- ea: `0x180009c00`
- end: `0x180009ca8`
- name: `??1IIS_CONFIG_RECORD@@QEAA@XZ`
- size: `168`
- prototype: `void __fastcall(IIS_CONFIG_RECORD *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180009b4c`
- `0x18000ab6c`
- `0x18000abfc`

## callees

- `0x180001048`
- `0x180007090`
- `0x1800086bc`
- `0x180009c00`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180009c69`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009c76`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009c83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009c8d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009c69`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009c76`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009c83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009c8d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009ca1`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180009c5c`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180009c5c`

## pseudocode

```c
void __fastcall IIS_CONFIG_RECORD::~IIS_CONFIG_RECORD(IIS_CONFIG_RECORD *this)
{
  APPLICATION_MANAGER *v2; // rcx
  volatile signed __int32 *v3; // rdi

  v2 = (APPLICATION_MANAGER *)*((_QWORD *)this + 51);
  if ( v2 )
  {
    APPLICATION_MANAGER::Shutdown(v2);
    v3 = (volatile signed __int32 *)*((_QWORD *)this + 51);
    if ( _InterlockedExchangeAdd(v3 + 35, 0xFFFFFFFF) == 1 && v3 )
    {
      APPLICATION_MANAGER::~APPLICATION_MANAGER((APPLICATION_MANAGER *)v3);
      operator delete((void *)v3);
    }
    *((_QWORD *)this + 51) = 0;
  }
  MULTISZ::~MULTISZ((IIS_CONFIG_RECORD *)((char *)this + 312));
  STRU::~STRU((IIS_CONFIG_RECORD *)((char *)this + 248));
  STRU::~STRU((IIS_CONFIG_RECORD *)((char *)this + 192));
  STRU::~STRU((IIS_CONFIG_RECORD *)((char *)this + 136));
  STRU::~STRU((IIS_CONFIG_RECORD *)((char *)this + 80));
  STRU::~STRU((IIS_CONFIG_RECORD *)((char *)this + 24));
}

```

## disassembly

```asm
0x180009c00  mov     [rsp+arg_8], rbx
0x180009c05  push    rdi
0x180009c06  sub     rsp, 20h
0x180009c0a  mov     rbx, rcx
0x180009c0d  mov     rcx, [rcx+198h]; this
0x180009c14  test    rcx, rcx
0x180009c17  jz      short loc_180009C55
0x180009c19  call    ?Shutdown@APPLICATION_MANAGER@@QEAAJXZ; APPLICATION_MANAGER::Shutdown(void)
0x180009c1e  mov     rdi, [rbx+198h]
0x180009c25  or      eax, 0FFFFFFFFh
0x180009c28  lock xadd [rdi+8Ch], eax
0x180009c30  cmp     eax, 1
0x180009c33  jnz     short loc_180009C4A
0x180009c35  test    rdi, rdi
0x180009c38  jz      short loc_180009C4A
0x180009c3a  mov     rcx, rdi; this
0x180009c3d  call    ??1APPLICATION_MANAGER@@AEAA@XZ; APPLICATION_MANAGER::~APPLICATION_MANAGER(void)
0x180009c42  mov     rcx, rdi; Block
0x180009c45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009c4a  mov     qword ptr [rbx+198h], 0
0x180009c55  lea     rcx, [rbx+138h]
0x180009c5c  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180009c62  lea     rcx, [rbx+0F8h]
0x180009c69  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009c6f  lea     rcx, [rbx+0C0h]
0x180009c76  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009c7c  lea     rcx, [rbx+88h]
0x180009c83  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009c89  lea     rcx, [rbx+50h]
0x180009c8d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009c93  lea     rcx, [rbx+18h]
0x180009c97  mov     rbx, [rsp+28h+arg_8]
0x180009c9c  add     rsp, 20h
0x180009ca0  pop     rdi
0x180009ca1  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
