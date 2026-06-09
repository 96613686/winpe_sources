# AslLogpWritePanther(_ASL_LOG *,ASL_LOG_LEVEL,char const *,unsigned __int64,char const *,tagLOG_PARTIAL_MSG * (*)(int,ulong,char const *,...),tagLOGRESULT (*)(void *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint))

- ea: `0x1800154e0`
- end: `0x1800155e5`
- name: `?AslLogpWritePanther@@YAXPEAU_ASL_LOG@@W4ASL_LOG_LEVEL@@PEBD_K2P6APEAUtagLOG_PARTIAL_MSG@@HK2ZZP6A?AW4tagLOGRESULT@@PEAXK22K225K5I@Z@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016880`

## callees

- `0x180015e60`
- `0x1800191f0`
- `0x18001a010`

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

  v7 = (__int64 (__fastcall *)(__int64, __int64, const char *, _QWORD, int, __int64, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))qword_1800268F0;
  v8 = (__int64 (__fastcall *)(__int64, __int64, const char *, char *))qword_1800268D8;
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
0x1800154e0  mov     [rsp+arg_8], rbx
0x1800154e5  push    rbp
0x1800154e6  push    rsi
0x1800154e7  push    rdi
0x1800154e8  push    r14
0x1800154ea  push    r15
0x1800154ec  sub     rsp, 470h
0x1800154f3  mov     rax, cs:__security_cookie
0x1800154fa  xor     rax, rsp
0x1800154fd  mov     [rsp+498h+var_38], rax
0x180015505  mov     rbx, [rsp+498h+arg_20]
0x18001550d  mov     r15, r9
0x180015510  mov     r9, [rcx]
0x180015513  mov     r14, r8
0x180015516  mov     rbp, cs:qword_1800268F0
0x18001551d  lea     rcx, [rsp+498h+var_438]; char *
0x180015522  mov     rdi, cs:qword_1800268D8
0x180015529  lea     r8, aHsHs; "%hs: %hs"
0x180015530  mov     esi, edx
0x180015532  mov     [rsp+498h+var_478], rbx
0x180015537  mov     edx, 400h; unsigned __int64
0x18001553c  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015541  test    eax, eax
0x180015543  lea     r9, [rsp+498h+var_438]
0x180015548  mov     ecx, 1
0x18001554d  lea     r8, aHs; "%hs"
0x180015554  cmovs   r9, rbx
0x180015558  mov     edx, 2000000h
0x18001555d  cmp     esi, ecx
0x18001555f  mov     eax, 4000000h
0x180015564  cmovnz  edx, eax
0x180015567  mov     rax, rdi
0x18001556a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001556f  mov     [rsp+498h+var_448], 0
0x180015577  lea     r8, aD_0; "D"
0x18001557e  mov     [rsp+498h+var_450], 0
0x180015587  mov     rcx, rax
0x18001558a  mov     [rsp+498h+var_458], 0
0x180015592  xor     r9d, r9d
0x180015595  mov     [rsp+498h+var_460], 0
0x18001559e  mov     edx, 0A4000h
0x1800155a3  mov     [rsp+498h+var_468], 0
0x1800155ac  mov     rax, rbp
0x1800155af  mov     [rsp+498h+var_470], r14
0x1800155b4  mov     dword ptr [rsp+498h+var_478], r15d
0x1800155b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155be  mov     rcx, [rsp+498h+var_38]
0x1800155c6  xor     rcx, rsp; StackCookie
0x1800155c9  call    __security_check_cookie
0x1800155ce  mov     rbx, [rsp+498h+arg_8]
0x1800155d6  add     rsp, 470h
0x1800155dd  pop     r15
0x1800155df  pop     r14
0x1800155e1  pop     rdi
0x1800155e2  pop     rsi
0x1800155e3  pop     rbp
0x1800155e4  retn
```
