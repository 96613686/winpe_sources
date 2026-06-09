# UMRxReadDWORDFromTheRegistry

- ea: `0x1400282d4`
- end: `0x140028507`
- name: `UMRxReadDWORDFromTheRegistry`
- size: `563`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140016d2c`
- `0x140017dfc`

## callees

- `0x140001680`
- `0x140006900`
- `0x1400282d4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002839c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002842c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028498`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002839c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002842c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028498`
- `ntoskrnl!ExAllocatePool2` at `0x1400283ed`
- `ntoskrnl!ExAllocatePool2` at `0x1400283ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400284e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400284e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028323`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400283cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028323`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400283cf`
- `ntoskrnl!NtClose` at `0x1400284c7`
- `ntoskrnl!NtClose` at `0x1400284c7`
- `ntoskrnl!ZwOpenKey` at `0x140028362`
- `ntoskrnl!ZwOpenKey` at `0x140028362`
- `ntoskrnl!ZwQueryValueKey` at `0x140028468`
- `ntoskrnl!ZwQueryValueKey` at `0x140028468`

## string_xrefs

- `0x1400282ff`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\MRxDAV\Parameters`

## pseudocode

```c
__int64 __fastcall UMRxReadDWORDFromTheRegistry(__int64 a1, const WCHAR *a2, void *a3)
{
  unsigned int v5; // esi
  unsigned int *Pool2; // rdi
  __int64 v7; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  HANDLE v11; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+20h] BYREF
  int v17; // [rsp+A4h] [rbp+24h]
  void *KeyHandle; // [rsp+B8h] [rbp+38h] BYREF

  v17 = HIDWORD(a1);
  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\MRxDAV\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v5 )
  {
    Pool2 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      v9 = 134;
LABEL_5:
      WPP_SF_qD(v7, v9, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId, v5);
    }
  }
  else
  {
    RtlInitUnicodeString(&ValueName, a2);
    Pool2 = (unsigned int *)ExAllocatePool2(258, 20, 1146507369);
    if ( Pool2 )
    {
      v5 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, 0x14u, &ResultLength);
      if ( !v5 )
      {
        memmove(a3, Pool2 + 3, Pool2[2]);
        goto LABEL_16;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
      {
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        CurrentThreadId = PsGetCurrentThreadId();
        v9 = 136;
        goto LABEL_5;
      }
    }
    else
    {
      v5 = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
      {
        v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v11 = PsGetCurrentThreadId();
        WPP_SF_qD(v10, 135, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v11, -1073741670);
      }
    }
  }
LABEL_16:
  if ( KeyHandle )
  {
    NtClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return v5;
}

```

## disassembly

```asm
0x1400282d4  mov     [rsp-18h+arg_8], rbx
0x1400282d9  mov     qword ptr [rsp-18h+arg_0], rcx
0x1400282de  push    rbp
0x1400282df  push    rsi
0x1400282e0  push    rdi
0x1400282e1  mov     rbp, rsp
0x1400282e4  sub     rsp, 80h
0x1400282eb  xorps   xmm0, xmm0
0x1400282ee  mov     [rbp+KeyHandle], 0
0x1400282f6  mov     rdi, rdx
0x1400282f9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400282fd  xor     eax, eax
0x1400282ff  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140028306  xorps   xmm1, xmm1
0x140028309  mov     [rbp+arg_0], eax
0x14002830c  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140028310  mov     rbx, r8
0x140028313  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140028317  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14002831b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002831f  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x140028323  call    cs:__imp_RtlInitUnicodeString
0x14002832a  nop     dword ptr [rax+rax+00h]
0x14002832f  lea     rax, [rbp+DestinationString]
0x140028333  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002833a  xorps   xmm0, xmm0
0x14002833d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140028341  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140028345  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002834d  mov     edx, 20019h; DesiredAccess
0x140028352  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140028359  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14002835d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140028362  call    cs:__imp_ZwOpenKey
0x140028369  nop     dword ptr [rax+rax+00h]
0x14002836e  mov     esi, eax
0x140028370  test    eax, eax
0x140028372  jz      short loc_1400283C8
0x140028374  xor     edi, edi
0x140028376  mov     rbx, cs:WPP_GLOBAL_Control
0x14002837d  lea     rcx, WPP_GLOBAL_Control
0x140028384  cmp     rbx, rcx
0x140028387  jz      loc_1400284BE
0x14002838d  mov     ecx, [rbx+2Ch]
0x140028390  test    cl, cl
0x140028392  jns     loc_1400284BE
0x140028398  mov     rbx, [rbx+18h]
0x14002839c  call    cs:__imp_PsGetCurrentThreadId
0x1400283a3  nop     dword ptr [rax+rax+00h]
0x1400283a8  mov     edx, 86h
0x1400283ad  mov     [rsp+80h+Length], esi
0x1400283b1  mov     r9, rax
0x1400283b4  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400283bb  mov     rcx, rbx
0x1400283be  call    WPP_SF_qD
0x1400283c3  jmp     loc_1400284BE
0x1400283c8  mov     rdx, rdi; SourceString
0x1400283cb  lea     rcx, [rbp+ValueName]; DestinationString
0x1400283cf  call    cs:__imp_RtlInitUnicodeString
0x1400283d6  nop     dword ptr [rax+rax+00h]
0x1400283db  mov     esi, 14h
0x1400283e0  mov     r8d, 44565069h
0x1400283e6  mov     edx, esi
0x1400283e8  mov     ecx, 102h
0x1400283ed  call    cs:__imp_ExAllocatePool2
0x1400283f4  nop     dword ptr [rax+rax+00h]
0x1400283f9  mov     rdi, rax
0x1400283fc  test    rax, rax
0x1400283ff  jnz     short loc_14002844A
0x140028401  mov     esi, 0C000009Ah
0x140028406  mov     rbx, cs:WPP_GLOBAL_Control
0x14002840d  lea     rcx, WPP_GLOBAL_Control
0x140028414  cmp     rbx, rcx
0x140028417  jz      loc_1400284BE
0x14002841d  mov     ecx, [rbx+2Ch]
0x140028420  test    cl, cl
0x140028422  jns     loc_1400284BE
0x140028428  mov     rbx, [rbx+18h]
0x14002842c  call    cs:__imp_PsGetCurrentThreadId
0x140028433  nop     dword ptr [rax+rax+00h]
0x140028438  mov     edx, 87h
0x14002843d  mov     [rsp+80h+Length], 0C000009Ah
0x140028445  jmp     loc_1400283B1
0x14002844a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002844e  lea     rax, [rbp+arg_0]
0x140028452  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140028457  lea     rdx, [rbp+ValueName]; ValueName
0x14002845b  mov     r9, rdi; KeyValueInformation
0x14002845e  mov     [rsp+80h+Length], esi; Length
0x140028462  mov     r8d, 2; KeyValueInformationClass
0x140028468  call    cs:__imp_ZwQueryValueKey
0x14002846f  nop     dword ptr [rax+rax+00h]
0x140028474  mov     esi, eax
0x140028476  test    eax, eax
0x140028478  jz      short loc_1400284AE
0x14002847a  mov     rbx, cs:WPP_GLOBAL_Control
0x140028481  lea     rcx, WPP_GLOBAL_Control
0x140028488  cmp     rbx, rcx
0x14002848b  jz      short loc_1400284BE
0x14002848d  mov     eax, [rbx+2Ch]
0x140028490  test    al, al
0x140028492  jns     short loc_1400284BE
0x140028494  mov     rbx, [rbx+18h]
0x140028498  call    cs:__imp_PsGetCurrentThreadId
0x14002849f  nop     dword ptr [rax+rax+00h]
0x1400284a4  mov     edx, 88h
0x1400284a9  jmp     loc_1400283AD
0x1400284ae  mov     r8d, [rdi+8]; Size
0x1400284b2  lea     rdx, [rdi+0Ch]; Src
0x1400284b6  mov     rcx, rbx; void *
0x1400284b9  call    memmove
0x1400284be  mov     rcx, [rbp+KeyHandle]; Handle
0x1400284c2  test    rcx, rcx
0x1400284c5  jz      short loc_1400284DB
0x1400284c7  call    cs:__imp_NtClose
0x1400284ce  nop     dword ptr [rax+rax+00h]
0x1400284d3  mov     [rbp+KeyHandle], 0
0x1400284db  test    rdi, rdi
0x1400284de  jz      short loc_1400284F1
0x1400284e0  xor     edx, edx; Tag
0x1400284e2  mov     rcx, rdi; P
0x1400284e5  call    cs:__imp_ExFreePoolWithTag
0x1400284ec  nop     dword ptr [rax+rax+00h]
0x1400284f1  mov     rbx, [rsp+80h+arg_8]
0x1400284f9  mov     eax, esi
0x1400284fb  add     rsp, 80h
0x140028502  pop     rdi
0x140028503  pop     rsi
0x140028504  pop     rbp
0x140028505  retn
```
