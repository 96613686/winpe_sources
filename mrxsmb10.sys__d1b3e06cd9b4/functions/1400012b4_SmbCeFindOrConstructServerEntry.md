# SmbCeFindOrConstructServerEntry

- ea: `0x1400012b4`
- end: `0x140001799`
- name: `SmbCeFindOrConstructServerEntry`
- size: `1253`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400010f0`

## callees

- `0x1400012b4`
- `0x140001e40`
- `0x140002470`
- `0x140005c60`
- `0x14000a440`
- `0x14000b9dc`
- `0x14000dfa8`
- `0x14000ed10`
- `0x140016560`
- `0x1400166c0`
- `0x1400169c0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400015c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000167d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400015c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000167d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400014d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400014d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000145f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000145f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000152c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000152c`
- `ntoskrnl!ExAllocatePool2` at `0x14000136a`
- `ntoskrnl!ExAllocatePool2` at `0x14000136a`
- `mrxsmb!MRxSmbBootedRemotely` at `0x1400014e3`
- `mrxsmb!MRxSmbActivateRecurrentService` at `0x140001492`
- `mrxsmb!MRxSmbActivateRecurrentService` at `0x140001492`
- `mrxsmb!MRxSmbRemoteBootShare` at `0x1400014f6`
- `mrxsmb!SmbCepDereferenceTransport` at `0x140001744`
- `mrxsmb!SmbCepDereferenceTransport` at `0x140001744`
- `mrxsmb!MRxSmbDeviceObject` at `0x140001481`

## pseudocode

```c
__int64 __fastcall SmbCeFindOrConstructServerEntry(
        const UNICODE_STRING *a1,
        __int64 a2,
        __int64 *a3,
        char *a4,
        UNICODE_STRING *a5,
        int a6)
{
  UNICODE_STRING *p_String1; // rsi
  unsigned int v8; // r12d
  char v9; // r15
  __int64 ServerEntry; // rbx
  __int64 Pool2; // rax
  USHORT *v12; // r15
  USHORT *v13; // r13
  unsigned __int16 v14; // ax
  void *v15; // rcx
  _QWORD *v16; // rdx
  USHORT v17; // ax
  UNICODE_STRING v18; // xmm0
  _QWORD *v19; // rsi
  WCHAR *Buffer; // rdi
  USHORT v21; // cx
  WCHAR *v22; // rax
  __int64 v23; // rax
  USHORT Length; // ax
  WCHAR *v25; // rdi
  USHORT v26; // cx
  WCHAR *v27; // rax
  __int64 v28; // rax
  USHORT v29; // ax
  PWSTR v30; // rdx
  UNICODE_STRING String2; // [rsp+38h] [rbp-48h] BYREF
  UNICODE_STRING v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 *v34; // [rsp+58h] [rbp-28h]
  char *v35; // [rsp+60h] [rbp-20h]
  UNICODE_STRING String1; // [rsp+68h] [rbp-18h] BYREF

  p_String1 = &String1;
  v35 = a4;
  v34 = a3;
  if ( a5 )
    p_String1 = a5;
  v8 = 0;
  v9 = 0;
  String1 = 0;
  if ( a6 == 1 || (ServerEntry = 0, a6 == 2) )
    ServerEntry = SmbCeFindServerEntry(a1);
  if ( (a6 & 0xFFFFFFFD) != 0 )
  {
    if ( !ServerEntry )
    {
      v8 = -1073741275;
      goto LABEL_53;
    }
    goto LABEL_54;
  }
  if ( ServerEntry )
  {
LABEL_54:
    if ( *(_QWORD *)(ServerEntry + 336) )
    {
      SmbCepDereferenceTransport();
      *(_QWORD *)(ServerEntry + 336) = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (unsigned int)WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
        ServerEntry,
        ServerEntry + 80);
    goto LABEL_53;
  }
  ServerEntry = SmbMmAllocateObject(0);
  if ( !ServerEntry )
    goto LABEL_13;
  Pool2 = ExAllocatePool2(66, a1->Length + 2LL, 1918070099);
  *(_QWORD *)(ServerEntry + 88) = Pool2;
  if ( !Pool2 )
  {
    SmbMmFreeObjectPool(ServerEntry);
    ServerEntry = 0;
LABEL_13:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids);
    v8 = -1073741670;
    goto LABEL_53;
  }
  v12 = (USHORT *)(ServerEntry + 80);
  *(_WORD *)(ServerEntry + 80) = a1->Length;
  v13 = (USHORT *)(ServerEntry + 82);
  v14 = a1->Length + 2;
  v15 = *(void **)(ServerEntry + 88);
  *(_WORD *)(ServerEntry + 82) = v14;
  *(_QWORD *)&v33.Length = ServerEntry + 88;
  memset(v15, 0, v14);
  memmove(*(void **)(ServerEntry + 88), a1->Buffer, *(unsigned __int16 *)(ServerEntry + 80));
  *(_QWORD *)(ServerEntry + 144) = 0;
  _InterlockedExchange((volatile __int32 *)(ServerEntry + 12), 3);
  *(_DWORD *)(ServerEntry + 4) = 2;
  *(_QWORD *)(ServerEntry + 336) = 0;
  MRxSmbTrackRefCount(ServerEntry, "SmbCeFindOrConstructServerEntry", 405);
  SmbReferenceRecord(ServerEntry + 792, "SmbCeFindOrConstructServerEntry", 405);
  _InterlockedIncrement((volatile signed __int32 *)(ServerEntry + 8));
  s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  if ( (__int64 *)s_DbServers == &s_DbServers )
    MRxSmbActivateRecurrentService(MRxSmbDeviceObject, MRxSmbEchoProbeServiceContext);
  v16 = (_QWORD *)qword_14001FB98;
  if ( *(__int64 **)qword_14001FB98 != &s_DbServers )
    __fastfail(3u);
  *(_QWORD *)(ServerEntry + 40) = qword_14001FB98;
  *(_QWORD *)(ServerEntry + 32) = &s_DbServers;
  *v16 = ServerEntry + 32;
  qword_14001FB98 = ServerEntry + 32;
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  *(_BYTE *)(ServerEntry + 507) = 0;
  if ( MRxSmbBootedRemotely )
  {
    v17 = *v12;
    if ( LOWORD(MRxSmbRemoteBootShare[0]) > *v12 )
    {
      String2 = 0;
      String2.Length = v17;
      String2.MaximumLength = *v13;
      String2.Buffer = &MRxSmbRemoteBootShare[1]->Length;
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)(ServerEntry + 80), &String2, 1u) )
        *(_BYTE *)(ServerEntry + 507) = 1;
    }
  }
  v18 = *p_String1;
  v19 = *(_QWORD **)&v33.Length;
  *(UNICODE_STRING *)(ServerEntry + 760) = v18;
  if ( stru_140020310.Length )
  {
    Buffer = stru_140020310.Buffer;
    v21 = *v12 - 2;
    String2.MaximumLength = *v13;
    v22 = (WCHAR *)(*v19 + 2LL);
    *(_DWORD *)(&String2.MaximumLength + 1) = 0;
    String2.Buffer = v22;
    String1 = 0;
    String2.Length = v21;
    while ( *Buffer )
    {
      v23 = -1;
      do
        ++v23;
      while ( Buffer[v23] );
      Length = 2 * v23;
      String1.Length = Length;
      if ( Length == v21 )
      {
        String1.MaximumLength = Length;
        String1.Buffer = Buffer;
        if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
        {
          *(_BYTE *)(ServerEntry + 510) = 1;
          break;
        }
        Length = String1.Length;
        v21 = String2.Length;
      }
      Buffer += ((unsigned __int64)Length >> 1) + 1;
    }
  }
  if ( byte_140020330 )
  {
LABEL_48:
    *(_BYTE *)(ServerEntry + 640) = 1;
  }
  else if ( stru_140020320.Length )
  {
    v25 = stru_140020320.Buffer;
    v26 = *v12 - 2;
    String2.MaximumLength = *v13;
    v27 = (WCHAR *)(*v19 + 2LL);
    *(_DWORD *)(&String2.MaximumLength + 1) = 0;
    String2.Buffer = v27;
    v33 = 0;
    String2.Length = v26;
    while ( *v25 )
    {
      v28 = -1;
      do
        ++v28;
      while ( v25[v28] );
      v29 = 2 * v28;
      v30 = v25;
      v33.Length = v29;
      v33.MaximumLength = v29;
      v33.Buffer = v25;
      if ( v29 == v26 )
      {
        if ( !RtlCompareUnicodeString(&v33, &String2, 1u) )
          goto LABEL_48;
        v30 = v33.Buffer;
        v29 = v33.Length;
        v26 = String2.Length;
      }
      if ( v29 && *v30 == 42 )
      {
        byte_140020330 = 1;
        goto LABEL_48;
      }
      v25 += ((unsigned __int64)v29 >> 1) + 1;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
      ServerEntry,
      ServerEntry + 80);
  v9 = 1;
LABEL_53:
  *v34 = ServerEntry;
  *v35 = v9;
  return v8;
}

```

## disassembly

```asm
0x1400012b4  mov     [rsp-38h+arg_8], rbx
0x1400012b9  push    rbp
0x1400012ba  push    rsi
0x1400012bb  push    rdi
0x1400012bc  push    r12
0x1400012be  push    r13
0x1400012c0  push    r14
0x1400012c2  push    r15
0x1400012c4  mov     rbp, rsp
0x1400012c7  sub     rsp, 80h
0x1400012ce  mov     rax, cs:__security_cookie
0x1400012d5  xor     rax, rsp
0x1400012d8  mov     [rbp+var_8], rax
0x1400012dc  mov     rax, [rbp+arg_20]
0x1400012e0  lea     rsi, [rbp+String1]
0x1400012e4  mov     edi, [rbp+arg_28]
0x1400012e7  xor     r13d, r13d
0x1400012ea  test    rax, rax
0x1400012ed  mov     [rbp+var_20], r9
0x1400012f1  xorps   xmm0, xmm0
0x1400012f4  mov     [rbp+var_28], r8
0x1400012f8  cmovnz  rsi, rax
0x1400012fc  mov     r14, rcx
0x1400012ff  mov     r12d, r13d
0x140001302  mov     r15b, r13b
0x140001305  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140001309  cmp     edi, 1
0x14000130c  jz      short loc_140001316
0x14000130e  mov     ebx, r13d
0x140001311  cmp     edi, 2
0x140001314  jnz     short loc_140001321
0x140001316  mov     r8, rsi
0x140001319  call    SmbCeFindServerEntry
0x14000131e  mov     rbx, rax
0x140001321  test    edi, 0FFFFFFFDh
0x140001327  jz      short loc_14000133D
0x140001329  test    rbx, rbx
0x14000132c  jnz     loc_140001738
0x140001332  mov     r12d, 0C0000225h
0x140001338  jmp     loc_1400016FF
0x14000133d  test    rbx, rbx
0x140001340  jnz     loc_140001738
0x140001346  xor     ecx, ecx
0x140001348  call    SmbMmAllocateObject
0x14000134d  mov     rbx, rax
0x140001350  test    rax, rax
0x140001353  jz      short loc_14000138A
0x140001355  movzx   edx, word ptr [r14]
0x140001359  mov     edi, 2
0x14000135e  add     rdx, rdi
0x140001361  mov     r8d, 72536D53h
0x140001367  lea     ecx, [rdi+40h]
0x14000136a  call    cs:__imp_ExAllocatePool2
0x140001371  nop     dword ptr [rax+rax+00h]
0x140001376  mov     [rbx+58h], rax
0x14000137a  test    rax, rax
0x14000137d  jnz     short loc_1400013C6
0x14000137f  mov     rcx, rbx
0x140001382  call    SmbMmFreeObjectPool
0x140001387  mov     rbx, r13
0x14000138a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140001391  lea     rax, WPP_GLOBAL_Control
0x140001398  cmp     rcx, rax
0x14000139b  jz      short loc_1400013BB
0x14000139d  test    dword ptr [rcx+2Ch], 400h
0x1400013a4  jz      short loc_1400013BB
0x1400013a6  mov     rcx, [rcx+18h]
0x1400013aa  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x1400013b1  mov     edx, 0Bh
0x1400013b6  call    WPP_SF_
0x1400013bb  mov     r12d, 0C000009Ah
0x1400013c1  jmp     loc_1400016FF
0x1400013c6  movzx   eax, word ptr [r14]
0x1400013ca  lea     r15, [rbx+50h]
0x1400013ce  mov     [r15], ax
0x1400013d2  lea     r13, [rbx+52h]
0x1400013d6  movzx   eax, word ptr [r14]
0x1400013da  xor     edx, edx; Val
0x1400013dc  add     ax, di
0x1400013df  lea     rdi, [rbx+58h]
0x1400013e3  mov     rcx, [rdi]; void *
0x1400013e6  movzx   r8d, ax; Size
0x1400013ea  mov     [r13+0], r8w
0x1400013ef  mov     qword ptr [rbp+var_38.Length], rdi
0x1400013f3  call    memset
0x1400013f8  movzx   r8d, word ptr [r15]; Size
0x1400013fc  mov     rdx, [r14+8]; Src
0x140001400  mov     rcx, [rdi]; void *
0x140001403  call    memmove
0x140001408  xor     r14d, r14d
0x14000140b  lea     rdx, aSmbcefindorcon_1; "SmbCeFindOrConstructServerEntry"
0x140001412  mov     [rbx+90h], r14
0x140001419  mov     edi, 195h
0x14000141e  mov     r8d, edi
0x140001421  mov     rcx, rbx
0x140001424  lea     eax, [r14+3]
0x140001428  xchg    eax, [rbx+0Ch]
0x14000142b  mov     dword ptr [rbx+4], 2
0x140001432  mov     [rbx+150h], r14
0x140001439  call    MRxSmbTrackRefCount
0x14000143e  lea     rcx, [rbx+318h]
0x140001445  mov     r8d, edi
0x140001448  lea     rdx, aSmbcefindorcon_1; "SmbCeFindOrConstructServerEntry"
0x14000144f  call    SmbReferenceRecord
0x140001454  lock inc dword ptr [rbx+8]
0x140001458  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000145f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001466  nop     dword ptr [rax+rax+00h]
0x14000146b  lea     rdi, s_DbServers
0x140001472  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140001478  cmp     cs:s_DbServers, rdi
0x14000147f  jnz     short loc_14000149E
0x140001481  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140001488  lea     rdx, MRxSmbEchoProbeServiceContext
0x14000148f  mov     rcx, [rcx]
0x140001492  call    cs:__imp_MRxSmbActivateRecurrentService
0x140001499  nop     dword ptr [rax+rax+00h]
0x14000149e  mov     rdx, cs:qword_14001FB98
0x1400014a5  cmp     [rdx], rdi
0x1400014a8  jz      short loc_1400014B1
0x1400014aa  mov     ecx, 3
0x1400014af  int     29h; Win8: RtlFailFast(ecx)
0x1400014b1  lea     rax, [rbx+20h]
0x1400014b5  mov     [rbp+var_50], 1
0x1400014b9  mov     [rax+8], rdx
0x1400014bd  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400014c4  mov     [rax], rdi
0x1400014c7  mov     [rdx], rax
0x1400014ca  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x1400014d0  mov     cs:qword_14001FB98, rax
0x1400014d7  call    cs:__imp_KeReleaseSpinLock
0x1400014de  nop     dword ptr [rax+rax+00h]
0x1400014e3  mov     rax, cs:__imp_MRxSmbBootedRemotely
0x1400014ea  mov     [rbx+1FBh], r14b
0x1400014f1  cmp     [rax], r14b
0x1400014f4  jz      short loc_140001543
0x1400014f6  mov     rcx, cs:__imp_MRxSmbRemoteBootShare
0x1400014fd  movzx   eax, word ptr [r15]
0x140001501  cmp     [rcx], ax
0x140001504  jbe     short loc_140001543
0x140001506  xorps   xmm0, xmm0
0x140001509  lea     rdx, [rbp+String2]; String2
0x14000150d  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140001511  mov     [rbp+String2.Length], ax
0x140001515  mov     r8b, 1; CaseInSensitive
0x140001518  movzx   eax, word ptr [r13+0]
0x14000151d  mov     [rbp+String2.MaximumLength], ax
0x140001521  mov     rax, [rcx+8]
0x140001525  mov     rcx, r15; String1
0x140001528  mov     [rbp+String2.Buffer], rax
0x14000152c  call    cs:__imp_RtlEqualUnicodeString
0x140001533  nop     dword ptr [rax+rax+00h]
0x140001538  test    al, al
0x14000153a  jz      short loc_140001543
0x14000153c  mov     byte ptr [rbx+1FBh], 1
0x140001543  movups  xmm0, xmmword ptr [rsi]
0x140001546  mov     rsi, qword ptr [rbp+var_38.Length]
0x14000154a  movdqu  xmmword ptr [rbx+2F8h], xmm0
0x140001552  cmp     cs:stru_140020310.Length, r14w
0x14000155a  jz      loc_1400015F7
0x140001560  movzx   eax, word ptr [r13+0]
0x140001565  mov     edx, 2
0x14000156a  movzx   ecx, word ptr [r15]
0x14000156e  xorps   xmm0, xmm0
0x140001571  mov     rdi, cs:stru_140020310.Buffer
0x140001578  sub     cx, dx
0x14000157b  mov     [rbp+String2.MaximumLength], ax
0x14000157f  mov     rax, [rsi]
0x140001582  add     rax, rdx
0x140001585  mov     dword ptr [rbp+String2+4], r14d
0x140001589  mov     [rbp+String2.Buffer], rax
0x14000158d  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140001591  mov     [rbp+String2.Length], cx
0x140001595  cmp     [rdi], r14w
0x140001599  jz      short loc_1400015F7
0x14000159b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000159f  inc     rax
0x1400015a2  cmp     [rdi+rax*2], r14w
0x1400015a7  jnz     short loc_14000159F
0x1400015a9  add     ax, ax
0x1400015ac  mov     [rbp+String1.Length], ax
0x1400015b0  cmp     ax, cx
0x1400015b3  jnz     short loc_1400015E0
0x1400015b5  mov     r8b, 1; CaseInSensitive
0x1400015b8  mov     [rbp+String1.MaximumLength], ax
0x1400015bc  lea     rdx, [rbp+String2]; String2
0x1400015c0  mov     [rbp+String1.Buffer], rdi
0x1400015c4  lea     rcx, [rbp+String1]; String1
0x1400015c8  call    cs:__imp_RtlCompareUnicodeString
0x1400015cf  nop     dword ptr [rax+rax+00h]
0x1400015d4  test    eax, eax
0x1400015d6  jz      short loc_1400015F0
0x1400015d8  movzx   eax, [rbp+String1.Length]
0x1400015dc  movzx   ecx, [rbp+String2.Length]
0x1400015e0  movzx   eax, ax
0x1400015e3  shr     rax, 1
0x1400015e6  lea     rdi, [rdi+rax*2]
0x1400015ea  add     rdi, 2
0x1400015ee  jmp     short loc_140001595
0x1400015f0  mov     byte ptr [rbx+1FEh], 1
0x1400015f7  cmp     cs:byte_140020330, r14b
0x1400015fe  jnz     loc_1400016BB
0x140001604  cmp     cs:stru_140020320.Length, r14w
0x14000160c  jz      loc_1400016C2
0x140001612  movzx   eax, word ptr [r13+0]
0x140001617  mov     edx, 2
0x14000161c  movzx   ecx, word ptr [r15]
0x140001620  xorps   xmm0, xmm0
0x140001623  mov     rdi, cs:stru_140020320.Buffer
0x14000162a  sub     cx, dx
0x14000162d  mov     [rbp+String2.MaximumLength], ax
0x140001631  mov     rax, [rsi]
0x140001634  add     rax, rdx
0x140001637  mov     dword ptr [rbp+String2+4], r14d
0x14000163b  mov     [rbp+String2.Buffer], rax
0x14000163f  movups  xmmword ptr [rbp+var_38.Length], xmm0
0x140001643  mov     [rbp+String2.Length], cx
0x140001647  cmp     [rdi], r14w
0x14000164b  jz      short loc_1400016C2
0x14000164d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001651  inc     rax
0x140001654  cmp     [rdi+rax*2], r14w
0x140001659  jnz     short loc_140001651
0x14000165b  add     ax, ax
0x14000165e  mov     rdx, rdi
0x140001661  mov     [rbp+var_38.Length], ax
0x140001665  mov     [rbp+var_38.MaximumLength], ax
0x140001669  mov     [rbp+var_38.Buffer], rdx
0x14000166d  cmp     ax, cx
0x140001670  jnz     short loc_140001699
0x140001672  mov     r8b, 1; CaseInSensitive
0x140001675  lea     rdx, [rbp+String2]; String2
0x140001679  lea     rcx, [rbp+var_38]; String1
0x14000167d  call    cs:__imp_RtlCompareUnicodeString
0x140001684  nop     dword ptr [rax+rax+00h]
0x140001689  test    eax, eax
0x14000168b  jz      short loc_1400016BB
0x14000168d  mov     rdx, [rbp+var_38.Buffer]
0x140001691  movzx   eax, [rbp+var_38.Length]
0x140001695  movzx   ecx, [rbp+String2.Length]
0x140001699  test    ax, ax
0x14000169c  jz      short loc_1400016A4
0x14000169e  cmp     word ptr [rdx], 2Ah ; '*'
0x1400016a2  jz      short loc_1400016B4
0x1400016a4  movzx   eax, ax
0x1400016a7  shr     rax, 1
0x1400016aa  lea     rdi, [rdi+rax*2]
0x1400016ae  add     rdi, 2
0x1400016b2  jmp     short loc_140001647
0x1400016b4  mov     cs:byte_140020330, 1
0x1400016bb  mov     byte ptr [rbx+280h], 1
0x1400016c2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400016c9  lea     rax, WPP_GLOBAL_Control
0x1400016d0  cmp     rcx, rax
0x1400016d3  jz      short loc_1400016FB
0x1400016d5  test    dword ptr [rcx+2Ch], 200h
0x1400016dc  jz      short loc_1400016FB
0x1400016de  mov     rcx, [rcx+18h]
0x1400016e2  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x1400016e9  mov     edx, 0Ah
0x1400016ee  mov     [rsp+80h+var_60], r15
0x1400016f3  mov     r9, rbx
0x1400016f6  call    WPP_SF_qZ
0x1400016fb  mov     r15b, [rbp+var_50]
0x1400016ff  mov     rax, [rbp+var_28]
0x140001703  mov     [rax], rbx
0x140001706  mov     rax, [rbp+var_20]
0x14000170a  mov     [rax], r15b
0x14000170d  mov     eax, r12d
0x140001710  mov     rcx, [rbp+var_8]
0x140001714  xor     rcx, rsp; StackCookie
0x140001717  call    __security_check_cookie
0x14000171c  mov     rbx, [rsp+80h+arg_8]
0x140001724  add     rsp, 80h
0x14000172b  pop     r15
0x14000172d  pop     r14
0x14000172f  pop     r13
0x140001731  pop     r12
0x140001733  pop     rdi
0x140001734  pop     rsi
0x140001735  pop     rbp
0x140001736  retn
0x140001738  mov     rcx, [rbx+150h]
0x14000173f  test    rcx, rcx
0x140001742  jz      short loc_140001757
0x140001744  call    cs:__imp_SmbCepDereferenceTransport
0x14000174b  nop     dword ptr [rax+rax+00h]
0x140001750  mov     [rbx+150h], r13
0x140001757  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000175e  lea     rax, WPP_GLOBAL_Control
0x140001765  cmp     rcx, rax
0x140001768  jz      short loc_1400016FF
0x14000176a  test    dword ptr [rcx+2Ch], 200h
0x140001771  jz      short loc_1400016FF
0x140001773  mov     rcx, [rcx+18h]
0x140001777  lea     r8, [rbx+50h]
0x14000177b  mov     [rsp+80h+var_60], r8
0x140001780  mov     edx, 0Ch
0x140001785  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x14000178c  mov     r9, rbx
  ... truncated ...
```
