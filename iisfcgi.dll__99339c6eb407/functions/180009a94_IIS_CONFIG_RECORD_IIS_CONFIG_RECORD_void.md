# IIS_CONFIG_RECORD::IIS_CONFIG_RECORD(void)

- ea: `0x180009a94`
- end: `0x180009b43`
- name: `??0IIS_CONFIG_RECORD@@QEAA@XZ`
- size: `175`
- prototype: `IIS_CONFIG_RECORD *__fastcall(IIS_CONFIG_RECORD *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000a028`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180009aa1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009aab`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009ab8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009ac5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009ad2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009aa1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009aab`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009ab8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009ac5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009ad2`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180009ae9`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180009ae9`

## pseudocode

```c
IIS_CONFIG_RECORD *__fastcall IIS_CONFIG_RECORD::IIS_CONFIG_RECORD(IIS_CONFIG_RECORD *this)
{
  IIS_CONFIG_RECORD *result; // rax

  STRU::STRU((IIS_CONFIG_RECORD *)((char *)this + 24));
  STRU::STRU((IIS_CONFIG_RECORD *)((char *)this + 80));
  STRU::STRU((IIS_CONFIG_RECORD *)((char *)this + 136));
  STRU::STRU((IIS_CONFIG_RECORD *)((char *)this + 192));
  STRU::STRU((IIS_CONFIG_RECORD *)((char *)this + 248));
  *((_DWORD *)this + 76) = 0;
  MULTISZ::MULTISZ((IIS_CONFIG_RECORD *)((char *)this + 312));
  result = this;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_DWORD *)this + 100) = 0;
  *((_DWORD *)this + 101) = 10;
  *((_QWORD *)this + 51) = 0;
  return result;
}

```

## disassembly

```asm
0x180009a94  push    rbx
0x180009a96  sub     rsp, 20h
0x180009a9a  mov     rbx, rcx
0x180009a9d  add     rcx, 18h
0x180009aa1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009aa7  lea     rcx, [rbx+50h]
0x180009aab  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009ab1  lea     rcx, [rbx+88h]
0x180009ab8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009abe  lea     rcx, [rbx+0C0h]
0x180009ac5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009acb  lea     rcx, [rbx+0F8h]
0x180009ad2  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009ad8  lea     rcx, [rbx+138h]
0x180009adf  mov     dword ptr [rbx+130h], 0
0x180009ae9  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180009aef  mov     rax, rbx
0x180009af2  mov     qword ptr [rbx+170h], 0
0x180009afd  mov     qword ptr [rbx+178h], 0
0x180009b08  mov     qword ptr [rbx+180h], 0
0x180009b13  mov     qword ptr [rbx+188h], 0
0x180009b1e  mov     dword ptr [rbx+190h], 0
0x180009b28  mov     dword ptr [rbx+194h], 0Ah
0x180009b32  mov     qword ptr [rbx+198h], 0
0x180009b3d  add     rsp, 20h
0x180009b41  pop     rbx
0x180009b42  retn
```
