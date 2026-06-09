# UlpOpenRequestQueue

- ea: `0x1400cf398`
- end: `0x1400cf88e`
- name: `UlpOpenRequestQueue`
- size: `1270`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a339c`

## callees

- `0x14000a350`
- `0x1400422d8`
- `0x1400953dc`
- `0x140095f70`
- `0x1400a03f0`
- `0x1400cdfec`
- `0x1400cec34`
- `0x1400cf398`
- `0x1400d03d4`
- `0x140167b40`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c5a0c`
- `0x1401c5e80`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cf70a`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cf771`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cf70a`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cf771`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cf5ba`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cf5ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf716`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf77d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf7a5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf716`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf77d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cf7a5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400cf799`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400cf799`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400cf6d2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400cf6d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf5a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf6bd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf5a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf6bd`

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
0x1400cf398  mov     rax, rsp
0x1400cf39b  mov     [rax+8], rbx
0x1400cf39f  mov     [rax+20h], r9
0x1400cf3a3  mov     [rax+10h], edx
0x1400cf3a6  push    rbp
0x1400cf3a7  push    rsi
0x1400cf3a8  push    rdi
0x1400cf3a9  push    r12
0x1400cf3ab  push    r13
0x1400cf3ad  push    r14
0x1400cf3af  push    r15
0x1400cf3b1  lea     rbp, [rax-3Fh]
0x1400cf3b5  sub     rsp, 0B0h
0x1400cf3bc  xor     edi, edi
0x1400cf3be  mov     r15, r8
0x1400cf3c1  mov     [rbp+37h+var_7C], edi
0x1400cf3c4  mov     ebx, edx
0x1400cf3c6  mov     [rbp+37h+BugCheckParameter2], rdi
0x1400cf3ca  mov     r13, rcx
0x1400cf3cd  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cf3d4  mov     r14d, [rbp+37h+arg_30]
0x1400cf3d8  mov     r12d, [rbp+37h+DesiredAccess]
0x1400cf3dc  mov     rsi, [rbp+37h+arg_28]
0x1400cf3e0  jz      short loc_1400CF421
0x1400cf3e2  mov     r8, [rbp+37h+arg_50]
0x1400cf3e9  mov     rax, [r15+8]
0x1400cf3ed  mov     [rsp+58h], r8
0x1400cf3f2  mov     dword ptr [rsp+0E0h+var_90], r14d
0x1400cf3f7  mov     qword ptr [rsp+0E0h+var_98], rsi
0x1400cf3fc  mov     dword ptr [rsp+0E0h+var_A0], r12d
0x1400cf401  mov     qword ptr [rsp+0E0h+var_A8], r9
0x1400cf406  mov     r9, r13
0x1400cf409  mov     [rsp+0E0h+var_B0], rax
0x1400cf40e  shr     edx, 10h
0x1400cf411  movzx   ecx, bx
0x1400cf414  mov     dword ptr [rsp+0E0h+var_B8], edx
0x1400cf418  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x1400cf41c  call    WPP_SF_qllSqLqLq
0x1400cf421  mov     rax, [rbp+37h+arg_50]
0x1400cf428  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf42f  mov     [rax], rdi
0x1400cf432  cmp     r14d, 8
0x1400cf436  ja      loc_1400CF7FB
0x1400cf43c  mov     eax, 112h
0x1400cf441  bt      eax, r14d
0x1400cf445  jnb     loc_1400CF7FB
0x1400cf44b  mov     eax, dword ptr [rbp+37h+arg_48]
0x1400cf451  test    al, 10h
0x1400cf453  jnz     short loc_1400CF469
0x1400cf455  mov     byte ptr [rbp+37h+arg_30], dil
0x1400cf459  cmp     [r15+8], rdi
0x1400cf45d  jnz     short loc_1400CF4B4
0x1400cf45f  mov     edi, 0C000000Dh
0x1400cf464  jmp     loc_1400CF800
0x1400cf469  test    al, 2
0x1400cf46b  jnz     loc_1400CF7E3
0x1400cf471  test    al, 4
0x1400cf473  jnz     loc_1400CF7CB
0x1400cf479  test    al, 8
0x1400cf47b  jnz     loc_1400CF7B3
0x1400cf481  mov     byte ptr [rbp+37h+arg_30], 1
0x1400cf485  cmp     r12d, 0E0000h
0x1400cf48c  jz      short loc_1400CF459
0x1400cf48e  mov     edi, 0C000000Dh
0x1400cf493  test    byte ptr cs:xmmword_1401A2C90+1, 1
0x1400cf49a  jz      loc_1400CF800
0x1400cf4a0  mov     edx, 46h ; 'F'
0x1400cf4a5  mov     ecx, 208h
0x1400cf4aa  call    WPP_SF_
0x1400cf4af  jmp     loc_1400CF800
0x1400cf4b4  lea     rdx, [rbp+37h+var_7C]
0x1400cf4b8  mov     rcx, r15; String
0x1400cf4bb  call    UlpValidateRequestQueueName
0x1400cf4c0  mov     edi, eax
0x1400cf4c2  test    eax, eax
0x1400cf4c4  js      loc_1400CF800
0x1400cf4ca  cmp     r14d, 4
0x1400cf4ce  jnz     short loc_1400CF4E0
0x1400cf4d0  test    r12b, 20h
0x1400cf4d4  jnz     short loc_1400CF4E0
0x1400cf4d6  mov     edi, 0C0000022h
0x1400cf4db  jmp     loc_1400CF800
0x1400cf4e0  lea     r8, [rbp+37h+BugCheckParameter2]
0x1400cf4e4  mov     edx, r14d
0x1400cf4e7  mov     rcx, rsi
0x1400cf4ea  call    UlpAllocateConsumer
0x1400cf4ef  mov     edi, eax
0x1400cf4f1  test    eax, eax
0x1400cf4f3  js      loc_1400CF800
0x1400cf4f9  mov     edi, [rbp+37h+arg_38]
0x1400cf4fc  test    edi, edi
0x1400cf4fe  jz      loc_1400CF6B9
0x1400cf504  xor     edx, edx; Val
0x1400cf506  lea     rcx, [rbp+37h+var_70]; void *
0x1400cf50a  lea     r8d, [rdx+40h]; Size
0x1400cf50e  call    memset
0x1400cf513  mov     eax, [rbp+37h+var_7C]
0x1400cf516  lea     r9, [rbp+37h+var_70]
0x1400cf51a  mov     [rbp+37h+var_68], eax
0x1400cf51d  lea     rcx, UlpFindRequestQueueWithExternalIdAndPod
0x1400cf524  mov     rax, [rbp+37h+arg_40]
0x1400cf52b  xor     r8d, r8d
0x1400cf52e  mov     dl, 1
0x1400cf530  mov     [rbp+37h+var_60], rax
0x1400cf534  mov     [rbp+37h+var_70], r15
0x1400cf538  mov     [rbp+37h+var_58], edi
0x1400cf53b  mov     [rsp+0E0h+var_C0], 0
0x1400cf544  call    UxPodEnumerateEx
0x1400cf549  mov     rsi, [rbp+37h+var_50]
0x1400cf54d  test    rsi, rsi
0x1400cf550  jnz     short loc_1400CF55C
0x1400cf552  mov     edi, 0C0000034h
0x1400cf557  jmp     loc_1400CF800
0x1400cf55c  mov     r9, [rbp+37h+var_48]
0x1400cf560  cmp     r13, r9
0x1400cf563  mov     r13, r9
0x1400cf566  setnz   [rbp+37h+var_80]
0x1400cf56a  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400cf571  jz      short loc_1400CF589
0x1400cf573  mov     edx, 47h ; 'G'
0x1400cf578  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf57f  mov     ecx, 416h
0x1400cf584  call    WPP_SF_q
0x1400cf589  cmp     [rsi+114h], bx
0x1400cf590  jnz     loc_1400CF78B
0x1400cf596  movzx   eax, [rbp+37h+arg_A]
0x1400cf59a  cmp     [rsi+116h], ax
0x1400cf5a1  jnz     loc_1400CF78B
0x1400cf5a7  call    cs:__imp_KeEnterCriticalRegion
0x1400cf5ae  nop     dword ptr [rax+rax+00h]
0x1400cf5b3  mov     rcx, [rsi+118h]
0x1400cf5ba  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400cf5c1  nop     dword ptr [rax+rax+00h]
0x1400cf5c6  mov     rax, [r15+8]
0x1400cf5ca  mov     r8d, r12d; DesiredAccess
0x1400cf5cd  mov     rbx, [rbp+37h+arg_28]
0x1400cf5d1  mov     rdx, [rbp+37h+AccessState]; AccessState
0x1400cf5d5  mov     rcx, [rsi+98h]; SecurityDescriptor
0x1400cf5dc  mov     [rsp+0E0h+var_B8], 0; char
0x1400cf5e1  mov     r9b, [rbx+40h]; AccessMode
0x1400cf5e5  mov     [rsp+0E0h+var_C0], rax; __int64
0x1400cf5ea  call    UlAccessCheck
0x1400cf5ef  mov     edi, eax
0x1400cf5f1  xor     eax, eax
0x1400cf5f3  test    edi, edi
0x1400cf5f5  jns     short loc_1400CF65C
0x1400cf5f7  cmp     byte ptr [rbp+37h+arg_30], al
0x1400cf5fa  jz      loc_1400CF76A
0x1400cf600  mov     r9b, [rbx+40h]; AccessMode
0x1400cf604  lea     rcx, UxAdminSDBytes; SecurityDescriptor
0x1400cf60b  mov     rdx, [rbp+37h+AccessState]; AccessState
0x1400cf60f  mov     r8d, 20000h; DesiredAccess
0x1400cf615  mov     [rsp+0E0h+var_B8], al; char
0x1400cf619  mov     [rsp+0E0h+var_C0], rax; __int64
0x1400cf61e  call    UlAccessCheck
0x1400cf623  mov     edi, eax
0x1400cf625  test    eax, eax
0x1400cf627  js      loc_1400CF76A
0x1400cf62d  mov     rax, [r15+8]
0x1400cf631  mov     r8d, r12d; DesiredAccess
0x1400cf634  mov     r9b, [rbx+40h]; AccessMode
0x1400cf638  mov     rdx, [rbp+37h+AccessState]; AccessState
0x1400cf63c  mov     rcx, [rsi+98h]; SecurityDescriptor
0x1400cf643  mov     [rsp+0E0h+var_B8], 1; char
0x1400cf648  mov     [rsp+0E0h+var_C0], rax; __int64
0x1400cf64d  call    UlAccessCheck
0x1400cf652  mov     edi, eax
0x1400cf654  test    eax, eax
0x1400cf656  js      loc_1400CF76A
0x1400cf65c  mov     rdx, [rbp+37h+BugCheckParameter2]; ULONG_PTR
0x1400cf660  mov     rcx, rsi; BugCheckParameter2
0x1400cf663  call    UlpAttachConsumerToRequestQueue
0x1400cf668  mov     edi, eax
0x1400cf66a  test    eax, eax
0x1400cf66c  js      loc_1400CF76A
0x1400cf672  cmp     [rbp+37h+var_80], 0
0x1400cf676  jz      loc_1400CF703
0x1400cf67c  mov     rax, [rbp+37h+BugCheckParameter2]
0x1400cf680  lea     rdx, [r13+1070h]; BugCheckParameter2
0x1400cf687  mov     byte ptr [rax+80h], 1
0x1400cf68e  mov     eax, 1
0x1400cf693  lock xadd [rdx], eax
0x1400cf697  inc     eax
0x1400cf699  cmp     cs:UxDebugCheckRefcount, 0
0x1400cf6a0  jz      short loc_1400CF703
0x1400cf6a2  cmp     eax, 0FFFFFFFFh
0x1400cf6a5  jg      short loc_1400CF703
0x1400cf6a7  mov     ecx, 3; BugCheckParameter1
0x1400cf6ac  movsxd  r9, eax; BugCheckParameter4
0x1400cf6af  lea     r8d, [rcx+7]; BugCheckParameter3
0x1400cf6b3  call    UlBugCheckEx
0x1400cf6b9  mov     [rbp+37h+var_80], 0
0x1400cf6bd  call    cs:__imp_KeEnterCriticalRegion
0x1400cf6c4  nop     dword ptr [rax+rax+00h]
0x1400cf6c9  lea     rcx, [r13+1030h]
0x1400cf6d0  xor     edx, edx
0x1400cf6d2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400cf6d9  nop     dword ptr [rax+rax+00h]
0x1400cf6de  mov     r8d, [rbp+37h+var_7C]
0x1400cf6e2  mov     rdx, r15
0x1400cf6e5  mov     rcx, r13
0x1400cf6e8  call    UlpFindRequestQueue
0x1400cf6ed  mov     rsi, rax
0x1400cf6f0  test    rax, rax
0x1400cf6f3  jnz     loc_1400CF589
0x1400cf6f9  mov     edi, 0C0000034h
0x1400cf6fe  jmp     loc_1400CF790
0x1400cf703  mov     rcx, [rsi+118h]
0x1400cf70a  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cf711  nop     dword ptr [rax+rax+00h]
0x1400cf716  call    cs:__imp_KeLeaveCriticalRegion
0x1400cf71d  nop     dword ptr [rax+rax+00h]
0x1400cf722  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400cf729  jz      short loc_1400CF752
0x1400cf72b  mov     rax, [rbp+37h+BugCheckParameter2]
0x1400cf72f  lea     rcx, [rsi+0A0h]
0x1400cf736  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x1400cf73b  mov     edx, 48h ; 'H'
0x1400cf740  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400cf745  mov     r9, rsi
0x1400cf748  mov     [rsp+0E0h+var_C0], rcx
0x1400cf74d  call    WPP_SF_qZqL
0x1400cf752  mov     rax, [rbp+37h+BugCheckParameter2]
0x1400cf756  mov     r8, [rbp+37h+arg_50]
0x1400cf75d  mov     [rbp+37h+BugCheckParameter2], 0
0x1400cf765  mov     [r8], rax
0x1400cf768  jmp     short loc_1400CF790
0x1400cf76a  mov     rcx, [rsi+118h]
0x1400cf771  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cf778  nop     dword ptr [rax+rax+00h]
0x1400cf77d  call    cs:__imp_KeLeaveCriticalRegion
0x1400cf784  nop     dword ptr [rax+rax+00h]
0x1400cf789  jmp     short loc_1400CF790
0x1400cf78b  mov     edi, 0C00000BBh
0x1400cf790  lea     rcx, [r13+1030h]
0x1400cf797  xor     edx, edx
0x1400cf799  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400cf7a0  nop     dword ptr [rax+rax+00h]
0x1400cf7a5  call    cs:__imp_KeLeaveCriticalRegion
0x1400cf7ac  nop     dword ptr [rax+rax+00h]
0x1400cf7b1  jmp     short loc_1400CF800
0x1400cf7b3  mov     edi, 0C000000Dh
0x1400cf7b8  test    byte ptr cs:xmmword_1401A2C90+1, 1
0x1400cf7bf  jz      short loc_1400CF800
0x1400cf7c1  mov     edx, 45h ; 'E'
0x1400cf7c6  jmp     loc_1400CF4A5
0x1400cf7cb  mov     edi, 0C000000Dh
0x1400cf7d0  test    byte ptr cs:xmmword_1401A2C90+1, 1
0x1400cf7d7  jz      short loc_1400CF800
0x1400cf7d9  mov     edx, 44h ; 'D'
0x1400cf7de  jmp     loc_1400CF4A5
0x1400cf7e3  mov     edi, 0C000000Dh
0x1400cf7e8  test    byte ptr cs:xmmword_1401A2C90+1, 1
0x1400cf7ef  jz      short loc_1400CF800
0x1400cf7f1  mov     edx, 43h ; 'C'
0x1400cf7f6  jmp     loc_1400CF4A5
0x1400cf7fb  mov     edi, 0C00000BBh
0x1400cf800  mov     rdx, [rbp+37h+BugCheckParameter2]; BugCheckParameter2
0x1400cf804  test    rdx, rdx
0x1400cf807  jz      short loc_1400CF843
0x1400cf809  or      eax, 0FFFFFFFFh
0x1400cf80c  lock xadd [rdx], eax
0x1400cf810  dec     eax
0x1400cf812  cmp     cs:UxDebugCheckRefcount, 0
0x1400cf819  jz      short loc_1400CF832
0x1400cf81b  cmp     eax, 0FFFFFFFFh
0x1400cf81e  jg      short loc_1400CF832
0x1400cf820  mov     ecx, 3; BugCheckParameter1
0x1400cf825  movsxd  r9, eax; BugCheckParameter4
0x1400cf828  lea     r8d, [rcx-2]; BugCheckParameter3
0x1400cf82c  call    UlBugCheckEx
0x1400cf832  mov     rcx, [rbp+37h+BugCheckParameter2]; P
0x1400cf836  call    UlpFreeConsumer
0x1400cf83b  mov     [rbp+37h+BugCheckParameter2], 0
0x1400cf843  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cf84a  jz      short loc_1400CF870
0x1400cf84c  mov     rax, [rbp+37h+arg_50]
0x1400cf853  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cf85a  mov     edx, 49h ; 'I'
0x1400cf85f  mov     dword ptr [rsp+0E0h+var_C0], edi
0x1400cf863  mov     ecx, 408h
0x1400cf868  mov     r9, [rax]
0x1400cf86b  call    WPP_SF_qD
0x1400cf870  mov     rbx, [rsp+0E0h+arg_0]
0x1400cf878  mov     eax, edi
0x1400cf87a  add     rsp, 0B0h
0x1400cf881  pop     r15
0x1400cf883  pop     r14
0x1400cf885  pop     r13
0x1400cf887  pop     r12
0x1400cf889  pop     rdi
0x1400cf88a  pop     rsi
0x1400cf88b  pop     rbp
0x1400cf88c  retn
```
