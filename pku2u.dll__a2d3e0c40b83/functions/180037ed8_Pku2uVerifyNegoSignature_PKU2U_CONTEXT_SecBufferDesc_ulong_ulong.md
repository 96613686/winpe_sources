# Pku2uVerifyNegoSignature(_PKU2U_CONTEXT *,_SecBufferDesc *,ulong,ulong *)

- ea: `0x180037ed8`
- end: `0x180038289`
- name: `?Pku2uVerifyNegoSignature@@YAJPEAU_PKU2U_CONTEXT@@PEAU_SecBufferDesc@@KPEAK@Z`
- size: `945`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, struct _SecBufferDesc *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003754c`

## callees

- `0x1800210f0`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d9c`
- `0x18002b744`
- `0x180037ed8`
- `0x180038290`
- `0x180046010`

## import_xrefs

- `cryptdll!CDLocateCheckSum` at `0x18003807a`
- `cryptdll!CDLocateCheckSum` at `0x18003807a`

## string_xrefs

- `0x180037f99`: `onecore\ds\security\protocols\pku2u\negosupport.cxx`
- `0x18003822b`: `onecore\ds\security\protocols\pku2u\negosupport.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uVerifyNegoSignature(
        struct _PKU2U_CONTEXT *a1,
        struct _SecBufferDesc *a2,
        __int64 a3,
        unsigned int *a4)
{
  bool v4; // zf
  PSecBuffer pBuffers; // r9
  struct _SecBuffer *v9; // rdx
  unsigned int v10; // ecx
  struct _SecBuffer *v11; // r8
  int BufferType; // eax
  int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // edi
  PSecBuffer v17; // rcx
  __int64 cbBuffer; // rdx
  struct _WST_GSS_SIGNATURE_NEW *v19; // rdi
  int v20; // eax
  char v21; // r8
  __int64 i; // rdx
  char v23; // cl
  char v24; // al
  unsigned int *v26; // [rsp+28h] [rbp-71h]
  struct _CRYPTO_SYSTEM **v27; // [rsp+38h] [rbp-61h]
  __int64 v28; // [rsp+50h] [rbp-49h] BYREF
  __int64 v29; // [rsp+58h] [rbp-41h] BYREF
  int v30; // [rsp+60h] [rbp-39h] BYREF
  struct _WST_GSS_SIGNATURE_NEW *v31; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int64 v32; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v33[64]; // [rsp+80h] [rbp-19h] BYREF

  v4 = a2->cBuffers == 0;
  v29 = 0;
  v28 = 0;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  if ( v4 )
  {
LABEL_45:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)WPP_801de8da242a398af64deff044103c73_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\negosupport.cxx",
        252);
    v13 = -1073741811;
LABEL_49:
    if ( v28 && v29 )
      (*(void (__fastcall **)(__int64 *))(v29 + 40))(&v28);
  }
  else
  {
    pBuffers = a2->pBuffers;
    v9 = 0;
    v10 = 0;
    do
    {
      v11 = &pBuffers[v10];
      BufferType = v11->BufferType;
      if ( BufferType < 0 && (BufferType & 0x10000000) != 0 )
      {
        v13 = -2146893048;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_801de8da242a398af64deff044103c73_Traceguids);
          goto LABEL_49;
        }
        return (unsigned int)v13;
      }
      if ( (BufferType & 0xFFFFFFF) == 2 )
        v9 = &pBuffers[v10];
      ++v10;
    }
    while ( v10 < a2->cBuffers );
    if ( !v9 )
      goto LABEL_45;
    if ( (*((_DWORD *)a1 + 16) & 0x1000C) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)WPP_801de8da242a398af64deff044103c73_Traceguids,
          *((_DWORD *)a1 + 16),
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\negosupport.cxx",
          7);
      v13 = -1073741637;
      goto LABEL_49;
    }
    v13 = Pku2uVerifySignatureToken(
            a1,
            v9,
            (unsigned __int8)v11,
            (unsigned __int64)pBuffers,
            &v31,
            v26,
            &v30,
            v27,
            &v32);
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_49;
      v15 = 33;
LABEL_21:
      WPP_SF_d(v14[2], v15, WPP_801de8da242a398af64deff044103c73_Traceguids, (unsigned int)v13);
      goto LABEL_49;
    }
    v13 = CDLocateCheckSum((unsigned int)v30, &v29);
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_49;
      v15 = 34;
      goto LABEL_21;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v29 + 48))(
            *((_QWORD *)a1 + 30),
            *((unsigned int *)a1 + 58),
            (*((_DWORD *)a1 + 10) & 4) != 0 ? 25 : 23,
            &v28);
    if ( v13 < 0 )
      goto LABEL_49;
    v16 = 0;
    if ( a2->cBuffers )
    {
      do
      {
        v17 = a2->pBuffers;
        if ( (v17[v16].BufferType & 0xFFFFFFF) != 2 && (v17[v16].BufferType & 0x80000000) == 0 )
        {
          cbBuffer = v17[v16].cbBuffer;
          if ( (_DWORD)cbBuffer )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(v29 + 24))(v28, cbBuffer, v17[v16].pvBuffer);
            if ( v13 < 0 )
              goto LABEL_49;
          }
        }
      }
      while ( ++v16 < a2->cBuffers );
    }
    v19 = v31;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v29 + 24))(v28, 16, (char *)v31 - 2);
    if ( v13 < 0 )
      goto LABEL_49;
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(v29 + 32))(v28, v33);
    if ( v13 < 0 )
      goto LABEL_49;
    v20 = (*(__int64 (__fastcall **)(__int64 *))(v29 + 40))(&v28);
    v28 = 0;
    v13 = v20;
    if ( v20 >= 0 )
    {
      v21 = 0;
      for ( i = 0; i != 12; ++i )
      {
        v23 = *((_BYTE *)v19 + i + 14);
        v24 = v33[i];
        v21 |= v24 ^ v23;
      }
      if ( v21 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_801de8da242a398af64deff044103c73_Traceguids);
        v13 = -2146893041;
      }
      else if ( a4 )
      {
        *a4 = 0;
      }
      goto LABEL_49;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180037ed8  push    rbp
0x180037eda  push    rbx
0x180037edb  push    rsi
0x180037edc  push    rdi
0x180037edd  push    r14
0x180037edf  lea     rbp, [rsp-37h]
0x180037ee4  sub     rsp, 0D0h
0x180037eeb  mov     rax, cs:__security_cookie
0x180037ef2  xor     rax, rsp
0x180037ef5  mov     [rbp+57h+var_30], rax
0x180037ef9  cmp     dword ptr [rdx+4], 0
0x180037efd  mov     r14, r9
0x180037f00  mov     rsi, rdx
0x180037f03  mov     [rbp+57h+var_98], 0
0x180037f0b  mov     rdi, rcx
0x180037f0e  mov     [rbp+57h+var_A0], 0
0x180037f16  mov     [rbp+57h+var_88], 0
0x180037f1e  mov     [rbp+57h+var_90], 0
0x180037f25  mov     [rbp+57h+var_80], 0
0x180037f2d  jbe     loc_18003820E
0x180037f33  mov     r9, [rsi+8]; unsigned __int64
0x180037f37  xor     edx, edx
0x180037f39  xor     ecx, ecx
0x180037f3b  mov     r8d, ecx
0x180037f3e  shl     r8, 4
0x180037f42  add     r8, r9; unsigned __int8
0x180037f45  mov     eax, [r8+4]
0x180037f49  test    eax, eax
0x180037f4b  jns     short loc_180037F53
0x180037f4d  bt      eax, 1Ch
0x180037f51  jb      short loc_180037FCC
0x180037f53  and     eax, 0FFFFFFFh
0x180037f58  cmp     eax, 2
0x180037f5b  cmovz   rdx, r8; struct _SecBuffer *
0x180037f5f  inc     ecx
0x180037f61  cmp     ecx, [rsi+4]
0x180037f64  jb      short loc_180037F3B
0x180037f66  test    rdx, rdx
0x180037f69  jz      loc_18003820E
0x180037f6f  test    dword ptr [rdi+40h], 1000Ch
0x180037f76  jnz     loc_18003800C
0x180037f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f83  lea     rax, WPP_GLOBAL_Control
0x180037f8a  cmp     rcx, rax
0x180037f8d  jz      short loc_180037FC2
0x180037f8f  test    byte ptr [rcx+1Ch], 1
0x180037f93  jz      short loc_180037FC2
0x180037f95  mov     rcx, [rcx+10h]
0x180037f99  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\protocols\\pku2u"...
0x180037fa0  mov     dword ptr [rsp+0F0h+var_C8], 207h
0x180037fa8  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180037faf  mov     [rsp+0F0h+var_D0], r9
0x180037fb4  mov     edx, 20h ; ' '
0x180037fb9  mov     r9d, [rdi+40h]
0x180037fbd  call    WPP_SF_dsd
0x180037fc2  mov     ebx, 0C00000BBh
0x180037fc7  jmp     loc_180038250
0x180037fcc  mov     ebx, 80090308h
0x180037fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fd8  lea     rax, WPP_GLOBAL_Control
0x180037fdf  cmp     rcx, rax
0x180037fe2  jz      loc_18003826D
0x180037fe8  test    byte ptr [rcx+1Ch], 1
0x180037fec  jz      loc_18003826D
0x180037ff2  mov     rcx, [rcx+10h]
0x180037ff6  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180037ffd  mov     edx, 1Eh
0x180038002  call    WPP_SF_
0x180038007  jmp     loc_180038250
0x18003800c  lea     rax, [rbp+57h+var_80]
0x180038010  mov     rcx, rdi; struct _PKU2U_CONTEXT *
0x180038013  mov     [rsp+0F0h+var_B0], rax; unsigned __int64 *
0x180038018  lea     rax, [rbp+57h+var_90]
0x18003801c  mov     [rsp+0F0h+var_C0], rax; int *
0x180038021  lea     rax, [rbp+57h+var_88]
0x180038025  mov     [rsp+0F0h+var_D0], rax; struct _WST_GSS_SIGNATURE_NEW **
0x18003802a  call    ?Pku2uVerifySignatureToken@@YAJPEAU_PKU2U_CONTEXT@@PEAU_SecBuffer@@E_KPEAPEAU_WST_GSS_SIGNATURE_NEW@@PEAKPEAJPEAPEAU_CRYPTO_SYSTEM@@PEA_K@Z; Pku2uVerifySignatureToken(_PKU2U_CONTEXT *,_SecBuffer *,uchar,unsigned __int64,_WST_GSS_SIGNATURE_NEW * *,ulong *,long *,_CRYPTO_SYSTEM * *,unsigned __int64 *)
0x18003802f  mov     ebx, eax
0x180038031  test    eax, eax
0x180038033  jns     short loc_180038073
0x180038035  mov     rcx, cs:WPP_GLOBAL_Control
0x18003803c  lea     rax, WPP_GLOBAL_Control
0x180038043  cmp     rcx, rax
0x180038046  jz      loc_180038250
0x18003804c  test    byte ptr [rcx+1Ch], 1
0x180038050  jz      loc_180038250
0x180038056  mov     edx, 21h ; '!'
0x18003805b  mov     rcx, [rcx+10h]
0x18003805f  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180038066  mov     r9d, ebx
0x180038069  call    WPP_SF_d
0x18003806e  jmp     loc_180038250
0x180038073  mov     ecx, [rbp+57h+var_90]
0x180038076  lea     rdx, [rbp+57h+var_98]
0x18003807a  call    cs:__imp_CDLocateCheckSum
0x180038080  mov     ebx, eax
0x180038082  test    eax, eax
0x180038084  jns     short loc_1800380AE
0x180038086  mov     rcx, cs:WPP_GLOBAL_Control
0x18003808d  lea     rax, WPP_GLOBAL_Control
0x180038094  cmp     rcx, rax
0x180038097  jz      loc_180038250
0x18003809d  test    byte ptr [rcx+1Ch], 1
0x1800380a1  jz      loc_180038250
0x1800380a7  mov     edx, 22h ; '"'
0x1800380ac  jmp     short loc_18003805B
0x1800380ae  mov     eax, [rdi+28h]
0x1800380b1  lea     r9, [rbp+57h+var_A0]
0x1800380b5  mov     edx, [rdi+0E8h]
0x1800380bb  and     al, 4
0x1800380bd  mov     rcx, [rdi+0F0h]
0x1800380c4  neg     al
0x1800380c6  mov     rax, [rbp+57h+var_98]
0x1800380ca  sbb     r8d, r8d
0x1800380cd  and     r8d, 2
0x1800380d1  add     r8d, 17h
0x1800380d5  mov     rax, [rax+30h]
0x1800380d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380de  mov     ebx, eax
0x1800380e0  test    eax, eax
0x1800380e2  js      loc_180038250
0x1800380e8  xor     edi, edi
0x1800380ea  cmp     [rsi+4], edi
0x1800380ed  jbe     short loc_18003813D
0x1800380ef  mov     rcx, [rsi+8]
0x1800380f3  mov     r8d, edi
0x1800380f6  add     r8, r8
0x1800380f9  mov     edx, [rcx+r8*8+4]
0x1800380fe  mov     eax, edx
0x180038100  and     eax, 0FFFFFFFh
0x180038105  cmp     eax, 2
0x180038108  jz      short loc_180038136
0x18003810a  test    edx, edx
0x18003810c  js      short loc_180038136
0x18003810e  mov     edx, [rcx+r8*8]
0x180038112  test    edx, edx
0x180038114  jz      short loc_180038136
0x180038116  mov     rax, [rbp+57h+var_98]
0x18003811a  mov     r8, [rcx+r8*8+8]
0x18003811f  mov     rcx, [rbp+57h+var_A0]
0x180038123  mov     rax, [rax+18h]
0x180038127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003812c  mov     ebx, eax
0x18003812e  test    eax, eax
0x180038130  js      loc_180038250
0x180038136  inc     edi
0x180038138  cmp     edi, [rsi+4]
0x18003813b  jb      short loc_1800380EF
0x18003813d  mov     rax, [rbp+57h+var_98]
0x180038141  mov     edx, 10h
0x180038146  mov     rdi, [rbp+57h+var_88]
0x18003814a  mov     rcx, [rbp+57h+var_A0]
0x18003814e  mov     rax, [rax+18h]
0x180038152  lea     r8, [rdi-2]
0x180038156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003815b  mov     ebx, eax
0x18003815d  test    eax, eax
0x18003815f  js      loc_180038250
0x180038165  mov     rax, [rbp+57h+var_98]
0x180038169  lea     rdx, [rbp+57h+var_70]
0x18003816d  mov     rcx, [rbp+57h+var_A0]
0x180038171  mov     rax, [rax+20h]
0x180038175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003817a  mov     ebx, eax
0x18003817c  test    eax, eax
0x18003817e  js      loc_180038250
0x180038184  mov     rax, [rbp+57h+var_98]
0x180038188  lea     rcx, [rbp+57h+var_A0]
0x18003818c  mov     rax, [rax+28h]
0x180038190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038195  mov     [rbp+57h+var_A0], 0
0x18003819d  mov     ebx, eax
0x18003819f  test    eax, eax
0x1800381a1  js      loc_18003826D
0x1800381a7  xor     r8b, r8b
0x1800381aa  xor     edx, edx
0x1800381ac  mov     cl, [rdx+rdi+0Eh]
0x1800381b0  mov     al, [rbp+rdx+57h+var_70]
0x1800381b4  inc     rdx
0x1800381b7  xor     cl, al
0x1800381b9  or      r8b, cl
0x1800381bc  cmp     rdx, 0Ch
0x1800381c0  jnz     short loc_1800381AC
0x1800381c2  test    r8b, r8b
0x1800381c5  jnz     short loc_1800381D9
0x1800381c7  test    r14, r14
0x1800381ca  jz      loc_180038250
0x1800381d0  mov     dword ptr [r14], 0
0x1800381d7  jmp     short loc_180038250
0x1800381d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381e0  lea     rax, WPP_GLOBAL_Control
0x1800381e7  cmp     rcx, rax
0x1800381ea  jz      short loc_180038207
0x1800381ec  test    byte ptr [rcx+1Ch], 1
0x1800381f0  jz      short loc_180038207
0x1800381f2  mov     rcx, [rcx+10h]
0x1800381f6  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x1800381fd  mov     edx, 23h ; '#'
0x180038202  call    WPP_SF_
0x180038207  mov     ebx, 8009030Fh
0x18003820c  jmp     short loc_180038250
0x18003820e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038215  lea     rax, WPP_GLOBAL_Control
0x18003821c  cmp     rcx, rax
0x18003821f  jz      short loc_18003824B
0x180038221  test    byte ptr [rcx+1Ch], 1
0x180038225  jz      short loc_18003824B
0x180038227  mov     rcx, [rcx+10h]
0x18003822b  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\protocols\\pku2u"...
0x180038232  mov     edx, 1Fh
0x180038237  mov     dword ptr [rsp+0F0h+var_D0], 1FCh
0x18003823f  lea     r8, WPP_801de8da242a398af64deff044103c73_Traceguids
0x180038246  call    WPP_SF_sd
0x18003824b  mov     ebx, 0C000000Dh
0x180038250  cmp     [rbp+57h+var_A0], 0
0x180038255  jz      short loc_18003826D
0x180038257  mov     rax, [rbp+57h+var_98]
0x18003825b  test    rax, rax
0x18003825e  jz      short loc_18003826D
0x180038260  mov     rax, [rax+28h]
0x180038264  lea     rcx, [rbp+57h+var_A0]
0x180038268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003826d  mov     eax, ebx
0x18003826f  mov     rcx, [rbp+57h+var_30]
0x180038273  xor     rcx, rsp; StackCookie
0x180038276  call    __security_check_cookie
0x18003827b  add     rsp, 0D0h
0x180038282  pop     r14
0x180038284  pop     rdi
0x180038285  pop     rsi
0x180038286  pop     rbx
0x180038287  pop     rbp
0x180038288  retn
```
