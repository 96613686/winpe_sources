# CCorSvcMgr::IsInterruptRequested(void)

- ea: `0x180025110`
- end: `0x1800251bc`
- name: `?IsInterruptRequested@CCorSvcMgr@@AEAAHXZ`
- size: `172`
- prototype: `__int64 __fastcall(CCorSvcMgr *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002142c`
- `0x180023924`
- `0x18002587c`
- `0x180026b78`
- `0x1800270b0`
- `0x180044593`

## callees

- `0x180025110`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x180025141`
- `KERNEL32!OpenEventW` at `0x180025141`
- `KERNEL32!WaitForSingleObject` at `0x18002516e`
- `KERNEL32!WaitForSingleObject` at `0x18002516e`
- `KERNEL32!CloseHandle` at `0x18002517f`
- `KERNEL32!CloseHandle` at `0x18002519a`
- `KERNEL32!CloseHandle` at `0x18002517f`
- `KERNEL32!CloseHandle` at `0x18002519a`
- `OLEAUT32!__imp_SysStringLen` at `0x180025129`
- `OLEAUT32!__imp_SysStringLen` at `0x180025129`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCorSvcMgr::IsInterruptRequested(BSTR *this)
{
  HANDLE v2; // rax
  void *v3; // rbx
  BOOL v4; // edi

  if ( !SysStringLen(this[25]) )
    return (unsigned __int8)NGENService::g_bIsShutdownInProgress;
  v2 = OpenEventW(0x100000u, 0, this[25]);
  v3 = v2;
  v4 = v2 != (HANDLE)-1LL;
  if ( !v2 || WaitForSingleObject(v2, 0) )
  {
    if ( v4 && v3 )
      CloseHandle(v3);
    return (unsigned __int8)NGENService::g_bIsShutdownInProgress;
  }
  if ( v4 )
    CloseHandle(v3);
  return 1;
}

```

## disassembly

```asm
0x180025110  mov     [rsp+arg_0], rbx
0x180025115  mov     [rsp+arg_8], rbp
0x18002511a  push    rdi
0x18002511b  sub     rsp, 30h
0x18002511f  mov     rbx, rcx
0x180025122  mov     rcx, [rcx+0C8h]; pbstr
0x180025129  call    cs:__imp_SysStringLen
0x18002512f  test    eax, eax
0x180025131  jz      short loc_1800251A5
0x180025133  mov     r8, [rbx+0C8h]; lpName
0x18002513a  xor     edx, edx; bInheritHandle
0x18002513c  mov     ecx, 100000h; dwDesiredAccess
0x180025141  call    cs:__imp_OpenEventW
0x180025147  mov     rbx, rax
0x18002514a  mov     [rsp+38h+var_18], rax
0x18002514f  and     [rsp+38h+var_10], 0
0x180025154  xor     edi, edi
0x180025156  lea     ebp, [rdi+1]
0x180025159  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002515d  cmovnz  edi, ebp
0x180025160  mov     [rsp+38h+var_10], edi
0x180025164  test    rax, rax
0x180025167  jz      short loc_18002518E
0x180025169  xor     edx, edx; dwMilliseconds
0x18002516b  mov     rcx, rax; hHandle
0x18002516e  call    cs:__imp_WaitForSingleObject
0x180025174  test    eax, eax
0x180025176  jnz     short loc_18002518E
0x180025178  test    edi, edi
0x18002517a  jz      short loc_18002518A
0x18002517c  mov     rcx, rbx; hObject
0x18002517f  call    cs:__imp_CloseHandle
0x180025185  and     [rsp+38h+var_10], 0
0x18002518a  mov     eax, ebp
0x18002518c  jmp     short loc_1800251AC
0x18002518e  test    edi, edi
0x180025190  jz      short loc_1800251A5
0x180025192  test    rbx, rbx
0x180025195  jz      short loc_1800251A0
0x180025197  mov     rcx, rbx; hObject
0x18002519a  call    cs:__imp_CloseHandle
0x1800251a0  and     [rsp+38h+var_10], 0
0x1800251a5  movzx   eax, cs:?g_bIsShutdownInProgress@NGENService@@3V?$Volatile@_N@@A; Volatile<bool> NGENService::g_bIsShutdownInProgress
0x1800251ac  mov     rbx, [rsp+38h+arg_0]
0x1800251b1  mov     rbp, [rsp+38h+arg_8]
0x1800251b6  add     rsp, 30h
0x1800251ba  pop     rdi
0x1800251bb  retn
```
