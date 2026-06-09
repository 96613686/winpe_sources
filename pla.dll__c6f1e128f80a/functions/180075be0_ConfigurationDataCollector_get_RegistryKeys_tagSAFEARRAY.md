# _ConfigurationDataCollector::get_RegistryKeys(tagSAFEARRAY * *)

- ea: `0x180075be0`
- end: `0x180075dd8`
- name: `?get_RegistryKeys@_ConfigurationDataCollector@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `504`
- prototype: `int(_ConfigurationDataCollector *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180075be0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075da9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075da9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075ca2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075ca2`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180075cbe`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180075cbe`

## string_xrefs

- `0x180075c08`: `_ConfigurationDataCollector::get_RegistryKeys`

## pseudocode

```c
__int64 __fastcall _ConfigurationDataCollector::get_RegistryKeys(
        _ConfigurationDataCollector *this,
        struct tagSAFEARRAY **a2)
{
  unsigned int v4; // edi
  SAFEARRAY *v5; // rcx
  HRESULT v6; // eax
  __int64 v7; // rax
  __int64 v9; // [rsp+48h] [rbp-F0h]
  __int64 v10; // [rsp+50h] [rbp-E8h]
  int v11; // [rsp+70h] [rbp-C8h] BYREF
  _ConfigurationDataCollector *v12; // [rsp+78h] [rbp-C0h] BYREF
  unsigned __int16 v13[64]; // [rsp+80h] [rbp-B8h] BYREF

  v11 = *((_DWORD *)this + 14);
  v12 = this;
  v4 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "_ConfigurationDataCollector::get_RegistryKeys",
      46,
      &v12,
      8,
      &v11,
      4,
      v9,
      v10);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *a2 = 0;
  v5 = (SAFEARRAY *)*((_QWORD *)this + 21);
  if ( v5 )
  {
    v6 = SafeArrayCopy(v5, a2);
    v4 = v6;
    if ( v6 < 0 )
    {
      v11 = 0;
      LODWORD(v12) = v6;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v13, 0x4000000000000800uLL);
          v7 = -1;
          do
            ++v7;
          while ( v13[v7] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v12,
            4,
            qword_180147320,
            1,
            &v11,
            4,
            "_ConfigurationDataCollector::get_RegistryKeys",
            46);
        }
      }
    }
  }
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v4;
}

```

## disassembly

```asm
0x180075be0  mov     [rsp+arg_10], rbx
0x180075be5  push    rbp
0x180075be6  push    rsi
0x180075be7  push    rdi
0x180075be8  push    r12
0x180075bea  push    r14
0x180075bec  sub     rsp, 110h
0x180075bf3  mov     rax, cs:__security_cookie
0x180075bfa  xor     rax, rsp
0x180075bfd  mov     [rsp+138h+var_38], rax
0x180075c05  mov     eax, [rcx+38h]
0x180075c08  lea     r12, aConfigurationd_13; "_ConfigurationDataCollector::get_Regist"...
0x180075c0f  xor     ebp, ebp
0x180075c11  mov     [rsp+138h+var_C8], eax
0x180075c15  cmp     dword ptr cs:xmmword_180169738, ebp
0x180075c1b  mov     rsi, rdx
0x180075c1e  mov     rbx, rcx
0x180075c21  mov     [rsp+138h+var_C0], rcx
0x180075c26  mov     edi, ebp
0x180075c28  lea     r14d, [rbp+4]
0x180075c2c  jz      short loc_180075C99
0x180075c2e  mov     rdx, 4000000000000400h
0x180075c38  test    qword ptr cs:xmmword_180169738+8, rdx
0x180075c3f  jz      short loc_180075C99
0x180075c41  mov     rax, cs:qword_180169748
0x180075c48  and     rax, rdx
0x180075c4b  cmp     cs:qword_180169748, rax
0x180075c52  jnz     short loc_180075C99
0x180075c54  mov     [rsp+138h+var_F8], r14
0x180075c59  lea     rax, [rsp+138h+var_C8]
0x180075c5e  mov     [rsp+138h+var_100], rax
0x180075c63  lea     r8d, [rbp+3]
0x180075c67  lea     rax, [rsp+138h+var_C0]
0x180075c6c  mov     [rsp+138h+var_108], 8
0x180075c75  mov     [rsp+138h+var_110], rax
0x180075c7a  lea     rdx, PLA_EVENT_METHOD
0x180075c81  mov     r9, r12
0x180075c84  mov     [rsp+138h+var_118], 2Eh ; '.'
0x180075c8d  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180075c94  call    EventingWriteEvent
0x180075c99  cmp     [rbx+8], ebp
0x180075c9c  jz      short loc_180075CA8
0x180075c9e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180075ca2  call    cs:__imp_EnterCriticalSection
0x180075ca8  mov     [rsi], rbp
0x180075cab  mov     rcx, [rbx+0A8h]; psa
0x180075cb2  test    rcx, rcx
0x180075cb5  jz      loc_180075DA0
0x180075cbb  mov     rdx, rsi; ppsaOut
0x180075cbe  call    cs:__imp_SafeArrayCopy
0x180075cc4  mov     edi, eax
0x180075cc6  test    eax, eax
0x180075cc8  jns     loc_180075DA0
0x180075cce  cmp     dword ptr cs:xmmword_180169738, ebp
0x180075cd4  mov     [rsp+138h+var_C8], ebp
0x180075cd8  mov     dword ptr [rsp+138h+var_C0], eax
0x180075cdc  jz      loc_180075DA0
0x180075ce2  mov     rdx, 4000000000000800h; unsigned __int64
0x180075cec  test    qword ptr cs:xmmword_180169738+8, rdx
0x180075cf3  jz      loc_180075DA0
0x180075cf9  mov     rax, cs:qword_180169748
0x180075d00  and     rax, rdx
0x180075d03  cmp     cs:qword_180169748, rax
0x180075d0a  jnz     loc_180075DA0
0x180075d10  lea     rcx, [rsp+138h+var_B8]; unsigned __int16 *
0x180075d18  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180075d1d  lea     rcx, [rsp+138h+var_B8]
0x180075d25  or      rax, 0FFFFFFFFFFFFFFFFh
0x180075d29  inc     rax
0x180075d2c  cmp     [rcx+rax*2], bp
0x180075d30  jnz     short loc_180075D29
0x180075d32  lea     ecx, [rax+rax]
0x180075d35  mov     r8d, 5
0x180075d3b  add     rcx, 2
0x180075d3f  lea     rax, [rsp+138h+var_B8]
0x180075d47  mov     [rsp+138h+var_D8], rcx
0x180075d4c  lea     r9, [rsp+138h+var_C0]
0x180075d51  mov     [rsp+138h+var_E0], rax
0x180075d56  lea     rdx, PLA_EVENT_ERROR
0x180075d5d  mov     [rsp+138h+var_E8], 2Eh ; '.'
0x180075d66  lea     rax, [rsp+138h+var_C8]
0x180075d6b  mov     [rsp+138h+var_F0], r12
0x180075d70  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180075d77  mov     [rsp+138h+var_F8], r14
0x180075d7c  mov     [rsp+138h+var_100], rax
0x180075d81  lea     rax, qword_180147320
0x180075d88  mov     [rsp+138h+var_108], 1
0x180075d91  mov     [rsp+138h+var_110], rax
0x180075d96  mov     [rsp+138h+var_118], r14
0x180075d9b  call    EventingWriteEvent
0x180075da0  cmp     [rbx+8], ebp
0x180075da3  jz      short loc_180075DAF
0x180075da5  lea     rcx, [rbx+10h]; lpCriticalSection
0x180075da9  call    cs:__imp_LeaveCriticalSection
0x180075daf  mov     eax, edi
0x180075db1  mov     rcx, [rsp+138h+var_38]
0x180075db9  xor     rcx, rsp; StackCookie
0x180075dbc  call    __security_check_cookie
0x180075dc1  mov     rbx, [rsp+138h+arg_10]
0x180075dc9  add     rsp, 110h
0x180075dd0  pop     r14
0x180075dd2  pop     r12
0x180075dd4  pop     rdi
0x180075dd5  pop     rsi
0x180075dd6  pop     rbp
0x180075dd7  retn
```
