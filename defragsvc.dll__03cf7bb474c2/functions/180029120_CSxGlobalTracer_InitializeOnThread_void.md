# CSxGlobalTracer::_InitializeOnThread(void)

- ea: `0x180029120`
- end: `0x1800292cc`
- name: `?_InitializeOnThread@CSxGlobalTracer@@AEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(CSxGlobalTracer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002906c`
- `0x18004b9e0`

## callees

- `0x18001a630`
- `0x180029120`
- `0x180046494`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180029131`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800291de`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002922c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180029131`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800291de`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002922c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800291a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800291a5`

## pseudocode

```c
__int64 __fastcall CSxGlobalTracer::_InitializeOnThread(CSxGlobalTracer *this)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int LastFailureAsHRESULT; // eax
  unsigned int v6; // ebx
  CSxGlobalTracer *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  signed __int32 v10; // esi
  unsigned int v11; // edi
  unsigned int v12; // ebp
  int *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // eax
  int v19; // esi

  if ( !TlsSetValue(dwTlsIndex, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v2, v1, v3, v4);
    v6 = LastFailureAsHRESULT;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 16;
      v9 = LastFailureAsHRESULT;
LABEL_19:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids, v9);
      return v6;
    }
    return v6;
  }
  v10 = dword_180089370;
  v11 = dword_180089370;
  v12 = dword_180089370 + 512;
  if ( dword_180089370 < (unsigned int)(dword_180089370 + 512) )
  {
    do
    {
      v13 = &g_Trace[10 * (v11 & 0x1FF) + 4];
      if ( !*v13 && !_InterlockedCompareExchange(v13, GetCurrentThreadId(), 0) )
        break;
      v13 = 0;
      ++v11;
    }
    while ( v11 < v12 );
    if ( v13 )
    {
      *((_QWORD *)v13 + 4) = 0;
      v13[2] = 0;
      if ( TlsSetValue(dwTlsIndex, v13) )
      {
        _InterlockedCompareExchange(&dword_180089370, ((_WORD)v11 + 1) & 0x1FF, v10);
        return 0;
      }
      v18 = GetLastFailureAsHRESULT(v15, v14, v16, v17);
      v19 = v18;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids, v18);
      }
      TlsSetValue(dwTlsIndex, 0);
      _InterlockedExchange(v13, 0);
      v7 = WPP_GLOBAL_Control;
LABEL_15:
      v6 = v19;
      if ( v19 >= 0 )
        return v6;
      goto LABEL_16;
    }
  }
  v6 = -2147467259;
  v19 = -2147467259;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_15;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids, 2147500037LL);
  v7 = WPP_GLOBAL_Control;
LABEL_16:
  if ( v7 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
  {
    v8 = 17;
    v9 = (unsigned int)v19;
    goto LABEL_19;
  }
  return v6;
}

```

## disassembly

```asm
0x180029120  push    rbx
0x180029122  push    rbp
0x180029123  push    rsi
0x180029124  push    rdi
0x180029125  sub     rsp, 28h
0x180029129  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002912f  xor     edx, edx; lpTlsValue
0x180029131  call    cs:__imp_TlsSetValue
0x180029137  test    eax, eax
0x180029139  jnz     short loc_180029170
0x18002913b  call    GetLastFailureAsHRESULT
0x180029140  mov     ebx, eax
0x180029142  mov     rcx, cs:WPP_GLOBAL_Control
0x180029149  lea     rdi, WPP_GLOBAL_Control
0x180029150  cmp     rcx, rdi
0x180029153  jz      loc_180029266
0x180029159  test    byte ptr [rcx+1Ch], 1
0x18002915d  jz      loc_180029266
0x180029163  mov     edx, 10h
0x180029168  mov     r9d, eax
0x18002916b  jmp     loc_180029256
0x180029170  mov     esi, cs:dword_180089370
0x180029176  mov     edi, esi
0x180029178  lea     ebp, [rsi+200h]
0x18002917e  cmp     esi, ebp
0x180029180  jnb     loc_180029288
0x180029186  mov     eax, edi
0x180029188  and     eax, 1FFh
0x18002918d  lea     rbx, [rax+rax*4]
0x180029191  lea     rbx, [rbx+2]
0x180029195  lea     rax, ?g_Trace@@3VCSxGlobalTracer@@A; CSxGlobalTracer g_Trace
0x18002919c  lea     rbx, [rax+rbx*8]
0x1800291a0  cmp     dword ptr [rbx], 0
0x1800291a3  jnz     short loc_1800291B5
0x1800291a5  call    cs:__imp_GetCurrentThreadId
0x1800291ab  mov     ecx, eax
0x1800291ad  xor     eax, eax
0x1800291af  lock cmpxchg [rbx], ecx
0x1800291b3  jz      short loc_1800291BD
0x1800291b5  xor     ebx, ebx
0x1800291b7  inc     edi
0x1800291b9  cmp     edi, ebp
0x1800291bb  jb      short loc_180029186
0x1800291bd  test    rbx, rbx
0x1800291c0  jz      loc_180029288
0x1800291c6  mov     qword ptr [rbx+20h], 0
0x1800291ce  mov     rdx, rbx; lpTlsValue
0x1800291d1  mov     dword ptr [rbx+8], 0
0x1800291d8  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800291de  call    cs:__imp_TlsSetValue
0x1800291e4  test    eax, eax
0x1800291e6  jnz     loc_180029271
0x1800291ec  call    GetLastFailureAsHRESULT
0x1800291f1  mov     esi, eax
0x1800291f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291fa  lea     rdi, WPP_GLOBAL_Control
0x180029201  cmp     rcx, rdi
0x180029204  jz      short loc_180029224
0x180029206  test    byte ptr [rcx+1Ch], 1
0x18002920a  jz      short loc_180029224
0x18002920c  mov     rcx, [rcx+10h]
0x180029210  lea     r8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids
0x180029217  mov     edx, 18h
0x18002921c  mov     r9d, eax
0x18002921f  call    WPP_SF_d
0x180029224  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002922a  xor     edx, edx; lpTlsValue
0x18002922c  call    cs:__imp_TlsSetValue
0x180029232  xor     eax, eax
0x180029234  xchg    eax, [rbx]
0x180029236  mov     rcx, cs:WPP_GLOBAL_Control
0x18002923d  mov     ebx, esi
0x18002923f  test    esi, esi
0x180029241  jns     short loc_180029266
0x180029243  cmp     rcx, rdi
0x180029246  jz      short loc_180029266
0x180029248  test    byte ptr [rcx+1Ch], 1
0x18002924c  jz      short loc_180029266
0x18002924e  mov     edx, 11h
0x180029253  mov     r9d, esi
0x180029256  mov     rcx, [rcx+10h]
0x18002925a  lea     r8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids
0x180029261  call    WPP_SF_d
0x180029266  mov     eax, ebx
0x180029268  add     rsp, 28h
0x18002926c  pop     rdi
0x18002926d  pop     rsi
0x18002926e  pop     rbp
0x18002926f  pop     rbx
0x180029270  retn
0x180029271  lea     ecx, [rdi+1]
0x180029274  mov     eax, esi
0x180029276  and     ecx, 1FFh
0x18002927c  lock cmpxchg cs:dword_180089370, ecx
0x180029284  xor     ebx, ebx
0x180029286  jmp     short loc_180029266
0x180029288  mov     ebx, 80004005h
0x18002928d  mov     esi, ebx
0x18002928f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029296  lea     rdi, WPP_GLOBAL_Control
0x18002929d  cmp     rcx, rdi
0x1800292a0  jz      short loc_18002923D
0x1800292a2  test    byte ptr [rcx+1Ch], 1
0x1800292a6  jz      short loc_18002923D
0x1800292a8  mov     rcx, [rcx+10h]
0x1800292ac  lea     r8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids
0x1800292b3  mov     edx, 17h
0x1800292b8  mov     r9d, ebx
0x1800292bb  call    WPP_SF_d
0x1800292c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292c7  jmp     loc_180029243
```
