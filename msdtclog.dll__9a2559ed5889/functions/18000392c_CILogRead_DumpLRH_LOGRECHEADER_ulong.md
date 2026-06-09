# CILogRead::_DumpLRH(_LOGRECHEADER *,ulong *)

- ea: `0x18000392c`
- end: `0x180003a55`
- name: `?_DumpLRH@CILogRead@@AEAAPEADPEAU_LOGRECHEADER@@PEAK@Z`
- size: `297`
- prototype: `char *__fastcall(CILogRead *__hidden this, struct _LOGRECHEADER *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000341c`

## callees

- `0x18000130c`
- `0x180003358`
- `0x18000392c`

## pseudocode

```c
char *__fastcall CILogRead::_DumpLRH(CILogRead *this, struct _LOGRECHEADER *a2, unsigned int *a3)
{
  char *v5; // rsi
  int v6; // edi
  char *v7; // rbx
  unsigned int v8; // edi
  char *v9; // rbx
  char *v10; // rbx
  char *v11; // rax
  CILogRead *v13; // [rsp+50h] [rbp+8h] BYREF

  v13 = this;
  if ( !a2 )
    return 0;
  LODWORD(v13) = 0;
  v5 = (char *)operator new[](0x12Cu);
  if ( !v5 )
    return 0;
  TracedSafeStrPrintfA(
    v5,
    0x12Cu,
    (unsigned int *)&v13,
    "Log Record \n\tOffset \t\t: %.8X\n\tPrev. Offset \t: %.8X\n",
    *(_DWORD *)a2,
    *((_DWORD *)a2 + 1));
  v6 = 300 - (_DWORD)v13;
  v7 = &v5[(unsigned int)v13];
  TracedSafeStrPrintfA(
    v7,
    (unsigned int)(300 - (_DWORD)v13),
    (unsigned int *)&v13,
    "\tData Length \t: %.8X\n\tUser Type\t: %.4X\n",
    *((_DWORD *)a2 + 2),
    *((unsigned __int16 *)a2 + 6));
  v8 = v6 - (_DWORD)v13;
  v9 = &v7[(unsigned int)v13];
  TracedSafeStrPrintfA(
    v9,
    v8,
    (unsigned int *)&v13,
    "\tSystem Type \t: %.4X\n\tClient ID\t: %.8X\n",
    *((unsigned __int16 *)a2 + 7),
    *((_DWORD *)a2 + 4));
  v10 = &v9[(unsigned int)v13];
  TracedSafeStrPrintfA(
    v10,
    v8 - (unsigned int)v13,
    (unsigned int *)&v13,
    "\tNext Offset\t: %.8X\n**********************************\n",
    *((_DWORD *)a2 + 5));
  v11 = &v10[(unsigned int)v13];
  *v11 = 0;
  if ( a3 )
    *a3 = (_DWORD)v11 - (_DWORD)v5 + 1;
  return v5;
}

```

## disassembly

```asm
0x18000392c  mov     rax, rsp
0x18000392f  mov     [rax+10h], rbx
0x180003933  mov     [rax+18h], rsi
0x180003937  mov     [rax+8], rcx
0x18000393b  push    rdi
0x18000393c  push    r14
0x18000393e  push    r15
0x180003940  sub     rsp, 30h
0x180003944  mov     r15, r8
0x180003947  mov     r14, rdx
0x18000394a  test    rdx, rdx
0x18000394d  jz      loc_180003A3F
0x180003953  mov     edi, 12Ch
0x180003958  mov     dword ptr [rax+8], 0
0x18000395f  mov     ecx, edi; unsigned __int64
0x180003961  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003966  mov     rsi, rax
0x180003969  test    rax, rax
0x18000396c  jz      loc_180003A3F
0x180003972  mov     eax, [r14+4]
0x180003976  lea     r9, aLogRecordOffse; "Log Record \n\tOffset \t\t: %.8X\n\tPre"...
0x18000397d  mov     [rsp+48h+var_20], eax
0x180003981  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180003986  mov     eax, [r14]
0x180003989  mov     edx, edi; unsigned __int64
0x18000398b  mov     rcx, rsi; char *
0x18000398e  mov     [rsp+48h+var_28], eax
0x180003992  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003997  movzx   eax, word ptr [r14+0Ch]
0x18000399c  lea     r9, aDataLength8xUs; "\tData Length \t: %.8X\n\tUser Type\t: "...
0x1800039a3  mov     ebx, dword ptr [rsp+48h+arg_0]
0x1800039a7  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x1800039ac  sub     edi, dword ptr [rsp+48h+arg_0]
0x1800039b0  add     rbx, rsi
0x1800039b3  mov     [rsp+48h+var_20], eax
0x1800039b7  mov     rcx, rbx; char *
0x1800039ba  mov     eax, [r14+8]
0x1800039be  mov     edx, edi; unsigned __int64
0x1800039c0  mov     [rsp+48h+var_28], eax
0x1800039c4  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x1800039c9  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800039cd  lea     r9, aSystemType4xCl; "\tSystem Type \t: %.4X\n\tClient ID\t: "...
0x1800039d4  movzx   ecx, word ptr [r14+0Eh]
0x1800039d9  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x1800039de  sub     edi, dword ptr [rsp+48h+arg_0]
0x1800039e2  add     rbx, rax
0x1800039e5  mov     eax, [r14+10h]
0x1800039e9  mov     edx, edi; unsigned __int64
0x1800039eb  mov     [rsp+48h+var_20], eax
0x1800039ef  mov     [rsp+48h+var_28], ecx
0x1800039f3  mov     rcx, rbx; char *
0x1800039f6  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x1800039fb  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800039ff  lea     r9, aNextOffset8x; "\tNext Offset\t: %.8X\n****************"...
0x180003a06  sub     edi, dword ptr [rsp+48h+arg_0]
0x180003a0a  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180003a0f  add     rbx, rax
0x180003a12  mov     edx, edi; unsigned __int64
0x180003a14  mov     eax, [r14+14h]
0x180003a18  mov     rcx, rbx; char *
0x180003a1b  mov     [rsp+48h+var_28], eax
0x180003a1f  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003a24  mov     eax, dword ptr [rsp+48h+arg_0]
0x180003a28  add     rax, rbx
0x180003a2b  mov     byte ptr [rax], 0
0x180003a2e  test    r15, r15
0x180003a31  jz      short loc_180003A3A
0x180003a33  sub     eax, esi
0x180003a35  inc     eax
0x180003a37  mov     [r15], eax
0x180003a3a  mov     rax, rsi
0x180003a3d  jmp     short loc_180003A41
0x180003a3f  xor     eax, eax
0x180003a41  mov     rbx, [rsp+48h+arg_8]
0x180003a46  mov     rsi, [rsp+48h+arg_10]
0x180003a4b  add     rsp, 30h
0x180003a4f  pop     r15
0x180003a51  pop     r14
0x180003a53  pop     rdi
0x180003a54  retn
```
