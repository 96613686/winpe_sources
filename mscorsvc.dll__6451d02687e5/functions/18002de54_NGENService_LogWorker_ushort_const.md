# NGENService::LogWorker(ushort const *)

- ea: `0x18002de54`
- end: `0x18002df9f`
- name: `?LogWorker@NGENService@@YAXPEBG@Z`
- size: `331`
- prototype: `void __fastcall(NGENService *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x18002dfa0`
- `0x18002e1d0`
- `0x18002e308`

## callees

- `0x180001e8c`
- `0x18002dd20`
- `0x18002de54`
- `0x180030d84`
- `0x180032440`
- `0x18003a414`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18002dec6`
- `KERNEL32!GetCurrentProcessId` at `0x18002dec6`
- `KERNEL32!GetLocalTime` at `0x18002dec0`
- `KERNEL32!GetLocalTime` at `0x18002dec0`
- `KERNEL32!HeapFree` at `0x18002df72`
- `KERNEL32!HeapFree` at `0x18002df72`
- `KERNEL32!GetProcessHeap` at `0x18002df5d`
- `KERNEL32!GetProcessHeap` at `0x18002df5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NGENService::LogWorker(NGENService *this, const unsigned __int16 *a2)
{
  DWORD CurrentProcessId; // eax
  CircularLog *v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  int v8; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v9; // [rsp+64h] [rbp-9Ch]
  LPVOID lpMem; // [rsp+70h] [rbp-90h]
  __int16 v11; // [rsp+78h] [rbp-88h] BYREF

  NGENService::DebugLogWorker(this, a2);
  v9 = 512;
  lpMem = &v11;
  v8 = 2;
  v11 = 0;
  GetLocalTime(&SystemTime);
  CurrentProcessId = GetCurrentProcessId();
  SString::Printf(
    (SString *)&v8,
    "%02hu/%02hu/%02hu %02hu:%02hu:%02hu.%03hu [%i]: ",
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wYear,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond,
    SystemTime.wMilliseconds,
    CurrentProcessId);
  SString::Append((SString *)&v8, (unsigned __int16 *)this);
  SString::ConvertToUnicode((SString *)&v8);
  CircularLog::Log(v4, (const unsigned __int16 *)lpMem);
  if ( (v9 & 0x800000000LL) != 0 )
  {
    v5 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v5);
    }
  }
}

```

## disassembly

```asm
0x18002de54  mov     [rsp-8+arg_8], rbx
0x18002de59  mov     [rsp-8+arg_10], rsi
0x18002de5e  push    rbp
0x18002de5f  push    rdi
0x18002de60  push    r14
0x18002de62  lea     rbp, [rsp-190h]
0x18002de6a  sub     rsp, 290h
0x18002de71  mov     rax, cs:__security_cookie
0x18002de78  xor     rax, rsp
0x18002de7b  mov     [rbp+1A0h+var_20], rax
0x18002de82  mov     rsi, rcx
0x18002de85  call    ?DebugLogWorker@NGENService@@YAXPEBG@Z
0x18002de8a  xor     r14d, r14d
0x18002de8d  mov     [rsp+2A0h+var_240], r14
0x18002de92  mov     [rsp+2A0h+var_240+4], 200h
0x18002de9b  mov     [rsp+2A0h+lpMem], r14
0x18002dea0  lea     rax, [rsp+2A0h+var_228]
0x18002dea5  mov     [rsp+2A0h+lpMem], rax
0x18002deaa  mov     dword ptr [rsp+2A0h+var_240], 2
0x18002deb2  mov     rax, [rsp+2A0h+lpMem]
0x18002deb7  mov     [rax], r14w
0x18002debb  lea     rcx, [rsp+2A0h+SystemTime]; lpSystemTime
0x18002dec0  call    cs:__imp_GetLocalTime
0x18002dec6  call    cs:__imp_GetCurrentProcessId
0x18002decc  movzx   ecx, [rsp+2A0h+SystemTime.wMilliseconds]
0x18002ded1  movzx   r10d, [rsp+2A0h+SystemTime.wSecond]
0x18002ded7  movzx   r11d, [rsp+2A0h+SystemTime.wMinute]
0x18002dedd  movzx   ebx, [rsp+2A0h+SystemTime.wHour]
0x18002dee2  movzx   edi, [rsp+2A0h+SystemTime.wYear]
0x18002dee7  movzx   r9d, [rsp+2A0h+SystemTime.wDay]
0x18002deed  movzx   r8d, [rsp+2A0h+SystemTime.wMonth]
0x18002def3  mov     [rsp+2A0h+var_258], eax
0x18002def7  mov     [rsp+2A0h+var_260], ecx
0x18002defb  mov     [rsp+2A0h+var_268], r10d
0x18002df00  mov     [rsp+2A0h+var_270], r11d
0x18002df05  mov     [rsp+2A0h+var_278], ebx
0x18002df09  mov     [rsp+2A0h+var_280], edi
0x18002df0d  lea     rdx, a02hu02hu02hu02
0x18002df14  lea     rcx, [rsp+2A0h+var_240]; this
0x18002df19  call    ?Printf@SString@@QEAAXPEBDZZ
0x18002df1e  mov     rdx, rsi; unsigned __int16 *
0x18002df21  lea     rcx, [rsp+2A0h+var_240]; this
0x18002df26  call    ?Append@SString@@QEAAXPEBG@Z
0x18002df2b  lea     rcx, [rsp+2A0h+var_240]; this
0x18002df30  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18002df35  mov     rdx, [rsp+2A0h+lpMem]; unsigned __int16 *
0x18002df3a  call    ?Log@CircularLog@@QEAAXPEBG@Z
0x18002df3f  nop
0x18002df40  test    [rsp+2A0h+var_238], 8
0x18002df45  jz      short loc_18002DF78
0x18002df47  mov     rbx, [rsp+2A0h+lpMem]
0x18002df4c  test    rbx, rbx
0x18002df4f  jz      short loc_18002DF78
0x18002df51  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x18002df58  test    rax, rax
0x18002df5b  jnz     short loc_18002DF6A
0x18002df5d  call    cs:__imp_GetProcessHeap
0x18002df63  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x18002df6a  mov     r8, rbx; lpMem
0x18002df6d  xor     edx, edx; dwFlags
0x18002df6f  mov     rcx, rax; hHeap
0x18002df72  call    cs:__imp_HeapFree
0x18002df78  mov     rcx, [rbp+1A0h+var_20]
0x18002df7f  xor     rcx, rsp; StackCookie
0x18002df82  call    __security_check_cookie
0x18002df87  lea     r11, [rsp+2A0h+var_10]
0x18002df8f  mov     rbx, [r11+28h]
0x18002df93  mov     rsi, [r11+30h]
0x18002df97  mov     rsp, r11
0x18002df9a  pop     r14
0x18002df9c  pop     rdi
0x18002df9d  pop     rbp
0x18002df9e  retn
```
