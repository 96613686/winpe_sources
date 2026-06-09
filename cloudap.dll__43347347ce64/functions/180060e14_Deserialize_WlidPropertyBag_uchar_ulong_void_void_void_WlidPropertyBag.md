# Deserialize<_WlidPropertyBag>(uchar *,ulong,void (*)(void *,void *),_WlidPropertyBag *)

- ea: `0x180060e14`
- end: `0x18006111f`
- name: `??$Deserialize@U_WlidPropertyBag@@@@YAJPEAEKP6AXPEAX1@ZPEAU_WlidPropertyBag@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(void *Source, unsigned int BufferSize, __int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180048e60`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800293c0`
- `0x18002fd00`
- `0x180043158`
- `0x18004b8e8`
- `0x180060e14`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180060fad`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180060fad`
- `RPCRT4!MesHandleFree` at `0x1800610fd`
- `RPCRT4!MesHandleFree` at `0x1800610fd`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007feb8`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007feb8`

## string_xrefs

- `0x180060e66`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060ebb`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060f0c`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060f6c`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060fca`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180061037`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18006108f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x180060fe5`: `MesDecodeBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall Deserialize<_WlidPropertyBag>(void *Source, unsigned int BufferSize, __int64 a3, void *a4)
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
    WlidPropertyBagDecode(pHandle, a4);
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
0x180060e14  mov     rax, rsp
0x180060e17  mov     [rax+10h], rbx
0x180060e1b  mov     [rax+20h], rsi
0x180060e1f  mov     [rax+18h], r8
0x180060e23  push    rdi
0x180060e24  push    r12
0x180060e26  push    r13
0x180060e28  push    r14
0x180060e2a  push    r15
0x180060e2c  sub     rsp, 50h
0x180060e30  mov     r15, r9
0x180060e33  mov     esi, edx
0x180060e35  mov     r12, rcx
0x180060e38  mov     qword ptr [rax+8], 0
0x180060e40  xor     edi, edi
0x180060e42  xor     r14d, r14d
0x180060e45  test    rcx, rcx
0x180060e48  jz      loc_180061086
0x180060e4e  test    r9, r9
0x180060e51  jz      loc_180061086
0x180060e57  test    sil, 7
0x180060e5b  jz      short loc_180060E9A
0x180060e5d  mov     r8d, 0C000000Dh
0x180060e63  mov     ebx, r8d
0x180060e66  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060e6d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060e72  mov     r9, rax
0x180060e75  lea     rax, Class
0x180060e7c  mov     [rsp+78h+var_48], rax
0x180060e81  lea     rax, aInvalidargCbse_0; "InvalidArg:cbSerializedObject"
0x180060e88  mov     [rsp+78h+var_50], rax
0x180060e8d  mov     [rsp+78h+var_58], 0F4h
0x180060e95  jmp     loc_1800610BE
0x180060e9a  lea     eax, [rsi+10h]
0x180060e9d  or      r14d, 0FFFFFFFFh
0x180060ea1  cmp     eax, esi
0x180060ea3  cmovnb  r14d, eax
0x180060ea7  mov     dword ptr [rsp+78h+arg_10], r14d
0x180060eaf  sbb     ebx, ebx
0x180060eb1  and     ebx, 0C0000095h
0x180060eb7  cmp     eax, esi
0x180060eb9  jnb     short loc_180060EF2
0x180060ebb  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060ec2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060ec7  mov     r9, rax
0x180060eca  lea     rax, Class
0x180060ed1  mov     [rsp+78h+var_48], rax
0x180060ed6  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x180060edd  mov     [rsp+78h+var_50], rax
0x180060ee2  mov     [rsp+78h+var_58], 0F9h
0x180060eea  mov     r8d, ebx
0x180060eed  jmp     loc_1800610BE
0x180060ef2  mov     ecx, r14d; size
0x180060ef5  call    MIDL_user_allocate
0x180060efa  mov     rdi, rax
0x180060efd  mov     [rsp+78h+var_30], rax
0x180060f02  test    rax, rax
0x180060f05  jnz     short loc_180060F3D
0x180060f07  mov     ebx, 0C0000017h
0x180060f0c  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060f13  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060f18  mov     r9, rax
0x180060f1b  lea     rax, Class
0x180060f22  mov     [rsp+78h+var_48], rax
0x180060f27  lea     rax, aMidlUserAlloca; "MIDL_user_allocate"
0x180060f2e  mov     [rsp+78h+var_50], rax
0x180060f33  mov     [rsp+78h+var_58], 0FFh
0x180060f3b  jmp     short loc_180060EEA
0x180060f3d  lea     r13, [rax+7]
0x180060f41  and     r13, 0FFFFFFFFFFFFFFF8h
0x180060f45  mov     r9, rsi; SourceSize
0x180060f48  mov     edx, eax
0x180060f4a  sub     edx, r13d
0x180060f4d  add     edx, r14d
0x180060f50  mov     ecx, 0FFFFFFF8h
0x180060f55  and     rdx, rcx; DestinationSize
0x180060f58  mov     r8, r12; Source
0x180060f5b  mov     rcx, r13; Destination
0x180060f5e  call    memcpy_s_0
0x180060f63  test    eax, eax
0x180060f65  jz      short loc_180060FA0
0x180060f67  mov     ebx, 0C00000E5h
0x180060f6c  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060f73  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060f78  mov     r9, rax
0x180060f7b  lea     rax, Class
0x180060f82  mov     [rsp+78h+var_48], rax
0x180060f87  lea     rax, aMemcpyS; "memcpy_s"
0x180060f8e  mov     [rsp+78h+var_50], rax
0x180060f93  mov     [rsp+78h+var_58], 10Eh
0x180060f9b  jmp     loc_180060EEA
0x180060fa0  lea     r8, [rsp+78h+pHandle]; pHandle
0x180060fa8  mov     edx, esi; BufferSize
0x180060faa  mov     rcx, r13; Buffer
0x180060fad  call    cs:__imp_MesDecodeBufferHandleCreate
0x180060fb3  test    eax, eax
0x180060fb5  jz      short loc_18006100F
0x180060fb7  jg      short loc_180060FBD
0x180060fb9  mov     ebx, eax
0x180060fbb  jmp     short loc_180060FC6
0x180060fbd  movzx   ebx, ax
0x180060fc0  or      ebx, 0C0070000h
0x180060fc6  mov     [rsp+78h+var_38], ebx
0x180060fca  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180060fd1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180060fd6  mov     r9, rax
0x180060fd9  lea     rax, Class
0x180060fe0  mov     [rsp+78h+var_48], rax
0x180060fe5  lea     rax, aMesdecodebuffe; "MesDecodeBufferHandleCreate"
0x180060fec  mov     [rsp+78h+var_50], rax
0x180060ff1  mov     [rsp+78h+var_58], 11Ah
0x180060ff9  mov     r8d, ebx
0x180060ffc  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180061003  xor     ecx, ecx
0x180061005  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18006100a  jmp     loc_1800610CC
0x18006100f  mov     rdx, r15; void *
0x180061012  mov     rcx, [rsp+78h+pHandle]; void *
0x18006101a  call    ?WlidPropertyBagDecode@@YAXPEAX0@Z; WlidPropertyBagDecode(void *,void *)
0x18006101f  jmp     loc_1800610CC
0x180061024  mov     ebx, eax
0x180061026  test    eax, eax
0x180061028  jle     short loc_180061033
0x18006102a  movzx   ebx, ax
0x18006102d  or      ebx, 0C0070000h
0x180061033  mov     [rsp+78h+var_38], ebx
0x180061037  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18006103e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180061043  mov     r9, rax
0x180061046  lea     rax, Class
0x18006104d  mov     [rsp+78h+var_48], rax
0x180061052  lea     rax, aFndecode; "fnDecode"
0x180061059  mov     [rsp+78h+var_50], rax
0x18006105e  mov     [rsp+78h+var_58], 125h
0x180061066  mov     r8d, ebx
0x180061069  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180061070  xor     ecx, ecx
0x180061072  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180061077  mov     rdi, [rsp+78h+var_30]
0x18006107c  mov     r14d, dword ptr [rsp+78h+arg_10]
0x180061084  jmp     short loc_1800610CC
0x180061086  mov     r8d, 0C000000Dh
0x18006108c  mov     ebx, r8d
0x18006108f  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180061096  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006109b  mov     r9, rax
0x18006109e  lea     rax, Class
0x1800610a5  mov     [rsp+78h+var_48], rax
0x1800610aa  lea     rax, aInvalidargS; "InvalidArg(s)"
0x1800610b1  mov     [rsp+78h+var_50], rax
0x1800610b6  mov     [rsp+78h+var_58], 0EDh
0x1800610be  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800610c5  xor     ecx, ecx
0x1800610c7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800610cc  test    rdi, rdi
0x1800610cf  jz      short loc_1800610F0
0x1800610d1  mov     eax, r14d
0x1800610d4  mov     rcx, rdi
0x1800610d7  test    r14d, r14d
0x1800610da  jz      short loc_1800610E8
0x1800610dc  mov     byte ptr [rcx], 0
0x1800610df  inc     rcx
0x1800610e2  sub     rax, 1
0x1800610e6  jnz     short loc_1800610DC
0x1800610e8  mov     rcx, rdi; void *
0x1800610eb  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x1800610f0  mov     rcx, [rsp+78h+pHandle]; Handle
0x1800610f8  test    rcx, rcx
0x1800610fb  jz      short loc_180061103
0x1800610fd  call    cs:__imp_MesHandleFree
0x180061103  mov     eax, ebx
0x180061105  lea     r11, [rsp+78h+var_28]
0x18006110a  mov     rbx, [r11+38h]
0x18006110e  mov     rsi, [r11+48h]
0x180061112  mov     rsp, r11
0x180061115  pop     r15
0x180061117  pop     r14
0x180061119  pop     r13
0x18006111b  pop     r12
0x18006111d  pop     rdi
0x18006111e  retn
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
