# CFontEnumAgents::Next(CFontAgent * *)

- ea: `0x180007f30`
- end: `0x180008028`
- name: `?Next@CFontEnumAgents@@UEAAJPEAPEAVCFontAgent@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(CFontEnumAgents *this, struct CFontAgent **)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d074`
- `0x18001d490`
- `0x18001d868`

## callees

- `0x180007154`
- `0x180007980`
- `0x180007f30`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180007fd5`
- `SHLWAPI!SHStrDupW` at `0x180007fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ffe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ffe`

## pseudocode

```c
__int64 __fastcall CFontEnumAgents::Next(CFontEnumAgents *this, struct CFontAgent **a2)
{
  __int64 v3; // rcx
  HRESULT v5; // ebx
  void *v6; // rcx
  HRESULT FontAgentFromPath; // eax
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  DWORD nLength; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR psz[264]; // [rsp+30h] [rbp-D0h] BYREF

  *a2 = 0;
  v3 = *((_QWORD *)this + 1);
  pv = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v3 + 24LL))(v3, &pv);
  if ( !v5 )
  {
    memset_0(psz, 0, 0x208u);
    if ( !*((_DWORD *)this + 4) )
    {
      nLength = 260;
      if ( (int)GetRemotePath((const unsigned __int16 *)pv, psz, &nLength) < 0 )
      {
        v5 = 0;
      }
      else
      {
        CoTaskMemFree(pv);
        v5 = SHStrDupW(psz, (LPWSTR *)&pv);
      }
    }
    v6 = pv;
    if ( pv )
    {
      if ( v5 >= 0 )
      {
        FontAgentFromPath = CreateFontAgentFromPath((const unsigned __int16 *)pv, a2);
        v6 = pv;
        v5 = FontAgentFromPath;
      }
      CoTaskMemFree(v6);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007f30  mov     [rsp-8+arg_10], rbx
0x180007f35  push    rbp
0x180007f36  push    rsi
0x180007f37  push    rdi
0x180007f38  lea     rbp, [rsp-150h]
0x180007f40  sub     rsp, 250h
0x180007f47  mov     rax, cs:__security_cookie
0x180007f4e  xor     rax, rsp
0x180007f51  mov     [rbp+160h+var_20], rax
0x180007f58  mov     qword ptr [rdx], 0
0x180007f5f  mov     rdi, rcx
0x180007f62  mov     rcx, [rcx+8]
0x180007f66  mov     rsi, rdx
0x180007f69  mov     [rsp+260h+pv], 0
0x180007f72  lea     rdx, [rsp+260h+pv]
0x180007f77  mov     rax, [rcx]
0x180007f7a  mov     rax, [rax+18h]
0x180007f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f83  mov     ebx, eax
0x180007f85  test    eax, eax
0x180007f87  jnz     short loc_180008004
0x180007f89  xor     edx, edx; Val
0x180007f8b  lea     rcx, [rsp+260h+psz]; void *
0x180007f90  mov     r8d, 208h; Size
0x180007f96  call    memset_0
0x180007f9b  cmp     [rdi+10h], ebx
0x180007f9e  jnz     short loc_180007FE1
0x180007fa0  mov     rcx, [rsp+260h+pv]; unsigned __int16 *
0x180007fa5  lea     r8, [rsp+260h+nLength]; lpnLength
0x180007faa  lea     rdx, [rsp+260h+psz]; unsigned __int16 *
0x180007faf  mov     [rsp+260h+nLength], 104h
0x180007fb7  call    ?GetRemotePath@@YAJPEBGPEAGPEAK@Z; GetRemotePath(ushort const *,ushort *,ulong *)
0x180007fbc  test    eax, eax
0x180007fbe  js      short loc_180007FDF
0x180007fc0  mov     rcx, [rsp+260h+pv]; pv
0x180007fc5  call    cs:__imp_CoTaskMemFree
0x180007fcb  lea     rdx, [rsp+260h+pv]; ppwsz
0x180007fd0  lea     rcx, [rsp+260h+psz]; psz
0x180007fd5  call    cs:__imp_SHStrDupW
0x180007fdb  mov     ebx, eax
0x180007fdd  jmp     short loc_180007FE1
0x180007fdf  xor     ebx, ebx
0x180007fe1  mov     rcx, [rsp+260h+pv]; unsigned __int16 *
0x180007fe6  test    rcx, rcx
0x180007fe9  jz      short loc_180008004
0x180007feb  test    ebx, ebx
0x180007fed  js      short loc_180007FFE
0x180007fef  mov     rdx, rsi; struct CFontAgent **
0x180007ff2  call    ?CreateFontAgentFromPath@@YAJPEBGPEAPEAVCFontAgent@@@Z; CreateFontAgentFromPath(ushort const *,CFontAgent * *)
0x180007ff7  mov     rcx, [rsp+260h+pv]; pv
0x180007ffc  mov     ebx, eax
0x180007ffe  call    cs:__imp_CoTaskMemFree
0x180008004  mov     eax, ebx
0x180008006  mov     rcx, [rbp+160h+var_20]
0x18000800d  xor     rcx, rsp; StackCookie
0x180008010  call    __security_check_cookie
0x180008015  mov     rbx, [rsp+260h+arg_10]
0x18000801d  add     rsp, 250h
0x180008024  pop     rdi
0x180008025  pop     rsi
0x180008026  pop     rbp
0x180008027  retn
```
