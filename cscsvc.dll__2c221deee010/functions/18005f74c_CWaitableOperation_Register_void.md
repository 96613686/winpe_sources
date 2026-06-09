# CWaitableOperation::_Register(void)

- ea: `0x18005f74c`
- end: `0x18005f858`
- name: `?_Register@CWaitableOperation@@AEAAJXZ`
- size: `268`
- prototype: `__int64 __fastcall(CWaitableOperation *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18005d3a0`
- `0x18005eb40`
- `0x18005ebec`

## callees

- `0x180036394`
- `0x1800413c8`
- `0x18004ff34`
- `0x18005f74c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f75e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f75e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f847`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f847`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005f83d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005f83d`

## pseudocode

```c
__int64 __fastcall CWaitableOperation::_Register(CWaitableOperation *this)
{
  unsigned int v2; // edi
  __int64 v3; // rax
  int v4; // eax
  HANDLE h; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
      *((_QWORD *)this + 2),
      *((_DWORD *)this + 8));
  }
  if ( !*((_DWORD *)this + 8) )
  {
    v3 = *(_QWORD *)this;
    h = 0;
    v4 = (*(__int64 (__fastcall **)(CWaitableOperation *, HANDLE *))(v3 + 8))(this, &h);
    v2 = v4;
    if ( v4 >= 0 )
    {
      *((_DWORD *)this + 9) = 1;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      {
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
          h,
          *((_QWORD *)this + 2));
      }
      SetThreadpoolWait(*((PTP_WAIT *)this + 2), h, 0);
    }
    else if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
        (unsigned int)v4);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  return v2;
}

```

## disassembly

```asm
0x18005f74c  push    rbx
0x18005f74e  push    rbp
0x18005f74f  push    rsi
0x18005f750  push    rdi
0x18005f751  sub     rsp, 38h
0x18005f755  mov     rbx, rcx
0x18005f758  xor     edi, edi
0x18005f75a  add     rcx, 28h ; '('; lpCriticalSection
0x18005f75e  call    cs:__imp_EnterCriticalSection
0x18005f764  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f76b  lea     rbp, WPP_GLOBAL_Control
0x18005f772  cmp     rcx, rbp
0x18005f775  jz      short loc_18005F79E
0x18005f777  test    dword ptr [rcx+1Ch], 10000h
0x18005f77e  jz      short loc_18005F79E
0x18005f780  mov     eax, [rbx+20h]
0x18005f783  lea     edx, [rdi+0Fh]
0x18005f786  mov     r9, [rbx+10h]
0x18005f78a  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005f791  mov     rcx, [rcx+10h]
0x18005f795  mov     dword ptr [rsp+58h+var_38], eax
0x18005f799  call    WPP_SF_qD
0x18005f79e  cmp     [rbx+20h], edi
0x18005f7a1  jnz     loc_18005F843
0x18005f7a7  mov     rax, [rbx]
0x18005f7aa  lea     rdx, [rsp+58h+h]
0x18005f7af  mov     rcx, rbx
0x18005f7b2  mov     [rsp+58h+h], rdi
0x18005f7b7  mov     rax, [rax+8]
0x18005f7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f7c0  mov     edi, eax
0x18005f7c2  test    eax, eax
0x18005f7c4  jns     short loc_18005F7F2
0x18005f7c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f7cd  cmp     rcx, rbp
0x18005f7d0  jz      short loc_18005F843
0x18005f7d2  test    byte ptr [rcx+1Ch], 2
0x18005f7d6  jz      short loc_18005F843
0x18005f7d8  mov     rcx, [rcx+10h]
0x18005f7dc  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005f7e3  mov     edx, 10h
0x18005f7e8  mov     r9d, eax
0x18005f7eb  call    WPP_SF_d
0x18005f7f0  jmp     short loc_18005F843
0x18005f7f2  mov     dword ptr [rbx+24h], 1
0x18005f7f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f800  cmp     rcx, rbp
0x18005f803  jz      short loc_18005F831
0x18005f805  test    dword ptr [rcx+1Ch], 10000h
0x18005f80c  jz      short loc_18005F831
0x18005f80e  mov     rax, [rbx+10h]
0x18005f812  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005f819  mov     r9, [rsp+58h+h]
0x18005f81e  mov     edx, 11h
0x18005f823  mov     rcx, [rcx+10h]
0x18005f827  mov     [rsp+58h+var_38], rax
0x18005f82c  call    WPP_SF_qq
0x18005f831  mov     rdx, [rsp+58h+h]; h
0x18005f836  xor     r8d, r8d; pftTimeout
0x18005f839  mov     rcx, [rbx+10h]; pwa
0x18005f83d  call    cs:__imp_SetThreadpoolWait
0x18005f843  lea     rcx, [rbx+28h]; lpCriticalSection
0x18005f847  call    cs:__imp_LeaveCriticalSection
0x18005f84d  mov     eax, edi
0x18005f84f  add     rsp, 38h
0x18005f853  pop     rdi
0x18005f854  pop     rsi
0x18005f855  pop     rbp
0x18005f856  pop     rbx
0x18005f857  retn
```
