# TdiConnect

- ea: `0x1400074d0`
- end: `0x1400077c4`
- name: `TdiConnect`
- size: `756`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140004788`
- `0x140007488`
- `0x1400074d0`
- `0x1400079c0`
- `0x140007b60`
- `0x14000b974`
- `0x14000be58`
- `0x14000bf00`
- `0x14001ed50`
- `0x14001fc30`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400075b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400075b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400075f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007752`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400075f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007752`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x140007561`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x140007561`
- `ntoskrnl!RtlCompareMemory` at `0x140007674`
- `ntoskrnl!RtlCompareMemory` at `0x140007674`

## pseudocode

```c
__int64 __fastcall TdiConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  int v7; // eax
  __int64 v9; // rdi
  unsigned int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  int v14; // edi
  __int64 v15; // rdx
  int v16; // edx
  unsigned int v17; // eax
  char v18; // r14
  __int64 v19; // [rsp+50h] [rbp-58h] BYREF
  int v20; // [rsp+58h] [rbp-50h]

  v4 = *(_QWORD *)(a4 + 8);
  v7 = *(_DWORD *)(v4 + 32);
  if ( v7 < 36 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        15,
        115,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        v7,
        36,
        13);
    v19 = 58375007;
    v20 = -1073741811;
    RtlLogUnexpectedCodepath(&v19);
    return 3221225485LL;
  }
  v9 = *(_QWORD *)(v4 + 40);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_i_guid_d(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a4);
  *(_BYTE *)(a3 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 48));
  v10 = TdiConnStateLocked(a3, 1);
  if ( !v10 )
  {
    *(_OWORD *)(a3 + 116) = *(_OWORD *)(v9 + 8);
    *(_OWORD *)(a3 + 128) = *(_OWORD *)(v9 + 20);
    if ( (*(_QWORD *)(a3 + 116) & 0xFFFF000000000000uLL) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_i(WPP_GLOBAL_Control->DeviceExtension, v11, v12, v13);
LABEL_13:
      v14 = -1073741305;
LABEL_24:
      v15 = 0;
      goto LABEL_9;
    }
    v17 = *(_DWORD *)(a3 + 140);
    if ( !v17 || (v18 = 1, v17 > 0x1E) )
    {
      if ( RtlCompareMemory((const void *)(a3 + 124), qword_140022B88, 0x10u) == 16 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            1,
            118,
            (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
            *(_DWORD *)(a3 + 140));
        goto LABEL_13;
      }
      v18 = 0;
    }
    if ( *(_QWORD *)(a3 + 344) == a3 + 344 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_DDd_guid_(
          WPP_GLOBAL_Control->DeviceExtension,
          a3 + 124,
          (unsigned __int16)WORD2(*(_QWORD *)(a3 + 116)),
          v13);
      v14 = IrpList_EnqueueEx(a3 + 344, a2);
      KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), *(_BYTE *)(a3 + 56));
      if ( v14 >= 0 )
      {
        if ( v18 )
          TdiConnectToPortWithPolicy(a3);
        else
          TdiConnectToUuid(a3, a2);
      }
      goto LABEL_31;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        1,
        119,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
    v14 = -1073741504;
    goto LABEL_24;
  }
  v14 = 0;
  v15 = v10;
LABEL_9:
  TdiConnStateLocked(a3, v15);
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), *(_BYTE *)(a3 + 56));
LABEL_31:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      15,
      121,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400074d0  push    rbx
0x1400074d2  push    rbp
0x1400074d3  push    rsi
0x1400074d4  push    rdi
0x1400074d5  push    r12
0x1400074d7  push    r14
0x1400074d9  push    r15
0x1400074db  sub     rsp, 70h
0x1400074df  mov     rax, cs:__security_cookie
0x1400074e6  xor     rax, rsp
0x1400074e9  mov     [rsp+0A8h+var_48], rax
0x1400074ee  mov     rdi, [r9+8]
0x1400074f2  mov     rbx, r8
0x1400074f5  mov     r12, rdx
0x1400074f8  mov     eax, [rdi+20h]
0x1400074fb  cmp     eax, 24h ; '$'
0x1400074fe  jge     short loc_140007574
0x140007500  lea     rsi, WPP_RECORDER_INITIALIZED
0x140007507  mov     ebx, 0C000000Dh
0x14000750c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140007513  jz      short loc_14000754B
0x140007515  mov     rcx, cs:WPP_GLOBAL_Control
0x14000751c  lea     rbp, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140007523  mov     [rsp+0A8h+var_70], ebx
0x140007527  mov     r9d, 73h ; 's'
0x14000752d  mov     dword ptr [rsp+0A8h+var_78], 24h ; '$'
0x140007535  mov     dword ptr [rsp+0A8h+var_80], eax
0x140007539  mov     rcx, [rcx+40h]
0x14000753d  lea     r8d, [r9-64h]
0x140007541  mov     [rsp+0A8h+var_88], rbp
0x140007546  call    WPP_RECORDER_SF_ddd
0x14000754b  lea     rcx, [rsp+0A8h+var_58]
0x140007550  mov     [rsp+0A8h+var_58], 37ABB5Fh
0x140007559  mov     [rsp+0A8h+var_50], 0C000000Dh
0x140007561  call    cs:__imp_RtlLogUnexpectedCodepath
0x140007568  nop     dword ptr [rax+rax+00h]
0x14000756d  mov     eax, ebx
0x14000756f  jmp     loc_1400077A7
0x140007574  mov     rdi, [rdi+28h]
0x140007578  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000757f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140007586  jz      short loc_1400075B1
0x140007588  mov     eax, [rdi+20h]
0x14000758b  lea     rcx, [rdi+10h]
0x14000758f  mov     [rsp+0A8h+var_70], eax
0x140007593  mov     rax, [rdi+8]
0x140007597  mov     [rsp+0A8h+var_78], rcx
0x14000759c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075a3  mov     [rsp+0A8h+var_80], rax
0x1400075a8  mov     rcx, [rcx+40h]
0x1400075ac  call    WPP_RECORDER_SF_i_guid_d
0x1400075b1  lea     r15, [rbx+30h]
0x1400075b5  mov     rcx, r15; SpinLock
0x1400075b8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400075bf  nop     dword ptr [rax+rax+00h]
0x1400075c4  mov     edx, 1
0x1400075c9  mov     rcx, rbx
0x1400075cc  mov     [rbx+38h], al
0x1400075cf  call    TdiConnStateLocked
0x1400075d4  lea     rbp, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400075db  test    eax, eax
0x1400075dd  jz      short loc_140007602
0x1400075df  xor     edi, edi
0x1400075e1  mov     edx, eax
0x1400075e3  mov     rcx, rbx
0x1400075e6  call    TdiConnStateLocked
0x1400075eb  mov     dl, [rbx+38h]; NewIrql
0x1400075ee  mov     rcx, r15; SpinLock
0x1400075f1  call    cs:__imp_KeReleaseSpinLock
0x1400075f8  nop     dword ptr [rax+rax+00h]
0x1400075fd  jmp     loc_140007779
0x140007602  movups  xmm0, xmmword ptr [rdi+8]
0x140007606  mov     rcx, 0FFFF000000000000h
0x140007610  movups  xmmword ptr [rbx+74h], xmm0
0x140007614  movups  xmm1, xmmword ptr [rdi+14h]
0x140007618  movups  xmmword ptr [rbx+80h], xmm1
0x14000761f  mov     rax, [rbx+74h]
0x140007623  test    rcx, rax
0x140007626  jz      short loc_140007650
0x140007628  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000762f  jz      short loc_140007646
0x140007631  mov     rcx, cs:WPP_GLOBAL_Control
0x140007638  mov     [rsp+0A8h+var_80], rax
0x14000763d  mov     rcx, [rcx+40h]
0x140007641  call    WPP_RECORDER_SF_i
0x140007646  mov     edi, 0C0000207h
0x14000764b  jmp     loc_1400076F4
0x140007650  mov     eax, [rbx+8Ch]
0x140007656  cmp     eax, 1
0x140007659  jb      short loc_140007663
0x14000765b  mov     r14b, 1
0x14000765e  cmp     eax, 1Eh
0x140007661  jbe     short loc_1400076BB
0x140007663  lea     rcx, [rbx+7Ch]; Source1
0x140007667  mov     r8d, 10h; Length
0x14000766d  lea     rdx, qword_140022B88; Source2
0x140007674  call    cs:__imp_RtlCompareMemory
0x14000767b  nop     dword ptr [rax+rax+00h]
0x140007680  cmp     rax, 10h
0x140007684  jnz     short loc_1400076B8
0x140007686  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000768d  jz      short loc_140007646
0x14000768f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007696  lea     r9d, [rax+66h]
0x14000769a  mov     eax, [rbx+8Ch]
0x1400076a0  lea     r8d, [r9-75h]
0x1400076a4  mov     dword ptr [rsp+0A8h+var_80], eax
0x1400076a8  mov     [rsp+0A8h+var_88], rbp
0x1400076ad  mov     rcx, [rcx+40h]
0x1400076b1  call    WPP_RECORDER_SF_d
0x1400076b6  jmp     short loc_140007646
0x1400076b8  xor     r14b, r14b
0x1400076bb  lea     rdi, [rbx+158h]
0x1400076c2  cmp     [rdi], rdi
0x1400076c5  jz      short loc_1400076FB
0x1400076c7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400076ce  jz      short loc_1400076EF
0x1400076d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400076d7  mov     r9d, 77h ; 'w'
0x1400076dd  mov     [rsp+0A8h+var_88], rbp
0x1400076e2  mov     rcx, [rcx+40h]
0x1400076e6  lea     r8d, [r9-76h]
0x1400076ea  call    WPP_RECORDER_SF_
0x1400076ef  mov     edi, 0C0000140h
0x1400076f4  xor     edx, edx
0x1400076f6  jmp     loc_1400075E3
0x1400076fb  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140007702  jz      short loc_14000773F
0x140007704  mov     rax, [rbx+74h]
0x140007708  lea     rdx, [rbx+7Ch]
0x14000770c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007713  shr     rax, 20h
0x140007717  movzx   r8d, ax
0x14000771b  mov     eax, [rbx+8Ch]
0x140007721  mov     rcx, [rcx+40h]
0x140007725  mov     [rsp+0A8h+var_68], rdx
0x14000772a  mov     [rsp+0A8h+var_70], eax
0x14000772e  mov     eax, [rbx+74h]
0x140007731  mov     dword ptr [rsp+0A8h+var_78], eax
0x140007735  mov     dword ptr [rsp+0A8h+var_80], r8d
0x14000773a  call    WPP_RECORDER_SF_DDd_guid_
0x14000773f  mov     rdx, r12
0x140007742  mov     rcx, rdi
0x140007745  call    IrpList_EnqueueEx
0x14000774a  mov     dl, [rbx+38h]; NewIrql
0x14000774d  mov     rcx, r15; SpinLock
0x140007750  mov     edi, eax
0x140007752  call    cs:__imp_KeReleaseSpinLock
0x140007759  nop     dword ptr [rax+rax+00h]
0x14000775e  test    edi, edi
0x140007760  js      short loc_140007779
0x140007762  mov     rcx, rbx
0x140007765  test    r14b, r14b
0x140007768  jz      short loc_140007771
0x14000776a  call    TdiConnectToPortWithPolicy
0x14000776f  jmp     short loc_140007779
0x140007771  mov     rdx, r12
0x140007774  call    TdiConnectToUuid
0x140007779  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140007780  jz      short loc_1400077A5
0x140007782  mov     rcx, cs:WPP_GLOBAL_Control
0x140007789  mov     r9d, 79h ; 'y'
0x14000778f  mov     dword ptr [rsp+0A8h+var_80], edi
0x140007793  mov     [rsp+0A8h+var_88], rbp
0x140007798  mov     rcx, [rcx+40h]
0x14000779c  lea     r8d, [r9-6Ah]
0x1400077a0  call    WPP_RECORDER_SF_d
0x1400077a5  mov     eax, edi
0x1400077a7  mov     rcx, [rsp+0A8h+var_48]
0x1400077ac  xor     rcx, rsp; StackCookie
0x1400077af  call    __security_check_cookie
0x1400077b4  add     rsp, 70h
0x1400077b8  pop     r15
0x1400077ba  pop     r14
0x1400077bc  pop     r12
0x1400077be  pop     rdi
0x1400077bf  pop     rsi
0x1400077c0  pop     rbp
0x1400077c1  pop     rbx
0x1400077c2  retn
```
