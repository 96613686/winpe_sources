# CReportEvent::Process(_radiuslogtype_,_packettype_,ulong,sockaddr *,ushort const *,void *)

- ea: `0x1800283c0`
- end: `0x180028530`
- name: `?Process@CReportEvent@@QEAAXW4_radiuslogtype_@@W4_packettype_@@KPEAUsockaddr@@PEBGPEAX@Z`
- size: `368`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180013f90`
- `0x18001408c`
- `0x180014388`
- `0x180014f88`
- `0x1800151cc`
- `0x1800179a4`
- `0x180019944`
- `0x180019d84`
- `0x180019ff4`
- `0x18002eacd`

## callees

- `0x1800094e4`
- `0x18000dc54`
- `0x18001d31c`
- `0x18002819c`
- `0x1800283c0`
- `0x18002e230`

## import_xrefs

- `iassvcs!IASReportEvent` at `0x1800284b8`
- `iassvcs!IASReportEvent` at `0x1800284b8`

## string_xrefs

- `0x1800284da`: `Unable to report event from Radius Component`

## pseudocode

```c
void __fastcall CReportEvent::Process(
        __int64 a1,
        int a2,
        int a3,
        unsigned int a4,
        SOCKADDR *pSockaddr,
        __int64 a6,
        __int64 a7)
{
  __int64 v8; // rdi
  __int64 v9; // rsi
  int v10; // eax
  char v11; // bl
  __int128 v12; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE v13[144]; // [rsp+50h] [rbp-C8h] BYREF

  v8 = a3;
  v9 = a2;
  v12 = 0;
  if ( a3 <= 11 )
  {
    v10 = ias_inet_htow(pSockaddr, v13);
    v11 = v10;
    if ( v10 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("ias_inet_htow failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_a7bed7f64ccc30db73a0218edcab85bc_Traceguids,
        (unsigned int)"NAPBASE",
        v11);
    }
    v12 = (unsigned __int64)v13;
    if ( (int)IASReportEvent(*(unsigned int *)&byte_180041F70[48 * v9 + 4 * v8], 2, a4, &v12, a7) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("Unable to report event from Radius Component");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a7bed7f64ccc30db73a0218edcab85bc_Traceguids, "NAPBASE");
    }
  }
}

```

## disassembly

```asm
0x1800283c0  mov     [rsp+arg_0], rbx
0x1800283c5  push    rbp
0x1800283c6  push    rsi
0x1800283c7  push    rdi
0x1800283c8  push    r14
0x1800283ca  push    r15
0x1800283cc  sub     rsp, 0F0h
0x1800283d3  mov     rax, cs:__security_cookie
0x1800283da  xor     rax, rsp
0x1800283dd  mov     [rsp+118h+var_38], rax
0x1800283e5  mov     rcx, [rsp+118h+pSockaddr]; pSockaddr
0x1800283ed  xorps   xmm0, xmm0
0x1800283f0  mov     r14, [rsp+118h+arg_30]
0x1800283f8  mov     ebp, r9d
0x1800283fb  movsxd  rdi, r8d
0x1800283fe  movsxd  rsi, edx
0x180028401  mov     [rsp+118h+var_E8], 41h ; 'A'
0x18002840a  movups  [rsp+118h+var_E0], xmm0
0x18002840f  cmp     edi, 0Bh
0x180028412  jg      loc_180028509
0x180028418  lea     r8, [rsp+118h+var_E8]
0x18002841d  lea     rdx, [rsp+118h+var_C8]; void *
0x180028422  call    ias_inet_htow
0x180028427  lea     r15, WPP_GLOBAL_Control
0x18002842e  mov     ebx, eax
0x180028430  test    eax, eax
0x180028432  jns     short loc_180028481
0x180028434  mov     rcx, cs:WPP_GLOBAL_Control
0x18002843b  cmp     rcx, r15
0x18002843e  jz      short loc_180028481
0x180028440  cmp     byte ptr [rcx+19h], 2
0x180028444  jb      short loc_180028481
0x180028446  test    byte ptr [rcx+1Ch], 1
0x18002844a  jz      short loc_180028481
0x18002844c  mov     edx, eax
0x18002844e  lea     rcx, aIasInetHtowFai_0; "ias_inet_htow failed with 0x%x"
0x180028455  call    WppDbgPrint
0x18002845a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028461  lea     r9, aNapbase; "NAPBASE"
0x180028468  mov     edx, 0Ah
0x18002846d  mov     dword ptr [rsp+118h+var_F8], ebx
0x180028471  lea     r8, WPP_a7bed7f64ccc30db73a0218edcab85bc_Traceguids
0x180028478  mov     rcx, [rcx+10h]
0x18002847c  call    WPP_SF_sd
0x180028481  lea     rax, [rsp+118h+var_C8]
0x180028486  mov     qword ptr [rsp+118h+var_E0+8], 0
0x18002848f  mov     qword ptr [rsp+118h+var_E0], rax
0x180028494  lea     rcx, [rsi+rsi*2]
0x180028498  lea     rax, byte_180041F70
0x18002849f  mov     [rsp+118h+var_F8], r14
0x1800284a4  lea     rcx, [rdi+rcx*4]
0x1800284a8  mov     r8d, ebp
0x1800284ab  mov     ecx, [rax+rcx*4]
0x1800284ae  lea     r9, [rsp+118h+var_E0]
0x1800284b3  mov     edx, 2
0x1800284b8  call    cs:__imp_IASReportEvent
0x1800284be  test    eax, eax
0x1800284c0  jns     short loc_180028509
0x1800284c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800284c9  cmp     rax, r15
0x1800284cc  jz      short loc_180028509
0x1800284ce  cmp     byte ptr [rax+19h], 2
0x1800284d2  jb      short loc_180028509
0x1800284d4  test    byte ptr [rax+1Ch], 1
0x1800284d8  jz      short loc_180028509
0x1800284da  lea     rcx, aUnableToReport; "Unable to report event from Radius Comp"...
0x1800284e1  call    WppDbgPrint
0x1800284e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284ed  lea     r9, aNapbase; "NAPBASE"
0x1800284f4  mov     edx, 0Bh
0x1800284f9  lea     r8, WPP_a7bed7f64ccc30db73a0218edcab85bc_Traceguids
0x180028500  mov     rcx, [rcx+10h]
0x180028504  call    WPP_SF_s
0x180028509  mov     rcx, [rsp+118h+var_38]
0x180028511  xor     rcx, rsp; StackCookie
0x180028514  call    __security_check_cookie
0x180028519  mov     rbx, [rsp+118h+arg_0]
0x180028521  add     rsp, 0F0h
0x180028528  pop     r15
0x18002852a  pop     r14
0x18002852c  pop     rdi
0x18002852d  pop     rsi
0x18002852e  pop     rbp
0x18002852f  retn
```
