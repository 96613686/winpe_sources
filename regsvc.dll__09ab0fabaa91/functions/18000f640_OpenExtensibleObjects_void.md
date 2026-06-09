# OpenExtensibleObjects(void)

- ea: `0x18000f640`
- end: `0x18000fb64`
- name: `?OpenExtensibleObjects@@YAXXZ`
- size: `1316`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008c30`

## callees

- `0x180005da0`
- `0x180008050`
- `0x18000abc4`
- `0x18000b350`
- `0x18000bef8`
- `0x18000c134`
- `0x18000e1a8`
- `0x18000f640`
- `0x18000ffe8`
- `0x1800100e0`
- `0x180010188`
- `0x18001e43d`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x18000f93a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000f93a`
- `ntdll!NtEnumerateKey` at `0x18000f8d9`
- `ntdll!NtEnumerateKey` at `0x18000f8d9`
- `ntdll!NtOpenKey` at `0x18000f84e`
- `ntdll!NtOpenKey` at `0x18000f985`
- `ntdll!NtOpenKey` at `0x18000f9a0`
- `ntdll!NtOpenKey` at `0x18000f84e`
- `ntdll!NtOpenKey` at `0x18000f985`
- `ntdll!NtOpenKey` at `0x18000f9a0`
- `ntdll!RtlInitUnicodeString` at `0x18000f6af`
- `ntdll!RtlInitUnicodeString` at `0x18000f6c4`
- `ntdll!RtlInitUnicodeString` at `0x18000f6af`
- `ntdll!RtlInitUnicodeString` at `0x18000f6c4`
- `ntdll!NtClose` at `0x18000f7b8`
- `ntdll!NtClose` at `0x18000fa46`
- `ntdll!NtClose` at `0x18000fa86`
- `ntdll!NtClose` at `0x18000fb24`
- `ntdll!NtClose` at `0x18001e5bd`
- `ntdll!NtClose` at `0x18000f7b8`
- `ntdll!NtClose` at `0x18000fa46`
- `ntdll!NtClose` at `0x18000fa86`
- `ntdll!NtClose` at `0x18000fb24`
- `ntdll!NtClose` at `0x18001e5bd`

## string_xrefs

- `0x18000f767`: `OpenProcedureWaitTime`
- `0x18000f6a4`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Services`

## pseudocode

```c
void OpenExtensibleObjects(void)
{
  _QWORD *v0; // rdi
  unsigned int v1; // edx
  unsigned int v2; // r8d
  unsigned int v3; // edx
  unsigned int v4; // r8d
  unsigned int v5; // edx
  unsigned int v6; // r8d
  unsigned int v7; // edx
  unsigned int v8; // r8d
  NTSTATUS v9; // ebx
  USHORT *v10; // rsi
  __int64 v11; // rax
  void *v12; // r15
  ULONG v13; // r14d
  NTSTATUS v14; // eax
  unsigned int v15; // ecx
  unsigned __int64 v16; // r12
  int v17; // edx
  NTSTATUS v18; // ebx
  int v19; // r8d
  struct EXT_OBJECT *v20; // rax
  unsigned int v21; // eax
  int v22; // edx
  int v23; // ecx
  ULONG Length; // [rsp+20h] [rbp-E8h]
  ULONG Lengtha; // [rsp+20h] [rbp-E8h]
  ULONG Lengthb; // [rsp+20h] [rbp-E8h]
  ULONG Lengthc; // [rsp+20h] [rbp-E8h]
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE v29; // [rsp+50h] [rbp-B8h] BYREF
  ULONG v30; // [rsp+58h] [rbp-B0h]
  USHORT *v31; // [rsp+60h] [rbp-A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-A0h] BYREF
  struct EXT_OBJECT *v33; // [rsp+98h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-68h] BYREF
  __int16 v35; // [rsp+B2h] [rbp-56h]
  __int64 v36; // [rsp+B8h] [rbp-50h]
  struct _UNICODE_STRING v37[4]; // [rsp+C0h] [rbp-48h] BYREF
  int v38; // [rsp+110h] [rbp+8h] BYREF
  ULONG ResultLength; // [rsp+118h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+120h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+128h] [rbp+20h] BYREF

  ResultLength = 0;
  v29 = 0;
  *(_QWORD *)&Destination.Length = 0;
  v37[0] = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Handle = 0;
  v0 = 0;
  Destination.Buffer = 0;
  v31 = 0;
  v36 = 0;
  KeyHandle = 0;
  RtlInitUnicodeString(v37, L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Services");
  RtlInitUnicodeString(&DestinationString, L"\\Performance");
  v38 = 1;
  GetPerflibKeyValue(L"EventLogLevel", v1, v2, &lEventLogLevel, Length, &v38, (HKEY *)&Handle);
  v38 = 1;
  GetPerflibKeyValue(L"ExtCounterTestLevel", v3, v4, &lExtCounterTestLevel, Lengtha, &v38, (HKEY *)&Handle);
  v38 = 10000;
  GetPerflibKeyValue(L"OpenProcedureWaitTime", v5, v6, &dwExtCtrOpenProcWaitMs, Lengthb, &v38, (HKEY *)&Handle);
  v38 = 120000;
  GetPerflibKeyValue(L"Library Unload Time", v7, v8, &dwThreadAndLibraryTimeout, Lengthc, &v38, (HKEY *)&Handle);
  if ( Handle )
    NtClose(Handle);
  McGenEventRegister_EtwEventRegister();
  Destination.Length = 0;
  Destination.MaximumLength = DestinationString.MaximumLength + 514;
  Destination.Buffer = (PWSTR)operator new(
                                saturated_mul(
                                  (unsigned __int64)(unsigned __int16)(DestinationString.MaximumLength + 514) >> 1,
                                  2u));
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = v37;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v10 = (USHORT *)operator new(536);
  v31 = v10;
  v35 = 512;
  v11 = operator new(512);
  v12 = (void *)v11;
  v36 = v11;
  if ( v9 >= 0 && Destination.Buffer && v10 && v11 )
  {
    v13 = 0;
    v30 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          do
          {
            v14 = NtEnumerateKey(KeyHandle, v13++, KeyBasicInformation, v10, 0x218u, &ResultLength);
            v30 = v13;
            if ( v14 < 0 )
              goto LABEL_35;
            v15 = v10[6];
          }
          while ( Destination.MaximumLength < (unsigned __int16)(v15 + 2) );
          Destination.Length = v10[6];
          memmove_0(Destination.Buffer, v10 + 8, v15);
          v16 = (unsigned __int64)Destination.Length >> 1;
          Destination.Buffer[v16] = 0;
          RtlAppendUnicodeStringToString(&Destination, &DestinationString);
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = &Destination;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v18 = NtOpenKey(&v29, 0x2001Fu, &ObjectAttributes);
          if ( v18 < 0 )
            v18 = NtOpenKey(&v29, 0x20019u, &ObjectAttributes);
          if ( v18 >= 0 )
            break;
          if ( v18 != -1073741772 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_Zd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v19, (unsigned int)&Destination, v18);
            if ( PerfpThrottleError(0x7D1u, 0, &PerfpErrorLog)
              && lEventLogLevel >= 2
              && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
            {
              v21 = PerfpDosError(v18);
              McTemplateU0zqq_EtwEventWriteTransfer(v23, v22, Destination.Buffer, v21, v18);
            }
          }
        }
        Destination.Buffer[v16] = 0;
        v20 = AllocateAndInitializeExtObject((HKEY)KeyHandle, (HKEY)v29, &Destination);
        if ( v20 )
          break;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Z(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
            &Destination);
LABEL_26:
        NtClose(v29);
      }
      if ( !*((_BYTE *)v20 + 524) )
        goto LABEL_26;
      if ( ExtensibleObjects )
      {
        if ( v0 )
        {
          *v0 = v20;
          v0 = v20;
          v33 = v20;
        }
        else
        {
          *(_QWORD *)v20 = ExtensibleObjects;
          ExtensibleObjects = v20;
        }
        ++NumExtensibleObjects;
      }
      else
      {
        v0 = v20;
        ExtensibleObjects = v20;
        v33 = v20;
        NumExtensibleObjects = 1;
      }
    }
  }
LABEL_35:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Destination.Buffer )
    operator delete(Destination.Buffer);
  if ( v10 )
    operator delete(v10);
  if ( v12 )
    operator delete(v12);
}

```

## disassembly

```asm
0x18000f640  mov     rax, rsp
0x18000f643  push    rbx
0x18000f644  push    rsi
0x18000f645  push    rdi
0x18000f646  push    r12
0x18000f648  push    r14
0x18000f64a  push    r15
0x18000f64c  sub     rsp, 0D8h
0x18000f653  mov     dword ptr [rax+10h], 0
0x18000f65a  mov     [rsp+108h+var_B8], 0
0x18000f663  mov     qword ptr [rsp+108h+Destination.Length], 0
0x18000f66c  xorps   xmm0, xmm0
0x18000f66f  movups  xmmword ptr [rax-48h], xmm0
0x18000f673  xorps   xmm1, xmm1
0x18000f676  movups  xmmword ptr [rax-68h], xmm1
0x18000f67a  movups  xmmword ptr [rsp+108h+ObjectAttributes.Length], xmm0
0x18000f67f  movups  xmmword ptr [rsp+108h+ObjectAttributes.ObjectName], xmm0
0x18000f684  movups  xmmword ptr [rax-80h], xmm0
0x18000f688  mov     qword ptr [rax+20h], 0
0x18000f690  xor     edi, edi
0x18000f692  mov     [rsp+108h+Destination.Buffer], rdi
0x18000f697  mov     [rsp+108h+var_A8], rdi
0x18000f69c  mov     [rax-50h], rdi
0x18000f6a0  mov     [rax+18h], rdi
0x18000f6a4  lea     rdx, ?ExtPath@@3QBGB; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18000f6ab  lea     rcx, [rax-48h]; DestinationString
0x18000f6af  call    cs:__imp_RtlInitUnicodeString
0x18000f6b5  lea     rdx, ?PerfSubKey@@3QBGB; "\\Performance"
0x18000f6bc  lea     rcx, [rsp+108h+DestinationString]; DestinationString
0x18000f6c4  call    cs:__imp_RtlInitUnicodeString
0x18000f6ca  nop
0x18000f6cb  mov     [rsp+108h+arg_0], 1
0x18000f6d6  lea     rax, [rsp+108h+Handle]
0x18000f6de  mov     [rsp+108h+var_D8], rax; HKEY *
0x18000f6e3  lea     rax, [rsp+108h+arg_0]
0x18000f6eb  mov     [rsp+108h+ResultLength], rax; void *
0x18000f6f0  lea     r9, ?lEventLogLevel@@3JA; void *
0x18000f6f7  lea     rcx, ?EventLogLevel@@3QBGB; "EventLogLevel"
0x18000f6fe  call    ?GetPerflibKeyValue@@YAJPEBGKKPEAXK1PEAPEAUHKEY__@@@Z; GetPerflibKeyValue(ushort const *,ulong,ulong,void *,ulong,void *,HKEY__ * *)
0x18000f703  mov     [rsp+108h+arg_0], 1
0x18000f70e  lea     rax, [rsp+108h+Handle]
0x18000f716  mov     [rsp+108h+var_D8], rax; HKEY *
0x18000f71b  lea     rax, [rsp+108h+arg_0]
0x18000f723  mov     [rsp+108h+ResultLength], rax; void *
0x18000f728  lea     r9, ?lExtCounterTestLevel@@3JA; void *
0x18000f72f  lea     rcx, ?ExtCounterTestLevel@@3QBGB; "ExtCounterTestLevel"
0x18000f736  call    ?GetPerflibKeyValue@@YAJPEBGKKPEAXK1PEAPEAUHKEY__@@@Z; GetPerflibKeyValue(ushort const *,ulong,ulong,void *,ulong,void *,HKEY__ * *)
0x18000f73b  mov     [rsp+108h+arg_0], 2710h
0x18000f746  lea     rax, [rsp+108h+Handle]
0x18000f74e  mov     [rsp+108h+var_D8], rax; HKEY *
0x18000f753  lea     rax, [rsp+108h+arg_0]
0x18000f75b  mov     [rsp+108h+ResultLength], rax; void *
0x18000f760  lea     r9, ?dwExtCtrOpenProcWaitMs@@3KA; void *
0x18000f767  lea     rcx, ?OpenProcedureWaitTime@@3QBGB; "OpenProcedureWaitTime"
0x18000f76e  call    ?GetPerflibKeyValue@@YAJPEBGKKPEAXK1PEAPEAUHKEY__@@@Z; GetPerflibKeyValue(ushort const *,ulong,ulong,void *,ulong,void *,HKEY__ * *)
0x18000f773  mov     [rsp+108h+arg_0], 1D4C0h
0x18000f77e  lea     rax, [rsp+108h+Handle]
0x18000f786  mov     [rsp+108h+var_D8], rax; HKEY *
0x18000f78b  lea     rax, [rsp+108h+arg_0]
0x18000f793  mov     [rsp+108h+ResultLength], rax; void *
0x18000f798  lea     r9, ?dwThreadAndLibraryTimeout@@3KA; void *
0x18000f79f  lea     rcx, ?LibraryUnloadTime@@3QBGB; "Library Unload Time"
0x18000f7a6  call    ?GetPerflibKeyValue@@YAJPEBGKKPEAXK1PEAPEAUHKEY__@@@Z; GetPerflibKeyValue(ushort const *,ulong,ulong,void *,ulong,void *,HKEY__ * *)
0x18000f7ab  mov     rcx, [rsp+108h+Handle]; Handle
0x18000f7b3  test    rcx, rcx
0x18000f7b6  jz      short loc_18000F7BE
0x18000f7b8  call    cs:__imp_NtClose
0x18000f7be  call    McGenEventRegister_EtwEventRegister
0x18000f7c3  xor     eax, eax
0x18000f7c5  mov     [rsp+108h+Destination.Length], ax
0x18000f7ca  mov     ecx, 202h
0x18000f7cf  movzx   eax, [rsp+108h+DestinationString.MaximumLength]
0x18000f7d7  add     ax, cx
0x18000f7da  movzx   ecx, ax
0x18000f7dd  mov     [rsp+108h+Destination.MaximumLength], cx
0x18000f7e2  shr     rcx, 1
0x18000f7e5  mov     r12d, 2
0x18000f7eb  mov     eax, r12d
0x18000f7ee  mul     rcx
0x18000f7f1  lea     rcx, [r12-3]
0x18000f7f6  cmovb   rax, rcx
0x18000f7fa  mov     rcx, rax
0x18000f7fd  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000f802  mov     [rsp+108h+Destination.Buffer], rax
0x18000f807  mov     [rsp+108h+ObjectAttributes.Length], 30h ; '0'
0x18000f80f  mov     [rsp+108h+ObjectAttributes.RootDirectory], 0
0x18000f818  mov     [rsp+108h+ObjectAttributes.Attributes], 40h ; '@'
0x18000f823  lea     rax, [rsp+108h+var_48]
0x18000f82b  mov     [rsp+108h+ObjectAttributes.ObjectName], rax
0x18000f830  xorps   xmm0, xmm0
0x18000f833  movdqu  xmmword ptr [rsp+108h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f83c  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x18000f841  mov     edx, 20019h; DesiredAccess
0x18000f846  lea     rcx, [rsp+108h+KeyHandle]; KeyHandle
0x18000f84e  call    cs:__imp_NtOpenKey
0x18000f854  mov     ebx, eax
0x18000f856  mov     ecx, 218h
0x18000f85b  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000f860  mov     rsi, rax
0x18000f863  mov     [rsp+108h+var_A8], rax
0x18000f868  mov     ecx, 200h
0x18000f86d  mov     [rsp+108h+var_56], cx
0x18000f875  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000f87a  mov     r15, rax
0x18000f87d  mov     [rsp+108h+var_50], rax
0x18000f885  test    ebx, ebx
0x18000f887  js      loc_18000FB17
0x18000f88d  cmp     [rsp+108h+Destination.Buffer], 0
0x18000f893  jz      loc_18000FB17
0x18000f899  test    rsi, rsi
0x18000f89c  jz      loc_18000FB17
0x18000f8a2  test    rax, rax
0x18000f8a5  jz      loc_18000FB17
0x18000f8ab  xor     r14d, r14d
0x18000f8ae  mov     [rsp+108h+var_B0], r14d
0x18000f8b3  lea     rax, [rsp+108h+arg_8]
0x18000f8bb  mov     [rsp+108h+ResultLength], rax; ResultLength
0x18000f8c0  mov     [rsp+108h+Length], 218h; Length
0x18000f8c8  mov     r9, rsi; KeyInformation
0x18000f8cb  xor     r8d, r8d; KeyInformationClass
0x18000f8ce  mov     edx, r14d; Index
0x18000f8d1  mov     rcx, [rsp+108h+KeyHandle]; KeyHandle
0x18000f8d9  call    cs:__imp_NtEnumerateKey
0x18000f8df  inc     r14d
0x18000f8e2  mov     [rsp+108h+var_B0], r14d
0x18000f8e7  test    eax, eax
0x18000f8e9  js      loc_18000FB17
0x18000f8ef  movzx   ecx, word ptr [rsi+0Ch]
0x18000f8f3  lea     eax, [r12+rcx]
0x18000f8f7  cmp     [rsp+108h+Destination.MaximumLength], ax
0x18000f8fc  jb      loc_18000FA0F
0x18000f902  mov     [rsp+108h+Destination.Length], cx
0x18000f907  mov     r8d, ecx; Size
0x18000f90a  lea     rdx, [rsi+10h]; Src
0x18000f90e  mov     rcx, [rsp+108h+Destination.Buffer]; void *
0x18000f913  call    memmove_0
0x18000f918  movzx   r12d, [rsp+108h+Destination.Length]
0x18000f91e  shr     r12, 1
0x18000f921  xor     ecx, ecx
0x18000f923  mov     rax, [rsp+108h+Destination.Buffer]
0x18000f928  mov     [rax+r12*2], cx
0x18000f92d  lea     rdx, [rsp+108h+DestinationString]; Source
0x18000f935  lea     rcx, [rsp+108h+Destination]; Destination
0x18000f93a  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000f940  mov     [rsp+108h+ObjectAttributes.Length], 30h ; '0'
0x18000f948  mov     rax, [rsp+108h+KeyHandle]
0x18000f950  mov     [rsp+108h+ObjectAttributes.RootDirectory], rax
0x18000f955  mov     [rsp+108h+ObjectAttributes.Attributes], 40h ; '@'
0x18000f960  lea     rax, [rsp+108h+Destination]
0x18000f965  mov     [rsp+108h+ObjectAttributes.ObjectName], rax
0x18000f96a  xorps   xmm0, xmm0
0x18000f96d  movdqu  xmmword ptr [rsp+108h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f976  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x18000f97b  mov     edx, 2001Fh; DesiredAccess
0x18000f980  lea     rcx, [rsp+108h+var_B8]; KeyHandle
0x18000f985  call    cs:__imp_NtOpenKey
0x18000f98b  mov     ebx, eax
0x18000f98d  test    eax, eax
0x18000f98f  jns     short loc_18000F9A8
0x18000f991  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x18000f996  mov     edx, 20019h; DesiredAccess
0x18000f99b  lea     rcx, [rsp+108h+var_B8]; KeyHandle
0x18000f9a0  call    cs:__imp_NtOpenKey
0x18000f9a6  mov     ebx, eax
0x18000f9a8  test    ebx, ebx
0x18000f9aa  js      loc_18000FA8E
0x18000f9b0  xor     ecx, ecx
0x18000f9b2  mov     rax, [rsp+108h+Destination.Buffer]
0x18000f9b7  mov     [rax+r12*2], cx
0x18000f9bc  lea     r8, [rsp+108h+Destination]; struct _UNICODE_STRING *
0x18000f9c1  mov     rdx, [rsp+108h+var_B8]; HKEY
0x18000f9c6  mov     rcx, [rsp+108h+KeyHandle]; HKEY
0x18000f9ce  call    ?AllocateAndInitializeExtObject@@YAPEAUEXT_OBJECT@@PEAUHKEY__@@0PEAU_UNICODE_STRING@@@Z; AllocateAndInitializeExtObject(HKEY__ *,HKEY__ *,_UNICODE_STRING *)
0x18000f9d3  test    rax, rax
0x18000f9d6  jz      short loc_18000FA4E
0x18000f9d8  cmp     byte ptr [rax+20Ch], 0
0x18000f9df  jz      short loc_18000FA41
0x18000f9e1  mov     rcx, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x18000f9e8  test    rcx, rcx
0x18000f9eb  jnz     short loc_18000FA14
0x18000f9ed  mov     rdi, rax
0x18000f9f0  mov     cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA, rax; EXT_OBJECT * ExtensibleObjects
0x18000f9f7  mov     [rsp+108h+var_70], rax
0x18000f9ff  mov     cs:?NumExtensibleObjects@@3KA, 1; ulong NumExtensibleObjects
0x18000fa09  mov     r12d, 2
0x18000fa0f  jmp     loc_18000F8B3
0x18000fa14  mov     r12d, 2
0x18000fa1a  test    rdi, rdi
0x18000fa1d  jz      short loc_18000FA2F
0x18000fa1f  mov     [rdi], rax
0x18000fa22  mov     rdi, rax
0x18000fa25  mov     [rsp+108h+var_70], rax
0x18000fa2d  jmp     short loc_18000FA39
0x18000fa2f  mov     [rax], rcx
0x18000fa32  mov     cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA, rax; EXT_OBJECT * ExtensibleObjects
0x18000fa39  inc     cs:?NumExtensibleObjects@@3KA; ulong NumExtensibleObjects
0x18000fa3f  jmp     short loc_18000FA0F
0x18000fa41  mov     rcx, [rsp+108h+var_B8]; Handle
0x18000fa46  call    cs:__imp_NtClose
0x18000fa4c  jmp     short loc_18000FA09
0x18000fa4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa55  mov     r12d, 2
0x18000fa5b  test    byte ptr [rcx+1Ch], 4
0x18000fa5f  jz      short loc_18000FA81
0x18000fa61  cmp     [rcx+19h], r12b
0x18000fa65  jb      short loc_18000FA81
0x18000fa67  lea     edx, [r12+1Dh]
0x18000fa6c  lea     r9, [rsp+108h+Destination]
0x18000fa71  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x18000fa78  mov     rcx, [rcx+10h]
0x18000fa7c  call    WPP_SF_Z
0x18000fa81  mov     rcx, [rsp+108h+var_B8]; Handle
0x18000fa86  call    cs:__imp_NtClose
0x18000fa8c  jmp     short loc_18000FA0F
0x18000fa8e  cmp     ebx, 0C0000034h
0x18000fa94  jz      loc_18000FA09
0x18000fa9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faa1  mov     r12d, 2
0x18000faa7  test    byte ptr [rcx+1Ch], 4
0x18000faab  jz      short loc_18000FAC5
0x18000faad  cmp     [rcx+19h], r12b
0x18000fab1  jb      short loc_18000FAC5
0x18000fab3  mov     [rsp+108h+Length], ebx
0x18000fab7  lea     r9, [rsp+108h+Destination]
0x18000fabc  mov     rcx, [rcx+10h]
0x18000fac0  call    WPP_SF_Zd
0x18000fac5  lea     r8, ?PerfpErrorLog@@3UERROR_LOG@@A; struct ERROR_LOG *
0x18000facc  xor     edx, edx; HKEY
0x18000face  mov     ecx, 7D1h; unsigned int
0x18000fad3  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x18000fad8  test    eax, eax
0x18000fada  jz      loc_18000FA0F
0x18000fae0  cmp     cs:?lEventLogLevel@@3JA, r12d; long lEventLogLevel
0x18000fae7  jl      loc_18000FA0F
0x18000faed  test    cs:Microsoft_Windows_PerflibEnableBits, 4
0x18000faf4  jz      loc_18000FA0F
0x18000fafa  mov     ecx, ebx; int
0x18000fafc  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x18000fb01  mov     r9d, eax
0x18000fb04  mov     [rsp+108h+Length], ebx
0x18000fb08  mov     r8, [rsp+108h+Destination.Buffer]
0x18000fb0d  call    McTemplateU0zqq_EtwEventWriteTransfer
0x18000fb12  jmp     loc_18000FA0F
0x18000fb17  mov     rcx, [rsp+108h+KeyHandle]; Handle
0x18000fb1f  test    rcx, rcx
0x18000fb22  jz      short loc_18000FB2A
0x18000fb24  call    cs:__imp_NtClose
0x18000fb2a  mov     rcx, [rsp+108h+Destination.Buffer]; Block
0x18000fb2f  test    rcx, rcx
0x18000fb32  jz      short loc_18000FB39
0x18000fb34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fb39  test    rsi, rsi
0x18000fb3c  jz      short loc_18000FB46
0x18000fb3e  mov     rcx, rsi; Block
0x18000fb41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fb46  test    r15, r15
0x18000fb49  jz      short loc_18000FB53
0x18000fb4b  mov     rcx, r15; Block
0x18000fb4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fb53  add     rsp, 0D8h
0x18000fb5a  pop     r15
0x18000fb5c  pop     r14
0x18000fb5e  pop     r12
0x18000fb60  pop     rdi
0x18000fb61  pop     rsi
0x18000fb62  pop     rbx
0x18000fb63  retn
0x18001e5a8  push    rbp
0x18001e5aa  sub     rsp, 40h
0x18001e5ae  mov     rbp, rdx
0x18001e5b1  mov     rcx, [rbp+120h]; Handle
0x18001e5b8  test    rcx, rcx
0x18001e5bb  jz      short loc_18001E5C4
0x18001e5bd  call    cs:__imp_NtClose
0x18001e5c3  nop
0x18001e5c4  mov     rcx, [rbp+48h]; Block
0x18001e5c8  test    rcx, rcx
0x18001e5cb  jz      short loc_18001E5D3
0x18001e5cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e5d2  nop
0x18001e5d3  mov     rcx, [rbp+60h]; Block
0x18001e5d7  test    rcx, rcx
0x18001e5da  jz      short loc_18001E5E2
0x18001e5dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e5e1  nop
0x18001e5e2  mov     rcx, [rbp+0B8h]; Block
0x18001e5e9  test    rcx, rcx
0x18001e5ec  jz      short loc_18001E5F4
0x18001e5ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e5f3  nop
0x18001e5f4  add     rsp, 40h
0x18001e5f8  pop     rbp
0x18001e5f9  retn
```
