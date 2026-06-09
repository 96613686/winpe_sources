# CMCellularEntriesNodeProcessor::CreateInstance(void)

- ea: `0x1800224b0`
- end: `0x180022526`
- name: `?CreateInstance@CMCellularEntriesNodeProcessor@@SAPEAUIUnknown@@XZ`
- size: `118`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800145f0`
- `0x1800224b0`
- `0x1800228a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022508`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022508`

## pseudocode

```c
struct IUnknown *CMCellularEntriesNodeProcessor::CreateInstance(void)
{
  CWAPNodeProcessorBase *v0; // rax
  CWAPNodeProcessorBase *v1; // rbx
  IUnknown *v2; // rdx

  v0 = (CWAPNodeProcessorBase *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v1 = v0;
  if ( !v0 )
    return 0;
  CWAPNodeProcessorBase::CWAPNodeProcessorBase(v0);
  *(_QWORD *)v1 = &CMCellularEntriesNodeProcessor::`vftable';
  *((_QWORD *)v1 + 2) = v2;
  *((_QWORD *)v1 + 3) = v2;
  *((_DWORD *)v1 + 8) = (_DWORD)v2;
  *((_DWORD *)v1 + 8) = CoCreateInstance(
                          &GUID_9c62d90d_9c14_400a_942a_404aba5e1f38,
                          v2,
                          (_DWORD)v2 + 1,
                          &GUID_d4c5e807_d2bf_49a0_83a4_f9c7d57e08d8,
                          (LPVOID *)v1 + 2);
  return (struct IUnknown *)v1;
}

```

## disassembly

```asm
0x1800224b0  push    rbx
0x1800224b2  sub     rsp, 30h
0x1800224b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800224bd  mov     ecx, 28h ; '('; unsigned __int64
0x1800224c2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800224c7  xor     edx, edx
0x1800224c9  mov     rbx, rax
0x1800224cc  test    rax, rax
0x1800224cf  jz      short loc_180022519
0x1800224d1  mov     rcx, rax; this
0x1800224d4  call    ??0CWAPNodeProcessorBase@@QEAA@XZ; CWAPNodeProcessorBase::CWAPNodeProcessorBase(void)
0x1800224d9  lea     rax, [rbx+10h]
0x1800224dd  lea     rcx, ??_7CMCellularEntriesNodeProcessor@@6B@; const CMCellularEntriesNodeProcessor::`vftable'
0x1800224e4  mov     [rsp+38h+ppv], rax; ppv
0x1800224e9  mov     [rbx], rcx
0x1800224ec  lea     r9, _GUID_d4c5e807_d2bf_49a0_83a4_f9c7d57e08d8; riid
0x1800224f3  mov     [rax], rdx
0x1800224f6  lea     rcx, _GUID_9c62d90d_9c14_400a_942a_404aba5e1f38; rclsid
0x1800224fd  lea     r8d, [rdx+1]; dwClsContext
0x180022501  mov     [rbx+18h], rdx
0x180022505  mov     [rbx+20h], edx
0x180022508  call    cs:__imp_CoCreateInstance
0x18002250f  nop     dword ptr [rax+rax+00h]
0x180022514  mov     [rbx+20h], eax
0x180022517  jmp     short loc_18002251C
0x180022519  mov     rbx, rdx
0x18002251c  mov     rax, rbx
0x18002251f  add     rsp, 30h
0x180022523  pop     rbx
0x180022524  retn
```
