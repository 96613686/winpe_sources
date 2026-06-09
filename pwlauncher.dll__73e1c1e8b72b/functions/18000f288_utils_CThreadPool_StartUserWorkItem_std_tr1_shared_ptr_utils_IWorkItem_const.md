# utils::CThreadPool::StartUserWorkItem(std::tr1::shared_ptr<utils::IWorkItem> const &)

- ea: `0x18000f288`
- end: `0x18000f34e`
- name: `?StartUserWorkItem@CThreadPool@utils@@SAXAEBV?$shared_ptr@VIWorkItem@utils@@@tr1@std@@@Z`
- size: `198`
- prototype: `uintptr_t __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ab94`

## callees

- `0x1800016e4`
- `0x180002148`
- `0x18000ce50`
- `0x18000f148`
- `0x18000f260`
- `0x18000f288`
- `0x18000f3fc`

## import_xrefs

- `msvcrt!_errno` at `0x18000f31b`
- `msvcrt!_errno` at `0x18000f31b`
- `msvcrt!_beginthreadex` at `0x18000f2d6`
- `msvcrt!_beginthreadex` at `0x18000f2d6`

## pseudocode

```c
uintptr_t __fastcall utils::CThreadPool::StartUserWorkItem(__int64 *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  uintptr_t result; // rax
  int v5; // ebx
  int *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  _QWORD *pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v2 = operator new(0x10u);
  pExceptionObject = v2;
  if ( v2 )
    v3 = utils::CThreadPool::WorkItemWrapper::WorkItemWrapper(v2, a1);
  else
    v3 = 0;
  result = _beginthreadex(0, 0, utils::CThreadPool::ThreadEntry, v3, 0, 0);
  if ( !result )
  {
    if ( v3 )
      utils::CThreadPool::WorkItemWrapper::`scalar deleting destructor'((utils::CThreadPool::WorkItemWrapper *)v3);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject);
    v5 = (int)pExceptionObject;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = _errno();
      WPP_SF_dsD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, (unsigned int)*v6);
    }
    LODWORD(pExceptionObject) = v5;
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18000f288  push    rbx
0x18000f28a  sub     rsp, 30h
0x18000f28e  mov     rbx, rcx
0x18000f291  mov     ecx, 10h; Size
0x18000f296  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f29b  mov     [rsp+38h+pExceptionObject], rax
0x18000f2a0  test    rax, rax
0x18000f2a3  jz      short loc_18000F2B5
0x18000f2a5  mov     rdx, rbx
0x18000f2a8  mov     rcx, rax
0x18000f2ab  call    ??0WorkItemWrapper@CThreadPool@utils@@QEAA@AEBV?$shared_ptr@VIWorkItem@utils@@@tr1@std@@@Z; utils::CThreadPool::WorkItemWrapper::WorkItemWrapper(std::tr1::shared_ptr<utils::IWorkItem> const &)
0x18000f2b0  mov     rbx, rax
0x18000f2b3  jmp     short loc_18000F2B7
0x18000f2b5  xor     ebx, ebx
0x18000f2b7  mov     [rsp+38h+ThrdAddr], 0; ThrdAddr
0x18000f2c0  mov     [rsp+38h+InitFlag], 0; InitFlag
0x18000f2c8  mov     r9, rbx; ArgList
0x18000f2cb  lea     r8, ?ThreadEntry@CThreadPool@utils@@CAIPEAX@Z; StartAddress
0x18000f2d2  xor     edx, edx; StackSize
0x18000f2d4  xor     ecx, ecx; Security
0x18000f2d6  call    cs:__imp__beginthreadex
0x18000f2dc  test    rax, rax
0x18000f2df  jz      short loc_18000F2E7
0x18000f2e1  add     rsp, 30h
0x18000f2e5  pop     rbx
0x18000f2e6  retn
0x18000f2e7  test    rbx, rbx
0x18000f2ea  jz      short loc_18000F2F4
0x18000f2ec  mov     rcx, rbx; this
0x18000f2ef  call    ??_GWorkItemWrapper@CThreadPool@utils@@QEAAPEAXI@Z; utils::CThreadPool::WorkItemWrapper::`scalar deleting destructor'(uint)
0x18000f2f4  lea     rcx, [rsp+38h+pExceptionObject]; this
0x18000f2f9  call    ??0CAtlException@ATL@@QEAA@XZ; ATL::CAtlException::CAtlException(void)
0x18000f2fe  lea     rcx, WPP_GLOBAL_Control
0x18000f305  mov     ebx, dword ptr [rsp+38h+pExceptionObject]
0x18000f309  mov     rax, cs:WPP_GLOBAL_Control
0x18000f310  cmp     rax, rcx
0x18000f313  jz      short loc_18000F338
0x18000f315  test    byte ptr [rax+1Ch], 1
0x18000f319  jz      short loc_18000F338
0x18000f31b  call    cs:__imp__errno
0x18000f321  mov     dword ptr [rsp+38h+ThrdAddr], ebx
0x18000f325  mov     r9d, [rax]
0x18000f328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f32f  mov     rcx, [rcx+10h]
0x18000f333  call    WPP_SF_dsD
0x18000f338  mov     dword ptr [rsp+38h+pExceptionObject], ebx
0x18000f33c  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000f343  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000f348  call    _CxxThrowException_0
```
