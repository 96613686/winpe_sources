# RefsTrustVolume(_GUID &,_GUID &)

- ea: `0x1402c6774`
- end: `0x1402c6bb5`
- name: `?RefsTrustVolume@@YAXAEAU_GUID@@0@Z`
- size: `1089`
- prototype: `void(struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402c6004`

## callees

- `0x14008dbd0`
- `0x1400ca788`
- `0x1400e1534`
- `0x1401e9ce0`
- `0x1402c6774`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1402c6a74`
- `ntoskrnl!ZwSetValueKey` at `0x1402c6afd`
- `ntoskrnl!ZwSetValueKey` at `0x1402c6a74`
- `ntoskrnl!ZwSetValueKey` at `0x1402c6afd`
- `ntoskrnl!ZwClose` at `0x1402c6b73`
- `ntoskrnl!ZwClose` at `0x1402c6b89`
- `ntoskrnl!ZwClose` at `0x1402c6b73`
- `ntoskrnl!ZwClose` at `0x1402c6b89`
- `ntoskrnl!ZwCreateKey` at `0x1402c691e`
- `ntoskrnl!ZwCreateKey` at `0x1402c69ef`
- `ntoskrnl!ZwCreateKey` at `0x1402c691e`
- `ntoskrnl!ZwCreateKey` at `0x1402c69ef`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x1402c6990`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x1402c6990`

## string_xrefs

- `0x1402c6880`: `mount.c`
- `0x1402c6b59`: `mount.c`
- `0x1402c67a2`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystemVolumes`

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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids, 3221226694LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073740602, 0, "mount.c", 0x1849u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids);
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
              97,
              WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
              (unsigned int)v11);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
          {
            v8 = 6299;
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
            96,
            WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
            (unsigned int)v10);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v8 = 6286;
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
          95,
          WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
          (unsigned int)v9);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v8 = 6269;
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
        94,
        WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
        (unsigned int)v6);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v8 = 6243;
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
0x1402c6774  mov     [rsp-8+arg_10], rbx
0x1402c6779  push    rbp
0x1402c677a  push    rsi
0x1402c677b  push    rdi
0x1402c677c  lea     rbp, [rsp-30h]
0x1402c6781  sub     rsp, 130h
0x1402c6788  mov     rax, cs:__security_cookie
0x1402c678f  xor     rax, rsp
0x1402c6792  mov     [rbp+40h+var_20], rax
0x1402c6796  xorps   xmm0, xmm0
0x1402c6799  mov     [rsp+140h+KeyHandle], 0
0x1402c67a2  lea     rax, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402c67a9  mov     [rsp+140h+Handle], 0
0x1402c67b2  mov     [rsp+140h+var_D0], rax
0x1402c67b7  mov     rsi, rdx
0x1402c67ba  lea     rax, [rbp+40h+var_70]
0x1402c67be  mov     [rsp+140h+var_D8], 8A0088h
0x1402c67c7  mov     [rsp+140h+var_E0], rax
0x1402c67cc  mov     rbx, rcx
0x1402c67cf  lea     rax, aFsguid; "FsGuid"
0x1402c67d6  mov     [rsp+140h+var_E8], 4E0000h
0x1402c67df  mov     [rbp+40h+ValueName.Buffer], rax
0x1402c67e3  lea     rax, aFsflags; "FsFlags"
0x1402c67ea  mov     [rbp+40h+var_B8.Buffer], rax
0x1402c67ee  mov     rax, [rcx]
0x1402c67f1  sub     rax, qword ptr cs:?ZeroGuid@?1??IsGuidZero@@YA_NAEBU_GUID@@@Z@4U2@B.Data1; _GUID const `IsGuidZero(_GUID const &)'::`2'::ZeroGuid ...
0x1402c67f8  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1402c67fc  mov     qword ptr [rsp+140h+ValueName.Length], 0E000Ch
0x1402c6805  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1402c6809  mov     qword ptr [rbp+40h+var_B8.Length], 10000Eh
0x1402c6811  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c6815  mov     [rsp+140h+Data], 1
0x1402c681d  jnz     short loc_1402C682A
0x1402c681f  mov     rax, [rcx+8]
0x1402c6823  sub     rax, qword ptr cs:?ZeroGuid@?1??IsGuidZero@@YA_NAEBU_GUID@@@Z@4U2@B.Data4; _GUID const `IsGuidZero(_GUID const &)'::`2'::ZeroGuid ...
0x1402c682a  test    rax, rax
0x1402c682d  jnz     loc_1402C68CF
0x1402c6833  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c683a  lea     rbx, WPP_GLOBAL_Control
0x1402c6841  mov     edi, 0C00004C6h
0x1402c6846  cmp     rcx, rbx
0x1402c6849  jz      short loc_1402C6870
0x1402c684b  test    dword ptr [rcx+2Ch], 100h
0x1402c6852  jz      short loc_1402C6870
0x1402c6854  cmp     byte ptr [rcx+29h], 4
0x1402c6858  jb      short loc_1402C6870
0x1402c685a  mov     rcx, [rcx+18h]
0x1402c685e  lea     edx, [rax+5Ch]
0x1402c6861  mov     r9d, edi
0x1402c6864  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x1402c686b  call    WPP_SF_d
0x1402c6870  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c6876  test    al, al
0x1402c6878  jz      short loc_1402C6890
0x1402c687a  mov     r9d, 1849h; unsigned int
0x1402c6880  lea     r8, aMountC; "mount.c"
0x1402c6887  xor     edx, edx; struct _IRP_CONTEXT *
0x1402c6889  mov     ecx, edi; Status
0x1402c688b  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402c6890  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c6897  cmp     rcx, rbx
0x1402c689a  jz      loc_1402C6B69
0x1402c68a0  mov     eax, [rcx+2Ch]
0x1402c68a3  test    al, 4
0x1402c68a5  jz      loc_1402C6B69
0x1402c68ab  cmp     byte ptr [rcx+29h], 2
0x1402c68af  jb      loc_1402C6B69
0x1402c68b5  mov     rcx, [rcx+18h]
0x1402c68b9  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x1402c68c0  mov     edx, 5Dh ; ']'
0x1402c68c5  call    WPP_SF_
0x1402c68ca  jmp     loc_1402C6B69
0x1402c68cf  lea     rax, [rsp+140h+var_D8]
0x1402c68d4  mov     [rsp+140h+Disposition], 0; Disposition
0x1402c68dd  mov     [rsp+140h+CreateOptions], 0; CreateOptions
0x1402c68e5  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1402c68e9  xor     r9d, r9d; TitleIndex
0x1402c68ec  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x1402c68f0  mov     edx, 2001Fh; DesiredAccess
0x1402c68f5  mov     [rsp+140h+Class], 0; Class
0x1402c68fe  lea     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x1402c6903  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1402c690a  mov     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x1402c6912  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x1402c6919  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c691e  call    cs:__imp_ZwCreateKey
0x1402c6925  nop     dword ptr [rax+rax+00h]
0x1402c692a  mov     edi, eax
0x1402c692c  test    eax, eax
0x1402c692e  jns     short loc_1402C6985
0x1402c6930  mov     r10, cs:WPP_GLOBAL_Control
0x1402c6937  lea     rbx, WPP_GLOBAL_Control
0x1402c693e  cmp     r10, rbx
0x1402c6941  jz      short loc_1402C696C
0x1402c6943  test    dword ptr [r10+2Ch], 100h
0x1402c694b  jz      short loc_1402C696C
0x1402c694d  cmp     byte ptr [r10+29h], 4
0x1402c6952  jb      short loc_1402C696C
0x1402c6954  mov     rcx, [r10+18h]
0x1402c6958  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x1402c695f  mov     edx, 5Eh ; '^'
0x1402c6964  mov     r9d, eax
0x1402c6967  call    WPP_SF_d
0x1402c696c  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c6972  test    al, al
0x1402c6974  jz      loc_1402C6B69
0x1402c697a  mov     r9d, 1863h
0x1402c6980  jmp     loc_1402C6B59
0x1402c6985  xor     r8d, r8d
0x1402c6988  lea     rdx, [rsp+140h+var_E8]
0x1402c698d  mov     rcx, rbx
0x1402c6990  call    cs:__imp_RtlStringFromGUIDEx
0x1402c6997  nop     dword ptr [rax+rax+00h]
0x1402c699c  mov     rax, [rsp+140h+KeyHandle]
0x1402c69a1  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1402c69a5  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x1402c69a9  lea     rcx, [rsp+140h+Handle]; KeyHandle
0x1402c69ae  lea     rax, [rsp+140h+var_E8]
0x1402c69b3  mov     [rsp+140h+Disposition], 0; Disposition
0x1402c69bc  xorps   xmm0, xmm0
0x1402c69bf  mov     [rsp+140h+CreateOptions], 0; CreateOptions
0x1402c69c7  xor     r9d, r9d; TitleIndex
0x1402c69ca  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x1402c69ce  mov     edx, 2001Fh; DesiredAccess
0x1402c69d3  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1402c69da  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x1402c69e1  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c69e6  mov     [rsp+140h+Class], 0; Class
0x1402c69ef  call    cs:__imp_ZwCreateKey
0x1402c69f6  nop     dword ptr [rax+rax+00h]
0x1402c69fb  mov     edi, eax
0x1402c69fd  test    eax, eax
0x1402c69ff  jns     short loc_1402C6A54
0x1402c6a01  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c6a08  lea     rbx, WPP_GLOBAL_Control
0x1402c6a0f  cmp     rcx, rbx
0x1402c6a12  jz      short loc_1402C6A3B
0x1402c6a14  test    dword ptr [rcx+2Ch], 100h
0x1402c6a1b  jz      short loc_1402C6A3B
0x1402c6a1d  cmp     byte ptr [rcx+29h], 4
0x1402c6a21  jb      short loc_1402C6A3B
0x1402c6a23  mov     rcx, [rcx+18h]
0x1402c6a27  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x1402c6a2e  mov     edx, 5Fh ; '_'
0x1402c6a33  mov     r9d, eax
0x1402c6a36  call    WPP_SF_d
0x1402c6a3b  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c6a41  test    al, al
0x1402c6a43  jz      loc_1402C6B69
0x1402c6a49  mov     r9d, 187Dh
0x1402c6a4f  jmp     loc_1402C6B59
0x1402c6a54  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x1402c6a59  lea     rdx, [rsp+140h+ValueName]; ValueName
0x1402c6a5e  mov     [rsp+140h+CreateOptions], 10h; DataSize
0x1402c6a66  mov     r9d, 3; Type
0x1402c6a6c  xor     r8d, r8d; TitleIndex
0x1402c6a6f  mov     [rsp+140h+Class], rsi; Data
0x1402c6a74  call    cs:__imp_ZwSetValueKey
0x1402c6a7b  nop     dword ptr [rax+rax+00h]
0x1402c6a80  mov     edi, eax
0x1402c6a82  test    eax, eax
0x1402c6a84  jns     short loc_1402C6AD9
0x1402c6a86  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c6a8d  lea     rbx, WPP_GLOBAL_Control
0x1402c6a94  cmp     rcx, rbx
0x1402c6a97  jz      short loc_1402C6AC0
0x1402c6a99  test    dword ptr [rcx+2Ch], 100h
0x1402c6aa0  jz      short loc_1402C6AC0
0x1402c6aa2  cmp     byte ptr [rcx+29h], 4
0x1402c6aa6  jb      short loc_1402C6AC0
0x1402c6aa8  mov     rcx, [rcx+18h]
0x1402c6aac  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x1402c6ab3  mov     edx, 60h ; '`'
0x1402c6ab8  mov     r9d, eax
0x1402c6abb  call    WPP_SF_d
0x1402c6ac0  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c6ac6  test    al, al
0x1402c6ac8  jz      loc_1402C6B69
0x1402c6ace  mov     r9d, 188Eh
0x1402c6ad4  jmp     loc_1402C6B59
0x1402c6ad9  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x1402c6ade  lea     rax, [rsp+140h+Data]
0x1402c6ae3  mov     [rsp+140h+CreateOptions], 4; DataSize
0x1402c6aeb  lea     rdx, [rbp+40h+var_B8]; ValueName
0x1402c6aef  mov     r9d, 4; Type
0x1402c6af5  mov     [rsp+140h+Class], rax; Data
0x1402c6afa  xor     r8d, r8d; TitleIndex
0x1402c6afd  call    cs:__imp_ZwSetValueKey
0x1402c6b04  nop     dword ptr [rax+rax+00h]
0x1402c6b09  mov     edi, eax
0x1402c6b0b  test    eax, eax
0x1402c6b0d  jns     short loc_1402C6B69
0x1402c6b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c6b16  lea     rbx, WPP_GLOBAL_Control
0x1402c6b1d  cmp     rcx, rbx
0x1402c6b20  jz      short loc_1402C6B49
0x1402c6b22  test    dword ptr [rcx+2Ch], 100h
0x1402c6b29  jz      short loc_1402C6B49
0x1402c6b2b  cmp     byte ptr [rcx+29h], 4
0x1402c6b2f  jb      short loc_1402C6B49
0x1402c6b31  mov     rcx, [rcx+18h]
0x1402c6b35  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x1402c6b3c  mov     edx, 61h ; 'a'
0x1402c6b41  mov     r9d, eax
0x1402c6b44  call    WPP_SF_d
0x1402c6b49  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c6b4f  test    al, al
0x1402c6b51  jz      short loc_1402C6B69
0x1402c6b53  mov     r9d, 189Bh; unsigned int
0x1402c6b59  lea     r8, aMountC; "mount.c"
0x1402c6b60  xor     edx, edx; struct _IRP_CONTEXT *
0x1402c6b62  mov     ecx, edi; Status
0x1402c6b64  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402c6b69  mov     rcx, [rsp+140h+Handle]; Handle
0x1402c6b6e  test    rcx, rcx
0x1402c6b71  jz      short loc_1402C6B7F
0x1402c6b73  call    cs:__imp_ZwClose
0x1402c6b7a  nop     dword ptr [rax+rax+00h]
0x1402c6b7f  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x1402c6b84  test    rcx, rcx
0x1402c6b87  jz      short loc_1402C6B95
0x1402c6b89  call    cs:__imp_ZwClose
0x1402c6b90  nop     dword ptr [rax+rax+00h]
0x1402c6b95  mov     rcx, [rbp+40h+var_20]
0x1402c6b99  xor     rcx, rsp; StackCookie
0x1402c6b9c  call    __security_check_cookie
0x1402c6ba1  mov     rbx, [rsp+140h+arg_10]
0x1402c6ba9  add     rsp, 130h
0x1402c6bb0  pop     rdi
0x1402c6bb1  pop     rsi
0x1402c6bb2  pop     rbp
0x1402c6bb3  retn
```
