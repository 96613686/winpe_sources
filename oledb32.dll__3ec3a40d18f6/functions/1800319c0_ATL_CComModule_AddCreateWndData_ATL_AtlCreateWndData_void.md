# ATL::CComModule::AddCreateWndData(ATL::_AtlCreateWndData *,void *)

- ea: `0x1800319c0`
- end: `0x180031a2b`
- name: `?AddCreateWndData@CComModule@ATL@@QEAAXPEAU_AtlCreateWndData@2@PEAX@Z`
- size: `107`
- prototype: `void __fastcall(ATL::CComModule *__hidden this, struct ATL::_AtlCreateWndData *, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002765c`
- `0x1800507d0`

## callees

- `0x1800319c0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800319ef`
- `KERNEL32!EnterCriticalSection` at `0x1800319ef`
- `KERNEL32!LeaveCriticalSection` at `0x180031a24`
- `KERNEL32!RaiseException` at `0x1800319e1`
- `KERNEL32!RaiseException` at `0x1800319e1`
- `KERNEL32!GetCurrentThreadId` at `0x1800319f8`
- `KERNEL32!GetCurrentThreadId` at `0x1800319f8`

## pseudocode

```c
void __fastcall ATL::CComModule::AddCreateWndData(ATL::CComModule *this, struct ATL::_AtlCreateWndData *a2, void *a3)
{
  if ( !a3 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    __debugbreak();
  }
  EnterCriticalSection(&stru_1800BE3A0);
  *(_QWORD *)a2 = a3;
  *((_DWORD *)a2 + 2) = GetCurrentThreadId();
  *((_QWORD *)a2 + 2) = qword_1800BE3F0;
  qword_1800BE3F0 = (__int64)a2;
  LeaveCriticalSection(&stru_1800BE3A0);
}

```

## disassembly

```asm
0x1800319c0  mov     [rsp+arg_0], rbx
0x1800319c5  push    rdi
0x1800319c6  sub     rsp, 20h
0x1800319ca  mov     rdi, r8
0x1800319cd  mov     rbx, rdx
0x1800319d0  test    r8, r8
0x1800319d3  jnz     short loc_1800319E8
0x1800319d5  xor     r9d, r9d; lpArguments
0x1800319d8  lea     edx, [r8+1]; dwExceptionFlags
0x1800319dc  mov     ecx, 0C0000005h; dwExceptionCode
0x1800319e1  call    cs:__imp_RaiseException
0x1800319e7  int     3; Trap to Debugger
0x1800319e8  lea     rcx, stru_1800BE3A0; lpCriticalSection
0x1800319ef  call    cs:__imp_EnterCriticalSection
0x1800319f5  mov     [rbx], rdi
0x1800319f8  call    cs:__imp_GetCurrentThreadId
0x1800319fe  mov     [rbx+8], eax
0x180031a01  lea     rcx, stru_1800BE3A0
0x180031a08  mov     rax, cs:qword_1800BE3F0
0x180031a0f  mov     [rbx+10h], rax
0x180031a13  mov     cs:qword_1800BE3F0, rbx
0x180031a1a  mov     rbx, [rsp+28h+arg_0]
0x180031a1f  add     rsp, 20h
0x180031a23  pop     rdi
0x180031a24  jmp     cs:__imp_LeaveCriticalSection
```
