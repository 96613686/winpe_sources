# MF::DLNA::GetAACLevel

- ea: `0x180064138`
- end: `0x180064366`
- name: `MF::DLNA::GetAACLevel`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18005ff50`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180064138`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006429b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006429b`

## string_xrefs

- `0x18006414d`: `MF::DLNA::GetAACLevel`
- `0x1800642f8`: `MF::DLNA::GetAACLevel`

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
      v8 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180064138  mov     [rsp+arg_8], rbx
0x18006413d  mov     [rsp+arg_10], rsi
0x180064142  push    rdi
0x180064143  sub     rsp, 30h
0x180064147  mov     rdi, rdx
0x18006414a  movzx   ebx, cl
0x18006414d  lea     rdx, aMfDlnaGetaacle; "MF::DLNA::GetAACLevel"
0x180064154  mov     r8d, 1BAFh; int
0x18006415a  lea     rcx, [rsp+38h+arg_0]; this
0x18006415f  xor     esi, esi
0x180064161  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180064166  mov     ecx, ebx
0x180064168  cmp     ebx, 14h
0x18006416b  ja      loc_180064208
0x180064171  jz      loc_1800641FD
0x180064177  cmp     ebx, 8
0x18006417a  ja      short loc_1800641C8
0x18006417c  jz      loc_180064343
0x180064182  sub     ecx, 1
0x180064185  jz      loc_180064240
0x18006418b  sub     ecx, 1
0x18006418e  jz      loc_180064235
0x180064194  sub     ecx, 1
0x180064197  jz      short loc_1800641BD
0x180064199  sub     ecx, 1
0x18006419c  jz      loc_180064343
0x1800641a2  sub     ecx, 1
0x1800641a5  jz      loc_180064240
0x1800641ab  sub     ecx, 1
0x1800641ae  jz      loc_180064235
0x1800641b4  cmp     ecx, 1
0x1800641b7  jnz     loc_180064288
0x1800641bd  mov     dword ptr [rdi], 3
0x1800641c3  jmp     loc_180064349
0x1800641c8  sub     ecx, 0Eh
0x1800641cb  jz      short loc_180064240
0x1800641cd  sub     ecx, 1
0x1800641d0  jz      short loc_180064235
0x1800641d2  sub     ecx, 1
0x1800641d5  jz      short loc_1800641BD
0x1800641d7  sub     ecx, 1
0x1800641da  jz      loc_180064343
0x1800641e0  sub     ecx, 1
0x1800641e3  jz      loc_18006433B
0x1800641e9  cmp     ecx, 1
0x1800641ec  jnz     loc_180064288
0x1800641f2  mov     dword ptr [rdi], 6
0x1800641f8  jmp     loc_180064349
0x1800641fd  mov     dword ptr [rdi], 7
0x180064203  jmp     loc_180064349
0x180064208  cmp     ecx, 2Dh ; '-'
0x18006420b  ja      short loc_180064256
0x18006420d  jz      short loc_1800641BD
0x18006420f  sub     ecx, 15h
0x180064212  jz      short loc_18006424B
0x180064214  sub     ecx, 13h
0x180064217  jz      short loc_180064240
0x180064219  sub     ecx, 1
0x18006421c  jz      short loc_180064235
0x18006421e  sub     ecx, 1
0x180064221  jz      loc_180064343
0x180064227  sub     ecx, 1
0x18006422a  jz      loc_18006433B
0x180064230  cmp     ecx, 1
0x180064233  jnz     short loc_180064288
0x180064235  mov     dword ptr [rdi], 2
0x18006423b  jmp     loc_180064349
0x180064240  mov     dword ptr [rdi], 1
0x180064246  jmp     loc_180064349
0x18006424b  mov     dword ptr [rdi], 8
0x180064251  jmp     loc_180064349
0x180064256  sub     ecx, 2Eh ; '.'
0x180064259  jz      loc_180064343
0x18006425f  sub     ecx, 1
0x180064262  jz      loc_18006433B
0x180064268  sub     ecx, 1
0x18006426b  jz      short loc_180064235
0x18006426d  sub     ecx, 1
0x180064270  jz      loc_1800641BD
0x180064276  sub     ecx, 1
0x180064279  jz      loc_180064343
0x18006427f  cmp     ecx, 1
0x180064282  jz      loc_18006433B
0x180064288  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006428f  mov     [rdi], esi
0x180064291  mov     esi, 0C00D36D5h
0x180064296  test    rcx, rcx
0x180064299  jnz     short loc_1800642E2
0x18006429b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800642a2  nop     dword ptr [rax+rax+00h]
0x1800642a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800642ae  mov     rcx, rax
0x1800642b1  test    rax, rax
0x1800642b4  jz      short loc_1800642D4
0x1800642b6  mov     rax, [rax]
0x1800642b9  mov     edx, 7F0h
0x1800642be  mov     rax, [rax+8]
0x1800642c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642c7  test    eax, eax
0x1800642c9  jz      short loc_1800642D4
0x1800642cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800642d2  jmp     short loc_1800642E2
0x1800642d4  lea     rcx, qword_1800DBF70; this
0x1800642db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800642e2  cmp     byte ptr [rcx+8], 0
0x1800642e6  jz      short loc_18006430D
0x1800642e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800642ed  cmp     [rax+7CCh], esi
0x1800642f3  jz      short loc_18006430D
0x1800642f5  mov     r9d, esi; int
0x1800642f8  lea     rdx, aMfDlnaGetaacle; "MF::DLNA::GetAACLevel"
0x1800642ff  mov     r8d, 1BE9h; int
0x180064305  mov     rcx, rax; this
0x180064308  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006430d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064314  jb      short loc_180064349
0x180064316  mov     rcx, cs:WPP_GLOBAL_Control
0x18006431d  lea     r8, WPP_fa77beb46c243ad195817512d9db2f50_Traceguids
0x180064324  mov     edx, 24h ; '$'
0x180064329  mov     [rsp+38h+var_18], esi
0x18006432d  xor     r9d, r9d
0x180064330  mov     rcx, [rcx+10h]
0x180064334  call    WPP_SF_qD
0x180064339  jmp     short loc_180064349
0x18006433b  mov     dword ptr [rdi], 5
0x180064341  jmp     short loc_180064349
0x180064343  mov     dword ptr [rdi], 4
0x180064349  lea     rcx, [rsp+38h+arg_0]; this
0x18006434e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180064353  mov     rbx, [rsp+38h+arg_8]
0x180064358  mov     eax, esi
0x18006435a  mov     rsi, [rsp+38h+arg_10]
0x18006435f  add     rsp, 30h
0x180064363  pop     rdi
0x180064364  retn
```
