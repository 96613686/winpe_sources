# PmAttributesPhase1(_DEVICE_EXTENSION *,uchar *)

- ea: `0x14002589c`
- end: `0x140025a21`
- name: `?PmAttributesPhase1@@YAJPEAU_DEVICE_EXTENSION@@PEAE@Z`
- size: `389`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400068b0`
- `0x140007674`

## callees

- `0x14000ab3c`
- `0x14000e6f0`
- `0x140010f20`
- `0x14001cc58`
- `0x14002589c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140025999`
- `ntoskrnl!KeWaitForSingleObject` at `0x140025999`
- `ntoskrnl!KeReleaseMutex` at `0x1400259dd`
- `ntoskrnl!KeReleaseMutex` at `0x1400259dd`

## pseudocode

```c
__int64 __fastcall PmAttributesPhase1(struct _DEVICE_EXTENSION *a1, unsigned __int8 *a2)
{
  char *DeviceExtension; // rbx
  bool v5; // zf
  int v6; // ebx
  int PersistedAttributes; // eax
  unsigned int v8; // edi
  __int64 MSFTIdentifier; // rax
  struct _KMUTANT *v10; // r14
  _DWORD v12[4]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h]
  __int128 v14; // [rsp+48h] [rbp-18h]

  memset(&v12[1], 0, 12);
  v14 = 0;
  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  *a2 = 0;
  v5 = *((_DWORD *)a1 + 42) == -1;
  v12[0] = 40;
  v13 = -1;
  if ( v5 )
  {
    *(_QWORD *)&v12[2] = 7;
    v6 = 2;
    return (unsigned int)PmSetDiskAttributes((__int64)a1, (__int64)v12, v6);
  }
  PersistedAttributes = PmGetPersistedAttributes(a1, (unsigned __int64 *)&v12[2]);
  v8 = PersistedAttributes;
  if ( PersistedAttributes >= 0 )
  {
    *((_QWORD *)a1 + 67) = *(_QWORD *)&v12[2];
LABEL_5:
    v6 = 1;
    return (unsigned int)PmSetDiskAttributes((__int64)a1, (__int64)v12, v6);
  }
  if ( PersistedAttributes == -1073741772 )
  {
    if ( DeviceExtension[440] )
    {
      MSFTIdentifier = StRtlFindMSFTIdentifier(*((_QWORD *)a1 + 31));
      if ( MSFTIdentifier )
      {
        if ( *(_QWORD *)(MSFTIdentifier + 8) == *(_QWORD *)&GUID_BOOT_DISK.Data1
          && *(_QWORD *)(MSFTIdentifier + 16) == *(_QWORD *)GUID_BOOT_DISK.Data4 )
        {
          *(_QWORD *)&v12[2] = 128;
          LOBYTE(v12[1]) = 1;
          goto LABEL_5;
        }
      }
    }
    v10 = (struct _KMUTANT *)(DeviceExtension + 16);
    v8 = 0;
    KeWaitForSingleObject(DeviceExtension + 16, Executive, 0, 0, 0);
    if ( *((_DWORD *)DeviceExtension + 40) == 5 )
    {
      *(_QWORD *)&v12[2] = 64;
    }
    else
    {
      if ( *((_DWORD *)DeviceExtension + 40) != 6 )
      {
        v6 = 0;
        *a2 = 1;
        goto LABEL_18;
      }
      *(_QWORD *)&v12[2] = 128;
    }
    LOBYTE(v12[1]) = 1;
    v6 = 1;
LABEL_18:
    KeReleaseMutex(v10, 0);
    if ( v6 )
      return (unsigned int)PmSetDiskAttributes((__int64)a1, (__int64)v12, v6);
  }
  return v8;
}

```

## disassembly

```asm
0x14002589c  mov     [rsp-28h+arg_10], rbx
0x1400258a1  push    rbp
0x1400258a2  push    rsi
0x1400258a3  push    rdi
0x1400258a4  push    r14
0x1400258a6  push    r15
0x1400258a8  mov     rbp, rsp
0x1400258ab  sub     rsp, 60h
0x1400258af  mov     rax, cs:__security_cookie
0x1400258b6  xor     rax, rsp
0x1400258b9  mov     [rbp+var_8], rax
0x1400258bd  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x1400258c4  xorps   xmm0, xmm0
0x1400258c7  mov     r15, rdx
0x1400258ca  mov     [rbp+var_2C], 0
0x1400258d2  mov     rsi, rcx
0x1400258d5  mov     [rbp+var_24], 0
0x1400258dc  movdqu  [rbp+var_18], xmm0
0x1400258e1  mov     rbx, [rax+40h]
0x1400258e5  mov     byte ptr [rdx], 0
0x1400258e8  cmp     dword ptr [rcx+0A8h], 0FFFFFFFFh
0x1400258ef  mov     [rbp+var_30], 28h ; '('
0x1400258f6  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x1400258fe  jnz     short loc_140025912
0x140025900  mov     [rbp+var_2C+4], 7
0x140025908  mov     ebx, 2
0x14002590d  jmp     loc_1400259ED
0x140025912  lea     rdx, [rbp+var_2C+4]; unsigned __int64 *
0x140025916  call    ?PmGetPersistedAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEA_K@Z; PmGetPersistedAttributes(_DEVICE_EXTENSION *,unsigned __int64 *)
0x14002591b  mov     edi, eax
0x14002591d  test    eax, eax
0x14002591f  js      short loc_140025936
0x140025921  mov     rax, [rbp+var_2C+4]
0x140025925  mov     [rsi+218h], rax
0x14002592c  mov     ebx, 1
0x140025931  jmp     loc_1400259ED
0x140025936  cmp     eax, 0C0000034h
0x14002593b  jnz     loc_1400259FE
0x140025941  cmp     byte ptr [rbx+1B8h], 0
0x140025948  jz      short loc_140025983
0x14002594a  mov     rcx, [rsi+0F8h]
0x140025951  call    StRtlFindMSFTIdentifier
0x140025956  test    rax, rax
0x140025959  jz      short loc_140025983
0x14002595b  mov     rcx, [rax+8]
0x14002595f  cmp     rcx, qword ptr cs:?GUID_BOOT_DISK@@3U_GUID@@B.Data1; _GUID const GUID_BOOT_DISK ...
0x140025966  jnz     short loc_140025983
0x140025968  mov     rax, [rax+10h]
0x14002596c  cmp     rax, qword ptr cs:?GUID_BOOT_DISK@@3U_GUID@@B.Data4; _GUID const GUID_BOOT_DISK ...
0x140025973  jnz     short loc_140025983
0x140025975  mov     [rbp+var_2C+4], 80h
0x14002597d  mov     byte ptr [rbp+var_2C], 1
0x140025981  jmp     short loc_14002592C
0x140025983  lea     r14, [rbx+10h]
0x140025987  xor     edi, edi
0x140025989  mov     rcx, r14; Object
0x14002598c  mov     [rsp+60h+Timeout], rdi; Timeout
0x140025991  xor     r9d, r9d; Alertable
0x140025994  xor     r8d, r8d; WaitMode
0x140025997  xor     edx, edx; WaitReason
0x140025999  call    cs:__imp_KeWaitForSingleObject
0x1400259a0  nop     dword ptr [rax+rax+00h]
0x1400259a5  mov     ecx, [rbx+0A0h]
0x1400259ab  sub     ecx, 5
0x1400259ae  jz      short loc_1400259C7
0x1400259b0  cmp     ecx, 1
0x1400259b3  jz      short loc_1400259BD
0x1400259b5  xor     ebx, ebx
0x1400259b7  mov     byte ptr [r15], 1
0x1400259bb  jmp     short loc_1400259D8
0x1400259bd  mov     [rbp+var_2C+4], 80h
0x1400259c5  jmp     short loc_1400259CF
0x1400259c7  mov     [rbp+var_2C+4], 40h ; '@'
0x1400259cf  mov     byte ptr [rbp+var_2C], 1
0x1400259d3  mov     ebx, 1
0x1400259d8  xor     edx, edx; Wait
0x1400259da  mov     rcx, r14; Mutex
0x1400259dd  call    cs:__imp_KeReleaseMutex
0x1400259e4  nop     dword ptr [rax+rax+00h]
0x1400259e9  test    ebx, ebx
0x1400259eb  jz      short loc_1400259FE
0x1400259ed  mov     r8d, ebx
0x1400259f0  lea     rdx, [rbp+var_30]
0x1400259f4  mov     rcx, rsi
0x1400259f7  call    ?PmSetDiskAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SET_DISK_ATTRIBUTES@@W4_DISK_OFFLINE_REASON@@@Z; PmSetDiskAttributes(_DEVICE_EXTENSION *,_SET_DISK_ATTRIBUTES *,_DISK_OFFLINE_REASON)
0x1400259fc  mov     edi, eax
0x1400259fe  mov     eax, edi
0x140025a00  mov     rcx, [rbp+var_8]
0x140025a04  xor     rcx, rsp; StackCookie
0x140025a07  call    __security_check_cookie
0x140025a0c  mov     rbx, [rsp+60h+arg_10]
0x140025a14  add     rsp, 60h
0x140025a18  pop     r15
0x140025a1a  pop     r14
0x140025a1c  pop     rdi
0x140025a1d  pop     rsi
0x140025a1e  pop     rbp
0x140025a1f  retn
```
