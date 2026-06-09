# CiInstrumentDefenderMrtId

- ea: `0x1800651d4`
- end: `0x18006531c`
- name: `CiInstrumentDefenderMrtId`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180069660`

## callees

- `0x18000f3bc`
- `0x18000fb30`
- `0x18002bf20`
- `0x18002c380`
- `0x18005abe8`
- `0x1800651d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180065256`
- `ntoskrnl!RtlInitUnicodeString` at `0x180065256`

## string_xrefs

- `0x180065232`: `\Registry\Machine\SOFTWARE\Microsoft\RemovalTools\MRT`

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
          return tlgWriteTransfer_EtwWriteTransfer(v3, (unsigned __int8 *)&byte_18003D4AF, 0, 0, 5u, &v6);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800651d4  push    rbp
0x1800651d6  lea     rbp, [rsp-10h]
0x1800651db  sub     rsp, 110h
0x1800651e2  mov     rax, cs:__security_cookie
0x1800651e9  xor     rax, rsp
0x1800651ec  mov     [rbp+10h+var_10], rax
0x1800651f0  xor     edx, edx; Val
0x1800651f2  mov     dword ptr [rsp+110h+var_D0], 0
0x1800651fa  xorps   xmm0, xmm0
0x1800651fd  lea     rcx, [rbp+10h+SourceString]; void *
0x180065201  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x180065206  lea     r8d, [rdx+4Eh]; Size
0x18006520a  call    memset
0x18006520f  lea     rax, [rsp+110h+var_D0]
0x180065214  mov     r9d, 2
0x18006521a  mov     [rsp+110h+var_E0], rax
0x18006521f  lea     r8, aGuid; "GUID"
0x180065226  lea     rax, [rbp+10h+SourceString]
0x18006522a  mov     dword ptr [rsp+110h+var_E8], 4Eh ; 'N'
0x180065232  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180065239  mov     [rsp+110h+var_F0], rax
0x18006523e  xor     ecx, ecx
0x180065240  call    CipGetRegistryValue
0x180065245  test    eax, eax
0x180065247  js      loc_180065306
0x18006524d  lea     rdx, [rbp+10h+SourceString]; SourceString
0x180065251  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x180065256  call    cs:__imp_RtlInitUnicodeString
0x18006525d  nop     dword ptr [rax+rax+00h]
0x180065262  mov     ecx, 1
0x180065267  xor     eax, eax
0x180065269  lock cmpxchg cs:g_LoggedMrtId, ecx
0x180065271  jnz     loc_180065306
0x180065277  mov     eax, cs:dword_180049128
0x18006527d  cmp     eax, 5
0x180065280  jbe     loc_180065306
0x180065286  mov     rdx, 800000000000h
0x180065290  lea     rcx, dword_180049128
0x180065297  call    _tlgKeywordOn
0x18006529c  test    al, al
0x18006529e  jz      short loc_180065306
0x1800652a0  lea     rax, [rsp+110h+var_D0]
0x1800652a5  mov     [rsp+110h+var_D0], 800h
0x1800652ae  mov     [rbp+10h+var_90], rax
0x1800652b2  lea     rdx, byte_18003D4AF
0x1800652b9  lea     rax, [rbp+10h+var_68]
0x1800652bd  mov     [rbp+10h+var_88], 8
0x1800652c5  mov     [rbp+10h+var_80], rax
0x1800652c9  xor     r9d, r9d
0x1800652cc  mov     rax, [rsp+110h+DestinationString.Buffer]
0x1800652d1  xor     r8d, r8d
0x1800652d4  mov     [rbp+10h+var_70], rax
0x1800652d8  movzx   eax, [rsp+110h+DestinationString.Length]
0x1800652dd  mov     [rbp+10h+var_68], eax
0x1800652e0  lea     rax, [rsp+110h+var_B0]
0x1800652e5  mov     [rsp+110h+var_E8], rax
0x1800652ea  mov     dword ptr [rsp+110h+var_F0], 5
0x1800652f2  mov     [rbp+10h+var_78], 2
0x1800652fa  mov     [rbp+10h+var_64], 0
0x180065301  call    _tlgWriteTransfer_EtwWriteTransfer
0x180065306  mov     rcx, [rbp+10h+var_10]
0x18006530a  xor     rcx, rsp; StackCookie
0x18006530d  call    __security_check_cookie
0x180065312  add     rsp, 110h
0x180065319  pop     rbp
0x18006531a  retn
```
