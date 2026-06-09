# CFveApiBase::GetSidFromDpapiNgInfo(_FVE_DPAPI_NG_INFO const *,void * *)

- ea: `0x180085880`
- end: `0x18008599f`
- name: `?GetSidFromDpapiNgInfo@CFveApiBase@@IEBAJPEBU_FVE_DPAPI_NG_INFO@@PEAPEAX@Z`
- size: `287`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, const struct _FVE_DPAPI_NG_INFO *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800855e0`

## callees

- `0x180005410`
- `0x18000ba30`
- `0x18000ca50`
- `0x180085880`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085939`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085939`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085902`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085902`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800858e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800858e0`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetSidFromDpapiNgInfo(
        CFveApiBase *this,
        const struct _FVE_DPAPI_NG_INFO *a2,
        void **a3)
{
  void *v4; // rbx
  int LastHresultError; // edi
  DWORD LengthSid; // esi
  void *v7; // rax
  PSID Sid; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR StringSid; // [rsp+48h] [rbp-30h] BYREF

  Sid = 0;
  v4 = 0;
  *a3 = 0;
  StringSid = 0;
  LastHresultError = (*(__int64 (__fastcall **)(CFveApiBase *, const struct _FVE_DPAPI_NG_INFO *, _QWORD, LPCWSTR *))(*(_QWORD *)this + 200LL))(
                       this,
                       a2,
                       0,
                       &StringSid);
  if ( LastHresultError >= 0 )
  {
    if ( !ConvertStringSidToSidW(StringSid, &Sid) )
    {
LABEL_3:
      LastHresultError = GetLastHresultError();
      goto LABEL_8;
    }
    LengthSid = GetLengthSid(Sid);
    v7 = CFveApiBase::FastAlloc(LengthSid);
    v4 = v7;
    if ( v7 )
    {
      if ( !CopySid(LengthSid, v7, Sid) )
        goto LABEL_3;
      *a3 = v4;
      v4 = 0;
    }
    else
    {
      LastHresultError = -2147024882;
    }
  }
LABEL_8:
  if ( StringSid )
    CFveApiBase::FastFree((void *)StringSid);
  if ( Sid )
    CFveApiBase::FastFree(Sid);
  if ( v4 )
    CFveApiBase::FastFree(v4);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x180085880  mov     r11, rsp
0x180085883  mov     [r11+20h], rbx
0x180085887  push    rsi
0x180085888  push    rdi
0x180085889  push    r14
0x18008588b  sub     rsp, 60h
0x18008588f  mov     rax, cs:__security_cookie
0x180085896  xor     rax, rsp
0x180085899  mov     [rsp+78h+var_28], rax
0x18008589e  mov     r14, r8
0x1800858a1  mov     qword ptr [r11-38h], 0
0x1800858a9  xor     ebx, ebx
0x1800858ab  mov     [r11-40h], rbx
0x1800858af  mov     [r8], rbx
0x1800858b2  mov     [r11-30h], rbx
0x1800858b6  mov     rax, [rcx]
0x1800858b9  lea     r9, [r11-30h]
0x1800858bd  xor     r8d, r8d
0x1800858c0  mov     rax, [rax+0C8h]
0x1800858c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858cc  mov     edi, eax
0x1800858ce  mov     [rsp+78h+var_48], eax
0x1800858d2  test    eax, eax
0x1800858d4  js      short loc_180085953
0x1800858d6  lea     rdx, [rsp+78h+Sid]; Sid
0x1800858db  mov     rcx, [rsp+78h+StringSid]; StringSid
0x1800858e0  call    cs:__imp_ConvertStringSidToSidW
0x1800858e7  nop     dword ptr [rax+rax+00h]
0x1800858ec  test    eax, eax
0x1800858ee  jnz     short loc_1800858FD
0x1800858f0  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800858f5  mov     edi, eax
0x1800858f7  mov     [rsp+78h+var_48], eax
0x1800858fb  jmp     short loc_180085953
0x1800858fd  mov     rcx, [rsp+78h+Sid]; pSid
0x180085902  call    cs:__imp_GetLengthSid
0x180085909  nop     dword ptr [rax+rax+00h]
0x18008590e  mov     esi, eax
0x180085910  mov     ecx, eax; unsigned __int64
0x180085912  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x180085917  mov     rbx, rax
0x18008591a  mov     [rsp+78h+var_40], rax
0x18008591f  test    rax, rax
0x180085922  jnz     short loc_18008592F
0x180085924  mov     edi, 8007000Eh
0x180085929  mov     [rsp+78h+var_48], edi
0x18008592d  jmp     short loc_180085953
0x18008592f  mov     r8, [rsp+78h+Sid]; pSourceSid
0x180085934  mov     rdx, rbx; pDestinationSid
0x180085937  mov     ecx, esi; nDestinationSidLength
0x180085939  call    cs:__imp_CopySid
0x180085940  nop     dword ptr [rax+rax+00h]
0x180085945  test    eax, eax
0x180085947  jz      short loc_1800858F0
0x180085949  mov     [r14], rbx
0x18008594c  xor     ebx, ebx
0x18008594e  mov     [rsp+78h+var_40], rbx
0x180085953  mov     rcx, [rsp+78h+StringSid]; lpMem
0x180085958  test    rcx, rcx
0x18008595b  jz      short loc_180085962
0x18008595d  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180085962  mov     rcx, [rsp+78h+Sid]; lpMem
0x180085967  test    rcx, rcx
0x18008596a  jz      short loc_180085971
0x18008596c  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180085971  test    rbx, rbx
0x180085974  jz      short loc_18008597E
0x180085976  mov     rcx, rbx; lpMem
0x180085979  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18008597e  mov     eax, edi
0x180085980  mov     rcx, [rsp+78h+var_28]
0x180085985  xor     rcx, rsp; StackCookie
0x180085988  call    __security_check_cookie
0x18008598d  mov     rbx, [rsp+78h+arg_18]
0x180085995  add     rsp, 60h
0x180085999  pop     r14
0x18008599b  pop     rdi
0x18008599c  pop     rsi
0x18008599d  retn
0x1801243f9  push    rbp
0x1801243fb  sub     rsp, 30h
0x1801243ff  mov     rbp, rdx
0x180124402  mov     rcx, [rbp+48h]; lpMem
0x180124406  test    rcx, rcx
0x180124409  jz      short loc_180124411
0x18012440b  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180124410  nop
0x180124411  mov     rcx, [rbp+40h]; lpMem
0x180124415  test    rcx, rcx
0x180124418  jz      short loc_180124420
0x18012441a  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18012441f  nop
0x180124420  mov     rcx, [rbp+38h]; lpMem
0x180124424  test    rcx, rcx
0x180124427  jz      short loc_18012442F
0x180124429  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18012442e  nop
0x18012442f  add     rsp, 30h
0x180124433  pop     rbp
0x180124434  retn
```
