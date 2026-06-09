# CxPlatTlsParamGet

- ea: `0x140035c4c`
- end: `0x140035f36`
- name: `CxPlatTlsParamGet`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400235bc`

## callees

- `0x140035c4c`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003fdf8`

## import_xrefs

- `ksecdd!QueryContextAttributesExW` at `0x140035cf4`
- `ksecdd!QueryContextAttributesExW` at `0x140035cf4`
- `ksecdd!QueryContextAttributesW` at `0x140035d33`
- `ksecdd!QueryContextAttributesW` at `0x140035d6b`
- `ksecdd!QueryContextAttributesW` at `0x140035e32`
- `ksecdd!QueryContextAttributesW` at `0x140035e96`
- `ksecdd!QueryContextAttributesW` at `0x140035d33`
- `ksecdd!QueryContextAttributesW` at `0x140035d6b`
- `ksecdd!QueryContextAttributesW` at `0x140035e32`
- `ksecdd!QueryContextAttributesW` at `0x140035e96`
- `ksecdd!QuerySecurityContextToken` at `0x140035ccd`
- `ksecdd!QuerySecurityContextToken` at `0x140035ccd`

## string_xrefs

- `0x140035d8b`: `Query Application Protocol`

## pseudocode

```c
__int64 __fastcall CxPlatTlsParamGet(struct _SecHandle *a1, int a2, unsigned int *a3, __int64 a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  SECURITY_STATUS ContextAttributesW; // ebx
  int v13; // ecx
  const char *v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // eax
  __int128 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+48h] [rbp-B8h]
  _DWORD pBuffer[172]; // [rsp+50h] [rbp-B0h] BYREF

  v7 = a2 - 100663296;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 0xFFFFFF;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 )
            return (unsigned int)-1073741637;
          if ( *a3 < 8 )
          {
            *a3 = 8;
            return (unsigned int)-1073741789;
          }
          if ( a4 )
            return (unsigned int)QuerySecurityContextToken(a1 + 1, (void **)a4);
          return (unsigned int)-1073741811;
        }
        if ( *a3 >= 0x10 )
        {
          if ( a4 )
            return (unsigned int)QueryContextAttributesExW(
                                   a1 + 1,
                                   *(_DWORD *)a4,
                                   *(void **)(a4 + 8),
                                   *(_DWORD *)(a4 + 4));
          return (unsigned int)-1073741811;
        }
      }
      else if ( *a3 >= 0x10 )
      {
        if ( a4 )
          return (unsigned int)QueryContextAttributesW(a1 + 1, *(_DWORD *)a4, *(void **)(a4 + 8));
        return (unsigned int)-1073741811;
      }
      *a3 = 16;
      return (unsigned int)-1073741789;
    }
    if ( !a4 )
      return (unsigned int)-1073741811;
    memset(pBuffer, 0, 0x108u);
    ContextAttributesW = QueryContextAttributesW(a1 + 1, 0x23u, pBuffer);
    if ( ContextAttributesW < 0 )
    {
      if ( byte_14005C48D >= 0 )
        return (unsigned int)ContextAttributesW;
      v14 = "Query Application Protocol";
LABEL_37:
      McTemplateU0pqs_EtwWriteTransfer(
        v13,
        (unsigned int)QuicTlsErrorStatus,
        a1[4].dwUpper,
        ContextAttributesW,
        (__int64)v14);
      return (unsigned int)ContextAttributesW;
    }
    if ( pBuffer[0] == 1 )
    {
      v15 = LOBYTE(pBuffer[2]);
      v16 = *a3;
      *a3 = LOBYTE(pBuffer[2]);
      if ( v16 >= v15 )
      {
        memmove((void *)a4, (char *)&pBuffer[2] + 1, v15);
        return (unsigned int)ContextAttributesW;
      }
      return (unsigned int)-1073741789;
    }
    if ( byte_14005C48D < 0 )
      McTemplateU0pqs_EtwWriteTransfer(
        v13,
        (unsigned int)QuicTlsErrorStatus,
        a1[4].dwUpper,
        pBuffer[0],
        (__int64)"ALPN negotiation status");
    return (unsigned int)-1073741436;
  }
  else
  {
    if ( *a3 < 0x20 )
    {
      *a3 = 36;
      return (unsigned int)-1073741789;
    }
    if ( !a4 )
      return (unsigned int)-1073741811;
    v19 = 0;
    v20 = 0;
    v18 = 0;
    ContextAttributesW = QueryContextAttributesW(a1 + 1, 0x5Au, &v18);
    if ( ContextAttributesW < 0 )
    {
      if ( byte_14005C48D >= 0 )
        return (unsigned int)ContextAttributesW;
      v14 = "Query Connection Info";
      goto LABEL_37;
    }
    memset(pBuffer, 0, 0x2A8u);
    ContextAttributesW = QueryContextAttributesW(a1 + 1, 0x64u, pBuffer);
    if ( ContextAttributesW < 0 )
    {
      if ( byte_14005C48D >= 0 )
        return (unsigned int)ContextAttributesW;
      v14 = "Query Cipher Info";
      goto LABEL_37;
    }
    *(_DWORD *)a4 = (v18 & 0x3000) != 0 ? 0x3000 : 0;
    *(_QWORD *)(a4 + 4) = *(_QWORD *)((char *)&v18 + 4);
    *(_DWORD *)(a4 + 12) = HIDWORD(v18);
    *(_QWORD *)(a4 + 16) = v19;
    *(_DWORD *)(a4 + 24) = v20;
    *(_DWORD *)(a4 + 28) = pBuffer[2];
    if ( *a3 >= 0x24 )
      *(_DWORD *)(a4 + 32) = pBuffer[169];
  }
  return (unsigned int)ContextAttributesW;
}

```

## disassembly

```asm
0x140035c4c  mov     [rsp-8+arg_8], rbx
0x140035c51  push    rbp
0x140035c52  push    rsi
0x140035c53  push    rdi
0x140035c54  push    r14
0x140035c56  push    r15
0x140035c58  lea     rbp, [rsp-210h]
0x140035c60  sub     rsp, 310h
0x140035c67  mov     rax, cs:__security_cookie
0x140035c6e  xor     rax, rsp
0x140035c71  mov     [rbp+230h+var_30], rax
0x140035c78  mov     rdi, r9
0x140035c7b  mov     rsi, r8
0x140035c7e  mov     r14, rcx
0x140035c81  sub     edx, 6000000h
0x140035c87  jz      loc_140035DF8
0x140035c8d  sub     edx, 1
0x140035c90  jz      loc_140035D46
0x140035c96  sub     edx, 0FFFFFFh
0x140035c9c  jz      short loc_140035D02
0x140035c9e  sub     edx, 1
0x140035ca1  jz      short loc_140035CDB
0x140035ca3  cmp     edx, 1
0x140035ca6  jz      short loc_140035CB2
0x140035ca8  mov     ebx, 0C00000BBh
0x140035cad  jmp     loc_140035F0D
0x140035cb2  cmp     dword ptr [r8], 8
0x140035cb6  jnb     short loc_140035CC1
0x140035cb8  mov     dword ptr [r8], 8
0x140035cbf  jmp     short loc_140035D0F
0x140035cc1  test    rdi, rdi
0x140035cc4  jz      short loc_140035D1E
0x140035cc6  add     rcx, 10h; phContext
0x140035cca  mov     rdx, rdi; Token
0x140035ccd  call    cs:__imp_QuerySecurityContextToken
0x140035cd4  nop     dword ptr [rax+rax+00h]
0x140035cd9  jmp     short loc_140035D3F
0x140035cdb  cmp     dword ptr [r8], 10h
0x140035cdf  jb      short loc_140035D08
0x140035ce1  test    rdi, rdi
0x140035ce4  jz      short loc_140035D1E
0x140035ce6  mov     r9d, [r9+4]; cbBuffer
0x140035cea  add     rcx, 10h; phContext
0x140035cee  mov     r8, [rdi+8]; pBuffer
0x140035cf2  mov     edx, [rdi]; ulAttribute
0x140035cf4  call    cs:__imp_QueryContextAttributesExW
0x140035cfb  nop     dword ptr [rax+rax+00h]
0x140035d00  jmp     short loc_140035D3F
0x140035d02  cmp     dword ptr [r8], 10h
0x140035d06  jnb     short loc_140035D19
0x140035d08  mov     dword ptr [r8], 10h
0x140035d0f  mov     ebx, 0C0000023h
0x140035d14  jmp     loc_140035F0D
0x140035d19  test    rdi, rdi
0x140035d1c  jnz     short loc_140035D28
0x140035d1e  mov     ebx, 0C000000Dh
0x140035d23  jmp     loc_140035F0D
0x140035d28  mov     r8, [r9+8]; pBuffer
0x140035d2c  add     rcx, 10h; phContext
0x140035d30  mov     edx, [r9]; ulAttribute
0x140035d33  call    cs:__imp_QueryContextAttributesW
0x140035d3a  nop     dword ptr [rax+rax+00h]
0x140035d3f  mov     ebx, eax
0x140035d41  jmp     loc_140035F0D
0x140035d46  test    rdi, rdi
0x140035d49  jz      short loc_140035D1E
0x140035d4b  xor     edx, edx; Val
0x140035d4d  lea     rcx, [rsp+330h+pBuffer]; void *
0x140035d52  mov     r8d, 108h; Size
0x140035d58  call    memset
0x140035d5d  lea     rcx, [r14+10h]; phContext
0x140035d61  mov     edx, 23h ; '#'; ulAttribute
0x140035d66  lea     r8, [rsp+330h+pBuffer]; pBuffer
0x140035d6b  call    cs:__imp_QueryContextAttributesW
0x140035d72  nop     dword ptr [rax+rax+00h]
0x140035d77  mov     ebx, eax
0x140035d79  test    eax, eax
0x140035d7b  jns     short loc_140035D97
0x140035d7d  mov     al, cs:byte_14005C48D
0x140035d83  test    al, al
0x140035d85  jns     loc_140035F0D
0x140035d8b  lea     rax, aQueryApplicati; "Query Application Protocol"
0x140035d92  jmp     loc_140035E59
0x140035d97  mov     r9d, [rsp+330h+pBuffer]
0x140035d9c  cmp     r9d, 1
0x140035da0  jz      short loc_140035DD2
0x140035da2  mov     al, cs:byte_14005C48D
0x140035da8  test    al, al
0x140035daa  jns     short loc_140035DC8
0x140035dac  mov     r8, [r14+48h]
0x140035db0  lea     rax, aAlpnNegotiatio; "ALPN negotiation status"
0x140035db7  lea     rdx, QuicTlsErrorStatus
0x140035dbe  mov     [rsp+330h+var_310], rax
0x140035dc3  call    McTemplateU0pqs_EtwWriteTransfer
0x140035dc8  mov     ebx, 0C0000184h
0x140035dcd  jmp     loc_140035F0D
0x140035dd2  movzx   edx, byte ptr [rsp+330h+Src]
0x140035dd7  mov     eax, [rsi]
0x140035dd9  mov     [rsi], edx
0x140035ddb  cmp     eax, edx
0x140035ddd  jb      loc_140035D0F
0x140035de3  mov     r8d, edx; Size
0x140035de6  mov     rcx, rdi; void *
0x140035de9  lea     rdx, [rsp+330h+Src+1]; Src
0x140035dee  call    memmove
0x140035df3  jmp     loc_140035F0D
0x140035df8  cmp     dword ptr [r8], 20h ; ' '
0x140035dfc  jnb     short loc_140035E0A
0x140035dfe  mov     dword ptr [r8], 24h ; '$'
0x140035e05  jmp     loc_140035D0F
0x140035e0a  test    rdi, rdi
0x140035e0d  jz      loc_140035D1E
0x140035e13  xor     eax, eax
0x140035e15  lea     r8, [rsp+330h+var_300]; pBuffer
0x140035e1a  xorps   xmm0, xmm0
0x140035e1d  mov     [rsp+330h+var_2F0], rax
0x140035e22  add     rcx, 10h; phContext
0x140035e26  mov     [rsp+330h+var_2E8], eax
0x140035e2a  movups  [rsp+330h+var_300], xmm0
0x140035e2f  lea     edx, [rax+5Ah]; ulAttribute
0x140035e32  call    cs:__imp_QueryContextAttributesW
0x140035e39  nop     dword ptr [rax+rax+00h]
0x140035e3e  mov     ebx, eax
0x140035e40  test    eax, eax
0x140035e42  jns     short loc_140035E76
0x140035e44  mov     al, cs:byte_14005C48D
0x140035e4a  test    al, al
0x140035e4c  jns     loc_140035F0D
0x140035e52  lea     rax, aQueryConnectio; "Query Connection Info"
0x140035e59  mov     r8, [r14+48h]
0x140035e5d  lea     rdx, QuicTlsErrorStatus
0x140035e64  mov     r9d, ebx
0x140035e67  mov     [rsp+330h+var_310], rax
0x140035e6c  call    McTemplateU0pqs_EtwWriteTransfer
0x140035e71  jmp     loc_140035F0D
0x140035e76  xor     edx, edx; Val
0x140035e78  lea     rcx, [rsp+330h+pBuffer]; void *
0x140035e7d  mov     r8d, 2A8h; Size
0x140035e83  call    memset
0x140035e88  lea     r8, [rsp+330h+pBuffer]; pBuffer
0x140035e8d  mov     edx, 64h ; 'd'; ulAttribute
0x140035e92  lea     rcx, [r14+10h]; phContext
0x140035e96  call    cs:__imp_QueryContextAttributesW
0x140035e9d  nop     dword ptr [rax+rax+00h]
0x140035ea2  mov     ebx, eax
0x140035ea4  test    eax, eax
0x140035ea6  jns     short loc_140035EBB
0x140035ea8  mov     al, cs:byte_14005C48D
0x140035eae  test    al, al
0x140035eb0  jns     short loc_140035F0D
0x140035eb2  lea     rax, aQueryCipherInf; "Query Cipher Info"
0x140035eb9  jmp     short loc_140035E59
0x140035ebb  mov     eax, dword ptr [rsp+330h+var_300]
0x140035ebf  mov     ecx, 3000h
0x140035ec4  and     eax, ecx
0x140035ec6  neg     eax
0x140035ec8  sbb     eax, eax
0x140035eca  and     eax, ecx
0x140035ecc  mov     [rdi], eax
0x140035ece  mov     eax, dword ptr [rsp+330h+var_300+4]
0x140035ed2  mov     [rdi+4], eax
0x140035ed5  mov     eax, dword ptr [rsp+330h+var_300+8]
0x140035ed9  mov     [rdi+8], eax
0x140035edc  mov     eax, dword ptr [rsp+330h+var_300+0Ch]
0x140035ee0  mov     [rdi+0Ch], eax
0x140035ee3  mov     eax, dword ptr [rsp+330h+var_2F0]
0x140035ee7  mov     [rdi+10h], eax
0x140035eea  mov     eax, dword ptr [rsp+330h+var_2F0+4]
0x140035eee  mov     [rdi+14h], eax
0x140035ef1  mov     eax, [rsp+330h+var_2E8]
0x140035ef5  mov     [rdi+18h], eax
0x140035ef8  mov     eax, [rsp+330h+Src]
0x140035efc  mov     [rdi+1Ch], eax
0x140035eff  cmp     dword ptr [rsi], 24h ; '$'
0x140035f02  jb      short loc_140035F0D
0x140035f04  mov     eax, [rbp+230h+var_3C]
0x140035f0a  mov     [rdi+20h], eax
0x140035f0d  mov     eax, ebx
0x140035f0f  mov     rcx, [rbp+230h+var_30]
0x140035f16  xor     rcx, rsp; StackCookie
0x140035f19  call    __security_check_cookie
0x140035f1e  mov     rbx, [rsp+330h+arg_8]
0x140035f26  add     rsp, 310h
0x140035f2d  pop     r15
0x140035f2f  pop     r14
0x140035f31  pop     rdi
0x140035f32  pop     rsi
0x140035f33  pop     rbp
0x140035f34  retn
```
