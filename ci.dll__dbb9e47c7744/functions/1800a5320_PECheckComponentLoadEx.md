# PECheckComponentLoadEx

- ea: `0x1800a5320`
- end: `0x1800a55de`
- name: `PECheckComponentLoadEx`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a5118`

## callees

- `0x18000ea44`
- `0x18000ec18`
- `0x18000ee04`
- `0x1800203e4`
- `0x18002bf20`
- `0x18008047c`
- `0x1800a5320`
- `0x1800a55e4`
- `0x1800a56e4`
- `0x1800a59e4`
- `0x1800a5b5c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a5416`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a5416`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5477`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5477`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a542b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a542b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a546b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a546b`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800a5595`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800a5595`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a5391`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a5391`

## pseudocode

```c
__int64 __fastcall PECheckComponentLoadEx(
        void *a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        unsigned int a4,
        int a5,
        _DWORD *a6)
{
  int v8; // esi
  int DPLForInterrupt; // ebx
  int v10; // eax
  unsigned int v11; // edi
  int v12; // r14d
  unsigned int v13; // ebx
  const UNICODE_STRING *v14; // r14
  unsigned int v15; // edi
  __int64 *v16; // rdx
  int v18; // esi
  char v19[4]; // [rsp+30h] [rbp-48h] BYREF
  __int16 SystemInformation; // [rsp+34h] [rbp-44h] BYREF
  char v21; // [rsp+36h] [rbp-42h]
  int v22; // [rsp+38h] [rbp-40h] BYREF
  int v23; // [rsp+3Ch] [rbp-3Ch] BYREF
  const UNICODE_STRING *v24; // [rsp+40h] [rbp-38h]
  void *Source2; // [rsp+48h] [rbp-30h]
  __int128 v26; // [rsp+50h] [rbp-28h] BYREF
  int v27; // [rsp+60h] [rbp-18h]

  v24 = a3;
  Source2 = a1;
  v27 = 0;
  v23 = 0;
  v26 = 0;
  v8 = 0;
  v22 = 0;
  v19[0] = 0;
  if ( g_PEAuthStateVariables )
  {
    SystemInformation = 0;
    v21 = 0;
    if ( ZwQuerySystemInformation(SystemFileCacheInformation|0x80, &SystemInformation, 3u, 0) < 0
      || (_BYTE)SystemInformation
      || (DPLForInterrupt = GetDPLForInterrupt(1), v10 = GetDPLForInterrupt(65), DPLForInterrupt)
      || v10
      || (unsigned __int8)GetDR7Value() )
    {
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
  }
  v11 = I_PELoadGRL(a1, a2, a3);
  v12 = 2;
  if ( a2 )
  {
    v13 = v11 | I_PECheckMincryptPolicy(a2, a4, (unsigned int)&v26, (unsigned int)&v23, (__int64)&v22);
    if ( v13 )
    {
      v8 = v22;
    }
    else
    {
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
      if ( qword_180049410 )
        v13 = (unsigned int)MFIsHashInGRL(qword_180049410, Source2, a4 == 0) != 0 ? 0x2000 : 0;
      else
        v13 |= 0x1000u;
      ExReleaseResourceLite(&g_GRLContextLock);
      KeLeaveCriticalRegion();
      v8 = v22;
      if ( v22 == 0x10002 )
      {
        if ( (int)PEAuthGetDebugCredentialsData(v19) < 0 )
        {
          PEAuthStoreParameter(1, 0);
          g_PEAuthStateVariables = 0;
          PEAuthStoreParameter(2, 0);
        }
        if ( !v19[0] )
          v13 |= 0x10000u;
      }
    }
  }
  else
  {
    v13 = v11;
  }
  if ( v13 )
  {
    v15 = -1073740760;
    v18 = 1;
    if ( (v13 & 0xFFFFEFCF) == 0 )
    {
      v15 = 0;
      v18 = 0;
      *a6 |= v13;
    }
    if ( a4 )
    {
      v15 = 0;
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 |= v12;
    if ( PsIsCurrentThreadPrefetching() )
    {
      v18 = 0;
    }
    else if ( (g_PEAuthConfigOptions & 1) != 0 )
    {
      v14 = v24;
      I_PEWriteComponentLoadExEvents(v13, *(unsigned int *)(a2 + 8), v24, a4);
LABEL_24:
      if ( !v18 )
        return v15;
      goto LABEL_16;
    }
    v14 = v24;
    goto LABEL_24;
  }
  v14 = v24;
  v15 = 0;
  if ( (v8 & 0x10000) != 0 )
    *a6 |= 0x1000000u;
LABEL_16:
  if ( Source2 )
  {
    v16 = (__int64 *)&v26;
    if ( !v23 )
      v16 = g_rgEmptyHash;
    I_PEUpdateHashCache(Source2, (__int64)v16, v14, v13, a4, a5);
  }
  return v15;
}

```

## disassembly

```asm
0x1800a5320  push    rbp
0x1800a5322  push    rbx
0x1800a5323  push    rsi
0x1800a5324  push    rdi
0x1800a5325  push    r12
0x1800a5327  push    r13
0x1800a5329  push    r14
0x1800a532b  push    r15
0x1800a532d  mov     rbp, rsp
0x1800a5330  sub     rsp, 78h
0x1800a5334  mov     rax, cs:__security_cookie
0x1800a533b  xor     rax, rsp
0x1800a533e  mov     [rbp+var_10], rax
0x1800a5342  mov     r15, [rbp+arg_28]
0x1800a5346  xor     edi, edi
0x1800a5348  xor     eax, eax
0x1800a534a  mov     [rbp+var_38], r8
0x1800a534e  cmp     cs:g_PEAuthStateVariables, edi
0x1800a5354  xorps   xmm0, xmm0
0x1800a5357  mov     r12d, r9d
0x1800a535a  mov     [rbp+Source2], rcx
0x1800a535e  mov     r13, rdx
0x1800a5361  mov     [rbp+var_18], eax
0x1800a5364  lea     r14d, [rax+1]
0x1800a5368  mov     [rbp+var_3C], edi
0x1800a536b  movups  [rbp+var_28], xmm0
0x1800a536f  mov     esi, edi
0x1800a5371  mov     [rbp+var_40], edi
0x1800a5374  mov     [rbp+var_48], dil
0x1800a5378  jz      short loc_1800A53DA
0x1800a537a  xor     r9d, r9d; ReturnLength
0x1800a537d  mov     [rbp+SystemInformation], ax
0x1800a5381  lea     r8d, [rax+3]; SystemInformationLength
0x1800a5385  mov     [rbp+var_42], al
0x1800a5388  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x1800a538c  mov     ecx, 95h; SystemInformationClass
0x1800a5391  call    cs:__imp_ZwQuerySystemInformation
0x1800a5398  nop     dword ptr [rax+rax+00h]
0x1800a539d  test    eax, eax
0x1800a539f  js      short loc_1800A53CA
0x1800a53a1  cmp     byte ptr [rbp+SystemInformation], dil
0x1800a53a5  jnz     short loc_1800A53CA
0x1800a53a7  mov     ecx, r14d
0x1800a53aa  call    GetDPLForInterrupt
0x1800a53af  lea     ecx, [rdi+41h]
0x1800a53b2  mov     ebx, eax
0x1800a53b4  call    GetDPLForInterrupt
0x1800a53b9  test    ebx, ebx
0x1800a53bb  jnz     short loc_1800A53CA
0x1800a53bd  test    eax, eax
0x1800a53bf  jnz     short loc_1800A53CA
0x1800a53c1  call    GetDR7Value
0x1800a53c6  test    al, al
0x1800a53c8  jz      short loc_1800A53DA
0x1800a53ca  xor     edx, edx
0x1800a53cc  mov     ecx, r14d
0x1800a53cf  call    PEAuthStoreParameter
0x1800a53d4  mov     cs:g_PEAuthStateVariables, edi
0x1800a53da  call    I_PELoadGRL
0x1800a53df  mov     edi, eax
0x1800a53e1  mov     r14d, 2
0x1800a53e7  test    r13, r13
0x1800a53ea  jz      loc_1800A5503
0x1800a53f0  lea     rax, [rbp+var_40]
0x1800a53f4  mov     edx, r12d
0x1800a53f7  lea     r9, [rbp+var_3C]
0x1800a53fb  mov     qword ptr [rsp+78h+var_58], rax
0x1800a5400  lea     r8, [rbp+var_28]
0x1800a5404  mov     rcx, r13
0x1800a5407  call    I_PECheckMincryptPolicy
0x1800a540c  mov     ebx, eax
0x1800a540e  or      ebx, edi
0x1800a5410  jnz     loc_1800A5510
0x1800a5416  call    cs:__imp_KeEnterCriticalRegion
0x1800a541d  nop     dword ptr [rax+rax+00h]
0x1800a5422  mov     dl, 1; Wait
0x1800a5424  lea     rcx, g_GRLContextLock; Resource
0x1800a542b  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a5432  nop     dword ptr [rax+rax+00h]
0x1800a5437  mov     rcx, cs:qword_180049410
0x1800a543e  test    rcx, rcx
0x1800a5441  jz      loc_1800A5507
0x1800a5447  mov     rdx, [rbp+Source2]
0x1800a544b  xor     r8d, r8d
0x1800a544e  test    r12d, r12d
0x1800a5451  setz    r8b
0x1800a5455  call    MFIsHashInGRL
0x1800a545a  neg     eax
0x1800a545c  sbb     ebx, ebx
0x1800a545e  and     ebx, 2000h
0x1800a5464  lea     rcx, g_GRLContextLock; Resource
0x1800a546b  call    cs:__imp_ExReleaseResourceLite
0x1800a5472  nop     dword ptr [rax+rax+00h]
0x1800a5477  call    cs:__imp_KeLeaveCriticalRegion
0x1800a547e  nop     dword ptr [rax+rax+00h]
0x1800a5483  mov     esi, [rbp+var_40]
0x1800a5486  mov     eax, esi
0x1800a5488  xor     eax, 10002h
0x1800a548d  jz      loc_1800A551E
0x1800a5493  test    ebx, ebx
0x1800a5495  jnz     loc_1800A555C
0x1800a549b  mov     r14, [rbp+var_38]
0x1800a549f  xor     edi, edi
0x1800a54a1  bt      esi, 10h
0x1800a54a5  jb      loc_1800A55D4
0x1800a54ab  mov     rax, [rbp+Source2]
0x1800a54af  test    rax, rax
0x1800a54b2  jz      short loc_1800A54E3
0x1800a54b4  cmp     [rbp+var_3C], 0
0x1800a54b8  lea     r8, g_rgEmptyHash
0x1800a54bf  mov     r10d, [rbp+arg_20]
0x1800a54c3  lea     rdx, [rbp+var_28]
0x1800a54c7  cmovz   rdx, r8
0x1800a54cb  mov     [rsp+78h+var_50], r10d; int
0x1800a54d0  mov     r8, r14
0x1800a54d3  mov     [rsp+78h+var_58], r12d; int
0x1800a54d8  mov     r9d, ebx
0x1800a54db  mov     rcx, rax; Source2
0x1800a54de  call    I_PEUpdateHashCache
0x1800a54e3  mov     eax, edi
0x1800a54e5  mov     rcx, [rbp+var_10]
0x1800a54e9  xor     rcx, rsp; StackCookie
0x1800a54ec  call    __security_check_cookie
0x1800a54f1  add     rsp, 78h
0x1800a54f5  pop     r15
0x1800a54f7  pop     r14
0x1800a54f9  pop     r13
0x1800a54fb  pop     r12
0x1800a54fd  pop     rdi
0x1800a54fe  pop     rsi
0x1800a54ff  pop     rbx
0x1800a5500  pop     rbp
0x1800a5501  retn
0x1800a5503  mov     ebx, edi
0x1800a5505  jmp     short loc_1800A5493
0x1800a5507  bts     ebx, 0Ch
0x1800a550b  jmp     loc_1800A5464
0x1800a5510  mov     esi, [rbp+var_40]
0x1800a5513  jmp     loc_1800A5493
0x1800a5518  test    esi, esi
0x1800a551a  jz      short loc_1800A54E3
0x1800a551c  jmp     short loc_1800A54AB
0x1800a551e  lea     rcx, [rbp+var_48]
0x1800a5522  call    PEAuthGetDebugCredentialsData
0x1800a5527  test    eax, eax
0x1800a5529  jns     short loc_1800A5549
0x1800a552b  xor     edx, edx
0x1800a552d  lea     ecx, [rdx+1]
0x1800a5530  call    PEAuthStoreParameter
0x1800a5535  xor     edx, edx
0x1800a5537  mov     cs:g_PEAuthStateVariables, 0
0x1800a5541  mov     ecx, r14d
0x1800a5544  call    PEAuthStoreParameter
0x1800a5549  cmp     [rbp+var_48], 0
0x1800a554d  ja      loc_1800A5493
0x1800a5553  bts     ebx, 10h
0x1800a5557  jmp     loc_1800A5493
0x1800a555c  mov     eax, 1
0x1800a5561  mov     edi, 0C0000428h
0x1800a5566  mov     esi, eax
0x1800a5568  test    ebx, 0FFFFEFCFh
0x1800a556e  jnz     short loc_1800A5577
0x1800a5570  xor     edi, edi
0x1800a5572  xor     esi, esi
0x1800a5574  or      [r15], ebx
0x1800a5577  test    r12d, r12d
0x1800a557a  jz      short loc_1800A558F
0x1800a557c  xor     edi, edi
0x1800a557e  xor     edx, edx
0x1800a5580  mov     ecx, eax
0x1800a5582  call    PEAuthStoreParameter
0x1800a5587  mov     cs:g_PEAuthStateVariables, edi
0x1800a558d  jmp     short loc_1800A5592
0x1800a558f  mov     r14d, eax
0x1800a5592  or      ebx, r14d
0x1800a5595  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800a559c  nop     dword ptr [rax+rax+00h]
0x1800a55a1  test    al, al
0x1800a55a3  jz      short loc_1800A55B0
0x1800a55a5  xor     esi, esi
0x1800a55a7  mov     r14, [rbp+var_38]
0x1800a55ab  jmp     loc_1800A5518
0x1800a55b0  mov     eax, cs:g_PEAuthConfigOptions
0x1800a55b6  test    al, 1
0x1800a55b8  jz      short loc_1800A55A7
0x1800a55ba  mov     r14, [rbp+var_38]
0x1800a55be  mov     r9d, r12d
0x1800a55c1  mov     edx, [r13+8]
0x1800a55c5  mov     r8, r14
0x1800a55c8  mov     ecx, ebx
0x1800a55ca  call    I_PEWriteComponentLoadExEvents
0x1800a55cf  jmp     loc_1800A5518
0x1800a55d4  bts     dword ptr [r15], 18h
0x1800a55d9  jmp     loc_1800A54AB
```
