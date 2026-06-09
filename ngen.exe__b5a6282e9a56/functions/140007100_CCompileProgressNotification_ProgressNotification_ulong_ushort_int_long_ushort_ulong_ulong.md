# CCompileProgressNotification::ProgressNotification(ulong,ushort *,int,long,ushort *,ulong,ulong)

- ea: `0x140007100`
- end: `0x140007234`
- name: `?ProgressNotification@CCompileProgressNotification@@UEAAJKPEAGHJ0KK@Z`
- size: `308`
- prototype: `__int64 __fastcall(CCompileProgressNotification *this, __int64, unsigned __int16 *, int, int, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140007100`
- `0x1400072ec`
- `0x14000b010`
- `0x14000bd40`
- `0x14000bf60`
- `0x140013200`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007205`
- `KERNEL32!HeapFree` at `0x140007205`
- `KERNEL32!GetProcessHeap` at `0x1400071f0`
- `KERNEL32!GetProcessHeap` at `0x1400071f0`

## string_xrefs

- `0x14000718c`: `    Compiling assembly %s ...\n`
- `0x140007185`: `    Finished compiling assembly %s ...\n`

## pseudocode

```c
__int64 __fastcall CCompileProgressNotification::ProgressNotification(
        CCompileProgressNotification *this,
        __int64 a2,
        unsigned __int16 *a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8)
{
  const unsigned __int16 *v11; // rdx
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  _BYTE v15[12]; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-D0h]
  __int16 v17; // [rsp+38h] [rbp-C8h] BYREF

  *(_QWORD *)&v15[4] = 512;
  lpMem = &v17;
  *(_DWORD *)v15 = 2;
  v17 = 0;
  if ( a8 )
    SString::Printf((SString *)v15, L"%d>");
  v11 = L"    Compiling assembly %s ...\n";
  if ( !a4 )
    v11 = L"    Finished compiling assembly %s ...\n";
  SString::AppendPrintf((SString *)v15, v11, a3);
  SString::ConvertToUnicode((SString *)v15);
  CCompileProgressNotification::LogWorker((__int64)this - 16, 3 - (a4 != 0), L"%s", lpMem, *(_QWORD *)v15);
  *((_DWORD *)this + 5) = 1;
  if ( (v15[8] & 8) != 0 )
  {
    v12 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140007100  mov     [rsp-8+arg_8], rbx
0x140007105  mov     [rsp-8+arg_18], rsi
0x14000710a  push    rbp
0x14000710b  push    rdi
0x14000710c  push    r14
0x14000710e  lea     rbp, [rsp-150h]
0x140007116  sub     rsp, 250h
0x14000711d  mov     rax, cs:__security_cookie
0x140007124  xor     rax, rsp
0x140007127  mov     [rbp+160h+var_20], rax
0x14000712e  mov     ebx, r9d
0x140007131  mov     rsi, r8
0x140007134  mov     rdi, rcx
0x140007137  xor     r14d, r14d
0x14000713a  mov     [rsp+260h+var_240], r14
0x14000713f  mov     [rsp+260h+var_240+4], 200h
0x140007148  mov     [rsp+260h+lpMem], r14
0x14000714d  lea     rax, [rsp+260h+var_228]
0x140007152  mov     [rsp+260h+lpMem], rax
0x140007157  mov     dword ptr [rsp+260h+var_240], 2
0x14000715f  mov     rax, [rsp+260h+lpMem]
0x140007164  mov     [rax], r14w
0x140007168  mov     r8d, [rbp+160h+arg_38]
0x14000716f  test    r8d, r8d
0x140007172  jz      short loc_140007185
0x140007174  lea     rdx, aD; "%d>"
0x14000717b  lea     rcx, [rsp+260h+var_240]; this
0x140007180  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x140007185  lea     rax, aFinishedCompil; "    Finished compiling assembly %s ..."...
0x14000718c  lea     rdx, aCompilingAssem; "    Compiling assembly %s ...\n"
0x140007193  test    ebx, ebx
0x140007195  cmovz   rdx, rax; unsigned __int16 *
0x140007199  mov     r8, rsi
0x14000719c  lea     rcx, [rsp+260h+var_240]; this
0x1400071a1  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x1400071a6  lea     rcx, [rsp+260h+var_240]; this
0x1400071ab  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1400071b0  neg     ebx
0x1400071b2  sbb     edx, edx
0x1400071b4  add     edx, 3
0x1400071b7  lea     rcx, [rdi-10h]
0x1400071bb  mov     r9, [rsp+260h+lpMem]
0x1400071c0  lea     r8, aS; "%s"
0x1400071c7  call    ?LogWorker@CCompileProgressNotification@@AEAAXW4CorSvcLogLevel@@PEAGZZ; CCompileProgressNotification::LogWorker(CorSvcLogLevel,ushort *,...)
0x1400071cc  mov     dword ptr [rdi+14h], 1
0x1400071d3  test    [rsp+260h+var_238], 8
0x1400071d8  jz      short loc_14000720B
0x1400071da  mov     rbx, [rsp+260h+lpMem]
0x1400071df  test    rbx, rbx
0x1400071e2  jz      short loc_14000720B
0x1400071e4  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400071eb  test    rax, rax
0x1400071ee  jnz     short loc_1400071FD
0x1400071f0  call    cs:__imp_GetProcessHeap
0x1400071f6  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400071fd  mov     r8, rbx; lpMem
0x140007200  xor     edx, edx; dwFlags
0x140007202  mov     rcx, rax; hHeap
0x140007205  call    cs:__imp_HeapFree
0x14000720b  xor     eax, eax
0x14000720d  mov     rcx, [rbp+160h+var_20]
0x140007214  xor     rcx, rsp; StackCookie
0x140007217  call    __security_check_cookie
0x14000721c  lea     r11, [rsp+260h+var_10]
0x140007224  mov     rbx, [r11+28h]
0x140007228  mov     rsi, [r11+38h]
0x14000722c  mov     rsp, r11
0x14000722f  pop     r14
0x140007231  pop     rdi
0x140007232  pop     rbp
0x140007233  retn
```
