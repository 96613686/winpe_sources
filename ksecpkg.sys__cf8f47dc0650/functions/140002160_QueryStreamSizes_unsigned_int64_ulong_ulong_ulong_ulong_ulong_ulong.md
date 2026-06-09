# QueryStreamSizes(unsigned __int64,ulong,ulong,ulong,ulong *,ulong *,ulong *)

- ea: `0x140002160`
- end: `0x140002407`
- name: `?QueryStreamSizes@@YAJ_KKKKPEAK11@Z`
- size: `679`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, unsigned int, unsigned int, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140001940`
- `0x14000bb0c`

## callees

- `0x140002160`
- `0x140010160`
- `0x1400105c0`

## import_xrefs

- `cng!SslLookupCipherSuiteInfo` at `0x140002213`
- `cng!SslLookupCipherSuiteInfo` at `0x140002213`
- `cng!SslLookupCipherLengths` at `0x1400022c1`
- `cng!SslLookupCipherLengths` at `0x1400022c1`

## pseudocode

```c
__int64 __fastcall QueryStreamSizes(
        __int64 a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  __int64 v11; // rdx
  __int64 result; // rax
  unsigned int v13; // ecx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int128 v16; // [rsp+40h] [rbp-318h] BYREF
  int v17; // [rsp+50h] [rbp-308h]
  _DWORD v18[172]; // [rsp+60h] [rbp-2F8h] BYREF

  memset(v18, 0, 0x2A4u);
  if ( (a3 & 0xF0000) != 0 && (a3 & 0x3FFC) != 0 )
  {
    v11 = 0;
  }
  else if ( (a3 & 0xC0000) != 0 )
  {
    v11 = 65277;
  }
  else if ( (a3 & 0x30000) != 0 )
  {
    v11 = 65279;
  }
  else if ( (a3 & 0x3000) != 0 )
  {
    v11 = 772;
  }
  else if ( (a3 & 0xC00) != 0 )
  {
    v11 = 771;
  }
  else if ( (a3 & 0x300) != 0 )
  {
    v11 = 770;
  }
  else if ( (a3 & 0xC0) != 0 )
  {
    v11 = 769;
  }
  else if ( (a3 & 0x30) != 0 )
  {
    v11 = 768;
  }
  else
  {
    v11 = (a3 & 0xC) != 0 ? 2 : 0;
  }
  result = SslLookupCipherSuiteInfo(a1, v11, a2, a4, v18, 0);
  if ( !(_DWORD)result )
  {
    v13 = v18[68];
    if ( a5 )
      *a5 = v18[68];
    if ( a6 )
      *a6 = v18[101] >> 3;
    if ( a7 )
    {
      v14 = 0;
      if ( v13 > 1 )
        v14 = v13;
      *a7 = v14;
    }
    if ( (a3 & 0x3F00) != 0 )
    {
      v17 = 0;
      v16 = 0;
      if ( (a3 & 0xF0000) != 0 && (a3 & 0x3FFC) != 0 )
      {
        v15 = 0;
      }
      else if ( (a3 & 0xC0000) != 0 )
      {
        v15 = 65277;
      }
      else if ( (a3 & 0x30000) != 0 )
      {
        v15 = 65279;
      }
      else if ( (a3 & 0x3000) != 0 )
      {
        v15 = 772;
      }
      else if ( (a3 & 0xC00) != 0 )
      {
        v15 = 771;
      }
      else if ( (a3 & 0x300) != 0 )
      {
        v15 = 770;
      }
      else if ( (a3 & 0xC0) != 0 )
      {
        v15 = 769;
      }
      else
      {
        v15 = (a3 & 0x30) != 0 ? 768LL : (a3 & 0xC) != 0 ? 2 : 0;
      }
      if ( !(unsigned int)SslLookupCipherLengths(a1, v15, a2, a4, &v16, 20, 0) )
      {
        if ( a6 )
          *a6 = DWORD2(v16);
        if ( a7 )
          *a7 = HIDWORD(v16);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002160  mov     [rsp+arg_10], rbx
0x140002165  push    rbp
0x140002166  push    rsi
0x140002167  push    rdi
0x140002168  push    r12
0x14000216a  push    r13
0x14000216c  push    r14
0x14000216e  push    r15
0x140002170  sub     rsp, 320h
0x140002177  mov     rax, cs:__security_cookie
0x14000217e  xor     rax, rsp
0x140002181  mov     [rsp+358h+var_48], rax
0x140002189  mov     r14, [rsp+358h+arg_20]
0x140002191  mov     ebx, r8d
0x140002194  mov     rdi, [rsp+358h+arg_28]
0x14000219c  mov     r15d, edx
0x14000219f  mov     rsi, [rsp+358h+arg_30]
0x1400021a7  mov     rbp, rcx
0x1400021aa  xor     edx, edx; Val
0x1400021ac  lea     rcx, [rsp+358h+var_2F8]; void *
0x1400021b1  mov     r8d, 2A4h; Size
0x1400021b7  mov     r12d, r9d
0x1400021ba  call    memset
0x1400021bf  mov     r13d, ebx
0x1400021c2  and     r13d, 0F0000h
0x1400021c9  jnz     loc_140002315
0x1400021cf  test    ebx, 0C0000h
0x1400021d5  jnz     loc_140002328
0x1400021db  test    ebx, 30000h
0x1400021e1  jnz     loc_140002332
0x1400021e7  test    ebx, 3000h
0x1400021ed  jz      loc_14000233C
0x1400021f3  mov     edx, 304h
0x1400021f8  lea     rax, [rsp+358h+var_2F8]
0x1400021fd  mov     [rsp+358h+var_330], 0
0x140002205  mov     r9d, r12d
0x140002208  mov     [rsp+358h+var_338], rax
0x14000220d  mov     r8d, r15d
0x140002210  mov     rcx, rbp
0x140002213  call    cs:__imp_SslLookupCipherSuiteInfo
0x14000221a  nop     dword ptr [rax+rax+00h]
0x14000221f  test    eax, eax
0x140002221  jnz     loc_1400022E9
0x140002227  mov     ecx, [rsp+358h+var_1E8]
0x14000222e  test    r14, r14
0x140002231  jz      short loc_140002236
0x140002233  mov     [r14], ecx
0x140002236  test    rdi, rdi
0x140002239  jz      short loc_140002247
0x14000223b  mov     eax, [rsp+358h+var_164]
0x140002242  shr     eax, 3
0x140002245  mov     [rdi], eax
0x140002247  test    rsi, rsi
0x14000224a  jz      short loc_140002256
0x14000224c  xor     eax, eax
0x14000224e  cmp     ecx, 1
0x140002251  cmova   eax, ecx
0x140002254  mov     [rsi], eax
0x140002256  test    ebx, 3F00h
0x14000225c  jz      loc_1400022E7
0x140002262  xor     eax, eax
0x140002264  xorps   xmm0, xmm0
0x140002267  mov     [rsp+358h+var_308], eax
0x14000226b  movups  [rsp+358h+var_318], xmm0
0x140002270  test    r13d, r13d
0x140002273  jnz     loc_14000238F
0x140002279  test    ebx, 0C0000h
0x14000227f  jnz     loc_1400023A2
0x140002285  test    ebx, 30000h
0x14000228b  jnz     loc_1400023AC
0x140002291  test    ebx, 3000h
0x140002297  jz      loc_1400023B6
0x14000229d  mov     edx, 304h
0x1400022a2  mov     [rsp+358h+var_328], eax
0x1400022a6  mov     r9d, r12d
0x1400022a9  lea     rax, [rsp+358h+var_318]
0x1400022ae  mov     [rsp+358h+var_330], 14h
0x1400022b6  mov     r8d, r15d
0x1400022b9  mov     [rsp+358h+var_338], rax
0x1400022be  mov     rcx, rbp
0x1400022c1  call    cs:__imp_SslLookupCipherLengths
0x1400022c8  nop     dword ptr [rax+rax+00h]
0x1400022cd  test    eax, eax
0x1400022cf  jnz     short loc_1400022E7
0x1400022d1  test    rdi, rdi
0x1400022d4  jz      short loc_1400022DC
0x1400022d6  mov     eax, dword ptr [rsp+358h+var_318+8]
0x1400022da  mov     [rdi], eax
0x1400022dc  test    rsi, rsi
0x1400022df  jz      short loc_1400022E7
0x1400022e1  mov     eax, dword ptr [rsp+358h+var_318+0Ch]
0x1400022e5  mov     [rsi], eax
0x1400022e7  xor     eax, eax
0x1400022e9  mov     rcx, [rsp+358h+var_48]
0x1400022f1  xor     rcx, rsp; StackCookie
0x1400022f4  call    __security_check_cookie
0x1400022f9  mov     rbx, [rsp+358h+arg_10]
0x140002301  add     rsp, 320h
0x140002308  pop     r15
0x14000230a  pop     r14
0x14000230c  pop     r13
0x14000230e  pop     r12
0x140002310  pop     rdi
0x140002311  pop     rsi
0x140002312  pop     rbp
0x140002313  retn
0x140002315  test    ebx, 3FFCh
0x14000231b  jz      loc_1400021CF
0x140002321  xor     edx, edx
0x140002323  jmp     loc_1400021F8
0x140002328  mov     edx, 0FEFDh
0x14000232d  jmp     loc_1400021F8
0x140002332  mov     edx, 0FEFFh
0x140002337  jmp     loc_1400021F8
0x14000233c  test    ebx, 0C00h
0x140002342  jz      short loc_14000234E
0x140002344  mov     edx, 303h
0x140002349  jmp     loc_1400021F8
0x14000234e  test    ebx, 300h
0x140002354  jz      short loc_140002360
0x140002356  mov     edx, 302h
0x14000235b  jmp     loc_1400021F8
0x140002360  test    bl, 0C0h
0x140002363  jz      short loc_14000236F
0x140002365  mov     edx, 301h
0x14000236a  jmp     loc_1400021F8
0x14000236f  test    bl, 30h
0x140002372  jz      short loc_14000237E
0x140002374  mov     edx, 300h
0x140002379  jmp     loc_1400021F8
0x14000237e  movzx   eax, bl
0x140002381  and     al, 0Ch
0x140002383  neg     al
0x140002385  sbb     edx, edx
0x140002387  and     edx, 2
0x14000238a  jmp     loc_1400021F8
0x14000238f  test    ebx, 3FFCh
0x140002395  jz      loc_140002279
0x14000239b  xor     edx, edx
0x14000239d  jmp     loc_1400022A2
0x1400023a2  mov     edx, 0FEFDh
0x1400023a7  jmp     loc_1400022A2
0x1400023ac  mov     edx, 0FEFFh
0x1400023b1  jmp     loc_1400022A2
0x1400023b6  test    ebx, 0C00h
0x1400023bc  jz      short loc_1400023C8
0x1400023be  mov     edx, 303h
0x1400023c3  jmp     loc_1400022A2
0x1400023c8  test    ebx, 300h
0x1400023ce  jz      short loc_1400023DA
0x1400023d0  mov     edx, 302h
0x1400023d5  jmp     loc_1400022A2
0x1400023da  test    bl, 0C0h
0x1400023dd  jz      short loc_1400023E9
0x1400023df  mov     edx, 301h
0x1400023e4  jmp     loc_1400022A2
0x1400023e9  test    bl, 30h
0x1400023ec  jz      short loc_1400023F8
0x1400023ee  mov     edx, 300h
0x1400023f3  jmp     loc_1400022A2
0x1400023f8  and     bl, 0Ch
0x1400023fb  neg     bl
0x1400023fd  sbb     edx, edx
0x1400023ff  and     edx, 2
0x140002402  jmp     loc_1400022A2
```
