# BiLoadHive

- ea: `0x1800334d4`
- end: `0x18003390e`
- name: `BiLoadHive`
- size: `1082`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d9b0`

## callees

- `0x180002690`
- `0x1800334d4`
- `0x180033b40`
- `0x180034254`
- `0x180034db0`
- `0x1800350ac`
- `0x1800352f8`
- `0x180049010`

## import_xrefs

- `ntdll!ZwUnloadKey` at `0x180033847`
- `ntdll!ZwUnloadKey` at `0x180033847`
- `ntdll!ZwLoadKey` at `0x1800337bf`
- `ntdll!ZwLoadKey` at `0x1800337bf`
- `ntdll!ZwClose` at `0x18003388c`
- `ntdll!ZwClose` at `0x18003388c`
- `ntdll!ZwQueryAttributesFile` at `0x180033611`
- `ntdll!ZwQueryAttributesFile` at `0x180033611`
- `ntdll!RtlInitUnicodeString` at `0x1800335bb`
- `ntdll!RtlInitUnicodeString` at `0x180033684`
- `ntdll!RtlInitUnicodeString` at `0x1800336cb`
- `ntdll!RtlInitUnicodeString` at `0x1800335bb`
- `ntdll!RtlInitUnicodeString` at `0x180033684`
- `ntdll!RtlInitUnicodeString` at `0x1800336cb`
- `ntdll!ZwOpenKey` at `0x18003381d`
- `ntdll!ZwOpenKey` at `0x18003381d`

## string_xrefs

- `0x18003363e`: `\Registry\Machine`
- `0x180033659`: `\Registry\Machine`
- `0x180033731`: `\Registry\Machine`
- `0x180033660`: `Failed open key %ws. Status: %x`
- `0x18003386a`: `Failed open newly loaded key %ws. Flags: 0x%x Status: %x`

## pseudocode

```c
__int64 __fastcall BiLoadHive(PCWSTR SourceString, __int64 a2, void **a3)
{
  unsigned int i; // esi
  HANDLE v5; // rdi
  const WCHAR *v6; // r13
  int v7; // eax
  int v8; // ebx
  NTSTATUS v9; // eax
  __int64 v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-168h]
  __int64 v13; // [rsp+28h] [rbp-160h]
  __int64 v14; // [rsp+30h] [rbp-158h]
  HANDLE Handle; // [rsp+38h] [rbp-150h] BYREF
  __int64 v16; // [rsp+40h] [rbp-148h] BYREF
  __int64 v17; // [rsp+48h] [rbp-140h]
  PHANDLE KeyHandle; // [rsp+50h] [rbp-138h]
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+58h] [rbp-130h] BYREF
  PCWSTR v20; // [rsp+88h] [rbp-100h]
  __int64 v21; // [rsp+90h] [rbp-F8h]
  void **v22; // [rsp+98h] [rbp-F0h]
  struct _OBJECT_ATTRIBUTES FileObjectAttributes; // [rsp+A0h] [rbp-E8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp-88h] BYREF
  struct _UNICODE_STRING v26; // [rsp+110h] [rbp-78h] BYREF
  struct _UNICODE_STRING v27; // [rsp+120h] [rbp-68h] BYREF
  struct _FILE_BASIC_INFORMATION FileInformation; // [rsp+130h] [rbp-58h] BYREF

  KeyHandle = a3;
  v17 = a2;
  v20 = SourceString;
  v21 = a2;
  v22 = a3;
  memset(&FileObjectAttributes, 0, 44);
  memset(&KeyObjectAttributes, 0, 44);
  v16 = 0;
  v27 = 0;
  v26 = 0;
  for ( i = 0; ; ++i )
  {
    v5 = 0;
    Handle = 0;
    memset(&ObjectAttributes, 0, 44);
    memset(&FileInformation, 0, sizeof(FileInformation));
    DestinationString = 0;
    v6 = (const WCHAR *)(a2 + 12);
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(a2 + 12));
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwQueryAttributesFile(&ObjectAttributes, &FileInformation) < 0 || (FileInformation.FileAttributes & 0x10) != 0 )
    {
      v8 = -1073741809;
    }
    else
    {
      v7 = BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 983103, &Handle);
      v8 = v7;
      if ( v7 >= 0 )
      {
        RtlInitUnicodeString(&v26, SourceString);
        KeyObjectAttributes.Length = 48;
        v5 = Handle;
        KeyObjectAttributes.RootDirectory = Handle;
        KeyObjectAttributes.Attributes = 64;
        KeyObjectAttributes.ObjectName = &v26;
        *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
        RtlInitUnicodeString(&v27, v6);
        FileObjectAttributes.Length = 48;
        FileObjectAttributes.RootDirectory = 0;
        FileObjectAttributes.Attributes = 64;
        FileObjectAttributes.ObjectName = &v27;
        *(_OWORD *)&FileObjectAttributes.SecurityDescriptor = 0;
        v9 = BiAcquirePrivilege(0x12u, (__int64)&v16);
        v8 = v9;
        if ( v9 >= 0 )
        {
          Handle = 0;
          v8 = BiLookupNtdllProcedureAddress("ZwLoadKey2", &Handle);
          if ( v8 >= 0 )
          {
            v8 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _OBJECT_ATTRIBUTES *, __int64))Handle)(
                   &KeyObjectAttributes,
                   &FileObjectAttributes,
                   6016);
            if ( v8 < 0 )
              v8 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _OBJECT_ATTRIBUTES *, __int64))Handle)(
                     &KeyObjectAttributes,
                     &FileObjectAttributes,
                     4992);
          }
          if ( v8 < 0 )
            v8 = ZwLoadKey(&KeyObjectAttributes, &FileObjectAttributes);
          BiReleasePrivilege(&v16);
          if ( v8 >= 0 )
          {
            v8 = ZwOpenKey(KeyHandle, 0x20019u, &KeyObjectAttributes);
            if ( v8 < 0 )
            {
              BiAcquirePrivilege(0x11u, (__int64)&v16);
              ZwUnloadKey(&KeyObjectAttributes);
              BiReleasePrivilege(&v16);
              LODWORD(v12) = v8;
              BiLogMessage(4, L"Failed open newly loaded key %ws. Flags: 0x%x Status: %x", SourceString, 64, v12);
            }
          }
          else
          {
            LODWORD(v14) = v8;
            v10 = 2;
            if ( v8 != -1073741790 )
              v10 = 4;
            LODWORD(v13) = v8;
            BiLogMessage(v10, L"Failed load key %ws. Flags: 0x%x File: %s Status: %x", SourceString, 64, v6, v13, v14);
          }
        }
        else
        {
          BiLogMessage(
            4,
            L"Failed to acquire permissions to load hive. Status: %x",
            L"\\Registry\\Machine",
            (unsigned int)v9);
        }
      }
      else
      {
        BiLogMessage(4, L"Failed open key %ws. Status: %x", L"\\Registry\\Machine", (unsigned int)v7);
        v5 = Handle;
      }
    }
    if ( v5 )
      ZwClose(v5);
    if ( v8 != -1073741443 )
      break;
    __debugbreak();
    a2 = v17;
    if ( i >= 5 )
      break;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800334d4  mov     r11, rsp
0x1800334d7  mov     [r11+20h], rbx
0x1800334db  push    rsi
0x1800334dc  push    rdi
0x1800334dd  push    r12
0x1800334df  push    r13
0x1800334e1  push    r14
0x1800334e3  sub     rsp, 160h
0x1800334ea  mov     rax, cs:__security_cookie
0x1800334f1  xor     rax, rsp
0x1800334f4  mov     [rsp+188h+var_30], rax
0x1800334fc  mov     rax, r8
0x1800334ff  mov     [rsp+188h+KeyHandle], rax
0x180033504  mov     [rsp+188h+var_140], rdx
0x180033509  mov     r12, rcx
0x18003350c  mov     [rsp+188h+var_100], rcx
0x180033514  mov     [rsp+188h+var_F8], rdx
0x18003351c  mov     [rsp+188h+var_F0], rax
0x180033524  xor     eax, eax
0x180033526  xorps   xmm0, xmm0
0x180033529  movups  xmmword ptr [rsp+188h+FileObjectAttributes.Length], xmm0
0x180033531  movups  xmmword ptr [rsp+188h+FileObjectAttributes.ObjectName], xmm0
0x180033539  movups  xmmword ptr [rsp+188h+FileObjectAttributes+1Ch], xmm0
0x180033541  movups  xmmword ptr [rsp+188h+KeyObjectAttributes.Length], xmm0
0x180033546  movups  xmmword ptr [rsp+188h+KeyObjectAttributes.ObjectName], xmm0
0x18003354b  movups  xmmword ptr [rsp+188h+KeyObjectAttributes+1Ch], xmm0
0x180033550  mov     [rsp+188h+var_148], rax
0x180033555  movups  xmmword ptr [r11-68h], xmm0
0x18003355a  xorps   xmm1, xmm1
0x18003355d  movups  xmmword ptr [r11-78h], xmm1
0x180033562  xor     esi, esi
0x180033564  lea     r14d, [rax+4]
0x180033568  xor     edi, edi
0x18003356a  mov     [rsp+188h+Handle], rdi
0x18003356f  xor     eax, eax
0x180033571  xorps   xmm0, xmm0
0x180033574  movups  xmmword ptr [rsp+188h+ObjectAttributes.Length], xmm0
0x18003357c  movups  xmmword ptr [rsp+188h+ObjectAttributes.ObjectName], xmm0
0x180033584  movups  xmmword ptr [rsp+188h+ObjectAttributes+1Ch], xmm0
0x18003358c  movups  xmmword ptr [rsp+188h+FileInformation.CreationTime], xmm0
0x180033594  movups  xmmword ptr [rsp+188h+FileInformation.LastWriteTime], xmm0
0x18003359c  mov     qword ptr [rsp+188h+FileInformation.FileAttributes], rax
0x1800335a4  movups  xmmword ptr [rsp+188h+DestinationString.Length], xmm0
0x1800335ac  lea     r13, [rdx+0Ch]
0x1800335b0  mov     rdx, r13; SourceString
0x1800335b3  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x1800335bb  call    cs:__imp_RtlInitUnicodeString
0x1800335c2  nop     dword ptr [rax+rax+00h]
0x1800335c7  mov     [rsp+188h+ObjectAttributes.Length], 30h ; '0'
0x1800335d2  mov     [rsp+188h+ObjectAttributes.RootDirectory], rdi
0x1800335da  mov     [rsp+188h+ObjectAttributes.Attributes], 40h ; '@'
0x1800335e5  lea     rax, [rsp+188h+DestinationString]
0x1800335ed  mov     [rsp+188h+ObjectAttributes.ObjectName], rax
0x1800335f5  xorps   xmm0, xmm0
0x1800335f8  movdqu  xmmword ptr [rsp+188h+ObjectAttributes.SecurityDescriptor], xmm0
0x180033601  lea     rdx, [rsp+188h+FileInformation]; FileInformation
0x180033609  lea     rcx, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x180033611  call    cs:__imp_ZwQueryAttributesFile
0x180033618  nop     dword ptr [rax+rax+00h]
0x18003361d  test    eax, eax
0x18003361f  js      loc_18003387B
0x180033625  test    byte ptr [rsp+188h+FileInformation.FileAttributes], 10h
0x18003362d  jnz     loc_18003387B
0x180033633  lea     r9, [rsp+188h+Handle]
0x180033638  mov     r8d, 0F003Fh
0x18003363e  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine"
0x180033645  xor     ecx, ecx
0x180033647  call    BiOpenKeyNonBcd
0x18003364c  mov     ebx, eax
0x18003364e  mov     dword ptr [rsp+188h+var_158], eax
0x180033652  test    eax, eax
0x180033654  jns     short loc_180033679
0x180033656  mov     r9d, eax
0x180033659  lea     r8, aRegistryMachin_1; "\\Registry\\Machine"
0x180033660  lea     rdx, aFailedOpenKeyW; "Failed open key %ws. Status: %x"
0x180033667  mov     ecx, r14d
0x18003366a  call    BiLogMessage
0x18003366f  mov     rdi, [rsp+188h+Handle]
0x180033674  jmp     loc_180033884
0x180033679  mov     rdx, r12; SourceString
0x18003367c  lea     rcx, [rsp+188h+var_78]; DestinationString
0x180033684  call    cs:__imp_RtlInitUnicodeString
0x18003368b  nop     dword ptr [rax+rax+00h]
0x180033690  mov     [rsp+188h+KeyObjectAttributes.Length], 30h ; '0'
0x180033698  mov     rdi, [rsp+188h+Handle]
0x18003369d  mov     [rsp+188h+KeyObjectAttributes.RootDirectory], rdi
0x1800336a2  mov     [rsp+188h+KeyObjectAttributes.Attributes], 40h ; '@'
0x1800336aa  lea     rax, [rsp+188h+var_78]
0x1800336b2  mov     [rsp+188h+KeyObjectAttributes.ObjectName], rax
0x1800336b7  xorps   xmm0, xmm0
0x1800336ba  movdqu  xmmword ptr [rsp+188h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x1800336c0  mov     rdx, r13; SourceString
0x1800336c3  lea     rcx, [rsp+188h+var_68]; DestinationString
0x1800336cb  call    cs:__imp_RtlInitUnicodeString
0x1800336d2  nop     dword ptr [rax+rax+00h]
0x1800336d7  mov     [rsp+188h+FileObjectAttributes.Length], 30h ; '0'
0x1800336e2  mov     [rsp+188h+FileObjectAttributes.RootDirectory], 0
0x1800336ee  mov     [rsp+188h+FileObjectAttributes.Attributes], 40h ; '@'
0x1800336f9  lea     rax, [rsp+188h+var_68]
0x180033701  mov     [rsp+188h+FileObjectAttributes.ObjectName], rax
0x180033709  xorps   xmm0, xmm0
0x18003370c  movdqu  xmmword ptr [rsp+188h+FileObjectAttributes.SecurityDescriptor], xmm0
0x180033715  lea     rdx, [rsp+188h+var_148]
0x18003371a  mov     ecx, 12h
0x18003371f  call    BiAcquirePrivilege
0x180033724  mov     ebx, eax
0x180033726  mov     dword ptr [rsp+188h+var_158], eax
0x18003372a  test    eax, eax
0x18003372c  jns     short loc_18003374C
0x18003372e  mov     r9d, eax
0x180033731  lea     r8, aRegistryMachin_1; "\\Registry\\Machine"
0x180033738  lea     rdx, aFailedToAcquir; "Failed to acquire permissions to load h"...
0x18003373f  mov     ecx, r14d
0x180033742  call    BiLogMessage
0x180033747  jmp     loc_180033884
0x18003374c  mov     [rsp+188h+Handle], 0
0x180033755  lea     rdx, [rsp+188h+Handle]
0x18003375a  lea     rcx, aZwloadkey2; "ZwLoadKey2"
0x180033761  call    BiLookupNtdllProcedureAddress
0x180033766  mov     ebx, eax
0x180033768  test    eax, eax
0x18003376a  js      short loc_1800337AE
0x18003376c  mov     r8d, 1780h
0x180033772  lea     rdx, [rsp+188h+FileObjectAttributes]
0x18003377a  lea     rcx, [rsp+188h+KeyObjectAttributes]
0x18003377f  mov     rax, [rsp+188h+Handle]
0x180033784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033789  mov     ebx, eax
0x18003378b  test    eax, eax
0x18003378d  jns     short loc_1800337AE
0x18003378f  mov     r8d, 1380h
0x180033795  lea     rdx, [rsp+188h+FileObjectAttributes]
0x18003379d  lea     rcx, [rsp+188h+KeyObjectAttributes]
0x1800337a2  mov     rax, [rsp+188h+Handle]
0x1800337a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337ac  mov     ebx, eax
0x1800337ae  test    ebx, ebx
0x1800337b0  jns     short loc_1800337CD
0x1800337b2  lea     rdx, [rsp+188h+FileObjectAttributes]; FileObjectAttributes
0x1800337ba  lea     rcx, [rsp+188h+KeyObjectAttributes]; KeyObjectAttributes
0x1800337bf  call    cs:__imp_ZwLoadKey
0x1800337c6  nop     dword ptr [rax+rax+00h]
0x1800337cb  mov     ebx, eax
0x1800337cd  lea     rcx, [rsp+188h+var_148]
0x1800337d2  call    BiReleasePrivilege
0x1800337d7  test    ebx, ebx
0x1800337d9  jns     short loc_18003380E
0x1800337db  mov     dword ptr [rsp+188h+var_158], ebx
0x1800337df  mov     ecx, 2
0x1800337e4  cmp     ebx, 0C0000022h
0x1800337ea  cmovnz  ecx, r14d
0x1800337ee  mov     dword ptr [rsp+188h+var_160], ebx
0x1800337f2  mov     [rsp+188h+var_168], r13
0x1800337f7  mov     r9d, 40h ; '@'
0x1800337fd  mov     r8, r12
0x180033800  lea     rdx, aFailedLoadKeyW; "Failed load key %ws. Flags: 0x%x File: "...
0x180033807  call    BiLogMessage
0x18003380c  jmp     short loc_180033884
0x18003380e  lea     r8, [rsp+188h+KeyObjectAttributes]; ObjectAttributes
0x180033813  mov     edx, 20019h; DesiredAccess
0x180033818  mov     rcx, [rsp+188h+KeyHandle]; KeyHandle
0x18003381d  call    cs:__imp_ZwOpenKey
0x180033824  nop     dword ptr [rax+rax+00h]
0x180033829  mov     ebx, eax
0x18003382b  mov     dword ptr [rsp+188h+var_158], eax
0x18003382f  test    eax, eax
0x180033831  jns     short loc_180033884
0x180033833  lea     rdx, [rsp+188h+var_148]
0x180033838  mov     ecx, 11h
0x18003383d  call    BiAcquirePrivilege
0x180033842  lea     rcx, [rsp+188h+KeyObjectAttributes]; KeyObjectAttributes
0x180033847  call    cs:__imp_ZwUnloadKey
0x18003384e  nop     dword ptr [rax+rax+00h]
0x180033853  lea     rcx, [rsp+188h+var_148]
0x180033858  call    BiReleasePrivilege
0x18003385d  mov     dword ptr [rsp+188h+var_168], ebx
0x180033861  mov     r9d, 40h ; '@'
0x180033867  mov     r8, r12
0x18003386a  lea     rdx, aFailedOpenNewl; "Failed open newly loaded key %ws. Flags"...
0x180033871  mov     ecx, r14d
0x180033874  call    BiLogMessage
0x180033879  jmp     short loc_180033884
0x18003387b  mov     ebx, 0C000000Fh
0x180033880  mov     dword ptr [rsp+188h+var_158], ebx
0x180033884  test    rdi, rdi
0x180033887  jz      short loc_180033898
0x180033889  mov     rcx, rdi; Handle
0x18003388c  call    cs:__imp_ZwClose
0x180033893  nop     dword ptr [rax+rax+00h]
0x180033898  cmp     ebx, 0C000017Dh
0x18003389e  jnz     short loc_1800338E3
0x1800338a0  int     3; Trap to Debugger
0x1800338a1  mov     rdx, [rsp+188h+var_140]
0x1800338a6  jmp     short loc_1800338D7
0x1800338a8  mov     esi, 5
0x1800338ad  lea     r14d, [rsi-1]
0x1800338b1  mov     ebx, dword ptr [rsp+188h+var_158]
0x1800338b5  mov     r12, [rsp+188h+var_100]
0x1800338bd  mov     rdx, [rsp+188h+var_F8]
0x1800338c5  mov     [rsp+188h+var_140], rdx
0x1800338ca  mov     rax, [rsp+188h+var_F0]
0x1800338d2  mov     [rsp+188h+KeyHandle], rax
0x1800338d7  cmp     esi, 5
0x1800338da  jnb     short loc_1800338E3
0x1800338dc  inc     esi
0x1800338de  jmp     loc_180033568
0x1800338e3  mov     eax, ebx
0x1800338e5  mov     rcx, [rsp+188h+var_30]
0x1800338ed  xor     rcx, rsp; StackCookie
0x1800338f0  call    __security_check_cookie
0x1800338f5  mov     rbx, [rsp+188h+arg_18]
0x1800338fd  add     rsp, 160h
0x180033904  pop     r14
0x180033906  pop     r13
0x180033908  pop     r12
0x18003390a  pop     rdi
0x18003390b  pop     rsi
0x18003390c  retn
```
