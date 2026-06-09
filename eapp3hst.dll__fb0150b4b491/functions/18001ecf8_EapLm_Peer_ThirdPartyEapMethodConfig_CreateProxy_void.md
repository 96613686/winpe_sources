# EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)

- ea: `0x18001ecf8`
- end: `0x18001edd5`
- name: `?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ`
- size: `221`
- prototype: `LPVOID *__fastcall(const struct _EAP_METHOD_TYPE *, LPVOID *)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e8b0`
- `0x18001eb30`
- `0x18001ede0`
- `0x18001efa0`
- `0x18001f170`
- `0x18001f680`
- `0x18001f7e0`
- `0x18001f990`
- `0x18001fb30`

## callees

- `0x180004ec0`
- `0x180005994`
- `0x1800154c8`
- `0x18001ecf8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ed71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ed71`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
LPVOID *__fastcall EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(const struct _EAP_METHOD_TYPE *a1, LPVOID *a2)
{
  const struct EapHost::EapMethodType *v5; // rax
  unsigned int v6; // r9d
  _BYTE v7[40]; // [rsp+38h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids);
  *a2 = 0;
  if ( CoCreateInstance(
         &GUID_1f7d1be9_7a50_40b6_a605_c4f3696f49c0,
         0,
         0x10004u,
         &GUID_32c5a81f_27c0_4e66_a894_786f646f1236,
         a2) < 0 )
  {
    v5 = (const struct EapHost::EapMethodType *)EapHost::EapMethodType::EapMethodType(
                                                  (EapHost::EapMethodType *)v7,
                                                  a1 + 1);
    EapHost::EapException::Throw(v6, v5);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids);
  return a2;
}

```

## disassembly

```asm
0x18001ecf8  mov     rax, rsp
0x18001ecfb  mov     [rax+8], rbx
0x18001ecff  mov     [rax+18h], rsi
0x18001ed03  mov     [rax+10h], rdx
0x18001ed07  push    rdi
0x18001ed08  sub     rsp, 60h
0x18001ed0c  mov     rbx, rdx
0x18001ed0f  mov     rdi, rcx
0x18001ed12  mov     dword ptr [rax-38h], 0
0x18001ed19  lea     rsi, WPP_GLOBAL_Control
0x18001ed20  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed27  cmp     rcx, rsi
0x18001ed2a  jz      short loc_18001ED47
0x18001ed2c  test    byte ptr [rcx+1Ch], 4
0x18001ed30  jz      short loc_18001ED47
0x18001ed32  mov     edx, 12h
0x18001ed37  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001ed3e  mov     rcx, [rcx+10h]
0x18001ed42  call    WPP_SF_
0x18001ed47  mov     qword ptr [rbx], 0
0x18001ed4e  mov     [rsp+68h+var_38], 1
0x18001ed56  mov     [rsp+68h+ppv], rbx; ppv
0x18001ed5b  lea     r9, _GUID_32c5a81f_27c0_4e66_a894_786f646f1236; riid
0x18001ed62  xor     edx, edx; pUnkOuter
0x18001ed64  mov     r8d, 10004h; dwClsContext
0x18001ed6a  lea     rcx, _GUID_1f7d1be9_7a50_40b6_a605_c4f3696f49c0; rclsid
0x18001ed71  call    cs:__imp_CoCreateInstance
0x18001ed77  mov     r9d, eax
0x18001ed7a  test    eax, eax
0x18001ed7c  js      short loc_18001EDBA
0x18001ed7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed85  cmp     rcx, rsi
0x18001ed88  jz      short loc_18001EDA5
0x18001ed8a  test    byte ptr [rcx+1Ch], 4
0x18001ed8e  jz      short loc_18001EDA5
0x18001ed90  mov     edx, 13h
0x18001ed95  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001ed9c  mov     rcx, [rcx+10h]
0x18001eda0  call    WPP_SF_
0x18001eda5  mov     rax, rbx
0x18001eda8  lea     r11, [rsp+68h+var_8]
0x18001edad  mov     rbx, [r11+10h]
0x18001edb1  mov     rsi, [r11+20h]
0x18001edb5  mov     rsp, r11
0x18001edb8  pop     rdi
0x18001edb9  retn
0x18001edba  lea     rdx, [rdi+10h]; struct _EAP_METHOD_TYPE *
0x18001edbe  lea     rcx, [rsp+68h+var_30]; this
0x18001edc3  call    ??0EapMethodType@EapHost@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapHost::EapMethodType::EapMethodType(_EAP_METHOD_TYPE const &)
0x18001edc8  nop
0x18001edc9  mov     rdx, rax; struct EapHost::EapMethodType *
0x18001edcc  mov     ecx, r9d; unsigned int
0x18001edcf  call    ?Throw@EapException@EapHost@@SAXJAEBVEapMethodType@2@@Z; EapHost::EapException::Throw(long,EapHost::EapMethodType const &)
```
