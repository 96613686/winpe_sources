# PerflibCheckPerfFile

- ea: `0x180011180`
- end: `0x1800113aa`
- name: `PerflibCheckPerfFile`
- size: `554`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180010430`

## callees

- `0x180005da0`
- `0x180007740`
- `0x180008042`
- `0x180008050`
- `0x1800102c0`
- `0x180010328`
- `0x180011180`
- `0x1800113b0`
- `0x180011738`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800111ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011214`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800111ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011214`

## pseudocode

```c
__int64 __fastcall PerflibCheckPerfFile(unsigned __int16 *a1)
{
  UINT SystemDirectoryW; // eax
  __int64 v3; // rbp
  __int64 v4; // rsi
  __int64 CounterFile; // r14
  int v6; // eax
  unsigned __int64 v7; // r15
  WCHAR *v8; // rax
  WCHAR *v9; // rbx
  unsigned __int16 *v10; // rbp
  unsigned int LangIdFromSzLang; // eax
  unsigned __int16 v13[4]; // [rsp+40h] [rbp-58h] BYREF
  __int16 v14; // [rsp+48h] [rbp-50h]

  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v3 = SystemDirectoryW;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  CounterFile = 0;
  if ( !SystemDirectoryW )
  {
    v9 = 0;
    goto LABEL_16;
  }
  v6 = v4 + 9;
  if ( (unsigned int)(v4 + 9) < 0xD )
    v6 = 13;
  v7 = (unsigned int)(v6 + v3 + 1);
  v8 = (WCHAR *)operator new(saturated_mul((unsigned int)(v7 + v3 + 1), 2u));
  v9 = v8;
  if ( v8 && GetSystemDirectoryW(v8, v3 + 1) )
  {
    v10 = &v9[v3 + 1];
    if ( (_DWORD)v4 != 4 )
    {
      StringCchPrintfW(v10, (unsigned int)v7, L"%ws\\%ws%ws%ws", v9, L"perfc", a1, L".dat");
      CounterFile = PerflibFindCounterFile(v10);
      if ( CounterFile )
        goto LABEL_16;
      memset_0(v10, 0, 2 * v7);
      StringCchPrintfW(v10, v7, L"%ws\\%ws??%ws%ws", v9, L"prfc", a1 + 1, L".dat");
      goto LABEL_12;
    }
    StringCchPrintfW(v10, (unsigned int)v7, L"%ws\\%ws%ws%ws", v9, L"prfc", a1, L".dat");
    CounterFile = PerflibFindCounterFile(v10);
    if ( !CounterFile )
    {
      LangIdFromSzLang = GetLangIdFromSzLang(a1);
      if ( LangIdFromSzLang )
      {
        *(_QWORD *)v13 = 0;
        v14 = 0;
        PerfGetLangId(LangIdFromSzLang & 0x3FF, 1u, v13, 5u);
        memset_0(v10, 0, 2 * v7);
        StringCchPrintfW(v10, (unsigned int)v7, L"%ws\\%ws%ws%ws", v9, L"perfc", v13, L".dat");
LABEL_12:
        CounterFile = PerflibFindCounterFile(v10);
      }
    }
  }
LABEL_16:
  operator delete(v9);
  return CounterFile;
}

```

## disassembly

```asm
0x180011180  mov     [rsp+arg_10], rbx
0x180011185  push    rbp
0x180011186  push    rsi
0x180011187  push    rdi
0x180011188  push    r12
0x18001118a  push    r13
0x18001118c  push    r14
0x18001118e  push    r15
0x180011190  sub     rsp, 60h
0x180011194  mov     rax, cs:__security_cookie
0x18001119b  xor     rax, rsp
0x18001119e  mov     [rsp+98h+var_48], rax
0x1800111a3  mov     r12, rdx
0x1800111a6  mov     rdi, rcx
0x1800111a9  xor     edx, edx; uSize
0x1800111ab  xor     ecx, ecx; lpBuffer
0x1800111ad  call    cs:__imp_GetSystemDirectoryW
0x1800111b3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800111b7  mov     ebp, eax
0x1800111b9  mov     rsi, r8
0x1800111bc  xor     r13d, r13d
0x1800111bf  inc     rsi
0x1800111c2  cmp     [rdi+rsi*2], r13w
0x1800111c7  jnz     short loc_1800111BF
0x1800111c9  mov     r14, r13
0x1800111cc  test    eax, eax
0x1800111ce  jz      loc_180011377
0x1800111d4  mov     ecx, 0Dh
0x1800111d9  lea     eax, [rsi+9]
0x1800111dc  cmp     eax, ecx
0x1800111de  lea     r15d, [rbp+1]
0x1800111e2  cmovb   eax, ecx
0x1800111e5  lea     ecx, [rbp+1]
0x1800111e8  add     r15d, eax
0x1800111eb  mov     eax, 2
0x1800111f0  add     ecx, r15d
0x1800111f3  mul     rcx
0x1800111f6  cmovb   rax, r8
0x1800111fa  mov     rcx, rax
0x1800111fd  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180011202  mov     rbx, rax
0x180011205  test    rax, rax
0x180011208  jz      loc_18001137A
0x18001120e  lea     edx, [rbp+1]; uSize
0x180011211  mov     rcx, rax; lpBuffer
0x180011214  call    cs:__imp_GetSystemDirectoryW
0x18001121a  test    eax, eax
0x18001121c  jz      loc_18001137A
0x180011222  inc     rbp
0x180011225  lea     r8, aWsWsWsWs; "%ws\\%ws%ws%ws"
0x18001122c  cmp     esi, 4
0x18001122f  mov     r9, rbx
0x180011232  lea     rsi, aDat; ".dat"
0x180011239  mov     edx, r15d; unsigned __int64
0x18001123c  mov     [rsp+98h+var_68], rsi
0x180011241  lea     rbp, [rbx+rbp*2]
0x180011245  mov     [rsp+98h+var_70], rdi
0x18001124a  mov     rcx, rbp; unsigned __int16 *
0x18001124d  jnz     loc_18001130A
0x180011253  lea     rax, aPrfc; "prfc"
0x18001125a  mov     [rsp+98h+var_78], rax
0x18001125f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011264  mov     r9, r12
0x180011267  mov     r8, rdi
0x18001126a  xor     edx, edx
0x18001126c  mov     rcx, rbp; lpFileName
0x18001126f  call    PerflibFindCounterFile
0x180011274  mov     r14, rax
0x180011277  test    rax, rax
0x18001127a  jnz     loc_18001137A
0x180011280  mov     rcx, rdi; unsigned __int16 *
0x180011283  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180011288  test    eax, eax
0x18001128a  jz      loc_18001137A
0x180011290  xor     ecx, ecx
0x180011292  lea     r9d, [r14+5]; unsigned int
0x180011296  mov     qword ptr [rsp+98h+var_58], rcx
0x18001129b  lea     r8, [rsp+98h+var_58]; unsigned __int16 *
0x1800112a0  mov     [rsp+98h+var_50], cx
0x1800112a5  mov     dl, 1; unsigned __int8
0x1800112a7  movzx   ecx, ax
0x1800112aa  and     ecx, 3FFh; unsigned int
0x1800112b0  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x1800112b5  xor     edx, edx; Val
0x1800112b7  lea     r8, [r15+r15]; Size
0x1800112bb  mov     rcx, rbp; void *
0x1800112be  call    memset_0
0x1800112c3  lea     rax, [rsp+98h+var_58]
0x1800112c8  mov     [rsp+98h+var_68], rsi
0x1800112cd  mov     [rsp+98h+var_70], rax
0x1800112d2  lea     r8, aWsWsWsWs; "%ws\\%ws%ws%ws"
0x1800112d9  lea     rax, aPerfc; "perfc"
0x1800112e0  mov     r9, rbx
0x1800112e3  mov     edx, r15d; unsigned __int64
0x1800112e6  mov     [rsp+98h+var_78], rax
0x1800112eb  mov     rcx, rbp; unsigned __int16 *
0x1800112ee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800112f3  lea     r8, [rsp+98h+var_58]
0x1800112f8  xor     edx, edx
0x1800112fa  mov     r9, r12
0x1800112fd  mov     rcx, rbp; lpFileName
0x180011300  call    PerflibFindCounterFile
0x180011305  mov     r14, rax
0x180011308  jmp     short loc_18001137A
0x18001130a  lea     rax, aPerfc; "perfc"
0x180011311  mov     [rsp+98h+var_78], rax
0x180011316  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001131b  mov     r9, r12
0x18001131e  mov     r8, rdi
0x180011321  xor     edx, edx
0x180011323  mov     rcx, rbp; lpFileName
0x180011326  call    PerflibFindCounterFile
0x18001132b  mov     r14, rax
0x18001132e  test    rax, rax
0x180011331  jnz     short loc_18001137A
0x180011333  lea     r8, [r15+r15]; Size
0x180011337  xor     edx, edx; Val
0x180011339  mov     rcx, rbp; void *
0x18001133c  call    memset_0
0x180011341  lea     rax, [rdi+2]
0x180011345  mov     [rsp+98h+var_68], rsi
0x18001134a  mov     [rsp+98h+var_70], rax
0x18001134f  lea     r8, aWsWsWsWs_0; "%ws\\%ws??%ws%ws"
0x180011356  lea     rax, aPrfc; "prfc"
0x18001135d  mov     r9, rbx
0x180011360  mov     rdx, r15; unsigned __int64
0x180011363  mov     [rsp+98h+var_78], rax
0x180011368  mov     rcx, rbp; unsigned __int16 *
0x18001136b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011370  mov     r8, rdi
0x180011373  mov     dl, 1
0x180011375  jmp     short loc_1800112FA
0x180011377  mov     rbx, r13
0x18001137a  mov     rcx, rbx; Block
0x18001137d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011382  mov     rax, r14
0x180011385  mov     rcx, [rsp+98h+var_48]
0x18001138a  xor     rcx, rsp; StackCookie
0x18001138d  call    __security_check_cookie
0x180011392  mov     rbx, [rsp+98h+arg_10]
0x18001139a  add     rsp, 60h
0x18001139e  pop     r15
0x1800113a0  pop     r14
0x1800113a2  pop     r13
0x1800113a4  pop     r12
0x1800113a6  pop     rdi
0x1800113a7  pop     rsi
0x1800113a8  pop     rbp
0x1800113a9  retn
```
