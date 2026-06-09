# CiInstrumentDefenderMrtId

- ea: `0x180065344`
- end: `0x18006548c`
- name: `CiInstrumentDefenderMrtId`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800697d0`

## callees

- `0x18000f3cc`
- `0x18000fb40`
- `0x18002c0d0`
- `0x18002c500`
- `0x18005ab10`
- `0x180065344`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800653c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800653c6`

## string_xrefs

- `0x1800653a2`: `\Registry\Machine\SOFTWARE\Microsoft\RemovalTools\MRT`

## pseudocode

```c
NTSTATUS CiInstrumentDefenderMrtId()
{
  NTSTATUS result; // eax
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 v3; // rcx
  __int64 v4; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v7; // [rsp+80h] [rbp-80h]
  __int64 v8; // [rsp+88h] [rbp-78h]
  _DWORD *v9; // [rsp+90h] [rbp-70h]
  __int64 v10; // [rsp+98h] [rbp-68h]
  PWSTR Buffer; // [rsp+A0h] [rbp-60h]
  _DWORD v12[2]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SourceString[40]; // [rsp+B0h] [rbp-50h] BYREF

  LODWORD(v4) = 0;
  DestinationString = 0;
  memset(SourceString, 0, 0x4Eu);
  result = CipGetRegistryValue(
             0,
             L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\RemovalTools\\MRT",
             (__int64)L"GUID",
             2,
             (__int64)SourceString,
             78,
             (__int64)&v4);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    result = _InterlockedCompareExchange(&g_LoggedMrtId, 1, 0);
    if ( !result )
    {
      result = dword_180049128;
      if ( (unsigned int)dword_180049128 > 5 )
      {
        result = tlgKeywordOn(&dword_180049128, 0x800000000000LL, v1, v2);
        if ( (_BYTE)result )
        {
          v4 = 2048;
          v7 = &v4;
          v8 = 8;
          v9 = v12;
          Buffer = DestinationString.Buffer;
          v12[0] = DestinationString.Length;
          v10 = 2;
          v12[1] = 0;
          return tlgWriteTransfer_EtwWriteTransfer(v3, (unsigned __int8 *)byte_18003D1AB, 0, 0, 5u, &v6);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180065344  push    rbp
0x180065346  lea     rbp, [rsp-10h]
0x18006534b  sub     rsp, 110h
0x180065352  mov     rax, cs:__security_cookie
0x180065359  xor     rax, rsp
0x18006535c  mov     [rbp+10h+var_10], rax
0x180065360  xor     edx, edx; Val
0x180065362  mov     dword ptr [rsp+110h+var_D0], 0
0x18006536a  xorps   xmm0, xmm0
0x18006536d  lea     rcx, [rbp+10h+SourceString]; void *
0x180065371  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x180065376  lea     r8d, [rdx+4Eh]; Size
0x18006537a  call    memset
0x18006537f  lea     rax, [rsp+110h+var_D0]
0x180065384  mov     r9d, 2
0x18006538a  mov     [rsp+110h+var_E0], rax
0x18006538f  lea     r8, aGuid; "GUID"
0x180065396  lea     rax, [rbp+10h+SourceString]
0x18006539a  mov     dword ptr [rsp+110h+var_E8], 4Eh ; 'N'
0x1800653a2  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800653a9  mov     [rsp+110h+var_F0], rax
0x1800653ae  xor     ecx, ecx
0x1800653b0  call    CipGetRegistryValue
0x1800653b5  test    eax, eax
0x1800653b7  js      loc_180065476
0x1800653bd  lea     rdx, [rbp+10h+SourceString]; SourceString
0x1800653c1  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x1800653c6  call    cs:__imp_RtlInitUnicodeString
0x1800653cd  nop     dword ptr [rax+rax+00h]
0x1800653d2  mov     ecx, 1
0x1800653d7  xor     eax, eax
0x1800653d9  lock cmpxchg cs:g_LoggedMrtId, ecx
0x1800653e1  jnz     loc_180065476
0x1800653e7  mov     eax, cs:dword_180049128
0x1800653ed  cmp     eax, 5
0x1800653f0  jbe     loc_180065476
0x1800653f6  mov     rdx, 800000000000h
0x180065400  lea     rcx, dword_180049128
0x180065407  call    _tlgKeywordOn
0x18006540c  test    al, al
0x18006540e  jz      short loc_180065476
0x180065410  lea     rax, [rsp+110h+var_D0]
0x180065415  mov     [rsp+110h+var_D0], 800h
0x18006541e  mov     [rbp+10h+var_90], rax
0x180065422  lea     rdx, byte_18003D1AB
0x180065429  lea     rax, [rbp+10h+var_68]
0x18006542d  mov     [rbp+10h+var_88], 8
0x180065435  mov     [rbp+10h+var_80], rax
0x180065439  xor     r9d, r9d
0x18006543c  mov     rax, [rsp+110h+DestinationString.Buffer]
0x180065441  xor     r8d, r8d
0x180065444  mov     [rbp+10h+var_70], rax
0x180065448  movzx   eax, [rsp+110h+DestinationString.Length]
0x18006544d  mov     [rbp+10h+var_68], eax
0x180065450  lea     rax, [rsp+110h+var_B0]
0x180065455  mov     [rsp+110h+var_E8], rax
0x18006545a  mov     dword ptr [rsp+110h+var_F0], 5
0x180065462  mov     [rbp+10h+var_78], 2
0x18006546a  mov     [rbp+10h+var_64], 0
0x180065471  call    _tlgWriteTransfer_EtwWriteTransfer
0x180065476  mov     rcx, [rbp+10h+var_10]
0x18006547a  xor     rcx, rsp; StackCookie
0x18006547d  call    __security_check_cookie
0x180065482  add     rsp, 110h
0x180065489  pop     rbp
0x18006548a  retn
```
