# CInetLogInformation::GetComputerNameW(char *,ulong *)

- ea: `0x1800032a0`
- end: `0x1800032c7`
- name: `?GetComputerNameW@CInetLogInformation@@UEAAPEADPEADPEAK@Z`
- size: `39`
- prototype: `char *__fastcall(CInetLogInformation *__hidden this, char *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800032a0`
- `0x180003604`

## pseudocode

```c
char *__fastcall CInetLogInformation::GetComputerNameW(CInetLogInformation *this, char *a2, unsigned int *a3)
{
  __int64 v3; // rax

  v3 = -1;
  do
    ++v3;
  while ( g_pszComputerName[v3] );
  return CInetLogInformation::ReturnStringInfo(this, a2, a3, g_pszComputerName, v3);
}

```

## disassembly

```asm
0x1800032a0  sub     rsp, 38h
0x1800032a4  lea     r9, ?g_pszComputerName@@3PADA; char *
0x1800032ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800032af  inc     rax
0x1800032b2  cmp     byte ptr [r9+rax], 0
0x1800032b7  jnz     short loc_1800032AF
0x1800032b9  mov     [rsp+38h+var_18], eax; unsigned int
0x1800032bd  call    ?ReturnStringInfo@CInetLogInformation@@AEAAPEADPEADPEAKPEBDK@Z; CInetLogInformation::ReturnStringInfo(char *,ulong *,char const *,ulong)
0x1800032c2  add     rsp, 38h
0x1800032c6  retn
```
