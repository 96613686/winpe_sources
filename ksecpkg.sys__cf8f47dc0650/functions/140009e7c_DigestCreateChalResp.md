# DigestCreateChalResp

- ea: `0x140009e7c`
- end: `0x14000a404`
- name: `DigestCreateChalResp`
- size: `1416`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140008af4`

## callees

- `0x140006194`
- `0x140006214`
- `0x140008a70`
- `0x140008ad0`
- `0x1400095a0`
- `0x140009608`
- `0x140009e7c`
- `0x1400102c0`

## import_xrefs

- `ntoskrnl!RtlInitString` at `0x140009f40`
- `ntoskrnl!RtlInitString` at `0x140009f40`

## string_xrefs

- `0x14000a06b`: `digest-uri`
- `0x14000a313`: `,hashed-dirs="%hZ",service-name="%hZ",channel-binding="%hZ"`

## pseudocode

```c
__int64 __fastcall DigestCreateChalResp(__int64 a1, __int64 a2, __int64 a3)
{
  char *Memory; // rsi
  unsigned int v6; // ebx
  char *v7; // rdi
  int v8; // r14d
  int v9; // eax
  const char *v10; // rdx
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  int v14; // r11d
  int v15; // r10d
  unsigned int v16; // edx
  __int64 v17; // rdx
  const char *v18; // rax
  __int128 *v19; // r9
  int v20; // eax
  const char *v21; // r8
  int v22; // eax
  const char *v23; // r9
  __int128 *v24; // rcx
  __int64 v25; // rax
  size_t v26; // r14
  __int64 v27; // rax
  struct _STRING DestinationString; // [rsp+40h] [rbp-39h] BYREF
  __int128 v30; // [rsp+50h] [rbp-29h] BYREF
  __int128 v31; // [rsp+60h] [rbp-19h] BYREF
  __int128 v32; // [rsp+70h] [rbp-9h] BYREF
  __int128 v33; // [rsp+80h] [rbp+7h] BYREF
  _OWORD v34[4]; // [rsp+90h] [rbp+17h] BYREF
  __int16 v35; // [rsp+E8h] [rbp+6Fh]
  int v36; // [rsp+F8h] [rbp+7Fh] BYREF

  DestinationString = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34[0] = 0;
  Memory = (char *)DigestAllocateMemory(0x3001u);
  if ( !Memory )
  {
    v6 = -2146893056;
    goto LABEL_92;
  }
  v7 = (char *)DigestAllocateMemory(0x1001u);
  if ( !v7 )
    goto LABEL_4;
  if ( *(_DWORD *)a1 == 4 || (v8 = 0, *(_DWORD *)a1 == 5) )
    v8 = 1;
  v9 = *(_DWORD *)(a1 + 12);
  switch ( v9 )
  {
    case 4:
      v10 = "auth-conf";
      break;
    case 3:
      v10 = "auth-int";
      break;
    case 2:
      v10 = "auth";
      break;
    default:
      goto LABEL_15;
  }
  RtlInitString(&DestinationString, v10);
LABEL_15:
  v11 = *(unsigned __int16 *)(a1 + 976);
  v12 = *(unsigned __int16 *)(a1 + 40);
  v13 = *(unsigned __int16 *)(a1 + 24);
  v14 = *(unsigned __int16 *)(a1 + 72);
  v15 = *(unsigned __int16 *)(a1 + 88);
  v36 = v13;
  v35 = v12;
  v16 = DestinationString.Length
      + v15
      + v14
      + *(unsigned __int16 *)(a1 + 56)
      + *(unsigned __int16 *)(a1 + 200)
      + *(unsigned __int16 *)(a1 + 248)
      + *(unsigned __int16 *)(a1 + 152)
      + v13
      + v12
      + v11
      + (unsigned __int16)v30
      + 384;
  if ( _bittest16((const signed __int16 *)(a1 + 4), 8u) )
    v16 += *(unsigned __int16 *)(a1 + 392) + *(unsigned __int16 *)(a1 + 376) + *(unsigned __int16 *)(a1 + 360);
  if ( v16 > 0x1000 )
    goto LABEL_18;
  if ( !(_WORD)v11 || !(_WORD)v15 || !(_WORD)v14 )
    goto LABEL_89;
  if ( a1 != -24 && (_WORD)v36 )
  {
    if ( !(unsigned int)ValidateDigestName(a1 + 24, &v36, 0) )
      goto LABEL_89;
    LOWORD(v12) = v35;
  }
  if ( a1 == -40 || !(_WORD)v12 || (unsigned int)ValidateDigestName(a1 + 40, &v36, 0) )
  {
    v17 = *(_QWORD *)(a1 + 32);
    *((_QWORD *)&v30 + 1) = &byte_140012BFC;
    v18 = "digest-uri";
    *(_QWORD *)&v30 = 0x20000;
    v19 = &v30;
    if ( v35 )
    {
      if ( v8 != 1 )
        v18 = "uri";
      if ( v17 )
        v19 = (__int128 *)(a1 + 24);
      sprintf_s(
        Memory,
        0x3001u,
        "username=\"%hZ\",realm=\"%hZ\",nonce=\"%hZ\",%s=\"%hZ\"",
        v19,
        a1 + 40,
        a1 + 56,
        v18,
        a1 + 152);
    }
    else
    {
      if ( v8 != 1 )
        v18 = "uri";
      if ( v17 )
        v19 = (__int128 *)(a1 + 24);
      sprintf_s(Memory, 0x3001u, "username=\"%hZ\",realm=\"\",nonce=\"%hZ\",%s=\"%hZ\"", v19, a1 + 56, v18, a1 + 152);
    }
    if ( *(_DWORD *)(a1 + 12) != 1 )
    {
      sprintf_s(v7, 0x1001u, ",cnonce=\"%hZ\",nc=%hZ", a1 + 72, a1 + 88);
      strcat_s(Memory, 0x3001u, v7);
    }
    if ( v8 == 1 )
    {
      sprintf_s(v7, 0x1001u, ",response=%hZ", a1 + 976);
      goto LABEL_50;
    }
    v20 = *(_DWORD *)(a1 + 8);
    switch ( v20 )
    {
      case 3:
        sprintf_s(v7, 0x1001u, ",algorithm=MD5-sess,response=\"%hZ\"", a1 + 976);
        goto LABEL_50;
      case 2:
        sprintf_s(v7, 0x1001u, ",algorithm=MD5,response=\"%hZ\"", a1 + 976);
        goto LABEL_50;
      case 1:
        sprintf_s(v7, 0x1001u, ",response=\"%hZ\"", a1 + 976);
LABEL_50:
        strcat_s(Memory, 0x3001u, v7);
        if ( DestinationString.Length )
        {
          if ( v8 == 1 || (v21 = ",qop=\"%hZ\"", (*(_BYTE *)(a1 + 4) & 0x20) == 0) )
            v21 = ",qop=%hZ";
          sprintf_s(v7, 0x1001u, v21, &DestinationString);
          strcat_s(Memory, 0x3001u, v7);
        }
        if ( *(_DWORD *)(a1 + 12) == 4 )
        {
          v22 = *(_DWORD *)(a1 + 16);
          switch ( v22 )
          {
            case 4:
              v23 = "rc4";
              break;
            case 5:
              v23 = "rc4-56";
              break;
            case 3:
              v23 = "rc4-40";
              break;
            case 1:
              v23 = "3des";
              break;
            case 2:
              v23 = "des";
              break;
            default:
              goto LABEL_67;
          }
          sprintf_s(v7, 0x1001u, ",cipher=%s", v23);
          strcat_s(Memory, 0x3001u, v7);
        }
LABEL_67:
        if ( v8 )
        {
          if ( (*(_BYTE *)(a1 + 4) & 2) == 0 )
            goto LABEL_75;
          if ( *(_WORD *)(a1 + 200) )
            sprintf_s(v7, 0x1001u, ",authzid=\"%hZ\"");
          else
            sprintf_s(v7, 0x1001u, ",authzid=\"\"");
        }
        else
        {
          if ( !*(_WORD *)(a1 + 248) )
            goto LABEL_75;
          sprintf_s(v7, 0x1001u, ",opaque=\"%hZ\"");
        }
        strcat_s(Memory, 0x3001u, v7);
LABEL_75:
        if ( *(_DWORD *)(a1 + 20) == 2 )
          strcat_s(Memory, 0x3001u, ",charset=utf-8");
        if ( _bittest16((const signed __int16 *)(a1 + 4), 8u) )
        {
          *(_QWORD *)&v30 = 0x20000;
          *((_QWORD *)&v30 + 1) = &byte_140012BFC;
          v24 = &v30;
          if ( *(_WORD *)(a1 + 376) )
            v24 = (__int128 *)(a1 + 376);
          sprintf_s(
            v7,
            0x1001u,
            ",hashed-dirs=\"%hZ\",service-name=\"%hZ\",channel-binding=\"%hZ\"",
            a1 + 360,
            v24,
            a1 + 392);
          strcat_s(Memory, 0x3001u, v7);
        }
        v25 = -1;
        do
          ++v25;
        while ( Memory[v25] );
        v26 = (unsigned __int16)v25;
        if ( (unsigned __int16)v25 <= 0x1000u )
        {
          if ( !*(_DWORD *)a3 )
          {
            v27 = DigestAllocateMemory((unsigned __int16)v25);
            *(_QWORD *)(a3 + 8) = v27;
            if ( !v27 )
            {
LABEL_4:
              v6 = -2146893056;
              goto LABEL_90;
            }
            goto LABEL_88;
          }
          if ( (unsigned int)(unsigned __int16)v25 <= *(_DWORD *)a3 )
          {
LABEL_88:
            v6 = 0;
            memmove(*(void **)(a3 + 8), Memory, v26);
            *(_DWORD *)a3 = v26;
            *(_DWORD *)(a3 + 4) = 2;
            goto LABEL_90;
          }
        }
LABEL_18:
        v6 = -1073741789;
        goto LABEL_90;
    }
  }
LABEL_89:
  v6 = -1073741811;
LABEL_90:
  DigestFreeMemory(Memory);
  if ( v7 )
    DigestFreeMemory(v7);
LABEL_92:
  StringFree(&v31);
  StringFree(&v32);
  StringFree(&v33);
  StringFree(v34);
  return v6;
}

```

## disassembly

```asm
0x140009e7c  mov     [rsp-8+arg_0], rbx
0x140009e81  mov     [rsp-8+arg_8], rdx
0x140009e86  push    rbp
0x140009e87  push    rsi
0x140009e88  push    rdi
0x140009e89  push    r12
0x140009e8b  push    r13
0x140009e8d  push    r14
0x140009e8f  push    r15
0x140009e91  lea     rbp, [rsp-27h]
0x140009e96  sub     rsp, 0A0h
0x140009e9d  xorps   xmm0, xmm0
0x140009ea0  xorps   xmm1, xmm1
0x140009ea3  mov     rbx, rcx
0x140009ea6  mov     r15, r8
0x140009ea9  mov     ecx, 3001h; Size
0x140009eae  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140009eb2  movups  [rbp+57h+var_80], xmm1
0x140009eb6  movups  [rbp+57h+var_70], xmm0
0x140009eba  movups  [rbp+57h+var_60], xmm1
0x140009ebe  movups  [rbp+57h+var_50], xmm0
0x140009ec2  movups  [rbp+57h+var_40], xmm1
0x140009ec6  call    DigestAllocateMemory
0x140009ecb  xor     r12d, r12d
0x140009ece  mov     rsi, rax
0x140009ed1  test    rax, rax
0x140009ed4  jnz     short loc_140009EE0
0x140009ed6  mov     ebx, 80090300h
0x140009edb  jmp     loc_14000A3C2
0x140009ee0  mov     ecx, 1001h; Size
0x140009ee5  call    DigestAllocateMemory
0x140009eea  mov     rdi, rax
0x140009eed  test    rax, rax
0x140009ef0  jnz     short loc_140009EFC
0x140009ef2  mov     ebx, 80090300h
0x140009ef7  jmp     loc_14000A3AD
0x140009efc  mov     eax, [rbx]
0x140009efe  cmp     eax, 4
0x140009f01  jz      short loc_140009F0B
0x140009f03  mov     r14d, r12d
0x140009f06  cmp     eax, 5
0x140009f09  jnz     short loc_140009F11
0x140009f0b  mov     r14d, 1
0x140009f11  mov     eax, [rbx+0Ch]
0x140009f14  cmp     eax, 4
0x140009f17  jnz     short loc_140009F22
0x140009f19  lea     rdx, aAuthConf; "auth-conf"
0x140009f20  jmp     short loc_140009F3C
0x140009f22  cmp     eax, 3
0x140009f25  jnz     short loc_140009F30
0x140009f27  lea     rdx, aAuthInt; "auth-int"
0x140009f2e  jmp     short loc_140009F3C
0x140009f30  cmp     eax, 2
0x140009f33  jnz     short loc_140009F4C
0x140009f35  lea     rdx, SourceString; "auth"
0x140009f3c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140009f40  call    cs:__imp_RtlInitString
0x140009f47  nop     dword ptr [rax+rax+00h]
0x140009f4c  movzx   r8d, word ptr [rbx+3D0h]
0x140009f54  lea     r12, [rbx+28h]
0x140009f58  movzx   r9d, word ptr [r12]
0x140009f5d  lea     r13, [rbx+18h]
0x140009f61  movzx   eax, word ptr [r13+0]
0x140009f66  movzx   r11d, word ptr [rbx+48h]
0x140009f6b  movzx   r10d, word ptr [rbx+58h]
0x140009f70  movzx   edx, word ptr [rbp+57h+var_80]
0x140009f74  lea     ecx, [r9+r8]
0x140009f78  add     ecx, eax
0x140009f7a  mov     [rbp+57h+arg_18], eax
0x140009f7d  movzx   eax, word ptr [rbx+98h]
0x140009f84  add     edx, 180h
0x140009f8a  add     ecx, eax
0x140009f8c  mov     dword ptr [rbp+57h+arg_8], r9d
0x140009f90  movzx   eax, word ptr [rbx+0F8h]
0x140009f97  add     ecx, eax
0x140009f99  movzx   eax, word ptr [rbx+0C8h]
0x140009fa0  add     ecx, eax
0x140009fa2  movzx   eax, word ptr [rbx+38h]
0x140009fa6  add     ecx, eax
0x140009fa8  movzx   eax, [rbp+57h+DestinationString.Length]
0x140009fac  add     ecx, r11d
0x140009faf  add     ecx, r10d
0x140009fb2  add     ecx, eax
0x140009fb4  add     edx, ecx
0x140009fb6  bt      word ptr [rbx+4], 8
0x140009fbc  jnb     short loc_140009FD9
0x140009fbe  movzx   ecx, word ptr [rbx+178h]
0x140009fc5  movzx   eax, word ptr [rbx+188h]
0x140009fcc  add     ecx, edx
0x140009fce  movzx   edx, word ptr [rbx+168h]
0x140009fd5  add     ecx, eax
0x140009fd7  add     edx, ecx
0x140009fd9  cmp     edx, 1000h
0x140009fdf  jbe     short loc_140009FEB
0x140009fe1  mov     ebx, 0C0000023h
0x140009fe6  jmp     loc_14000A3AD
0x140009feb  test    r8w, r8w
0x140009fef  jz      loc_14000A3A8
0x140009ff5  xor     r8d, r8d
0x140009ff8  test    r10w, r10w
0x140009ffc  jz      loc_14000A3A8
0x14000a002  test    r11w, r11w
0x14000a006  jz      loc_14000A3A8
0x14000a00c  test    r13, r13
0x14000a00f  jz      short loc_14000A033
0x14000a011  cmp     word ptr [rbp+57h+arg_18], r8w
0x14000a016  jz      short loc_14000A033
0x14000a018  lea     rdx, [rbp+57h+arg_18]
0x14000a01c  mov     rcx, r13
0x14000a01f  call    ValidateDigestName
0x14000a024  xor     r8d, r8d
0x14000a027  test    eax, eax
0x14000a029  jz      loc_14000A3A8
0x14000a02f  mov     r9d, dword ptr [rbp+57h+arg_8]
0x14000a033  test    r12, r12
0x14000a036  jz      short loc_14000A055
0x14000a038  test    r9w, r9w
0x14000a03c  jz      short loc_14000A055
0x14000a03e  lea     rdx, [rbp+57h+arg_18]
0x14000a042  mov     rcx, r12
0x14000a045  call    ValidateDigestName
0x14000a04a  xor     r8d, r8d
0x14000a04d  test    eax, eax
0x14000a04f  jz      loc_14000A3A8
0x14000a055  lea     rax, byte_140012BFC
0x14000a05c  mov     rdx, [r13+8]
0x14000a060  lea     rcx, aUri; "uri"
0x14000a067  mov     qword ptr [rbp+57h+var_80+8], rax
0x14000a06b  lea     rax, aDigestUri; "digest-uri"
0x14000a072  mov     qword ptr [rbp+57h+var_80], 20000h
0x14000a07a  lea     r9, [rbp+57h+var_80]
0x14000a07e  cmp     word ptr [rbp+57h+arg_8], r8w
0x14000a083  jz      short loc_14000A0CD
0x14000a085  cmp     r14d, 1
0x14000a089  lea     r8, aUsernameHzReal; "username=\"%hZ\",realm=\"%hZ\",nonce=\""...
0x14000a090  cmovnz  rax, rcx
0x14000a094  test    rdx, rdx
0x14000a097  lea     rcx, [rbx+98h]
0x14000a09e  mov     [rsp+0D0h+var_98], rcx
0x14000a0a3  cmovnz  r9, r13
0x14000a0a7  mov     [rsp+0D0h+var_A0], rax
0x14000a0ac  mov     r13d, 3001h
0x14000a0b2  lea     rax, [rbx+38h]
0x14000a0b6  mov     edx, r13d; SizeInBytes
0x14000a0b9  mov     [rsp+0D0h+var_A8], rax
0x14000a0be  mov     rcx, rsi; DstBuf
0x14000a0c1  mov     [rsp+0D0h+var_B0], r12
0x14000a0c6  call    sprintf_s
0x14000a0cb  jmp     short loc_14000A10E
0x14000a0cd  cmp     r14d, 1
0x14000a0d1  lea     r8, aUsernameHzReal_0; "username=\"%hZ\",realm=\"\",nonce=\"%hZ"...
0x14000a0d8  cmovnz  rax, rcx
0x14000a0dc  test    rdx, rdx
0x14000a0df  lea     rcx, [rbx+98h]
0x14000a0e6  mov     [rsp+0D0h+var_A0], rcx
0x14000a0eb  cmovnz  r9, r13
0x14000a0ef  mov     [rsp+0D0h+var_A8], rax
0x14000a0f4  mov     r13d, 3001h
0x14000a0fa  lea     rax, [rbx+38h]
0x14000a0fe  mov     edx, r13d; SizeInBytes
0x14000a101  mov     rcx, rsi; DstBuf
0x14000a104  mov     [rsp+0D0h+var_B0], rax
0x14000a109  call    sprintf_s
0x14000a10e  cmp     dword ptr [rbx+0Ch], 1
0x14000a112  jz      short loc_14000A143
0x14000a114  lea     rax, [rbx+58h]
0x14000a118  mov     edx, 1001h; SizeInBytes
0x14000a11d  lea     r9, [rbx+48h]
0x14000a121  mov     [rsp+0D0h+var_B0], rax
0x14000a126  lea     r8, aCnonceHzNcHz; ",cnonce=\"%hZ\",nc=%hZ"
0x14000a12d  mov     rcx, rdi; DstBuf
0x14000a130  call    sprintf_s
0x14000a135  mov     r8, rdi; Src
0x14000a138  mov     rdx, r13; SizeInBytes
0x14000a13b  mov     rcx, rsi; char *
0x14000a13e  call    strcat_s
0x14000a143  cmp     r14d, 1
0x14000a147  jnz     short loc_14000A152
0x14000a149  lea     r8, aResponseHz; ",response=%hZ"
0x14000a150  jmp     short loc_14000A181
0x14000a152  mov     eax, [rbx+8]
0x14000a155  cmp     eax, 3
0x14000a158  jnz     short loc_14000A163
0x14000a15a  lea     r8, aAlgorithmMd5Se; ",algorithm=MD5-sess,response=\"%hZ\""
0x14000a161  jmp     short loc_14000A181
0x14000a163  cmp     eax, 2
0x14000a166  jnz     short loc_14000A171
0x14000a168  lea     r8, aAlgorithmMd5Re; ",algorithm=MD5,response=\"%hZ\""
0x14000a16f  jmp     short loc_14000A181
0x14000a171  cmp     eax, 1
0x14000a174  jnz     loc_14000A3A8
0x14000a17a  lea     r8, aResponseHz_0; ",response=\"%hZ\""
0x14000a181  lea     r9, [rbx+3D0h]
0x14000a188  mov     edx, 1001h; SizeInBytes
0x14000a18d  mov     rcx, rdi; DstBuf
0x14000a190  call    sprintf_s
0x14000a195  mov     r8, rdi; Src
0x14000a198  mov     rdx, r13; SizeInBytes
0x14000a19b  mov     rcx, rsi; char *
0x14000a19e  call    strcat_s
0x14000a1a3  xor     r12d, r12d
0x14000a1a6  cmp     [rbp+57h+DestinationString.Length], r12w
0x14000a1ab  jz      short loc_14000A1E6
0x14000a1ad  cmp     r14d, 1
0x14000a1b1  jz      short loc_14000A1C0
0x14000a1b3  test    byte ptr [rbx+4], 20h
0x14000a1b7  lea     r8, aQopHz_0; ",qop=\"%hZ\""
0x14000a1be  jnz     short loc_14000A1C7
0x14000a1c0  lea     r8, aQopHz; ",qop=%hZ"
0x14000a1c7  lea     r9, [rbp+57h+DestinationString]
0x14000a1cb  mov     edx, 1001h; SizeInBytes
0x14000a1d0  mov     rcx, rdi; DstBuf
0x14000a1d3  call    sprintf_s
0x14000a1d8  mov     r8, rdi; Src
0x14000a1db  mov     rdx, r13; SizeInBytes
0x14000a1de  mov     rcx, rsi; char *
0x14000a1e1  call    strcat_s
0x14000a1e6  cmp     dword ptr [rbx+0Ch], 4
0x14000a1ea  jnz     short loc_14000A255
0x14000a1ec  mov     eax, [rbx+10h]
0x14000a1ef  cmp     eax, 4
0x14000a1f2  jnz     short loc_14000A1FD
0x14000a1f4  lea     r9, aRc4_0; "rc4"
0x14000a1fb  jmp     short loc_14000A233
0x14000a1fd  cmp     eax, 5
0x14000a200  jnz     short loc_14000A20B
0x14000a202  lea     r9, aRc456; "rc4-56"
0x14000a209  jmp     short loc_14000A233
0x14000a20b  cmp     eax, 3
0x14000a20e  jnz     short loc_14000A219
0x14000a210  lea     r9, aRc440; "rc4-40"
0x14000a217  jmp     short loc_14000A233
0x14000a219  cmp     eax, 1
0x14000a21c  jnz     short loc_14000A227
0x14000a21e  lea     r9, a3des; "3des"
0x14000a225  jmp     short loc_14000A233
0x14000a227  cmp     eax, 2
0x14000a22a  jnz     short loc_14000A255
0x14000a22c  lea     r9, aDes_0; "des"
0x14000a233  lea     r8, aCipherS; ",cipher=%s"
0x14000a23a  mov     edx, 1001h; SizeInBytes
0x14000a23f  mov     rcx, rdi; DstBuf
0x14000a242  call    sprintf_s
0x14000a247  mov     r8, rdi; Src
0x14000a24a  mov     rdx, r13; SizeInBytes
0x14000a24d  mov     rcx, rsi; char *
0x14000a250  call    strcat_s
0x14000a255  test    r14d, r14d
0x14000a258  jnz     short loc_14000A278
0x14000a25a  lea     r9, [rbx+0F8h]
0x14000a261  cmp     [r9], r12w
0x14000a265  jz      short loc_14000A2C1
0x14000a267  lea     r8, aOpaqueHz; ",opaque=\"%hZ\""
0x14000a26e  mov     edx, 1001h
0x14000a273  mov     rcx, rdi
0x14000a276  jmp     short loc_14000A2A0
0x14000a278  cmp     r14d, 1
0x14000a27c  jnz     short loc_14000A2C1
0x14000a27e  test    byte ptr [rbx+4], 2
0x14000a282  jz      short loc_14000A2C1
0x14000a284  lea     r9, [rbx+0C8h]
0x14000a28b  mov     edx, 1001h; SizeInBytes
0x14000a290  mov     rcx, rdi; DstBuf
0x14000a293  cmp     [r9], r12w
0x14000a297  jz      short loc_14000A2A7
0x14000a299  lea     r8, aAuthzidHz; ",authzid=\"%hZ\""
0x14000a2a0  call    sprintf_s
0x14000a2a5  jmp     short loc_14000A2B3
0x14000a2a7  lea     r8, aAuthzid; ",authzid=\"\""
0x14000a2ae  call    sprintf_s
0x14000a2b3  mov     r8, rdi; Src
0x14000a2b6  mov     rdx, r13; SizeInBytes
0x14000a2b9  mov     rcx, rsi; char *
0x14000a2bc  call    strcat_s
0x14000a2c1  mov     ecx, 2
0x14000a2c6  cmp     [rbx+14h], ecx
0x14000a2c9  jnz     short loc_14000A2DD
0x14000a2cb  lea     r8, Src; ",charset=utf-8"
0x14000a2d2  mov     rdx, r13; SizeInBytes
0x14000a2d5  mov     rcx, rsi; char *
0x14000a2d8  call    strcat_s
0x14000a2dd  bt      word ptr [rbx+4], 8
0x14000a2e3  jnb     short loc_14000A345
0x14000a2e5  lea     rax, byte_140012BFC
0x14000a2ec  mov     qword ptr [rbp+57h+var_80], 20000h
0x14000a2f4  mov     qword ptr [rbp+57h+var_80+8], rax
0x14000a2f8  lea     rcx, [rbp+57h+var_80]
0x14000a2fc  lea     rax, [rbx+178h]
0x14000a303  mov     edx, 1001h; SizeInBytes
0x14000a308  cmp     [rax], r12w
0x14000a30c  lea     r9, [rbx+168h]
0x14000a313  lea     r8, aHashedDirsHzSe; ",hashed-dirs=\"%hZ\",service-name=\"%hZ"...
0x14000a31a  cmovnz  rcx, rax
0x14000a31e  lea     rax, [rbx+188h]
0x14000a325  mov     [rsp+0D0h+var_A8], rax
0x14000a32a  mov     [rsp+0D0h+var_B0], rcx
0x14000a32f  mov     rcx, rdi; DstBuf
0x14000a332  call    sprintf_s
0x14000a337  mov     r8, rdi; Src
0x14000a33a  mov     rdx, r13; SizeInBytes
  ... truncated ...
```
