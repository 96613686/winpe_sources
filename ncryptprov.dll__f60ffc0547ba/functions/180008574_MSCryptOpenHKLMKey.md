# MSCryptOpenHKLMKey

- ea: `0x180008574`
- end: `0x1800086c5`
- name: `MSCryptOpenHKLMKey`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008d5c`

## callees

- `0x180008574`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800086b2`
- `ntdll!RtlNtStatusToDosError` at `0x1800086b2`
- `ntdll!NtOpenKey` at `0x18000861a`
- `ntdll!NtOpenKey` at `0x18000861a`
- `ntdll!RtlAppendUnicodeToString` at `0x1800085c8`
- `ntdll!RtlAppendUnicodeToString` at `0x1800085de`
- `ntdll!RtlAppendUnicodeToString` at `0x1800085c8`
- `ntdll!RtlAppendUnicodeToString` at `0x1800085de`

## string_xrefs

- `0x1800085b4`: `\Registry\MACHINE\`
- `0x18000866f`: `onecore\ds\security\cryptoapi\ncrypt\common\registry.c`
- `0x18000869b`: `onecore\ds\security\cryptoapi\ncrypt\common\registry.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenHKLMKey(__int64 a1, __int64 a2, void **a3)
{
  struct _UNICODE_STRING *v4; // rax
  int v5; // edx
  struct _UNICODE_STRING *v6; // rbx
  ULONG v7; // edi
  NTSTATUS v8; // eax
  NTSTATUS v9; // esi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  memset(&ObjectAttributes, 0, 44);
  v4 = (struct _UNICODE_STRING *)SafeAllocaAllocateFromHeap(116);
  v6 = v4;
  if ( v4 )
  {
    *(_DWORD *)&v4->Length = 6553600;
    v4->Buffer = &v4[1].Length;
    v7 = 0;
    RtlAppendUnicodeToString(v4, L"\\Registry\\MACHINE\\");
    RtlAppendUnicodeToString(v6, L"Software\\Microsoft\\Cryptography");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = v6;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = NtOpenKey(a3, 0x20119u, &ObjectAttributes);
    v9 = v8;
    if ( v8 < 0 )
    {
      DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\registry.c", 116);
      v7 = RtlNtStatusToDosError(v9);
    }
    MSCryptFree(v6);
    return v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\registry.c",
        (unsigned int)"lError",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\registry.c",
        96);
    return 8;
  }
}

```

## disassembly

```asm
0x180008574  mov     [rsp+arg_0], rbx
0x180008579  mov     [rsp+arg_8], rsi
0x18000857e  push    rdi
0x18000857f  sub     rsp, 70h
0x180008583  xorps   xmm0, xmm0
0x180008586  xor     eax, eax
0x180008588  movups  xmmword ptr [rsp+78h+ObjectAttributes.ObjectName], xmm0
0x18000858d  mov     rsi, r8
0x180008590  movups  xmmword ptr [rsp+78h+ObjectAttributes.Length], xmm0
0x180008595  lea     ecx, [rax+74h]
0x180008598  movups  xmmword ptr [rsp+78h+ObjectAttributes+1Ch], xmm0
0x18000859d  call    SafeAllocaAllocateFromHeap
0x1800085a2  mov     rbx, rax
0x1800085a5  test    rax, rax
0x1800085a8  jz      loc_180008649
0x1800085ae  mov     dword ptr [rax], 640000h
0x1800085b4  lea     rdx, Source; "\\Registry\\MACHINE\\"
0x1800085bb  add     rax, 10h
0x1800085bf  mov     rcx, rbx; Destination
0x1800085c2  mov     [rbx+8], rax
0x1800085c6  xor     edi, edi
0x1800085c8  call    cs:__imp_RtlAppendUnicodeToString
0x1800085cf  nop     dword ptr [rax+rax+00h]
0x1800085d4  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Cryptography"
0x1800085db  mov     rcx, rbx; Destination
0x1800085de  call    cs:__imp_RtlAppendUnicodeToString
0x1800085e5  nop     dword ptr [rax+rax+00h]
0x1800085ea  xorps   xmm0, xmm0
0x1800085ed  mov     [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x1800085f5  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x1800085fa  mov     [rsp+78h+ObjectAttributes.RootDirectory], rdi
0x1800085ff  mov     edx, 20119h; DesiredAccess
0x180008604  mov     [rsp+78h+ObjectAttributes.Attributes], 40h ; '@'
0x18000860c  mov     rcx, rsi; KeyHandle
0x18000860f  mov     [rsp+78h+ObjectAttributes.ObjectName], rbx
0x180008614  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000861a  call    cs:__imp_NtOpenKey
0x180008621  nop     dword ptr [rax+rax+00h]
0x180008626  mov     esi, eax
0x180008628  test    eax, eax
0x18000862a  js      short loc_180008695
0x18000862c  mov     rcx, rbx
0x18000862f  call    MSCryptFree
0x180008634  mov     eax, edi
0x180008636  lea     r11, [rsp+78h+var_8]
0x18000863b  mov     rbx, [r11+10h]
0x18000863f  mov     rsi, [r11+18h]
0x180008643  mov     rsp, r11
0x180008646  pop     rdi
0x180008647  retn
0x180008649  mov     rcx, cs:WPP_GLOBAL_Control
0x180008650  lea     rax, WPP_GLOBAL_Control
0x180008657  mov     ebx, 8
0x18000865c  cmp     rcx, rax
0x18000865f  jz      short loc_180008667
0x180008661  test    byte ptr [rcx+1Ch], 1
0x180008665  jnz     short loc_18000866B
0x180008667  mov     eax, ebx
0x180008669  jmp     short loc_180008636
0x18000866b  mov     rcx, [rcx+10h]
0x18000866f  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008676  mov     [rsp+78h+var_48], 60h ; '`'
0x18000867e  lea     r9, aLerror; "lError"
0x180008685  mov     [rsp+78h+var_50], r8
0x18000868a  mov     [rsp+78h+var_58], ebx
0x18000868e  call    WPP_SF_sDsd
0x180008693  jmp     short loc_180008667
0x180008695  mov     r9d, 74h ; 't'
0x18000869b  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800086a2  lea     rdx, aStatus; "Status"
0x1800086a9  mov     ecx, esi
0x1800086ab  call    DebugTraceError
0x1800086b0  mov     ecx, esi; Status
0x1800086b2  call    cs:__imp_RtlNtStatusToDosError
0x1800086b9  nop     dword ptr [rax+rax+00h]
0x1800086be  mov     edi, eax
0x1800086c0  jmp     loc_18000862C
```
