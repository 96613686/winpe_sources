# CThreadPool::AddWorkItem(ulong (*)(void *),void *,void *,ulong)

- ea: `0x180005f58`
- end: `0x180006072`
- name: `?AddWorkItem@CThreadPool@@QEAAJP6AKPEAX@Z00K@Z`
- size: `282`
- prototype: `int(CThreadPool *__hidden this, unsigned int (*)(void *), void *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037214`

## callees

- `0x180005f58`
- `0x1800061c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005f86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005f86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000605c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000605c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000603e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000603e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180006011`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180006011`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180005fcd`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180005fcd`

## pseudocode

```c
__int64 __fastcall CThreadPool::AddWorkItem(CThreadPool *this, unsigned int (*a2)(void *), void *a3, void *a4)
{
  HANDLE ProcessHeap; // rax
  void **v9; // rax
  void **v10; // rdi
  signed int v11; // ebx
  void **phNewToken; // rax
  signed int LastError; // eax
  signed int v15; // eax

  ProcessHeap = GetProcessHeap();
  v9 = (void **)HeapAlloc(ProcessHeap, 0, 0x20u);
  v10 = v9;
  if ( v9 )
  {
    v9[1] = a3;
    v11 = 0;
    *((_DWORD *)v9 + 6) = 16;
    *v9 = a2;
    phNewToken = v9 + 2;
    *phNewToken = 0;
    if ( !a4 || DuplicateTokenEx(a4, 0xCu, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
      goto LABEL_17;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
    {
LABEL_17:
      if ( TrySubmitThreadpoolCallback(
             (PTP_SIMPLE_CALLBACK)_WorkItemWrapper,
             v10,
             (PTP_CALLBACK_ENVIRON)((char *)this + 8)) )
      {
        v10 = 0;
      }
      else
      {
        v15 = GetLastError();
        v11 = v15;
        if ( v15 > 0 )
          v11 = (unsigned __int16)v15 | 0x80070000;
      }
    }
    _DestroyWorkItemInfo((struct WorkItemInfo *)v10);
  }
  else
  {
    SetLastError(8u);
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005f58  push    rbx
0x180005f5a  push    rbp
0x180005f5b  push    rsi
0x180005f5c  push    rdi
0x180005f5d  push    r14
0x180005f5f  push    r15
0x180005f61  sub     rsp, 38h
0x180005f65  mov     rsi, r9
0x180005f68  mov     rbp, r8
0x180005f6b  mov     r14, rdx
0x180005f6e  mov     r15, rcx
0x180005f71  call    cs:__imp_GetProcessHeap
0x180005f78  nop     dword ptr [rax+rax+00h]
0x180005f7d  xor     edx, edx; dwFlags
0x180005f7f  mov     rcx, rax; hHeap
0x180005f82  lea     r8d, [rdx+20h]; dwBytes
0x180005f86  call    cs:__imp_HeapAlloc
0x180005f8d  nop     dword ptr [rax+rax+00h]
0x180005f92  mov     rdi, rax
0x180005f95  test    rax, rax
0x180005f98  jz      loc_180006057
0x180005f9e  mov     [rax+8], rbp
0x180005fa2  xor     ebx, ebx
0x180005fa4  mov     dword ptr [rax+18h], 10h
0x180005fab  mov     ebp, 80070000h
0x180005fb0  mov     [rax], r14
0x180005fb3  add     rax, 10h
0x180005fb7  mov     [rax], rbx
0x180005fba  test    rsi, rsi
0x180005fbd  jnz     short loc_180005FF7
0x180005fbf  lea     r8, [r15+8]; pcbe
0x180005fc3  mov     rdx, rdi; pv
0x180005fc6  lea     rcx, ?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180005fcd  call    cs:__imp_TrySubmitThreadpoolCallback
0x180005fd4  nop     dword ptr [rax+rax+00h]
0x180005fd9  test    eax, eax
0x180005fdb  jz      short loc_18000603E
0x180005fdd  xor     edi, edi
0x180005fdf  mov     rcx, rdi; lpMem
0x180005fe2  call    ?_DestroyWorkItemInfo@@YAXPEAUWorkItemInfo@@@Z; _DestroyWorkItemInfo(WorkItemInfo *)
0x180005fe7  mov     eax, ebx
0x180005fe9  add     rsp, 38h
0x180005fed  pop     r15
0x180005fef  pop     r14
0x180005ff1  pop     rdi
0x180005ff2  pop     rsi
0x180005ff3  pop     rbp
0x180005ff4  pop     rbx
0x180005ff5  retn
0x180005ff7  mov     r9d, 2; ImpersonationLevel
0x180005ffd  mov     [rsp+68h+phNewToken], rax; phNewToken
0x180006002  xor     r8d, r8d; lpTokenAttributes
0x180006005  mov     [rsp+68h+TokenType], r9d; TokenType
0x18000600a  mov     rcx, rsi; hExistingToken
0x18000600d  lea     edx, [r9+0Ah]; dwDesiredAccess
0x180006011  call    cs:__imp_DuplicateTokenEx
0x180006018  nop     dword ptr [rax+rax+00h]
0x18000601d  test    eax, eax
0x18000601f  jnz     short loc_180005FBF
0x180006021  call    cs:__imp_GetLastError
0x180006028  nop     dword ptr [rax+rax+00h]
0x18000602d  mov     ebx, eax
0x18000602f  test    eax, eax
0x180006031  jle     short loc_180006038
0x180006033  movzx   ebx, ax
0x180006036  or      ebx, ebp
0x180006038  test    ebx, ebx
0x18000603a  js      short loc_180005FDF
0x18000603c  jmp     short loc_180005FBF
0x18000603e  call    cs:__imp_GetLastError
0x180006045  nop     dword ptr [rax+rax+00h]
0x18000604a  mov     ebx, eax
0x18000604c  test    eax, eax
0x18000604e  jle     short loc_180005FDF
0x180006050  movzx   ebx, ax
0x180006053  or      ebx, ebp
0x180006055  jmp     short loc_180005FDF
0x180006057  mov     ecx, 8; dwErrCode
0x18000605c  call    cs:__imp_SetLastError
0x180006063  nop     dword ptr [rax+rax+00h]
0x180006068  mov     ebx, 8007000Eh
0x18000606d  jmp     loc_180005FE7
```
