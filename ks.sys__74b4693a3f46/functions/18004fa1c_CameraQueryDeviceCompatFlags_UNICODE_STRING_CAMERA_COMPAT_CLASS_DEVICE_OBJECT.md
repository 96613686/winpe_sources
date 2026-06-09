# CameraQueryDeviceCompatFlags(_UNICODE_STRING *,CAMERA_COMPAT_CLASS,_DEVICE_OBJECT *)

- ea: `0x18004fa1c`
- end: `0x18004fcf2`
- name: `?CameraQueryDeviceCompatFlags@@YA?ATCAMERA_DEVICE_FLAGS@@PEAU_UNICODE_STRING@@W4CAMERA_COMPAT_CLASS@@PEAU_DEVICE_OBJECT@@@Z`
- size: `726`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004db2c`

## callees

- `0x18000d1ac`
- `0x18000e0f0`
- `0x18000ec10`
- `0x180019fc0`
- `0x18004fa1c`
- `0x1800640e0`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x18004fb22`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004fbb2`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004fb22`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004fbb2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fa77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004facf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fb49`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fa77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004facf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fb49`
- `ntoskrnl!ExFreePool` at `0x18004fca6`
- `ntoskrnl!ExFreePool` at `0x18004fcb5`
- `ntoskrnl!ExFreePool` at `0x18004fcc9`
- `ntoskrnl!ExFreePool` at `0x18004fca6`
- `ntoskrnl!ExFreePool` at `0x18004fcb5`
- `ntoskrnl!ExFreePool` at `0x18004fcc9`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004fc45`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004fc97`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004fc45`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004fc97`

## pseudocode

```c
__int64 __fastcall CameraQueryDeviceCompatFlags(UNICODE_STRING *a1, __int64 a2, struct _DEVICE_OBJECT *a3)
{
  unsigned __int16 *PoolWithTag; // rax
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rbx
  unsigned __int64 v8; // r12
  SIZE_T v9; // rdi
  PVOID v10; // rax
  void *v11; // rsi
  NTSTATUS DevicePropertyData; // eax
  ULONG v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *Data; // rdi
  unsigned __int16 *v16; // rdi
  unsigned __int64 v17; // r15
  unsigned __int64 i; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-8h] BYREF
  ULONG Type; // [rsp+90h] [rbp+40h] BYREF
  ULONG Size; // [rsp+98h] [rbp+48h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+58h] BYREF

  Size = 0;
  Type = 0;
  i = 0;
  v23 = 0;
  if ( !a1 )
    return v23;
  if ( !a3 )
    return v23;
  PoolWithTag = (unsigned __int16 *)ExAllocatePoolWithTag(PagedPool, 0xD2u, 0x434D4143u);
  v6 = PoolWithTag;
  if ( !PoolWithTag )
    return v23;
  v7 = 0;
  memset(PoolWithTag, 0, 0xD2u);
  if ( (int)CreateFingerprintStringPrefix(a1, a3, v6, &i) >= 0 )
  {
    v8 = i + 25;
    v9 = 2 * (i + 25);
    v10 = ExAllocatePoolWithTag(PagedPool, v9, 0x434D4143u);
    v11 = v10;
    if ( v10 )
    {
      memset(v10, 0, v9);
      DevicePropertyData = IoGetDevicePropertyData(a3, &DEVPKEY_Device_HardwareIds, 0, 0, Size, 0, &Size, &Type);
      if ( DevicePropertyData == -1073741789 )
      {
        v13 = Size;
        v14 = (unsigned __int16 *)ExAllocatePoolWithTag((POOL_TYPE)1025, Size, 0x434D4143u);
        Data = v14;
        if ( ExPoolZeroingNativelySupported || !v14 )
        {
          v7 = v14;
          if ( !v14 )
          {
LABEL_22:
            ExFreePool(v11);
            goto LABEL_23;
          }
        }
        else
        {
          memset(v14, 0, v13);
          v7 = Data;
        }
        DevicePropertyData = IoGetDevicePropertyData(a3, &DEVPKEY_Device_HardwareIds, 0, 0, Size, Data, &Size, &Type);
      }
      if ( DevicePropertyData >= 0 && Type == 8210 )
      {
        v16 = v7;
        for ( i = 0; *v16; v16 += v17 + 1 )
        {
          v20 = 0;
          if ( (int)RtlStringCchLengthW(v16, 0xC8u, &i) < 0 )
            break;
          v17 = i;
          CameraGenerateDWORD64Hash((PUCHAR)v16, 2 * i, &v20);
          if ( (int)RtlStringCchPrintfW((unsigned __int16 *)v11, v8, L"Camera:%ws%016I64X;", v6, v20) >= 0 )
          {
            KseQueryDeviceFlags(v11, L"CamDevice", &v23);
            if ( v23 )
              break;
          }
        }
      }
      else if ( (int)RtlStringCchPrintfW((unsigned __int16 *)v11, v8, L"Camera:%ws%016I64X;", v6, 0) >= 0 )
      {
        KseQueryDeviceFlags(v11, L"CamDevice", &v23);
      }
      goto LABEL_22;
    }
  }
LABEL_23:
  ExFreePool(v6);
  if ( v7 )
    ExFreePool(v7);
  return v23;
}

```

## disassembly

```asm
0x18004fa1c  mov     [rsp-38h+arg_10], rbx
0x18004fa21  mov     [rsp-38h+arg_8], edx
0x18004fa25  push    rbp
0x18004fa26  push    rsi
0x18004fa27  push    rdi
0x18004fa28  push    r12
0x18004fa2a  push    r13
0x18004fa2c  push    r14
0x18004fa2e  push    r15
0x18004fa30  mov     rbp, rsp
0x18004fa33  sub     rsp, 50h
0x18004fa37  xor     r13d, r13d
0x18004fa3a  mov     r15, r8
0x18004fa3d  mov     [rbp+arg_8], r13d
0x18004fa41  mov     rdi, rcx
0x18004fa44  mov     [rbp+arg_0], r13d
0x18004fa48  mov     [rbp+var_10], r13
0x18004fa4c  mov     [rbp+arg_18], r13
0x18004fa50  test    rcx, rcx
0x18004fa53  jz      loc_18004FCD5
0x18004fa59  test    r8, r8
0x18004fa5c  jz      loc_18004FCD5
0x18004fa62  mov     esi, 434D4143h
0x18004fa67  lea     ecx, [r13+1]; PoolType
0x18004fa6b  mov     r12d, 0D2h
0x18004fa71  mov     r8d, esi; Tag
0x18004fa74  mov     edx, r12d; NumberOfBytes
0x18004fa77  call    cs:__imp_ExAllocatePoolWithTag
0x18004fa7e  nop     dword ptr [rax+rax+00h]
0x18004fa83  mov     r14, rax
0x18004fa86  test    rax, rax
0x18004fa89  jz      loc_18004FCD5
0x18004fa8f  mov     r8d, r12d; Size
0x18004fa92  xor     edx, edx; Val
0x18004fa94  mov     rcx, rax; void *
0x18004fa97  mov     ebx, r13d
0x18004fa9a  call    memset
0x18004fa9f  lea     r9, [rbp+var_10]; unsigned __int64 *
0x18004faa3  mov     r8, r14; unsigned __int16 *
0x18004faa6  mov     rdx, r15; Pdo
0x18004faa9  mov     rcx, rdi; SymbolicLinkName
0x18004faac  call    ?CreateFingerprintStringPrefix@@YAJPEAU_UNICODE_STRING@@PEAU_DEVICE_OBJECT@@PEAGPEA_K@Z; CreateFingerprintStringPrefix(_UNICODE_STRING *,_DEVICE_OBJECT *,ushort *,unsigned __int64 *)
0x18004fab1  test    eax, eax
0x18004fab3  js      loc_18004FCB2
0x18004fab9  mov     r12, [rbp+var_10]
0x18004fabd  lea     ecx, [r13+1]; PoolType
0x18004fac1  add     r12, 19h
0x18004fac5  mov     r8d, esi; Tag
0x18004fac8  lea     rdi, [r12+r12]
0x18004facc  mov     rdx, rdi; NumberOfBytes
0x18004facf  call    cs:__imp_ExAllocatePoolWithTag
0x18004fad6  nop     dword ptr [rax+rax+00h]
0x18004fadb  mov     rsi, rax
0x18004fade  test    rax, rax
0x18004fae1  jz      loc_18004FCB2
0x18004fae7  mov     r8, rdi; Size
0x18004faea  xor     edx, edx; Val
0x18004faec  mov     rcx, rax; void *
0x18004faef  call    memset
0x18004faf4  mov     ecx, [rbp+arg_8]
0x18004faf7  lea     rax, [rbp+arg_0]
0x18004fafb  mov     [rsp+50h+Type], rax; Type
0x18004fb00  lea     rdx, DEVPKEY_Device_HardwareIds; PropertyKey
0x18004fb07  lea     rax, [rbp+arg_8]
0x18004fb0b  xor     r9d, r9d; Flags
0x18004fb0e  mov     [rsp+50h+RequiredSize], rax; RequiredSize
0x18004fb13  xor     r8d, r8d; Lcid
0x18004fb16  mov     [rsp+50h+Data], r13; Data
0x18004fb1b  mov     [rsp+50h+Size], ecx; Size
0x18004fb1f  mov     rcx, r15; Pdo
0x18004fb22  call    cs:__imp_IoGetDevicePropertyData
0x18004fb29  nop     dword ptr [rax+rax+00h]
0x18004fb2e  cmp     eax, 0C0000023h
0x18004fb33  jnz     loc_18004FBBE
0x18004fb39  mov     ebx, [rbp+arg_8]
0x18004fb3c  mov     r8d, 434D4143h; Tag
0x18004fb42  mov     edx, ebx; NumberOfBytes
0x18004fb44  mov     ecx, 401h; PoolType
0x18004fb49  call    cs:__imp_ExAllocatePoolWithTag
0x18004fb50  nop     dword ptr [rax+rax+00h]
0x18004fb55  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x18004fb5c  mov     rdi, rax
0x18004fb5f  jnz     short loc_18004FB78
0x18004fb61  test    rax, rax
0x18004fb64  jz      short loc_18004FB78
0x18004fb66  mov     r8d, ebx; Size
0x18004fb69  xor     edx, edx; Val
0x18004fb6b  mov     rcx, rax; void *
0x18004fb6e  call    memset
0x18004fb73  mov     rbx, rdi
0x18004fb76  jmp     short loc_18004FB84
0x18004fb78  mov     rbx, rdi
0x18004fb7b  test    rdi, rdi
0x18004fb7e  jz      loc_18004FCA3
0x18004fb84  lea     rax, [rbp+arg_0]
0x18004fb88  xor     r9d, r9d; Flags
0x18004fb8b  mov     [rsp+50h+Type], rax; Type
0x18004fb90  lea     rdx, DEVPKEY_Device_HardwareIds; PropertyKey
0x18004fb97  lea     rax, [rbp+arg_8]
0x18004fb9b  xor     r8d, r8d; Lcid
0x18004fb9e  mov     [rsp+50h+RequiredSize], rax; RequiredSize
0x18004fba3  mov     rcx, r15; Pdo
0x18004fba6  mov     eax, [rbp+arg_8]
0x18004fba9  mov     [rsp+50h+Data], rdi; Data
0x18004fbae  mov     [rsp+50h+Size], eax; Size
0x18004fbb2  call    cs:__imp_IoGetDevicePropertyData
0x18004fbb9  nop     dword ptr [rax+rax+00h]
0x18004fbbe  test    eax, eax
0x18004fbc0  js      loc_18004FC6B
0x18004fbc6  cmp     [rbp+arg_0], 2012h
0x18004fbcd  jnz     loc_18004FC6B
0x18004fbd3  mov     rdi, rbx
0x18004fbd6  mov     [rbp+var_10], r13
0x18004fbda  cmp     [rbx], r13w
0x18004fbde  jz      loc_18004FCA3
0x18004fbe4  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18004fbe8  mov     [rbp+var_8], r13
0x18004fbec  mov     edx, 0C8h; unsigned __int64
0x18004fbf1  mov     rcx, rdi; unsigned __int16 *
0x18004fbf4  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004fbf9  test    eax, eax
0x18004fbfb  js      loc_18004FCA3
0x18004fc01  mov     r15, [rbp+var_10]
0x18004fc05  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18004fc09  mov     rcx, rdi; pbInput
0x18004fc0c  lea     edx, [r15+r15]; cbInput
0x18004fc10  call    ?CameraGenerateDWORD64Hash@@YAJPEAEKPEA_K@Z; CameraGenerateDWORD64Hash(uchar *,ulong,unsigned __int64 *)
0x18004fc15  mov     rax, [rbp+var_8]
0x18004fc19  lea     r8, aCameraWs016i64; "Camera:%ws%016I64X;"
0x18004fc20  mov     r9, r14
0x18004fc23  mov     qword ptr [rsp+50h+Size], rax
0x18004fc28  mov     rdx, r12; unsigned __int64
0x18004fc2b  mov     rcx, rsi; unsigned __int16 *
0x18004fc2e  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fc33  test    eax, eax
0x18004fc35  js      short loc_18004FC57
0x18004fc37  lea     r8, [rbp+arg_18]
0x18004fc3b  mov     rcx, rsi
0x18004fc3e  lea     rdx, aCamdevice; "CamDevice"
0x18004fc45  call    cs:__imp_KseQueryDeviceFlags
0x18004fc4c  nop     dword ptr [rax+rax+00h]
0x18004fc51  cmp     [rbp+arg_18], r13
0x18004fc55  jnz     short loc_18004FCA3
0x18004fc57  lea     rdi, [rdi+r15*2]
0x18004fc5b  add     rdi, 2
0x18004fc5f  cmp     [rdi], r13w
0x18004fc63  jnz     loc_18004FBE4
0x18004fc69  jmp     short loc_18004FCA3
0x18004fc6b  mov     r9, r14
0x18004fc6e  mov     qword ptr [rsp+50h+Size], r13
0x18004fc73  lea     r8, aCameraWs016i64; "Camera:%ws%016I64X;"
0x18004fc7a  mov     rdx, r12; unsigned __int64
0x18004fc7d  mov     rcx, rsi; unsigned __int16 *
0x18004fc80  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fc85  test    eax, eax
0x18004fc87  js      short loc_18004FCA3
0x18004fc89  lea     r8, [rbp+arg_18]
0x18004fc8d  mov     rcx, rsi
0x18004fc90  lea     rdx, aCamdevice; "CamDevice"
0x18004fc97  call    cs:__imp_KseQueryDeviceFlags
0x18004fc9e  nop     dword ptr [rax+rax+00h]
0x18004fca3  mov     rcx, rsi; P
0x18004fca6  call    cs:__imp_ExFreePool
0x18004fcad  nop     dword ptr [rax+rax+00h]
0x18004fcb2  mov     rcx, r14; P
0x18004fcb5  call    cs:__imp_ExFreePool
0x18004fcbc  nop     dword ptr [rax+rax+00h]
0x18004fcc1  test    rbx, rbx
0x18004fcc4  jz      short loc_18004FCD5
0x18004fcc6  mov     rcx, rbx; P
0x18004fcc9  call    cs:__imp_ExFreePool
0x18004fcd0  nop     dword ptr [rax+rax+00h]
0x18004fcd5  mov     rax, [rbp+arg_18]
0x18004fcd9  mov     rbx, [rsp+50h+arg_10]
0x18004fce1  add     rsp, 50h
0x18004fce5  pop     r15
0x18004fce7  pop     r14
0x18004fce9  pop     r13
0x18004fceb  pop     r12
0x18004fced  pop     rdi
0x18004fcee  pop     rsi
0x18004fcef  pop     rbp
0x18004fcf0  retn
```
