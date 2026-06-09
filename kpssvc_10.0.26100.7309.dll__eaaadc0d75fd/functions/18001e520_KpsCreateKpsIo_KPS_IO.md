# KpsCreateKpsIo(_KPS_IO * *)

- ea: `0x18001e520`
- end: `0x18001e721`
- name: `?KpsCreateKpsIo@@YAKPEAPEAU_KPS_IO@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(struct _KPS_IO **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800210f4`
- `0x180021b10`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x18001e520`
- `0x1800203ac`
- `0x180026a08`
- `0x180026d9c`
- `0x1800300f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001e607`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001e607`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e637`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e68e`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e637`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e68e`
- `ntdll!RtlInitializeCriticalSection` at `0x18001e5db`
- `ntdll!RtlInitializeCriticalSection` at `0x18001e5db`
- `ntdll!RtlEnterCriticalSection` at `0x18001e5ea`
- `ntdll!RtlEnterCriticalSection` at `0x18001e64a`
- `ntdll!RtlEnterCriticalSection` at `0x18001e5ea`
- `ntdll!RtlEnterCriticalSection` at `0x18001e64a`

## string_xrefs

- `0x18001e5a4`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
__int64 __fastcall KpsCreateKpsIo(struct _KPS_IO **a1)
{
  unsigned int v2; // edi
  char *v3; // rax
  _QWORD *v4; // rbx
  _QWORD *v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  PTP_WAIT ThreadpoolWait; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids);
  v3 = (char *)KpsAllocMem(0x160u);
  v4 = v3;
  if ( !v3 )
  {
    v2 = 8;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v2;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      8,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      362);
    goto LABEL_15;
  }
  *((_QWORD *)v3 + 27) = -1;
  v6 = (struct _RTL_CRITICAL_SECTION *)(v3 + 288);
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v3 + 288));
  RtlEnterCriticalSection(v6);
  ThreadpoolWait = CreateThreadpoolWait(KpsTimeoutCallback, v4, &pcbe);
  v4[41] = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    KpsFreeKpsIo((struct _KPS_IO *)v4);
    goto LABEL_15;
  }
  v4[43] = 1;
  *((_DWORD *)v4 + 84) = 0;
  RtlLeaveCriticalSection(v6);
  RtlEnterCriticalSection(&stru_18003AC20);
  v8 = qword_18003AC48;
  v9 = v4 + 5;
  if ( *(__int64 **)(qword_18003AC48 + 8) != &qword_18003AC48 )
    __fastfail(3u);
  *v9 = qword_18003AC48;
  v4[6] = &qword_18003AC48;
  *(_QWORD *)(v8 + 8) = v9;
  qword_18003AC48 = (__int64)(v4 + 5);
  RtlLeaveCriticalSection(&stru_18003AC20);
  _InterlockedIncrement64(&qword_18003AC58);
  *a1 = (struct _KPS_IO *)v4;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_16:
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
        WPP_SF_D(v5[2], 15, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v2);
      return v2;
    }
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v4);
LABEL_15:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  return v2;
}

```

## disassembly

```asm
0x18001e520  mov     rax, rsp
0x18001e523  mov     [rax+8], rbx
0x18001e527  mov     [rax+10h], rbp
0x18001e52b  mov     [rax+18h], rsi
0x18001e52f  mov     [rax+20h], rdi
0x18001e533  push    r14
0x18001e535  sub     rsp, 30h
0x18001e539  mov     r14, rcx
0x18001e53c  xor     edi, edi
0x18001e53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e545  lea     rbp, WPP_GLOBAL_Control
0x18001e54c  cmp     rcx, rbp
0x18001e54f  jz      short loc_18001E56A
0x18001e551  test    byte ptr [rcx+1Ch], 20h
0x18001e555  jz      short loc_18001E56A
0x18001e557  mov     rcx, [rcx+10h]
0x18001e55b  lea     edx, [rdi+0Ch]
0x18001e55e  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e565  call    WPP_SF_
0x18001e56a  mov     ecx, 160h; unsigned __int64
0x18001e56f  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x18001e574  mov     rbx, rax
0x18001e577  test    rax, rax
0x18001e57a  jnz     short loc_18001E5C9
0x18001e57c  lea     r9d, [rax+8]
0x18001e580  mov     edi, r9d
0x18001e583  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e58a  cmp     rcx, rbp
0x18001e58d  jz      loc_18001E703
0x18001e593  test    byte ptr [rcx+1Ch], 1
0x18001e597  jz      loc_18001E6E0
0x18001e59d  mov     rcx, [rcx+10h]
0x18001e5a1  lea     edx, [rax+0Dh]
0x18001e5a4  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001e5ab  mov     [rsp+38h+var_10], 16Ah
0x18001e5b3  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e5ba  mov     [rsp+38h+var_18], rax
0x18001e5bf  call    WPP_SF_Dsd
0x18001e5c4  jmp     loc_18001E6D9
0x18001e5c9  or      qword ptr [rax+0D8h], 0FFFFFFFFFFFFFFFFh
0x18001e5d1  lea     rsi, [rax+120h]
0x18001e5d8  mov     rcx, rsi; CriticalSection
0x18001e5db  call    cs:__imp_RtlInitializeCriticalSection
0x18001e5e2  nop     dword ptr [rax+rax+00h]
0x18001e5e7  mov     rcx, rsi; CriticalSection
0x18001e5ea  call    cs:__imp_RtlEnterCriticalSection
0x18001e5f1  nop     dword ptr [rax+rax+00h]
0x18001e5f6  lea     r8, pcbe; pcbe
0x18001e5fd  mov     rdx, rbx; pv
0x18001e600  lea     rcx, ?KpsTimeoutCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001e607  call    cs:__imp_CreateThreadpoolWait
0x18001e60e  nop     dword ptr [rax+rax+00h]
0x18001e613  mov     [rbx+148h], rax
0x18001e61a  test    rax, rax
0x18001e61d  jz      loc_18001E6D1
0x18001e623  mov     rcx, rsi; CriticalSection
0x18001e626  mov     qword ptr [rbx+158h], 1
0x18001e631  mov     [rbx+150h], edi
0x18001e637  call    cs:__imp_RtlLeaveCriticalSection
0x18001e63e  nop     dword ptr [rax+rax+00h]
0x18001e643  lea     rcx, stru_18003AC20; CriticalSection
0x18001e64a  call    cs:__imp_RtlEnterCriticalSection
0x18001e651  nop     dword ptr [rax+rax+00h]
0x18001e656  mov     rcx, cs:qword_18003AC48
0x18001e65d  lea     rdx, qword_18003AC48
0x18001e664  lea     rax, [rbx+28h]
0x18001e668  cmp     [rcx+8], rdx
0x18001e66c  jz      short loc_18001E675
0x18001e66e  mov     ecx, 3
0x18001e673  int     29h; Win8: RtlFailFast(ecx)
0x18001e675  mov     [rax], rcx
0x18001e678  mov     [rax+8], rdx
0x18001e67c  mov     [rcx+8], rax
0x18001e680  lea     rcx, stru_18003AC20; CriticalSection
0x18001e687  mov     cs:qword_18003AC48, rax
0x18001e68e  call    cs:__imp_RtlLeaveCriticalSection
0x18001e695  nop     dword ptr [rax+rax+00h]
0x18001e69a  lock inc cs:qword_18003AC58
0x18001e6a2  mov     [r14], rbx
0x18001e6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6ac  cmp     rcx, rbp
0x18001e6af  jz      short loc_18001E703
0x18001e6b1  test    byte ptr [rcx+1Ch], 4
0x18001e6b5  jz      short loc_18001E6E0
0x18001e6b7  mov     rcx, [rcx+10h]
0x18001e6bb  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e6c2  mov     edx, 0Eh
0x18001e6c7  mov     r9, rbx
0x18001e6ca  call    WPP_SF_q
0x18001e6cf  jmp     short loc_18001E6D9
0x18001e6d1  mov     rcx, rbx; lpMem
0x18001e6d4  call    ?KpsFreeKpsIo@@YAXPEAU_KPS_IO@@@Z; KpsFreeKpsIo(_KPS_IO *)
0x18001e6d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6e0  cmp     rcx, rbp
0x18001e6e3  jz      short loc_18001E703
0x18001e6e5  test    byte ptr [rcx+1Ch], 20h
0x18001e6e9  jz      short loc_18001E703
0x18001e6eb  mov     rcx, [rcx+10h]
0x18001e6ef  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001e6f6  mov     edx, 0Fh
0x18001e6fb  mov     r9d, edi
0x18001e6fe  call    WPP_SF_D
0x18001e703  mov     rbx, [rsp+38h+arg_0]
0x18001e708  mov     eax, edi
0x18001e70a  mov     rdi, [rsp+38h+arg_18]
0x18001e70f  mov     rbp, [rsp+38h+arg_8]
0x18001e714  mov     rsi, [rsp+38h+arg_10]
0x18001e719  add     rsp, 30h
0x18001e71d  pop     r14
0x18001e71f  retn
```
