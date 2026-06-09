# Pku2uMakeNegoSignature(_PKU2U_CONTEXT *,ulong,_SecBufferDesc *,ulong)

- ea: `0x1800379d4`
- end: `0x180037d72`
- name: `?Pku2uMakeNegoSignature@@YAJPEAU_PKU2U_CONTEXT@@KPEAU_SecBufferDesc@@K@Z`
- size: `926`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, unsigned int, struct _SecBufferDesc *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003754c`

## callees

- `0x1800210f0`
- `0x180023cb8`
- `0x180023d9c`
- `0x18002b408`
- `0x18002b744`
- `0x1800379d4`
- `0x180037d78`
- `0x180046010`

## import_xrefs

- `cryptdll!CDLocateCSystem` at `0x180037bb0`
- `cryptdll!CDLocateCSystem` at `0x180037bb0`
- `cryptdll!CDLocateCheckSum` at `0x180037b5c`
- `cryptdll!CDLocateCheckSum` at `0x180037b5c`

## string_xrefs

- `0x180037a9d`: `onecore\ds\security\protocols\pku2u\negosupport.cxx`
- `0x180037d0b`: `onecore\ds\security\protocols\pku2u\negosupport.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uMakeNegoSignature(struct _PKU2U_CONTEXT *a1, __int64 a2, struct _SecBufferDesc *a3)
{
  bool v3; // zf
  PSecBuffer pBuffers; // r9
  struct _SecBuffer *v7; // r8
  unsigned int v8; // ecx
  struct _SecBuffer *v9; // rdx
  int BufferType; // eax
  int v11; // r10d
  int SignatureToken; // ebx
  int v13; // eax
  unsigned int v14; // esi
  unsigned int v15; // edi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  int v19; // edi
  PSecBuffer v20; // rcx
  __int64 cbBuffer; // rdx
  struct _WST_GSS_SIGNATURE_NEW *v22; // rdi
  int v23; // eax
  unsigned __int8 v25; // [rsp+20h] [rbp-79h]
  unsigned __int64 v26; // [rsp+28h] [rbp-71h]
  unsigned int v27; // [rsp+30h] [rbp-69h]
  __int64 v28; // [rsp+50h] [rbp-49h] BYREF
  __int64 v29; // [rsp+58h] [rbp-41h] BYREF
  struct _WST_GSS_SIGNATURE_NEW *v30; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp-31h] BYREF
  __int64 v32; // [rsp+70h] [rbp-29h] BYREF
  __int64 v33; // [rsp+80h] [rbp-19h] BYREF
  int v34; // [rsp+88h] [rbp-11h]

  v3 = a3->cBuffers == 0;
  v29 = 0;
  v32 = 0;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  if ( v3 )
  {
LABEL_42:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)WPP_801de8da242a398af64deff044103c73_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\negosupport.cxx",
        231);
    SignatureToken = -1073741811;
  }
  else
  {
    pBuffers = a3->pBuffers;
    v7 = 0;
    v8 = 0;
    do
    {
      v9 = &pBuffers[v8];
      BufferType = v9->BufferType;
      if ( BufferType < 0 && (BufferType & 0x10000000) != 0 )
      {
        SignatureToken = -2146893048;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_801de8da242a398af64deff044103c73_Traceguids);
          goto LABEL_46;
        }
        return (unsigned int)SignatureToken;
      }
      if ( (BufferType & 0xFFFFFFF) == 2 )
        v7 = &pBuffers[v8];
      ++v8;
    }
    while ( v8 < a3->cBuffers );
    if ( !v7 )
      goto LABEL_42;
    v11 = *((_DWORD *)a1 + 16);
    if ( (v11 & 0x1000C) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)WPP_801de8da242a398af64deff044103c73_Traceguids,
          v11,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\negosupport.cxx",
          242);
      goto LABEL_13;
    }
    v13 = *((_DWORD *)a1 + 56);
    if ( v13 == 17 )
    {
      v14 = -148;
      v15 = 15;
    }
    else
    {
      if ( v13 != 18 )
      {
LABEL_13:
        SignatureToken = -1073741637;
        goto LABEL_46;
      }
      v14 = -149;
      v15 = 16;
    }
    SignatureToken = Pku2uMakeSignatureToken(
                       a1,
                       (unsigned int)v9,
                       v7,
                       (unsigned int)pBuffers,
                       v25,
                       v26,
                       v27,
                       &v30,
                       &v31);
    if ( SignatureToken >= 0 )
    {
      SignatureToken = CDLocateCheckSum(v15, &v29);
      if ( SignatureToken >= 0 )
      {
        SignatureToken = CDLocateCSystem(v14, &v32);
        if ( SignatureToken >= 0 )
        {
          SignatureToken = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v29 + 48))(
                             *((_QWORD *)a1 + 30),
                             *((unsigned int *)a1 + 58),
                             (*((_DWORD *)a1 + 10) & 2) != 0 ? 25 : 23,
                             &v28);
          if ( SignatureToken < 0 )
            goto LABEL_46;
          v19 = 0;
          if ( a3->cBuffers )
          {
            while ( 1 )
            {
              v20 = a3->pBuffers;
              if ( (v20[v19].BufferType & 0xFFFFFFF) != 2 && (v20[v19].BufferType & 0x80000000) == 0 )
              {
                cbBuffer = v20[v19].cbBuffer;
                if ( (_DWORD)cbBuffer )
                {
                  SignatureToken = (*(__int64 (__fastcall **)(__int64, __int64, void *))(v29 + 24))(
                                     v28,
                                     cbBuffer,
                                     v20[v19].pvBuffer);
                  if ( SignatureToken < 0 )
                    break;
                }
              }
              if ( ++v19 >= a3->cBuffers )
                goto LABEL_38;
            }
          }
          else
          {
LABEL_38:
            v22 = v30;
            SignatureToken = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v29 + 24))(v28, 16, (char *)v30 - 2);
            if ( SignatureToken >= 0 )
            {
              SignatureToken = (*(__int64 (__fastcall **)(__int64, __int64 *))(v29 + 32))(v28, &v33);
              if ( SignatureToken >= 0 )
              {
                v23 = (*(__int64 (__fastcall **)(__int64 *))(v29 + 40))(&v28);
                v28 = 0;
                SignatureToken = v23;
                if ( v23 < 0 )
                  return (unsigned int)SignatureToken;
                *(_QWORD *)((char *)v22 + 14) = v33;
                *(_DWORD *)((char *)v22 + 22) = v34;
              }
            }
          }
        }
        else
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 40;
            v18 = v14;
            goto LABEL_26;
          }
        }
      }
      else
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 39;
          v18 = v15;
LABEL_26:
          WPP_SF_dd(v16[2], v17, WPP_801de8da242a398af64deff044103c73_Traceguids, v18, SignatureToken);
        }
      }
    }
  }
LABEL_46:
  if ( v28 && v29 )
    (*(void (__fastcall **)(__int64 *))(v29 + 40))(&v28);
  return (unsigned int)SignatureToken;
}

```

## disassembly

```asm
0x1800379d4  mov     [rsp-8+arg_8], rbx
0x1800379d9  push    rbp
0x1800379da  push    rsi
0x1800379db  push    rdi
0x1800379dc  push    r14
0x1800379de  push    r15
0x1800379e0  lea     rbp, [rsp-37h]
0x1800379e5  sub     rsp, 0D0h
0x1800379ec  mov     rax, cs:__security_cookie
0x1800379f3  xor     rax, rsp
0x1800379f6  mov     [rbp+57h+var_30], rax
0x1800379fa  cmp     dword ptr [r8+4], 0
0x1800379ff  mov     r14, r8
0x180037a02  mov     r15, rcx
0x180037a05  mov     [rbp+57h+var_98], 0
0x180037a0d  mov     [rbp+57h+var_80], 0
0x180037a15  mov     [rbp+57h+var_A0], 0
0x180037a1d  mov     [rbp+57h+var_90], 0
0x180037a25  mov     [rbp+57h+var_88], 0
0x180037a2d  jbe     loc_180037CEE
0x180037a33  mov     r9, [r14+8]; unsigned int
0x180037a37  xor     r8d, r8d
0x180037a3a  xor     ecx, ecx
0x180037a3c  mov     edx, ecx
0x180037a3e  shl     rdx, 4
0x180037a42  add     rdx, r9; unsigned int
0x180037a45  mov     eax, [rdx+4]
0x180037a48  test    eax, eax
0x180037a4a  jns     short loc_180037A52
0x180037a4c  bt      eax, 1Ch
0x180037a50  jb      short loc_180037ACF
0x180037a52  and     eax, 0FFFFFFFh
0x180037a57  cmp     eax, 2
0x180037a5a  cmovz   r8, rdx; struct _SecBuffer *
0x180037a5e  inc     ecx
0x180037a60  cmp     ecx, [r14+4]
0x180037a64  jb      short loc_180037A3C
0x180037a66  test    r8, r8
0x180037a69  jz      loc_180037CEE
0x180037a6f  mov     r10d, [r15+40h]
0x180037a73  test    r10d, 1000Ch
0x180037a7a  jnz     loc_180037B0F
0x180037a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a87  lea     rax, WPP_GLOBAL_Control
0x180037a8e  cmp     rcx, rax
0x180037a91  jz      short loc_180037AC5
0x180037a93  test    byte ptr [rcx+1Ch], 1
0x180037a97  jz      short loc_180037AC5
0x180037a99  mov     rcx, [rcx+10h]
0x180037a9d  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\protocols\\pku2u"...
0x180037aa4  mov     dword ptr [rsp+0F0h+var_C8], 2F2h
0x180037aac  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180037ab3  mov     [rsp+0F0h+var_D0], r9
0x180037ab8  mov     edx, 26h ; '&'
0x180037abd  mov     r9d, r10d
0x180037ac0  call    WPP_SF_dsd
0x180037ac5  mov     ebx, 0C00000BBh
0x180037aca  jmp     loc_180037D30
0x180037acf  mov     ebx, 80090308h
0x180037ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180037adb  lea     rax, WPP_GLOBAL_Control
0x180037ae2  cmp     rcx, rax
0x180037ae5  jz      loc_180037D4D
0x180037aeb  test    byte ptr [rcx+1Ch], 1
0x180037aef  jz      loc_180037D4D
0x180037af5  mov     rcx, [rcx+10h]
0x180037af9  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180037b00  mov     edx, 24h ; '$'
0x180037b05  call    WPP_SF_
0x180037b0a  jmp     loc_180037D30
0x180037b0f  mov     eax, [r15+0E0h]
0x180037b16  cmp     eax, 11h
0x180037b19  jnz     short loc_180037B25
0x180037b1b  mov     esi, 0FFFFFF6Ch
0x180037b20  lea     edi, [rax-2]
0x180037b23  jmp     short loc_180037B32
0x180037b25  cmp     eax, 12h
0x180037b28  jnz     short loc_180037AC5
0x180037b2a  mov     esi, 0FFFFFF6Bh
0x180037b2f  lea     edi, [rax-2]
0x180037b32  lea     rax, [rbp+57h+var_88]
0x180037b36  mov     rcx, r15; struct _PKU2U_CONTEXT *
0x180037b39  mov     [rsp+0F0h+var_B0], rax; unsigned __int64 *
0x180037b3e  lea     rax, [rbp+57h+var_90]
0x180037b42  mov     [rsp+0F0h+var_B8], rax; struct _WST_GSS_SIGNATURE_NEW **
0x180037b47  call    ?Pku2uMakeSignatureToken@@YAJPEAU_PKU2U_CONTEXT@@KPEAU_SecBuffer@@KE_KKPEAPEAU_WST_GSS_SIGNATURE_NEW@@PEA_K@Z; Pku2uMakeSignatureToken(_PKU2U_CONTEXT *,ulong,_SecBuffer *,ulong,uchar,unsigned __int64,ulong,_WST_GSS_SIGNATURE_NEW * *,unsigned __int64 *)
0x180037b4c  mov     ebx, eax
0x180037b4e  test    eax, eax
0x180037b50  js      loc_180037D30
0x180037b56  lea     rdx, [rbp+57h+var_98]
0x180037b5a  mov     ecx, edi
0x180037b5c  call    cs:__imp_CDLocateCheckSum
0x180037b62  mov     ebx, eax
0x180037b64  test    eax, eax
0x180037b66  jns     short loc_180037BAA
0x180037b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b6f  lea     rax, WPP_GLOBAL_Control
0x180037b76  cmp     rcx, rax
0x180037b79  jz      loc_180037D30
0x180037b7f  test    byte ptr [rcx+1Ch], 1
0x180037b83  jz      loc_180037D30
0x180037b89  mov     edx, 27h ; '''
0x180037b8e  mov     r9d, edi
0x180037b91  mov     rcx, [rcx+10h]
0x180037b95  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180037b9c  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180037ba0  call    WPP_SF_dd
0x180037ba5  jmp     loc_180037D30
0x180037baa  lea     rdx, [rbp+57h+var_80]
0x180037bae  mov     ecx, esi
0x180037bb0  call    cs:__imp_CDLocateCSystem
0x180037bb6  mov     ebx, eax
0x180037bb8  test    eax, eax
0x180037bba  jns     short loc_180037BE7
0x180037bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bc3  lea     rax, WPP_GLOBAL_Control
0x180037bca  cmp     rcx, rax
0x180037bcd  jz      loc_180037D30
0x180037bd3  test    byte ptr [rcx+1Ch], 1
0x180037bd7  jz      loc_180037D30
0x180037bdd  mov     edx, 28h ; '('
0x180037be2  mov     r9d, esi
0x180037be5  jmp     short loc_180037B91
0x180037be7  mov     eax, [r15+28h]
0x180037beb  lea     r9, [rbp+57h+var_A0]
0x180037bef  mov     edx, [r15+0E8h]
0x180037bf6  and     al, 2
0x180037bf8  mov     rcx, [r15+0F0h]
0x180037bff  neg     al
0x180037c01  mov     rax, [rbp+57h+var_98]
0x180037c05  sbb     r8d, r8d
0x180037c08  and     r8d, 2
0x180037c0c  add     r8d, 17h
0x180037c10  mov     rax, [rax+30h]
0x180037c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c19  mov     ebx, eax
0x180037c1b  test    eax, eax
0x180037c1d  js      loc_180037D30
0x180037c23  xor     edi, edi
0x180037c25  cmp     [r14+4], edi
0x180037c29  jbe     short loc_180037C7A
0x180037c2b  mov     rcx, [r14+8]
0x180037c2f  mov     r8d, edi
0x180037c32  add     r8, r8
0x180037c35  mov     edx, [rcx+r8*8+4]
0x180037c3a  mov     eax, edx
0x180037c3c  and     eax, 0FFFFFFFh
0x180037c41  cmp     eax, 2
0x180037c44  jz      short loc_180037C72
0x180037c46  test    edx, edx
0x180037c48  js      short loc_180037C72
0x180037c4a  mov     edx, [rcx+r8*8]
0x180037c4e  test    edx, edx
0x180037c50  jz      short loc_180037C72
0x180037c52  mov     rax, [rbp+57h+var_98]
0x180037c56  mov     r8, [rcx+r8*8+8]
0x180037c5b  mov     rcx, [rbp+57h+var_A0]
0x180037c5f  mov     rax, [rax+18h]
0x180037c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c68  mov     ebx, eax
0x180037c6a  test    eax, eax
0x180037c6c  js      loc_180037D30
0x180037c72  inc     edi
0x180037c74  cmp     edi, [r14+4]
0x180037c78  jb      short loc_180037C2B
0x180037c7a  mov     rax, [rbp+57h+var_98]
0x180037c7e  mov     edx, 10h
0x180037c83  mov     rdi, [rbp+57h+var_90]
0x180037c87  mov     rcx, [rbp+57h+var_A0]
0x180037c8b  mov     rax, [rax+18h]
0x180037c8f  lea     r8, [rdi-2]
0x180037c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c98  mov     ebx, eax
0x180037c9a  test    eax, eax
0x180037c9c  js      loc_180037D30
0x180037ca2  mov     rax, [rbp+57h+var_98]
0x180037ca6  lea     rdx, [rbp+57h+var_70]
0x180037caa  mov     rcx, [rbp+57h+var_A0]
0x180037cae  mov     rax, [rax+20h]
0x180037cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cb7  mov     ebx, eax
0x180037cb9  test    eax, eax
0x180037cbb  js      short loc_180037D30
0x180037cbd  mov     rax, [rbp+57h+var_98]
0x180037cc1  lea     rcx, [rbp+57h+var_A0]
0x180037cc5  mov     rax, [rax+28h]
0x180037cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cce  mov     [rbp+57h+var_A0], 0
0x180037cd6  mov     ebx, eax
0x180037cd8  test    eax, eax
0x180037cda  js      short loc_180037D4D
0x180037cdc  movsd   xmm0, [rbp+57h+var_70]
0x180037ce1  movsd   qword ptr [rdi+0Eh], xmm0
0x180037ce6  mov     eax, [rbp+57h+var_68]
0x180037ce9  mov     [rdi+16h], eax
0x180037cec  jmp     short loc_180037D30
0x180037cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180037cf5  lea     rax, WPP_GLOBAL_Control
0x180037cfc  cmp     rcx, rax
0x180037cff  jz      short loc_180037D2B
0x180037d01  test    byte ptr [rcx+1Ch], 1
0x180037d05  jz      short loc_180037D2B
0x180037d07  mov     rcx, [rcx+10h]
0x180037d0b  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\protocols\\pku2u"...
0x180037d12  mov     edx, 25h ; '%'
0x180037d17  mov     dword ptr [rsp+0F0h+var_D0], 2E7h
0x180037d1f  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180037d26  call    WPP_SF_sd
0x180037d2b  mov     ebx, 0C000000Dh
0x180037d30  cmp     [rbp+57h+var_A0], 0
0x180037d35  jz      short loc_180037D4D
0x180037d37  mov     rax, [rbp+57h+var_98]
0x180037d3b  test    rax, rax
0x180037d3e  jz      short loc_180037D4D
0x180037d40  mov     rax, [rax+28h]
0x180037d44  lea     rcx, [rbp+57h+var_A0]
0x180037d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d4d  mov     eax, ebx
0x180037d4f  mov     rcx, [rbp+57h+var_30]
0x180037d53  xor     rcx, rsp; StackCookie
0x180037d56  call    __security_check_cookie
0x180037d5b  mov     rbx, [rsp+0F0h+arg_8]
0x180037d63  add     rsp, 0D0h
0x180037d6a  pop     r15
0x180037d6c  pop     r14
0x180037d6e  pop     rdi
0x180037d6f  pop     rsi
0x180037d70  pop     rbp
0x180037d71  retn
```
