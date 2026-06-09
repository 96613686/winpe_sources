# NlpChangeCachePassword

- ea: `0x18004417c`
- end: `0x1800444db`
- name: `NlpChangeCachePassword`
- size: `863`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c000`
- `0x18003fdec`

## callees

- `0x18002ee7c`
- `0x18002f014`
- `0x180030844`
- `0x180040338`
- `0x180040c58`
- `0x180041f64`
- `0x180042664`
- `0x180042dac`
- `0x1800432c8`
- `0x180043968`
- `0x18004417c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004436a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004436a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004431b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004431b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004433e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004433e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800444be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800444be`
- `ntdll!NtQuerySystemTime` at `0x1800443df`
- `ntdll!NtQuerySystemTime` at `0x1800443df`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800441e4`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800441e4`
- `ntdll!RtlReleaseResource` at `0x1800441fa`
- `ntdll!RtlReleaseResource` at `0x180044476`
- `ntdll!RtlReleaseResource` at `0x1800441fa`
- `ntdll!RtlReleaseResource` at `0x180044476`

## pseudocode

```c
__int64 __fastcall NlpChangeCachePassword(int a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, _QWORD *a4)
{
  void *v7; // rdi
  void *DomainRelativeSid; // r15
  int v10; // eax
  __int64 v11; // rsi
  int v12; // ebx
  DWORD LastError; // eax
  unsigned int v14; // r14d
  size_t Size; // [rsp+30h] [rbp-40h] BYREF
  WINBOOL IsMember[2]; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h] BYREF
  __int128 v19; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]

  *(_QWORD *)IsMember = 0;
  LODWORD(Size) = 0;
  v17 = 0;
  v7 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( !NlpCacheInitialized )
    return 3221226021LL;
  RtlAcquireResourceExclusive(&NlpLogonCacheCritSec, 1u);
  if ( !HIDWORD(NlpCacheControl) )
  {
    RtlReleaseResource(&NlpLogonCacheCritSec);
    return 3221226021LL;
  }
  DomainRelativeSid = 0;
  v10 = NlpReadCacheEntry(a2, a3, 0, &v17, (struct _LOGON_CACHE_ENTRY **)IsMember, (unsigned int *)&Size);
  v11 = *(_QWORD *)IsMember;
  v12 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_905305d962583d6f838b30057de84013_Traceguids,
        (unsigned int)v10);
    if ( v12 == -1073741715 )
      v12 = -1073741275;
    goto LABEL_37;
  }
  if ( a1 != 2 )
    goto LABEL_28;
  if ( ((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v19) )
  {
    if ( (WORD4(v19) & 0x200) == 0 )
    {
      IsMember[0] = 0;
      v12 = NlpBuildAccountInfo((unsigned __int16 *)v11, &v18);
      if ( v12 < 0 )
        goto LABEL_44;
      v7 = (void *)v18;
      DomainRelativeSid = NlpMakeDomainRelativeSid(*(PSID *)(v18 + 224), *(_DWORD *)(v18 + 148));
      if ( !DomainRelativeSid )
      {
        v12 = -1073741801;
        goto LABEL_37;
      }
      v12 = LsaFunctions->ImpersonateClient();
      if ( v12 < 0 )
        goto LABEL_37;
      if ( !CheckTokenMembership(0, DomainRelativeSid, IsMember) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_905305d962583d6f838b30057de84013_Traceguids, LastError);
        }
        IsMember[0] = 0;
      }
      RevertToSelf();
      if ( !IsMember[0] )
      {
        v12 = -1073741727;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_905305d962583d6f838b30057de84013_Traceguids);
        goto LABEL_37;
      }
    }
LABEL_28:
    if ( (*(_BYTE *)(v11 + 140) & 8) != 0 )
      goto LABEL_37;
    if ( v7 )
    {
LABEL_32:
      NtQuerySystemTime((PLARGE_INTEGER)(v11 + 32));
      v14 = v17;
      *((_QWORD *)NlpCteTable + 4 * v17 + 2) = *(_QWORD *)(v11 + 32);
      NlpAddEntryToActiveList(v14);
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, _QWORD, __int64))(*(_QWORD *)*a4 + 80LL))(
              *a4,
              (__int64)v7 + 48,
              a4,
              *(unsigned __int16 *)(v11 + 50),
              v11 + 96);
      if ( v12 >= 0 )
      {
        v12 = NlpEncryptCacheEntry((struct _LOGON_CACHE_ENTRY *)v11, Size);
        if ( v12 >= 0 )
        {
          v12 = NlpWriteCacheEntry(v14, (struct _LOGON_CACHE_ENTRY *)v11, Size);
          if ( v12 >= 0 && a1 == 1 )
            NlpInvalidateOldSmartCardCacheEntries(a2, a3);
        }
      }
      goto LABEL_37;
    }
    v12 = NlpBuildAccountInfo((unsigned __int16 *)v11, &v18);
    if ( v12 >= 0 )
    {
      v7 = (void *)v18;
      goto LABEL_32;
    }
LABEL_44:
    v7 = (void *)v18;
    goto LABEL_37;
  }
  v12 = -1073741595;
LABEL_37:
  RtlReleaseResource(&NlpLogonCacheCritSec);
  if ( v11 )
  {
    memset_0((void *)v11, 0, (unsigned int)Size);
    ((void (__fastcall *)(__int64))qword_180088398)(v11);
  }
  if ( DomainRelativeSid )
    ((void (__fastcall *)(void *))LsaFunctions->FreeLsaHeap)(DomainRelativeSid);
  if ( v7 )
    LocalFree(v7);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004417c  mov     [rsp-38h+arg_18], r9
0x180044181  mov     [rsp-38h+arg_10], r8
0x180044186  mov     [rsp-38h+arg_8], rdx
0x18004418b  push    rbp
0x18004418c  push    rbx
0x18004418d  push    rsi
0x18004418e  push    rdi
0x18004418f  push    r12
0x180044191  push    r14
0x180044193  push    r15
0x180044195  mov     rbp, rsp
0x180044198  sub     rsp, 70h
0x18004419c  xor     r14d, r14d
0x18004419f  xor     eax, eax
0x1800441a1  cmp     cs:NlpCacheInitialized, r14b
0x1800441a8  xorps   xmm0, xmm0
0x1800441ab  mov     rbx, r8
0x1800441ae  mov     qword ptr [rbp+IsMember], r14
0x1800441b2  mov     rsi, rdx
0x1800441b5  mov     dword ptr [rbp+Size], r14d
0x1800441b9  mov     r12d, ecx
0x1800441bc  mov     [rbp+var_30], r14d
0x1800441c0  mov     edi, r14d
0x1800441c3  mov     [rbp+var_28], r14
0x1800441c7  movups  [rbp+var_20], xmm0
0x1800441cb  mov     [rbp+var_10], rax
0x1800441cf  jnz     short loc_1800441DB
0x1800441d1  mov     eax, 0C0000225h
0x1800441d6  jmp     loc_1800444C6
0x1800441db  mov     dl, 1; Wait
0x1800441dd  lea     rcx, NlpLogonCacheCritSec; Resource
0x1800441e4  call    cs:__imp_RtlAcquireResourceExclusive
0x1800441ea  cmp     dword ptr cs:NlpCacheControl+4, r14d
0x1800441f1  jnz     short loc_180044202
0x1800441f3  lea     rcx, NlpLogonCacheCritSec; Resource
0x1800441fa  call    cs:__imp_RtlReleaseResource
0x180044200  jmp     short loc_1800441D1
0x180044202  lea     rax, [rbp+Size]
0x180044206  xor     r8d, r8d; unsigned int
0x180044209  mov     [rsp+70h+var_48], rax; unsigned int *
0x18004420e  lea     r9, [rbp+var_30]; unsigned int *
0x180044212  lea     rax, [rbp+IsMember]
0x180044216  mov     rdx, rbx; struct _UNICODE_STRING *
0x180044219  mov     rcx, rsi; struct _UNICODE_STRING *
0x18004421c  mov     [rsp+70h+var_50], rax; struct _LOGON_CACHE_ENTRY **
0x180044221  mov     r15, r14
0x180044224  call    ?NlpReadCacheEntry@@YAJPEAU_UNICODE_STRING@@0KPEAKPEAPEAU_LOGON_CACHE_ENTRY@@1@Z; NlpReadCacheEntry(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,_LOGON_CACHE_ENTRY * *,ulong *)
0x180044229  mov     rsi, qword ptr [rbp+IsMember]
0x18004422d  mov     ebx, eax
0x18004422f  test    eax, eax
0x180044231  jns     short loc_18004427A
0x180044233  mov     rcx, cs:WPP_GLOBAL_Control
0x18004423a  lea     r14, WPP_GLOBAL_Control
0x180044241  cmp     rcx, r14
0x180044244  jz      short loc_180044264
0x180044246  test    byte ptr [rcx+1Ch], 2
0x18004424a  jz      short loc_180044264
0x18004424c  mov     rcx, [rcx+10h]
0x180044250  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x180044257  mov     edx, 1Fh
0x18004425c  mov     r9d, eax
0x18004425f  call    WPP_SF_d
0x180044264  cmp     ebx, 0C000006Dh
0x18004426a  jnz     loc_18004446F
0x180044270  mov     ebx, 0C0000225h
0x180044275  jmp     loc_18004446F
0x18004427a  cmp     r12d, 2
0x18004427e  jnz     loc_1800443AF
0x180044284  mov     rax, cs:LsaFunctions
0x18004428b  lea     rcx, [rbp+var_20]
0x18004428f  mov     rax, [rax+0C0h]
0x180044296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004429b  test    al, al
0x18004429d  jnz     short loc_1800442A9
0x18004429f  mov     ebx, 0C00000E5h
0x1800442a4  jmp     loc_18004446F
0x1800442a9  test    dword ptr [rbp+var_20+8], 200h
0x1800442b0  jnz     loc_1800443AF
0x1800442b6  lea     rdx, [rbp+var_28]
0x1800442ba  mov     [rbp+IsMember], r14d
0x1800442be  mov     rcx, rsi
0x1800442c1  call    NlpBuildAccountInfo
0x1800442c6  mov     ebx, eax
0x1800442c8  test    eax, eax
0x1800442ca  js      loc_1800444D5
0x1800442d0  mov     rdi, [rbp+var_28]
0x1800442d4  mov     edx, [rdi+94h]
0x1800442da  mov     rcx, [rdi+0E0h]; SourceSid
0x1800442e1  call    NlpMakeDomainRelativeSid
0x1800442e6  mov     r15, rax
0x1800442e9  test    rax, rax
0x1800442ec  jnz     short loc_1800442F8
0x1800442ee  mov     ebx, 0C0000017h
0x1800442f3  jmp     loc_18004446F
0x1800442f8  mov     rax, cs:LsaFunctions
0x1800442ff  mov     rax, [rax+58h]
0x180044303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044308  mov     ebx, eax
0x18004430a  test    eax, eax
0x18004430c  js      loc_18004446F
0x180044312  lea     r8, [rbp+IsMember]; IsMember
0x180044316  mov     rdx, r15; SidToCheck
0x180044319  xor     ecx, ecx; TokenHandle
0x18004431b  call    cs:__imp_CheckTokenMembership
0x180044321  lea     r14, WPP_GLOBAL_Control
0x180044328  test    eax, eax
0x18004432a  jnz     short loc_18004436A
0x18004432c  mov     rax, cs:WPP_GLOBAL_Control
0x180044333  cmp     rax, r14
0x180044336  jz      short loc_180044363
0x180044338  test    byte ptr [rax+1Ch], 1
0x18004433c  jz      short loc_180044363
0x18004433e  call    cs:__imp_GetLastError
0x180044344  mov     rcx, cs:WPP_GLOBAL_Control
0x18004434b  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x180044352  mov     edx, 20h ; ' '
0x180044357  mov     r9d, eax
0x18004435a  mov     rcx, [rcx+10h]
0x18004435e  call    WPP_SF_d
0x180044363  mov     [rbp+IsMember], 0
0x18004436a  call    cs:__imp_RevertToSelf
0x180044370  cmp     [rbp+IsMember], 0
0x180044374  jnz     short loc_1800443AF
0x180044376  mov     ebx, 0C0000061h
0x18004437b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044382  cmp     rcx, r14
0x180044385  jz      loc_18004446F
0x18004438b  test    byte ptr [rcx+1Ch], 1
0x18004438f  jz      loc_18004446F
0x180044395  mov     rcx, [rcx+10h]
0x180044399  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x1800443a0  mov     edx, 21h ; '!'
0x1800443a5  call    WPP_SF_
0x1800443aa  jmp     loc_18004446F
0x1800443af  test    byte ptr [rsi+8Ch], 8
0x1800443b6  jnz     loc_18004446F
0x1800443bc  test    rdi, rdi
0x1800443bf  jnz     short loc_1800443DB
0x1800443c1  lea     rdx, [rbp+var_28]
0x1800443c5  mov     rcx, rsi
0x1800443c8  call    NlpBuildAccountInfo
0x1800443cd  mov     ebx, eax
0x1800443cf  test    eax, eax
0x1800443d1  js      loc_1800444D5
0x1800443d7  mov     rdi, [rbp+var_28]
0x1800443db  lea     rcx, [rsi+20h]; SystemTime
0x1800443df  call    cs:__imp_NtQuerySystemTime
0x1800443e5  mov     rcx, [rsi+20h]
0x1800443e9  mov     r14d, [rbp+var_30]
0x1800443ed  mov     rax, cs:?NlpCteTable@@3PEAU_NLP_CTE@@EA; _NLP_CTE * NlpCteTable
0x1800443f4  mov     edx, r14d
0x1800443f7  shl     rdx, 5
0x1800443fb  mov     [rdx+rax+10h], rcx
0x180044400  mov     ecx, r14d; unsigned int
0x180044403  call    ?NlpAddEntryToActiveList@@YAXK@Z; NlpAddEntryToActiveList(ulong)
0x180044408  mov     r10, [rbp+arg_18]
0x18004440c  lea     r8, [rsi+60h]
0x180044410  movzx   r9d, word ptr [rsi+32h]
0x180044415  lea     rdx, [rdi+30h]
0x180044419  mov     [rsp+70h+var_50], r8
0x18004441e  mov     r8, r10
0x180044421  mov     rcx, [r10]
0x180044424  mov     rax, [rcx]
0x180044427  mov     rax, [rax+50h]
0x18004442b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044430  mov     ebx, eax
0x180044432  test    eax, eax
0x180044434  js      short loc_18004446F
0x180044436  mov     edx, dword ptr [rbp+Size]; unsigned int
0x180044439  mov     rcx, rsi; struct _LOGON_CACHE_ENTRY *
0x18004443c  call    ?NlpEncryptCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@K@Z; NlpEncryptCacheEntry(_LOGON_CACHE_ENTRY *,ulong)
0x180044441  mov     ebx, eax
0x180044443  test    eax, eax
0x180044445  js      short loc_18004446F
0x180044447  mov     r8d, dword ptr [rbp+Size]; unsigned int
0x18004444b  mov     rdx, rsi; struct _LOGON_CACHE_ENTRY *
0x18004444e  mov     ecx, r14d; unsigned int
0x180044451  call    ?NlpWriteCacheEntry@@YAJKPEAU_LOGON_CACHE_ENTRY@@K@Z; NlpWriteCacheEntry(ulong,_LOGON_CACHE_ENTRY *,ulong)
0x180044456  mov     ebx, eax
0x180044458  test    eax, eax
0x18004445a  js      short loc_18004446F
0x18004445c  cmp     r12d, 1
0x180044460  jnz     short loc_18004446F
0x180044462  mov     rdx, [rbp+arg_10]; struct _UNICODE_STRING *
0x180044466  mov     rcx, [rbp+arg_8]; struct _UNICODE_STRING *
0x18004446a  call    ?NlpInvalidateOldSmartCardCacheEntries@@YAXPEBU_UNICODE_STRING@@0@Z; NlpInvalidateOldSmartCardCacheEntries(_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18004446f  lea     rcx, NlpLogonCacheCritSec; Resource
0x180044476  call    cs:__imp_RtlReleaseResource
0x18004447c  test    rsi, rsi
0x18004447f  jz      short loc_18004449E
0x180044481  mov     r8d, dword ptr [rbp+Size]; Size
0x180044485  xor     edx, edx; Val
0x180044487  mov     rcx, rsi; void *
0x18004448a  call    memset_0
0x18004448f  mov     rax, cs:qword_180088398
0x180044496  mov     rcx, rsi
0x180044499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004449e  test    r15, r15
0x1800444a1  jz      short loc_1800444B6
0x1800444a3  mov     rax, cs:LsaFunctions
0x1800444aa  mov     rcx, r15
0x1800444ad  mov     rax, [rax+30h]
0x1800444b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444b6  test    rdi, rdi
0x1800444b9  jz      short loc_1800444C4
0x1800444bb  mov     rcx, rdi; hMem
0x1800444be  call    cs:__imp_LocalFree
0x1800444c4  mov     eax, ebx
0x1800444c6  add     rsp, 70h
0x1800444ca  pop     r15
0x1800444cc  pop     r14
0x1800444ce  pop     r12
0x1800444d0  pop     rdi
0x1800444d1  pop     rsi
0x1800444d2  pop     rbx
0x1800444d3  pop     rbp
0x1800444d4  retn
0x1800444d5  mov     rdi, [rbp+var_28]
0x1800444d9  jmp     short loc_18004446F
```
