# CameraQueryDeviceCompatFlags(_UNICODE_STRING *,CAMERA_COMPAT_CLASS,_DEVICE_OBJECT *)

- ea: `0x18004fbbc`
- end: `0x18004fe92`
- name: `?CameraQueryDeviceCompatFlags@@YA?ATCAMERA_DEVICE_FLAGS@@PEAU_UNICODE_STRING@@W4CAMERA_COMPAT_CLASS@@PEAU_DEVICE_OBJECT@@@Z`
- size: `726`
- prototype: `__int64 __fastcall(UNICODE_STRING *, __int64, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004dccc`

## callees

- `0x18000d1ac`
- `0x18000e0f0`
- `0x18000f300`
- `0x18001a000`
- `0x18004fbbc`
- `0x180064280`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x18004fcc2`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004fd52`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004fcc2`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18004fd52`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fc17`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fc6f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fce9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fc17`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fc6f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004fce9`
- `ntoskrnl!ExFreePool` at `0x18004fe46`
- `ntoskrnl!ExFreePool` at `0x18004fe55`
- `ntoskrnl!ExFreePool` at `0x18004fe69`
- `ntoskrnl!ExFreePool` at `0x18004fe46`
- `ntoskrnl!ExFreePool` at `0x18004fe55`
- `ntoskrnl!ExFreePool` at `0x18004fe69`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004fde5`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004fe37`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004fde5`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004fe37`

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
          if ( RtlStringCchLengthW(v16, 0xC8u, &i) < 0 )
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
0x18004fbbc  mov     [rsp-38h+arg_10], rbx
0x18004fbc1  mov     [rsp-38h+arg_8], edx
0x18004fbc5  push    rbp
0x18004fbc6  push    rsi
0x18004fbc7  push    rdi
0x18004fbc8  push    r12
0x18004fbca  push    r13
0x18004fbcc  push    r14
0x18004fbce  push    r15
0x18004fbd0  mov     rbp, rsp
0x18004fbd3  sub     rsp, 50h
0x18004fbd7  xor     r13d, r13d
0x18004fbda  mov     r15, r8
0x18004fbdd  mov     [rbp+arg_8], r13d
0x18004fbe1  mov     rdi, rcx
0x18004fbe4  mov     [rbp+arg_0], r13d
0x18004fbe8  mov     [rbp+var_10], r13
0x18004fbec  mov     [rbp+arg_18], r13
0x18004fbf0  test    rcx, rcx
0x18004fbf3  jz      loc_18004FE75
0x18004fbf9  test    r8, r8
0x18004fbfc  jz      loc_18004FE75
0x18004fc02  mov     esi, 434D4143h
0x18004fc07  lea     ecx, [r13+1]; PoolType
0x18004fc0b  mov     r12d, 0D2h
0x18004fc11  mov     r8d, esi; Tag
0x18004fc14  mov     edx, r12d; NumberOfBytes
0x18004fc17  call    cs:__imp_ExAllocatePoolWithTag
0x18004fc1e  nop     dword ptr [rax+rax+00h]
0x18004fc23  mov     r14, rax
0x18004fc26  test    rax, rax
0x18004fc29  jz      loc_18004FE75
0x18004fc2f  mov     r8d, r12d; Size
0x18004fc32  xor     edx, edx; Val
0x18004fc34  mov     rcx, rax; void *
0x18004fc37  mov     ebx, r13d
0x18004fc3a  call    memset
0x18004fc3f  lea     r9, [rbp+var_10]; unsigned __int64 *
0x18004fc43  mov     r8, r14; unsigned __int16 *
0x18004fc46  mov     rdx, r15; Pdo
0x18004fc49  mov     rcx, rdi; SymbolicLinkName
0x18004fc4c  call    ?CreateFingerprintStringPrefix@@YAJPEAU_UNICODE_STRING@@PEAU_DEVICE_OBJECT@@PEAGPEA_K@Z; CreateFingerprintStringPrefix(_UNICODE_STRING *,_DEVICE_OBJECT *,ushort *,unsigned __int64 *)
0x18004fc51  test    eax, eax
0x18004fc53  js      loc_18004FE52
0x18004fc59  mov     r12, [rbp+var_10]
0x18004fc5d  lea     ecx, [r13+1]; PoolType
0x18004fc61  add     r12, 19h
0x18004fc65  mov     r8d, esi; Tag
0x18004fc68  lea     rdi, [r12+r12]
0x18004fc6c  mov     rdx, rdi; NumberOfBytes
0x18004fc6f  call    cs:__imp_ExAllocatePoolWithTag
0x18004fc76  nop     dword ptr [rax+rax+00h]
0x18004fc7b  mov     rsi, rax
0x18004fc7e  test    rax, rax
0x18004fc81  jz      loc_18004FE52
0x18004fc87  mov     r8, rdi; Size
0x18004fc8a  xor     edx, edx; Val
0x18004fc8c  mov     rcx, rax; void *
0x18004fc8f  call    memset
0x18004fc94  mov     ecx, [rbp+arg_8]
0x18004fc97  lea     rax, [rbp+arg_0]
0x18004fc9b  mov     [rsp+50h+Type], rax; Type
0x18004fca0  lea     rdx, DEVPKEY_Device_HardwareIds; PropertyKey
0x18004fca7  lea     rax, [rbp+arg_8]
0x18004fcab  xor     r9d, r9d; Flags
0x18004fcae  mov     [rsp+50h+RequiredSize], rax; RequiredSize
0x18004fcb3  xor     r8d, r8d; Lcid
0x18004fcb6  mov     [rsp+50h+Data], r13; Data
0x18004fcbb  mov     [rsp+50h+Size], ecx; Size
0x18004fcbf  mov     rcx, r15; Pdo
0x18004fcc2  call    cs:__imp_IoGetDevicePropertyData
0x18004fcc9  nop     dword ptr [rax+rax+00h]
0x18004fcce  cmp     eax, 0C0000023h
0x18004fcd3  jnz     loc_18004FD5E
0x18004fcd9  mov     ebx, [rbp+arg_8]
0x18004fcdc  mov     r8d, 434D4143h; Tag
0x18004fce2  mov     edx, ebx; NumberOfBytes
0x18004fce4  mov     ecx, 401h; PoolType
0x18004fce9  call    cs:__imp_ExAllocatePoolWithTag
0x18004fcf0  nop     dword ptr [rax+rax+00h]
0x18004fcf5  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x18004fcfc  mov     rdi, rax
0x18004fcff  jnz     short loc_18004FD18
0x18004fd01  test    rax, rax
0x18004fd04  jz      short loc_18004FD18
0x18004fd06  mov     r8d, ebx; Size
0x18004fd09  xor     edx, edx; Val
0x18004fd0b  mov     rcx, rax; void *
0x18004fd0e  call    memset
0x18004fd13  mov     rbx, rdi
0x18004fd16  jmp     short loc_18004FD24
0x18004fd18  mov     rbx, rdi
0x18004fd1b  test    rdi, rdi
0x18004fd1e  jz      loc_18004FE43
0x18004fd24  lea     rax, [rbp+arg_0]
0x18004fd28  xor     r9d, r9d; Flags
0x18004fd2b  mov     [rsp+50h+Type], rax; Type
0x18004fd30  lea     rdx, DEVPKEY_Device_HardwareIds; PropertyKey
0x18004fd37  lea     rax, [rbp+arg_8]
0x18004fd3b  xor     r8d, r8d; Lcid
0x18004fd3e  mov     [rsp+50h+RequiredSize], rax; RequiredSize
0x18004fd43  mov     rcx, r15; Pdo
0x18004fd46  mov     eax, [rbp+arg_8]
0x18004fd49  mov     [rsp+50h+Data], rdi; Data
0x18004fd4e  mov     [rsp+50h+Size], eax; Size
0x18004fd52  call    cs:__imp_IoGetDevicePropertyData
0x18004fd59  nop     dword ptr [rax+rax+00h]
0x18004fd5e  test    eax, eax
0x18004fd60  js      loc_18004FE0B
0x18004fd66  cmp     [rbp+arg_0], 2012h
0x18004fd6d  jnz     loc_18004FE0B
0x18004fd73  mov     rdi, rbx
0x18004fd76  mov     [rbp+var_10], r13
0x18004fd7a  cmp     [rbx], r13w
0x18004fd7e  jz      loc_18004FE43
0x18004fd84  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18004fd88  mov     [rbp+var_8], r13
0x18004fd8c  mov     edx, 0C8h; unsigned __int64
0x18004fd91  mov     rcx, rdi; unsigned __int16 *
0x18004fd94  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004fd99  test    eax, eax
0x18004fd9b  js      loc_18004FE43
0x18004fda1  mov     r15, [rbp+var_10]
0x18004fda5  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18004fda9  mov     rcx, rdi; pbInput
0x18004fdac  lea     edx, [r15+r15]; cbInput
0x18004fdb0  call    ?CameraGenerateDWORD64Hash@@YAJPEAEKPEA_K@Z; CameraGenerateDWORD64Hash(uchar *,ulong,unsigned __int64 *)
0x18004fdb5  mov     rax, [rbp+var_8]
0x18004fdb9  lea     r8, aCameraWs016i64; "Camera:%ws%016I64X;"
0x18004fdc0  mov     r9, r14
0x18004fdc3  mov     qword ptr [rsp+50h+Size], rax
0x18004fdc8  mov     rdx, r12; unsigned __int64
0x18004fdcb  mov     rcx, rsi; unsigned __int16 *
0x18004fdce  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fdd3  test    eax, eax
0x18004fdd5  js      short loc_18004FDF7
0x18004fdd7  lea     r8, [rbp+arg_18]
0x18004fddb  mov     rcx, rsi
0x18004fdde  lea     rdx, aCamdevice; "CamDevice"
0x18004fde5  call    cs:__imp_KseQueryDeviceFlags
0x18004fdec  nop     dword ptr [rax+rax+00h]
0x18004fdf1  cmp     [rbp+arg_18], r13
0x18004fdf5  jnz     short loc_18004FE43
0x18004fdf7  lea     rdi, [rdi+r15*2]
0x18004fdfb  add     rdi, 2
0x18004fdff  cmp     [rdi], r13w
0x18004fe03  jnz     loc_18004FD84
0x18004fe09  jmp     short loc_18004FE43
0x18004fe0b  mov     r9, r14
0x18004fe0e  mov     qword ptr [rsp+50h+Size], r13
0x18004fe13  lea     r8, aCameraWs016i64; "Camera:%ws%016I64X;"
0x18004fe1a  mov     rdx, r12; unsigned __int64
0x18004fe1d  mov     rcx, rsi; unsigned __int16 *
0x18004fe20  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fe25  test    eax, eax
0x18004fe27  js      short loc_18004FE43
0x18004fe29  lea     r8, [rbp+arg_18]
0x18004fe2d  mov     rcx, rsi
0x18004fe30  lea     rdx, aCamdevice; "CamDevice"
0x18004fe37  call    cs:__imp_KseQueryDeviceFlags
0x18004fe3e  nop     dword ptr [rax+rax+00h]
0x18004fe43  mov     rcx, rsi; P
0x18004fe46  call    cs:__imp_ExFreePool
0x18004fe4d  nop     dword ptr [rax+rax+00h]
0x18004fe52  mov     rcx, r14; P
0x18004fe55  call    cs:__imp_ExFreePool
0x18004fe5c  nop     dword ptr [rax+rax+00h]
0x18004fe61  test    rbx, rbx
0x18004fe64  jz      short loc_18004FE75
0x18004fe66  mov     rcx, rbx; P
0x18004fe69  call    cs:__imp_ExFreePool
0x18004fe70  nop     dword ptr [rax+rax+00h]
0x18004fe75  mov     rax, [rbp+arg_18]
0x18004fe79  mov     rbx, [rsp+50h+arg_10]
0x18004fe81  add     rsp, 50h
0x18004fe85  pop     r15
0x18004fe87  pop     r14
0x18004fe89  pop     r13
0x18004fe8b  pop     r12
0x18004fe8d  pop     rdi
0x18004fe8e  pop     rsi
0x18004fe8f  pop     rbp
0x18004fe90  retn
```
