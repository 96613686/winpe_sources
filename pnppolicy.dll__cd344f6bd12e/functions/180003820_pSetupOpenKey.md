# pSetupOpenKey

- ea: `0x180003820`
- end: `0x1800038fb`
- name: `pSetupOpenKey`
- size: `219`
- prototype: `__int64 __fastcall(void *, const WCHAR *, __int64, ACCESS_MASK, _QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001ad0`
- `0x180003904`
- `0x180003cf8`
- `0x1800040d8`
- `0x180005018`
- `0x1800051f8`
- `0x1800054d4`
- `0x1800058a0`
- `0x180007548`

## callees

- `0x180003820`
- `0x180003904`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800038be`
- `ntdll!NtOpenKey` at `0x1800038be`
- `ntdll!RtlInitUnicodeString` at `0x180003884`
- `ntdll!RtlInitUnicodeString` at `0x180003884`
- `ntdll!NtClose` at `0x1800038e6`
- `ntdll!NtClose` at `0x1800038e6`
- `ntdll!RtlNtStatusToDosError` at `0x1800038ca`
- `ntdll!RtlNtStatusToDosError` at `0x1800038ca`

## pseudocode

```c
__int64 __fastcall pSetupOpenKey(void *a1, const WCHAR *a2, __int64 a3, ACCESS_MASK a4, _QWORD *a5)
{
  HANDLE v5; // rbx
  void *v8; // rsi
  ULONG v9; // edi
  ULONG v10; // eax
  int v11; // eax
  void *KeyHandle; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+38h] BYREF

  KeyHandle = 0;
  v5 = 0;
  Handle = 0;
  v8 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)a1 + 0x80000000 <= 7 )
  {
    v10 = pSetupOpenPredefinedKey(a1, &Handle);
    v5 = Handle;
    v9 = v10;
    if ( v10 )
      goto LABEL_9;
  }
  else
  {
    v9 = 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  if ( v5 )
    v8 = v5;
  ObjectAttributes.RootDirectory = v8;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenKey(&KeyHandle, a4, &ObjectAttributes);
  if ( v11 >= 0 )
    *a5 = (int)KeyHandle;
  else
    v9 = RtlNtStatusToDosError(v11);
LABEL_9:
  if ( v5 )
    NtClose((HANDLE)(unsigned int)v5);
  return v9;
}

```

## disassembly

```asm
0x180003820  push    rbp
0x180003822  push    rbx
0x180003823  push    rsi
0x180003824  push    rdi
0x180003825  push    r14
0x180003827  push    r15
0x180003829  mov     rbp, rsp
0x18000382c  sub     rsp, 78h
0x180003830  xor     eax, eax
0x180003832  xorps   xmm0, xmm0
0x180003835  mov     [rbp+KeyHandle], rax
0x180003839  xor     ebx, ebx
0x18000383b  mov     eax, 80000000h
0x180003840  mov     [rbp+Handle], rbx
0x180003844  add     rax, rcx
0x180003847  mov     r14d, r9d
0x18000384a  mov     r15, rdx
0x18000384d  mov     rsi, rcx
0x180003850  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180003854  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180003858  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000385c  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180003860  cmp     rax, 7
0x180003864  jbe     short loc_18000386A
0x180003866  xor     edi, edi
0x180003868  jmp     short loc_18000387D
0x18000386a  lea     rdx, [rbp+Handle]
0x18000386e  call    pSetupOpenPredefinedKey
0x180003873  mov     rbx, [rbp+Handle]
0x180003877  mov     edi, eax
0x180003879  test    eax, eax
0x18000387b  jnz     short loc_1800038DF
0x18000387d  mov     rdx, r15; SourceString
0x180003880  lea     rcx, [rbp+DestinationString]; DestinationString
0x180003884  call    cs:__imp_RtlInitUnicodeString
0x18000388a  lea     rax, [rbp+DestinationString]
0x18000388e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180003895  xorps   xmm0, xmm0
0x180003898  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000389f  test    rbx, rbx
0x1800038a2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800038a6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800038aa  mov     edx, r14d; DesiredAccess
0x1800038ad  cmovnz  rsi, rbx
0x1800038b1  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800038b5  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1800038b9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800038be  call    cs:__imp_NtOpenKey
0x1800038c4  test    eax, eax
0x1800038c6  jns     short loc_1800038D4
0x1800038c8  mov     ecx, eax; Status
0x1800038ca  call    cs:__imp_RtlNtStatusToDosError
0x1800038d0  mov     edi, eax
0x1800038d2  jmp     short loc_1800038DF
0x1800038d4  mov     rax, [rbp+arg_20]
0x1800038d8  movsxd  rcx, dword ptr [rbp+KeyHandle]
0x1800038dc  mov     [rax], rcx
0x1800038df  test    rbx, rbx
0x1800038e2  jz      short loc_1800038EC
0x1800038e4  mov     ecx, ebx; Handle
0x1800038e6  call    cs:__imp_NtClose
0x1800038ec  mov     eax, edi
0x1800038ee  add     rsp, 78h
0x1800038f2  pop     r15
0x1800038f4  pop     r14
0x1800038f6  pop     rdi
0x1800038f7  pop     rsi
0x1800038f8  pop     rbx
0x1800038f9  pop     rbp
0x1800038fa  retn
```
