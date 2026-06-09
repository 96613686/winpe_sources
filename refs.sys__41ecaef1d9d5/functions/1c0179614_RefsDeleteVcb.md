# RefsDeleteVcb

- ea: `0x1c0179614`
- end: `0x1c0179929`
- name: `RefsDeleteVcb`
- size: `789`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1c003cac4`

## callees

- `0x1c00045c4`
- `0x1c0062858`
- `0x1c00628f4`
- `0x1c016556c`
- `0x1c0165a48`
- `0x1c0171fc0`
- `0x1c0179614`
- `0x1c0179930`
- `0x1c01799b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c017976e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0179798`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01797d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017980d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017987a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c018b00f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c018b032`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017976e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0179798`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01797d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017980d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017987a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c018b00f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c018b032`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01798bd`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01798bd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01796e3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c018afd5`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01796e3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c018afd5`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017971f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017971f`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c017982e`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c017985a`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c01798d3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c017982e`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c017985a`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c01798d3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c0179673`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c0179692`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c01796b1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c0179673`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c0179692`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c01796b1`
- `ntoskrnl!FsRtlHeatUninit` at `0x1c018af10`
- `ntoskrnl!FsRtlHeatUninit` at `0x1c018af10`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x1c01797b8`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x1c01797b8`
- `ntoskrnl!MmFreeMappingAddress` at `0x1c01798a7`
- `ntoskrnl!MmFreeMappingAddress` at `0x1c01798a7`
- `ntoskrnl!IoDeleteDevice` at `0x1c0179902`
- `ntoskrnl!IoDeleteDevice` at `0x1c0179902`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1c01796fd`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1c01796fd`
- `ntoskrnl!ExDeleteFastResource` at `0x1c0179844`
- `ntoskrnl!ExDeleteFastResource` at `0x1c0179844`

## pseudocode

```c
char __fastcall RefsDeleteVcb(__int64 a1, _QWORD *a2)
{
  struct _DEVICE_OBJECT *v4; // r12
  __int64 v5; // rax
  __int64 v6; // rcx
  struct _FAST_MUTEX *v7; // rcx
  _QWORD *v8; // rax
  _QWORD *v9; // rsi
  struct _FAST_MUTEX *v10; // rcx
  __int64 v11; // rcx
  wchar_t *v12; // rax
  __int64 v13; // rsi
  PVOID *i; // rbx
  __int64 v15; // rcx
  char result; // al
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  _QWORD *v19; // r14
  _QWORD *v20; // rbx
  __int64 v21; // rdx
  _QWORD *v22; // rbx
  _QWORD *v23; // [rsp+20h] [rbp-10h] BYREF
  char v24; // [rsp+78h] [rbp+48h] BYREF
  __int64 v25; // [rsp+80h] [rbp+50h] BYREF
  PVOID RestartKey; // [rsp+88h] [rbp+58h] BYREF

  RefsDeletePerVolumeTelemetry(*a2);
  v4 = (struct _DEVICE_OBJECT *)(*a2 - 336LL);
  if ( (*(_DWORD *)(*a2 + 24LL) & 0x20) != 0 )
    FsRtlHeatUninit(*a2 + 3820LL, *a2 + 3832LL);
  NtOfsPurgeSecurityCache();
  *(_BYTE *)(*a2 + 3817LL) = 1;
  v5 = *a2;
  if ( *(_QWORD *)(*a2 + 3616LL) )
  {
    RtlFreeUnicodeString((PUNICODE_STRING)(v5 + 3608));
    v5 = *a2;
  }
  if ( *(_QWORD *)(v5 + 3632) )
  {
    RtlFreeUnicodeString((PUNICODE_STRING)(v5 + 3624));
    v5 = *a2;
  }
  if ( *(_QWORD *)(v5 + 3472) )
  {
    RtlFreeUnicodeString((PUNICODE_STRING)(v5 + 3464));
    v5 = *a2;
  }
  v6 = *(_QWORD *)(v5 + 200);
  if ( v6 )
  {
    *(_DWORD *)(v6 + 4) &= 0xFFFFFFF3;
    RefsFullDeleteLcb(0, *a2 + 200LL);
    *(_QWORD *)(*a2 + 200LL) = 0;
  }
  while ( 1 )
  {
    v7 = (struct _FAST_MUTEX *)(*a2 + 536LL);
    v24 = 0;
    RestartKey = 0;
    KeAcquireGuardedMutex(v7);
    v8 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)(*a2 + 704LL), &RestartKey);
    v9 = v8;
    if ( v8 )
      v9 = (_QWORD *)v8[2];
    v10 = (struct _FAST_MUTEX *)(*a2 + 536LL);
    v23 = v9;
    KeReleaseGuardedMutex(v10);
    if ( !v9 )
      break;
    RefsAcquireExclusiveFcb(a1, v9, 0, 1);
    v17 = v9 + 7;
    while ( 1 )
    {
      v18 = *v17 - 104LL;
      if ( (_QWORD *)*v17 == v17 )
        v18 = 0;
      v25 = v18;
      if ( !v18 )
        break;
      RefsDeleteScb(a1, &v25);
    }
    v19 = v9 + 5;
    while ( 1 )
    {
      v20 = (_QWORD *)*v19;
      if ( (_QWORD *)*v19 == v19 )
        break;
      v21 = *(v20 - 2);
      v22 = v20 - 5;
      v25 = (__int64)v22;
      RefsAcquireExclusiveFcb(a1, *(_QWORD *)(v21 + 120), 0, 1);
      RefsFullDeleteLcb(v22[3], &v25);
    }
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*a2 + 536LL));
    v24 = 0;
    v9[28] = &v24;
    LOBYTE(v25) = 1;
    RefsDeleteFcb(a1, &v23, &v25);
  }
  *(_QWORD *)(*a2 + 672LL) = 0;
  v11 = *a2;
  v12 = *(wchar_t **)(*a2 + 2560LL);
  if ( v12 && v12 != L"$STANDARD_INFORMATION" )
  {
    ExFreePoolWithTag(*(PVOID *)(*a2 + 2560LL), 0);
    *(_QWORD *)(*a2 + 2560LL) = 0;
    v11 = *a2;
  }
  if ( *(_QWORD *)(v11 + 696) )
  {
    ExFreePoolWithTag(*(PVOID *)(v11 + 696), 0);
    *(_QWORD *)(*a2 + 696LL) = 0;
    v11 = *a2;
  }
  if ( *(_QWORD *)(v11 + 8248) )
  {
    ExFreePoolWithTag(*(PVOID *)(v11 + 8248), 0);
    *(_QWORD *)(*a2 + 8248LL) = 0;
    v11 = *a2;
  }
  FsRtlNotifyUninitializeSync((PNOTIFY_SYNC *)(v11 + 824));
  v13 = *a2;
  if ( (*(_DWORD *)(*a2 + 4LL) & 0x400) != 0 )
  {
    ExFreePoolWithTag(*(PVOID *)(v13 + 208), 0);
    *(_QWORD *)(*a2 + 208LL) = 0;
    v13 = *a2;
  }
  for ( i = (PVOID *)(v13 + 2816); *i; ++i )
  {
    ExFreePoolWithTag(*i, 0);
    *i = 0;
    if ( i == (PVOID *)(v13 + 3064) )
      break;
  }
  ExDeleteResourceLite((PERESOURCE)(v13 + 2712));
  ExDeleteFastResource(*a2 + 1424LL);
  ExDeleteResourceLite((PERESOURCE)(*a2 + 3480LL));
  v15 = *a2;
  if ( *(_QWORD *)(*a2 + 680LL) )
  {
    ExFreePoolWithTag(*(PVOID *)(*a2 + 680LL), 0);
    *(_QWORD *)(*a2 + 680LL) = 0;
    v15 = *a2;
  }
  if ( *(_QWORD *)(v15 + 3256) )
  {
    MmFreeMappingAddress(*(PVOID *)(v15 + 3256), 0x62666552u);
    v15 = *a2;
  }
  ObfDereferenceObject(*(PVOID *)(v15 + 192));
  ExDeleteResourceLite((PERESOURCE)(*a2 + 1176LL));
  if ( *(_QWORD *)(*a2 + 2608LL) )
  {
    ExFreePoolWithTag(*(PVOID *)(*a2 + 2608LL), 0);
    *(_QWORD *)(*a2 + 2608LL) = 0;
  }
  MsKmeDeleteReservedIoRequestsForVcb();
  MsKmeDeleteReservedIoRunsForVcb(*a2);
  IoDeleteDevice(v4);
  result = 1;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x1c0179614  mov     [rsp-38h+arg_0], rbx
0x1c0179619  push    rbp
0x1c017961a  push    rsi
0x1c017961b  push    rdi
0x1c017961c  push    r12
0x1c017961e  push    r13
0x1c0179620  push    r14
0x1c0179622  push    r15
0x1c0179624  mov     rbp, rsp
0x1c0179627  sub     rsp, 30h
0x1c017962b  mov     r15, rcx
0x1c017962e  mov     rdi, rdx
0x1c0179631  mov     rcx, [rdx]
0x1c0179634  call    RefsDeletePerVolumeTelemetry
0x1c0179639  mov     rcx, [rdi]
0x1c017963c  mov     eax, [rcx+18h]
0x1c017963f  lea     r12, [rcx-150h]
0x1c0179646  test    al, 20h
0x1c0179648  jnz     loc_1C018AF02
0x1c017964e  call    NtOfsPurgeSecurityCache
0x1c0179653  mov     rax, [rdi]
0x1c0179656  xor     r13d, r13d
0x1c0179659  mov     byte ptr [rax+0EE9h], 1
0x1c0179660  mov     rax, [rdi]
0x1c0179663  cmp     [rax+0E20h], r13
0x1c017966a  jz      short loc_1C0179682
0x1c017966c  lea     rcx, [rax+0E18h]; UnicodeString
0x1c0179673  call    cs:__imp_RtlFreeUnicodeString
0x1c017967a  nop     dword ptr [rax+rax+00h]
0x1c017967f  mov     rax, [rdi]
0x1c0179682  cmp     [rax+0E30h], r13
0x1c0179689  jz      short loc_1C01796A1
0x1c017968b  lea     rcx, [rax+0E28h]; UnicodeString
0x1c0179692  call    cs:__imp_RtlFreeUnicodeString
0x1c0179699  nop     dword ptr [rax+rax+00h]
0x1c017969e  mov     rax, [rdi]
0x1c01796a1  cmp     [rax+0D90h], r13
0x1c01796a8  jz      short loc_1C01796C0
0x1c01796aa  lea     rcx, [rax+0D88h]; UnicodeString
0x1c01796b1  call    cs:__imp_RtlFreeUnicodeString
0x1c01796b8  nop     dword ptr [rax+rax+00h]
0x1c01796bd  mov     rax, [rdi]
0x1c01796c0  mov     rcx, [rax+0C8h]
0x1c01796c7  test    rcx, rcx
0x1c01796ca  jnz     loc_1C018AF24
0x1c01796d0  mov     ebx, 218h
0x1c01796d5  mov     rcx, [rdi]
0x1c01796d8  add     rcx, rbx; Mutex
0x1c01796db  mov     [rbp+arg_8], r13b
0x1c01796df  mov     [rbp+RestartKey], r13
0x1c01796e3  call    cs:__imp_KeAcquireGuardedMutex
0x1c01796ea  nop     dword ptr [rax+rax+00h]
0x1c01796ef  mov     rcx, [rdi]
0x1c01796f2  lea     rdx, [rbp+RestartKey]; RestartKey
0x1c01796f6  add     rcx, 2C0h; Table
0x1c01796fd  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1c0179704  nop     dword ptr [rax+rax+00h]
0x1c0179709  mov     rsi, rax
0x1c017970c  test    rax, rax
0x1c017970f  jnz     loc_1C018AF48
0x1c0179715  mov     rcx, [rdi]
0x1c0179718  add     rcx, rbx; Mutex
0x1c017971b  mov     [rbp+var_10], rsi
0x1c017971f  call    cs:__imp_KeReleaseGuardedMutex
0x1c0179726  nop     dword ptr [rax+rax+00h]
0x1c017972b  test    rsi, rsi
0x1c017972e  jnz     loc_1C018AF51
0x1c0179734  mov     rax, [rdi]
0x1c0179737  mov     [rax+2A0h], r13
0x1c017973e  mov     rcx, [rdi]
0x1c0179741  mov     rax, [rcx+0A00h]
0x1c0179748  test    rax, rax
0x1c017974b  jz      short loc_1C017975D
0x1c017974d  lea     rdx, RefsAttributeDefinitions; "$STANDARD_INFORMATION"
0x1c0179754  cmp     rax, rdx
0x1c0179757  jnz     loc_1C018B00A
0x1c017975d  mov     rax, [rcx+2B8h]
0x1c0179764  test    rax, rax
0x1c0179767  jz      short loc_1C0179787
0x1c0179769  xor     edx, edx; Tag
0x1c017976b  mov     rcx, rax; P
0x1c017976e  call    cs:__imp_ExFreePoolWithTag
0x1c0179775  nop     dword ptr [rax+rax+00h]
0x1c017977a  mov     rax, [rdi]
0x1c017977d  mov     [rax+2B8h], r13
0x1c0179784  mov     rcx, [rdi]
0x1c0179787  mov     rax, [rcx+2038h]
0x1c017978e  test    rax, rax
0x1c0179791  jz      short loc_1C01797B1
0x1c0179793  xor     edx, edx; Tag
0x1c0179795  mov     rcx, rax; P
0x1c0179798  call    cs:__imp_ExFreePoolWithTag
0x1c017979f  nop     dword ptr [rax+rax+00h]
0x1c01797a4  mov     rax, [rdi]
0x1c01797a7  mov     [rax+2038h], r13
0x1c01797ae  mov     rcx, [rdi]
0x1c01797b1  add     rcx, 338h; NotifySync
0x1c01797b8  call    cs:__imp_FsRtlNotifyUninitializeSync
0x1c01797bf  nop     dword ptr [rax+rax+00h]
0x1c01797c4  mov     rsi, [rdi]
0x1c01797c7  test    dword ptr [rsi+4], 400h
0x1c01797ce  jz      short loc_1C01797F2
0x1c01797d0  mov     rcx, [rsi+0D0h]; P
0x1c01797d7  xor     edx, edx; Tag
0x1c01797d9  call    cs:__imp_ExFreePoolWithTag
0x1c01797e0  nop     dword ptr [rax+rax+00h]
0x1c01797e5  mov     rax, [rdi]
0x1c01797e8  mov     [rax+0D0h], r13
0x1c01797ef  mov     rsi, [rdi]
0x1c01797f2  lea     rbx, [rsi+0B00h]
0x1c01797f9  lea     r14, [rsi+0BF8h]
0x1c0179800  mov     rax, [rbx]
0x1c0179803  test    rax, rax
0x1c0179806  jz      short loc_1C0179827
0x1c0179808  xor     edx, edx; Tag
0x1c017980a  mov     rcx, rax; P
0x1c017980d  call    cs:__imp_ExFreePoolWithTag
0x1c0179814  nop     dword ptr [rax+rax+00h]
0x1c0179819  mov     [rbx], r13
0x1c017981c  cmp     rbx, r14
0x1c017981f  jz      short loc_1C0179827
0x1c0179821  add     rbx, 8
0x1c0179825  jmp     short loc_1C0179800
0x1c0179827  lea     rcx, [rsi+0A98h]; Resource
0x1c017982e  call    cs:__imp_ExDeleteResourceLite
0x1c0179835  nop     dword ptr [rax+rax+00h]
0x1c017983a  mov     rcx, [rdi]
0x1c017983d  add     rcx, 590h
0x1c0179844  call    cs:__imp_ExDeleteFastResource
0x1c017984b  nop     dword ptr [rax+rax+00h]
0x1c0179850  mov     rcx, [rdi]
0x1c0179853  add     rcx, 0D98h; Resource
0x1c017985a  call    cs:__imp_ExDeleteResourceLite
0x1c0179861  nop     dword ptr [rax+rax+00h]
0x1c0179866  mov     rcx, [rdi]
0x1c0179869  mov     rax, [rcx+2A8h]
0x1c0179870  test    rax, rax
0x1c0179873  jz      short loc_1C0179893
0x1c0179875  xor     edx, edx; Tag
0x1c0179877  mov     rcx, rax; P
0x1c017987a  call    cs:__imp_ExFreePoolWithTag
0x1c0179881  nop     dword ptr [rax+rax+00h]
0x1c0179886  mov     rax, [rdi]
0x1c0179889  mov     [rax+2A8h], r13
0x1c0179890  mov     rcx, [rdi]
0x1c0179893  mov     rax, [rcx+0CB8h]
0x1c017989a  test    rax, rax
0x1c017989d  jz      short loc_1C01798B6
0x1c017989f  mov     edx, 62666552h; PoolTag
0x1c01798a4  mov     rcx, rax; BaseAddress
0x1c01798a7  call    cs:__imp_MmFreeMappingAddress
0x1c01798ae  nop     dword ptr [rax+rax+00h]
0x1c01798b3  mov     rcx, [rdi]
0x1c01798b6  mov     rcx, [rcx+0C0h]; Object
0x1c01798bd  call    cs:__imp_ObfDereferenceObject
0x1c01798c4  nop     dword ptr [rax+rax+00h]
0x1c01798c9  mov     rcx, [rdi]
0x1c01798cc  add     rcx, 498h; Resource
0x1c01798d3  call    cs:__imp_ExDeleteResourceLite
0x1c01798da  nop     dword ptr [rax+rax+00h]
0x1c01798df  mov     rcx, [rdi]
0x1c01798e2  mov     r8, [rcx+0A30h]
0x1c01798e9  test    r8, r8
0x1c01798ec  jnz     loc_1C018B02D
0x1c01798f2  call    MsKmeDeleteReservedIoRequestsForVcb
0x1c01798f7  mov     rcx, [rdi]
0x1c01798fa  call    MsKmeDeleteReservedIoRunsForVcb
0x1c01798ff  mov     rcx, r12; DeviceObject
0x1c0179902  call    cs:__imp_IoDeleteDevice
0x1c0179909  nop     dword ptr [rax+rax+00h]
0x1c017990e  mov     rbx, [rsp+30h+arg_0]
0x1c0179913  mov     al, 1
0x1c0179915  mov     [rdi], r13
0x1c0179918  add     rsp, 30h
0x1c017991c  pop     r15
0x1c017991e  pop     r14
0x1c0179920  pop     r13
0x1c0179922  pop     r12
0x1c0179924  pop     rdi
0x1c0179925  pop     rsi
0x1c0179926  pop     rbp
0x1c0179927  retn
0x1c018af02  lea     rdx, [rcx+0EF8h]
0x1c018af09  add     rcx, 0EECh
0x1c018af10  call    cs:__imp_FsRtlHeatUninit
0x1c018af17  nop     dword ptr [rax+rax+00h]
0x1c018af1c  mov     rcx, [rdi]
0x1c018af1f  jmp     loc_1C017964E
0x1c018af24  and     dword ptr [rcx+4], 0FFFFFFF3h
0x1c018af28  xor     ecx, ecx
0x1c018af2a  mov     rdx, [rdi]
0x1c018af2d  add     rdx, 0C8h
0x1c018af34  call    RefsFullDeleteLcb
0x1c018af39  mov     rax, [rdi]
0x1c018af3c  mov     [rax+0C8h], r13
0x1c018af43  jmp     loc_1C01796D0
0x1c018af48  mov     rsi, [rax+10h]
0x1c018af4c  jmp     loc_1C0179715
0x1c018af51  mov     r9d, 1
0x1c018af57  xor     r8d, r8d
0x1c018af5a  mov     rdx, rsi
0x1c018af5d  mov     rcx, r15
0x1c018af60  call    RefsAcquireExclusiveFcb
0x1c018af65  lea     rbx, [rsi+38h]
0x1c018af69  mov     rax, [rbx]
0x1c018af6c  cmp     rax, rbx
0x1c018af6f  lea     rcx, [rax-68h]
0x1c018af73  cmovz   rcx, r13
0x1c018af77  mov     [rbp+arg_10], rcx
0x1c018af7b  test    rcx, rcx
0x1c018af7e  jz      short loc_1C018AF8E
0x1c018af80  lea     rdx, [rbp+arg_10]
0x1c018af84  mov     rcx, r15
0x1c018af87  call    RefsDeleteScb
0x1c018af8c  jmp     short loc_1C018AF69
0x1c018af8e  lea     r14, [rsi+28h]
0x1c018af92  mov     rbx, [r14]
0x1c018af95  cmp     rbx, r14
0x1c018af98  jz      short loc_1C018AFCA
0x1c018af9a  mov     rdx, [rbx-10h]
0x1c018af9e  add     rbx, 0FFFFFFFFFFFFFFD8h
0x1c018afa2  mov     r9d, 1
0x1c018afa8  mov     [rbp+arg_10], rbx
0x1c018afac  xor     r8d, r8d
0x1c018afaf  mov     rcx, r15
0x1c018afb2  mov     rdx, [rdx+78h]
0x1c018afb6  call    RefsAcquireExclusiveFcb
0x1c018afbb  mov     rcx, [rbx+18h]
0x1c018afbf  lea     rdx, [rbp+arg_10]
0x1c018afc3  call    RefsFullDeleteLcb
0x1c018afc8  jmp     short loc_1C018AF92
0x1c018afca  mov     rcx, [rdi]
0x1c018afcd  mov     ebx, 218h
0x1c018afd2  add     rcx, rbx; Mutex
0x1c018afd5  call    cs:__imp_KeAcquireGuardedMutex
0x1c018afdc  nop     dword ptr [rax+rax+00h]
0x1c018afe1  lea     rax, [rbp+arg_8]
0x1c018afe5  mov     [rbp+arg_8], r13b
0x1c018afe9  lea     r8, [rbp+arg_10]
0x1c018afed  mov     [rsi+0E0h], rax
0x1c018aff4  lea     rdx, [rbp+var_10]
0x1c018aff8  mov     byte ptr [rbp+arg_10], 1
0x1c018affc  mov     rcx, r15
0x1c018afff  call    RefsDeleteFcb
0x1c018b004  nop
0x1c018b005  jmp     loc_1C01796D5
0x1c018b00a  xor     edx, edx; Tag
0x1c018b00c  mov     rcx, rax; P
0x1c018b00f  call    cs:__imp_ExFreePoolWithTag
0x1c018b016  nop     dword ptr [rax+rax+00h]
0x1c018b01b  mov     rax, [rdi]
0x1c018b01e  mov     [rax+0A00h], r13
0x1c018b025  mov     rcx, [rdi]
0x1c018b028  jmp     loc_1C017975D
0x1c018b02d  xor     edx, edx; Tag
0x1c018b02f  mov     rcx, r8; P
0x1c018b032  call    cs:__imp_ExFreePoolWithTag
0x1c018b039  nop     dword ptr [rax+rax+00h]
0x1c018b03e  mov     rdx, [rdi]
0x1c018b041  mov     [rdx+0A30h], r13
0x1c018b048  mov     rcx, [rdi]
0x1c018b04b  jmp     loc_1C01798F2
```
