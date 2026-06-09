# IASAttributeFromVariant(tagVARIANT *,IASTYPEENUM)

- ea: `0x1800276b0`
- end: `0x180027930`
- name: `?IASAttributeFromVariant@@YAPEAU_IASATTRIBUTE@@PEAUtagVARIANT@@W4IASTYPEENUM@@@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800241e0`

## callees

- `0x18000bea8`
- `0x18000bf20`
- `0x18000c108`
- `0x18000c1fc`
- `0x18000c808`
- `0x18000d55c`
- `0x1800273d0`
- `0x1800274dc`
- `0x1800276b0`
- `0x18002b4a0`

## import_xrefs

- `iassvcs!IASVariantChangeType` at `0x18002777d`
- `iassvcs!IASVariantChangeType` at `0x1800277ee`
- `iassvcs!IASVariantChangeType` at `0x18002784c`
- `iassvcs!IASVariantChangeType` at `0x18002787f`
- `iassvcs!IASVariantChangeType` at `0x1800278c0`
- `iassvcs!IASVariantChangeType` at `0x1800278e9`
- `iassvcs!IASVariantChangeType` at `0x18002777d`
- `iassvcs!IASVariantChangeType` at `0x1800277ee`
- `iassvcs!IASVariantChangeType` at `0x18002784c`
- `iassvcs!IASVariantChangeType` at `0x18002787f`
- `iassvcs!IASVariantChangeType` at `0x1800278c0`
- `iassvcs!IASVariantChangeType` at `0x1800278e9`
- `KERNEL32!SystemTimeToFileTime` at `0x1800277bc`
- `KERNEL32!SystemTimeToFileTime` at `0x1800277bc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027762`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027831`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027762`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027831`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18002779f`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18002779f`
- `WS2_32!__imp_htonl` at `0x180027894`
- `WS2_32!__imp_htonl` at `0x180027894`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct _FILETIME *__fastcall IASAttributeFromVariant(__int64 a1, BOOL a2)
{
  struct _FILETIME *v4; // rsi
  int v5; // eax
  unsigned int v6; // eax
  int v7; // edx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  DWORD v13; // edi
  struct _FILETIME *v15; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int8 v16[8]; // [rsp+28h] [rbp-28h] BYREF
  SAFEARRAY *psa[2]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *Src; // [rsp+40h] [rbp-10h]

  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&v15, a2);
  v4 = v15;
  if ( a2 )
  {
    v12 = IASVariantChangeType(a1, a1, 0, 11);
    v13 = 0;
    if ( v12 < 0 )
      _com_issue_error(v12);
    LOBYTE(v13) = *(_WORD *)(a1 + 8) != 0;
    v4[3].dwLowDateTime = v13;
  }
  else
  {
    switch ( a2 )
    {
      case 2:
      case 3:
        v11 = IASVariantChangeType(a1, a1, 0, 3);
        if ( v11 < 0 )
          _com_issue_error(v11);
        v4[3].dwLowDateTime = *(_DWORD *)(a1 + 8);
        break;
      case 4:
        v10 = IASVariantChangeType(a1, a1, 0, 3);
        if ( v10 < 0 )
          _com_issue_error(v10);
        *(_DWORD *)v16 = htonl(*(_DWORD *)(a1 + 8));
        IASTL::IASAttribute::setSockAddress((IASTL::IASAttribute *)&v15, 2u, v16);
        break;
      case 5:
        v9 = IASVariantChangeType(a1, a1, 0, 8);
        if ( v9 < 0 )
          _com_issue_error(v9);
        IASTL::IASAttribute::setString((IASTL::IASAttribute *)&v15, *(const unsigned __int16 **)(a1 + 8));
        break;
      case 6:
LABEL_17:
        if ( (unsigned __int16)(*(_WORD *)a1 - 8208) <= 1u )
        {
          CVariantVector<unsigned char>::CVariantVector<unsigned char>(psa, a1);
          IASTL::IASAttribute::setOctetString((IASTL::IASAttribute *)&v15, LODWORD(psa[1]), Src);
          SafeArrayUnaccessData(psa[0]);
        }
        else
        {
          v8 = IASVariantChangeType(a1, a1, 0, 8);
          if ( v8 < 0 )
            _com_issue_error(v8);
          IASTL::IASAttribute::setOctetString((IASTL::IASAttribute *)&v15, *(LPCWCH *)(a1 + 8));
        }
        break;
      case 7:
        v5 = IASVariantChangeType(a1, a1, 0, 7);
        if ( v5 < 0 )
          _com_issue_error(v5);
        *(_OWORD *)psa = 0;
        if ( !VariantTimeToSystemTime(*(DOUBLE *)(a1 + 8), (LPSYSTEMTIME)psa) )
          _com_issue_error(-2147024809);
        v6 = SystemTimeToFileTime((const SYSTEMTIME *)psa, v4 + 3);
        _w32_util::CheckSuccess((_w32_util *)v6, v7);
        break;
      case 8:
        goto LABEL_17;
      case 10:
        CVariantVector<unsigned char>::CVariantVector<unsigned char>(psa, a1);
        IASTL::IASAttribute::setSockAddress((IASTL::IASAttribute *)&v15, 0x17u, Src);
        SafeArrayUnaccessData(psa[0]);
        break;
      default:
        _com_issue_error(-2147024809);
    }
  }
  v4[2].dwLowDateTime = a2;
  return v4;
}

```

## disassembly

```asm
0x1800276b0  mov     [rsp-18h+arg_8], rbx
0x1800276b5  mov     [rsp-18h+arg_10], rsi
0x1800276ba  push    rbp
0x1800276bb  push    rdi
0x1800276bc  push    r14
0x1800276be  mov     rbp, rsp
0x1800276c1  sub     rsp, 50h
0x1800276c5  mov     rax, cs:__security_cookie
0x1800276cc  xor     rax, rsp
0x1800276cf  mov     [rbp+var_8], rax
0x1800276d3  mov     r14d, edx
0x1800276d6  mov     rbx, rcx
0x1800276d9  lea     rcx, [rbp+var_30]; this
0x1800276dd  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x1800276e2  nop
0x1800276e3  mov     ecx, r14d
0x1800276e6  mov     rsi, [rbp+var_30]
0x1800276ea  sub     ecx, 1
0x1800276ed  jz      loc_1800278DA
0x1800276f3  sub     ecx, 1
0x1800276f6  jz      loc_1800278B1
0x1800276fc  sub     ecx, 1
0x1800276ff  jz      loc_1800278B1
0x180027705  sub     ecx, 1
0x180027708  jz      loc_180027870
0x18002770e  sub     ecx, 1
0x180027711  jz      loc_18002783D
0x180027717  sub     ecx, 1
0x18002771a  jz      loc_1800277CE
0x180027720  sub     ecx, 1
0x180027723  jz      short loc_18002776E
0x180027725  sub     ecx, 1
0x180027728  jz      loc_1800277CE
0x18002772e  cmp     ecx, 2
0x180027731  jz      short loc_18002773E
0x180027733  mov     ecx, 80070057h; int
0x180027738  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002773e  mov     rdx, rbx
0x180027741  lea     rcx, [rbp+psa]
0x180027745  call    ??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@@Z; CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *)
0x18002774a  nop
0x18002774b  mov     edx, 17h; unsigned __int16
0x180027750  mov     r8, [rbp+Src]; unsigned __int8 *
0x180027754  lea     rcx, [rbp+var_30]; this
0x180027758  call    ?setSockAddress@IASAttribute@IASTL@@QEAAXGQEAE@Z; IASTL::IASAttribute::setSockAddress(ushort,uchar * const)
0x18002775d  nop
0x18002775e  mov     rcx, [rbp+psa]; psa
0x180027762  call    cs:__imp_SafeArrayUnaccessData
0x180027768  nop
0x180027769  jmp     loc_180027908
0x18002776e  mov     r9d, 7
0x180027774  xor     r8d, r8d
0x180027777  mov     rdx, rbx
0x18002777a  mov     rcx, rbx
0x18002777d  call    cs:__imp_IASVariantChangeType
0x180027783  test    eax, eax
0x180027785  jns     short loc_18002778F
0x180027787  mov     ecx, eax; int
0x180027789  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002778f  xorps   xmm0, xmm0
0x180027792  movups  xmmword ptr [rbp+psa], xmm0
0x180027796  lea     rdx, [rbp+psa]; lpSystemTime
0x18002779a  movsd   xmm0, qword ptr [rbx+8]; vtime
0x18002779f  call    cs:__imp_VariantTimeToSystemTime
0x1800277a5  test    eax, eax
0x1800277a7  jnz     short loc_1800277B4
0x1800277a9  mov     ecx, 80070057h; int
0x1800277ae  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800277b4  lea     rdx, [rsi+18h]; lpFileTime
0x1800277b8  lea     rcx, [rbp+psa]; lpSystemTime
0x1800277bc  call    cs:__imp_SystemTimeToFileTime
0x1800277c2  mov     ecx, eax; this
0x1800277c4  call    ?CheckSuccess@_w32_util@@YAXH@Z; _w32_util::CheckSuccess(int)
0x1800277c9  jmp     loc_180027908
0x1800277ce  mov     ecx, 2010h
0x1800277d3  movzx   eax, word ptr [rbx]
0x1800277d6  sub     ax, cx
0x1800277d9  mov     rdx, rbx
0x1800277dc  cmp     ax, 1
0x1800277e0  jbe     short loc_180027812
0x1800277e2  mov     r9d, 8
0x1800277e8  xor     r8d, r8d
0x1800277eb  mov     rcx, rbx
0x1800277ee  call    cs:__imp_IASVariantChangeType
0x1800277f4  test    eax, eax
0x1800277f6  jns     short loc_180027800
0x1800277f8  mov     ecx, eax; int
0x1800277fa  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180027800  mov     rdx, [rbx+8]; lpWideCharStr
0x180027804  lea     rcx, [rbp+var_30]; this
0x180027808  call    ?setOctetString@IASAttribute@IASTL@@QEAAXPEBG@Z; IASTL::IASAttribute::setOctetString(ushort const *)
0x18002780d  jmp     loc_180027908
0x180027812  lea     rcx, [rbp+psa]
0x180027816  call    ??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@@Z; CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *)
0x18002781b  nop
0x18002781c  mov     r8, [rbp+Src]; Src
0x180027820  mov     edx, dword ptr [rbp+psa+8]; Size
0x180027823  lea     rcx, [rbp+var_30]; this
0x180027827  call    ?setOctetString@IASAttribute@IASTL@@QEAAXKPEBE@Z; IASTL::IASAttribute::setOctetString(ulong,uchar const *)
0x18002782c  nop
0x18002782d  mov     rcx, [rbp+psa]; psa
0x180027831  call    cs:__imp_SafeArrayUnaccessData
0x180027837  nop
0x180027838  jmp     loc_180027908
0x18002783d  mov     r9d, 8
0x180027843  xor     r8d, r8d
0x180027846  mov     rdx, rbx
0x180027849  mov     rcx, rbx
0x18002784c  call    cs:__imp_IASVariantChangeType
0x180027852  test    eax, eax
0x180027854  jns     short loc_18002785E
0x180027856  mov     ecx, eax; int
0x180027858  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002785e  mov     rdx, [rbx+8]; Src
0x180027862  lea     rcx, [rbp+var_30]; this
0x180027866  call    ?setString@IASAttribute@IASTL@@QEAAXPEBG@Z; IASTL::IASAttribute::setString(ushort const *)
0x18002786b  jmp     loc_180027908
0x180027870  mov     r9d, 3
0x180027876  xor     r8d, r8d
0x180027879  mov     rdx, rbx
0x18002787c  mov     rcx, rbx
0x18002787f  call    cs:__imp_IASVariantChangeType
0x180027885  test    eax, eax
0x180027887  jns     short loc_180027891
0x180027889  mov     ecx, eax; int
0x18002788b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180027891  mov     ecx, [rbx+8]; hostlong
0x180027894  call    cs:__imp_htonl
0x18002789a  mov     dword ptr [rbp+var_28], eax
0x18002789d  mov     edx, 2; unsigned __int16
0x1800278a2  lea     r8, [rbp+var_28]; unsigned __int8 *
0x1800278a6  lea     rcx, [rbp+var_30]; this
0x1800278aa  call    ?setSockAddress@IASAttribute@IASTL@@QEAAXGQEAE@Z; IASTL::IASAttribute::setSockAddress(ushort,uchar * const)
0x1800278af  jmp     short loc_180027908
0x1800278b1  mov     r9d, 3
0x1800278b7  xor     r8d, r8d
0x1800278ba  mov     rdx, rbx
0x1800278bd  mov     rcx, rbx
0x1800278c0  call    cs:__imp_IASVariantChangeType
0x1800278c6  test    eax, eax
0x1800278c8  jns     short loc_1800278D2
0x1800278ca  mov     ecx, eax; int
0x1800278cc  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800278d2  mov     eax, [rbx+8]
0x1800278d5  mov     [rsi+18h], eax
0x1800278d8  jmp     short loc_180027908
0x1800278da  mov     r9d, 0Bh
0x1800278e0  xor     r8d, r8d
0x1800278e3  mov     rdx, rbx
0x1800278e6  mov     rcx, rbx
0x1800278e9  call    cs:__imp_IASVariantChangeType
0x1800278ef  xor     edi, edi
0x1800278f1  test    eax, eax
0x1800278f3  jns     short loc_1800278FD
0x1800278f5  mov     ecx, eax; int
0x1800278f7  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800278fd  cmp     [rbx+8], di
0x180027901  setnz   dil
0x180027905  mov     [rsi+18h], edi
0x180027908  mov     [rsi+10h], r14d
0x18002790c  mov     rax, rsi
0x18002790f  mov     rcx, [rbp+var_8]
0x180027913  xor     rcx, rsp; StackCookie
0x180027916  call    __security_check_cookie
0x18002791b  lea     r11, [rsp+50h+var_s0]
0x180027920  mov     rbx, [r11+28h]
0x180027924  mov     rsi, [r11+30h]
0x180027928  mov     rsp, r11
0x18002792b  pop     r14
0x18002792d  pop     rdi
0x18002792e  pop     rbp
0x18002792f  retn
```
