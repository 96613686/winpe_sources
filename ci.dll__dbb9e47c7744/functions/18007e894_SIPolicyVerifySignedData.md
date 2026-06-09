# SIPolicyVerifySignedData

- ea: `0x18007e894`
- end: `0x18007e9cd`
- name: `SIPolicyVerifySignedData`
- size: `313`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800782f8`
- `0x18007d17c`
- `0x18007e774`

## callees

- `0x18002bf20`
- `0x18007e894`
- `0x18008ed10`
- `0x18008f458`
- `0x1800957f8`
- `0x18009860c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x18007e92e`
- `ntoskrnl!RtlCompareMemory` at `0x18007e92e`

## pseudocode

```c
__int64 __fastcall SIPolicyVerifySignedData(
        int a1,
        int a2,
        const void *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v9; // ebx
  int v11[4]; // [rsp+50h] [rbp-89h] BYREF
  __int128 v12; // [rsp+60h] [rbp-79h]
  __int128 v13; // [rsp+70h] [rbp-69h]
  int v14; // [rsp+80h] [rbp-59h] BYREF
  void *Source2; // [rsp+88h] [rbp-51h]
  unsigned int v16; // [rsp+90h] [rbp-49h]
  __int64 v17; // [rsp+98h] [rbp-41h]

  *(_OWORD *)v11 = 0;
  v12 = 0;
  v13 = 0;
  v9 = MinCrypK_VerifySignedDataKModeEx(a1, a2, 0, 0, a5, (int)v11, &v14, 0, 0);
  if ( v9 >= 0 )
  {
    if ( v14 == 9
      && RtlCompareMemory(a3, Source2, 9u) == 9
      && (int)MinAsn1ExtractContent(v17, v16, a7, a6) >= 0
      && (!a5 || (*(_DWORD *)(a5 + 4) & 0x20) == 0 || (v11[2] & 0x4000) != 0)
      && v11[0]
      && (_QWORD)v12
      && (v11[2] & 0xFFFF0000) == 0 )
    {
      if ( a8 )
        v9 = SIPolicyConvertChainInfo(v12, a8);
    }
    else
    {
      v9 = -1073740760;
    }
  }
  if ( v11[0] )
    I_MincryptFreeChainInfo(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007e894  push    rbp
0x18007e896  push    rbx
0x18007e897  push    rsi
0x18007e898  push    rdi
0x18007e899  push    r12
0x18007e89b  push    r14
0x18007e89d  push    r15
0x18007e89f  lea     rbp, [rsp-7]
0x18007e8a4  sub     rsp, 0E0h
0x18007e8ab  mov     rax, cs:__security_cookie
0x18007e8b2  xor     rax, rsp
0x18007e8b5  mov     [rbp+37h+var_40], rax
0x18007e8b9  mov     rdi, [rbp+37h+arg_20]
0x18007e8bd  lea     rax, [rbp+37h+var_90]
0x18007e8c1  mov     r15, [rbp+37h+arg_28]
0x18007e8c5  xorps   xmm0, xmm0
0x18007e8c8  mov     r12, [rbp+37h+arg_30]
0x18007e8cc  mov     r14, r8
0x18007e8cf  mov     rsi, [rbp+37h+arg_38]
0x18007e8d3  xor     r9d, r9d; int
0x18007e8d6  mov     [rsp+110h+var_D0], 0; __int64
0x18007e8df  xor     r8d, r8d; int
0x18007e8e2  mov     [rsp+110h+var_D8], 0; __int64
0x18007e8eb  mov     [rsp+110h+var_E0], rax; void *
0x18007e8f0  lea     rax, [rsp+110h+var_C0]
0x18007e8f5  mov     qword ptr [rsp+110h+var_E8], rax; int
0x18007e8fa  mov     [rsp+110h+var_F0], rdi; __int64
0x18007e8ff  movups  xmmword ptr [rsp+110h+var_C0], xmm0
0x18007e904  movups  [rbp+37h+var_B0], xmm0
0x18007e908  movups  [rbp+37h+var_A0], xmm0
0x18007e90c  call    MinCrypK_VerifySignedDataKModeEx
0x18007e911  mov     ebx, eax
0x18007e913  test    eax, eax
0x18007e915  js      loc_18007E99C
0x18007e91b  cmp     [rbp+37h+var_90], 9
0x18007e91f  jnz     short loc_18007E997
0x18007e921  mov     rdx, [rbp+37h+Source2]; Source2
0x18007e925  mov     r8d, 9; Length
0x18007e92b  mov     rcx, r14; Source1
0x18007e92e  call    cs:__imp_RtlCompareMemory
0x18007e935  nop     dword ptr [rax+rax+00h]
0x18007e93a  cmp     rax, 9
0x18007e93e  jnz     short loc_18007E997
0x18007e940  mov     edx, [rbp+37h+var_80]
0x18007e943  mov     r9, r15
0x18007e946  mov     rcx, [rbp+37h+var_78]
0x18007e94a  mov     r8, r12
0x18007e94d  call    MinAsn1ExtractContent
0x18007e952  test    eax, eax
0x18007e954  js      short loc_18007E997
0x18007e956  test    rdi, rdi
0x18007e959  jz      short loc_18007E96C
0x18007e95b  mov     eax, [rdi+4]
0x18007e95e  test    al, 20h
0x18007e960  jz      short loc_18007E96C
0x18007e962  test    [rsp+110h+var_C0+8], 4000h
0x18007e96a  jz      short loc_18007E997
0x18007e96c  cmp     [rsp+110h+var_C0], 0
0x18007e971  jz      short loc_18007E997
0x18007e973  mov     rcx, qword ptr [rbp+37h+var_B0]
0x18007e977  test    rcx, rcx
0x18007e97a  jz      short loc_18007E997
0x18007e97c  test    [rsp+110h+var_C0+8], 0FFFF0000h
0x18007e984  jnz     short loc_18007E997
0x18007e986  test    rsi, rsi
0x18007e989  jz      short loc_18007E99C
0x18007e98b  mov     rdx, rsi
0x18007e98e  call    SIPolicyConvertChainInfo
0x18007e993  mov     ebx, eax
0x18007e995  jmp     short loc_18007E99C
0x18007e997  mov     ebx, 0C0000428h
0x18007e99c  cmp     [rsp+110h+var_C0], 0
0x18007e9a1  jz      short loc_18007E9AC
0x18007e9a3  mov     rcx, qword ptr [rbp+37h+var_B0]
0x18007e9a7  call    I_MincryptFreeChainInfo
0x18007e9ac  mov     eax, ebx
0x18007e9ae  mov     rcx, [rbp+37h+var_40]
0x18007e9b2  xor     rcx, rsp; StackCookie
0x18007e9b5  call    __security_check_cookie
0x18007e9ba  add     rsp, 0E0h
0x18007e9c1  pop     r15
0x18007e9c3  pop     r14
0x18007e9c5  pop     r12
0x18007e9c7  pop     rdi
0x18007e9c8  pop     rsi
0x18007e9c9  pop     rbx
0x18007e9ca  pop     rbp
0x18007e9cb  retn
```
