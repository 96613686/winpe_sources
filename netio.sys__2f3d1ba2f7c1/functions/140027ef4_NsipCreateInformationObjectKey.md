# NsipCreateInformationObjectKey

- ea: `0x140027ef4`
- end: `0x14002834f`
- name: `NsipCreateInformationObjectKey`
- size: `1115`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140026fac`
- `0x14005f520`

## callees

- `0x140027e70`
- `0x140027ef4`
- `0x140028588`
- `0x140050b00`
- `0x140050ea4`
- `0x14005fe0c`
- `0x14005fe98`
- `0x1400605c8`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14002805d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002805d`
- `ntoskrnl!RtlStringFromGUID` at `0x140027f90`
- `ntoskrnl!RtlStringFromGUID` at `0x140027f90`
- `ntoskrnl!ZwClose` at `0x14002833e`
- `ntoskrnl!ZwClose` at `0x14002833e`
- `ntoskrnl!ZwCreateKey` at `0x1400281c5`
- `ntoskrnl!ZwCreateKey` at `0x1400281c5`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140027fd0`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140027fd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028168`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028168`

## string_xrefs

- `0x140027fb3`: `\Registry\Machine\System\CurrentControlSet\Control\Nsi`

## pseudocode

```c
__int64 __fastcall NsipCreateInformationObjectKey(PHANDLE KeyHandle, unsigned int *a2, ACCESS_MASK a3)
{
  _BYTE *v6; // rcx
  __int64 v7; // r9
  NTSTATUS PersistedStateLocation; // ebx
  wchar_t *v9; // rsi
  int v10; // r8d
  int Key; // eax
  int v12; // r8d
  __int64 result; // rax
  int v14; // r8d
  PDEVICE_OBJECT v15; // rcx
  int v16; // edx
  PUNICODE_STRING Class; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandlea; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[24]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SourceString[256]; // [rsp+C0h] [rbp-40h] BYREF

  GuidString = 0;
  memset(SourceString, 0, sizeof(SourceString));
  KeyHandlea = 0;
  v18 = 0;
  memset(v21, 0, 22);
  if ( !*a2 && !*((_QWORD *)a2 + 1) )
    return 3221225485LL;
  v6 = (_BYTE *)*((_QWORD *)a2 + 1);
  if ( !v6 )
  {
    result = NsipFindModuleGuidByModuleId(*a2, v21);
    if ( (int)result < 0 )
      return result;
    v6 = v21;
  }
  v7 = *((unsigned int *)v6 + 1);
  if ( (_DWORD)v7 == 1 )
  {
    PersistedStateLocation = RtlStringFromGUID((const GUID *const)(v6 + 8), &GuidString);
    if ( PersistedStateLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids,
          (unsigned int)PersistedStateLocation);
      }
      return (unsigned int)PersistedStateLocation;
    }
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"NsiPersistentStore",
                               0,
                               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nsi",
                               0,
                               SourceString,
                               512,
                               &v18);
    if ( PersistedStateLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids,
          (unsigned int)PersistedStateLocation);
      }
      goto LABEL_9;
    }
    v9 = &SourceString[((unsigned __int64)v18 >> 1) - 1];
    LODWORD(Class) = a2[4];
    if ( StringCbPrintfW(v9, 512LL - v18, L"\\%ls\\%u", GuidString.Buffer, Class) < 0 )
    {
      PersistedStateLocation = -1073741789;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_SDD(WPP_GLOBAL_Control->AttachedDevice, 13, v10, GuidString.Buffer, a2[4]);
      }
      goto LABEL_9;
    }
    Key = NsipCreateKey(KeyHandle, a3);
    PersistedStateLocation = Key;
    if ( Key == -1073741772 )
    {
      if ( StringCbPrintfW(v9, 512LL - v18, L"\\%ls", GuidString.Buffer) < 0 )
      {
        PersistedStateLocation = -1073741789;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_SD(WPP_GLOBAL_Control->AttachedDevice, 15, v14, GuidString.Buffer, 35);
        }
        goto LABEL_9;
      }
      DestinationString = 0;
      memset(&ObjectAttributes, 0, 44);
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 1728;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      PersistedStateLocation = ZwCreateKey(&KeyHandlea, a3, &ObjectAttributes, 0, 0, 0, 0);
      if ( PersistedStateLocation >= 0 )
      {
        if ( StringCbPrintfW(SourceString, 0x200u, L"%u", a2[4]) < 0 )
        {
          PersistedStateLocation = -1073741789;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids);
          }
          goto LABEL_9;
        }
        PersistedStateLocation = NsipCreateKey(KeyHandle, a3);
        if ( PersistedStateLocation < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            v16 = 18;
            goto LABEL_59;
          }
        }
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          v16 = 16;
LABEL_59:
          WPP_SF_SD(v15->AttachedDevice, v16, v12, (unsigned int)SourceString, PersistedStateLocation);
        }
      }
    }
    else if ( Key < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        v16 = 14;
        goto LABEL_59;
      }
    }
LABEL_9:
    if ( KeyHandlea )
      ZwClose(KeyHandlea);
    RtlFreeUnicodeString(&GuidString);
    return (unsigned int)PersistedStateLocation;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids, v7);
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x140027ef4  push    rbp
0x140027ef6  push    rbx
0x140027ef7  push    rsi
0x140027ef8  push    rdi
0x140027ef9  push    r12
0x140027efb  push    r14
0x140027efd  push    r15
0x140027eff  lea     rbp, [rsp-1D0h]
0x140027f07  sub     rsp, 2D0h
0x140027f0e  mov     rax, cs:__security_cookie
0x140027f15  xor     rax, rsp
0x140027f18  mov     [rbp+200h+var_40], rax
0x140027f1f  mov     r14d, r8d
0x140027f22  mov     rdi, rdx
0x140027f25  mov     r15, rcx
0x140027f28  xorps   xmm0, xmm0
0x140027f2b  mov     esi, 200h
0x140027f30  lea     rcx, [rbp+200h+SourceString]; void *
0x140027f34  mov     r8d, esi; Size
0x140027f37  xor     edx, edx; Val
0x140027f39  mov     r12, r9
0x140027f3c  movups  xmmword ptr [rsp+300h+GuidString.Length], xmm0
0x140027f41  call    memset
0x140027f46  xor     eax, eax
0x140027f48  mov     [rsp+300h+KeyHandle], 0
0x140027f51  xorps   xmm0, xmm0
0x140027f54  mov     [rsp+300h+var_2C0], eax
0x140027f58  movups  xmmword ptr [rsp+300h+var_2A0], xmm0
0x140027f5d  mov     qword ptr [rsp+300h+var_2A0+0Eh], rax
0x140027f62  mov     eax, [rdi]
0x140027f64  test    eax, eax
0x140027f66  jz      loc_14002808D
0x140027f6c  mov     rcx, [rdi+8]
0x140027f70  test    rcx, rcx
0x140027f73  jz      loc_14002827E
0x140027f79  mov     r9d, [rcx+4]
0x140027f7d  cmp     r9d, 1
0x140027f81  jnz     loc_140028261
0x140027f87  add     rcx, 8; Guid
0x140027f8b  lea     rdx, [rsp+300h+GuidString]; GuidString
0x140027f90  call    cs:__imp_RtlStringFromGUID
0x140027f97  nop     dword ptr [rax+rax+00h]
0x140027f9c  mov     ebx, eax
0x140027f9e  test    eax, eax
0x140027fa0  js      loc_14002809F
0x140027fa6  lea     rax, [rsp+300h+var_2C0]
0x140027fab  xor     r9d, r9d
0x140027fae  mov     [rsp+300h+Disposition], rax
0x140027fb3  lea     r8, NsiDefaultPersistentStoreRootKey
0x140027fba  lea     rax, [rbp+200h+SourceString]
0x140027fbe  mov     [rsp+300h+CreateOptions], esi
0x140027fc2  xor     edx, edx
0x140027fc4  mov     [rsp+300h+Class], rax
0x140027fc9  lea     rcx, aNsipersistents
0x140027fd0  call    cs:__imp_RtlGetPersistedStateLocation
0x140027fd7  nop     dword ptr [rax+rax+00h]
0x140027fdc  mov     ebx, eax
0x140027fde  test    eax, eax
0x140027fe0  js      loc_1400280D9
0x140027fe6  mov     ecx, [rsp+300h+var_2C0]
0x140027fea  lea     r8, aLsU
0x140027ff1  mov     r9, [rsp+300h+GuidString.Buffer]
0x140027ff6  mov     eax, ecx
0x140027ff8  shr     rax, 1
0x140027ffb  mov     edx, 200h
0x140028000  sub     rdx, rcx; cbDest
0x140028003  lea     rsi, [rbp+rax*2+200h+pszDest]
0x140028008  mov     eax, [rdi+10h]
0x14002800b  mov     rcx, rsi; pszDest
0x14002800e  mov     dword ptr [rsp+300h+Class], eax
0x140028012  call    StringCbPrintfW
0x140028017  test    eax, eax
0x140028019  js      loc_140028211
0x14002801f  mov     r9, r12
0x140028022  mov     dword ptr [rsp+300h+Class], r14d; DesiredAccess
0x140028027  lea     r8, [rbp+200h+SourceString]
0x14002802b  xor     edx, edx
0x14002802d  mov     rcx, r15; KeyHandle
0x140028030  call    NsipCreateKey
0x140028035  mov     ebx, eax
0x140028037  cmp     eax, 0C0000034h
0x14002803c  jz      loc_140028122
0x140028042  test    eax, eax
0x140028044  js      loc_1400282C0
0x14002804a  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x14002804f  test    rcx, rcx
0x140028052  jnz     loc_14002833E
0x140028058  lea     rcx, [rsp+300h+GuidString]; UnicodeString
0x14002805d  call    cs:__imp_RtlFreeUnicodeString
0x140028064  nop     dword ptr [rax+rax+00h]
0x140028069  mov     eax, ebx
0x14002806b  mov     rcx, [rbp+200h+var_40]
0x140028072  xor     rcx, rsp; StackCookie
0x140028075  call    __security_check_cookie
0x14002807a  add     rsp, 2D0h
0x140028081  pop     r15
0x140028083  pop     r14
0x140028085  pop     r12
0x140028087  pop     rdi
0x140028088  pop     rsi
0x140028089  pop     rbx
0x14002808a  pop     rbp
0x14002808b  retn
0x14002808d  cmp     qword ptr [rdi+8], 0
0x140028092  jnz     loc_140027F6C
0x140028098  mov     eax, 0C000000Dh
0x14002809d  jmp     short loc_14002806B
0x14002809f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400280a6  lea     rax, WPP_GLOBAL_Control
0x1400280ad  cmp     rcx, rax
0x1400280b0  jz      short loc_140028069
0x1400280b2  cmp     byte ptr [rcx+29h], 2
0x1400280b6  jb      short loc_140028069
0x1400280b8  mov     eax, [rcx+2Ch]
0x1400280bb  test    al, 10h
0x1400280bd  jz      short loc_140028069
0x1400280bf  mov     rcx, [rcx+18h]
0x1400280c3  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x1400280ca  mov     edx, 0Bh
0x1400280cf  mov     r9d, ebx
0x1400280d2  call    WPP_SF_d
0x1400280d7  jmp     short loc_140028069
0x1400280d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400280e0  lea     rax, WPP_GLOBAL_Control
0x1400280e7  cmp     rcx, rax
0x1400280ea  jz      loc_14002804A
0x1400280f0  cmp     byte ptr [rcx+29h], 2
0x1400280f4  jb      loc_14002804A
0x1400280fa  mov     eax, [rcx+2Ch]
0x1400280fd  test    al, 10h
0x1400280ff  jz      loc_14002804A
0x140028105  mov     rcx, [rcx+18h]
0x140028109  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x140028110  mov     edx, 0Ch
0x140028115  mov     r9d, ebx
0x140028118  call    WPP_SF_d
0x14002811d  jmp     loc_14002804A
0x140028122  mov     eax, [rsp+300h+var_2C0]
0x140028126  lea     r8, aLs
0x14002812d  mov     r9, [rsp+300h+GuidString.Buffer]
0x140028132  mov     edx, 200h
0x140028137  sub     rdx, rax; cbDest
0x14002813a  mov     rcx, rsi; pszDest
0x14002813d  call    StringCbPrintfW
0x140028142  test    eax, eax
0x140028144  js      loc_1400282F6
0x14002814a  xorps   xmm0, xmm0
0x14002814d  lea     rdx, [rbp+200h+SourceString]; SourceString
0x140028151  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x140028155  xor     eax, eax
0x140028157  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x14002815b  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x14002815f  movups  xmmword ptr [rbp+200h+DestinationString.Length], xmm0
0x140028163  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm0
0x140028168  call    cs:__imp_RtlInitUnicodeString
0x14002816f  nop     dword ptr [rax+rax+00h]
0x140028174  lea     rax, [rbp+200h+DestinationString]
0x140028178  mov     [rsp+300h+Disposition], 0; Disposition
0x140028181  xorps   xmm0, xmm0
0x140028184  mov     [rsp+300h+CreateOptions], 0; CreateOptions
0x14002818c  xor     r9d, r9d; TitleIndex
0x14002818f  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x140028193  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x140028198  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x1400281a0  mov     edx, r14d; DesiredAccess
0x1400281a3  mov     [rbp+200h+ObjectAttributes.RootDirectory], 0
0x1400281ab  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400281b0  mov     [rbp+200h+ObjectAttributes.Attributes], 6C0h
0x1400281b7  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400281bc  mov     [rsp+300h+Class], 0; Class
0x1400281c5  call    cs:__imp_ZwCreateKey
0x1400281cc  nop     dword ptr [rax+rax+00h]
0x1400281d1  mov     ebx, eax
0x1400281d3  test    eax, eax
0x1400281d5  jns     loc_14007B5C0
0x1400281db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400281e2  lea     rax, WPP_GLOBAL_Control
0x1400281e9  cmp     rcx, rax
0x1400281ec  jz      loc_14002804A
0x1400281f2  cmp     byte ptr [rcx+29h], 3
0x1400281f6  jb      loc_14002804A
0x1400281fc  mov     eax, [rcx+2Ch]
0x1400281ff  test    al, 10h
0x140028201  jz      loc_14002804A
0x140028207  mov     edx, 10h
0x14002820c  jmp     loc_14007B689
0x140028211  mov     ebx, 0C0000023h
0x140028216  mov     rcx, cs:WPP_GLOBAL_Control
0x14002821d  lea     rax, WPP_GLOBAL_Control
0x140028224  cmp     rcx, rax
0x140028227  jz      loc_14002804A
0x14002822d  cmp     byte ptr [rcx+29h], 2
0x140028231  jb      loc_14002804A
0x140028237  mov     eax, [rcx+2Ch]
0x14002823a  test    al, 10h
0x14002823c  jz      loc_14002804A
0x140028242  mov     eax, [rdi+10h]
0x140028245  mov     edx, 0Dh
0x14002824a  mov     r9, [rsp+300h+GuidString.Buffer]
0x14002824f  mov     rcx, [rcx+18h]
0x140028253  mov     dword ptr [rsp+300h+Class], eax
0x140028257  call    WPP_SF_SDD
0x14002825c  jmp     loc_14002804A
0x140028261  mov     rcx, cs:WPP_GLOBAL_Control
0x140028268  lea     rax, WPP_GLOBAL_Control
0x14002826f  cmp     rcx, rax
0x140028272  jnz     short loc_14002829C
0x140028274  mov     eax, 0C00000BBh
0x140028279  jmp     loc_14002806B
0x14002827e  lea     rdx, [rsp+300h+var_2A0]
0x140028283  mov     ecx, eax
0x140028285  call    NsipFindModuleGuidByModuleId
0x14002828a  test    eax, eax
0x14002828c  js      loc_14002806B
0x140028292  lea     rcx, [rsp+300h+var_2A0]
0x140028297  jmp     loc_140027F79
0x14002829c  cmp     byte ptr [rcx+29h], 2
0x1400282a0  jb      short loc_140028274
0x1400282a2  mov     eax, [rcx+2Ch]
0x1400282a5  test    al, 10h
0x1400282a7  jz      short loc_140028274
0x1400282a9  mov     rcx, [rcx+18h]
0x1400282ad  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x1400282b4  mov     edx, 0Ah
0x1400282b9  call    WPP_SF_d
0x1400282be  jmp     short loc_140028274
0x1400282c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400282c7  lea     rax, WPP_GLOBAL_Control
0x1400282ce  cmp     rcx, rax
0x1400282d1  jz      loc_14002804A
0x1400282d7  cmp     byte ptr [rcx+29h], 3
0x1400282db  jb      loc_14002804A
0x1400282e1  mov     eax, [rcx+2Ch]
0x1400282e4  test    al, 10h
0x1400282e6  jz      loc_14002804A
0x1400282ec  mov     edx, 0Eh
0x1400282f1  jmp     loc_14007B689
0x1400282f6  mov     ebx, 0C0000023h
0x1400282fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140028302  lea     rax, WPP_GLOBAL_Control
0x140028309  cmp     rcx, rax
0x14002830c  jz      loc_14002804A
0x140028312  cmp     byte ptr [rcx+29h], 2
0x140028316  jb      loc_14002804A
0x14002831c  mov     eax, [rcx+2Ch]
0x14002831f  test    al, 10h
0x140028321  jz      loc_14002804A
0x140028327  mov     r9, [rsp+300h+GuidString.Buffer]
0x14002832c  mov     edx, 0Fh
0x140028331  mov     dword ptr [rsp+300h+Class], 0C0000023h
0x140028339  jmp     loc_14007B691
0x14002833e  call    cs:__imp_ZwClose
0x140028345  nop     dword ptr [rax+rax+00h]
0x14002834a  jmp     loc_140028058
0x14007b5c0  mov     r9d, [rdi+10h]
0x14007b5c4  lea     r8, aU
0x14007b5cb  mov     edx, 200h; cbDest
0x14007b5d0  lea     rcx, [rbp+200h+SourceString]; pszDest
0x14007b5d4  call    StringCbPrintfW
0x14007b5d9  test    eax, eax
0x14007b5db  jns     short loc_14007B635
0x14007b5dd  mov     ebx, 0C0000023h
0x14007b5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b5e9  lea     rax, WPP_GLOBAL_Control
0x14007b5f0  cmp     rcx, rax
0x14007b5f3  jz      loc_14002804A
0x14007b5f9  cmp     byte ptr [rcx+29h], 2
0x14007b5fd  jb      loc_14002804A
0x14007b603  mov     eax, [rcx+2Ch]
0x14007b606  test    al, 10h
0x14007b608  jz      loc_14002804A
0x14007b60e  mov     r9d, [rdi+10h]
0x14007b612  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x14007b619  mov     rcx, [rcx+18h]
0x14007b61d  mov     edx, 11h
0x14007b622  mov     dword ptr [rsp+300h+Class], 0C0000023h
0x14007b62a  call    WPP_SF_Dd
0x14007b62f  nop
0x14007b630  jmp     loc_14002804A
0x14007b635  mov     rdx, [rsp+300h+KeyHandle]
0x14007b63a  lea     r8, [rbp+200h+SourceString]
0x14007b63e  mov     r9, r12
0x14007b641  mov     dword ptr [rsp+300h+Class], r14d; DesiredAccess
0x14007b646  mov     rcx, r15; KeyHandle
0x14007b649  call    NsipCreateKey
0x14007b64e  mov     ebx, eax
0x14007b650  test    eax, eax
0x14007b652  jns     loc_14002804A
0x14007b658  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b65f  lea     rax, WPP_GLOBAL_Control
0x14007b666  cmp     rcx, rax
0x14007b669  jz      loc_14002804A
0x14007b66f  cmp     byte ptr [rcx+29h], 2
0x14007b673  jb      loc_14002804A
0x14007b679  mov     eax, [rcx+2Ch]
0x14007b67c  test    al, 10h
0x14007b67e  jz      loc_14002804A
0x14007b684  mov     edx, 12h
0x14007b689  lea     r9, [rbp+200h+SourceString]
0x14007b68d  mov     dword ptr [rsp+300h+Class], ebx
  ... truncated ...
```
