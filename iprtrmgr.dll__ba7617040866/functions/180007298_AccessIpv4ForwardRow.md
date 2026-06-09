# AccessIpv4ForwardRow

- ea: `0x180007298`
- end: `0x1800075a5`
- name: `AccessIpv4ForwardRow`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005db0`

## callees

- `0x180007298`
- `0x18000aa9c`
- `0x18000ac60`
- `0x18000ace0`
- `0x18000baa8`
- `0x18002e6e8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180007402`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007402`
- `ntdll!RtlReleaseResource` at `0x180007552`
- `ntdll!RtlReleaseResource` at `0x180007552`
- `ntdll!RtlAcquireResourceShared` at `0x18000740a`
- `ntdll!RtlAcquireResourceShared` at `0x18000740a`

## string_xrefs

- `0x180007304`: `AccessIpForwardRow`
- `0x18000735d`: `Leaving: AccessIpForwardRow`
- `0x180007561`: `Leaving: AccessIpForwardRow`
- `0x1800073a8`: `AccessIpForwardRow: Error %d updating IpForward Cache`

## pseudocode

```c
__int64 __fastcall AccessIpv4ForwardRow(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v10; // eax
  unsigned int updated; // eax
  unsigned int IpForwardRow; // edi
  char v14; // cl
  bool v15; // zf
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // eax
  __int64 v22; // rbx
  char *v23; // rax
  __int64 v24; // rcx
  char *v25; // rax
  unsigned int v26[4]; // [rsp+20h] [rbp-848h] BYREF
  int v27; // [rsp+30h] [rbp-838h] BYREF
  char v28[2044]; // [rsp+34h] [rbp-834h] BYREF

  v26[0] = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Entered: %ws", L"AccessIpForwardRow");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v27);
  }
  if ( a1 != 9 )
  {
    v10 = *a4;
    *a4 = 64;
    if ( v10 < 0x40 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessIpForwardRow");
      return 122;
    }
    *(_DWORD *)a5 = 8;
  }
  updated = UpdateCache(1, a6);
  IpForwardRow = updated;
  if ( updated )
  {
    v14 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v27, L"AccessIpForwardRow: Error %d updating IpForward Cache", updated);
      v14 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v27);
        v14 = Microsoft_Windows_RRASEnableBits;
      }
    }
    v15 = v14 >= 0;
    goto LABEL_37;
  }
  if ( a1 <= 4 )
    RtlAcquireResourceShared(&stru_18008C260, 1u);
  else
    RtlAcquireResourceExclusive(&stru_18008C260, 1u);
  IpForwardRow = LocateIpForwardRow(a1, (a2 >> 2) - 1, a3 + 4, v26);
  if ( IpForwardRow )
  {
    if ( ((a1 - 5) & 0xFFFFFFFD) == 0 )
    {
      if ( *(_DWORD *)(a5 + 32) != 2 )
      {
        v21 = SetIpForwardRow(0, a5 + 8);
LABEL_34:
        IpForwardRow = v21;
        if ( !v21 )
          dword_18008C824 = 0;
        goto LABEL_36;
      }
      IpForwardRow = 87;
    }
  }
  else
  {
    v16 = a1 - 1;
    if ( v16 && (v17 = v16 - 1) != 0 && (v18 = v17 - 2) != 0 )
    {
      v19 = v18 - 1;
      if ( !v19 )
      {
        v22 = 56LL * v26[0];
        IpForwardRow = SetIpForwardRow((char *)qword_18008C7E8 + v22 + 4, a5 + 8);
        if ( !IpForwardRow )
        {
          v23 = (char *)qword_18008C7E8;
          *(_OWORD *)((char *)qword_18008C7E8 + v22 + 4) = *(_OWORD *)(a5 + 8);
          *(_OWORD *)&v23[v22 + 20] = *(_OWORD *)(a5 + 24);
          *(_OWORD *)&v23[v22 + 36] = *(_OWORD *)(a5 + 40);
          *(_QWORD *)&v23[v22 + 52] = *(_QWORD *)(a5 + 56);
        }
        goto LABEL_36;
      }
      v20 = v19 - 2;
      if ( v20 )
      {
        if ( v20 == 2 )
        {
          v21 = DeleteIpForwardRow((char *)qword_18008C7E8 + 56 * v26[0] + 4);
          goto LABEL_34;
        }
      }
      else
      {
        IpForwardRow = 183;
      }
    }
    else
    {
      v24 = 56LL * v26[0];
      v25 = (char *)qword_18008C7E8;
      *(_OWORD *)(a5 + 8) = *(_OWORD *)((char *)qword_18008C7E8 + v24 + 4);
      *(_OWORD *)(a5 + 24) = *(_OWORD *)&v25[v24 + 20];
      *(_OWORD *)(a5 + 40) = *(_OWORD *)&v25[v24 + 36];
      *(_QWORD *)(a5 + 56) = *(_QWORD *)&v25[v24 + 52];
    }
  }
LABEL_36:
  RtlReleaseResource(&stru_18008C260);
  v15 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
LABEL_37:
  if ( !v15 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessIpForwardRow");
  return IpForwardRow;
}

```

## disassembly

```asm
0x180007298  mov     [rsp+arg_0], rbx
0x18000729d  push    rsi
0x18000729e  push    rdi
0x18000729f  push    r13
0x1800072a1  push    r14
0x1800072a3  push    r15
0x1800072a5  sub     rsp, 840h
0x1800072ac  mov     rax, cs:__security_cookie
0x1800072b3  xor     rax, rsp
0x1800072b6  mov     [rsp+868h+var_38], rax
0x1800072be  mov     rsi, [rsp+868h+arg_20]
0x1800072c6  mov     r13, r8
0x1800072c9  mov     r15, [rsp+868h+arg_28]
0x1800072d1  mov     r14d, edx
0x1800072d4  mov     ebx, ecx
0x1800072d6  mov     [rsp+868h+var_848], 0
0x1800072de  xor     eax, eax
0x1800072e0  lea     rcx, [rsp+868h+var_834]; void *
0x1800072e5  xor     edx, edx; Val
0x1800072e7  mov     [rsp+868h+var_838], eax
0x1800072eb  mov     r8d, 7FCh; Size
0x1800072f1  mov     rdi, r9
0x1800072f4  call    memset_0
0x1800072f9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007300  jge     short loc_180007342
0x180007302  xor     eax, eax
0x180007304  lea     r8, aAccessipforwar_5; "AccessIpForwardRow"
0x18000730b  lea     rdx, aEnteredWs; "Entered: %ws"
0x180007312  mov     word ptr [rsp+868h+var_838], ax
0x180007317  lea     rcx, [rsp+868h+var_838]
0x18000731c  call    FormatRRASErrorString
0x180007321  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007328  jge     short loc_180007342
0x18000732a  lea     r8, [rsp+868h+var_838]
0x18000732f  lea     rdx, RasRtrmgrTraceInfo
0x180007336  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000733d  call    McTemplateU0z_EventWriteTransfer
0x180007342  cmp     ebx, 9
0x180007345  jz      short loc_180007387
0x180007347  mov     eax, [rdi]
0x180007349  mov     dword ptr [rdi], 40h ; '@'
0x18000734f  cmp     eax, 40h ; '@'
0x180007352  jnb     short loc_180007381
0x180007354  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000735b  jz      short loc_180007377
0x18000735d  lea     r8, aLeavingAccessi_7; "Leaving: AccessIpForwardRow"
0x180007364  lea     rdx, RasRtrmgrTraceInfo
0x18000736b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007372  call    McTemplateU0z_EventWriteTransfer
0x180007377  mov     eax, 7Ah ; 'z'
0x18000737c  jmp     loc_18000757D
0x180007381  mov     dword ptr [rsi], 8
0x180007387  mov     rdx, r15
0x18000738a  mov     ecx, 1
0x18000738f  call    UpdateCache
0x180007394  mov     edi, eax
0x180007396  test    eax, eax
0x180007398  jz      short loc_1800073F4
0x18000739a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800073a1  test    cl, 40h
0x1800073a4  jz      short loc_1800073EC
0x1800073a6  xor     ecx, ecx
0x1800073a8  lea     rdx, aAccessipforwar_1; "AccessIpForwardRow: Error %d updating I"...
0x1800073af  mov     word ptr [rsp+868h+var_838], cx
0x1800073b4  mov     r8d, eax
0x1800073b7  lea     rcx, [rsp+868h+var_838]
0x1800073bc  call    FormatRRASErrorString
0x1800073c1  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800073c8  test    cl, 40h
0x1800073cb  jz      short loc_1800073EC
0x1800073cd  lea     r8, [rsp+868h+var_838]
0x1800073d2  lea     rdx, RasRtrMgrTraceError
0x1800073d9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800073e0  call    McTemplateU0z_EventWriteTransfer
0x1800073e5  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x1800073ec  test    cl, 80h
0x1800073ef  jmp     loc_18000755F
0x1800073f4  lea     rcx, stru_18008C260; Resource
0x1800073fb  mov     dl, 1; Wait
0x1800073fd  cmp     ebx, 4
0x180007400  jbe     short loc_18000740A
0x180007402  call    cs:__imp_RtlAcquireResourceExclusive
0x180007408  jmp     short loc_180007410
0x18000740a  call    cs:__imp_RtlAcquireResourceShared
0x180007410  shr     r14d, 2
0x180007414  lea     r8, [r13+4]
0x180007418  lea     r9, [rsp+868h+var_848]
0x18000741d  mov     ecx, ebx
0x18000741f  lea     edx, [r14-1]
0x180007423  call    LocateIpForwardRow
0x180007428  mov     edi, eax
0x18000742a  test    eax, eax
0x18000742c  jnz     loc_180007519
0x180007432  sub     ebx, 1
0x180007435  jz      loc_1800074E2
0x18000743b  sub     ebx, 1
0x18000743e  jz      loc_1800074E2
0x180007444  sub     ebx, 2
0x180007447  jz      loc_1800074E2
0x18000744d  sub     ebx, 1
0x180007450  jz      short loc_18000748A
0x180007452  sub     ebx, 2
0x180007455  jz      short loc_180007480
0x180007457  cmp     ebx, 2
0x18000745a  jnz     loc_18000754B
0x180007460  mov     eax, [rsp+868h+var_848]
0x180007464  imul    rcx, rax, 38h ; '8'
0x180007468  mov     rax, cs:qword_18008C7E8
0x18000746f  add     rax, 4
0x180007473  add     rcx, rax
0x180007476  call    DeleteIpForwardRow
0x18000747b  jmp     loc_18000753B
0x180007480  mov     edi, 0B7h
0x180007485  jmp     loc_18000754B
0x18000748a  mov     eax, [rsp+868h+var_848]
0x18000748e  lea     rdx, [rsi+8]
0x180007492  mov     rcx, cs:qword_18008C7E8
0x180007499  imul    rbx, rax, 38h ; '8'
0x18000749d  add     rcx, 4
0x1800074a1  add     rcx, rbx
0x1800074a4  call    SetIpForwardRow
0x1800074a9  mov     edi, eax
0x1800074ab  test    eax, eax
0x1800074ad  jnz     loc_18000754B
0x1800074b3  movups  xmm0, xmmword ptr [rsi+8]
0x1800074b7  mov     rax, cs:qword_18008C7E8
0x1800074be  movups  xmmword ptr [rbx+rax+4], xmm0
0x1800074c3  movups  xmm1, xmmword ptr [rsi+18h]
0x1800074c7  movups  xmmword ptr [rbx+rax+14h], xmm1
0x1800074cc  movups  xmm0, xmmword ptr [rsi+28h]
0x1800074d0  movups  xmmword ptr [rbx+rax+24h], xmm0
0x1800074d5  movsd   xmm1, qword ptr [rsi+38h]
0x1800074da  movsd   qword ptr [rbx+rax+34h], xmm1
0x1800074e0  jmp     short loc_18000754B
0x1800074e2  mov     eax, [rsp+868h+var_848]
0x1800074e6  imul    rcx, rax, 38h ; '8'
0x1800074ea  mov     rax, cs:qword_18008C7E8
0x1800074f1  movups  xmm0, xmmword ptr [rcx+rax+4]
0x1800074f6  movups  xmmword ptr [rsi+8], xmm0
0x1800074fa  movups  xmm1, xmmword ptr [rcx+rax+14h]
0x1800074ff  movups  xmmword ptr [rsi+18h], xmm1
0x180007503  movups  xmm0, xmmword ptr [rcx+rax+24h]
0x180007508  movups  xmmword ptr [rsi+28h], xmm0
0x18000750c  movsd   xmm1, qword ptr [rcx+rax+34h]
0x180007512  movsd   qword ptr [rsi+38h], xmm1
0x180007517  jmp     short loc_18000754B
0x180007519  lea     eax, [rbx-5]
0x18000751c  test    eax, 0FFFFFFFDh
0x180007521  jnz     short loc_18000754B
0x180007523  cmp     dword ptr [rsi+20h], 2
0x180007527  jnz     short loc_180007530
0x180007529  mov     edi, 57h ; 'W'
0x18000752e  jmp     short loc_18000754B
0x180007530  lea     rdx, [rsi+8]
0x180007534  xor     ecx, ecx
0x180007536  call    SetIpForwardRow
0x18000753b  mov     edi, eax
0x18000753d  test    eax, eax
0x18000753f  jnz     short loc_18000754B
0x180007541  mov     cs:dword_18008C824, 0
0x18000754b  lea     rcx, stru_18008C260; Resource
0x180007552  call    cs:__imp_RtlReleaseResource
0x180007558  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000755f  jz      short loc_18000757B
0x180007561  lea     r8, aLeavingAccessi_7; "Leaving: AccessIpForwardRow"
0x180007568  lea     rdx, RasRtrmgrTraceInfo
0x18000756f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007576  call    McTemplateU0z_EventWriteTransfer
0x18000757b  mov     eax, edi
0x18000757d  mov     rcx, [rsp+868h+var_38]
0x180007585  xor     rcx, rsp; StackCookie
0x180007588  call    __security_check_cookie
0x18000758d  mov     rbx, [rsp+868h+arg_0]
0x180007595  add     rsp, 840h
0x18000759c  pop     r15
0x18000759e  pop     r14
0x1800075a0  pop     r13
0x1800075a2  pop     rdi
0x1800075a3  pop     rsi
0x1800075a4  retn
```
