# CInetLogInformation::ReturnStringInfo(char const *,char *,ulong *)

- ea: `0x180003658`
- end: `0x1800036b3`
- name: `?ReturnStringInfo@CInetLogInformation@@AEAAPEADPEBDPEADPEAK@Z`
- size: `91`
- prototype: `char *__fastcall(CInetLogInformation *__hidden this, const char *, char *, unsigned int *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180003260`
- `0x180003280`
- `0x1800032f0`
- `0x180003310`
- `0x1800033c0`
- `0x180003500`
- `0x180003520`

## callees

- `0x180003658`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003698`

## pseudocode

```c
char *__fastcall CInetLogInformation::ReturnStringInfo(
        CInetLogInformation *this,
        const char *a2,
        char *a3,
        unsigned int *a4)
{
  __int64 v4; // rcx
  int v6; // eax
  DWORD v7; // ecx
  char *result; // rax
  char *v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = a3;
  v4 = *((_QWORD *)this + 8);
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, const char *, char **))(*(_QWORD *)v4 + 120LL))(v4, a2, &v9);
  v7 = v6;
  if ( v6 >= 0 )
    return v9;
  if ( (v6 & 0x1FFF0000) == 0x70000 )
    v7 = (unsigned __int16)v6;
  SetLastError(v7);
  result = 0;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x180003658  mov     [rsp+arg_10], r8
0x18000365d  push    rbx
0x18000365e  sub     rsp, 30h
0x180003662  mov     rcx, [rcx+40h]
0x180003666  lea     r8, [rsp+38h+arg_10]
0x18000366b  mov     [rsp+38h+arg_10], 0
0x180003674  mov     rbx, r9
0x180003677  mov     rax, [rcx]
0x18000367a  mov     rax, [rax+78h]
0x18000367e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003683  mov     ecx, eax
0x180003685  test    eax, eax
0x180003687  jns     short loc_1800036A8
0x180003689  and     eax, 1FFF0000h
0x18000368e  cmp     eax, 70000h
0x180003693  jnz     short loc_180003698
0x180003695  movzx   ecx, cx; dwErrCode
0x180003698  call    cs:__imp_SetLastError
0x18000369e  xor     eax, eax
0x1800036a0  mov     dword ptr [rbx], 0
0x1800036a6  jmp     short loc_1800036AD
0x1800036a8  mov     rax, [rsp+38h+arg_10]
0x1800036ad  add     rsp, 30h
0x1800036b1  pop     rbx
0x1800036b2  retn
```
