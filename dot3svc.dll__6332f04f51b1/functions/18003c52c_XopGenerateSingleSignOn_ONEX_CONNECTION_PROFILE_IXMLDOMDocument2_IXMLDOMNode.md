# XopGenerateSingleSignOn(_ONEX_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x18003c52c`
- end: `0x18003c68e`
- name: `?XopGenerateSingleSignOn@@YAKPEAU_ONEX_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `354`
- prototype: `unsigned int(struct _ONEX_CONNECTION_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bd50`

## callees

- `0x1800326fc`
- `0x18003aa34`
- `0x18003acc4`
- `0x18003acfc`
- `0x18003ada8`
- `0x18003c52c`

## string_xrefs

- `0x18003c567`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18003c59f`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18003c603`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18003c65a`: `http://www.microsoft.com/networking/OneX/v1`

## pseudocode

```c
__int64 __fastcall XopGenerateSingleSignOn(
        struct _ONEX_CONNECTION_PROFILE *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  unsigned int v3; // esi
  bool v4; // zf
  int v7; // ebx
  struct IXMLDOMNode *v8; // rbx
  const unsigned __int16 *v9; // r9
  unsigned int v11; // [rsp+20h] [rbp-48h]
  struct IXMLDOMNode **v12; // [rsp+28h] [rbp-40h]
  struct IXMLDOMNode **v13; // [rsp+38h] [rbp-30h]
  struct IXMLDOMNode *v14; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  v4 = (*((_BYTE *)a1 + 8) & 1) == 0;
  v14 = 0;
  if ( !v4 )
  {
    v7 = *((_DWORD *)a1 + 3) & 0xC;
    if ( v7 )
    {
      v3 = XcAddChildElement(
             a2,
             a3,
             (OLECHAR *)L"singleSignOn",
             (OLECHAR *)L"http://www.microsoft.com/networking/OneX/v1",
             0,
             &v14);
      if ( !v3 )
      {
        v11 = v7;
        v8 = v14;
        v3 = XcAddChildElementEnum(
               a2,
               v14,
               (OLECHAR *)L"type",
               (OLECHAR *)L"http://www.microsoft.com/networking/OneX/v1",
               v11,
               (const struct _XC_STRING_VALUE_MAPPING *)&off_1800424C0,
               2u,
               v13);
        if ( !v3
          && ((*((_DWORD *)a1 + 2) & 0x100) == 0
           || (v3 = XcAddChildElementDWORD(a2, v8, (OLECHAR *)L"maxDelay", v9, *((_DWORD *)a1 + 11), v12)) == 0)
          && ((*((_DWORD *)a1 + 2) & 0x200) == 0
           || (v3 = XcAddChildElementBoolean(
                      a2,
                      v8,
                      L"allowAdditionalDialogs",
                      L"http://www.microsoft.com/networking/OneX/v1",
                      *((_DWORD *)a1 + 13),
                      v12)) == 0)
          && ((*((_DWORD *)a1 + 2) & 0x400) == 0
           || (v3 = XcAddChildElementDWORD(
                      a2,
                      v8,
                      (OLECHAR *)L"maxDelayWithAdditionalDialogs",
                      v9,
                      *((_DWORD *)a1 + 12),
                      v12)) == 0)
          && (*((_DWORD *)a1 + 2) & 0x800) != 0 )
        {
          v3 = XcAddChildElementBoolean(
                 a2,
                 v8,
                 L"userBasedVirtualLan",
                 L"http://www.microsoft.com/networking/OneX/v1",
                 *((_DWORD *)a1 + 14),
                 v12);
        }
      }
    }
  }
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&v14);
  return v3;
}

```

## disassembly

```asm
0x18003c52c  mov     r11, rsp
0x18003c52f  push    rbx
0x18003c530  push    rbp
0x18003c531  push    rsi
0x18003c532  push    rdi
0x18003c533  sub     rsp, 48h
0x18003c537  xor     esi, esi
0x18003c539  mov     rax, r8
0x18003c53c  test    byte ptr [rcx+8], 1
0x18003c540  mov     rbp, rdx
0x18003c543  mov     rdi, rcx
0x18003c546  mov     [r11+8], rsi
0x18003c54a  jz      loc_18003C679
0x18003c550  mov     ebx, [rcx+0Ch]
0x18003c553  and     ebx, 0Ch
0x18003c556  jz      loc_18003C679
0x18003c55c  lea     rcx, [r11+8]
0x18003c560  mov     rdx, rax; struct IXMLDOMNode *
0x18003c563  mov     [r11-40h], rcx
0x18003c567  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003c56e  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003c571  mov     [r11-48h], rsi
0x18003c575  lea     r8, aSinglesignon; "singleSignOn"
0x18003c57c  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18003c581  mov     esi, eax
0x18003c583  test    eax, eax
0x18003c585  jnz     loc_18003C679
0x18003c58b  lea     rax, off_1800424C0; "preLogon"
0x18003c592  mov     [rsp+68h+var_38], 2; unsigned int
0x18003c59a  mov     [rsp+68h+var_40], rax; struct IXMLDOMNode **
0x18003c59f  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003c5a6  mov     [rsp+68h+var_48], ebx; unsigned int
0x18003c5aa  lea     r8, aType; "type"
0x18003c5b1  mov     rbx, [rsp+68h+arg_0]
0x18003c5b6  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003c5b9  mov     rdx, rbx; struct IXMLDOMNode *
0x18003c5bc  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18003c5c1  mov     esi, eax
0x18003c5c3  test    eax, eax
0x18003c5c5  jnz     loc_18003C679
0x18003c5cb  test    dword ptr [rdi+8], 100h
0x18003c5d2  jz      short loc_18003C5F7
0x18003c5d4  mov     eax, [rdi+2Ch]
0x18003c5d7  lea     r8, aMaxdelay; "maxDelay"
0x18003c5de  mov     rdx, rbx; struct IXMLDOMNode *
0x18003c5e1  mov     [rsp+68h+var_48], eax; unsigned int
0x18003c5e5  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003c5e8  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18003c5ed  mov     esi, eax
0x18003c5ef  test    eax, eax
0x18003c5f1  jnz     loc_18003C679
0x18003c5f7  test    dword ptr [rdi+8], 200h
0x18003c5fe  jz      short loc_18003C626
0x18003c600  mov     eax, [rdi+34h]
0x18003c603  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003c60a  lea     r8, aAllowadditiona; "allowAdditionalDialogs"
0x18003c611  mov     [rsp+68h+var_48], eax; int
0x18003c615  mov     rdx, rbx; struct IXMLDOMNode *
0x18003c618  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003c61b  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x18003c620  mov     esi, eax
0x18003c622  test    eax, eax
0x18003c624  jnz     short loc_18003C679
0x18003c626  test    dword ptr [rdi+8], 400h
0x18003c62d  jz      short loc_18003C64E
0x18003c62f  mov     eax, [rdi+30h]
0x18003c632  lea     r8, aMaxdelaywithad; "maxDelayWithAdditionalDialogs"
0x18003c639  mov     rdx, rbx; struct IXMLDOMNode *
0x18003c63c  mov     [rsp+68h+var_48], eax; unsigned int
0x18003c640  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003c643  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18003c648  mov     esi, eax
0x18003c64a  test    eax, eax
0x18003c64c  jnz     short loc_18003C679
0x18003c64e  test    dword ptr [rdi+8], 800h
0x18003c655  jz      short loc_18003C679
0x18003c657  mov     eax, [rdi+38h]
0x18003c65a  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003c661  lea     r8, aUserbasedvirtu; "userBasedVirtualLan"
0x18003c668  mov     [rsp+68h+var_48], eax; int
0x18003c66c  mov     rdx, rbx; struct IXMLDOMNode *
0x18003c66f  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18003c672  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x18003c677  mov     esi, eax
0x18003c679  lea     rcx, [rsp+68h+arg_0]
0x18003c67e  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003c683  mov     eax, esi
0x18003c685  add     rsp, 48h
0x18003c689  pop     rdi
0x18003c68a  pop     rsi
0x18003c68b  pop     rbp
0x18003c68c  pop     rbx
0x18003c68d  retn
```
