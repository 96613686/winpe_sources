# PsmpSetApplicationPropertiesFromExtension

- ea: `0x180007fd0`
- end: `0x18000834c`
- name: `PsmpSetApplicationPropertiesFromExtension`
- size: `892`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007fd0`
- `0x1800092b4`
- `0x1800093d0`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x18000f7dc`
- `0x180017fa0`
- `0x180019c30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800082ca`
- `ntdll!RtlFreeHeap` at `0x1800082ca`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800080e2`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008151`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800080e2`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008151`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008180`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800081ca`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008180`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800081ca`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800081a7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000822e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800081a7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000822e`
- `ntdll!RtlEqualSid` at `0x180008125`
- `ntdll!RtlEqualSid` at `0x180008125`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000808d`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800080f5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000808d`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800080f5`

## pseudocode

```c
__int64 __fastcall PsmpSetApplicationPropertiesFromExtension(
        void *a1,
        int a2,
        WCHAR *a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  int v9; // r11d
  __int64 v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r9
  _UNKNOWN **i; // r8
  signed __int32 *v14; // rdi
  signed __int32 v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  signed __int32 *j; // rsi
  signed __int32 *v20; // rbx
  signed __int32 v21; // eax
  _QWORD *Application; // rax
  __int64 v23; // rbp
  __int64 v24; // rsi
  signed __int32 v25; // eax
  __int64 *HostJobContext; // rdi
  unsigned int v27; // ebx
  __int64 v29; // rdx
  signed __int32 **v30; // rcx
  __int64 v31; // [rsp+50h] [rbp-58h]
  __int64 v32; // [rsp+58h] [rbp-50h]
  __int64 v33; // [rsp+60h] [rbp-48h]
  _DWORD *v36; // [rsp+E0h] [rbp+38h]

  v9 = *(_DWORD *)(a7 + 28);
  v33 = a7 & -(__int64)((v9 & 2) != 0);
  v32 = (a7 + 8) & -(__int64)((v9 & 4) != 0);
  v31 = (a7 + 16) & -(__int64)((v9 & 8) != 0);
  v10 = -1;
  v36 = (_DWORD *)((a7 + 24) & -(__int64)((v9 & 0x10) != 0));
  do
    ++v10;
  while ( a3[v10] );
  if ( (a6 & 0xFFFFFFF3) == 0 && a6 != 12 )
  {
    RtlAcquireSRWLockShared(&PsmpManagerLock);
    for ( i = (_UNKNOWN **)PsmpManagerList; i != &PsmpManagerList; i = (_UNKNOWN **)*i )
    {
      v14 = (signed __int32 *)(i - 5);
      if ( a2 == *((_DWORD *)i - 5) && a6 == v14[4] )
      {
        _m_prefetchw(v14);
        v15 = *v14;
        while ( v15 > 0 )
        {
          v11 = (unsigned int)v15;
          v15 = _InterlockedCompareExchange(v14, v15 + 1, v15);
          if ( v15 == (_DWORD)v11 )
            goto LABEL_12;
        }
      }
    }
    v14 = 0;
LABEL_12:
    RtlReleaseSRWLockShared(&PsmpManagerLock, v11, i, v12);
    if ( v14 )
    {
      RtlAcquireSRWLockShared(v14 + 2);
      for ( j = (signed __int32 *)*((_QWORD *)v14 + 3); j != v14 + 6; j = *(signed __int32 **)j )
      {
        v20 = j - 2;
        if ( *(j - 1) == a2 && RtlEqualSid(*((PSID *)v20 + 5), a1) )
        {
          _m_prefetchw(v20);
          v21 = *v20;
          while ( v21 > 0 )
          {
            v16 = (unsigned int)v21;
            v21 = _InterlockedCompareExchange(v20, v21 + 1, v21);
            if ( v21 == (_DWORD)v16 )
              goto LABEL_20;
          }
        }
      }
      v20 = 0;
LABEL_20:
      RtlReleaseSRWLockShared(v14 + 2, v16, v17, v18);
      if ( v20 )
      {
        Application = PsmpFindApplication(0, (__int64)v20, a3, 2 * v10 + 2);
        v23 = *((_QWORD *)v20 + 7);
        v24 = (__int64)Application;
        RtlAcquireSRWLockExclusive(v23 + 8);
        v25 = _InterlockedDecrement(v20);
        if ( v25 == -1 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        else if ( (v25 & 0x7FFFFFFF) == 0 )
        {
          v29 = *((_QWORD *)v20 + 1);
          if ( *(signed __int32 **)(v29 + 8) != v20 + 2
            || (v30 = (signed __int32 **)*((_QWORD *)v20 + 2), *v30 != v20 + 2) )
          {
            __fastfail(3u);
          }
          *v30 = (signed __int32 *)v29;
          *(_QWORD *)(v29 + 8) = v30;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
        }
        RtlReleaseSRWLockExclusive(v23 + 8);
        PsmpDereferenceManagerContext((char *)v14);
        if ( v24 )
        {
          HostJobContext = 0;
          RtlAcquireSRWLockExclusive(v24 + 328);
          if ( a4 != 4 || (HostJobContext = PsmpFindHostJobContext(v24, a5)) != 0 )
            v27 = PsmpSetApplicationProperties(v24, a4, a5, 0, v33, v32, v31, v36, 0);
          else
            v27 = -1073741772;
          RtlReleaseSRWLockExclusive(v24 + 328);
          if ( HostJobContext )
            PsmpDereferenceHostContext(HostJobContext, 0);
          PsmpDereferenceApplicationEx(v24, 0);
          return v27;
        }
      }
      else
      {
        PsmpDereferenceManagerContext((char *)v14);
      }
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      (unsigned int)&WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
      (_DWORD)a3,
      a2);
  return 3221225524LL;
}

```

## disassembly

```asm
0x180007fd0  mov     [rsp+arg_8], rbx
0x180007fd5  mov     [rsp+arg_18], r9d
0x180007fda  mov     [rsp+Sid2], rcx
0x180007fdf  push    rbp
0x180007fe0  push    rsi
0x180007fe1  push    rdi
0x180007fe2  push    r12
0x180007fe4  push    r13
0x180007fe6  push    r14
0x180007fe8  push    r15
0x180007fea  sub     rsp, 70h
0x180007fee  mov     r10, [rsp+0A8h+arg_30]
0x180007ff6  mov     r13, r8
0x180007ff9  mov     r12d, edx
0x180007ffc  mov     r11d, [r10+1Ch]
0x180008000  mov     eax, r11d
0x180008003  and     al, 2
0x180008005  mov     r9d, r11d
0x180008008  neg     al
0x18000800a  sbb     rax, rax
0x18000800d  and     r9b, 4
0x180008011  and     rax, r10
0x180008014  mov     [rsp+0A8h+var_48], rax
0x180008019  neg     r9b
0x18000801c  lea     rax, [r10+8]
0x180008020  sbb     rcx, rcx
0x180008023  and     rcx, rax
0x180008026  mov     eax, r11d
0x180008029  and     al, 8
0x18000802b  mov     [rsp+0A8h+var_50], rcx
0x180008030  neg     al
0x180008032  lea     rcx, [r10+10h]
0x180008036  sbb     rax, rax
0x180008039  and     r11b, 10h
0x18000803d  and     rax, rcx
0x180008040  neg     r11b
0x180008043  mov     [rsp+0A8h+var_58], rax
0x180008048  lea     rax, [r10+18h]
0x18000804c  sbb     rcx, rcx
0x18000804f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180008053  and     rcx, rax
0x180008056  mov     [rsp+0A8h+arg_30], rcx
0x18000805e  xor     esi, esi
0x180008060  inc     r15
0x180008063  cmp     [r8+r15*2], si
0x180008068  jnz     short loc_180008060
0x18000806a  mov     ebx, [rsp+0A8h+arg_28]
0x180008071  test    ebx, 0FFFFFFF3h
0x180008077  jnz     loc_180008263
0x18000807d  cmp     ebx, 0Ch
0x180008080  jz      loc_180008263
0x180008086  lea     rcx, PsmpManagerLock
0x18000808d  call    cs:__imp_RtlAcquireSRWLockShared
0x180008093  mov     r8, cs:PsmpManagerList
0x18000809a  lea     rax, PsmpManagerList
0x1800080a1  cmp     r8, rax
0x1800080a4  jz      loc_180008311
0x1800080aa  lea     rdi, [r8-28h]
0x1800080ae  cmp     r12d, [rdi+14h]
0x1800080b2  jnz     loc_18000824B
0x1800080b8  cmp     ebx, [rdi+10h]
0x1800080bb  jnz     loc_18000824B
0x1800080c1  prefetchw byte ptr [rdi]
0x1800080c4  mov     eax, [rdi]
0x1800080c6  test    eax, eax
0x1800080c8  jle     loc_18000824B
0x1800080ce  mov     edx, eax
0x1800080d0  lea     ecx, [rax+1]
0x1800080d3  lock cmpxchg [rdi], ecx
0x1800080d7  cmp     eax, edx
0x1800080d9  jnz     short loc_1800080C6
0x1800080db  lea     rcx, PsmpManagerLock
0x1800080e2  call    cs:__imp_RtlReleaseSRWLockShared
0x1800080e8  test    rdi, rdi
0x1800080eb  jz      loc_180008263
0x1800080f1  lea     rcx, [rdi+8]
0x1800080f5  call    cs:__imp_RtlAcquireSRWLockShared
0x1800080fb  lea     r14, [rdi+18h]
0x1800080ff  mov     rsi, [r14]
0x180008102  cmp     rsi, r14
0x180008105  jz      loc_180008319
0x18000810b  lea     rbx, [rsi-8]
0x18000810f  cmp     [rbx+4], r12d
0x180008113  jnz     loc_180008253
0x180008119  mov     rdx, [rsp+0A8h+Sid2]; Sid2
0x180008121  mov     rcx, [rbx+28h]; Sid1
0x180008125  call    cs:__imp_RtlEqualSid
0x18000812b  test    al, al
0x18000812d  jz      loc_180008253
0x180008133  prefetchw byte ptr [rbx]
0x180008136  mov     eax, [rbx]
0x180008138  test    eax, eax
0x18000813a  jle     loc_180008253
0x180008140  mov     edx, eax
0x180008142  lea     ecx, [rax+1]
0x180008145  lock cmpxchg [rbx], ecx
0x180008149  cmp     eax, edx
0x18000814b  jnz     short loc_180008138
0x18000814d  lea     rcx, [rdi+8]
0x180008151  call    cs:__imp_RtlReleaseSRWLockShared
0x180008157  test    rbx, rbx
0x18000815a  jz      loc_18000825B
0x180008160  lea     r9, ds:2[r15*2]
0x180008168  mov     r8, r13
0x18000816b  mov     rdx, rbx
0x18000816e  xor     ecx, ecx
0x180008170  call    PsmpFindApplication
0x180008175  mov     rbp, [rbx+38h]
0x180008179  mov     rsi, rax
0x18000817c  lea     rcx, [rbp+8]
0x180008180  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008186  or      eax, 0FFFFFFFFh
0x180008189  lock xadd [rbx], eax
0x18000818d  dec     eax
0x18000818f  cmp     eax, 0FFFFFFFFh
0x180008192  jz      loc_180008291
0x180008198  test    eax, 7FFFFFFFh
0x18000819d  jz      loc_18000829B
0x1800081a3  lea     rcx, [rbp+8]
0x1800081a7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800081ad  mov     rcx, rdi; P
0x1800081b0  call    PsmpDereferenceManagerContext
0x1800081b5  test    rsi, rsi
0x1800081b8  jz      loc_180008263
0x1800081be  lea     rbp, [rsi+148h]
0x1800081c5  xor     edi, edi
0x1800081c7  mov     rcx, rbp
0x1800081ca  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800081d0  mov     ebx, [rsp+0A8h+arg_18]
0x1800081d7  cmp     ebx, 4
0x1800081da  jz      loc_1800082EB
0x1800081e0  mov     rax, [rsp+0A8h+arg_30]
0x1800081e8  xor     r9d, r9d
0x1800081eb  mov     r8, [rsp+0A8h+arg_20]
0x1800081f3  mov     edx, ebx
0x1800081f5  mov     [rsp+0A8h+var_68], 0
0x1800081fe  mov     rcx, rsi
0x180008201  mov     [rsp+0A8h+var_70], rax
0x180008206  mov     rax, [rsp+0A8h+var_58]
0x18000820b  mov     [rsp+0A8h+var_78], rax
0x180008210  mov     rax, [rsp+0A8h+var_50]
0x180008215  mov     [rsp+0A8h+var_80], rax
0x18000821a  mov     rax, [rsp+0A8h+var_48]
0x18000821f  mov     [rsp+0A8h+var_88], rax
0x180008224  call    PsmpSetApplicationProperties
0x180008229  mov     ebx, eax
0x18000822b  mov     rcx, rbp
0x18000822e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008234  test    rdi, rdi
0x180008237  jnz     loc_1800082DC
0x18000823d  xor     edx, edx
0x18000823f  mov     rcx, rsi
0x180008242  call    PsmpDereferenceApplicationEx
0x180008247  mov     eax, ebx
0x180008249  jmp     short loc_180008279
0x18000824b  mov     r8, [r8]
0x18000824e  jmp     loc_18000809A
0x180008253  mov     rsi, [rsi]
0x180008256  jmp     loc_180008102
0x18000825b  mov     rcx, rdi; P
0x18000825e  call    PsmpDereferenceManagerContext
0x180008263  mov     rcx, cs:WPP_GLOBAL_Control
0x18000826a  test    byte ptr [rcx+1Ch], 2
0x18000826e  jnz     loc_180008320
0x180008274  mov     eax, 0C0000034h
0x180008279  mov     rbx, [rsp+0A8h+arg_8]
0x180008281  add     rsp, 70h
0x180008285  pop     r15
0x180008287  pop     r14
0x180008289  pop     r13
0x18000828b  pop     r12
0x18000828d  pop     rdi
0x18000828e  pop     rsi
0x18000828f  pop     rbp
0x180008290  retn
0x180008291  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008296  jmp     loc_1800081A3
0x18000829b  lea     rax, [rbx+8]
0x18000829f  mov     rdx, [rax]
0x1800082a2  cmp     [rdx+8], rax
0x1800082a6  jnz     short loc_1800082D5
0x1800082a8  mov     rcx, [rax+8]
0x1800082ac  cmp     [rcx], rax
0x1800082af  jnz     short loc_1800082D5
0x1800082b1  mov     [rcx], rdx
0x1800082b4  mov     r8, rbx; P
0x1800082b7  mov     [rdx+8], rcx
0x1800082bb  xor     edx, edx; Flags
0x1800082bd  mov     rcx, gs:60h
0x1800082c6  mov     rcx, [rcx+30h]; HeapHandle
0x1800082ca  call    cs:__imp_RtlFreeHeap
0x1800082d0  jmp     loc_1800081A3
0x1800082d5  mov     ecx, 3
0x1800082da  int     29h; Win8: RtlFailFast(ecx)
0x1800082dc  xor     edx, edx
0x1800082de  mov     rcx, rdi
0x1800082e1  call    PsmpDereferenceHostContext
0x1800082e6  jmp     loc_18000823D
0x1800082eb  mov     rdx, [rsp+0A8h+arg_20]
0x1800082f3  mov     rcx, rsi
0x1800082f6  call    PsmpFindHostJobContext
0x1800082fb  mov     rdi, rax
0x1800082fe  test    rax, rax
0x180008301  jnz     loc_1800081E0
0x180008307  mov     ebx, 0C0000034h
0x18000830c  jmp     loc_18000822B
0x180008311  mov     rdi, rsi
0x180008314  jmp     loc_1800080DB
0x180008319  xor     ebx, ebx
0x18000831b  jmp     loc_18000814D
0x180008320  cmp     byte ptr [rcx+19h], 2
0x180008324  jb      loc_180008274
0x18000832a  mov     rcx, [rcx+10h]
0x18000832e  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x180008335  mov     edx, 4Ah ; 'J'
0x18000833a  mov     dword ptr [rsp+0A8h+var_88], r12d
0x18000833f  mov     r9, r13
0x180008342  call    WPP_SF_Sd
0x180008347  jmp     loc_180008274
```
