# _ConfigurationDataCollector::get_ManagementQueries(tagSAFEARRAY * *)

- ea: `0x180096c20`
- end: `0x180096e18`
- name: `?get_ManagementQueries@_ConfigurationDataCollector@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `504`
- prototype: `int(_ConfigurationDataCollector *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180096c20`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096de9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096de9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096ce2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096ce2`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180096cfe`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180096cfe`

## string_xrefs

- `0x180096c48`: `_ConfigurationDataCollector::get_ManagementQueries`

## pseudocode

```c
__int64 __fastcall _ConfigurationDataCollector::get_ManagementQueries(
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
      "_ConfigurationDataCollector::get_ManagementQueries",
      51,
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
  v5 = (SAFEARRAY *)*((_QWORD *)this + 23);
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
            "_ConfigurationDataCollector::get_ManagementQueries",
            51);
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
0x180096c20  mov     [rsp+arg_10], rbx
0x180096c25  push    rbp
0x180096c26  push    rsi
0x180096c27  push    rdi
0x180096c28  push    r12
0x180096c2a  push    r14
0x180096c2c  sub     rsp, 110h
0x180096c33  mov     rax, cs:__security_cookie
0x180096c3a  xor     rax, rsp
0x180096c3d  mov     [rsp+138h+var_38], rax
0x180096c45  mov     eax, [rcx+38h]
0x180096c48  lea     r12, aConfigurationd_14; "_ConfigurationDataCollector::get_Manage"...
0x180096c4f  xor     ebp, ebp
0x180096c51  mov     [rsp+138h+var_C8], eax
0x180096c55  cmp     dword ptr cs:xmmword_180169738, ebp
0x180096c5b  mov     rsi, rdx
0x180096c5e  mov     rbx, rcx
0x180096c61  mov     [rsp+138h+var_C0], rcx
0x180096c66  mov     edi, ebp
0x180096c68  lea     r14d, [rbp+4]
0x180096c6c  jz      short loc_180096CD9
0x180096c6e  mov     rdx, 4000000000000400h
0x180096c78  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096c7f  jz      short loc_180096CD9
0x180096c81  mov     rax, cs:qword_180169748
0x180096c88  and     rax, rdx
0x180096c8b  cmp     cs:qword_180169748, rax
0x180096c92  jnz     short loc_180096CD9
0x180096c94  mov     [rsp+138h+var_F8], r14
0x180096c99  lea     rax, [rsp+138h+var_C8]
0x180096c9e  mov     [rsp+138h+var_100], rax
0x180096ca3  lea     r8d, [rbp+3]
0x180096ca7  lea     rax, [rsp+138h+var_C0]
0x180096cac  mov     [rsp+138h+var_108], 8
0x180096cb5  mov     [rsp+138h+var_110], rax
0x180096cba  lea     rdx, PLA_EVENT_METHOD
0x180096cc1  mov     r9, r12
0x180096cc4  mov     [rsp+138h+var_118], 33h ; '3'
0x180096ccd  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180096cd4  call    EventingWriteEvent
0x180096cd9  cmp     [rbx+8], ebp
0x180096cdc  jz      short loc_180096CE8
0x180096cde  lea     rcx, [rbx+10h]; lpCriticalSection
0x180096ce2  call    cs:__imp_EnterCriticalSection
0x180096ce8  mov     [rsi], rbp
0x180096ceb  mov     rcx, [rbx+0B8h]; psa
0x180096cf2  test    rcx, rcx
0x180096cf5  jz      loc_180096DE0
0x180096cfb  mov     rdx, rsi; ppsaOut
0x180096cfe  call    cs:__imp_SafeArrayCopy
0x180096d04  mov     edi, eax
0x180096d06  test    eax, eax
0x180096d08  jns     loc_180096DE0
0x180096d0e  cmp     dword ptr cs:xmmword_180169738, ebp
0x180096d14  mov     [rsp+138h+var_C8], ebp
0x180096d18  mov     dword ptr [rsp+138h+var_C0], eax
0x180096d1c  jz      loc_180096DE0
0x180096d22  mov     rdx, 4000000000000800h; unsigned __int64
0x180096d2c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096d33  jz      loc_180096DE0
0x180096d39  mov     rax, cs:qword_180169748
0x180096d40  and     rax, rdx
0x180096d43  cmp     cs:qword_180169748, rax
0x180096d4a  jnz     loc_180096DE0
0x180096d50  lea     rcx, [rsp+138h+var_B8]; unsigned __int16 *
0x180096d58  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180096d5d  lea     rcx, [rsp+138h+var_B8]
0x180096d65  or      rax, 0FFFFFFFFFFFFFFFFh
0x180096d69  inc     rax
0x180096d6c  cmp     [rcx+rax*2], bp
0x180096d70  jnz     short loc_180096D69
0x180096d72  lea     ecx, [rax+rax]
0x180096d75  mov     r8d, 5
0x180096d7b  add     rcx, 2
0x180096d7f  lea     rax, [rsp+138h+var_B8]
0x180096d87  mov     [rsp+138h+var_D8], rcx
0x180096d8c  lea     r9, [rsp+138h+var_C0]
0x180096d91  mov     [rsp+138h+var_E0], rax
0x180096d96  lea     rdx, PLA_EVENT_ERROR
0x180096d9d  mov     [rsp+138h+var_E8], 33h ; '3'
0x180096da6  lea     rax, [rsp+138h+var_C8]
0x180096dab  mov     [rsp+138h+var_F0], r12
0x180096db0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180096db7  mov     [rsp+138h+var_F8], r14
0x180096dbc  mov     [rsp+138h+var_100], rax
0x180096dc1  lea     rax, qword_180147320
0x180096dc8  mov     [rsp+138h+var_108], 1
0x180096dd1  mov     [rsp+138h+var_110], rax
0x180096dd6  mov     [rsp+138h+var_118], r14
0x180096ddb  call    EventingWriteEvent
0x180096de0  cmp     [rbx+8], ebp
0x180096de3  jz      short loc_180096DEF
0x180096de5  lea     rcx, [rbx+10h]; lpCriticalSection
0x180096de9  call    cs:__imp_LeaveCriticalSection
0x180096def  mov     eax, edi
0x180096df1  mov     rcx, [rsp+138h+var_38]
0x180096df9  xor     rcx, rsp; StackCookie
0x180096dfc  call    __security_check_cookie
0x180096e01  mov     rbx, [rsp+138h+arg_10]
0x180096e09  add     rsp, 110h
0x180096e10  pop     r14
0x180096e12  pop     r12
0x180096e14  pop     rdi
0x180096e15  pop     rsi
0x180096e16  pop     rbp
0x180096e17  retn
```
