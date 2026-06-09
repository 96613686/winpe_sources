# _ConfigurationDataCollector::put_Files(tagSAFEARRAY *)

- ea: `0x1800f6ee0`
- end: `0x1800f722a`
- name: `?put_Files@_ConfigurationDataCollector@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `842`
- prototype: `__int64 __fastcall(_ConfigurationDataCollector *this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18006e574`
- `0x1800f6ee0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f71f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f71f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f6fae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f6fae`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f715f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f7174`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f715f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f7174`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800f70ab`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800f70ab`

## string_xrefs

- `0x1800f6f6f`: `_ConfigurationDataCollector::put_Files`
- `0x1800f704c`: `_ConfigurationDataCollector::put_Files`
- `0x1800f7134`: `_ConfigurationDataCollector::put_Files`

## pseudocode

```c
__int64 __fastcall _ConfigurationDataCollector::put_Files(_ConfigurationDataCollector *this, struct tagSAFEARRAY *a2)
{
  HRESULT v4; // ebx
  int v5; // eax
  __int64 v6; // rax
  int *v7; // r9
  HRESULT *v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rax
  SAFEARRAY *v11; // rcx
  __int64 v12; // rax
  HRESULT v14; // [rsp+70h] [rbp-90h] BYREF
  int v15; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *ppsaOut[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v17[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v18[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v19[64]; // [rsp+190h] [rbp+90h] BYREF

  v14 = *((_DWORD *)this + 14);
  v4 = 0;
  ppsaOut[0] = (SAFEARRAY *)this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      &PLA_EVENT_METHOD,
      3,
      "_ConfigurationDataCollector::put_Files",
      39,
      ppsaOut,
      8,
      &v14,
      4);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ppsaOut[0] = 0;
  if ( a2 )
  {
    v5 = PlaiValidateSafeArray(a2);
    v4 = v5;
    if ( v5 < 0 )
    {
      v14 = 0;
      v15 = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v17, 0x4000000000000800uLL);
        v6 = -1;
        do
          ++v6;
        while ( v17[v6] );
        v7 = &v15;
        v8 = &v14;
        goto LABEL_15;
      }
      goto LABEL_34;
    }
    v9 = SafeArrayCopy(a2, ppsaOut);
    v4 = v9;
    if ( v9 < 0 )
    {
      v15 = 0;
      v14 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_34;
      }
      PlaiWhoAmI(v18, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v18[v10] );
LABEL_22:
      v7 = &v14;
      v8 = &v15;
LABEL_15:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v7, 4, byte_180147320, 1, v8, 4);
      goto LABEL_34;
    }
  }
  v11 = (SAFEARRAY *)*((_QWORD *)this + 22);
  if ( !v11 || (v4 = SafeArrayDestroy(v11), v4 >= 0) )
  {
    *((SAFEARRAY **)this + 22) = ppsaOut[0];
    goto LABEL_34;
  }
  if ( ppsaOut[0] )
    SafeArrayDestroy(ppsaOut[0]);
  v15 = 0;
  v14 = v4;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v19, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v19[v12] );
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
0x1800f6ee0  mov     [rsp-8+arg_10], rbx
0x1800f6ee5  mov     [rsp-8+arg_18], rsi
0x1800f6eea  push    rbp
0x1800f6eeb  push    rdi
0x1800f6eec  push    r12
0x1800f6eee  push    r14
0x1800f6ef0  push    r15
0x1800f6ef2  lea     rbp, [rsp-120h]
0x1800f6efa  sub     rsp, 220h
0x1800f6f01  mov     rax, cs:__security_cookie
0x1800f6f08  xor     rax, rsp
0x1800f6f0b  mov     [rbp+140h+var_30], rax
0x1800f6f12  mov     eax, [rcx+38h]
0x1800f6f15  xor     r14d, r14d
0x1800f6f18  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f6f1f  mov     rsi, rdx
0x1800f6f22  mov     rdi, rcx
0x1800f6f25  mov     [rsp+240h+var_1D0], eax
0x1800f6f29  mov     ebx, r14d
0x1800f6f2c  mov     [rbp+140h+ppsaOut], rcx
0x1800f6f30  lea     r15d, [r14+4]
0x1800f6f34  lea     r12d, [r14+27h]
0x1800f6f38  jz      short loc_1800F6FA4
0x1800f6f3a  mov     rdx, 4000000000000400h
0x1800f6f44  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f6f4b  jz      short loc_1800F6FA4
0x1800f6f4d  mov     rax, cs:qword_180169748
0x1800f6f54  and     rax, rdx
0x1800f6f57  cmp     cs:qword_180169748, rax
0x1800f6f5e  jnz     short loc_1800F6FA4
0x1800f6f60  mov     [rsp+240h+var_200], r15
0x1800f6f65  lea     rax, [rsp+240h+var_1D0]
0x1800f6f6a  mov     [rsp+240h+var_208], rax
0x1800f6f6f  lea     r9, aConfigurationd_4; "_ConfigurationDataCollector::put_Files"
0x1800f6f76  lea     rax, [rbp+140h+ppsaOut]
0x1800f6f7a  mov     [rsp+240h+var_210], 8
0x1800f6f83  mov     [rsp+240h+var_218], rax
0x1800f6f88  lea     r8d, [r14+3]
0x1800f6f8c  lea     rdx, PLA_EVENT_METHOD
0x1800f6f93  mov     [rsp+240h+var_220], r12
0x1800f6f98  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f6f9f  call    EventingWriteEvent
0x1800f6fa4  cmp     [rdi+8], r14d
0x1800f6fa8  jz      short loc_1800F6FB4
0x1800f6faa  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800f6fae  call    cs:__imp_EnterCriticalSection
0x1800f6fb4  mov     [rbp+140h+ppsaOut], r14
0x1800f6fb8  test    rsi, rsi
0x1800f6fbb  jz      loc_1800F714F
0x1800f6fc1  mov     rcx, rsi; psa
0x1800f6fc4  call    ?PlaiValidateSafeArray@@YAJPEAUtagSAFEARRAY@@@Z; PlaiValidateSafeArray(tagSAFEARRAY *)
0x1800f6fc9  mov     ebx, eax
0x1800f6fcb  test    eax, eax
0x1800f6fcd  jns     loc_1800F70A4
0x1800f6fd3  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f6fda  mov     [rsp+240h+var_1D0], r14d
0x1800f6fdf  mov     [rsp+240h+var_1C8], eax
0x1800f6fe3  jz      loc_1800F71ED
0x1800f6fe9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f6ff3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f6ffa  jz      loc_1800F71ED
0x1800f7000  mov     rax, cs:qword_180169748
0x1800f7007  and     rax, rdx
0x1800f700a  cmp     cs:qword_180169748, rax
0x1800f7011  jnz     loc_1800F71ED
0x1800f7017  lea     rcx, [rbp+140h+var_1B0]; unsigned __int16 *
0x1800f701b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f7020  lea     rcx, [rbp+140h+var_1B0]
0x1800f7024  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f7028  inc     rax
0x1800f702b  cmp     [rcx+rax*2], r14w
0x1800f7030  jnz     short loc_1800F7028
0x1800f7032  lea     ecx, [rax+rax]
0x1800f7035  lea     rax, [rbp+140h+var_1B0]
0x1800f7039  add     rcx, 2
0x1800f703d  mov     [rsp+240h+var_1E0], rcx
0x1800f7042  lea     r9, [rsp+240h+var_1C8]
0x1800f7047  mov     [rsp+240h+var_1E8], rax
0x1800f704c  lea     rax, aConfigurationd_4; "_ConfigurationDataCollector::put_Files"
0x1800f7053  mov     [rsp+240h+var_1F0], r12
0x1800f7058  mov     [rsp+240h+var_1F8], rax
0x1800f705d  lea     rax, [rsp+240h+var_1D0]
0x1800f7062  mov     [rsp+240h+var_200], r15
0x1800f7067  lea     rdx, PLA_EVENT_ERROR
0x1800f706e  mov     [rsp+240h+var_208], rax
0x1800f7073  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f707a  lea     rax, byte_180147320
0x1800f7081  mov     [rsp+240h+var_210], 1
0x1800f708a  mov     [rsp+240h+var_218], rax
0x1800f708f  mov     r8d, 5
0x1800f7095  mov     [rsp+240h+var_220], r15
0x1800f709a  call    EventingWriteEvent
0x1800f709f  jmp     loc_1800F71ED
0x1800f70a4  lea     rdx, [rbp+140h+ppsaOut]; ppsaOut
0x1800f70a8  mov     rcx, rsi; psa
0x1800f70ab  call    cs:__imp_SafeArrayCopy
0x1800f70b1  mov     ebx, eax
0x1800f70b3  test    eax, eax
0x1800f70b5  jns     loc_1800F714F
0x1800f70bb  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f70c2  mov     [rsp+240h+var_1C8], r14d
0x1800f70c7  mov     [rsp+240h+var_1D0], eax
0x1800f70cb  jz      loc_1800F71ED
0x1800f70d1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f70db  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f70e2  jz      loc_1800F71ED
0x1800f70e8  mov     rax, cs:qword_180169748
0x1800f70ef  and     rax, rdx
0x1800f70f2  cmp     cs:qword_180169748, rax
0x1800f70f9  jnz     loc_1800F71ED
0x1800f70ff  lea     rcx, [rbp+140h+var_130]; unsigned __int16 *
0x1800f7103  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f7108  lea     rcx, [rbp+140h+var_130]
0x1800f710c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f7110  inc     rax
0x1800f7113  cmp     [rcx+rax*2], r14w
0x1800f7118  jnz     short loc_1800F7110
0x1800f711a  lea     ecx, [rax+rax]
0x1800f711d  lea     rax, [rbp+140h+var_130]
0x1800f7121  add     rcx, 2
0x1800f7125  lea     r9, [rsp+240h+var_1D0]
0x1800f712a  mov     [rsp+240h+var_1E0], rcx
0x1800f712f  mov     [rsp+240h+var_1E8], rax
0x1800f7134  lea     rax, aConfigurationd_4; "_ConfigurationDataCollector::put_Files"
0x1800f713b  mov     [rsp+240h+var_1F0], r12
0x1800f7140  mov     [rsp+240h+var_1F8], rax
0x1800f7145  lea     rax, [rsp+240h+var_1C8]
0x1800f714a  jmp     loc_1800F7062
0x1800f714f  mov     rcx, [rdi+0B0h]; psa
0x1800f7156  test    rcx, rcx
0x1800f7159  jz      loc_1800F71E2
0x1800f715f  call    cs:__imp_SafeArrayDestroy
0x1800f7165  mov     ebx, eax
0x1800f7167  test    eax, eax
0x1800f7169  jns     short loc_1800F71E2
0x1800f716b  mov     rcx, [rbp+140h+ppsaOut]; psa
0x1800f716f  test    rcx, rcx
0x1800f7172  jz      short loc_1800F717A
0x1800f7174  call    cs:__imp_SafeArrayDestroy
0x1800f717a  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f7181  mov     [rsp+240h+var_1C8], r14d
0x1800f7186  mov     [rsp+240h+var_1D0], ebx
0x1800f718a  jz      short loc_1800F71ED
0x1800f718c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f7196  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f719d  jz      short loc_1800F71ED
0x1800f719f  mov     rax, cs:qword_180169748
0x1800f71a6  and     rax, rdx
0x1800f71a9  cmp     cs:qword_180169748, rax
0x1800f71b0  jnz     short loc_1800F71ED
0x1800f71b2  lea     rcx, [rbp+140h+var_B0]; unsigned __int16 *
0x1800f71b9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f71be  lea     rcx, [rbp+140h+var_B0]
0x1800f71c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f71c9  inc     rax
0x1800f71cc  cmp     [rcx+rax*2], r14w
0x1800f71d1  jnz     short loc_1800F71C9
0x1800f71d3  lea     ecx, [rax+rax]
0x1800f71d6  lea     rax, [rbp+140h+var_B0]
0x1800f71dd  jmp     loc_1800F7121
0x1800f71e2  mov     rax, [rbp+140h+ppsaOut]
0x1800f71e6  mov     [rdi+0B0h], rax
0x1800f71ed  cmp     [rdi+8], r14d
0x1800f71f1  jz      short loc_1800F71FD
0x1800f71f3  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800f71f7  call    cs:__imp_LeaveCriticalSection
0x1800f71fd  mov     eax, ebx
0x1800f71ff  mov     rcx, [rbp+140h+var_30]
0x1800f7206  xor     rcx, rsp; StackCookie
0x1800f7209  call    __security_check_cookie
0x1800f720e  lea     r11, [rsp+240h+var_20]
0x1800f7216  mov     rbx, [r11+40h]
0x1800f721a  mov     rsi, [r11+48h]
0x1800f721e  mov     rsp, r11
0x1800f7221  pop     r15
0x1800f7223  pop     r14
0x1800f7225  pop     r12
0x1800f7227  pop     rdi
0x1800f7228  pop     rbp
0x1800f7229  retn
```
