# HidpGetIoctlSupportabilities

- ea: `0x180041248`
- end: `0x180041690`
- name: `HidpGetIoctlSupportabilities`
- size: `1096`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003a590`

## callees

- `0x18000ddc8`
- `0x180014e80`
- `0x180041248`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18004142a`
- `ntoskrnl!ZwQueryValueKey` at `0x1800415ba`
- `ntoskrnl!ZwQueryValueKey` at `0x18004142a`
- `ntoskrnl!ZwQueryValueKey` at `0x1800415ba`
- `ntoskrnl!ZwClose` at `0x18004166a`
- `ntoskrnl!ZwClose` at `0x18004166a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800414d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041655`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800414d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041655`
- `ntoskrnl!ExAllocatePool2` at `0x180041364`
- `ntoskrnl!ExAllocatePool2` at `0x180041512`
- `ntoskrnl!ExAllocatePool2` at `0x180041364`
- `ntoskrnl!ExAllocatePool2` at `0x180041512`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18004129a`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18004129a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180041341`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800414ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x180041341`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800414ef`

## string_xrefs

- `0x1800414e4`: `WriteReportExSupported`

## pseudocode

```c
void __fastcall HidpGetIoctlSupportabilities(__int64 a1, struct _DEVICE_OBJECT *a2)
{
  char v3; // bl
  NTSTATUS v4; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // edx
  unsigned int *Pool2; // rdi
  int v9; // r8d
  NTSTATUS v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  unsigned int *v14; // rdi
  int v15; // r8d
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  ULONG Length; // [rsp+A0h] [rbp+30h] BYREF
  void *DeviceRegKey; // [rsp+B0h] [rbp+40h] BYREF

  *(_BYTE *)(a1 + 1888) = 0;
  *(_BYTE *)(a1 + 1976) = 0;
  DeviceRegKey = 0;
  v3 = 1;
  Length = 0;
  DestinationString = 0;
  v4 = IoOpenDeviceRegistryKey(a2, 1u, 0x1F0000u, &DeviceRegKey);
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"DeviceResetNotificationEnabled");
    Length = DestinationString.MaximumLength + 28;
    Pool2 = (unsigned int *)ExAllocatePool2(256, Length, 1130654024);
    if ( Pool2 )
    {
      v10 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValueFullInformation, Pool2, Length, &Length);
      if ( v10 >= 0 )
      {
        if ( Pool2[3] == 4 )
          *(_BYTE *)(a1 + 1888) = *(unsigned int *)((char *)Pool2 + Pool2[2]) != 0;
      }
      else
      {
        LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qL(
            WPP_GLOBAL_Control->AttachedDevice,
            v11,
            v12,
            *(_QWORD *)(a1 + 672),
            3,
            3,
            16,
            (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
            *(_QWORD *)a1,
            v10);
        }
      }
      ExFreePoolWithTag(Pool2, 0);
      RtlInitUnicodeString(&DestinationString, L"WriteReportExSupported");
      Length = DestinationString.MaximumLength + 28;
      v14 = (unsigned int *)ExAllocatePool2(256, Length, 1130654024);
      if ( !v14 )
      {
        LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qLL(
            WPP_GLOBAL_Control->AttachedDevice,
            v13,
            v15,
            *(_QWORD *)(a1 + 672),
            2,
            3,
            17,
            (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
            *(_QWORD *)a1,
            Length,
            154);
        }
      }
      v16 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValueFullInformation, v14, Length, &Length);
      if ( v16 >= 0 )
      {
        if ( v14[3] == 4 )
          *(_BYTE *)(a1 + 1976) = *(unsigned int *)((char *)v14 + v14[2]) != 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
          v3 = 0;
        }
        if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v17) = v3;
          LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qL(
            WPP_GLOBAL_Control->AttachedDevice,
            v17,
            v18,
            *(_QWORD *)(a1 + 672),
            3,
            3,
            18,
            (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
            *(_QWORD *)a1,
            v16);
        }
      }
      if ( v14 )
        ExFreePoolWithTag(v14, 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v3 = 0;
      }
      if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = v3;
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v7,
          v9,
          *(_QWORD *)(a1 + 672),
          2,
          3,
          15,
          (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
          *(_QWORD *)a1,
          Length,
          154);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = v3;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v6,
        *(_QWORD *)(a1 + 672),
        2,
        3,
        14,
        (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
        *(_QWORD *)a1,
        v4);
    }
  }
  if ( DeviceRegKey )
    ZwClose(DeviceRegKey);
}

```

## disassembly

```asm
0x180041248  mov     [rsp-28h+arg_8], rbx
0x18004124d  mov     [rsp-28h+arg_18], rsi
0x180041252  push    rbp
0x180041253  push    rdi
0x180041254  push    r13
0x180041256  push    r14
0x180041258  push    r15
0x18004125a  mov     rbp, rsp
0x18004125d  sub     rsp, 70h
0x180041261  xor     r15d, r15d
0x180041264  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x180041268  mov     rax, rdx
0x18004126b  mov     [rcx+760h], r15b
0x180041272  mov     rsi, rcx
0x180041275  mov     [rcx+7B8h], r15b
0x18004127c  xorps   xmm0, xmm0
0x18004127f  mov     [rbp+DeviceRegKey], r15
0x180041283  lea     ebx, [r15+1]
0x180041287  mov     [rbp+arg_0], r15d
0x18004128b  mov     edx, ebx; DevInstKeyType
0x18004128d  mov     r8d, 1F0000h; DesiredAccess
0x180041293  mov     rcx, rax; DeviceObject
0x180041296  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004129a  call    cs:__imp_IoOpenDeviceRegistryKey
0x1800412a1  nop     dword ptr [rax+rax+00h]
0x1800412a6  test    eax, eax
0x1800412a8  jns     loc_180041336
0x1800412ae  mov     r10, cs:WPP_GLOBAL_Control
0x1800412b5  lea     r14, WPP_GLOBAL_Control
0x1800412bc  cmp     r10, r14
0x1800412bf  jz      short loc_1800412D1
0x1800412c1  mov     ecx, [r10+2Ch]
0x1800412c5  test    cl, 4
0x1800412c8  jz      short loc_1800412D1
0x1800412ca  cmp     byte ptr [r10+29h], 2
0x1800412cf  jnb     short loc_1800412D4
0x1800412d1  mov     bl, r15b
0x1800412d4  lea     r15, WPP_RECORDER_INITIALIZED
0x1800412db  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800412e2  setnz   r8b
0x1800412e6  test    bl, bl
0x1800412e8  jnz     short loc_1800412F3
0x1800412ea  test    r8b, r8b
0x1800412ed  jz      loc_180041661
0x1800412f3  mov     r9, [rsi+2A0h]
0x1800412fa  lea     r13, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180041301  mov     rcx, [r10+18h]
0x180041305  mov     dl, bl
0x180041307  mov     [rsp+70h+var_28], eax
0x18004130b  mov     rax, [rsi]
0x18004130e  mov     [rsp+70h+var_30], rax
0x180041313  mov     [rsp+70h+var_38], r13
0x180041318  mov     [rsp+70h+var_40], 0Eh
0x18004131f  mov     dword ptr [rsp+70h+ResultLength], 3
0x180041327  mov     byte ptr [rsp+70h+Length], 2
0x18004132c  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180041331  jmp     loc_180041661
0x180041336  lea     rdx, aDeviceresetnot; "DeviceResetNotificationEnabled"
0x18004133d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180041341  call    cs:__imp_RtlInitUnicodeString
0x180041348  nop     dword ptr [rax+rax+00h]
0x18004134d  movzx   eax, [rbp+DestinationString.MaximumLength]
0x180041351  mov     ecx, 100h
0x180041356  add     eax, 1Ch
0x180041359  mov     r8d, 43646948h
0x18004135f  mov     edx, eax
0x180041361  mov     [rbp+arg_0], eax
0x180041364  call    cs:__imp_ExAllocatePool2
0x18004136b  nop     dword ptr [rax+rax+00h]
0x180041370  mov     rdi, rax
0x180041373  test    rax, rax
0x180041376  jnz     loc_18004140C
0x18004137c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041383  lea     r14, WPP_GLOBAL_Control
0x18004138a  cmp     rcx, r14
0x18004138d  jz      short loc_18004139C
0x18004138f  mov     eax, [rcx+2Ch]
0x180041392  test    al, 4
0x180041394  jz      short loc_18004139C
0x180041396  cmp     byte ptr [rcx+29h], 2
0x18004139a  jnb     short loc_18004139F
0x18004139c  mov     bl, r15b
0x18004139f  lea     r15, WPP_RECORDER_INITIALIZED
0x1800413a6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800413ad  setnz   r8b
0x1800413b1  test    bl, bl
0x1800413b3  jnz     short loc_1800413BE
0x1800413b5  test    r8b, r8b
0x1800413b8  jz      loc_180041661
0x1800413be  mov     eax, [rbp+arg_0]
0x1800413c1  lea     r13, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x1800413c8  mov     r9, [rsi+2A0h]
0x1800413cf  mov     dl, bl
0x1800413d1  mov     rcx, [rcx+18h]
0x1800413d5  mov     [rsp+70h+var_20], 0C000009Ah
0x1800413dd  mov     [rsp+70h+var_28], eax
0x1800413e1  mov     rax, [rsi]
0x1800413e4  mov     [rsp+70h+var_30], rax
0x1800413e9  mov     [rsp+70h+var_38], r13
0x1800413ee  mov     [rsp+70h+var_40], 0Fh
0x1800413f5  mov     dword ptr [rsp+70h+ResultLength], 3
0x1800413fd  mov     byte ptr [rsp+70h+Length], 2
0x180041402  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x180041407  jmp     loc_180041661
0x18004140c  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x180041410  lea     rax, [rbp+arg_0]
0x180041414  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180041419  lea     rdx, [rbp+DestinationString]; ValueName
0x18004141d  mov     eax, [rbp+arg_0]
0x180041420  mov     r9, rdi; KeyValueInformation
0x180041423  mov     r8d, ebx; KeyValueInformationClass
0x180041426  mov     [rsp+70h+Length], eax; Length
0x18004142a  call    cs:__imp_ZwQueryValueKey
0x180041431  nop     dword ptr [rax+rax+00h]
0x180041436  lea     r14, WPP_GLOBAL_Control
0x18004143d  mov     r9d, eax
0x180041440  lea     r15, WPP_RECORDER_INITIALIZED
0x180041447  lea     r13, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x18004144e  test    eax, eax
0x180041450  jns     short loc_1800414BD
0x180041452  mov     rcx, cs:WPP_GLOBAL_Control
0x180041459  cmp     rcx, r14
0x18004145c  jz      short loc_18004146F
0x18004145e  mov     eax, [rcx+2Ch]
0x180041461  test    al, 4
0x180041463  jz      short loc_18004146F
0x180041465  cmp     byte ptr [rcx+29h], 3
0x180041469  jb      short loc_18004146F
0x18004146b  mov     dl, bl
0x18004146d  jmp     short loc_180041471
0x18004146f  xor     dl, dl
0x180041471  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180041478  setnz   r8b
0x18004147c  test    dl, dl
0x18004147e  jnz     short loc_180041485
0x180041480  test    r8b, r8b
0x180041483  jz      short loc_1800414D3
0x180041485  mov     rax, [rsi]
0x180041488  mov     rcx, [rcx+18h]
0x18004148c  mov     [rsp+70h+var_28], r9d
0x180041491  mov     r9, [rsi+2A0h]
0x180041498  mov     [rsp+70h+var_30], rax
0x18004149d  mov     [rsp+70h+var_38], r13
0x1800414a2  mov     [rsp+70h+var_40], 10h
0x1800414a9  mov     dword ptr [rsp+70h+ResultLength], 3
0x1800414b1  mov     byte ptr [rsp+70h+Length], 3
0x1800414b6  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1800414bb  jmp     short loc_1800414D3
0x1800414bd  cmp     dword ptr [rdi+0Ch], 4
0x1800414c1  jnz     short loc_1800414D3
0x1800414c3  mov     eax, [rdi+8]
0x1800414c6  cmp     dword ptr [rax+rdi], 0
0x1800414ca  setnz   al
0x1800414cd  mov     [rsi+760h], al
0x1800414d3  xor     edx, edx; Tag
0x1800414d5  mov     rcx, rdi; P
0x1800414d8  call    cs:__imp_ExFreePoolWithTag
0x1800414df  nop     dword ptr [rax+rax+00h]
0x1800414e4  lea     rdx, aWritereportexs; "WriteReportExSupported"
0x1800414eb  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800414ef  call    cs:__imp_RtlInitUnicodeString
0x1800414f6  nop     dword ptr [rax+rax+00h]
0x1800414fb  movzx   eax, [rbp+DestinationString.MaximumLength]
0x1800414ff  mov     ecx, 100h
0x180041504  add     eax, 1Ch
0x180041507  mov     r8d, 43646948h
0x18004150d  mov     edx, eax
0x18004150f  mov     [rbp+arg_0], eax
0x180041512  call    cs:__imp_ExAllocatePool2
0x180041519  nop     dword ptr [rax+rax+00h]
0x18004151e  mov     rdi, rax
0x180041521  test    rax, rax
0x180041524  jnz     short loc_18004159C
0x180041526  mov     r10, cs:WPP_GLOBAL_Control
0x18004152d  cmp     r10, r14
0x180041530  jz      short loc_180041546
0x180041532  mov     ecx, [r10+2Ch]
0x180041536  test    cl, 4
0x180041539  jz      short loc_180041546
0x18004153b  cmp     byte ptr [r10+29h], 2
0x180041540  jb      short loc_180041546
0x180041542  mov     dl, bl
0x180041544  jmp     short loc_180041548
0x180041546  xor     dl, dl
0x180041548  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18004154f  setnz   r8b
0x180041553  test    dl, dl
0x180041555  jnz     short loc_18004155C
0x180041557  test    r8b, r8b
0x18004155a  jz      short loc_18004159C
0x18004155c  mov     eax, [rbp+arg_0]
0x18004155f  mov     r9, [rsi+2A0h]
0x180041566  mov     rcx, [r10+18h]
0x18004156a  mov     [rsp+70h+var_20], 0C000009Ah
0x180041572  mov     [rsp+70h+var_28], eax
0x180041576  mov     rax, [rsi]
0x180041579  mov     [rsp+70h+var_30], rax
0x18004157e  mov     [rsp+70h+var_38], r13
0x180041583  mov     [rsp+70h+var_40], 11h
0x18004158a  mov     dword ptr [rsp+70h+ResultLength], 3
0x180041592  mov     byte ptr [rsp+70h+Length], 2
0x180041597  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x18004159c  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x1800415a0  lea     rax, [rbp+arg_0]
0x1800415a4  mov     [rsp+70h+ResultLength], rax; ResultLength
0x1800415a9  lea     rdx, [rbp+DestinationString]; ValueName
0x1800415ad  mov     eax, [rbp+arg_0]
0x1800415b0  mov     r9, rdi; KeyValueInformation
0x1800415b3  mov     r8d, ebx; KeyValueInformationClass
0x1800415b6  mov     [rsp+70h+Length], eax; Length
0x1800415ba  call    cs:__imp_ZwQueryValueKey
0x1800415c1  nop     dword ptr [rax+rax+00h]
0x1800415c6  test    eax, eax
0x1800415c8  jns     short loc_180041635
0x1800415ca  mov     r10, cs:WPP_GLOBAL_Control
0x1800415d1  cmp     r10, r14
0x1800415d4  jz      short loc_1800415E6
0x1800415d6  mov     ecx, [r10+2Ch]
0x1800415da  test    cl, 4
0x1800415dd  jz      short loc_1800415E6
0x1800415df  cmp     byte ptr [r10+29h], 3
0x1800415e4  jnb     short loc_1800415E8
0x1800415e6  xor     bl, bl
0x1800415e8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800415ef  setnz   r8b
0x1800415f3  test    bl, bl
0x1800415f5  jnz     short loc_1800415FC
0x1800415f7  test    r8b, r8b
0x1800415fa  jz      short loc_18004164B
0x1800415fc  mov     r9, [rsi+2A0h]
0x180041603  mov     dl, bl
0x180041605  mov     rcx, [r10+18h]
0x180041609  mov     [rsp+70h+var_28], eax
0x18004160d  mov     rax, [rsi]
0x180041610  mov     [rsp+70h+var_30], rax
0x180041615  mov     [rsp+70h+var_38], r13
0x18004161a  mov     [rsp+70h+var_40], 12h
0x180041621  mov     dword ptr [rsp+70h+ResultLength], 3
0x180041629  mov     byte ptr [rsp+70h+Length], 3
0x18004162e  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180041633  jmp     short loc_18004164B
0x180041635  cmp     dword ptr [rdi+0Ch], 4
0x180041639  jnz     short loc_18004164B
0x18004163b  mov     eax, [rdi+8]
0x18004163e  cmp     dword ptr [rax+rdi], 0
0x180041642  setnz   al
0x180041645  mov     [rsi+7B8h], al
0x18004164b  test    rdi, rdi
0x18004164e  jz      short loc_180041661
0x180041650  xor     edx, edx; Tag
0x180041652  mov     rcx, rdi; P
0x180041655  call    cs:__imp_ExFreePoolWithTag
0x18004165c  nop     dword ptr [rax+rax+00h]
0x180041661  mov     rcx, [rbp+DeviceRegKey]; Handle
0x180041665  test    rcx, rcx
0x180041668  jz      short loc_180041676
0x18004166a  call    cs:__imp_ZwClose
0x180041671  nop     dword ptr [rax+rax+00h]
0x180041676  lea     r11, [rsp+70h+var_s0]
0x18004167b  mov     rbx, [r11+38h]
0x18004167f  mov     rsi, [r11+48h]
0x180041683  mov     rsp, r11
0x180041686  pop     r15
0x180041688  pop     r14
0x18004168a  pop     r13
0x18004168c  pop     rdi
0x18004168d  pop     rbp
0x18004168e  retn
```
