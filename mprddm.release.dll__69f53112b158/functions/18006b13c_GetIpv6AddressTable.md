# GetIpv6AddressTable

- ea: `0x18006b13c`
- end: `0x18006b40e`
- name: `GetIpv6AddressTable`
- size: `722`
- prototype: `__int64 __fastcall(NET_IF_COMPARTMENT_ID CompartmentId, PMIB_UNICASTIPADDRESS_TABLE *Table)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006b810`

## callees

- `0x18006b13c`
- `0x18006c3c4`
- `0x1800755b8`
- `0x180079774`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006b1fd`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006b381`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006b1fd`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18006b381`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006b1ed`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18006b1ed`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18006b295`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18006b295`

## string_xrefs

- `0x18006b22d`: `GetIpv6AddressTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x18006b27c`: `GetIpv6AddressTable: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall GetIpv6AddressTable(NET_IF_COMPARTMENT_ID CompartmentId, PMIB_UNICASTIPADDRESS_TABLE *Table)
{
  __int64 result; // rax
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // edi
  unsigned int v6; // eax
  unsigned int UnicastIpAddressTable; // ebx
  int v8; // eax
  _OWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v11; // [rsp+64h] [rbp-9Ch]
  __int128 v12; // [rsp+74h] [rbp-8Ch]
  int v13; // [rsp+84h] [rbp-7Ch]
  int v14; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v15[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v14 = 0;
  memset(v9, 0, sizeof(v9));
  memset_0(v15, 0, sizeof(v15));
  v10 = 0;
  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( (CompartmentId == 1 || !unk_1800D1080) && xmmword_1800D1088 == 0 && !unk_1800D1098
    || (result = NsiGetRoutingDomainIdForCompartment(CompartmentId, v9), !(_DWORD)result) )
  {
    CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
    v6 = SetCurrentThreadCompartmentId(CompartmentId);
    UnicastIpAddressTable = v6;
    if ( v6 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800D1088 + 1) )
        {
          LOWORD(v14) = 0;
          LOWORD(v10) = 0;
          FormatRRASErrorString(&v14, L"GetIpv6AddressTable: SetCurrentThreadCompartmentId failed and returned %d", v6);
          ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            *((_QWORD *)&xmmword_1800D1088 + 1),
            &v14,
            v9,
            0,
            &v10);
        }
      }
      else
      {
        TraceHlp("GetIpv6AddressTable: SetCurrentThreadCompartmentId failed and returned %d");
      }
      goto LABEL_22;
    }
    UnicastIpAddressTable = GetUnicastIpAddressTable(0x17u, Table);
    if ( !UnicastIpAddressTable )
    {
LABEL_21:
      SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
LABEL_22:
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( unk_1800D1098 )
        {
          LOWORD(v10) = 0;
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            unk_1800D1098,
            L"GetIpv6AddressTable End",
            v9,
            0,
            &v10);
        }
      }
      else
      {
        TraceHlp("GetIpv6AddressTable End");
      }
      return UnicastIpAddressTable;
    }
    v8 = gIsIphlpEtwTracingAvailable;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_1800D1088 + 1) )
        goto LABEL_19;
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"GetUnicastIpAddressTable failed with error 0x%x", UnicastIpAddressTable);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800D1088 + 1),
        &v14);
    }
    else
    {
      TraceHlp("GetUnicastIpAddressTable failed with error 0x%x");
    }
    v8 = gIsIphlpEtwTracingAvailable;
    if ( !gIsIphlpEtwTracingAvailable )
      goto LABEL_20;
    if ( *((_QWORD *)&xmmword_1800D1088 + 1) )
    {
      LOWORD(v14) = 0;
      LOWORD(v10) = 0;
      FormatRRASErrorString(
        &v14,
        L"GetIpv6AddressTable: GetUnicastIpAddressTable failed and returned %d",
        UnicastIpAddressTable);
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800D1088 + 1),
        &v14,
        v9,
        0,
        &v10);
      goto LABEL_21;
    }
LABEL_19:
    if ( v8 )
      goto LABEL_21;
LABEL_20:
    TraceHlp("GetIpv6AddressTable: GetUnicastIpAddressTable failed and returned %d");
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x18006b13c  mov     [rsp-8+arg_10], rbx
0x18006b141  mov     [rsp-8+arg_18], rsi
0x18006b146  push    rbp
0x18006b147  push    rdi
0x18006b148  push    r14
0x18006b14a  lea     rbp, [rsp-7A0h]
0x18006b152  sub     rsp, 8A0h
0x18006b159  mov     rax, cs:__security_cookie
0x18006b160  xor     rax, rsp
0x18006b163  mov     [rbp+7B0h+var_20], rax
0x18006b16a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006b171  mov     rsi, rdx
0x18006b174  mov     ebx, ecx
0x18006b176  xor     r14d, r14d
0x18006b179  lea     rcx, [rbp+7B0h+var_81C]; void *
0x18006b17d  xor     edx, edx; Val
0x18006b17f  mov     [rbp+7B0h+var_820], r14d
0x18006b183  mov     r8d, 7FCh; Size
0x18006b189  movdqu  [rsp+8B0h+var_870], xmm0
0x18006b18f  call    memset_0
0x18006b194  xorps   xmm0, xmm0
0x18006b197  mov     [rsp+8B0h+var_850], r14d
0x18006b19c  xor     eax, eax
0x18006b19e  mov     [rbp+7B0h+var_82C], eax
0x18006b1a1  movups  [rsp+8B0h+var_84C], xmm0
0x18006b1a6  movups  [rsp+8B0h+var_83C], xmm0
0x18006b1ab  movups  [rsp+8B0h+var_860], xmm0
0x18006b1b0  cmp     ebx, 1
0x18006b1b3  jz      short loc_18006B1BE
0x18006b1b5  cmp     qword ptr cs:unk_1800D1080, r14
0x18006b1bc  jnz     short loc_18006B1D9
0x18006b1be  cmp     qword ptr cs:xmmword_1800D1088, r14
0x18006b1c5  jnz     short loc_18006B1D9
0x18006b1c7  cmp     qword ptr cs:xmmword_1800D1088+8, r14
0x18006b1ce  jnz     short loc_18006B1D9
0x18006b1d0  cmp     qword ptr cs:unk_1800D1098, r14
0x18006b1d7  jz      short loc_18006B1ED
0x18006b1d9  lea     rdx, [rsp+8B0h+var_870]
0x18006b1de  mov     ecx, ebx
0x18006b1e0  call    NsiGetRoutingDomainIdForCompartment
0x18006b1e5  test    eax, eax
0x18006b1e7  jnz     loc_18006B3E6
0x18006b1ed  call    cs:__imp_GetCurrentThreadCompartmentId
0x18006b1f4  nop     dword ptr [rax+rax+00h]
0x18006b1f9  mov     ecx, ebx; CompartmentId
0x18006b1fb  mov     edi, eax
0x18006b1fd  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006b204  nop     dword ptr [rax+rax+00h]
0x18006b209  mov     ebx, eax
0x18006b20b  test    eax, eax
0x18006b20d  jz      short loc_18006B28D
0x18006b20f  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006b216  jz      short loc_18006B27A
0x18006b218  cmp     qword ptr cs:xmmword_1800D1088+8, r14
0x18006b21f  jz      loc_18006B38D
0x18006b225  mov     r8d, eax
0x18006b228  mov     word ptr [rbp+7B0h+var_820], r14w
0x18006b22d  lea     rdx, aGetipv6address_4; "GetIpv6AddressTable: SetCurrentThreadCo"...
0x18006b234  mov     word ptr [rsp+8B0h+var_850], r14w
0x18006b23a  lea     rcx, [rbp+7B0h+var_820]
0x18006b23e  call    FormatRRASErrorString
0x18006b243  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006b24a  lea     rax, [rsp+8B0h+var_850]
0x18006b24f  mov     rcx, cs:gIphlpEtwContext
0x18006b256  lea     r9, [rsp+8B0h+var_870]
0x18006b25b  mov     [rsp+8B0h+var_888], rax
0x18006b260  lea     r8, [rbp+7B0h+var_820]
0x18006b264  mov     rax, cs:gIphlpParamTemplateFunc
0x18006b26b  mov     [rsp+8B0h+var_890], r14
0x18006b270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b275  jmp     loc_18006B38D
0x18006b27a  mov     edx, eax
0x18006b27c  lea     rcx, aGetipv6address_1; "GetIpv6AddressTable: SetCurrentThreadCo"...
0x18006b283  call    TraceHlp
0x18006b288  jmp     loc_18006B38D
0x18006b28d  mov     ecx, 17h; Family
0x18006b292  mov     rdx, rsi; Table
0x18006b295  call    cs:__imp_GetUnicastIpAddressTable
0x18006b29c  nop     dword ptr [rax+rax+00h]
0x18006b2a1  mov     ebx, eax
0x18006b2a3  test    eax, eax
0x18006b2a5  jz      loc_18006B37F
0x18006b2ab  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006b2b1  test    eax, eax
0x18006b2b3  jz      short loc_18006B2FA
0x18006b2b5  cmp     qword ptr cs:xmmword_1800D1088+8, r14
0x18006b2bc  jz      loc_18006B36D
0x18006b2c2  mov     r8d, ebx
0x18006b2c5  mov     word ptr [rbp+7B0h+var_820], r14w
0x18006b2ca  lea     rdx, aGetunicastipad_0; "GetUnicastIpAddressTable failed with er"...
0x18006b2d1  lea     rcx, [rbp+7B0h+var_820]
0x18006b2d5  call    FormatRRASErrorString
0x18006b2da  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006b2e1  lea     r8, [rbp+7B0h+var_820]
0x18006b2e5  mov     rcx, cs:gIphlpEtwContext
0x18006b2ec  mov     rax, cs:gIphlpTemplateFunc
0x18006b2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2f8  jmp     short loc_18006B308
0x18006b2fa  mov     edx, ebx
0x18006b2fc  lea     rcx, aGetunicastipad; "GetUnicastIpAddressTable failed with er"...
0x18006b303  call    TraceHlp
0x18006b308  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006b30e  test    eax, eax
0x18006b310  jz      short loc_18006B371
0x18006b312  cmp     qword ptr cs:xmmword_1800D1088+8, r14
0x18006b319  jz      short loc_18006B36D
0x18006b31b  mov     r8d, ebx
0x18006b31e  mov     word ptr [rbp+7B0h+var_820], r14w
0x18006b323  lea     rdx, aGetipv6address; "GetIpv6AddressTable: GetUnicastIpAddres"...
0x18006b32a  mov     word ptr [rsp+8B0h+var_850], r14w
0x18006b330  lea     rcx, [rbp+7B0h+var_820]
0x18006b334  call    FormatRRASErrorString
0x18006b339  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006b340  lea     rax, [rsp+8B0h+var_850]
0x18006b345  mov     rcx, cs:gIphlpEtwContext
0x18006b34c  lea     r9, [rsp+8B0h+var_870]
0x18006b351  mov     [rsp+8B0h+var_888], rax
0x18006b356  lea     r8, [rbp+7B0h+var_820]
0x18006b35a  mov     rax, cs:gIphlpParamTemplateFunc
0x18006b361  mov     [rsp+8B0h+var_890], r14
0x18006b366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b36b  jmp     short loc_18006B37F
0x18006b36d  test    eax, eax
0x18006b36f  jnz     short loc_18006B37F
0x18006b371  mov     edx, ebx
0x18006b373  lea     rcx, aGetipv6address_0; "GetIpv6AddressTable: GetUnicastIpAddres"...
0x18006b37a  call    TraceHlp
0x18006b37f  mov     ecx, edi; CompartmentId
0x18006b381  call    cs:__imp_SetCurrentThreadCompartmentId
0x18006b388  nop     dword ptr [rax+rax+00h]
0x18006b38d  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18006b394  jz      short loc_18006B3D8
0x18006b396  mov     rdx, qword ptr cs:unk_1800D1098
0x18006b39d  test    rdx, rdx
0x18006b3a0  jz      short loc_18006B3E4
0x18006b3a2  mov     rcx, cs:gIphlpEtwContext
0x18006b3a9  lea     rax, [rsp+8B0h+var_850]
0x18006b3ae  mov     [rsp+8B0h+var_888], rax
0x18006b3b3  lea     r9, [rsp+8B0h+var_870]
0x18006b3b8  mov     rax, cs:gIphlpParamTemplateFunc
0x18006b3bf  lea     r8, aGetipv6address_3; "GetIpv6AddressTable End"
0x18006b3c6  mov     word ptr [rsp+8B0h+var_850], r14w
0x18006b3cc  mov     [rsp+8B0h+var_890], r14
0x18006b3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3d6  jmp     short loc_18006B3E4
0x18006b3d8  lea     rcx, aGetipv6address_2; "GetIpv6AddressTable End"
0x18006b3df  call    TraceHlp
0x18006b3e4  mov     eax, ebx
0x18006b3e6  mov     rcx, [rbp+7B0h+var_20]
0x18006b3ed  xor     rcx, rsp; StackCookie
0x18006b3f0  call    __security_check_cookie
0x18006b3f5  lea     r11, [rsp+8B0h+var_10]
0x18006b3fd  mov     rbx, [r11+30h]
0x18006b401  mov     rsi, [r11+38h]
0x18006b405  mov     rsp, r11
0x18006b408  pop     r14
0x18006b40a  pop     rdi
0x18006b40b  pop     rbp
0x18006b40c  retn
```
