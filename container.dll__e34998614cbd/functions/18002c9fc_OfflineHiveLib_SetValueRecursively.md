# OfflineHiveLib::SetValueRecursively

- ea: `0x18002c9fc`
- end: `0x18002ccce`
- name: `OfflineHiveLib::SetValueRecursively`
- size: `722`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024700`
- `0x18002c9fc`

## callees

- `0x180002640`
- `0x180002ad0`
- `0x1800051b0`
- `0x18000ca10`
- `0x1800120d0`
- `0x180012b10`
- `0x18002c9fc`
- `0x18002cd74`
- `0x18002cdfc`
- `0x18002d56c`
- `0x18002d9b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002caf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002caf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cb08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cb77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cb08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cb77`

## string_xrefs

- `0x18002cc92`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`
- `0x18002cca7`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`
- `0x18002ccbc`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OfflineHiveLib::SetValueRecursively(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v5; // r15
  __int64 v9; // rax
  _QWORD *v10; // r14
  char *v11; // rbx
  __int64 trivial_2; // rax
  __int64 v13; // rsi
  int *v14; // rdx
  __int64 v15; // r15
  DWORD LastError; // ebx
  int *v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // r15
  DWORD v20; // ebx
  int *v21; // rdx
  unsigned int v22; // eax
  unsigned __int64 v23; // rsi
  unsigned __int64 v24; // rax
  __int64 v25; // rbx
  _QWORD *v27; // rdx
  unsigned int v28; // eax
  wil::details::in1diag3 *v29; // rcx
  unsigned int pSecurityDescriptor; // [rsp+20h] [rbp-71h]
  __int64 v31; // [rsp+40h] [rbp-51h] BYREF
  __int64 v32; // [rsp+48h] [rbp-49h]
  __int128 v33; // [rsp+50h] [rbp-41h] BYREF
  __int64 v34; // [rsp+60h] [rbp-31h]
  __int64 v35; // [rsp+68h] [rbp-29h]
  _QWORD *v36; // [rsp+70h] [rbp-21h]
  int v37[4]; // [rsp+78h] [rbp-19h] BYREF
  __int128 v38; // [rsp+88h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v5 = a4;
  v32 = a4;
  v36 = a2;
  v9 = a2[2];
  if ( a2[3] <= 7u )
    v10 = a2;
  else
    v10 = (_QWORD *)*a2;
  if ( v9 )
  {
    v11 = (char *)v10 + 2 * v9;
    trivial_2 = _std_find_trivial_2(v10, v11, 92);
    if ( (char *)trivial_2 != v11 )
    {
      v13 = (trivial_2 - (__int64)v10) >> 1;
      if ( v13 != -1 )
      {
        *(_OWORD *)v37 = 0;
        v38 = 0;
        std::wstring::_Construct<1,unsigned short const *>(v37);
        v31 = 0;
        v14 = v37;
        if ( *((_QWORD *)&v38 + 1) > 7u )
          v14 = *(int **)v37;
        if ( (unsigned int)OROpenKey(a1, v14, &v31) )
        {
          v15 = v31;
          if ( v31 )
          {
            LastError = GetLastError();
            ORCloseKey(v15);
            SetLastError(LastError);
          }
          v31 = 0;
          v17 = v37;
          if ( *((_QWORD *)&v38 + 1) > 7u )
            v17 = *(int **)v37;
          v18 = ORCreateKey(a1, v17, 0, 0, 0, &v31, 0);
          if ( v18 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x6D2,
              (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
              (const char *)v18,
              pSecurityDescriptor);
          v19 = v31;
          if ( v31 )
          {
            v20 = GetLastError();
            ORCloseKey(v19);
            SetLastError(v20);
          }
          v31 = 0;
          v21 = v37;
          if ( *((_QWORD *)&v38 + 1) > 7u )
            v21 = *(int **)v37;
          v22 = OROpenKey(a1, v21, &v31);
          if ( v22 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x6D5,
              (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
              (const char *)v22,
              pSecurityDescriptor);
          LODWORD(v5) = v32;
        }
        v23 = v13 + 1;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        v24 = a2[2];
        if ( v24 >= v23 )
        {
          std::wstring::_Construct<1,unsigned short const *>(&v33);
          v25 = v31;
          OfflineHiveLib::SetValueRecursively(v31, (unsigned int)&v33, a3, v5, a5);
          std::wstring::~wstring(v37);
          if ( v25 )
            ORCloseKey(v25);
          return std::wstring::~wstring(a2);
        }
        v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
LABEL_31:
        wil::details::in1diag3::Throw_Win32(
          v29,
          (void *)0x6BC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
          (const char *)v28,
          pSecurityDescriptor);
      }
    }
  }
  if ( a2[3] <= 7u )
    v27 = a2;
  else
    v27 = (_QWORD *)*a2;
  pSecurityDescriptor = a5;
  v28 = ORSetValueInternal(a1, v27, a3, v5);
  v29 = retaddr;
  if ( v28 )
    goto LABEL_31;
  return std::wstring::~wstring(a2);
}

```

## disassembly

```asm
0x18002c9fc  push    rbp
0x18002c9fe  push    rbx
0x18002c9ff  push    rsi
0x18002ca00  push    rdi
0x18002ca01  push    r12
0x18002ca03  push    r13
0x18002ca05  push    r14
0x18002ca07  push    r15
0x18002ca09  lea     rbp, [rsp-17h]
0x18002ca0e  sub     rsp, 0A8h
0x18002ca15  mov     rax, cs:__security_cookie
0x18002ca1c  xor     rax, rsp
0x18002ca1f  mov     [rbp+4Fh+var_48], rax
0x18002ca23  mov     r15, r9
0x18002ca26  mov     [rbp+4Fh+var_98], r9
0x18002ca2a  mov     r13d, r8d
0x18002ca2d  mov     rdi, rdx
0x18002ca30  mov     r12, rcx
0x18002ca33  mov     [rbp+4Fh+var_70], rdx
0x18002ca37  mov     rax, [rdx+10h]
0x18002ca3b  cmp     qword ptr [rdx+18h], 7
0x18002ca40  jbe     short loc_18002CA47
0x18002ca42  mov     r14, [rdx]
0x18002ca45  jmp     short loc_18002CA4A
0x18002ca47  mov     r14, rdi
0x18002ca4a  test    rax, rax
0x18002ca4d  jz      loc_18002CC5B
0x18002ca53  lea     rbx, [r14+rax*2]
0x18002ca57  mov     r8d, 5Ch ; '\'
0x18002ca5d  mov     rdx, rbx
0x18002ca60  mov     rcx, r14
0x18002ca63  call    __std_find_trivial_2
0x18002ca68  mov     rsi, rax
0x18002ca6b  cmp     rax, rbx
0x18002ca6e  jz      loc_18002CC5B
0x18002ca74  sub     rsi, r14
0x18002ca77  sar     rsi, 1
0x18002ca7a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002ca7e  cmp     rsi, r14
0x18002ca81  jz      loc_18002CC5B
0x18002ca87  xor     ebx, ebx
0x18002ca89  mov     [rbp+4Fh+var_A0], rbx
0x18002ca8d  xorps   xmm0, xmm0
0x18002ca90  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x18002ca94  xorps   xmm1, xmm1
0x18002ca97  movdqu  [rbp+4Fh+var_58], xmm1
0x18002ca9c  mov     r8, rsi
0x18002ca9f  cmp     [rdi+10h], rsi
0x18002caa3  cmovb   r8, [rdi+10h]
0x18002caa8  cmp     qword ptr [rdi+18h], 7
0x18002caad  jbe     short loc_18002CAB4
0x18002caaf  mov     rdx, [rdi]
0x18002cab2  jmp     short loc_18002CAB7
0x18002cab4  mov     rdx, rdi
0x18002cab7  lea     rcx, [rbp+4Fh+var_68]
0x18002cabb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cac0  nop
0x18002cac1  mov     [rbp+4Fh+var_A0], rbx
0x18002cac5  lea     rdx, [rbp+4Fh+var_68]
0x18002cac9  cmp     qword ptr [rbp+4Fh+var_58+8], 7
0x18002cace  cmova   rdx, qword ptr [rbp+4Fh+var_68]
0x18002cad3  lea     r8, [rbp+4Fh+var_A0]
0x18002cad7  mov     rcx, r12
0x18002cada  call    OROpenKey
0x18002cadf  test    eax, eax
0x18002cae1  jz      loc_18002CBB4
0x18002cae7  mov     r15, [rbp+4Fh+var_A0]
0x18002caeb  test    r15, r15
0x18002caee  jz      short loc_18002CB17
0x18002caf0  call    cs:__imp_GetLastError
0x18002caf7  nop     dword ptr [rax+rax+00h]
0x18002cafc  mov     ebx, eax
0x18002cafe  mov     rcx, r15
0x18002cb01  call    ORCloseKey
0x18002cb06  mov     ecx, ebx; dwErrCode
0x18002cb08  call    cs:__imp_SetLastError
0x18002cb0f  nop     dword ptr [rax+rax+00h]
0x18002cb14  nop
0x18002cb15  xor     ebx, ebx
0x18002cb17  mov     [rbp+4Fh+var_A0], rbx
0x18002cb1b  lea     rdx, [rbp+4Fh+var_68]
0x18002cb1f  cmp     qword ptr [rbp+4Fh+var_58+8], 7
0x18002cb24  cmova   rdx, qword ptr [rbp+4Fh+var_68]; int
0x18002cb29  mov     [rsp+0E0h+var_B0], rbx; __int64
0x18002cb2e  lea     rax, [rbp+4Fh+var_A0]
0x18002cb32  mov     [rsp+0E0h+var_B8], rax; __int64
0x18002cb37  mov     [rsp+0E0h+pSecurityDescriptor], rbx; unsigned int
0x18002cb3c  xor     r9d, r9d; int
0x18002cb3f  xor     r8d, r8d; int
0x18002cb42  mov     rcx, r12; int
0x18002cb45  call    ORCreateKey
0x18002cb4a  mov     rcx, [rbp+57h]; this
0x18002cb4e  test    eax, eax
0x18002cb50  jnz     loc_18002CCA4
0x18002cb56  mov     r15, [rbp+4Fh+var_A0]
0x18002cb5a  test    r15, r15
0x18002cb5d  jz      short loc_18002CB86
0x18002cb5f  call    cs:__imp_GetLastError
0x18002cb66  nop     dword ptr [rax+rax+00h]
0x18002cb6b  mov     ebx, eax
0x18002cb6d  mov     rcx, r15
0x18002cb70  call    ORCloseKey
0x18002cb75  mov     ecx, ebx; dwErrCode
0x18002cb77  call    cs:__imp_SetLastError
0x18002cb7e  nop     dword ptr [rax+rax+00h]
0x18002cb83  nop
0x18002cb84  xor     ebx, ebx
0x18002cb86  mov     [rbp+4Fh+var_A0], rbx
0x18002cb8a  lea     rdx, [rbp+4Fh+var_68]
0x18002cb8e  cmp     qword ptr [rbp+4Fh+var_58+8], 7
0x18002cb93  cmova   rdx, qword ptr [rbp+4Fh+var_68]
0x18002cb98  lea     r8, [rbp+4Fh+var_A0]
0x18002cb9c  mov     rcx, r12
0x18002cb9f  call    OROpenKey
0x18002cba4  mov     rcx, [rbp+57h]; this
0x18002cba8  test    eax, eax
0x18002cbaa  jnz     loc_18002CCB9
0x18002cbb0  mov     r15, [rbp+4Fh+var_98]
0x18002cbb4  inc     rsi
0x18002cbb7  xorps   xmm0, xmm0
0x18002cbba  movups  [rbp+4Fh+var_90], xmm0
0x18002cbbe  mov     [rbp+4Fh+var_80], rbx
0x18002cbc2  mov     [rbp+4Fh+var_78], rbx
0x18002cbc6  mov     rax, [rdi+10h]
0x18002cbca  cmp     rax, rsi
0x18002cbcd  jb      loc_18002CC89
0x18002cbd3  sub     rax, rsi
0x18002cbd6  cmp     rax, r14
0x18002cbd9  cmovb   r14, rax
0x18002cbdd  cmp     qword ptr [rdi+18h], 7
0x18002cbe2  jbe     short loc_18002CBE9
0x18002cbe4  mov     rax, [rdi]
0x18002cbe7  jmp     short loc_18002CBEC
0x18002cbe9  mov     rax, rdi
0x18002cbec  lea     rdx, [rax+rsi*2]
0x18002cbf0  mov     r8, r14
0x18002cbf3  lea     rcx, [rbp+4Fh+var_90]
0x18002cbf7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cbfc  mov     eax, [rbp+4Fh+arg_20]
0x18002cbff  mov     dword ptr [rsp+0E0h+pSecurityDescriptor], eax
0x18002cc03  mov     r9, r15
0x18002cc06  mov     r8d, r13d
0x18002cc09  lea     rdx, [rbp+4Fh+var_90]
0x18002cc0d  mov     rbx, [rbp+4Fh+var_A0]
0x18002cc11  mov     rcx, rbx
0x18002cc14  call    OfflineHiveLib__SetValueRecursively
0x18002cc19  nop
0x18002cc1a  lea     rcx, [rbp+4Fh+var_68]
0x18002cc1e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cc23  nop
0x18002cc24  test    rbx, rbx
0x18002cc27  jz      short loc_18002CC32
0x18002cc29  mov     rcx, rbx
0x18002cc2c  call    ORCloseKey
0x18002cc31  nop
0x18002cc32  mov     rcx, rdi
0x18002cc35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cc3a  mov     rcx, [rbp+4Fh+var_48]
0x18002cc3e  xor     rcx, rsp; StackCookie
0x18002cc41  call    __security_check_cookie
0x18002cc46  add     rsp, 0A8h
0x18002cc4d  pop     r15
0x18002cc4f  pop     r14
0x18002cc51  pop     r13
0x18002cc53  pop     r12
0x18002cc55  pop     rdi
0x18002cc56  pop     rsi
0x18002cc57  pop     rbx
0x18002cc58  pop     rbp
0x18002cc59  retn
0x18002cc5b  cmp     qword ptr [rdi+18h], 7
0x18002cc60  jbe     short loc_18002CC67
0x18002cc62  mov     rdx, [rdi]
0x18002cc65  jmp     short loc_18002CC6A
0x18002cc67  mov     rdx, rdi
0x18002cc6a  mov     eax, [rbp+4Fh+arg_20]
0x18002cc6d  mov     dword ptr [rsp+0E0h+pSecurityDescriptor], eax
0x18002cc71  mov     r9, r15
0x18002cc74  mov     r8d, r13d
0x18002cc77  mov     rcx, r12
0x18002cc7a  call    ORSetValueInternal
0x18002cc7f  mov     rcx, [rbp+57h]
0x18002cc83  test    eax, eax
0x18002cc85  jnz     short loc_18002CC8F
0x18002cc87  jmp     short loc_18002CC32
0x18002cc89  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
0x18002cc8e  nop
0x18002cc8f  mov     r9d, eax; char *
0x18002cc92  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\registry"...
0x18002cc99  mov     edx, 6BCh; void *
0x18002cc9e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002cca4  mov     r9d, eax; char *
0x18002cca7  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\registry"...
0x18002ccae  mov     edx, 6D2h; void *
0x18002ccb3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002ccb9  mov     r9d, eax; char *
0x18002ccbc  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\registry"...
0x18002ccc3  mov     edx, 6D5h; void *
0x18002ccc8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
