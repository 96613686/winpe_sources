# CCacheMutex::SetName(ushort const *,ushort const *,ushort const *)

- ea: `0x14002c1e0`
- end: `0x14002c30c`
- name: `?SetName@CCacheMutex@@QEAAJPEBG00@Z`
- size: `300`
- prototype: `int(CCacheMutex *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002bff0`

## callees

- `0x140002c10`
- `0x140007740`
- `0x14002c1e0`
- `0x140033ab0`
- `0x140046514`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x14002c21e`
- `KERNEL32!lstrlenW` at `0x14002c22f`
- `KERNEL32!lstrlenW` at `0x14002c21e`
- `KERNEL32!lstrlenW` at `0x14002c22f`
- `KERNEL32!CreateMutexW` at `0x14002c285`
- `KERNEL32!CreateMutexW` at `0x14002c285`
- `KERNEL32!GetLastError` at `0x14002c298`
- `KERNEL32!GetLastError` at `0x14002c298`

## string_xrefs

- `0x14002c2b8`: `Failed to create PkgDef mutex`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCacheMutex::SetName(
        CCacheMutex *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  const unsigned __int16 *v9; // rbx
  HANDLE MutexW; // rax
  signed int v11; // edi
  signed int LastError; // eax
  LPCWSTR lpName; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 || !a3 || !a4 || lstrlenW(a2) <= 0 || lstrlenW(a4) <= 0 )
    return 2147942487LL;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  lpName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpName,
    L"Local\\PkgDefMutex_%s_%s_%s",
    a4,
    a2,
    a3);
  v9 = lpName;
  MutexW = CreateMutexW(0, 0, lpName);
  *((_QWORD *)this + 1) = MutexW;
  if ( MutexW )
  {
    v11 = 0;
  }
  else
  {
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    if ( v11 < 0 )
    {
      _mm_lfence();
      CLogger::LogError(L"Failed to create PkgDef mutex", v11, v9);
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002c1e0  mov     [rsp+arg_0], rbx
0x14002c1e5  mov     [rsp+arg_10], rbp
0x14002c1ea  mov     [rsp+arg_18], rsi
0x14002c1ef  push    rdi
0x14002c1f0  sub     rsp, 30h
0x14002c1f4  mov     rbx, r9
0x14002c1f7  mov     rsi, r8
0x14002c1fa  mov     rdi, rdx
0x14002c1fd  mov     rbp, rcx
0x14002c200  test    rdx, rdx
0x14002c203  jz      loc_14002C2E7
0x14002c209  test    r8, r8
0x14002c20c  jz      loc_14002C2E7
0x14002c212  test    rbx, rbx
0x14002c215  jz      loc_14002C2E7
0x14002c21b  mov     rcx, rdx; lpString
0x14002c21e  call    cs:__imp_lstrlenW
0x14002c224  test    eax, eax
0x14002c226  jle     loc_14002C2E7
0x14002c22c  mov     rcx, rbx; lpString
0x14002c22f  call    cs:__imp_lstrlenW
0x14002c235  test    eax, eax
0x14002c237  jle     loc_14002C2E7
0x14002c23d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002c242  mov     rcx, rax
0x14002c245  test    rax, rax
0x14002c248  jz      loc_14002C301
0x14002c24e  mov     rax, [rax]
0x14002c251  call    qword ptr [rax+18h]
0x14002c254  add     rax, 18h
0x14002c258  mov     [rsp+38h+lpName], rax
0x14002c25d  mov     [rsp+38h+var_18], rsi
0x14002c262  mov     r9, rdi
0x14002c265  mov     r8, rbx
0x14002c268  lea     rdx, aLocalPkgdefmut; "Local\\PkgDefMutex_%s_%s_%s"
0x14002c26f  lea     rcx, [rsp+38h+lpName]
0x14002c274  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14002c279  mov     rbx, [rsp+38h+lpName]
0x14002c27e  mov     r8, rbx; lpName
0x14002c281  xor     edx, edx; bInitialOwner
0x14002c283  xor     ecx, ecx; lpMutexAttributes
0x14002c285  call    cs:__imp_CreateMutexW
0x14002c28b  mov     [rbp+8], rax
0x14002c28f  test    rax, rax
0x14002c292  jz      short loc_14002C298
0x14002c294  xor     edi, edi
0x14002c296  jmp     short loc_14002C2C5
0x14002c298  call    cs:__imp_GetLastError
0x14002c29e  movzx   edi, ax
0x14002c2a1  or      edi, 80070000h
0x14002c2a7  test    eax, eax
0x14002c2a9  cmovle  edi, eax
0x14002c2ac  test    edi, edi
0x14002c2ae  jns     short loc_14002C2C5
0x14002c2b0  lfence
0x14002c2b3  mov     r8, rbx; unsigned __int16 *
0x14002c2b6  mov     edx, edi; int
0x14002c2b8  lea     rcx, aFailedToCreate_0; "Failed to create PkgDef mutex"
0x14002c2bf  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14002c2c4  nop
0x14002c2c5  lea     rdx, [rbx-18h]
0x14002c2c9  or      ecx, 0FFFFFFFFh
0x14002c2cc  lock xadd [rdx+10h], ecx
0x14002c2d1  sub     ecx, 1
0x14002c2d4  jg      short loc_14002C2E3
0x14002c2d6  lfence
0x14002c2d9  mov     rcx, [rdx]
0x14002c2dc  mov     r8, [rcx]
0x14002c2df  call    qword ptr [r8+8]
0x14002c2e3  mov     eax, edi
0x14002c2e5  jmp     short loc_14002C2EC
0x14002c2e7  mov     eax, 80070057h
0x14002c2ec  mov     rbx, [rsp+38h+arg_0]
0x14002c2f1  mov     rbp, [rsp+38h+arg_10]
0x14002c2f6  mov     rsi, [rsp+38h+arg_18]
0x14002c2fb  add     rsp, 30h
0x14002c2ff  pop     rdi
0x14002c300  retn
0x14002c301  mov     ecx, 80004005h; int
0x14002c306  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
