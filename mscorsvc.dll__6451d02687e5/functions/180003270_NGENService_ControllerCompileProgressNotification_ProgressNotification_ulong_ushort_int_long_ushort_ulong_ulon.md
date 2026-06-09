# NGENService::ControllerCompileProgressNotification::ProgressNotification(ulong,ushort *,int,long,ushort *,ulong,ulong)

- ea: `0x180003270`
- end: `0x1800034bd`
- name: `?ProgressNotification@ControllerCompileProgressNotification@NGENService@@UEAAJKPEAGHJ0KK@Z`
- size: `589`
- prototype: `int(NGENService::ControllerCompileProgressNotification *__hidden this, unsigned int, unsigned __int16 *, int, int, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001e8c`
- `0x180003270`
- `0x18002e1d0`
- `0x18002e418`
- `0x180030d84`
- `0x180032654`
- `0x180032948`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000348e`
- `KERNEL32!HeapFree` at `0x18000348e`
- `KERNEL32!GetProcessHeap` at `0x180003479`
- `KERNEL32!GetProcessHeap` at `0x180003479`

## string_xrefs

- `0x1800032ab`: `Service Manager Callback:\n`
- `0x18000330c`: `Began compiling: %s\n`
- `0x180003384`: `Failed to compile: %s . `
- `0x180003429`: `Successfully compiled: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NGENService::ControllerCompileProgressNotification::ProgressNotification(
        NGENService::ControllerCompileProgressNotification *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8)
{
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  _BYTE v13[12]; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-D0h]
  char v15; // [rsp+38h] [rbp-C8h] BYREF

  NGENService::DebugLog((NGENService *)L"Service Manager Callback:\n", a2);
  *(_DWORD *)v13 = 0;
  *(_QWORD *)&v13[4] = 512;
  lpMem = &v15;
  if ( a4 )
  {
    *(_DWORD *)v13 = 2;
    *(_WORD *)lpMem = 0;
    if ( a8 )
      SString::Printf((SString *)v13, L"%d>");
    SString::AppendPrintf((SString *)v13, L"Began compiling: %s\n", a3);
    SString::ConvertToUnicode((SString *)v13);
    NGENService::EventLog(
      (NGENService *)a3,
      (const unsigned __int16 *)4,
      0x44Cu,
      (unsigned int)lpMem,
      *(const unsigned __int16 **)v13);
  }
  else if ( a5 >= 0 )
  {
    *(_DWORD *)v13 = 2;
    *(_WORD *)lpMem = 0;
    if ( a8 )
      SString::Printf((SString *)v13, L"%d>");
    SString::AppendPrintf((SString *)v13, L"Successfully compiled: %s\n", a3);
    SString::ConvertToUnicode((SString *)v13);
    NGENService::EventLog((NGENService *)a3, 0, 0x44Eu, (unsigned int)lpMem, *(const unsigned __int16 **)v13);
  }
  else
  {
    *(_DWORD *)v13 = 2;
    *(_WORD *)lpMem = 0;
    if ( a8 )
      SString::Printf((SString *)v13, L"%d>");
    SString::AppendPrintf((SString *)v13, L"Failed to compile: %s . ", a3);
    SString::AppendPrintf((SString *)v13, L"Error code = 0x%08x ", (unsigned int)a5);
    if ( a6 )
      SString::AppendPrintf((SString *)v13, L": %s", a6);
    SString::Append((SString *)v13, L"\n");
    SString::ConvertToUnicode((SString *)v13);
    NGENService::EventLog(
      (NGENService *)a3,
      (const unsigned __int16 *)1,
      0x44Du,
      (unsigned int)lpMem,
      *(const unsigned __int16 **)v13);
  }
  if ( (v13[8] & 8) != 0 )
  {
    v10 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v10);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003270  mov     [rsp-8+arg_0], rbx
0x180003275  mov     [rsp-8+arg_8], rsi
0x18000327a  push    rbp
0x18000327b  push    rdi
0x18000327c  push    r14
0x18000327e  lea     rbp, [rsp-150h]
0x180003286  sub     rsp, 250h
0x18000328d  mov     rax, cs:__security_cookie
0x180003294  xor     rax, rsp
0x180003297  mov     [rbp+160h+var_20], rax
0x18000329e  mov     ebx, r9d
0x1800032a1  mov     rdi, r8
0x1800032a4  mov     rsi, [rbp+160h+arg_28]
0x1800032ab  lea     rcx, aServiceManager_1; "Service Manager Callback:\n"
0x1800032b2  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800032b7  xor     r14d, r14d
0x1800032ba  mov     [rsp+260h+var_240], r14
0x1800032bf  mov     [rsp+260h+lpMem], r14
0x1800032c4  lea     rax, [rsp+260h+var_228]
0x1800032c9  mov     [rsp+260h+var_240+4], 200h
0x1800032d2  mov     [rsp+260h+lpMem], rax
0x1800032d7  test    ebx, ebx
0x1800032d9  jz      short loc_180003345
0x1800032db  mov     dword ptr [rsp+260h+var_240], 2; unsigned __int16 *
0x1800032e3  mov     rax, [rsp+260h+lpMem]
0x1800032e8  mov     [rax], r14w
0x1800032ec  mov     r8d, [rbp+160h+arg_38]
0x1800032f3  test    r8d, r8d
0x1800032f6  jz      short loc_180003309
0x1800032f8  lea     rdx, aD_0; "%d>"
0x1800032ff  lea     rcx, [rsp+260h+var_240]; this
0x180003304  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180003309  mov     r8, rdi
0x18000330c  lea     rdx, aBeganCompiling; "Began compiling: %s\n"
0x180003313  lea     rcx, [rsp+260h+var_240]; this
0x180003318  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18000331d  lea     rcx, [rsp+260h+var_240]; this
0x180003322  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180003327  mov     edx, 4; unsigned __int16 *
0x18000332c  mov     r9, [rsp+260h+lpMem]; unsigned int
0x180003331  mov     r8d, 44Ch; unsigned __int16
0x180003337  mov     rcx, rdi; this
0x18000333a  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x18000333f  nop
0x180003340  jmp     loc_18000345C
0x180003345  mov     ebx, [rbp+160h+arg_20]
0x18000334b  test    ebx, ebx
0x18000334d  jns     loc_1800033F8
0x180003353  mov     dword ptr [rsp+260h+var_240], 2; unsigned __int16 *
0x18000335b  mov     rax, [rsp+260h+lpMem]
0x180003360  mov     [rax], r14w
0x180003364  mov     r8d, [rbp+160h+arg_38]
0x18000336b  test    r8d, r8d
0x18000336e  jz      short loc_180003381
0x180003370  lea     rdx, aD_0; "%d>"
0x180003377  lea     rcx, [rsp+260h+var_240]; this
0x18000337c  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180003381  mov     r8, rdi
0x180003384  lea     rdx, aFailedToCompil; "Failed to compile: %s . "
0x18000338b  lea     rcx, [rsp+260h+var_240]; this
0x180003390  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x180003395  mov     r8d, ebx
0x180003398  lea     rdx, aErrorCode0x08x; "Error code = 0x%08x "
0x18000339f  lea     rcx, [rsp+260h+var_240]; this
0x1800033a4  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x1800033a9  test    rsi, rsi
0x1800033ac  jz      short loc_1800033C2
0x1800033ae  mov     r8, rsi
0x1800033b1  lea     rdx, aS_4; ": %s"
0x1800033b8  lea     rcx, [rsp+260h+var_240]; this
0x1800033bd  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x1800033c2  lea     rdx, asc_180051EB0; "\n"
0x1800033c9  lea     rcx, [rsp+260h+var_240]; this
0x1800033ce  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800033d3  lea     rcx, [rsp+260h+var_240]; this
0x1800033d8  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800033dd  mov     edx, 1; unsigned __int16 *
0x1800033e2  mov     r9, [rsp+260h+lpMem]; unsigned int
0x1800033e7  mov     r8d, 44Dh; unsigned __int16
0x1800033ed  mov     rcx, rdi; this
0x1800033f0  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x1800033f5  nop
0x1800033f6  jmp     short loc_18000345C
0x1800033f8  mov     dword ptr [rsp+260h+var_240], 2; unsigned __int16 *
0x180003400  mov     rax, [rsp+260h+lpMem]
0x180003405  mov     [rax], r14w
0x180003409  mov     r8d, [rbp+160h+arg_38]
0x180003410  test    r8d, r8d
0x180003413  jz      short loc_180003426
0x180003415  lea     rdx, aD_0; "%d>"
0x18000341c  lea     rcx, [rsp+260h+var_240]; this
0x180003421  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180003426  mov     r8, rdi
0x180003429  lea     rdx, aSuccessfullyCo; "Successfully compiled: %s\n"
0x180003430  lea     rcx, [rsp+260h+var_240]; this
0x180003435  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x18000343a  lea     rcx, [rsp+260h+var_240]; this
0x18000343f  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180003444  mov     r9, [rsp+260h+lpMem]; unsigned int
0x180003449  mov     r8d, 44Eh; unsigned __int16
0x18000344f  movzx   edx, r14w; unsigned __int16 *
0x180003453  mov     rcx, rdi; this
0x180003456  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x18000345b  nop
0x18000345c  test    [rsp+260h+var_238], 8
0x180003461  jz      short loc_180003494
0x180003463  mov     rbx, [rsp+260h+lpMem]
0x180003468  test    rbx, rbx
0x18000346b  jz      short loc_180003494
0x18000346d  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180003474  test    rax, rax
0x180003477  jnz     short loc_180003486
0x180003479  call    cs:__imp_GetProcessHeap
0x18000347f  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180003486  mov     r8, rbx; lpMem
0x180003489  xor     edx, edx; dwFlags
0x18000348b  mov     rcx, rax; hHeap
0x18000348e  call    cs:__imp_HeapFree
0x180003494  xor     eax, eax
0x180003496  mov     rcx, [rbp+160h+var_20]
0x18000349d  xor     rcx, rsp; StackCookie
0x1800034a0  call    __security_check_cookie
0x1800034a5  lea     r11, [rsp+260h+var_10]
0x1800034ad  mov     rbx, [r11+20h]
0x1800034b1  mov     rsi, [r11+28h]
0x1800034b5  mov     rsp, r11
0x1800034b8  pop     r14
0x1800034ba  pop     rdi
0x1800034bb  pop     rbp
0x1800034bc  retn
```
