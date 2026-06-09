# DiscpFilterCondition5TupleV4Create

- ea: `0x180015918`
- end: `0x180015c94`
- name: `DiscpFilterCondition5TupleV4Create`
- size: `892`
- prototype: `__int64 __fastcall(char, unsigned int, unsigned int, unsigned int, unsigned int, __int16, unsigned int, char, _QWORD *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800165c4`

## callees

- `0x180001cfe`
- `0x180015918`
- `0x180016060`
- `0x1800160e0`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180015a5a`
- `ISCSIUM!DiscpAllocMemory` at `0x180015a5a`

## pseudocode

```c
__int64 __fastcall DiscpFilterCondition5TupleV4Create(
        char a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int16 a6,
        unsigned int a7,
        char a8,
        _QWORD *a9,
        int *a10)
{
  unsigned int v11; // ebp
  int v12; // edi
  unsigned int v13; // r15d
  int v14; // eax
  unsigned int v15; // r13d
  __int16 v16; // r12
  int v17; // ecx
  unsigned int v18; // r14d
  unsigned int v19; // esi
  char *v20; // rbx
  const GUID *v21; // rcx
  const GUID *v22; // rcx
  __int16 v23; // r8
  __int64 v24; // rdx
  GUID v25; // xmm0
  __int64 v26; // rdx
  GUID v27; // xmm0
  char v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rcx
  int v32; // [rsp+20h] [rbp-68h]
  unsigned int v33; // [rsp+24h] [rbp-64h]
  unsigned int v34; // [rsp+28h] [rbp-60h]
  char *v35; // [rsp+30h] [rbp-58h] BYREF
  int v36; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v37; // [rsp+98h] [rbp+10h]
  unsigned int v38; // [rsp+A0h] [rbp+18h]
  unsigned int v39; // [rsp+A8h] [rbp+20h]

  v39 = a4;
  v38 = a3;
  v37 = a2;
  v36 = 0;
  v11 = 0;
  v32 = 0;
  v12 = 0;
  *a9 = 0;
  *a10 = 0;
  if ( a2 || a3 )
  {
    v12 = 1;
    v36 = 1;
    v13 = 0;
    v14 = 1;
  }
  else
  {
    v13 = 0xFFFF;
    v14 = 0;
  }
  if ( a4 || a5 )
  {
    v12 = v14 + 1;
    v15 = v14;
    v36 = ++v14;
  }
  else
  {
    v15 = 0xFFFF;
  }
  if ( a6 )
  {
    v12 = v14 + 1;
    v33 = v14;
    v36 = ++v14;
  }
  else
  {
    v33 = 0xFFFF;
  }
  v16 = a7;
  if ( (_WORD)a7 )
  {
    v12 = v14 + 1;
    a7 = v14;
    v36 = ++v14;
  }
  else
  {
    a7 = 0xFFFF;
  }
  if ( a8 )
  {
    v12 = v14 + 1;
    v34 = v14;
    v36 = ++v14;
  }
  else
  {
    v34 = 0xFFFF;
  }
  v17 = a1 & 2;
  if ( (a1 & 1) != 0 || v17 )
  {
    v12 = v14 + 1;
    v18 = v14;
    v36 = v14 + 1;
    v19 = v14 + 1;
    if ( v17 )
      v32 = 1;
  }
  else
  {
    v18 = 0xFFFF;
    v19 = v14;
  }
  if ( v19 )
  {
    v35 = (char *)DiscpAllocMemory(40 * v19);
    v20 = v35;
    if ( v35 )
    {
      memset_0(v35, 0, 40LL * v19);
      if ( v13 != 0xFFFF )
      {
        v21 = &FWPM_CONDITION_IP_LOCAL_ADDRESS;
        if ( !v32 )
          v21 = &FWPM_CONDITION_IP_REMOTE_ADDRESS;
        v11 = DiscpFilterConditionIpAddressV4Fill(v21, v37, v38, &v35[40 * v13]);
        if ( v11 )
          goto LABEL_48;
      }
      if ( v15 == 0xFFFF )
        goto LABEL_33;
      v22 = &FWPM_CONDITION_IP_REMOTE_ADDRESS;
      if ( !v32 )
        v22 = &FWPM_CONDITION_IP_LOCAL_ADDRESS;
      v11 = DiscpFilterConditionIpAddressV4Fill(v22, v39, a5, &v35[40 * v15]);
      if ( v11 )
      {
LABEL_48:
        DiscpFilterConditionDestroy(&v35, &v36);
      }
      else
      {
LABEL_33:
        if ( v33 != 0xFFFF )
        {
          v23 = a6;
          v24 = 5LL * v33;
          *(_OWORD *)&v35[8 * v24] = 0;
          *(_OWORD *)&v20[8 * v24 + 16] = 0;
          *(_QWORD *)&v20[8 * v24 + 32] = 0;
          if ( v32 )
            v25 = FWPM_CONDITION_IP_LOCAL_PORT;
          else
            v25 = FWPM_CONDITION_IP_REMOTE_PORT;
          *(GUID *)&v20[40 * v33] = v25;
          *(_DWORD *)&v20[40 * v33 + 16] = v23 == 0 ? 3 : 0;
          *(_WORD *)&v20[40 * v33 + 32] = v23;
          *(_DWORD *)&v20[40 * v33 + 24] = 2;
        }
        if ( a7 != 0xFFFF )
        {
          v26 = 5LL * a7;
          *(_OWORD *)&v20[8 * v26] = 0;
          *(_OWORD *)&v20[8 * v26 + 16] = 0;
          *(_QWORD *)&v20[8 * v26 + 32] = 0;
          if ( v32 )
            v27 = FWPM_CONDITION_IP_REMOTE_PORT;
          else
            v27 = FWPM_CONDITION_IP_LOCAL_PORT;
          *(GUID *)&v20[8 * v26] = v27;
          *(_DWORD *)&v20[8 * v26 + 16] = v16 == 0 ? 3 : 0;
          *(_WORD *)&v20[8 * v26 + 32] = v16;
          *(_DWORD *)&v20[8 * v26 + 24] = 2;
        }
        if ( v34 != 0xFFFF )
        {
          v28 = a8;
          v29 = 5LL * v34;
          *(_OWORD *)&v20[8 * v29 + 16] = 0;
          *(_QWORD *)&v20[8 * v29 + 32] = 0;
          *(GUID *)&v20[8 * v29] = FWPM_CONDITION_IP_PROTOCOL;
          *(_DWORD *)&v20[8 * v29 + 16] = v28 == 0 ? 3 : 0;
          *(_DWORD *)&v20[8 * v29 + 24] = 1;
          v20[8 * v29 + 32] = v28;
        }
        if ( v18 != 0xFFFF )
        {
          v30 = 5LL * v18;
          *(_OWORD *)&v20[8 * v30] = 0;
          *(_OWORD *)&v20[8 * v30 + 16] = 0;
          *(_QWORD *)&v20[8 * v30 + 32] = 0;
          *(_DWORD *)&v20[8 * v30 + 24] = 1;
          v20[8 * v30 + 32] = 1;
          *(GUID *)&v20[8 * v30] = FWPM_CONDITION_IP_LOCAL_ADDRESS_TYPE;
        }
        *a9 = v20;
        *a10 = v12;
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180015918  mov     r11, rsp
0x18001591b  mov     [r11+20h], r9d
0x18001591f  mov     [r11+18h], r8d
0x180015923  mov     [rsp+arg_8], edx
0x180015927  push    rbx
0x180015928  push    rbp
0x180015929  push    rsi
0x18001592a  push    rdi
0x18001592b  push    r12
0x18001592d  push    r13
0x18001592f  push    r14
0x180015931  push    r15
0x180015933  sub     rsp, 48h
0x180015937  mov     r10d, ecx
0x18001593a  mov     eax, r8d
0x18001593d  mov     rcx, [rsp+88h+arg_40]
0x180015945  xor     r8d, r8d
0x180015948  mov     [r11+8], r8d
0x18001594c  mov     ebp, r8d
0x18001594f  mov     [rsp+88h+var_68], r8d
0x180015954  mov     edi, r8d
0x180015957  mov     r11d, 0FFFFh
0x18001595d  mov     [rcx], r8
0x180015960  lea     ebx, [r8+1]
0x180015964  mov     rcx, [rsp+88h+arg_48]
0x18001596c  mov     [rcx], r8d
0x18001596f  test    edx, edx
0x180015971  jnz     short loc_18001597F
0x180015973  test    eax, eax
0x180015975  jnz     short loc_18001597F
0x180015977  mov     r15d, r11d
0x18001597a  mov     eax, r8d
0x18001597d  jmp     short loc_18001598D
0x18001597f  mov     edi, ebx
0x180015981  mov     [rsp+88h+arg_0], ebx
0x180015988  mov     r15d, r8d
0x18001598b  mov     eax, ebx
0x18001598d  test    r9d, r9d
0x180015990  jnz     short loc_1800159A1
0x180015992  cmp     [rsp+88h+arg_20], r8d
0x18001599a  jnz     short loc_1800159A1
0x18001599c  mov     r13d, r11d
0x18001599f  jmp     short loc_1800159B0
0x1800159a1  lea     edi, [rax+1]
0x1800159a4  mov     r13d, eax
0x1800159a7  mov     [rsp+88h+arg_0], edi
0x1800159ae  mov     eax, edi
0x1800159b0  cmp     [rsp+88h+arg_28], r8w
0x1800159b9  jz      short loc_1800159CD
0x1800159bb  lea     edi, [rax+1]
0x1800159be  mov     [rsp+88h+var_64], eax
0x1800159c2  mov     [rsp+88h+arg_0], edi
0x1800159c9  mov     eax, edi
0x1800159cb  jmp     short loc_1800159D2
0x1800159cd  mov     [rsp+88h+var_64], r11d
0x1800159d2  movzx   r12d, word ptr [rsp+88h+arg_30]
0x1800159db  test    r12w, r12w
0x1800159df  jz      short loc_1800159F6
0x1800159e1  lea     edi, [rax+1]
0x1800159e4  mov     [rsp+88h+arg_30], eax
0x1800159eb  mov     [rsp+88h+arg_0], edi
0x1800159f2  mov     eax, edi
0x1800159f4  jmp     short loc_1800159FE
0x1800159f6  mov     [rsp+88h+arg_30], r11d
0x1800159fe  cmp     [rsp+88h+arg_38], r8b
0x180015a06  jz      short loc_180015A1A
0x180015a08  lea     edi, [rax+1]
0x180015a0b  mov     [rsp+88h+var_60], eax
0x180015a0f  mov     [rsp+88h+arg_0], edi
0x180015a16  mov     eax, edi
0x180015a18  jmp     short loc_180015A1F
0x180015a1a  mov     [rsp+88h+var_60], r11d
0x180015a1f  mov     ecx, r10d
0x180015a22  and     ecx, 2
0x180015a25  test    bl, r10b
0x180015a28  jnz     short loc_180015A35
0x180015a2a  test    ecx, ecx
0x180015a2c  jnz     short loc_180015A35
0x180015a2e  mov     r14d, r11d
0x180015a31  mov     esi, eax
0x180015a33  jmp     short loc_180015A4C
0x180015a35  lea     edi, [rax+1]
0x180015a38  mov     r14d, eax
0x180015a3b  mov     [rsp+88h+arg_0], edi
0x180015a42  mov     esi, edi
0x180015a44  test    ecx, ecx
0x180015a46  jz      short loc_180015A4C
0x180015a48  mov     [rsp+88h+var_68], ebx
0x180015a4c  test    esi, esi
0x180015a4e  jz      loc_180015C81
0x180015a54  lea     ecx, [rsi+rsi*4]
0x180015a57  shl     ecx, 3
0x180015a5a  call    cs:__imp_DiscpAllocMemory
0x180015a60  mov     [rsp+88h+var_58], rax
0x180015a65  mov     rbx, rax
0x180015a68  test    rax, rax
0x180015a6b  jz      loc_180015C81
0x180015a71  mov     eax, esi
0x180015a73  xor     edx, edx; Val
0x180015a75  mov     rcx, rbx; void *
0x180015a78  lea     r8, [rax+rax*4]
0x180015a7c  shl     r8, 3; Size
0x180015a80  call    memset_0
0x180015a85  mov     esi, [rsp+88h+var_68]
0x180015a89  cmp     r15d, 0FFFFh
0x180015a90  jz      short loc_180015ACD
0x180015a92  mov     r8d, [rsp+88h+arg_10]
0x180015a9a  mov     edx, [rsp+88h+arg_8]
0x180015aa1  mov     eax, r15d
0x180015aa4  lea     rcx, [rax+rax*4]
0x180015aa8  lea     r9, [rbx+rcx*8]
0x180015aac  lea     rcx, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x180015ab3  test    esi, esi
0x180015ab5  jnz     short loc_180015ABE
0x180015ab7  lea     rcx, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x180015abe  call    DiscpFilterConditionIpAddressV4Fill
0x180015ac3  mov     ebp, eax
0x180015ac5  test    eax, eax
0x180015ac7  jnz     loc_180015C6F
0x180015acd  mov     r15d, 0FFFFh
0x180015ad3  cmp     r13d, r15d
0x180015ad6  jz      short loc_180015B13
0x180015ad8  mov     r8d, [rsp+88h+arg_20]
0x180015ae0  lea     rcx, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x180015ae7  mov     eax, r13d
0x180015aea  lea     rdx, [rax+rax*4]
0x180015aee  lea     r9, [rbx+rdx*8]
0x180015af2  mov     edx, [rsp+88h+arg_18]
0x180015af9  test    esi, esi
0x180015afb  jnz     short loc_180015B04
0x180015afd  lea     rcx, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x180015b04  call    DiscpFilterConditionIpAddressV4Fill
0x180015b09  mov     ebp, eax
0x180015b0b  test    eax, eax
0x180015b0d  jnz     loc_180015C6F
0x180015b13  mov     eax, [rsp+88h+var_64]
0x180015b17  cmp     eax, r15d
0x180015b1a  jz      short loc_180015B75
0x180015b1c  movzx   r8d, [rsp+88h+arg_28]
0x180015b25  lea     rdx, [rax+rax*4]
0x180015b29  xor     eax, eax
0x180015b2b  xorps   xmm0, xmm0
0x180015b2e  movups  xmmword ptr [rbx+rdx*8], xmm0
0x180015b32  movups  xmmword ptr [rbx+rdx*8+10h], xmm0
0x180015b37  mov     [rbx+rdx*8+20h], rax
0x180015b3c  movzx   eax, r8w
0x180015b40  test    esi, esi
0x180015b42  jz      short loc_180015B4D
0x180015b44  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x180015b4b  jmp     short loc_180015B54
0x180015b4d  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x180015b54  movdqu  xmmword ptr [rbx+rdx*8], xmm0
0x180015b59  neg     ax
0x180015b5c  sbb     ecx, ecx
0x180015b5e  not     ecx
0x180015b60  and     ecx, 3
0x180015b63  mov     [rbx+rdx*8+10h], ecx
0x180015b67  mov     [rbx+rdx*8+20h], r8w
0x180015b6d  mov     dword ptr [rbx+rdx*8+18h], 2
0x180015b75  mov     eax, [rsp+88h+arg_30]
0x180015b7c  cmp     eax, r15d
0x180015b7f  jz      short loc_180015BD1
0x180015b81  lea     rdx, [rax+rax*4]
0x180015b85  xorps   xmm0, xmm0
0x180015b88  xor     eax, eax
0x180015b8a  movups  xmmword ptr [rbx+rdx*8], xmm0
0x180015b8e  movups  xmmword ptr [rbx+rdx*8+10h], xmm0
0x180015b93  mov     [rbx+rdx*8+20h], rax
0x180015b98  movzx   eax, r12w
0x180015b9c  test    esi, esi
0x180015b9e  jz      short loc_180015BA9
0x180015ba0  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x180015ba7  jmp     short loc_180015BB0
0x180015ba9  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x180015bb0  movdqu  xmmword ptr [rbx+rdx*8], xmm0
0x180015bb5  neg     ax
0x180015bb8  sbb     ecx, ecx
0x180015bba  not     ecx
0x180015bbc  and     ecx, 3
0x180015bbf  mov     [rbx+rdx*8+10h], ecx
0x180015bc3  mov     [rbx+rdx*8+20h], r12w
0x180015bc9  mov     dword ptr [rbx+rdx*8+18h], 2
0x180015bd1  mov     eax, [rsp+88h+var_60]
0x180015bd5  cmp     eax, r15d
0x180015bd8  jz      short loc_180015C1E
0x180015bda  mov     r8b, [rsp+88h+arg_38]
0x180015be2  lea     rdx, [rax+rax*4]
0x180015be6  xor     eax, eax
0x180015be8  xorps   xmm0, xmm0
0x180015beb  movups  xmmword ptr [rbx+rdx*8+10h], xmm0
0x180015bf0  mov     [rbx+rdx*8+20h], rax
0x180015bf5  mov     al, r8b
0x180015bf8  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x180015bff  neg     al
0x180015c01  sbb     ecx, ecx
0x180015c03  not     ecx
0x180015c05  and     ecx, 3
0x180015c08  movdqu  xmmword ptr [rbx+rdx*8], xmm0
0x180015c0d  mov     [rbx+rdx*8+10h], ecx
0x180015c11  mov     dword ptr [rbx+rdx*8+18h], 1
0x180015c19  mov     [rbx+rdx*8+20h], r8b
0x180015c1e  cmp     r14d, r15d
0x180015c21  jz      short loc_180015C56
0x180015c23  xorps   xmm0, xmm0
0x180015c26  mov     eax, r14d
0x180015c29  lea     rcx, [rax+rax*4]
0x180015c2d  xor     eax, eax
0x180015c2f  movups  xmmword ptr [rbx+rcx*8], xmm0
0x180015c33  movups  xmmword ptr [rbx+rcx*8+10h], xmm0
0x180015c38  mov     [rbx+rcx*8+20h], rax
0x180015c3d  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS_TYPE.Data1
0x180015c44  mov     dword ptr [rbx+rcx*8+18h], 1
0x180015c4c  mov     byte ptr [rbx+rcx*8+20h], 1
0x180015c51  movdqu  xmmword ptr [rbx+rcx*8], xmm0
0x180015c56  mov     rax, [rsp+88h+arg_40]
0x180015c5e  mov     [rax], rbx
0x180015c61  mov     rax, [rsp+88h+arg_48]
0x180015c69  mov     [rax], edi
0x180015c6b  test    ebp, ebp
0x180015c6d  jz      short loc_180015C81
0x180015c6f  lea     rdx, [rsp+88h+arg_0]
0x180015c77  lea     rcx, [rsp+88h+var_58]
0x180015c7c  call    DiscpFilterConditionDestroy
0x180015c81  mov     eax, ebp
0x180015c83  add     rsp, 48h
0x180015c87  pop     r15
0x180015c89  pop     r14
0x180015c8b  pop     r13
0x180015c8d  pop     r12
0x180015c8f  pop     rdi
0x180015c90  pop     rsi
0x180015c91  pop     rbp
0x180015c92  pop     rbx
0x180015c93  retn
```
