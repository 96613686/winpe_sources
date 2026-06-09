# CProviderSession::GetDataSource(_GUID const &,IUnknown * *)

- ea: `0x18002ed00`
- end: `0x18002ede2`
- name: `?GetDataSource@CProviderSession@@UEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(CProviderSession *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e770`
- `0x18002ed00`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002ed33`
- `KERNEL32!GetCurrentThreadId` at `0x18002ed33`
- `KERNEL32!LeaveCriticalSection` at `0x18002edc6`
- `KERNEL32!LeaveCriticalSection` at `0x18002edc6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002ed54`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002ed54`
- `MSDART!UMSEnterCSWraper` at `0x18002ed1d`
- `MSDART!UMSEnterCSWraper` at `0x18002ed1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderSession::GetDataSource(
        CProviderSession *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  char *v6; // rbx
  DWORD *v7; // rdi
  unsigned int v8; // r8d
  int v9; // edx
  __int64 (__fastcall ***v10)(_QWORD, const struct _GUID *, struct IUnknown **); // rcx
  unsigned int v11; // esi
  __int64 v13; // rcx

  v6 = (char *)this + 40;
  UMSEnterCSWraper((char *)this + 40);
  v7 = (DWORD *)(v6 + 8);
  if ( !*((_DWORD *)v6 + 3) )
    *v7 = GetCurrentThreadId();
  ++*((_DWORD *)v6 + 3);
  ++*((_DWORD *)v6 + 4);
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this + 88) = IID_IGetDataSource;
  *((_DWORD *)this + 1051) = 0;
  if ( a3 )
  {
    v10 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, struct IUnknown **))*((_QWORD *)this + 8);
    if ( v10 )
      v9 = (**v10)(v10, a2, a3);
    else
      v9 = -2147467259;
  }
  else
  {
    v9 = -2147024809;
  }
  v11 = CError::PostErrorIfNone((CProviderSession *)((char *)this + 72), v9, v8);
  --*((_DWORD *)v6 + 4);
  if ( (*((_DWORD *)v6 + 3))-- == 1 )
    *v7 = -1;
  v13 = *(_QWORD *)v6;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v11;
}

```

## disassembly

```asm
0x18002ed00  push    rbx
0x18002ed02  push    rbp
0x18002ed03  push    rsi
0x18002ed04  push    rdi
0x18002ed05  push    r14
0x18002ed07  push    r15
0x18002ed09  sub     rsp, 28h
0x18002ed0d  mov     r14, r8
0x18002ed10  mov     r15, rdx
0x18002ed13  mov     rbp, rcx
0x18002ed16  lea     rbx, [rcx+28h]
0x18002ed1a  mov     rcx, rbx
0x18002ed1d  call    cs:__imp_UMSEnterCSWraper
0x18002ed24  nop     dword ptr [rax+rax+00h]
0x18002ed29  lea     rdi, [rbx+8]
0x18002ed2d  cmp     dword ptr [rbx+0Ch], 0
0x18002ed31  jnz     short loc_18002ED41
0x18002ed33  call    cs:__imp_GetCurrentThreadId
0x18002ed3a  nop     dword ptr [rax+rax+00h]
0x18002ed3f  mov     [rdi], eax
0x18002ed41  inc     dword ptr [rbx+0Ch]
0x18002ed44  inc     dword ptr [rbx+10h]
0x18002ed47  mov     [rsp+58h+arg_0], rbx
0x18002ed4c  lea     rsi, [rbp+48h]
0x18002ed50  xor     edx, edx; perrinfo
0x18002ed52  xor     ecx, ecx; dwReserved
0x18002ed54  call    cs:__imp_SetErrorInfo
0x18002ed5b  nop     dword ptr [rax+rax+00h]
0x18002ed60  movups  xmm0, xmmword ptr cs:IID_IGetDataSource.Data1
0x18002ed67  movdqu  xmmword ptr [rsi+10h], xmm0
0x18002ed6c  mov     dword ptr [rsi+1024h], 0
0x18002ed76  test    r14, r14
0x18002ed79  jnz     short loc_18002ED82
0x18002ed7b  mov     edx, 80070057h
0x18002ed80  jmp     short loc_18002EDA5
0x18002ed82  mov     rcx, [rbp+40h]
0x18002ed86  test    rcx, rcx
0x18002ed89  jnz     short loc_18002ED92
0x18002ed8b  mov     edx, 80004005h
0x18002ed90  jmp     short loc_18002EDA5
0x18002ed92  mov     rax, [rcx]
0x18002ed95  mov     r8, r14
0x18002ed98  mov     rdx, r15
0x18002ed9b  mov     rax, [rax]
0x18002ed9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eda3  mov     edx, eax; int
0x18002eda5  mov     rcx, rsi; this
0x18002eda8  call    ?PostErrorIfNone@CError@@QEAAJJK@Z; CError::PostErrorIfNone(long,ulong)
0x18002edad  mov     esi, eax
0x18002edaf  or      edx, 0FFFFFFFFh
0x18002edb2  add     [rbx+10h], edx
0x18002edb5  add     [rbx+0Ch], edx
0x18002edb8  jnz     short loc_18002EDBC
0x18002edba  mov     [rdi], edx
0x18002edbc  mov     rcx, [rbx]
0x18002edbf  dec     dword ptr [rcx+30h]
0x18002edc2  add     rcx, 8; lpCriticalSection
0x18002edc6  call    cs:__imp_LeaveCriticalSection
0x18002edcd  nop     dword ptr [rax+rax+00h]
0x18002edd2  mov     eax, esi
0x18002edd4  add     rsp, 28h
0x18002edd8  pop     r15
0x18002edda  pop     r14
0x18002eddc  pop     rdi
0x18002eddd  pop     rsi
0x18002edde  pop     rbp
0x18002eddf  pop     rbx
0x18002ede0  retn
```
