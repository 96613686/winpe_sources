# KsServiceBusEnumCreateRequest

- ea: `0x180059c50`
- end: `0x18005a0b9`
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
- `0x180010de4`
- `0x180011158`
- `0x180059c50`
- `0x18005a0c0`
- `0x18005a308`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x180059cd1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x180059cd1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180059cbe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180059cbe`
- `ntoskrnl!_wcsnicmp` at `0x180059d4d`
- `ntoskrnl!_wcsnicmp` at `0x180059d4d`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059fd4`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059fd4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059d11`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059fb6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005a099`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059d11`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059fb6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005a099`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059d1d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059fc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005a0a5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059d1d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059fc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005a0a5`
- `HAL!KeQueryPerformanceCounter` at `0x180059df8`
- `HAL!KeQueryPerformanceCounter` at `0x180059df8`

## pseudocode

```c
NTSTATUS __stdcall KsServiceBusEnumCreateRequest(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  int v2; // r8d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 v5; // r14
  __int64 *v6; // rdx
  const wchar_t *v7; // rdx
  int v8; // r8d
  LARGE_INTEGER i; // rbx
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
  v5 = *(_QWORD *)DeviceObject->DeviceExtension;
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
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v5 + 24));
  for ( i = *(LARGE_INTEGER *)v5; ; i = *(LARGE_INTEGER *)i.QuadPart )
  {
    if ( i.QuadPart == v5 )
      goto LABEL_12;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_S(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v7,
        v8,
        55,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        *(_QWORD *)(i.QuadPart + 96));
    v7 = *(const wchar_t **)(i.QuadPart + 96);
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
  if ( *(_QWORD *)(i.QuadPart + 48) )
  {
    v12 = *(_DWORD *)(i.QuadPart + 56);
    if ( v12 == 2 )
    {
LABEL_12:
      Pdo = -1073741772;
      Irp->IoStatus.Status = -1073741772;
LABEL_13:
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 24));
      KeLeaveCriticalRegion();
      return Pdo;
    }
    if ( v12 >= 4 && *(_DWORD *)(i.QuadPart + 80) != 2 )
    {
      Pdo = ((__int64 (__fastcall *)(_QWORD, _QWORD))IssueReparseForIrp)(Irp, (LARGE_INTEGER)i.QuadPart);
      goto LABEL_13;
    }
    *(_QWORD *)(i.QuadPart + 128) = *(_QWORD *)(i.QuadPart + 120);
    v19 = (struct _LIST_ENTRY *)(i.QuadPart + 32);
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
  v13 = (LARGE_INTEGER)(*(_QWORD *)&KeQueryPerformanceCounter(0) - *(_QWORD *)(i.QuadPart + 112));
  v14.QuadPart = v13.QuadPart + 0x7FFFFFFFFFFFFFFFLL;
  if ( v13.QuadPart >= 0 )
    v14 = v13;
  v15 = *(LARGE_INTEGER *)(i.QuadPart + 120);
  if ( v14.QuadPart >= *(_QWORD *)(v5 + 752) )
  {
    v21 = v15.QuadPart / 2;
    *(_QWORD *)(i.QuadPart + 120) = v21;
    if ( v21 <= 15LL * *(_QWORD *)(v5 + 744) )
      v21 = 15LL * *(_QWORD *)(v5 + 744);
    *(_QWORD *)(i.QuadPart + 120) = v21;
  }
  else if ( v14.QuadPart > v15.QuadPart )
  {
    *(LARGE_INTEGER *)(i.QuadPart + 120) = v14;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v22 = ((10000000 * (unsigned __int64)*(unsigned int *)(i.QuadPart + 124) / *(_QWORD *)(v5 + 744)) << 32)
        + (((10000000 * (unsigned __int64)*(unsigned int *)(i.QuadPart + 124) % *(_QWORD *)(v5 + 744)) << 32)
         + 10000000LL * *(unsigned int *)(i.QuadPart + 120))
        / *(_QWORD *)(v5 + 744);
    WPP_RECORDER_SF_i(WPP_GLOBAL_Control->DeviceExtension, v22 / 0x2710, v22, 57, v23, v22 / 0x2710);
  }
  Pdo = CreatePdo(v5, (LARGE_INTEGER *)i.QuadPart, (PDEVICE_OBJECT *)(i.QuadPart + 48));
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
        *(_QWORD *)(i.QuadPart + 48));
    }
    v17 = (struct _LIST_ENTRY *)(i.QuadPart + 32);
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    v18 = v17->Blink;
    if ( v18->Flink == v17 )
    {
      Irp->Tail.Overlay.ListEntry.Blink = v18;
      Irp->Tail.Overlay.ListEntry.Flink = v17;
      v18->Flink = &Irp->Tail.Overlay.ListEntry;
      v17->Blink = &Irp->Tail.Overlay.ListEntry;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 24));
      KeLeaveCriticalRegion();
      IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(v5 + 96), BusRelations);
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
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 24));
  KeLeaveCriticalRegion();
  Irp->IoStatus.Status = Pdo;
  return Pdo;
}

```

## disassembly

```asm
0x180059c50  push    rbx
0x180059c52  push    rbp
0x180059c53  push    rsi
0x180059c54  push    rdi
0x180059c55  push    r12
0x180059c57  push    r13
0x180059c59  push    r14
0x180059c5b  push    r15
0x180059c5d  sub     rsp, 38h
0x180059c61  mov     rax, [rcx+40h]
0x180059c65  mov     rsi, rdx
0x180059c68  mov     rdi, [rdx+0B8h]
0x180059c6f  mov     r14, [rax]
0x180059c72  xor     r12d, r12d
0x180059c75  lea     r13, WPP_RECORDER_INITIALIZED
0x180059c7c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059c83  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059c8a  lea     r15d, [r12+1]
0x180059c8f  jz      short loc_180059CBE
0x180059c91  mov     rcx, cs:WPP_GLOBAL_Control
0x180059c98  cmp     [rcx+48h], r12w
0x180059c9d  jnz     loc_180059FEA
0x180059ca3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059caa  jz      short loc_180059CBE
0x180059cac  mov     rcx, cs:WPP_GLOBAL_Control
0x180059cb3  cmp     [rcx+48h], r12w
0x180059cb8  jnz     loc_18005A00F
0x180059cbe  call    cs:__imp_KeEnterCriticalRegion
0x180059cc5  nop     dword ptr [rax+rax+00h]
0x180059cca  lea     rbp, [r14+18h]
0x180059cce  mov     rcx, rbp; FastMutex
0x180059cd1  call    cs:__imp_ExAcquireFastMutexUnsafe
0x180059cd8  nop     dword ptr [rax+rax+00h]
0x180059cdd  mov     rbx, [r14]
0x180059ce0  mov     r9d, 2
0x180059ce6  cmp     rbx, r14
0x180059ce9  jz      short loc_180059D06
0x180059ceb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059cf2  jnz     loc_180059DB5
0x180059cf8  mov     rdx, [rbx+60h]; Str2
0x180059cfc  test    rdx, rdx
0x180059cff  jnz     short loc_180059D3D
0x180059d01  mov     rbx, [rbx]
0x180059d04  jmp     short loc_180059CE0
0x180059d06  mov     edi, 0C0000034h
0x180059d0b  mov     [rsi+30h], edi
0x180059d0e  mov     rcx, rbp; FastMutex
0x180059d11  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059d18  nop     dword ptr [rax+rax+00h]
0x180059d1d  call    cs:__imp_KeLeaveCriticalRegion
0x180059d24  nop     dword ptr [rax+rax+00h]
0x180059d29  mov     eax, edi
0x180059d2b  add     rsp, 38h
0x180059d2f  pop     r15
0x180059d31  pop     r14
0x180059d33  pop     r13
0x180059d35  pop     r12
0x180059d37  pop     rdi
0x180059d38  pop     rsi
0x180059d39  pop     rbp
0x180059d3a  pop     rbx
0x180059d3b  retn
0x180059d3d  mov     rax, [rdi+30h]
0x180059d41  mov     rcx, [rax+60h]
0x180059d45  movzx   r8d, word ptr [rax+58h]; MaxCount
0x180059d4a  add     rcx, r9; Str1
0x180059d4d  call    cs:__imp__wcsnicmp
0x180059d54  nop     dword ptr [rax+rax+00h]
0x180059d59  test    eax, eax
0x180059d5b  jnz     short loc_180059D01
0x180059d5d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059d64  jz      short loc_180059D78
0x180059d66  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d6d  cmp     [rcx+48h], r12w
0x180059d72  jnz     loc_18005A035
0x180059d78  lea     r15, [rbx+30h]
0x180059d7c  cmp     [r15], r12
0x180059d7f  jz      short loc_180059DF6
0x180059d81  mov     eax, [rbx+38h]
0x180059d84  mov     ecx, 2
0x180059d89  cmp     eax, ecx
0x180059d8b  jz      loc_180059D06
0x180059d91  cmp     eax, 4
0x180059d94  jl      loc_180059E87
0x180059d9a  cmp     [rbx+50h], ecx
0x180059d9d  jz      loc_180059E87
0x180059da3  mov     rdx, rbx
0x180059da6  mov     rcx, rsi
0x180059da9  call    IssueReparseForIrp
0x180059dae  mov     edi, eax
0x180059db0  jmp     loc_180059D0E
0x180059db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180059dbc  cmp     [rcx+48h], r12w
0x180059dc1  jz      loc_180059CF8
0x180059dc7  mov     rax, [rbx+60h]
0x180059dcb  mov     r9d, 37h ; '7'
0x180059dd1  mov     rcx, [rcx+40h]
0x180059dd5  mov     [rsp+78h+var_50], rax
0x180059dda  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059de1  mov     [rsp+78h+var_58], rax
0x180059de6  call    WPP_RECORDER_SF_S
0x180059deb  mov     r9d, 2
0x180059df1  jmp     loc_180059CF8
0x180059df6  xor     ecx, ecx; PerformanceFrequency
0x180059df8  call    cs:__imp_KeQueryPerformanceCounter
0x180059dff  nop     dword ptr [rax+rax+00h]
0x180059e04  sub     rax, [rbx+70h]
0x180059e08  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180059e12  add     rcx, rax
0x180059e15  test    rax, rax
0x180059e18  cmovns  rcx, rax
0x180059e1c  mov     rax, [rbx+78h]
0x180059e20  cmp     rcx, [r14+2F0h]
0x180059e27  jge     loc_180059F05
0x180059e2d  cmp     rcx, rax
0x180059e30  jle     short loc_180059E36
0x180059e32  mov     [rbx+78h], rcx
0x180059e36  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059e3d  jnz     loc_180059F2B
0x180059e43  mov     r8, r15
0x180059e46  mov     rdx, rbx
0x180059e49  mov     rcx, r14
0x180059e4c  call    CreatePdo
0x180059e51  mov     edi, eax
0x180059e53  test    eax, eax
0x180059e55  js      loc_18005A05A
0x180059e5b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180059e62  jnz     short loc_180059EC9
0x180059e64  mov     rax, [rsi+0B8h]
0x180059e6b  add     rbx, 20h ; ' '
0x180059e6f  or      byte ptr [rax+3], 1
0x180059e73  mov     rcx, [rbx+8]
0x180059e77  cmp     [rcx], rbx
0x180059e7a  jz      loc_180059F9E
0x180059e80  mov     ecx, 3
0x180059e85  int     29h; Win8: RtlFailFast(ecx)
0x180059e87  mov     rax, [rbx+78h]
0x180059e8b  mov     [rbx+80h], rax
0x180059e92  add     rbx, 20h ; ' '
0x180059e96  mov     rax, [rsi+0B8h]
0x180059e9d  or      byte ptr [rax+3], 1
0x180059ea1  mov     rcx, [rbx+8]
0x180059ea5  cmp     [rcx], rbx
0x180059ea8  jnz     short loc_180059E80
0x180059eaa  lea     rax, [rsi+0A8h]
0x180059eb1  mov     edi, 103h
0x180059eb6  mov     [rax], rbx
0x180059eb9  mov     [rax+8], rcx
0x180059ebd  mov     [rcx], rax
0x180059ec0  mov     [rbx+8], rax
0x180059ec4  jmp     loc_180059D0E
0x180059ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180059ed0  cmp     [rcx+48h], r12w
0x180059ed5  jz      short loc_180059E64
0x180059ed7  mov     rax, [r15]
0x180059eda  mov     r9d, 3Bh ; ';'
0x180059ee0  mov     rcx, [rcx+40h]
0x180059ee4  mov     dl, 5
0x180059ee6  mov     [rsp+78h+var_50], rax
0x180059eeb  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059ef2  mov     [rsp+78h+var_58], rax
0x180059ef7  lea     r8d, [r9-3Ah]
0x180059efb  call    WPP_RECORDER_SF_q
0x180059f00  jmp     loc_180059E64
0x180059f05  cqo
0x180059f07  mov     ecx, 2
0x180059f0c  idiv    rcx
0x180059f0f  mov     [rbx+78h], rax
0x180059f13  imul    rcx, [r14+2E8h], 0Fh
0x180059f1b  cmp     rax, rcx
0x180059f1e  cmovle  rax, rcx
0x180059f22  mov     [rbx+78h], rax
0x180059f26  jmp     loc_180059E36
0x180059f2b  mov     r10, cs:WPP_GLOBAL_Control
0x180059f32  cmp     [r10+48h], r12w
0x180059f37  jz      loc_180059E43
0x180059f3d  mov     r8, [r14+2E8h]
0x180059f44  xor     edx, edx
0x180059f46  mov     eax, [rbx+7Ch]
0x180059f49  mov     ecx, [rbx+78h]
0x180059f4c  imul    rax, 989680h
0x180059f53  div     r8
0x180059f56  mov     r9, rax
0x180059f59  shl     rdx, 20h
0x180059f5d  imul    rax, rcx, 989680h
0x180059f64  mov     rcx, [r10+40h]
0x180059f68  add     rax, rdx
0x180059f6b  shl     r9, 20h
0x180059f6f  xor     edx, edx
0x180059f71  div     r8
0x180059f74  lea     r8, [r9+rax]
0x180059f78  mov     rax, 346DC5D63886594Bh
0x180059f82  mul     r8
0x180059f85  mov     r9d, 39h ; '9'
0x180059f8b  shr     rdx, 0Bh
0x180059f8f  mov     [rsp+78h+var_50], rdx
0x180059f94  call    WPP_RECORDER_SF_i
0x180059f99  jmp     loc_180059E43
0x180059f9e  lea     rax, [rsi+0A8h]
0x180059fa5  mov     [rax+8], rcx
0x180059fa9  mov     [rax], rbx
0x180059fac  mov     [rcx], rax
0x180059faf  mov     rcx, rbp; FastMutex
0x180059fb2  mov     [rbx+8], rax
0x180059fb6  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059fbd  nop     dword ptr [rax+rax+00h]
0x180059fc2  call    cs:__imp_KeLeaveCriticalRegion
0x180059fc9  nop     dword ptr [rax+rax+00h]
0x180059fce  mov     rcx, [r14+60h]; DeviceObject
0x180059fd2  xor     edx, edx; Type
0x180059fd4  call    cs:__imp_IoInvalidateDeviceRelations
0x180059fdb  nop     dword ptr [rax+rax+00h]
0x180059fe0  mov     edi, 103h
0x180059fe5  jmp     loc_180059D29
0x180059fea  mov     rcx, [rcx+40h]
0x180059fee  mov     r9d, 35h ; '5'
0x180059ff4  mov     [rsp+78h+var_58], rdx
0x180059ff9  mov     r8d, r15d
0x180059ffc  mov     dl, 5
0x180059ffe  call    WPP_RECORDER_SF_
0x18005a003  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a00a  jmp     loc_180059CA3
0x18005a00f  mov     rax, [rdi+30h]
0x18005a013  mov     r9d, 36h ; '6'
0x18005a019  mov     rcx, [rcx+40h]
0x18005a01d  mov     rax, [rax+60h]
0x18005a021  mov     [rsp+78h+var_50], rax
0x18005a026  mov     [rsp+78h+var_58], rdx
0x18005a02b  call    WPP_RECORDER_SF_S
0x18005a030  jmp     loc_180059CBE
0x18005a035  mov     rcx, [rcx+40h]
0x18005a039  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a040  mov     r9d, 38h ; '8'
0x18005a046  mov     [rsp+78h+var_58], rax
0x18005a04b  mov     r8d, r15d
0x18005a04e  mov     dl, 5
0x18005a050  call    WPP_RECORDER_SF_
0x18005a055  jmp     loc_180059D78
0x18005a05a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005a061  jz      short loc_18005A096
0x18005a063  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a06a  cmp     [rcx+48h], r12w
0x18005a06f  jz      short loc_18005A096
0x18005a071  mov     rcx, [rcx+40h]
0x18005a075  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a07c  mov     r9d, 3Ah ; ':'
0x18005a082  mov     dword ptr [rsp+78h+var_50], edi
0x18005a086  mov     dl, 5
0x18005a088  mov     [rsp+78h+var_58], rax
0x18005a08d  lea     r8d, [r9-39h]
0x18005a091  call    WPP_RECORDER_SF_D
0x18005a096  mov     rcx, rbp; FastMutex
0x18005a099  call    cs:__imp_ExReleaseFastMutexUnsafe
0x18005a0a0  nop     dword ptr [rax+rax+00h]
0x18005a0a5  call    cs:__imp_KeLeaveCriticalRegion
0x18005a0ac  nop     dword ptr [rax+rax+00h]
0x18005a0b1  mov     [rsi+30h], edi
0x18005a0b4  jmp     loc_180059D29
```
