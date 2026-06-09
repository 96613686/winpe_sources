# COOBESettingsStore::GetBool(ushort const *,int *)

- ea: `0x180056be0`
- end: `0x180056d22`
- name: `?GetBool@COOBESettingsStore@@UEAAJPEBGPEAH@Z`
- size: `322`
- prototype: `__int64 __fastcall(COOBESettingsStore *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002b60`
- `0x180007d34`
- `0x180056968`
- `0x180056be0`
- `0x1800576bc`
- `0x1800576f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180056cdd`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180056cdd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056c9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056cc6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056c9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056cc6`
- `OLEAUT32!__imp_SysFreeString` at `0x180056cfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180056cfc`

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
0x180056be0  push    rbx
0x180056be2  push    rbp
0x180056be3  push    rsi
0x180056be4  push    rdi
0x180056be5  push    r14
0x180056be7  sub     rsp, 270h
0x180056bee  mov     rax, cs:__security_cookie
0x180056bf5  xor     rax, rsp
0x180056bf8  mov     [rsp+298h+var_38], rax
0x180056c00  mov     r14, r8
0x180056c03  mov     rbp, rcx
0x180056c06  mov     dword ptr [r8], 0
0x180056c0d  mov     qword ptr [rsp+298h+bIgnoreCase], rdx
0x180056c12  lea     r9, aOobe; "oobe"
0x180056c19  lea     r8, aSS_0; "%s/%s"
0x180056c20  mov     edx, 104h; unsigned __int64
0x180056c25  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x180056c2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056c2f  mov     ebx, eax
0x180056c31  test    eax, eax
0x180056c33  js      loc_180056D02
0x180056c39  mov     ebx, 80070490h
0x180056c3e  xor     esi, esi
0x180056c40  cmp     esi, 5
0x180056c43  jnb     loc_180056D02
0x180056c49  mov     rcx, [rbp+rsi*8+10h]
0x180056c4e  test    rcx, rcx
0x180056c51  jz      short loc_180056C7D
0x180056c53  lea     r8, [rsp+298h+var_248]
0x180056c58  lea     rdx, [rsp+298h+var_268]
0x180056c5d  call    ?selectNode@CXMLDOMNode@@QEAA?AV1@PEBGH@Z; CXMLDOMNode::selectNode(ushort const *,int)
0x180056c62  nop
0x180056c63  mov     rcx, rax; this
0x180056c66  call    ?innerText@CXMLDOMNode@@QEAAPEAGXZ; CXMLDOMNode::innerText(void)
0x180056c6b  mov     rdi, rax
0x180056c6e  lea     rcx, [rsp+298h+var_268]; this
0x180056c73  call    ??1CXMLDOMNode@@QEAA@XZ; CXMLDOMNode::~CXMLDOMNode(void)
0x180056c78  test    rdi, rdi
0x180056c7b  jnz     short loc_180056C81
0x180056c7d  inc     esi
0x180056c7f  jmp     short loc_180056C40
0x180056c81  mov     [rsp+298h+bIgnoreCase], 1; bIgnoreCase
0x180056c89  or      ebx, 0FFFFFFFFh
0x180056c8c  mov     r9d, ebx; cchCount2
0x180056c8f  lea     r8, aTrue; "true"
0x180056c96  mov     edx, ebx; cchCount1
0x180056c98  mov     rcx, rdi; lpString1
0x180056c9b  call    cs:__imp_CompareStringOrdinal
0x180056ca1  cmp     eax, 2
0x180056ca4  jnz     short loc_180056CAF
0x180056ca6  mov     dword ptr [r14], 1
0x180056cad  jmp     short loc_180056CF7
0x180056caf  mov     [rsp+298h+bIgnoreCase], 1; bIgnoreCase
0x180056cb7  mov     r9d, ebx; cchCount2
0x180056cba  lea     r8, aFalse; "false"
0x180056cc1  mov     edx, ebx; cchCount1
0x180056cc3  mov     rcx, rdi; lpString1
0x180056cc6  call    cs:__imp_CompareStringOrdinal
0x180056ccc  cmp     eax, 2
0x180056ccf  jnz     short loc_180056CDA
0x180056cd1  mov     dword ptr [r14], 0
0x180056cd8  jmp     short loc_180056CF7
0x180056cda  mov     rcx, rdi
0x180056cdd  call    cs:__imp__o__wtol
0x180056ce3  test    eax, eax
0x180056ce5  jnz     short loc_180056CF4
0x180056ce7  cmp     word ptr [rdi], 30h ; '0'
0x180056ceb  jz      short loc_180056CF4
0x180056ced  mov     ebx, 8000FFFFh
0x180056cf2  jmp     short loc_180056CF9
0x180056cf4  mov     [r14], eax
0x180056cf7  xor     ebx, ebx
0x180056cf9  mov     rcx, rdi; bstrString
0x180056cfc  call    cs:__imp_SysFreeString
0x180056d02  mov     eax, ebx
0x180056d04  mov     rcx, [rsp+298h+var_38]
0x180056d0c  xor     rcx, rsp; StackCookie
0x180056d0f  call    __security_check_cookie
0x180056d14  add     rsp, 270h
0x180056d1b  pop     r14
0x180056d1d  pop     rdi
0x180056d1e  pop     rsi
0x180056d1f  pop     rbp
0x180056d20  pop     rbx
0x180056d21  retn
```
