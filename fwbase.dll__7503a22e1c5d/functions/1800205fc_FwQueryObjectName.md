# FwQueryObjectName

- ea: `0x1800205fc`
- end: `0x18002072b`
- name: `FwQueryObjectName`
- size: `303`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180007180`

## callees

- `0x1800045f0`
- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x180017c20`
- `0x18001e1d0`
- `0x1800205fc`
- `0x18002f38c`

## import_xrefs

- `ntdll!NtQueryObject` at `0x18002064d`
- `ntdll!NtQueryObject` at `0x1800206cd`
- `ntdll!NtQueryObject` at `0x18002064d`
- `ntdll!NtQueryObject` at `0x1800206cd`

## string_xrefs

- `0x180020661`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwQueryObjectName(HANDLE Handle, _QWORD *a2)
{
  NTSTATUS Object; // eax
  __int64 v5; // rdx
  _WORD **v6; // rax
  _WORD **v7; // rdi
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // r8d
  int v12; // r8d
  ULONG ObjectInformationLength; // [rsp+30h] [rbp-38h] BYREF
  __int128 v15; // [rsp+38h] [rbp-30h] BYREF

  *a2 = 0;
  ObjectInformationLength = 0;
  v15 = 0;
  Object = NtQueryObject(Handle, ObjectNameInformation, &v15, 0x10u, &ObjectInformationLength);
  if ( Object < 0 )
  {
    if ( Object != -2147483643 )
    {
      v7 = 0;
      goto LABEL_7;
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredArgs((__int64)"mpssvc.dll", Object, 0);
  }
  v6 = (_WORD **)FwAlloc(ObjectInformationLength, v5);
  v7 = v6;
  if ( !v6 )
  {
    v8 = FwReportErrorAsWinError((int)"FwQueryObjectName", (__int64)"FwAlloc", 8);
LABEL_8:
    v9 = v8;
    goto LABEL_12;
  }
  Object = NtQueryObject(Handle, ObjectNameInformation, v6, ObjectInformationLength, 0);
  if ( Object < 0 )
  {
LABEL_7:
    v8 = FwReportErrorAsNtStatus("FwQueryObjectName", "NtQueryObject", (unsigned int)Object);
    goto LABEL_8;
  }
  v10 = FwStringCopy(v7[1], a2);
  v9 = v10;
  if ( v10 < 0 )
    FwReportReturnError((int)"FwQueryObjectName", (unsigned int)v10, v11);
LABEL_12:
  FwFree(v7);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError((int)"FwQueryObjectName", (unsigned int)v9, v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800205fc  mov     r11, rsp
0x1800205ff  mov     [r11+18h], rbx
0x180020603  push    rsi
0x180020604  push    rdi
0x180020605  push    r14
0x180020607  sub     rsp, 50h
0x18002060b  mov     rax, cs:__security_cookie
0x180020612  xor     rax, rsp
0x180020615  mov     [rsp+68h+var_20], rax
0x18002061a  mov     r9d, 10h; ObjectInformationLength
0x180020620  mov     qword ptr [rdx], 0
0x180020627  mov     rbx, rdx
0x18002062a  mov     [rsp+68h+ObjectInformationLength], 0
0x180020632  xorps   xmm0, xmm0
0x180020635  lea     rax, [r11-38h]
0x180020639  lea     r8, [r11-30h]; ObjectInformation
0x18002063d  mov     [r11-48h], rax
0x180020641  lea     edx, [r9-0Fh]; ObjectInformationClass
0x180020645  mov     rsi, rcx
0x180020648  movups  [rsp+68h+var_30], xmm0
0x18002064d  call    cs:__imp_NtQueryObject
0x180020653  lea     r14, aFwqueryobjectn; "FwQueryObjectName"
0x18002065a  test    eax, eax
0x18002065c  js      short loc_180020695
0x18002065e  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "!NT_SUCCESS(ntStatus)", "NtWQueryObject Failed")
0x180020661  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x180020668  mov     edx, eax
0x18002066a  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002066f  mov     ecx, [rsp+68h+ObjectInformationLength]
0x180020673  call    FwAlloc
0x180020678  mov     rdi, rax
0x18002067b  test    rax, rax
0x18002067e  jnz     short loc_1800206B4
0x180020680  lea     r8d, [rax+8]
0x180020684  mov     rcx, r14
0x180020687  lea     rdx, aFwalloc_0; "FwAlloc"
0x18002068e  call    FwReportErrorAsWinError
0x180020693  jmp     short loc_1800206B0
0x180020695  cmp     eax, 80000005h
0x18002069a  jz      short loc_18002066F
0x18002069c  xor     edi, edi
0x18002069e  mov     r8d, eax
0x1800206a1  lea     rdx, aNtqueryobject; "NtQueryObject"
0x1800206a8  mov     rcx, r14
0x1800206ab  call    FwReportErrorAsNtStatus
0x1800206b0  mov     ebx, eax
0x1800206b2  jmp     short loc_1800206F3
0x1800206b4  mov     r9d, [rsp+68h+ObjectInformationLength]; ObjectInformationLength
0x1800206b9  mov     r8, rdi; ObjectInformation
0x1800206bc  mov     edx, 1; ObjectInformationClass
0x1800206c1  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x1800206ca  mov     rcx, rsi; Handle
0x1800206cd  call    cs:__imp_NtQueryObject
0x1800206d3  test    eax, eax
0x1800206d5  js      short loc_18002069E
0x1800206d7  mov     rcx, [rdi+8]; Src
0x1800206db  mov     rdx, rbx
0x1800206de  call    FwStringCopy
0x1800206e3  mov     ebx, eax
0x1800206e5  test    eax, eax
0x1800206e7  jns     short loc_1800206F3
0x1800206e9  mov     edx, eax
0x1800206eb  mov     rcx, r14
0x1800206ee  call    FwReportReturnError
0x1800206f3  mov     rcx, rdi
0x1800206f6  call    FwFree
0x1800206fb  test    ebx, ebx
0x1800206fd  jns     short loc_18002070B
0x1800206ff  mov     edx, ebx
0x180020701  mov     rcx, r14
0x180020704  call    FwReportReturnError
0x180020709  mov     ebx, eax
0x18002070b  mov     eax, ebx
0x18002070d  mov     rcx, [rsp+68h+var_20]
0x180020712  xor     rcx, rsp; StackCookie
0x180020715  call    __security_check_cookie
0x18002071a  mov     rbx, [rsp+68h+arg_10]
0x180020722  add     rsp, 50h
0x180020726  pop     r14
0x180020728  pop     rdi
0x180020729  pop     rsi
0x18002072a  retn
```
