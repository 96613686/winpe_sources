# TdiTransportsValueQueryCallback

- ea: `0x140033d10`
- end: `0x140033e1e`
- name: `TdiTransportsValueQueryCallback`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x1400041f8`
- `0x140033d10`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140033da8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140033da8`

## pseudocode

```c
__int64 __fastcall TdiTransportsValueQueryCallback(__int64 a1, int a2, wchar_t *a3, int a4, int a5, _BYTE *a6)
{
  unsigned __int16 v6; // bx
  int v8; // edx
  UNICODE_STRING String2; // [rsp+40h] [rbp-38h] BYREF

  v6 = a4;
  if ( !a6 || a2 != 1 || !a4 )
    return 3221225485LL;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Sd(
      WPP_GLOBAL_Control->DeviceExtension,
      1,
      15,
      15,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      (__int64)a3,
      a4);
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String2.Length = v6 - 2;
  String2.MaximumLength = v6;
  String2.Buffer = a3;
  if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        15,
        16,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
    *a6 = 1;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      15,
      17,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140033d10  push    rbx
0x140033d12  push    rbp
0x140033d13  push    rsi
0x140033d14  push    rdi
0x140033d15  push    r15
0x140033d17  sub     rsp, 50h
0x140033d1b  mov     rdi, [rsp+78h+arg_28]
0x140033d23  mov     ebx, r9d
0x140033d26  mov     rsi, r8
0x140033d29  test    rdi, rdi
0x140033d2c  jz      loc_140033E0D
0x140033d32  cmp     edx, 1
0x140033d35  jnz     loc_140033E0D
0x140033d3b  test    ebx, ebx
0x140033d3d  jz      loc_140033E0D
0x140033d43  lea     rbp, WPP_RECORDER_INITIALIZED
0x140033d4a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140033d51  lea     r15, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140033d58  jz      short loc_140033D7F
0x140033d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033d61  lea     r9d, [rdx+0Eh]
0x140033d65  mov     [rsp+78h+var_48], ebx
0x140033d69  mov     [rsp+78h+var_50], r8
0x140033d6e  mov     r8d, r9d
0x140033d71  mov     [rsp+78h+var_58], r15
0x140033d76  mov     rcx, [rcx+40h]
0x140033d7a  call    WPP_RECORDER_SF_Sd
0x140033d7f  lea     eax, [rbx-2]
0x140033d82  mov     dword ptr [rsp+78h+String2+4], 0
0x140033d8a  mov     r8b, 1; CaseInSensitive
0x140033d8d  mov     [rsp+78h+String2.Length], ax
0x140033d92  lea     rdx, [rsp+78h+String2]; String2
0x140033d97  mov     [rsp+78h+String2.MaximumLength], bx
0x140033d9c  lea     rcx, String1; String1
0x140033da3  mov     [rsp+78h+String2.Buffer], rsi
0x140033da8  call    cs:__imp_RtlCompareUnicodeString
0x140033daf  nop     dword ptr [rax+rax+00h]
0x140033db4  test    eax, eax
0x140033db6  jnz     short loc_140033DE1
0x140033db8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140033dbf  jz      short loc_140033DDE
0x140033dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140033dc8  lea     r9d, [rax+10h]
0x140033dcc  lea     r8d, [rax+0Fh]
0x140033dd0  mov     [rsp+78h+var_58], r15
0x140033dd5  mov     rcx, [rcx+40h]
0x140033dd9  call    WPP_RECORDER_SF_
0x140033dde  mov     byte ptr [rdi], 1
0x140033de1  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140033de8  jz      short loc_140033E09
0x140033dea  mov     rcx, cs:WPP_GLOBAL_Control
0x140033df1  mov     r9d, 11h
0x140033df7  mov     [rsp+78h+var_58], r15
0x140033dfc  mov     rcx, [rcx+40h]
0x140033e00  lea     r8d, [r9-2]
0x140033e04  call    WPP_RECORDER_SF_
0x140033e09  xor     eax, eax
0x140033e0b  jmp     short loc_140033E12
0x140033e0d  mov     eax, 0C000000Dh
0x140033e12  add     rsp, 50h
0x140033e16  pop     r15
0x140033e18  pop     rdi
0x140033e19  pop     rsi
0x140033e1a  pop     rbp
0x140033e1b  pop     rbx
0x140033e1c  retn
```
