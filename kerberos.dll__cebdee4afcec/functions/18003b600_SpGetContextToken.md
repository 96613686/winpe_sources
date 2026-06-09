# SpGetContextToken

- ea: `0x18003b600`
- end: `0x18003b7d2`
- name: `SpGetContextToken`
- size: `466`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180006680`
- `0x18003b600`
- `0x180047140`
- `0x180081690`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b63b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b78b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b63b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b78b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b6f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b6f0`
- `ntdll!RtlReleaseResource` at `0x18003b71c`
- `ntdll!RtlReleaseResource` at `0x18003b71c`
- `ntdll!RtlAcquireResourceShared` at `0x18003b6ff`
- `ntdll!RtlAcquireResourceShared` at `0x18003b6ff`

## string_xrefs

- `0x18003b641`: `SpGetContextToken called pid:0x%x, ctxt:%p\n`
- `0x18003b657`: `SpGetContextToken`
- `0x18003b67a`: `SpGetContextToken`
- `0x18003b750`: `SpGetContextToken`
- `0x18003b7a1`: `SpGetContextToken`
- `0x18003b66d`: `Null token handle supplied for GetContextToken`
- `0x18003b73e`: `GetContextToken: Context %p expired`
- `0x18003b796`: `SpGetContextToken returned 0x%x, pid:0x%x, ctxt:%p\n`

## pseudocode

```c
__int64 __fastcall SpGetContextToken(unsigned __int64 a1, _QWORD *a2)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v4; // rdi
  const void *v5; // rbx
  DWORD CurrentProcessId; // eax
  int v7; // ebx
  struct _KERB_CONTEXT *v8; // rbp
  __int64 v9; // r15
  unsigned __int64 v10; // rax
  DWORD v11; // eax
  struct _KERB_CONTEXT *v13; // [rsp+70h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp+10h] BYREF

  v13 = 0;
  v2 = a1 >> 16;
  SystemTimeAsFileTime = 0;
  v4 = a1;
  if ( a1 )
    v5 = (const void *)WORD1(a1);
  else
    v5 = 0;
  CurrentProcessId = GetCurrentProcessId();
  KerbTracerT::Log(7, "SpGetContextToken", 1045, "SpGetContextToken called pid:0x%x, ctxt:%p\n", CurrentProcessId, v5);
  if ( a2 )
  {
    v7 = KerbReferenceContextByLsaHandle(v4, 0, &v13);
    if ( v7 >= 0 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      RtlAcquireResourceShared(&KerbContextResource, 1u);
      v8 = v13;
      *a2 = *((_QWORD *)v13 + 15);
      v9 = *((_QWORD *)v8 + 3);
      RtlReleaseResource(&KerbContextResource);
      if ( KerbGlobalEnforceTime && v9 < *(_QWORD *)&SystemTimeAsFileTime )
      {
        if ( v4 )
          v10 = (unsigned __int16)v2;
        else
          v10 = 0;
        KerbTracerT::Log(1, "SpGetContextToken", 1076, "GetContextToken: Context %p expired", (const void *)v10);
        v7 = -2146893033;
        *a2 = 0;
      }
      else if ( !*a2 )
      {
        v7 = -2146893045;
      }
      KerbDereferenceContext(v8);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_95d87aeda44130b8efc295250a7df1d2_Traceguids, v4, v7);
    }
  }
  else
  {
    v7 = -1073741811;
    KerbTracerT::Log(1, "SpGetContextToken", 1050, "Null token handle supplied for GetContextToken");
  }
  if ( v4 )
    v4 = (unsigned __int16)v2;
  v11 = GetCurrentProcessId();
  KerbTracerT::Log(
    7,
    "SpGetContextToken",
    1097,
    "SpGetContextToken returned 0x%x, pid:0x%x, ctxt:%p\n",
    v7,
    v11,
    (const void *)v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003b600  mov     [rsp+arg_10], rbx
0x18003b605  push    rbp
0x18003b606  push    rsi
0x18003b607  push    rdi
0x18003b608  push    r14
0x18003b60a  push    r15
0x18003b60c  sub     rsp, 40h
0x18003b610  mov     rsi, rcx
0x18003b613  mov     [rsp+68h+arg_0], 0
0x18003b61c  shr     rsi, 10h
0x18003b620  mov     r14, rdx
0x18003b623  mov     qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003b62c  mov     rdi, rcx
0x18003b62f  test    rcx, rcx
0x18003b632  jz      short loc_18003B639
0x18003b634  movzx   ebx, si
0x18003b637  jmp     short loc_18003B63B
0x18003b639  xor     ebx, ebx
0x18003b63b  call    cs:__imp_GetCurrentProcessId
0x18003b641  lea     r9, aSpgetcontextto_1; "SpGetContextToken called pid:0x%x, ctxt"...
0x18003b648  mov     [rsp+68h+var_40], rbx
0x18003b64d  mov     r8d, 415h
0x18003b653  mov     dword ptr [rsp+68h+var_48], eax
0x18003b657  lea     rdx, aSpgetcontextto; "SpGetContextToken"
0x18003b65e  mov     ecx, 7
0x18003b663  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003b668  test    r14, r14
0x18003b66b  jnz     short loc_18003B694
0x18003b66d  lea     r9, aNullTokenHandl; "Null token handle supplied for GetConte"...
0x18003b674  mov     r8d, 41Ah
0x18003b67a  lea     rdx, aSpgetcontextto; "SpGetContextToken"
0x18003b681  mov     ebx, 0C000000Dh
0x18003b686  lea     ecx, [r14+1]
0x18003b68a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003b68f  jmp     loc_18003B783
0x18003b694  lea     r8, [rsp+68h+arg_0]; struct _KERB_CONTEXT **
0x18003b699  xor     edx, edx; unsigned __int8
0x18003b69b  mov     rcx, rdi; unsigned __int64
0x18003b69e  call    ?KerbReferenceContextByLsaHandle@@YAJ_KEPEAPEAU_KERB_CONTEXT@@@Z; KerbReferenceContextByLsaHandle(unsigned __int64,uchar,_KERB_CONTEXT * *)
0x18003b6a3  mov     ebx, eax
0x18003b6a5  test    eax, eax
0x18003b6a7  jns     short loc_18003B6EB
0x18003b6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6b0  lea     rax, WPP_GLOBAL_Control
0x18003b6b7  cmp     rcx, rax
0x18003b6ba  jz      loc_18003B783
0x18003b6c0  test    byte ptr [rcx+1Ch], 1
0x18003b6c4  jz      loc_18003B783
0x18003b6ca  mov     rcx, [rcx+10h]
0x18003b6ce  lea     r8, WPP_95d87aeda44130b8efc295250a7df1d2_Traceguids
0x18003b6d5  mov     edx, 10h
0x18003b6da  mov     dword ptr [rsp+68h+var_48], ebx
0x18003b6de  mov     r9, rdi
0x18003b6e1  call    WPP_SF_qD
0x18003b6e6  jmp     loc_18003B783
0x18003b6eb  lea     rcx, [rsp+68h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003b6f0  call    cs:__imp_GetSystemTimeAsFileTime
0x18003b6f6  mov     dl, 1; Wait
0x18003b6f8  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18003b6ff  call    cs:__imp_RtlAcquireResourceShared
0x18003b705  mov     rbp, [rsp+68h+arg_0]
0x18003b70a  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18003b711  mov     rax, [rbp+78h]
0x18003b715  mov     [r14], rax
0x18003b718  mov     r15, [rbp+18h]
0x18003b71c  call    cs:__imp_RtlReleaseResource
0x18003b722  cmp     cs:?KerbGlobalEnforceTime@@3EA, 0; uchar KerbGlobalEnforceTime
0x18003b729  jz      short loc_18003B76F
0x18003b72b  cmp     r15, qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime]
0x18003b730  jge     short loc_18003B76F
0x18003b732  test    rdi, rdi
0x18003b735  jz      short loc_18003B73C
0x18003b737  movzx   eax, si
0x18003b73a  jmp     short loc_18003B73E
0x18003b73c  xor     eax, eax
0x18003b73e  lea     r9, aGetcontexttoke; "GetContextToken: Context %p expired"
0x18003b745  mov     [rsp+68h+var_48], rax
0x18003b74a  mov     r8d, 434h
0x18003b750  lea     rdx, aSpgetcontextto; "SpGetContextToken"
0x18003b757  mov     ecx, 1
0x18003b75c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003b761  mov     ebx, 80090317h
0x18003b766  mov     qword ptr [r14], 0
0x18003b76d  jmp     short loc_18003B77B
0x18003b76f  cmp     qword ptr [r14], 0
0x18003b773  mov     eax, 8009030Bh
0x18003b778  cmovz   ebx, eax
0x18003b77b  mov     rcx, rbp; this
0x18003b77e  call    ?KerbDereferenceContext@@YAXPEAU_KERB_CONTEXT@@@Z; KerbDereferenceContext(_KERB_CONTEXT *)
0x18003b783  test    rdi, rdi
0x18003b786  jz      short loc_18003B78B
0x18003b788  movzx   edi, si
0x18003b78b  call    cs:__imp_GetCurrentProcessId
0x18003b791  mov     [rsp+68h+var_38], rdi
0x18003b796  lea     r9, aSpgetcontextto_0; "SpGetContextToken returned 0x%x, pid:0x"...
0x18003b79d  mov     dword ptr [rsp+68h+var_40], eax
0x18003b7a1  lea     rdx, aSpgetcontextto; "SpGetContextToken"
0x18003b7a8  mov     r8d, 449h
0x18003b7ae  mov     dword ptr [rsp+68h+var_48], ebx
0x18003b7b2  mov     ecx, 7
0x18003b7b7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18003b7bc  mov     eax, ebx
0x18003b7be  mov     rbx, [rsp+68h+arg_10]
0x18003b7c6  add     rsp, 40h
0x18003b7ca  pop     r15
0x18003b7cc  pop     r14
0x18003b7ce  pop     rdi
0x18003b7cf  pop     rsi
0x18003b7d0  pop     rbp
0x18003b7d1  retn
```
