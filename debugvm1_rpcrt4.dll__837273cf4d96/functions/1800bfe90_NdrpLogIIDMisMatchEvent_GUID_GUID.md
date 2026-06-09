# NdrpLogIIDMisMatchEvent(_GUID *,_GUID *)

- ea: `0x1800bfe90`
- end: `0x1800bffaa`
- name: `?NdrpLogIIDMisMatchEvent@@YAXPEFAU_GUID@@PEAU1@@Z`
- size: `282`
- prototype: `void(struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002c000`
- `0x180084710`
- `0x1800bfe90`
- `0x1800c0200`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x1800bff3a`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800bff3a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800bff49`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800bff49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bff2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bff2c`

## pseudocode

```c
void __fastcall NdrpLogIIDMisMatchEvent(struct _GUID *a1, struct _GUID *a2)
{
  UUID v3; // xmm1
  RPC_WSTR v4; // rdi
  RPC_WSTR v5; // rbx
  ULONG CurrentProcessId; // eax
  unsigned int CommandLineW; // eax
  int v8; // edx
  int v9; // ecx
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-50h] BYREF
  RPC_WSTR v11; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING String; // [rsp+40h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v14[24]; // [rsp+60h] [rbp-20h] BYREF

  if ( !byte_1800FA466 )
  {
    v3 = *a1;
    StringUuid = 0;
    v11 = 0;
    Uuid = v3;
    String = 0;
    if ( !UuidToStringW(&Uuid, &StringUuid) )
    {
      v4 = StringUuid;
      if ( StringUuid )
      {
        if ( UuidToStringW(a2, &v11) || (v5 = v11) == 0 )
        {
          RpcStringFreeW(&StringUuid);
        }
        else
        {
          *(_DWORD *)&String.Length = 1441792;
          String.Buffer = (PWSTR)v14;
          CurrentProcessId = GetCurrentProcessId();
          RtlIntegerToUnicodeString(CurrentProcessId, 0, &String);
          if ( (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
          {
            CommandLineW = (unsigned int)GetCommandLineW();
            McTemplateU0zzzz_EtwEventWriteTransfer(v9, v8, CommandLineW, (unsigned int)v14, (__int64)v4, (__int64)v5);
          }
          RpcStringFreeW(&StringUuid);
          RpcStringFreeW(&v11);
          byte_1800FA466 = 1;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800bfe90  mov     [rsp-8+arg_10], rbx
0x1800bfe95  mov     [rsp-8+arg_18], rdi
0x1800bfe9a  push    rbp
0x1800bfe9b  mov     rbp, rsp
0x1800bfe9e  sub     rsp, 80h
0x1800bfea5  mov     rax, cs:__security_cookie
0x1800bfeac  xor     rax, rsp
0x1800bfeaf  mov     [rbp+var_8], rax
0x1800bfeb3  cmp     cs:byte_1800FA466, 0
0x1800bfeba  mov     rbx, rdx
0x1800bfebd  jnz     loc_1800BFF89
0x1800bfec3  movups  xmm1, xmmword ptr [rcx]
0x1800bfec6  mov     [rbp+StringUuid], 0
0x1800bfece  lea     rdx, [rbp+StringUuid]; StringUuid
0x1800bfed2  xorps   xmm0, xmm0
0x1800bfed5  mov     [rbp+var_48], 0
0x1800bfedd  lea     rcx, [rbp+Uuid]; Uuid
0x1800bfee1  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm1
0x1800bfee6  movups  xmmword ptr [rbp+String.Length], xmm0
0x1800bfeea  call    UuidToStringW
0x1800bfeef  test    eax, eax
0x1800bfef1  jnz     loc_1800BFF89
0x1800bfef7  mov     rdi, [rbp+StringUuid]
0x1800bfefb  test    rdi, rdi
0x1800bfefe  jz      loc_1800BFF89
0x1800bff04  lea     rdx, [rbp+var_48]; StringUuid
0x1800bff08  mov     rcx, rbx; Uuid
0x1800bff0b  call    UuidToStringW
0x1800bff10  test    eax, eax
0x1800bff12  jnz     short loc_1800BFF80
0x1800bff14  mov     rbx, [rbp+var_48]
0x1800bff18  test    rbx, rbx
0x1800bff1b  jz      short loc_1800BFF80
0x1800bff1d  lea     rax, [rbp+var_20]
0x1800bff21  mov     dword ptr [rbp+String.Length], 160000h
0x1800bff28  mov     [rbp+String.Buffer], rax
0x1800bff2c  call    cs:__imp_GetCurrentProcessId
0x1800bff32  lea     r8, [rbp+String]; String
0x1800bff36  xor     edx, edx; Base
0x1800bff38  mov     ecx, eax; Value
0x1800bff3a  call    cs:__imp_RtlIntegerToUnicodeString
0x1800bff40  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800bff47  jz      short loc_1800BFF65
0x1800bff49  call    cs:__imp_GetCommandLineW
0x1800bff4f  mov     [rsp+80h+var_58], rbx
0x1800bff54  lea     r9, [rbp+var_20]
0x1800bff58  mov     r8, rax
0x1800bff5b  mov     [rsp+80h+var_60], rdi
0x1800bff60  call    McTemplateU0zzzz_EtwEventWriteTransfer
0x1800bff65  lea     rcx, [rbp+StringUuid]; String
0x1800bff69  call    RpcStringFreeW
0x1800bff6e  lea     rcx, [rbp+var_48]; String
0x1800bff72  call    RpcStringFreeW
0x1800bff77  mov     cs:byte_1800FA466, 1
0x1800bff7e  jmp     short loc_1800BFF89
0x1800bff80  lea     rcx, [rbp+StringUuid]; String
0x1800bff84  call    RpcStringFreeW
0x1800bff89  mov     rcx, [rbp+var_8]
0x1800bff8d  xor     rcx, rsp; StackCookie
0x1800bff90  call    __security_check_cookie
0x1800bff95  lea     r11, [rsp+80h+var_s0]
0x1800bff9d  mov     rbx, [r11+20h]
0x1800bffa1  mov     rdi, [r11+28h]
0x1800bffa5  mov     rsp, r11
0x1800bffa8  pop     rbp
0x1800bffa9  retn
```
