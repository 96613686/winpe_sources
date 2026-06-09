# PcpCounterSetCallback

- ea: `0x140002e80`
- end: `0x140003769`
- name: `PcpCounterSetCallback`
- size: `2281`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002e80`
- `0x140003770`
- `0x1400037fc`
- `0x140003864`
- `0x140003934`
- `0x1400057b0`
- `0x140009100`
- `0x140013110`
- `0x140013300`
- `0x140013600`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140003102`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400032d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003714`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003102`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400032d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003714`
- `ntoskrnl!KfRaiseIrql` at `0x140002f59`
- `ntoskrnl!KfRaiseIrql` at `0x140002f59`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003513`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400036da`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003513`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400036da`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000349a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000349a`
- `ntoskrnl!KeLowerIrql` at `0x140002f97`
- `ntoskrnl!KeLowerIrql` at `0x14000352a`
- `ntoskrnl!KeLowerIrql` at `0x140002f97`
- `ntoskrnl!KeLowerIrql` at `0x14000352a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002fce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000327e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400033f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003594`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003660`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002fce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000327e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400033f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003594`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003660`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036ae`
- `ntoskrnl!ExAllocatePool2` at `0x140002f2d`
- `ntoskrnl!ExAllocatePool2` at `0x140003008`
- `ntoskrnl!ExAllocatePool2` at `0x14000315c`
- `ntoskrnl!ExAllocatePool2` at `0x140003458`
- `ntoskrnl!ExAllocatePool2` at `0x1400034ec`
- `ntoskrnl!ExAllocatePool2` at `0x140003561`
- `ntoskrnl!ExAllocatePool2` at `0x140002f2d`
- `ntoskrnl!ExAllocatePool2` at `0x140003008`
- `ntoskrnl!ExAllocatePool2` at `0x14000315c`
- `ntoskrnl!ExAllocatePool2` at `0x140003458`
- `ntoskrnl!ExAllocatePool2` at `0x1400034ec`
- `ntoskrnl!ExAllocatePool2` at `0x140003561`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400031d7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000342e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400031d7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000342e`
- `ntoskrnl!PcwAddInstance` at `0x14000326a`
- `ntoskrnl!PcwAddInstance` at `0x1400033c3`
- `ntoskrnl!PcwAddInstance` at `0x14000364c`
- `ntoskrnl!PcwAddInstance` at `0x140003748`
- `ntoskrnl!PcwAddInstance` at `0x14000326a`
- `ntoskrnl!PcwAddInstance` at `0x1400033c3`
- `ntoskrnl!PcwAddInstance` at `0x14000364c`
- `ntoskrnl!PcwAddInstance` at `0x140003748`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003197`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000360c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003197`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000360c`
- `NDIS!NdisAcquireRWLockRead` at `0x140003037`
- `NDIS!NdisAcquireRWLockRead` at `0x140003066`
- `NDIS!NdisAcquireRWLockRead` at `0x140003037`
- `NDIS!NdisAcquireRWLockRead` at `0x140003066`
- `NDIS!NdisReleaseRWLock` at `0x14000309f`
- `NDIS!NdisReleaseRWLock` at `0x1400030c0`
- `NDIS!NdisReleaseRWLock` at `0x1400030eb`
- `NDIS!NdisReleaseRWLock` at `0x1400035c3`
- `NDIS!NdisReleaseRWLock` at `0x14000309f`
- `NDIS!NdisReleaseRWLock` at `0x1400030c0`
- `NDIS!NdisReleaseRWLock` at `0x1400030eb`
- `NDIS!NdisReleaseRWLock` at `0x1400035c3`

## pseudocode

```c
__int64 __fastcall PcpCounterSetCallback(int a1, __int64 a2, __int64 a3)
{
  ULONG v6; // edi
  PPCW_BUFFER Pool2; // r14
  ULONG v9; // esi
  struct _DEVICE_OBJECT *DeviceContext; // rbx
  ULONG v11; // r15d
  struct _PCW_BUFFER *j; // r12
  ULONG v13; // edx
  ULONG v14; // edi
  int v15; // r15d
  ULONG v16; // esi
  PNDIS_RW_LOCK_EX i; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  ULONG v20; // r15d
  __int64 v21; // rbx
  struct _PCW_BUFFER *v22; // rdx
  WCHAR *v23; // r12
  __int64 v24; // rcx
  ULONG v25; // ebx
  struct _PCW_BUFFER *k; // r12
  __int64 v27; // r15
  __int64 v28; // rcx
  ULONG v29; // edx
  ULONG v30; // ebx
  __int64 v31; // r15
  USHORT v32; // r13
  WCHAR *v33; // rax
  WCHAR *v34; // r12
  struct _DEVICE_OBJECT **p_NextDevice; // rax
  struct _DEVICE_OBJECT *m; // r15
  __int64 v37; // rax
  unsigned __int64 v38; // r13
  struct _PCW_BUFFER *v39; // rax
  unsigned __int64 v40; // r15
  struct _PCW_BUFFER *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rbx
  KIRQL NewIrql; // [rsp+30h] [rbp-D0h]
  struct _LOCK_STATE_EX v45; // [rsp+34h] [rbp-CCh] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp-C8h] BYREF
  int v47; // [rsp+3Ch] [rbp-C4h]
  PPCW_BUFFER v48; // [rsp+40h] [rbp-C0h]
  struct _PCW_DATA Data; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING Name; // [rsp+58h] [rbp-A8h] BYREF
  PPCW_BUFFER Buffer; // [rsp+68h] [rbp-98h]
  UNICODE_STRING v52; // [rsp+70h] [rbp-90h] BYREF
  struct _PCW_BUFFER *v53; // [rsp+80h] [rbp-80h]
  PVOID *p_Reserved; // [rsp+88h] [rbp-78h]
  _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v56[20]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v57[14]; // [rsp+F0h] [rbp-10h] BYREF

  v48 = (PPCW_BUFFER)a2;
  LODWORD(Buffer) = a1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v45.OldIrql = 0;
  v45.Flags = 0;
  v52 = 0;
  Name = 0;
  memset(v56, 0, 0x44u);
  memset(v57, 0, 0x68u);
  DestinationString = 0;
  if ( (unsigned int)(a1 - 2) > 1 )
    return 0;
  if ( a3 == 1 )
  {
    v14 = 0;
    Pool2 = (PPCW_BUFFER)ExAllocatePool2(64, 48, 1935896656);
    if ( !Pool2 )
      return 3221225626LL;
    v15 = 6;
    v16 = 0;
    NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
    for ( i = (PNDIS_RW_LOCK_EX)PcgLineList; i != (PNDIS_RW_LOCK_EX)&PcgLineList; i = *(PNDIS_RW_LOCK_EX *)i )
    {
      NdisAcquireRWLockRead(*((PNDIS_RW_LOCK_EX *)i + 2), &v45, 0);
      if ( *((_DWORD *)i + 61) != 2
        || (v18 = *((_QWORD *)i + 32)) != 0 && *(_DWORD *)(v18 + 16) == 3 && *(PNDIS_RW_LOCK_EX *)(v18 + 160) == i )
      {
        NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)i + 2), &v45);
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)i + 62);
        NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)i + 2), &v45);
        if ( v16 == v15 )
        {
          v40 = (unsigned int)(2 * v15);
          v47 = v40;
          v41 = (struct _PCW_BUFFER *)ExAllocatePool2(64, 8 * v40, 1935896656);
          v48 = v41;
          if ( !v41 )
          {
            PcpLineDereference(i);
            NdisReleaseRWLock(PcgLineListLock, &LockState);
            if ( v16 )
            {
              do
                PcpLineDereference(*((PVOID *)Pool2 + v14++));
              while ( v14 < v16 );
            }
            goto LABEL_43;
          }
          memmove(v41, Pool2, 8 * (v40 >> 1));
          ExFreePoolWithTag(Pool2, 0x73637050u);
          Pool2 = v48;
          v15 = v47;
        }
        v19 = v16++;
        *((_QWORD *)Pool2 + v19) = i;
      }
    }
    NdisReleaseRWLock(PcgLineListLock, &LockState);
    RtlInitUnicodeString(&DestinationString, L"Traffic Control Global Interface");
    if ( (_DWORD)Buffer == 2 )
    {
      v30 = 0;
      v48 = *(PPCW_BUFFER *)(a2 + 24);
      while ( 1 )
      {
        if ( v30 >= v16 )
          goto LABEL_34;
        v31 = *((_QWORD *)Pool2 + v30);
        if ( RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v31 + 264), 1u) )
        {
          v32 = *(_WORD *)(v31 + 266);
          v33 = (WCHAR *)ExAllocatePool2(256, v32, 1935896656);
          v34 = v33;
          if ( !v33 )
          {
            if ( v16 )
            {
              do
                PcpLineDereference(*((PVOID *)Pool2 + v14++));
              while ( v14 < v16 );
            }
            goto LABEL_43;
          }
          *(_QWORD *)&Name.Length = 0;
          Name.MaximumLength = v32;
          Name.Buffer = v33;
          RtlCopyUnicodeString(&Name, (PCUNICODE_STRING)(v31 + 264));
          PcpConvertToInstanceName(&Name);
          Data.Data = 0;
          Data.Size = 68;
          PcwAddInstance(v48, &Name, v30, 1u, &Data);
          ExFreePoolWithTag(v34, 0x73637050u);
        }
        PcpLineDereference((PVOID)v31);
        ++v30;
      }
    }
    if ( (_DWORD)Buffer == 3 )
    {
      v20 = 0;
      Buffer = *(PPCW_BUFFER *)(a2 + 24);
      while ( 1 )
      {
        if ( v20 >= v16 )
          goto LABEL_34;
        v21 = *((_QWORD *)Pool2 + v20);
        v22 = (struct _PCW_BUFFER *)*(unsigned __int16 *)(v21 + 266);
        v48 = v22;
        v23 = (WCHAR *)ExAllocatePool2(256, v22, 1935896656);
        if ( !v23 )
          break;
        *(_QWORD *)&Name.Length = 0;
        Name.MaximumLength = (unsigned __int16)v48;
        Name.Buffer = v23;
        RtlCopyUnicodeString(&Name, (PCUNICODE_STRING)(v21 + 264));
        PcpConvertToInstanceName(&Name);
        v24 = *(_QWORD *)(a2 + 8);
        if ( !*(_QWORD *)(v24 + 8) || (unsigned __int8)PcpWildcardMatch(v24, &Name) )
        {
          if ( RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v21 + 264), 1u) )
          {
            memset(v56, 0, 0x44u);
            v56[0] = *(_DWORD *)(v21 + 80);
            v56[1] = *(_DWORD *)(v21 + 84);
            v56[2] = *(_DWORD *)(v21 + 88);
            v56[3] = *(_DWORD *)(v21 + 92);
            v56[4] = *(_DWORD *)(v21 + 96);
            v56[5] = *(_DWORD *)(v21 + 100);
            v56[6] = *(_DWORD *)(v21 + 104);
            v56[7] = *(_DWORD *)(v21 + 108);
            v56[8] = *(_DWORD *)(v21 + 108);
            v56[9] = *(_DWORD *)(v21 + 116);
            v56[10] = *(_DWORD *)(v21 + 112);
            Data.Data = v56;
            Data.Size = 68;
            PcwAddInstance(Buffer, &Name, v20, 1u, &Data);
          }
          ExFreePoolWithTag(v23, 0x73637050u);
        }
        PcpLineDereference((PVOID)v21);
        ++v20;
      }
      if ( v16 )
      {
        do
          PcpLineDereference(*((PVOID *)Pool2 + v14++));
        while ( v14 < v16 );
      }
LABEL_43:
      v29 = 1935896656;
      goto LABEL_44;
    }
LABEL_34:
    v13 = 1935896656;
    goto LABEL_10;
  }
  v6 = 0;
  Pool2 = (PPCW_BUFFER)ExAllocatePool2(64, 96, 1935894096);
  if ( !Pool2 )
    return 3221225626LL;
  v47 = 12;
  v9 = 0;
  NewIrql = KfRaiseIrql(2u);
  RtlAcquireReadLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  DeviceContext = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Queue.Wcb.DeviceContext;
LABEL_6:
  if ( DeviceContext == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext )
  {
    _InterlockedDecrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
    KeLowerIrql(NewIrql);
    if ( (_DWORD)Buffer == 2 )
    {
      v11 = 0;
      for ( j = (struct _PCW_BUFFER *)*((_QWORD *)v48 + 3); v11 < v9; ++v11 )
      {
        v43 = *((_QWORD *)Pool2 + v11);
        RtlInitUnicodeString(&v52, (PCWSTR)(v43 + 52));
        Data.Data = 0;
        Data.Size = 104;
        PcwAddInstance(j, &v52, v11, 1u, &Data);
        PcpDereferenceFlow(v43);
      }
    }
    else if ( (_DWORD)Buffer == 3 )
    {
      v25 = 0;
      for ( k = (struct _PCW_BUFFER *)*((_QWORD *)v48 + 3); v25 < v9; ++v25 )
      {
        v27 = *((_QWORD *)Pool2 + v25);
        RtlInitUnicodeString(&v52, (PCWSTR)(v27 + 52));
        v28 = *((_QWORD *)v48 + 1);
        if ( !*(_QWORD *)(v28 + 8) || (unsigned __int8)PcpWildcardMatch(v28, &v52) )
        {
          memset(v57, 0, 0x68u);
          v57[0] = *(_QWORD *)(v27 + 140);
          LODWORD(v57[1]) = *(_DWORD *)(v27 + 148);
          v57[2] = *(_QWORD *)(v27 + 152);
          v57[3] = *(_QWORD *)(v27 + 160);
          v57[4] = *(_QWORD *)(v27 + 160);
          v57[5] = *(_QWORD *)(v27 + 152);
          LODWORD(v57[6]) = *(_DWORD *)(v27 + 148);
          HIDWORD(v57[6]) = *(_DWORD *)(v27 + 144);
          LODWORD(v57[7]) = *(_DWORD *)(v27 + 140);
          HIDWORD(v57[7]) = *(_DWORD *)(v27 + 308);
          LODWORD(v57[8]) = *(_DWORD *)(v27 + 308);
          HIDWORD(v57[8]) = *(_DWORD *)(v27 + 316);
          LODWORD(v57[9]) = *(_DWORD *)(v27 + 312);
          Data.Data = v57;
          Data.Size = 104;
          PcwAddInstance(k, &v52, v25, 1u, &Data);
        }
        PcpDereferenceFlow(v27);
      }
    }
    v13 = 1935894096;
LABEL_10:
    ExFreePoolWithTag(Pool2, v13);
    return 0;
  }
  Data.Data = &DeviceContext->CurrentIrp;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&DeviceContext->CurrentIrp);
  p_NextDevice = &DeviceContext->NextDevice;
  for ( m = DeviceContext->NextDevice; ; m = *(struct _DEVICE_OBJECT **)&m->Type )
  {
    if ( m == (struct _DEVICE_OBJECT *)p_NextDevice )
    {
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&DeviceContext->CurrentIrp);
      DeviceContext = *(struct _DEVICE_OBJECT **)&DeviceContext->Type;
      goto LABEL_6;
    }
    p_Reserved = &m[-1].Reserved;
    PcpReferenceFlow((__int64)&m[-1].Reserved);
    if ( v9 == v47 )
      break;
LABEL_68:
    v42 = v9++;
    *((_QWORD *)Pool2 + v42) = (char *)m - 16;
    p_NextDevice = &DeviceContext->NextDevice;
  }
  v37 = (unsigned int)(2 * v47);
  v47 = v37;
  v38 = (unsigned int)v37;
  v39 = (struct _PCW_BUFFER *)ExAllocatePool2(64, 8 * v37, 1935894096);
  v53 = v39;
  if ( v39 )
  {
    memmove(v39, Pool2, 8 * (v38 >> 1));
    ExFreePoolWithTag(Pool2, 0x73636650u);
    Pool2 = v53;
    goto LABEL_68;
  }
  PcpDereferenceFlow(p_Reserved);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)Data.Data);
  _InterlockedDecrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
  KeLowerIrql(NewIrql);
  if ( v9 )
  {
    do
      PcpDereferenceFlow(*((_QWORD *)Pool2 + v6++));
    while ( v6 < v9 );
  }
  v29 = 1935894096;
LABEL_44:
  ExFreePoolWithTag(Pool2, v29);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140002e80  push    rbp
0x140002e82  push    rbx
0x140002e83  push    rsi
0x140002e84  push    rdi
0x140002e85  push    r12
0x140002e87  push    r13
0x140002e89  push    r14
0x140002e8b  push    r15
0x140002e8d  lea     rbp, [rsp-78h]
0x140002e92  sub     rsp, 178h
0x140002e99  mov     rax, cs:__security_cookie
0x140002ea0  xor     rax, rsp
0x140002ea3  mov     [rbp+0B0h+var_50], rax
0x140002ea7  xor     eax, eax
0x140002ea9  mov     [rsp+1B0h+var_170], rdx
0x140002eae  mov     rbx, r8
0x140002eb1  mov     dword ptr [rsp+1B0h+Buffer], ecx
0x140002eb5  mov     r13, rdx
0x140002eb8  mov     word ptr [rsp+1B0h+LockState.OldIrql], ax
0x140002ebd  mov     r15d, ecx
0x140002ec0  mov     [rsp+1B0h+LockState.Flags], al
0x140002ec4  xorps   xmm0, xmm0
0x140002ec7  mov     word ptr [rsp+1B0h+var_17C.OldIrql], ax
0x140002ecc  xorps   xmm1, xmm1
0x140002ecf  mov     [rsp+1B0h+var_17C.Flags], al
0x140002ed3  lea     r8d, [rax+44h]; Size
0x140002ed7  xor     edx, edx; Val
0x140002ed9  lea     rcx, [rbp+0B0h+var_110]; void *
0x140002edd  movups  xmmword ptr [rsp+1B0h+var_140.Length], xmm0
0x140002ee2  movups  xmmword ptr [rsp+1B0h+Name.Length], xmm1
0x140002ee7  call    memset
0x140002eec  xor     edx, edx; Val
0x140002eee  lea     rcx, [rbp+0B0h+var_C0]; void *
0x140002ef2  lea     r8d, [rdx+68h]; Size
0x140002ef6  call    memset
0x140002efb  lea     eax, [r15-2]
0x140002eff  xorps   xmm0, xmm0
0x140002f02  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x140002f06  cmp     eax, 1
0x140002f09  ja      loc_140002FDA
0x140002f0f  mov     r12d, 40h ; '@'
0x140002f15  mov     ecx, r12d
0x140002f18  cmp     rbx, 1
0x140002f1c  jz      loc_140002FFD
0x140002f22  lea     edx, [r12+20h]
0x140002f27  mov     r8d, 73636650h
0x140002f2d  call    cs:__imp_ExAllocatePool2
0x140002f34  nop     dword ptr [rax+rax+00h]
0x140002f39  xor     edi, edi
0x140002f3b  mov     r14, rax
0x140002f3e  test    rax, rax
0x140002f41  jnz     short loc_140002F4D
0x140002f43  mov     eax, 0C000009Ah
0x140002f48  jmp     loc_140002FDC
0x140002f4d  mov     cl, 2; NewIrql
0x140002f4f  mov     [rsp+1B0h+var_174], 0Ch
0x140002f57  mov     esi, edi
0x140002f59  call    cs:__imp_KfRaiseIrql
0x140002f60  nop     dword ptr [rax+rax+00h]
0x140002f65  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140002f6c  mov     [rsp+1B0h+NewIrql], al
0x140002f70  call    RtlAcquireReadLockAtDpcLevel
0x140002f75  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x140002f7c  lea     rax, WPP_MAIN_CB.Queue+20h
0x140002f83  cmp     rbx, rax
0x140002f86  jnz     loc_14000348E
0x140002f8c  mov     cl, [rsp+1B0h+NewIrql]; NewIrql
0x140002f90  lock dec dword ptr cs:WPP_MAIN_CB.Queue+38h
0x140002f97  call    cs:__imp_KeLowerIrql
0x140002f9e  nop     dword ptr [rax+rax+00h]
0x140002fa3  mov     r15d, dword ptr [rsp+1B0h+Buffer]
0x140002fa8  cmp     r15d, 2
0x140002fac  jnz     loc_1400032A4
0x140002fb2  mov     rax, [rsp+1B0h+var_170]
0x140002fb7  mov     r15d, edi
0x140002fba  mov     r12, [rax+18h]
0x140002fbe  test    esi, esi
0x140002fc0  jnz     loc_140003704
0x140002fc6  mov     edx, 73636650h; Tag
0x140002fcb  mov     rcx, r14; P
0x140002fce  call    cs:__imp_ExFreePoolWithTag
0x140002fd5  nop     dword ptr [rax+rax+00h]
0x140002fda  xor     eax, eax
0x140002fdc  mov     rcx, [rbp+0B0h+var_50]
0x140002fe0  xor     rcx, rsp; StackCookie
0x140002fe3  call    __security_check_cookie
0x140002fe8  add     rsp, 178h
0x140002fef  pop     r15
0x140002ff1  pop     r14
0x140002ff3  pop     r13
0x140002ff5  pop     r12
0x140002ff7  pop     rdi
0x140002ff8  pop     rsi
0x140002ff9  pop     rbx
0x140002ffa  pop     rbp
0x140002ffb  retn
0x140002ffd  mov     edx, 30h ; '0'
0x140003002  mov     r8d, 73637050h
0x140003008  call    cs:__imp_ExAllocatePool2
0x14000300f  nop     dword ptr [rax+rax+00h]
0x140003014  xor     edi, edi
0x140003016  mov     r14, rax
0x140003019  test    rax, rax
0x14000301c  jz      loc_140002F43
0x140003022  mov     rcx, cs:PcgLineListLock; Lock
0x140003029  lea     rdx, [rsp+1B0h+LockState]; LockState
0x14000302e  xor     r8d, r8d; Flags
0x140003031  lea     r15d, [rdi+6]
0x140003035  mov     esi, edi
0x140003037  call    cs:__imp_NdisAcquireRWLockRead
0x14000303e  nop     dword ptr [rax+rax+00h]
0x140003043  mov     rbx, cs:PcgLineList
0x14000304a  lea     rax, PcgLineList
0x140003051  cmp     rbx, rax
0x140003054  jz      loc_1400030DF
0x14000305a  mov     rcx, [rbx+10h]; Lock
0x14000305e  lea     rdx, [rsp+1B0h+var_17C]; LockState
0x140003063  xor     r8d, r8d; Flags
0x140003066  call    cs:__imp_NdisAcquireRWLockRead
0x14000306d  nop     dword ptr [rax+rax+00h]
0x140003072  cmp     dword ptr [rbx+0F4h], 2
0x140003079  jnz     short loc_140003096
0x14000307b  mov     rax, [rbx+100h]
0x140003082  test    rax, rax
0x140003085  jz      short loc_1400030B0
0x140003087  cmp     dword ptr [rax+10h], 3
0x14000308b  jnz     short loc_1400030B0
0x14000308d  cmp     [rax+0A0h], rbx
0x140003094  jnz     short loc_1400030B0
0x140003096  mov     rcx, [rbx+10h]; Lock
0x14000309a  lea     rdx, [rsp+1B0h+var_17C]; LockState
0x14000309f  call    cs:__imp_NdisReleaseRWLock
0x1400030a6  nop     dword ptr [rax+rax+00h]
0x1400030ab  mov     rbx, [rbx]
0x1400030ae  jmp     short loc_14000304A
0x1400030b0  lock inc dword ptr [rbx+0F8h]
0x1400030b7  mov     rcx, [rbx+10h]; Lock
0x1400030bb  lea     rdx, [rsp+1B0h+var_17C]; LockState
0x1400030c0  call    cs:__imp_NdisReleaseRWLock
0x1400030c7  nop     dword ptr [rax+rax+00h]
0x1400030cc  cmp     esi, r15d
0x1400030cf  jz      loc_140003548
0x1400030d5  mov     eax, esi
0x1400030d7  inc     esi
0x1400030d9  mov     [r14+rax*8], rbx
0x1400030dd  jmp     short loc_1400030AB
0x1400030df  mov     rcx, cs:PcgLineListLock; Lock
0x1400030e6  lea     rdx, [rsp+1B0h+LockState]; LockState
0x1400030eb  call    cs:__imp_NdisReleaseRWLock
0x1400030f2  nop     dword ptr [rax+rax+00h]
0x1400030f7  lea     rdx, SourceString; "Traffic Control Global Interface"
0x1400030fe  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x140003102  call    cs:__imp_RtlInitUnicodeString
0x140003109  nop     dword ptr [rax+rax+00h]
0x14000310e  mov     r15d, dword ptr [rsp+1B0h+Buffer]
0x140003113  cmp     r15d, 2
0x140003117  jz      loc_140003407
0x14000311d  cmp     r15d, 3
0x140003121  jnz     loc_14000329A
0x140003127  mov     rax, [r13+18h]
0x14000312b  mov     r15d, edi
0x14000312e  mov     [rsp+1B0h+Buffer], rax
0x140003133  cmp     r15d, esi
0x140003136  jnb     loc_14000329A
0x14000313c  mov     eax, r15d
0x14000313f  mov     ecx, 100h
0x140003144  mov     r8d, 73637050h
0x14000314a  mov     rbx, [r14+rax*8]
0x14000314e  movzx   eax, word ptr [rbx+10Ah]
0x140003155  mov     edx, eax
0x140003157  mov     [rsp+1B0h+var_170], rax
0x14000315c  call    cs:__imp_ExAllocatePool2
0x140003163  nop     dword ptr [rax+rax+00h]
0x140003168  mov     r12, rax
0x14000316b  test    rax, rax
0x14000316e  jz      loc_1400033E6
0x140003174  mov     rax, [rsp+1B0h+var_170]
0x140003179  lea     rdx, [rbx+108h]; SourceString
0x140003180  xorps   xmm0, xmm0
0x140003183  lea     rcx, [rsp+1B0h+Name]; DestinationString
0x140003188  movups  xmmword ptr [rsp+1B0h+Name.Length], xmm0
0x14000318d  mov     [rsp+1B0h+Name.MaximumLength], ax
0x140003192  mov     [rsp+1B0h+Name.Buffer], r12
0x140003197  call    cs:__imp_RtlCopyUnicodeString
0x14000319e  nop     dword ptr [rax+rax+00h]
0x1400031a3  lea     rcx, [rsp+1B0h+Name]
0x1400031a8  call    PcpConvertToInstanceName
0x1400031ad  mov     rcx, [r13+8]
0x1400031b1  cmp     [rcx+8], rdi
0x1400031b5  jz      short loc_1400031C9
0x1400031b7  lea     rdx, [rsp+1B0h+Name]
0x1400031bc  call    PcpWildcardMatch
0x1400031c1  test    al, al
0x1400031c3  jz      loc_14000328A
0x1400031c9  mov     r8b, 1; CaseInSensitive
0x1400031cc  lea     rdx, [rbx+108h]; String2
0x1400031d3  lea     rcx, [rbp+0B0h+DestinationString]; String1
0x1400031d7  call    cs:__imp_RtlCompareUnicodeString
0x1400031de  nop     dword ptr [rax+rax+00h]
0x1400031e3  test    eax, eax
0x1400031e5  jz      loc_140003276
0x1400031eb  xor     edx, edx; Val
0x1400031ed  lea     rcx, [rbp+0B0h+var_110]; void *
0x1400031f1  lea     r8d, [rdx+44h]; Size
0x1400031f5  call    memset
0x1400031fa  mov     eax, [rbx+50h]
0x1400031fd  lea     rdx, [rsp+1B0h+Name]; Name
0x140003202  mov     rcx, [rsp+1B0h+Buffer]; Buffer
0x140003207  mov     r9d, 1; Count
0x14000320d  mov     [rbp+0B0h+var_110], eax
0x140003210  mov     r8d, r15d; Id
0x140003213  mov     eax, [rbx+54h]
0x140003216  mov     [rbp+0B0h+var_10C], eax
0x140003219  mov     eax, [rbx+58h]
0x14000321c  mov     [rbp+0B0h+var_108], eax
0x14000321f  mov     eax, [rbx+5Ch]
0x140003222  mov     [rbp+0B0h+var_104], eax
0x140003225  mov     eax, [rbx+60h]
0x140003228  mov     [rbp+0B0h+var_100], eax
0x14000322b  mov     eax, [rbx+64h]
0x14000322e  mov     [rbp+0B0h+var_FC], eax
0x140003231  mov     eax, [rbx+68h]
0x140003234  mov     [rbp+0B0h+var_F8], eax
0x140003237  mov     eax, [rbx+6Ch]
0x14000323a  mov     [rbp+0B0h+var_F4], eax
0x14000323d  mov     eax, [rbx+6Ch]
0x140003240  mov     [rbp+0B0h+var_F0], eax
0x140003243  mov     eax, [rbx+74h]
0x140003246  mov     [rbp+0B0h+var_EC], eax
0x140003249  mov     eax, [rbx+70h]
0x14000324c  mov     [rbp+0B0h+var_E8], eax
0x14000324f  lea     rax, [rbp+0B0h+var_110]
0x140003253  mov     [rsp+1B0h+var_168.Data], rax
0x140003258  lea     rax, [rsp+1B0h+var_168]
0x14000325d  mov     [rsp+1B0h+Data], rax; Data
0x140003262  mov     [rsp+1B0h+var_168.Size], 44h ; 'D'
0x14000326a  call    cs:__imp_PcwAddInstance
0x140003271  nop     dword ptr [rax+rax+00h]
0x140003276  mov     edx, 73637050h; Tag
0x14000327b  mov     rcx, r12; P
0x14000327e  call    cs:__imp_ExFreePoolWithTag
0x140003285  nop     dword ptr [rax+rax+00h]
0x14000328a  mov     rcx, rbx; P
0x14000328d  call    PcpLineDereference
0x140003292  inc     r15d
0x140003295  jmp     loc_140003133
0x14000329a  mov     edx, 73637050h
0x14000329f  jmp     loc_140002FCB
0x1400032a4  cmp     r15d, 3
0x1400032a8  jnz     loc_140002FC6
0x1400032ae  mov     r13, [rsp+1B0h+var_170]
0x1400032b3  mov     ebx, edi
0x1400032b5  mov     r12, [r13+18h]
0x1400032b9  test    esi, esi
0x1400032bb  jz      loc_140002FC6
0x1400032c1  mov     eax, ebx
0x1400032c3  lea     rcx, [rsp+1B0h+var_140]; DestinationString
0x1400032c8  mov     r15, [r14+rax*8]
0x1400032cc  lea     rdx, [r15+34h]; SourceString
0x1400032d0  call    cs:__imp_RtlInitUnicodeString
0x1400032d7  nop     dword ptr [rax+rax+00h]
0x1400032dc  mov     rcx, [r13+8]
0x1400032e0  cmp     [rcx+8], rdi
0x1400032e4  jz      short loc_1400032F8
0x1400032e6  lea     rdx, [rsp+1B0h+var_140]
0x1400032eb  call    PcpWildcardMatch
0x1400032f0  test    al, al
0x1400032f2  jz      loc_1400033CF
0x1400032f8  xor     edx, edx; Val
0x1400032fa  lea     rcx, [rbp+0B0h+var_C0]; void *
0x1400032fe  lea     r8d, [rdx+68h]; Size
0x140003302  call    memset
0x140003307  mov     eax, [r15+8Ch]
0x14000330e  lea     rdx, [rsp+1B0h+var_140]; Name
0x140003313  mov     [rbp+0B0h+var_C0], eax
0x140003316  mov     r9d, 1; Count
0x14000331c  mov     eax, [r15+90h]
0x140003323  mov     r8d, ebx; Id
0x140003326  mov     [rbp+0B0h+var_BC], eax
0x140003329  mov     rcx, r12; Buffer
0x14000332c  mov     eax, [r15+94h]
0x140003333  mov     [rbp+0B0h+var_B8], eax
0x140003336  mov     rax, [r15+98h]
0x14000333d  mov     [rbp+0B0h+var_B0], rax
0x140003341  mov     rax, [r15+0A0h]
0x140003348  mov     [rbp+0B0h+var_A8], rax
0x14000334c  mov     rax, [r15+0A0h]
0x140003353  mov     [rbp+0B0h+var_A0], rax
0x140003357  mov     rax, [r15+98h]
0x14000335e  mov     [rbp+0B0h+var_98], rax
0x140003362  mov     eax, [r15+94h]
0x140003369  mov     [rbp+0B0h+var_90], eax
0x14000336c  mov     eax, [r15+90h]
0x140003373  mov     [rbp+0B0h+var_8C], eax
0x140003376  mov     eax, [r15+8Ch]
0x14000337d  mov     [rbp+0B0h+var_88], eax
0x140003380  mov     eax, [r15+134h]
0x140003387  mov     [rbp+0B0h+var_84], eax
0x14000338a  mov     eax, [r15+134h]
0x140003391  mov     [rbp+0B0h+var_80], eax
  ... truncated ...
```
