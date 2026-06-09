# GetIpv6AddressTable

- ea: `0x180068730`
- end: `0x1800689e9`
- name: `GetIpv6AddressTable`
- size: `697`
- prototype: `__int64 __fastcall(NET_IF_COMPARTMENT_ID CompartmentId, PMIB_UNICASTIPADDRESS_TABLE *Table)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180068de0`

## callees

- `0x180068730`
- `0x180069984`
- `0x180071cec`
- `0x1800759b8`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800687eb`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180068963`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800687eb`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180068963`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800687e1`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800687e1`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18006887d`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18006887d`

## string_xrefs

- `0x180068815`: `GetIpv6AddressTable: SetCurrentThreadCompartmentId failed and returned %d`
- `0x180068864`: `GetIpv6AddressTable: SetCurrentThreadCompartmentId failed and returned %d`

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
  if ( (CompartmentId == 1 || !unk_1800CA080) && xmmword_1800CA088 == 0 && !unk_1800CA098
    || (result = NsiGetRoutingDomainIdForCompartment(CompartmentId, v9), !(_DWORD)result) )
  {
    CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
    v6 = SetCurrentThreadCompartmentId(CompartmentId);
    UnicastIpAddressTable = v6;
    if ( v6 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800CA088 + 1) )
        {
          LOWORD(v14) = 0;
          LOWORD(v10) = 0;
          FormatRRASErrorString(&v14, L"GetIpv6AddressTable: SetCurrentThreadCompartmentId failed and returned %d", v6);
          ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            *((_QWORD *)&xmmword_1800CA088 + 1),
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
        if ( unk_1800CA098 )
        {
          LOWORD(v10) = 0;
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            unk_1800CA098,
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
      if ( !*((_QWORD *)&xmmword_1800CA088 + 1) )
        goto LABEL_19;
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"GetUnicastIpAddressTable failed with error 0x%x", UnicastIpAddressTable);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800CA088 + 1),
        &v14);
    }
    else
    {
      TraceHlp("GetUnicastIpAddressTable failed with error 0x%x");
    }
    v8 = gIsIphlpEtwTracingAvailable;
    if ( !gIsIphlpEtwTracingAvailable )
      goto LABEL_20;
    if ( *((_QWORD *)&xmmword_1800CA088 + 1) )
    {
      LOWORD(v14) = 0;
      LOWORD(v10) = 0;
      FormatRRASErrorString(
        &v14,
        L"GetIpv6AddressTable: GetUnicastIpAddressTable failed and returned %d",
        UnicastIpAddressTable);
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_1800CA088 + 1),
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
0x180068730  mov     [rsp-8+arg_10], rbx
0x180068735  mov     [rsp-8+arg_18], rsi
0x18006873a  push    rbp
0x18006873b  push    rdi
0x18006873c  push    r14
0x18006873e  lea     rbp, [rsp-7A0h]
0x180068746  sub     rsp, 8A0h
0x18006874d  mov     rax, cs:__security_cookie
0x180068754  xor     rax, rsp
0x180068757  mov     [rbp+7B0h+var_20], rax
0x18006875e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180068765  mov     rsi, rdx
0x180068768  mov     ebx, ecx
0x18006876a  xor     r14d, r14d
0x18006876d  lea     rcx, [rbp+7B0h+var_81C]; void *
0x180068771  xor     edx, edx; Val
0x180068773  mov     [rbp+7B0h+var_820], r14d
0x180068777  mov     r8d, 7FCh; Size
0x18006877d  movdqu  [rsp+8B0h+var_870], xmm0
0x180068783  call    memset_0
0x180068788  xorps   xmm0, xmm0
0x18006878b  mov     [rsp+8B0h+var_850], r14d
0x180068790  xor     eax, eax
0x180068792  mov     [rbp+7B0h+var_82C], eax
0x180068795  movups  [rsp+8B0h+var_84C], xmm0
0x18006879a  movups  [rsp+8B0h+var_83C], xmm0
0x18006879f  movups  [rsp+8B0h+var_860], xmm0
0x1800687a4  cmp     ebx, 1
0x1800687a7  jz      short loc_1800687B2
0x1800687a9  cmp     qword ptr cs:unk_1800CA080, r14
0x1800687b0  jnz     short loc_1800687CD
0x1800687b2  cmp     qword ptr cs:xmmword_1800CA088, r14
0x1800687b9  jnz     short loc_1800687CD
0x1800687bb  cmp     qword ptr cs:xmmword_1800CA088+8, r14
0x1800687c2  jnz     short loc_1800687CD
0x1800687c4  cmp     qword ptr cs:unk_1800CA098, r14
0x1800687cb  jz      short loc_1800687E1
0x1800687cd  lea     rdx, [rsp+8B0h+var_870]
0x1800687d2  mov     ecx, ebx
0x1800687d4  call    NsiGetRoutingDomainIdForCompartment
0x1800687d9  test    eax, eax
0x1800687db  jnz     loc_1800689C2
0x1800687e1  call    cs:__imp_GetCurrentThreadCompartmentId
0x1800687e7  mov     ecx, ebx; CompartmentId
0x1800687e9  mov     edi, eax
0x1800687eb  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800687f1  mov     ebx, eax
0x1800687f3  test    eax, eax
0x1800687f5  jz      short loc_180068875
0x1800687f7  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x1800687fe  jz      short loc_180068862
0x180068800  cmp     qword ptr cs:xmmword_1800CA088+8, r14
0x180068807  jz      loc_180068969
0x18006880d  mov     r8d, eax
0x180068810  mov     word ptr [rbp+7B0h+var_820], r14w
0x180068815  lea     rdx, aGetipv6address_4; "GetIpv6AddressTable: SetCurrentThreadCo"...
0x18006881c  mov     word ptr [rsp+8B0h+var_850], r14w
0x180068822  lea     rcx, [rbp+7B0h+var_820]
0x180068826  call    FormatRRASErrorString
0x18006882b  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x180068832  lea     rax, [rsp+8B0h+var_850]
0x180068837  mov     rcx, cs:gIphlpEtwContext
0x18006883e  lea     r9, [rsp+8B0h+var_870]
0x180068843  mov     [rsp+8B0h+var_888], rax
0x180068848  lea     r8, [rbp+7B0h+var_820]
0x18006884c  mov     rax, cs:gIphlpParamTemplateFunc
0x180068853  mov     [rsp+8B0h+var_890], r14
0x180068858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006885d  jmp     loc_180068969
0x180068862  mov     edx, eax
0x180068864  lea     rcx, aGetipv6address_1; "GetIpv6AddressTable: SetCurrentThreadCo"...
0x18006886b  call    TraceHlp
0x180068870  jmp     loc_180068969
0x180068875  mov     ecx, 17h; Family
0x18006887a  mov     rdx, rsi; Table
0x18006887d  call    cs:__imp_GetUnicastIpAddressTable
0x180068883  mov     ebx, eax
0x180068885  test    eax, eax
0x180068887  jz      loc_180068961
0x18006888d  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x180068893  test    eax, eax
0x180068895  jz      short loc_1800688DC
0x180068897  cmp     qword ptr cs:xmmword_1800CA088+8, r14
0x18006889e  jz      loc_18006894F
0x1800688a4  mov     r8d, ebx
0x1800688a7  mov     word ptr [rbp+7B0h+var_820], r14w
0x1800688ac  lea     rdx, aGetunicastipad_0; "GetUnicastIpAddressTable failed with er"...
0x1800688b3  lea     rcx, [rbp+7B0h+var_820]
0x1800688b7  call    FormatRRASErrorString
0x1800688bc  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x1800688c3  lea     r8, [rbp+7B0h+var_820]
0x1800688c7  mov     rcx, cs:gIphlpEtwContext
0x1800688ce  mov     rax, cs:gIphlpTemplateFunc
0x1800688d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688da  jmp     short loc_1800688EA
0x1800688dc  mov     edx, ebx
0x1800688de  lea     rcx, aGetunicastipad; "GetUnicastIpAddressTable failed with er"...
0x1800688e5  call    TraceHlp
0x1800688ea  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x1800688f0  test    eax, eax
0x1800688f2  jz      short loc_180068953
0x1800688f4  cmp     qword ptr cs:xmmword_1800CA088+8, r14
0x1800688fb  jz      short loc_18006894F
0x1800688fd  mov     r8d, ebx
0x180068900  mov     word ptr [rbp+7B0h+var_820], r14w
0x180068905  lea     rdx, aGetipv6address; "GetIpv6AddressTable: GetUnicastIpAddres"...
0x18006890c  mov     word ptr [rsp+8B0h+var_850], r14w
0x180068912  lea     rcx, [rbp+7B0h+var_820]
0x180068916  call    FormatRRASErrorString
0x18006891b  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x180068922  lea     rax, [rsp+8B0h+var_850]
0x180068927  mov     rcx, cs:gIphlpEtwContext
0x18006892e  lea     r9, [rsp+8B0h+var_870]
0x180068933  mov     [rsp+8B0h+var_888], rax
0x180068938  lea     r8, [rbp+7B0h+var_820]
0x18006893c  mov     rax, cs:gIphlpParamTemplateFunc
0x180068943  mov     [rsp+8B0h+var_890], r14
0x180068948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006894d  jmp     short loc_180068961
0x18006894f  test    eax, eax
0x180068951  jnz     short loc_180068961
0x180068953  mov     edx, ebx
0x180068955  lea     rcx, aGetipv6address_0; "GetIpv6AddressTable: GetUnicastIpAddres"...
0x18006895c  call    TraceHlp
0x180068961  mov     ecx, edi; CompartmentId
0x180068963  call    cs:__imp_SetCurrentThreadCompartmentId
0x180068969  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180068970  jz      short loc_1800689B4
0x180068972  mov     rdx, qword ptr cs:unk_1800CA098
0x180068979  test    rdx, rdx
0x18006897c  jz      short loc_1800689C0
0x18006897e  mov     rcx, cs:gIphlpEtwContext
0x180068985  lea     rax, [rsp+8B0h+var_850]
0x18006898a  mov     [rsp+8B0h+var_888], rax
0x18006898f  lea     r9, [rsp+8B0h+var_870]
0x180068994  mov     rax, cs:gIphlpParamTemplateFunc
0x18006899b  lea     r8, aGetipv6address_3; "GetIpv6AddressTable End"
0x1800689a2  mov     word ptr [rsp+8B0h+var_850], r14w
0x1800689a8  mov     [rsp+8B0h+var_890], r14
0x1800689ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689b2  jmp     short loc_1800689C0
0x1800689b4  lea     rcx, aGetipv6address_2; "GetIpv6AddressTable End"
0x1800689bb  call    TraceHlp
0x1800689c0  mov     eax, ebx
0x1800689c2  mov     rcx, [rbp+7B0h+var_20]
0x1800689c9  xor     rcx, rsp; StackCookie
0x1800689cc  call    __security_check_cookie
0x1800689d1  lea     r11, [rsp+8B0h+var_10]
0x1800689d9  mov     rbx, [r11+30h]
0x1800689dd  mov     rsi, [r11+38h]
0x1800689e1  mov     rsp, r11
0x1800689e4  pop     r14
0x1800689e6  pop     rdi
0x1800689e7  pop     rbp
0x1800689e8  retn
```
