# EuCredentialsCommitRouterIPSec

- ea: `0x180013660`
- end: `0x180013851`
- name: `EuCredentialsCommitRouterIPSec`
- size: `497`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012b78`

## callees

- `0x180013660`
- `0x18003bea0`
- `0x18003c860`
- `0x18003ce6c`
- `0x18003d184`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x1800136dc`
- `rtutils!TracePrintfExA` at `0x180013810`
- `rtutils!TracePrintfExA` at `0x1800136dc`
- `rtutils!TracePrintfExA` at `0x180013810`

## string_xrefs

- `0x1800136d2`: `EuCredComRouterIPSec`
- `0x1800137a1`: `EuCredComRouterIPSec: MprAdminInterfaceGetHandle error %d`
- `0x180013804`: `EuCredComRouterIPSec: MprAdminInterfaceSetCredentialsEx error %d`

## pseudocode

```c
__int64 __fastcall EuCredentialsCommitRouterIPSec(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  const wchar_t *v4; // rax
  const wchar_t *v5; // rsi
  unsigned int v6; // edi
  unsigned int v7; // eax
  __int16 *v8; // rbx
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  __int16 *v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v13[257]; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+252h] [rbp+152h]
  __int16 v15; // [rsp+256h] [rbp+156h]
  int v16; // [rsp+260h] [rbp+160h]
  int v17; // [rsp+264h] [rbp+164h]

  v9 = 0;
  v14 = 0;
  v15 = 0;
  v12 = 0;
  memset_0(v13, 0, 0x222u);
  LODWORD(v11) = 0;
  v10 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EuCredComRouterIPSec");
  if ( !*(_DWORD *)(a1 + 1008) )
    return 0;
  result = ((__int64 (__fastcall *)(_QWORD, __int64 *))g_pMprAdminServerConnect)(*(_QWORD *)(a1 + 48), &v9);
  if ( !(_DWORD)result )
  {
    memset_0(v13, 0, 0x228u);
    v3 = *(_QWORD *)(a1 + 872);
    v17 = 2;
    v16 = 1;
    v4 = (const wchar_t *)StrDup(*(STRSAFE_LPCWSTR *)(v3 + 8));
    v5 = v4;
    if ( v4 )
    {
      v6 = StringCchCopyWrapW(v13, 0x101u, v4);
      if ( !v6 )
      {
        v7 = ((__int64 (__fastcall *)(__int64, const wchar_t *, __int64 *, _QWORD))g_pMprAdminInterfaceGetHandle)(
               v9,
               v5,
               &v12,
               0);
        v6 = v7;
        if ( v7 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "EuCredComRouterIPSec: MprAdminInterfaceGetHandle error %d", v7);
        }
        else
        {
          v8 = (__int16 *)(a1 + 1012);
          v10 = 514;
          v11 = v8;
          EncodePasswordW(v8);
          v6 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))g_pMprAdminInterfaceSetCredentialsEx)(
                 v9,
                 v12,
                 1,
                 &v10);
          EncodePasswordW(v8);
          if ( v6 && g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "EuCredComRouterIPSec: MprAdminInterfaceSetCredentialsEx error %d", v6);
        }
      }
      Free0(v5);
    }
    else
    {
      v6 = 8;
    }
    if ( v9 )
      ((void (*)(void))g_pMprAdminServerDisconnect)();
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180013660  push    rbp
0x180013662  push    rbx
0x180013663  push    rsi
0x180013664  push    rdi
0x180013665  lea     rbp, [rsp-198h]
0x18001366d  sub     rsp, 298h
0x180013674  mov     rax, cs:__security_cookie
0x18001367b  xor     rax, rsp
0x18001367e  mov     [rbp+1B0h+var_30], rax
0x180013685  xor     eax, eax
0x180013687  mov     [rsp+2B0h+var_280], 0
0x180013690  mov     rbx, rcx
0x180013693  mov     [rbp+1B0h+var_5E], eax
0x180013699  lea     rcx, [rsp+2B0h+var_260]; void *
0x18001369e  mov     [rbp+1B0h+var_5A], ax
0x1800136a5  xor     edx, edx; Val
0x1800136a7  mov     [rsp+2B0h+var_268], 0
0x1800136b0  mov     r8d, 222h; Size
0x1800136b6  call    memset_0
0x1800136bb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800136c1  xor     eax, eax
0x1800136c3  mov     qword ptr [rsp+2B0h+var_274], rax
0x1800136c8  mov     [rsp+38h], rax
0x1800136cd  cmp     ecx, 0FFFFFFFFh
0x1800136d0  jz      short loc_1800136E2
0x1800136d2  lea     r8, aEucredcomroute_1; "EuCredComRouterIPSec"
0x1800136d9  lea     edx, [rax+0Ch]; dwFlags
0x1800136dc  call    cs:__imp_TracePrintfExA
0x1800136e2  cmp     dword ptr [rbx+3F0h], 0
0x1800136e9  jnz     short loc_1800136F2
0x1800136eb  xor     eax, eax
0x1800136ed  jmp     loc_180013836
0x1800136f2  mov     rcx, [rbx+30h]
0x1800136f6  lea     rdx, [rsp+2B0h+var_280]
0x1800136fb  mov     rax, cs:g_pMprAdminServerConnect
0x180013702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013707  test    eax, eax
0x180013709  jnz     loc_180013836
0x18001370f  xor     edx, edx; Val
0x180013711  lea     rcx, [rsp+2B0h+var_260]; void *
0x180013716  mov     r8d, 228h; Size
0x18001371c  call    memset_0
0x180013721  mov     rcx, [rbx+368h]
0x180013728  mov     [rbp+1B0h+var_4C], 2
0x180013732  mov     [rbp+1B0h+var_50], 1
0x18001373c  mov     rcx, [rcx+8]; pszSrc
0x180013740  call    StrDup
0x180013745  mov     rsi, rax
0x180013748  test    rax, rax
0x18001374b  jnz     short loc_180013755
0x18001374d  lea     edi, [rax+8]
0x180013750  jmp     loc_18001381E
0x180013755  mov     r8, rsi
0x180013758  lea     rcx, [rsp+2B0h+var_260]
0x18001375d  mov     edx, 101h
0x180013762  call    StringCchCopyWrapW
0x180013767  mov     edi, eax
0x180013769  test    eax, eax
0x18001376b  jnz     loc_180013816
0x180013771  mov     rcx, [rsp+2B0h+var_280]
0x180013776  lea     r8, [rsp+2B0h+var_268]
0x18001377b  mov     rax, cs:g_pMprAdminInterfaceGetHandle
0x180013782  xor     r9d, r9d
0x180013785  mov     rdx, rsi
0x180013788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001378d  mov     edi, eax
0x18001378f  test    eax, eax
0x180013791  jz      short loc_1800137AA
0x180013793  mov     ecx, cs:g_dwTraceId
0x180013799  cmp     ecx, 0FFFFFFFFh
0x18001379c  jz      short loc_180013816
0x18001379e  mov     r9d, eax
0x1800137a1  lea     r8, aEucredcomroute_0; "EuCredComRouterIPSec: MprAdminInterface"...
0x1800137a8  jmp     short loc_18001380B
0x1800137aa  add     rbx, 3F4h
0x1800137b1  mov     qword ptr [rsp+38h], 202h
0x1800137ba  mov     rcx, rbx
0x1800137bd  mov     qword ptr [rsp+2B0h+var_274+4], rbx
0x1800137c2  call    EncodePasswordW
0x1800137c7  mov     rdx, [rsp+2B0h+var_268]
0x1800137cc  lea     r9, [rsp+2B0h+var_278]
0x1800137d1  mov     rcx, [rsp+2B0h+var_280]
0x1800137d6  mov     r8d, 1
0x1800137dc  mov     rax, cs:g_pMprAdminInterfaceSetCredentialsEx
0x1800137e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137e8  mov     rcx, rbx
0x1800137eb  mov     edi, eax
0x1800137ed  call    EncodePasswordW
0x1800137f2  test    edi, edi
0x1800137f4  jz      short loc_180013816
0x1800137f6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800137fc  cmp     ecx, 0FFFFFFFFh
0x1800137ff  jz      short loc_180013816
0x180013801  mov     r9d, edi
0x180013804  lea     r8, aEucredcomroute; "EuCredComRouterIPSec: MprAdminInterface"...
0x18001380b  mov     edx, 0Ch; dwFlags
0x180013810  call    cs:__imp_TracePrintfExA
0x180013816  mov     rcx, rsi
0x180013819  call    Free0
0x18001381e  mov     rcx, [rsp+2B0h+var_280]
0x180013823  test    rcx, rcx
0x180013826  jz      short loc_180013834
0x180013828  mov     rax, cs:g_pMprAdminServerDisconnect
0x18001382f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013834  mov     eax, edi
0x180013836  mov     rcx, [rbp+1B0h+var_30]
0x18001383d  xor     rcx, rsp; StackCookie
0x180013840  call    __security_check_cookie
0x180013845  add     rsp, 298h
0x18001384c  pop     rdi
0x18001384d  pop     rsi
0x18001384e  pop     rbx
0x18001384f  pop     rbp
0x180013850  retn
```
