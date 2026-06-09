# CheckForAllowedVerb(REQUEST_FILTER_CONFIG *,IHttpContext *,int *)

- ea: `0x1800056b0`
- end: `0x18000580f`
- name: `?CheckForAllowedVerb@@YAJPEAVREQUEST_FILTER_CONFIG@@PEAVIHttpContext@@PEAH@Z`
- size: `351`
- prototype: `__int64 __fastcall(struct REQUEST_FILTER_CONFIG *, struct IHttpContext *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800010c0`

## callees

- `0x1800056b0`
- `0x180008010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180005700`
- `msvcrt!_stricmp` at `0x180005700`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180005714`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x1800057b2`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180005714`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x1800057b2`
- `iisutil!PuDbgPrint` at `0x180005751`
- `iisutil!PuDbgPrint` at `0x1800057f4`
- `iisutil!PuDbgPrint` at `0x180005751`
- `iisutil!PuDbgPrint` at `0x1800057f4`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x1800056ec`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180005779`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x1800056ec`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180005779`

## string_xrefs

- `0x18000574a`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\requestfiltering.cxx`
- `0x1800057ed`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\requestfiltering.cxx`

## pseudocode

```c
__int64 __fastcall CheckForAllowedVerb(struct REQUEST_FILTER_CONFIG *a1, struct IHttpContext *a2, int *a3)
{
  __int64 v5; // rax
  const char *v6; // r14
  const char *i; // rax
  const char *v8; // rsi
  const char *j; // rax
  const char *v10; // rcx
  int v11; // r9d
  int v12; // r8d

  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v6 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
  for ( i = MULTISZA::First((struct REQUEST_FILTER_CONFIG *)((char *)a1 + 224));
        ;
        i = MULTISZA::Next((struct REQUEST_FILTER_CONFIG *)((char *)a1 + 224), v8) )
  {
    v8 = i;
    if ( !i )
      break;
    if ( !_stricmp(i, v6) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\requestfiltering.cxx",
          1022,
          "CheckForAllowedVerb",
          "Found denied verb '%s'.\r\n",
          v6);
      *a3 = 1;
      return 0;
    }
  }
  if ( *((_DWORD *)a1 + 10) )
  {
LABEL_19:
    *a3 = 0;
  }
  else
  {
    *a3 = 1;
    for ( j = MULTISZA::First((struct REQUEST_FILTER_CONFIG *)((char *)a1 + 168));
          j;
          j = MULTISZA::Next((struct REQUEST_FILTER_CONFIG *)((char *)a1 + 168), j) )
    {
      v10 = j;
      do
      {
        v11 = (unsigned __int8)v10[v6 - j];
        v12 = *(unsigned __int8 *)v10 - v11;
        if ( v12 )
          break;
        ++v10;
      }
      while ( v11 );
      if ( !v12 )
        goto LABEL_19;
    }
    if ( *a3 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\requestfiltering.cxx",
        1075,
        "CheckForAllowedVerb",
        "Verb '%s' is not specifically allowed and will be rejected.\r\n",
        v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800056b0  push    rbx
0x1800056b2  push    rbp
0x1800056b3  push    rsi
0x1800056b4  push    rdi
0x1800056b5  push    r14
0x1800056b7  sub     rsp, 30h
0x1800056bb  mov     rax, [rdx]
0x1800056be  mov     rbx, rcx
0x1800056c1  mov     rcx, rdx
0x1800056c4  mov     rdi, r8
0x1800056c7  mov     rax, [rax+18h]
0x1800056cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d0  mov     rdx, rax
0x1800056d3  mov     rcx, [rax]
0x1800056d6  mov     rax, [rcx+40h]
0x1800056da  mov     rcx, rdx
0x1800056dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056e2  lea     rcx, [rbx+0E0h]
0x1800056e9  mov     r14, rax
0x1800056ec  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x1800056f2  mov     rsi, rax
0x1800056f5  test    rax, rax
0x1800056f8  jz      short loc_180005762
0x1800056fa  mov     rdx, r14; String2
0x1800056fd  mov     rcx, rax; String1
0x180005700  call    cs:__imp__stricmp
0x180005706  test    eax, eax
0x180005708  jz      short loc_18000571C
0x18000570a  mov     rdx, rsi
0x18000570d  lea     rcx, [rbx+0E0h]
0x180005714  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x18000571a  jmp     short loc_1800056F2
0x18000571c  test    byte ptr cs:g_dwDebugFlags, 3
0x180005723  jz      short loc_180005757
0x180005725  mov     rcx, cs:g_pDebug
0x18000572c  lea     rax, aFoundDeniedVer; "Found denied verb '%s'.\r\n"
0x180005733  mov     [rsp+58h+var_30], r14
0x180005738  lea     r9, aCheckforallowe_1; "CheckForAllowedVerb"
0x18000573f  mov     r8d, 3FEh
0x180005745  mov     [rsp+58h+var_38], rax
0x18000574a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005751  call    cs:__imp_PuDbgPrint
0x180005757  mov     dword ptr [rdi], 1
0x18000575d  jmp     loc_180005802
0x180005762  cmp     dword ptr [rbx+28h], 0
0x180005766  jnz     loc_1800057FC
0x18000576c  lea     rcx, [rbx+0A8h]
0x180005773  mov     dword ptr [rdi], 1
0x180005779  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x18000577f  test    rax, rax
0x180005782  jz      short loc_1800057BA
0x180005784  mov     rdx, r14
0x180005787  mov     rcx, rax
0x18000578a  sub     rdx, rax
0x18000578d  movzx   r8d, byte ptr [rcx]
0x180005791  movzx   r9d, byte ptr [rcx+rdx]
0x180005796  sub     r8d, r9d
0x180005799  jnz     short loc_1800057A3
0x18000579b  inc     rcx
0x18000579e  test    r9d, r9d
0x1800057a1  jnz     short loc_18000578D
0x1800057a3  test    r8d, r8d
0x1800057a6  jz      short loc_1800057FC
0x1800057a8  mov     rdx, rax
0x1800057ab  lea     rcx, [rbx+0A8h]
0x1800057b2  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x1800057b8  jmp     short loc_18000577F
0x1800057ba  cmp     dword ptr [rdi], 0
0x1800057bd  jz      short loc_180005802
0x1800057bf  test    byte ptr cs:g_dwDebugFlags, 3
0x1800057c6  jz      short loc_180005802
0x1800057c8  mov     rcx, cs:g_pDebug
0x1800057cf  lea     rax, aVerbSIsNotSpec; "Verb '%s' is not specifically allowed a"...
0x1800057d6  mov     [rsp+58h+var_30], r14
0x1800057db  lea     r9, aCheckforallowe_1; "CheckForAllowedVerb"
0x1800057e2  mov     r8d, 433h
0x1800057e8  mov     [rsp+58h+var_38], rax
0x1800057ed  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800057f4  call    cs:__imp_PuDbgPrint
0x1800057fa  jmp     short loc_180005802
0x1800057fc  mov     dword ptr [rdi], 0
0x180005802  xor     eax, eax
0x180005804  add     rsp, 30h
0x180005808  pop     r14
0x18000580a  pop     rdi
0x18000580b  pop     rsi
0x18000580c  pop     rbp
0x18000580d  pop     rbx
0x18000580e  retn
```
