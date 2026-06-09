# GetLocalPathFromCNRLink(_cnrlink const *,ushort *,ulong *)

- ea: `0x180001580`
- end: `0x18000165f`
- name: `?GetLocalPathFromCNRLink@@YAHPEBU_cnrlink@@PEAGPEAK@Z`
- size: `223`
- prototype: `__int64 __fastcall(const struct _cnrlink *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800014c0`

## callees

- `0x180001580`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800015ee`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800015ee`
- `ext-ms-win-shell-ntshrui-l1-1-0!GetLocalPathFromNetResourceW` at `0x180001617`
- `ext-ms-win-shell-ntshrui-l1-1-0!GetLocalPathFromNetResourceW` at `0x180001617`

## pseudocode

```c
__int64 __fastcall GetLocalPathFromCNRLink(const struct _cnrlink *a1, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v5; // esi
  const CHAR *v6; // r8
  WCHAR *v7; // rdi
  __int64 result; // rax
  _DWORD v9[4]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR WideCharStr[264]; // [rsp+40h] [rbp-248h] BYREF

  *a3 = 0;
  if ( (*((_BYTE *)a1 + 4) & 2) != 0 )
    v5 = *((_DWORD *)a1 + 4);
  else
    v5 = 0;
  v6 = (char *)a1 + *((unsigned int *)a1 + 2);
  if ( v6 == (char *)a1 + 20 )
  {
    v7 = WideCharStr;
    MultiByteToWideChar(0, 0, v6, -1, WideCharStr, 260);
  }
  else
  {
    v7 = (WCHAR *)((char *)a1 + *((unsigned int *)a1 + 5));
  }
  v9[0] = 0;
  result = GetLocalPathFromNetResourceW(v7, v5, a2, 260, v9);
  if ( (_DWORD)result )
  {
    if ( v9[0] )
      *a3 |= 1u;
  }
  return result;
}

```

## disassembly

```asm
0x180001580  push    rbx
0x180001582  push    rbp
0x180001583  push    rsi
0x180001584  push    rdi
0x180001585  push    r14
0x180001587  sub     rsp, 260h
0x18000158e  mov     rax, cs:__security_cookie
0x180001595  xor     rax, rsp
0x180001598  mov     [rsp+288h+var_38], rax
0x1800015a0  xor     r14d, r14d
0x1800015a3  mov     rbx, r8
0x1800015a6  mov     [r8], r14d
0x1800015a9  mov     rbp, rdx
0x1800015ac  test    byte ptr [rcx+4], 2
0x1800015b0  jz      loc_180001650
0x1800015b6  mov     esi, [rcx+10h]
0x1800015b9  mov     r8d, [rcx+8]
0x1800015bd  lea     rax, [rcx+14h]
0x1800015c1  add     r8, rcx; lpMultiByteStr
0x1800015c4  cmp     r8, rax
0x1800015c7  jnz     loc_180001658
0x1800015cd  lea     rax, [rsp+288h+WideCharStr]
0x1800015d2  mov     [rsp+288h+cchWideChar], 104h; cchWideChar
0x1800015da  xor     edx, edx; dwFlags
0x1800015dc  mov     [rsp+288h+lpWideCharStr], rax; lpWideCharStr
0x1800015e1  xor     ecx, ecx; CodePage
0x1800015e3  lea     rdi, [rsp+288h+WideCharStr]
0x1800015e8  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800015ee  call    cs:__imp_MultiByteToWideChar
0x1800015f5  nop     dword ptr [rax+rax+00h]
0x1800015fa  lea     rax, [rsp+288h+var_258]
0x1800015ff  mov     [rsp+288h+var_258], r14d
0x180001604  mov     r9d, 104h
0x18000160a  mov     [rsp+288h+lpWideCharStr], rax
0x18000160f  mov     r8, rbp
0x180001612  mov     edx, esi
0x180001614  mov     rcx, rdi
0x180001617  call    cs:__imp_GetLocalPathFromNetResourceW
0x18000161e  nop     dword ptr [rax+rax+00h]
0x180001623  test    eax, eax
0x180001625  jz      short loc_180001631
0x180001627  cmp     [rsp+288h+var_258], r14d
0x18000162c  jz      short loc_180001631
0x18000162e  or      dword ptr [rbx], 1
0x180001631  mov     rcx, [rsp+288h+var_38]
0x180001639  xor     rcx, rsp; StackCookie
0x18000163c  call    __security_check_cookie
0x180001641  add     rsp, 260h
0x180001648  pop     r14
0x18000164a  pop     rdi
0x18000164b  pop     rsi
0x18000164c  pop     rbp
0x18000164d  pop     rbx
0x18000164e  retn
0x180001650  mov     esi, r14d
0x180001653  jmp     loc_1800015B9
0x180001658  mov     edi, [rax]
0x18000165a  add     rdi, rcx
0x18000165d  jmp     short loc_1800015FA
```
