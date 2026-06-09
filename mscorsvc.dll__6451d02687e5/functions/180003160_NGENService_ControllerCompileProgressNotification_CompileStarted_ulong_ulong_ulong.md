# NGENService::ControllerCompileProgressNotification::CompileStarted(ulong,ulong,ulong)

- ea: `0x180003160`
- end: `0x180003263`
- name: `?CompileStarted@ControllerCompileProgressNotification@NGENService@@UEAAJKKK@Z`
- size: `259`
- prototype: `__int64 __fastcall(NGENService::ControllerCompileProgressNotification *this, unsigned int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003160`
- `0x18002e308`
- `0x180030d84`
- `0x180032654`
- `0x180032948`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003237`
- `KERNEL32!HeapFree` at `0x180003237`
- `KERNEL32!GetProcessHeap` at `0x180003222`
- `KERNEL32!GetProcessHeap` at `0x180003222`

## string_xrefs

- `0x1800031d8`: `Assemblies to compile: %i\n`

## pseudocode

```c
__int64 __fastcall NGENService::ControllerCompileProgressNotification::CompileStarted(
        NGENService::ControllerCompileProgressNotification *this,
        unsigned int a2,
        __int64 a3,
        unsigned int a4)
{
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+24h] [rbp-DCh]
  LPVOID lpMem; // [rsp+30h] [rbp-D0h]
  __int16 v11; // [rsp+38h] [rbp-C8h] BYREF

  v9 = 512;
  lpMem = &v11;
  v8 = 2;
  v11 = 0;
  if ( a4 )
    SString::Printf((SString *)&v8, L"%d>", a4);
  SString::AppendPrintf((SString *)&v8, L"Assemblies to compile: %i\n", a2);
  SString::ConvertToUnicode((SString *)&v8);
  NGENService::Log((NGENService *)L"%s", (const unsigned __int16 *)lpMem);
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
  return 0;
}

```

## disassembly

```asm
0x180003160  mov     [rsp-8+arg_0], rbx
0x180003165  mov     [rsp-8+arg_10], rdi
0x18000316a  push    rbp
0x18000316b  lea     rbp, [rsp-150h]
0x180003173  sub     rsp, 250h
0x18000317a  mov     rax, cs:__security_cookie
0x180003181  xor     rax, rsp
0x180003184  mov     [rbp+150h+var_10], rax
0x18000318b  mov     ebx, edx
0x18000318d  xor     edi, edi
0x18000318f  mov     [rsp+250h+var_230], rdi
0x180003194  mov     [rsp+250h+var_230+4], 200h
0x18000319d  mov     [rsp+250h+lpMem], rdi
0x1800031a2  lea     rax, [rsp+250h+var_218]
0x1800031a7  mov     [rsp+250h+lpMem], rax
0x1800031ac  mov     dword ptr [rsp+250h+var_230], 2
0x1800031b4  mov     rax, [rsp+250h+lpMem]
0x1800031b9  mov     [rax], di
0x1800031bc  test    r9d, r9d
0x1800031bf  jz      short loc_1800031D5
0x1800031c1  mov     r8d, r9d
0x1800031c4  lea     rdx, aD_0; "%d>"
0x1800031cb  lea     rcx, [rsp+250h+var_230]; this
0x1800031d0  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x1800031d5  mov     r8d, ebx
0x1800031d8  lea     rdx, aAssembliesToCo; "Assemblies to compile: %i\n"
0x1800031df  lea     rcx, [rsp+250h+var_230]; this
0x1800031e4  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x1800031e9  lea     rcx, [rsp+250h+var_230]; this
0x1800031ee  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800031f3  mov     rdx, [rsp+250h+lpMem]; unsigned __int16 *
0x1800031f8  lea     rcx, aS_7; "%s"
0x1800031ff  call    ?Log@NGENService@@YAXPEBGZZ; NGENService::Log(ushort const *,...)
0x180003204  nop
0x180003205  test    [rsp+250h+var_228], 8
0x18000320a  jz      short loc_18000323D
0x18000320c  mov     rbx, [rsp+250h+lpMem]
0x180003211  test    rbx, rbx
0x180003214  jz      short loc_18000323D
0x180003216  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000321d  test    rax, rax
0x180003220  jnz     short loc_18000322F
0x180003222  call    cs:__imp_GetProcessHeap
0x180003228  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000322f  mov     r8, rbx; lpMem
0x180003232  xor     edx, edx; dwFlags
0x180003234  mov     rcx, rax; hHeap
0x180003237  call    cs:__imp_HeapFree
0x18000323d  xor     eax, eax
0x18000323f  mov     rcx, [rbp+150h+var_10]
0x180003246  xor     rcx, rsp; StackCookie
0x180003249  call    __security_check_cookie
0x18000324e  lea     r11, [rsp+250h+var_s0]
0x180003256  mov     rbx, [r11+10h]
0x18000325a  mov     rdi, [r11+20h]
0x18000325e  mov     rsp, r11
0x180003261  pop     rbp
0x180003262  retn
```
