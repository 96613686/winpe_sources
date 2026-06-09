# ResolveLocalPathFromServer(_ilinkinfoW const *,ushort *,ulong *)

- ea: `0x1800014c0`
- end: `0x18000156f`
- name: `?ResolveLocalPathFromServer@@YAHPEBU_ilinkinfoW@@PEAGPEAK@Z`
- size: `175`
- prototype: `__int64 __fastcall(const CHAR *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001780`

## callees

- `0x1800014c0`
- `0x180001580`
- `0x180001bd0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000152a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000152a`

## pseudocode

```c
__int64 __fastcall ResolveLocalPathFromServer(const CHAR *a1, unsigned __int16 *a2, unsigned int *a3)
{
  __int64 result; // rax
  unsigned int v6; // esi
  unsigned __int16 *v7; // rdi
  WCHAR WideCharStr[264]; // [rsp+30h] [rbp-238h] BYREF

  result = GetLocalPathFromCNRLink((const struct _cnrlink *)&a1[*((unsigned int *)a1 + 5)], a2, a3);
  v6 = result;
  if ( (_DWORD)result )
  {
    if ( *((_DWORD *)a1 + 1) == 28 )
    {
      v7 = WideCharStr;
      MultiByteToWideChar(0, 0, &a1[*((unsigned int *)a1 + 6)], -1, WideCharStr, 260);
    }
    else
    {
      v7 = (unsigned __int16 *)&a1[*((unsigned int *)a1 + 8)];
    }
    CatPath(a2, v7);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800014c0  push    rbx
0x1800014c2  push    rbp
0x1800014c3  push    rsi
0x1800014c4  sub     rsp, 250h
0x1800014cb  mov     rax, cs:__security_cookie
0x1800014d2  xor     rax, rsp
0x1800014d5  mov     [rsp+268h+var_28], rax
0x1800014dd  mov     rbx, rcx
0x1800014e0  mov     rbp, rdx
0x1800014e3  mov     ecx, [rcx+14h]
0x1800014e6  add     rcx, rbx; struct _cnrlink *
0x1800014e9  call    ?GetLocalPathFromCNRLink@@YAHPEBU_cnrlink@@PEAGPEAK@Z; GetLocalPathFromCNRLink(_cnrlink const *,ushort *,ulong *)
0x1800014ee  mov     esi, eax
0x1800014f0  test    eax, eax
0x1800014f2  jz      short loc_18000154B
0x1800014f4  cmp     dword ptr [rbx+4], 1Ch
0x1800014f8  mov     [rsp+268h+arg_18], rdi
0x180001500  jnz     short loc_180001567
0x180001502  mov     r8d, [rbx+18h]
0x180001506  lea     rax, [rsp+268h+WideCharStr]
0x18000150b  add     r8, rbx; lpMultiByteStr
0x18000150e  mov     [rsp+268h+cchWideChar], 104h; cchWideChar
0x180001516  xor     edx, edx; dwFlags
0x180001518  mov     [rsp+268h+lpWideCharStr], rax; lpWideCharStr
0x18000151d  xor     ecx, ecx; CodePage
0x18000151f  lea     rdi, [rsp+268h+WideCharStr]
0x180001524  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18000152a  call    cs:__imp_MultiByteToWideChar
0x180001531  nop     dword ptr [rax+rax+00h]
0x180001536  mov     rdx, rdi; unsigned __int16 *
0x180001539  mov     rcx, rbp; unsigned __int16 *
0x18000153c  call    ?CatPath@@YAJPEAGPEBGH@Z; CatPath(ushort *,ushort const *,int)
0x180001541  mov     rdi, [rsp+268h+arg_18]
0x180001549  mov     eax, esi
0x18000154b  mov     rcx, [rsp+268h+var_28]
0x180001553  xor     rcx, rsp; StackCookie
0x180001556  call    __security_check_cookie
0x18000155b  add     rsp, 250h
0x180001562  pop     rsi
0x180001563  pop     rbp
0x180001564  pop     rbx
0x180001565  retn
0x180001567  mov     edi, [rbx+20h]
0x18000156a  add     rdi, rbx
0x18000156d  jmp     short loc_180001536
```
