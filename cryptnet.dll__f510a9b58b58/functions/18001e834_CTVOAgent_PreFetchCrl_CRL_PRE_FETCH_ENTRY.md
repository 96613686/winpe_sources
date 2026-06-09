# CTVOAgent::PreFetchCrl(_CRL_PRE_FETCH_ENTRY *)

- ea: `0x18001e834`
- end: `0x18001e954`
- name: `?PreFetchCrl@CTVOAgent@@QEAAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z`
- size: `288`
- prototype: `void __fastcall(CTVOAgent *this, struct _CRL_PRE_FETCH_ENTRY *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18001f480`

## callees

- `0x18000a990`
- `0x180017de4`
- `0x18001e660`
- `0x18001e834`
- `0x18001e95c`
- `0x18001eee8`
- `0x18001f100`
- `0x18001f61c`

## import_xrefs

- `CRYPT32!CertFreeCRLContext` at `0x18001e8af`
- `CRYPT32!CertFreeCRLContext` at `0x18001e8af`
- `CRYPT32!CertDuplicateCRLContext` at `0x18001e8b8`
- `CRYPT32!CertDuplicateCRLContext` at `0x18001e8b8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001e8f4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001e8f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e886`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e886`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e897`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e930`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e897`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e930`

## pseudocode

```c
void __fastcall CTVOAgent::PreFetchCrl(CTVOAgent *this, struct _CRL_PRE_FETCH_ENTRY *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int Crl; // eax
  const WCHAR *v5; // rsi
  int v6; // r15d
  int v7; // r14d
  const WCHAR *UrlList; // rax
  WCHAR *v9; // rbx
  __int64 v10; // rsi
  const CRL_CONTEXT *v11; // rbx

  v2 = g_pProcessTVOAgent;
  Crl = RetrieveCrlPreFetchCrl((__int64)a2);
  v5 = (const WCHAR *)*((_QWORD *)a2 + 11);
  v6 = Crl;
  v7 = 0;
  UrlList = GetCrlPreFetchUrlList();
  v9 = (WCHAR *)UrlList;
  if ( UrlList )
  {
    LOBYTE(v7) = (unsigned int)IsInMultiSzList(UrlList, v5) != 0;
    operator delete(v9);
  }
  EnterCriticalSection(v2);
  v10 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
  {
    if ( v6 )
    {
      v11 = (const CRL_CONTEXT *)*((_QWORD *)a2 + 8);
      CertFreeCRLContext(*(PCCRL_CONTEXT *)(v10 + 40));
      *(_QWORD *)(v10 + 40) = CertDuplicateCRLContext(v11);
      *(FILETIME *)(v10 + 84) = v11->pCrlInfo->ThisUpdate;
      *(FILETIME *)(v10 + 92) = v11->pCrlInfo->NextUpdate;
      *(_QWORD *)(v10 + 100) = *((_QWORD *)a2 + 12);
      *(_QWORD *)(v10 + 108) = 0;
    }
    else if ( CompareFileTime((const FILETIME *)a2 + 12, (const FILETIME *)(v10 + 100)) > 0 )
    {
      *(_QWORD *)(v10 + 100) = *((_QWORD *)a2 + 12);
    }
    if ( v7 )
    {
      LeaveCriticalSection(v2);
      GetCrlPreFetchScheduleParameters((char *)a2 + 120);
      ScheduleNextCrlPreFetch(a2);
    }
    else
    {
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(v10 + 144) = 0;
      LeaveCriticalSection(v2);
      FreeCrlPreFetchEntry(a2);
    }
  }
  else
  {
    LeaveCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x18001e834  push    rbx
0x18001e836  push    rbp
0x18001e837  push    rsi
0x18001e838  push    rdi
0x18001e839  push    r14
0x18001e83b  push    r15
0x18001e83d  sub     rsp, 28h
0x18001e841  mov     rbp, cs:?g_pProcessTVOAgent@@3PEAVCTVOAgent@@EA; CTVOAgent * g_pProcessTVOAgent
0x18001e848  mov     rcx, rdx
0x18001e84b  mov     rdi, rdx
0x18001e84e  call    _RetrieveCrlPreFetchCrl
0x18001e853  mov     rsi, [rdi+58h]
0x18001e857  mov     r15d, eax
0x18001e85a  xor     r14d, r14d
0x18001e85d  call    ?GetCrlPreFetchUrlList@@YAPEAGXZ; GetCrlPreFetchUrlList(void)
0x18001e862  mov     rbx, rax
0x18001e865  test    rax, rax
0x18001e868  jz      short loc_18001E883
0x18001e86a  mov     rdx, rsi; lpString2
0x18001e86d  mov     rcx, rax; lpString1
0x18001e870  call    _IsInMultiSzList
0x18001e875  test    eax, eax
0x18001e877  mov     rcx, rbx; hMem
0x18001e87a  setnz   r14b
0x18001e87e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e883  mov     rcx, rbp; lpCriticalSection
0x18001e886  call    cs:__imp_EnterCriticalSection
0x18001e88c  mov     rsi, [rdi]
0x18001e88f  test    rsi, rsi
0x18001e892  jnz     short loc_18001E8A2
0x18001e894  mov     rcx, rbp; lpCriticalSection
0x18001e897  call    cs:__imp_LeaveCriticalSection
0x18001e89d  jmp     loc_18001E947
0x18001e8a2  test    r15d, r15d
0x18001e8a5  jz      short loc_18001E8EC
0x18001e8a7  mov     rcx, [rsi+28h]; pCrlContext
0x18001e8ab  mov     rbx, [rdi+40h]
0x18001e8af  call    cs:__imp_CertFreeCRLContext
0x18001e8b5  mov     rcx, rbx; pCrlContext
0x18001e8b8  call    cs:__imp_CertDuplicateCRLContext
0x18001e8be  mov     [rsi+28h], rax
0x18001e8c2  mov     rax, [rbx+18h]
0x18001e8c6  mov     rcx, [rax+30h]
0x18001e8ca  mov     [rsi+54h], rcx
0x18001e8ce  mov     rax, [rbx+18h]
0x18001e8d2  mov     rcx, [rax+38h]
0x18001e8d6  mov     [rsi+5Ch], rcx
0x18001e8da  mov     rax, [rdi+60h]
0x18001e8de  mov     [rsi+64h], rax
0x18001e8e2  mov     qword ptr [rsi+6Ch], 0
0x18001e8ea  jmp     short loc_18001E906
0x18001e8ec  lea     rdx, [rsi+64h]; lpFileTime2
0x18001e8f0  lea     rcx, [rdi+60h]; lpFileTime1
0x18001e8f4  call    cs:__imp_CompareFileTime
0x18001e8fa  test    eax, eax
0x18001e8fc  jle     short loc_18001E906
0x18001e8fe  mov     rax, [rdi+60h]
0x18001e902  mov     [rsi+64h], rax
0x18001e906  mov     rcx, rbp; lpCriticalSection
0x18001e909  test    r14d, r14d
0x18001e90c  jnz     short loc_18001E930
0x18001e90e  mov     qword ptr [rdi], 0
0x18001e915  mov     qword ptr [rsi+90h], 0
0x18001e920  call    cs:__imp_LeaveCriticalSection
0x18001e926  mov     rcx, rdi; hMem
0x18001e929  call    ?FreeCrlPreFetchEntry@@YAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z; FreeCrlPreFetchEntry(_CRL_PRE_FETCH_ENTRY *)
0x18001e92e  jmp     short loc_18001E947
0x18001e930  call    cs:__imp_LeaveCriticalSection
0x18001e936  lea     rcx, [rdi+78h]
0x18001e93a  call    _GetCrlPreFetchScheduleParameters
0x18001e93f  mov     rcx, rdi; struct _CRL_PRE_FETCH_ENTRY *
0x18001e942  call    ?ScheduleNextCrlPreFetch@@YAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z; ScheduleNextCrlPreFetch(_CRL_PRE_FETCH_ENTRY *)
0x18001e947  add     rsp, 28h
0x18001e94b  pop     r15
0x18001e94d  pop     r14
0x18001e94f  pop     rdi
0x18001e950  pop     rsi
0x18001e951  pop     rbp
0x18001e952  pop     rbx
0x18001e953  retn
```
