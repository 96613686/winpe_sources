# FltpGetTargetInfo

- ea: `0x180066990`
- end: `0x180066fa0`
- name: `FltpGetTargetInfo`
- size: `1552`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, PVOID *, PVOID *, _QWORD *)`
- caller_count: `3`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001bf00`
- `0x18005aa30`
- `0x18005d2b0`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x1800243a0`
- `0x1800243e0`
- `0x180024c00`
- `0x18005c5a0`
- `0x18005fcf0`
- `0x180066990`
- `0x180067b00`
- `0x18007c220`
- `0x18007c724`
- `0x18007caa0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180066da4`
- `ntoskrnl!ExAllocatePool2` at `0x180066da4`
- `ntoskrnl!ObfDereferenceObject` at `0x180066c98`
- `ntoskrnl!ObfDereferenceObject` at `0x180066c98`
- `ntoskrnl!ObfReferenceObject` at `0x180066c26`
- `ntoskrnl!ObfReferenceObject` at `0x180066c26`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180066e40`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180066e40`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180066e54`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180066e54`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180066a16`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180066a16`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180066f5f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180066f5f`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180066bf1`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180066bf1`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1800669d9`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1800669d9`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180066ad7`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180066ad7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180066abf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180066abf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180066ba1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180066ba1`
- `ntoskrnl!ExReleaseFastResource` at `0x180066b95`
- `ntoskrnl!ExReleaseFastResource` at `0x180066b95`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180066d66`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180066d66`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180066ce8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180066ce8`

## pseudocode

```c
__int64 __fastcall FltpGetTargetInfo(_QWORD *a1, _QWORD *a2, PVOID *a3, PVOID *a4, _QWORD *a5)
{
  PVOID *v8; // r15
  UNICODE_STRING *v9; // rax
  UNICODE_STRING *v10; // rbx
  _WORD *v12; // r12
  char v13; // r14
  unsigned int FltVolumeFromAttachmentList; // eax
  __int64 v15; // r8
  PVOID v16; // rsi
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  unsigned int v19; // eax
  unsigned int ObjectName; // esi
  PDEVICE_OBJECT v21; // rcx
  const UNICODE_STRING *v22; // r14
  unsigned __int16 v23; // cx
  unsigned __int64 v24; // r12
  _WORD *Pool2; // rdi
  unsigned __int16 v26; // r12
  bool v27; // zf
  unsigned __int64 v28; // rax
  unsigned __int16 Length; // ax
  bool v30; // r14
  __int64 v31; // rdi
  __int64 v32; // [rsp+20h] [rbp-D8h]
  bool v33; // [rsp+30h] [rbp-C8h]
  __int64 v34; // [rsp+38h] [rbp-C0h] BYREF
  PVOID v35; // [rsp+40h] [rbp-B8h]
  PVOID v36; // [rsp+48h] [rbp-B0h]
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+50h] [rbp-A8h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-A0h] BYREF
  _WORD *v39; // [rsp+68h] [rbp-90h]
  _BYTE v40[80]; // [rsp+70h] [rbp-88h] BYREF
  PVOID FltObject; // [rsp+108h] [rbp+10h] BYREF
  PVOID *v42; // [rsp+118h] [rbp+20h]

  v42 = a4;
  DiskDeviceObject = 0;
  v8 = a4;
  memset(v40, 0, 0x48u);
  v34 = 0;
  v33 = 0;
  ExInitializeFastOwnerEntry(v40);
  v36 = 0;
  FltObject = 0;
  if ( a2 )
    v33 = a2[30] != 0;
  v9 = (UNICODE_STRING *)ExAllocateFromNPagedLookasideList(&stru_18003EDC0);
  v10 = v9;
  if ( !v9 )
    return 3221225626LL;
  *(_DWORD *)&v9[1].Length = 0;
  LODWORD(v9[1].Buffer) = 0;
  *(_DWORD *)(&v9[1].MaximumLength + 1) = 254;
  v12 = 0;
  *v9 = 0;
  v13 = 0;
  v9->MaximumLength = 254;
  v9->Buffer = (wchar_t *)&v9[1].Buffer + 2;
  v35 = 0;
  v39 = 0;
  if ( a2 )
  {
    FltVolumeFromAttachmentList = FltpGetFltVolumeFromAttachmentList(a2[7], a2, *a1, &FltObject);
    if ( (int)FltpDbgStatus(FltVolumeFromAttachmentList, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2490, 0) < 0 )
    {
      v36 = FltObject;
    }
    else
    {
      KeEnterCriticalRegion();
      LOBYTE(v15) = 1;
      ExAcquireFastResourceShared(a2 + 14, v40, v15);
      v16 = FltObject;
      v17 = a2 + 27;
      v18 = (_QWORD *)a2[27];
      *(_QWORD *)&String2.Length = v18;
      v36 = FltObject;
      if ( v18 != a2 + 27 )
      {
        while ( 1 )
        {
          v35 = v18 - 15;
          if ( (PVOID)*(v18 - 7) == v16 )
          {
            if ( v33 )
              v19 = FltpvObjectReferenceForFilter(a2);
            else
              v19 = FltObjectReference(v18 - 15);
            v32 = 0;
            if ( (int)FltpDbgStatus(v19, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2514, 3223060491LL) >= 0 )
            {
LABEL_15:
              v8 = v42;
              v12 = v39;
              break;
            }
            v18 = *(_QWORD **)&String2.Length;
            v17 = a2 + 27;
          }
          v18 = (_QWORD *)*v18;
          v35 = 0;
          *(_QWORD *)&String2.Length = v18;
          if ( v18 == v17 )
            goto LABEL_15;
        }
      }
      ExReleaseFastResource(a2 + 14, v40);
      KeLeaveCriticalRegion();
      if ( v35 )
      {
        if ( v33 )
          FltpvObjectDereferenceForFilter(a2, v16);
        else
          FltObjectDereference(v16);
        v36 = 0;
      }
    }
  }
  ObjectName = IoGetDiskDeviceObject((PDEVICE_OBJECT)*a1, &DiskDeviceObject);
  if ( ObjectName == -1073741811 )
  {
    v21 = (PDEVICE_OBJECT)*a1;
    if ( !*(_QWORD *)(*a1 + 56LL) && !v21->DeviceObjectExtension->Vpb )
    {
      v13 = 1;
      DiskDeviceObject = (PDEVICE_OBJECT)*a1;
      ObfReferenceObject(v21);
      ObjectName = 0;
    }
  }
  if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2570, 0) >= 0 && v33 )
    ObjectName = FltpvPreAllocateVerifierObject(a2, &v34);
  if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2576, 0) < 0 )
    goto LABEL_48;
  ObjectName = FltpGetObjectName(DiskDeviceObject, (__int64)v10);
  ObfDereferenceObject(DiskDeviceObject);
  if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2582, 0) < 0 )
    goto LABEL_48;
  if ( v13 )
  {
    *(_QWORD *)&String2.Length = 1572886;
    String2.Buffer = L"\\Device\\Mup";
    if ( RtlCompareUnicodeString(v10, &String2, 1u) )
      ObjectName = -1073740951;
  }
  if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2599, 0) < 0 )
    goto LABEL_48;
  v22 = (const UNICODE_STRING *)(a1 + 1);
  v23 = v10->Length + *((_WORD *)a1 + 4) + 210;
  if ( v23 > 0x150u )
  {
    v24 = ((unsigned __int64)v23 - 273) >> 6;
    if ( (unsigned __int16)v24 >= 7u )
    {
      v26 = v10->Length + *((_WORD *)a1 + 4) + 210;
      LOBYTE(FltObject) = 0;
      Pool2 = (_WORD *)ExAllocatePool2(256, v23, 946752838);
      goto LABEL_40;
    }
  }
  else
  {
    LOWORD(v24) = 0;
  }
  Pool2 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&qword_18003F840[16
                                                                                 * (unsigned __int64)(unsigned __int16)v24]);
  LOBYTE(FltObject) = 1;
  v26 = ((_WORD)v24 << 6) + 336;
LABEL_40:
  if ( Pool2 )
  {
    memset(Pool2, 0, 0xD0u);
    v27 = (_BYTE)FltObject == 0;
    *((_DWORD *)Pool2 + 50) = 1;
    *Pool2 = -3580;
    Pool2[1] = v26;
    if ( !v27 )
      *((_DWORD *)Pool2 + 18) |= 0x1000u;
    *((_DWORD *)Pool2 + 18) |= 0x800u;
    *(_OWORD *)(Pool2 + 44) = 0;
    v28 = v26 - 208LL;
    v12 = Pool2 + 40;
    if ( v28 > 0xFFFE )
      LOWORD(v28) = -2;
    Pool2[45] = v28;
    *((_QWORD *)Pool2 + 12) = Pool2 + 104;
    *v12 = 120;
    *((_DWORD *)Pool2 + 21) = 2;
    RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 44), v10);
    RtlAppendUnicodeStringToString((PUNICODE_STRING)(Pool2 + 44), v22);
    Length = v10->Length;
    v30 = v33;
    v31 = v34;
    v12[13] = v10->Length;
    v12[12] = Length;
    *((_QWORD *)v12 + 4) = *((_QWORD *)v12 + 2);
    if ( v33 )
      FltpvLinkResourceToFilter(a2, v12, 4, v31, v32);
    goto LABEL_49;
  }
  v12 = v39;
  ObjectName = -1073741670;
LABEL_48:
  v30 = v33;
  v31 = v34;
LABEL_49:
  if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2691, 0) >= 0 )
  {
    if ( a3 )
      *a3 = v35;
    if ( v8 )
      *v8 = v36;
    *a5 = v12;
  }
  else
  {
    if ( v35 )
    {
      if ( v30 )
        FltpvObjectDereferenceForFilter(a2, v35);
      else
        FltObjectDereference(v35);
    }
    if ( v36 )
    {
      if ( v30 )
        FltpvObjectDereferenceForFilter(a2, v36);
      else
        FltObjectDereference(v36);
    }
    if ( v31 )
      FltpvFreeVerifierObject(a2, v31);
  }
  FltpCleanupNameControl(v10);
  ExFreeToNPagedLookasideList(&stru_18003EDC0, v10);
  return ObjectName;
}

```

## disassembly

```asm
0x180066990  mov     [rsp+arg_18], r9
0x180066995  push    rbx
0x180066996  push    rbp
0x180066997  push    rsi
0x180066998  push    rdi
0x180066999  push    r13
0x18006699b  push    r15
0x18006699d  sub     rsp, 0C8h
0x1800669a4  mov     r13, r8
0x1800669a7  mov     rbp, rdx
0x1800669aa  mov     rdi, rcx
0x1800669ad  xor     esi, esi
0x1800669af  xor     edx, edx; Val
0x1800669b1  mov     [rsp+0F8h+DiskDeviceObject], rsi
0x1800669b6  mov     r8d, 48h ; 'H'; Size
0x1800669bc  lea     rcx, [rsp+0F8h+var_88]; void *
0x1800669c1  mov     r15, r9
0x1800669c4  call    memset
0x1800669c9  xor     bl, bl
0x1800669cb  mov     [rsp+0F8h+var_C0], rsi
0x1800669d0  lea     rcx, [rsp+0F8h+var_88]
0x1800669d5  mov     dword ptr [rsp+0F8h+var_C8], ebx
0x1800669d9  call    cs:__imp_ExInitializeFastOwnerEntry
0x1800669e0  nop     dword ptr [rax+rax+00h]
0x1800669e5  mov     eax, esi
0x1800669e7  mov     [rsp+0F8h+var_B0], rax
0x1800669ec  mov     [rsp+0F8h+FltObject], rax
0x1800669f4  mov     eax, 1
0x1800669f9  test    rbp, rbp
0x1800669fc  jz      short loc_180066A0F
0x1800669fe  cmp     [rbp+0F0h], rsi
0x180066a05  movzx   ebx, bl
0x180066a08  cmovnz  ebx, eax
0x180066a0b  mov     dword ptr [rsp+0F8h+var_C8], ebx
0x180066a0f  lea     rcx, stru_18003EDC0; Lookaside
0x180066a16  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180066a1d  nop     dword ptr [rax+rax+00h]
0x180066a22  mov     rbx, rax
0x180066a25  test    rax, rax
0x180066a28  jnz     short loc_180066A40
0x180066a2a  mov     eax, 0C000009Ah
0x180066a2f  add     rsp, 0C8h
0x180066a36  pop     r15
0x180066a38  pop     r13
0x180066a3a  pop     rdi
0x180066a3b  pop     rsi
0x180066a3c  pop     rbp
0x180066a3d  pop     rbx
0x180066a3e  retn
0x180066a40  mov     [rax+10h], esi
0x180066a43  xorps   xmm0, xmm0
0x180066a46  mov     [rax+18h], esi
0x180066a49  mov     eax, 0FEh
0x180066a4e  mov     [rbx+14h], eax
0x180066a51  mov     [rsp+0F8h+arg_0], r12
0x180066a59  mov     r12, rsi
0x180066a5c  movups  xmmword ptr [rbx], xmm0
0x180066a5f  mov     [rsp+0F8h+var_38], r14
0x180066a67  xor     r14b, r14b
0x180066a6a  mov     [rbx+2], ax
0x180066a6e  lea     rax, [rbx+1Ch]
0x180066a72  mov     [rbx+8], rax
0x180066a76  mov     [rsp+0F8h+var_B8], rsi
0x180066a7b  mov     [rsp+0F8h+var_90], rsi
0x180066a80  test    rbp, rbp
0x180066a83  jz      loc_180066BE9
0x180066a89  mov     r8, [rdi]
0x180066a8c  lea     r9, [rsp+0F8h+FltObject]
0x180066a94  mov     rcx, [rbp+38h]
0x180066a98  mov     rdx, rbp
0x180066a9b  call    FltpGetFltVolumeFromAttachmentList
0x180066aa0  mov     r8d, 9BAh
0x180066aa6  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180066aad  xor     r9d, r9d
0x180066ab0  mov     ecx, eax
0x180066ab2  call    FltpDbgStatus
0x180066ab7  test    eax, eax
0x180066ab9  js      loc_180066BDC
0x180066abf  call    cs:__imp_KeEnterCriticalRegion
0x180066ac6  nop     dword ptr [rax+rax+00h]
0x180066acb  lea     rcx, [rbp+70h]
0x180066acf  mov     r8b, 1
0x180066ad2  lea     rdx, [rsp+0F8h+var_88]
0x180066ad7  call    cs:__imp_ExAcquireFastResourceShared
0x180066ade  nop     dword ptr [rax+rax+00h]
0x180066ae3  mov     rsi, [rsp+0F8h+FltObject]
0x180066aeb  lea     rcx, [rbp+0D8h]
0x180066af2  mov     rax, [rcx]
0x180066af5  mov     qword ptr [rsp+0F8h+String2.Length], rax
0x180066afa  mov     [rsp+0F8h+var_B0], rsi
0x180066aff  cmp     rax, rcx
0x180066b02  jz      loc_180066B8C
0x180066b08  mov     r12d, dword ptr [rsp+0F8h+var_C8]
0x180066b0d  mov     r15d, 9D2h
0x180066b13  lea     rdx, [rax-78h]
0x180066b17  mov     [rsp+0F8h+var_B8], rdx
0x180066b1c  cmp     [rdx+40h], rsi
0x180066b20  jnz     short loc_180066B69
0x180066b22  test    r12b, r12b
0x180066b25  jz      short loc_180066B31
0x180066b27  mov     rcx, rbp
0x180066b2a  call    FltpvObjectReferenceForFilter
0x180066b2f  jmp     short loc_180066B39
0x180066b31  mov     rcx, rdx; FltObject
0x180066b34  call    FltObjectReference
0x180066b39  mov     r9d, 0C01C000Bh
0x180066b3f  mov     [rsp+0F8h+var_D8], 0
0x180066b48  mov     r8d, r15d
0x180066b4b  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180066b52  mov     ecx, eax
0x180066b54  call    FltpDbgStatus
0x180066b59  test    eax, eax
0x180066b5b  jns     short loc_180066B7F
0x180066b5d  mov     rax, qword ptr [rsp+0F8h+String2.Length]
0x180066b62  lea     rcx, [rbp+0D8h]
0x180066b69  mov     rax, [rax]
0x180066b6c  mov     [rsp+0F8h+var_B8], 0
0x180066b75  mov     qword ptr [rsp+0F8h+String2.Length], rax
0x180066b7a  cmp     rax, rcx
0x180066b7d  jnz     short loc_180066B13
0x180066b7f  mov     r15, [rsp+0F8h+arg_18]
0x180066b87  mov     r12, [rsp+0F8h+var_90]
0x180066b8c  lea     rdx, [rsp+0F8h+var_88]
0x180066b91  lea     rcx, [rbp+70h]
0x180066b95  call    cs:__imp_ExReleaseFastResource
0x180066b9c  nop     dword ptr [rax+rax+00h]
0x180066ba1  call    cs:__imp_KeLeaveCriticalRegion
0x180066ba8  nop     dword ptr [rax+rax+00h]
0x180066bad  cmp     [rsp+0F8h+var_B8], 0
0x180066bb3  jz      short loc_180066BE9
0x180066bb5  cmp     [rsp+0F8h+var_C8], r14b
0x180066bba  jz      short loc_180066BC9
0x180066bbc  mov     rdx, rsi
0x180066bbf  mov     rcx, rbp
0x180066bc2  call    FltpvObjectDereferenceForFilter
0x180066bc7  jmp     short loc_180066BD1
0x180066bc9  mov     rcx, rsi; FltObject
0x180066bcc  call    FltObjectDereference
0x180066bd1  mov     [rsp+0F8h+var_B0], 0
0x180066bda  jmp     short loc_180066BE9
0x180066bdc  mov     rax, [rsp+0F8h+FltObject]
0x180066be4  mov     [rsp+0F8h+var_B0], rax
0x180066be9  mov     rcx, [rdi]; FileSystemDeviceObject
0x180066bec  lea     rdx, [rsp+0F8h+DiskDeviceObject]; DiskDeviceObject
0x180066bf1  call    cs:__imp_IoGetDiskDeviceObject
0x180066bf8  nop     dword ptr [rax+rax+00h]
0x180066bfd  mov     esi, eax
0x180066bff  cmp     eax, 0C000000Dh
0x180066c04  jnz     short loc_180066C34
0x180066c06  mov     rcx, [rdi]; Object
0x180066c09  cmp     qword ptr [rcx+38h], 0
0x180066c0e  jnz     short loc_180066C34
0x180066c10  mov     rdx, [rcx+138h]
0x180066c17  cmp     qword ptr [rdx+48h], 0
0x180066c1c  jnz     short loc_180066C34
0x180066c1e  mov     r14b, 1
0x180066c21  mov     [rsp+0F8h+DiskDeviceObject], rcx
0x180066c26  call    cs:__imp_ObfReferenceObject
0x180066c2d  nop     dword ptr [rax+rax+00h]
0x180066c32  xor     esi, esi
0x180066c34  mov     r8d, 0A0Ah
0x180066c3a  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180066c41  xor     r9d, r9d
0x180066c44  mov     ecx, esi
0x180066c46  call    FltpDbgStatus
0x180066c4b  test    eax, eax
0x180066c4d  js      short loc_180066C65
0x180066c4f  cmp     [rsp+0F8h+var_C8], 0
0x180066c54  jz      short loc_180066C65
0x180066c56  lea     rdx, [rsp+0F8h+var_C0]
0x180066c5b  mov     rcx, rbp
0x180066c5e  call    FltpvPreAllocateVerifierObject
0x180066c63  mov     esi, eax
0x180066c65  mov     r8d, 0A10h
0x180066c6b  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180066c72  xor     r9d, r9d
0x180066c75  mov     ecx, esi
0x180066c77  call    FltpDbgStatus
0x180066c7c  test    eax, eax
0x180066c7e  js      loc_180066EA8
0x180066c84  mov     rcx, [rsp+0F8h+DiskDeviceObject]; Object
0x180066c89  mov     rdx, rbx
0x180066c8c  call    FltpGetObjectName
0x180066c91  mov     rcx, [rsp+0F8h+DiskDeviceObject]; Object
0x180066c96  mov     esi, eax
0x180066c98  call    cs:__imp_ObfDereferenceObject
0x180066c9f  nop     dword ptr [rax+rax+00h]
0x180066ca4  mov     r8d, 0A16h
0x180066caa  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180066cb1  xor     r9d, r9d
0x180066cb4  mov     ecx, esi
0x180066cb6  call    FltpDbgStatus
0x180066cbb  test    eax, eax
0x180066cbd  js      loc_180066EA8
0x180066cc3  test    r14b, r14b
0x180066cc6  jz      short loc_180066CFE
0x180066cc8  lea     rax, aDeviceMup; "\\Device\\Mup"
0x180066ccf  mov     qword ptr [rsp+0F8h+String2.Length], 180016h
0x180066cd8  mov     r8b, 1; CaseInSensitive
0x180066cdb  mov     [rsp+0F8h+String2.Buffer], rax
0x180066ce0  lea     rdx, [rsp+0F8h+String2]; String2
0x180066ce5  mov     rcx, rbx; String1
0x180066ce8  call    cs:__imp_RtlCompareUnicodeString
0x180066cef  nop     dword ptr [rax+rax+00h]
0x180066cf4  test    eax, eax
0x180066cf6  mov     ecx, 0C0000369h
0x180066cfb  cmovnz  esi, ecx
0x180066cfe  mov     r8d, 0A27h
0x180066d04  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180066d0b  xor     r9d, r9d
0x180066d0e  mov     ecx, esi
0x180066d10  call    FltpDbgStatus
0x180066d15  test    eax, eax
0x180066d17  js      loc_180066EA8
0x180066d1d  movzx   ecx, word ptr [rdi+8]
0x180066d21  lea     r14, [rdi+8]
0x180066d25  add     cx, [rbx]
0x180066d28  mov     eax, 0D2h
0x180066d2d  add     cx, ax
0x180066d30  mov     eax, 150h
0x180066d35  cmp     cx, ax
0x180066d38  ja      short loc_180066D3F
0x180066d3a  xor     r12d, r12d
0x180066d3d  jmp     short loc_180066D54
0x180066d3f  movzx   edx, cx
0x180066d42  lea     r12, [rdx-111h]
0x180066d49  shr     r12, 6
0x180066d4d  cmp     r12w, 7
0x180066d52  jnb     short loc_180066D8D
0x180066d54  lea     rax, qword_18003F840
0x180066d5b  movzx   ecx, r12w
0x180066d5f  shl     rcx, 7
0x180066d63  add     rcx, rax; Lookaside
0x180066d66  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180066d6d  nop     dword ptr [rax+rax+00h]
0x180066d72  mov     rdi, rax
0x180066d75  shl     r12w, 6
0x180066d7a  mov     eax, 150h
0x180066d7f  mov     byte ptr [rsp+0F8h+FltObject], 1
0x180066d87  add     r12w, ax
0x180066d8b  jmp     short loc_180066DB3
0x180066d8d  movzx   r12d, cx
0x180066d91  mov     byte ptr [rsp+0F8h+FltObject], 0
0x180066d99  mov     ecx, 100h
0x180066d9e  mov     r8d, 386E4D46h
0x180066da4  call    cs:__imp_ExAllocatePool2
0x180066dab  nop     dword ptr [rax+rax+00h]
0x180066db0  mov     rdi, rax
0x180066db3  test    rdi, rdi
0x180066db6  jz      loc_180066E9E
0x180066dbc  xor     edx, edx; Val
0x180066dbe  mov     r8d, 0D0h; Size
0x180066dc4  mov     rcx, rdi; void *
0x180066dc7  call    memset
0x180066dcc  cmp     byte ptr [rsp+0F8h+FltObject], 0
0x180066dd4  mov     dword ptr [rdi+0C8h], 1
0x180066dde  mov     word ptr [rdi], 0F204h
0x180066de3  mov     [rdi+2], r12w
0x180066de8  jz      short loc_180066DF1
0x180066dea  or      dword ptr [rdi+48h], 1000h
0x180066df1  or      dword ptr [rdi+48h], 800h
0x180066df8  mov     ecx, 0FFFEh
0x180066dfd  movzx   eax, r12w
0x180066e01  xorps   xmm0, xmm0
0x180066e04  movups  xmmword ptr [rdi+58h], xmm0
0x180066e08  add     rax, 0FFFFFFFFFFFFFF30h
0x180066e0e  lea     r12, [rdi+50h]
0x180066e12  cmp     rax, rcx
0x180066e15  mov     rdx, rbx; SourceString
0x180066e18  cmova   rax, rcx
0x180066e1c  lea     rcx, [r12+8]; DestinationString
0x180066e21  mov     [rdi+5Ah], ax
0x180066e25  lea     rax, [rdi+0D0h]
0x180066e2c  mov     [rdi+60h], rax
0x180066e30  mov     word ptr [r12], 78h ; 'x'
0x180066e37  mov     dword ptr [r12+4], 2
0x180066e40  call    cs:__imp_RtlCopyUnicodeString
0x180066e47  nop     dword ptr [rax+rax+00h]
0x180066e4c  mov     rdx, r14; Source
0x180066e4f  lea     rcx, [r12+8]; Destination
0x180066e54  call    cs:__imp_RtlAppendUnicodeStringToString
0x180066e5b  nop     dword ptr [rax+rax+00h]
0x180066e60  movzx   eax, word ptr [rbx]
0x180066e63  mov     r14d, dword ptr [rsp+0F8h+var_C8]
0x180066e68  mov     rdi, [rsp+0F8h+var_C0]
0x180066e6d  mov     [r12+1Ah], ax
0x180066e73  mov     [r12+18h], ax
0x180066e79  mov     rax, [r12+10h]
0x180066e7e  mov     [r12+20h], rax
0x180066e83  test    r14b, r14b
0x180066e86  jz      short loc_180066EB2
0x180066e88  mov     r9, rdi
0x180066e8b  mov     r8d, 4
0x180066e91  mov     rdx, r12
0x180066e94  mov     rcx, rbp
0x180066e97  call    FltpvLinkResourceToFilter
0x180066e9c  jmp     short loc_180066EB2
0x180066e9e  mov     r12, [rsp+0F8h+var_90]
0x180066ea3  mov     esi, 0C000009Ah
0x180066ea8  mov     r14d, dword ptr [rsp+0F8h+var_C8]
  ... truncated ...
```
