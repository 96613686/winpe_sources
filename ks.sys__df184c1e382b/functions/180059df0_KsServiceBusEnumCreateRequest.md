# KsServiceBusEnumCreateRequest

- ea: `0x180059df0`
- end: `0x18005a259`
- name: `KsServiceBusEnumCreateRequest`
- size: `1129`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, loader_planting, service_task`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x18000dddc`
- `0x180011684`
- `0x1800119f8`
- `0x180059df0`
- `0x18005a260`
- `0x18005a4a8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x180059e71`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x180059e71`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180059e5e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180059e5e`
- `ntoskrnl!_wcsnicmp` at `0x180059eed`
- `ntoskrnl!_wcsnicmp` at `0x180059eed`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x18005a174`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x18005a174`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059eb1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005a156`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005a239`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059eb1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005a156`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005a239`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059ebd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005a162`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005a245`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059ebd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005a162`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005a245`
- `HAL!KeQueryPerformanceCounter` at `0x180059f98`
- `HAL!KeQueryPerformanceCounter` at `0x180059f98`

## pseudocode

```c
NTSTATUS __stdcall KsServiceBusEnumCreateRequest(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  int v2; // r8d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 **v5; // r14
  __int64 *v6; // rdx
  const wchar_t *v7; // rdx
  int v8; // r8d
  __int64 *i; // rbx
  NTSTATUS Pdo; // edi
  int v12; // eax
  LARGE_INTEGER v13; // rax
  LARGE_INTEGER v14; // rcx
  LARGE_INTEGER v15; // rax
  int v16; // edx
  struct _LIST_ENTRY *v17; // rbx
  struct _LIST_ENTRY *v18; // rcx
  struct _LIST_ENTRY *v19; // rbx
  struct _LIST_ENTRY *Blink; // rcx
  __int64 v21; // rax
  unsigned __int64 v22; // r8
  int v23; // [rsp+20h] [rbp-58h]
  __int64 v24; // [rsp+28h] [rbp-50h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v5 = *(__int64 ***)DeviceObject->DeviceExtension;
  v6 = WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v6,
        1,
        53,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_S(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        v2,
        54,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        (__int64)CurrentStackLocation->FileObject->FileName.Buffer);
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v5 + 3));
  for ( i = *v5; ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)v5 )
      goto LABEL_12;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_S(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v7,
        v8,
        55,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        i[12]);
    v7 = (const wchar_t *)i[12];
    if ( v7 )
    {
      if ( !_wcsnicmp(
              (const wchar_t *)CurrentStackLocation->FileObject->FileName.Buffer + 1,
              v7,
              CurrentStackLocation->FileObject->FileName.Length) )
        break;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v7,
      1,
      56,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
  }
  if ( i[6] )
  {
    v12 = *((_DWORD *)i + 14);
    if ( v12 == 2 )
    {
LABEL_12:
      Pdo = -1073741772;
      Irp->IoStatus.Status = -1073741772;
LABEL_13:
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 3));
      KeLeaveCriticalRegion();
      return Pdo;
    }
    if ( v12 >= 4 && *((_DWORD *)i + 20) != 2 )
    {
      Pdo = IssueReparseForIrp(Irp, i);
      goto LABEL_13;
    }
    i[16] = i[15];
    v19 = (struct _LIST_ENTRY *)(i + 4);
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    Blink = v19->Blink;
    if ( Blink->Flink == v19 )
    {
      Pdo = 259;
      Irp->Tail.Overlay.ListEntry.Flink = v19;
      Irp->Tail.Overlay.ListEntry.Blink = Blink;
      Blink->Flink = &Irp->Tail.Overlay.ListEntry;
      v19->Blink = &Irp->Tail.Overlay.ListEntry;
      goto LABEL_13;
    }
LABEL_35:
    __fastfail(3u);
  }
  v13.QuadPart = *(_QWORD *)&KeQueryPerformanceCounter(0) - i[14];
  v14.QuadPart = v13.QuadPart + 0x7FFFFFFFFFFFFFFFLL;
  if ( v13.QuadPart >= 0 )
    v14 = v13;
  v15.QuadPart = i[15];
  if ( v14.QuadPart >= (__int64)v5[94] )
  {
    v21 = v15.QuadPart / 2;
    i[15] = v21;
    if ( v21 <= 15 * (__int64)v5[93] )
      v21 = 15LL * (_QWORD)v5[93];
    i[15] = v21;
  }
  else if ( v14.QuadPart > v15.QuadPart )
  {
    i[15] = v14.QuadPart;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v22 = ((10000000 * (unsigned __int64)*((unsigned int *)i + 31) / (unsigned __int64)v5[93]) << 32)
        + (((10000000 * (unsigned __int64)*((unsigned int *)i + 31) % (unsigned __int64)v5[93]) << 32)
         + 10000000LL * *((unsigned int *)i + 30))
        / (unsigned __int64)v5[93];
    WPP_RECORDER_SF_i(WPP_GLOBAL_Control->DeviceExtension, v22 / 0x2710, v22, 57, v23, v22 / 0x2710);
  }
  Pdo = CreatePdo(v5, i, i + 6);
  if ( Pdo >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v16) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        1,
        59,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        i[6]);
    }
    v17 = (struct _LIST_ENTRY *)(i + 4);
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    v18 = v17->Blink;
    if ( v18->Flink == v17 )
    {
      Irp->Tail.Overlay.ListEntry.Blink = v18;
      Irp->Tail.Overlay.ListEntry.Flink = v17;
      v18->Flink = &Irp->Tail.Overlay.ListEntry;
      v17->Blink = &Irp->Tail.Overlay.ListEntry;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 3));
      KeLeaveCriticalRegion();
      IoInvalidateDeviceRelations((PDEVICE_OBJECT)v5[12], BusRelations);
      return 259;
    }
    goto LABEL_35;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v24) = Pdo;
    LOBYTE(v16) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      1,
      58,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
      v24);
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 3));
  KeLeaveCriticalRegion();
  Irp->IoStatus.Status = Pdo;
  return Pdo;
}

```

## disassembly

```asm
0x180059df0  push    rbx
0x180059df2  push    rbp
0x180059df3  push    rsi
0x180059df4  push    rdi
0x180059df5  push    r12
0x180059df7  push    r13
0x180059df9  push    r14
0x180059dfb  push    r15
0x180059dfd  sub     rsp, 38h
0x180059e01  mov     rax, [rcx+40h]
0x180059e05  mov     rsi, rdx
0x180059e08  mov     rdi, [rdx+0B8h]
0x180059e0f  mov     r14, [rax]
0x180059e12  xor     r12d, r12d
0x180059e15  lea     r13, WPP_RECORDER_INITIALIZED
0x180059e1c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059e23  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059e2a  lea     r15d, [r12+1]
0x180059e2f  jz      short loc_180059E5E
0x180059e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180059e38  cmp     [rcx+48h], r12w
0x180059e3d  jnz     loc_18005A18A
0x180059e43  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059e4a  jz      short loc_180059E5E
0x180059e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180059e53  cmp     [rcx+48h], r12w
0x180059e58  jnz     loc_18005A1AF
0x180059e5e  call    cs:__imp_KeEnterCriticalRegion
0x180059e65  nop     dword ptr [rax+rax+00h]
0x180059e6a  lea     rbp, [r14+18h]
0x180059e6e  mov     rcx, rbp; FastMutex
0x180059e71  call    cs:__imp_ExAcquireFastMutexUnsafe
0x180059e78  nop     dword ptr [rax+rax+00h]
0x180059e7d  mov     rbx, [r14]
0x180059e80  mov     r9d, 2
0x180059e86  cmp     rbx, r14
0x180059e89  jz      short loc_180059EA6
0x180059e8b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059e92  jnz     loc_180059F55
0x180059e98  mov     rdx, [rbx+60h]; Str2
0x180059e9c  test    rdx, rdx
0x180059e9f  jnz     short loc_180059EDD
0x180059ea1  mov     rbx, [rbx]
0x180059ea4  jmp     short loc_180059E80
0x180059ea6  mov     edi, 0C0000034h
0x180059eab  mov     [rsi+30h], edi
0x180059eae  mov     rcx, rbp; FastMutex
0x180059eb1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059eb8  nop     dword ptr [rax+rax+00h]
0x180059ebd  call    cs:__imp_KeLeaveCriticalRegion
0x180059ec4  nop     dword ptr [rax+rax+00h]
0x180059ec9  mov     eax, edi
0x180059ecb  add     rsp, 38h
0x180059ecf  pop     r15
0x180059ed1  pop     r14
0x180059ed3  pop     r13
0x180059ed5  pop     r12
0x180059ed7  pop     rdi
0x180059ed8  pop     rsi
0x180059ed9  pop     rbp
0x180059eda  pop     rbx
0x180059edb  retn
0x180059edd  mov     rax, [rdi+30h]
0x180059ee1  mov     rcx, [rax+60h]
0x180059ee5  movzx   r8d, word ptr [rax+58h]; MaxCount
0x180059eea  add     rcx, r9; Str1
0x180059eed  call    cs:__imp__wcsnicmp
0x180059ef4  nop     dword ptr [rax+rax+00h]
0x180059ef9  test    eax, eax
0x180059efb  jnz     short loc_180059EA1
0x180059efd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059f04  jz      short loc_180059F18
0x180059f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f0d  cmp     [rcx+48h], r12w
0x180059f12  jnz     loc_18005A1D5
0x180059f18  lea     r15, [rbx+30h]
0x180059f1c  cmp     [r15], r12
0x180059f1f  jz      short loc_180059F96
0x180059f21  mov     eax, [rbx+38h]
0x180059f24  mov     ecx, 2
0x180059f29  cmp     eax, ecx
0x180059f2b  jz      loc_180059EA6
0x180059f31  cmp     eax, 4
0x180059f34  jl      loc_18005A027
0x180059f3a  cmp     [rbx+50h], ecx
0x180059f3d  jz      loc_18005A027
0x180059f43  mov     rdx, rbx
0x180059f46  mov     rcx, rsi
0x180059f49  call    IssueReparseForIrp
0x180059f4e  mov     edi, eax
0x180059f50  jmp     loc_180059EAE
0x180059f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f5c  cmp     [rcx+48h], r12w
0x180059f61  jz      loc_180059E98
0x180059f67  mov     rax, [rbx+60h]
0x180059f6b  mov     r9d, 37h ; '7'
0x180059f71  mov     rcx, [rcx+40h]
0x180059f75  mov     [rsp+78h+var_50], rax
0x180059f7a  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059f81  mov     [rsp+78h+var_58], rax
0x180059f86  call    WPP_RECORDER_SF_S
0x180059f8b  mov     r9d, 2
0x180059f91  jmp     loc_180059E98
0x180059f96  xor     ecx, ecx; PerformanceFrequency
0x180059f98  call    cs:__imp_KeQueryPerformanceCounter
0x180059f9f  nop     dword ptr [rax+rax+00h]
0x180059fa4  sub     rax, [rbx+70h]
0x180059fa8  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180059fb2  add     rcx, rax
0x180059fb5  test    rax, rax
0x180059fb8  cmovns  rcx, rax
0x180059fbc  mov     rax, [rbx+78h]
0x180059fc0  cmp     rcx, [r14+2F0h]
0x180059fc7  jge     loc_18005A0A5
0x180059fcd  cmp     rcx, rax
0x180059fd0  jle     short loc_180059FD6
0x180059fd2  mov     [rbx+78h], rcx
0x180059fd6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059fdd  jnz     loc_18005A0CB
0x180059fe3  mov     r8, r15
0x180059fe6  mov     rdx, rbx
0x180059fe9  mov     rcx, r14
0x180059fec  call    CreatePdo
0x180059ff1  mov     edi, eax
0x180059ff3  test    eax, eax
0x180059ff5  js      loc_18005A1FA
0x180059ffb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005a002  jnz     short loc_18005A069
0x18005a004  mov     rax, [rsi+0B8h]
0x18005a00b  add     rbx, 20h ; ' '
0x18005a00f  or      byte ptr [rax+3], 1
0x18005a013  mov     rcx, [rbx+8]
0x18005a017  cmp     [rcx], rbx
0x18005a01a  jz      loc_18005A13E
0x18005a020  mov     ecx, 3
0x18005a025  int     29h; Win8: RtlFailFast(ecx)
0x18005a027  mov     rax, [rbx+78h]
0x18005a02b  mov     [rbx+80h], rax
0x18005a032  add     rbx, 20h ; ' '
0x18005a036  mov     rax, [rsi+0B8h]
0x18005a03d  or      byte ptr [rax+3], 1
0x18005a041  mov     rcx, [rbx+8]
0x18005a045  cmp     [rcx], rbx
0x18005a048  jnz     short loc_18005A020
0x18005a04a  lea     rax, [rsi+0A8h]
0x18005a051  mov     edi, 103h
0x18005a056  mov     [rax], rbx
0x18005a059  mov     [rax+8], rcx
0x18005a05d  mov     [rcx], rax
0x18005a060  mov     [rbx+8], rax
0x18005a064  jmp     loc_180059EAE
0x18005a069  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a070  cmp     [rcx+48h], r12w
0x18005a075  jz      short loc_18005A004
0x18005a077  mov     rax, [r15]
0x18005a07a  mov     r9d, 3Bh ; ';'
0x18005a080  mov     rcx, [rcx+40h]
0x18005a084  mov     dl, 5
0x18005a086  mov     [rsp+78h+var_50], rax
0x18005a08b  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a092  mov     [rsp+78h+var_58], rax
0x18005a097  lea     r8d, [r9-3Ah]
0x18005a09b  call    WPP_RECORDER_SF_q
0x18005a0a0  jmp     loc_18005A004
0x18005a0a5  cqo
0x18005a0a7  mov     ecx, 2
0x18005a0ac  idiv    rcx
0x18005a0af  mov     [rbx+78h], rax
0x18005a0b3  imul    rcx, [r14+2E8h], 0Fh
0x18005a0bb  cmp     rax, rcx
0x18005a0be  cmovle  rax, rcx
0x18005a0c2  mov     [rbx+78h], rax
0x18005a0c6  jmp     loc_180059FD6
0x18005a0cb  mov     r10, cs:WPP_GLOBAL_Control
0x18005a0d2  cmp     [r10+48h], r12w
0x18005a0d7  jz      loc_180059FE3
0x18005a0dd  mov     r8, [r14+2E8h]
0x18005a0e4  xor     edx, edx
0x18005a0e6  mov     eax, [rbx+7Ch]
0x18005a0e9  mov     ecx, [rbx+78h]
0x18005a0ec  imul    rax, 989680h
0x18005a0f3  div     r8
0x18005a0f6  mov     r9, rax
0x18005a0f9  shl     rdx, 20h
0x18005a0fd  imul    rax, rcx, 989680h
0x18005a104  mov     rcx, [r10+40h]
0x18005a108  add     rax, rdx
0x18005a10b  shl     r9, 20h
0x18005a10f  xor     edx, edx
0x18005a111  div     r8
0x18005a114  lea     r8, [r9+rax]
0x18005a118  mov     rax, 346DC5D63886594Bh
0x18005a122  mul     r8
0x18005a125  mov     r9d, 39h ; '9'
0x18005a12b  shr     rdx, 0Bh
0x18005a12f  mov     [rsp+78h+var_50], rdx
0x18005a134  call    WPP_RECORDER_SF_i
0x18005a139  jmp     loc_180059FE3
0x18005a13e  lea     rax, [rsi+0A8h]
0x18005a145  mov     [rax+8], rcx
0x18005a149  mov     [rax], rbx
0x18005a14c  mov     [rcx], rax
0x18005a14f  mov     rcx, rbp; FastMutex
0x18005a152  mov     [rbx+8], rax
0x18005a156  call    cs:__imp_ExReleaseFastMutexUnsafe
0x18005a15d  nop     dword ptr [rax+rax+00h]
0x18005a162  call    cs:__imp_KeLeaveCriticalRegion
0x18005a169  nop     dword ptr [rax+rax+00h]
0x18005a16e  mov     rcx, [r14+60h]; DeviceObject
0x18005a172  xor     edx, edx; Type
0x18005a174  call    cs:__imp_IoInvalidateDeviceRelations
0x18005a17b  nop     dword ptr [rax+rax+00h]
0x18005a180  mov     edi, 103h
0x18005a185  jmp     loc_180059EC9
0x18005a18a  mov     rcx, [rcx+40h]
0x18005a18e  mov     r9d, 35h ; '5'
0x18005a194  mov     [rsp+78h+var_58], rdx
0x18005a199  mov     r8d, r15d
0x18005a19c  mov     dl, 5
0x18005a19e  call    WPP_RECORDER_SF_
0x18005a1a3  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a1aa  jmp     loc_180059E43
0x18005a1af  mov     rax, [rdi+30h]
0x18005a1b3  mov     r9d, 36h ; '6'
0x18005a1b9  mov     rcx, [rcx+40h]
0x18005a1bd  mov     rax, [rax+60h]
0x18005a1c1  mov     [rsp+78h+var_50], rax
0x18005a1c6  mov     [rsp+78h+var_58], rdx
0x18005a1cb  call    WPP_RECORDER_SF_S
0x18005a1d0  jmp     loc_180059E5E
0x18005a1d5  mov     rcx, [rcx+40h]
0x18005a1d9  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a1e0  mov     r9d, 38h ; '8'
0x18005a1e6  mov     [rsp+78h+var_58], rax
0x18005a1eb  mov     r8d, r15d
0x18005a1ee  mov     dl, 5
0x18005a1f0  call    WPP_RECORDER_SF_
0x18005a1f5  jmp     loc_180059F18
0x18005a1fa  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005a201  jz      short loc_18005A236
0x18005a203  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a20a  cmp     [rcx+48h], r12w
0x18005a20f  jz      short loc_18005A236
0x18005a211  mov     rcx, [rcx+40h]
0x18005a215  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a21c  mov     r9d, 3Ah ; ':'
0x18005a222  mov     dword ptr [rsp+78h+var_50], edi
0x18005a226  mov     dl, 5
0x18005a228  mov     [rsp+78h+var_58], rax
0x18005a22d  lea     r8d, [r9-39h]
0x18005a231  call    WPP_RECORDER_SF_D
0x18005a236  mov     rcx, rbp; FastMutex
0x18005a239  call    cs:__imp_ExReleaseFastMutexUnsafe
0x18005a240  nop     dword ptr [rax+rax+00h]
0x18005a245  call    cs:__imp_KeLeaveCriticalRegion
0x18005a24c  nop     dword ptr [rax+rax+00h]
0x18005a251  mov     [rsi+30h], edi
0x18005a254  jmp     loc_180059EC9
```
