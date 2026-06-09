# KerbReferenceContext(unsigned __int64,uchar,_KERB_CONTEXT * *)

- ea: `0x180046e70`
- end: `0x18004712e`
- name: `?KerbReferenceContext@@YAJ_KEPEAPEAU_KERB_CONTEXT@@@Z`
- size: `702`
- prototype: `__int64 __fastcall(struct _KERBEROS_LIST_ENTRY *, unsigned __int8, struct _KERB_CONTEXT **)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180021574`
- `0x18002db10`
- `0x18003c340`
- `0x18005e600`
- `0x1800cb31c`
- `0x1800cc8a8`
- `0x1800d0678`

## callees

- `0x1800121b0`
- `0x180046e70`
- `0x18008b70c`
- `0x18008bea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046f3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046f3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180047008`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180047008`
- `ntdll!RtlEnterCriticalSection` at `0x180046faa`
- `ntdll!RtlEnterCriticalSection` at `0x180046faa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800470d4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800470d4`

## pseudocode

```c
__int64 __fastcall KerbReferenceContext(struct _KERBEROS_LIST_ENTRY *a1, unsigned __int8 a2, struct _KERB_CONTEXT **a3)
{
  int v6; // ebx
  __int64 result; // rax
  char v8; // si
  unsigned int v9; // edx
  unsigned __int64 v10; // r15
  int v11; // ecx
  struct _KERBEROS_LIST_ENTRY *v12; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-68h] BYREF
  __int128 v14; // [rsp+38h] [rbp-60h] BYREF
  __int64 v15; // [rsp+48h] [rbp-50h]
  __int128 v16; // [rsp+50h] [rbp-48h] BYREF
  __int128 v17; // [rsp+60h] [rbp-38h]
  int v18; // [rsp+B8h] [rbp+20h] BYREF

  v16 = 0;
  v17 = 0;
  if ( KerbGlobalPackageState == 1 )
  {
    v6 = ((__int64 (__fastcall *)(__int128 *))LsaFunctions->GetClientInfo)(&v16);
    if ( v6 < 0 )
    {
      v15 = 0;
      v14 = 0;
      if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v14) || (BYTE8(v14) & 0x20) == 0 )
      {
        KerbTracerT::Log(1, "KerbReferenceContext", 340, "Failed to get client info: 0x%x", v6);
        result = (unsigned int)v6;
        *a3 = 0;
        return result;
      }
      v6 = 0;
      v17 = 0;
      LOBYTE(v17) = 1;
      v16 = 0;
    }
  }
  else
  {
    v6 = 0;
    DWORD2(v16) = GetCurrentProcessId();
  }
  v8 = 0;
  if ( *((_DWORD *)a1 + 92) == 1098413123 )
  {
    v9 = *((_DWORD *)a1 + 26);
    v10 = 56LL
        * (unsigned __int8)((v9 >> 4)
                          + BYTE2(v9)
                          + HIBYTE(v9)
                          + v9
                          + BYTE1(v9)
                          + (((v9 >> 4) + HIWORD(v9) + HIBYTE(v9) + v9 + (v9 >> 8)) >> 4));
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KerbContextList + v10 + 16));
    v11 = KerbGlobalPackageState;
    if ( !(_BYTE)v17 && *((_DWORD *)a1 + 26) != DWORD2(v16) && KerbGlobalPackageState == 1 )
    {
      KerbTracerT::Log(1, "KerbReferenceContext", 374, "Trying to reference a context from another process!");
      v8 = 0;
LABEL_23:
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&qword_180141270[v10 / 8]);
      goto LABEL_24;
    }
    if ( KerbGlobalEnforceTime && !a2 )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( *((_QWORD *)a1 + 3) < *(__int64 *)&SystemTimeAsFileTime )
      {
        KerbTracerT::Log(2, "KerbReferenceContext", 391, "Trying to reference expired context\n");
        v8 = 0;
        v6 = -2146893033;
        goto LABEL_23;
      }
      v11 = KerbGlobalPackageState;
    }
    if ( v11 == 1
      && (v18 = 0, ((void (__fastcall *)(int *))LsaFunctions->GetExtendedCallFlags)(&v18), (v18 & 3) == 1)
      && (((unsigned __int8)v18 ^ (unsigned __int8)(*((_DWORD *)a1 + 49) >> 17)) & 4) != 0 )
    {
      KerbTracerT::Log(1, "KerbReferenceContext", 414, "Trying to change SECPKG_CALLFLAGS_FORCE_SUPPLIED\n");
      v8 = 0;
      v6 = -2146892963;
    }
    else
    {
      KerbReferenceListEntry((struct _KERBEROS_LIST *)((char *)&KerbContextList + v10), a1, a2);
      v8 = 1;
    }
    goto LABEL_23;
  }
LABEL_24:
  v12 = 0;
  if ( v8 )
    v12 = a1;
  *a3 = v12;
  if ( v12 )
  {
    KerbTracerT::SetCorrelationIdGuid((struct _GUID *)((char *)v12 + 428));
    return (unsigned int)v6;
  }
  else
  {
    if ( v6 >= 0 )
      return (unsigned int)-2146893055;
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180046e70  push    rbx
0x180046e72  push    rbp
0x180046e73  push    rdi
0x180046e74  push    r14
0x180046e76  sub     rsp, 78h
0x180046e7a  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180046e81  xorps   xmm0, xmm0
0x180046e84  movups  [rsp+98h+var_48], xmm0
0x180046e89  mov     r14, r8
0x180046e8c  movzx   ebp, dl
0x180046e8f  movups  [rsp+98h+var_38], xmm0
0x180046e94  mov     rdi, rcx
0x180046e97  jnz     loc_180046F3C
0x180046e9d  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180046ea4  lea     rcx, [rsp+98h+var_48]
0x180046ea9  mov     rax, [rax+80h]
0x180046eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046eb5  mov     ebx, eax
0x180046eb7  test    eax, eax
0x180046eb9  jns     loc_180046F48
0x180046ebf  mov     rcx, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180046ec6  xor     eax, eax
0x180046ec8  mov     [rsp+98h+var_50], rax
0x180046ecd  xorps   xmm0, xmm0
0x180046ed0  movups  [rsp+98h+var_60], xmm0
0x180046ed5  mov     rax, [rcx+0C0h]
0x180046edc  lea     rcx, [rsp+98h+var_60]
0x180046ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ee6  test    al, al
0x180046ee8  jz      short loc_180046F07
0x180046eea  test    byte ptr [rsp+98h+var_60+8], 20h
0x180046eef  jz      short loc_180046F07
0x180046ef1  xorps   xmm0, xmm0
0x180046ef4  xor     ebx, ebx
0x180046ef6  movups  [rsp+98h+var_38], xmm0
0x180046efb  mov     byte ptr [rsp+98h+var_38], 1
0x180046f00  movups  [rsp+98h+var_48], xmm0
0x180046f05  jmp     short loc_180046F48
0x180046f07  lea     r9, aFailedToGetCli_1; "Failed to get client info: 0x%x"
0x180046f0e  mov     [rsp+98h+var_78], ebx
0x180046f12  mov     r8d, 154h
0x180046f18  lea     rdx, aKerbreferencec_5; "KerbReferenceContext"
0x180046f1f  mov     ecx, 1
0x180046f24  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180046f29  mov     eax, ebx
0x180046f2b  mov     qword ptr [r14], 0
0x180046f32  add     rsp, 78h
0x180046f36  pop     r14
0x180046f38  pop     rdi
0x180046f39  pop     rbp
0x180046f3a  pop     rbx
0x180046f3b  retn
0x180046f3c  xor     ebx, ebx
0x180046f3e  call    cs:__imp_GetCurrentProcessId
0x180046f44  mov     dword ptr [rsp+98h+var_48+8], eax
0x180046f48  mov     [rsp+98h+arg_0], rsi
0x180046f50  xor     sil, sil
0x180046f53  cmp     dword ptr [rdi+170h], 41787443h
0x180046f5d  jnz     loc_1800470E7
0x180046f63  mov     edx, [rdi+68h]
0x180046f66  mov     ecx, edx
0x180046f68  shr     ecx, 18h
0x180046f6b  mov     eax, edx
0x180046f6d  shr     eax, 10h
0x180046f70  add     ecx, eax
0x180046f72  mov     [rsp+98h+arg_8], r13
0x180046f7a  mov     eax, edx
0x180046f7c  mov     [rsp+98h+var_28], r15
0x180046f81  shr     eax, 8
0x180046f84  lea     r13, ?KerbContextList@@3PAU_KERBEROS_LIST@@A; _KERBEROS_LIST near * KerbContextList
0x180046f8b  add     eax, edx
0x180046f8d  shr     edx, 4
0x180046f90  add     eax, ecx
0x180046f92  add     eax, edx
0x180046f94  mov     ecx, eax
0x180046f96  shr     ecx, 4
0x180046f99  add     ecx, eax
0x180046f9b  movzx   eax, cl
0x180046f9e  imul    r15, rax, 38h ; '8'
0x180046fa2  lea     rsi, [r15+r13]
0x180046fa6  lea     rcx, [rsi+10h]; CriticalSection
0x180046faa  call    cs:__imp_RtlEnterCriticalSection
0x180046fb0  cmp     byte ptr [rsp+98h+var_38], 0
0x180046fb5  mov     ecx, cs:?KerbGlobalPackageState@@3W4KerberosState@@A; KerberosState KerbGlobalPackageState
0x180046fbb  jnz     short loc_180046FEC
0x180046fbd  mov     eax, dword ptr [rsp+98h+var_48+8]
0x180046fc1  cmp     [rdi+68h], eax
0x180046fc4  jz      short loc_180046FEC
0x180046fc6  cmp     ecx, 1
0x180046fc9  jnz     short loc_180046FEC
0x180046fcb  lea     r9, aTryingToRefere_1; "Trying to reference a context from anot"...
0x180046fd2  mov     r8d, 176h
0x180046fd8  lea     rdx, aKerbreferencec_5; "KerbReferenceContext"
0x180046fdf  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180046fe4  xor     sil, sil
0x180046fe7  jmp     loc_1800470CD
0x180046fec  cmp     cs:?KerbGlobalEnforceTime@@3EA, 0; uchar KerbGlobalEnforceTime
0x180046ff3  jz      short loc_18004704A
0x180046ff5  test    bpl, bpl
0x180046ff8  jnz     short loc_18004704A
0x180046ffa  lea     rcx, [rsp+98h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180046fff  mov     qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180047008  call    cs:__imp_GetSystemTimeAsFileTime
0x18004700e  mov     rax, qword ptr [rsp+98h+SystemTimeAsFileTime.dwLowDateTime]
0x180047013  cmp     [rdi+18h], rax
0x180047017  jge     short loc_180047044
0x180047019  lea     r9, aTryingToRefere_0; "Trying to reference expired context\n"
0x180047020  mov     r8d, 187h
0x180047026  lea     rdx, aKerbreferencec_5; "KerbReferenceContext"
0x18004702d  mov     ecx, 2
0x180047032  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180047037  xor     sil, sil
0x18004703a  mov     ebx, 80090317h
0x18004703f  jmp     loc_1800470CD
0x180047044  mov     ecx, cs:?KerbGlobalPackageState@@3W4KerberosState@@A; KerberosState KerbGlobalPackageState
0x18004704a  cmp     ecx, 1
0x18004704d  jnz     short loc_1800470BB
0x18004704f  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180047056  lea     rcx, [rsp+98h+arg_18]
0x18004705e  mov     [rsp+98h+arg_18], 0
0x180047069  mov     rax, [rax+1B0h]
0x180047070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047075  mov     ecx, [rsp+98h+arg_18]
0x18004707c  mov     eax, ecx
0x18004707e  and     al, 3
0x180047080  cmp     al, 1
0x180047082  jnz     short loc_1800470BB
0x180047084  mov     eax, [rdi+0C4h]
0x18004708a  shr     eax, 11h
0x18004708d  xor     eax, ecx
0x18004708f  test    al, 4
0x180047091  jz      short loc_1800470BB
0x180047093  lea     r9, aTryingToChange; "Trying to change SECPKG_CALLFLAGS_FORCE"...
0x18004709a  mov     r8d, 19Eh
0x1800470a0  lea     rdx, aKerbreferencec_5; "KerbReferenceContext"
0x1800470a7  mov     ecx, 1
0x1800470ac  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800470b1  xor     sil, sil
0x1800470b4  mov     ebx, 8009035Dh
0x1800470b9  jmp     short loc_1800470CD
0x1800470bb  movzx   r8d, bpl; unsigned __int8
0x1800470bf  mov     rdx, rdi; struct _KERBEROS_LIST_ENTRY *
0x1800470c2  mov     rcx, rsi; struct _KERBEROS_LIST *
0x1800470c5  call    ?KerbReferenceListEntry@@YAXPEAU_KERBEROS_LIST@@PEAU_KERBEROS_LIST_ENTRY@@E@Z; KerbReferenceListEntry(_KERBEROS_LIST *,_KERBEROS_LIST_ENTRY *,uchar)
0x1800470ca  mov     sil, 1
0x1800470cd  lea     rcx, [r13+10h]
0x1800470d1  add     rcx, r15; CriticalSection
0x1800470d4  call    cs:__imp_RtlLeaveCriticalSection
0x1800470da  mov     r15, [rsp+98h+var_28]
0x1800470df  mov     r13, [rsp+98h+arg_8]
0x1800470e7  xor     ecx, ecx
0x1800470e9  test    sil, sil
0x1800470ec  mov     rsi, [rsp+98h+arg_0]
0x1800470f4  cmovnz  rcx, rdi
0x1800470f8  mov     [r14], rcx
0x1800470fb  test    rcx, rcx
0x1800470fe  jz      short loc_180047118
0x180047100  add     rcx, 1ACh; struct _GUID *
0x180047107  call    ?SetCorrelationIdGuid@KerbTracerT@@SAXAEAU_GUID@@@Z; KerbTracerT::SetCorrelationIdGuid(_GUID &)
0x18004710c  mov     eax, ebx
0x18004710e  add     rsp, 78h
0x180047112  pop     r14
0x180047114  pop     rdi
0x180047115  pop     rbp
0x180047116  pop     rbx
0x180047117  retn
0x180047118  mov     eax, 80090301h
0x18004711d  test    ebx, ebx
0x18004711f  cmovns  ebx, eax
0x180047122  mov     eax, ebx
0x180047124  add     rsp, 78h
0x180047128  pop     r14
0x18004712a  pop     rdi
0x18004712b  pop     rbp
0x18004712c  pop     rbx
0x18004712d  retn
```
