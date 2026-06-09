# HrOnCommandFix(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x1800456d0`
- end: `0x180045779`
- name: `?HrOnCommandFix@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800020b0`
- `0x180005c8c`
- `0x18001e1e0`
- `0x1800456d0`
- `0x180045780`
- `0x18004a540`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180045738`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180045738`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004572c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004572c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrOnCommandFix(__int64 a1, HWND a2)
{
  int v4; // ebx
  ConFoldPidl_v3 *v5; // rcx
  HANDLE CurrentThread; // rax
  struct IShellFolder *v7; // r8
  _BYTE v9[144]; // [rsp+20h] [rbp-A8h] BYREF

  CConFoldEntry::CConFoldEntry((CConFoldEntry *)v9);
  if ( *(_QWORD *)a1 == *(_QWORD *)(a1 + 8) )
  {
    v4 = 0;
  }
  else
  {
    v5 = **(ConFoldPidl_v3 ***)a1;
    if ( v5 )
    {
      v4 = ConFoldPidl_v3::ConvertToConFoldEntry(v5, (struct CConFoldEntry *)v9);
      if ( v4 >= 0 )
      {
        CurrentThread = GetCurrentThread();
        SetThreadPriority(CurrentThread, -1);
        HrOnCommandFixInternal((const struct CConFoldEntry *)v9, a2, v7);
      }
    }
    else
    {
      v4 = -2147418113;
    }
  }
  CConFoldEntry::~CConFoldEntry((CConFoldEntry *)v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800456d0  mov     [rsp+arg_10], rbx
0x1800456d5  push    rdi
0x1800456d6  sub     rsp, 0C0h
0x1800456dd  mov     rax, cs:__security_cookie
0x1800456e4  xor     rax, rsp
0x1800456e7  mov     [rsp+0C8h+var_18], rax
0x1800456ef  mov     rdi, rdx
0x1800456f2  mov     rbx, rcx
0x1800456f5  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800456fa  call    ??0CConFoldEntry@@QEAA@XZ; CConFoldEntry::CConFoldEntry(void)
0x1800456ff  nop
0x180045700  mov     rcx, [rbx]
0x180045703  cmp     rcx, [rbx+8]
0x180045707  jnz     short loc_18004570D
0x180045709  xor     ebx, ebx
0x18004570b  jmp     short loc_18004574C
0x18004570d  mov     rcx, [rcx]; this
0x180045710  test    rcx, rcx
0x180045713  jnz     short loc_18004571C
0x180045715  mov     ebx, 8000FFFFh
0x18004571a  jmp     short loc_18004574C
0x18004571c  lea     rdx, [rsp+0C8h+var_A8]; struct CConFoldEntry *
0x180045721  call    ?ConvertToConFoldEntry@ConFoldPidl_v3@@QEBAJAEAVCConFoldEntry@@@Z; ConFoldPidl_v3::ConvertToConFoldEntry(CConFoldEntry &)
0x180045726  mov     ebx, eax
0x180045728  test    eax, eax
0x18004572a  js      short loc_18004574C
0x18004572c  call    cs:__imp_GetCurrentThread
0x180045732  mov     rcx, rax; hThread
0x180045735  or      edx, 0FFFFFFFFh; nPriority
0x180045738  call    cs:__imp_SetThreadPriority
0x18004573e  mov     rdx, rdi; HWND
0x180045741  lea     rcx, [rsp+0C8h+var_A8]; struct CConFoldEntry *
0x180045746  call    ?HrOnCommandFixInternal@@YAJAEBVCConFoldEntry@@PEAUHWND__@@PEAUIShellFolder@@@Z; HrOnCommandFixInternal(CConFoldEntry const &,HWND__ *,IShellFolder *)
0x18004574b  nop
0x18004574c  lea     rcx, [rsp+0C8h+var_A8]; this
0x180045751  call    ??1CConFoldEntry@@QEAA@XZ; CConFoldEntry::~CConFoldEntry(void)
0x180045756  mov     eax, ebx
0x180045758  mov     rcx, [rsp+0C8h+var_18]
0x180045760  xor     rcx, rsp; StackCookie
0x180045763  call    __security_check_cookie
0x180045768  mov     rbx, [rsp+0C8h+arg_10]
0x180045770  add     rsp, 0C0h
0x180045777  pop     rdi
0x180045778  retn
```
