# FwStaticFwPortDecode

- ea: `0x180012288`
- end: `0x180012501`
- name: `FwStaticFwPortDecode`
- size: `633`
- prototype: `__int64 __fastcall(wchar_t *String, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bce0`

## callees

- `0x1800047e0`
- `0x180012288`
- `0x180012508`
- `0x180012904`
- `0x18001e1d0`
- `0x18001eb54`
- `0x18002a6e8`
- `0x18002b38c`
- `0x18002b538`
- `0x18002c2c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012361`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012361`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180012301`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180012301`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180012320`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180012320`

## string_xrefs

- `0x18001238d`: `FwExtractIpProtocol`
- `0x18001239c`: `FwExtractIpProtocol`

## pseudocode

```c
__int64 __fastcall FwStaticFwPortDecode(wchar_t *String, _OWORD *a2)
{
  unsigned int v4; // eax
  int v5; // ebx
  wchar_t *v6; // rdi
  int SubNets; // eax
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  int ServiceType; // eax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  unsigned __int16 *v15[2]; // [rsp+20h] [rbp-60h] BYREF
  _OWORD v16[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v17; // [rsp+50h] [rbp-30h] BYREF
  __int64 v18; // [rsp+60h] [rbp-20h]
  wchar_t *EndPtr; // [rsp+70h] [rbp-10h] BYREF

  EndPtr = 0;
  memset_0(v15, 0, 0x48u);
  if ( !String )
  {
    v5 = -2147467261;
    v9 = 2147500035LL;
    goto LABEL_14;
  }
  memset_0(a2, 0, 0x48u);
  *((_DWORD *)a2 + 3) = 6;
  *((_DWORD *)a2 + 14) = 1;
  *((_DWORD *)a2 + 16) = 1;
  if ( (unsigned int)_o_iswdigit(*String) && (v4 = wcstoul(String, &EndPtr, 10), v4 - 1 <= 0xFFFE) )
  {
    LOWORD(v15[1]) = v4;
    v5 = 0;
  }
  else
  {
    FwReportReturnError("FwExtractPortNumber", 2147942413LL);
    SubNets = FwReportReturnError("FwExtractPortNumber", 2147942413LL);
    v5 = SubNets;
    if ( SubNets < 0 )
      goto LABEL_13;
  }
  v6 = EndPtr;
  if ( !*EndPtr )
    goto LABEL_19;
  if ( *EndPtr == 58 && !(unsigned int)_o__wcsnicmp(EndPtr + 1, L"TCP", 3) )
  {
    v8 = v6 + 4;
    HIDWORD(v15[1]) = 6;
    EndPtr = v6 + 4;
LABEL_18:
    v5 = 0;
    goto LABEL_11;
  }
  if ( (unsigned int)FwIsNextToken(v6, L"UDP", (const unsigned __int16 **)&EndPtr) )
  {
    v8 = EndPtr;
    HIDWORD(v15[1]) = 17;
    goto LABEL_18;
  }
  FwReportReturnError("FwExtractIpProtocol", 2147942413LL);
  SubNets = FwReportReturnError("FwExtractIpProtocol", 2147942413LL);
  v5 = SubNets;
  if ( SubNets >= 0 )
  {
    v8 = EndPtr;
LABEL_11:
    if ( !*v8
      || (SubNets = FwExtractSubNets(v8, (struct ICF_AUTHBYPASS_SUBNETS_ *)v16, (const unsigned __int16 **)&EndPtr),
          v5 = SubNets,
          SubNets >= 0)
      && (!*EndPtr
       || (SubNets = FwExtractEnabled(EndPtr, (int *)&v17 + 2, (const unsigned __int16 **)&EndPtr),
           v5 = SubNets,
           SubNets >= 0)
       && (!*EndPtr || (SubNets = FwExtractName(EndPtr, v15), v5 = SubNets, SubNets >= 0))) )
    {
LABEL_19:
      ServiceType = FwGetServiceType(HIDWORD(v15[1]), LOWORD(v15[1]));
      v12 = v16[0];
      *a2 = *(_OWORD *)v15;
      HIDWORD(v17) = ServiceType;
      v13 = v16[1];
      a2[1] = v12;
      v14 = v17;
      a2[2] = v13;
      *(_QWORD *)&v13 = v18;
      a2[3] = v14;
      *((_QWORD *)a2 + 8) = v13;
      if ( v5 >= 0 )
        return (unsigned int)v5;
      goto LABEL_15;
    }
  }
LABEL_13:
  v9 = (unsigned int)SubNets;
LABEL_14:
  FwReportReturnError("FwStaticFwPortDecode", v9);
LABEL_15:
  FwIcfAuthBypassStaticFwPortDestroy(v15);
  return (unsigned int)FwReportReturnError("FwStaticFwPortDecode", (unsigned int)v5);
}

```

## disassembly

```asm
0x180012288  mov     [rsp-28h+arg_10], rbx
0x18001228d  mov     [rsp-28h+arg_18], rsi
0x180012292  push    rbp
0x180012293  push    rdi
0x180012294  push    r12
0x180012296  push    r14
0x180012298  push    r15
0x18001229a  mov     rbp, rsp
0x18001229d  sub     rsp, 80h
0x1800122a4  mov     rax, cs:__security_cookie
0x1800122ab  xor     rax, rsp
0x1800122ae  mov     [rbp+var_8], rax
0x1800122b2  xor     r14d, r14d
0x1800122b5  mov     rsi, rdx
0x1800122b8  mov     rbx, rcx
0x1800122bb  mov     [rbp+EndPtr], r14
0x1800122bf  xor     edx, edx; Val
0x1800122c1  lea     rcx, [rbp+var_60]; void *
0x1800122c5  lea     edi, [r14+48h]
0x1800122c9  mov     r8d, edi; Size
0x1800122cc  call    memset_0
0x1800122d1  lea     r15, aFwstaticfwport_1; "FwStaticFwPortDecode"
0x1800122d8  test    rbx, rbx
0x1800122db  jz      loc_18001246D
0x1800122e1  mov     r8d, edi; Size
0x1800122e4  xor     edx, edx; Val
0x1800122e6  mov     rcx, rsi; void *
0x1800122e9  call    memset_0
0x1800122ee  lea     eax, [rdi-47h]
0x1800122f1  mov     dword ptr [rsi+0Ch], 6
0x1800122f8  mov     [rsi+38h], eax
0x1800122fb  mov     [rsi+40h], eax
0x1800122fe  movzx   ecx, word ptr [rbx]
0x180012301  call    cs:__imp__o_iswdigit
0x180012307  mov     r12d, 8007000Dh
0x18001230d  test    eax, eax
0x18001230f  jz      loc_180012479
0x180012315  lea     r8d, [r14+0Ah]; Radix
0x180012319  mov     rcx, rbx; String
0x18001231c  lea     rdx, [rbp+EndPtr]; EndPtr
0x180012320  call    cs:__imp_wcstoul
0x180012326  mov     ecx, eax
0x180012328  dec     eax
0x18001232a  cmp     eax, 0FFFEh
0x18001232f  ja      loc_180012479
0x180012335  mov     word ptr [rbp+var_60+8], cx
0x180012339  mov     ebx, r14d
0x18001233c  mov     rdi, [rbp+EndPtr]
0x180012340  cmp     [rdi], r14w
0x180012344  jz      loc_18001242C
0x18001234a  cmp     word ptr [rdi], 3Ah ; ':'
0x18001234e  jnz     short loc_18001236F
0x180012350  mov     r8d, 3
0x180012356  lea     rdx, aTcp; "TCP"
0x18001235d  lea     rcx, [rdi+2]
0x180012361  call    cs:__imp__o__wcsnicmp
0x180012367  test    eax, eax
0x180012369  jz      loc_180012418
0x18001236f  lea     r8, [rbp+EndPtr]; unsigned __int16 **
0x180012373  mov     rcx, rdi; unsigned __int16 *
0x180012376  lea     rdx, aUdp; "UDP"
0x18001237d  call    ?FwIsNextToken@@YAHPEBG0PEAPEBG@Z; FwIsNextToken(ushort const *,ushort const *,ushort const * *)
0x180012382  test    eax, eax
0x180012384  jnz     loc_1800124A6
0x18001238a  mov     edx, r12d
0x18001238d  lea     rcx, aFwextractippro; "FwExtractIpProtocol"
0x180012394  call    FwReportReturnError
0x180012399  mov     edx, r12d
0x18001239c  lea     rcx, aFwextractippro; "FwExtractIpProtocol"
0x1800123a3  call    FwReportReturnError
0x1800123a8  mov     ebx, eax
0x1800123aa  test    eax, eax
0x1800123ac  js      short loc_1800123CF
0x1800123ae  mov     rcx, [rbp+EndPtr]; unsigned __int16 *
0x1800123b2  cmp     [rcx], r14w
0x1800123b6  jz      short loc_18001242C
0x1800123b8  lea     r8, [rbp+EndPtr]; unsigned __int16 **
0x1800123bc  lea     rdx, [rbp+var_50]; struct ICF_AUTHBYPASS_SUBNETS_ *
0x1800123c0  call    ?FwExtractSubNets@@YAJPEBGPEAUICF_AUTHBYPASS_SUBNETS_@@PEAPEBG@Z; FwExtractSubNets(ushort const *,ICF_AUTHBYPASS_SUBNETS_ *,ushort const * *)
0x1800123c5  mov     ebx, eax
0x1800123c7  test    eax, eax
0x1800123c9  jns     loc_1800124B6
0x1800123cf  mov     edx, eax
0x1800123d1  mov     rcx, r15
0x1800123d4  call    FwReportReturnError
0x1800123d9  lea     rcx, [rbp+var_60]; void *
0x1800123dd  call    FwIcfAuthBypassStaticFwPortDestroy
0x1800123e2  mov     edx, ebx
0x1800123e4  mov     rcx, r15
0x1800123e7  call    FwReportReturnError
0x1800123ec  mov     ebx, eax
0x1800123ee  mov     eax, ebx
0x1800123f0  mov     rcx, [rbp+var_8]
0x1800123f4  xor     rcx, rsp; StackCookie
0x1800123f7  call    __security_check_cookie
0x1800123fc  lea     r11, [rsp+80h+var_s0]
0x180012404  mov     rbx, [r11+40h]
0x180012408  mov     rsi, [r11+48h]
0x18001240c  mov     rsp, r11
0x18001240f  pop     r15
0x180012411  pop     r14
0x180012413  pop     r12
0x180012415  pop     rdi
0x180012416  pop     rbp
0x180012417  retn
0x180012418  lea     rcx, [rdi+8]
0x18001241c  mov     dword ptr [rbp+var_60+0Ch], 6
0x180012423  mov     [rbp+EndPtr], rcx
0x180012427  mov     ebx, r14d
0x18001242a  jmp     short loc_1800123B2
0x18001242c  movzx   edx, word ptr [rbp+var_60+8]
0x180012430  mov     ecx, dword ptr [rbp+var_60+0Ch]
0x180012433  call    FwGetServiceType
0x180012438  movaps  xmm0, xmmword ptr [rbp+var_60]
0x18001243c  movaps  xmm1, [rbp+var_50]
0x180012440  movups  xmmword ptr [rsi], xmm0
0x180012443  mov     [rbp+var_24], eax
0x180012446  movaps  xmm0, [rbp+var_40]
0x18001244a  movups  xmmword ptr [rsi+10h], xmm1
0x18001244e  movaps  xmm1, xmmword ptr [rbp-30h]
0x180012452  movups  xmmword ptr [rsi+20h], xmm0
0x180012456  movsd   xmm0, [rbp+var_20]
0x18001245b  movups  xmmword ptr [rsi+30h], xmm1
0x18001245f  movsd   qword ptr [rsi+40h], xmm0
0x180012464  test    ebx, ebx
0x180012466  jns     short loc_1800123EE
0x180012468  jmp     loc_1800123D9
0x18001246d  mov     ebx, 80004003h
0x180012472  mov     edx, ebx
0x180012474  jmp     loc_1800123D1
0x180012479  mov     edx, r12d
0x18001247c  lea     rcx, aFwextractportn_0; "FwExtractPortNumber"
0x180012483  call    FwReportReturnError
0x180012488  mov     edx, r12d
0x18001248b  lea     rcx, aFwextractportn_0; "FwExtractPortNumber"
0x180012492  call    FwReportReturnError
0x180012497  mov     ebx, eax
0x180012499  test    eax, eax
0x18001249b  jns     loc_18001233C
0x1800124a1  jmp     loc_1800123CF
0x1800124a6  mov     rcx, [rbp+EndPtr]
0x1800124aa  mov     dword ptr [rbp+var_60+0Ch], 11h
0x1800124b1  jmp     loc_180012427
0x1800124b6  mov     rcx, [rbp+EndPtr]; unsigned __int16 *
0x1800124ba  cmp     [rcx], r14w
0x1800124be  jz      loc_18001242C
0x1800124c4  lea     r8, [rbp+EndPtr]; unsigned __int16 **
0x1800124c8  lea     rdx, [rbp+var_28]; int *
0x1800124cc  call    ?FwExtractEnabled@@YAJPEBGPEAHPEAPEBG@Z; FwExtractEnabled(ushort const *,int *,ushort const * *)
0x1800124d1  mov     ebx, eax
0x1800124d3  test    eax, eax
0x1800124d5  js      loc_1800123CF
0x1800124db  mov     rcx, [rbp+EndPtr]; unsigned __int16 *
0x1800124df  cmp     [rcx], r14w
0x1800124e3  jz      loc_18001242C
0x1800124e9  lea     rdx, [rbp+var_60]; unsigned __int16 **
0x1800124ed  call    ?FwExtractName@@YAJPEBGPEAPEAG@Z; FwExtractName(ushort const *,ushort * *)
0x1800124f2  mov     ebx, eax
0x1800124f4  test    eax, eax
0x1800124f6  js      loc_1800123CF
0x1800124fc  jmp     loc_18001242C
```
