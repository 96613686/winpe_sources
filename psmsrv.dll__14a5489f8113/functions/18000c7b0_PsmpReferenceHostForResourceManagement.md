# PsmpReferenceHostForResourceManagement

- ea: `0x18000c7b0`
- end: `0x18000cb2c`
- name: `PsmpReferenceHostForResourceManagement`
- size: `892`
- prototype: `__int64 __fastcall(void *, unsigned int, _WORD *, int, __int64, char, char, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x180009b40`
- `0x18000a750`
- `0x18000c7b0`
- `0x18000cb34`
- `0x18000cb7c`
- `0x18000d378`
- `0x18000de88`
- `0x18000e3d0`
- `0x18001720c`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001ea9c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000c8f0`
- `ntdll!RtlCopySid` at `0x18000c8f0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c9ef`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c9ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ca1f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ca1f`
- `ext-ms-win-core-psm-service-l1-1-6!PsmHamReferenceHostId` at `0x18000c9d1`
- `ext-ms-win-core-psm-service-l1-1-6!PsmHamReferenceHostId` at `0x18000c9d1`
- `ext-ms-win-core-psm-service-l1-1-6!PsmHamDereferenceHostId` at `0x18000cb21`
- `ext-ms-win-core-psm-service-l1-1-6!PsmHamDereferenceHostId` at `0x18000cb21`

## pseudocode

```c
__int64 __fastcall PsmpReferenceHostForResourceManagement(
        void *a1,
        unsigned int a2,
        _WORD *a3,
        int a4,
        __int64 a5,
        char a6,
        char a7,
        _QWORD *a8)
{
  int v9; // r12d
  __int64 v11; // rbx
  unsigned int v12; // esi
  __int64 *v13; // r14
  __int64 v14; // rdx
  _WORD *v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rcx
  _WORD *v18; // rdx
  _WORD *v19; // rax
  bool v20; // zf
  _WORD *v21; // rcx
  PSID pSid; // rbx
  PSID v23; // r8
  int v24; // eax
  __int64 v25; // r15
  int v26; // edi
  __int64 v28; // rbx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h]
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  PSID SourceSid; // [rsp+60h] [rbp-A0h]
  _WORD *v38; // [rsp+68h] [rbp-98h]
  _QWORD *v39; // [rsp+70h] [rbp-90h]
  _DWORD v40[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v41[464]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE DestinationSid[72]; // [rsp+258h] [rbp+158h] BYREF

  v9 = 1;
  v38 = a3;
  v33 = a5;
  v11 = 232;
  v12 = (a7 & 1) << 30;
  v13 = 0;
  SourceSid = a1;
  v39 = a8;
  v36 = 0;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  if ( !a3 )
    goto LABEL_38;
  v14 = 232;
  v15 = a3;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = (232 - v14) & -(__int64)(v14 != 0);
  if ( !v14 )
LABEL_38:
    LODWORD(v16) = 0;
  memset_0(v41, 0, 0x218u);
  v17 = 2147483646;
  v40[0] = a2;
  v18 = a3;
  v40[1] = 2 * v16 + 2;
  v19 = v41;
  do
  {
    if ( !v17 )
      break;
    if ( !*v18 )
      break;
    *v19 = *v18;
    --v17;
    ++v19;
    ++v18;
    --v11;
  }
  while ( v11 );
  v20 = v11 == 0;
  v21 = v19 - 1;
  pSid = SourceSid;
  if ( !v20 )
    v21 = v19;
  v23 = SourceSid;
  *v21 = 0;
  RtlCopySid(0x44u, DestinationSid, v23);
  DestinationSid[68] = a6;
  v24 = PsmpAllocateOrLookupApplicationEx(v40, v12, 0, &v36);
  v25 = v36;
  v26 = v24;
  if ( v24 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S_sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), pSid, a2);
    goto LABEL_14;
  }
  v28 = v33;
  if ( a4 == 4 )
  {
    v26 = PsmpFindOrCreateHostJobContext(v36, v33, &v32);
    if ( v26 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_ii(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
          *(_QWORD *)(v25 + 96),
          v28);
      v13 = (__int64 *)v32;
      goto LABEL_30;
    }
    v13 = (__int64 *)v32;
    _interlockedbittestandset((volatile signed __int32 *)(v32 + 84), 4u);
    v12 |= 8u;
  }
  else if ( a4 == 8 )
  {
    v12 |= 4u;
  }
  if ( (a7 & 2) != 0 || (v35 = PsmHamReferenceHostId(v38, SourceSid, a2, v28)) != 0 )
  {
    RtlAcquireSRWLockExclusive(v25 + 328);
    v26 = PsmpCreateAndInitializeHostJob(v25, v12, v33, (__int64)v13, 0, &v35);
    RtlReleaseSRWLockExclusive(v25 + 328);
    if ( v26 >= 0 )
    {
      if ( a4 != 4 )
      {
        v30 = 0;
        if ( a4 == 8 )
          v30 = 2;
        v9 = v30;
      }
      v26 = PsmpInternalWorkItemReferenceCreate(v25, (__int64)v13, v9, &v34);
      if ( v26 >= 0 )
      {
        *v39 = v34;
        v29 = 0;
        v26 = 0;
      }
      else
      {
        v29 = v34;
      }
      if ( v29 )
        PsmpInternalWorkItemReferenceDestroy(v29);
    }
  }
  else
  {
    v26 = -1058275322;
  }
LABEL_30:
  if ( v13 )
    PsmpDereferenceHostContext(v13, 0);
LABEL_14:
  if ( v25 )
    PsmpDereferenceApplicationEx(v25, 0);
  if ( v35 )
    PsmHamDereferenceHostId();
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18000c7b0  mov     [rsp-8+arg_18], rbx
0x18000c7b5  push    rbp
0x18000c7b6  push    rsi
0x18000c7b7  push    rdi
0x18000c7b8  push    r12
0x18000c7ba  push    r13
0x18000c7bc  push    r14
0x18000c7be  push    r15
0x18000c7c0  lea     rbp, [rsp-1B0h]
0x18000c7c8  sub     rsp, 2B0h
0x18000c7cf  mov     rax, cs:__security_cookie
0x18000c7d6  xor     rax, rsp
0x18000c7d9  mov     [rbp+1E0h+var_40], rax
0x18000c7e0  mov     esi, dword ptr [rbp+1E0h+arg_30]
0x18000c7e6  mov     r15, r8
0x18000c7e9  mov     rax, [rbp+1E0h+arg_38]
0x18000c7f0  mov     r12d, 1
0x18000c7f6  mov     [rsp+2E0h+var_278], r8
0x18000c7fb  and     esi, r12d
0x18000c7fe  mov     r8, [rbp+1E0h+arg_20]
0x18000c805  mov     r13d, r9d
0x18000c808  mov     [rsp+2E0h+var_2A0], r8
0x18000c80d  mov     ebx, 0E8h
0x18000c812  xor     r8d, r8d
0x18000c815  shl     esi, 1Eh
0x18000c818  mov     dword ptr [rsp+2E0h+var_2B0], edx
0x18000c81c  mov     r14d, r8d
0x18000c81f  mov     [rsp+2E0h+SourceSid], rcx
0x18000c824  mov     [rsp+2E0h+var_270], rax
0x18000c829  mov     [rsp+2E0h+var_288], r8
0x18000c82e  mov     [rsp+2E0h+var_2A8], r8
0x18000c833  mov     [rsp+2E0h+var_298], r8
0x18000c838  mov     [rsp+2E0h+var_290], r8
0x18000c83d  test    r15, r15
0x18000c840  jz      loc_18000CAA5
0x18000c846  mov     edx, ebx
0x18000c848  mov     rax, r15
0x18000c84b  cmp     [rax], r8w
0x18000c84f  jz      short loc_18000C85A
0x18000c851  add     rax, 2
0x18000c855  sub     rdx, r12
0x18000c858  jnz     short loc_18000C84B
0x18000c85a  mov     rcx, rbx
0x18000c85d  mov     rax, rdx
0x18000c860  sub     rcx, rdx
0x18000c863  neg     rax
0x18000c866  sbb     rdi, rdi
0x18000c869  and     rdi, rcx
0x18000c86c  test    rdx, rdx
0x18000c86f  jz      loc_18000CAA5
0x18000c875  xor     edx, edx; Val
0x18000c877  lea     rcx, [rbp+1E0h+var_258]; void *
0x18000c87b  mov     r8d, 218h; Size
0x18000c881  call    memset_0
0x18000c886  mov     eax, dword ptr [rsp+2E0h+var_2B0]
0x18000c88a  mov     ecx, 7FFFFFFEh
0x18000c88f  mov     [rbp+1E0h+var_260], eax
0x18000c892  mov     rdx, r15
0x18000c895  lea     eax, ds:2[rdi*2]
0x18000c89c  xor     r9d, r9d
0x18000c89f  mov     [rbp+1E0h+var_25C], eax
0x18000c8a2  lea     rax, [rbp+1E0h+var_258]
0x18000c8a6  test    rcx, rcx
0x18000c8a9  jz      short loc_18000C8CD
0x18000c8ab  movzx   r8d, word ptr [rdx]
0x18000c8af  test    r8w, r8w
0x18000c8b3  jz      short loc_18000C8CD
0x18000c8b5  mov     [rax], r8w
0x18000c8b9  sub     rcx, r12
0x18000c8bc  mov     r8d, 2
0x18000c8c2  add     rax, r8
0x18000c8c5  add     rdx, r8
0x18000c8c8  sub     rbx, r12
0x18000c8cb  jnz     short loc_18000C8A6
0x18000c8cd  test    rbx, rbx
0x18000c8d0  lea     rcx, [rax-2]
0x18000c8d4  mov     rbx, [rsp+2E0h+SourceSid]
0x18000c8d9  lea     rdx, [rbp+1E0h+DestinationSid]; DestinationSid
0x18000c8e0  cmovnz  rcx, rax
0x18000c8e4  mov     r8, rbx; SourceSid
0x18000c8e7  mov     [rcx], r9w
0x18000c8eb  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000c8f0  call    cs:__imp_RtlCopySid
0x18000c8f6  mov     al, [rbp+1E0h+arg_28]
0x18000c8fc  lea     r9, [rsp+2E0h+var_288]
0x18000c901  xor     r8d, r8d
0x18000c904  mov     [rbp+1E0h+var_44], al
0x18000c90a  mov     edx, esi
0x18000c90c  lea     rcx, [rbp+1E0h+var_260]
0x18000c910  call    PsmpAllocateOrLookupApplicationEx
0x18000c915  mov     r15, [rsp+2E0h+var_288]
0x18000c91a  mov     edi, eax
0x18000c91c  test    eax, eax
0x18000c91e  jns     short loc_18000C97E
0x18000c920  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c927  mov     eax, 2
0x18000c92c  test    [rcx+1Ch], al
0x18000c92f  jnz     loc_18000CAAD
0x18000c935  test    r15, r15
0x18000c938  jz      short loc_18000C944
0x18000c93a  xor     edx, edx
0x18000c93c  mov     rcx, r15
0x18000c93f  call    PsmpDereferenceApplicationEx
0x18000c944  mov     rcx, [rsp+2E0h+var_290]
0x18000c949  test    rcx, rcx
0x18000c94c  jnz     loc_18000CB21
0x18000c952  mov     eax, edi
0x18000c954  mov     rcx, [rbp+1E0h+var_40]
0x18000c95b  xor     rcx, rsp; StackCookie
0x18000c95e  call    __security_check_cookie
0x18000c963  mov     rbx, [rsp+2E0h+arg_18]
0x18000c96b  add     rsp, 2B0h
0x18000c972  pop     r15
0x18000c974  pop     r14
0x18000c976  pop     r13
0x18000c978  pop     r12
0x18000c97a  pop     rdi
0x18000c97b  pop     rsi
0x18000c97c  pop     rbp
0x18000c97d  retn
0x18000c97e  mov     rbx, [rsp+2E0h+var_2A0]
0x18000c983  cmp     r13d, 4
0x18000c987  jnz     loc_18000CA6F
0x18000c98d  lea     r8, [rsp+2E0h+var_2A8]
0x18000c992  mov     rdx, rbx
0x18000c995  mov     rcx, r15
0x18000c998  call    PsmpFindOrCreateHostJobContext
0x18000c99d  mov     edi, eax
0x18000c99f  test    eax, eax
0x18000c9a1  js      loc_18000CADB
0x18000c9a7  mov     r14, [rsp+2E0h+var_2A8]
0x18000c9ac  lock bts dword ptr [r14+54h], 4
0x18000c9b3  or      esi, 8
0x18000c9b6  test    [rbp+1E0h+arg_30], 2
0x18000c9bd  jnz     short loc_18000C9E5
0x18000c9bf  mov     r8d, dword ptr [rsp+2E0h+var_2B0]
0x18000c9c4  mov     r9, rbx
0x18000c9c7  mov     rdx, [rsp+2E0h+SourceSid]
0x18000c9cc  mov     rcx, [rsp+2E0h+var_278]
0x18000c9d1  call    cs:__imp_PsmHamReferenceHostId
0x18000c9d7  mov     [rsp+2E0h+var_290], rax
0x18000c9dc  test    rax, rax
0x18000c9df  jz      loc_18000CB17
0x18000c9e5  lea     rbx, [r15+148h]
0x18000c9ec  mov     rcx, rbx
0x18000c9ef  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000c9f5  mov     r8, [rsp+2E0h+var_2A0]
0x18000c9fa  lea     rax, [rsp+2E0h+var_290]
0x18000c9ff  mov     qword ptr [rsp+2E0h+var_2B8], rax
0x18000ca04  mov     r9, r14
0x18000ca07  mov     edx, esi
0x18000ca09  mov     [rsp+2E0h+pSid], 0
0x18000ca12  mov     rcx, r15
0x18000ca15  call    PsmpCreateAndInitializeHostJob
0x18000ca1a  mov     rcx, rbx
0x18000ca1d  mov     edi, eax
0x18000ca1f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000ca25  test    edi, edi
0x18000ca27  js      short loc_18000CA57
0x18000ca29  cmp     r13d, 4
0x18000ca2d  jnz     short loc_18000CA94
0x18000ca2f  lea     r9, [rsp+2E0h+var_298]
0x18000ca34  mov     r8d, r12d
0x18000ca37  mov     rdx, r14
0x18000ca3a  mov     rcx, r15
0x18000ca3d  call    PsmpInternalWorkItemReferenceCreate
0x18000ca42  mov     edi, eax
0x18000ca44  test    eax, eax
0x18000ca46  jns     short loc_18000CA81
0x18000ca48  mov     rcx, [rsp+2E0h+var_298]
0x18000ca4d  test    rcx, rcx
0x18000ca50  jz      short loc_18000CA57
0x18000ca52  call    PsmpInternalWorkItemReferenceDestroy
0x18000ca57  test    r14, r14
0x18000ca5a  jz      loc_18000C935
0x18000ca60  xor     edx, edx
0x18000ca62  mov     rcx, r14
0x18000ca65  call    PsmpDereferenceHostContext
0x18000ca6a  jmp     loc_18000C935
0x18000ca6f  cmp     r13d, 8
0x18000ca73  jnz     loc_18000C9B6
0x18000ca79  or      esi, 4
0x18000ca7c  jmp     loc_18000C9B6
0x18000ca81  mov     rcx, [rsp+2E0h+var_270]
0x18000ca86  mov     rax, [rsp+2E0h+var_298]
0x18000ca8b  mov     [rcx], rax
0x18000ca8e  xor     ecx, ecx
0x18000ca90  xor     edi, edi
0x18000ca92  jmp     short loc_18000CA4D
0x18000ca94  xor     eax, eax
0x18000ca96  cmp     r13d, 8
0x18000ca9a  lea     ecx, [rax+2]
0x18000ca9d  cmovz   eax, ecx
0x18000caa0  mov     r12d, eax
0x18000caa3  jmp     short loc_18000CA2F
0x18000caa5  mov     rdi, r8
0x18000caa8  jmp     loc_18000C875
0x18000caad  cmp     [rcx+19h], al
0x18000cab0  jb      loc_18000C935
0x18000cab6  mov     eax, dword ptr [rsp+2E0h+var_2B0]
0x18000caba  mov     edx, 19h
0x18000cabf  mov     r9, [rsp+2E0h+var_278]
0x18000cac4  mov     rcx, [rcx+10h]; LoggerHandle
0x18000cac8  mov     dword ptr [rsp+2E0h+var_2B8], eax; char
0x18000cacc  mov     [rsp+2E0h+pSid], rbx; pSid
0x18000cad1  call    WPP_SF_S_sid_d
0x18000cad6  jmp     loc_18000C935
0x18000cadb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cae2  mov     eax, 2
0x18000cae7  test    [rcx+1Ch], al
0x18000caea  jz      short loc_18000CB0D
0x18000caec  cmp     [rcx+19h], al
0x18000caef  jb      short loc_18000CB0D
0x18000caf1  mov     r9, [r15+60h]
0x18000caf5  lea     edx, [rax+18h]
0x18000caf8  mov     rcx, [rcx+10h]
0x18000cafc  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x18000cb03  mov     [rsp+2E0h+pSid], rbx
0x18000cb08  call    WPP_SF_ii
0x18000cb0d  mov     r14, [rsp+2E0h+var_2A8]
0x18000cb12  jmp     loc_18000CA57
0x18000cb17  mov     edi, 0C0EC0006h
0x18000cb1c  jmp     loc_18000CA57
0x18000cb21  call    cs:__imp_PsmHamDereferenceHostId
0x18000cb27  jmp     loc_18000C952
```
