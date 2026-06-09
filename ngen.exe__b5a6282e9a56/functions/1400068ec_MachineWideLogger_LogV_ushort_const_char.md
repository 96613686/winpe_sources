# MachineWideLogger::LogV(ushort const *,char *)

- ea: `0x1400068ec`
- end: `0x140006a35`
- name: `?LogV@MachineWideLogger@@QEAAXPEBGPEAD@Z`
- size: `329`
- prototype: `void __fastcall(MachineWideLogger *__hidden this, const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140006a38`
- `0x1400072ec`

## callees

- `0x1400068ec`
- `0x14000b010`
- `0x14000bb2c`
- `0x14000bf84`
- `0x140010938`
- `0x140013200`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000695c`
- `KERNEL32!GetCurrentProcessId` at `0x14000695c`
- `KERNEL32!GetLocalTime` at `0x140006925`
- `KERNEL32!GetLocalTime` at `0x140006925`
- `KERNEL32!HeapFree` at `0x140006a0e`
- `KERNEL32!HeapFree` at `0x140006a0e`
- `KERNEL32!GetProcessHeap` at `0x1400069f9`
- `KERNEL32!GetProcessHeap` at `0x1400069f9`

## pseudocode

```c
void __fastcall MachineWideLogger::LogV(MachineWideLogger *this, const unsigned __int16 *a2, char *a3)
{
  DWORD CurrentProcessId; // eax
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  int v10; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v11; // [rsp+64h] [rbp-9Ch]
  LPVOID lpMem; // [rsp+70h] [rbp-90h]
  __int16 v13; // [rsp+78h] [rbp-88h] BYREF

  GetLocalTime(&SystemTime);
  v11 = 512;
  lpMem = &v13;
  v10 = 2;
  v13 = 0;
  CurrentProcessId = GetCurrentProcessId();
  SString::Printf(
    (SString *)&v10,
    "%02hu/%02hu/%02hu %02hu:%02hu:%02hu.%03hu [%i]: ",
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wYear,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond,
    SystemTime.wMilliseconds,
    CurrentProcessId);
  SString::AppendVPrintf((SString *)&v10, a2, a3);
  SString::ConvertToUnicode((SString *)&v10);
  CircularLog::Log(this, (const unsigned __int16 *)lpMem);
  if ( (v11 & 0x800000000LL) != 0 )
  {
    v7 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v7);
    }
  }
}

```

## disassembly

```asm
0x1400068ec  push    rbp
0x1400068ee  push    rbx
0x1400068ef  push    rsi
0x1400068f0  push    rdi
0x1400068f1  push    r12
0x1400068f3  push    r14
0x1400068f5  push    r15
0x1400068f7  lea     rbp, [rsp-190h]
0x1400068ff  sub     rsp, 290h
0x140006906  mov     rax, cs:__security_cookie
0x14000690d  xor     rax, rsp
0x140006910  mov     [rbp+1C0h+var_40], rax
0x140006917  mov     r14, r8
0x14000691a  mov     rsi, rdx
0x14000691d  mov     r15, rcx
0x140006920  lea     rcx, [rsp+2C0h+SystemTime]; lpSystemTime
0x140006925  call    cs:__imp_GetLocalTime
0x14000692b  xor     r12d, r12d
0x14000692e  mov     [rsp+2C0h+var_260], r12
0x140006933  mov     [rsp+2C0h+var_260+4], 200h
0x14000693c  mov     [rsp+2C0h+lpMem], r12
0x140006941  lea     rax, [rsp+2C0h+var_248]
0x140006946  mov     [rsp+2C0h+lpMem], rax
0x14000694b  mov     dword ptr [rsp+2C0h+var_260], 2
0x140006953  mov     rax, [rsp+2C0h+lpMem]
0x140006958  mov     [rax], r12w
0x14000695c  call    cs:__imp_GetCurrentProcessId
0x140006962  movzx   ecx, [rsp+2C0h+SystemTime.wMilliseconds]
0x140006967  movzx   r10d, [rsp+2C0h+SystemTime.wSecond]
0x14000696d  movzx   r11d, [rsp+2C0h+SystemTime.wMinute]
0x140006973  movzx   ebx, [rsp+2C0h+SystemTime.wHour]
0x140006978  movzx   edi, [rsp+2C0h+SystemTime.wYear]
0x14000697d  movzx   r9d, [rsp+2C0h+SystemTime.wDay]
0x140006983  movzx   r8d, [rsp+2C0h+SystemTime.wMonth]
0x140006989  mov     [rsp+2C0h+var_278], eax
0x14000698d  mov     [rsp+2C0h+var_280], ecx
0x140006991  mov     [rsp+2C0h+var_288], r10d
0x140006996  mov     [rsp+2C0h+var_290], r11d
0x14000699b  mov     [rsp+2C0h+var_298], ebx
0x14000699f  mov     [rsp+2C0h+var_2A0], edi
0x1400069a3  lea     rdx, a02hu02hu02hu02; "%02hu/%02hu/%02hu %02hu:%02hu:%02hu.%03"...
0x1400069aa  lea     rcx, [rsp+2C0h+var_260]; this
0x1400069af  call    ?Printf@SString@@QEAAXPEBDZZ; SString::Printf(char const *,...)
0x1400069b4  mov     r8, r14; char *
0x1400069b7  mov     rdx, rsi; unsigned __int16 *
0x1400069ba  lea     rcx, [rsp+2C0h+var_260]; this
0x1400069bf  call    ?AppendVPrintf@SString@@QEAAXPEBGPEAD@Z; SString::AppendVPrintf(ushort const *,char *)
0x1400069c4  lea     rcx, [rsp+2C0h+var_260]; this
0x1400069c9  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1400069ce  mov     rdx, [rsp+2C0h+lpMem]; unsigned __int16 *
0x1400069d3  mov     rcx, r15; this
0x1400069d6  call    ?Log@CircularLog@@QEAAXPEBG@Z; CircularLog::Log(ushort const *)
0x1400069db  nop
0x1400069dc  test    [rsp+2C0h+var_258], 8
0x1400069e1  jz      short loc_140006A14
0x1400069e3  mov     rbx, [rsp+2C0h+lpMem]
0x1400069e8  test    rbx, rbx
0x1400069eb  jz      short loc_140006A14
0x1400069ed  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400069f4  test    rax, rax
0x1400069f7  jnz     short loc_140006A06
0x1400069f9  call    cs:__imp_GetProcessHeap
0x1400069ff  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140006a06  mov     r8, rbx; lpMem
0x140006a09  xor     edx, edx; dwFlags
0x140006a0b  mov     rcx, rax; hHeap
0x140006a0e  call    cs:__imp_HeapFree
0x140006a14  mov     rcx, [rbp+1C0h+var_40]
0x140006a1b  xor     rcx, rsp; StackCookie
0x140006a1e  call    __security_check_cookie
0x140006a23  add     rsp, 290h
0x140006a2a  pop     r15
0x140006a2c  pop     r14
0x140006a2e  pop     r12
0x140006a30  pop     rdi
0x140006a31  pop     rsi
0x140006a32  pop     rbx
0x140006a33  pop     rbp
0x140006a34  retn
```
