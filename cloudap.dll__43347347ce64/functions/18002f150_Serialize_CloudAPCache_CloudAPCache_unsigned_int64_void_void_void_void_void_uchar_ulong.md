# Serialize<_CloudAPCache>(_CloudAPCache *,unsigned __int64 (*)(void *,void *),void (*)(void *,void *),uchar * *,ulong *)

- ea: `0x18002f150`
- end: `0x18002f594`
- name: `??$Serialize@U_CloudAPCache@@@@YAJPEAU_CloudAPCache@@P6A_KPEAX1@ZP6AX11@ZPEAPEAEPEAK@Z`
- size: `1092`
- prototype: `__int64 __fastcall(void *, __int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002e3e0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800293c0`
- `0x18002f150`
- `0x18002fd00`
- `0x18003bfa4`
- `0x18003ddf0`
- `0x180042410`
- `0x180043158`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f537`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f537`
- `RPCRT4!MesHandleFree` at `0x18002f4f4`
- `RPCRT4!MesHandleFree` at `0x18002f4f4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007fb7e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007fb7e`
- `RPCRT4!MesBufferHandleReset` at `0x18002f303`
- `RPCRT4!MesBufferHandleReset` at `0x18002f303`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002f1f7`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18002f1f7`

## string_xrefs

- `0x18002f212`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18002f288`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18002f31e`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18002f38b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18002f3dd`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18002f434`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18002f48f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\serializationutility.cpp`
- `0x18002f22d`: `MesEncodeFixedBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall Serialize<_CloudAPCache>(void *a1, __int64 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  _BYTE *v7; // rsi
  _BYTE *v8; // rdi
  rsize_t v9; // r14
  RPC_STATUS v10; // eax
  unsigned int v11; // ebx
  const char *v12; // rax
  unsigned int v13; // ebx
  _BYTE *v14; // rax
  const char *v15; // rax
  RPC_STATUS v16; // eax
  const char *v17; // rax
  _BYTE *v18; // rax
  const char *v19; // r9
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // rdx
  bool v23; // zf
  __int64 v24; // rdx
  _BYTE *v25; // rax
  __int64 v26; // rcx
  _BYTE *v27; // rax
  __int64 BufferSize; // [rsp+20h] [rbp-A8h]
  unsigned int pEncodedSize; // [rsp+40h] [rbp-88h] BYREF
  int v31; // [rsp+44h] [rbp-84h]
  unsigned int v32; // [rsp+48h] [rbp-80h]
  handle_t Handle; // [rsp+50h] [rbp-78h] BYREF
  char *pBuffer; // [rsp+60h] [rbp-68h] BYREF
  void *v35; // [rsp+68h] [rbp-60h]
  __int64 v36; // [rsp+70h] [rbp-58h]
  __int128 v37; // [rsp+78h] [rbp-50h] BYREF
  __int64 v38; // [rsp+88h] [rbp-40h]
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+0h] BYREF

  Handle = 0;
  pEncodedSize = 0;
  v37 = 0;
  v38 = 0;
  v7 = 0;
  v35 = 0;
  v32 = 0;
  pBuffer = 0;
  v8 = 0;
  v36 = 0;
  LODWORD(v9) = 0;
  if ( a1 && a4 && a5 )
  {
    *a4 = 0;
    *a5 = 0;
    v10 = MesEncodeFixedBufferHandleCreate(
            (char *)&v37,
            ((unsigned int)&retaddr - 56 - (unsigned int)&v37) & 0xFFFFFFF8,
            &pEncodedSize,
            &Handle);
    v11 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0xC0070000;
      v31 = v11;
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v12, 120, "MesEncodeFixedBufferHandleCreate", &Class);
    }
    else
    {
      v13 = CloudAPCacheAlignSize(Handle, a1) + 16;
      v32 = v13;
      v14 = MIDL_user_allocate(v13);
      v7 = v14;
      v35 = v14;
      if ( v14 )
      {
        pBuffer = (char *)((unsigned __int64)(v14 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        v16 = MesBufferHandleReset(
                Handle,
                1u,
                MES_ENCODE,
                &pBuffer,
                ((_DWORD)v14 + v13 - (_DWORD)pBuffer) & 0xFFFFFFF8,
                &pEncodedSize);
        v11 = v16;
        if ( v16 )
        {
          if ( v16 > 0 )
            v11 = (unsigned __int16)v16 | 0xC0070000;
          v31 = v11;
          v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
          LODWORD(BufferSize) = 150;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v17, BufferSize, "MesBufferHandleReset", &Class);
        }
        else
        {
          CloudAPCacheEncode(Handle, a1);
          v9 = pEncodedSize;
          v18 = MIDL_user_allocate(pEncodedSize);
          v8 = v18;
          if ( v18 )
          {
            if ( memcpy_s_0(v18, v9, pBuffer, pEncodedSize) )
            {
              v11 = -1073741595;
              v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
              LODWORD(BufferSize) = 181;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v20, BufferSize, "memcpy_s", &Class);
            }
            else
            {
              v11 = 0;
              *a4 = v8;
              *a5 = v9;
              v8 = 0;
            }
          }
          else
          {
            v11 = -1073741801;
            v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
            LODWORD(BufferSize) = 171;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v19, BufferSize, "MIDL_user_allocate", &Class);
          }
        }
      }
      else
      {
        v11 = -1073741801;
        v31 = -1073741801;
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v15, 130, "MIDL_user_allocate", &Class);
      }
    }
  }
  else
  {
    v11 = -1073741811;
    v21 = "";
    while ( 1 )
    {
      v22 = v21--;
      v23 = *v21 == 92;
      if ( *v21 == 92 )
        break;
      if ( v21 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\serializationutility.cpp" )
      {
        v23 = *v21 == 92;
        break;
      }
    }
    if ( v23 )
      v21 = v22;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v21, 95, "InvalidArg(s)", &Class);
  }
  if ( Handle )
    MesHandleFree(Handle);
  if ( v7 )
  {
    v24 = v32;
    v25 = v7;
    if ( v32 )
    {
      do
      {
        *v25++ = 0;
        --v24;
      }
      while ( v24 );
    }
    if ( g_pLsaFunctionTable )
      ((void (__fastcall *)(_BYTE *))g_pLsaFunctionTable->FreeLsaHeap)(v7);
    else
      LocalFree(v7);
  }
  if ( v8 )
  {
    v26 = (unsigned int)v9;
    v27 = v8;
    if ( (_DWORD)v9 )
    {
      do
      {
        *v27++ = 0;
        --v26;
      }
      while ( v26 );
    }
    FreeMemory(v8);
  }
  return v11;
}

```

## disassembly

```asm
0x18002f150  mov     r11, rsp
0x18002f153  mov     [r11+10h], rbx
0x18002f157  mov     [r11+18h], rsi
0x18002f15b  push    rdi
0x18002f15c  push    r12
0x18002f15e  push    r13
0x18002f160  push    r14
0x18002f162  push    r15
0x18002f164  sub     rsp, 0A0h
0x18002f16b  mov     rax, cs:__security_cookie
0x18002f172  xor     rax, rsp
0x18002f175  mov     [rsp+0C8h+var_38], rax
0x18002f17d  mov     r15, r9
0x18002f180  mov     r13, rcx
0x18002f183  mov     r12, [rsp+0C8h+arg_20]
0x18002f18b  xor     ecx, ecx
0x18002f18d  mov     [r11-78h], rcx
0x18002f191  mov     [rsp+0C8h+pEncodedSize], ecx
0x18002f195  xorps   xmm0, xmm0
0x18002f198  xor     eax, eax
0x18002f19a  movups  [rsp+0C8h+var_50], xmm0
0x18002f19f  mov     [r11-40h], rax
0x18002f1a3  mov     esi, ecx
0x18002f1a5  mov     [r11-60h], rcx
0x18002f1a9  mov     [rsp+0C8h+var_80], ecx
0x18002f1ad  mov     [r11-68h], rcx
0x18002f1b1  mov     edi, ecx
0x18002f1b3  mov     [rsp+0C8h+var_58], rcx
0x18002f1b8  mov     r14d, ecx
0x18002f1bb  test    r13, r13
0x18002f1be  jz      loc_18002F483
0x18002f1c4  test    r9, r9
0x18002f1c7  jz      loc_18002F483
0x18002f1cd  test    r12, r12
0x18002f1d0  jz      loc_18002F483
0x18002f1d6  mov     [r9], rcx
0x18002f1d9  mov     [r12], ecx
0x18002f1dd  lea     rcx, [r11-49h]
0x18002f1e1  and     rcx, 0FFFFFFFFFFFFFFF8h; pBuffer
0x18002f1e5  lea     rdx, [r11-38h]
0x18002f1e9  sub     edx, ecx
0x18002f1eb  and     edx, 0FFFFFFF8h; BufferSize
0x18002f1ee  lea     r9, [r11-78h]; pHandle
0x18002f1f2  lea     r8, [rsp+0C8h+pEncodedSize]; pEncodedSize
0x18002f1f7  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x18002f1fd  mov     ebx, eax
0x18002f1ff  test    eax, eax
0x18002f201  jz      short loc_18002F257
0x18002f203  jle     short loc_18002F20E
0x18002f205  movzx   ebx, ax
0x18002f208  or      ebx, 0C0070000h
0x18002f20e  mov     [rsp+0C8h+var_84], ebx
0x18002f212  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002f219  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002f21e  mov     r9, rax
0x18002f221  lea     rax, Class
0x18002f228  mov     [rsp+0C8h+var_98], rax
0x18002f22d  lea     rax, aMesencodefixed; "MesEncodeFixedBufferHandleCreate"
0x18002f234  mov     [rsp+0C8h+var_A0], rax
0x18002f239  mov     dword ptr [rsp+0C8h+BufferSize], 78h ; 'x'
0x18002f241  mov     r8d, ebx
0x18002f244  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002f24b  xor     ecx, ecx
0x18002f24d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002f252  jmp     loc_18002F4EA
0x18002f257  mov     rdx, r13; void *
0x18002f25a  mov     rcx, [rsp+0C8h+Handle]; void *
0x18002f25f  call    ?CloudAPCacheAlignSize@@YA_KPEAX0@Z; CloudAPCacheAlignSize(void *,void *)
0x18002f264  lea     ebx, [rax+10h]
0x18002f267  mov     [rsp+0C8h+var_80], ebx
0x18002f26b  mov     ecx, ebx; size
0x18002f26d  call    MIDL_user_allocate
0x18002f272  mov     rsi, rax
0x18002f275  mov     [rsp+0C8h+var_60], rax
0x18002f27a  test    rax, rax
0x18002f27d  jnz     short loc_18002F2CD
0x18002f27f  mov     ebx, 0C0000017h
0x18002f284  mov     [rsp+0C8h+var_84], ebx
0x18002f288  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002f28f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002f294  mov     r9, rax
0x18002f297  lea     rax, Class
0x18002f29e  mov     [rsp+0C8h+var_98], rax
0x18002f2a3  lea     rax, aMidlUserAlloca; "MIDL_user_allocate"
0x18002f2aa  mov     [rsp+0C8h+var_A0], rax
0x18002f2af  mov     dword ptr [rsp+0C8h+BufferSize], 82h
0x18002f2b7  mov     r8d, ebx
0x18002f2ba  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002f2c1  xor     ecx, ecx
0x18002f2c3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002f2c8  jmp     loc_18002F4EA
0x18002f2cd  add     rax, 7
0x18002f2d1  and     rax, 0FFFFFFFFFFFFFFF8h
0x18002f2d5  mov     [rsp+0C8h+pBuffer], rax
0x18002f2da  mov     ecx, ebx
0x18002f2dc  sub     ecx, eax
0x18002f2de  add     ecx, esi
0x18002f2e0  and     ecx, 0FFFFFFF8h
0x18002f2e3  lea     rax, [rsp+0C8h+pEncodedSize]
0x18002f2e8  mov     [rsp+0C8h+var_A0], rax; pEncodedSize
0x18002f2ed  mov     dword ptr [rsp+0C8h+BufferSize], ecx; BufferSize
0x18002f2f1  lea     r9, [rsp+0C8h+pBuffer]; pBuffer
0x18002f2f6  xor     r8d, r8d; Operation
0x18002f2f9  mov     edx, 1; HandleStyle
0x18002f2fe  mov     rcx, [rsp+0C8h+Handle]; Handle
0x18002f303  call    cs:__imp_MesBufferHandleReset
0x18002f309  mov     ebx, eax
0x18002f30b  test    eax, eax
0x18002f30d  jz      short loc_18002F363
0x18002f30f  jle     short loc_18002F31A
0x18002f311  movzx   ebx, ax
0x18002f314  or      ebx, 0C0070000h
0x18002f31a  mov     [rsp+0C8h+var_84], ebx
0x18002f31e  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002f325  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002f32a  mov     r9, rax
0x18002f32d  lea     rax, Class
0x18002f334  mov     [rsp+0C8h+var_98], rax
0x18002f339  lea     rax, aMesbufferhandl; "MesBufferHandleReset"
0x18002f340  mov     [rsp+0C8h+var_A0], rax
0x18002f345  mov     dword ptr [rsp+0C8h+BufferSize], 96h
0x18002f34d  mov     r8d, ebx
0x18002f350  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002f357  xor     ecx, ecx
0x18002f359  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002f35e  jmp     loc_18002F4EA
0x18002f363  mov     rdx, r13; void *
0x18002f366  mov     rcx, [rsp+0C8h+Handle]; void *
0x18002f36b  call    ?CloudAPCacheEncode@@YAXPEAX0@Z; CloudAPCacheEncode(void *,void *)
0x18002f370  nop
0x18002f371  mov     r14d, [rsp+0C8h+pEncodedSize]
0x18002f376  mov     ecx, r14d; size
0x18002f379  call    MIDL_user_allocate
0x18002f37e  mov     rdi, rax
0x18002f381  test    rax, rax
0x18002f384  jnz     short loc_18002F3BF
0x18002f386  mov     ebx, 0C0000017h
0x18002f38b  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002f392  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002f397  mov     r9, rax
0x18002f39a  lea     rax, Class
0x18002f3a1  mov     [rsp+0C8h+var_98], rax
0x18002f3a6  lea     rax, aMidlUserAlloca; "MIDL_user_allocate"
0x18002f3ad  mov     [rsp+0C8h+var_A0], rax
0x18002f3b2  mov     dword ptr [rsp+0C8h+BufferSize], 0ABh
0x18002f3ba  jmp     loc_18002F4D9
0x18002f3bf  mov     r9d, [rsp+0C8h+pEncodedSize]; SourceSize
0x18002f3c4  mov     r8, [rsp+0C8h+pBuffer]; Source
0x18002f3c9  mov     rdx, r14; DestinationSize
0x18002f3cc  mov     rcx, rdi; Destination
0x18002f3cf  call    memcpy_s_0
0x18002f3d4  test    eax, eax
0x18002f3d6  jz      short loc_18002F411
0x18002f3d8  mov     ebx, 0C00000E5h
0x18002f3dd  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002f3e4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002f3e9  mov     r9, rax
0x18002f3ec  lea     rax, Class
0x18002f3f3  mov     [rsp+0C8h+var_98], rax
0x18002f3f8  lea     rax, aMemcpyS; "memcpy_s"
0x18002f3ff  mov     [rsp+0C8h+var_A0], rax
0x18002f404  mov     dword ptr [rsp+0C8h+BufferSize], 0B5h
0x18002f40c  jmp     loc_18002F4D9
0x18002f411  xor     ebx, ebx
0x18002f413  mov     [r15], rdi
0x18002f416  mov     [r12], r14d
0x18002f41a  xor     edi, edi
0x18002f41c  jmp     loc_18002F4EA
0x18002f421  mov     ebx, eax
0x18002f423  test    eax, eax
0x18002f425  jle     short loc_18002F430
0x18002f427  movzx   ebx, ax
0x18002f42a  or      ebx, 0C0070000h
0x18002f430  mov     [rsp+0C8h+var_84], ebx
0x18002f434  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002f43b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002f440  mov     r9, rax
0x18002f443  lea     rax, Class
0x18002f44a  mov     [rsp+0C8h+var_98], rax
0x18002f44f  lea     rax, aFnencode; "fnEncode"
0x18002f456  mov     [rsp+0C8h+var_A0], rax
0x18002f45b  mov     dword ptr [rsp+0C8h+BufferSize], 0A1h
0x18002f463  mov     r8d, ebx
0x18002f466  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002f46d  xor     ecx, ecx
0x18002f46f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002f474  mov     rsi, [rsp+0C8h+var_60]
0x18002f479  mov     rdi, [rsp+0C8h+var_58]
0x18002f47e  mov     r14d, edi
0x18002f481  jmp     short loc_18002F4EA
0x18002f483  mov     ebx, 0C000000Dh
0x18002f488  lea     r9, aOnecoreDsExtCl_13+45h; ""
0x18002f48f  lea     rcx, aOnecoreDsExtCl_13; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002f496  nop     word ptr [rax+rax+00000000h]
0x18002f4a0  mov     rdx, r9
0x18002f4a3  dec     r9
0x18002f4a6  movzx   eax, byte ptr [r9]
0x18002f4aa  cmp     al, 5Ch ; '\'
0x18002f4ac  jz      short loc_18002F4B5
0x18002f4ae  cmp     r9, rcx
0x18002f4b1  ja      short loc_18002F4A0
0x18002f4b3  cmp     al, 5Ch ; '\'
0x18002f4b5  cmovz   r9, rdx
0x18002f4b9  lea     rax, Class
0x18002f4c0  mov     [rsp+0C8h+var_98], rax
0x18002f4c5  lea     rax, aInvalidargS; "InvalidArg(s)"
0x18002f4cc  mov     [rsp+0C8h+var_A0], rax
0x18002f4d1  mov     dword ptr [rsp+0C8h+BufferSize], 5Fh ; '_'
0x18002f4d9  mov     r8d, ebx
0x18002f4dc  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002f4e3  xor     ecx, ecx
0x18002f4e5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002f4ea  mov     rcx, [rsp+0C8h+Handle]; Handle
0x18002f4ef  test    rcx, rcx
0x18002f4f2  jz      short loc_18002F4FA
0x18002f4f4  call    cs:__imp_MesHandleFree
0x18002f4fa  test    rsi, rsi
0x18002f4fd  jz      short loc_18002F53D
0x18002f4ff  mov     edx, [rsp+0C8h+var_80]
0x18002f503  mov     rax, rsi
0x18002f506  test    rdx, rdx
0x18002f509  jz      short loc_18002F51D
0x18002f50b  nop     dword ptr [rax+rax+00h]
0x18002f510  mov     byte ptr [rax], 0
0x18002f513  lea     rax, [rax+1]
0x18002f517  sub     rdx, 1
0x18002f51b  jnz     short loc_18002F510
0x18002f51d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002f524  mov     rcx, rsi; hMem
0x18002f527  test    rax, rax
0x18002f52a  jz      short loc_18002F537
0x18002f52c  mov     rax, [rax+30h]
0x18002f530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f535  jmp     short loc_18002F53D
0x18002f537  call    cs:__imp_LocalFree
0x18002f53d  test    rdi, rdi
0x18002f540  jz      short loc_18002F565
0x18002f542  mov     ecx, r14d
0x18002f545  mov     rax, rdi
0x18002f548  test    r14d, r14d
0x18002f54b  jz      short loc_18002F55D
0x18002f54d  nop     dword ptr [rax]
0x18002f550  mov     byte ptr [rax], 0
0x18002f553  lea     rax, [rax+1]
0x18002f557  sub     rcx, 1
0x18002f55b  jnz     short loc_18002F550
0x18002f55d  mov     rcx, rdi; void *
0x18002f560  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18002f565  mov     eax, ebx
0x18002f567  mov     rcx, [rsp+0C8h+var_38]
0x18002f56f  xor     rcx, rsp; StackCookie
0x18002f572  call    __security_check_cookie
0x18002f577  lea     r11, [rsp+0C8h+var_28]
0x18002f57f  mov     rbx, [r11+38h]
0x18002f583  mov     rsi, [r11+40h]
0x18002f587  mov     rsp, r11
0x18002f58a  pop     r15
0x18002f58c  pop     r14
0x18002f58e  pop     r13
0x18002f590  pop     r12
0x18002f592  pop     rdi
0x18002f593  retn
0x18007fb70  push    rbp
0x18007fb72  sub     rsp, 40h
0x18007fb76  mov     rbp, rdx
0x18007fb79  mov     rcx, [rcx]
0x18007fb7c  mov     ecx, [rcx]; ExceptionCode
0x18007fb7e  call    cs:__imp_I_RpcExceptionFilter
0x18007fb84  nop
0x18007fb85  add     rsp, 40h
0x18007fb89  pop     rbp
0x18007fb8a  retn
```
