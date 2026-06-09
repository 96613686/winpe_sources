# COOBESettingsStore::GetBool(ushort const *,int *)

- ea: `0x1800b3540`
- end: `0x1800b3682`
- name: `?GetBool@COOBESettingsStore@@UEAAJPEBGPEAH@Z`
- size: `322`
- prototype: `__int64 __fastcall(COOBESettingsStore *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003470`
- `0x180008b98`
- `0x180044080`
- `0x180044c9c`
- `0x1800b3540`
- `0x1800b3bd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800b363d`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800b363d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b35fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b3626`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b35fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b3626`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b365c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b365c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COOBESettingsStore::GetBool(COOBESettingsStore *this, const unsigned __int16 *a2, int *a3)
{
  unsigned int v5; // ebx
  __int64 i; // rsi
  __int64 v7; // rcx
  CXMLDOMNode *v8; // rax
  OLECHAR *v9; // rdi
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 v13[264]; // [rsp+50h] [rbp-248h] BYREF

  *a3 = 0;
  v5 = StringCchPrintfW(v13, 0x104u, L"%s/%s", L"oobe", a2);
  if ( (v5 & 0x80000000) == 0 )
  {
    v5 = -2147023728;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= 5 )
        return v5;
      v7 = *((_QWORD *)this + i + 2);
      if ( v7 )
      {
        v8 = (CXMLDOMNode *)CXMLDOMNode::selectNode(v7, v12, v13);
        v9 = CXMLDOMNode::innerText(v8);
        CXMLDOMNode::~CXMLDOMNode((CXMLDOMNode *)v12);
        if ( v9 )
          break;
      }
    }
    if ( CompareStringOrdinal(v9, -1, L"true", -1, 1) == 2 )
    {
      *a3 = 1;
    }
    else if ( CompareStringOrdinal(v9, -1, L"false", -1, 1) == 2 )
    {
      *a3 = 0;
    }
    else
    {
      v10 = _o__wtol(v9);
      if ( !v10 && *v9 != 48 )
      {
        v5 = -2147418113;
LABEL_16:
        SysFreeString(v9);
        return v5;
      }
      *a3 = v10;
    }
    v5 = 0;
    goto LABEL_16;
  }
  return v5;
}

```

## disassembly

```asm
0x1800b3540  push    rbx
0x1800b3542  push    rbp
0x1800b3543  push    rsi
0x1800b3544  push    rdi
0x1800b3545  push    r14
0x1800b3547  sub     rsp, 270h
0x1800b354e  mov     rax, cs:__security_cookie
0x1800b3555  xor     rax, rsp
0x1800b3558  mov     [rsp+298h+var_38], rax
0x1800b3560  mov     r14, r8
0x1800b3563  mov     rbp, rcx
0x1800b3566  mov     dword ptr [r8], 0
0x1800b356d  mov     qword ptr [rsp+298h+bIgnoreCase], rdx
0x1800b3572  lea     r9, aOobe; "oobe"
0x1800b3579  lea     r8, aSS_1; "%s/%s"
0x1800b3580  mov     edx, 104h; unsigned __int64
0x1800b3585  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x1800b358a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b358f  mov     ebx, eax
0x1800b3591  test    eax, eax
0x1800b3593  js      loc_1800B3662
0x1800b3599  mov     ebx, 80070490h
0x1800b359e  xor     esi, esi
0x1800b35a0  cmp     esi, 5
0x1800b35a3  jnb     loc_1800B3662
0x1800b35a9  mov     rcx, [rbp+rsi*8+10h]
0x1800b35ae  test    rcx, rcx
0x1800b35b1  jz      short loc_1800B35DD
0x1800b35b3  lea     r8, [rsp+298h+var_248]
0x1800b35b8  lea     rdx, [rsp+298h+var_268]
0x1800b35bd  call    ?selectNode@CXMLDOMNode@@QEAA?AV1@PEBGH@Z; CXMLDOMNode::selectNode(ushort const *,int)
0x1800b35c2  nop
0x1800b35c3  mov     rcx, rax; this
0x1800b35c6  call    ?innerText@CXMLDOMNode@@QEAAPEAGXZ; CXMLDOMNode::innerText(void)
0x1800b35cb  mov     rdi, rax
0x1800b35ce  lea     rcx, [rsp+298h+var_268]; this
0x1800b35d3  call    ??1CXMLDOMNode@@QEAA@XZ; CXMLDOMNode::~CXMLDOMNode(void)
0x1800b35d8  test    rdi, rdi
0x1800b35db  jnz     short loc_1800B35E1
0x1800b35dd  inc     esi
0x1800b35df  jmp     short loc_1800B35A0
0x1800b35e1  mov     [rsp+298h+bIgnoreCase], 1; bIgnoreCase
0x1800b35e9  or      ebx, 0FFFFFFFFh
0x1800b35ec  mov     r9d, ebx; cchCount2
0x1800b35ef  lea     r8, aTrue; "true"
0x1800b35f6  mov     edx, ebx; cchCount1
0x1800b35f8  mov     rcx, rdi; lpString1
0x1800b35fb  call    cs:__imp_CompareStringOrdinal
0x1800b3601  cmp     eax, 2
0x1800b3604  jnz     short loc_1800B360F
0x1800b3606  mov     dword ptr [r14], 1
0x1800b360d  jmp     short loc_1800B3657
0x1800b360f  mov     [rsp+298h+bIgnoreCase], 1; bIgnoreCase
0x1800b3617  mov     r9d, ebx; cchCount2
0x1800b361a  lea     r8, aFalse; "false"
0x1800b3621  mov     edx, ebx; cchCount1
0x1800b3623  mov     rcx, rdi; lpString1
0x1800b3626  call    cs:__imp_CompareStringOrdinal
0x1800b362c  cmp     eax, 2
0x1800b362f  jnz     short loc_1800B363A
0x1800b3631  mov     dword ptr [r14], 0
0x1800b3638  jmp     short loc_1800B3657
0x1800b363a  mov     rcx, rdi
0x1800b363d  call    cs:__imp__o__wtol
0x1800b3643  test    eax, eax
0x1800b3645  jnz     short loc_1800B3654
0x1800b3647  cmp     word ptr [rdi], 30h ; '0'
0x1800b364b  jz      short loc_1800B3654
0x1800b364d  mov     ebx, 8000FFFFh
0x1800b3652  jmp     short loc_1800B3659
0x1800b3654  mov     [r14], eax
0x1800b3657  xor     ebx, ebx
0x1800b3659  mov     rcx, rdi; bstrString
0x1800b365c  call    cs:__imp_SysFreeString
0x1800b3662  mov     eax, ebx
0x1800b3664  mov     rcx, [rsp+298h+var_38]
0x1800b366c  xor     rcx, rsp; StackCookie
0x1800b366f  call    __security_check_cookie
0x1800b3674  add     rsp, 270h
0x1800b367b  pop     r14
0x1800b367d  pop     rdi
0x1800b367e  pop     rsi
0x1800b367f  pop     rbp
0x1800b3680  pop     rbx
0x1800b3681  retn
```
