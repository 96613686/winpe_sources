# NgcKeyTransportKey::OpenKey(_NGC_IDP_ACCOUNT_INFO *,ushort const *)

- ea: `0x1800193d4`
- end: `0x18001941b`
- name: `?OpenKey@NgcKeyTransportKey@@QEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG@Z`
- size: `71`
- prototype: `__int64 __fastcall(NgcKeyTransportKey *this, struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e940`
- `0x1800127d4`
- `0x180012858`

## callees

- `0x18000b0fc`
- `0x1800193d4`
- `0x180019424`

## string_xrefs

- `0x1800193f3`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcKeyTransportKey::OpenKey(
        NgcKeyTransportKey *this,
        struct _NGC_IDP_ACCOUNT_INFO *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = NgcKeyTransportKey::OpenKeyBasedOnKeyDatabase(this, a2, a3);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  if ( (unsigned int)(v3 + 2147024894) <= 1 )
    v4 = -2146893807;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE5,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
    (const char *)v4,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800193d4  push    rbx; int
0x1800193d6  sub     rsp, 20h
0x1800193da  call    ?OpenKeyBasedOnKeyDatabase@NgcKeyTransportKey@@AEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG@Z; NgcKeyTransportKey::OpenKeyBasedOnKeyDatabase(_NGC_IDP_ACCOUNT_INFO *,ushort const *)
0x1800193df  mov     ebx, eax
0x1800193e1  test    eax, eax
0x1800193e3  jns     short loc_180019413
0x1800193e5  lea     ecx, [rax+7FF8FFFEh]
0x1800193eb  mov     edx, 0E5h; void *
0x1800193f0  cmp     ecx, 1
0x1800193f3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800193fa  mov     rcx, [rsp+28h]; this
0x1800193ff  mov     eax, 80090011h
0x180019404  cmovbe  ebx, eax
0x180019407  mov     r9d, ebx; char *
0x18001940a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001940f  mov     eax, ebx
0x180019411  jmp     short loc_180019415
0x180019413  xor     eax, eax
0x180019415  add     rsp, 20h
0x180019419  pop     rbx
0x18001941a  retn
```
