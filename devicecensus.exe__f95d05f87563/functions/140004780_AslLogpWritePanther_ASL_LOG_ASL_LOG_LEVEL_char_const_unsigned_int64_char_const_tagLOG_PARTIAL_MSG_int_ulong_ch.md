# AslLogpWritePanther(_ASL_LOG *,ASL_LOG_LEVEL,char const *,unsigned __int64,char const *,tagLOG_PARTIAL_MSG * (*)(int,ulong,char const *,...),tagLOGRESULT (*)(void *,ulong,char const *,char const *,ulong,char const *,char const *,void *,ulong,void *,uint))

- ea: `0x140004780`
- end: `0x140004885`
- name: `?AslLogpWritePanther@@YAXPEAU_ASL_LOG@@W4ASL_LOG_LEVEL@@PEBD_K2P6APEAUtagLOG_PARTIAL_MSG@@HK2ZZP6A?AW4tagLOGRESULT@@PEAXK22K225K5I@Z@Z`
- size: `261`
- prototype: `__int64 __fastcall(const char **, int, __int64, int, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400050a0`

## callees

- `0x140004a5c`
- `0x1400115f0`
- `0x140012010`

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

  v7 = (__int64 (__fastcall *)(__int64, __int64, const char *, _QWORD, int, __int64, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))qword_14001C900;
  v8 = (__int64 (__fastcall *)(__int64, __int64, const char *, char *))qword_14001C8E8;
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
0x140004780  mov     [rsp+arg_8], rbx
0x140004785  push    rbp
0x140004786  push    rsi
0x140004787  push    rdi
0x140004788  push    r14
0x14000478a  push    r15
0x14000478c  sub     rsp, 470h
0x140004793  mov     rax, cs:__security_cookie
0x14000479a  xor     rax, rsp
0x14000479d  mov     [rsp+498h+var_38], rax
0x1400047a5  mov     rbx, [rsp+498h+arg_20]
0x1400047ad  mov     r15, r9
0x1400047b0  mov     r9, [rcx]
0x1400047b3  mov     r14, r8
0x1400047b6  mov     rbp, cs:qword_14001C900
0x1400047bd  lea     rcx, [rsp+498h+var_438]; char *
0x1400047c2  mov     rdi, cs:qword_14001C8E8
0x1400047c9  lea     r8, aHsHs; "%hs: %hs"
0x1400047d0  mov     esi, edx
0x1400047d2  mov     [rsp+498h+var_478], rbx
0x1400047d7  mov     edx, 400h; unsigned __int64
0x1400047dc  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1400047e1  test    eax, eax
0x1400047e3  lea     r9, [rsp+498h+var_438]
0x1400047e8  mov     ecx, 1
0x1400047ed  lea     r8, aHs; "%hs"
0x1400047f4  cmovs   r9, rbx
0x1400047f8  mov     edx, 2000000h
0x1400047fd  cmp     esi, ecx
0x1400047ff  mov     eax, 4000000h
0x140004804  cmovnz  edx, eax
0x140004807  mov     rax, rdi
0x14000480a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000480f  mov     [rsp+498h+var_448], 0
0x140004817  lea     r8, aD_0; "D"
0x14000481e  mov     [rsp+498h+var_450], 0
0x140004827  mov     rcx, rax
0x14000482a  mov     [rsp+498h+var_458], 0
0x140004832  xor     r9d, r9d
0x140004835  mov     [rsp+498h+var_460], 0
0x14000483e  mov     edx, 0A4000h
0x140004843  mov     [rsp+498h+var_468], 0
0x14000484c  mov     rax, rbp
0x14000484f  mov     [rsp+498h+var_470], r14
0x140004854  mov     dword ptr [rsp+498h+var_478], r15d
0x140004859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000485e  mov     rcx, [rsp+498h+var_38]
0x140004866  xor     rcx, rsp; StackCookie
0x140004869  call    __security_check_cookie
0x14000486e  mov     rbx, [rsp+498h+arg_8]
0x140004876  add     rsp, 470h
0x14000487d  pop     r15
0x14000487f  pop     r14
0x140004881  pop     rdi
0x140004882  pop     rsi
0x140004883  pop     rbp
0x140004884  retn
```
