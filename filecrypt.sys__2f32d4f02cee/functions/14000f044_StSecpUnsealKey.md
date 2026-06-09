# StSecpUnsealKey

- ea: `0x14000f044`
- end: `0x14000f2ac`
- name: `StSecpUnsealKey`
- size: `616`
- prototype: `__int64 __fastcall(void *Src, size_t Size, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000eb20`

## callees

- `0x140003540`
- `0x140003640`
- `0x140003b80`
- `0x14000ef5c`
- `0x14000f044`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x14000f1a4`
- `tbs!Tbsip_Submit_Command` at `0x14000f22a`
- `tbs!Tbsip_Submit_Command` at `0x14000f1a4`
- `tbs!Tbsip_Submit_Command` at `0x14000f22a`
- `tbs!Tbsip_Context_Close` at `0x14000f27c`
- `tbs!Tbsip_Context_Close` at `0x14000f27c`
- `tbs!Tbsi_Context_Create` at `0x14000f0f8`
- `tbs!Tbsi_Context_Create` at `0x14000f0f8`

## pseudocode

```c
__int64 __fastcall StSecpUnsealKey(void *Src, size_t Size, void *a3, _DWORD *a4)
{
  size_t v5; // rdi
  unsigned int v8; // ebx
  unsigned int pcbResult; // [rsp+40h] [rbp-C0h] BYREF
  PVOID phContext; // [rsp+48h] [rbp-B8h] BYREF
  TBS_CONTEXT_PARAMS pContextParams; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+54h] [rbp-ACh]
  BYTE pabCommand[512]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = (unsigned int)Size;
  pContextParams.version = 2;
  v13 = 4;
  phContext = 0;
  memset(pabCommand, 0, sizeof(pabCommand));
  pcbResult = 512;
  if ( !(unsigned int)StSecpSealKeyTestHookSet() )
  {
    if ( (unsigned int)v5 > 0x1E5 )
    {
      v8 = -1073741811;
      goto LABEL_17;
    }
    if ( Tbsi_Context_Create(&pContextParams, &phContext) )
      goto LABEL_8;
    *(_WORD *)pabCommand = 640;
    *(_DWORD *)&pabCommand[6] = 1459683328;
    pabCommand[2] = (unsigned int)(v5 + 27) >> 24;
    *(_DWORD *)&pabCommand[10] = 16777345;
    pabCommand[3] = (unsigned int)(v5 + 27) >> 16;
    pabCommand[4] = (unsigned __int16)(v5 + 27) >> 8;
    *(_DWORD *)&pabCommand[14] = 150994944;
    *(_DWORD *)&pabCommand[18] = 150995008;
    *(_DWORD *)&pabCommand[22] = 0x10000;
    pabCommand[26] = 0;
    pabCommand[5] = v5 + 27;
    memmove(&pabCommand[27], Src, v5);
    if ( Tbsip_Submit_Command(phContext, 0, 0xC8u, pabCommand, v5 + 27, pabCommand, &pcbResult) )
      goto LABEL_8;
    if ( *(_DWORD *)&pabCommand[6] )
      goto LABEL_8;
    pcbResult = 512;
    *(_DWORD *)pabCommand = 640;
    *(_DWORD *)&pabCommand[4] = 6912;
    *(_WORD *)&pabCommand[8] = 24065;
    *(_DWORD *)&pabCommand[14] = 150994944;
    *(_DWORD *)&pabCommand[18] = 150995008;
    *(_DWORD *)&pabCommand[22] = 0x10000;
    pabCommand[26] = 0;
    if ( Tbsip_Submit_Command(phContext, 0, 0xC8u, pabCommand, 0x1Bu, pabCommand, &pcbResult) )
    {
LABEL_8:
      v8 = -1073741823;
      goto LABEL_17;
    }
    LODWORD(v5) = pabCommand[15] + (pabCommand[14] << 8);
    if ( a3 && *a4 >= (unsigned int)v5 )
    {
      memmove(a3, &pabCommand[16], (unsigned int)v5);
      v8 = 0;
      goto LABEL_16;
    }
LABEL_15:
    v8 = -1073741789;
    goto LABEL_16;
  }
  if ( !a3 || *a4 < (unsigned int)v5 )
    goto LABEL_15;
  v8 = 0;
  memmove(a3, Src, (unsigned int)v5);
LABEL_16:
  *a4 = v5;
LABEL_17:
  if ( phContext )
    Tbsip_Context_Close(phContext);
  return v8;
}

```

## disassembly

```asm
0x14000f044  push    rbp
0x14000f046  push    rbx
0x14000f047  push    rsi
0x14000f048  push    rdi
0x14000f049  push    r12
0x14000f04b  push    r14
0x14000f04d  push    r15
0x14000f04f  lea     rbp, [rsp-170h]
0x14000f057  sub     rsp, 270h
0x14000f05e  mov     rax, cs:__security_cookie
0x14000f065  xor     rax, rsp
0x14000f068  mov     [rbp+1A0h+var_40], rax
0x14000f06f  mov     r14, r8
0x14000f072  mov     edi, edx
0x14000f074  mov     r15, rcx
0x14000f077  mov     [rsp+2A0h+pContextParams.version], 2
0x14000f07f  xor     r12d, r12d
0x14000f082  mov     [rsp+2A0h+var_24C], 4
0x14000f08a  xor     edx, edx; Val
0x14000f08c  mov     [rsp+2A0h+phContext], r12
0x14000f091  mov     r8d, 200h; Size
0x14000f097  lea     rcx, [rsp+2A0h+pabCommand]; void *
0x14000f09c  mov     rsi, r9
0x14000f09f  call    memset
0x14000f0a4  mov     [rsp+2A0h+var_260], 200h
0x14000f0ac  call    StSecpSealKeyTestHookSet
0x14000f0b1  test    eax, eax
0x14000f0b3  jz      short loc_14000F0DC
0x14000f0b5  test    r14, r14
0x14000f0b8  jz      loc_14000F26B
0x14000f0be  cmp     [rsi], edi
0x14000f0c0  jb      loc_14000F26B
0x14000f0c6  mov     r8d, edi; Size
0x14000f0c9  mov     rdx, r15; Src
0x14000f0cc  mov     rcx, r14; void *
0x14000f0cf  mov     ebx, r12d
0x14000f0d2  call    memmove
0x14000f0d7  jmp     loc_14000F270
0x14000f0dc  cmp     edi, 1E5h
0x14000f0e2  jbe     short loc_14000F0EE
0x14000f0e4  mov     ebx, 0C000000Dh
0x14000f0e9  jmp     loc_14000F272
0x14000f0ee  lea     rdx, [rsp+2A0h+phContext]; phContext
0x14000f0f3  lea     rcx, [rsp+2A0h+pContextParams]; pContextParams
0x14000f0f8  call    cs:__imp_Tbsi_Context_Create
0x14000f0ff  nop     dword ptr [rax+rax+00h]
0x14000f104  test    eax, eax
0x14000f106  jz      short loc_14000F112
0x14000f108  mov     ebx, 0C0000001h
0x14000f10d  jmp     loc_14000F272
0x14000f112  lea     ebx, [rdi+1Bh]
0x14000f115  mov     word ptr [rsp+2A0h+pabCommand], 280h
0x14000f11c  mov     eax, ebx
0x14000f11e  mov     [rsp+2A0h+var_23C+2], 57010000h
0x14000f126  shr     eax, 18h
0x14000f129  lea     rcx, [rsp+2A0h+var_225]; void *
0x14000f12e  mov     [rsp+2A0h+pabCommand+2], al
0x14000f132  mov     r8, rdi; Size
0x14000f135  mov     eax, ebx
0x14000f137  mov     [rsp+2A0h+var_236], 1000081h
0x14000f13f  shr     eax, 10h
0x14000f142  mov     rdx, r15; Src
0x14000f145  mov     [rsp+2A0h+pabCommand+3], al
0x14000f149  mov     eax, ebx
0x14000f14b  shr     eax, 8
0x14000f14e  mov     byte ptr [rsp+2A0h+var_23C], al
0x14000f152  mov     [rsp+2A0h+Src], 9000000h
0x14000f15a  mov     [rsp+2A0h+var_22E], 9000040h
0x14000f162  mov     [rsp+2A0h+var_22A], 10000h
0x14000f16a  mov     [rsp+2A0h+var_226], r12b
0x14000f16f  mov     byte ptr [rsp+2A0h+var_23C+1], bl
0x14000f173  call    memmove
0x14000f178  mov     rcx, [rsp+2A0h+phContext]; hContext
0x14000f17d  lea     rax, [rsp+2A0h+var_260]
0x14000f182  mov     [rsp+2A0h+pcbResult], rax; pcbResult
0x14000f187  lea     r9, [rsp+2A0h+pabCommand]; pabCommand
0x14000f18c  lea     rax, [rsp+2A0h+pabCommand]
0x14000f191  xor     edx, edx; Locality
0x14000f193  mov     [rsp+2A0h+pabResult], rax; pabResult
0x14000f198  mov     [rsp+2A0h+cbCommand], ebx; cbCommand
0x14000f19c  mov     ebx, 0C8h
0x14000f1a1  mov     r8d, ebx; Priority
0x14000f1a4  call    cs:__imp_Tbsip_Submit_Command
0x14000f1ab  nop     dword ptr [rax+rax+00h]
0x14000f1b0  test    eax, eax
0x14000f1b2  jnz     loc_14000F108
0x14000f1b8  cmp     [rsp+2A0h+var_23C+2], r12d
0x14000f1bd  jnz     loc_14000F108
0x14000f1c3  mov     rcx, [rsp+2A0h+phContext]; hContext
0x14000f1c8  lea     rax, [rsp+2A0h+var_260]
0x14000f1cd  mov     [rsp+2A0h+pcbResult], rax; pcbResult
0x14000f1d2  lea     r9, [rsp+2A0h+pabCommand]; pabCommand
0x14000f1d7  lea     rax, [rsp+2A0h+pabCommand]
0x14000f1dc  mov     [rsp+2A0h+var_260], 200h
0x14000f1e4  mov     [rsp+2A0h+pabResult], rax; pabResult
0x14000f1e9  mov     r8d, ebx; Priority
0x14000f1ec  xor     edx, edx; Locality
0x14000f1ee  mov     [rsp+2A0h+cbCommand], 1Bh; cbCommand
0x14000f1f6  mov     dword ptr [rsp+2A0h+pabCommand], 280h
0x14000f1fe  mov     [rsp+2A0h+var_23C], 1B00h
0x14000f206  mov     [rsp+2A0h+var_238], 5E01h
0x14000f20d  mov     [rsp+2A0h+Src], 9000000h
0x14000f215  mov     [rsp+2A0h+var_22E], 9000040h
0x14000f21d  mov     [rsp+2A0h+var_22A], 10000h
0x14000f225  mov     [rsp+2A0h+var_226], r12b
0x14000f22a  call    cs:__imp_Tbsip_Submit_Command
0x14000f231  nop     dword ptr [rax+rax+00h]
0x14000f236  test    eax, eax
0x14000f238  jnz     loc_14000F108
0x14000f23e  movzx   edi, byte ptr [rsp+2A0h+Src]
0x14000f243  movzx   eax, byte ptr [rsp+2A0h+Src+1]
0x14000f248  shl     edi, 8
0x14000f24b  add     edi, eax
0x14000f24d  test    r14, r14
0x14000f250  jz      short loc_14000F26B
0x14000f252  cmp     [rsi], edi
0x14000f254  jb      short loc_14000F26B
0x14000f256  mov     r8d, edi; Size
0x14000f259  lea     rdx, [rsp+2A0h+Src+2]; Src
0x14000f25e  mov     rcx, r14; void *
0x14000f261  call    memmove
0x14000f266  mov     ebx, r12d
0x14000f269  jmp     short loc_14000F270
0x14000f26b  mov     ebx, 0C0000023h
0x14000f270  mov     [rsi], edi
0x14000f272  mov     rcx, [rsp+2A0h+phContext]; hContext
0x14000f277  test    rcx, rcx
0x14000f27a  jz      short loc_14000F288
0x14000f27c  call    cs:__imp_Tbsip_Context_Close
0x14000f283  nop     dword ptr [rax+rax+00h]
0x14000f288  mov     eax, ebx
0x14000f28a  mov     rcx, [rbp+1A0h+var_40]
0x14000f291  xor     rcx, rsp; StackCookie
0x14000f294  call    __security_check_cookie
0x14000f299  add     rsp, 270h
0x14000f2a0  pop     r15
0x14000f2a2  pop     r14
0x14000f2a4  pop     r12
0x14000f2a6  pop     rdi
0x14000f2a7  pop     rsi
0x14000f2a8  pop     rbx
0x14000f2a9  pop     rbp
0x14000f2aa  retn
```
