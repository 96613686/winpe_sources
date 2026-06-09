# AppendRedirectionURLText

- ea: `0x18000c8b8`
- end: `0x18000ca06`
- name: `AppendRedirectionURLText`
- size: `334`
- prototype: `void __fastcall(CIsMicrosoftDllCache *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca0c`

## callees

- `0x180007014`
- `0x18000c8b8`
- `0x18000f6f4`
- `0x180017ee4`
- `0x1800210cc`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18000c97e`
- `msvcrt!_wcsupr` at `0x18000c995`
- `msvcrt!_wcsupr` at `0x18000c97e`
- `msvcrt!_wcsupr` at `0x18000c995`
- `msvcrt!wcsstr` at `0x18000c9a3`
- `msvcrt!wcsstr` at `0x18000c9a3`
- `KERNEL32!LocalFree` at `0x18000c9b1`
- `KERNEL32!LocalFree` at `0x18000c9d5`
- `KERNEL32!LocalFree` at `0x18000c9b1`
- `KERNEL32!LocalFree` at `0x18000c9d5`
- `KERNEL32!LocalAlloc` at `0x18000c955`
- `KERNEL32!LocalAlloc` at `0x18000c955`

## string_xrefs

- `0x18000c90f`: `http://www.microsoft.com/contentredirect.asp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppendRedirectionURLText(CIsMicrosoftDllCache *a1, const unsigned __int16 **a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned __int64 v5; // rsi
  unsigned __int16 *v6; // rbx
  int v7[4]; // [rsp+20h] [rbp-248h] BYREF
  wchar_t String[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( g_wszRedirectionTextToAppend )
  {
    v7[0] = 0;
    CIsMicrosoftDllCache::Fetch(a1, (WCHAR *)a1, v7);
    if ( v7[0] )
    {
      if ( !wcsistr(*a2, L"http://www.microsoft.com/contentredirect.asp") )
      {
        v3 = -1;
        v4 = -1;
        do
          ++v4;
        while ( *(&g_wszRedirectionTextToAppend + v4) );
        do
          ++v3;
        while ( (*a2)[v3] );
        v5 = v4 + v3 + 1;
        v6 = (unsigned __int16 *)LocalAlloc(0, 2 * v5);
        if ( v6 )
        {
          StringCchCopyW(String, 0x104u, &g_wszRedirectionURL);
          _wcsupr(String);
          StringCchCopyW(v6, v5, *a2);
          _wcsupr(v6);
          if ( wcsstr(v6, String) )
          {
            LocalFree(v6);
          }
          else
          {
            StringCchCopyW(v6, v5, *a2);
            StringCchCatW(v6, v5, &g_wszRedirectionTextToAppend);
            LocalFree((HLOCAL)*a2);
            *a2 = v6;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000c8b8  mov     [rsp+arg_10], rbx
0x18000c8bd  mov     [rsp+arg_18], rbp
0x18000c8c2  push    rsi
0x18000c8c3  push    rdi
0x18000c8c4  push    r14
0x18000c8c6  sub     rsp, 250h
0x18000c8cd  mov     rax, cs:__security_cookie
0x18000c8d4  xor     rax, rsp
0x18000c8d7  mov     [rsp+268h+var_28], rax
0x18000c8df  xor     ebp, ebp
0x18000c8e1  mov     rdi, rdx
0x18000c8e4  cmp     cs:?g_wszRedirectionTextToAppend@@3PAGA, bp; ushort near * g_wszRedirectionTextToAppend
0x18000c8eb  jz      loc_18000C9DE
0x18000c8f1  lea     r8, [rsp+268h+var_248]; int *
0x18000c8f6  mov     [rsp+268h+var_248], ebp
0x18000c8fa  mov     rdx, rcx; unsigned __int16 *
0x18000c8fd  call    ?Fetch@CIsMicrosoftDllCache@@QEAAJPEBGPEAH@Z; CIsMicrosoftDllCache::Fetch(ushort const *,int *)
0x18000c902  cmp     [rsp+268h+var_248], ebp
0x18000c906  jz      loc_18000C9DE
0x18000c90c  mov     rcx, [rdi]; unsigned __int16 *
0x18000c90f  lea     rdx, aHttpWwwMicroso; "http://www.microsoft.com/contentredirec"...
0x18000c916  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000c91b  test    rax, rax
0x18000c91e  jnz     loc_18000C9DE
0x18000c924  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c928  lea     r14, ?g_wszRedirectionTextToAppend@@3PAGA; ushort near * g_wszRedirectionTextToAppend
0x18000c92f  mov     rcx, rax
0x18000c932  inc     rcx
0x18000c935  cmp     [r14+rcx*2], bp
0x18000c93a  jnz     short loc_18000C932
0x18000c93c  mov     rdx, [rdi]
0x18000c93f  inc     rax
0x18000c942  cmp     [rdx+rax*2], bp
0x18000c946  jnz     short loc_18000C93F
0x18000c948  lea     rsi, [rax+1]
0x18000c94c  add     rsi, rcx
0x18000c94f  xor     ecx, ecx; uFlags
0x18000c951  lea     rdx, [rsi+rsi]; uBytes
0x18000c955  call    cs:__imp_LocalAlloc
0x18000c95b  mov     rbx, rax
0x18000c95e  test    rax, rax
0x18000c961  jz      short loc_18000C9DE
0x18000c963  lea     r8, ?g_wszRedirectionURL@@3PAGA; unsigned __int16 *
0x18000c96a  mov     edx, 104h; unsigned __int64
0x18000c96f  lea     rcx, [rsp+268h+String]; unsigned __int16 *
0x18000c974  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c979  lea     rcx, [rsp+268h+String]; String
0x18000c97e  call    cs:__imp__wcsupr
0x18000c984  mov     r8, [rdi]; unsigned __int16 *
0x18000c987  mov     rdx, rsi; unsigned __int64
0x18000c98a  mov     rcx, rbx; unsigned __int16 *
0x18000c98d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c992  mov     rcx, rbx; String
0x18000c995  call    cs:__imp__wcsupr
0x18000c99b  lea     rdx, [rsp+268h+String]; SubStr
0x18000c9a0  mov     rcx, rbx; Str
0x18000c9a3  call    cs:__imp_wcsstr
0x18000c9a9  mov     rcx, rbx; unsigned __int16 *
0x18000c9ac  test    rax, rax
0x18000c9af  jz      short loc_18000C9B9
0x18000c9b1  call    cs:__imp_LocalFree
0x18000c9b7  jmp     short loc_18000C9DE
0x18000c9b9  mov     r8, [rdi]; unsigned __int16 *
0x18000c9bc  mov     rdx, rsi; unsigned __int64
0x18000c9bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c9c4  mov     r8, r14; unsigned __int16 *
0x18000c9c7  mov     rdx, rsi; unsigned __int64
0x18000c9ca  mov     rcx, rbx; unsigned __int16 *
0x18000c9cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c9d2  mov     rcx, [rdi]; hMem
0x18000c9d5  call    cs:__imp_LocalFree
0x18000c9db  mov     [rdi], rbx
0x18000c9de  mov     rcx, [rsp+268h+var_28]
0x18000c9e6  xor     rcx, rsp; StackCookie
0x18000c9e9  call    __security_check_cookie
0x18000c9ee  lea     r11, [rsp+268h+var_18]
0x18000c9f6  mov     rbx, [r11+30h]
0x18000c9fa  mov     rbp, [r11+38h]
0x18000c9fe  mov     rsp, r11
0x18000ca01  pop     r14
0x18000ca03  pop     rdi
0x18000ca04  pop     rsi
0x18000ca05  retn
```
