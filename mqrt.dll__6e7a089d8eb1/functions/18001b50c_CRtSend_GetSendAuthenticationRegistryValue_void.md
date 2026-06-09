# CRtSend::GetSendAuthenticationRegistryValue(void)

- ea: `0x18001b50c`
- end: `0x18001b5f3`
- name: `?GetSendAuthenticationRegistryValue@CRtSend@@AEAAKXZ`
- size: `231`
- prototype: `unsigned int __fastcall(CRtSend *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ad18`

## callees

- `0x180012e88`
- `0x18001b50c`
- `0x1800237d4`

## string_xrefs

- `0x18001b547`: `security\SendMsgAuthn`

## pseudocode

```c
__int64 __fastcall CRtSend::GetSendAuthenticationRegistryValue(CRtSend *this)
{
  __int64 result; // rax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  int v4; // [rsp+30h] [rbp-38h] BYREF
  const WCHAR *v5; // [rsp+38h] [rbp-30h]
  const wchar_t *v6; // [rsp+40h] [rbp-28h]
  int v7; // [rsp+48h] [rbp-20h]
  __int64 v8; // [rsp+50h] [rbp-18h]

  if ( !CRtSend::s_fAuthnAlreadyRead )
  {
    v4 = 0;
    CRtSend::s_dwAuthnLevel = 2;
    v5 = &Class;
    v6 = L"security\\SendMsgAuthn";
    v7 = 2;
    v8 = 0;
    QueryValueInternal((struct RegEntry *)&v4);
    result = CRtSend::s_dwAuthnLevel;
    if ( (CRtSend::s_dwAuthnLevel & 0xFFFFFFF0) != 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 2) == 0 )
        goto LABEL_12;
      v3 = 17;
    }
    else
    {
      if ( (CRtSend::s_dwAuthnLevel & 1) == 0 || CRtSend::s_dwAuthnLevel == 1 )
        goto LABEL_13;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 2) == 0 )
      {
LABEL_12:
        result = 2;
        CRtSend::s_dwAuthnLevel = 2;
LABEL_13:
        CRtSend::s_fAuthnAlreadyRead = 1;
        return result;
      }
      v3 = 18;
    }
    WPP_SF_dd(v2[32], v3, &WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids, CRtSend::s_dwAuthnLevel, 2);
    goto LABEL_12;
  }
  return CRtSend::s_dwAuthnLevel;
}

```

## disassembly

```asm
0x18001b50c  mov     r11, rsp
0x18001b50f  push    rbx
0x18001b510  sub     rsp, 60h
0x18001b514  xor     ecx, ecx
0x18001b516  cmp     cs:?s_fAuthnAlreadyRead@CRtSend@@0HA, ecx; int CRtSend::s_fAuthnAlreadyRead
0x18001b51c  jnz     loc_18001B5E7
0x18001b522  mov     [rsp+68h+var_38], ecx
0x18001b526  lea     ebx, [rcx+2]
0x18001b529  lea     edx, [rcx+4]
0x18001b52c  mov     cs:?s_dwAuthnLevel@CRtSend@@0KA, ebx; ulong CRtSend::s_dwAuthnLevel
0x18001b532  lea     rax, Class
0x18001b539  mov     r9d, edx
0x18001b53c  mov     [r11-30h], rax
0x18001b540  lea     r8, ?s_dwAuthnLevel@CRtSend@@0KA; ulong CRtSend::s_dwAuthnLevel
0x18001b547  lea     rax, aSecuritySendms; "security\\SendMsgAuthn"
0x18001b54e  mov     [r11-28h], rax
0x18001b552  mov     [rsp+68h+var_20], ebx
0x18001b556  mov     [r11-18h], rcx
0x18001b55a  lea     rcx, [r11-38h]; struct RegEntry *
0x18001b55e  call    QueryValueInternal
0x18001b563  mov     eax, cs:?s_dwAuthnLevel@CRtSend@@0KA; ulong CRtSend::s_dwAuthnLevel
0x18001b569  test    eax, 0FFFFFFF0h
0x18001b56e  jz      short loc_18001B590
0x18001b570  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b577  lea     rdx, WPP_GLOBAL_Control
0x18001b57e  cmp     rcx, rdx
0x18001b581  jz      short loc_18001B5D3
0x18001b583  test    [rcx+10Ch], bl
0x18001b589  jz      short loc_18001B5D3
0x18001b58b  lea     edx, [rbx+0Fh]
0x18001b58e  jmp     short loc_18001B5B9
0x18001b590  test    al, 1
0x18001b592  jz      short loc_18001B5DB
0x18001b594  cmp     eax, 1
0x18001b597  jz      short loc_18001B5DB
0x18001b599  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5a0  lea     rdx, WPP_GLOBAL_Control
0x18001b5a7  cmp     rcx, rdx
0x18001b5aa  jz      short loc_18001B5D3
0x18001b5ac  test    [rcx+10Ch], bl
0x18001b5b2  jz      short loc_18001B5D3
0x18001b5b4  mov     edx, 12h
0x18001b5b9  mov     rcx, [rcx+100h]
0x18001b5c0  lea     r8, WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids
0x18001b5c7  mov     r9d, eax
0x18001b5ca  mov     [rsp+68h+var_48], ebx
0x18001b5ce  call    WPP_SF_dd
0x18001b5d3  mov     eax, ebx
0x18001b5d5  mov     cs:?s_dwAuthnLevel@CRtSend@@0KA, ebx; ulong CRtSend::s_dwAuthnLevel
0x18001b5db  mov     cs:?s_fAuthnAlreadyRead@CRtSend@@0HA, 1; int CRtSend::s_fAuthnAlreadyRead
0x18001b5e5  jmp     short loc_18001B5ED
0x18001b5e7  mov     eax, cs:?s_dwAuthnLevel@CRtSend@@0KA; ulong CRtSend::s_dwAuthnLevel
0x18001b5ed  add     rsp, 60h
0x18001b5f1  pop     rbx
0x18001b5f2  retn
```
