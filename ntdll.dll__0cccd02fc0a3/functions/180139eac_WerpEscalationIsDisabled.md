# WerpEscalationIsDisabled

- ea: `0x180139eac`
- end: `0x180139f61`
- name: `WerpEscalationIsDisabled`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ccde8`

## callees

- `0x1800c0420`
- `0x1800cdb18`
- `0x180139eac`
- `0x18015e4b0`
- `0x18015e510`

## string_xrefs

- `0x180139ebc`: `\Registry\Machine\Software\Microsoft\Windows\Windows Error Reporting\Escalation`

## pseudocode

```c
_BOOL8 WerpEscalationIsDisabled()
{
  int v0; // ebx
  int v1; // eax
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  __int128 v4; // [rsp+30h] [rbp-30h]
  __m256i v5; // [rsp+40h] [rbp-20h] BYREF
  int v6; // [rsp+70h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+18h]

  memset(&v5, 0, 28);
  v0 = 0;
  Handle = 0;
  v6 = 0;
  v4 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\Windows Error Reporting\\Escalation");
  LODWORD(v4) = 48;
  v5.m256i_i64[0] = (__int64)&DestinationString;
  *((_QWORD *)&v4 + 1) = 0;
  v5.m256i_i32[2] = 64;
  *(_OWORD *)&v5.m256i_u64[2] = 0;
  if ( (int)NtOpenKey() >= 0 )
  {
    v1 = WerpEscalationReadUlongFromKey(Handle, L"DisableEscalation", &v6);
    v0 = v6;
    if ( v1 < 0 )
      v0 = 0;
  }
  if ( Handle )
    NtClose(Handle);
  return v0 != 0;
}

```

## disassembly

```asm
0x180139eac  mov     [rsp-8+arg_10], rbx
0x180139eb1  push    rbp
0x180139eb2  mov     rbp, rsp
0x180139eb5  sub     rsp, 60h
0x180139eb9  xorps   xmm0, xmm0
0x180139ebc  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\Software\\Microsof"...
0x180139ec3  xor     eax, eax
0x180139ec5  lea     rcx, [rbp+DestinationString]; DestinationString
0x180139ec9  movups  [rbp+var_20], xmm0
0x180139ecd  xor     ebx, ebx
0x180139ecf  mov     [rbp+Handle], rax
0x180139ed3  movups  [rbp+var_20+0Ch], xmm0
0x180139ed7  mov     [rbp+arg_0], ebx
0x180139eda  movups  [rbp+var_30], xmm0
0x180139ede  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180139ee2  call    RtlInitUnicodeString
0x180139ee7  lea     rax, [rbp+DestinationString]
0x180139eeb  mov     dword ptr [rbp+var_30], 30h ; '0'
0x180139ef2  xorps   xmm0, xmm0
0x180139ef5  mov     qword ptr [rbp+var_20], rax
0x180139ef9  lea     r8, [rbp+var_30]
0x180139efd  mov     qword ptr [rbp+var_30+8], rbx
0x180139f01  mov     edx, 20019h
0x180139f06  mov     dword ptr [rbp+var_20+8], 40h ; '@'
0x180139f0d  lea     rcx, [rbp+Handle]
0x180139f11  movdqu  [rbp+var_10], xmm0
0x180139f16  call    NtOpenKey
0x180139f1b  test    eax, eax
0x180139f1d  js      short loc_180139F3D
0x180139f1f  mov     rcx, [rbp+Handle]
0x180139f23  lea     r8, [rbp+arg_0]
0x180139f27  lea     rdx, aDisableescalat; "DisableEscalation"
0x180139f2e  call    WerpEscalationReadUlongFromKey
0x180139f33  mov     ebx, [rbp+arg_0]
0x180139f36  xor     ecx, ecx
0x180139f38  test    eax, eax
0x180139f3a  cmovs   ebx, ecx
0x180139f3d  mov     rcx, [rbp+Handle]; Handle
0x180139f41  test    rcx, rcx
0x180139f44  jz      short loc_180139F4B
0x180139f46  call    NtClose
0x180139f4b  xor     eax, eax
0x180139f4d  test    ebx, ebx
0x180139f4f  mov     rbx, [rsp+60h+arg_10]
0x180139f57  setnz   al
0x180139f5a  add     rsp, 60h
0x180139f5e  pop     rbp
0x180139f5f  retn
```
