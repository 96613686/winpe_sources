# HyperVRepository::GetTypeName(void)

- ea: `0x180093510`
- end: `0x1800936c9`
- name: `?GetTypeName@HyperVRepository@@UEBAPEBGXZ`
- size: `441`
- prototype: `const unsigned __int16 *__fastcall(HyperVRepository *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800067c0`
- `0x18000995c`
- `0x180009e8c`
- `0x1800136d0`
- `0x18001587c`
- `0x180020c90`
- `0x18003a140`
- `0x18003aa98`
- `0x180093510`
- `0x1800942d0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009353b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009353b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009364f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009364f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180093568`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180093568`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009360f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009360f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093615`

## string_xrefs

- `0x1800935c8`: `/configuration/properties/type_id`
- `0x1800936b7`: `onecore\vm\common\repository\core\VmRepositoryUtilities.h`
- `0x180093697`: `onecore\vm\common\repository\core\hypervrepository.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
RTL_SRWLOCK *__fastcall HyperVRepository::GetTypeName(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // r14
  RTL_SRWLOCK *v3; // rdi
  RTL_SRWLOCK *Ptr; // rbx
  const struct type_info *v5; // rdx
  int v6; // eax
  int v7; // eax
  unsigned int v9; // eax
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h]
  __int64 v12; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v2 = this + 20;
  AcquireSRWLockShared(this + 20);
  v3 = this + 22;
  if ( this[24].Ptr )
  {
    if ( this[25].Ptr <= (PVOID)7 )
      Ptr = this + 22;
    else
      Ptr = (RTL_SRWLOCK *)v3->Ptr;
  }
  else
  {
    Ptr = 0;
  }
  ReleaseSRWLockShared(v2);
  if ( Ptr )
    return Ptr;
  v10 = 0;
  v11 = 0;
  v12 = 7;
  LOWORD(v10) = 0;
  Vml::VmSharableObject::AddUserInternal((Vml::VmSharableObject *)&this[1], v5);
  v6 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, _QWORD))this->Ptr + 43))(this, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
      (const char *)(unsigned int)v6,
      (int)this);
  v7 = HyperVRepository::ReadString(this, L"/configuration/properties/type_id", &v10);
  if ( v7 < 0 )
  {
    if ( v7 != -2147024894 && v7 != -2147188715 )
    {
      v9 = wil::verify_hresult<long>((unsigned int)v7);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\VmRepositoryUtilities.h",
        (const char *)v9,
        (int)this);
    }
    goto LABEL_13;
  }
  if ( !v11 )
LABEL_13:
    std::wstring::_Assign<unsigned short>(&v10, L"HyperVRepository");
  AcquireSRWLockExclusive(v2);
  LODWORD(v2[1].Ptr) = GetCurrentThreadId();
  if ( !this[24].Ptr )
    std::wstring::operator=(&this[22], &v10);
  if ( this[25].Ptr <= (PVOID)7 )
    Ptr = this + 22;
  else
    Ptr = (RTL_SRWLOCK *)v3->Ptr;
  LODWORD(v2[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v2);
  (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 5))(this);
  Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)&this[1]);
  std::wstring::~wstring(&v10);
  return Ptr;
}

```

## disassembly

```asm
0x180093510  push    rbp
0x180093512  push    rbx
0x180093513  push    rsi
0x180093514  push    rdi
0x180093515  push    r14
0x180093517  push    r15
0x180093519  mov     rbp, rsp
0x18009351c  sub     rsp, 68h
0x180093520  mov     rax, cs:__security_cookie
0x180093527  xor     rax, rsp
0x18009352a  mov     [rbp+var_18], rax
0x18009352e  mov     rsi, rcx
0x180093531  lea     r14, [rcx+0A0h]
0x180093538  mov     rcx, r14; SRWLock
0x18009353b  call    cs:__imp_AcquireSRWLockShared
0x180093541  lea     rdi, [rsi+0B0h]
0x180093548  cmp     qword ptr [rsi+0C0h], 0
0x180093550  jnz     short loc_180093556
0x180093552  xor     ebx, ebx
0x180093554  jmp     short loc_180093565
0x180093556  cmp     qword ptr [rdi+18h], 7
0x18009355b  jbe     short loc_180093562
0x18009355d  mov     rbx, [rdi]
0x180093560  jmp     short loc_180093565
0x180093562  mov     rbx, rdi
0x180093565  mov     rcx, r14; SRWLock
0x180093568  call    cs:__imp_ReleaseSRWLockShared
0x18009356e  test    rbx, rbx
0x180093571  jnz     loc_180093678
0x180093577  xorps   xmm0, xmm0
0x18009357a  movups  [rbp+var_38], xmm0
0x18009357e  mov     [rbp+var_28], rbx
0x180093582  mov     [rbp+var_20], 7
0x18009358a  xor     eax, eax
0x18009358c  mov     word ptr [rbp+var_38], ax
0x180093590  movups  [rbp+var_48], xmm0
0x180093594  mov     qword ptr [rbp+var_48], rsi
0x180093598  lea     rcx, [rsi+8]; this
0x18009359c  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x1800935a1  mov     rax, [rsi]
0x1800935a4  xor     edx, edx
0x1800935a6  mov     rcx, rsi
0x1800935a9  mov     rax, [rax+158h]
0x1800935b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800935b5  mov     dword ptr [rbp+var_48+8], eax
0x1800935b8  mov     rcx, [rbp+30h]; this
0x1800935bc  test    eax, eax
0x1800935be  js      loc_180093694
0x1800935c4  lea     r8, [rbp+var_38]
0x1800935c8  lea     rdx, ?CONFIGURATION_TYPE_ID_XPATH@@3QBGB; "/configuration/properties/type_id"
0x1800935cf  mov     rcx, rsi
0x1800935d2  call    ?ReadString@HyperVRepository@@UEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HyperVRepository::ReadString(ushort const *,std::wstring &)
0x1800935d7  test    eax, eax
0x1800935d9  jns     short loc_1800935EF
0x1800935db  cmp     eax, 80070002h
0x1800935e0  jz      short loc_1800935F6
0x1800935e2  cmp     eax, 80048015h
0x1800935e7  jnz     loc_1800936A9
0x1800935ed  jmp     short loc_1800935F6
0x1800935ef  cmp     [rbp+var_28], 0
0x1800935f4  jnz     short loc_18009360C
0x1800935f6  mov     r8d, 10h
0x1800935fc  lea     rdx, ?HYPERV_REPOSITORY_TYPE_NAME@@3QBGB; "HyperVRepository"
0x180093603  lea     rcx, [rbp+var_38]
0x180093607  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009360c  mov     rcx, r14; SRWLock
0x18009360f  call    cs:__imp_AcquireSRWLockExclusive
0x180093615  call    cs:__imp_GetCurrentThreadId
0x18009361b  mov     [r14+8], eax
0x18009361f  cmp     qword ptr [rdi+10h], 0
0x180093624  jnz     short loc_180093632
0x180093626  lea     rdx, [rbp+var_38]
0x18009362a  mov     rcx, rdi
0x18009362d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180093632  cmp     qword ptr [rsi+0C8h], 7
0x18009363a  jbe     short loc_180093641
0x18009363c  mov     rbx, [rdi]
0x18009363f  jmp     short loc_180093644
0x180093641  mov     rbx, rdi
0x180093644  mov     dword ptr [r14+8], 0
0x18009364c  mov     rcx, r14; SRWLock
0x18009364f  call    cs:__imp_ReleaseSRWLockExclusive
0x180093655  nop
0x180093656  mov     rdx, [rsi]
0x180093659  mov     rcx, rsi
0x18009365c  mov     rax, [rdx+28h]
0x180093660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093665  lea     rcx, [rsi+8]; this
0x180093669  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x18009366e  nop
0x18009366f  lea     rcx, [rbp+var_38]
0x180093673  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180093678  mov     rax, rbx
0x18009367b  mov     rcx, [rbp+var_18]
0x18009367f  xor     rcx, rsp; StackCookie
0x180093682  call    __security_check_cookie
0x180093687  add     rsp, 68h
0x18009368b  pop     r15
0x18009368d  pop     r14
0x18009368f  pop     rdi
0x180093690  pop     rsi
0x180093691  pop     rbx
0x180093692  pop     rbp
0x180093693  retn
0x180093694  mov     r9d, eax; char *
0x180093697  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\repository\\core\\"...
0x18009369e  mov     edx, 118h; void *
0x1800936a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800936a9  mov     ecx, eax
0x1800936ab  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800936b0  mov     r9d, eax; char *
0x1800936b3  mov     rcx, [rbp+30h]; this
0x1800936b7  lea     r8, aOnecoreVmCommo_32; "onecore\\vm\\common\\repository\\core\\"...
0x1800936be  mov     edx, 24h ; '$'; void *
0x1800936c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
