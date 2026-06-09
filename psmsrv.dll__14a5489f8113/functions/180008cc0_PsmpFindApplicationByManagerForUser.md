# PsmpFindApplicationByManagerForUser

- ea: `0x180008cc0`
- end: `0x180008f09`
- name: `PsmpFindApplicationByManagerForUser`
- size: `585`
- prototype: `__int64 __fastcall(PSID Sid2, int, __int64, __int64, int, __int64 *)`
- caller_count: `18`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003af0`
- `0x1800049a0`
- `0x180006f5c`
- `0x180007214`
- `0x1800078e0`
- `0x180007d40`
- `0x180013b40`
- `0x180017768`
- `0x18001cf00`
- `0x18001d740`
- `0x18001d840`
- `0x18001deb0`
- `0x18001e20c`
- `0x18001e510`
- `0x18001f6f0`
- `0x180023ae8`
- `0x18002ae60`
- `0x18002b990`

## callees

- `0x180008cc0`
- `0x1800092b4`
- `0x1800093d0`
- `0x180019c30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180008e9f`
- `ntdll!RtlFreeHeap` at `0x180008e9f`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008d51`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008dca`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008ecf`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008eee`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008d51`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008dca`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008ecf`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008eee`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008df6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008df6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008e18`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008e18`
- `ntdll!RtlEqualSid` at `0x180008d9e`
- `ntdll!RtlEqualSid` at `0x180008d9e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008cfc`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008d73`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008cfc`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008d73`

## pseudocode

```c
__int64 __fastcall PsmpFindApplicationByManagerForUser(PSID Sid2, int a2, __int64 a3, __int64 a4, int a5, __int64 *a6)
{
  __int64 v9; // rdx
  _UNKNOWN **i; // r8
  signed __int32 *v11; // rbx
  signed __int32 v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  signed __int32 *j; // rsi
  signed __int32 *v17; // rdi
  signed __int32 v18; // eax
  __int64 Application; // rax
  __int64 v20; // rbp
  __int64 v21; // rsi
  signed __int32 v22; // ecx
  __int64 v24; // rcx
  signed __int32 **v25; // rdx

  if ( (a5 & 0xFFFFFFF3) != 0 || a5 == 12 )
    return 3221225715LL;
  RtlAcquireSRWLockShared(&PsmpManagerLock);
  for ( i = (_UNKNOWN **)PsmpManagerList; i != &PsmpManagerList; i = (_UNKNOWN **)*i )
  {
    v11 = (signed __int32 *)(i - 5);
    if ( a2 == *((_DWORD *)i - 5) && a5 == v11[4] )
    {
      _m_prefetchw(v11);
      v12 = *v11;
      while ( v12 > 0 )
      {
        v9 = (unsigned int)v12;
        v12 = _InterlockedCompareExchange(v11, v12 + 1, v12);
        if ( v12 == (_DWORD)v9 )
        {
          RtlReleaseSRWLockShared(&PsmpManagerLock, v9, i, &PsmpManagerList);
          if ( !v11 )
            return 3221225473LL;
          RtlAcquireSRWLockShared(v11 + 2);
          for ( j = (signed __int32 *)*((_QWORD *)v11 + 3); j != v11 + 6; j = *(signed __int32 **)j )
          {
            v17 = j - 2;
            if ( *(j - 1) == a2 && RtlEqualSid(*((PSID *)v17 + 5), Sid2) )
            {
              _m_prefetchw(v17);
              v18 = *v17;
              while ( v18 > 0 )
              {
                v13 = (unsigned int)v18;
                v18 = _InterlockedCompareExchange(v17, v18 + 1, v18);
                if ( v18 == (_DWORD)v13 )
                {
                  RtlReleaseSRWLockShared(v11 + 2, v13, v14, v15);
                  if ( j == (signed __int32 *)8 )
                    goto LABEL_34;
                  Application = PsmpFindApplication(0, j - 2, a3, a4);
                  v20 = *((_QWORD *)v17 + 7);
                  v21 = Application;
                  RtlAcquireSRWLockExclusive(v20 + 8);
                  v22 = _InterlockedDecrement(v17);
                  if ( v22 == -1 )
                  {
                    MicrosoftTelemetryAssertTriggeredNoArgs();
                  }
                  else if ( (v22 & 0x7FFFFFFF) == 0 )
                  {
                    v24 = *((_QWORD *)v17 + 1);
                    if ( *(signed __int32 **)(v24 + 8) != v17 + 2
                      || (v25 = (signed __int32 **)*((_QWORD *)v17 + 2), *v25 != v17 + 2) )
                    {
                      __fastfail(3u);
                    }
                    *v25 = (signed __int32 *)v24;
                    *(_QWORD *)(v24 + 8) = v25;
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
                  }
                  RtlReleaseSRWLockExclusive(v20 + 8);
                  PsmpDereferenceManagerContext(v11);
                  if ( !v21 )
                    return 3221225524LL;
                  *a6 = v21;
                  return 0;
                }
              }
            }
          }
          RtlReleaseSRWLockShared(v11 + 2, v13, v14, v15);
LABEL_34:
          PsmpDereferenceManagerContext(v11);
          return 3221225473LL;
        }
      }
    }
  }
  RtlReleaseSRWLockShared(&PsmpManagerLock, v9, i, &PsmpManagerList);
  return 3221225473LL;
}

```

## disassembly

```asm
0x180008cc0  mov     [rsp+arg_10], r8
0x180008cc5  push    rbp
0x180008cc6  push    rdi
0x180008cc7  push    r12
0x180008cc9  push    r13
0x180008ccb  sub     rsp, 28h
0x180008ccf  mov     edi, [rsp+48h+arg_20]
0x180008cd3  mov     r13, r9
0x180008cd6  mov     ebp, edx
0x180008cd8  mov     r12, rcx
0x180008cdb  test    edi, 0FFFFFFF3h
0x180008ce1  jnz     loc_180008EAA
0x180008ce7  cmp     edi, 0Ch
0x180008cea  jz      loc_180008EAA
0x180008cf0  lea     rcx, PsmpManagerLock
0x180008cf7  mov     [rsp+48h+arg_0], rbx
0x180008cfc  call    cs:__imp_RtlAcquireSRWLockShared
0x180008d02  mov     r8, cs:PsmpManagerList
0x180008d09  lea     r9, PsmpManagerList
0x180008d10  cmp     r8, r9
0x180008d13  jz      loc_180008EE7
0x180008d19  cmp     ebp, [r8-14h]
0x180008d1d  lea     rbx, [r8-28h]
0x180008d21  jnz     loc_180008E58
0x180008d27  cmp     edi, [rbx+10h]
0x180008d2a  jnz     loc_180008E58
0x180008d30  prefetchw byte ptr [rbx]
0x180008d33  mov     eax, [rbx]
0x180008d35  test    eax, eax
0x180008d37  jle     loc_180008E58
0x180008d3d  mov     edx, eax
0x180008d3f  lea     ecx, [rax+1]
0x180008d42  lock cmpxchg [rbx], ecx
0x180008d46  cmp     eax, edx
0x180008d48  jnz     short loc_180008D35
0x180008d4a  lea     rcx, PsmpManagerLock
0x180008d51  call    cs:__imp_RtlReleaseSRWLockShared
0x180008d57  test    rbx, rbx
0x180008d5a  jz      loc_180008EF4
0x180008d60  mov     [rsp+48h+arg_8], rsi
0x180008d65  lea     rcx, [rbx+8]
0x180008d69  mov     [rsp+48h+arg_18], r14
0x180008d6e  mov     [rsp+48h+var_28], r15
0x180008d73  call    cs:__imp_RtlAcquireSRWLockShared
0x180008d79  mov     rsi, [rbx+18h]
0x180008d7d  lea     r14, [rbx+18h]
0x180008d81  cmp     rsi, r14
0x180008d84  jz      loc_180008ECB
0x180008d8a  cmp     [rsi-4], ebp
0x180008d8d  lea     rdi, [rsi-8]
0x180008d91  jnz     loc_180008E60
0x180008d97  mov     rcx, [rdi+28h]; Sid1
0x180008d9b  mov     rdx, r12; Sid2
0x180008d9e  call    cs:__imp_RtlEqualSid
0x180008da4  test    al, al
0x180008da6  jz      loc_180008E60
0x180008dac  prefetchw byte ptr [rdi]
0x180008daf  mov     eax, [rdi]
0x180008db1  test    eax, eax
0x180008db3  jle     loc_180008E60
0x180008db9  mov     edx, eax
0x180008dbb  lea     ecx, [rax+1]
0x180008dbe  lock cmpxchg [rdi], ecx
0x180008dc2  cmp     eax, edx
0x180008dc4  jnz     short loc_180008DB1
0x180008dc6  lea     rcx, [rbx+8]
0x180008dca  call    cs:__imp_RtlReleaseSRWLockShared
0x180008dd0  test    rdi, rdi
0x180008dd3  jz      loc_180008ED5
0x180008dd9  mov     r8, [rsp+48h+arg_10]
0x180008dde  mov     r9, r13
0x180008de1  mov     rdx, rdi
0x180008de4  xor     ecx, ecx
0x180008de6  call    PsmpFindApplication
0x180008deb  mov     rbp, [rdi+38h]
0x180008def  mov     rsi, rax
0x180008df2  lea     rcx, [rbp+8]
0x180008df6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008dfc  mov     ecx, 0FFFFFFFFh
0x180008e01  lock xadd [rdi], ecx
0x180008e05  dec     ecx
0x180008e07  cmp     ecx, 0FFFFFFFFh
0x180008e0a  jz      short loc_180008E68
0x180008e0c  test    ecx, 7FFFFFFFh
0x180008e12  jz      short loc_180008E6F
0x180008e14  lea     rcx, [rbp+8]
0x180008e18  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008e1e  mov     rcx, rbx; P
0x180008e21  call    PsmpDereferenceManagerContext
0x180008e26  test    rsi, rsi
0x180008e29  jz      loc_180008EC1
0x180008e2f  mov     rax, [rsp+48h+arg_28]
0x180008e34  mov     [rax], rsi
0x180008e37  xor     eax, eax
0x180008e39  mov     r14, [rsp+48h+arg_18]
0x180008e3e  mov     rsi, [rsp+48h+arg_8]
0x180008e43  mov     r15, [rsp+48h+var_28]
0x180008e48  mov     rbx, [rsp+48h+arg_0]
0x180008e4d  add     rsp, 28h
0x180008e51  pop     r13
0x180008e53  pop     r12
0x180008e55  pop     rdi
0x180008e56  pop     rbp
0x180008e57  retn
0x180008e58  mov     r8, [r8]
0x180008e5b  jmp     loc_180008D10
0x180008e60  mov     rsi, [rsi]
0x180008e63  jmp     loc_180008D81
0x180008e68  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008e6d  jmp     short loc_180008E14
0x180008e6f  mov     rcx, [rdi+8]
0x180008e73  lea     rax, [rdi+8]
0x180008e77  cmp     [rcx+8], rax
0x180008e7b  jnz     short loc_180008EBA
0x180008e7d  mov     rdx, [rax+8]
0x180008e81  cmp     [rdx], rax
0x180008e84  jnz     short loc_180008EBA
0x180008e86  mov     [rdx], rcx
0x180008e89  mov     r8, rdi; P
0x180008e8c  mov     [rcx+8], rdx
0x180008e90  xor     edx, edx; Flags
0x180008e92  mov     rcx, gs:60h
0x180008e9b  mov     rcx, [rcx+30h]; HeapHandle
0x180008e9f  call    cs:__imp_RtlFreeHeap
0x180008ea5  jmp     loc_180008E14
0x180008eaa  mov     eax, 0C00000F3h
0x180008eaf  add     rsp, 28h
0x180008eb3  pop     r13
0x180008eb5  pop     r12
0x180008eb7  pop     rdi
0x180008eb8  pop     rbp
0x180008eb9  retn
0x180008eba  mov     ecx, 3
0x180008ebf  int     29h; Win8: RtlFailFast(ecx)
0x180008ec1  mov     eax, 0C0000034h
0x180008ec6  jmp     loc_180008E39
0x180008ecb  lea     rcx, [rbx+8]
0x180008ecf  call    cs:__imp_RtlReleaseSRWLockShared
0x180008ed5  mov     rcx, rbx; P
0x180008ed8  call    PsmpDereferenceManagerContext
0x180008edd  mov     eax, 0C0000001h
0x180008ee2  jmp     loc_180008E39
0x180008ee7  lea     rcx, PsmpManagerLock
0x180008eee  call    cs:__imp_RtlReleaseSRWLockShared
0x180008ef4  mov     rbx, [rsp+48h+arg_0]
0x180008ef9  mov     eax, 0C0000001h
0x180008efe  add     rsp, 28h
0x180008f02  pop     r13
0x180008f04  pop     r12
0x180008f06  pop     rdi
0x180008f07  pop     rbp
0x180008f08  retn
```
