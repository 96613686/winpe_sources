# StSecpSealKey

- ea: `0x14000ecd4`
- end: `0x14000ef55`
- name: `StSecpSealKey`
- size: `641`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000eb20`

## callees

- `0x140003540`
- `0x140003640`
- `0x140003b80`
- `0x14000ecd4`
- `0x14000ef5c`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x14000ee93`
- `tbs!Tbsip_Submit_Command` at `0x14000ee93`
- `tbs!Tbsip_Context_Close` at `0x14000ef1c`
- `tbs!Tbsip_Context_Close` at `0x14000ef1c`
- `tbs!Tbsi_Context_Create` at `0x14000edcb`
- `tbs!Tbsi_Context_Create` at `0x14000edcb`

## pseudocode

```c
__int64 __fastcall StSecpSealKey(__int64 a1, unsigned int a2, void *a3, unsigned int *a4)
{
  const void *v4; // r12
  size_t v6; // rsi
  unsigned int v8; // ebx
  unsigned int v9; // edi
  __int128 v11; // [rsp+40h] [rbp-C0h]
  __int128 v12; // [rsp+50h] [rbp-B0h]
  unsigned int pcbResult; // [rsp+68h] [rbp-98h] BYREF
  PVOID phContext; // [rsp+70h] [rbp-90h] BYREF
  TBS_CONTEXT_PARAMS pContextParams; // [rsp+78h] [rbp-88h] BYREF
  int v16; // [rsp+7Ch] [rbp-84h]
  BYTE pabCommand[512]; // [rsp+80h] [rbp-80h] BYREF

  v4 = g_MasterKey;
  v6 = a2;
  *(_QWORD *)&v11 = 0xFFFFFFFF0280LL;
  *((_QWORD *)&v11 + 1) = 0x10000815301LL;
  *(_QWORD *)&v12 = 0x90000400900LL;
  *((_QWORD *)&v12 + 1) = 0xFF0000FFFF000001uLL;
  pContextParams.version = 2;
  v16 = 4;
  phContext = 0;
  memset(pabCommand, 0, sizeof(pabCommand));
  pcbResult = 512;
  if ( (unsigned int)StSecpSealKeyTestHookSet() )
  {
    if ( a3 && *a4 >= (unsigned int)v6 )
    {
      v8 = 0;
      memmove(a3, v4, (unsigned int)v6);
    }
    else
    {
      v8 = -1073741789;
    }
    *a4 = v6;
  }
  else if ( (unsigned int)v6 > 0x80 )
  {
    v8 = -1073741811;
  }
  else
  {
    if ( Tbsi_Context_Create(&pContextParams, &phContext) )
      goto LABEL_9;
    *(_OWORD *)pabCommand = v11;
    pabCommand[2] = (unsigned int)(v6 + 55) >> 24;
    pabCommand[3] = (unsigned int)(v6 + 55) >> 16;
    pabCommand[4] = (unsigned __int16)(v6 + 55) >> 8;
    *(_OWORD *)&pabCommand[16] = v12;
    pabCommand[27] = (unsigned __int16)(v6 + 4) >> 8;
    pabCommand[28] = v6 + 4;
    pabCommand[31] = BYTE1(v6);
    pabCommand[5] = v6 + 55;
    pabCommand[32] = v6;
    memmove(&pabCommand[33], v4, v6);
    *(_DWORD *)&pabCommand[v6 + 33] = 134221312;
    *(_DWORD *)&pabCommand[v6 + 37] = 2816;
    *(_DWORD *)&pabCommand[v6 + 41] = 20996;
    *(_QWORD *)&pabCommand[v6 + 45] = 4096;
    *(_WORD *)&pabCommand[v6 + 53] = 0;
    if ( Tbsip_Submit_Command(phContext, 0, 0xC8u, pabCommand, v6 + 55, pabCommand, &pcbResult)
      || *(_DWORD *)&pabCommand[6] )
    {
LABEL_9:
      v8 = -1073741823;
    }
    else
    {
      v9 = pabCommand[256 * pabCommand[14] + 17 + pabCommand[15]]
         + 4
         + pabCommand[15]
         + ((pabCommand[14] + pabCommand[256 * pabCommand[14] + 16 + pabCommand[15]]) << 8);
      if ( a3 && *a4 >= v9 )
      {
        memmove(a3, &pabCommand[14], v9);
        v8 = 0;
      }
      else
      {
        v8 = -1073741789;
      }
      *a4 = v9;
    }
  }
  if ( phContext )
    Tbsip_Context_Close(phContext);
  return v8;
}

```

## disassembly

```asm
0x14000ecd4  mov     [rsp-8+arg_0], rbx
0x14000ecd9  push    rbp
0x14000ecda  push    rsi
0x14000ecdb  push    rdi
0x14000ecdc  push    r12
0x14000ecde  push    r13
0x14000ece0  push    r14
0x14000ece2  push    r15
0x14000ece4  lea     rbp, [rsp-190h]
0x14000ecec  sub     rsp, 290h
0x14000ecf3  mov     rax, cs:__security_cookie
0x14000ecfa  xor     rax, rsp
0x14000ecfd  mov     [rbp+1C0h+var_40], rax
0x14000ed04  mov     r12, cs:g_MasterKey
0x14000ed0b  lea     rcx, [rbp+1C0h+pabCommand]; void *
0x14000ed0f  mov     r15, r8
0x14000ed12  mov     esi, edx
0x14000ed14  mov     ebx, 200h
0x14000ed19  mov     dword ptr [rsp+2C0h+var_280], 0FFFF0280h
0x14000ed21  xor     r13d, r13d
0x14000ed24  mov     dword ptr [rsp+2C0h+var_280+4], 0FFFFh
0x14000ed2c  mov     r8d, ebx; Size
0x14000ed2f  mov     dword ptr [rsp+2C0h+var_280+8], 815301h
0x14000ed37  xor     edx, edx; Val
0x14000ed39  mov     dword ptr [rsp+2C0h+var_280+0Ch], 100h
0x14000ed41  mov     r14, r9
0x14000ed44  mov     dword ptr [rsp+2C0h+var_270], 400900h
0x14000ed4c  mov     dword ptr [rsp+2C0h+var_270+4], 900h
0x14000ed54  mov     dword ptr [rsp+2C0h+var_270+8], 0FF000001h
0x14000ed5c  mov     dword ptr [rsp+2C0h+var_270+0Ch], 0FF0000FFh
0x14000ed64  mov     [rsp+2C0h+pContextParams.version], 2
0x14000ed6c  mov     [rsp+2C0h+var_244], 4
0x14000ed74  mov     [rsp+2C0h+phContext], r13
0x14000ed79  call    memset
0x14000ed7e  mov     [rsp+2C0h+var_258], ebx
0x14000ed82  call    StSecpSealKeyTestHookSet
0x14000ed87  test    eax, eax
0x14000ed89  jz      short loc_14000EDB5
0x14000ed8b  test    r15, r15
0x14000ed8e  jz      short loc_14000EDA8
0x14000ed90  cmp     [r14], esi
0x14000ed93  jb      short loc_14000EDA8
0x14000ed95  mov     r8d, esi; Size
0x14000ed98  mov     rdx, r12; Src
0x14000ed9b  mov     rcx, r15; void *
0x14000ed9e  mov     ebx, r13d
0x14000eda1  call    memmove
0x14000eda6  jmp     short loc_14000EDAD
0x14000eda8  mov     ebx, 0C0000023h
0x14000edad  mov     [r14], esi
0x14000edb0  jmp     loc_14000EF12
0x14000edb5  cmp     esi, 80h
0x14000edbb  ja      loc_14000EF0D
0x14000edc1  lea     rdx, [rsp+2C0h+phContext]; phContext
0x14000edc6  lea     rcx, [rsp+2C0h+pContextParams]; pContextParams
0x14000edcb  call    cs:__imp_Tbsi_Context_Create
0x14000edd2  nop     dword ptr [rax+rax+00h]
0x14000edd7  test    eax, eax
0x14000edd9  jz      short loc_14000EDE5
0x14000eddb  mov     ebx, 0C0000001h
0x14000ede0  jmp     loc_14000EF12
0x14000ede5  movups  xmm0, [rsp+2C0h+var_280]
0x14000edea  lea     edi, [rsi+37h]
0x14000eded  mov     [rbp+1C0h+var_220], 0FFh
0x14000edf1  movups  xmm1, [rsp+2C0h+var_270]
0x14000edf6  lea     rcx, [rbp+1C0h+var_21F]; void *
0x14000edfa  mov     eax, edi
0x14000edfc  movaps  xmmword ptr [rbp+1C0h+pabCommand], xmm0
0x14000ee00  mov     r8, rsi; Size
0x14000ee03  shr     eax, 18h
0x14000ee06  mov     rdx, r12; Src
0x14000ee09  mov     [rbp+1C0h+pabCommand+2], al
0x14000ee0c  mov     eax, edi
0x14000ee0e  shr     eax, 10h
0x14000ee11  mov     [rbp+1C0h+pabCommand+3], al
0x14000ee14  mov     eax, edi
0x14000ee16  shr     eax, 8
0x14000ee19  mov     [rbp+1C0h+pabCommand+4], al
0x14000ee1c  lea     eax, [rsi+4]
0x14000ee1f  shr     eax, 8
0x14000ee22  movaps  [rbp+1C0h+var_230], xmm1
0x14000ee26  mov     byte ptr [rbp+1C0h+var_230+0Bh], al
0x14000ee29  lea     eax, [rsi+4]
0x14000ee2c  mov     byte ptr [rbp+1C0h+var_230+0Ch], al
0x14000ee2f  mov     eax, esi
0x14000ee31  shr     eax, 8
0x14000ee34  mov     byte ptr [rbp+1C0h+var_230+0Fh], al
0x14000ee37  mov     [rbp+1C0h+pabCommand+5], dil
0x14000ee3b  mov     [rbp+1C0h+var_220], sil
0x14000ee3f  call    memmove
0x14000ee44  mov     [rbp+rsi+1C0h+var_21F], 8000E00h
0x14000ee4c  lea     rax, [rsp+2C0h+var_258]
0x14000ee51  mov     [rbp+rsi+1C0h+var_21B], 0B00h
0x14000ee59  lea     r9, [rbp+1C0h+pabCommand]; pabCommand
0x14000ee5d  mov     [rsp+2C0h+pcbResult], rax; pcbResult
0x14000ee62  xor     edx, edx; Locality
0x14000ee64  mov     [rbp+rsi+1C0h+var_217], 5204h
0x14000ee6c  lea     rax, [rbp+1C0h+pabCommand]
0x14000ee70  mov     [rbp+rsi+1C0h+var_213], 1000h
0x14000ee79  mov     r8d, 0C8h; Priority
0x14000ee7f  mov     [rbp+rsi+1C0h+var_20B], r13w
0x14000ee85  mov     rcx, [rsp+2C0h+phContext]; hContext
0x14000ee8a  mov     [rsp+2C0h+pabResult], rax; pabResult
0x14000ee8f  mov     [rsp+2C0h+cbCommand], edi; cbCommand
0x14000ee93  call    cs:__imp_Tbsip_Submit_Command
0x14000ee9a  nop     dword ptr [rax+rax+00h]
0x14000ee9f  test    eax, eax
0x14000eea1  jnz     loc_14000EDDB
0x14000eea7  cmp     dword ptr [rbp+1C0h+pabCommand+6], r13d
0x14000eeab  jnz     loc_14000EDDB
0x14000eeb1  movzx   r10d, [rbp+1C0h+pabCommand+0Fh]
0x14000eeb6  movzx   r9d, [rbp+1C0h+pabCommand+0Eh]
0x14000eebb  mov     edx, r9d
0x14000eebe  shl     edx, 8
0x14000eec1  lea     eax, [r10+10h]
0x14000eec5  add     eax, edx
0x14000eec7  movzx   edi, [rbp+rax+1C0h+pabCommand]
0x14000eecc  lea     eax, [r10+11h]
0x14000eed0  add     edi, r9d
0x14000eed3  add     eax, edx
0x14000eed5  shl     edi, 8
0x14000eed8  add     edi, r10d
0x14000eedb  movzx   edx, [rbp+rax+1C0h+pabCommand]
0x14000eee0  add     edx, 4
0x14000eee3  add     edi, edx
0x14000eee5  test    r15, r15
0x14000eee8  jz      short loc_14000EF03
0x14000eeea  cmp     [r14], edi
0x14000eeed  jb      short loc_14000EF03
0x14000eeef  mov     r8d, edi; Size
0x14000eef2  lea     rdx, [rbp+1C0h+pabCommand+0Eh]; Src
0x14000eef6  mov     rcx, r15; void *
0x14000eef9  call    memmove
0x14000eefe  mov     ebx, r13d
0x14000ef01  jmp     short loc_14000EF08
0x14000ef03  mov     ebx, 0C0000023h
0x14000ef08  mov     [r14], edi
0x14000ef0b  jmp     short loc_14000EF12
0x14000ef0d  mov     ebx, 0C000000Dh
0x14000ef12  mov     rcx, [rsp+2C0h+phContext]; hContext
0x14000ef17  test    rcx, rcx
0x14000ef1a  jz      short loc_14000EF28
0x14000ef1c  call    cs:__imp_Tbsip_Context_Close
0x14000ef23  nop     dword ptr [rax+rax+00h]
0x14000ef28  mov     eax, ebx
0x14000ef2a  mov     rcx, [rbp+1C0h+var_40]
0x14000ef31  xor     rcx, rsp; StackCookie
0x14000ef34  call    __security_check_cookie
0x14000ef39  mov     rbx, [rsp+2C0h+arg_0]
0x14000ef41  add     rsp, 290h
0x14000ef48  pop     r15
0x14000ef4a  pop     r14
0x14000ef4c  pop     r13
0x14000ef4e  pop     r12
0x14000ef50  pop     rdi
0x14000ef51  pop     rsi
0x14000ef52  pop     rbp
0x14000ef53  retn
```
