# AslLogpWritePanther(_ASL_LOG *,ASL_LOG_LEVEL,char const *,unsigned __int64,char const *,tagLOG_PARTIAL_MSG * (*)(int,ulong,char const *,...),tagLOGRESULT (*)(void *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint))

- ea: `0x180008c40`
- end: `0x180008d45`
- name: `?AslLogpWritePanther@@YAXPEAU_ASL_LOG@@W4ASL_LOG_LEVEL@@PEBD_K2P6APEAUtagLOG_PARTIAL_MSG@@HK2ZZP6A?AW4tagLOGRESULT@@PEAXK22K225K5I@Z@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800092ac`

## callees

- `0x180008ea8`
- `0x18000c030`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall AslLogpWritePanther(const char **a1, int a2, __int64 a3, int a4, const char *a5)
{
  __int64 (__fastcall *v7)(__int64, __int64, const char *, _QWORD, int, __int64, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD); // rbp
  __int64 (__fastcall *v8)(__int64, __int64, const char *, char *); // rdi
  int v10; // eax
  char *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rax
  char v15[1024]; // [rsp+60h] [rbp-438h] BYREF

  v7 = (__int64 (__fastcall *)(__int64, __int64, const char *, _QWORD, int, __int64, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))WdsSetupLogMessageA;
  v8 = (__int64 (__fastcall *)(__int64, __int64, const char *, char *))qword_180014808;
  v10 = RtlStringCchPrintfA(v15, 0x400u, "%hs: %hs", *a1, a5);
  v11 = v15;
  if ( v10 < 0 )
    v11 = (char *)a5;
  v12 = 0x2000000;
  if ( a2 != 1 )
    v12 = 0x4000000;
  v13 = v8(1, v12, "%hs", v11);
  return v7(v13, 671744, "D", 0, a4, a3, 0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x180008c40  mov     [rsp+arg_8], rbx
0x180008c45  push    rbp
0x180008c46  push    rsi
0x180008c47  push    rdi
0x180008c48  push    r14
0x180008c4a  push    r15
0x180008c4c  sub     rsp, 470h
0x180008c53  mov     rax, cs:__security_cookie
0x180008c5a  xor     rax, rsp
0x180008c5d  mov     [rsp+498h+var_38], rax
0x180008c65  mov     rbx, [rsp+498h+arg_20]
0x180008c6d  mov     r15, r9
0x180008c70  mov     r9, [rcx]
0x180008c73  mov     r14, r8
0x180008c76  mov     rbp, cs:WdsSetupLogMessageA
0x180008c7d  lea     rcx, [rsp+498h+var_438]; char *
0x180008c82  mov     rdi, cs:qword_180014808
0x180008c89  lea     r8, aHsHs; "%hs: %hs"
0x180008c90  mov     esi, edx
0x180008c92  mov     [rsp+498h+var_478], rbx
0x180008c97  mov     edx, 400h; unsigned __int64
0x180008c9c  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008ca1  test    eax, eax
0x180008ca3  lea     r9, [rsp+498h+var_438]
0x180008ca8  mov     ecx, 1
0x180008cad  lea     r8, aHs; "%hs"
0x180008cb4  cmovs   r9, rbx
0x180008cb8  mov     edx, 2000000h
0x180008cbd  cmp     esi, ecx
0x180008cbf  mov     eax, 4000000h
0x180008cc4  cmovnz  edx, eax
0x180008cc7  mov     rax, rdi
0x180008cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ccf  mov     [rsp+498h+var_448], 0
0x180008cd7  lea     r8, aD_0; "D"
0x180008cde  mov     [rsp+498h+var_450], 0
0x180008ce7  mov     rcx, rax
0x180008cea  mov     [rsp+498h+var_458], 0
0x180008cf2  xor     r9d, r9d
0x180008cf5  mov     [rsp+498h+var_460], 0
0x180008cfe  mov     edx, 0A4000h
0x180008d03  mov     [rsp+498h+var_468], 0
0x180008d0c  mov     rax, rbp
0x180008d0f  mov     [rsp+498h+var_470], r14
0x180008d14  mov     dword ptr [rsp+498h+var_478], r15d
0x180008d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1e  mov     rcx, [rsp+498h+var_38]
0x180008d26  xor     rcx, rsp; StackCookie
0x180008d29  call    __security_check_cookie
0x180008d2e  mov     rbx, [rsp+498h+arg_8]
0x180008d36  add     rsp, 470h
0x180008d3d  pop     r15
0x180008d3f  pop     r14
0x180008d41  pop     rdi
0x180008d42  pop     rsi
0x180008d43  pop     rbp
0x180008d44  retn
```
