# RdInfo::GetRdConfigParam(_RD_IP_ADDR_CONFIG_TYPE,ulong *,void *)

- ea: `0x1800607e4`
- end: `0x180060bf7`
- name: `?GetRdConfigParam@RdInfo@@QEAAKW4_RD_IP_ADDR_CONFIG_TYPE@@PEAKPEAX@Z`
- size: `1043`
- prototype: `unsigned int __high(enum _RD_IP_ADDR_CONFIG_TYPE, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180058e78`

## callees

- `0x1800607e4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180060932`
- `msvcrt!memcpy_s` at `0x180060b0f`
- `msvcrt!memcpy_s` at `0x180060bce`
- `msvcrt!memcpy_s` at `0x180060932`
- `msvcrt!memcpy_s` at `0x180060b0f`
- `msvcrt!memcpy_s` at `0x180060bce`

## string_xrefs

- `0x1800609a7`: `RdInfo::GetRdConfigParam`
- `0x18006094f`: `GetRdConfigParam: memcpy_s for SERVER_V6_NBO_IP_ADDRESS failed with error %d`
- `0x180060beb`: `GetRdConfigParam: memcpy_s for SERVER_ADAPTER_NAME failed with error %d`
- `0x180060b2c`: `GetRdConfigParam: memcpy_s for SERVER_V6_IF_ID failed with error %d`
- `0x180060a59`: `GetRdConfigParam: Invalid configtype passed %d`

## pseudocode

```c
__int64 __fastcall RdInfo::GetRdConfigParam(_DWORD *a1, int a2, _DWORD *a3, _DWORD *a4)
{
  unsigned int v8; // ebx
  bool v9; // zf
  __int64 v10; // r9
  int v11; // eax
  unsigned int v12; // eax
  const wchar_t *v13; // rdx
  _WORD *v15; // r8
  rsize_t v16; // r9
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v18[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( !a3 || !a4 )
    return 87;
  v8 = 0;
  if ( a2 > 5 )
  {
    switch ( a2 )
    {
      case 6:
        if ( *a3 < 0x204u )
        {
          v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
          *a3 = 516;
          if ( v9 )
            return 122;
          v10 = 405;
          goto LABEL_32;
        }
        v15 = a1 + 24;
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        v12 = memcpy_s(a4, (unsigned int)*a3, v15, v16);
        v8 = v12;
        if ( v12 && (_QWORD)xmmword_1800C9740 )
        {
          v13 = L"GetRdConfigParam: memcpy_s for SERVER_ADAPTER_NAME failed with error %d";
          goto LABEL_28;
        }
        break;
      case 7:
        if ( *a3 < 4u )
        {
          v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
          *a3 = 4;
          if ( v9 )
            return 122;
          v10 = 417;
          goto LABEL_32;
        }
        v11 = a1[153];
        goto LABEL_35;
      case 8:
        if ( *a3 < 4u )
        {
          v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
          *a3 = 4;
          if ( v9 )
            return 122;
          v10 = 423;
          goto LABEL_32;
        }
        v11 = a1[154];
        goto LABEL_35;
      case 9:
        if ( *a3 < 8u )
        {
          v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
          *a3 = 8;
          if ( v9 )
            return 122;
          v10 = 429;
          goto LABEL_32;
        }
        v12 = memcpy_s(a4, (unsigned int)*a3, a1 + 18, 8u);
        v8 = v12;
        if ( v12 && (_QWORD)xmmword_1800C9740 )
        {
          v13 = L"GetRdConfigParam: memcpy_s for SERVER_V6_IF_ID failed with error %d";
          goto LABEL_28;
        }
        break;
      case 10:
        if ( *a3 < 4u )
        {
          v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
          *a3 = 4;
          if ( v9 )
            return 122;
          v10 = 440;
          goto LABEL_32;
        }
        v11 = a1[156];
        goto LABEL_35;
      default:
LABEL_45:
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v17) = 0;
          FormatRRASErrorString(&v17, L"GetRdConfigParam: Invalid configtype passed %d", (unsigned int)a2);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v17);
        }
        return 87;
    }
  }
  else
  {
    if ( a2 == 5 )
    {
      if ( *a3 < 4u )
      {
        v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
        *a3 = 4;
        if ( v9 )
          return 122;
        v10 = 399;
        goto LABEL_32;
      }
      v11 = a1[23];
      goto LABEL_35;
    }
    if ( !a2 )
    {
      if ( *a3 < 4u )
      {
        v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
        *a3 = 4;
        if ( !v9 )
        {
          v10 = 363;
          goto LABEL_32;
        }
        return 122;
      }
      v11 = a1[4];
      goto LABEL_35;
    }
    if ( a2 != 1 )
    {
      switch ( a2 )
      {
        case 2:
          if ( *a3 < 4u )
          {
            v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
            *a3 = 4;
            if ( !v9 )
            {
              v10 = 381;
              goto LABEL_32;
            }
            return 122;
          }
          v11 = a1[20];
          goto LABEL_35;
        case 3:
          if ( *a3 < 4u )
          {
            v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
            *a3 = 4;
            if ( !v9 )
            {
              v10 = 387;
              goto LABEL_32;
            }
            return 122;
          }
          v11 = a1[21];
LABEL_35:
          *a4 = v11;
          return v8;
        case 4:
          if ( *a3 < 4u )
          {
            v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
            *a3 = 4;
            if ( !v9 )
            {
              v10 = 393;
LABEL_32:
              LOWORD(v17) = 0;
              FormatRRASErrorString(&v17, L"%s(Line#%d): Insufficient buffer.", "RdInfo::GetRdConfigParam", v10);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                *((_QWORD *)&xmmword_1800C9740 + 1),
                &v17);
              return 122;
            }
            return 122;
          }
          v11 = a1[22];
          goto LABEL_35;
      }
      goto LABEL_45;
    }
    if ( *a3 < 0x34u )
    {
      v9 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
      *a3 = 52;
      if ( !v9 )
      {
        v10 = 369;
        goto LABEL_32;
      }
      return 122;
    }
    v12 = memcpy_s(a4, (unsigned int)*a3, a1 + 5, 0x34u);
    v8 = v12;
    if ( v12 && (_QWORD)xmmword_1800C9740 )
    {
      v13 = L"GetRdConfigParam: memcpy_s for SERVER_V6_NBO_IP_ADDRESS failed with error %d";
LABEL_28:
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, v13, v12);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v17);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800607e4  push    rbp
0x1800607e6  push    rbx
0x1800607e7  push    rsi
0x1800607e8  push    rdi
0x1800607e9  push    r12
0x1800607eb  push    r14
0x1800607ed  push    r15
0x1800607ef  lea     rbp, [rsp-730h]
0x1800607f7  sub     rsp, 830h
0x1800607fe  mov     rax, cs:__security_cookie
0x180060805  xor     rax, rsp
0x180060808  mov     [rbp+760h+var_40], rax
0x18006080f  mov     rdi, r8
0x180060812  mov     r15d, edx
0x180060815  mov     r14, rcx
0x180060818  xor     r12d, r12d
0x18006081b  xor     edx, edx; Val
0x18006081d  mov     [rsp+860h+var_840], r12d
0x180060822  mov     r8d, 7FCh; Size
0x180060828  lea     rcx, [rsp+860h+var_83C]; void *
0x18006082d  mov     rsi, r9
0x180060830  call    memset_0
0x180060835  test    rdi, rdi
0x180060838  jz      loc_180060A89
0x18006083e  test    rsi, rsi
0x180060841  jz      loc_180060A89
0x180060847  mov     ebx, r12d
0x18006084a  cmp     r15d, 5
0x18006084e  jg      loc_180060A1B
0x180060854  jz      loc_1800609F9
0x18006085a  mov     ecx, r15d
0x18006085d  test    r15d, r15d
0x180060860  jz      loc_18006098D
0x180060866  sub     ecx, 1
0x180060869  jz      loc_180060906
0x18006086f  sub     ecx, 1
0x180060872  jz      short loc_1800608DA
0x180060874  sub     ecx, 1
0x180060877  jz      short loc_1800608AE
0x180060879  cmp     ecx, 1
0x18006087c  jnz     loc_180060A47
0x180060882  cmp     dword ptr [rdi], 4
0x180060885  jnb     short loc_1800608A5
0x180060887  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x18006088e  mov     dword ptr [rdi], 4
0x180060894  jz      loc_1800609E4
0x18006089a  mov     r9d, 189h
0x1800608a0  jmp     loc_1800609A7
0x1800608a5  mov     eax, [r14+58h]
0x1800608a9  jmp     loc_1800609F2
0x1800608ae  cmp     dword ptr [rdi], 4
0x1800608b1  jnb     short loc_1800608D1
0x1800608b3  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x1800608ba  mov     dword ptr [rdi], 4
0x1800608c0  jz      loc_1800609E4
0x1800608c6  mov     r9d, 183h
0x1800608cc  jmp     loc_1800609A7
0x1800608d1  mov     eax, [r14+54h]
0x1800608d5  jmp     loc_1800609F2
0x1800608da  cmp     dword ptr [rdi], 4
0x1800608dd  jnb     short loc_1800608FD
0x1800608df  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x1800608e6  mov     dword ptr [rdi], 4
0x1800608ec  jz      loc_1800609E4
0x1800608f2  mov     r9d, 17Dh
0x1800608f8  jmp     loc_1800609A7
0x1800608fd  mov     eax, [r14+50h]
0x180060901  jmp     loc_1800609F2
0x180060906  mov     r9d, 34h ; '4'; SourceSize
0x18006090c  cmp     [rdi], r9d
0x18006090f  jnb     short loc_180060929
0x180060911  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x180060918  mov     [rdi], r9d
0x18006091b  jz      loc_1800609E4
0x180060921  mov     r9d, 171h
0x180060927  jmp     short loc_1800609A7
0x180060929  mov     edx, [rdi]; DestinationSize
0x18006092b  lea     r8, [r14+14h]; Source
0x18006092f  mov     rcx, rsi; Destination
0x180060932  call    cs:__imp_memcpy_s
0x180060938  mov     ebx, eax
0x18006093a  test    eax, eax
0x18006093c  jz      loc_180060A8E
0x180060942  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180060949  jz      loc_180060A8E
0x18006094f  lea     rdx, aGetrdconfigpar_3; "GetRdConfigParam: memcpy_s for SERVER_V"...
0x180060956  mov     r8d, eax
0x180060959  mov     word ptr [rsp+860h+var_840], r12w
0x18006095f  lea     rcx, [rsp+860h+var_840]
0x180060964  call    FormatRRASErrorString
0x180060969  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180060970  lea     r8, [rsp+860h+var_840]
0x180060975  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18006097c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180060983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060988  jmp     loc_180060A8E
0x18006098d  cmp     dword ptr [rdi], 4
0x180060990  jnb     short loc_1800609EE
0x180060992  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x180060999  mov     dword ptr [rdi], 4
0x18006099f  jz      short loc_1800609E4
0x1800609a1  mov     r9d, 16Bh
0x1800609a7  lea     r8, aRdinfoGetrdcon; "RdInfo::GetRdConfigParam"
0x1800609ae  mov     word ptr [rsp+860h+var_840], r12w
0x1800609b4  lea     rdx, aSLineDInsuffic; "%s(Line#%d): Insufficient buffer."
0x1800609bb  lea     rcx, [rsp+860h+var_840]
0x1800609c0  call    FormatRRASErrorString
0x1800609c5  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x1800609cc  lea     r8, [rsp+860h+var_840]
0x1800609d1  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800609d8  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800609df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800609e4  mov     ebx, 7Ah ; 'z'
0x1800609e9  jmp     loc_180060A8E
0x1800609ee  mov     eax, [r14+10h]
0x1800609f2  mov     [rsi], eax
0x1800609f4  jmp     loc_180060A8E
0x1800609f9  cmp     dword ptr [rdi], 4
0x1800609fc  jnb     short loc_180060A15
0x1800609fe  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x180060a05  mov     dword ptr [rdi], 4
0x180060a0b  jz      short loc_1800609E4
0x180060a0d  mov     r9d, 18Fh
0x180060a13  jmp     short loc_1800609A7
0x180060a15  mov     eax, [r14+5Ch]
0x180060a19  jmp     short loc_1800609F2
0x180060a1b  mov     ecx, r15d
0x180060a1e  sub     ecx, 6
0x180060a21  jz      loc_180060B96
0x180060a27  sub     ecx, 1
0x180060a2a  jz      loc_180060B67
0x180060a30  sub     ecx, 1
0x180060a33  jz      loc_180060B38
0x180060a39  sub     ecx, 1
0x180060a3c  jz      loc_180060AE0
0x180060a42  cmp     ecx, 1
0x180060a45  jz      short loc_180060AB1
0x180060a47  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180060a4e  jz      short loc_180060A89
0x180060a50  mov     r8d, r15d
0x180060a53  mov     word ptr [rsp+860h+var_840], r12w
0x180060a59  lea     rdx, aGetrdconfigpar_1; "GetRdConfigParam: Invalid configtype pa"...
0x180060a60  lea     rcx, [rsp+860h+var_840]
0x180060a65  call    FormatRRASErrorString
0x180060a6a  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180060a71  lea     r8, [rsp+860h+var_840]
0x180060a76  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180060a7d  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180060a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060a89  mov     ebx, 57h ; 'W'
0x180060a8e  mov     eax, ebx
0x180060a90  mov     rcx, [rbp+760h+var_40]
0x180060a97  xor     rcx, rsp; StackCookie
0x180060a9a  call    __security_check_cookie
0x180060a9f  add     rsp, 830h
0x180060aa6  pop     r15
0x180060aa8  pop     r14
0x180060aaa  pop     r12
0x180060aac  pop     rdi
0x180060aad  pop     rsi
0x180060aae  pop     rbx
0x180060aaf  pop     rbp
0x180060ab0  retn
0x180060ab1  cmp     dword ptr [rdi], 4
0x180060ab4  jnb     short loc_180060AD4
0x180060ab6  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x180060abd  mov     dword ptr [rdi], 4
0x180060ac3  jz      loc_1800609E4
0x180060ac9  mov     r9d, 1B8h
0x180060acf  jmp     loc_1800609A7
0x180060ad4  mov     eax, [r14+270h]
0x180060adb  jmp     loc_1800609F2
0x180060ae0  mov     r9d, 8; SourceSize
0x180060ae6  cmp     [rdi], r9d
0x180060ae9  jnb     short loc_180060B06
0x180060aeb  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x180060af2  mov     [rdi], r9d
0x180060af5  jz      loc_1800609E4
0x180060afb  mov     r9d, 1ADh
0x180060b01  jmp     loc_1800609A7
0x180060b06  mov     edx, [rdi]; DestinationSize
0x180060b08  lea     r8, [r14+48h]; Source
0x180060b0c  mov     rcx, rsi; Destination
0x180060b0f  call    cs:__imp_memcpy_s
0x180060b15  mov     ebx, eax
0x180060b17  test    eax, eax
0x180060b19  jz      loc_180060A8E
0x180060b1f  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180060b26  jz      loc_180060A8E
0x180060b2c  lea     rdx, aGetrdconfigpar_0; "GetRdConfigParam: memcpy_s for SERVER_V"...
0x180060b33  jmp     loc_180060956
0x180060b38  cmp     dword ptr [rdi], 4
0x180060b3b  jnb     short loc_180060B5B
0x180060b3d  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x180060b44  mov     dword ptr [rdi], 4
0x180060b4a  jz      loc_1800609E4
0x180060b50  mov     r9d, 1A7h
0x180060b56  jmp     loc_1800609A7
0x180060b5b  mov     eax, [r14+268h]
0x180060b62  jmp     loc_1800609F2
0x180060b67  cmp     dword ptr [rdi], 4
0x180060b6a  jnb     short loc_180060B8A
0x180060b6c  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x180060b73  mov     dword ptr [rdi], 4
0x180060b79  jz      loc_1800609E4
0x180060b7f  mov     r9d, 1A1h
0x180060b85  jmp     loc_1800609A7
0x180060b8a  mov     eax, [r14+264h]
0x180060b91  jmp     loc_1800609F2
0x180060b96  mov     eax, 204h
0x180060b9b  cmp     [rdi], eax
0x180060b9d  jnb     short loc_180060BB7
0x180060b9f  cmp     qword ptr cs:xmmword_1800C9740+8, r12
0x180060ba6  mov     [rdi], eax
0x180060ba8  jz      loc_1800609E4
0x180060bae  lea     r9d, [rax-6Fh]
0x180060bb2  jmp     loc_1800609A7
0x180060bb7  lea     r8, [r14+60h]; Source
0x180060bbb  or      r9, 0FFFFFFFFFFFFFFFFh
0x180060bbf  inc     r9; SourceSize
0x180060bc2  cmp     [r8+r9*2], r12w
0x180060bc7  jnz     short loc_180060BBF
0x180060bc9  mov     edx, [rdi]; DestinationSize
0x180060bcb  mov     rcx, rsi; Destination
0x180060bce  call    cs:__imp_memcpy_s
0x180060bd4  mov     ebx, eax
0x180060bd6  test    eax, eax
0x180060bd8  jz      loc_180060A8E
0x180060bde  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180060be5  jz      loc_180060A8E
0x180060beb  lea     rdx, aGetrdconfigpar; "GetRdConfigParam: memcpy_s for SERVER_A"...
0x180060bf2  jmp     loc_180060956
```
