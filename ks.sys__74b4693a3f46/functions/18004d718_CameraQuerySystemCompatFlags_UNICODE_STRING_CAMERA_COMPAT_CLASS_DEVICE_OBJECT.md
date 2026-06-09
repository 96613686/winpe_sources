# CameraQuerySystemCompatFlags(_UNICODE_STRING *,CAMERA_COMPAT_CLASS,_DEVICE_OBJECT *)

- ea: `0x18004d718`
- end: `0x18004da18`
- name: `?CameraQuerySystemCompatFlags@@YA?ATCAMERA_DEVICE_FLAGS@@PEAU_UNICODE_STRING@@W4CAMERA_COMPAT_CLASS@@PEAU_DEVICE_OBJECT@@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004db2c`

## callees

- `0x18000e0f0`
- `0x180019b80`
- `0x180019fc0`
- `0x18004d718`
- `0x1800640e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18004d83a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004d83a`
- `ntoskrnl!ZwClose` at `0x18004d9a3`
- `ntoskrnl!ZwClose` at `0x18004d9a3`
- `ntoskrnl!ZwOpenKey` at `0x18004d876`
- `ntoskrnl!ZwOpenKey` at `0x18004d876`
- `ntoskrnl!ZwQueryKey` at `0x18004d8a1`
- `ntoskrnl!ZwQueryKey` at `0x18004d8a1`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18004d927`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18004d927`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d7b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d80a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d8d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d7b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d80a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004d8d6`
- `ntoskrnl!ExFreePool` at `0x18004d9b7`
- `ntoskrnl!ExFreePool` at `0x18004d9cb`
- `ntoskrnl!ExFreePool` at `0x18004d9df`
- `ntoskrnl!ExFreePool` at `0x18004d9b7`
- `ntoskrnl!ExFreePool` at `0x18004d9cb`
- `ntoskrnl!ExFreePool` at `0x18004d9df`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004d97a`
- `ntoskrnl!KseQueryDeviceFlags` at `0x18004d97a`

## string_xrefs

- `0x18004d82f`: `\Registry\Machine\SYSTEM\HardwareConfig\Current\ComputerIds`

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
0x18004d718  mov     [rsp-8+arg_8], rbx
0x18004d71d  mov     [rsp-8+arg_18], rsi
0x18004d722  push    rbp
0x18004d723  push    rdi
0x18004d724  push    r12
0x18004d726  push    r14
0x18004d728  push    r15
0x18004d72a  lea     rbp, [rsp-37h]
0x18004d72f  sub     rsp, 0D0h
0x18004d736  mov     rax, cs:__security_cookie
0x18004d73d  xor     rax, rsp
0x18004d740  mov     [rbp+57h+var_30], rax
0x18004d744  mov     [rbp+57h+KeyHandle], 0
0x18004d74c  xorps   xmm0, xmm0
0x18004d74f  mov     [rbp+57h+var_C0], 0
0x18004d756  xorps   xmm1, xmm1
0x18004d759  mov     [rbp+57h+var_A8], 0
0x18004d761  mov     r14, r8
0x18004d764  mov     [rbp+57h+var_B0], 0
0x18004d76c  mov     r15, rcx
0x18004d76f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18004d773  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18004d777  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18004d77b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18004d77f  movups  [rbp+57h+KeyInformation], xmm0
0x18004d783  movups  [rbp+57h+var_50], xmm0
0x18004d787  movups  [rbp+57h+var_40], xmm0
0x18004d78b  test    rcx, rcx
0x18004d78e  jz      loc_18004D9EB
0x18004d794  test    r8, r8
0x18004d797  jz      loc_18004D9EB
0x18004d79d  xor     edi, edi
0x18004d79f  mov     r12d, 0D2h
0x18004d7a5  mov     r8d, 434D4143h; Tag
0x18004d7ab  mov     edx, r12d; NumberOfBytes
0x18004d7ae  xor     ebx, ebx
0x18004d7b0  lea     ecx, [rdi+1]; PoolType
0x18004d7b3  call    cs:__imp_ExAllocatePoolWithTag
0x18004d7ba  nop     dword ptr [rax+rax+00h]
0x18004d7bf  mov     rsi, rax
0x18004d7c2  test    rax, rax
0x18004d7c5  jz      loc_18004D99A
0x18004d7cb  mov     r8d, r12d; Size
0x18004d7ce  xor     edx, edx; Val
0x18004d7d0  mov     rcx, rax; void *
0x18004d7d3  call    memset
0x18004d7d8  lea     r9, [rbp+57h+var_A8]; unsigned __int64 *
0x18004d7dc  mov     r8, rsi; unsigned __int16 *
0x18004d7df  mov     rdx, r14; Pdo
0x18004d7e2  mov     rcx, r15; SymbolicLinkName
0x18004d7e5  call    ?CreateFingerprintStringPrefix@@YAJPEAU_UNICODE_STRING@@PEAU_DEVICE_OBJECT@@PEAGPEA_K@Z; CreateFingerprintStringPrefix(_UNICODE_STRING *,_DEVICE_OBJECT *,ushort *,unsigned __int64 *)
0x18004d7ea  test    eax, eax
0x18004d7ec  js      loc_18004D99A
0x18004d7f2  mov     r12, [rbp+57h+var_A8]
0x18004d7f6  lea     ecx, [rdi+1]; PoolType
0x18004d7f9  add     r12, 30h ; '0'
0x18004d7fd  mov     r8d, 434D4143h; Tag
0x18004d803  lea     r14, [r12+r12]
0x18004d807  mov     rdx, r14; NumberOfBytes
0x18004d80a  call    cs:__imp_ExAllocatePoolWithTag
0x18004d811  nop     dword ptr [rax+rax+00h]
0x18004d816  mov     rdi, rax
0x18004d819  test    rax, rax
0x18004d81c  jz      loc_18004D99A
0x18004d822  mov     r8, r14; Size
0x18004d825  xor     edx, edx; Val
0x18004d827  mov     rcx, rax; void *
0x18004d82a  call    memset
0x18004d82f  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\SYSTEM\\HardwareCo"...
0x18004d836  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004d83a  call    cs:__imp_RtlInitUnicodeString
0x18004d841  nop     dword ptr [rax+rax+00h]
0x18004d846  lea     rax, [rbp+57h+DestinationString]
0x18004d84a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18004d84e  xorps   xmm0, xmm0
0x18004d851  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18004d855  lea     r14d, [rbx+30h]
0x18004d859  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18004d860  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004d864  mov     [rbp+57h+ObjectAttributes.Length], r14d
0x18004d868  mov     edx, 20019h; DesiredAccess
0x18004d86d  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004d871  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004d876  call    cs:__imp_ZwOpenKey
0x18004d87d  nop     dword ptr [rax+rax+00h]
0x18004d882  test    eax, eax
0x18004d884  js      loc_18004D99A
0x18004d88a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004d88e  lea     rax, [rbp+57h+var_C0]
0x18004d892  mov     r9d, r14d; Length
0x18004d895  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x18004d89a  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x18004d89e  lea     edx, [rbx+2]; KeyInformationClass
0x18004d8a1  call    cs:__imp_ZwQueryKey
0x18004d8a8  nop     dword ptr [rax+rax+00h]
0x18004d8ad  test    eax, eax
0x18004d8af  js      loc_18004D99A
0x18004d8b5  cmp     dword ptr [rbp+57h+var_40], 1
0x18004d8b9  jbe     loc_18004D99A
0x18004d8bf  mov     r15d, dword ptr [rbp+57h+var_40+4]
0x18004d8c3  lea     ecx, [rbx+1]; PoolType
0x18004d8c6  add     r15d, 12h
0x18004d8ca  mov     r8d, 434D4143h; Tag
0x18004d8d0  mov     edx, r15d; NumberOfBytes
0x18004d8d3  mov     r14d, r15d
0x18004d8d6  call    cs:__imp_ExAllocatePoolWithTag
0x18004d8dd  nop     dword ptr [rax+rax+00h]
0x18004d8e2  mov     rbx, rax
0x18004d8e5  test    rax, rax
0x18004d8e8  jz      loc_18004D99A
0x18004d8ee  mov     r8d, r14d; Size
0x18004d8f1  xor     edx, edx; Val
0x18004d8f3  mov     rcx, rax; void *
0x18004d8f6  call    memset
0x18004d8fb  xor     r14d, r14d
0x18004d8fe  cmp     dword ptr [rbp+57h+var_40], r14d
0x18004d902  jbe     loc_18004D99A
0x18004d908  add     r15d, 0FFFFFFFEh
0x18004d90c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004d910  lea     rax, [rbp+57h+var_C0]
0x18004d914  mov     [rsp+0F0h+var_C8], rax; ResultLength
0x18004d919  mov     r9, rbx; KeyValueInformation
0x18004d91c  xor     r8d, r8d; KeyValueInformationClass
0x18004d91f  mov     dword ptr [rsp+0F0h+ResultLength], r15d; Length
0x18004d924  mov     edx, r14d; Index
0x18004d927  call    cs:__imp_ZwEnumerateValueKey
0x18004d92e  nop     dword ptr [rax+rax+00h]
0x18004d933  test    eax, eax
0x18004d935  js      short loc_18004D94A
0x18004d937  cmp     dword ptr [rbx+4], 7
0x18004d93b  jnz     short loc_18004D98D
0x18004d93d  mov     ecx, [rbx+8]
0x18004d940  shr     rcx, 1
0x18004d943  xor     eax, eax
0x18004d945  mov     [rbx+rcx*2+0Ch], ax
0x18004d94a  lea     rax, [rbx+0Ch]
0x18004d94e  mov     r9, rsi
0x18004d951  lea     r8, aSystemWsWs; "System:%ws%ws;"
0x18004d958  mov     [rsp+0F0h+ResultLength], rax
0x18004d95d  mov     rdx, r12; unsigned __int64
0x18004d960  mov     rcx, rdi; unsigned __int16 *
0x18004d963  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d968  test    eax, eax
0x18004d96a  js      short loc_18004D986
0x18004d96c  lea     r8, [rbp+57h+var_B0]
0x18004d970  mov     rcx, rdi
0x18004d973  lea     rdx, aCamacpirotatio; "CamAcpiRotation"
0x18004d97a  call    cs:__imp_KseQueryDeviceFlags
0x18004d981  nop     dword ptr [rax+rax+00h]
0x18004d986  cmp     [rbp+57h+var_B0], 0
0x18004d98b  jnz     short loc_18004D99A
0x18004d98d  inc     r14d
0x18004d990  cmp     r14d, dword ptr [rbp+57h+var_40]
0x18004d994  jb      loc_18004D90C
0x18004d99a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18004d99e  test    rcx, rcx
0x18004d9a1  jz      short loc_18004D9AF
0x18004d9a3  call    cs:__imp_ZwClose
0x18004d9aa  nop     dword ptr [rax+rax+00h]
0x18004d9af  test    rbx, rbx
0x18004d9b2  jz      short loc_18004D9C3
0x18004d9b4  mov     rcx, rbx; P
0x18004d9b7  call    cs:__imp_ExFreePool
0x18004d9be  nop     dword ptr [rax+rax+00h]
0x18004d9c3  test    rdi, rdi
0x18004d9c6  jz      short loc_18004D9D7
0x18004d9c8  mov     rcx, rdi; P
0x18004d9cb  call    cs:__imp_ExFreePool
0x18004d9d2  nop     dword ptr [rax+rax+00h]
0x18004d9d7  test    rsi, rsi
0x18004d9da  jz      short loc_18004D9EB
0x18004d9dc  mov     rcx, rsi; P
0x18004d9df  call    cs:__imp_ExFreePool
0x18004d9e6  nop     dword ptr [rax+rax+00h]
0x18004d9eb  mov     rax, [rbp+57h+var_B0]
0x18004d9ef  mov     rcx, [rbp+57h+var_30]
0x18004d9f3  xor     rcx, rsp; StackCookie
0x18004d9f6  call    __security_check_cookie
0x18004d9fb  lea     r11, [rsp+0F0h+var_20]
0x18004da03  mov     rbx, [r11+38h]
0x18004da07  mov     rsi, [r11+48h]
0x18004da0b  mov     rsp, r11
0x18004da0e  pop     r15
0x18004da10  pop     r14
0x18004da12  pop     r12
0x18004da14  pop     rdi
0x18004da15  pop     rbp
0x18004da16  retn
```
