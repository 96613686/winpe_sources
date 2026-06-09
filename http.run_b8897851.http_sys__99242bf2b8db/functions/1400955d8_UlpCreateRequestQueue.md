# UlpCreateRequestQueue

- ea: `0x1400955d8`
- end: `0x14009592d`
- name: `UlpCreateRequestQueue`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a339c`

## callees

- `0x14000a350`
- `0x1400636dc`
- `0x1400953dc`
- `0x1400955d8`
- `0x140095934`
- `0x140095d9c`
- `0x140095f70`
- `0x14009622c`
- `0x1400cdfec`
- `0x1400cec34`
- `0x1400d03d4`
- `0x1400d72fc`
- `0x1401c5a0c`
- `0x1401c6088`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140095749`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x14017bda2`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140095749`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x14017bda2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14009577a`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14009577a`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140095725`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14017bd79`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140095725`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x14017bd79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400956d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140095755`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14017bdae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400956d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140095755`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14017bdae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400956c7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400956c7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140095672`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140095672`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009565a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140095712`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14017bd66`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009565a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140095712`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14017bd66`

## pseudocode

```c
__int64 __fastcall UlpCreateRequestQueue(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        HANDLE Handle,
        ULONG_PTR *a8)
{
  ULONG_PTR v8; // rsi
  const UNICODE_STRING *v9; // rdi
  __int64 *v12; // r14
  __int64 v13; // rsi
  int Consumer; // edi
  __int64 v16; // r13
  ULONG_PTR *v17; // rcx
  ULONG_PTR v18; // rdx
  int v19; // eax
  ULONG_PTR v20; // rdx
  int v21; // eax
  ULONG_PTR v22; // rbx
  ULONG_PTR v23; // rax
  ULONG_PTR v24; // r8
  void *v25; // rbx
  ULONG_PTR v26; // [rsp+68h] [rbp-18h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+70h] [rbp-10h] BYREF

  v8 = 0;
  v26 = 0;
  v9 = (const UNICODE_STRING *)a3;
  BugCheckParameter2[0] = 0;
  v12 = (__int64 *)(a3 + 8);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_qllSqqLqq((unsigned __int16)a2, HIWORD(a2), a3, a1, a2, SBYTE2(a2), *v12, a4, a5, a6, (char)Handle, (char)a8);
    v8 = v26;
  }
  *a8 = 0;
  if ( a6 - 1 <= 1 )
  {
    if ( *v12 )
    {
      Consumer = UlpValidateRequestQueueName(v9);
      if ( Consumer < 0 )
      {
LABEL_34:
        v8 = v26;
        goto LABEL_37;
      }
      v9 = (const UNICODE_STRING *)a3;
LABEL_6:
      KeEnterCriticalRegion();
      v13 = a1 + 4144;
      ExAcquirePushLockExclusiveEx(a1 + 4144, 0);
      if ( *v12 && UlpFindRequestQueue(a1, v9, 1) )
      {
        Consumer = -1073741771;
        goto LABEL_9;
      }
      Consumer = UlListenerObjectAccessCheck(a5, L"RequestQueue");
      if ( Consumer >= 0 )
      {
        Consumer = UlpAllocateRequestQueue(a1, a2, a3, a4, &v26);
        if ( Consumer >= 0 )
        {
          Consumer = UlpAllocateConsumer(a5, a6, BugCheckParameter2);
          if ( Consumer >= 0 )
          {
            v22 = v26;
            if ( *(_BYTE *)(v26 + 144) )
            {
              Consumer = UlCreateAutoServerSession(Handle);
              if ( Consumer < 0 )
                goto LABEL_9;
              v22 = v26;
            }
            KeEnterCriticalRegion();
            ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v22 + 280));
            UlpAttachConsumerToRequestQueue(v26, BugCheckParameter2[0]);
            ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v26 + 280));
            KeLeaveCriticalRegion();
            RtlInsertEntryHashTable(
              (PRTL_DYNAMIC_HASH_TABLE)(a1 + 4152),
              (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v26 + 176),
              1u,
              0);
            v16 = a1 + 4192;
            v17 = *(ULONG_PTR **)(v16 + 8);
            if ( *v17 != v16 )
              __fastfail(3u);
            v23 = v26 + 200;
            *(_QWORD *)(v26 + 200) = v16;
            *(_QWORD *)(v23 + 8) = v17;
            *v17 = v23;
            v24 = BugCheckParameter2[0];
            *(_QWORD *)(v16 + 8) = v23;
            *a8 = v24;
            if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
              WPP_SF_qZqL((_DWORD)v17, 75, v24, v26, v26 + 160, v24, a6);
          }
        }
      }
LABEL_9:
      ExReleasePushLockExclusiveEx(v13, 0);
      KeLeaveCriticalRegion();
      if ( Consumer >= 0 )
        goto LABEL_10;
      goto LABEL_34;
    }
    if ( a6 == 1 )
      goto LABEL_6;
  }
  Consumer = -1073741811;
LABEL_37:
  if ( v8 )
  {
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v8 + 280));
    v25 = *(void **)(v26 + 136);
    *(_QWORD *)(v26 + 136) = 0;
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v26 + 280));
    KeLeaveCriticalRegion();
    if ( v25 )
      UlDeleteAutoServerSession(v25);
    v18 = v26;
    v19 = _InterlockedDecrement((volatile signed __int32 *)v26);
    if ( UxDebugCheckRefcount && v19 <= -1 )
      UlBugCheckEx(3u, v18, 1u, v19);
    if ( !v19 )
      UlFreeRequestQueue((PVOID)v26);
  }
  v20 = BugCheckParameter2[0];
  if ( BugCheckParameter2[0] )
  {
    v21 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2[0]);
    if ( UxDebugCheckRefcount && v21 <= -1 )
      UlBugCheckEx(3u, v20, 1u, v21);
    UlpFreeConsumer((PVOID)BugCheckParameter2[0]);
  }
LABEL_10:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 76, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, *a8, Consumer);
  return (unsigned int)Consumer;
}

```

## disassembly

```asm
0x1400955d8  mov     [rsp-38h+arg_0], rbx
0x1400955dd  mov     [rsp-38h+arg_18], r9
0x1400955e2  mov     [rsp-38h+arg_10], r8
0x1400955e7  push    rbp
0x1400955e8  push    rsi
0x1400955e9  push    rdi
0x1400955ea  push    r12
0x1400955ec  push    r13
0x1400955ee  push    r14
0x1400955f0  push    r15
0x1400955f2  mov     rbp, rsp
0x1400955f5  sub     rsp, 80h
0x1400955fc  xor     esi, esi
0x1400955fe  mov     dword ptr [rbp+Signature], 1
0x140095605  mov     [rbp+var_18], rsi
0x140095609  mov     rdi, r8
0x14009560c  mov     [rbp+BugCheckParameter2], rsi
0x140095610  mov     ebx, edx
0x140095612  mov     r13, rcx
0x140095615  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14009561c  lea     r14, [r8+8]
0x140095620  mov     r15d, [rbp+arg_28]
0x140095624  mov     r12, [rbp+arg_20]
0x140095628  jnz     loc_140095821
0x14009562e  mov     rax, [rbp+arg_38]
0x140095632  mov     qword ptr [rax], 0
0x140095639  lea     eax, [r15-1]
0x14009563d  cmp     eax, 1
0x140095640  ja      loc_140095869
0x140095646  cmp     qword ptr [r14], 0
0x14009564a  jnz     loc_140095873
0x140095650  cmp     r15d, 1
0x140095654  jnz     loc_140095869
0x14009565a  call    cs:__imp_KeEnterCriticalRegion
0x140095661  nop     dword ptr [rax+rax+00h]
0x140095666  lea     rsi, [r13+1030h]
0x14009566d  xor     edx, edx
0x14009566f  mov     rcx, rsi
0x140095672  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140095679  nop     dword ptr [rax+rax+00h]
0x14009567e  cmp     qword ptr [r14], 0
0x140095682  jnz     loc_14009588E
0x140095688  lea     rdx, aRequestqueue; "RequestQueue"
0x14009568f  mov     rcx, r12
0x140095692  call    UlListenerObjectAccessCheck
0x140095697  mov     edi, eax
0x140095699  test    eax, eax
0x14009569b  js      short loc_1400956C2
0x14009569d  mov     r9, [rbp+arg_18]
0x1400956a1  lea     rax, [rbp+var_18]
0x1400956a5  mov     r8, [rbp+arg_10]
0x1400956a9  mov     edx, ebx
0x1400956ab  mov     rcx, r13
0x1400956ae  mov     [rsp+80h+var_60], rax
0x1400956b3  call    UlpAllocateRequestQueue
0x1400956b8  mov     edi, eax
0x1400956ba  test    eax, eax
0x1400956bc  jns     loc_1400958B0
0x1400956c2  xor     edx, edx
0x1400956c4  mov     rcx, rsi
0x1400956c7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400956ce  nop     dword ptr [rax+rax+00h]
0x1400956d3  call    cs:__imp_KeLeaveCriticalRegion
0x1400956da  nop     dword ptr [rax+rax+00h]
0x1400956df  test    edi, edi
0x1400956e1  js      loc_1400958FE
0x1400956e7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400956ee  jnz     loc_140095907
0x1400956f4  mov     rbx, [rsp+80h+arg_0]
0x1400956fc  mov     eax, edi
0x1400956fe  add     rsp, 80h
0x140095705  pop     r15
0x140095707  pop     r14
0x140095709  pop     r13
0x14009570b  pop     r12
0x14009570d  pop     rdi
0x14009570e  pop     rsi
0x14009570f  pop     rbp
0x140095710  retn
0x140095712  call    cs:__imp_KeEnterCriticalRegion
0x140095719  nop     dword ptr [rax+rax+00h]
0x14009571e  mov     rcx, [rbx+118h]
0x140095725  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x14009572c  nop     dword ptr [rax+rax+00h]
0x140095731  mov     rdx, [rbp+BugCheckParameter2]; ULONG_PTR
0x140095735  mov     rcx, [rbp+var_18]; BugCheckParameter2
0x140095739  call    UlpAttachConsumerToRequestQueue
0x14009573e  mov     rcx, [rbp+var_18]
0x140095742  mov     rcx, [rcx+118h]
0x140095749  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x140095750  nop     dword ptr [rax+rax+00h]
0x140095755  call    cs:__imp_KeLeaveCriticalRegion
0x14009575c  nop     dword ptr [rax+rax+00h]
0x140095761  mov     rdx, [rbp+var_18]
0x140095765  lea     rcx, [r13+1038h]; HashTable
0x14009576c  mov     r8d, dword ptr [rbp+Signature]; Signature
0x140095770  add     rdx, 0B0h; Entry
0x140095777  xor     r9d, r9d; Context
0x14009577a  call    cs:__imp_RtlInsertEntryHashTable
0x140095781  nop     dword ptr [rax+rax+00h]
0x140095786  add     r13, 1060h
0x14009578d  mov     rcx, [r13+8]
0x140095791  cmp     [rcx], r13
0x140095794  jz      loc_14017BCFC
0x14009579a  mov     ecx, 3
0x14009579f  int     29h; Win8: RtlFailFast(ecx)
0x1400957a1  mov     rdx, [rbp+var_18]; BugCheckParameter2
0x1400957a5  mov     eax, r15d
0x1400957a8  lock xadd [rdx], eax
0x1400957ac  add     eax, r15d
0x1400957af  cmp     cs:UxDebugCheckRefcount, r14b
0x1400957b6  jnz     short loc_1400957FC
0x1400957b8  test    eax, eax
0x1400957ba  jnz     short loc_1400957C5
0x1400957bc  mov     rcx, [rbp+var_18]; P
0x1400957c0  call    UlFreeRequestQueue
0x1400957c5  mov     rdx, [rbp+BugCheckParameter2]; BugCheckParameter2
0x1400957c9  test    rdx, rdx
0x1400957cc  jz      loc_1400956E7
0x1400957d2  mov     eax, r15d
0x1400957d5  lock xadd [rdx], eax
0x1400957d9  add     eax, r15d
0x1400957dc  cmp     cs:UxDebugCheckRefcount, r14b
0x1400957e3  jz      short loc_140095813
0x1400957e5  cmp     eax, r15d
0x1400957e8  jg      short loc_140095813
0x1400957ea  mov     ecx, 3; BugCheckParameter1
0x1400957ef  movsxd  r9, eax; BugCheckParameter4
0x1400957f2  lea     r8d, [rcx-2]; BugCheckParameter3
0x1400957f6  call    UlBugCheckEx
0x1400957fc  cmp     eax, r15d
0x1400957ff  jg      short loc_1400957B8
0x140095801  mov     ecx, 3; BugCheckParameter1
0x140095806  movsxd  r9, eax; BugCheckParameter4
0x140095809  lea     r8d, [rcx-2]; BugCheckParameter3
0x14009580d  call    UlBugCheckEx
0x140095813  mov     rcx, [rbp+BugCheckParameter2]; P
0x140095817  call    UlpFreeConsumer
0x14009581c  jmp     loc_1400956E7
0x140095821  mov     rax, [rbp+arg_38]
0x140095825  mov     [rsp+80h+var_28], rax
0x14009582a  mov     rax, [rbp+Handle]
0x14009582e  mov     [rsp+80h+var_30], rax
0x140095833  mov     rax, [r14]
0x140095836  mov     [rsp+80h+var_38], r15d
0x14009583b  mov     [rsp+80h+var_40], r12
0x140095840  mov     [rsp+80h+var_48], r9
0x140095845  mov     r9, r13
0x140095848  mov     [rsp+80h+var_50], rax
0x14009584d  shr     edx, 10h
0x140095850  movzx   ecx, bx
0x140095853  mov     [rsp+80h+var_58], edx
0x140095857  mov     dword ptr [rsp+80h+var_60], ecx
0x14009585b  call    WPP_SF_qllSqqLqq
0x140095860  mov     rsi, [rbp+var_18]
0x140095864  jmp     loc_14009562E
0x140095869  mov     edi, 0C000000Dh
0x14009586e  jmp     loc_14017BD56
0x140095873  lea     rdx, [rbp+Signature]
0x140095877  mov     rcx, rdi; String
0x14009587a  call    UlpValidateRequestQueueName
0x14009587f  mov     edi, eax
0x140095881  test    eax, eax
0x140095883  js      short loc_1400958FE
0x140095885  mov     rdi, [rbp+arg_10]
0x140095889  jmp     loc_14009565A
0x14009588e  mov     r8d, dword ptr [rbp+Signature]
0x140095892  mov     rdx, rdi
0x140095895  mov     rcx, r13
0x140095898  call    UlpFindRequestQueue
0x14009589d  test    rax, rax
0x1400958a0  jz      loc_140095688
0x1400958a6  mov     edi, 0C0000035h
0x1400958ab  jmp     loc_1400956C2
0x1400958b0  lea     r8, [rbp+BugCheckParameter2]
0x1400958b4  mov     edx, r15d
0x1400958b7  mov     rcx, r12
0x1400958ba  call    UlpAllocateConsumer
0x1400958bf  mov     edi, eax
0x1400958c1  test    eax, eax
0x1400958c3  js      loc_1400956C2
0x1400958c9  mov     rbx, [rbp+var_18]
0x1400958cd  cmp     byte ptr [rbx+90h], 0
0x1400958d4  jz      loc_140095712
0x1400958da  mov     dl, [r12+40h]
0x1400958df  mov     r8, rbx
0x1400958e2  mov     rcx, [rbp+Handle]; Handle
0x1400958e6  call    UlCreateAutoServerSession
0x1400958eb  mov     edi, eax
0x1400958ed  test    eax, eax
0x1400958ef  js      loc_1400956C2
0x1400958f5  mov     rbx, [rbp+var_18]
0x1400958f9  jmp     loc_140095712
0x1400958fe  mov     rsi, [rbp+var_18]
0x140095902  jmp     loc_14017BD56
0x140095907  mov     rax, [rbp+arg_38]
0x14009590b  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140095912  mov     edx, 4Ch ; 'L'
0x140095917  mov     dword ptr [rsp+80h+var_60], edi
0x14009591b  mov     ecx, 408h
0x140095920  mov     r9, [rax]
0x140095923  call    WPP_SF_qD
0x140095928  jmp     loc_1400956F4
0x14017bcfc  mov     rax, [rbp+var_18]
0x14017bd00  add     rax, 0C8h
0x14017bd06  mov     [rax], r13
0x14017bd09  mov     [rax+8], rcx
0x14017bd0d  mov     [rcx], rax
0x14017bd10  mov     r8, [rbp+BugCheckParameter2]
0x14017bd14  mov     [r13+8], rax
0x14017bd18  mov     rax, [rbp+arg_38]
0x14017bd1c  mov     [rax], r8
0x14017bd1f  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x14017bd26  jz      loc_1400956C2
0x14017bd2c  mov     r9, [rbp+var_18]
0x14017bd30  mov     edx, 4Bh ; 'K'
0x14017bd35  mov     dword ptr [rsp+80h+var_50], r15d
0x14017bd3a  mov     qword ptr [rsp+80h+var_58], r8
0x14017bd3f  lea     rax, [r9+0A0h]
0x14017bd46  mov     [rsp+80h+var_60], rax
0x14017bd4b  call    WPP_SF_qZqL
0x14017bd50  nop
0x14017bd51  jmp     loc_1400956C2
0x14017bd56  or      r15d, 0FFFFFFFFh
0x14017bd5a  xor     r14d, r14d
0x14017bd5d  test    rsi, rsi
0x14017bd60  jz      loc_1400957C5
0x14017bd66  call    cs:__imp_KeEnterCriticalRegion
0x14017bd6d  nop     dword ptr [rax+rax+00h]
0x14017bd72  mov     rcx, [rsi+118h]
0x14017bd79  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x14017bd80  nop     dword ptr [rax+rax+00h]
0x14017bd85  mov     rax, [rbp+var_18]
0x14017bd89  mov     rbx, [rax+88h]
0x14017bd90  mov     [rax+88h], r14
0x14017bd97  mov     rcx, [rbp+var_18]
0x14017bd9b  mov     rcx, [rcx+118h]
0x14017bda2  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x14017bda9  nop     dword ptr [rax+rax+00h]
0x14017bdae  call    cs:__imp_KeLeaveCriticalRegion
0x14017bdb5  nop     dword ptr [rax+rax+00h]
0x14017bdba  test    rbx, rbx
0x14017bdbd  jz      loc_1400957A1
0x14017bdc3  mov     rcx, rbx
0x14017bdc6  call    UlDeleteAutoServerSession
0x14017bdcb  nop
0x14017bdcc  jmp     loc_1400957A1
```
