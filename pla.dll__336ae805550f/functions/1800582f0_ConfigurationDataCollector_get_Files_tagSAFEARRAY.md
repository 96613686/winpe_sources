# _ConfigurationDataCollector::get_Files(tagSAFEARRAY * *)

- ea: `0x1800582f0`
- end: `0x1800584e8`
- name: `?get_Files@_ConfigurationDataCollector@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `504`
- prototype: `int(_ConfigurationDataCollector *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800582f0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800584b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800584b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800583b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800583b2`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800583ce`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800583ce`

## string_xrefs

- `0x180058318`: `_ConfigurationDataCollector::get_Files`

## pseudocode

```c
__int64 __fastcall _ConfigurationDataCollector::get_Files(_ConfigurationDataCollector *this, struct tagSAFEARRAY **a2)
{
  unsigned int v4; // edi
  SAFEARRAY *v5; // rcx
  HRESULT v6; // eax
  __int64 v7; // rax
  int v9; // [rsp+70h] [rbp-C8h] BYREF
  _ConfigurationDataCollector *v10; // [rsp+78h] [rbp-C0h] BYREF
  unsigned __int16 v11[64]; // [rsp+80h] [rbp-B8h] BYREF

  v9 = *((_DWORD *)this + 14);
  v10 = this;
  v4 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "_ConfigurationDataCollector::get_Files", 39, &v10, 8, &v9, 4);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *a2 = 0;
  v5 = (SAFEARRAY *)*((_QWORD *)this + 22);
  if ( v5 )
  {
    v6 = SafeArrayCopy(v5, a2);
    v4 = v6;
    if ( v6 < 0 )
    {
      v9 = 0;
      LODWORD(v10) = v6;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v11, 0x4000000000000800uLL);
          v7 = -1;
          do
            ++v7;
          while ( v11[v7] );
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v10, 4, byte_180147320, 1, &v9, 4);
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
0x1800582f0  mov     [rsp+arg_10], rbx
0x1800582f5  push    rbp
0x1800582f6  push    rsi
0x1800582f7  push    rdi
0x1800582f8  push    r12
0x1800582fa  push    r14
0x1800582fc  sub     rsp, 110h
0x180058303  mov     rax, cs:__security_cookie
0x18005830a  xor     rax, rsp
0x18005830d  mov     [rsp+138h+var_38], rax
0x180058315  mov     eax, [rcx+38h]
0x180058318  lea     r12, aConfigurationd_15; "_ConfigurationDataCollector::get_Files"
0x18005831f  xor     ebp, ebp
0x180058321  mov     [rsp+138h+var_C8], eax
0x180058325  cmp     dword ptr cs:xmmword_180169738, ebp
0x18005832b  mov     rsi, rdx
0x18005832e  mov     rbx, rcx
0x180058331  mov     [rsp+138h+var_C0], rcx
0x180058336  mov     edi, ebp
0x180058338  lea     r14d, [rbp+4]
0x18005833c  jz      short loc_1800583A9
0x18005833e  mov     rdx, 4000000000000400h
0x180058348  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005834f  jz      short loc_1800583A9
0x180058351  mov     rax, cs:qword_180169748
0x180058358  and     rax, rdx
0x18005835b  cmp     cs:qword_180169748, rax
0x180058362  jnz     short loc_1800583A9
0x180058364  mov     [rsp+138h+var_F8], r14
0x180058369  lea     rax, [rsp+138h+var_C8]
0x18005836e  mov     [rsp+138h+var_100], rax
0x180058373  lea     r8d, [rbp+3]
0x180058377  lea     rax, [rsp+138h+var_C0]
0x18005837c  mov     [rsp+138h+var_108], 8
0x180058385  mov     [rsp+138h+var_110], rax
0x18005838a  lea     rdx, PLA_EVENT_METHOD
0x180058391  mov     r9, r12
0x180058394  mov     [rsp+138h+var_118], 27h ; '''
0x18005839d  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800583a4  call    EventingWriteEvent
0x1800583a9  cmp     [rbx+8], ebp
0x1800583ac  jz      short loc_1800583B8
0x1800583ae  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800583b2  call    cs:__imp_EnterCriticalSection
0x1800583b8  mov     [rsi], rbp
0x1800583bb  mov     rcx, [rbx+0B0h]; psa
0x1800583c2  test    rcx, rcx
0x1800583c5  jz      loc_1800584B0
0x1800583cb  mov     rdx, rsi; ppsaOut
0x1800583ce  call    cs:__imp_SafeArrayCopy
0x1800583d4  mov     edi, eax
0x1800583d6  test    eax, eax
0x1800583d8  jns     loc_1800584B0
0x1800583de  cmp     dword ptr cs:xmmword_180169738, ebp
0x1800583e4  mov     [rsp+138h+var_C8], ebp
0x1800583e8  mov     dword ptr [rsp+138h+var_C0], eax
0x1800583ec  jz      loc_1800584B0
0x1800583f2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800583fc  test    qword ptr cs:xmmword_180169738+8, rdx
0x180058403  jz      loc_1800584B0
0x180058409  mov     rax, cs:qword_180169748
0x180058410  and     rax, rdx
0x180058413  cmp     cs:qword_180169748, rax
0x18005841a  jnz     loc_1800584B0
0x180058420  lea     rcx, [rsp+138h+var_B8]; unsigned __int16 *
0x180058428  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005842d  lea     rcx, [rsp+138h+var_B8]
0x180058435  or      rax, 0FFFFFFFFFFFFFFFFh
0x180058439  inc     rax
0x18005843c  cmp     [rcx+rax*2], bp
0x180058440  jnz     short loc_180058439
0x180058442  lea     ecx, [rax+rax]
0x180058445  mov     r8d, 5
0x18005844b  add     rcx, 2
0x18005844f  lea     rax, [rsp+138h+var_B8]
0x180058457  mov     [rsp+138h+var_D8], rcx
0x18005845c  lea     r9, [rsp+138h+var_C0]
0x180058461  mov     [rsp+138h+var_E0], rax
0x180058466  lea     rdx, PLA_EVENT_ERROR
0x18005846d  mov     [rsp+138h+var_E8], 27h ; '''
0x180058476  lea     rax, [rsp+138h+var_C8]
0x18005847b  mov     [rsp+138h+var_F0], r12
0x180058480  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180058487  mov     [rsp+138h+var_F8], r14
0x18005848c  mov     [rsp+138h+var_100], rax
0x180058491  lea     rax, byte_180147320
0x180058498  mov     [rsp+138h+var_108], 1
0x1800584a1  mov     [rsp+138h+var_110], rax
0x1800584a6  mov     [rsp+138h+var_118], r14
0x1800584ab  call    EventingWriteEvent
0x1800584b0  cmp     [rbx+8], ebp
0x1800584b3  jz      short loc_1800584BF
0x1800584b5  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800584b9  call    cs:__imp_LeaveCriticalSection
0x1800584bf  mov     eax, edi
0x1800584c1  mov     rcx, [rsp+138h+var_38]
0x1800584c9  xor     rcx, rsp; StackCookie
0x1800584cc  call    __security_check_cookie
0x1800584d1  mov     rbx, [rsp+138h+arg_10]
0x1800584d9  add     rsp, 110h
0x1800584e0  pop     r14
0x1800584e2  pop     r12
0x1800584e4  pop     rdi
0x1800584e5  pop     rsi
0x1800584e6  pop     rbp
0x1800584e7  retn
```
