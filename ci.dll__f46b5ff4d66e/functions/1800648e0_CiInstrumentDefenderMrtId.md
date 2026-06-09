# CiInstrumentDefenderMrtId

- ea: `0x1800648e0`
- end: `0x180064a28`
- name: `CiInstrumentDefenderMrtId`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800683e0`

## callees

- `0x18000f3bc`
- `0x18000fb30`
- `0x18002bef0`
- `0x18002c340`
- `0x180059ed0`
- `0x1800648e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180064962`
- `ntoskrnl!RtlInitUnicodeString` at `0x180064962`

## string_xrefs

- `0x18006493e`: `\Registry\Machine\SOFTWARE\Microsoft\RemovalTools\MRT`

## pseudocode

```c
NTSTATUS CiInstrumentDefenderMrtId()
{
  NTSTATUS result; // eax
  __int64 v1; // rcx
  __int64 v2; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v5; // [rsp+80h] [rbp-80h]
  __int64 v6; // [rsp+88h] [rbp-78h]
  _DWORD *v7; // [rsp+90h] [rbp-70h]
  __int64 v8; // [rsp+98h] [rbp-68h]
  PWSTR Buffer; // [rsp+A0h] [rbp-60h]
  _DWORD v10[2]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SourceString[40]; // [rsp+B0h] [rbp-50h] BYREF

  LODWORD(v2) = 0;
  DestinationString = 0;
  memset(SourceString, 0, 0x4Eu);
  result = CipGetRegistryValue(
             0,
             L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\RemovalTools\\MRT",
             (__int64)L"GUID",
             2,
             (__int64)SourceString,
             78,
             (__int64)&v2);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    result = _InterlockedCompareExchange(&g_LoggedMrtId, 1, 0);
    if ( !result )
    {
      result = dword_180048128;
      if ( (unsigned int)dword_180048128 > 5 )
      {
        result = tlgKeywordOn(&dword_180048128, 0x800000000000LL);
        if ( (_BYTE)result )
        {
          v2 = 2048;
          v5 = &v2;
          v6 = 8;
          v7 = v10;
          Buffer = DestinationString.Buffer;
          v10[0] = DestinationString.Length;
          v8 = 2;
          v10[1] = 0;
          return tlgWriteTransfer_EtwWriteTransfer(v1, (unsigned __int8 *)byte_18003D0AB, 0, 0, 5u, &v4);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800648e0  push    rbp
0x1800648e2  lea     rbp, [rsp-10h]
0x1800648e7  sub     rsp, 110h
0x1800648ee  mov     rax, cs:__security_cookie
0x1800648f5  xor     rax, rsp
0x1800648f8  mov     [rbp+10h+var_10], rax
0x1800648fc  xor     edx, edx; Val
0x1800648fe  mov     dword ptr [rsp+110h+var_D0], 0
0x180064906  xorps   xmm0, xmm0
0x180064909  lea     rcx, [rbp+10h+SourceString]; void *
0x18006490d  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x180064912  lea     r8d, [rdx+4Eh]; Size
0x180064916  call    memset
0x18006491b  lea     rax, [rsp+110h+var_D0]
0x180064920  mov     r9d, 2
0x180064926  mov     [rsp+110h+var_E0], rax
0x18006492b  lea     r8, aGuid; "GUID"
0x180064932  lea     rax, [rbp+10h+SourceString]
0x180064936  mov     dword ptr [rsp+110h+var_E8], 4Eh ; 'N'
0x18006493e  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180064945  mov     [rsp+110h+var_F0], rax
0x18006494a  xor     ecx, ecx
0x18006494c  call    CipGetRegistryValue
0x180064951  test    eax, eax
0x180064953  js      loc_180064A12
0x180064959  lea     rdx, [rbp+10h+SourceString]; SourceString
0x18006495d  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x180064962  call    cs:__imp_RtlInitUnicodeString
0x180064969  nop     dword ptr [rax+rax+00h]
0x18006496e  mov     ecx, 1
0x180064973  xor     eax, eax
0x180064975  lock cmpxchg cs:g_LoggedMrtId, ecx
0x18006497d  jnz     loc_180064A12
0x180064983  mov     eax, cs:dword_180048128
0x180064989  cmp     eax, 5
0x18006498c  jbe     loc_180064A12
0x180064992  mov     rdx, 800000000000h
0x18006499c  lea     rcx, dword_180048128
0x1800649a3  call    _tlgKeywordOn
0x1800649a8  test    al, al
0x1800649aa  jz      short loc_180064A12
0x1800649ac  lea     rax, [rsp+110h+var_D0]
0x1800649b1  mov     [rsp+110h+var_D0], 800h
0x1800649ba  mov     [rbp+10h+var_90], rax
0x1800649be  lea     rdx, byte_18003D0AB
0x1800649c5  lea     rax, [rbp+10h+var_68]
0x1800649c9  mov     [rbp+10h+var_88], 8
0x1800649d1  mov     [rbp+10h+var_80], rax
0x1800649d5  xor     r9d, r9d
0x1800649d8  mov     rax, [rsp+110h+DestinationString.Buffer]
0x1800649dd  xor     r8d, r8d
0x1800649e0  mov     [rbp+10h+var_70], rax
0x1800649e4  movzx   eax, [rsp+110h+DestinationString.Length]
0x1800649e9  mov     [rbp+10h+var_68], eax
0x1800649ec  lea     rax, [rsp+110h+var_B0]
0x1800649f1  mov     [rsp+110h+var_E8], rax
0x1800649f6  mov     dword ptr [rsp+110h+var_F0], 5
0x1800649fe  mov     [rbp+10h+var_78], 2
0x180064a06  mov     [rbp+10h+var_64], 0
0x180064a0d  call    _tlgWriteTransfer_EtwWriteTransfer
0x180064a12  mov     rcx, [rbp+10h+var_10]
0x180064a16  xor     rcx, rsp; StackCookie
0x180064a19  call    __security_check_cookie
0x180064a1e  add     rsp, 110h
0x180064a25  pop     rbp
0x180064a26  retn
```
