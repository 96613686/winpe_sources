# GetSetActivityId(_GUID *)

- ea: `0x180002b08`
- end: `0x180002c4a`
- name: `?GetSetActivityId@@YAXPEAU_GUID@@@Z`
- size: `322`
- prototype: `void __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002284`
- `0x18000afc0`

## callees

- `0x180002b08`
- `0x180002f10`
- `0x180002f4c`
- `0x18000bbf0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002b6c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002bc0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002bd2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002b6c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002bc0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180002bd2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180002bac`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180002bac`

## pseudocode

```c
void __fastcall GetSetActivityId(struct _GUID *a1)
{
  int v2; // r8d
  int v3; // r9d
  int v4; // r8d
  int v5; // r9d
  _QWORD *v6; // rcx
  GUID ActivityId; // [rsp+30h] [rbp-38h] BYREF
  __int128 Source1; // [rsp+40h] [rbp-28h] BYREF

  ActivityId = 0;
  Source1 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  EventActivityIdControl(1u, &ActivityId);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v2, v3, (__int64)&ActivityId);
  if ( RtlCompareMemory(&Source1, &ActivityId, 0x10u) != 16 || EventActivityIdControl(3u, &ActivityId) )
    goto LABEL_12;
  EventActivityIdControl(2u, &ActivityId);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v4, v5, (__int64)&ActivityId);
LABEL_12:
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_s(v6[2], 20, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
LABEL_16:
  *a1 = ActivityId;
}

```

## disassembly

```asm
0x180002b08  mov     [rsp+arg_8], rbx
0x180002b0d  push    rsi
0x180002b0e  sub     rsp, 60h
0x180002b12  mov     rax, cs:__security_cookie
0x180002b19  xor     rax, rsp
0x180002b1c  mov     [rsp+68h+var_18], rax
0x180002b21  xorps   xmm0, xmm0
0x180002b24  xorps   xmm1, xmm1
0x180002b27  movups  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x180002b2c  mov     rbx, rcx
0x180002b2f  movups  [rsp+68h+Source1], xmm1
0x180002b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b3b  lea     rsi, WPP_GLOBAL_Control
0x180002b42  cmp     rcx, rsi
0x180002b45  jz      short loc_180002B62
0x180002b47  cmp     byte ptr [rcx+19h], 4
0x180002b4b  jb      short loc_180002B62
0x180002b4d  mov     rcx, [rcx+10h]
0x180002b51  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002b58  mov     edx, 11h
0x180002b5d  call    WPP_SF_s
0x180002b62  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x180002b67  mov     ecx, 1; ControlCode
0x180002b6c  call    cs:__imp_EventActivityIdControl
0x180002b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b79  cmp     rcx, rsi
0x180002b7c  jz      short loc_180002B9C
0x180002b7e  cmp     byte ptr [rcx+19h], 4
0x180002b82  jb      short loc_180002B9C
0x180002b84  mov     rcx, [rcx+10h]
0x180002b88  lea     rax, [rsp+68h+ActivityId]
0x180002b8d  mov     edx, 12h
0x180002b92  mov     [rsp+68h+var_48], rax
0x180002b97  call    WPP_SF_s_guid_
0x180002b9c  mov     r8d, 10h; Length
0x180002ba2  lea     rdx, [rsp+68h+ActivityId]; Source2
0x180002ba7  lea     rcx, [rsp+68h+Source1]; Source1
0x180002bac  call    cs:__imp_RtlCompareMemory
0x180002bb2  cmp     rax, 10h
0x180002bb6  jnz     short loc_180002C02
0x180002bb8  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x180002bbd  lea     ecx, [rax-0Dh]; ControlCode
0x180002bc0  call    cs:__imp_EventActivityIdControl
0x180002bc6  test    eax, eax
0x180002bc8  jnz     short loc_180002C02
0x180002bca  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x180002bcf  lea     ecx, [rax+2]; ControlCode
0x180002bd2  call    cs:__imp_EventActivityIdControl
0x180002bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bdf  cmp     rcx, rsi
0x180002be2  jz      short loc_180002C29
0x180002be4  cmp     byte ptr [rcx+19h], 4
0x180002be8  jb      short loc_180002C09
0x180002bea  mov     rcx, [rcx+10h]
0x180002bee  lea     rax, [rsp+68h+ActivityId]
0x180002bf3  mov     edx, 13h
0x180002bf8  mov     [rsp+68h+var_48], rax
0x180002bfd  call    WPP_SF_s_guid_
0x180002c02  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c09  cmp     rcx, rsi
0x180002c0c  jz      short loc_180002C29
0x180002c0e  cmp     byte ptr [rcx+19h], 4
0x180002c12  jb      short loc_180002C29
0x180002c14  mov     rcx, [rcx+10h]
0x180002c18  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002c1f  mov     edx, 14h
0x180002c24  call    WPP_SF_s
0x180002c29  movups  xmm0, xmmword ptr [rsp+68h+ActivityId.Data1]
0x180002c2e  movdqu  xmmword ptr [rbx], xmm0
0x180002c32  mov     rcx, [rsp+68h+var_18]
0x180002c37  xor     rcx, rsp; StackCookie
0x180002c3a  call    __security_check_cookie
0x180002c3f  mov     rbx, [rsp+68h+arg_8]
0x180002c44  add     rsp, 60h
0x180002c48  pop     rsi
0x180002c49  retn
```
