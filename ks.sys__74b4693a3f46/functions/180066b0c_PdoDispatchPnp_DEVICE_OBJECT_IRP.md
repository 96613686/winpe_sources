# PdoDispatchPnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180066b0c`
- end: `0x180066d94`
- name: `?PdoDispatchPnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048c60`

## callees

- `0x18000da50`
- `0x18000dddc`
- `0x18000ee54`
- `0x18003b4cc`
- `0x180066b0c`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x180066c74`
- `ntoskrnl!ObfReferenceObject` at `0x180066c74`
- `ntoskrnl!IofCallDriver` at `0x180066d7e`
- `ntoskrnl!IofCallDriver` at `0x180066d7e`
- `ntoskrnl!IoDeleteDevice` at `0x180066bd5`
- `ntoskrnl!IoDeleteDevice` at `0x180066bd5`
- `ntoskrnl!IofCompleteRequest` at `0x180066cfb`
- `ntoskrnl!IofCompleteRequest` at `0x180066cfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066bc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066bc6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180066c4f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180066c4f`

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
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      (char)Object,
      *((_QWORD *)DeviceExtension + 1));
  }
  return IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Irp);
}

```

## disassembly

```asm
0x180066b0c  push    rbx
0x180066b0e  push    rbp
0x180066b0f  push    rsi
0x180066b10  push    rdi
0x180066b11  sub     rsp, 48h
0x180066b15  mov     rsi, [rcx+40h]
0x180066b19  mov     rdi, rdx
0x180066b1c  mov     rdx, [rdx+0B8h]
0x180066b23  xor     ebx, ebx
0x180066b25  mov     rbp, rcx
0x180066b28  movzx   r8d, byte ptr [rdx+1]
0x180066b2d  cmp     r8d, 7
0x180066b31  ja      loc_180066C9C
0x180066b37  jz      loc_180066C39
0x180066b3d  test    r8d, r8d
0x180066b40  jz      loc_180066BE6
0x180066b46  sub     r8d, 1
0x180066b4a  jz      loc_180066CF3
0x180066b50  sub     r8d, 1
0x180066b54  jz      short loc_180066B6F
0x180066b56  sub     r8d, 2
0x180066b5a  jz      loc_180066CF3
0x180066b60  cmp     r8d, 1
0x180066b64  jz      loc_180066CF3
0x180066b6a  jmp     loc_180066CB4
0x180066b6f  lea     rax, WPP_RECORDER_INITIALIZED
0x180066b76  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180066b7d  jz      short loc_180066BB2
0x180066b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066b86  cmp     [rcx+48h], bx
0x180066b8a  jz      short loc_180066BB2
0x180066b8c  mov     rcx, [rcx+40h]
0x180066b90  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180066b97  mov     r9d, 15h
0x180066b9d  mov     [rsp+68h+var_40], rbp
0x180066ba2  mov     dl, 5
0x180066ba4  mov     [rsp+68h+var_48], rax
0x180066ba9  lea     r8d, [r9-14h]
0x180066bad  call    WPP_RECORDER_SF_q
0x180066bb2  cmp     [rsi+2Ch], bl
0x180066bb5  jz      loc_180066CF3
0x180066bbb  mov     rcx, [rsi+20h]; P
0x180066bbf  test    rcx, rcx
0x180066bc2  jz      short loc_180066BD2
0x180066bc4  xor     edx, edx; Tag
0x180066bc6  call    cs:__imp_ExFreePoolWithTag
0x180066bcd  nop     dword ptr [rax+rax+00h]
0x180066bd2  mov     rcx, rbp; DeviceObject
0x180066bd5  call    cs:__imp_IoDeleteDevice
0x180066bdc  nop     dword ptr [rax+rax+00h]
0x180066be1  jmp     loc_180066CF3
0x180066be6  lea     rax, WPP_RECORDER_INITIALIZED
0x180066bed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180066bf4  jz      short loc_180066C31
0x180066bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180066bfd  cmp     [rcx+48h], bx
0x180066c01  jz      short loc_180066C31
0x180066c03  movzx   eax, byte ptr [rsi+2Ch]
0x180066c07  mov     r9d, 14h
0x180066c0d  mov     rcx, [rcx+40h]
0x180066c11  mov     dl, 5
0x180066c13  mov     dword ptr [rsp+68h+var_38], eax
0x180066c17  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180066c1e  mov     [rsp+68h+var_40], rbp
0x180066c23  lea     r8d, [r9-13h]
0x180066c27  mov     [rsp+68h+var_48], rax
0x180066c2c  call    WPP_RECORDER_SF_qD
0x180066c31  mov     [rsi+2Ch], bl
0x180066c34  jmp     loc_180066CF3
0x180066c39  cmp     dword ptr [rdx+8], 4
0x180066c3d  jnz     short loc_180066CB4
0x180066c3f  mov     edx, 10h; NumberOfBytes
0x180066c44  mov     ecx, 401h; PoolType
0x180066c49  mov     r8d, 7264534Bh; Tag
0x180066c4f  call    cs:__imp_ExAllocatePoolWithTag
0x180066c56  nop     dword ptr [rax+rax+00h]
0x180066c5b  cmp     cs:ExPoolZeroingNativelySupported, bl
0x180066c61  mov     rsi, rax
0x180066c64  jnz     short loc_180066C90
0x180066c66  test    rax, rax
0x180066c69  jz      short loc_180066C95
0x180066c6b  xorps   xmm0, xmm0
0x180066c6e  movups  xmmword ptr [rax], xmm0
0x180066c71  mov     rcx, rbp; Object
0x180066c74  call    cs:__imp_ObfReferenceObject
0x180066c7b  nop     dword ptr [rax+rax+00h]
0x180066c80  mov     dword ptr [rsi], 1
0x180066c86  mov     [rsi+8], rbp
0x180066c8a  mov     [rdi+38h], rsi
0x180066c8e  jmp     short loc_180066CF3
0x180066c90  test    rsi, rsi
0x180066c93  jnz     short loc_180066C71
0x180066c95  mov     ebx, 0C000009Ah
0x180066c9a  jmp     short loc_180066C8A
0x180066c9c  sub     r8d, 8
0x180066ca0  jz      short loc_180066D0B
0x180066ca2  sub     r8d, 1
0x180066ca6  jz      short loc_180066CC9
0x180066ca8  sub     r8d, 2
0x180066cac  jz      short loc_180066CF3
0x180066cae  cmp     r8d, 8
0x180066cb2  jz      short loc_180066CB9
0x180066cb4  mov     ebx, [rdi+30h]
0x180066cb7  jmp     short loc_180066CF3
0x180066cb9  mov     edx, [rdx+8]; enum BUS_QUERY_ID_TYPE
0x180066cbc  lea     r8, [rdi+38h]; unsigned __int16 **
0x180066cc0  call    ?QueryEnumId@@YAJPEAU_DEVICE_OBJECT@@W4BUS_QUERY_ID_TYPE@@PEAPEAG@Z; QueryEnumId(_DEVICE_OBJECT *,BUS_QUERY_ID_TYPE,ushort * *)
0x180066cc5  mov     ebx, eax
0x180066cc7  jmp     short loc_180066CF3
0x180066cc9  mov     rcx, [rdx+8]
0x180066ccd  mov     eax, 0Ah
0x180066cd2  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x180066cda  and     dword ptr [rcx+4], 0FFFFFF83h
0x180066cde  mov     [rcx+2Ch], rbx
0x180066ce2  mov     [rcx+34h], eax
0x180066ce5  mov     [rcx+38h], eax
0x180066ce8  mov     [rcx+3Ch], eax
0x180066ceb  movups  xmmword ptr [rcx+10h], xmm0
0x180066cef  movups  xmmword ptr [rcx+1Ch], xmm0
0x180066cf3  xor     edx, edx; PriorityBoost
0x180066cf5  mov     [rdi+30h], ebx
0x180066cf8  mov     rcx, rdi; Irp
0x180066cfb  call    cs:__imp_IofCompleteRequest
0x180066d02  nop     dword ptr [rax+rax+00h]
0x180066d07  mov     eax, ebx
0x180066d09  jmp     short loc_180066D8A
0x180066d0b  movups  xmm0, xmmword ptr [rdx]
0x180066d0e  movups  xmmword ptr [rdx-48h], xmm0
0x180066d12  movups  xmm1, xmmword ptr [rdx+10h]
0x180066d16  movups  xmmword ptr [rdx-38h], xmm1
0x180066d1a  movups  xmm0, xmmword ptr [rdx+20h]
0x180066d1e  movups  xmmword ptr [rdx-28h], xmm0
0x180066d22  movsd   xmm1, qword ptr [rdx+30h]
0x180066d27  movsd   qword ptr [rdx-18h], xmm1
0x180066d2c  mov     [rdx-45h], bl
0x180066d2f  lea     rax, WPP_RECORDER_INITIALIZED
0x180066d36  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180066d3d  jz      short loc_180066D77
0x180066d3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d46  cmp     [rcx+48h], bx
0x180066d4a  jz      short loc_180066D77
0x180066d4c  mov     rax, [rsi+8]
0x180066d50  mov     r9d, 13h
0x180066d56  mov     rcx, [rcx+40h]
0x180066d5a  mov     dl, 5
0x180066d5c  mov     [rsp+68h+var_38], rax
0x180066d61  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180066d68  mov     [rsp+68h+var_40], rbp
0x180066d6d  mov     [rsp+68h+var_48], rax
0x180066d72  call    WPP_RECORDER_SF_qq
0x180066d77  mov     rcx, [rsi+8]; DeviceObject
0x180066d7b  mov     rdx, rdi; Irp
0x180066d7e  call    cs:__imp_IofCallDriver
0x180066d85  nop     dword ptr [rax+rax+00h]
0x180066d8a  add     rsp, 48h
0x180066d8e  pop     rdi
0x180066d8f  pop     rsi
0x180066d90  pop     rbp
0x180066d91  pop     rbx
0x180066d92  retn
```
