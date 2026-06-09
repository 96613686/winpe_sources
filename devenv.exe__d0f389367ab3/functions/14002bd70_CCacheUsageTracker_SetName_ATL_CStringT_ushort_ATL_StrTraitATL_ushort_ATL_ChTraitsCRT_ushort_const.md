# CCacheUsageTracker::SetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14002bd70`
- end: `0x14002bf32`
- name: `?SetName@CCacheUsageTracker@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `450`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002bc80`
- `0x14002c310`
- `0x140051c20`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140007740`
- `0x14000f478`
- `0x140014e5c`
- `0x14002bd70`
- `0x14002bf34`
- `0x140033ab0`
- `0x140046514`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14002be66`
- `KERNEL32!LocalFree` at `0x14002be66`
- `KERNEL32!CreateSemaphoreW` at `0x14002be58`
- `KERNEL32!CreateSemaphoreW` at `0x14002be58`
- `KERNEL32!CloseHandle` at `0x14002bda5`
- `KERNEL32!CloseHandle` at `0x14002bda5`
- `KERNEL32!GetLastError` at `0x14002bddb`
- `KERNEL32!GetLastError` at `0x14002be73`
- `KERNEL32!GetLastError` at `0x14002be88`
- `KERNEL32!GetLastError` at `0x14002beab`
- `KERNEL32!GetLastError` at `0x14002bddb`
- `KERNEL32!GetLastError` at `0x14002be73`
- `KERNEL32!GetLastError` at `0x14002be88`
- `KERNEL32!GetLastError` at `0x14002beab`

## string_xrefs

- `0x14002be9f`: `Failed to create/obtain PkgDef Semaphore`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCacheUsageTracker::SetName(__int64 a1, _QWORD *a2)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  char UserIdString; // al
  int *v6; // rdi
  signed int LastError; // eax
  unsigned int v8; // esi
  struct ATL::IAtlStringMgr *v9; // rax
  char v10; // al
  const unsigned __int16 *v11; // rbx
  signed int v12; // eax
  unsigned int v13; // edx
  signed int v14; // eax
  int *v16; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR lpName; // [rsp+28h] [rbp-28h] BYREF
  struct _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+30h] [rbp-20h] BYREF

  if ( *(_QWORD *)(a1 + 8) )
  {
    CCacheUsageTracker::SetInUseFlag((CCacheUsageTracker *)a1, 0);
    CloseHandle(*(HANDLE *)(a1 + 8));
  }
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v16 = (int *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  UserIdString = GetUserIdString(&v16);
  v6 = v16;
  if ( !UserIdString )
  {
    LastError = GetLastError();
    v8 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v8 = LastError;
    goto LABEL_19;
  }
  v9 = ATL::CAtlStringMgr::GetInstance();
  if ( !v9 )
    ATL::AtlThrowImpl(-2147467259);
  lpName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v9 + 24LL))(v9) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpName,
    L"Global\\%s:%s",
    v6,
    *a2);
  SemaphoreAttributes.nLength = 24;
  SemaphoreAttributes.bInheritHandle = 0;
  v10 = CreateMyDACL(&v16, &SemaphoreAttributes);
  v11 = lpName;
  if ( !v10 )
    goto LABEL_15;
  *(_QWORD *)(a1 + 8) = CreateSemaphoreW(&SemaphoreAttributes, 500000, 500000, lpName);
  LocalFree(SemaphoreAttributes.lpSecurityDescriptor);
  if ( !*(_QWORD *)(a1 + 8) )
  {
    v12 = GetLastError();
    v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 <= 0 )
      v13 = v12;
    CLogger::LogError(L"Failed to create/obtain PkgDef Semaphore", v13, v11);
LABEL_15:
    v14 = GetLastError();
    v8 = (unsigned __int16)v14 | 0x80070000;
    if ( v14 <= 0 )
      v8 = v14;
    goto LABEL_17;
  }
  *(_BYTE *)(a1 + 16) = GetLastError() != 183;
  v8 = 0;
LABEL_17:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  }
LABEL_19:
  if ( _InterlockedExchangeAdd(v6 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 - 3) + 8LL))(*((_QWORD *)v6 - 3));
  }
  return v8;
}

```

## disassembly

```asm
0x14002bd70  mov     [rsp-18h+arg_10], rbx
0x14002bd75  push    rbp
0x14002bd76  push    rsi
0x14002bd77  push    rdi
0x14002bd78  mov     rbp, rsp
0x14002bd7b  sub     rsp, 50h
0x14002bd7f  mov     rax, cs:__security_cookie
0x14002bd86  xor     rax, rsp
0x14002bd89  mov     [rbp+var_8], rax
0x14002bd8d  mov     rbx, rdx
0x14002bd90  mov     rsi, rcx
0x14002bd93  cmp     qword ptr [rcx+8], 0
0x14002bd98  jz      short loc_14002BDAB
0x14002bd9a  xor     edx, edx; bool
0x14002bd9c  call    ?SetInUseFlag@CCacheUsageTracker@@QEAAJ_N@Z; CCacheUsageTracker::SetInUseFlag(bool)
0x14002bda1  mov     rcx, [rsi+8]; hObject
0x14002bda5  call    cs:__imp_CloseHandle
0x14002bdab  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002bdb0  mov     rcx, rax
0x14002bdb3  test    rax, rax
0x14002bdb6  jz      loc_14002BF27
0x14002bdbc  mov     rax, [rax]
0x14002bdbf  call    qword ptr [rax+18h]
0x14002bdc2  add     rax, 18h
0x14002bdc6  mov     [rbp+var_30], rax
0x14002bdca  lea     rcx, [rbp+var_30]
0x14002bdce  call    GetUserIdString
0x14002bdd3  mov     rdi, [rbp+var_30]
0x14002bdd7  test    al, al
0x14002bdd9  jnz     short loc_14002BDF4
0x14002bddb  call    cs:__imp_GetLastError
0x14002bde1  movzx   esi, ax
0x14002bde4  or      esi, 80070000h
0x14002bdea  test    eax, eax
0x14002bdec  cmovle  esi, eax
0x14002bdef  jmp     loc_14002BEDD
0x14002bdf4  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002bdf9  mov     rcx, rax
0x14002bdfc  test    rax, rax
0x14002bdff  jz      loc_14002BF19
0x14002be05  mov     rax, [rax]
0x14002be08  call    qword ptr [rax+18h]
0x14002be0b  add     rax, 18h
0x14002be0f  mov     [rbp+lpName], rax
0x14002be13  mov     r9, [rbx]
0x14002be16  mov     r8, rdi
0x14002be19  lea     rdx, aGlobalSS; "Global\\%s:%s"
0x14002be20  lea     rcx, [rbp+lpName]
0x14002be24  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14002be29  mov     [rbp+SemaphoreAttributes.nLength], 18h
0x14002be30  and     [rbp+SemaphoreAttributes.bInheritHandle], 0
0x14002be34  lea     rdx, [rbp+SemaphoreAttributes]
0x14002be38  lea     rcx, [rbp+var_30]
0x14002be3c  call    CreateMyDACL
0x14002be41  mov     rbx, [rbp+lpName]
0x14002be45  test    al, al
0x14002be47  jz      short loc_14002BEAB
0x14002be49  mov     r9, rbx; lpName
0x14002be4c  mov     edx, 7A120h; lInitialCount
0x14002be51  mov     r8d, edx; lMaximumCount
0x14002be54  lea     rcx, [rbp+SemaphoreAttributes]; lpSemaphoreAttributes
0x14002be58  call    cs:__imp_CreateSemaphoreW
0x14002be5e  mov     [rsi+8], rax
0x14002be62  mov     rcx, [rbp+SemaphoreAttributes.lpSecurityDescriptor]; hMem
0x14002be66  call    cs:__imp_LocalFree
0x14002be6c  cmp     qword ptr [rsi+8], 0
0x14002be71  jz      short loc_14002BE88
0x14002be73  call    cs:__imp_GetLastError
0x14002be79  cmp     eax, 0B7h
0x14002be7e  setnz   al
0x14002be81  mov     [rsi+10h], al
0x14002be84  xor     esi, esi
0x14002be86  jmp     short loc_14002BEBF
0x14002be88  call    cs:__imp_GetLastError
0x14002be8e  movzx   edx, ax
0x14002be91  or      edx, 80070000h
0x14002be97  test    eax, eax
0x14002be99  cmovle  edx, eax; int
0x14002be9c  mov     r8, rbx; unsigned __int16 *
0x14002be9f  lea     rcx, aFailedToCreate; "Failed to create/obtain PkgDef Semaphor"...
0x14002bea6  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14002beab  call    cs:__imp_GetLastError
0x14002beb1  movzx   esi, ax
0x14002beb4  or      esi, 80070000h
0x14002beba  test    eax, eax
0x14002bebc  cmovle  esi, eax
0x14002bebf  lea     rdx, [rbx-18h]
0x14002bec3  or      eax, 0FFFFFFFFh
0x14002bec6  lock xadd [rdx+10h], eax
0x14002becb  sub     eax, 1
0x14002bece  jg      short loc_14002BEDD
0x14002bed0  lfence
0x14002bed3  mov     rcx, [rdx]
0x14002bed6  mov     rax, [rcx]
0x14002bed9  call    qword ptr [rax+8]
0x14002bedc  nop
0x14002bedd  lea     rdx, [rdi-18h]
0x14002bee1  or      ecx, 0FFFFFFFFh
0x14002bee4  lock xadd [rdx+10h], ecx
0x14002bee9  sub     ecx, 1
0x14002beec  jg      short loc_14002BEFB
0x14002beee  lfence
0x14002bef1  mov     rcx, [rdx]
0x14002bef4  mov     r8, [rcx]
0x14002bef7  call    qword ptr [r8+8]
0x14002befb  mov     eax, esi
0x14002befd  mov     rcx, [rbp+var_8]
0x14002bf01  xor     rcx, rsp; StackCookie
0x14002bf04  call    __security_check_cookie
0x14002bf09  mov     rbx, [rsp+50h+arg_10]
0x14002bf11  add     rsp, 50h
0x14002bf15  pop     rdi
0x14002bf16  pop     rsi
0x14002bf17  pop     rbp
0x14002bf18  retn
0x14002bf19  mov     ecx, 80004005h; int
0x14002bf1e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002bf24  jmp     short $+2
0x14002bf26  nop
0x14002bf27  mov     ecx, 80004005h; int
0x14002bf2c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
