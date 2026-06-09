# CompleteQueuedIrpsForPolled

- ea: `0x18000adc0`
- end: `0x18000b031`
- name: `CompleteQueuedIrpsForPolled`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ac70`

## callees

- `0x18000adc0`
- `0x18000c250`
- `0x18000cd00`
- `0x180023538`
- `0x180023610`
- `0x180023a40`
- `0x180027d00`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000af55`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000af55`
- `ntoskrnl!IofCompleteRequest` at `0x18000b007`
- `ntoskrnl!IofCompleteRequest` at `0x18000b007`

## pseudocode

```c
__int64 __fastcall CompleteQueuedIrpsForPolled(_QWORD *a1, __int64 a2, const void *a3, unsigned int a4, int a5)
{
  size_t v5; // r12
  __int64 result; // rax
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  __int64 SystemIrp; // rax
  int v17; // r8d
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  __int64 SessionIrp; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rax
  __int64 Irp; // rax
  __int64 v25; // rcx
  IRP *v26; // rdi
  __int128 *v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // r15
  _MDL *MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-58h]
  ULONG Priority; // [rsp+28h] [rbp-50h]
  int v34; // [rsp+30h] [rbp-48h]
  int v35; // [rsp+38h] [rbp-40h]
  __int128 v36; // [rsp+60h] [rbp-18h] BYREF

  v5 = a4;
  result = GetHidclassCollection(a1, a2);
  v9 = result;
  if ( result )
  {
    v10 = *(unsigned int *)(result + 4);
    v11 = a1[36];
    v36 = 0;
    v12 = *(_QWORD *)(v11 + 8 * v10);
    *((_QWORD *)&v36 + 1) = &v36;
    *(_QWORD *)&v36 = &v36;
    if ( *(_DWORD *)(v9 + 336) )
    {
      while ( 1 )
      {
        SystemIrp = DequeuePolledReadSystemIrp(v9);
        if ( !SystemIrp )
          goto LABEL_16;
        v14 = (_QWORD *)*((_QWORD *)&v36 + 1);
        if ( **((__int128 ***)&v36 + 1) != &v36 )
          break;
        v15 = (_QWORD *)(SystemIrp + 168);
        *v15 = &v36;
        v15[1] = v14;
        *v14 = v15;
        *((_QWORD *)&v36 + 1) = v15;
      }
LABEL_39:
      __fastfail(3u);
    }
    v13 = v9;
    if ( !*(_BYTE *)(v12 + 289) )
    {
      while ( 1 )
      {
        Irp = DequeuePolledReadIrp(v13);
        if ( !Irp )
          goto LABEL_16;
        v21 = (_QWORD *)*((_QWORD *)&v36 + 1);
        if ( **((__int128 ***)&v36 + 1) != &v36 )
          goto LABEL_39;
        v22 = (_QWORD *)(Irp + 168);
        v22[1] = *((_QWORD *)&v36 + 1);
        *v22 = &v36;
        *v21 = v22;
        v13 = v9;
        *((_QWORD *)&v36 + 1) = v22;
      }
    }
    while ( 1 )
    {
      SessionIrp = DequeuePolledReadSessionIrp(v13);
      if ( !SessionIrp )
        break;
      v18 = (_QWORD *)*((_QWORD *)&v36 + 1);
      if ( **((__int128 ***)&v36 + 1) != &v36 )
        goto LABEL_39;
      v19 = (_QWORD *)(SessionIrp + 168);
      v19[1] = *((_QWORD *)&v36 + 1);
      *v19 = &v36;
      *v18 = v19;
      v13 = v9;
      *((_QWORD *)&v36 + 1) = v19;
    }
LABEL_16:
    while ( 1 )
    {
      result = v36;
      if ( (__int128 *)v36 == &v36 )
        break;
      if ( *(__int128 **)(v36 + 8) != &v36 )
        goto LABEL_39;
      v25 = *(_QWORD *)v36;
      if ( *(_QWORD *)(*(_QWORD *)v36 + 8LL) != (_QWORD)v36 )
        goto LABEL_39;
      *(_QWORD *)&v36 = *(_QWORD *)v36;
      v26 = (IRP *)(result - 168);
      v27 = &v36;
      *(_QWORD *)(v25 + 8) = &v36;
      v28 = *(_QWORD *)(result - 168 + 184);
      v29 = *(_QWORD *)(*(_QWORD *)(v28 + 48) + 24LL);
      if ( a5 >= 0 )
      {
        MdlAddress = v26->MdlAddress;
        if ( MdlAddress
          && ((MdlAddress->MdlFlags & 5) == 0
            ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u))
            : (MappedSystemVa = MdlAddress->MappedSystemVa),
              MappedSystemVa && *(_DWORD *)(v28 + 8) >= (unsigned int)v5) )
        {
          memmove(MappedSystemVa, a3, v5);
          v26->IoStatus.Information = v5;
        }
        else
        {
          a5 = -1073741592;
        }
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || (LOBYTE(v27) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      {
        LOBYTE(v27) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v17) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v17) = 0;
      }
      if ( (_BYTE)v27 || (_BYTE)v17 )
        WPP_RECORDER_AND_TRACE_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v27,
          v17,
          a1[84],
          BugCheckOnFailure,
          Priority,
          v34,
          v35,
          *a1,
          (char)v26,
          v29,
          v26->IoStatus.Status);
      v26->IoStatus.Status = a5;
      IofCompleteRequest(v26, 6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000adc0  push    rbp
0x18000adc2  push    rbx
0x18000adc3  push    rsi
0x18000adc4  push    rdi
0x18000adc5  push    r12
0x18000adc7  push    r13
0x18000adc9  push    r14
0x18000adcb  push    r15
0x18000adcd  mov     rbp, rsp
0x18000add0  sub     rsp, 78h
0x18000add4  mov     r12d, r9d
0x18000add7  mov     r13, r8
0x18000adda  mov     r14, rcx
0x18000addd  call    GetHidclassCollection
0x18000ade2  xor     edi, edi
0x18000ade4  mov     rbx, rax
0x18000ade7  test    rax, rax
0x18000adea  jz      loc_18000B01F
0x18000adf0  lea     rcx, [rbp+var_18]
0x18000adf4  mov     r8d, [rax+4]
0x18000adf8  xorps   xmm0, xmm0
0x18000adfb  mov     rdx, [r14+120h]
0x18000ae02  movups  [rbp+var_18], xmm0
0x18000ae06  mov     rax, [rdx+r8*8]
0x18000ae0a  mov     qword ptr [rbp+var_18+8], rcx
0x18000ae0e  lea     rcx, [rbp+var_18]
0x18000ae12  mov     qword ptr [rbp+var_18], rcx
0x18000ae16  cmp     [rbx+150h], edi
0x18000ae1c  jnz     short loc_18000AE58
0x18000ae1e  mov     rcx, rbx
0x18000ae21  cmp     [rax+121h], dil
0x18000ae28  jnz     short loc_18000AE93
0x18000ae2a  jmp     loc_18000AECB
0x18000ae2f  mov     rcx, qword ptr [rbp+var_18+8]
0x18000ae33  lea     rdx, [rbp+var_18]
0x18000ae37  cmp     [rcx], rdx
0x18000ae3a  jnz     loc_18000B018
0x18000ae40  add     rax, 0A8h
0x18000ae46  lea     rdx, [rbp+var_18]
0x18000ae4a  mov     [rax], rdx
0x18000ae4d  mov     [rax+8], rcx
0x18000ae51  mov     [rcx], rax
0x18000ae54  mov     qword ptr [rbp+var_18+8], rax
0x18000ae58  mov     rcx, rbx
0x18000ae5b  call    DequeuePolledReadSystemIrp
0x18000ae60  test    rax, rax
0x18000ae63  jnz     short loc_18000AE2F
0x18000ae65  jmp     short loc_18000AED5
0x18000ae67  mov     rcx, qword ptr [rbp+var_18+8]
0x18000ae6b  lea     rdx, [rbp+var_18]
0x18000ae6f  cmp     [rcx], rdx
0x18000ae72  jnz     loc_18000B018
0x18000ae78  add     rax, 0A8h
0x18000ae7e  lea     rdx, [rbp+var_18]
0x18000ae82  mov     [rax+8], rcx
0x18000ae86  mov     [rax], rdx
0x18000ae89  mov     [rcx], rax
0x18000ae8c  mov     rcx, rbx
0x18000ae8f  mov     qword ptr [rbp+var_18+8], rax
0x18000ae93  call    DequeuePolledReadSessionIrp
0x18000ae98  test    rax, rax
0x18000ae9b  jnz     short loc_18000AE67
0x18000ae9d  jmp     short loc_18000AED5
0x18000ae9f  mov     rcx, qword ptr [rbp+var_18+8]
0x18000aea3  lea     rdx, [rbp+var_18]
0x18000aea7  cmp     [rcx], rdx
0x18000aeaa  jnz     loc_18000B018
0x18000aeb0  add     rax, 0A8h
0x18000aeb6  lea     rdx, [rbp+var_18]
0x18000aeba  mov     [rax+8], rcx
0x18000aebe  mov     [rax], rdx
0x18000aec1  mov     [rcx], rax
0x18000aec4  mov     rcx, rbx
0x18000aec7  mov     qword ptr [rbp+var_18+8], rax
0x18000aecb  call    DequeuePolledReadIrp
0x18000aed0  test    rax, rax
0x18000aed3  jnz     short loc_18000AE9F
0x18000aed5  mov     esi, [rbp+arg_20]
0x18000aed8  mov     rax, qword ptr [rbp+var_18]
0x18000aedc  lea     rcx, [rbp+var_18]
0x18000aee0  cmp     rax, rcx
0x18000aee3  jz      loc_18000B01F
0x18000aee9  lea     rcx, [rbp+var_18]
0x18000aeed  cmp     [rax+8], rcx
0x18000aef1  jnz     loc_18000B018
0x18000aef7  mov     rcx, [rax]
0x18000aefa  cmp     [rcx+8], rax
0x18000aefe  jnz     loc_18000B018
0x18000af04  mov     qword ptr [rbp+var_18], rcx
0x18000af08  lea     rdi, [rax-0A8h]
0x18000af0f  lea     rdx, [rbp+var_18]
0x18000af13  xor     r9d, r9d; RequestedAddress
0x18000af16  mov     [rcx+8], rdx
0x18000af1a  mov     rbx, [rdi+0B8h]
0x18000af21  mov     rax, [rbx+30h]
0x18000af25  mov     r15, [rax+18h]
0x18000af29  test    esi, esi
0x18000af2b  js      short loc_18000AF8B
0x18000af2d  mov     rcx, [rdi+8]; MemoryDescriptorList
0x18000af31  test    rcx, rcx
0x18000af34  jz      short loc_18000AF86
0x18000af36  test    byte ptr [rcx+0Ah], 5
0x18000af3a  jz      short loc_18000AF42
0x18000af3c  mov     rax, [rcx+18h]
0x18000af40  jmp     short loc_18000AF64
0x18000af42  xor     edx, edx; AccessMode
0x18000af44  mov     [rsp+78h+Priority], 40000010h; Priority
0x18000af4c  mov     [rsp+78h+BugCheckOnFailure], r9d; BugCheckOnFailure
0x18000af51  lea     r8d, [rdx+1]; CacheType
0x18000af55  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000af5c  nop     dword ptr [rax+rax+00h]
0x18000af61  xor     r9d, r9d
0x18000af64  test    rax, rax
0x18000af67  jz      short loc_18000AF86
0x18000af69  cmp     [rbx+8], r12d
0x18000af6d  jb      short loc_18000AF86
0x18000af6f  mov     r8, r12; Size
0x18000af72  mov     rdx, r13; Src
0x18000af75  mov     rcx, rax; void *
0x18000af78  call    memmove
0x18000af7d  xor     r9d, r9d
0x18000af80  mov     [rdi+38h], r12
0x18000af84  jmp     short loc_18000AF8B
0x18000af86  mov     esi, 0C00000E8h
0x18000af8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af92  lea     rax, WPP_GLOBAL_Control
0x18000af99  cmp     rcx, rax
0x18000af9c  jz      short loc_18000AFAD
0x18000af9e  mov     eax, [rcx+2Ch]
0x18000afa1  test    al, 10h
0x18000afa3  jz      short loc_18000AFAD
0x18000afa5  cmp     byte ptr [rcx+29h], 5
0x18000afa9  mov     dl, 1
0x18000afab  jnb     short loc_18000AFB0
0x18000afad  mov     dl, r9b
0x18000afb0  lea     rax, WPP_RECORDER_INITIALIZED
0x18000afb7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000afbe  jz      short loc_18000AFCA
0x18000afc0  mov     r8b, 1
0x18000afc3  cmp     [rcx+48h], r9w
0x18000afc8  jnz     short loc_18000AFCD
0x18000afca  mov     r8b, r9b
0x18000afcd  test    dl, dl
0x18000afcf  jnz     short loc_18000AFD6
0x18000afd1  test    r8b, r8b
0x18000afd4  jz      short loc_18000AFFF
0x18000afd6  mov     eax, [rdi+30h]
0x18000afd9  mov     r9, [r14+2A0h]
0x18000afe0  mov     rcx, [rcx+18h]
0x18000afe4  mov     [rsp+78h+var_20], eax
0x18000afe8  mov     rax, [r14]
0x18000afeb  mov     [rsp+78h+var_28], r15
0x18000aff0  mov     [rsp+78h+var_30], rdi
0x18000aff5  mov     [rsp+78h+var_38], rax
0x18000affa  call    WPP_RECORDER_AND_TRACE_SF_qqqd
0x18000afff  mov     dl, 6; PriorityBoost
0x18000b001  mov     [rdi+30h], esi
0x18000b004  mov     rcx, rdi; Irp
0x18000b007  call    cs:__imp_IofCompleteRequest
0x18000b00e  nop     dword ptr [rax+rax+00h]
0x18000b013  jmp     loc_18000AED8
0x18000b018  mov     ecx, 3
0x18000b01d  int     29h; Win8: RtlFailFast(ecx)
0x18000b01f  add     rsp, 78h
0x18000b023  pop     r15
0x18000b025  pop     r14
0x18000b027  pop     r13
0x18000b029  pop     r12
0x18000b02b  pop     rdi
0x18000b02c  pop     rsi
0x18000b02d  pop     rbx
0x18000b02e  pop     rbp
0x18000b02f  retn
```
