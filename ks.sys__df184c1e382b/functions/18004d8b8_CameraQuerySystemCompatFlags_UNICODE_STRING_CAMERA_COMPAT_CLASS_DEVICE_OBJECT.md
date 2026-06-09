# CameraQuerySystemCompatFlags(_UNICODE_STRING *,CAMERA_COMPAT_CLASS,_DEVICE_OBJECT *)

- ea: `0x18004d8b8`
- end: `0x18004dbb8`
- name: `?CameraQuerySystemCompatFlags@@YA?ATCAMERA_DEVICE_FLAGS@@PEAU_UNICODE_STRING@@W4CAMERA_COMPAT_CLASS@@PEAU_DEVICE_OBJECT@@@Z`
- size: `768`
- prototype: `__int64 __fastcall(UNICODE_STRING *, __int64, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004dccc`

## callees

- `0x18000e0f0`
- `0x180019bd0`
- `0x18001a000`
- `0x18004d8b8`
- `0x180064280`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18004d9da`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d9da`
- `ntoskrnl!ZwClose` at `0x18004db43`
- `ntoskrnl!ZwClose` at `0x18004db43`
- `ntoskrnl!ZwOpenKey` at `0x18004da16`
- `ntoskrnl!ZwOpenKey` at `0x18004da16`
- `ntoskrnl!ZwQueryKey` at `0x18004da41`
- `ntoskrnl!ZwQueryKey` at `0x18004da41`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18004dac7`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18004dac7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d953`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d9aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004da76`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d953`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d9aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004da76`
- `ntoskrnl!ExFreePool` at `0x18004db57`
- `ntoskrnl!ExFreePool` at `0x18004db6b`
- `ntoskrnl!ExFreePool` at `0x18004db7f`
- `ntoskrnl!ExFreePool` at `0x18004db57`
- `ntoskrnl!ExFreePool` at `0x18004db6b`
- `ntoskrnl!ExFreePool` at `0x18004db7f`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004db1a`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004db1a`

## string_xrefs

- `0x18004d9cf`: `\Registry\Machine\SYSTEM\HardwareConfig\Current\ComputerIds`

## pseudocode

```c
__int64 __fastcall CameraQuerySystemCompatFlags(UNICODE_STRING *a1, __int64 a2, struct _DEVICE_OBJECT *a3)
{
  unsigned __int16 *v5; // rdi
  _DWORD *v6; // rbx
  unsigned __int16 *PoolWithTag; // rax
  unsigned __int16 *v8; // rsi
  unsigned __int64 v9; // r12
  SIZE_T v10; // r14
  unsigned __int16 *v11; // rax
  int v12; // r15d
  unsigned int v13; // r14d
  _DWORD *v14; // rax
  ULONG v15; // r14d
  ULONG v16; // r15d
  ULONG ResultLength; // [rsp+30h] [rbp-69h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-61h] BYREF
  __int64 v20; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-51h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-39h] BYREF
  _OWORD KeyInformation[2]; // [rsp+90h] [rbp-9h] BYREF
  __int128 v25; // [rsp+B0h] [rbp+17h]

  KeyHandle = 0;
  ResultLength = 0;
  v21 = 0;
  v20 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(KeyInformation, 0, sizeof(KeyInformation));
  v25 = 0;
  if ( a1 && a3 )
  {
    v5 = 0;
    v6 = 0;
    PoolWithTag = (unsigned __int16 *)ExAllocatePoolWithTag(PagedPool, 0xD2u, 0x434D4143u);
    v8 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 0xD2u);
      if ( (int)CreateFingerprintStringPrefix(a1, a3, v8, &v21) >= 0 )
      {
        v9 = v21 + 48;
        v10 = 2 * (v21 + 48);
        v11 = (unsigned __int16 *)ExAllocatePoolWithTag(PagedPool, v10, 0x434D4143u);
        v5 = v11;
        if ( v11 )
        {
          memset(v11, 0, v10);
          RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\SYSTEM\\HardwareConfig\\Current\\ComputerIds");
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 576;
          ObjectAttributes.Length = 48;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0
            && ZwQueryKey(KeyHandle, KeyFullInformation, KeyInformation, 0x30u, &ResultLength) >= 0
            && (unsigned int)v25 > 1 )
          {
            v12 = DWORD1(v25) + 18;
            v13 = DWORD1(v25) + 18;
            v14 = ExAllocatePoolWithTag(PagedPool, (unsigned int)(DWORD1(v25) + 18), 0x434D4143u);
            v6 = v14;
            if ( v14 )
            {
              memset(v14, 0, v13);
              v15 = 0;
              if ( (_DWORD)v25 )
              {
                v16 = v12 - 2;
                do
                {
                  if ( ZwEnumerateValueKey(KeyHandle, v15, KeyValueBasicInformation, v6, v16, &ResultLength) >= 0 )
                  {
                    if ( v6[1] != 7 )
                      goto LABEL_18;
                    *((_WORD *)v6 + ((unsigned __int64)(unsigned int)v6[2] >> 1) + 6) = 0;
                  }
                  if ( (int)RtlStringCchPrintfW(v5, v9, L"System:%ws%ws;", v8, v6 + 3) >= 0 )
                    KseQueryDeviceFlags(v5, L"CamAcpiRotation", &v20);
                  if ( v20 )
                    break;
LABEL_18:
                  ++v15;
                }
                while ( v15 < (unsigned int)v25 );
              }
            }
          }
        }
      }
    }
    if ( KeyHandle )
      ZwClose(KeyHandle);
    if ( v6 )
      ExFreePool(v6);
    if ( v5 )
      ExFreePool(v5);
    if ( v8 )
      ExFreePool(v8);
  }
  return v20;
}

```

## disassembly

```asm
0x18004d8b8  mov     [rsp-8+arg_8], rbx
0x18004d8bd  mov     [rsp-8+arg_18], rsi
0x18004d8c2  push    rbp
0x18004d8c3  push    rdi
0x18004d8c4  push    r12
0x18004d8c6  push    r14
0x18004d8c8  push    r15
0x18004d8ca  lea     rbp, [rsp-37h]
0x18004d8cf  sub     rsp, 0D0h
0x18004d8d6  mov     rax, cs:__security_cookie
0x18004d8dd  xor     rax, rsp
0x18004d8e0  mov     [rbp+57h+var_30], rax
0x18004d8e4  mov     [rbp+57h+KeyHandle], 0
0x18004d8ec  xorps   xmm0, xmm0
0x18004d8ef  mov     [rbp+57h+var_C0], 0
0x18004d8f6  xorps   xmm1, xmm1
0x18004d8f9  mov     [rbp+57h+var_A8], 0
0x18004d901  mov     r14, r8
0x18004d904  mov     [rbp+57h+var_B0], 0
0x18004d90c  mov     r15, rcx
0x18004d90f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18004d913  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18004d917  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18004d91b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18004d91f  movups  [rbp+57h+KeyInformation], xmm0
0x18004d923  movups  [rbp+57h+var_50], xmm0
0x18004d927  movups  [rbp+57h+var_40], xmm0
0x18004d92b  test    rcx, rcx
0x18004d92e  jz      loc_18004DB8B
0x18004d934  test    r8, r8
0x18004d937  jz      loc_18004DB8B
0x18004d93d  xor     edi, edi
0x18004d93f  mov     r12d, 0D2h
0x18004d945  mov     r8d, 434D4143h; Tag
0x18004d94b  mov     edx, r12d; NumberOfBytes
0x18004d94e  xor     ebx, ebx
0x18004d950  lea     ecx, [rdi+1]; PoolType
0x18004d953  call    cs:__imp_ExAllocatePoolWithTag
0x18004d95a  nop     dword ptr [rax+rax+00h]
0x18004d95f  mov     rsi, rax
0x18004d962  test    rax, rax
0x18004d965  jz      loc_18004DB3A
0x18004d96b  mov     r8d, r12d; Size
0x18004d96e  xor     edx, edx; Val
0x18004d970  mov     rcx, rax; void *
0x18004d973  call    memset
0x18004d978  lea     r9, [rbp+57h+var_A8]; unsigned __int64 *
0x18004d97c  mov     r8, rsi; unsigned __int16 *
0x18004d97f  mov     rdx, r14; Pdo
0x18004d982  mov     rcx, r15; SymbolicLinkName
0x18004d985  call    ?CreateFingerprintStringPrefix@@YAJPEAU_UNICODE_STRING@@PEAU_DEVICE_OBJECT@@PEAGPEA_K@Z; CreateFingerprintStringPrefix(_UNICODE_STRING *,_DEVICE_OBJECT *,ushort *,unsigned __int64 *)
0x18004d98a  test    eax, eax
0x18004d98c  js      loc_18004DB3A
0x18004d992  mov     r12, [rbp+57h+var_A8]
0x18004d996  lea     ecx, [rdi+1]; PoolType
0x18004d999  add     r12, 30h ; '0'
0x18004d99d  mov     r8d, 434D4143h; Tag
0x18004d9a3  lea     r14, [r12+r12]
0x18004d9a7  mov     rdx, r14; NumberOfBytes
0x18004d9aa  call    cs:__imp_ExAllocatePoolWithTag
0x18004d9b1  nop     dword ptr [rax+rax+00h]
0x18004d9b6  mov     rdi, rax
0x18004d9b9  test    rax, rax
0x18004d9bc  jz      loc_18004DB3A
0x18004d9c2  mov     r8, r14; Size
0x18004d9c5  xor     edx, edx; Val
0x18004d9c7  mov     rcx, rax; void *
0x18004d9ca  call    memset
0x18004d9cf  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\SYSTEM\\HardwareCo"...
0x18004d9d6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004d9da  call    cs:__imp_RtlInitUnicodeString
0x18004d9e1  nop     dword ptr [rax+rax+00h]
0x18004d9e6  lea     rax, [rbp+57h+DestinationString]
0x18004d9ea  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18004d9ee  xorps   xmm0, xmm0
0x18004d9f1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18004d9f5  lea     r14d, [rbx+30h]
0x18004d9f9  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18004da00  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004da04  mov     [rbp+57h+ObjectAttributes.Length], r14d
0x18004da08  mov     edx, 20019h; DesiredAccess
0x18004da0d  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004da11  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004da16  call    cs:__imp_ZwOpenKey
0x18004da1d  nop     dword ptr [rax+rax+00h]
0x18004da22  test    eax, eax
0x18004da24  js      loc_18004DB3A
0x18004da2a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004da2e  lea     rax, [rbp+57h+var_C0]
0x18004da32  mov     r9d, r14d; Length
0x18004da35  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x18004da3a  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x18004da3e  lea     edx, [rbx+2]; KeyInformationClass
0x18004da41  call    cs:__imp_ZwQueryKey
0x18004da48  nop     dword ptr [rax+rax+00h]
0x18004da4d  test    eax, eax
0x18004da4f  js      loc_18004DB3A
0x18004da55  cmp     dword ptr [rbp+57h+var_40], 1
0x18004da59  jbe     loc_18004DB3A
0x18004da5f  mov     r15d, dword ptr [rbp+57h+var_40+4]
0x18004da63  lea     ecx, [rbx+1]; PoolType
0x18004da66  add     r15d, 12h
0x18004da6a  mov     r8d, 434D4143h; Tag
0x18004da70  mov     edx, r15d; NumberOfBytes
0x18004da73  mov     r14d, r15d
0x18004da76  call    cs:__imp_ExAllocatePoolWithTag
0x18004da7d  nop     dword ptr [rax+rax+00h]
0x18004da82  mov     rbx, rax
0x18004da85  test    rax, rax
0x18004da88  jz      loc_18004DB3A
0x18004da8e  mov     r8d, r14d; Size
0x18004da91  xor     edx, edx; Val
0x18004da93  mov     rcx, rax; void *
0x18004da96  call    memset
0x18004da9b  xor     r14d, r14d
0x18004da9e  cmp     dword ptr [rbp+57h+var_40], r14d
0x18004daa2  jbe     loc_18004DB3A
0x18004daa8  add     r15d, 0FFFFFFFEh
0x18004daac  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004dab0  lea     rax, [rbp+57h+var_C0]
0x18004dab4  mov     [rsp+0F0h+var_C8], rax; ResultLength
0x18004dab9  mov     r9, rbx; KeyValueInformation
0x18004dabc  xor     r8d, r8d; KeyValueInformationClass
0x18004dabf  mov     dword ptr [rsp+0F0h+ResultLength], r15d; Length
0x18004dac4  mov     edx, r14d; Index
0x18004dac7  call    cs:__imp_ZwEnumerateValueKey
0x18004dace  nop     dword ptr [rax+rax+00h]
0x18004dad3  test    eax, eax
0x18004dad5  js      short loc_18004DAEA
0x18004dad7  cmp     dword ptr [rbx+4], 7
0x18004dadb  jnz     short loc_18004DB2D
0x18004dadd  mov     ecx, [rbx+8]
0x18004dae0  shr     rcx, 1
0x18004dae3  xor     eax, eax
0x18004dae5  mov     [rbx+rcx*2+0Ch], ax
0x18004daea  lea     rax, [rbx+0Ch]
0x18004daee  mov     r9, rsi
0x18004daf1  lea     r8, aSystemWsWs; "System:%ws%ws;"
0x18004daf8  mov     [rsp+0F0h+ResultLength], rax
0x18004dafd  mov     rdx, r12; unsigned __int64
0x18004db00  mov     rcx, rdi; unsigned __int16 *
0x18004db03  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004db08  test    eax, eax
0x18004db0a  js      short loc_18004DB26
0x18004db0c  lea     r8, [rbp+57h+var_B0]
0x18004db10  mov     rcx, rdi
0x18004db13  lea     rdx, aCamacpirotatio; "CamAcpiRotation"
0x18004db1a  call    cs:__imp_KseQueryDeviceFlags
0x18004db21  nop     dword ptr [rax+rax+00h]
0x18004db26  cmp     [rbp+57h+var_B0], 0
0x18004db2b  jnz     short loc_18004DB3A
0x18004db2d  inc     r14d
0x18004db30  cmp     r14d, dword ptr [rbp+57h+var_40]
0x18004db34  jb      loc_18004DAAC
0x18004db3a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18004db3e  test    rcx, rcx
0x18004db41  jz      short loc_18004DB4F
0x18004db43  call    cs:__imp_ZwClose
0x18004db4a  nop     dword ptr [rax+rax+00h]
0x18004db4f  test    rbx, rbx
0x18004db52  jz      short loc_18004DB63
0x18004db54  mov     rcx, rbx; P
0x18004db57  call    cs:__imp_ExFreePool
0x18004db5e  nop     dword ptr [rax+rax+00h]
0x18004db63  test    rdi, rdi
0x18004db66  jz      short loc_18004DB77
0x18004db68  mov     rcx, rdi; P
0x18004db6b  call    cs:__imp_ExFreePool
0x18004db72  nop     dword ptr [rax+rax+00h]
0x18004db77  test    rsi, rsi
0x18004db7a  jz      short loc_18004DB8B
0x18004db7c  mov     rcx, rsi; P
0x18004db7f  call    cs:__imp_ExFreePool
0x18004db86  nop     dword ptr [rax+rax+00h]
0x18004db8b  mov     rax, [rbp+57h+var_B0]
0x18004db8f  mov     rcx, [rbp+57h+var_30]
0x18004db93  xor     rcx, rsp; StackCookie
0x18004db96  call    __security_check_cookie
0x18004db9b  lea     r11, [rsp+0F0h+var_20]
0x18004dba3  mov     rbx, [r11+38h]
0x18004dba7  mov     rsi, [r11+48h]
0x18004dbab  mov     rsp, r11
0x18004dbae  pop     r15
0x18004dbb0  pop     r14
0x18004dbb2  pop     r12
0x18004dbb4  pop     rdi
0x18004dbb5  pop     rbp
0x18004dbb6  retn
```
