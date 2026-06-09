# ParseTaskData(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::vector<uchar,std::allocator<uchar>> &,bool &)

- ea: `0x180018efc`
- end: `0x180019196`
- name: `?ParseTaskData@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@AEAV?$vector@EV?$allocator@E@std@@@2@AEA_N@Z`
- size: `666`
- prototype: `void __fastcall(const std::wstring *Data, std::wstring *Method, std::vector<unsigned char> *Payload, bool *FirstAttemptWasFailedReregistration)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017d2c`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x18000a42c`
- `0x18000b0a0`
- `0x180010984`
- `0x180011844`
- `0x180011cfc`
- `0x180012400`
- `0x180012748`
- `0x1800127cc`
- `0x18001282c`
- `0x180017730`
- `0x180017834`
- `0x180017b60`
- `0x180017bb4`
- `0x180018efc`
- `0x18001a0d4`
- `0x18004ab20`

## import_xrefs

- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x180019038`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x180019038`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x180018f78`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x18001910a`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x180018f78`
- `msvcp_win!??7ios_base@std@@QEBA_NXZ` at `0x18001910a`

## string_xrefs

- `0x1800190c1`: `ServiceActivation`
- `0x180019042`: `FirstAttemptWasFailedReregistration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ParseTaskData(
        const std::wstring *Data,
        std::wstring *Method,
        std::vector<unsigned char> *Payload,
        bool *FirstAttemptWasFailedReregistration)
{
  _QWORD *v8; // r8
  _BYTE *v9; // r9
  int v10; // r8d
  std::basic_istream<unsigned short> *v11; // rax
  WPP_PROJECT_CONTROL_BLOCK *v12; // r10
  const wchar_t *v13; // rax
  __int64 v14; // r10
  unsigned __int64 v15; // rax
  const wchar_t *v16; // rcx
  const wchar_t *v17; // r10
  std::basic_istream<unsigned short> *v18; // rax
  const wchar_t *v19; // rax
  const wchar_t *v20; // r8
  unsigned __int64 v21; // r9
  const wchar_t *v22; // rax
  __int64 v23; // r10
  int _a2; // r8d
  unsigned __int64 v25; // rax
  const wchar_t *v26; // rcx
  const wchar_t *v27; // r10
  std::basic_istream<unsigned short> *v28; // rax
  std::wstring nextLine; // [rsp+38h] [rbp-C8h] BYREF
  std::wstring encodedPayload; // [rsp+58h] [rbp-A8h] BYREF
  std::basic_istringstream<unsigned short> iss; // [rsp+80h] [rbp-80h] BYREF

  std::wstring::_Eos(Method, 0);
  if ( *v8 != v8[1] )
    v8[1] = *v8;
  *v9 = 0;
  memset_0(&iss, 0, sizeof(iss));
  std::basic_istringstream<unsigned short>::basic_istringstream<unsigned short>(&iss, Data, v10);
  v11 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(&iss, Method);
  if ( !(unsigned __int8)std::ios_base::operator!(&v11->gap0[*(int *)(*(_QWORD *)v11->gap0 + 4LL)]) )
    goto LABEL_7;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
LABEL_7:
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v12->ReserveSpace[28] & 0x10) != 0 )
  {
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Method->_Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v14 + 16), 0x1Au, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, v13);
  }
LABEL_11:
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Method->_Mypair._Myval2);
  v15 = std::_WChar_traits<unsigned short>::length(L"ReconnectToNetwork");
  if ( std::_Traits_equal<std::char_traits<unsigned short>>(v17, Method->_Mypair._Myval2._Mysize, v16, v15) )
  {
    std::wstring::wstring(&nextLine);
    v18 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(&iss, &nextLine);
    if ( (unsigned __int8)std::ios_base::operator bool(&v18->gap0[*(int *)(*(_QWORD *)v18->gap0 + 4LL)]) )
    {
      std::_WChar_traits<unsigned short>::length(L"FirstAttemptWasFailedReregistration");
      v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&nextLine._Mypair._Myval2);
      *FirstAttemptWasFailedReregistration = std::_Traits_equal<std::char_traits<unsigned short>>(
                                               v19,
                                               nextLine._Mypair._Myval2._Mysize,
                                               v20,
                                               v21);
    }
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&nextLine._Mypair._Myval2);
      WPP_SF_Sd(*(_QWORD *)(v23 + 16), 0x1Bu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, v22, _a2);
    }
    std::wstring::_Tidy_deallocate(&nextLine);
  }
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Method->_Mypair._Myval2);
  v25 = std::_WChar_traits<unsigned short>::length(L"ServiceActivation");
  if ( std::_Traits_equal<std::char_traits<unsigned short>>(v27, Method->_Mypair._Myval2._Mysize, v26, v25) )
  {
    std::wstring::wstring(&encodedPayload);
    v28 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
            &iss,
            &encodedPayload);
    if ( (unsigned __int8)std::ios_base::operator!(&v28->gap0[*(int *)(*(_QWORD *)v28->gap0 + 4LL)])
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Cu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
    }
    WcmCommon::Convert::EncodedStringToBinary((std::vector<unsigned char> *)&nextLine, &encodedPayload, Base64);
    std::vector<unsigned char>::operator=(Payload, (std::vector<unsigned char> *)&nextLine);
    std::vector<unsigned char>::_Tidy((std::vector<char> *)&nextLine);
    std::wstring::_Tidy_deallocate(&encodedPayload);
  }
  std::basic_istringstream<unsigned short>::`vbase destructor'(&iss);
}

```

## disassembly

```asm
0x180018efc  push    rbp
0x180018efe  push    rbx
0x180018eff  push    rsi
0x180018f00  push    rdi
0x180018f01  push    r14
0x180018f03  lea     rbp, [rsp-80h]
0x180018f08  sub     rsp, 180h
0x180018f0f  mov     rax, cs:__security_cookie
0x180018f16  xor     rax, rsp
0x180018f19  mov     [rbp+0A0h+var_30], rax
0x180018f1d  mov     rsi, FirstAttemptWasFailedReregistration
0x180018f20  mov     rdi, Payload
0x180018f23  mov     rbx, Method
0x180018f26  mov     r14, Data
0x180018f29  xor     edx, edx; _New_size
0x180018f2b  mov     Data, rbx; this
0x180018f2e  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x180018f33  mov     rax, [Payload]
0x180018f36  cmp     rax, [Payload+8]
0x180018f3a  jz      short loc_180018F40
0x180018f3c  mov     [Payload+8], rax
0x180018f40  mov     byte ptr [FirstAttemptWasFailedReregistration], 0
0x180018f44  xor     edx, edx; Val
0x180018f46  mov     r8d, 0F0h; Size
0x180018f4c  lea     Data, [rbp+0A0h+iss]; void *
0x180018f50  call    memset_0
0x180018f55  mov     Method, r14; _Str
0x180018f58  lea     Data, [rbp+0A0h+iss]; this
0x180018f5c  call    ??0?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_istringstream<ushort>::basic_istringstream<ushort>(std::wstring const &,int)
0x180018f61  nop
0x180018f62  mov     Method, rbx; _Str
0x180018f65  lea     Data, [rbp+0A0h+iss]; _Istr
0x180018f69  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180018f6e  mov     Data, [rax]
0x180018f71  movsxd  Data, dword ptr [Data+4]
0x180018f75  add     Data, rax
0x180018f78  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x180018f7e  lea     r14, WPP_GLOBAL_Control
0x180018f85  test    al, al
0x180018f87  jz      short loc_180018FB1
0x180018f89  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180018f90  cmp     r10, r14
0x180018f93  jz      short loc_180018FE4
0x180018f95  test    byte ptr [r10+1Ch], 10h
0x180018f9a  jz      short loc_180018FB8
0x180018f9c  mov     edx, 19h; id
0x180018fa1  lea     Payload, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018fa8  mov     Data, [r10+10h]; Logger
0x180018fac  call    WPP_SF_
0x180018fb1  mov     r10, cs:WPP_GLOBAL_Control
0x180018fb8  cmp     r10, r14; __annotation("TMF:",
0x180018fbb  jz      short loc_180018FE4
0x180018fbd  test    byte ptr [r10+1Ch], 10h
0x180018fc2  jz      short loc_180018FE4
0x180018fc4  mov     Data, rbx; this
0x180018fc7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018fcc  mov     edx, 1Ah; id
0x180018fd1  mov     FirstAttemptWasFailedReregistration, rax; _a1
0x180018fd4  lea     Payload, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018fdb  mov     Data, [r10+10h]; Logger
0x180018fdf  call    WPP_SF_S
0x180018fe4  mov     Data, rbx; this
0x180018fe7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018fec  mov     r10, rax
0x180018fef  lea     Data, aReconnecttonet; "ReconnectToNetwork"
0x180018ff6  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180018ffb  mov     FirstAttemptWasFailedReregistration, rax; _Right_size
0x180018ffe  mov     Payload, Data; _Right
0x180019001  mov     Method, [rbx+10h]; _Left_size
0x180019005  mov     Data, r10; _Left
0x180019008  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001900d  test    al, al
0x18001900f  jz      loc_1800190B6
0x180019015  lea     Data, [rsp+1A0h+nextLine]; this
0x18001901a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001901f  nop
0x180019020  lea     Method, [rsp+1A0h+nextLine]; _Str
0x180019025  lea     Data, [rbp+0A0h+iss]; _Istr
0x180019029  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18001902e  mov     Data, [rax]
0x180019031  movsxd  Data, dword ptr [Data+4]
0x180019035  add     Data, rax
0x180019038  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x18001903e  test    al, al
0x180019040  jz      short loc_18001906D
0x180019042  lea     Payload, aFirstattemptwa; "FirstAttemptWasFailedReregistration"
0x180019049  mov     Data, Payload; _First
0x18001904c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019051  mov     FirstAttemptWasFailedReregistration, rax
0x180019054  lea     Data, [rsp+1A0h+nextLine]; this
0x180019059  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001905e  mov     Data, rax; _Left
0x180019061  mov     Method, [rsp+1A0h+nextLine._Mypair._Myval2._Mysize]; _Left_size
0x180019066  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001906b  mov     [rsi], al
0x18001906d  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180019074  cmp     r10, r14
0x180019077  jz      short loc_1800190AC
0x180019079  test    byte ptr [r10+1Ch], 10h
0x18001907e  jz      short loc_1800190AC
0x180019080  movzx   r8d, byte ptr [rsi]
0x180019084  lea     Data, [rsp+1A0h+nextLine]; this
0x180019089  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001908e  mov     FirstAttemptWasFailedReregistration, rax; _a1
0x180019091  mov     edx, 1Bh; id
0x180019096  mov     [rsp+1A0h+_a2], r8d; _a2
0x18001909b  lea     Payload, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x1800190a2  mov     Data, [r10+10h]; Logger
0x1800190a6  call    WPP_SF_Sd
0x1800190ab  nop
0x1800190ac  lea     Data, [rsp+1A0h+nextLine]; this
0x1800190b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800190b6  mov     Data, rbx; this
0x1800190b9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800190be  mov     r10, rax
0x1800190c1  lea     Data, aServiceactivat; "ServiceActivation"
0x1800190c8  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800190cd  mov     FirstAttemptWasFailedReregistration, rax; _Right_size
0x1800190d0  mov     Payload, Data; _Right
0x1800190d3  mov     Method, [rbx+10h]; _Left_size
0x1800190d7  mov     Data, r10; _Left
0x1800190da  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800190df  test    al, al
0x1800190e1  jz      loc_180019173
0x1800190e7  lea     Data, [rsp+1A0h+encodedPayload]; this
0x1800190ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800190f1  nop
0x1800190f2  lea     Method, [rsp+1A0h+encodedPayload]; _Str
0x1800190f7  lea     Data, [rbp+0A0h+iss]; _Istr
0x1800190fb  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180019100  mov     Data, [rax]
0x180019103  movsxd  Data, dword ptr [Data+4]
0x180019107  add     Data, rax
0x18001910a  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x180019110  test    al, al
0x180019112  jz      short loc_18001913B
0x180019114  mov     Data, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001911b  cmp     Data, r14
0x18001911e  jz      short loc_18001913B
0x180019120  test    byte ptr [Data+1Ch], 4
0x180019124  jz      short loc_18001913B
0x180019126  mov     edx, 1Ch; id
0x18001912b  lea     Payload, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180019132  mov     Data, [Data+10h]; Logger
0x180019136  call    WPP_SF_
0x18001913b  mov     r8d, 1; encoding
0x180019141  lea     Method, [rsp+1A0h+encodedPayload]; str
0x180019146  lea     Data, [rsp+1A0h+nextLine]; result
0x18001914b  call    ?EncodedStringToBinary@Convert@WcmCommon@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@W4Encoding@12@@Z; WcmCommon::Convert::EncodedStringToBinary(std::wstring const &,WcmCommon::Convert::Encoding)
0x180019150  lea     Method, [rsp+1A0h+nextLine]; _Right
0x180019155  mov     Data, rdi; this
0x180019158  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18001915d  lea     Data, [rsp+1A0h+nextLine]; this
0x180019162  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180019167  nop
0x180019168  lea     Data, [rsp+1A0h+encodedPayload]; this
0x18001916d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019172  nop
0x180019173  lea     Data, [rbp+0A0h+iss]; this
0x180019177  call    ??_D?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_istringstream<ushort>::`vbase destructor'(void)
0x18001917c  mov     Data, [rbp+0A0h+var_30]
0x180019180  xor     Data, rsp; StackCookie
0x180019183  call    __security_check_cookie
0x180019188  add     rsp, 180h
0x18001918f  pop     r14
0x180019191  pop     rdi
0x180019192  pop     rsi
0x180019193  pop     rbx
0x180019194  pop     rbp
0x180019195  retn
```
