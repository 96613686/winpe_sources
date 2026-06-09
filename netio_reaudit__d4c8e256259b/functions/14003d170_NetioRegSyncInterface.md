# NetioRegSyncInterface

- ea: `0x14003d170`
- end: `0x14003d3a6`
- name: `NetioRegSyncInterface`
- size: `566`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140024cc0`
- `0x14003d170`
- `0x14003d3b0`
- `0x14003d4cc`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14003d369`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003d369`
- `ntoskrnl!RtlStringFromGUID` at `0x14003d240`
- `ntoskrnl!RtlStringFromGUID` at `0x14003d240`
- `ntoskrnl!ZwClose` at `0x14003d350`
- `ntoskrnl!ZwClose` at `0x14003d350`
- `ntoskrnl!ZwOpenKey` at `0x14003d2f7`
- `ntoskrnl!ZwOpenKey` at `0x14003d2f7`
- `ntoskrnl!ExAllocatePool2` at `0x14003d266`
- `ntoskrnl!ExAllocatePool2` at `0x14003d266`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d33a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d33a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003d2b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003d2b4`

## string_xrefs

- `0x14003d283`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall NetioRegSyncInterface(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int Parameter; // ebx
  wchar_t *Pool2; // rsi
  unsigned int i; // edi
  void *KeyHandle; // [rsp+30h] [rbp-A9h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v12; // [rsp+48h] [rbp-91h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-89h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-59h] BYREF
  _QWORD v15[10]; // [rsp+90h] [rbp-49h] BYREF
  GUID Guid; // [rsp+E0h] [rbp+7h] BYREF

  v12 = a1;
  KeyHandle = 0;
  DestinationString = 0;
  GuidString = 0;
  memset(&ObjectAttributes, 0, 44);
  Guid = 0;
  memset(v15, 0, sizeof(v15));
  LODWORD(v15[3]) = 0;
  v15[2] = &NPI_MS_NDIS_MODULEID;
  LODWORD(v15[6]) = 8;
  v15[5] = &v12;
  v15[8] = &Guid;
  LODWORD(v15[7]) = 2;
  v15[9] = 0x21800000010LL;
  v15[4] = 1;
  Parameter = NsiGetParameterEx((__int64)v15, v4, v5);
  if ( Parameter < 0 )
  {
    Guid = 0;
  }
  else
  {
    Parameter = RtlStringFromGUID(&Guid, &GuidString);
    if ( Parameter >= 0 )
    {
      Pool2 = (wchar_t *)ExAllocatePool2(64, 512, 1951421266);
      if ( Pool2 )
      {
        Parameter = RtlStringCchPrintfW(
                      Pool2,
                      0x100u,
                      L"%ls\\%ls",
                      L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
                      GuidString.Buffer);
        if ( Parameter >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, Pool2);
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Parameter = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
          if ( Parameter >= 0 )
          {
            for ( i = 0; i < a3; ++i )
            {
              Parameter = NetioRegSyncQueryAndUpdateKeyValue(KeyHandle);
              if ( Parameter < 0 )
              {
                Parameter = -1073741823;
                break;
              }
            }
          }
        }
        ExFreePoolWithTag(Pool2, 0);
      }
      else
      {
        Parameter = -1073741670;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x14003d170  push    rbp
0x14003d172  push    rbx
0x14003d173  push    rsi
0x14003d174  push    rdi
0x14003d175  push    r12
0x14003d177  push    r14
0x14003d179  push    r15
0x14003d17b  lea     rbp, [rsp-27h]
0x14003d180  sub     rsp, 100h
0x14003d187  mov     rax, cs:__security_cookie
0x14003d18e  xor     rax, rsp
0x14003d191  mov     [rbp+57h+var_40], rax
0x14003d195  xorps   xmm0, xmm0
0x14003d198  mov     [rsp+130h+var_E8], rcx
0x14003d19d  xor     eax, eax
0x14003d19f  mov     [rsp+130h+KeyHandle], 0
0x14003d1a8  mov     r14d, r8d
0x14003d1ab  lea     rcx, [rbp+57h+var_A0]; void *
0x14003d1af  mov     r15, rdx
0x14003d1b2  xorps   xmm1, xmm1
0x14003d1b5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14003d1b9  lea     r8d, [rax+50h]; Size
0x14003d1bd  xor     edx, edx; Val
0x14003d1bf  mov     r12, r9
0x14003d1c2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003d1c6  movups  xmmword ptr [rsp+130h+GuidString.Length], xmm1
0x14003d1cb  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x14003d1d0  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14003d1d4  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x14003d1d8  call    memset
0x14003d1dd  lea     rax, NPI_MS_NDIS_MODULEID
0x14003d1e4  mov     [rbp+57h+var_88], 0
0x14003d1eb  mov     [rbp+57h+var_90], rax
0x14003d1ef  lea     rcx, [rbp+57h+var_A0]
0x14003d1f3  lea     rax, [rsp+130h+var_E8]
0x14003d1f8  mov     [rbp+57h+var_70], 8
0x14003d1ff  mov     [rbp+57h+var_78], rax
0x14003d203  lea     rax, [rbp+57h+Guid]
0x14003d207  mov     [rbp+57h+var_60], rax
0x14003d20b  mov     [rbp+57h+var_68], 2
0x14003d212  mov     [rbp+57h+var_58], 10h
0x14003d219  mov     [rbp+57h+var_54], 218h
0x14003d220  mov     [rbp+57h+var_80], 1
0x14003d228  call    NsiGetParameterEx
0x14003d22d  mov     ebx, eax
0x14003d22f  test    eax, eax
0x14003d231  js      loc_14003D396
0x14003d237  lea     rdx, [rsp+130h+GuidString]; GuidString
0x14003d23c  lea     rcx, [rbp+57h+Guid]; Guid
0x14003d240  call    cs:__imp_RtlStringFromGUID
0x14003d247  nop     dword ptr [rax+rax+00h]
0x14003d24c  mov     ebx, eax
0x14003d24e  test    eax, eax
0x14003d250  js      loc_14003D346
0x14003d256  mov     edx, 200h
0x14003d25b  mov     ecx, 40h ; '@'
0x14003d260  mov     r8d, 74505352h
0x14003d266  call    cs:__imp_ExAllocatePool2
0x14003d26d  nop     dword ptr [rax+rax+00h]
0x14003d272  mov     rsi, rax
0x14003d275  test    rax, rax
0x14003d278  jz      loc_14003D39F
0x14003d27e  mov     rax, [rsp+130h+GuidString.Buffer]
0x14003d283  lea     r9, NetioInterfaceKey; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14003d28a  lea     r8, aLsLs; "%ls\\%ls"
0x14003d291  mov     [rsp+130h+var_110], rax
0x14003d296  mov     edx, 100h; cchDest
0x14003d29b  mov     rcx, rsi; pszDest
0x14003d29e  call    RtlStringCchPrintfW
0x14003d2a3  mov     ebx, eax
0x14003d2a5  test    eax, eax
0x14003d2a7  js      loc_14003D335
0x14003d2ad  mov     rdx, rsi; SourceString
0x14003d2b0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003d2b4  call    cs:__imp_RtlInitUnicodeString
0x14003d2bb  nop     dword ptr [rax+rax+00h]
0x14003d2c0  lea     rax, [rbp+57h+DestinationString]
0x14003d2c4  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x14003d2cc  xorps   xmm0, xmm0
0x14003d2cf  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14003d2d3  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x14003d2d8  mov     [rsp+130h+ObjectAttributes.RootDirectory], 0
0x14003d2e1  mov     edx, 20019h; DesiredAccess
0x14003d2e6  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14003d2ed  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14003d2f2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003d2f7  call    cs:__imp_ZwOpenKey
0x14003d2fe  nop     dword ptr [rax+rax+00h]
0x14003d303  mov     ebx, eax
0x14003d305  test    eax, eax
0x14003d307  js      short loc_14003D335
0x14003d309  xor     edi, edi
0x14003d30b  cmp     edi, r14d
0x14003d30e  jnb     short loc_14003D335
0x14003d310  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14003d315  mov     r8, r12
0x14003d318  mov     edx, edi
0x14003d31a  shl     rdx, 5
0x14003d31e  add     rdx, r15
0x14003d321  call    NetioRegSyncQueryAndUpdateKeyValue
0x14003d326  mov     ebx, eax
0x14003d328  test    eax, eax
0x14003d32a  js      short loc_14003D330
0x14003d32c  inc     edi
0x14003d32e  jmp     short loc_14003D30B
0x14003d330  mov     ebx, 0C0000001h
0x14003d335  xor     edx, edx; Tag
0x14003d337  mov     rcx, rsi; P
0x14003d33a  call    cs:__imp_ExFreePoolWithTag
0x14003d341  nop     dword ptr [rax+rax+00h]
0x14003d346  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14003d34b  test    rcx, rcx
0x14003d34e  jz      short loc_14003D35C
0x14003d350  call    cs:__imp_ZwClose
0x14003d357  nop     dword ptr [rax+rax+00h]
0x14003d35c  cmp     [rsp+130h+GuidString.Buffer], 0
0x14003d362  jz      short loc_14003D375
0x14003d364  lea     rcx, [rsp+130h+GuidString]; UnicodeString
0x14003d369  call    cs:__imp_RtlFreeUnicodeString
0x14003d370  nop     dword ptr [rax+rax+00h]
0x14003d375  mov     eax, ebx
0x14003d377  mov     rcx, [rbp+57h+var_40]
0x14003d37b  xor     rcx, rsp; StackCookie
0x14003d37e  call    __security_check_cookie
0x14003d383  add     rsp, 100h
0x14003d38a  pop     r15
0x14003d38c  pop     r14
0x14003d38e  pop     r12
0x14003d390  pop     rdi
0x14003d391  pop     rsi
0x14003d392  pop     rbx
0x14003d393  pop     rbp
0x14003d394  retn
0x14003d396  xorps   xmm0, xmm0
0x14003d399  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x14003d39d  jmp     short loc_14003D346
0x14003d39f  mov     ebx, 0C000009Ah
0x14003d3a4  jmp     short loc_14003D346
```
