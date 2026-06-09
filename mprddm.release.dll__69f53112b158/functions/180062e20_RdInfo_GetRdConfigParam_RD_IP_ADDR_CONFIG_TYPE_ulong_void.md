# RdInfo::GetRdConfigParam(_RD_IP_ADDR_CONFIG_TYPE,ulong *,void *)

- ea: `0x180062e20`
- end: `0x18006322c`
- name: `?GetRdConfigParam@RdInfo@@QEAAKW4_RD_IP_ADDR_CONFIG_TYPE@@PEAKPEAX@Z`
- size: `1036`
- prototype: `unsigned int __high(enum _RD_IP_ADDR_CONFIG_TYPE, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005adcc`

## callees

- `0x180062e20`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180062f7f`
- `msvcrt!memcpy_s` at `0x180063110`
- `msvcrt!memcpy_s` at `0x1800631dc`
- `msvcrt!memcpy_s` at `0x180062f7f`
- `msvcrt!memcpy_s` at `0x180063110`
- `msvcrt!memcpy_s` at `0x1800631dc`

## string_xrefs

- `0x180062fe8`: `RdInfo::GetRdConfigParam`
- `0x180062fa2`: `GetRdConfigParam: memcpy_s for SERVER_V6_NBO_IP_ADDRESS failed with error %d`
- `0x1800631f7`: `GetRdConfigParam: memcpy_s for SERVER_ADAPTER_NAME failed with error %d`
- `0x180063133`: `GetRdConfigParam: memcpy_s for SERVER_V6_IF_ID failed with error %d`
- `0x18006309d`: `GetRdConfigParam: Invalid configtype passed %d`

## pseudocode

```c
__int64 __fastcall RdInfo::GetRdConfigParam(_DWORD *a1, int a2, _DWORD *a3, _DWORD *a4)
{
  unsigned int v7; // ebx
  bool v9; // zf
  __int64 v10; // r9
  int v11; // eax
  unsigned int v12; // eax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  _WORD *v16; // r8
  rsize_t v17; // r9
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v20[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v19 = 0;
  v7 = 0;
  memset_0(v20, 0, sizeof(v20));
  if ( !a3 || !a4 )
    return 87;
  if ( a2 > 5 )
  {
    switch ( a2 )
    {
      case 6:
        if ( *a3 < 0x204u )
        {
          v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
          v7 = 122;
          *a3 = 516;
          if ( v9 )
            return v7;
          v10 = 406;
          goto LABEL_33;
        }
        v16 = a1 + 24;
        v17 = -1;
        do
          ++v17;
        while ( v16[v17] );
        v12 = memcpy_s(a4, (unsigned int)*a3, v16, v17);
        v7 = v12;
        if ( !v12 || !(_QWORD)xmmword_1800D0740 )
          return v7;
        v13 = L"GetRdConfigParam: memcpy_s for SERVER_ADAPTER_NAME failed with error %d";
        break;
      case 7:
        if ( *a3 < 4u )
        {
          v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
          v7 = 122;
          *a3 = 4;
          if ( v9 )
            return v7;
          v10 = 418;
          goto LABEL_33;
        }
        v11 = a1[153];
        goto LABEL_36;
      case 8:
        if ( *a3 < 4u )
        {
          v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
          v7 = 122;
          *a3 = 4;
          if ( v9 )
            return v7;
          v10 = 424;
          goto LABEL_33;
        }
        v11 = a1[154];
        goto LABEL_36;
      case 9:
        if ( *a3 < 8u )
        {
          v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
          v7 = 122;
          *a3 = 8;
          if ( v9 )
            return v7;
          v10 = 430;
          goto LABEL_33;
        }
        v12 = memcpy_s(a4, (unsigned int)*a3, a1 + 18, 8u);
        v7 = v12;
        if ( !v12 || !(_QWORD)xmmword_1800D0740 )
          return v7;
        v13 = L"GetRdConfigParam: memcpy_s for SERVER_V6_IF_ID failed with error %d";
        break;
      case 10:
        if ( *a3 < 4u )
        {
          v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
          v7 = 122;
          *a3 = 4;
          if ( v9 )
            return v7;
          v10 = 441;
          goto LABEL_33;
        }
        v11 = a1[156];
        goto LABEL_36;
      default:
LABEL_46:
        v7 = 87;
        if ( !(_QWORD)xmmword_1800D0740 )
          return v7;
        v14 = (unsigned int)a2;
        v13 = L"GetRdConfigParam: Invalid configtype passed %d";
        goto LABEL_29;
    }
LABEL_28:
    v14 = v12;
LABEL_29:
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, v13, v14);
    v15 = xmmword_1800D0740;
LABEL_34:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      v15,
      &v19);
    return v7;
  }
  switch ( a2 )
  {
    case 5:
      if ( *a3 < 4u )
      {
        v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
        v7 = 122;
        *a3 = 4;
        if ( v9 )
          return v7;
        v10 = 400;
        goto LABEL_33;
      }
      v11 = a1[23];
      goto LABEL_36;
    case 0:
      if ( *a3 < 4u )
      {
        v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
        v7 = 122;
        *a3 = 4;
        if ( !v9 )
        {
          v10 = 364;
          goto LABEL_33;
        }
        return v7;
      }
      v11 = a1[4];
      goto LABEL_36;
    case 1:
      if ( *a3 < 0x34u )
      {
        v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
        v7 = 122;
        *a3 = 52;
        if ( !v9 )
        {
          v10 = 370;
          goto LABEL_33;
        }
        return v7;
      }
      v12 = memcpy_s(a4, (unsigned int)*a3, a1 + 5, 0x34u);
      v7 = v12;
      if ( !v12 || !(_QWORD)xmmword_1800D0740 )
        return v7;
      v13 = L"GetRdConfigParam: memcpy_s for SERVER_V6_NBO_IP_ADDRESS failed with error %d";
      goto LABEL_28;
    case 2:
      if ( *a3 < 4u )
      {
        v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
        v7 = 122;
        *a3 = 4;
        if ( !v9 )
        {
          v10 = 382;
          goto LABEL_33;
        }
        return v7;
      }
      v11 = a1[20];
      goto LABEL_36;
  }
  if ( a2 != 3 )
  {
    if ( a2 == 4 )
    {
      if ( *a3 < 4u )
      {
        v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
        v7 = 122;
        *a3 = 4;
        if ( !v9 )
        {
          v10 = 394;
LABEL_33:
          LOWORD(v19) = 0;
          FormatRRASErrorString(&v19, L"%s(Line#%d): Insufficient buffer.", "RdInfo::GetRdConfigParam", v10);
          v15 = *((_QWORD *)&xmmword_1800D0740 + 1);
          goto LABEL_34;
        }
        return v7;
      }
      v11 = a1[22];
LABEL_36:
      *a4 = v11;
      return v7;
    }
    goto LABEL_46;
  }
  if ( *a3 >= 4u )
  {
    v11 = a1[21];
    goto LABEL_36;
  }
  v9 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
  v7 = 122;
  *a3 = 4;
  if ( !v9 )
  {
    v10 = 388;
    goto LABEL_33;
  }
  return v7;
}

```

## disassembly

```asm
0x180062e20  push    rbp
0x180062e22  push    rbx
0x180062e23  push    rsi
0x180062e24  push    rdi
0x180062e25  push    r12
0x180062e27  push    r14
0x180062e29  push    r15
0x180062e2b  lea     rbp, [rsp-730h]
0x180062e33  sub     rsp, 830h
0x180062e3a  mov     rax, cs:__security_cookie
0x180062e41  xor     rax, rsp
0x180062e44  mov     [rbp+760h+var_40], rax
0x180062e4b  mov     rdi, r8
0x180062e4e  mov     r15d, edx
0x180062e51  mov     r14, rcx
0x180062e54  xor     r12d, r12d
0x180062e57  xor     edx, edx; Val
0x180062e59  mov     [rsp+860h+var_840], r12d
0x180062e5e  mov     r8d, 7FCh; Size
0x180062e64  lea     rcx, [rsp+860h+var_83C]; void *
0x180062e69  mov     ebx, r12d
0x180062e6c  mov     rsi, r9
0x180062e6f  call    memset_0
0x180062e74  test    rdi, rdi
0x180062e77  jz      loc_180063203
0x180062e7d  test    rsi, rsi
0x180062e80  jz      loc_180063203
0x180062e86  cmp     r15d, 5
0x180062e8a  jg      loc_180063060
0x180062e90  jz      loc_180063035
0x180062e96  mov     ecx, r15d
0x180062e99  test    r15d, r15d
0x180062e9c  jz      loc_180062FC5
0x180062ea2  sub     ecx, 1
0x180062ea5  jz      loc_180062F4F
0x180062eab  sub     ecx, 1
0x180062eae  jz      short loc_180062F1E
0x180062eb0  sub     ecx, 1
0x180062eb3  jz      short loc_180062EED
0x180062eb5  cmp     ecx, 1
0x180062eb8  jnz     loc_180063088
0x180062ebe  cmp     dword ptr [rdi], 4
0x180062ec1  jnb     short loc_180062EE4
0x180062ec3  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x180062eca  lea     ebx, [rcx+79h]
0x180062ecd  mov     dword ptr [rdi], 4
0x180062ed3  jz      loc_180063208
0x180062ed9  mov     r9d, 18Ah
0x180062edf  jmp     loc_180062FE8
0x180062ee4  mov     eax, [r14+58h]
0x180062ee8  jmp     loc_18006302E
0x180062eed  cmp     dword ptr [rdi], 4
0x180062ef0  jnb     short loc_180062F15
0x180062ef2  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x180062ef9  mov     ebx, 7Ah ; 'z'
0x180062efe  mov     dword ptr [rdi], 4
0x180062f04  jz      loc_180063208
0x180062f0a  mov     r9d, 184h
0x180062f10  jmp     loc_180062FE8
0x180062f15  mov     eax, [r14+54h]
0x180062f19  jmp     loc_18006302E
0x180062f1e  cmp     dword ptr [rdi], 4
0x180062f21  jnb     short loc_180062F46
0x180062f23  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x180062f2a  mov     ebx, 7Ah ; 'z'
0x180062f2f  mov     dword ptr [rdi], 4
0x180062f35  jz      loc_180063208
0x180062f3b  mov     r9d, 17Eh
0x180062f41  jmp     loc_180062FE8
0x180062f46  mov     eax, [r14+50h]
0x180062f4a  jmp     loc_18006302E
0x180062f4f  mov     r9d, 34h ; '4'; SourceSize
0x180062f55  cmp     [rdi], r9d
0x180062f58  jnb     short loc_180062F76
0x180062f5a  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x180062f61  lea     ebx, [r9+46h]
0x180062f65  mov     [rdi], r9d
0x180062f68  jz      loc_180063208
0x180062f6e  mov     r9d, 172h
0x180062f74  jmp     short loc_180062FE8
0x180062f76  mov     edx, [rdi]; DestinationSize
0x180062f78  lea     r8, [r14+14h]; Source
0x180062f7c  mov     rcx, rsi; Destination
0x180062f7f  call    cs:__imp_memcpy_s
0x180062f86  nop     dword ptr [rax+rax+00h]
0x180062f8b  mov     ebx, eax
0x180062f8d  test    eax, eax
0x180062f8f  jz      loc_180063208
0x180062f95  cmp     qword ptr cs:xmmword_1800D0740, r12
0x180062f9c  jz      loc_180063208
0x180062fa2  lea     rdx, aGetrdconfigpar_3; "GetRdConfigParam: memcpy_s for SERVER_V"...
0x180062fa9  mov     r8d, eax
0x180062fac  lea     rcx, [rsp+860h+var_840]
0x180062fb1  mov     word ptr [rsp+860h+var_840], r12w
0x180062fb7  call    FormatRRASErrorString
0x180062fbc  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180062fc3  jmp     short loc_18006300D
0x180062fc5  cmp     dword ptr [rdi], 4
0x180062fc8  jnb     short loc_18006302A
0x180062fca  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x180062fd1  mov     ebx, 7Ah ; 'z'
0x180062fd6  mov     dword ptr [rdi], 4
0x180062fdc  jz      loc_180063208
0x180062fe2  mov     r9d, 16Ch
0x180062fe8  lea     r8, aRdinfoGetrdcon; "RdInfo::GetRdConfigParam"
0x180062fef  mov     word ptr [rsp+860h+var_840], r12w
0x180062ff5  lea     rdx, aSLineDInsuffic; "%s(Line#%d): Insufficient buffer."
0x180062ffc  lea     rcx, [rsp+860h+var_840]
0x180063001  call    FormatRRASErrorString
0x180063006  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18006300d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180063014  lea     r8, [rsp+860h+var_840]
0x180063019  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180063020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063025  jmp     loc_180063208
0x18006302a  mov     eax, [r14+10h]
0x18006302e  mov     [rsi], eax
0x180063030  jmp     loc_180063208
0x180063035  cmp     dword ptr [rdi], 4
0x180063038  jnb     short loc_18006305A
0x18006303a  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x180063041  mov     ebx, 7Ah ; 'z'
0x180063046  mov     dword ptr [rdi], 4
0x18006304c  jz      loc_180063208
0x180063052  mov     r9d, 190h
0x180063058  jmp     short loc_180062FE8
0x18006305a  mov     eax, [r14+5Ch]
0x18006305e  jmp     short loc_18006302E
0x180063060  mov     ecx, r15d
0x180063063  sub     ecx, 6
0x180063066  jz      loc_1800631A3
0x18006306c  sub     ecx, 1
0x18006306f  jz      loc_180063173
0x180063075  sub     ecx, 1
0x180063078  jz      loc_18006313F
0x18006307e  sub     ecx, 1
0x180063081  jz      short loc_1800630DD
0x180063083  cmp     ecx, 1
0x180063086  jz      short loc_1800630A9
0x180063088  cmp     qword ptr cs:xmmword_1800D0740, r12
0x18006308f  mov     ebx, 57h ; 'W'
0x180063094  jz      loc_180063208
0x18006309a  mov     r8d, r15d
0x18006309d  lea     rdx, aGetrdconfigpar_1; "GetRdConfigParam: Invalid configtype pa"...
0x1800630a4  jmp     loc_180062FAC
0x1800630a9  cmp     dword ptr [rdi], 4
0x1800630ac  jnb     short loc_1800630D1
0x1800630ae  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x1800630b5  mov     ebx, 7Ah ; 'z'
0x1800630ba  mov     dword ptr [rdi], 4
0x1800630c0  jz      loc_180063208
0x1800630c6  mov     r9d, 1B9h
0x1800630cc  jmp     loc_180062FE8
0x1800630d1  mov     eax, [r14+270h]
0x1800630d8  jmp     loc_18006302E
0x1800630dd  mov     r9d, 8; SourceSize
0x1800630e3  cmp     [rdi], r9d
0x1800630e6  jnb     short loc_180063107
0x1800630e8  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x1800630ef  lea     ebx, [r9+72h]
0x1800630f3  mov     [rdi], r9d
0x1800630f6  jz      loc_180063208
0x1800630fc  mov     r9d, 1AEh
0x180063102  jmp     loc_180062FE8
0x180063107  mov     edx, [rdi]; DestinationSize
0x180063109  lea     r8, [r14+48h]; Source
0x18006310d  mov     rcx, rsi; Destination
0x180063110  call    cs:__imp_memcpy_s
0x180063117  nop     dword ptr [rax+rax+00h]
0x18006311c  mov     ebx, eax
0x18006311e  test    eax, eax
0x180063120  jz      loc_180063208
0x180063126  cmp     qword ptr cs:xmmword_1800D0740, r12
0x18006312d  jz      loc_180063208
0x180063133  lea     rdx, aGetrdconfigpar_0; "GetRdConfigParam: memcpy_s for SERVER_V"...
0x18006313a  jmp     loc_180062FA9
0x18006313f  cmp     dword ptr [rdi], 4
0x180063142  jnb     short loc_180063167
0x180063144  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x18006314b  mov     ebx, 7Ah ; 'z'
0x180063150  mov     dword ptr [rdi], 4
0x180063156  jz      loc_180063208
0x18006315c  mov     r9d, 1A8h
0x180063162  jmp     loc_180062FE8
0x180063167  mov     eax, [r14+268h]
0x18006316e  jmp     loc_18006302E
0x180063173  cmp     dword ptr [rdi], 4
0x180063176  jnb     short loc_180063197
0x180063178  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x18006317f  mov     ebx, 7Ah ; 'z'
0x180063184  mov     dword ptr [rdi], 4
0x18006318a  jz      short loc_180063208
0x18006318c  mov     r9d, 1A2h
0x180063192  jmp     loc_180062FE8
0x180063197  mov     eax, [r14+264h]
0x18006319e  jmp     loc_18006302E
0x1800631a3  mov     eax, 204h
0x1800631a8  cmp     [rdi], eax
0x1800631aa  jnb     short loc_1800631C5
0x1800631ac  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x1800631b3  mov     ebx, 7Ah ; 'z'
0x1800631b8  mov     [rdi], eax
0x1800631ba  jz      short loc_180063208
0x1800631bc  lea     r9d, [rax-6Eh]
0x1800631c0  jmp     loc_180062FE8
0x1800631c5  lea     r8, [r14+60h]; Source
0x1800631c9  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800631cd  inc     r9; SourceSize
0x1800631d0  cmp     [r8+r9*2], r12w
0x1800631d5  jnz     short loc_1800631CD
0x1800631d7  mov     edx, [rdi]; DestinationSize
0x1800631d9  mov     rcx, rsi; Destination
0x1800631dc  call    cs:__imp_memcpy_s
0x1800631e3  nop     dword ptr [rax+rax+00h]
0x1800631e8  mov     ebx, eax
0x1800631ea  test    eax, eax
0x1800631ec  jz      short loc_180063208
0x1800631ee  cmp     qword ptr cs:xmmword_1800D0740, r12
0x1800631f5  jz      short loc_180063208
0x1800631f7  lea     rdx, aGetrdconfigpar; "GetRdConfigParam: memcpy_s for SERVER_A"...
0x1800631fe  jmp     loc_180062FA9
0x180063203  mov     ebx, 57h ; 'W'
0x180063208  mov     eax, ebx
0x18006320a  mov     rcx, [rbp+760h+var_40]
0x180063211  xor     rcx, rsp; StackCookie
0x180063214  call    __security_check_cookie
0x180063219  add     rsp, 830h
0x180063220  pop     r15
0x180063222  pop     r14
0x180063224  pop     r12
0x180063226  pop     rdi
0x180063227  pop     rsi
0x180063228  pop     rbx
0x180063229  pop     rbp
0x18006322a  retn
```
