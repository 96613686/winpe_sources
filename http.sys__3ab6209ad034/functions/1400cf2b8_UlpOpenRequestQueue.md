# UlpOpenRequestQueue

- ea: `0x1400cf2b8`
- end: `0x1400cf7ae`
- name: `UlpOpenRequestQueue`
- size: `1270`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, struct _ACCESS_STATE *, ACCESS_MASK DesiredAccess, __int64, unsigned int, int, __int64, char, ULONG_PTR *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a337c`

## callees

- `0x14000a350`
- `0x1400422b8`
- `0x1400953bc`
- `0x140095f50`
- `0x1400a03d0`
- `0x1400cdf0c`
- `0x1400ceb54`
- `0x1400cf2b8`
- `0x1400d02f4`
- `0x140167c40`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c5a0c`
- `0x1401c5e80`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cf62a`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cf691`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cf62a`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cf691`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cf4da`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cf4da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf636`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf69d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf6c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf636`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf69d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf6c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400cf6b9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400cf6b9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400cf5f2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400cf5f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf4c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf5dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf4c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf5dd`

## pseudocode

```c
__int64 __fastcall UlpOpenRequestQueue(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        struct _ACCESS_STATE *a4,
        ACCESS_MASK DesiredAccess,
        __int64 a6,
        unsigned int a7,
        int a8,
        __int64 a9,
        char a10,
        ULONG_PTR *a11)
{
  __int16 v12; // bx
  __int64 v13; // r13
  int v15; // eax
  int v16; // edi
  __int64 v17; // rdx
  int v18; // edx
  ULONG_PTR RequestQueue; // rsi
  bool v20; // zf
  int v21; // eax
  int v22; // r8d
  ULONG_PTR v23; // rax
  ULONG_PTR v24; // rdx
  int v25; // eax
  bool v27; // [rsp+68h] [rbp-49h]
  ULONG_PTR BugCheckParameter2; // [rsp+70h] [rbp-41h] BYREF
  _QWORD v29[8]; // [rsp+78h] [rbp-39h] BYREF
  __int16 v30; // [rsp+102h] [rbp+51h]
  char v32; // [rsp+128h] [rbp+77h]

  v30 = HIWORD(a2);
  v12 = a2;
  BugCheckParameter2 = 0;
  v13 = a1;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qllSqLqLq(
      (unsigned __int16)a2,
      HIWORD(a2),
      (_DWORD)a11,
      a1,
      a2,
      SBYTE2(a2),
      *(_QWORD *)(a3 + 8),
      (char)a4,
      DesiredAccess,
      a6,
      a7,
      (char)a11);
  *a11 = 0;
  if ( a7 > 8 || (v15 = 274, !_bittest(&v15, a7)) )
  {
    v16 = -1073741637;
    goto LABEL_52;
  }
  if ( (a10 & 0x10) != 0 )
  {
    if ( (a10 & 2) != 0 )
    {
      v16 = -1073741811;
      if ( (BYTE1(xmmword_1401A2C90) & 1) == 0 )
        goto LABEL_52;
      v17 = 67;
    }
    else if ( (a10 & 4) != 0 )
    {
      v16 = -1073741811;
      if ( (BYTE1(xmmword_1401A2C90) & 1) == 0 )
        goto LABEL_52;
      v17 = 68;
    }
    else if ( (a10 & 8) != 0 )
    {
      v16 = -1073741811;
      if ( (BYTE1(xmmword_1401A2C90) & 1) == 0 )
        goto LABEL_52;
      v17 = 69;
    }
    else
    {
      v32 = 1;
      if ( DesiredAccess == 917504 )
        goto LABEL_7;
      v16 = -1073741811;
      if ( (BYTE1(xmmword_1401A2C90) & 1) == 0 )
        goto LABEL_52;
      v17 = 70;
    }
    WPP_SF_(520, v17, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
    goto LABEL_52;
  }
  v32 = 0;
LABEL_7:
  if ( !*(_QWORD *)(a3 + 8) )
  {
    v16 = -1073741811;
    goto LABEL_52;
  }
  v16 = UlpValidateRequestQueueName((PCUNICODE_STRING)a3);
  if ( v16 >= 0 )
  {
    if ( a7 == 4 && (DesiredAccess & 0x20) == 0 )
    {
      v16 = -1073741790;
      goto LABEL_52;
    }
    v16 = UlpAllocateConsumer(a6, a7, &BugCheckParameter2);
    if ( v16 >= 0 )
    {
      if ( a8 )
      {
        memset(v29, 0, sizeof(v29));
        LODWORD(v29[1]) = 0;
        LOBYTE(v18) = 1;
        v29[2] = a9;
        v29[0] = a3;
        LODWORD(v29[3]) = a8;
        UxPodEnumerateEx((unsigned int)UlpFindRequestQueueWithExternalIdAndPod, v18, 0, (unsigned int)v29, 0);
        RequestQueue = v29[4];
        if ( !v29[4] )
        {
          v16 = -1073741772;
          goto LABEL_52;
        }
        v20 = v13 == v29[5];
        v13 = v29[5];
        v27 = !v20;
        if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
          WPP_SF_q(1046, 71, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v29[5]);
      }
      else
      {
        v27 = 0;
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v13 + 4144, 0);
        RequestQueue = UlpFindRequestQueue(v13, a3, 0);
        if ( !RequestQueue )
        {
          v16 = -1073741772;
LABEL_44:
          ExReleasePushLockExclusiveEx(v13 + 4144, 0);
          KeLeaveCriticalRegion();
          goto LABEL_52;
        }
      }
      if ( *(_WORD *)(RequestQueue + 276) == v12 && *(_WORD *)(RequestQueue + 278) == v30 )
      {
        KeEnterCriticalRegion();
        ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(RequestQueue + 280));
        v16 = UlAccessCheck(
                *(PSECURITY_DESCRIPTOR *)(RequestQueue + 152),
                a4,
                DesiredAccess,
                *(_BYTE *)(a6 + 64),
                *(_QWORD *)(a3 + 8),
                0);
        if ( (v16 >= 0
           || v32
           && (v16 = UlAccessCheck(UxAdminSDBytes, a4, 0x20000u, *(_BYTE *)(a6 + 64), 0, 0), v16 >= 0)
           && (v16 = UlAccessCheck(
                       *(PSECURITY_DESCRIPTOR *)(RequestQueue + 152),
                       a4,
                       DesiredAccess,
                       *(_BYTE *)(a6 + 64),
                       *(_QWORD *)(a3 + 8),
                       1),
               v16 >= 0))
          && (v16 = UlpAttachConsumerToRequestQueue(RequestQueue, BugCheckParameter2), v16 >= 0) )
        {
          if ( v27 )
          {
            *(_BYTE *)(BugCheckParameter2 + 128) = 1;
            v21 = _InterlockedIncrement((volatile signed __int32 *)(v13 + 4208));
            if ( UxDebugCheckRefcount )
            {
              if ( v21 <= -1 )
                UlBugCheckEx(3u, v13 + 4208, 0xAu, v21);
            }
          }
          ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(RequestQueue + 280));
          KeLeaveCriticalRegion();
          if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
            WPP_SF_qZqL(RequestQueue + 160, 72, v22, RequestQueue, RequestQueue + 160, BugCheckParameter2, a7);
          v23 = BugCheckParameter2;
          BugCheckParameter2 = 0;
          *a11 = v23;
        }
        else
        {
          ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(RequestQueue + 280));
          KeLeaveCriticalRegion();
        }
      }
      else
      {
        v16 = -1073741637;
      }
      goto LABEL_44;
    }
  }
LABEL_52:
  v24 = BugCheckParameter2;
  if ( BugCheckParameter2 )
  {
    v25 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2);
    if ( UxDebugCheckRefcount && v25 <= -1 )
      UlBugCheckEx(3u, v24, 1u, v25);
    UlpFreeConsumer((PVOID)BugCheckParameter2);
    BugCheckParameter2 = 0;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 73, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, *a11, v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400cf2b8  mov     rax, rsp
0x1400cf2bb  mov     [rax+8], rbx
0x1400cf2bf  mov     [rax+20h], r9
0x1400cf2c3  mov     [rax+10h], edx
0x1400cf2c6  push    rbp
0x1400cf2c7  push    rsi
0x1400cf2c8  push    rdi
0x1400cf2c9  push    r12
0x1400cf2cb  push    r13
0x1400cf2cd  push    r14
0x1400cf2cf  push    r15
0x1400cf2d1  lea     rbp, [rax-3Fh]
0x1400cf2d5  sub     rsp, 0B0h
0x1400cf2dc  xor     edi, edi
0x1400cf2de  mov     r15, r8
0x1400cf2e1  mov     [rbp+37h+var_7C], edi
0x1400cf2e4  mov     ebx, edx
0x1400cf2e6  mov     [rbp+37h+BugCheckParameter2], rdi
0x1400cf2ea  mov     r13, rcx
0x1400cf2ed  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cf2f4  mov     r14d, [rbp+37h+arg_30]
0x1400cf2f8  mov     r12d, [rbp+37h+DesiredAccess]
0x1400cf2fc  mov     rsi, [rbp+37h+arg_28]
0x1400cf300  jz      short loc_1400CF341
0x1400cf302  mov     r8, [rbp+37h+arg_50]
0x1400cf309  mov     rax, [r15+8]
0x1400cf30d  mov     [rsp+58h], r8
0x1400cf312  mov     dword ptr [rsp+0E0h+var_90], r14d
0x1400cf317  mov     qword ptr [rsp+0E0h+var_98], rsi
0x1400cf31c  mov     dword ptr [rsp+0E0h+var_A0], r12d
0x1400cf321  mov     qword ptr [rsp+0E0h+var_A8], r9
0x1400cf326  mov     r9, r13
0x1400cf329  mov     [rsp+0E0h+var_B0], rax
0x1400cf32e  shr     edx, 10h
0x1400cf331  movzx   ecx, bx
0x1400cf334  mov     dword ptr [rsp+0E0h+var_B8], edx
0x1400cf338  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x1400cf33c  call    WPP_SF_qllSqLqLq
0x1400cf341  mov     rax, [rbp+37h+arg_50]
0x1400cf348  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf34f  mov     [rax], rdi
0x1400cf352  cmp     r14d, 8
0x1400cf356  ja      loc_1400CF71B
0x1400cf35c  mov     eax, 112h
0x1400cf361  bt      eax, r14d
0x1400cf365  jnb     loc_1400CF71B
0x1400cf36b  mov     eax, dword ptr [rbp+37h+arg_48]
0x1400cf371  test    al, 10h
0x1400cf373  jnz     short loc_1400CF389
0x1400cf375  mov     byte ptr [rbp+37h+arg_30], dil
0x1400cf379  cmp     [r15+8], rdi
0x1400cf37d  jnz     short loc_1400CF3D4
0x1400cf37f  mov     edi, 0C000000Dh
0x1400cf384  jmp     loc_1400CF720
0x1400cf389  test    al, 2
0x1400cf38b  jnz     loc_1400CF703
0x1400cf391  test    al, 4
0x1400cf393  jnz     loc_1400CF6EB
0x1400cf399  test    al, 8
0x1400cf39b  jnz     loc_1400CF6D3
0x1400cf3a1  mov     byte ptr [rbp+37h+arg_30], 1
0x1400cf3a5  cmp     r12d, 0E0000h
0x1400cf3ac  jz      short loc_1400CF379
0x1400cf3ae  mov     edi, 0C000000Dh
0x1400cf3b3  test    byte ptr cs:xmmword_1401A2C90+1, 1
0x1400cf3ba  jz      loc_1400CF720
0x1400cf3c0  mov     edx, 46h ; 'F'
0x1400cf3c5  mov     ecx, 208h
0x1400cf3ca  call    WPP_SF_
0x1400cf3cf  jmp     loc_1400CF720
0x1400cf3d4  lea     rdx, [rbp+37h+var_7C]
0x1400cf3d8  mov     rcx, r15; String
0x1400cf3db  call    UlpValidateRequestQueueName
0x1400cf3e0  mov     edi, eax
0x1400cf3e2  test    eax, eax
0x1400cf3e4  js      loc_1400CF720
0x1400cf3ea  cmp     r14d, 4
0x1400cf3ee  jnz     short loc_1400CF400
0x1400cf3f0  test    r12b, 20h
0x1400cf3f4  jnz     short loc_1400CF400
0x1400cf3f6  mov     edi, 0C0000022h
0x1400cf3fb  jmp     loc_1400CF720
0x1400cf400  lea     r8, [rbp+37h+BugCheckParameter2]
0x1400cf404  mov     edx, r14d
0x1400cf407  mov     rcx, rsi
0x1400cf40a  call    UlpAllocateConsumer
0x1400cf40f  mov     edi, eax
0x1400cf411  test    eax, eax
0x1400cf413  js      loc_1400CF720
0x1400cf419  mov     edi, [rbp+37h+arg_38]
0x1400cf41c  test    edi, edi
0x1400cf41e  jz      loc_1400CF5D9
0x1400cf424  xor     edx, edx; Val
0x1400cf426  lea     rcx, [rbp+37h+var_70]; void *
0x1400cf42a  lea     r8d, [rdx+40h]; Size
0x1400cf42e  call    memset
0x1400cf433  mov     eax, [rbp+37h+var_7C]
0x1400cf436  lea     r9, [rbp+37h+var_70]
0x1400cf43a  mov     [rbp+37h+var_68], eax
0x1400cf43d  lea     rcx, UlpFindRequestQueueWithExternalIdAndPod
0x1400cf444  mov     rax, [rbp+37h+arg_40]
0x1400cf44b  xor     r8d, r8d
0x1400cf44e  mov     dl, 1
0x1400cf450  mov     [rbp+37h+var_60], rax
0x1400cf454  mov     [rbp+37h+var_70], r15
0x1400cf458  mov     [rbp+37h+var_58], edi
0x1400cf45b  mov     [rsp+0E0h+var_C0], 0
0x1400cf464  call    UxPodEnumerateEx
0x1400cf469  mov     rsi, [rbp+37h+var_50]
0x1400cf46d  test    rsi, rsi
0x1400cf470  jnz     short loc_1400CF47C
0x1400cf472  mov     edi, 0C0000034h
0x1400cf477  jmp     loc_1400CF720
0x1400cf47c  mov     r9, [rbp+37h+var_48]
0x1400cf480  cmp     r13, r9
0x1400cf483  mov     r13, r9
0x1400cf486  setnz   [rbp+37h+var_80]
0x1400cf48a  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400cf491  jz      short loc_1400CF4A9
0x1400cf493  mov     edx, 47h ; 'G'
0x1400cf498  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf49f  mov     ecx, 416h
0x1400cf4a4  call    WPP_SF_q
0x1400cf4a9  cmp     [rsi+114h], bx
0x1400cf4b0  jnz     loc_1400CF6AB
0x1400cf4b6  movzx   eax, [rbp+37h+arg_A]
0x1400cf4ba  cmp     [rsi+116h], ax
0x1400cf4c1  jnz     loc_1400CF6AB
0x1400cf4c7  call    cs:__imp_KeEnterCriticalRegion
0x1400cf4ce  nop     dword ptr [rax+rax+00h]
0x1400cf4d3  mov     rcx, [rsi+118h]
0x1400cf4da  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400cf4e1  nop     dword ptr [rax+rax+00h]
0x1400cf4e6  mov     rax, [r15+8]
0x1400cf4ea  mov     r8d, r12d; DesiredAccess
0x1400cf4ed  mov     rbx, [rbp+37h+arg_28]
0x1400cf4f1  mov     rdx, [rbp+37h+AccessState]; AccessState
0x1400cf4f5  mov     rcx, [rsi+98h]; SecurityDescriptor
0x1400cf4fc  mov     [rsp+0E0h+var_B8], 0; char
0x1400cf501  mov     r9b, [rbx+40h]; AccessMode
0x1400cf505  mov     [rsp+0E0h+var_C0], rax; __int64
0x1400cf50a  call    UlAccessCheck
0x1400cf50f  mov     edi, eax
0x1400cf511  xor     eax, eax
0x1400cf513  test    edi, edi
0x1400cf515  jns     short loc_1400CF57C
0x1400cf517  cmp     byte ptr [rbp+37h+arg_30], al
0x1400cf51a  jz      loc_1400CF68A
0x1400cf520  mov     r9b, [rbx+40h]; AccessMode
0x1400cf524  lea     rcx, UxAdminSDBytes; SecurityDescriptor
0x1400cf52b  mov     rdx, [rbp+37h+AccessState]; AccessState
0x1400cf52f  mov     r8d, 20000h; DesiredAccess
0x1400cf535  mov     [rsp+0E0h+var_B8], al; char
0x1400cf539  mov     [rsp+0E0h+var_C0], rax; __int64
0x1400cf53e  call    UlAccessCheck
0x1400cf543  mov     edi, eax
0x1400cf545  test    eax, eax
0x1400cf547  js      loc_1400CF68A
0x1400cf54d  mov     rax, [r15+8]
0x1400cf551  mov     r8d, r12d; DesiredAccess
0x1400cf554  mov     r9b, [rbx+40h]; AccessMode
0x1400cf558  mov     rdx, [rbp+37h+AccessState]; AccessState
0x1400cf55c  mov     rcx, [rsi+98h]; SecurityDescriptor
0x1400cf563  mov     [rsp+0E0h+var_B8], 1; char
0x1400cf568  mov     [rsp+0E0h+var_C0], rax; __int64
0x1400cf56d  call    UlAccessCheck
0x1400cf572  mov     edi, eax
0x1400cf574  test    eax, eax
0x1400cf576  js      loc_1400CF68A
0x1400cf57c  mov     rdx, [rbp+37h+BugCheckParameter2]; ULONG_PTR
0x1400cf580  mov     rcx, rsi; BugCheckParameter2
0x1400cf583  call    UlpAttachConsumerToRequestQueue
0x1400cf588  mov     edi, eax
0x1400cf58a  test    eax, eax
0x1400cf58c  js      loc_1400CF68A
0x1400cf592  cmp     [rbp+37h+var_80], 0
0x1400cf596  jz      loc_1400CF623
0x1400cf59c  mov     rax, [rbp+37h+BugCheckParameter2]
0x1400cf5a0  lea     rdx, [r13+1070h]; BugCheckParameter2
0x1400cf5a7  mov     byte ptr [rax+80h], 1
0x1400cf5ae  mov     eax, 1
0x1400cf5b3  lock xadd [rdx], eax
0x1400cf5b7  inc     eax
0x1400cf5b9  cmp     cs:UxDebugCheckRefcount, 0
0x1400cf5c0  jz      short loc_1400CF623
0x1400cf5c2  cmp     eax, 0FFFFFFFFh
0x1400cf5c5  jg      short loc_1400CF623
0x1400cf5c7  mov     ecx, 3; BugCheckParameter1
0x1400cf5cc  movsxd  r9, eax; BugCheckParameter4
0x1400cf5cf  lea     r8d, [rcx+7]; BugCheckParameter3
0x1400cf5d3  call    UlBugCheckEx
0x1400cf5d9  mov     [rbp+37h+var_80], 0
0x1400cf5dd  call    cs:__imp_KeEnterCriticalRegion
0x1400cf5e4  nop     dword ptr [rax+rax+00h]
0x1400cf5e9  lea     rcx, [r13+1030h]
0x1400cf5f0  xor     edx, edx
0x1400cf5f2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400cf5f9  nop     dword ptr [rax+rax+00h]
0x1400cf5fe  mov     r8d, [rbp+37h+var_7C]
0x1400cf602  mov     rdx, r15
0x1400cf605  mov     rcx, r13
0x1400cf608  call    UlpFindRequestQueue
0x1400cf60d  mov     rsi, rax
0x1400cf610  test    rax, rax
0x1400cf613  jnz     loc_1400CF4A9
0x1400cf619  mov     edi, 0C0000034h
0x1400cf61e  jmp     loc_1400CF6B0
0x1400cf623  mov     rcx, [rsi+118h]
0x1400cf62a  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cf631  nop     dword ptr [rax+rax+00h]
0x1400cf636  call    cs:__imp_KeLeaveCriticalRegion
0x1400cf63d  nop     dword ptr [rax+rax+00h]
0x1400cf642  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400cf649  jz      short loc_1400CF672
0x1400cf64b  mov     rax, [rbp+37h+BugCheckParameter2]
0x1400cf64f  lea     rcx, [rsi+0A0h]
0x1400cf656  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x1400cf65b  mov     edx, 48h ; 'H'
0x1400cf660  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400cf665  mov     r9, rsi
0x1400cf668  mov     [rsp+0E0h+var_C0], rcx
0x1400cf66d  call    WPP_SF_qZqL
0x1400cf672  mov     rax, [rbp+37h+BugCheckParameter2]
0x1400cf676  mov     r8, [rbp+37h+arg_50]
0x1400cf67d  mov     [rbp+37h+BugCheckParameter2], 0
0x1400cf685  mov     [r8], rax
0x1400cf688  jmp     short loc_1400CF6B0
0x1400cf68a  mov     rcx, [rsi+118h]
0x1400cf691  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cf698  nop     dword ptr [rax+rax+00h]
0x1400cf69d  call    cs:__imp_KeLeaveCriticalRegion
0x1400cf6a4  nop     dword ptr [rax+rax+00h]
0x1400cf6a9  jmp     short loc_1400CF6B0
0x1400cf6ab  mov     edi, 0C00000BBh
0x1400cf6b0  lea     rcx, [r13+1030h]
0x1400cf6b7  xor     edx, edx
0x1400cf6b9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400cf6c0  nop     dword ptr [rax+rax+00h]
0x1400cf6c5  call    cs:__imp_KeLeaveCriticalRegion
0x1400cf6cc  nop     dword ptr [rax+rax+00h]
0x1400cf6d1  jmp     short loc_1400CF720
0x1400cf6d3  mov     edi, 0C000000Dh
0x1400cf6d8  test    byte ptr cs:xmmword_1401A2C90+1, 1
0x1400cf6df  jz      short loc_1400CF720
0x1400cf6e1  mov     edx, 45h ; 'E'
0x1400cf6e6  jmp     loc_1400CF3C5
0x1400cf6eb  mov     edi, 0C000000Dh
0x1400cf6f0  test    byte ptr cs:xmmword_1401A2C90+1, 1
0x1400cf6f7  jz      short loc_1400CF720
0x1400cf6f9  mov     edx, 44h ; 'D'
0x1400cf6fe  jmp     loc_1400CF3C5
0x1400cf703  mov     edi, 0C000000Dh
0x1400cf708  test    byte ptr cs:xmmword_1401A2C90+1, 1
0x1400cf70f  jz      short loc_1400CF720
0x1400cf711  mov     edx, 43h ; 'C'
0x1400cf716  jmp     loc_1400CF3C5
0x1400cf71b  mov     edi, 0C00000BBh
0x1400cf720  mov     rdx, [rbp+37h+BugCheckParameter2]; BugCheckParameter2
0x1400cf724  test    rdx, rdx
0x1400cf727  jz      short loc_1400CF763
0x1400cf729  or      eax, 0FFFFFFFFh
0x1400cf72c  lock xadd [rdx], eax
0x1400cf730  dec     eax
0x1400cf732  cmp     cs:UxDebugCheckRefcount, 0
0x1400cf739  jz      short loc_1400CF752
0x1400cf73b  cmp     eax, 0FFFFFFFFh
0x1400cf73e  jg      short loc_1400CF752
0x1400cf740  mov     ecx, 3; BugCheckParameter1
0x1400cf745  movsxd  r9, eax; BugCheckParameter4
0x1400cf748  lea     r8d, [rcx-2]; BugCheckParameter3
0x1400cf74c  call    UlBugCheckEx
0x1400cf752  mov     rcx, [rbp+37h+BugCheckParameter2]; P
0x1400cf756  call    UlpFreeConsumer
0x1400cf75b  mov     [rbp+37h+BugCheckParameter2], 0
0x1400cf763  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cf76a  jz      short loc_1400CF790
0x1400cf76c  mov     rax, [rbp+37h+arg_50]
0x1400cf773  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf77a  mov     edx, 49h ; 'I'
0x1400cf77f  mov     dword ptr [rsp+0E0h+var_C0], edi
0x1400cf783  mov     ecx, 408h
0x1400cf788  mov     r9, [rax]
0x1400cf78b  call    WPP_SF_qD
0x1400cf790  mov     rbx, [rsp+0E0h+arg_0]
0x1400cf798  mov     eax, edi
0x1400cf79a  add     rsp, 0B0h
0x1400cf7a1  pop     r15
0x1400cf7a3  pop     r14
0x1400cf7a5  pop     r13
0x1400cf7a7  pop     r12
0x1400cf7a9  pop     rdi
0x1400cf7aa  pop     rsi
0x1400cf7ab  pop     rbp
0x1400cf7ac  retn
```
