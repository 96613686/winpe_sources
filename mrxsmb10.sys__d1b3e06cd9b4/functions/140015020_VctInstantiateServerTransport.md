# VctInstantiateServerTransport

- ea: `0x140015020`
- end: `0x14001533c`
- name: `VctInstantiateServerTransport`
- size: `796`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140014abc`

## callees

- `0x140014abc`
- `0x140015020`
- `0x140040ea0`
- `0x140041324`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400150e4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400150e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001520f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001520f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015195`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015195`
- `ntoskrnl!ExAllocatePool2` at `0x14001509b`
- `ntoskrnl!ExAllocatePool2` at `0x140015113`
- `ntoskrnl!ExAllocatePool2` at `0x140015166`
- `ntoskrnl!ExAllocatePool2` at `0x14001509b`
- `ntoskrnl!ExAllocatePool2` at `0x140015113`
- `ntoskrnl!ExAllocatePool2` at `0x140015166`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152f8`
- `mrxsmb!SmbMmFreeServerTransport` at `0x1400152d1`
- `mrxsmb!SmbMmFreeServerTransport` at `0x1400152d1`
- `mrxsmb!RxCeEstablishConnectionNew` at `0x140015288`
- `mrxsmb!RxCeEstablishConnectionNew` at `0x140015288`
- `mrxsmb!MRxSmbDeviceObject` at `0x14001521f`

## pseudocode

```c
__int64 __fastcall VctInstantiateServerTransport(_QWORD *P)
{
  __int64 v1; // r15
  __int64 Pool2; // rax
  __int64 v4; // rbp
  __int64 v5; // rdi
  __int64 v6; // r13
  _QWORD *v7; // r14
  unsigned int v8; // eax
  __int64 v9; // rax
  PVOID *v10; // rsi
  unsigned int v11; // ebx
  __int64 v12; // rax
  KIRQL v13; // al
  __int64 v14; // r9
  KIRQL v15; // r10
  __int64 v16; // rdx
  __int64 v17; // rax
  UNICODE_STRING SourceString; // [rsp+90h] [rbp-58h] BYREF
  int v20; // [rsp+F0h] [rbp+8h] BYREF

  v1 = P[4];
  v20 = 0;
  SourceString = 0;
  SourceString.Buffer = (PWSTR)(*(_QWORD *)(v1 + 88) + 2LL);
  SourceString.Length = *(_WORD *)(v1 + 80) - 2;
  SourceString.MaximumLength = *(_WORD *)(v1 + 82) - 2;
  *(_DWORD *)(v1 + 428) = 0;
  Pool2 = ExAllocatePool2(64, SourceString.MaximumLength + 176LL, 1666608467);
  v4 = Pool2;
  if ( !Pool2 )
  {
    v11 = -1073741670;
LABEL_20:
    *((_DWORD *)P + 1) = 4;
    *(_DWORD *)P = v11;
    SmbCeConstructServerTransport(P);
    return 259;
  }
  v5 = 0;
  *(_QWORD *)(Pool2 + 160) = Pool2 + 168;
  v6 = Pool2 + 152;
  *(_WORD *)(Pool2 + 154) = SourceString.MaximumLength;
  RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 152), &SourceString);
  v7 = (_QWORD *)(v4 + 80);
  *(_QWORD *)(v4 + 120) = P;
  *(_QWORD *)(v4 + 88) = v4 + 80;
  v8 = VctComputeTransportAddressSize(&SourceString);
  *(_DWORD *)(v4 + 96) = v8;
  v9 = ExAllocatePool2(64, v8, 1666608467);
  v10 = (PVOID *)(v4 + 104);
  *(_QWORD *)(v4 + 104) = v9;
  if ( !v9 )
    goto LABEL_3;
  v11 = VctBuildTransportAddress(v9, *(unsigned int *)(v4 + 96), &SourceString, &v20);
  if ( !v11 )
  {
    v12 = ExAllocatePool2(66, 72, 1666608467);
    v5 = v12;
    if ( !v12 )
    {
LABEL_3:
      v11 = -1073741670;
LABEL_13:
      if ( *v10 )
      {
        ExFreePoolWithTag(*v10, 0);
        *v10 = 0;
      }
      if ( *v7 )
      {
        *(_DWORD *)(*v7 + 8LL) = 0;
        SmbMmFreeServerTransport(*v7);
      }
      ExFreePoolWithTag((PVOID)v4, 0);
      if ( v5 )
        ExFreePoolWithTag((PVOID)v5, 0);
      goto LABEL_20;
    }
    *(_DWORD *)v12 = 0;
    *(_DWORD *)(v12 + 16) = 0;
    *(_DWORD *)(v12 + 32) = *(_DWORD *)(v4 + 96);
    *(_QWORD *)(v12 + 40) = *v10;
    v13 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
    v14 = 0;
    v15 = v13;
    s_SmbCeDbSpinLockSavedIrql = v13;
    v16 = *(_QWORD *)(v1 + 168);
    if ( v16 != v1 + 168 )
      v14 = v16 - 32;
    if ( v14 )
    {
      *(_QWORD *)(v5 + 48) = *(_QWORD *)(v14 + 144);
      *(_DWORD *)(v5 + 56) = *(_DWORD *)(v14 + 160);
      v17 = *(_QWORD *)(v14 + 176);
    }
    else
    {
      *(_QWORD *)(v5 + 48) = *(_QWORD *)(v1 + 560);
      *(_DWORD *)(v5 + 56) = *(_DWORD *)(v1 + 576);
      v17 = *(_QWORD *)(v1 + 592);
    }
    *(_QWORD *)(v5 + 64) = v17;
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, v15);
    *(_QWORD *)(v4 + 72) = v5;
    v11 = RxCeEstablishConnectionNew(
            v6,
            v5,
            v4,
            VctpCreateConnectionCallback,
            MRxSmbVctConnectionEventHandler,
            v1,
            *(_QWORD *)(v1 + 336),
            0,
            0,
            0,
            0,
            0,
            MRxSmbDeviceObject,
            0,
            0,
            0,
            0);
  }
  if ( v11 != 259 )
    goto LABEL_13;
  return v11;
}

```

## disassembly

```asm
0x140015020  mov     r11, rsp
0x140015023  push    rbx
0x140015024  push    rbp
0x140015025  push    rsi
0x140015026  push    rdi
0x140015027  push    r12
0x140015029  push    r13
0x14001502b  push    r14
0x14001502d  push    r15
0x14001502f  sub     rsp, 0A8h
0x140015036  mov     r15, [rcx+20h]
0x14001503a  mov     r12, rcx
0x14001503d  mov     ecx, 2
0x140015042  mov     dword ptr [r11+8], 0
0x14001504a  xorps   xmm0, xmm0
0x14001504d  mov     ebx, 63566D53h
0x140015052  movups  xmmword ptr [r11-58h], xmm0
0x140015057  mov     rax, [r15+58h]
0x14001505b  mov     r8d, ebx
0x14001505e  add     rax, rcx
0x140015061  lea     esi, [rcx+3Eh]
0x140015064  mov     [r11-50h], rax
0x140015068  movzx   eax, word ptr [r15+50h]
0x14001506d  sub     ax, cx
0x140015070  mov     [r11-58h], ax
0x140015075  movzx   eax, word ptr [r15+52h]
0x14001507a  sub     ax, cx
0x14001507d  mov     ecx, esi
0x14001507f  mov     [r11-56h], ax
0x140015084  mov     dword ptr [r15+1ACh], 0
0x14001508f  movzx   edx, word ptr [r11-56h]
0x140015094  add     rdx, 0B0h
0x14001509b  call    cs:__imp_ExAllocatePool2
0x1400150a2  nop     dword ptr [rax+rax+00h]
0x1400150a7  mov     rbp, rax
0x1400150aa  test    rax, rax
0x1400150ad  jz      loc_140015306
0x1400150b3  lea     rcx, [rax+0A8h]
0x1400150ba  xor     edi, edi
0x1400150bc  mov     [rax+0A0h], rcx
0x1400150c3  lea     r13, [rax+98h]
0x1400150ca  movzx   ecx, [rsp+0E8h+SourceString.MaximumLength]
0x1400150d2  lea     rdx, [rsp+0E8h+SourceString]; SourceString
0x1400150da  mov     [rax+9Ah], cx
0x1400150e1  mov     rcx, r13; DestinationString
0x1400150e4  call    cs:__imp_RtlCopyUnicodeString
0x1400150eb  nop     dword ptr [rax+rax+00h]
0x1400150f0  lea     r14, [rbp+50h]
0x1400150f4  mov     [rbp+78h], r12
0x1400150f8  lea     rcx, [rsp+0E8h+SourceString]
0x140015100  mov     [rbp+58h], r14
0x140015104  call    VctComputeTransportAddressSize
0x140015109  mov     edx, eax
0x14001510b  mov     r8d, ebx
0x14001510e  mov     ecx, esi
0x140015110  mov     [rbp+60h], edx
0x140015113  call    cs:__imp_ExAllocatePool2
0x14001511a  nop     dword ptr [rax+rax+00h]
0x14001511f  lea     rsi, [rbp+68h]
0x140015123  mov     [rsi], rax
0x140015126  test    rax, rax
0x140015129  jnz     short loc_140015135
0x14001512b  mov     ebx, 0C000009Ah
0x140015130  jmp     loc_1400152A2
0x140015135  mov     edx, [rbp+60h]
0x140015138  lea     r9, [rsp+0E8h+arg_0]
0x140015140  lea     r8, [rsp+0E8h+SourceString]
0x140015148  mov     rcx, rax
0x14001514b  call    VctBuildTransportAddress
0x140015150  mov     ebx, eax
0x140015152  test    eax, eax
0x140015154  jnz     loc_140015296
0x14001515a  lea     edx, [rax+48h]
0x14001515d  mov     r8d, 63566D53h
0x140015163  lea     ecx, [rax+42h]
0x140015166  call    cs:__imp_ExAllocatePool2
0x14001516d  nop     dword ptr [rax+rax+00h]
0x140015172  xor     ebx, ebx
0x140015174  mov     rdi, rax
0x140015177  test    rax, rax
0x14001517a  jz      short loc_14001512B
0x14001517c  mov     [rax], ebx
0x14001517e  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140015185  mov     [rax+10h], ebx
0x140015188  mov     eax, [rbp+60h]
0x14001518b  mov     [rdi+20h], eax
0x14001518e  mov     rax, [rsi]
0x140015191  mov     [rdi+28h], rax
0x140015195  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001519c  nop     dword ptr [rax+rax+00h]
0x1400151a1  lea     r8, [r15+0A8h]
0x1400151a8  mov     r9d, ebx
0x1400151ab  mov     r10b, al
0x1400151ae  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x1400151b4  mov     rdx, [r8]
0x1400151b7  cmp     rdx, r8
0x1400151ba  lea     rcx, [rdx-20h]
0x1400151be  cmovnz  r9, rcx
0x1400151c2  test    r9, r9
0x1400151c5  jz      short loc_1400151E5
0x1400151c7  mov     rax, [r9+90h]
0x1400151ce  mov     [rdi+30h], rax
0x1400151d2  mov     eax, [r9+0A0h]
0x1400151d9  mov     [rdi+38h], eax
0x1400151dc  mov     rax, [r9+0B0h]
0x1400151e3  jmp     short loc_140015201
0x1400151e5  mov     rax, [r15+230h]
0x1400151ec  mov     [rdi+30h], rax
0x1400151f0  mov     eax, [r15+240h]
0x1400151f7  mov     [rdi+38h], eax
0x1400151fa  mov     rax, [r15+250h]
0x140015201  mov     dl, r10b; NewIrql
0x140015204  mov     [rdi+40h], rax
0x140015208  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14001520f  call    cs:__imp_KeReleaseSpinLock
0x140015216  nop     dword ptr [rax+rax+00h]
0x14001521b  mov     [rbp+48h], rdi
0x14001521f  mov     rax, cs:__imp_MRxSmbDeviceObject
0x140015226  lea     r9, VctpCreateConnectionCallback
0x14001522d  mov     [rsp+0E8h+var_68], rbx
0x140015235  mov     r8, rbp
0x140015238  mov     [rsp+0E8h+var_70], rbx
0x14001523d  mov     rcx, r13
0x140015240  mov     [rsp+0E8h+var_78], rbx
0x140015245  mov     rdx, [rax]
0x140015248  mov     rax, [r15+150h]
0x14001524f  mov     [rsp+0E8h+var_80], rbx
0x140015254  mov     [rsp+0E8h+var_88], rdx
0x140015259  mov     rdx, rdi
0x14001525c  mov     [rsp+0E8h+var_90], ebx
0x140015260  mov     [rsp+0E8h+var_98], bl
0x140015264  mov     [rsp+0E8h+var_A0], bl
0x140015268  mov     [rsp+0E8h+var_A8], rbx
0x14001526d  mov     [rsp+0E8h+var_B0], rbx
0x140015272  mov     [rsp+0E8h+var_B8], rax
0x140015277  lea     rax, MRxSmbVctConnectionEventHandler
0x14001527e  mov     [rsp+0E8h+var_C0], r15
0x140015283  mov     [rsp+0E8h+var_C8], rax
0x140015288  call    cs:__imp_RxCeEstablishConnectionNew
0x14001528f  nop     dword ptr [rax+rax+00h]
0x140015294  mov     ebx, eax
0x140015296  cmp     ebx, 103h
0x14001529c  jz      loc_140015325
0x1400152a2  mov     rcx, [rsi]; P
0x1400152a5  test    rcx, rcx
0x1400152a8  jz      short loc_1400152BF
0x1400152aa  xor     edx, edx; Tag
0x1400152ac  call    cs:__imp_ExFreePoolWithTag
0x1400152b3  nop     dword ptr [rax+rax+00h]
0x1400152b8  mov     qword ptr [rsi], 0
0x1400152bf  mov     rax, [r14]
0x1400152c2  test    rax, rax
0x1400152c5  jz      short loc_1400152DD
0x1400152c7  mov     dword ptr [rax+8], 0
0x1400152ce  mov     rcx, [r14]
0x1400152d1  call    cs:__imp_SmbMmFreeServerTransport
0x1400152d8  nop     dword ptr [rax+rax+00h]
0x1400152dd  xor     edx, edx; Tag
0x1400152df  mov     rcx, rbp; P
0x1400152e2  call    cs:__imp_ExFreePoolWithTag
0x1400152e9  nop     dword ptr [rax+rax+00h]
0x1400152ee  test    rdi, rdi
0x1400152f1  jz      short loc_14001530B
0x1400152f3  xor     edx, edx; Tag
0x1400152f5  mov     rcx, rdi; P
0x1400152f8  call    cs:__imp_ExFreePoolWithTag
0x1400152ff  nop     dword ptr [rax+rax+00h]
0x140015304  jmp     short loc_14001530B
0x140015306  mov     ebx, 0C000009Ah
0x14001530b  mov     rcx, r12; P
0x14001530e  mov     dword ptr [r12+4], 4
0x140015317  mov     [r12], ebx
0x14001531b  call    SmbCeConstructServerTransport
0x140015320  mov     ebx, 103h
0x140015325  mov     eax, ebx
0x140015327  add     rsp, 0A8h
0x14001532e  pop     r15
0x140015330  pop     r14
0x140015332  pop     r13
0x140015334  pop     r12
0x140015336  pop     rdi
0x140015337  pop     rsi
0x140015338  pop     rbp
0x140015339  pop     rbx
0x14001533a  retn
```
