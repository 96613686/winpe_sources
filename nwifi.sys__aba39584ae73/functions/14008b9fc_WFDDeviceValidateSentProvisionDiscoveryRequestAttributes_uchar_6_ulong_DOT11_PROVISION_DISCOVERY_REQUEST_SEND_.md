# WFDDeviceValidateSentProvisionDiscoveryRequestAttributes(uchar (*)[6],ulong,_DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS *,uchar,uchar)

- ea: `0x14008b9fc`
- end: `0x14008bc51`
- name: `?WFDDeviceValidateSentProvisionDiscoveryRequestAttributes@@YAEPEAY05EKPEAU_DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS@@EE@Z`
- size: `597`
- prototype: `unsigned __int8 __usercall@<al>(unsigned __int8 (*)[6]@<rcx>, unsigned int@<edx>, struct _DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS *@<r8>, unsigned __int8@<r9b>, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140083374`

## callees

- `0x14000d21c`
- `0x14002f44c`
- `0x140030244`
- `0x14008af3c`
- `0x14008b9fc`
- `0x140099618`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008babf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008babf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008bba5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008bba5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bbb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bbb9`

## pseudocode

```c
unsigned __int8 __fastcall WFDDeviceValidateSentProvisionDiscoveryRequestAttributes(
        unsigned __int8 (*a1)[6],
        unsigned int a2,
        struct _DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS *a3,
        char a4,
        char a5)
{
  int v7; // r10d
  unsigned int *v8; // r15
  __int64 v9; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  char *v11; // rax
  ULONG *v12; // r14
  struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *v13; // r12
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  _QWORD v17[7]; // [rsp+30h] [rbp-38h] BYREF

  v7 = *((_DWORD *)a3 + 7);
  v8 = (unsigned int *)((char *)a3 + 24);
  if ( v7 && (v9 = *v8, (unsigned int)v9 < 0x20) || (v9 = *v8, (int)v9 + v7 < (unsigned int)v9) || (int)v9 + v7 > a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 288, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v9, v7, a2);
    }
  }
  else
  {
    if ( v7
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v17[0] = (unsigned __int16)v7;
      v17[1] = (char *)a3 + v9;
      WPP_SF__HEX_(AttachedDevice, 289, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v17);
    }
    v11 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
    v12 = (ULONG *)v11;
    if ( v11 )
    {
      *(_QWORD *)v11 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      v13 = (struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *)(v11 + 16);
      *((_DWORD *)v11 + 2) = 808679286;
      memset(v11 + 16, 0, 0xC0u);
      if ( WFDValidateIncomingProvisionDiscoveryRequestIEs(
             (__int64)a1,
             (unsigned __int8 *)a3 + *v8,
             *((_DWORD *)a3 + 7),
             (__int64)v13) )
      {
        if ( !WFDDeviceValidateProvisionDiscoveryRequestAttributes(v13, a1, 1, a4, a5) )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
          {
            v15 = 292;
            goto LABEL_21;
          }
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
        {
          v15 = 291;
LABEL_21:
          WPP_SF_(v14->AttachedDevice, v15, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        }
      }
      if ( v12 != (ULONG *)-16LL )
      {
        if ( *(_QWORD *)v12 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12, v12);
        else
          ExFreePoolWithTag(v12, v12[2]);
      }
      return 1;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 290, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14008b9fc  mov     [rsp+arg_0], rbx
0x14008ba01  mov     [rsp+arg_8], rbp
0x14008ba06  mov     [rsp+arg_18], r9b
0x14008ba0b  push    rdi
0x14008ba0c  push    r12
0x14008ba0e  push    r13
0x14008ba10  push    r14
0x14008ba12  push    r15
0x14008ba14  sub     rsp, 40h
0x14008ba18  mov     rbp, r8
0x14008ba1b  mov     r13, rcx
0x14008ba1e  mov     r8d, edx
0x14008ba21  mov     r10d, [rbp+1Ch]
0x14008ba25  lea     r15, [rbp+18h]
0x14008ba29  test    r10d, r10d
0x14008ba2c  jz      short loc_14008BA3B
0x14008ba2e  mov     r9d, [r15]
0x14008ba31  cmp     r9d, 20h ; ' '
0x14008ba35  jb      loc_14008BBF7
0x14008ba3b  mov     r9d, [r15]
0x14008ba3e  lea     eax, [r9+r10]
0x14008ba42  cmp     eax, r9d
0x14008ba45  jb      loc_14008BBF7
0x14008ba4b  cmp     eax, r8d
0x14008ba4e  ja      loc_14008BBF7
0x14008ba54  lea     rbx, WPP_GLOBAL_Control
0x14008ba5b  test    r10d, r10d
0x14008ba5e  jz      short loc_14008BAB5
0x14008ba60  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ba67  cmp     rcx, rbx
0x14008ba6a  jz      short loc_14008BAB5
0x14008ba6c  cmp     byte ptr [rcx+29h], 3
0x14008ba70  jb      short loc_14008BAB5
0x14008ba72  bt      dword ptr [rcx+2Ch], 15h
0x14008ba77  jnb     short loc_14008BAB5
0x14008ba79  mov     rcx, [rcx+18h]
0x14008ba7d  lea     rax, [r9+rbp]
0x14008ba81  xorps   xmm0, xmm0
0x14008ba84  lea     r9, [rsp+68h+var_38]
0x14008ba89  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x14008ba8e  mov     word ptr [rsp+68h+var_38], r10w
0x14008ba94  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008ba9b  mov     [rsp+68h+var_38+8], rax
0x14008baa0  mov     edx, 121h
0x14008baa5  movaps  xmm0, xmmword ptr [rsp+68h+var_38]
0x14008baaa  movdqa  xmmword ptr [rsp+68h+var_38], xmm0
0x14008bab0  call    WPP_SF__HEX_
0x14008bab5  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14008babc  mov     rcx, r12; Lookaside
0x14008babf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008bac6  nop     dword ptr [rax+rax+00h]
0x14008bacb  mov     r14, rax
0x14008bace  test    rax, rax
0x14008bad1  jz      loc_14008BBC7
0x14008bad7  mov     [rax], r12
0x14008bada  xor     edx, edx; Val
0x14008badc  lea     r12, [rax+10h]
0x14008bae0  mov     dword ptr [rax+8], 30337776h
0x14008bae7  mov     rcx, r12; void *
0x14008baea  mov     r8d, 0C0h; Size
0x14008baf0  call    memset
0x14008baf5  mov     edx, [r15]
0x14008baf8  mov     r9, r12
0x14008bafb  mov     r8d, [rbp+1Ch]
0x14008baff  add     rdx, rbp
0x14008bb02  mov     rcx, r13
0x14008bb05  call    WFDValidateIncomingProvisionDiscoveryRequestIEs
0x14008bb0a  test    al, al
0x14008bb0c  jnz     short loc_14008BB2E
0x14008bb0e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bb15  cmp     rcx, rbx
0x14008bb18  jz      short loc_14008BB81
0x14008bb1a  cmp     byte ptr [rcx+29h], 2
0x14008bb1e  jb      short loc_14008BB81
0x14008bb20  bt      dword ptr [rcx+2Ch], 15h
0x14008bb25  jnb     short loc_14008BB81
0x14008bb27  mov     edx, 123h
0x14008bb2c  jmp     short loc_14008BB71
0x14008bb2e  mov     al, [rsp+68h+arg_20]
0x14008bb35  mov     r8b, 1; unsigned __int8
0x14008bb38  mov     r9b, [rsp+68h+arg_18]; unsigned __int8
0x14008bb40  mov     rdx, r13; unsigned __int8 (*)[6]
0x14008bb43  mov     rcx, r12; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x14008bb46  mov     [rsp+68h+var_48], al; char
0x14008bb4a  call    ?WFDDeviceValidateProvisionDiscoveryRequestAttributes@@YAEPEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAY05EEEE@Z; WFDDeviceValidateProvisionDiscoveryRequestAttributes(_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar (*)[6],uchar,uchar,uchar)
0x14008bb4f  test    al, al
0x14008bb51  jnz     short loc_14008BB81
0x14008bb53  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bb5a  cmp     rcx, rbx
0x14008bb5d  jz      short loc_14008BB81
0x14008bb5f  cmp     byte ptr [rcx+29h], 2
0x14008bb63  jb      short loc_14008BB81
0x14008bb65  bt      dword ptr [rcx+2Ch], 15h
0x14008bb6a  jnb     short loc_14008BB81
0x14008bb6c  mov     edx, 124h
0x14008bb71  mov     rcx, [rcx+18h]
0x14008bb75  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008bb7c  call    WPP_SF_
0x14008bb81  mov     eax, 10h
0x14008bb86  lea     rcx, [rax+r14]
0x14008bb8a  test    rcx, rcx
0x14008bb8d  jz      loc_14008BC36
0x14008bb93  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14008bb97  mov     rax, [rcx]
0x14008bb9a  test    rax, rax
0x14008bb9d  jz      short loc_14008BBB6
0x14008bb9f  mov     rdx, rcx; Entry
0x14008bba2  mov     rcx, rax; Lookaside
0x14008bba5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008bbac  nop     dword ptr [rax+rax+00h]
0x14008bbb1  jmp     loc_14008BC36
0x14008bbb6  mov     edx, [rcx+8]; Tag
0x14008bbb9  call    cs:__imp_ExFreePoolWithTag
0x14008bbc0  nop     dword ptr [rax+rax+00h]
0x14008bbc5  jmp     short loc_14008BC36
0x14008bbc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bbce  cmp     rcx, rbx
0x14008bbd1  jz      short loc_14008BC36
0x14008bbd3  cmp     byte ptr [rcx+29h], 3
0x14008bbd7  jb      short loc_14008BC36
0x14008bbd9  bt      dword ptr [rcx+2Ch], 15h
0x14008bbde  jnb     short loc_14008BC36
0x14008bbe0  mov     rcx, [rcx+18h]
0x14008bbe4  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008bbeb  mov     edx, 122h
0x14008bbf0  call    WPP_SF_
0x14008bbf5  jmp     short loc_14008BC36
0x14008bbf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bbfe  lea     rbx, WPP_GLOBAL_Control
0x14008bc05  cmp     rcx, rbx
0x14008bc08  jz      short loc_14008BC36
0x14008bc0a  cmp     byte ptr [rcx+29h], 1
0x14008bc0e  jb      short loc_14008BC36
0x14008bc10  bt      dword ptr [rcx+2Ch], 15h
0x14008bc15  jnb     short loc_14008BC36
0x14008bc17  mov     rcx, [rcx+18h]
0x14008bc1b  mov     edx, 120h
0x14008bc20  mov     [rsp+68h+var_40], r8d
0x14008bc25  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008bc2c  mov     dword ptr [rsp+68h+var_48], r10d
0x14008bc31  call    WPP_SF_lll
0x14008bc36  mov     rbx, [rsp+68h+arg_0]
0x14008bc3b  mov     al, 1
0x14008bc3d  mov     rbp, [rsp+68h+arg_8]
0x14008bc42  add     rsp, 40h
0x14008bc46  pop     r15
0x14008bc48  pop     r14
0x14008bc4a  pop     r13
0x14008bc4c  pop     r12
0x14008bc4e  pop     rdi
0x14008bc4f  retn
```
