# MF::DLNA::GetAACLevel

- ea: `0x180061778`
- end: `0x18006199f`
- name: `MF::DLNA::GetAACLevel`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18005d764`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180061778`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800618db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800618db`

## string_xrefs

- `0x18006178d`: `MF::DLNA::GetAACLevel`
- `0x180061932`: `MF::DLNA::GetAACLevel`

## pseudocode

```c
__int64 __fastcall MF::DLNA::GetAACLevel(unsigned __int8 a1, _DWORD *a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v12; // [rsp+40h] [rbp+8h] BYREF

  v3 = a1;
  v4 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "MF::DLNA::GetAACLevel", 7087);
  if ( v3 > 0x14 )
  {
    if ( v3 > 0x2D )
    {
      if ( v3 == 46 )
        goto LABEL_49;
      if ( v3 != 47 )
      {
        switch ( v3 )
        {
          case '0':
            goto LABEL_29;
          case '1':
            goto LABEL_12;
          case '2':
            goto LABEL_49;
        }
        if ( v3 != 51 )
          goto LABEL_38;
      }
    }
    else
    {
      switch ( v3 )
      {
        case 0x2Du:
          goto LABEL_12;
        case 0x15u:
          *a2 = 8;
          goto LABEL_50;
        case 0x28u:
          goto LABEL_30;
        case 0x29u:
          goto LABEL_29;
        case 0x2Au:
          goto LABEL_49;
      }
      if ( v3 != 43 )
      {
        if ( v3 != 44 )
          goto LABEL_38;
LABEL_29:
        *a2 = 2;
        goto LABEL_50;
      }
    }
LABEL_48:
    *a2 = 5;
    goto LABEL_50;
  }
  if ( v3 == 20 )
  {
    *a2 = 7;
    goto LABEL_50;
  }
  if ( v3 > 8 )
  {
    switch ( v3 )
    {
      case 0xEu:
        goto LABEL_30;
      case 0xFu:
        goto LABEL_29;
      case 0x10u:
        goto LABEL_12;
    }
    if ( v3 != 17 )
    {
      if ( v3 != 18 )
      {
        if ( v3 == 19 )
        {
          *a2 = 6;
          goto LABEL_50;
        }
        goto LABEL_38;
      }
      goto LABEL_48;
    }
LABEL_49:
    *a2 = 4;
    goto LABEL_50;
  }
  switch ( v3 )
  {
    case 8u:
      goto LABEL_49;
    case 1u:
LABEL_30:
      *a2 = 1;
      goto LABEL_50;
    case 2u:
      goto LABEL_29;
    case 3u:
LABEL_12:
      *a2 = 3;
      goto LABEL_50;
    case 4u:
      goto LABEL_49;
    case 5u:
      goto LABEL_30;
    case 6u:
      goto LABEL_29;
    case 7u:
      goto LABEL_12;
  }
LABEL_38:
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  *a2 = 0;
  v4 = -1072875819;
  if ( !v8 )
  {
    v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
    CallStackTracing::s_wpInstance = v9;
    if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v8 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875819 )
      CallStackContext::TraceFailure(ThreadRelativeContext, "MF::DLNA::GetAACLevel", 7145, -1072875819);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_fa77beb46c243ad195817512d9db2f50_Traceguids, 0, -1072875819);
LABEL_50:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return v4;
}

```

## disassembly

```asm
0x180061778  mov     [rsp+arg_8], rbx
0x18006177d  mov     [rsp+arg_10], rsi
0x180061782  push    rdi
0x180061783  sub     rsp, 30h
0x180061787  mov     rdi, rdx
0x18006178a  movzx   ebx, cl
0x18006178d  lea     rdx, aMfDlnaGetaacle; "MF::DLNA::GetAACLevel"
0x180061794  mov     r8d, 1BAFh; int
0x18006179a  lea     rcx, [rsp+38h+arg_0]; this
0x18006179f  xor     esi, esi
0x1800617a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800617a6  mov     ecx, ebx
0x1800617a8  cmp     ebx, 14h
0x1800617ab  ja      loc_180061848
0x1800617b1  jz      loc_18006183D
0x1800617b7  cmp     ebx, 8
0x1800617ba  ja      short loc_180061808
0x1800617bc  jz      loc_18006197D
0x1800617c2  sub     ecx, 1
0x1800617c5  jz      loc_180061880
0x1800617cb  sub     ecx, 1
0x1800617ce  jz      loc_180061875
0x1800617d4  sub     ecx, 1
0x1800617d7  jz      short loc_1800617FD
0x1800617d9  sub     ecx, 1
0x1800617dc  jz      loc_18006197D
0x1800617e2  sub     ecx, 1
0x1800617e5  jz      loc_180061880
0x1800617eb  sub     ecx, 1
0x1800617ee  jz      loc_180061875
0x1800617f4  cmp     ecx, 1
0x1800617f7  jnz     loc_1800618C8
0x1800617fd  mov     dword ptr [rdi], 3
0x180061803  jmp     loc_180061983
0x180061808  sub     ecx, 0Eh
0x18006180b  jz      short loc_180061880
0x18006180d  sub     ecx, 1
0x180061810  jz      short loc_180061875
0x180061812  sub     ecx, 1
0x180061815  jz      short loc_1800617FD
0x180061817  sub     ecx, 1
0x18006181a  jz      loc_18006197D
0x180061820  sub     ecx, 1
0x180061823  jz      loc_180061975
0x180061829  cmp     ecx, 1
0x18006182c  jnz     loc_1800618C8
0x180061832  mov     dword ptr [rdi], 6
0x180061838  jmp     loc_180061983
0x18006183d  mov     dword ptr [rdi], 7
0x180061843  jmp     loc_180061983
0x180061848  cmp     ecx, 2Dh ; '-'
0x18006184b  ja      short loc_180061896
0x18006184d  jz      short loc_1800617FD
0x18006184f  sub     ecx, 15h
0x180061852  jz      short loc_18006188B
0x180061854  sub     ecx, 13h
0x180061857  jz      short loc_180061880
0x180061859  sub     ecx, 1
0x18006185c  jz      short loc_180061875
0x18006185e  sub     ecx, 1
0x180061861  jz      loc_18006197D
0x180061867  sub     ecx, 1
0x18006186a  jz      loc_180061975
0x180061870  cmp     ecx, 1
0x180061873  jnz     short loc_1800618C8
0x180061875  mov     dword ptr [rdi], 2
0x18006187b  jmp     loc_180061983
0x180061880  mov     dword ptr [rdi], 1
0x180061886  jmp     loc_180061983
0x18006188b  mov     dword ptr [rdi], 8
0x180061891  jmp     loc_180061983
0x180061896  sub     ecx, 2Eh ; '.'
0x180061899  jz      loc_18006197D
0x18006189f  sub     ecx, 1
0x1800618a2  jz      loc_180061975
0x1800618a8  sub     ecx, 1
0x1800618ab  jz      short loc_180061875
0x1800618ad  sub     ecx, 1
0x1800618b0  jz      loc_1800617FD
0x1800618b6  sub     ecx, 1
0x1800618b9  jz      loc_18006197D
0x1800618bf  cmp     ecx, 1
0x1800618c2  jz      loc_180061975
0x1800618c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618cf  mov     [rdi], esi
0x1800618d1  mov     esi, 0C00D36D5h
0x1800618d6  test    rcx, rcx
0x1800618d9  jnz     short loc_18006191C
0x1800618db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800618e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618e8  mov     rcx, rax
0x1800618eb  test    rax, rax
0x1800618ee  jz      short loc_18006190E
0x1800618f0  mov     rax, [rax]
0x1800618f3  mov     edx, 7F0h
0x1800618f8  mov     rax, [rax+8]
0x1800618fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061901  test    eax, eax
0x180061903  jz      short loc_18006190E
0x180061905  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006190c  jmp     short loc_18006191C
0x18006190e  lea     rcx, qword_1800D6F70; this
0x180061915  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006191c  cmp     byte ptr [rcx+8], 0
0x180061920  jz      short loc_180061947
0x180061922  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061927  cmp     [rax+7CCh], esi
0x18006192d  jz      short loc_180061947
0x18006192f  mov     r9d, esi; int
0x180061932  lea     rdx, aMfDlnaGetaacle; "MF::DLNA::GetAACLevel"
0x180061939  mov     r8d, 1BE9h; int
0x18006193f  mov     rcx, rax; this
0x180061942  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061947  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006194e  jb      short loc_180061983
0x180061950  mov     rcx, cs:WPP_GLOBAL_Control
0x180061957  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x18006195e  mov     edx, 24h ; '$'
0x180061963  mov     [rsp+38h+var_18], esi
0x180061967  xor     r9d, r9d
0x18006196a  mov     rcx, [rcx+10h]
0x18006196e  call    WPP_SF_qD
0x180061973  jmp     short loc_180061983
0x180061975  mov     dword ptr [rdi], 5
0x18006197b  jmp     short loc_180061983
0x18006197d  mov     dword ptr [rdi], 4
0x180061983  lea     rcx, [rsp+38h+arg_0]; this
0x180061988  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006198d  mov     rbx, [rsp+38h+arg_8]
0x180061992  mov     eax, esi
0x180061994  mov     rsi, [rsp+38h+arg_10]
0x180061999  add     rsp, 30h
0x18006199d  pop     rdi
0x18006199e  retn
```
