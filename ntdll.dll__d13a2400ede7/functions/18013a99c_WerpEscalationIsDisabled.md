# WerpEscalationIsDisabled

- ea: `0x18013a99c`
- end: `0x18013aa51`
- name: `WerpEscalationIsDisabled`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ce978`

## callees

- `0x1800c4700`
- `0x1800cf6a8`
- `0x18013a99c`
- `0x18015ecc0`
- `0x18015ed20`

## string_xrefs

- `0x18013a9ac`: `\Registry\Machine\Software\Microsoft\Windows\Windows Error Reporting\Escalation`

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
0x18013a99c  mov     [rsp-8+arg_10], rbx
0x18013a9a1  push    rbp
0x18013a9a2  mov     rbp, rsp
0x18013a9a5  sub     rsp, 60h
0x18013a9a9  xorps   xmm0, xmm0
0x18013a9ac  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\Software\\Microsof"...
0x18013a9b3  xor     eax, eax
0x18013a9b5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18013a9b9  movups  [rbp+var_20], xmm0
0x18013a9bd  xor     ebx, ebx
0x18013a9bf  mov     [rbp+Handle], rax
0x18013a9c3  movups  [rbp+var_20+0Ch], xmm0
0x18013a9c7  mov     [rbp+arg_0], ebx
0x18013a9ca  movups  [rbp+var_30], xmm0
0x18013a9ce  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18013a9d2  call    RtlInitUnicodeString
0x18013a9d7  lea     rax, [rbp+DestinationString]
0x18013a9db  mov     dword ptr [rbp+var_30], 30h ; '0'
0x18013a9e2  xorps   xmm0, xmm0
0x18013a9e5  mov     qword ptr [rbp+var_20], rax
0x18013a9e9  lea     r8, [rbp+var_30]
0x18013a9ed  mov     qword ptr [rbp+var_30+8], rbx
0x18013a9f1  mov     edx, 20019h
0x18013a9f6  mov     dword ptr [rbp+var_20+8], 40h ; '@'
0x18013a9fd  lea     rcx, [rbp+Handle]
0x18013aa01  movdqu  [rbp+var_10], xmm0
0x18013aa06  call    NtOpenKey
0x18013aa0b  test    eax, eax
0x18013aa0d  js      short loc_18013AA2D
0x18013aa0f  mov     rcx, [rbp+Handle]
0x18013aa13  lea     r8, [rbp+arg_0]
0x18013aa17  lea     rdx, aDisableescalat; "DisableEscalation"
0x18013aa1e  call    WerpEscalationReadUlongFromKey
0x18013aa23  mov     ebx, [rbp+arg_0]
0x18013aa26  xor     ecx, ecx
0x18013aa28  test    eax, eax
0x18013aa2a  cmovs   ebx, ecx
0x18013aa2d  mov     rcx, [rbp+Handle]; Handle
0x18013aa31  test    rcx, rcx
0x18013aa34  jz      short loc_18013AA3B
0x18013aa36  call    NtClose
0x18013aa3b  xor     eax, eax
0x18013aa3d  test    ebx, ebx
0x18013aa3f  mov     rbx, [rsp+60h+arg_10]
0x18013aa47  setnz   al
0x18013aa4a  add     rsp, 60h
0x18013aa4e  pop     rbp
0x18013aa4f  retn
```
