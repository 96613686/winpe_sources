# Deserialize<_DPAPICloudKeyCache>(uchar *,ulong,void (*)(void *,void *),_DPAPICloudKeyCache *)

- ea: `0x180060b00`
- end: `0x180060e0b`
- name: `??$Deserialize@U_DPAPICloudKeyCache@@@@YAJPEAEKP6AXPEAX1@ZPEAU_DPAPICloudKeyCache@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(void *Source, unsigned int BufferSize, __int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180061600`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800293c0`
- `0x18002fd00`
- `0x180043158`
- `0x180060b00`
- `0x1800619f4`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180060c99`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180060c99`
- `RPCRT4!MesHandleFree` at `0x180060de9`
- `RPCRT4!MesHandleFree` at `0x180060de9`

## string_xrefs

- `0x180060b52`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060ba7`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060bf8`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060c58`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060cb6`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060d23`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060d7b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060cd1`: `MesDecodeBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall Deserialize<_DPAPICloudKeyCache>(void *Source, unsigned int BufferSize, __int64 a3, void *a4)
{
  rsize_t v5; // rsi
  _BYTE *v7; // rdi
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  unsigned int v12; // eax
  const char *v13; // r9
  __int64 v14; // r8
  _BYTE *v15; // rax
  void *v16; // r13
  RPC_STATUS v17; // eax
  const char *v18; // rax
  __int64 v19; // rax
  _BYTE *v20; // rcx
  int v22; // [rsp+20h] [rbp-58h]
  const char *v23; // [rsp+28h] [rbp-50h]
  handle_t pHandle; // [rsp+80h] [rbp+8h] BYREF
  __int64 v25; // [rsp+90h] [rbp+18h]

  v25 = a3;
  v5 = BufferSize;
  pHandle = 0;
  v7 = 0;
  v8 = 0;
  if ( !Source || !a4 )
  {
    v9 = -1073741811;
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
    v23 = "InvalidArg(s)";
    v22 = 237;
    goto LABEL_21;
  }
  if ( (BufferSize & 7) != 0 )
  {
    v9 = -1073741811;
    v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v10, 244, "InvalidArg:cbSerializedObject", &Class);
    goto LABEL_22;
  }
  v12 = BufferSize + 16;
  v8 = -1;
  if ( BufferSize + 16 >= BufferSize )
    v8 = BufferSize + 16;
  LODWORD(v25) = v8;
  v9 = v12 < BufferSize ? 0xC0000095 : 0;
  if ( v12 < BufferSize )
  {
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
    v23 = "RtlDWordAdd";
    v22 = 249;
LABEL_9:
    v14 = v9;
LABEL_21:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v13, v22, v23, &Class);
    goto LABEL_22;
  }
  v15 = MIDL_user_allocate(v8);
  v7 = v15;
  if ( !v15 )
  {
    v9 = -1073741801;
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
    v23 = "MIDL_user_allocate";
    v22 = 255;
    goto LABEL_9;
  }
  v16 = (void *)((unsigned __int64)(v15 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
  if ( memcpy_s_0(v16, (v8 + (_DWORD)v15 - (_DWORD)v16) & 0xFFFFFFF8, Source, v5) )
  {
    v9 = -1073741595;
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
    v23 = "memcpy_s";
    v22 = 270;
    goto LABEL_9;
  }
  v17 = MesDecodeBufferHandleCreate((char *)v16, v5, &pHandle);
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
    LiveSSPCacheDecode(pHandle, a4);
  }
LABEL_22:
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
    FreeMemory(v7);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  return v9;
}

```

## disassembly

```asm
0x180060b00  mov     rax, rsp
0x180060b03  mov     [rax+10h], rbx
0x180060b07  mov     [rax+20h], rsi
0x180060b0b  mov     [rax+18h], r8
0x180060b0f  push    rdi
0x180060b10  push    r12
0x180060b12  push    r13
0x180060b14  push    r14
0x180060b16  push    r15
0x180060b18  sub     rsp, 50h
0x180060b1c  mov     r15, r9
0x180060b1f  mov     esi, edx
0x180060b21  mov     r12, rcx
0x180060b24  mov     qword ptr [rax+8], 0
0x180060b2c  xor     edi, edi
0x180060b2e  xor     r14d, r14d
0x180060b31  test    rcx, rcx
0x180060b34  jz      loc_180060D72
0x180060b3a  test    r9, r9
0x180060b3d  jz      loc_180060D72
0x180060b43  test    sil, 7
0x180060b47  jz      short loc_180060B86
0x180060b49  mov     r8d, 0C000000Dh
0x180060b4f  mov     ebx, r8d
0x180060b52  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060b59  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060b5e  mov     r9, rax
0x180060b61  lea     rax, Class
0x180060b68  mov     [rsp+78h+var_48], rax
0x180060b6d  lea     rax, aInvalidargCbse_0; "InvalidArg:cbSerializedObject"
0x180060b74  mov     [rsp+78h+var_50], rax
0x180060b79  mov     [rsp+78h+var_58], 0F4h
0x180060b81  jmp     loc_180060DAA
0x180060b86  lea     eax, [rsi+10h]
0x180060b89  or      r14d, 0FFFFFFFFh
0x180060b8d  cmp     eax, esi
0x180060b8f  cmovnb  r14d, eax
0x180060b93  mov     dword ptr [rsp+78h+arg_10], r14d
0x180060b9b  sbb     ebx, ebx
0x180060b9d  and     ebx, 0C0000095h
0x180060ba3  cmp     eax, esi
0x180060ba5  jnb     short loc_180060BDE
0x180060ba7  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060bae  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060bb3  mov     r9, rax
0x180060bb6  lea     rax, Class
0x180060bbd  mov     [rsp+78h+var_48], rax
0x180060bc2  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x180060bc9  mov     [rsp+78h+var_50], rax
0x180060bce  mov     [rsp+78h+var_58], 0F9h
0x180060bd6  mov     r8d, ebx
0x180060bd9  jmp     loc_180060DAA
0x180060bde  mov     ecx, r14d; size
0x180060be1  call    MIDL_user_allocate
0x180060be6  mov     rdi, rax
0x180060be9  mov     [rsp+78h+var_30], rax
0x180060bee  test    rax, rax
0x180060bf1  jnz     short loc_180060C29
0x180060bf3  mov     ebx, 0C0000017h
0x180060bf8  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060bff  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060c04  mov     r9, rax
0x180060c07  lea     rax, Class
0x180060c0e  mov     [rsp+78h+var_48], rax
0x180060c13  lea     rax, aMidlUserAlloca; "MIDL_user_allocate"
0x180060c1a  mov     [rsp+78h+var_50], rax
0x180060c1f  mov     [rsp+78h+var_58], 0FFh
0x180060c27  jmp     short loc_180060BD6
0x180060c29  lea     r13, [rax+7]
0x180060c2d  and     r13, 0FFFFFFFFFFFFFFF8h
0x180060c31  mov     r9, rsi; SourceSize
0x180060c34  mov     edx, eax
0x180060c36  sub     edx, r13d
0x180060c39  add     edx, r14d
0x180060c3c  mov     ecx, 0FFFFFFF8h
0x180060c41  and     rdx, rcx; DestinationSize
0x180060c44  mov     r8, r12; Source
0x180060c47  mov     rcx, r13; Destination
0x180060c4a  call    memcpy_s_0
0x180060c4f  test    eax, eax
0x180060c51  jz      short loc_180060C8C
0x180060c53  mov     ebx, 0C00000E5h
0x180060c58  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060c5f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060c64  mov     r9, rax
0x180060c67  lea     rax, Class
0x180060c6e  mov     [rsp+78h+var_48], rax
0x180060c73  lea     rax, aMemcpyS; "memcpy_s"
0x180060c7a  mov     [rsp+78h+var_50], rax
0x180060c7f  mov     [rsp+78h+var_58], 10Eh
0x180060c87  jmp     loc_180060BD6
0x180060c8c  lea     r8, [rsp+78h+pHandle]; pHandle
0x180060c94  mov     edx, esi; BufferSize
0x180060c96  mov     rcx, r13; Buffer
0x180060c99  call    cs:__imp_MesDecodeBufferHandleCreate
0x180060c9f  test    eax, eax
0x180060ca1  jz      short loc_180060CFB
0x180060ca3  jg      short loc_180060CA9
0x180060ca5  mov     ebx, eax
0x180060ca7  jmp     short loc_180060CB2
0x180060ca9  movzx   ebx, ax
0x180060cac  or      ebx, 0C0070000h
0x180060cb2  mov     [rsp+78h+var_38], ebx
0x180060cb6  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060cbd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060cc2  mov     r9, rax
0x180060cc5  lea     rax, Class
0x180060ccc  mov     [rsp+78h+var_48], rax
0x180060cd1  lea     rax, aMesdecodebuffe; "MesDecodeBufferHandleCreate"
0x180060cd8  mov     [rsp+78h+var_50], rax
0x180060cdd  mov     [rsp+78h+var_58], 11Ah
0x180060ce5  mov     r8d, ebx
0x180060ce8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180060cef  xor     ecx, ecx
0x180060cf1  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180060cf6  jmp     loc_180060DB8
0x180060cfb  mov     rdx, r15; void *
0x180060cfe  mov     rcx, [rsp+78h+pHandle]; void *
0x180060d06  call    ?LiveSSPCacheDecode@@YAXPEAX0@Z; LiveSSPCacheDecode(void *,void *)
0x180060d0b  jmp     loc_180060DB8
0x180060d10  mov     ebx, eax
0x180060d12  test    eax, eax
0x180060d14  jle     short loc_180060D1F
0x180060d16  movzx   ebx, ax
0x180060d19  or      ebx, 0C0070000h
0x180060d1f  mov     [rsp+78h+var_38], ebx
0x180060d23  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060d2a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060d2f  mov     r9, rax
0x180060d32  lea     rax, Class
0x180060d39  mov     [rsp+78h+var_48], rax
0x180060d3e  lea     rax, aFndecode; "fnDecode"
0x180060d45  mov     [rsp+78h+var_50], rax
0x180060d4a  mov     [rsp+78h+var_58], 125h
0x180060d52  mov     r8d, ebx
0x180060d55  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180060d5c  xor     ecx, ecx
0x180060d5e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180060d63  mov     rdi, [rsp+78h+var_30]
0x180060d68  mov     r14d, dword ptr [rsp+78h+arg_10]
0x180060d70  jmp     short loc_180060DB8
0x180060d72  mov     r8d, 0C000000Dh
0x180060d78  mov     ebx, r8d
0x180060d7b  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060d82  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060d87  mov     r9, rax
0x180060d8a  lea     rax, Class
0x180060d91  mov     [rsp+78h+var_48], rax
0x180060d96  lea     rax, aInvalidargS; "InvalidArg(s)"
0x180060d9d  mov     [rsp+78h+var_50], rax
0x180060da2  mov     [rsp+78h+var_58], 0EDh
0x180060daa  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180060db1  xor     ecx, ecx
0x180060db3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180060db8  test    rdi, rdi
0x180060dbb  jz      short loc_180060DDC
0x180060dbd  mov     eax, r14d
0x180060dc0  mov     rcx, rdi
0x180060dc3  test    r14d, r14d
0x180060dc6  jz      short loc_180060DD4
0x180060dc8  mov     byte ptr [rcx], 0
0x180060dcb  inc     rcx
0x180060dce  sub     rax, 1
0x180060dd2  jnz     short loc_180060DC8
0x180060dd4  mov     rcx, rdi; void *
0x180060dd7  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x180060ddc  mov     rcx, [rsp+78h+pHandle]; Handle
0x180060de4  test    rcx, rcx
0x180060de7  jz      short loc_180060DEF
0x180060de9  call    cs:__imp_MesHandleFree
0x180060def  mov     eax, ebx
0x180060df1  lea     r11, [rsp+78h+var_28]
0x180060df6  mov     rbx, [r11+38h]
0x180060dfa  mov     rsi, [r11+48h]
0x180060dfe  mov     rsp, r11
0x180060e01  pop     r15
0x180060e03  pop     r14
0x180060e05  pop     r13
0x180060e07  pop     r12
0x180060e09  pop     rdi
0x180060e0a  retn
0x18007feaa  push    rbp
0x18007feac  sub     rsp, 40h
0x18007feb0  mov     rbp, rdx
0x18007feb3  mov     rcx, [rcx]
0x18007feb6  mov     ecx, [rcx]; ExceptionCode
0x18007feb8  call    cs:__imp_I_RpcExceptionFilter
0x18007febe  nop
0x18007febf  add     rsp, 40h
0x18007fec3  pop     rbp
0x18007fec4  retn
```
