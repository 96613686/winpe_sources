# ResolveRemoteILinkInfo(_ilinkinfoW const *,ushort *,ulong,HWND__ *,ulong *)

- ea: `0x180005240`
- end: `0x180005354`
- name: `?ResolveRemoteILinkInfo@@YAHPEBU_ilinkinfoW@@PEAGKPEAUHWND__@@PEAK@Z`
- size: `276`
- prototype: `__int64 __fastcall(const CHAR *, unsigned __int16 *, char, HWND, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180001780`

## callees

- `0x180001bd0`
- `0x1800044f0`
- `0x1800048ec`
- `0x180005110`
- `0x180005240`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800052eb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800052eb`

## pseudocode

```c
__int64 __fastcall ResolveRemoteILinkInfo(const CHAR *a1, unsigned __int16 *a2, char a3, HWND a4, unsigned int *a5)
{
  DWORD v7; // edx
  unsigned int v8; // esi
  int v9; // r8d
  WCHAR *v10; // rdi
  int v11; // r8d
  unsigned int v13[4]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR WideCharStr[264]; // [rsp+40h] [rbp-248h] BYREF

  if ( (a3 & 1) != 0 )
  {
    v13[0] = 0;
    v7 = 2 * (a3 & 2);
    if ( (a3 & 4) != 0 )
      v7 |= 8u;
    if ( (a3 & 8) != 0 )
      v7 |= 0x80u;
    v8 = ConnectToCNR((const struct _cnrlink *)&a1[*((unsigned int *)a1 + 5)], v7, a4, a2, v13);
    if ( v8 )
    {
      if ( *((_DWORD *)a1 + 1) == 28 )
      {
        v10 = WideCharStr;
        MultiByteToWideChar(0, 0, &a1[*((unsigned int *)a1 + 6)], -1, WideCharStr, 260);
      }
      else
      {
        v10 = (WCHAR *)&a1[*((unsigned int *)a1 + 8)];
      }
      CatPath(a2, v10, v9);
      if ( (v13[0] & 0x40) != 0 )
        *a5 |= 2u;
    }
  }
  else
  {
    v8 = IsCNRAvailable((const struct _cnrlink *)&a1[*((unsigned int *)a1 + 5)]);
    if ( v8 )
      GetRemotePathFromILinkInfo((const struct _ilinkinfoW *)a1, a2, v11);
  }
  return v8;
}

```

## disassembly

```asm
0x180005240  push    rbx
0x180005242  push    rbp
0x180005243  push    rsi
0x180005244  push    rdi
0x180005245  push    r14
0x180005247  sub     rsp, 260h
0x18000524e  mov     rax, cs:__security_cookie
0x180005255  xor     rax, rsp
0x180005258  mov     [rsp+288h+var_38], rax
0x180005260  mov     rbp, [rsp+288h+arg_20]
0x180005268  mov     rax, r9
0x18000526b  mov     r14, rdx
0x18000526e  mov     rbx, rcx
0x180005271  test    r8b, 1
0x180005275  jz      loc_180005317
0x18000527b  mov     edx, r8d
0x18000527e  mov     [rsp+288h+var_258], 0
0x180005286  and     edx, 2
0x180005289  add     edx, edx
0x18000528b  test    r8b, 4
0x18000528f  jz      short loc_180005294
0x180005291  or      edx, 8
0x180005294  test    r8b, 8
0x180005298  jz      short loc_18000529E
0x18000529a  bts     edx, 7; dwFlags
0x18000529e  mov     ecx, [rcx+14h]
0x1800052a1  lea     r8, [rsp+288h+var_258]
0x1800052a6  mov     [rsp+288h+lpWideCharStr], r8; unsigned int *
0x1800052ab  add     rcx, rbx; struct _cnrlink *
0x1800052ae  mov     r8, rax; HWND
0x1800052b1  mov     r9, r14; unsigned __int16 *
0x1800052b4  call    ?ConnectToCNR@@YAHPEBU_cnrlink@@KPEAUHWND__@@PEAGPEAK@Z; ConnectToCNR(_cnrlink const *,ulong,HWND__ *,ushort *,ulong *)
0x1800052b9  mov     esi, eax
0x1800052bb  test    eax, eax
0x1800052bd  jz      short loc_180005333
0x1800052bf  cmp     dword ptr [rbx+4], 1Ch
0x1800052c3  jnz     short loc_1800052F9
0x1800052c5  mov     r8d, [rbx+18h]
0x1800052c9  lea     rax, [rsp+288h+WideCharStr]
0x1800052ce  add     r8, rbx; lpMultiByteStr
0x1800052d1  mov     [rsp+288h+cchWideChar], 104h; cchWideChar
0x1800052d9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800052dd  mov     [rsp+288h+lpWideCharStr], rax; lpWideCharStr
0x1800052e2  xor     edx, edx; dwFlags
0x1800052e4  lea     rdi, [rsp+288h+WideCharStr]
0x1800052e9  xor     ecx, ecx; CodePage
0x1800052eb  call    cs:__imp_MultiByteToWideChar
0x1800052f2  nop     dword ptr [rax+rax+00h]
0x1800052f7  jmp     short loc_1800052FF
0x1800052f9  mov     edi, [rbx+20h]
0x1800052fc  add     rdi, rbx
0x1800052ff  mov     rdx, rdi; unsigned __int16 *
0x180005302  mov     rcx, r14; unsigned __int16 *
0x180005305  call    ?CatPath@@YAJPEAGPEBGH@Z; CatPath(ushort *,ushort const *,int)
0x18000530a  test    byte ptr [rsp+288h+var_258], 40h
0x18000530f  jz      short loc_180005333
0x180005311  or      dword ptr [rbp+0], 2
0x180005315  jmp     short loc_180005333
0x180005317  mov     ecx, [rcx+14h]
0x18000531a  add     rcx, rbx; struct _cnrlink *
0x18000531d  call    ?IsCNRAvailable@@YAHPEBU_cnrlink@@@Z; IsCNRAvailable(_cnrlink const *)
0x180005322  mov     esi, eax
0x180005324  test    eax, eax
0x180005326  jz      short loc_180005333
0x180005328  mov     rdx, r14; unsigned __int16 *
0x18000532b  mov     rcx, rbx; struct _ilinkinfoW *
0x18000532e  call    ?GetRemotePathFromILinkInfo@@YAXPEBU_ilinkinfoW@@PEAGH@Z; GetRemotePathFromILinkInfo(_ilinkinfoW const *,ushort *,int)
0x180005333  mov     eax, esi
0x180005335  mov     rcx, [rsp+288h+var_38]
0x18000533d  xor     rcx, rsp; StackCookie
0x180005340  call    __security_check_cookie
0x180005345  add     rsp, 260h
0x18000534c  pop     r14
0x18000534e  pop     rdi
0x18000534f  pop     rsi
0x180005350  pop     rbp
0x180005351  pop     rbx
0x180005352  retn
```
