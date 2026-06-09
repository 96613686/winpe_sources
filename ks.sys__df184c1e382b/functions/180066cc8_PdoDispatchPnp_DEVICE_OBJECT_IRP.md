# PdoDispatchPnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180066cc8`
- end: `0x180066f50`
- name: `?PdoDispatchPnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `648`
- prototype: `NTSTATUS __fastcall(struct _DEVICE_OBJECT *Object, PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048c60`

## callees

- `0x18000da50`
- `0x18000dddc`
- `0x18000f544`
- `0x18003b4bc`
- `0x180066cc8`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x180066e30`
- `ntoskrnl!ObfReferenceObject` at `0x180066e30`
- `ntoskrnl!IofCallDriver` at `0x180066f3a`
- `ntoskrnl!IofCallDriver` at `0x180066f3a`
- `ntoskrnl!IoDeleteDevice` at `0x180066d91`
- `ntoskrnl!IoDeleteDevice` at `0x180066d91`
- `ntoskrnl!IofCompleteRequest` at `0x180066eb7`
- `ntoskrnl!IofCompleteRequest` at `0x180066eb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066d82`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066d82`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180066e0b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180066e0b`

## pseudocode

```c
NTSTATUS __fastcall PdoDispatchPnp(struct _DEVICE_OBJECT *Object, PIRP Irp)
{
  PVOID DeviceExtension; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  NTSTATUS Status; // ebx
  unsigned int MinorFunction; // r8d
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  void *v10; // rcx
  _OWORD *PoolWithTag; // rax
  ULONG_PTR v12; // rsi
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  __m128i si128; // xmm0

  DeviceExtension = Object->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Status = 0;
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( MinorFunction <= 7 )
  {
    if ( MinorFunction != 7 )
    {
      if ( !CurrentStackLocation->MinorFunction )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(CurrentStackLocation) = 5;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)CurrentStackLocation,
            1,
            20,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
            (char)Object,
            *((_BYTE *)DeviceExtension + 44));
        }
        *((_BYTE *)DeviceExtension + 44) = 0;
        goto LABEL_34;
      }
      v8 = MinorFunction - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( !v9 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(CurrentStackLocation) = 5;
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)CurrentStackLocation,
              1,
              21,
              (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
              (char)Object);
          }
          if ( *((_BYTE *)DeviceExtension + 44) )
          {
            v10 = (void *)*((_QWORD *)DeviceExtension + 4);
            if ( v10 )
              ExFreePoolWithTag(v10, 0);
            IoDeleteDevice(Object);
          }
          goto LABEL_34;
        }
        if ( v9 - 2 >= 2 )
          goto LABEL_31;
      }
LABEL_34:
      Irp->IoStatus.Status = Status;
      IofCompleteRequest(Irp, 0);
      return Status;
    }
    if ( CurrentStackLocation->Parameters.Read.Length != 4 )
    {
LABEL_31:
      Status = Irp->IoStatus.Status;
      goto LABEL_34;
    }
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, 0x10u, 0x7264534Bu);
    v12 = (ULONG_PTR)PoolWithTag;
    if ( ExPoolZeroingNativelySupported )
    {
      if ( PoolWithTag )
        goto LABEL_23;
    }
    else if ( PoolWithTag )
    {
      *PoolWithTag = 0;
LABEL_23:
      ObfReferenceObject(Object);
      *(_DWORD *)v12 = 1;
      *(_QWORD *)(v12 + 8) = Object;
LABEL_24:
      Irp->IoStatus.Information = v12;
      goto LABEL_34;
    }
    Status = -1073741670;
    goto LABEL_24;
  }
  v13 = MinorFunction - 8;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( !v14 )
    {
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      HIDWORD(SecurityContext->SecurityQos) &= 0xFFFFFF83;
      *(_QWORD *)&SecurityContext[1].FullCreateOptions = 0;
      HIDWORD(SecurityContext[2].SecurityQos) = 10;
      LODWORD(SecurityContext[2].AccessState) = 10;
      HIDWORD(SecurityContext[2].AccessState) = 10;
      *(__m128i *)&SecurityContext->DesiredAccess = si128;
      *(__m128i *)((char *)&SecurityContext[1].SecurityQos + 4) = si128;
      goto LABEL_34;
    }
    v15 = v14 - 2;
    if ( v15 )
    {
      if ( v15 == 8 )
      {
        Status = QueryEnumId(
                   Object,
                   CurrentStackLocation->Parameters.QueryId.IdType,
                   (unsigned __int16 **)&Irp->IoStatus.Information);
        goto LABEL_34;
      }
      goto LABEL_31;
    }
    goto LABEL_34;
  }
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(CurrentStackLocation) = 5;
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)CurrentStackLocation,
      0,
      19,
      (char)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      (char)Object);
  }
  return IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Irp);
}

```

## disassembly

```asm
0x180066cc8  push    rbx
0x180066cca  push    rbp
0x180066ccb  push    rsi
0x180066ccc  push    rdi
0x180066ccd  sub     rsp, 48h
0x180066cd1  mov     rsi, [rcx+40h]
0x180066cd5  mov     rdi, rdx
0x180066cd8  mov     rdx, [rdx+0B8h]
0x180066cdf  xor     ebx, ebx
0x180066ce1  mov     rbp, rcx
0x180066ce4  movzx   r8d, byte ptr [rdx+1]
0x180066ce9  cmp     r8d, 7
0x180066ced  ja      loc_180066E58
0x180066cf3  jz      loc_180066DF5
0x180066cf9  test    r8d, r8d
0x180066cfc  jz      loc_180066DA2
0x180066d02  sub     r8d, 1
0x180066d06  jz      loc_180066EAF
0x180066d0c  sub     r8d, 1
0x180066d10  jz      short loc_180066D2B
0x180066d12  sub     r8d, 2
0x180066d16  jz      loc_180066EAF
0x180066d1c  cmp     r8d, 1
0x180066d20  jz      loc_180066EAF
0x180066d26  jmp     loc_180066E70
0x180066d2b  lea     rax, WPP_RECORDER_INITIALIZED
0x180066d32  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180066d39  jz      short loc_180066D6E
0x180066d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d42  cmp     [rcx+48h], bx
0x180066d46  jz      short loc_180066D6E
0x180066d48  mov     rcx, [rcx+40h]
0x180066d4c  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180066d53  mov     r9d, 15h
0x180066d59  mov     [rsp+68h+var_40], rbp
0x180066d5e  mov     dl, 5
0x180066d60  mov     [rsp+68h+var_48], rax
0x180066d65  lea     r8d, [r9-14h]
0x180066d69  call    WPP_RECORDER_SF_q
0x180066d6e  cmp     [rsi+2Ch], bl
0x180066d71  jz      loc_180066EAF
0x180066d77  mov     rcx, [rsi+20h]; P
0x180066d7b  test    rcx, rcx
0x180066d7e  jz      short loc_180066D8E
0x180066d80  xor     edx, edx; Tag
0x180066d82  call    cs:__imp_ExFreePoolWithTag
0x180066d89  nop     dword ptr [rax+rax+00h]
0x180066d8e  mov     rcx, rbp; DeviceObject
0x180066d91  call    cs:__imp_IoDeleteDevice
0x180066d98  nop     dword ptr [rax+rax+00h]
0x180066d9d  jmp     loc_180066EAF
0x180066da2  lea     rax, WPP_RECORDER_INITIALIZED
0x180066da9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180066db0  jz      short loc_180066DED
0x180066db2  mov     rcx, cs:WPP_GLOBAL_Control
0x180066db9  cmp     [rcx+48h], bx
0x180066dbd  jz      short loc_180066DED
0x180066dbf  movzx   eax, byte ptr [rsi+2Ch]
0x180066dc3  mov     r9d, 14h
0x180066dc9  mov     rcx, [rcx+40h]
0x180066dcd  mov     dl, 5
0x180066dcf  mov     dword ptr [rsp+68h+var_38], eax
0x180066dd3  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180066dda  mov     [rsp+68h+var_40], rbp
0x180066ddf  lea     r8d, [r9-13h]
0x180066de3  mov     [rsp+68h+var_48], rax
0x180066de8  call    WPP_RECORDER_SF_qD
0x180066ded  mov     [rsi+2Ch], bl
0x180066df0  jmp     loc_180066EAF
0x180066df5  cmp     dword ptr [rdx+8], 4
0x180066df9  jnz     short loc_180066E70
0x180066dfb  mov     edx, 10h; NumberOfBytes
0x180066e00  mov     ecx, 401h; PoolType
0x180066e05  mov     r8d, 7264534Bh; Tag
0x180066e0b  call    cs:__imp_ExAllocatePoolWithTag
0x180066e12  nop     dword ptr [rax+rax+00h]
0x180066e17  cmp     cs:ExPoolZeroingNativelySupported, bl
0x180066e1d  mov     rsi, rax
0x180066e20  jnz     short loc_180066E4C
0x180066e22  test    rax, rax
0x180066e25  jz      short loc_180066E51
0x180066e27  xorps   xmm0, xmm0
0x180066e2a  movups  xmmword ptr [rax], xmm0
0x180066e2d  mov     rcx, rbp; Object
0x180066e30  call    cs:__imp_ObfReferenceObject
0x180066e37  nop     dword ptr [rax+rax+00h]
0x180066e3c  mov     dword ptr [rsi], 1
0x180066e42  mov     [rsi+8], rbp
0x180066e46  mov     [rdi+38h], rsi
0x180066e4a  jmp     short loc_180066EAF
0x180066e4c  test    rsi, rsi
0x180066e4f  jnz     short loc_180066E2D
0x180066e51  mov     ebx, 0C000009Ah
0x180066e56  jmp     short loc_180066E46
0x180066e58  sub     r8d, 8
0x180066e5c  jz      short loc_180066EC7
0x180066e5e  sub     r8d, 1
0x180066e62  jz      short loc_180066E85
0x180066e64  sub     r8d, 2
0x180066e68  jz      short loc_180066EAF
0x180066e6a  cmp     r8d, 8
0x180066e6e  jz      short loc_180066E75
0x180066e70  mov     ebx, [rdi+30h]
0x180066e73  jmp     short loc_180066EAF
0x180066e75  mov     edx, [rdx+8]; enum BUS_QUERY_ID_TYPE
0x180066e78  lea     r8, [rdi+38h]; unsigned __int16 **
0x180066e7c  call    ?QueryEnumId@@YAJPEAU_DEVICE_OBJECT@@W4BUS_QUERY_ID_TYPE@@PEAPEAG@Z; QueryEnumId(_DEVICE_OBJECT *,BUS_QUERY_ID_TYPE,ushort * *)
0x180066e81  mov     ebx, eax
0x180066e83  jmp     short loc_180066EAF
0x180066e85  mov     rcx, [rdx+8]
0x180066e89  mov     eax, 0Ah
0x180066e8e  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x180066e96  and     dword ptr [rcx+4], 0FFFFFF83h
0x180066e9a  mov     [rcx+2Ch], rbx
0x180066e9e  mov     [rcx+34h], eax
0x180066ea1  mov     [rcx+38h], eax
0x180066ea4  mov     [rcx+3Ch], eax
0x180066ea7  movups  xmmword ptr [rcx+10h], xmm0
0x180066eab  movups  xmmword ptr [rcx+1Ch], xmm0
0x180066eaf  xor     edx, edx; PriorityBoost
0x180066eb1  mov     [rdi+30h], ebx
0x180066eb4  mov     rcx, rdi; Irp
0x180066eb7  call    cs:__imp_IofCompleteRequest
0x180066ebe  nop     dword ptr [rax+rax+00h]
0x180066ec3  mov     eax, ebx
0x180066ec5  jmp     short loc_180066F46
0x180066ec7  movups  xmm0, xmmword ptr [rdx]
0x180066eca  movups  xmmword ptr [rdx-48h], xmm0
0x180066ece  movups  xmm1, xmmword ptr [rdx+10h]
0x180066ed2  movups  xmmword ptr [rdx-38h], xmm1
0x180066ed6  movups  xmm0, xmmword ptr [rdx+20h]
0x180066eda  movups  xmmword ptr [rdx-28h], xmm0
0x180066ede  movsd   xmm1, qword ptr [rdx+30h]
0x180066ee3  movsd   qword ptr [rdx-18h], xmm1
0x180066ee8  mov     [rdx-45h], bl
0x180066eeb  lea     rax, WPP_RECORDER_INITIALIZED
0x180066ef2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180066ef9  jz      short loc_180066F33
0x180066efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f02  cmp     [rcx+48h], bx
0x180066f06  jz      short loc_180066F33
0x180066f08  mov     rax, [rsi+8]
0x180066f0c  mov     r9d, 13h
0x180066f12  mov     rcx, [rcx+40h]
0x180066f16  mov     dl, 5
0x180066f18  mov     [rsp+68h+var_38], rax
0x180066f1d  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180066f24  mov     [rsp+68h+var_40], rbp
0x180066f29  mov     [rsp+68h+var_48], rax
0x180066f2e  call    WPP_RECORDER_SF_qq
0x180066f33  mov     rcx, [rsi+8]; DeviceObject
0x180066f37  mov     rdx, rdi; Irp
0x180066f3a  call    cs:__imp_IofCallDriver
0x180066f41  nop     dword ptr [rax+rax+00h]
0x180066f46  add     rsp, 48h
0x180066f4a  pop     rdi
0x180066f4b  pop     rsi
0x180066f4c  pop     rbp
0x180066f4d  pop     rbx
0x180066f4e  retn
```
