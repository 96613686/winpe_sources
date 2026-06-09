# CDimFullRouterInterface::UpdateRemoteEndPoints(void)

- ea: `0x180002afc`
- end: `0x180002c6f`
- name: `?UpdateRemoteEndPoints@CDimFullRouterInterface@@QEAAKXZ`
- size: `371`
- prototype: `unsigned int __fastcall(CDimFullRouterInterface *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002690`
- `0x18000ad04`

## callees

- `0x180002afc`
- `0x18000df70`
- `0x180010f80`
- `0x180011c40`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `MPRDDM!IfObjectLoadDestinationInfo` at `0x180002b87`
- `MPRDDM!IfObjectLoadDestinationInfo` at `0x180002b87`

## string_xrefs

- `0x180002bba`: `UpdateRemoteEndpoints: IfObjectLoadDestinationInfo failed: (dwRemoteEndpointCount: %d, dwRetCode: %d).`

## pseudocode

```c
__int64 __fastcall CDimFullRouterInterface::UpdateRemoteEndPoints(CDimFullRouterInterface *this)
{
  unsigned int DestinationInfo; // ebx
  void *v3; // r14
  unsigned int v4; // edi
  __int64 v5; // r8
  __int64 v6; // rcx
  __int128 *v7; // r9
  __int128 v9; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v11; // [rsp+44h] [rbp-BCh]
  __int128 v12; // [rsp+54h] [rbp-ACh]
  int v13; // [rsp+64h] [rbp-9Ch]
  int v14; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v15[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v14 = 0;
  DestinationInfo = 0;
  v9 = 0;
  memset_0(v15, 0, sizeof(v15));
  v10 = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  if ( !*((_QWORD *)this + 392) )
  {
    v3 = AcquirePhoneBookContextForThread();
    if ( (gbldwDIMComponentsLoaded & 4) != 0 )
    {
      DestinationInfo = IfObjectLoadDestinationInfo(this);
      v4 = DestinationInfo;
      if ( !DestinationInfo && *((_QWORD *)this + 392) )
      {
LABEL_14:
        ReleasePhoneBookContextForThread(v3);
        return DestinationInfo;
      }
    }
    else
    {
      v4 = 903;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      v5 = *((_QWORD *)this + 392);
      LOWORD(v14) = 0;
      LOWORD(v10) = 0;
      FormatRRASErrorString(
        &v14,
        L"UpdateRemoteEndpoints: IfObjectLoadDestinationInfo failed: (dwRemoteEndpointCount: %d, dwRetCode: %d).",
        v5,
        v4);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v6 = (*(__int64 (__fastcall **)(CDimFullRouterInterface *))(*(_QWORD *)this + 280LL))(this);
        v7 = &v9;
        if ( this != (CDimFullRouterInterface *)-3104LL )
          LODWORD(v7) = (_DWORD)this + 3104;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v14,
          (_DWORD)v7,
          v6,
          (__int64)&v10);
      }
    }
    DestinationInfo = v4;
    if ( !v4 )
      DestinationInfo = 1168;
    goto LABEL_14;
  }
  return DestinationInfo;
}

```

## disassembly

```asm
0x180002afc  mov     [rsp-8+arg_8], rbx
0x180002b01  mov     [rsp-8+arg_10], rsi
0x180002b06  push    rbp
0x180002b07  push    rdi
0x180002b08  push    r14
0x180002b0a  lea     rbp, [rsp-780h]
0x180002b12  sub     rsp, 880h
0x180002b19  mov     rax, cs:__security_cookie
0x180002b20  xor     rax, rsp
0x180002b23  mov     [rbp+790h+var_20], rax
0x180002b2a  mov     rsi, rcx
0x180002b2d  xorps   xmm0, xmm0
0x180002b30  xor     eax, eax
0x180002b32  lea     rcx, [rsp+890h+var_81C]; void *
0x180002b37  xor     edx, edx; Val
0x180002b39  mov     [rsp+890h+var_820], eax
0x180002b3d  mov     r8d, 7FCh; Size
0x180002b43  xor     ebx, ebx
0x180002b45  movups  [rsp+890h+var_860], xmm0
0x180002b4a  call    memset_0
0x180002b4f  xor     eax, eax
0x180002b51  xorps   xmm0, xmm0
0x180002b54  mov     [rsp+890h+var_850], eax
0x180002b58  movups  [rsp+890h+var_84C], xmm0
0x180002b5d  mov     [rsp+890h+var_82C], eax
0x180002b61  movups  [rsp+890h+var_83C], xmm0
0x180002b66  cmp     [rsi+0C40h], rax
0x180002b6d  jnz     loc_180002C46
0x180002b73  call    ?AcquirePhoneBookContextForThread@@YAPEAXXZ; AcquirePhoneBookContextForThread(void)
0x180002b78  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x180002b7f  mov     r14, rax
0x180002b82  jz      short loc_180002BA5
0x180002b84  mov     rcx, rsi
0x180002b87  call    cs:__imp_IfObjectLoadDestinationInfo
0x180002b8d  mov     ebx, eax
0x180002b8f  mov     edi, eax
0x180002b91  test    eax, eax
0x180002b93  jnz     short loc_180002BAA
0x180002b95  cmp     qword ptr [rsi+0C40h], 0
0x180002b9d  jnz     loc_180002C3E
0x180002ba3  jmp     short loc_180002BAA
0x180002ba5  mov     edi, 387h
0x180002baa  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180002bb1  jz      short loc_180002C32
0x180002bb3  mov     r8, [rsi+0C40h]
0x180002bba  lea     rdx, aUpdateremoteen; "UpdateRemoteEndpoints: IfObjectLoadDest"...
0x180002bc1  xor     eax, eax
0x180002bc3  lea     rcx, [rsp+890h+var_820]
0x180002bc8  mov     r9d, edi
0x180002bcb  mov     word ptr [rsp+890h+var_820], ax
0x180002bd0  mov     word ptr [rsp+890h+var_850], ax
0x180002bd5  call    FormatRRASErrorString
0x180002bda  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180002be1  jz      short loc_180002C32
0x180002be3  mov     rax, [rsi]
0x180002be6  mov     rcx, rsi
0x180002be9  mov     rax, [rax+118h]
0x180002bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf5  mov     rcx, rax
0x180002bf8  lea     r9, [rsp+890h+var_860]
0x180002bfd  lea     rax, [rsi+0C20h]
0x180002c04  test    rax, rax
0x180002c07  lea     r8, [rsp+890h+var_820]
0x180002c0c  lea     rdx, RasDimParamTraceError
0x180002c13  cmovnz  r9, rax
0x180002c17  lea     rax, [rsp+890h+var_850]
0x180002c1c  mov     [rsp+890h+var_868], rax
0x180002c21  mov     [rsp+890h+var_870], rcx
0x180002c26  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002c2d  call    McTemplateU0zjzz_EventWriteTransfer
0x180002c32  test    edi, edi
0x180002c34  mov     ebx, edi
0x180002c36  mov     eax, 490h
0x180002c3b  cmovz   ebx, eax
0x180002c3e  mov     rcx, r14; lpTlsValue
0x180002c41  call    ?ReleasePhoneBookContextForThread@@YAXPEAX@Z; ReleasePhoneBookContextForThread(void *)
0x180002c46  mov     eax, ebx
0x180002c48  mov     rcx, [rbp+790h+var_20]
0x180002c4f  xor     rcx, rsp; StackCookie
0x180002c52  call    __security_check_cookie
0x180002c57  lea     r11, [rsp+890h+var_10]
0x180002c5f  mov     rbx, [r11+28h]
0x180002c63  mov     rsi, [r11+30h]
0x180002c67  mov     rsp, r11
0x180002c6a  pop     r14
0x180002c6c  pop     rdi
0x180002c6d  pop     rbp
0x180002c6e  retn
```
