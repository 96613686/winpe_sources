# CRtSend::SignMessageForSrmpProtocol(void)

- ea: `0x18001c888`
- end: `0x18001c90d`
- name: `?SignMessageForSrmpProtocol@CRtSend@@AEAAJXZ`
- size: `133`
- prototype: `__int64 __fastcall(CRtSend *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c5f4`

## callees

- `0x180007dcc`
- `0x180013c74`
- `0x18001958c`
- `0x18001c888`

## pseudocode

```c
__int64 __fastcall CRtSend::SignMessageForSrmpProtocol(CRtSend *this)
{
  const char **v2; // rsi
  int v3; // eax
  unsigned int v4; // edi
  unsigned int v6; // eax
  const bad_CryptoApi *v7; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v8; // [rsp+40h] [rbp+8h]

  try
  {
    v2 = (const char **)((char *)this + 848);
    v3 = SignMessageXmlDSig(*((_DWORD **)this + 93), (__int64)this + 40, (__int64)this + 848);
  }
  catch ( const bad_CryptoApi *v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v6 = (*(__int64 (__fastcall **)(const bad_CryptoApi *))(*(_QWORD *)v7 + 16LL))(v7);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 28, &WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids, v6);
    }
    v8 = -1072824272;
    LogMsgHR(-1072824272, (wchar_t *)L"rt/CRtSend", 0xA7u);
    return v8;
  }
  catch ( bad_parameter )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 29, &WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids);
    v8 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"rt/CRtSend", 0xA8u);
    return v8;
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 30, &WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids);
    return (unsigned int)-1072824281;
  }
  v4 = v3;
  if ( v3 >= 0 )
  {
    v8 = v3;
    *((_DWORD *)this + 170) = mqstrlen(*v2);
    *((_QWORD *)this + 84) = *((_QWORD *)this + 107);
    return v8;
  }
  else
  {
    LogMsgHR(v3, (wchar_t *)L"rt/CRtSend", 0xA6u);
    return v4;
  }
}

```

## disassembly

```asm
0x18001c888  mov     [rsp+arg_8], rbx
0x18001c88d  mov     [rsp+arg_10], rsi
0x18001c892  push    rdi
0x18001c893  sub     rsp, 30h
0x18001c897  mov     rbx, rcx
0x18001c89a  lea     rsi, [rcx+350h]
0x18001c8a1  lea     rdx, [rcx+28h]
0x18001c8a5  mov     r8, rsi
0x18001c8a8  mov     rcx, [rcx+2E8h]
0x18001c8af  call    ?SignMessageXmlDSig@@YAJPEAVRTSecurityContextBase@@PEAVCACSendParameters@@AEAV?$AP@D@@@Z; SignMessageXmlDSig(RTSecurityContextBase *,CACSendParameters *,AP<char> &)
0x18001c8b4  mov     edi, eax
0x18001c8b6  test    eax, eax
0x18001c8b8  jns     short loc_18001C8D2
0x18001c8ba  mov     r8d, 0A6h; unsigned __int16
0x18001c8c0  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001c8c7  mov     ecx, eax; int
0x18001c8c9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001c8ce  mov     eax, edi
0x18001c8d0  jmp     short loc_18001C8FC
0x18001c8d2  mov     [rsp+38h+arg_0], edi
0x18001c8d6  mov     rcx, [rsi]; char *
0x18001c8d9  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x18001c8de  mov     [rbx+2A8h], eax
0x18001c8e4  mov     rax, [rbx+358h]
0x18001c8eb  mov     [rbx+2A0h], rax
0x18001c8f2  jmp     short loc_18001C8F8
0x18001c8f4  jmp     short loc_18001C8F8
0x18001c8f6  jmp     short $+2
0x18001c8f8  mov     eax, [rsp+38h+arg_0]
0x18001c8fc  mov     rbx, [rsp+38h+arg_8]
0x18001c901  mov     rsi, [rsp+38h+arg_10]
0x18001c906  add     rsp, 30h
0x18001c90a  pop     rdi
0x18001c90b  retn
```
