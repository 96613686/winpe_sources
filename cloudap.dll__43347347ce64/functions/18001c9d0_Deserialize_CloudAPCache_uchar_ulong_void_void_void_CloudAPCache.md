# Deserialize<_CloudAPCache>(uchar *,ulong,void (*)(void *,void *),_CloudAPCache *)

- ea: `0x18001c9d0`
- end: `0x18001cd6c`
- name: `??$Deserialize@U_CloudAPCache@@@@YAJPEAEKP6AXPEAX1@ZPEAU_CloudAPCache@@@Z`
- size: `924`
- prototype: `__int64 __fastcall(void *Source, rsize_t SourceSize, __int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001c000`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18001c9d0`
- `0x180032930`
- `0x180043158`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001caec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001caec`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001cbbc`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001cbbc`
- `RPCRT4!MesHandleFree` at `0x18001cd4a`
- `RPCRT4!MesHandleFree` at `0x18001cd4a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007fb3e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007fb3e`

## string_xrefs

- `0x18001ca1e`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18001ca7c`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18001cb0b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18001cb7b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18001cbd9`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18001cc46`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18001cca1`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18001cbf4`: `MesDecodeBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall Deserialize<_CloudAPCache>(void *Source, rsize_t SourceSize, __int64 a3, void *a4)
{
  rsize_t v5; // rsi
  _BYTE *v7; // rdi
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  const char *v10; // r9
  unsigned int v11; // eax
  const char *v12; // r9
  const char *v13; // rdx
  bool v14; // zf
  _BYTE *v15; // rax
  const char *v16; // r9
  RPC_STATUS v17; // eax
  const char *v18; // rax
  __int64 v19; // rdx
  _BYTE *v20; // rax
  int v22; // [rsp+20h] [rbp-58h]
  const char *v23; // [rsp+28h] [rbp-50h]
  handle_t pHandle; // [rsp+80h] [rbp+8h] BYREF
  __int64 v25; // [rsp+90h] [rbp+18h]

  v25 = a3;
  v5 = (unsigned int)SourceSize;
  pHandle = 0;
  v7 = 0;
  v8 = 0;
  if ( Source && a4 )
  {
    if ( (SourceSize & 7) != 0 )
    {
      v9 = -1073741811;
      v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v10, 244, "InvalidArg:cbSerializedObject", &Class);
      goto LABEL_38;
    }
    v11 = SourceSize + 16;
    v8 = -1;
    if ( (int)SourceSize + 16 >= (unsigned int)SourceSize )
      v8 = SourceSize + 16;
    LODWORD(v25) = v8;
    v9 = v11 < (unsigned int)SourceSize ? 0xC0000095 : 0;
    if ( v11 >= (unsigned int)SourceSize )
    {
      if ( g_pLsaFunctionTable )
        v15 = (_BYTE *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v8);
      else
        v15 = LocalAlloc(0x40u, v8);
      v7 = v15;
      if ( v15 )
      {
        if ( memcpy_s_0(
               (void *const)((unsigned __int64)(v15 + 7) & 0xFFFFFFFFFFFFFFF8uLL),
               (v8 + (_DWORD)v15 - (((_DWORD)v15 + 7) & 0xFFFFFFF8)) & 0xFFFFFFF8,
               Source,
               v5) )
        {
          v9 = -1073741595;
          v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v16, 270, "memcpy_s", &Class);
        }
        else
        {
          v17 = MesDecodeBufferHandleCreate((char *)((unsigned __int64)(v7 + 7) & 0xFFFFFFFFFFFFFFF8uLL), v5, &pHandle);
          if ( v17 )
          {
            if ( v17 > 0 )
              v9 = (unsigned __int16)v17 | 0xC0070000;
            else
              v9 = v17;
            v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v18, 282, "MesDecodeBufferHandleCreate", &Class);
          }
          else
          {
            CloudAPCacheDecode(pHandle, a4);
          }
        }
        goto LABEL_38;
      }
      v9 = -1073741801;
      v12 = "";
      while ( 1 )
      {
        v13 = v12--;
        v14 = *v12 == 92;
        if ( *v12 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp" )
        {
          v14 = *v12 == 92;
          break;
        }
      }
      v23 = "MIDL_user_allocate";
      v22 = 255;
    }
    else
    {
      v12 = "";
      while ( 1 )
      {
        v13 = v12--;
        v14 = *v12 == 92;
        if ( *v12 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp" )
        {
          v14 = *v12 == 92;
          break;
        }
      }
      v23 = "RtlDWordAdd";
      v22 = 249;
    }
  }
  else
  {
    v9 = -1073741811;
    v12 = "";
    while ( 1 )
    {
      v13 = v12--;
      v14 = *v12 == 92;
      if ( *v12 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp" )
      {
        v14 = *v12 == 92;
        break;
      }
    }
    v23 = "InvalidArg(s)";
    v22 = 237;
  }
  if ( v14 )
    v12 = v13;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v12, v22, v23, &Class);
LABEL_38:
  if ( v7 )
  {
    v19 = v8;
    v20 = v7;
    if ( v8 )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    if ( g_pLsaFunctionTable )
      ((void (__fastcall *)(_BYTE *, __int64))g_pLsaFunctionTable->FreeLsaHeap)(v7, v19);
    else
      LocalFree(v7);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  return v9;
}

```

## disassembly

```asm
0x18001c9d0  mov     rax, rsp
0x18001c9d3  mov     [rax+10h], rbx
0x18001c9d7  mov     [rax+20h], rsi
0x18001c9db  mov     [rax+18h], r8
0x18001c9df  push    rdi
0x18001c9e0  push    r12
0x18001c9e2  push    r13
0x18001c9e4  push    r14
0x18001c9e6  push    r15
0x18001c9e8  sub     rsp, 50h
0x18001c9ec  mov     r15, r9
0x18001c9ef  mov     esi, edx
0x18001c9f1  mov     r13, rcx
0x18001c9f4  mov     qword ptr [rax+8], 0
0x18001c9fc  xor     edi, edi
0x18001c9fe  xor     r14d, r14d
0x18001ca01  test    rcx, rcx
0x18001ca04  jz      loc_18001CC95
0x18001ca0a  test    r9, r9
0x18001ca0d  jz      loc_18001CC95
0x18001ca13  test    sil, 7
0x18001ca17  jz      short loc_18001CA52
0x18001ca19  mov     ebx, 0C000000Dh
0x18001ca1e  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001ca25  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001ca2a  mov     r9, rax
0x18001ca2d  lea     rax, Class
0x18001ca34  mov     [rsp+78h+var_48], rax
0x18001ca39  lea     rax, aInvalidargCbse_0; "InvalidArg:cbSerializedObject"
0x18001ca40  mov     [rsp+78h+var_50], rax
0x18001ca45  mov     [rsp+78h+var_58], 0F4h
0x18001ca4d  jmp     loc_18001CCE9
0x18001ca52  lea     eax, [rsi+10h]
0x18001ca55  mov     r14d, 0FFFFFFFFh
0x18001ca5b  cmp     eax, esi
0x18001ca5d  cmovnb  r14d, eax
0x18001ca61  mov     dword ptr [rsp+78h+arg_10], r14d
0x18001ca69  sbb     ebx, ebx
0x18001ca6b  and     ebx, 0C0000095h
0x18001ca71  cmp     eax, esi
0x18001ca73  jnb     short loc_18001CACA
0x18001ca75  lea     r9, aOnecoreDsExtCl_13+45h; ""
0x18001ca7c  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001ca83  nop     dword ptr [rax+00h]
0x18001ca87  nop     word ptr [rax+rax+00000000h]
0x18001ca90  mov     rdx, r9
0x18001ca93  dec     r9
0x18001ca96  movzx   eax, byte ptr [r9]
0x18001ca9a  cmp     al, 5Ch ; '\'
0x18001ca9c  jz      short loc_18001CAA5
0x18001ca9e  cmp     r9, rcx
0x18001caa1  ja      short loc_18001CA90
0x18001caa3  cmp     al, 5Ch ; '\'
0x18001caa5  lea     rax, Class
0x18001caac  mov     [rsp+78h+var_48], rax
0x18001cab1  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x18001cab8  mov     [rsp+78h+var_50], rax
0x18001cabd  mov     [rsp+78h+var_58], 0F9h
0x18001cac5  jmp     loc_18001CCE5
0x18001caca  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001cad1  test    rax, rax
0x18001cad4  jz      short loc_18001CAE4
0x18001cad6  mov     ecx, r14d
0x18001cad9  mov     rax, [rax+28h]
0x18001cadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cae2  jmp     short loc_18001CAF2
0x18001cae4  mov     edx, r14d; uBytes
0x18001cae7  mov     ecx, 40h ; '@'; uFlags
0x18001caec  call    cs:__imp_LocalAlloc
0x18001caf2  mov     rdi, rax
0x18001caf5  mov     [rsp+78h+var_30], rax
0x18001cafa  test    rax, rax
0x18001cafd  jnz     short loc_18001CB4C
0x18001caff  mov     ebx, 0C0000017h
0x18001cb04  lea     r9, aOnecoreDsExtCl_13+45h; ""
0x18001cb0b  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001cb12  mov     rdx, r9
0x18001cb15  dec     r9
0x18001cb18  movzx   eax, byte ptr [r9]
0x18001cb1c  cmp     al, 5Ch ; '\'
0x18001cb1e  jz      short loc_18001CB27
0x18001cb20  cmp     r9, rcx
0x18001cb23  ja      short loc_18001CB12
0x18001cb25  cmp     al, 5Ch ; '\'
0x18001cb27  lea     rax, Class
0x18001cb2e  mov     [rsp+78h+var_48], rax
0x18001cb33  lea     rax, aMidlUserAlloca; "MIDL_user_allocate"
0x18001cb3a  mov     [rsp+78h+var_50], rax
0x18001cb3f  mov     [rsp+78h+var_58], 0FFh
0x18001cb47  jmp     loc_18001CCE5
0x18001cb4c  lea     r12, [rdi+7]
0x18001cb50  and     r12, 0FFFFFFFFFFFFFFF8h
0x18001cb54  mov     r9, rsi; SourceSize
0x18001cb57  mov     edx, edi
0x18001cb59  sub     edx, r12d
0x18001cb5c  add     edx, r14d
0x18001cb5f  mov     ecx, 0FFFFFFF8h
0x18001cb64  and     rdx, rcx; DestinationSize
0x18001cb67  mov     r8, r13; Source
0x18001cb6a  mov     rcx, r12; Destination
0x18001cb6d  call    memcpy_s_0
0x18001cb72  test    eax, eax
0x18001cb74  jz      short loc_18001CBAF
0x18001cb76  mov     ebx, 0C00000E5h
0x18001cb7b  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001cb82  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001cb87  mov     r9, rax
0x18001cb8a  lea     rax, Class
0x18001cb91  mov     [rsp+78h+var_48], rax
0x18001cb96  lea     rax, aMemcpyS; "memcpy_s"
0x18001cb9d  mov     [rsp+78h+var_50], rax
0x18001cba2  mov     [rsp+78h+var_58], 10Eh
0x18001cbaa  jmp     loc_18001CCE9
0x18001cbaf  lea     r8, [rsp+78h+pHandle]; pHandle
0x18001cbb7  mov     edx, esi; BufferSize
0x18001cbb9  mov     rcx, r12; Buffer
0x18001cbbc  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001cbc2  test    eax, eax
0x18001cbc4  jz      short loc_18001CC1E
0x18001cbc6  jg      short loc_18001CBCC
0x18001cbc8  mov     ebx, eax
0x18001cbca  jmp     short loc_18001CBD5
0x18001cbcc  movzx   ebx, ax
0x18001cbcf  or      ebx, 0C0070000h
0x18001cbd5  mov     [rsp+78h+var_38], ebx
0x18001cbd9  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001cbe0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001cbe5  mov     r9, rax
0x18001cbe8  lea     rax, Class
0x18001cbef  mov     [rsp+78h+var_48], rax
0x18001cbf4  lea     rax, aMesdecodebuffe; "MesDecodeBufferHandleCreate"
0x18001cbfb  mov     [rsp+78h+var_50], rax
0x18001cc00  mov     [rsp+78h+var_58], 11Ah
0x18001cc08  mov     r8d, ebx
0x18001cc0b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001cc12  xor     ecx, ecx
0x18001cc14  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001cc19  jmp     loc_18001CCFA
0x18001cc1e  mov     rdx, r15; void *
0x18001cc21  mov     rcx, [rsp+78h+pHandle]; void *
0x18001cc29  call    ?CloudAPCacheDecode@@YAXPEAX0@Z; CloudAPCacheDecode(void *,void *)
0x18001cc2e  jmp     loc_18001CCFA
0x18001cc33  mov     ebx, eax
0x18001cc35  test    eax, eax
0x18001cc37  jle     short loc_18001CC42
0x18001cc39  movzx   ebx, ax
0x18001cc3c  or      ebx, 0C0070000h
0x18001cc42  mov     [rsp+78h+var_38], ebx
0x18001cc46  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001cc4d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001cc52  mov     r9, rax
0x18001cc55  lea     rax, Class
0x18001cc5c  mov     [rsp+78h+var_48], rax
0x18001cc61  lea     rax, aFndecode; "fnDecode"
0x18001cc68  mov     [rsp+78h+var_50], rax
0x18001cc6d  mov     [rsp+78h+var_58], 125h
0x18001cc75  mov     r8d, ebx
0x18001cc78  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001cc7f  xor     ecx, ecx
0x18001cc81  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001cc86  mov     rdi, [rsp+78h+var_30]
0x18001cc8b  mov     r14d, dword ptr [rsp+78h+arg_10]
0x18001cc93  jmp     short loc_18001CCFA
0x18001cc95  mov     ebx, 0C000000Dh
0x18001cc9a  lea     r9, aOnecoreDsExtCl_13+45h; ""
0x18001cca1  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001cca8  nop     dword ptr [rax+rax+00000000h]
0x18001ccb0  mov     rdx, r9
0x18001ccb3  dec     r9
0x18001ccb6  movzx   eax, byte ptr [r9]
0x18001ccba  cmp     al, 5Ch ; '\'
0x18001ccbc  jz      short loc_18001CCC5
0x18001ccbe  cmp     r9, rcx
0x18001ccc1  ja      short loc_18001CCB0
0x18001ccc3  cmp     al, 5Ch ; '\'
0x18001ccc5  lea     rax, Class
0x18001cccc  mov     [rsp+78h+var_48], rax
0x18001ccd1  lea     rax, aInvalidargS; "InvalidArg(s)"
0x18001ccd8  mov     [rsp+78h+var_50], rax
0x18001ccdd  mov     [rsp+78h+var_58], 0EDh
0x18001cce5  cmovz   r9, rdx
0x18001cce9  mov     r8d, ebx
0x18001ccec  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001ccf3  xor     ecx, ecx
0x18001ccf5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001ccfa  test    rdi, rdi
0x18001ccfd  jz      short loc_18001CD3D
0x18001ccff  mov     edx, r14d
0x18001cd02  mov     rax, rdi
0x18001cd05  test    r14d, r14d
0x18001cd08  jz      short loc_18001CD1D
0x18001cd0a  nop     word ptr [rax+rax+00h]
0x18001cd10  mov     byte ptr [rax], 0
0x18001cd13  lea     rax, [rax+1]
0x18001cd17  sub     rdx, 1
0x18001cd1b  jnz     short loc_18001CD10
0x18001cd1d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001cd24  mov     rcx, rdi; hMem
0x18001cd27  test    rax, rax
0x18001cd2a  jz      short loc_18001CD37
0x18001cd2c  mov     rax, [rax+30h]
0x18001cd30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd35  jmp     short loc_18001CD3D
0x18001cd37  call    cs:__imp_LocalFree
0x18001cd3d  mov     rcx, [rsp+78h+pHandle]; Handle
0x18001cd45  test    rcx, rcx
0x18001cd48  jz      short loc_18001CD50
0x18001cd4a  call    cs:__imp_MesHandleFree
0x18001cd50  mov     eax, ebx
0x18001cd52  lea     r11, [rsp+78h+var_28]
0x18001cd57  mov     rbx, [r11+38h]
0x18001cd5b  mov     rsi, [r11+48h]
0x18001cd5f  mov     rsp, r11
0x18001cd62  pop     r15
0x18001cd64  pop     r14
0x18001cd66  pop     r13
0x18001cd68  pop     r12
0x18001cd6a  pop     rdi
0x18001cd6b  retn
0x18007fb30  push    rbp
0x18007fb32  sub     rsp, 40h
0x18007fb36  mov     rbp, rdx
0x18007fb39  mov     rcx, [rcx]
0x18007fb3c  mov     ecx, [rcx]; ExceptionCode
0x18007fb3e  call    cs:__imp_I_RpcExceptionFilter
0x18007fb44  nop
0x18007fb45  add     rsp, 40h
0x18007fb49  pop     rbp
0x18007fb4a  retn
```
