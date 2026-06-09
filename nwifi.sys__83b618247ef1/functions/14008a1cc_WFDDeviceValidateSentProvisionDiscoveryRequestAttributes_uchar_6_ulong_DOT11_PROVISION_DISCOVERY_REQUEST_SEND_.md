# WFDDeviceValidateSentProvisionDiscoveryRequestAttributes(uchar (*)[6],ulong,_DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS *,uchar,uchar)

- ea: `0x14008a1cc`
- end: `0x14008a421`
- name: `?WFDDeviceValidateSentProvisionDiscoveryRequestAttributes@@YAEPEAY05EKPEAU_DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS@@EE@Z`
- size: `597`
- prototype: `unsigned __int8 __usercall@<al>(unsigned __int8 (*)[6]@<rcx>, unsigned int@<edx>, struct _DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS *@<r8>, unsigned __int8@<r9b>, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140081b44`

## callees

- `0x14000d22c`
- `0x14002f1bc`
- `0x14002ffb4`
- `0x14008970c`
- `0x14008a1cc`
- `0x140097e38`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a28f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a28f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a375`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a375`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a389`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a389`

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
0x14008a1cc  mov     [rsp+arg_0], rbx
0x14008a1d1  mov     [rsp+arg_8], rbp
0x14008a1d6  mov     [rsp+arg_18], r9b
0x14008a1db  push    rdi
0x14008a1dc  push    r12
0x14008a1de  push    r13
0x14008a1e0  push    r14
0x14008a1e2  push    r15
0x14008a1e4  sub     rsp, 40h
0x14008a1e8  mov     rbp, r8
0x14008a1eb  mov     r13, rcx
0x14008a1ee  mov     r8d, edx
0x14008a1f1  mov     r10d, [rbp+1Ch]
0x14008a1f5  lea     r15, [rbp+18h]
0x14008a1f9  test    r10d, r10d
0x14008a1fc  jz      short loc_14008A20B
0x14008a1fe  mov     r9d, [r15]
0x14008a201  cmp     r9d, 20h ; ' '
0x14008a205  jb      loc_14008A3C7
0x14008a20b  mov     r9d, [r15]
0x14008a20e  lea     eax, [r9+r10]
0x14008a212  cmp     eax, r9d
0x14008a215  jb      loc_14008A3C7
0x14008a21b  cmp     eax, r8d
0x14008a21e  ja      loc_14008A3C7
0x14008a224  lea     rbx, WPP_GLOBAL_Control
0x14008a22b  test    r10d, r10d
0x14008a22e  jz      short loc_14008A285
0x14008a230  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a237  cmp     rcx, rbx
0x14008a23a  jz      short loc_14008A285
0x14008a23c  cmp     byte ptr [rcx+29h], 3
0x14008a240  jb      short loc_14008A285
0x14008a242  bt      dword ptr [rcx+2Ch], 15h
0x14008a247  jnb     short loc_14008A285
0x14008a249  mov     rcx, [rcx+18h]
0x14008a24d  lea     rax, [r9+rbp]
0x14008a251  xorps   xmm0, xmm0
0x14008a254  lea     r9, [rsp+68h+var_38]
0x14008a259  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x14008a25e  mov     word ptr [rsp+68h+var_38], r10w
0x14008a264  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a26b  mov     [rsp+68h+var_38+8], rax
0x14008a270  mov     edx, 121h
0x14008a275  movaps  xmm0, xmmword ptr [rsp+68h+var_38]
0x14008a27a  movdqa  xmmword ptr [rsp+68h+var_38], xmm0
0x14008a280  call    WPP_SF__HEX_
0x14008a285  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14008a28c  mov     rcx, r12; Lookaside
0x14008a28f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008a296  nop     dword ptr [rax+rax+00h]
0x14008a29b  mov     r14, rax
0x14008a29e  test    rax, rax
0x14008a2a1  jz      loc_14008A397
0x14008a2a7  mov     [rax], r12
0x14008a2aa  xor     edx, edx; Val
0x14008a2ac  lea     r12, [rax+10h]
0x14008a2b0  mov     dword ptr [rax+8], 30337776h
0x14008a2b7  mov     rcx, r12; void *
0x14008a2ba  mov     r8d, 0C0h; Size
0x14008a2c0  call    memset
0x14008a2c5  mov     edx, [r15]
0x14008a2c8  mov     r9, r12
0x14008a2cb  mov     r8d, [rbp+1Ch]
0x14008a2cf  add     rdx, rbp
0x14008a2d2  mov     rcx, r13
0x14008a2d5  call    WFDValidateIncomingProvisionDiscoveryRequestIEs
0x14008a2da  test    al, al
0x14008a2dc  jnz     short loc_14008A2FE
0x14008a2de  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a2e5  cmp     rcx, rbx
0x14008a2e8  jz      short loc_14008A351
0x14008a2ea  cmp     byte ptr [rcx+29h], 2
0x14008a2ee  jb      short loc_14008A351
0x14008a2f0  bt      dword ptr [rcx+2Ch], 15h
0x14008a2f5  jnb     short loc_14008A351
0x14008a2f7  mov     edx, 123h
0x14008a2fc  jmp     short loc_14008A341
0x14008a2fe  mov     al, [rsp+68h+arg_20]
0x14008a305  mov     r8b, 1; unsigned __int8
0x14008a308  mov     r9b, [rsp+68h+arg_18]; unsigned __int8
0x14008a310  mov     rdx, r13; unsigned __int8 (*)[6]
0x14008a313  mov     rcx, r12; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x14008a316  mov     [rsp+68h+var_48], al; char
0x14008a31a  call    ?WFDDeviceValidateProvisionDiscoveryRequestAttributes@@YAEPEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAY05EEEE@Z; WFDDeviceValidateProvisionDiscoveryRequestAttributes(_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar (*)[6],uchar,uchar,uchar)
0x14008a31f  test    al, al
0x14008a321  jnz     short loc_14008A351
0x14008a323  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a32a  cmp     rcx, rbx
0x14008a32d  jz      short loc_14008A351
0x14008a32f  cmp     byte ptr [rcx+29h], 2
0x14008a333  jb      short loc_14008A351
0x14008a335  bt      dword ptr [rcx+2Ch], 15h
0x14008a33a  jnb     short loc_14008A351
0x14008a33c  mov     edx, 124h
0x14008a341  mov     rcx, [rcx+18h]
0x14008a345  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a34c  call    WPP_SF_
0x14008a351  mov     eax, 10h
0x14008a356  lea     rcx, [rax+r14]
0x14008a35a  test    rcx, rcx
0x14008a35d  jz      loc_14008A406
0x14008a363  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14008a367  mov     rax, [rcx]
0x14008a36a  test    rax, rax
0x14008a36d  jz      short loc_14008A386
0x14008a36f  mov     rdx, rcx; Entry
0x14008a372  mov     rcx, rax; Lookaside
0x14008a375  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008a37c  nop     dword ptr [rax+rax+00h]
0x14008a381  jmp     loc_14008A406
0x14008a386  mov     edx, [rcx+8]; Tag
0x14008a389  call    cs:__imp_ExFreePoolWithTag
0x14008a390  nop     dword ptr [rax+rax+00h]
0x14008a395  jmp     short loc_14008A406
0x14008a397  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a39e  cmp     rcx, rbx
0x14008a3a1  jz      short loc_14008A406
0x14008a3a3  cmp     byte ptr [rcx+29h], 3
0x14008a3a7  jb      short loc_14008A406
0x14008a3a9  bt      dword ptr [rcx+2Ch], 15h
0x14008a3ae  jnb     short loc_14008A406
0x14008a3b0  mov     rcx, [rcx+18h]
0x14008a3b4  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a3bb  mov     edx, 122h
0x14008a3c0  call    WPP_SF_
0x14008a3c5  jmp     short loc_14008A406
0x14008a3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a3ce  lea     rbx, WPP_GLOBAL_Control
0x14008a3d5  cmp     rcx, rbx
0x14008a3d8  jz      short loc_14008A406
0x14008a3da  cmp     byte ptr [rcx+29h], 1
0x14008a3de  jb      short loc_14008A406
0x14008a3e0  bt      dword ptr [rcx+2Ch], 15h
0x14008a3e5  jnb     short loc_14008A406
0x14008a3e7  mov     rcx, [rcx+18h]
0x14008a3eb  mov     edx, 120h
0x14008a3f0  mov     [rsp+68h+var_40], r8d
0x14008a3f5  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a3fc  mov     dword ptr [rsp+68h+var_48], r10d
0x14008a401  call    WPP_SF_lll
0x14008a406  mov     rbx, [rsp+68h+arg_0]
0x14008a40b  mov     al, 1
0x14008a40d  mov     rbp, [rsp+68h+arg_8]
0x14008a412  add     rsp, 40h
0x14008a416  pop     r15
0x14008a418  pop     r14
0x14008a41a  pop     r13
0x14008a41c  pop     r12
0x14008a41e  pop     rdi
0x14008a41f  retn
```
