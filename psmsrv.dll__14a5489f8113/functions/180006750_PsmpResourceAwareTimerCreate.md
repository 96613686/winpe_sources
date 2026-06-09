# PsmpResourceAwareTimerCreate

- ea: `0x180006750`
- end: `0x180006b3a`
- name: `PsmpResourceAwareTimerCreate`
- size: `1002`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004f08`
- `0x1800065a0`
- `0x180006750`
- `0x180006b40`
- `0x180006b7c`
- `0x180006c8c`
- `0x18001b7e0`
- `0x18002e17c`

## import_xrefs

- `ntdll!TpSetTimer` at `0x180006aea`
- `ntdll!TpSetTimer` at `0x180006aea`
- `ntdll!TpAllocTimer` at `0x1800068f4`
- `ntdll!TpAllocTimer` at `0x1800068f4`
- `ntdll!RtlFreeHeap` at `0x180006975`
- `ntdll!RtlFreeHeap` at `0x180006b20`
- `ntdll!RtlFreeHeap` at `0x180006975`
- `ntdll!RtlFreeHeap` at `0x180006b20`
- `ntdll!TpReleaseTimer` at `0x180006b03`
- `ntdll!TpReleaseTimer` at `0x180006b03`
- `ntdll!TpWaitForTimer` at `0x180006af9`
- `ntdll!TpWaitForTimer` at `0x180006af9`
- `ntdll!NtCreateWnfStateName` at `0x180006a89`
- `ntdll!NtCreateWnfStateName` at `0x180006a89`
- `ntdll!NtDeleteWnfStateName` at `0x180006b2f`
- `ntdll!NtDeleteWnfStateName` at `0x180006b2f`
- `ntdll!RtlAllocateHeap` at `0x1800067a4`
- `ntdll!RtlAllocateHeap` at `0x18000684a`
- `ntdll!RtlAllocateHeap` at `0x1800067a4`
- `ntdll!RtlAllocateHeap` at `0x18000684a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006a2a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006a2a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006a54`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006a54`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800068a3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800068a3`
- `RPCRT4!UuidCreate` at `0x1800067c2`
- `RPCRT4!UuidCreate` at `0x1800067c2`
- `RPCRT4!I_RpcMapWin32Status` at `0x180006aa4`
- `RPCRT4!I_RpcMapWin32Status` at `0x180006aa4`

## pseudocode

```c
__int64 __fastcall PsmpResourceAwareTimerCreate(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  char *Heap; // rax
  char *v7; // rbx
  RPC_STATUS v8; // eax
  __int64 *v9; // rax
  unsigned int v10; // r12d
  __int64 v11; // r13
  _QWORD *v12; // r14
  __int64 v13; // rcx
  _QWORD *v14; // r15
  __int64 v15; // rax
  char *v16; // rdi
  unsigned int v17; // ecx
  __int64 v18; // rax
  _WORD *v19; // rax
  _WORD *v20; // rsi
  __int64 v21; // rcx
  char *v22; // r8
  __int64 v23; // rdx
  _WORD *v24; // rcx
  DWORD LengthSid; // eax
  int v26; // edi
  _QWORD *v28; // rax
  __int64 v29; // rax
  UUID v30; // xmm0
  _QWORD *v31; // rax
  __int64 v32; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-31h]
  __int64 v34; // [rsp+50h] [rbp-29h]
  PSID pSid; // [rsp+58h] [rbp-21h]
  char *v36; // [rsp+60h] [rbp-19h]
  __int64 v37; // [rsp+68h] [rbp-11h]
  _QWORD *v38; // [rsp+70h] [rbp-9h]
  __int64 v39; // [rsp+78h] [rbp-1h] BYREF
  UUID Uuid; // [rsp+80h] [rbp+7h] BYREF

  v37 = a3;
  v38 = a4;
  Uuid = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x150u);
  v7 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741670;
  PsmpResourceAwareTimerInitialize(Heap);
  v8 = UuidCreate(&Uuid);
  if ( v8 )
  {
    v26 = I_RpcMapWin32Status(v8);
    goto LABEL_23;
  }
  if ( (*(_BYTE *)(a1 + 16) & 1) != 0 )
  {
    v9 = *(__int64 **)(a1 + 8);
    v10 = 4;
    v11 = v9[5];
    v12 = v9 + 13;
    v13 = v9[6];
LABEL_5:
    v34 = v13;
    goto LABEL_6;
  }
  v28 = *(_QWORD **)a1;
  if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
  {
    v11 = v28[851];
    v12 = v28 + 857;
    v13 = v28[25];
    v10 = 8;
    goto LABEL_5;
  }
  v11 = v28[850];
  v12 = v28 + 855;
  v10 = 2;
  v34 = v28[24];
LABEL_6:
  v14 = *(_QWORD **)a1;
  v32 = 0;
  v39 = 0;
  v15 = v14[39];
  v16 = (char *)v14[1];
  v36 = v16;
  v17 = *(_DWORD *)(v15 + 4);
  pSid = *(PSID *)(v15 + 40);
  v33 = v17;
  if ( a2 )
  {
    v18 = v37;
    *((_DWORD *)v7 + 16) |= 2u;
    *((_QWORD *)v7 + 7) = v18;
    *((_QWORD *)v7 + 6) = a2;
  }
  else
  {
    v20 = 0;
    v26 = NtCreateWnfStateName(&v39, 3, 0);
    if ( v26 < 0 )
      goto LABEL_16;
    v16 = v36;
  }
  v19 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x230u);
  v20 = v19;
  if ( v19 )
  {
    v21 = 2147483646;
    v22 = v16;
    v23 = 232;
    do
    {
      if ( !v21 )
        break;
      if ( !*(_WORD *)v22 )
        break;
      *v19 = *(_WORD *)v22;
      v22 += 2;
      ++v19;
      --v21;
      --v23;
    }
    while ( v23 );
    v24 = v19 - 1;
    if ( v23 )
      v24 = v19;
    *v24 = 0;
    LengthSid = GetLengthSid(pSid);
    memcpy_0(v20 + 232, pSid, LengthSid);
    *((_DWORD *)v20 + 133) = v33;
    *((_DWORD *)v20 + 134) = v10;
    *((_QWORD *)v20 + 68) = v11;
    *((_DWORD *)v20 + 138) = *(_DWORD *)(v14[40] + 16LL);
    v26 = TpAllocTimer(&v32, PsmpResourceAwareTimerCallback, v20, 0);
    if ( v26 >= 0 )
    {
      v26 = 0;
      *((_QWORD *)v7 + 5) = v32;
      v29 = v34;
      *((_QWORD *)v7 + 11) = v20;
      v30 = Uuid;
      v32 = 0;
      *((_QWORD *)v7 + 12) = v29;
      *(UUID *)(v7 + 68) = v30;
      *((_QWORD *)v7 + 3) = v14;
      *((_DWORD *)v7 + 4) = 1;
      PsmpResourceAwareTimerReference(v7);
      RtlAcquireSRWLockExclusive(v14 + 41);
      v31 = (_QWORD *)v12[1];
      if ( (_QWORD *)*v31 != v12 )
        __fastfail(3u);
      *(_QWORD *)v7 = v12;
      *((_QWORD *)v7 + 1) = v31;
      v20 = 0;
      *v31 = v7;
      v12[1] = v7;
      RtlReleaseSRWLockExclusive(v14 + 41);
    }
  }
  else
  {
    v26 = -1073741670;
  }
LABEL_16:
  PsmpLogResourceAwareTimerCreate(v36, (__int64)pSid, v33, v10, v11, (__int64)&Uuid, v26);
  if ( v32 )
  {
    TpSetTimer(v32, 0, 0, 0);
    TpWaitForTimer(v32, 1);
    TpReleaseTimer(v32);
  }
  if ( v20 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
  if ( v39 )
    NtDeleteWnfStateName(&v39);
  if ( v26 >= 0 )
  {
    PsmpResourceAwareTimerDereference(v7);
    *v38 = v7;
    return (unsigned int)v26;
  }
LABEL_23:
  PsmpResourceAwareTimerCleanup((__int64)v7);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180006750  mov     [rsp-8+arg_8], rbx
0x180006755  push    rbp
0x180006756  push    rsi
0x180006757  push    rdi
0x180006758  push    r12
0x18000675a  push    r13
0x18000675c  push    r14
0x18000675e  push    r15
0x180006760  lea     rbp, [rsp-27h]
0x180006765  sub     rsp, 0A0h
0x18000676c  mov     rax, cs:__security_cookie
0x180006773  xor     rax, rsp
0x180006776  mov     [rbp+57h+var_40], rax
0x18000677a  mov     rdi, rcx
0x18000677d  mov     [rbp+57h+var_68], r8
0x180006781  xorps   xmm0, xmm0
0x180006784  mov     [rbp+57h+var_60], r9
0x180006788  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18000678c  mov     rcx, gs:60h
0x180006795  mov     rsi, rdx
0x180006798  xor     edx, edx; Flags
0x18000679a  mov     r8d, 150h; Size
0x1800067a0  mov     rcx, [rcx+30h]; HeapHandle
0x1800067a4  call    cs:__imp_RtlAllocateHeap
0x1800067aa  mov     rbx, rax
0x1800067ad  test    rax, rax
0x1800067b0  jz      loc_1800069E6
0x1800067b6  mov     rcx, rax
0x1800067b9  call    PsmpResourceAwareTimerInitialize
0x1800067be  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1800067c2  call    cs:__imp_UuidCreate
0x1800067c8  xor     edx, edx
0x1800067ca  test    eax, eax
0x1800067cc  jnz     loc_180006AA2
0x1800067d2  test    byte ptr [rdi+10h], 1
0x1800067d6  jz      loc_1800069B5
0x1800067dc  mov     rax, [rdi+8]
0x1800067e0  lea     r12d, [rdx+4]
0x1800067e4  mov     r13, [rax+28h]
0x1800067e8  lea     r14, [rax+68h]
0x1800067ec  mov     rcx, [rax+30h]
0x1800067f0  mov     [rbp+57h+var_80], rcx
0x1800067f4  mov     r15, [rdi]
0x1800067f7  mov     [rbp+57h+var_90], rdx
0x1800067fb  mov     [rbp+57h+var_58], rdx
0x1800067ff  mov     rax, [r15+138h]
0x180006806  mov     rdi, [r15+8]
0x18000680a  mov     [rbp+57h+var_70], rdi
0x18000680e  mov     ecx, [rax+4]
0x180006811  mov     rax, [rax+28h]
0x180006815  mov     [rbp+57h+pSid], rax
0x180006819  mov     [rbp+57h+var_88], ecx
0x18000681c  test    rsi, rsi
0x18000681f  jz      loc_180006A5F
0x180006825  mov     rax, [rbp+57h+var_68]
0x180006829  or      dword ptr [rbx+40h], 2
0x18000682d  mov     [rbx+38h], rax
0x180006831  mov     [rbx+30h], rsi
0x180006835  mov     rcx, gs:60h
0x18000683e  xor     edx, edx; Flags
0x180006840  mov     r8d, 230h; Size
0x180006846  mov     rcx, [rcx+30h]; HeapHandle
0x18000684a  call    cs:__imp_RtlAllocateHeap
0x180006850  xor     r10d, r10d
0x180006853  mov     rsi, rax
0x180006856  test    rax, rax
0x180006859  jz      loc_180006AD1
0x18000685f  mov     ecx, 7FFFFFFEh
0x180006864  mov     r8, rdi
0x180006867  mov     edx, 0E8h
0x18000686c  test    rcx, rcx
0x18000686f  jz      short loc_180006890
0x180006871  movzx   r9d, word ptr [r8]
0x180006875  test    r9w, r9w
0x180006879  jz      short loc_180006890
0x18000687b  mov     [rax], r9w
0x18000687f  add     r8, 2
0x180006883  add     rax, 2
0x180006887  dec     rcx
0x18000688a  sub     rdx, 1
0x18000688e  jnz     short loc_18000686C
0x180006890  test    rdx, rdx
0x180006893  lea     rcx, [rax-2]
0x180006897  cmovnz  rcx, rax
0x18000689b  mov     [rcx], r10w
0x18000689f  mov     rcx, [rbp+57h+pSid]; pSid
0x1800068a3  call    cs:__imp_GetLengthSid
0x1800068a9  mov     rdx, [rbp+57h+pSid]; Src
0x1800068ad  lea     rcx, [rsi+1D0h]; void *
0x1800068b4  mov     r8d, eax; Size
0x1800068b7  call    memcpy_0
0x1800068bc  mov     eax, [rbp+57h+var_88]
0x1800068bf  lea     rdx, PsmpResourceAwareTimerCallback
0x1800068c6  mov     [rsi+214h], eax
0x1800068cc  xor     r9d, r9d
0x1800068cf  mov     [rsi+218h], r12d
0x1800068d6  mov     r8, rsi
0x1800068d9  mov     [rsi+220h], r13
0x1800068e0  mov     rax, [r15+140h]
0x1800068e7  mov     ecx, [rax+10h]
0x1800068ea  mov     [rsi+228h], ecx
0x1800068f0  lea     rcx, [rbp+57h+var_90]
0x1800068f4  call    cs:__imp_TpAllocTimer
0x1800068fa  mov     edi, eax
0x1800068fc  test    eax, eax
0x1800068fe  jns     loc_1800069ED
0x180006904  mov     r8d, [rbp+57h+var_88]
0x180006908  lea     rax, [rbp+57h+Uuid]
0x18000690c  mov     rdx, [rbp+57h+pSid]
0x180006910  mov     r9d, r12d
0x180006913  mov     rcx, [rbp+57h+var_70]
0x180006917  mov     dword ptr [rsp+0D0h+var_A0], edi
0x18000691b  mov     [rsp+0D0h+var_A8], rax
0x180006920  mov     [rsp+0D0h+var_B0], r13
0x180006925  call    PsmpLogResourceAwareTimerCreate
0x18000692a  mov     rcx, [rbp+57h+var_90]
0x18000692e  xor     r12d, r12d
0x180006931  test    rcx, rcx
0x180006934  jnz     loc_180006AE2
0x18000693a  test    rsi, rsi
0x18000693d  jnz     loc_180006B0E
0x180006943  cmp     dword ptr [rbp+57h+var_58], r12d
0x180006947  jnz     loc_180006B2B
0x18000694d  cmp     dword ptr [rbp+57h+var_58+4], r12d
0x180006951  jnz     loc_180006B2B
0x180006957  test    edi, edi
0x180006959  jns     short loc_1800069A4
0x18000695b  mov     rcx, rbx
0x18000695e  call    PsmpResourceAwareTimerCleanup
0x180006963  mov     rcx, gs:60h
0x18000696c  mov     r8, rbx; P
0x18000696f  xor     edx, edx; Flags
0x180006971  mov     rcx, [rcx+30h]; HeapHandle
0x180006975  call    cs:__imp_RtlFreeHeap
0x18000697b  mov     eax, edi
0x18000697d  mov     rcx, [rbp+57h+var_40]
0x180006981  xor     rcx, rsp; StackCookie
0x180006984  call    __security_check_cookie
0x180006989  mov     rbx, [rsp+0D0h+arg_8]
0x180006991  add     rsp, 0A0h
0x180006998  pop     r15
0x18000699a  pop     r14
0x18000699c  pop     r13
0x18000699e  pop     r12
0x1800069a0  pop     rdi
0x1800069a1  pop     rsi
0x1800069a2  pop     rbp
0x1800069a3  retn
0x1800069a4  mov     rcx, rbx; P
0x1800069a7  call    PsmpResourceAwareTimerDereference
0x1800069ac  mov     rax, [rbp+57h+var_60]
0x1800069b0  mov     [rax], rbx
0x1800069b3  jmp     short loc_18000697B
0x1800069b5  test    byte ptr [rdi+10h], 2
0x1800069b9  mov     rax, [rdi]
0x1800069bc  jnz     loc_180006AB1
0x1800069c2  mov     r13, [rax+1A90h]
0x1800069c9  lea     r14, [rax+1AB8h]
0x1800069d0  mov     rax, [rax+0C0h]
0x1800069d7  mov     r12d, 2
0x1800069dd  mov     [rbp+57h+var_80], rax
0x1800069e1  jmp     loc_1800067F4
0x1800069e6  mov     edi, 0C000009Ah
0x1800069eb  jmp     short loc_18000697B
0x1800069ed  mov     rax, [rbp+57h+var_90]
0x1800069f1  xor     edi, edi
0x1800069f3  mov     [rbx+28h], rax
0x1800069f7  mov     rcx, rbx
0x1800069fa  mov     rax, [rbp+57h+var_80]
0x1800069fe  mov     [rbx+58h], rsi
0x180006a02  movups  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x180006a06  mov     [rbp+57h+var_90], rdi
0x180006a0a  mov     [rbx+60h], rax
0x180006a0e  movdqu  xmmword ptr [rbx+44h], xmm0
0x180006a13  mov     [rbx+18h], r15
0x180006a17  mov     dword ptr [rbx+10h], 1
0x180006a1e  call    PsmpResourceAwareTimerReference
0x180006a23  lea     rcx, [r15+148h]
0x180006a2a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180006a30  mov     rax, [r14+8]
0x180006a34  cmp     [rax], r14
0x180006a37  jnz     loc_180006ADB
0x180006a3d  mov     [rbx], r14
0x180006a40  lea     rcx, [r15+148h]
0x180006a47  mov     [rbx+8], rax
0x180006a4b  mov     esi, edi
0x180006a4d  mov     [rax], rbx
0x180006a50  mov     [r14+8], rbx
0x180006a54  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180006a5a  jmp     loc_180006904
0x180006a5f  lea     rax, PsmpResourceTimerDescriptor
0x180006a66  xor     r9d, r9d
0x180006a69  mov     [rsp+0D0h+var_A0], rax
0x180006a6e  lea     rcx, [rbp+57h+var_58]
0x180006a72  mov     rsi, rdx
0x180006a75  mov     dword ptr [rsp+0D0h+var_A8], 10h
0x180006a7d  mov     [rsp+0D0h+var_B0], rdx
0x180006a82  xor     r8d, r8d
0x180006a85  lea     edx, [r9+3]
0x180006a89  call    cs:__imp_NtCreateWnfStateName
0x180006a8f  mov     edi, eax
0x180006a91  test    eax, eax
0x180006a93  js      loc_180006904
0x180006a99  mov     rdi, [rbp+57h+var_70]
0x180006a9d  jmp     loc_180006835
0x180006aa2  mov     ecx, eax; Status
0x180006aa4  call    cs:__imp_I_RpcMapWin32Status
0x180006aaa  mov     edi, eax
0x180006aac  jmp     loc_18000695B
0x180006ab1  mov     r13, [rax+1A98h]
0x180006ab8  lea     r14, [rax+1AC8h]
0x180006abf  mov     rcx, [rax+0C8h]
0x180006ac6  mov     r12d, 8
0x180006acc  jmp     loc_1800067F0
0x180006ad1  mov     edi, 0C000009Ah
0x180006ad6  jmp     loc_180006904
0x180006adb  mov     ecx, 3
0x180006ae0  int     29h; Win8: RtlFailFast(ecx)
0x180006ae2  xor     r9d, r9d
0x180006ae5  xor     r8d, r8d
0x180006ae8  xor     edx, edx
0x180006aea  call    cs:__imp_TpSetTimer
0x180006af0  mov     rcx, [rbp+57h+var_90]
0x180006af4  mov     edx, 1
0x180006af9  call    cs:__imp_TpWaitForTimer
0x180006aff  mov     rcx, [rbp+57h+var_90]
0x180006b03  call    cs:__imp_TpReleaseTimer
0x180006b09  jmp     loc_18000693A
0x180006b0e  mov     rcx, gs:60h
0x180006b17  mov     r8, rsi; P
0x180006b1a  xor     edx, edx; Flags
0x180006b1c  mov     rcx, [rcx+30h]; HeapHandle
0x180006b20  call    cs:__imp_RtlFreeHeap
0x180006b26  jmp     loc_180006943
0x180006b2b  lea     rcx, [rbp+57h+var_58]
0x180006b2f  call    cs:__imp_NtDeleteWnfStateName
0x180006b35  jmp     loc_180006957
```
