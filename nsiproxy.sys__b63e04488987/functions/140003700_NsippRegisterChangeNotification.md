# NsippRegisterChangeNotification

- ea: `0x140003700`
- end: `0x140003ae2`
- name: `NsippRegisterChangeNotification`
- size: `994`
- prototype: `__int64 __fastcall(void *Src, unsigned int, char, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x140003700`
- `0x1400056e8`
- `0x140006560`
- `0x140006980`
- `0x14000d0f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400039d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400039d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003a0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003a36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003a0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003a36`
- `ntoskrnl!ExAllocatePool2` at `0x14000383b`
- `ntoskrnl!ExAllocatePool2` at `0x140003919`
- `ntoskrnl!ExAllocatePool2` at `0x14000383b`
- `ntoskrnl!ExAllocatePool2` at `0x140003919`
- `ntoskrnl!IoIs32bitProcess` at `0x140003739`
- `ntoskrnl!IoIs32bitProcess` at `0x140003739`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ab7`
- `NETIO!NsiRegisterChangeNotificationEx` at `0x14000397f`
- `NETIO!NsiRegisterChangeNotificationEx` at `0x14000397f`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140003a66`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140003a66`

## pseudocode

```c
__int64 __fastcall NsippRegisterChangeNotification(void *Src, unsigned int a2, char a3, __int64 a4, _QWORD *a5)
{
  BOOLEAN v9; // al
  void *v10; // r15
  _QWORD *v11; // r12
  _QWORD *v12; // rsi
  _QWORD *Pool2; // rax
  _QWORD *v14; // rbx
  int v15; // edi
  char *v16; // rdi
  char *v17; // rcx
  char *v18; // rax
  __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  KIRQL v23; // al
  _QWORD *v24; // rcx
  void *v26[2]; // [rsp+20h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+30h] [rbp-B8h]
  __int64 v28; // [rsp+40h] [rbp-A8h]
  char *v29; // [rsp+48h] [rbp-A0h]
  __int64 v30; // [rsp+50h] [rbp-98h]
  void *v31; // [rsp+58h] [rbp-90h]
  _BYTE Srca[72]; // [rsp+60h] [rbp-88h] BYREF

  memset(Srca, 0, 0x44u);
  v9 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( v9 )
  {
    if ( a2 >= 0x28 )
    {
      *(_OWORD *)v26 = 0;
      v27 = 0;
      v28 = 0;
      if ( a3 )
        RtlCopyFromUser(v26, Src, 0x28u);
      else
        RtlCopyVolatileMemory(v26, Src, 0x28u);
      v10 = (void *)HIDWORD(v26[0]);
      *(_QWORD *)&Srca[8] = HIDWORD(v26[0]);
      *(_DWORD *)Srca = v26[0];
      *(_DWORD *)&Srca[16] = v26[1];
      *(_QWORD *)&Srca[24] = HIDWORD(v26[1]);
      Srca[32] = v27;
      *(_QWORD *)&Srca[40] = DWORD1(v27);
      *(_QWORD *)&Srca[48] = *((_QWORD *)&v27 + 1);
      v11 = (_QWORD *)HIDWORD(v28);
      *(_QWORD *)&Srca[64] = HIDWORD(v28);
      goto LABEL_13;
    }
    return 3221225485LL;
  }
  if ( a2 < 0x48 )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(Srca, Src, 0x48u);
  else
    RtlCopyVolatileMemory(Srca, Src, 0x48u);
  v11 = *(_QWORD **)&Srca[64];
  v10 = *(void **)&Srca[8];
LABEL_13:
  v12 = 0;
  v30 = 0;
  Pool2 = (_QWORD *)ExAllocatePool2(65, 104, 1735414606);
  v14 = Pool2;
  v31 = Pool2;
  if ( Pool2 )
  {
    v29 = (char *)Pool2;
    RtlCopyVolatileMemory(Pool2, Srca, 0x48u);
    v16 = (char *)(v14 + 9);
    v17 = (char *)(v14 + 9);
    v29 = (char *)(v14 + 9);
    if ( v10 )
    {
      if ( a3 )
        RtlCopyFromUser(v17, v10, 0x18u);
      else
        RtlCopyVolatileMemory(v17, v10, 0x18u);
      v17 = (char *)(v14 + 12);
      v29 = (char *)(v14 + 12);
    }
    else
    {
      v16 = 0;
    }
    v14[1] = v16;
    if ( v11 )
    {
      v18 = v17;
      v29 = v17 + 8;
    }
    else
    {
      v18 = 0;
    }
    v14[8] = v18;
    if ( a3 == 1 && v14[3] )
    {
      v15 = -1073741811;
    }
    else if ( a3 || v14[3] )
    {
      v19 = *(_QWORD *)(*(_QWORD *)(a4 + 48) + 24LL);
      v20 = ExAllocatePool2(65, 80, 1668305742);
      v12 = (_QWORD *)v20;
      v30 = v20;
      if ( v20 )
      {
        *(_QWORD *)(v20 + 8) = v20;
        *(_QWORD *)v20 = v20;
        *(_DWORD *)(v20 + 16) = 0;
        *(_OWORD *)(v20 + 24) = *(_OWORD *)v14;
        *(_QWORD *)(v20 + 40) = v14[2];
        if ( v10 )
        {
          v21 = v20 + 56;
          *(_QWORD *)(v20 + 32) = v20 + 56;
          v22 = v14[1];
          *(_OWORD *)v21 = *(_OWORD *)v22;
          *(_QWORD *)(v21 + 16) = *(_QWORD *)(v22 + 16);
        }
        v15 = NsiRegisterChangeNotificationEx(v14);
        if ( v15 >= 0 )
        {
          if ( v11 )
          {
            if ( a3 )
              RtlWriteULong64ToUser(v11, v12);
            else
              *v11 = *(_QWORD *)v14[8];
          }
          *a5 = 72;
          v12[6] = *(_QWORD *)v14[8];
          v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v19 + 24));
          if ( *(_BYTE *)(v19 + 16) )
          {
            *(_OWORD *)v26 = 0;
            v27 = 0;
            LODWORD(v28) = 0;
            KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 24), v23);
            *(_OWORD *)v26 = *(_OWORD *)v14;
            *(_QWORD *)&v27 = v14[2];
            *((_QWORD *)&v27 + 1) = *(_QWORD *)v14[8];
            NsiDeregisterChangeNotificationEx(v26);
            v15 = -1073741738;
          }
          else
          {
            v24 = *(_QWORD **)(v19 + 8);
            if ( *v24 != v19 )
              __fastfail(3u);
            *v12 = v19;
            v12[1] = v24;
            *v24 = v12;
            *(_QWORD *)(v19 + 8) = v12;
            KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 24), v23);
          }
        }
        if ( v15 >= 0 )
          goto LABEL_47;
      }
      else
      {
        v15 = -1073741670;
      }
    }
    else
    {
      v15 = -1073741811;
    }
  }
  else
  {
    v15 = -1073741670;
  }
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
LABEL_47:
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140003700  push    rbx
0x140003702  push    rsi
0x140003703  push    rdi
0x140003704  push    r12
0x140003706  push    r13
0x140003708  push    r14
0x14000370a  push    r15
0x14000370c  sub     rsp, 0B0h
0x140003713  mov     r13, r9
0x140003716  movzx   r14d, r8b
0x14000371a  mov     edi, edx
0x14000371c  mov     rbx, rcx
0x14000371f  xor     eax, eax
0x140003721  mov     [rsp+0E8h+var_84], eax
0x140003725  xor     edx, edx; Val
0x140003727  mov     r8d, 44h ; 'D'; Size
0x14000372d  lea     rcx, [rsp+0E8h+Src]; void *
0x140003732  call    memset
0x140003737  xor     ecx, ecx; Irp
0x140003739  call    cs:__imp_IoIs32bitProcess
0x140003740  nop     dword ptr [rax+rax+00h]
0x140003745  test    rbx, rbx
0x140003748  jz      loc_140003AC9
0x14000374e  test    al, al
0x140003750  jz      loc_1400037EF
0x140003756  cmp     edi, 28h ; '('
0x140003759  jb      loc_140003AC9
0x14000375f  xorps   xmm0, xmm0
0x140003762  xor     eax, eax
0x140003764  movups  xmmword ptr [rsp+0E8h+var_C8], xmm0
0x140003769  movups  [rsp+0E8h+var_B8], xmm0
0x14000376e  mov     [rsp+0E8h+var_A8], rax
0x140003773  mov     r8d, 28h ; '('; Size
0x140003779  mov     rdx, rbx; Src
0x14000377c  lea     rcx, [rsp+0E8h+var_C8]; void *
0x140003781  test    r14b, r14b
0x140003784  jz      short loc_14000378D
0x140003786  call    RtlCopyFromUser
0x14000378b  jmp     short loc_140003793
0x14000378d  call    RtlCopyVolatileMemory
0x140003792  nop
0x140003793  mov     r15d, dword ptr [rsp+0E8h+var_C8+4]
0x140003798  mov     [rsp+0E8h+var_80], r15
0x14000379d  mov     eax, dword ptr [rsp+0E8h+var_C8]
0x1400037a1  mov     [rsp+0E8h+Src], eax
0x1400037a5  mov     eax, dword ptr [rsp+0E8h+var_C8+8]
0x1400037a9  mov     [rsp+0E8h+var_78], eax
0x1400037ad  mov     eax, dword ptr [rsp+0E8h+var_C8+0Ch]
0x1400037b1  mov     [rsp+0E8h+var_70], rax
0x1400037b6  movzx   eax, byte ptr [rsp+0E8h+var_B8]
0x1400037bb  mov     [rsp+0E8h+var_68], al
0x1400037c2  mov     eax, dword ptr [rsp+0E8h+var_B8+4]
0x1400037c6  mov     [rsp+0E8h+var_60], rax
0x1400037ce  mov     rax, qword ptr [rsp+0E8h+var_B8+8]
0x1400037d3  mov     [rsp+0E8h+var_58], rax
0x1400037db  mov     r12d, dword ptr [rsp+0E8h+var_A8+4]
0x1400037e0  mov     [rsp+0E8h+var_48], r12
0x1400037e8  jmp     short loc_140003824
0x1400037ea  jmp     loc_140003ACE
0x1400037ef  cmp     edi, 48h ; 'H'
0x1400037f2  jb      loc_140003AC9
0x1400037f8  mov     r8d, 48h ; 'H'; Size
0x1400037fe  mov     rdx, rbx; Src
0x140003801  lea     rcx, [rsp+0E8h+Src]; void *
0x140003806  test    r14b, r14b
0x140003809  jz      short loc_140003812
0x14000380b  call    RtlCopyFromUser
0x140003810  jmp     short loc_140003817
0x140003812  call    RtlCopyVolatileMemory
0x140003817  mov     r12, [rsp+0E8h+var_48]
0x14000381f  mov     r15, [rsp+0E8h+var_80]
0x140003824  xor     esi, esi
0x140003826  mov     [rsp+0E8h+var_98], rsi
0x14000382b  mov     edx, 68h ; 'h'
0x140003830  mov     ecx, 41h ; 'A'
0x140003835  mov     r8d, 6770534Eh
0x14000383b  call    cs:__imp_ExAllocatePool2
0x140003842  nop     dword ptr [rax+rax+00h]
0x140003847  mov     rbx, rax
0x14000384a  mov     [rsp+0E8h+var_90], rax
0x14000384f  test    rax, rax
0x140003852  jnz     short loc_14000385E
0x140003854  mov     edi, 0C000009Ah
0x140003859  jmp     loc_140003A97
0x14000385e  mov     [rsp+0E8h+var_A0], rbx
0x140003863  mov     r8d, 48h ; 'H'; Size
0x140003869  lea     rdx, [rsp+0E8h+Src]; Src
0x14000386e  mov     rcx, rbx; void *
0x140003871  call    RtlCopyVolatileMemory
0x140003876  lea     rdi, [rbx+48h]
0x14000387a  mov     rcx, rdi; void *
0x14000387d  mov     [rsp+0E8h+var_A0], rcx
0x140003882  test    r15, r15
0x140003885  jz      short loc_1400038B5
0x140003887  mov     r8d, 18h; Size
0x14000388d  mov     rdx, r15; Src
0x140003890  test    r14b, r14b
0x140003893  jz      short loc_1400038A5
0x140003895  call    RtlCopyFromUser
0x14000389a  lea     rcx, [rdi+18h]
0x14000389e  mov     [rsp+0E8h+var_A0], rcx
0x1400038a3  jmp     short loc_1400038B7
0x1400038a5  call    RtlCopyVolatileMemory
0x1400038aa  lea     rcx, [rdi+18h]
0x1400038ae  mov     [rsp+0E8h+var_A0], rcx
0x1400038b3  jmp     short loc_1400038B7
0x1400038b5  xor     edi, edi
0x1400038b7  mov     [rbx+8], rdi
0x1400038bb  test    r12, r12
0x1400038be  jz      short loc_1400038CE
0x1400038c0  mov     rax, rcx
0x1400038c3  add     rcx, 8
0x1400038c7  mov     [rsp+0E8h+var_A0], rcx
0x1400038cc  jmp     short loc_1400038D0
0x1400038ce  xor     eax, eax
0x1400038d0  mov     [rbx+40h], rax
0x1400038d4  cmp     r14b, 1
0x1400038d8  jnz     short loc_1400038EB
0x1400038da  cmp     qword ptr [rbx+18h], 0
0x1400038df  jz      short loc_1400038EB
0x1400038e1  mov     edi, 0C000000Dh
0x1400038e6  jmp     loc_140003A97
0x1400038eb  test    r14b, r14b
0x1400038ee  jnz     short loc_140003901
0x1400038f0  cmp     qword ptr [rbx+18h], 0
0x1400038f5  jnz     short loc_140003901
0x1400038f7  mov     edi, 0C000000Dh
0x1400038fc  jmp     loc_140003A97
0x140003901  mov     rax, [r13+30h]
0x140003905  mov     r13, [rax+18h]
0x140003909  mov     edx, 50h ; 'P'
0x14000390e  mov     ecx, 41h ; 'A'
0x140003913  mov     r8d, 6370534Eh
0x140003919  call    cs:__imp_ExAllocatePool2
0x140003920  nop     dword ptr [rax+rax+00h]
0x140003925  mov     rsi, rax
0x140003928  mov     [rsp+0E8h+var_98], rax
0x14000392d  test    rax, rax
0x140003930  jnz     short loc_14000393C
0x140003932  mov     edi, 0C000009Ah
0x140003937  jmp     loc_140003A97
0x14000393c  mov     [rax+8], rsi
0x140003940  mov     [rax], rsi
0x140003943  mov     dword ptr [rax+10h], 0
0x14000394a  movups  xmm0, xmmword ptr [rbx]
0x14000394d  movups  xmmword ptr [rax+18h], xmm0
0x140003951  movsd   xmm1, qword ptr [rbx+10h]
0x140003956  movsd   qword ptr [rax+28h], xmm1
0x14000395b  test    r15, r15
0x14000395e  jz      short loc_14000397C
0x140003960  lea     rcx, [rax+38h]
0x140003964  mov     [rax+20h], rcx
0x140003968  mov     rax, [rbx+8]
0x14000396c  movups  xmm0, xmmword ptr [rax]
0x14000396f  movups  xmmword ptr [rcx], xmm0
0x140003972  movsd   xmm1, qword ptr [rax+10h]
0x140003977  movsd   qword ptr [rcx+10h], xmm1
0x14000397c  mov     rcx, rbx
0x14000397f  call    cs:__imp_NsiRegisterChangeNotificationEx
0x140003986  nop     dword ptr [rax+rax+00h]
0x14000398b  mov     edi, eax
0x14000398d  test    eax, eax
0x14000398f  js      loc_140003A93
0x140003995  test    r12, r12
0x140003998  jz      short loc_1400039B8
0x14000399a  test    r14b, r14b
0x14000399d  jnz     short loc_1400039AC
0x14000399f  mov     rax, [rbx+40h]
0x1400039a3  mov     rcx, [rax]
0x1400039a6  mov     [r12], rcx
0x1400039aa  jmp     short loc_1400039B8
0x1400039ac  mov     rdx, rsi
0x1400039af  mov     rcx, r12
0x1400039b2  call    RtlWriteULong64ToUser
0x1400039b7  nop
0x1400039b8  mov     rax, [rsp+0E8h+arg_20]
0x1400039c0  mov     qword ptr [rax], 48h ; 'H'
0x1400039c7  mov     rax, [rbx+40h]
0x1400039cb  mov     rcx, [rax]
0x1400039ce  mov     [rsi+30h], rcx
0x1400039d2  lea     rcx, [r13+18h]; SpinLock
0x1400039d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400039dd  nop     dword ptr [rax+rax+00h]
0x1400039e2  cmp     byte ptr [r13+10h], 0
0x1400039e7  jnz     short loc_140003A1C
0x1400039e9  mov     rcx, [r13+8]
0x1400039ed  cmp     [rcx], r13
0x1400039f0  jz      short loc_1400039F9
0x1400039f2  mov     ecx, 3
0x1400039f7  int     29h; Win8: RtlFailFast(ecx)
0x1400039f9  mov     [rsi], r13
0x1400039fc  mov     [rsi+8], rcx
0x140003a00  mov     [rcx], rsi
0x140003a03  mov     [r13+8], rsi
0x140003a07  movzx   edx, al; NewIrql
0x140003a0a  lea     rcx, [r13+18h]; SpinLock
0x140003a0e  call    cs:__imp_KeReleaseSpinLock
0x140003a15  nop     dword ptr [rax+rax+00h]
0x140003a1a  jmp     short loc_140003A93
0x140003a1c  xor     ecx, ecx
0x140003a1e  xorps   xmm0, xmm0
0x140003a21  movups  xmmword ptr [rsp+0E8h+var_C8], xmm0
0x140003a26  movups  [rsp+0E8h+var_B8], xmm0
0x140003a2b  mov     dword ptr [rsp+0E8h+var_A8], ecx
0x140003a2f  movzx   edx, al; NewIrql
0x140003a32  lea     rcx, [r13+18h]; SpinLock
0x140003a36  call    cs:__imp_KeReleaseSpinLock
0x140003a3d  nop     dword ptr [rax+rax+00h]
0x140003a42  movups  xmm0, xmmword ptr [rbx]
0x140003a45  movups  xmmword ptr [rsp+0E8h+var_C8], xmm0
0x140003a4a  movsd   xmm1, qword ptr [rbx+10h]
0x140003a4f  movsd   qword ptr [rsp+0E8h+var_B8], xmm1
0x140003a55  mov     rax, [rbx+40h]
0x140003a59  mov     rcx, [rax]
0x140003a5c  mov     qword ptr [rsp+0E8h+var_B8+8], rcx
0x140003a61  lea     rcx, [rsp+0E8h+var_C8]
0x140003a66  call    cs:__imp_NsiDeregisterChangeNotificationEx
0x140003a6d  nop     dword ptr [rax+rax+00h]
0x140003a72  mov     edi, 0C0000056h
0x140003a77  jmp     short loc_140003A93
0x140003a79  mov     edi, eax
0x140003a7b  mov     rsi, [rsp+0E8h+var_98]
0x140003a80  mov     rbx, [rsp+0E8h+var_90]
0x140003a85  jmp     short loc_140003A93
0x140003a87  mov     edi, eax
0x140003a89  mov     rsi, [rsp+0E8h+var_98]
0x140003a8e  mov     rbx, [rsp+0E8h+var_90]
0x140003a93  test    edi, edi
0x140003a95  jns     short loc_140003AAD
0x140003a97  test    rsi, rsi
0x140003a9a  jz      short loc_140003AAD
0x140003a9c  xor     edx, edx; Tag
0x140003a9e  mov     rcx, rsi; P
0x140003aa1  call    cs:__imp_ExFreePoolWithTag
0x140003aa8  nop     dword ptr [rax+rax+00h]
0x140003aad  test    rbx, rbx
0x140003ab0  jz      short loc_140003AC3
0x140003ab2  xor     edx, edx; Tag
0x140003ab4  mov     rcx, rbx; P
0x140003ab7  call    cs:__imp_ExFreePoolWithTag
0x140003abe  nop     dword ptr [rax+rax+00h]
0x140003ac3  mov     eax, edi
0x140003ac5  jmp     short loc_140003ACE
0x140003ac7  jmp     short loc_140003ACE
0x140003ac9  mov     eax, 0C000000Dh
0x140003ace  add     rsp, 0B0h
0x140003ad5  pop     r15
0x140003ad7  pop     r14
0x140003ad9  pop     r13
0x140003adb  pop     r12
0x140003add  pop     rdi
0x140003ade  pop     rsi
0x140003adf  pop     rbx
0x140003ae0  retn
```
