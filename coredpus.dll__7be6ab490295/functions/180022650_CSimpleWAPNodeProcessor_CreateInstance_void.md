# CSimpleWAPNodeProcessor::CreateInstance(void)

- ea: `0x180022650`
- end: `0x1800226c9`
- name: `?CreateInstance@CSimpleWAPNodeProcessor@@SAPEAUIUnknown@@XZ`
- size: `121`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800145f0`
- `0x180022650`
- `0x1800228a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800226ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800226ac`

## pseudocode

```c
struct IUnknown *CSimpleWAPNodeProcessor::CreateInstance(void)
{
  CWAPNodeProcessorBase *v0; // rax
  CWAPNodeProcessorBase *v1; // rbx

  v0 = (CWAPNodeProcessorBase *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v1 = v0;
  if ( !v0 )
    return 0;
  CWAPNodeProcessorBase::CWAPNodeProcessorBase(v0);
  *(_QWORD *)v1 = &CSimpleWAPNodeProcessor::`vftable';
  *((_QWORD *)v1 + 2) = 0;
  *((_DWORD *)v1 + 6) = 0;
  *((_DWORD *)v1 + 6) = CoCreateInstance(
                          &GUID_9c62d90d_9c14_400a_942a_404aba5e1f38,
                          0,
                          1u,
                          &GUID_d4c5e807_d2bf_49a0_83a4_f9c7d57e08d8,
                          (LPVOID *)v1 + 2);
  return (struct IUnknown *)v1;
}

```

## disassembly

```asm
0x180022650  push    rbx
0x180022652  sub     rsp, 30h
0x180022656  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002265d  mov     ecx, 20h ; ' '; unsigned __int64
0x180022662  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022667  mov     rbx, rax
0x18002266a  test    rax, rax
0x18002266d  jz      short loc_1800226BD
0x18002266f  mov     rcx, rax; this
0x180022672  call    ??0CWAPNodeProcessorBase@@QEAA@XZ; CWAPNodeProcessorBase::CWAPNodeProcessorBase(void)
0x180022677  lea     rax, [rbx+10h]
0x18002267b  xor     edx, edx; pUnkOuter
0x18002267d  lea     rcx, ??_7CSimpleWAPNodeProcessor@@6B@; const CSimpleWAPNodeProcessor::`vftable'
0x180022684  mov     [rsp+38h+ppv], rax; ppv
0x180022689  mov     [rbx], rcx
0x18002268c  lea     r9, _GUID_d4c5e807_d2bf_49a0_83a4_f9c7d57e08d8; riid
0x180022693  mov     qword ptr [rax], 0
0x18002269a  lea     rcx, _GUID_9c62d90d_9c14_400a_942a_404aba5e1f38; rclsid
0x1800226a1  lea     r8d, [rdx+1]; dwClsContext
0x1800226a5  mov     dword ptr [rbx+18h], 0
0x1800226ac  call    cs:__imp_CoCreateInstance
0x1800226b3  nop     dword ptr [rax+rax+00h]
0x1800226b8  mov     [rbx+18h], eax
0x1800226bb  jmp     short loc_1800226BF
0x1800226bd  xor     ebx, ebx
0x1800226bf  mov     rax, rbx
0x1800226c2  add     rsp, 30h
0x1800226c6  pop     rbx
0x1800226c7  retn
```
