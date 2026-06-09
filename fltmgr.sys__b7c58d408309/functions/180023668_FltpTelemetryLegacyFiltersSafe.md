# FltpTelemetryLegacyFiltersSafe

- ea: `0x180023668`
- end: `0x18002385c`
- name: `FltpTelemetryLegacyFiltersSafe`
- size: `500`
- prototype: `void __fastcall(__int64, signed __int32)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180052114`

## callees

- `0x180009f20`
- `0x180023668`
- `0x1800247a0`
- `0x180054e50`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x18002380d`
- `ntoskrnl!IoGetStackLimits` at `0x18002380d`
- `ntoskrnl!ZwClose` at `0x1800237d0`
- `ntoskrnl!ZwClose` at `0x1800237e0`
- `ntoskrnl!ZwClose` at `0x1800237d0`
- `ntoskrnl!ZwClose` at `0x1800237e0`
- `ntoskrnl!ZwOpenKey` at `0x1800236f2`
- `ntoskrnl!ZwOpenKey` at `0x1800236f2`
- `ntoskrnl!ZwCreateKey` at `0x1800237a8`
- `ntoskrnl!ZwCreateKey` at `0x1800237a8`

## pseudocode

```c
void __fastcall FltpTelemetryLegacyFiltersSafe(__int64 a1, signed __int32 a2)
{
  signed __int32 v4; // ecx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  HANDLE Handle; // [rsp+40h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int64 HighLimit; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v10[2]; // [rsp+58h] [rbp-31h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-21h] BYREF
  __int128 v12; // [rsp+98h] [rbp+Fh] BYREF
  _OWORD v13[2]; // [rsp+A8h] [rbp+1Fh]

  v4 = _InterlockedExchangeAdd(&dword_18003FFBC, 0);
  if ( v4 < a2 )
  {
    _InterlockedCompareExchange(&dword_18003FFBC, a2, v4);
    if ( !v4 )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      KeyHandle = 0;
      ObjectAttributes.RootDirectory = 0;
      *(_QWORD *)&ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v5 = ZwOpenKey(&KeyHandle, 0x20006u, &ObjectAttributes);
      if ( (int)FltpDbgStatus(v5) >= 0 )
      {
        v10[1] = &v12;
        v12 = *(_OWORD *)L"LegacyFiltersPresent";
        ObjectAttributes.RootDirectory = KeyHandle;
        v13[0] = *(_OWORD *)L"ltersPresent";
        v10[0] = 2752552;
        *(_OWORD *)((char *)v13 + 10) = *(_OWORD *)L"Present";
        Handle = 0;
        ObjectAttributes.Length = 48;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)v10;
        v6 = ZwCreateKey(&Handle, 0x20006u, &ObjectAttributes, 0, 0, 1u, 0);
        if ( (int)FltpDbgStatus(v6) >= 0 )
          ZwClose(Handle);
        ZwClose(KeyHandle);
      }
    }
  }
  if ( (unsigned int)dword_18003DAA8 > 5 )
  {
    HighLimit = 0;
    Handle = 0;
    IoGetStackLimits((PULONG_PTR)&Handle, &HighLimit);
    if ( (unsigned __int64)((char *)&HighLimit - (_BYTE *)Handle) >= 0x200 )
      FltpTelemetryLegacyFilters(a1, (unsigned int)a2);
    else
      _InterlockedIncrement(&dword_18003FFB0);
  }
}

```

## disassembly

```asm
0x180023668  mov     [rsp-8+arg_10], rbx
0x18002366d  push    rbp
0x18002366e  push    rsi
0x18002366f  push    rdi
0x180023670  lea     rbp, [rsp-47h]
0x180023675  sub     rsp, 0D0h
0x18002367c  mov     rax, cs:__security_cookie
0x180023683  xor     rax, rsp
0x180023686  mov     [rbp+57h+var_18], rax
0x18002368a  mov     rdi, rcx
0x18002368d  mov     ebx, edx
0x18002368f  xor     ecx, ecx
0x180023691  lock xadd cs:dword_18003FFBC, ecx
0x180023699  cmp     ecx, edx
0x18002369b  jge     loc_1800237EC
0x1800236a1  mov     eax, ecx
0x1800236a3  lock cmpxchg cs:dword_18003FFBC, ebx
0x1800236ab  test    ecx, ecx
0x1800236ad  jnz     loc_1800237EC
0x1800236b3  xor     eax, eax
0x1800236b5  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800236bd  mov     [rbp+57h+KeyHandle], rax
0x1800236c1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800236c5  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800236c9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800236cd  lea     rax, DestinationString
0x1800236d4  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800236dc  xorps   xmm0, xmm0
0x1800236df  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800236e3  mov     edx, 20006h; DesiredAccess
0x1800236e8  mov     esi, 92Ah
0x1800236ed  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800236f2  call    cs:__imp_ZwOpenKey
0x1800236f9  nop     dword ptr [rax+rax+00h]
0x1800236fe  xor     r9d, r9d
0x180023701  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180023708  mov     ecx, eax
0x18002370a  mov     r8d, esi
0x18002370d  call    FltpDbgStatus
0x180023712  test    eax, eax
0x180023714  js      loc_1800237EC
0x18002371a  movups  xmm0, xmmword ptr cs:aLegacyfiltersp; "LegacyFiltersPresent"
0x180023721  lea     rax, [rbp+57h+var_48]
0x180023725  mov     [rsp+0E0h+Disposition], 0; Disposition
0x18002372e  movups  xmm1, xmmword ptr cs:aLegacyfiltersp+10h; "ltersPresent"
0x180023735  mov     [rbp+57h+var_80], rax
0x180023739  xor     r9d, r9d; TitleIndex
0x18002373c  mov     rax, [rbp+57h+KeyHandle]
0x180023740  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180023744  movups  [rbp+57h+var_48], xmm0
0x180023748  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18002374c  lea     rax, [rbp+57h+var_88]
0x180023750  movups  xmm0, xmmword ptr cs:aLegacyfiltersp+1Ah; "Present"
0x180023757  mov     [rsp+0E0h+CreateOptions], 1; CreateOptions
0x18002375f  mov     edx, 20006h; DesiredAccess
0x180023764  movups  xmmword ptr [rbp+57h+var_38], xmm1
0x180023768  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18002376c  mov     [rbp+57h+var_88], 2A0028h
0x180023774  movups  xmmword ptr [rbp+57h+var_38+0Ah], xmm0
0x180023778  mov     [rbp+57h+Handle], 0
0x180023780  mov     esi, 93Bh
0x180023785  xorps   xmm0, xmm0
0x180023788  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002378f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180023794  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18002379b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002379f  mov     [rsp+0E0h+Class], 0; Class
0x1800237a8  call    cs:__imp_ZwCreateKey
0x1800237af  nop     dword ptr [rax+rax+00h]
0x1800237b4  xor     r9d, r9d
0x1800237b7  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x1800237be  mov     ecx, eax
0x1800237c0  mov     r8d, esi
0x1800237c3  call    FltpDbgStatus
0x1800237c8  test    eax, eax
0x1800237ca  js      short loc_1800237DC
0x1800237cc  mov     rcx, [rbp+57h+Handle]; Handle
0x1800237d0  call    cs:__imp_ZwClose
0x1800237d7  nop     dword ptr [rax+rax+00h]
0x1800237dc  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800237e0  call    cs:__imp_ZwClose
0x1800237e7  nop     dword ptr [rax+rax+00h]
0x1800237ec  cmp     cs:dword_18003DAA8, 5
0x1800237f3  jbe     short loc_18002383C
0x1800237f5  lea     rdx, [rbp+57h+HighLimit]; HighLimit
0x1800237f9  mov     [rbp+57h+HighLimit], 0
0x180023801  lea     rcx, [rbp+57h+Handle]; LowLimit
0x180023805  mov     [rbp+57h+Handle], 0
0x18002380d  call    cs:__imp_IoGetStackLimits
0x180023814  nop     dword ptr [rax+rax+00h]
0x180023819  lea     rax, [rbp+57h+HighLimit]
0x18002381d  sub     rax, [rbp+57h+Handle]
0x180023821  cmp     rax, 200h
0x180023827  jnb     short loc_180023832
0x180023829  lock inc cs:dword_18003FFB0
0x180023830  jmp     short loc_18002383C
0x180023832  mov     edx, ebx
0x180023834  mov     rcx, rdi
0x180023837  call    FltpTelemetryLegacyFilters
0x18002383c  mov     rcx, [rbp+57h+var_18]
0x180023840  xor     rcx, rsp; StackCookie
0x180023843  call    __security_check_cookie
0x180023848  mov     rbx, [rsp+0E0h+arg_10]
0x180023850  add     rsp, 0D0h
0x180023857  pop     rdi
0x180023858  pop     rsi
0x180023859  pop     rbp
0x18002385a  retn
```
