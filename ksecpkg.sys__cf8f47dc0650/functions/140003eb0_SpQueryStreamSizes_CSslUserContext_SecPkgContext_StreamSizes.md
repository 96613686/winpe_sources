# SpQueryStreamSizes(CSslUserContext *,_SecPkgContext_StreamSizes *)

- ea: `0x140003eb0`
- end: `0x140004254`
- name: `?SpQueryStreamSizes@@YAJPEAUCSslUserContext@@PEAU_SecPkgContext_StreamSizes@@@Z`
- size: `932`
- prototype: `__int64 __fastcall(struct CSslUserContext *, struct _SecPkgContext_StreamSizes *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14002f880`

## callees

- `0x140003eb0`
- `0x140010160`
- `0x1400105c0`

## import_xrefs

- `cng!SslLookupCipherSuiteInfo` at `0x140003f6a`
- `cng!SslLookupCipherSuiteInfo` at `0x140003f6a`
- `cng!SslLookupCipherLengths` at `0x140004005`
- `cng!SslLookupCipherLengths` at `0x140004005`

## pseudocode

```c
__int64 __fastcall SpQueryStreamSizes(struct CSslUserContext *a1, struct _SecPkgContext_StreamSizes *a2)
{
  int v2; // ebx
  unsigned int v5; // ebp
  unsigned int v6; // r14d
  __int64 v7; // r12
  __int64 v8; // rdx
  __int64 result; // rax
  unsigned int v10; // r12d
  int v11; // r14d
  int v12; // ebp
  __int64 v13; // rdx
  unsigned int v14; // edx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // edx
  unsigned int v18; // [rsp+40h] [rbp-328h]
  unsigned int v19; // [rsp+44h] [rbp-324h]
  __int64 v20; // [rsp+48h] [rbp-320h]
  __int128 v21; // [rsp+50h] [rbp-318h] BYREF
  int v22; // [rsp+60h] [rbp-308h]
  _DWORD v23[172]; // [rsp+70h] [rbp-2F8h] BYREF

  v2 = *((_DWORD *)a1 + 6);
  v5 = *((_DWORD *)a1 + 15);
  v6 = *((_DWORD *)a1 + 14);
  v7 = *((_QWORD *)a1 + 11);
  v20 = v7;
  v18 = v5;
  v19 = v6;
  memset(v23, 0, 0x2A4u);
  if ( (v2 & 0xF0000) != 0 && (v2 & 0x3FFC) != 0 )
  {
    v8 = 0;
  }
  else if ( (v2 & 0xC0000) != 0 )
  {
    v8 = 65277;
  }
  else if ( (v2 & 0x30000) != 0 )
  {
    v8 = 65279;
  }
  else if ( (v2 & 0x3000) != 0 )
  {
    v8 = 772;
  }
  else if ( (v2 & 0xC00) != 0 )
  {
    v8 = 771;
  }
  else if ( (v2 & 0x300) != 0 )
  {
    v8 = 770;
  }
  else if ( (v2 & 0xC0) != 0 )
  {
    v8 = 769;
  }
  else if ( (v2 & 0x30) != 0 )
  {
    v8 = 768;
  }
  else
  {
    v8 = (v2 & 0xC) != 0 ? 2 : 0;
  }
  result = SslLookupCipherSuiteInfo(v7, v8, v6, v5, v23, 0);
  if ( !(_DWORD)result )
  {
    v10 = v23[68];
    v11 = v23[68];
    v12 = v23[101] >> 3;
    if ( v23[68] <= 1u )
      v11 = 0;
    if ( (v2 & 0x3F00) != 0 )
    {
      v22 = 0;
      v21 = 0;
      if ( (v2 & 0xF0000) != 0 && (v2 & 0x3FFC) != 0 )
      {
        v13 = 0;
      }
      else if ( (v2 & 0xC0000) != 0 )
      {
        v13 = 65277;
      }
      else if ( (v2 & 0x30000) != 0 )
      {
        v13 = 65279;
      }
      else if ( (v2 & 0x3000) != 0 )
      {
        v13 = 772;
      }
      else if ( (v2 & 0xC00) != 0 )
      {
        v13 = 771;
      }
      else if ( (v2 & 0x300) != 0 )
      {
        v13 = 770;
      }
      else if ( (v2 & 0xC0) != 0 )
      {
        v13 = 769;
      }
      else if ( (v2 & 0x30) != 0 )
      {
        v13 = 768;
      }
      else
      {
        v13 = (v2 & 0xC) != 0 ? 2 : 0;
      }
      if ( !(unsigned int)SslLookupCipherLengths(v20, v13, v19, v18, &v21, 20, 0) )
      {
        v12 = DWORD2(v21);
        v11 = HIDWORD(v21);
      }
    }
    a2->cbHeader = 0;
    v14 = 0;
    v15 = *((_DWORD *)a1 + 6);
    if ( v15 == 0x40000 )
      goto LABEL_18;
    if ( v15 > 0x400 )
    {
      if ( v15 > 0x10000 )
      {
        if ( v15 != 0x20000 && v15 != 0x80000 )
          goto LABEL_69;
      }
      else if ( v15 != 0x10000 && v15 != 2048 && v15 != 4096 && v15 != 0x2000 )
      {
        goto LABEL_69;
      }
    }
    else if ( v15 != 1024 )
    {
      if ( v15 <= 0x80 )
      {
        if ( v15 == 128 || v15 == 16 || v15 == 32 || v15 == 64 )
        {
          v14 = *((_DWORD *)a1 + 18);
          a2->cbHeader = v14;
          goto LABEL_18;
        }
LABEL_69:
        a2->cbMaximumMessage = 0x4000;
        a2->cbTrailer = 0;
LABEL_22:
        a2->cbBlockSize = v10;
        result = 0;
        a2->cBuffers = 4;
        return result;
      }
      if ( v15 != 256 && v15 != 512 )
        goto LABEL_69;
    }
LABEL_18:
    a2->cbTrailer = v11 + v12;
    if ( (v2 & 0xF0000) != 0 )
      v16 = *((unsigned __int16 *)a1 + 68);
    else
      v16 = 0x4000;
    a2->cbMaximumMessage = v16;
    v17 = *((_DWORD *)a1 + 16) + *((_DWORD *)a1 + 17) + v14;
    a2->cbHeader = v17;
    if ( (*((_DWORD *)a1 + 6) & 0x3000) != 0 )
      a2->cbTrailer = v12 + v11 + v17 + v11 + v12 + 7;
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x140003eb0  mov     [rsp+arg_10], rbx
0x140003eb5  push    rbp
0x140003eb6  push    rsi
0x140003eb7  push    rdi
0x140003eb8  push    r12
0x140003eba  push    r13
0x140003ebc  push    r14
0x140003ebe  push    r15
0x140003ec0  sub     rsp, 330h
0x140003ec7  mov     rax, cs:__security_cookie
0x140003ece  xor     rax, rsp
0x140003ed1  mov     [rsp+368h+var_48], rax
0x140003ed9  mov     ebx, [rcx+18h]
0x140003edc  mov     r15, rdx
0x140003edf  mov     esi, ebx
0x140003ee1  mov     rdi, rcx
0x140003ee4  and     esi, 0F0000h
0x140003eea  jnz     loc_1400040AB
0x140003ef0  xor     r13b, r13b
0x140003ef3  mov     ebp, [rcx+3Ch]
0x140003ef6  xor     edx, edx; Val
0x140003ef8  mov     r14d, [rcx+38h]
0x140003efc  mov     r8d, 2A4h; Size
0x140003f02  mov     r12, [rcx+58h]
0x140003f06  lea     rcx, [rsp+368h+var_2F8]; void *
0x140003f0b  mov     [rsp+368h+var_320], r12
0x140003f10  mov     [rsp+368h+var_328], ebp
0x140003f14  mov     [rsp+368h+var_324], r14d
0x140003f19  call    memset
0x140003f1e  test    esi, esi
0x140003f20  jnz     loc_1400040B3
0x140003f26  test    ebx, 0C0000h
0x140003f2c  jnz     loc_1400040C6
0x140003f32  test    ebx, 30000h
0x140003f38  jnz     loc_1400040D0
0x140003f3e  test    ebx, 3000h
0x140003f44  jz      loc_1400040DA
0x140003f4a  mov     edx, 304h
0x140003f4f  lea     rax, [rsp+368h+var_2F8]
0x140003f54  mov     [rsp+368h+var_340], 0
0x140003f5c  mov     r9d, ebp
0x140003f5f  mov     [rsp+368h+var_348], rax
0x140003f64  mov     r8d, r14d
0x140003f67  mov     rcx, r12
0x140003f6a  call    cs:__imp_SslLookupCipherSuiteInfo
0x140003f71  nop     dword ptr [rax+rax+00h]
0x140003f76  test    eax, eax
0x140003f78  jnz     loc_14000407F
0x140003f7e  mov     r12d, [rsp+368h+var_1E8]
0x140003f86  mov     r14d, r12d
0x140003f89  mov     ebp, [rsp+368h+var_164]
0x140003f90  shr     ebp, 3
0x140003f93  cmp     r12d, 1
0x140003f97  cmovbe  r14d, eax
0x140003f9b  test    ebx, 3F00h
0x140003fa1  jz      short loc_14000401E
0x140003fa3  mov     [rsp+368h+var_308], eax
0x140003fa7  xorps   xmm0, xmm0
0x140003faa  movups  [rsp+368h+var_318], xmm0
0x140003faf  test    esi, esi
0x140003fb1  jnz     loc_14000412D
0x140003fb7  test    ebx, 0C0000h
0x140003fbd  jnz     loc_140004140
0x140003fc3  test    ebx, 30000h
0x140003fc9  jnz     loc_14000414A
0x140003fcf  test    ebx, 3000h
0x140003fd5  jz      loc_140004154
0x140003fdb  mov     edx, 304h
0x140003fe0  mov     r9d, [rsp+368h+var_328]
0x140003fe5  mov     r8d, [rsp+368h+var_324]
0x140003fea  mov     rcx, [rsp+368h+var_320]
0x140003fef  mov     [rsp+368h+var_338], eax
0x140003ff3  lea     rax, [rsp+368h+var_318]
0x140003ff8  mov     [rsp+368h+var_340], 14h
0x140004000  mov     [rsp+368h+var_348], rax
0x140004005  call    cs:__imp_SslLookupCipherLengths
0x14000400c  nop     dword ptr [rax+rax+00h]
0x140004011  test    eax, eax
0x140004013  jnz     short loc_14000401E
0x140004015  mov     ebp, dword ptr [rsp+368h+var_318+8]
0x140004019  mov     r14d, dword ptr [rsp+368h+var_318+0Ch]
0x14000401e  mov     dword ptr [r15], 0
0x140004025  xor     edx, edx
0x140004027  mov     eax, [rdi+18h]
0x14000402a  cmp     eax, 40000h
0x14000402f  jnz     loc_1400041A5
0x140004035  lea     ecx, [r14+rbp]
0x140004039  mov     [r15+4], ecx
0x14000403d  test    r13b, r13b
0x140004040  jnz     loc_140004248
0x140004046  mov     eax, 4000h
0x14000404b  mov     [r15+8], eax
0x14000404f  mov     eax, [rdi+44h]
0x140004052  add     eax, [rdi+40h]
0x140004055  add     edx, eax
0x140004057  mov     [r15], edx
0x14000405a  test    dword ptr [rdi+18h], 3000h
0x140004061  jz      short loc_140004071
0x140004063  lea     eax, [rcx+7]
0x140004066  add     eax, edx
0x140004068  add     eax, r14d
0x14000406b  add     eax, ebp
0x14000406d  mov     [r15+4], eax
0x140004071  mov     [r15+10h], r12d
0x140004075  xor     eax, eax
0x140004077  mov     dword ptr [r15+0Ch], 4
0x14000407f  mov     rcx, [rsp+368h+var_48]
0x140004087  xor     rcx, rsp; StackCookie
0x14000408a  call    __security_check_cookie
0x14000408f  mov     rbx, [rsp+368h+arg_10]
0x140004097  add     rsp, 330h
0x14000409e  pop     r15
0x1400040a0  pop     r14
0x1400040a2  pop     r13
0x1400040a4  pop     r12
0x1400040a6  pop     rdi
0x1400040a7  pop     rsi
0x1400040a8  pop     rbp
0x1400040a9  retn
0x1400040ab  mov     r13b, 1
0x1400040ae  jmp     loc_140003EF3
0x1400040b3  test    ebx, 3FFCh
0x1400040b9  jz      loc_140003F26
0x1400040bf  xor     edx, edx
0x1400040c1  jmp     loc_140003F4F
0x1400040c6  mov     edx, 0FEFDh
0x1400040cb  jmp     loc_140003F4F
0x1400040d0  mov     edx, 0FEFFh
0x1400040d5  jmp     loc_140003F4F
0x1400040da  test    ebx, 0C00h
0x1400040e0  jz      short loc_1400040EC
0x1400040e2  mov     edx, 303h
0x1400040e7  jmp     loc_140003F4F
0x1400040ec  test    ebx, 300h
0x1400040f2  jz      short loc_1400040FE
0x1400040f4  mov     edx, 302h
0x1400040f9  jmp     loc_140003F4F
0x1400040fe  test    bl, 0C0h
0x140004101  jz      short loc_14000410D
0x140004103  mov     edx, 301h
0x140004108  jmp     loc_140003F4F
0x14000410d  test    bl, 30h
0x140004110  jz      short loc_14000411C
0x140004112  mov     edx, 300h
0x140004117  jmp     loc_140003F4F
0x14000411c  movzx   eax, bl
0x14000411f  and     al, 0Ch
0x140004121  neg     al
0x140004123  sbb     edx, edx
0x140004125  and     edx, 2
0x140004128  jmp     loc_140003F4F
0x14000412d  test    ebx, 3FFCh
0x140004133  jz      loc_140003FB7
0x140004139  xor     edx, edx
0x14000413b  jmp     loc_140003FE0
0x140004140  mov     edx, 0FEFDh
0x140004145  jmp     loc_140003FE0
0x14000414a  mov     edx, 0FEFFh
0x14000414f  jmp     loc_140003FE0
0x140004154  test    ebx, 0C00h
0x14000415a  jz      short loc_140004166
0x14000415c  mov     edx, 303h
0x140004161  jmp     loc_140003FE0
0x140004166  test    ebx, 300h
0x14000416c  jz      short loc_140004178
0x14000416e  mov     edx, 302h
0x140004173  jmp     loc_140003FE0
0x140004178  test    bl, 0C0h
0x14000417b  jz      short loc_140004187
0x14000417d  mov     edx, 301h
0x140004182  jmp     loc_140003FE0
0x140004187  test    bl, 30h
0x14000418a  jz      short loc_140004196
0x14000418c  mov     edx, 300h
0x140004191  jmp     loc_140003FE0
0x140004196  and     bl, 0Ch
0x140004199  neg     bl
0x14000419b  sbb     edx, edx
0x14000419d  and     edx, 2
0x1400041a0  jmp     loc_140003FE0
0x1400041a5  cmp     eax, 400h
0x1400041aa  ja      short loc_1400041ED
0x1400041ac  jz      loc_140004035
0x1400041b2  cmp     eax, 80h
0x1400041b7  ja      short loc_1400041D5
0x1400041b9  jz      short loc_1400041CA
0x1400041bb  cmp     eax, 10h
0x1400041be  jz      short loc_1400041CA
0x1400041c0  cmp     eax, 20h ; ' '
0x1400041c3  jz      short loc_1400041CA
0x1400041c5  cmp     eax, 40h ; '@'
0x1400041c8  jnz     short loc_140004233
0x1400041ca  mov     edx, [rdi+48h]
0x1400041cd  mov     [r15], edx
0x1400041d0  jmp     loc_140004035
0x1400041d5  cmp     eax, 100h
0x1400041da  jz      loc_140004035
0x1400041e0  cmp     eax, 200h
0x1400041e5  jz      loc_140004035
0x1400041eb  jmp     short loc_140004233
0x1400041ed  cmp     eax, 10000h
0x1400041f2  ja      short loc_14000421D
0x1400041f4  jz      loc_140004035
0x1400041fa  cmp     eax, 800h
0x1400041ff  jz      loc_140004035
0x140004205  cmp     eax, 1000h
0x14000420a  jz      loc_140004035
0x140004210  cmp     eax, 2000h
0x140004215  jz      loc_140004035
0x14000421b  jmp     short loc_140004233
0x14000421d  cmp     eax, 20000h
0x140004222  jz      loc_140004035
0x140004228  cmp     eax, 80000h
0x14000422d  jz      loc_140004035
0x140004233  mov     dword ptr [r15+8], 4000h
0x14000423b  mov     dword ptr [r15+4], 0
0x140004243  jmp     loc_140004071
0x140004248  movzx   eax, word ptr [rdi+88h]
0x14000424f  jmp     loc_14000404B
```
