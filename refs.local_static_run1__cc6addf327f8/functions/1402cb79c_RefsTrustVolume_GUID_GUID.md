# RefsTrustVolume(_GUID &,_GUID &)

- ea: `0x1402cb79c`
- end: `0x1402cbbdd`
- name: `?RefsTrustVolume@@YAXAEAU_GUID@@0@Z`
- size: `1089`
- prototype: `void(struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402cb02c`

## callees

- `0x1400862c0`
- `0x1400d0fd8`
- `0x1400e6524`
- `0x1401f3fb0`
- `0x1402cb79c`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1402cba9c`
- `ntoskrnl!ZwSetValueKey` at `0x1402cbb25`
- `ntoskrnl!ZwSetValueKey` at `0x1402cba9c`
- `ntoskrnl!ZwSetValueKey` at `0x1402cbb25`
- `ntoskrnl!ZwClose` at `0x1402cbb9b`
- `ntoskrnl!ZwClose` at `0x1402cbbb1`
- `ntoskrnl!ZwClose` at `0x1402cbb9b`
- `ntoskrnl!ZwClose` at `0x1402cbbb1`
- `ntoskrnl!ZwCreateKey` at `0x1402cb946`
- `ntoskrnl!ZwCreateKey` at `0x1402cba17`
- `ntoskrnl!ZwCreateKey` at `0x1402cb946`
- `ntoskrnl!ZwCreateKey` at `0x1402cba17`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x1402cb9b8`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x1402cb9b8`

## string_xrefs

- `0x1402cb8a8`: `mount.c`
- `0x1402cbb81`: `mount.c`
- `0x1402cb7ca`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystemVolumes`

## pseudocode

```c
void __fastcall RefsTrustVolume(struct _GUID *a1, struct _GUID *a2)
{
  bool v4; // zf
  __int64 v5; // rax
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  unsigned int v8; // r9d
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  int Data; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v16[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v18; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  char v20; // [rsp+D0h] [rbp-30h] BYREF

  KeyHandle = 0;
  Handle = 0;
  v16[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystemVolumes";
  v16[0] = 9044104;
  v15[1] = &v20;
  v15[0] = 5111808;
  ValueName.Buffer = L"FsGuid";
  v18.Buffer = L"FsFlags";
  v5 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&`IsGuidZero'::`2'::ZeroGuid.Data1;
  v4 = *(_QWORD *)&a1->Data1 == *(_QWORD *)&`IsGuidZero'::`2'::ZeroGuid.Data1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_QWORD *)&ValueName.Length = 917516;
  *(_QWORD *)&v18.Length = 1048590;
  Data = 1;
  if ( v4 )
    v5 = *(_QWORD *)a1->Data4 - *(_QWORD *)`IsGuidZero'::`2'::ZeroGuid.Data4;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids, 3221226694LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073740602, 0, "mount.c", 0x168Au);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids);
    }
    goto LABEL_43;
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    RtlStringFromGUIDEx(a1, v15, 0);
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v15;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwCreateKey(&Handle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v10 = ZwSetValueKey(Handle, &ValueName, 0, 3u, a2, 0x10u);
      v7 = v10;
      if ( v10 >= 0 )
      {
        v11 = ZwSetValueKey(Handle, &v18, 0, 4u, &Data, 4u);
        v7 = v11;
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              85,
              WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
              (unsigned int)v11);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
          {
            v8 = 5852;
            goto LABEL_42;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            84,
            WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
            (unsigned int)v10);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v8 = 5839;
          goto LABEL_42;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          83,
          WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
          (unsigned int)v9);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v8 = 5822;
        goto LABEL_42;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        82,
        WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
        (unsigned int)v6);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v8 = 5796;
LABEL_42:
      RefsStatusDebug(v7, 0, "mount.c", v8);
    }
  }
LABEL_43:
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
}

```

## disassembly

```asm
0x1402cb79c  mov     [rsp-8+arg_10], rbx
0x1402cb7a1  push    rbp
0x1402cb7a2  push    rsi
0x1402cb7a3  push    rdi
0x1402cb7a4  lea     rbp, [rsp-30h]
0x1402cb7a9  sub     rsp, 130h
0x1402cb7b0  mov     rax, cs:__security_cookie
0x1402cb7b7  xor     rax, rsp
0x1402cb7ba  mov     [rbp+40h+var_20], rax
0x1402cb7be  xorps   xmm0, xmm0
0x1402cb7c1  mov     [rsp+140h+KeyHandle], 0
0x1402cb7ca  lea     rax, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402cb7d1  mov     [rsp+140h+Handle], 0
0x1402cb7da  mov     [rsp+140h+var_D0], rax
0x1402cb7df  mov     rsi, rdx
0x1402cb7e2  lea     rax, [rbp+40h+var_70]
0x1402cb7e6  mov     [rsp+140h+var_D8], 8A0088h
0x1402cb7ef  mov     [rsp+140h+var_E0], rax
0x1402cb7f4  mov     rbx, rcx
0x1402cb7f7  lea     rax, aFsguid; "FsGuid"
0x1402cb7fe  mov     [rsp+140h+var_E8], 4E0000h
0x1402cb807  mov     [rbp+40h+ValueName.Buffer], rax
0x1402cb80b  lea     rax, aFsflags; "FsFlags"
0x1402cb812  mov     [rbp+40h+var_B8.Buffer], rax
0x1402cb816  mov     rax, [rcx]
0x1402cb819  sub     rax, qword ptr cs:?ZeroGuid@?1??IsGuidZero@@YA_NAEBU_GUID@@@Z@4U2@B.Data1; _GUID const `IsGuidZero(_GUID const &)'::`2'::ZeroGuid ...
0x1402cb820  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1402cb824  mov     qword ptr [rsp+140h+ValueName.Length], 0E000Ch
0x1402cb82d  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1402cb831  mov     qword ptr [rbp+40h+var_B8.Length], 10000Eh
0x1402cb839  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402cb83d  mov     [rsp+140h+Data], 1
0x1402cb845  jnz     short loc_1402CB852
0x1402cb847  mov     rax, [rcx+8]
0x1402cb84b  sub     rax, qword ptr cs:?ZeroGuid@?1??IsGuidZero@@YA_NAEBU_GUID@@@Z@4U2@B.Data4; _GUID const `IsGuidZero(_GUID const &)'::`2'::ZeroGuid ...
0x1402cb852  test    rax, rax
0x1402cb855  jnz     loc_1402CB8F7
0x1402cb85b  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cb862  lea     rbx, WPP_GLOBAL_Control
0x1402cb869  mov     edi, 0C00004C6h
0x1402cb86e  cmp     rcx, rbx
0x1402cb871  jz      short loc_1402CB898
0x1402cb873  test    dword ptr [rcx+2Ch], 100h
0x1402cb87a  jz      short loc_1402CB898
0x1402cb87c  cmp     byte ptr [rcx+29h], 4
0x1402cb880  jb      short loc_1402CB898
0x1402cb882  mov     rcx, [rcx+18h]
0x1402cb886  lea     edx, [rax+50h]
0x1402cb889  mov     r9d, edi
0x1402cb88c  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cb893  call    WPP_SF_d
0x1402cb898  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cb89e  test    al, al
0x1402cb8a0  jz      short loc_1402CB8B8
0x1402cb8a2  mov     r9d, 168Ah; unsigned int
0x1402cb8a8  lea     r8, aMountC; "mount.c"
0x1402cb8af  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cb8b1  mov     ecx, edi; Status
0x1402cb8b3  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cb8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cb8bf  cmp     rcx, rbx
0x1402cb8c2  jz      loc_1402CBB91
0x1402cb8c8  mov     eax, [rcx+2Ch]
0x1402cb8cb  test    al, 4
0x1402cb8cd  jz      loc_1402CBB91
0x1402cb8d3  cmp     byte ptr [rcx+29h], 2
0x1402cb8d7  jb      loc_1402CBB91
0x1402cb8dd  mov     rcx, [rcx+18h]
0x1402cb8e1  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cb8e8  mov     edx, 51h ; 'Q'
0x1402cb8ed  call    WPP_SF_
0x1402cb8f2  jmp     loc_1402CBB91
0x1402cb8f7  lea     rax, [rsp+140h+var_D8]
0x1402cb8fc  mov     [rsp+140h+Disposition], 0; Disposition
0x1402cb905  mov     [rsp+140h+CreateOptions], 0; CreateOptions
0x1402cb90d  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1402cb911  xor     r9d, r9d; TitleIndex
0x1402cb914  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x1402cb918  mov     edx, 2001Fh; DesiredAccess
0x1402cb91d  mov     [rsp+140h+Class], 0; Class
0x1402cb926  lea     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x1402cb92b  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1402cb932  mov     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x1402cb93a  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x1402cb941  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402cb946  call    cs:__imp_ZwCreateKey
0x1402cb94d  nop     dword ptr [rax+rax+00h]
0x1402cb952  mov     edi, eax
0x1402cb954  test    eax, eax
0x1402cb956  jns     short loc_1402CB9AD
0x1402cb958  mov     r10, cs:WPP_GLOBAL_Control
0x1402cb95f  lea     rbx, WPP_GLOBAL_Control
0x1402cb966  cmp     r10, rbx
0x1402cb969  jz      short loc_1402CB994
0x1402cb96b  test    dword ptr [r10+2Ch], 100h
0x1402cb973  jz      short loc_1402CB994
0x1402cb975  cmp     byte ptr [r10+29h], 4
0x1402cb97a  jb      short loc_1402CB994
0x1402cb97c  mov     rcx, [r10+18h]
0x1402cb980  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cb987  mov     edx, 52h ; 'R'
0x1402cb98c  mov     r9d, eax
0x1402cb98f  call    WPP_SF_d
0x1402cb994  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cb99a  test    al, al
0x1402cb99c  jz      loc_1402CBB91
0x1402cb9a2  mov     r9d, 16A4h
0x1402cb9a8  jmp     loc_1402CBB81
0x1402cb9ad  xor     r8d, r8d
0x1402cb9b0  lea     rdx, [rsp+140h+var_E8]
0x1402cb9b5  mov     rcx, rbx
0x1402cb9b8  call    cs:__imp_RtlStringFromGUIDEx
0x1402cb9bf  nop     dword ptr [rax+rax+00h]
0x1402cb9c4  mov     rax, [rsp+140h+KeyHandle]
0x1402cb9c9  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1402cb9cd  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x1402cb9d1  lea     rcx, [rsp+140h+Handle]; KeyHandle
0x1402cb9d6  lea     rax, [rsp+140h+var_E8]
0x1402cb9db  mov     [rsp+140h+Disposition], 0; Disposition
0x1402cb9e4  xorps   xmm0, xmm0
0x1402cb9e7  mov     [rsp+140h+CreateOptions], 0; CreateOptions
0x1402cb9ef  xor     r9d, r9d; TitleIndex
0x1402cb9f2  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x1402cb9f6  mov     edx, 2001Fh; DesiredAccess
0x1402cb9fb  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1402cba02  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x1402cba09  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402cba0e  mov     [rsp+140h+Class], 0; Class
0x1402cba17  call    cs:__imp_ZwCreateKey
0x1402cba1e  nop     dword ptr [rax+rax+00h]
0x1402cba23  mov     edi, eax
0x1402cba25  test    eax, eax
0x1402cba27  jns     short loc_1402CBA7C
0x1402cba29  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cba30  lea     rbx, WPP_GLOBAL_Control
0x1402cba37  cmp     rcx, rbx
0x1402cba3a  jz      short loc_1402CBA63
0x1402cba3c  test    dword ptr [rcx+2Ch], 100h
0x1402cba43  jz      short loc_1402CBA63
0x1402cba45  cmp     byte ptr [rcx+29h], 4
0x1402cba49  jb      short loc_1402CBA63
0x1402cba4b  mov     rcx, [rcx+18h]
0x1402cba4f  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cba56  mov     edx, 53h ; 'S'
0x1402cba5b  mov     r9d, eax
0x1402cba5e  call    WPP_SF_d
0x1402cba63  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cba69  test    al, al
0x1402cba6b  jz      loc_1402CBB91
0x1402cba71  mov     r9d, 16BEh
0x1402cba77  jmp     loc_1402CBB81
0x1402cba7c  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x1402cba81  lea     rdx, [rsp+140h+ValueName]; ValueName
0x1402cba86  mov     [rsp+140h+CreateOptions], 10h; DataSize
0x1402cba8e  mov     r9d, 3; Type
0x1402cba94  xor     r8d, r8d; TitleIndex
0x1402cba97  mov     [rsp+140h+Class], rsi; Data
0x1402cba9c  call    cs:__imp_ZwSetValueKey
0x1402cbaa3  nop     dword ptr [rax+rax+00h]
0x1402cbaa8  mov     edi, eax
0x1402cbaaa  test    eax, eax
0x1402cbaac  jns     short loc_1402CBB01
0x1402cbaae  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cbab5  lea     rbx, WPP_GLOBAL_Control
0x1402cbabc  cmp     rcx, rbx
0x1402cbabf  jz      short loc_1402CBAE8
0x1402cbac1  test    dword ptr [rcx+2Ch], 100h
0x1402cbac8  jz      short loc_1402CBAE8
0x1402cbaca  cmp     byte ptr [rcx+29h], 4
0x1402cbace  jb      short loc_1402CBAE8
0x1402cbad0  mov     rcx, [rcx+18h]
0x1402cbad4  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cbadb  mov     edx, 54h ; 'T'
0x1402cbae0  mov     r9d, eax
0x1402cbae3  call    WPP_SF_d
0x1402cbae8  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cbaee  test    al, al
0x1402cbaf0  jz      loc_1402CBB91
0x1402cbaf6  mov     r9d, 16CFh
0x1402cbafc  jmp     loc_1402CBB81
0x1402cbb01  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x1402cbb06  lea     rax, [rsp+140h+Data]
0x1402cbb0b  mov     [rsp+140h+CreateOptions], 4; DataSize
0x1402cbb13  lea     rdx, [rbp+40h+var_B8]; ValueName
0x1402cbb17  mov     r9d, 4; Type
0x1402cbb1d  mov     [rsp+140h+Class], rax; Data
0x1402cbb22  xor     r8d, r8d; TitleIndex
0x1402cbb25  call    cs:__imp_ZwSetValueKey
0x1402cbb2c  nop     dword ptr [rax+rax+00h]
0x1402cbb31  mov     edi, eax
0x1402cbb33  test    eax, eax
0x1402cbb35  jns     short loc_1402CBB91
0x1402cbb37  mov     rcx, cs:WPP_GLOBAL_Control
0x1402cbb3e  lea     rbx, WPP_GLOBAL_Control
0x1402cbb45  cmp     rcx, rbx
0x1402cbb48  jz      short loc_1402CBB71
0x1402cbb4a  test    dword ptr [rcx+2Ch], 100h
0x1402cbb51  jz      short loc_1402CBB71
0x1402cbb53  cmp     byte ptr [rcx+29h], 4
0x1402cbb57  jb      short loc_1402CBB71
0x1402cbb59  mov     rcx, [rcx+18h]
0x1402cbb5d  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x1402cbb64  mov     edx, 55h ; 'U'
0x1402cbb69  mov     r9d, eax
0x1402cbb6c  call    WPP_SF_d
0x1402cbb71  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402cbb77  test    al, al
0x1402cbb79  jz      short loc_1402CBB91
0x1402cbb7b  mov     r9d, 16DCh; unsigned int
0x1402cbb81  lea     r8, aMountC; "mount.c"
0x1402cbb88  xor     edx, edx; struct _IRP_CONTEXT *
0x1402cbb8a  mov     ecx, edi; Status
0x1402cbb8c  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402cbb91  mov     rcx, [rsp+140h+Handle]; Handle
0x1402cbb96  test    rcx, rcx
0x1402cbb99  jz      short loc_1402CBBA7
0x1402cbb9b  call    cs:__imp_ZwClose
0x1402cbba2  nop     dword ptr [rax+rax+00h]
0x1402cbba7  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x1402cbbac  test    rcx, rcx
0x1402cbbaf  jz      short loc_1402CBBBD
0x1402cbbb1  call    cs:__imp_ZwClose
0x1402cbbb8  nop     dword ptr [rax+rax+00h]
0x1402cbbbd  mov     rcx, [rbp+40h+var_20]
0x1402cbbc1  xor     rcx, rsp; StackCookie
0x1402cbbc4  call    __security_check_cookie
0x1402cbbc9  mov     rbx, [rsp+140h+arg_10]
0x1402cbbd1  add     rsp, 130h
0x1402cbbd8  pop     rdi
0x1402cbbd9  pop     rsi
0x1402cbbda  pop     rbp
0x1402cbbdb  retn
```
