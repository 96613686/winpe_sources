# QuicConnFree

- ea: `0x1400200d8`
- end: `0x140020451`
- name: `QuicConnFree`
- size: `889`
- prototype: ``
- caller_count: `12`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x1400038cc`
- `0x140007b30`
- `0x14000edc0`
- `0x14001d490`
- `0x14001d6fc`
- `0x14001d7d0`
- `0x14001d88c`
- `0x14001de64`
- `0x14001dfec`
- `0x14002e518`
- `0x140030044`
- `0x1400452d0`

## callees

- `0x140008de0`
- `0x1400092c0`
- `0x140009340`
- `0x14001c440`
- `0x1400200d8`
- `0x140020458`
- `0x1400205b4`
- `0x140020620`
- `0x1400206e8`
- `0x1400207e0`
- `0x140022644`
- `0x140029104`
- `0x1400291f0`
- `0x14002b964`
- `0x14002bfd8`
- `0x140030338`
- `0x1400337e4`
- `0x140034e44`
- `0x140038bf4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020237`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002031d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002033a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400203d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020237`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002031d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002033a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400203d1`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400202f2`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400202f2`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14002042b`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14002042b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400203b4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400203b4`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140020415`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140020415`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14002010c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14002010c`

## pseudocode

```c
LONG_PTR __fastcall QuicConnFree(__int64 a1)
{
  __int64 v1; // rax
  void *v2; // r14
  volatile signed __int64 *v3; // rbp
  __int64 v5; // rcx
  __int64 v6; // r15
  char v7; // al
  _QWORD *v8; // rdi
  __int64 v9; // rsi
  _QWORD **v10; // rdi
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 *v17; // rax
  void *v18; // rcx
  void *v19; // rcx
  __int64 v20; // rax
  void *v21; // rcx
  void *v22; // rcx
  __int64 v23; // rcx
  char v24; // al
  struct _EX_RUNDOWN_REF *v25; // rcx
  void *v26; // rcx
  LONG_PTR result; // rax

  v1 = *(_QWORD *)(a1 + 88);
  v2 = 0;
  v3 = *(volatile signed __int64 **)(a1 + 72);
  if ( v1 && (v5 = *(_QWORD *)(v1 + 64)) != 0 )
    v6 = PsAttachSiloToCurrentThread(v5);
  else
    v6 = -1;
  if ( (*(_BYTE *)(a1 + 249) & 4) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 317, "!Connection->State.Freed");
    __int2c();
  }
  if ( *(_DWORD *)(a1 + 240) )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 318, "Connection->RefCount == 0");
  v7 = *(_BYTE *)(a1 + 249);
  if ( (v7 & 0x20) != 0 && (v7 & 2) == 0 )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 320, "Connection->State.HandleClosed");
  if ( *(_QWORD *)(a1 + 1280) )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 322, "Connection->SourceCids.Next == ((void *)0)");
  if ( *(_QWORD *)(a1 + 2152) != a1 + 2152 )
    CxPlatLogAssert(
      "C:\\__w\\1\\s\\msquic\\src\\core\\connection.c",
      323,
      "CxPlatListIsEmpty(&Connection->Streams.ClosedStreams)");
  QuicRangeUninitialize(a1 + 1880);
  QuicCryptoUninitialize(a1 + 2784);
  QuicLossDetectionUninitialize(a1 + 2632);
  QuicSendUninitialize(a1 + 3416);
  v8 = (_QWORD *)(a1 + 2760);
  v9 = 3;
  do
  {
    if ( *v8 )
    {
      QuicPacketSpaceUninitialize();
      *v8 = 0;
    }
    ++v8;
    --v9;
  }
  while ( v9 );
  v10 = (_QWORD **)(a1 + 1288);
  while ( 1 )
  {
    v11 = *v10;
    if ( *v10 == v10 )
      break;
    v12 = (_QWORD *)*v11;
    *v10 = (_QWORD *)*v11;
    v12[1] = v10;
    ExFreePoolWithTag(v11, 0x45306351u);
  }
  QuicConnUnregister(a1);
  v16 = *(_QWORD *)(a1 + 64);
  if ( v16 )
  {
    QuicTimerWheelRemoveConnection(v16 + 88, a1);
    QuicOperationQueueClear(a1 + 1424, v3);
  }
  v17 = *(__int64 **)(a1 + 1392);
  if ( v17 )
  {
    do
    {
      *((_WORD *)v17 + 15) &= ~2u;
      v17 = (__int64 *)*v17;
    }
    while ( v17 );
    CxPlatRecvDataReturn(*(_QWORD *)(a1 + 1392), v13, v14, v15);
    *(_QWORD *)(a1 + 1392) = 0;
  }
  v18 = *(void **)(a1 + 360);
  if ( v18 )
  {
    QuicLibraryReleaseBinding(v18);
    *(_QWORD *)(a1 + 360) = 0;
  }
  v19 = *(void **)(a1 + 2128);
  if ( v19 )
    CxPlatHashtableUninitialize(v19);
  QuicDatagramSendShutdown(a1 + 3552);
  v20 = *(_QWORD *)(a1 + 88);
  if ( v20 )
  {
    v2 = *(void **)(v20 + 64);
    if ( v2 )
      ObfReferenceObjectWithTag(*(PVOID *)(v20 + 64), 0x30306351u);
    QuicConfigurationRelease(*(_QWORD *)(a1 + 88));
    *(_QWORD *)(a1 + 88) = 0;
  }
  v21 = *(void **)(a1 + 1608);
  if ( v21 )
    ExFreePoolWithTag(v21, 0x32336351u);
  v22 = *(void **)(a1 + 1304);
  if ( v22 )
    ExFreePoolWithTag(v22, 0x43306351u);
  v23 = *(_QWORD *)(a1 + 3616);
  if ( v23 )
  {
    QuicCryptoTlsCleanupTransportParameters(v23);
    CxPlatPoolFree(*(_QWORD *)(a1 + 3616));
    *(_QWORD *)(a1 + 3616) = 0;
  }
  QuicCryptoTlsCleanupTransportParameters(a1 + 1624);
  QuicSettingsCleanup(a1 + 96);
  v24 = *(_BYTE *)(a1 + 248);
  if ( (v24 & 4) != 0 && (v24 & 8) == 0 )
    _InterlockedIncrement64(v3 + 277);
  if ( (*(_BYTE *)(a1 + 248) & 8) != 0 )
    _InterlockedDecrement64(v3 + 281);
  v25 = *(struct _EX_RUNDOWN_REF **)(a1 + 80);
  if ( v25 )
    ExReleaseRundownProtection(v25 + 16);
  v26 = *(void **)(a1 + 1600);
  if ( v26 )
    ExFreePoolWithTag(v26, 0x35336351u);
  *(_BYTE *)(a1 + 249) |= 4u;
  if ( (byte_14005C489 & 0x40) != 0 )
    McTemplateU0p_EtwWriteTransfer(v26, QuicConnDestroyed);
  result = CxPlatPoolFree(a1);
  _InterlockedDecrement64(v3 + 280);
  if ( v6 != -1 )
    result = PsDetachSiloFromCurrentThread(v6);
  if ( v2 )
    return ObfDereferenceObjectWithTag(v2, 0x30306351u);
  return result;
}

```

## disassembly

```asm
0x1400200d8  mov     [rsp+arg_0], rbx
0x1400200dd  mov     [rsp+arg_8], rbp
0x1400200e2  mov     [rsp+arg_10], rsi
0x1400200e7  push    rdi
0x1400200e8  push    r14
0x1400200ea  push    r15
0x1400200ec  sub     rsp, 20h
0x1400200f0  mov     rax, [rcx+58h]
0x1400200f4  xor     r14d, r14d
0x1400200f7  mov     rbp, [rcx+48h]
0x1400200fb  mov     rbx, rcx
0x1400200fe  test    rax, rax
0x140020101  jz      short loc_14002011D
0x140020103  mov     rcx, [rax+40h]
0x140020107  test    rcx, rcx
0x14002010a  jz      short loc_14002011D
0x14002010c  call    cs:__imp_PsAttachSiloToCurrentThread
0x140020113  nop     dword ptr [rax+rax+00h]
0x140020118  mov     r15, rax
0x14002011b  jmp     short loc_140020121
0x14002011d  or      r15, 0FFFFFFFFFFFFFFFFh
0x140020121  test    byte ptr [rbx+0F9h], 4
0x140020128  lea     rdi, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x14002012f  jz      short loc_140020147
0x140020131  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x140020138  mov     edx, 13Dh
0x14002013d  mov     rcx, rdi
0x140020140  call    CxPlatLogAssert
0x140020145  int     2Ch; Windows NT - assertion failure
0x140020147  cmp     [rbx+0F0h], r14d
0x14002014e  jz      short loc_140020164
0x140020150  lea     r8, aConnectionRefc; "Connection->RefCount == 0"
0x140020157  mov     edx, 13Eh
0x14002015c  mov     rcx, rdi
0x14002015f  call    CxPlatLogAssert
0x140020164  mov     al, [rbx+0F9h]
0x14002016a  test    al, 20h
0x14002016c  jz      short loc_140020186
0x14002016e  test    al, 2
0x140020170  jnz     short loc_140020186
0x140020172  lea     r8, aConnectionStat_1; "Connection->State.HandleClosed"
0x140020179  mov     edx, 140h
0x14002017e  mov     rcx, rdi
0x140020181  call    CxPlatLogAssert
0x140020186  cmp     [rbx+500h], r14
0x14002018d  jz      short loc_1400201A3
0x14002018f  lea     r8, aConnectionSour; "Connection->SourceCids.Next == ((void *"...
0x140020196  mov     edx, 142h
0x14002019b  mov     rcx, rdi
0x14002019e  call    CxPlatLogAssert
0x1400201a3  lea     rax, [rbx+868h]
0x1400201aa  cmp     [rax], rax
0x1400201ad  jz      short loc_1400201C3
0x1400201af  lea     r8, aCxplatlistisem_0; "CxPlatListIsEmpty(&Connection->Streams."...
0x1400201b6  mov     edx, 143h
0x1400201bb  mov     rcx, rdi
0x1400201be  call    CxPlatLogAssert
0x1400201c3  lea     rcx, [rbx+758h]
0x1400201ca  call    QuicRangeUninitialize
0x1400201cf  lea     rcx, [rbx+0AE0h]
0x1400201d6  call    QuicCryptoUninitialize
0x1400201db  lea     rcx, [rbx+0A48h]
0x1400201e2  call    QuicLossDetectionUninitialize
0x1400201e7  lea     rcx, [rbx+0D58h]
0x1400201ee  call    QuicSendUninitialize
0x1400201f3  lea     rdi, [rbx+0AC8h]
0x1400201fa  mov     esi, 3
0x1400201ff  mov     rcx, [rdi]
0x140020202  test    rcx, rcx
0x140020205  jz      short loc_14002020F
0x140020207  call    QuicPacketSpaceUninitialize
0x14002020c  and     [rdi], r14
0x14002020f  add     rdi, 8
0x140020213  sub     rsi, 1
0x140020217  jnz     short loc_1400201FF
0x140020219  lea     rdi, [rbx+508h]
0x140020220  mov     rcx, [rdi]; P
0x140020223  cmp     rcx, rdi
0x140020226  jz      short loc_140020245
0x140020228  mov     rax, [rcx]
0x14002022b  mov     edx, 45306351h; Tag
0x140020230  mov     [rdi], rax
0x140020233  mov     [rax+8], rdi
0x140020237  call    cs:__imp_ExFreePoolWithTag
0x14002023e  nop     dword ptr [rax+rax+00h]
0x140020243  jmp     short loc_140020220
0x140020245  mov     rcx, rbx
0x140020248  call    QuicConnUnregister
0x14002024d  mov     rcx, [rbx+40h]
0x140020251  test    rcx, rcx
0x140020254  jz      short loc_140020271
0x140020256  add     rcx, 58h ; 'X'
0x14002025a  mov     rdx, rbx
0x14002025d  call    QuicTimerWheelRemoveConnection
0x140020262  lea     rcx, [rbx+590h]
0x140020269  mov     rdx, rbp
0x14002026c  call    QuicOperationQueueClear
0x140020271  mov     rax, [rbx+570h]
0x140020278  test    rax, rax
0x14002027b  jz      short loc_1400202A1
0x14002027d  mov     ecx, 0FFFDh
0x140020282  and     [rax+1Eh], cx
0x140020286  mov     rax, [rax]
0x140020289  test    rax, rax
0x14002028c  jnz     short loc_14002027D
0x14002028e  mov     rcx, [rbx+570h]
0x140020295  call    CxPlatRecvDataReturn
0x14002029a  and     [rbx+570h], r14
0x1400202a1  mov     rcx, [rbx+168h]; P
0x1400202a8  test    rcx, rcx
0x1400202ab  jz      short loc_1400202B9
0x1400202ad  call    QuicLibraryReleaseBinding
0x1400202b2  and     [rbx+168h], r14
0x1400202b9  mov     rcx, [rbx+850h]; P
0x1400202c0  test    rcx, rcx
0x1400202c3  jz      short loc_1400202CA
0x1400202c5  call    CxPlatHashtableUninitialize
0x1400202ca  lea     rcx, [rbx+0DE0h]
0x1400202d1  call    QuicDatagramSendShutdown
0x1400202d6  mov     rax, [rbx+58h]
0x1400202da  mov     edi, 30306351h
0x1400202df  test    rax, rax
0x1400202e2  jz      short loc_14002030C
0x1400202e4  mov     r14, [rax+40h]
0x1400202e8  test    r14, r14
0x1400202eb  jz      short loc_1400202FE
0x1400202ed  mov     edx, edi; Tag
0x1400202ef  mov     rcx, r14; Object
0x1400202f2  call    cs:__imp_ObfReferenceObjectWithTag
0x1400202f9  nop     dword ptr [rax+rax+00h]
0x1400202fe  mov     rcx, [rbx+58h]
0x140020302  call    QuicConfigurationRelease
0x140020307  and     qword ptr [rbx+58h], 0
0x14002030c  mov     rcx, [rbx+648h]; P
0x140020313  test    rcx, rcx
0x140020316  jz      short loc_140020329
0x140020318  mov     edx, 32336351h; Tag
0x14002031d  call    cs:__imp_ExFreePoolWithTag
0x140020324  nop     dword ptr [rax+rax+00h]
0x140020329  mov     rcx, [rbx+518h]; P
0x140020330  test    rcx, rcx
0x140020333  jz      short loc_140020346
0x140020335  mov     edx, 43306351h; Tag
0x14002033a  call    cs:__imp_ExFreePoolWithTag
0x140020341  nop     dword ptr [rax+rax+00h]
0x140020346  mov     rcx, [rbx+0E20h]
0x14002034d  test    rcx, rcx
0x140020350  jz      short loc_14002036B
0x140020352  call    QuicCryptoTlsCleanupTransportParameters
0x140020357  mov     rcx, [rbx+0E20h]
0x14002035e  call    CxPlatPoolFree
0x140020363  and     qword ptr [rbx+0E20h], 0
0x14002036b  lea     rcx, [rbx+658h]
0x140020372  call    QuicCryptoTlsCleanupTransportParameters
0x140020377  lea     rcx, [rbx+60h]
0x14002037b  call    QuicSettingsCleanup
0x140020380  mov     al, [rbx+0F8h]
0x140020386  test    al, 4
0x140020388  jz      short loc_140020396
0x14002038a  test    al, 8
0x14002038c  jnz     short loc_140020396
0x14002038e  lock inc qword ptr [rbp+8A8h]
0x140020396  test    byte ptr [rbx+0F8h], 8
0x14002039d  jz      short loc_1400203A7
0x14002039f  lock dec qword ptr [rbp+8C8h]
0x1400203a7  mov     rcx, [rbx+50h]
0x1400203ab  test    rcx, rcx
0x1400203ae  jz      short loc_1400203C0
0x1400203b0  sub     rcx, 0FFFFFFFFFFFFFF80h; RunRef
0x1400203b4  call    cs:__imp_ExReleaseRundownProtection
0x1400203bb  nop     dword ptr [rax+rax+00h]
0x1400203c0  mov     rcx, [rbx+640h]; P
0x1400203c7  test    rcx, rcx
0x1400203ca  jz      short loc_1400203DD
0x1400203cc  mov     edx, 35336351h; Tag
0x1400203d1  call    cs:__imp_ExFreePoolWithTag
0x1400203d8  nop     dword ptr [rax+rax+00h]
0x1400203dd  or      byte ptr [rbx+0F9h], 4
0x1400203e4  test    cs:byte_14005C489, 40h
0x1400203eb  jz      short loc_1400203FC
0x1400203ed  mov     r8, rbx
0x1400203f0  lea     rdx, QuicConnDestroyed
0x1400203f7  call    McTemplateU0p_EtwWriteTransfer
0x1400203fc  mov     rcx, rbx
0x1400203ff  call    CxPlatPoolFree
0x140020404  lock dec qword ptr [rbp+8C0h]
0x14002040c  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140020410  jz      short loc_140020421
0x140020412  mov     rcx, r15
0x140020415  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14002041c  nop     dword ptr [rax+rax+00h]
0x140020421  test    r14, r14
0x140020424  jz      short loc_140020437
0x140020426  mov     edx, edi; Tag
0x140020428  mov     rcx, r14; Object
0x14002042b  call    cs:__imp_ObfDereferenceObjectWithTag
0x140020432  nop     dword ptr [rax+rax+00h]
0x140020437  mov     rbx, [rsp+38h+arg_0]
0x14002043c  mov     rbp, [rsp+38h+arg_8]
0x140020441  mov     rsi, [rsp+38h+arg_10]
0x140020446  add     rsp, 20h
0x14002044a  pop     r15
0x14002044c  pop     r14
0x14002044e  pop     rdi
0x14002044f  retn
```
