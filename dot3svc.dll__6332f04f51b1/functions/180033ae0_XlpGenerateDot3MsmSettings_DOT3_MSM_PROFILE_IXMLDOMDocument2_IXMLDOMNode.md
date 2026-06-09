# XlpGenerateDot3MsmSettings(_DOT3_MSM_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x180033ae0`
- end: `0x180033c01`
- name: `?XlpGenerateDot3MsmSettings@@YAKPEAU_DOT3_MSM_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `289`
- prototype: `unsigned int(struct _DOT3_MSM_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033a2c`

## callees

- `0x1800326fc`
- `0x180033ae0`
- `0x18003aa34`
- `0x18003acc4`
- `0x18003bd50`

## string_xrefs

- `0x180033b1d`: `http://www.microsoft.com/networking/LAN/profile/v1`
- `0x180033b4c`: `http://www.microsoft.com/networking/LAN/profile/v1`
- `0x180033b75`: `http://www.microsoft.com/networking/LAN/profile/v1`
- `0x180033b9d`: `http://www.microsoft.com/networking/LAN/profile/v1`
- `0x180033b53`: `security`

## pseudocode

```c
__int64 __fastcall XlpGenerateDot3MsmSettings(
        struct _DOT3_MSM_PROFILE *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  unsigned int OnexProfile; // edi
  struct _ONEX_CONNECTION_PROFILE *v6; // rcx
  struct IXMLDOMNode **v8; // [rsp+28h] [rbp-20h]
  struct IXMLDOMNode **v9; // [rsp+28h] [rbp-20h]
  struct IXMLDOMNode *v10[3]; // [rsp+30h] [rbp-18h] BYREF
  struct IXMLDOMNode *v11; // [rsp+68h] [rbp+20h] BYREF

  v10[0] = 0;
  v11 = 0;
  OnexProfile = XcAddChildElement(
                  a2,
                  a3,
                  (OLECHAR *)L"MSM",
                  (OLECHAR *)L"http://www.microsoft.com/networking/LAN/profile/v1",
                  0,
                  v10);
  if ( !OnexProfile )
  {
    OnexProfile = XcAddChildElement(
                    a2,
                    v10[0],
                    (OLECHAR *)L"security",
                    (OLECHAR *)L"http://www.microsoft.com/networking/LAN/profile/v1",
                    0,
                    &v11);
    if ( !OnexProfile )
    {
      OnexProfile = XcAddChildElementBoolean(
                      a2,
                      v11,
                      L"OneXEnforced",
                      L"http://www.microsoft.com/networking/LAN/profile/v1",
                      *((_DWORD *)a1 + 1),
                      v8);
      if ( !OnexProfile )
      {
        OnexProfile = XcAddChildElementBoolean(
                        a2,
                        v11,
                        L"OneXEnabled",
                        L"http://www.microsoft.com/networking/LAN/profile/v1",
                        *(_DWORD *)a1,
                        v9);
        if ( !OnexProfile )
        {
          v6 = (struct _ONEX_CONNECTION_PROFILE *)*((_QWORD *)a1 + 2);
          if ( v6 )
            OnexProfile = XoGenerateOnexProfile(v6, a2, v11);
        }
      }
    }
  }
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&v11);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)v10);
  return OnexProfile;
}

```

## disassembly

```asm
0x180033ae0  mov     r11, rsp
0x180033ae3  mov     [r11+8], rsi
0x180033ae7  mov     [r11+10h], rdi
0x180033aeb  push    r14
0x180033aed  sub     rsp, 40h
0x180033af1  mov     r14, rcx
0x180033af4  mov     qword ptr [r11-18h], 0
0x180033afc  lea     rcx, [r11-18h]
0x180033b00  mov     qword ptr [r11+20h], 0
0x180033b08  mov     rax, r8
0x180033b0b  mov     [r11-20h], rcx
0x180033b0f  mov     rsi, rdx
0x180033b12  mov     qword ptr [r11-28h], 0
0x180033b1a  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180033b1d  lea     r9, aHttpWwwMicroso; "http://www.microsoft.com/networking/LAN"...
0x180033b24  lea     r8, aMsm; "MSM"
0x180033b2b  mov     rdx, rax; struct IXMLDOMNode *
0x180033b2e  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180033b33  mov     edi, eax
0x180033b35  test    eax, eax
0x180033b37  jnz     loc_180033BDA
0x180033b3d  mov     rdx, [rsp+48h+var_18]; struct IXMLDOMNode *
0x180033b42  lea     rax, [rsp+48h+arg_18]
0x180033b47  mov     [rsp+48h+var_20], rax; struct IXMLDOMNode **
0x180033b4c  lea     r9, aHttpWwwMicroso; "http://www.microsoft.com/networking/LAN"...
0x180033b53  lea     r8, aSecurity; "security"
0x180033b5a  mov     [rsp+48h+var_28], 0; OLECHAR *
0x180033b63  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180033b66  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180033b6b  mov     edi, eax
0x180033b6d  test    eax, eax
0x180033b6f  jnz     short loc_180033BDA
0x180033b71  mov     eax, [r14+4]
0x180033b75  lea     r9, aHttpWwwMicroso; "http://www.microsoft.com/networking/LAN"...
0x180033b7c  mov     rdx, [rsp+48h+arg_18]; struct IXMLDOMNode *
0x180033b81  lea     r8, aOnexenforced; "OneXEnforced"
0x180033b88  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180033b8b  mov     dword ptr [rsp+48h+var_28], eax; int
0x180033b8f  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x180033b94  mov     edi, eax
0x180033b96  test    eax, eax
0x180033b98  jnz     short loc_180033BDA
0x180033b9a  mov     eax, [r14]
0x180033b9d  lea     r9, aHttpWwwMicroso; "http://www.microsoft.com/networking/LAN"...
0x180033ba4  mov     rdx, [rsp+48h+arg_18]; struct IXMLDOMNode *
0x180033ba9  lea     r8, aOnexenabled; "OneXEnabled"
0x180033bb0  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180033bb3  mov     dword ptr [rsp+48h+var_28], eax; int
0x180033bb7  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x180033bbc  mov     edi, eax
0x180033bbe  test    eax, eax
0x180033bc0  jnz     short loc_180033BDA
0x180033bc2  mov     rcx, [r14+10h]; struct _ONEX_CONNECTION_PROFILE *
0x180033bc6  test    rcx, rcx
0x180033bc9  jz      short loc_180033BDA
0x180033bcb  mov     r8, [rsp+48h+arg_18]; struct IXMLDOMNode *
0x180033bd0  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x180033bd3  call    ?XoGenerateOnexProfile@@YAKPEAU_ONEX_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XoGenerateOnexProfile(_ONEX_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x180033bd8  mov     edi, eax
0x180033bda  lea     rcx, [rsp+48h+arg_18]
0x180033bdf  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x180033be4  lea     rcx, [rsp+48h+var_18]
0x180033be9  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x180033bee  mov     rsi, [rsp+48h+arg_0]
0x180033bf3  mov     eax, edi
0x180033bf5  mov     rdi, [rsp+48h+arg_8]
0x180033bfa  add     rsp, 40h
0x180033bfe  pop     r14
0x180033c00  retn
```
