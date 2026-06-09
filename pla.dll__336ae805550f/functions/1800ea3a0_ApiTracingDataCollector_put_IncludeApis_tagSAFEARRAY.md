# _ApiTracingDataCollector::put_IncludeApis(tagSAFEARRAY *)

- ea: `0x1800ea3a0`
- end: `0x1800ea6ea`
- name: `?put_IncludeApis@_ApiTracingDataCollector@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `842`
- prototype: `int(_ApiTracingDataCollector *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18006e574`
- `0x1800ea3a0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ea6b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ea6b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ea46e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ea46e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800ea61f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800ea634`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800ea61f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800ea634`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800ea56b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800ea56b`

## pseudocode

```c
__int64 __fastcall _ApiTracingDataCollector::put_IncludeApis(_ApiTracingDataCollector *this, struct tagSAFEARRAY *a2)
{
  HRESULT v4; // ebx
  int v5; // eax
  __int64 v6; // rax
  int *v7; // r9
  HRESULT v8; // eax
  __int64 v9; // rax
  SAFEARRAY *v10; // rcx
  __int64 v11; // rax
  HRESULT v13; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v16[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v17[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v18[64]; // [rsp+190h] [rbp+90h] BYREF

  v13 = *((_DWORD *)this + 14);
  v4 = 0;
  ppsaOut = (SAFEARRAY *)this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      (__int64)&g_Eventing,
      (__int64)&PLA_EVENT_METHOD,
      3,
      (__int64)"_ApiTracingDataCollector::put_IncludeApis");
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ppsaOut = 0;
  if ( a2 )
  {
    v5 = PlaiValidateSafeArray(a2);
    v4 = v5;
    if ( v5 < 0 )
    {
      v13 = 0;
      v14 = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v16, 0x4000000000000800uLL);
        v6 = -1;
        do
          ++v6;
        while ( v16[v6] );
        v7 = &v14;
        goto LABEL_15;
      }
      goto LABEL_34;
    }
    v8 = SafeArrayCopy(a2, &ppsaOut);
    v4 = v8;
    if ( v8 < 0 )
    {
      v14 = 0;
      v13 = v8;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_34;
      }
      PlaiWhoAmI(v17, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v17[v9] );
LABEL_22:
      v7 = &v13;
LABEL_15:
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)v7);
      goto LABEL_34;
    }
  }
  v10 = (SAFEARRAY *)*((_QWORD *)this + 21);
  if ( !v10 || (v4 = SafeArrayDestroy(v10), v4 >= 0) )
  {
    *((_QWORD *)this + 21) = ppsaOut;
    goto LABEL_34;
  }
  if ( ppsaOut )
    SafeArrayDestroy(ppsaOut);
  v14 = 0;
  v13 = v4;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v18, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v18[v11] );
    goto LABEL_22;
  }
LABEL_34:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ea3a0  mov     [rsp-8+arg_10], rbx
0x1800ea3a5  mov     [rsp-8+arg_18], rsi
0x1800ea3aa  push    rbp
0x1800ea3ab  push    rdi
0x1800ea3ac  push    r12
0x1800ea3ae  push    r14
0x1800ea3b0  push    r15
0x1800ea3b2  lea     rbp, [rsp-120h]
0x1800ea3ba  sub     rsp, 220h
0x1800ea3c1  mov     rax, cs:__security_cookie
0x1800ea3c8  xor     rax, rsp
0x1800ea3cb  mov     [rbp+140h+var_30], rax
0x1800ea3d2  mov     eax, [rcx+38h]
0x1800ea3d5  xor     r14d, r14d
0x1800ea3d8  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800ea3df  mov     rsi, rdx
0x1800ea3e2  mov     rdi, rcx
0x1800ea3e5  mov     [rsp+240h+var_1D0], eax
0x1800ea3e9  mov     ebx, r14d
0x1800ea3ec  mov     [rbp+140h+ppsaOut], rcx
0x1800ea3f0  lea     r15d, [r14+4]
0x1800ea3f4  lea     r12d, [r14+2Ah]
0x1800ea3f8  jz      short loc_1800EA464
0x1800ea3fa  mov     rdx, 4000000000000400h
0x1800ea404  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ea40b  jz      short loc_1800EA464
0x1800ea40d  mov     rax, cs:qword_180169748
0x1800ea414  and     rax, rdx
0x1800ea417  cmp     cs:qword_180169748, rax
0x1800ea41e  jnz     short loc_1800EA464
0x1800ea420  mov     [rsp+240h+var_200], r15
0x1800ea425  lea     rax, [rsp+240h+var_1D0]
0x1800ea42a  mov     [rsp+240h+var_208], rax
0x1800ea42f  lea     r9, aApitracingdata_4; "_ApiTracingDataCollector::put_IncludeAp"...
0x1800ea436  lea     rax, [rbp+140h+ppsaOut]
0x1800ea43a  mov     [rsp+240h+var_210], 8
0x1800ea443  mov     [rsp+240h+var_218], rax
0x1800ea448  lea     r8d, [r14+3]
0x1800ea44c  lea     rdx, PLA_EVENT_METHOD
0x1800ea453  mov     [rsp+240h+var_220], r12
0x1800ea458  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ea45f  call    EventingWriteEvent
0x1800ea464  cmp     [rdi+8], r14d
0x1800ea468  jz      short loc_1800EA474
0x1800ea46a  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800ea46e  call    cs:__imp_EnterCriticalSection
0x1800ea474  mov     [rbp+140h+ppsaOut], r14
0x1800ea478  test    rsi, rsi
0x1800ea47b  jz      loc_1800EA60F
0x1800ea481  mov     rcx, rsi; psa
0x1800ea484  call    ?PlaiValidateSafeArray@@YAJPEAUtagSAFEARRAY@@@Z; PlaiValidateSafeArray(tagSAFEARRAY *)
0x1800ea489  mov     ebx, eax
0x1800ea48b  test    eax, eax
0x1800ea48d  jns     loc_1800EA564
0x1800ea493  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800ea49a  mov     [rsp+240h+var_1D0], r14d
0x1800ea49f  mov     [rsp+240h+var_1C8], eax
0x1800ea4a3  jz      loc_1800EA6AD
0x1800ea4a9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ea4b3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ea4ba  jz      loc_1800EA6AD
0x1800ea4c0  mov     rax, cs:qword_180169748
0x1800ea4c7  and     rax, rdx
0x1800ea4ca  cmp     cs:qword_180169748, rax
0x1800ea4d1  jnz     loc_1800EA6AD
0x1800ea4d7  lea     rcx, [rbp+140h+var_1B0]; unsigned __int16 *
0x1800ea4db  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ea4e0  lea     rcx, [rbp+140h+var_1B0]
0x1800ea4e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ea4e8  inc     rax
0x1800ea4eb  cmp     [rcx+rax*2], r14w
0x1800ea4f0  jnz     short loc_1800EA4E8
0x1800ea4f2  lea     ecx, [rax+rax]
0x1800ea4f5  lea     rax, [rbp+140h+var_1B0]
0x1800ea4f9  add     rcx, 2
0x1800ea4fd  mov     [rsp+240h+var_1E0], rcx
0x1800ea502  lea     r9, [rsp+240h+var_1C8]
0x1800ea507  mov     [rsp+240h+var_1E8], rax
0x1800ea50c  lea     rax, aApitracingdata_4; "_ApiTracingDataCollector::put_IncludeAp"...
0x1800ea513  mov     [rsp+240h+var_1F0], r12
0x1800ea518  mov     [rsp+240h+var_1F8], rax
0x1800ea51d  lea     rax, [rsp+240h+var_1D0]
0x1800ea522  mov     [rsp+240h+var_200], r15
0x1800ea527  lea     rdx, PLA_EVENT_ERROR
0x1800ea52e  mov     [rsp+240h+var_208], rax
0x1800ea533  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ea53a  lea     rax, byte_180147320
0x1800ea541  mov     [rsp+240h+var_210], 1
0x1800ea54a  mov     [rsp+240h+var_218], rax
0x1800ea54f  mov     r8d, 5
0x1800ea555  mov     [rsp+240h+var_220], r15
0x1800ea55a  call    EventingWriteEvent
0x1800ea55f  jmp     loc_1800EA6AD
0x1800ea564  lea     rdx, [rbp+140h+ppsaOut]; ppsaOut
0x1800ea568  mov     rcx, rsi; psa
0x1800ea56b  call    cs:__imp_SafeArrayCopy
0x1800ea571  mov     ebx, eax
0x1800ea573  test    eax, eax
0x1800ea575  jns     loc_1800EA60F
0x1800ea57b  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800ea582  mov     [rsp+240h+var_1C8], r14d
0x1800ea587  mov     [rsp+240h+var_1D0], eax
0x1800ea58b  jz      loc_1800EA6AD
0x1800ea591  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ea59b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ea5a2  jz      loc_1800EA6AD
0x1800ea5a8  mov     rax, cs:qword_180169748
0x1800ea5af  and     rax, rdx
0x1800ea5b2  cmp     cs:qword_180169748, rax
0x1800ea5b9  jnz     loc_1800EA6AD
0x1800ea5bf  lea     rcx, [rbp+140h+var_130]; unsigned __int16 *
0x1800ea5c3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ea5c8  lea     rcx, [rbp+140h+var_130]
0x1800ea5cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ea5d0  inc     rax
0x1800ea5d3  cmp     [rcx+rax*2], r14w
0x1800ea5d8  jnz     short loc_1800EA5D0
0x1800ea5da  lea     ecx, [rax+rax]
0x1800ea5dd  lea     rax, [rbp+140h+var_130]
0x1800ea5e1  add     rcx, 2
0x1800ea5e5  lea     r9, [rsp+240h+var_1D0]
0x1800ea5ea  mov     [rsp+240h+var_1E0], rcx
0x1800ea5ef  mov     [rsp+240h+var_1E8], rax
0x1800ea5f4  lea     rax, aApitracingdata_4; "_ApiTracingDataCollector::put_IncludeAp"...
0x1800ea5fb  mov     [rsp+240h+var_1F0], r12
0x1800ea600  mov     [rsp+240h+var_1F8], rax
0x1800ea605  lea     rax, [rsp+240h+var_1C8]
0x1800ea60a  jmp     loc_1800EA522
0x1800ea60f  mov     rcx, [rdi+0A8h]; psa
0x1800ea616  test    rcx, rcx
0x1800ea619  jz      loc_1800EA6A2
0x1800ea61f  call    cs:__imp_SafeArrayDestroy
0x1800ea625  mov     ebx, eax
0x1800ea627  test    eax, eax
0x1800ea629  jns     short loc_1800EA6A2
0x1800ea62b  mov     rcx, [rbp+140h+ppsaOut]; psa
0x1800ea62f  test    rcx, rcx
0x1800ea632  jz      short loc_1800EA63A
0x1800ea634  call    cs:__imp_SafeArrayDestroy
0x1800ea63a  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800ea641  mov     [rsp+240h+var_1C8], r14d
0x1800ea646  mov     [rsp+240h+var_1D0], ebx
0x1800ea64a  jz      short loc_1800EA6AD
0x1800ea64c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ea656  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ea65d  jz      short loc_1800EA6AD
0x1800ea65f  mov     rax, cs:qword_180169748
0x1800ea666  and     rax, rdx
0x1800ea669  cmp     cs:qword_180169748, rax
0x1800ea670  jnz     short loc_1800EA6AD
0x1800ea672  lea     rcx, [rbp+140h+var_B0]; unsigned __int16 *
0x1800ea679  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ea67e  lea     rcx, [rbp+140h+var_B0]
0x1800ea685  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ea689  inc     rax
0x1800ea68c  cmp     [rcx+rax*2], r14w
0x1800ea691  jnz     short loc_1800EA689
0x1800ea693  lea     ecx, [rax+rax]
0x1800ea696  lea     rax, [rbp+140h+var_B0]
0x1800ea69d  jmp     loc_1800EA5E1
0x1800ea6a2  mov     rax, [rbp+140h+ppsaOut]
0x1800ea6a6  mov     [rdi+0A8h], rax
0x1800ea6ad  cmp     [rdi+8], r14d
0x1800ea6b1  jz      short loc_1800EA6BD
0x1800ea6b3  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800ea6b7  call    cs:__imp_LeaveCriticalSection
0x1800ea6bd  mov     eax, ebx
0x1800ea6bf  mov     rcx, [rbp+140h+var_30]
0x1800ea6c6  xor     rcx, rsp; StackCookie
0x1800ea6c9  call    __security_check_cookie
0x1800ea6ce  lea     r11, [rsp+240h+var_20]
0x1800ea6d6  mov     rbx, [r11+40h]
0x1800ea6da  mov     rsi, [r11+48h]
0x1800ea6de  mov     rsp, r11
0x1800ea6e1  pop     r15
0x1800ea6e3  pop     r14
0x1800ea6e5  pop     r12
0x1800ea6e7  pop     rdi
0x1800ea6e8  pop     rbp
0x1800ea6e9  retn
```
