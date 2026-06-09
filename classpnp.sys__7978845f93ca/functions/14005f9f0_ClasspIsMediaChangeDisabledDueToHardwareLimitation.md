# ClasspIsMediaChangeDisabledDueToHardwareLimitation

- ea: `0x14005f9f0`
- end: `0x14005fd99`
- name: `ClasspIsMediaChangeDisabledDueToHardwareLimitation`
- size: `937`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400543e0`

## callees

- `0x14001fbf4`
- `0x14001feac`
- `0x14003e470`
- `0x14003e640`
- `0x14003e940`
- `0x14005f9f0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14005fd24`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14005fd24`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005fcb2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005fcb2`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14005fce7`
- `ntoskrnl!ExAllocatePool2` at `0x14005fb16`
- `ntoskrnl!ExAllocatePool2` at `0x14005fb16`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14005fcc2`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14005fcc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fd07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fd07`
- `ntoskrnl!ZwClose` at `0x14005fd34`
- `ntoskrnl!ZwClose` at `0x14005fd34`
- `ntoskrnl!ZwOpenKey` at `0x14005fa6d`
- `ntoskrnl!ZwOpenKey` at `0x14005fa6d`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14005fc06`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14005fc06`

## string_xrefs

- `0x14005fc70`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
char __fastcall ClasspIsMediaChangeDisabledDueToHardwareLimitation(__int64 a1, struct _UNICODE_STRING *a2)
{
  unsigned int *v2; // rdi
  size_t v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  _BYTE *v7; // rsi
  __int64 v8; // rax
  _BYTE *v9; // r14
  __int64 v10; // rax
  __int64 v11; // rax
  _BYTE *v12; // r15
  __int64 v13; // rax
  char *Pool2; // rax
  __int64 v15; // rdi
  size_t v16; // r8
  size_t v17; // r8
  __int64 v18; // rax
  NTSTATUS v19; // eax
  void *v20; // rbx
  PVOID SystemRoutineAddress; // rax
  struct _STRING SourceString; // [rsp+30h] [rbp-99h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-89h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+50h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v27[14]; // [rsp+90h] [rbp-39h] BYREF
  int v28; // [rsp+130h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+138h] [rbp+6Fh] BYREF

  v2 = *(unsigned int **)(a1 + 520);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  KeyHandle = 0;
  memset(v27, 0, sizeof(v27));
  v28 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a2;
  DestinationString = 0;
  SourceString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    return 1;
  SourceString.Buffer = 0;
  DestinationString.Buffer = 0;
  v4 = -1;
  v5 = v2[3];
  if ( (_DWORD)v5 )
  {
    v7 = (char *)v2 + v5;
    v6 = -1;
    do
      ++v6;
    while ( v7[v6] );
  }
  else
  {
    if ( !v2[4] )
      goto LABEL_48;
    LOWORD(v6) = 0;
    v7 = 0;
  }
  v8 = v2[4];
  if ( (_DWORD)v8 )
  {
    v9 = (char *)v2 + v8;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    LOWORD(v6) = v10 + v6;
  }
  else
  {
    v9 = 0;
  }
  v11 = v2[5];
  if ( (_DWORD)v11 )
  {
    v12 = (char *)v2 + v11;
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    LOWORD(v6) = v13 + v6;
  }
  else
  {
    v12 = 0;
  }
  SourceString.Length = v6;
  SourceString.MaximumLength = v6 + 1;
  Pool2 = (char *)ExAllocatePool2(64, (unsigned __int16)(v6 + 1), 1095525203);
  SourceString.Buffer = Pool2;
  if ( Pool2 )
  {
    LODWORD(v15) = 0;
    if ( v7 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v7[v16] );
      memmove(Pool2, v7, v16);
      v15 = -1;
      do
        ++v15;
      while ( v7[v15] );
    }
    if ( v9 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v9[v17] );
      memmove(&SourceString.Buffer[(unsigned int)v15], v9, v17);
      v18 = -1;
      do
        ++v18;
      while ( v9[v18] );
      LODWORD(v15) = v18 + v15;
    }
    if ( v12 )
    {
      do
        ++v4;
      while ( v12[v4] );
      memmove(&SourceString.Buffer[(unsigned int)v15], v12, v4);
    }
    SourceString.Buffer[SourceString.Length] = 0;
    v19 = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 1u);
    if ( v19 >= 0 )
    {
      v20 = KeyHandle;
      v27[0] = &ClasspMediaChangeRegistryCallBack;
      LODWORD(v27[1]) = 4;
      v27[2] = L"AutoRunAlwaysDisable";
      LODWORD(v27[4]) = 7;
      v27[3] = &v28;
      LODWORD(v27[6]) = 0;
      v27[5] = &qword_140043658;
      SystemRoutineName = 0;
      RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
      SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
      if ( !SystemRoutineAddress )
        SystemRoutineAddress = RtlQueryRegistryValues;
      ((void (__fastcall *)(__int64, void *, _QWORD *, struct _UNICODE_STRING *, _QWORD))SystemRoutineAddress)(
        0x40000000,
        v20,
        v27,
        &DestinationString,
        0);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        82,
        WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
        (unsigned int)v19);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
  }
  if ( SourceString.Buffer )
  {
    ExFreePoolWithTag(SourceString.Buffer, 0);
    SourceString.Buffer = 0;
  }
  if ( DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
LABEL_48:
  ZwClose(KeyHandle);
  if ( v28 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14005f9f0  mov     [rsp-8+arg_10], rbx
0x14005f9f5  mov     [rsp-8+arg_18], rsi
0x14005f9fa  push    rbp
0x14005f9fb  push    rdi
0x14005f9fc  push    r12
0x14005f9fe  push    r14
0x14005fa00  push    r15
0x14005fa02  lea     rbp, [rsp-37h]
0x14005fa07  sub     rsp, 100h
0x14005fa0e  mov     rdi, [rcx+208h]
0x14005fa15  xor     r12d, r12d
0x14005fa18  mov     rbx, rdx
0x14005fa1b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14005fa23  xor     edx, edx; Val
0x14005fa25  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14005fa2d  lea     rcx, [rbp+57h+var_90]; void *
0x14005fa31  mov     [rbp+57h+KeyHandle], r12
0x14005fa35  lea     r8d, [r12+70h]; Size
0x14005fa3a  call    memset
0x14005fa3f  xorps   xmm0, xmm0
0x14005fa42  mov     [rbp+57h+arg_0], r12d
0x14005fa46  xorps   xmm1, xmm1
0x14005fa49  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x14005fa4d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005fa51  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x14005fa55  mov     edx, 20019h; DesiredAccess
0x14005fa5a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005fa5e  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x14005fa63  movups  xmmword ptr [rsp+120h+SourceString.Length], xmm1
0x14005fa68  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005fa6d  call    cs:__imp_ZwOpenKey
0x14005fa74  nop     dword ptr [rax+rax+00h]
0x14005fa79  test    eax, eax
0x14005fa7b  js      loc_14005FD76
0x14005fa81  mov     [rsp+120h+SourceString.Buffer], r12
0x14005fa86  lea     rsi, WPP_GLOBAL_Control
0x14005fa8d  mov     [rsp+120h+DestinationString.Buffer], r12
0x14005fa92  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14005fa96  mov     eax, [rdi+0Ch]
0x14005fa99  test    eax, eax
0x14005fa9b  jnz     short loc_14005FAAF
0x14005fa9d  cmp     [rdi+10h], r12d
0x14005faa1  jz      loc_14005FD30
0x14005faa7  mov     ecx, r12d
0x14005faaa  mov     esi, r12d
0x14005faad  jmp     short loc_14005FABF
0x14005faaf  lea     rsi, [rdi+rax]
0x14005fab3  mov     rcx, rbx
0x14005fab6  inc     rcx
0x14005fab9  cmp     [rsi+rcx], r12b
0x14005fabd  jnz     short loc_14005FAB6
0x14005fabf  mov     eax, [rdi+10h]
0x14005fac2  test    eax, eax
0x14005fac4  jnz     short loc_14005FACB
0x14005fac6  mov     r14, r12
0x14005fac9  jmp     short loc_14005FADD
0x14005facb  lea     r14, [rdi+rax]
0x14005facf  mov     rax, rbx
0x14005fad2  inc     rax
0x14005fad5  cmp     [r14+rax], r12b
0x14005fad9  jnz     short loc_14005FAD2
0x14005fadb  add     ecx, eax
0x14005fadd  mov     eax, [rdi+14h]
0x14005fae0  test    eax, eax
0x14005fae2  jnz     short loc_14005FAE9
0x14005fae4  mov     r15, r12
0x14005fae7  jmp     short loc_14005FAFB
0x14005fae9  lea     r15, [rdi+rax]
0x14005faed  mov     rax, rbx
0x14005faf0  inc     rax
0x14005faf3  cmp     [r15+rax], r12b
0x14005faf7  jnz     short loc_14005FAF0
0x14005faf9  add     ecx, eax
0x14005fafb  mov     [rsp+120h+SourceString.Length], cx
0x14005fb00  mov     r8d, 414C6353h
0x14005fb06  inc     cx
0x14005fb09  movzx   edx, cx
0x14005fb0c  mov     ecx, 40h ; '@'
0x14005fb11  mov     [rsp+120h+SourceString.MaximumLength], dx
0x14005fb16  call    cs:__imp_ExAllocatePool2
0x14005fb1d  nop     dword ptr [rax+rax+00h]
0x14005fb22  mov     [rsp+120h+SourceString.Buffer], rax
0x14005fb27  test    rax, rax
0x14005fb2a  jnz     short loc_14005FB72
0x14005fb2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fb33  lea     rsi, WPP_GLOBAL_Control
0x14005fb3a  cmp     rcx, rsi
0x14005fb3d  jz      loc_14005FCFB
0x14005fb43  test    dword ptr [rcx+2Ch], 1000h
0x14005fb4a  jz      loc_14005FCFB
0x14005fb50  cmp     byte ptr [rcx+29h], 4
0x14005fb54  jb      loc_14005FCFB
0x14005fb5a  mov     rcx, [rcx+18h]
0x14005fb5e  lea     edx, [rax+51h]
0x14005fb61  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14005fb68  call    WPP_SF_
0x14005fb6d  jmp     loc_14005FCFB
0x14005fb72  mov     edi, r12d
0x14005fb75  test    rsi, rsi
0x14005fb78  jz      short loc_14005FB9D
0x14005fb7a  mov     r8, rbx
0x14005fb7d  inc     r8; Size
0x14005fb80  cmp     [rsi+r8], r12b
0x14005fb84  jnz     short loc_14005FB7D
0x14005fb86  mov     rdx, rsi; Src
0x14005fb89  mov     rcx, rax; void *
0x14005fb8c  call    memmove
0x14005fb91  mov     rdi, rbx
0x14005fb94  inc     rdi
0x14005fb97  cmp     [rsi+rdi], r12b
0x14005fb9b  jnz     short loc_14005FB94
0x14005fb9d  test    r14, r14
0x14005fba0  jz      short loc_14005FBCB
0x14005fba2  mov     r8, rbx
0x14005fba5  inc     r8; Size
0x14005fba8  cmp     [r14+r8], r12b
0x14005fbac  jnz     short loc_14005FBA5
0x14005fbae  mov     ecx, edi
0x14005fbb0  mov     rdx, r14; Src
0x14005fbb3  add     rcx, [rsp+120h+SourceString.Buffer]; void *
0x14005fbb8  call    memmove
0x14005fbbd  mov     rax, rbx
0x14005fbc0  inc     rax
0x14005fbc3  cmp     [r14+rax], r12b
0x14005fbc7  jnz     short loc_14005FBC0
0x14005fbc9  add     edi, eax
0x14005fbcb  test    r15, r15
0x14005fbce  jz      short loc_14005FBEB
0x14005fbd0  inc     rbx
0x14005fbd3  cmp     [r15+rbx], r12b
0x14005fbd7  jnz     short loc_14005FBD0
0x14005fbd9  mov     ecx, edi
0x14005fbdb  mov     r8, rbx; Size
0x14005fbde  add     rcx, [rsp+120h+SourceString.Buffer]; void *
0x14005fbe3  mov     rdx, r15; Src
0x14005fbe6  call    memmove
0x14005fbeb  movzx   ecx, [rsp+120h+SourceString.Length]
0x14005fbf0  lea     rdx, [rsp+120h+SourceString]; SourceString
0x14005fbf5  mov     rax, [rsp+120h+SourceString.Buffer]
0x14005fbfa  mov     r8b, 1; AllocateDestinationString
0x14005fbfd  mov     [rcx+rax], r12b
0x14005fc01  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14005fc06  call    cs:__imp_RtlAnsiStringToUnicodeString
0x14005fc0d  nop     dword ptr [rax+rax+00h]
0x14005fc12  test    eax, eax
0x14005fc14  jns     short loc_14005FC61
0x14005fc16  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fc1d  lea     rsi, WPP_GLOBAL_Control
0x14005fc24  cmp     rcx, rsi
0x14005fc27  jz      loc_14005FCFB
0x14005fc2d  test    dword ptr [rcx+2Ch], 1000h
0x14005fc34  jz      loc_14005FCFB
0x14005fc3a  cmp     byte ptr [rcx+29h], 4
0x14005fc3e  jb      loc_14005FCFB
0x14005fc44  mov     rcx, [rcx+18h]
0x14005fc48  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14005fc4f  mov     edx, 52h ; 'R'
0x14005fc54  mov     r9d, eax
0x14005fc57  call    WPP_SF_d
0x14005fc5c  jmp     loc_14005FCFB
0x14005fc61  mov     rbx, [rbp+57h+KeyHandle]
0x14005fc65  lea     rax, ClasspMediaChangeRegistryCallBack
0x14005fc6c  mov     [rbp+57h+var_90], rax
0x14005fc70  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x14005fc77  lea     rax, aAutorunalwaysd; "AutoRunAlwaysDisable"
0x14005fc7e  mov     [rbp+57h+var_88], 4
0x14005fc85  mov     [rbp+57h+var_80], rax
0x14005fc89  lea     rcx, [rbp+57h+SystemRoutineName]; DestinationString
0x14005fc8d  lea     rax, [rbp+57h+arg_0]
0x14005fc91  mov     [rbp+57h+var_70], 7
0x14005fc98  mov     [rbp+57h+var_78], rax
0x14005fc9c  xorps   xmm0, xmm0
0x14005fc9f  lea     rax, qword_140043658
0x14005fca6  mov     [rbp+57h+var_60], r12d
0x14005fcaa  mov     [rbp+57h+var_68], rax
0x14005fcae  movups  xmmword ptr [rbp+57h+SystemRoutineName.Length], xmm0
0x14005fcb2  call    cs:__imp_RtlInitUnicodeString
0x14005fcb9  nop     dword ptr [rax+rax+00h]
0x14005fcbe  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x14005fcc2  call    cs:__imp_MmGetSystemRoutineAddress
0x14005fcc9  nop     dword ptr [rax+rax+00h]
0x14005fcce  lea     r9, [rsp+120h+DestinationString]
0x14005fcd3  mov     [rsp+120h+var_100], r12
0x14005fcd8  test    rax, rax
0x14005fcdb  lea     r8, [rbp+57h+var_90]
0x14005fcdf  mov     rdx, rbx
0x14005fce2  mov     ecx, 40000000h
0x14005fce7  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14005fcef  call    _guard_dispatch_icall
0x14005fcf4  lea     rsi, WPP_GLOBAL_Control
0x14005fcfb  mov     rcx, [rsp+120h+SourceString.Buffer]; P
0x14005fd00  test    rcx, rcx
0x14005fd03  jz      short loc_14005FD18
0x14005fd05  xor     edx, edx; Tag
0x14005fd07  call    cs:__imp_ExFreePoolWithTag
0x14005fd0e  nop     dword ptr [rax+rax+00h]
0x14005fd13  mov     [rsp+120h+SourceString.Buffer], r12
0x14005fd18  cmp     [rsp+120h+DestinationString.Buffer], r12
0x14005fd1d  jz      short loc_14005FD30
0x14005fd1f  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x14005fd24  call    cs:__imp_RtlFreeUnicodeString
0x14005fd2b  nop     dword ptr [rax+rax+00h]
0x14005fd30  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14005fd34  call    cs:__imp_ZwClose
0x14005fd3b  nop     dword ptr [rax+rax+00h]
0x14005fd40  cmp     [rbp+57h+arg_0], r12d
0x14005fd44  jz      short loc_14005FD95
0x14005fd46  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fd4d  cmp     rcx, rsi
0x14005fd50  jz      short loc_14005FD76
0x14005fd52  test    dword ptr [rcx+2Ch], 1000h
0x14005fd59  jz      short loc_14005FD76
0x14005fd5b  cmp     byte ptr [rcx+29h], 4
0x14005fd5f  jb      short loc_14005FD76
0x14005fd61  mov     rcx, [rcx+18h]
0x14005fd65  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14005fd6c  mov     edx, 53h ; 'S'
0x14005fd71  call    WPP_SF_
0x14005fd76  mov     al, 1
0x14005fd78  lea     r11, [rsp+120h+var_20]
0x14005fd80  mov     rbx, [r11+40h]
0x14005fd84  mov     rsi, [r11+48h]
0x14005fd88  mov     rsp, r11
0x14005fd8b  pop     r15
0x14005fd8d  pop     r14
0x14005fd8f  pop     r12
0x14005fd91  pop     rdi
0x14005fd92  pop     rbp
0x14005fd93  retn
0x14005fd95  xor     al, al
0x14005fd97  jmp     short loc_14005FD78
```
