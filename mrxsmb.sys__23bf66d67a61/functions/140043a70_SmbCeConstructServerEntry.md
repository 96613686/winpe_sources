# SmbCeConstructServerEntry

- ea: `0x140043a70`
- end: `0x140043e06`
- name: `SmbCeConstructServerEntry`
- size: `918`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140092b0c`

## callees

- `0x140003480`
- `0x14001c230`
- `0x140026464`
- `0x140026d60`
- `0x1400377dc`
- `0x14003838c`
- `0x140043a70`
- `0x1400447fc`
- `0x140059dc0`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!PsReferenceSiloContext` at `0x140043c89`
- `ntoskrnl!PsReferenceSiloContext` at `0x140043c89`
- `ntoskrnl!ExUuidCreate` at `0x140043c4c`
- `ntoskrnl!ExUuidCreate` at `0x140043c4c`
- `ntoskrnl!KeResetEvent` at `0x140043d70`
- `ntoskrnl!KeResetEvent` at `0x140043d70`
- `ntoskrnl!RtlHashUnicodeString` at `0x140043bab`
- `ntoskrnl!RtlHashUnicodeString` at `0x140043bab`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140043d44`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140043d44`
- `ntoskrnl!ExAllocatePool2` at `0x140043b17`
- `ntoskrnl!ExAllocatePool2` at `0x140043b17`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140043d90`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140043d90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043db6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043db6`
- `rdbss!RxInitializeDiagnosticLogger` at `0x140043ae3`
- `rdbss!RxInitializeDiagnosticLogger` at `0x140043ae3`

## pseudocode

```c
__int64 __fastcall SmbCeConstructServerEntry(__int64 a1, __int64 a2, __int64 *a3)
{
  struct _KEVENT *v3; // r15
  const void **v5; // rbx
  __int64 Object; // rax
  __int64 v8; // rdi
  unsigned int v9; // r14d
  __int64 Pool2; // rax
  void *v11; // rcx
  UUID *v12; // rsi
  __int16 v13; // ax
  unsigned __int16 v14; // cx
  _WORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rax
  char v19; // cl
  char v20; // cl
  __int64 v21; // rdx
  __int64 v22; // r8
  KIRQL v23; // bl
  void *v24; // rcx
  ULONG HashValue; // [rsp+20h] [rbp-30h] BYREF
  int v27; // [rsp+24h] [rbp-2Ch] BYREF
  __int64 *v28; // [rsp+28h] [rbp-28h]
  UUID Uuid; // [rsp+30h] [rbp-20h] BYREF

  v3 = *(struct _KEVENT **)(a2 + 48);
  v5 = *(const void ***)(a2 + 64);
  v28 = a3;
  HashValue = 0;
  v27 = 0;
  Object = SmbMmAllocateObjectEx(0, 0, v3);
  v8 = Object;
  if ( !Object )
    return (unsigned int)-1073741670;
  *(_QWORD *)(Object + 16) = RxInitializeDiagnosticLogger(Object, 4096, (unsigned int)SmbCeTraceFlags);
  *(_QWORD *)(v8 + 192) = off_140061628;
  Pool2 = ExAllocatePool2(64, *(unsigned __int16 *)v5 + 2LL, 1834186323);
  *(_QWORD *)(v8 + 88) = Pool2;
  v11 = (void *)Pool2;
  v12 = (UUID *)(v8 + 80);
  if ( !Pool2 )
  {
    v9 = -1073741670;
LABEL_25:
    v24 = *(void **)(v8 + 88);
    if ( v24 )
    {
      ExFreePoolWithTag(v24, 0x6D537653u);
      *(_QWORD *)(v8 + 88) = 0;
    }
    *(_QWORD *)(v8 + 88) = 0;
    v12->Data1 = 0;
    SmbMmFreeObjectPool(v8);
    return v9;
  }
  v13 = *(_WORD *)v5;
  LOWORD(v12->Data1) = *(_WORD *)v5;
  *(_WORD *)(v8 + 82) = v13 + 2;
  memmove(v11, v5[1], *(unsigned __int16 *)v5);
  *(UUID *)(v8 + 128) = *v12;
  v14 = *(_WORD *)(v8 + 128);
  if ( v14 >= 2u )
  {
    v15 = *(_WORD **)(v8 + 136);
    if ( *v15 == 92 )
    {
      *(_QWORD *)(v8 + 136) = v15 + 1;
      *(_WORD *)(v8 + 130) -= 2;
      *(_WORD *)(v8 + 128) = v14 - 2;
    }
  }
  v9 = RtlHashUnicodeString((PCUNICODE_STRING)(v8 + 80), 1u, 0, &HashValue);
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_948a51171ac53989b14c3e6a960354da_Traceguids, v9);
    }
    goto LABEL_25;
  }
  *(_DWORD *)(v8 + 72) = HashValue;
  if ( !byte_14007D240
    || (Uuid = *v12, v9 = SmbCeRetrieveIpFromRegistryWithSubdomains(&Uuid, v16, v8 + 880, &v27), v9 != -1073741670) )
  {
    Uuid = 0;
    if ( ExUuidCreate(&Uuid) < 0 )
    {
      *(_QWORD *)&Uuid.Data1 = MEMORY[0xFFFFF78000000320];
      *(_QWORD *)Uuid.Data4 = v8;
    }
    *(UUID *)(v8 + 684) = Uuid;
    v17 = *(_QWORD *)(a2 + 88);
    if ( v17 )
    {
      PsReferenceSiloContext(*(_QWORD *)(a2 + 88));
      *(_QWORD *)(v8 + 520) = v17;
    }
    *(_DWORD *)(v8 + 704) = 4096;
    *(_DWORD *)(v8 + 708) = 4096;
    *(_DWORD *)(v8 + 712) = 4096;
    v18 = *(_QWORD *)(v8 + 24);
    *(_OWORD *)(v8 + 764) = *(_OWORD *)(v18 + 2368);
    *(_OWORD *)(v8 + 780) = *(_OWORD *)(v18 + 2384);
    LODWORD(v18) = *(_DWORD *)(v18 + 2400);
    *(_BYTE *)(v8 + 737) &= 0xF0u;
    *(_BYTE *)(v8 + 736) &= 0x80u;
    v19 = *(_BYTE *)(v8 + 737);
    *(_DWORD *)(v8 + 836) = 0;
    *(_DWORD *)(v8 + 796) = v18;
    *(_QWORD *)(v8 + 1008) = 0;
    if ( *(_WORD *)(a2 + 144) < *(_WORD *)(a2 + 146) )
    {
      v20 = v19 | 0x10;
      *(_BYTE *)(v8 + 737) = v20;
      if ( (*(_BYTE *)(a1 + 750) & 0x20) != 0 )
        *(_BYTE *)(v8 + 737) = v20 | 0x20;
      Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck();
      *(_BYTE *)(v8 + 764) |= 0x40u;
    }
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)(v8 + 512));
    *(_QWORD *)(v8 + 144) = 0;
    v23 = SmbCeAcquireSpinLock(v3, v21, v22);
    SmbCeAddServerEntryLite(v8);
    KeResetEvent(v3 + 55);
    v3[98].Header.LockNV = -1;
    ExReleaseSpinLockExclusive(&v3[80].Header.Lock, v23);
    *v28 = v8;
  }
  if ( v9 )
    goto LABEL_25;
  return v9;
}

```

## disassembly

```asm
0x140043a70  mov     [rsp-38h+arg_0], rbx
0x140043a75  push    rbp
0x140043a76  push    rsi
0x140043a77  push    rdi
0x140043a78  push    r12
0x140043a7a  push    r13
0x140043a7c  push    r14
0x140043a7e  push    r15
0x140043a80  mov     rbp, rsp
0x140043a83  sub     rsp, 50h
0x140043a87  mov     rax, cs:__security_cookie
0x140043a8e  xor     rax, rsp
0x140043a91  mov     [rbp+var_10], rax
0x140043a95  mov     r15, [rdx+30h]
0x140043a99  mov     r13, rdx
0x140043a9c  mov     rbx, [rdx+40h]
0x140043aa0  mov     r12, rcx
0x140043aa3  mov     [rbp+var_28], r8
0x140043aa7  xor     edx, edx
0x140043aa9  mov     r8, r15
0x140043aac  mov     [rbp+HashValue], 0
0x140043ab3  xor     ecx, ecx
0x140043ab5  mov     [rbp+var_2C], 0
0x140043abc  call    SmbMmAllocateObjectEx
0x140043ac1  mov     rdi, rax
0x140043ac4  test    rax, rax
0x140043ac7  jnz     short loc_140043AD4
0x140043ac9  mov     r14d, 0C000009Ah
0x140043acf  jmp     loc_140043DDE
0x140043ad4  mov     r8d, cs:SmbCeTraceFlags
0x140043adb  mov     edx, 1000h
0x140043ae0  mov     rcx, rdi
0x140043ae3  call    cs:__imp_RxInitializeDiagnosticLogger
0x140043aea  nop     dword ptr [rax+rax+00h]
0x140043aef  mov     [rdi+10h], rax
0x140043af3  mov     r14d, 2
0x140043af9  lea     rax, off_140061628
0x140043b00  mov     r8d, 6D537653h
0x140043b06  mov     [rdi+0C0h], rax
0x140043b0d  movzx   edx, word ptr [rbx]
0x140043b10  add     rdx, r14
0x140043b13  lea     ecx, [r14+3Eh]
0x140043b17  call    cs:__imp_ExAllocatePool2
0x140043b1e  nop     dword ptr [rax+rax+00h]
0x140043b23  mov     [rdi+58h], rax
0x140043b27  mov     rcx, rax; void *
0x140043b2a  lea     rsi, [rdi+50h]
0x140043b2e  test    rax, rax
0x140043b31  jnz     short loc_140043B3E
0x140043b33  mov     r14d, 0C000009Ah
0x140043b39  jmp     loc_140043DA8
0x140043b3e  movzx   eax, word ptr [rbx]
0x140043b41  mov     [rsi], ax
0x140043b44  add     ax, r14w
0x140043b48  mov     [rdi+52h], ax
0x140043b4c  movzx   r8d, word ptr [rbx]; Size
0x140043b50  mov     rdx, [rbx+8]; Src
0x140043b54  call    memmove
0x140043b59  movups  xmm0, xmmword ptr [rsi]
0x140043b5c  movdqu  xmmword ptr [rdi+80h], xmm0
0x140043b64  movzx   ecx, word ptr [rdi+80h]
0x140043b6b  cmp     cx, r14w
0x140043b6f  jb      short loc_140043B9F
0x140043b71  mov     rax, [rdi+88h]
0x140043b78  cmp     word ptr [rax], 5Ch ; '\'
0x140043b7c  jnz     short loc_140043B9F
0x140043b7e  add     rax, r14
0x140043b81  sub     cx, r14w
0x140043b85  mov     [rdi+88h], rax
0x140043b8c  mov     eax, 0FFFEh
0x140043b91  add     [rdi+82h], ax
0x140043b98  mov     [rdi+80h], cx
0x140043b9f  lea     r9, [rbp+HashValue]; HashValue
0x140043ba3  xor     r8d, r8d; HashAlgorithm
0x140043ba6  mov     dl, 1; CaseInSensitive
0x140043ba8  mov     rcx, rsi; String
0x140043bab  call    cs:__imp_RtlHashUnicodeString
0x140043bb2  nop     dword ptr [rax+rax+00h]
0x140043bb7  mov     r14d, eax
0x140043bba  test    eax, eax
0x140043bbc  jns     short loc_140043C08
0x140043bbe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043bc5  lea     rax, WPP_GLOBAL_Control
0x140043bcc  cmp     rcx, rax
0x140043bcf  jz      loc_140043DA8
0x140043bd5  mov     edx, [rcx+2Ch]
0x140043bd8  test    dl, 1
0x140043bdb  jz      loc_140043DA8
0x140043be1  cmp     byte ptr [rcx+29h], 1
0x140043be5  jb      loc_140043DA8
0x140043beb  mov     rcx, [rcx+18h]
0x140043bef  lea     r8, WPP_948a51171ac53989b14c3e6a960354da_Traceguids
0x140043bf6  mov     edx, 0Ch
0x140043bfb  mov     r9d, r14d
0x140043bfe  call    WPP_SF_d
0x140043c03  jmp     loc_140043DA8
0x140043c08  mov     eax, [rbp+HashValue]
0x140043c0b  mov     [rdi+48h], eax
0x140043c0e  cmp     cs:byte_14007D240, 0
0x140043c15  jz      short loc_140043C41
0x140043c17  movups  xmm0, xmmword ptr [rsi]
0x140043c1a  lea     r8, [rdi+370h]
0x140043c21  lea     r9, [rbp+var_2C]
0x140043c25  lea     rcx, [rbp+Uuid]
0x140043c29  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm0
0x140043c2e  call    SmbCeRetrieveIpFromRegistryWithSubdomains
0x140043c33  mov     r14d, eax
0x140043c36  cmp     eax, 0C000009Ah
0x140043c3b  jz      loc_140043DA3
0x140043c41  xorps   xmm0, xmm0
0x140043c44  lea     rcx, [rbp+Uuid]; Uuid
0x140043c48  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x140043c4c  call    cs:__imp_ExUuidCreate
0x140043c53  nop     dword ptr [rax+rax+00h]
0x140043c58  test    eax, eax
0x140043c5a  jns     short loc_140043C71
0x140043c5c  mov     rax, 0FFFFF78000000320h
0x140043c66  mov     rax, [rax]
0x140043c69  mov     qword ptr [rbp+Uuid.Data1], rax
0x140043c6d  mov     qword ptr [rbp+Uuid.Data4], rdi
0x140043c71  movups  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x140043c75  movdqu  xmmword ptr [rdi+2ACh], xmm0
0x140043c7d  mov     rbx, [r13+58h]
0x140043c81  test    rbx, rbx
0x140043c84  jz      short loc_140043C9C
0x140043c86  mov     rcx, rbx
0x140043c89  call    cs:__imp_PsReferenceSiloContext
0x140043c90  nop     dword ptr [rax+rax+00h]
0x140043c95  mov     [rdi+208h], rbx
0x140043c9c  mov     eax, 1000h
0x140043ca1  mov     [rdi+2C0h], eax
0x140043ca7  mov     [rdi+2C4h], eax
0x140043cad  mov     [rdi+2C8h], eax
0x140043cb3  mov     rax, [rdi+18h]
0x140043cb7  movups  xmm0, xmmword ptr [rax+940h]
0x140043cbe  movups  xmmword ptr [rdi+2FCh], xmm0
0x140043cc5  movups  xmm1, xmmword ptr [rax+950h]
0x140043ccc  movups  xmmword ptr [rdi+30Ch], xmm1
0x140043cd3  mov     eax, [rax+960h]
0x140043cd9  and     byte ptr [rdi+2E1h], 0F0h
0x140043ce0  and     byte ptr [rdi+2E0h], 80h
0x140043ce7  mov     cl, [rdi+2E1h]
0x140043ced  xor     ebx, ebx
0x140043cef  mov     [rdi+344h], ebx
0x140043cf5  mov     [rdi+31Ch], eax
0x140043cfb  mov     [rdi+3F0h], rbx
0x140043d02  movzx   eax, word ptr [r13+92h]
0x140043d0a  cmp     [r13+90h], ax
0x140043d12  jnb     short loc_140043D3D
0x140043d14  or      cl, 10h
0x140043d17  mov     [rdi+2E1h], cl
0x140043d1d  test    byte ptr [r12+2EEh], 20h
0x140043d26  jz      short loc_140043D31
0x140043d28  or      cl, 20h
0x140043d2b  mov     [rdi+2E1h], cl
0x140043d31  call    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck
0x140043d36  or      byte ptr [rdi+2FCh], 40h
0x140043d3d  lea     rcx, [rdi+200h]; RunRef
0x140043d44  call    cs:__imp_ExInitializeRundownProtection
0x140043d4b  nop     dword ptr [rax+rax+00h]
0x140043d50  mov     rcx, r15
0x140043d53  mov     [rdi+90h], rbx
0x140043d5a  call    SmbCeAcquireSpinLock
0x140043d5f  mov     rcx, rdi
0x140043d62  mov     bl, al
0x140043d64  call    SmbCeAddServerEntryLite
0x140043d69  lea     rcx, [r15+528h]; Event
0x140043d70  call    cs:__imp_KeResetEvent
0x140043d77  nop     dword ptr [rax+rax+00h]
0x140043d7c  lea     rcx, [r15+780h]; SpinLock
0x140043d83  mov     dword ptr [r15+930h], 0FFFFFFFFh
0x140043d8e  mov     dl, bl; OldIrql
0x140043d90  call    cs:__imp_ExReleaseSpinLockExclusive
0x140043d97  nop     dword ptr [rax+rax+00h]
0x140043d9c  mov     rax, [rbp+var_28]
0x140043da0  mov     [rax], rdi
0x140043da3  test    r14d, r14d
0x140043da6  jz      short loc_140043DDE
0x140043da8  mov     rcx, [rsi+8]; P
0x140043dac  test    rcx, rcx
0x140043daf  jz      short loc_140043DCA
0x140043db1  mov     edx, 6D537653h; Tag
0x140043db6  call    cs:__imp_ExFreePoolWithTag
0x140043dbd  nop     dword ptr [rax+rax+00h]
0x140043dc2  mov     qword ptr [rsi+8], 0
0x140043dca  xor     eax, eax
0x140043dcc  mov     qword ptr [rsi+8], 0
0x140043dd4  mov     rcx, rdi
0x140043dd7  mov     [rsi], eax
0x140043dd9  call    SmbMmFreeObjectPool
0x140043dde  mov     eax, r14d
0x140043de1  mov     rcx, [rbp+var_10]
0x140043de5  xor     rcx, rsp; StackCookie
0x140043de8  call    __security_check_cookie
0x140043ded  mov     rbx, [rsp+50h+arg_0]
0x140043df5  add     rsp, 50h
0x140043df9  pop     r15
0x140043dfb  pop     r14
0x140043dfd  pop     r13
0x140043dff  pop     r12
0x140043e01  pop     rdi
0x140043e02  pop     rsi
0x140043e03  pop     rbp
0x140043e04  retn
```
