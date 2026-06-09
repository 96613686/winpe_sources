# EtwpEventWriteFull

- ea: `0x180092790`
- end: `0x180092b0e`
- name: `EtwpEventWriteFull`
- size: `894`
- prototype: ``
- caller_count: `14`
- callee_count: `5`
- tags: ``

## callers

- `0x180001008`
- `0x180002120`
- `0x1800918b0`
- `0x180091900`
- `0x1800b7f20`
- `0x1800b8050`
- `0x1800d9d08`
- `0x1800e53c0`
- `0x18011fbd0`
- `0x1801370a8`
- `0x180137150`
- `0x18014ef38`
- `0x18014efd0`
- `0x18015d260`

## callees

- `0x180035b00`
- `0x180092790`
- `0x180092b20`
- `0x18015f690`
- `0x180162810`

## pseudocode

```c
__int64 __fastcall EtwpEventWriteFull(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int16 a5,
        _GUID *a6,
        __int128 *a7,
        unsigned int a8,
        __int64 a9)
{
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned __int64 v13; // r8
  __int64 v14; // rbx
  unsigned int v15; // r9d
  unsigned __int8 v16; // al
  char v17; // di
  unsigned __int8 v18; // al
  _GUID ActivityId; // xmm0
  __int128 v20; // xmm0
  NTSTATUS v21; // eax
  unsigned int i; // edx
  __int64 v23; // rax
  __int64 v24; // r8
  _OWORD v27[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+80h] [rbp-80h]
  __int128 v29; // [rsp+90h] [rbp-70h]
  _GUID v30; // [rsp+A0h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-50h]
  __int128 v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
  __int128 v34; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v35[7]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v36; // [rsp+160h] [rbp+60h]

  v33 = 0;
  v36 = 0;
  memset(v27, 0, sizeof(v27));
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v34 = 0;
  memset(v35, 0, sizeof(v35));
  if ( a2 )
  {
    DWORD2(v28) = *(_DWORD *)a2;
    BYTE12(v28) = *(_BYTE *)(a2 + 4);
    *(_WORD *)((char *)&v28 + 13) = *(_WORD *)(a2 + 5);
    HIBYTE(v28) = *(_BYTE *)(a2 + 7);
    *(_QWORD *)&v29 = *(_QWORD *)(a2 + 8);
    v10 = ((unsigned int)a1 >> 1) & 7;
    v11 = qword_1801C62A0[v10];
    if ( ((v11 != 0 && (unsigned int)a1 >> 4 < dword_1801934D0[v10]) & (unsigned __int8)a1) == 0 )
      return 6;
    v13 = (unsigned __int64)(unsigned int)a1 >> 4;
    v14 = 0;
    if ( (*(_QWORD *)(v11 + 8 * v13) & 1) == 0 )
      v14 = *(_QWORD *)(v11 + 8 * v13);
    if ( !v14 || WORD2(a1) != *(_WORD *)(v14 + 84) )
      return 6;
    v15 = 0;
    if ( *(_BYTE *)(v14 + 236)
      && ((v16 = *(_BYTE *)(v14 + 237), BYTE12(v28) <= v16) || !v16)
      && ((*(_BYTE *)(v14 + 232) & 0x40) != 0 && !(_QWORD)v29
       || ((unsigned __int64)v29 & *(_QWORD *)(v14 + 224)) != 0
       && ((unsigned __int64)v29 & *(_QWORD *)(v14 + 216)) == *(_QWORD *)(v14 + 216)) )
    {
      v17 = 1;
      v15 = EtwpWriteToPrivateBuffers((_BYTE *)v14, (_OWORD *)a2, a5, WORD2(a3), 0, a6, a7, a8, a9, (__int64)&v34);
      if ( v15 )
      {
LABEL_28:
        for ( i = 0; i < (unsigned int)v36; ++i )
        {
          v23 = 2LL * i;
          v24 = *(_QWORD *)&v35[v23 - 1];
          if ( v15 )
            *(_WORD *)(*((_QWORD *)&v34 + 4 * i + 1) + 2LL) = -16371;
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v35[v23] + 12LL));
          _InterlockedDecrement((volatile signed __int32 *)(16LL * *(unsigned int *)(v24 + 20) + EtwpLoggerArray + 8));
        }
        return v15;
      }
    }
    else
    {
      v17 = 0;
    }
    if ( *(_BYTE *)(v14 + 116) )
    {
      v18 = *(_BYTE *)(v14 + 117);
      if ( (BYTE12(v28) <= v18 || !v18)
        && ((*(_BYTE *)(v14 + 112) & 0x40) != 0 && !(_QWORD)v29
         || ((unsigned __int64)v29 & *(_QWORD *)(v14 + 104)) != 0
         && ((unsigned __int64)v29 & *(_QWORD *)(v14 + 96)) == *(_QWORD *)(v14 + 96)) )
      {
        WORD3(v27[0]) = a5;
        WORD2(v27[0]) = 0;
        DWORD1(v31) = a8;
        *((_QWORD *)&v31 + 1) = a9;
        if ( a6 )
          ActivityId = *a6;
        else
          ActivityId = NtCurrentTeb()->ActivityId;
        LOBYTE(v31) = 0;
        v30 = ActivityId;
        if ( a7 )
        {
          v20 = *a7;
          LOBYTE(v31) = 1;
          v32 = v20;
        }
        WORD1(v31) = a3;
        LODWORD(v33) = a4;
        v21 = NtTraceEvent(*(_QWORD *)(v14 + 88), 768, 120, v27);
        if ( v21 )
          v15 = RtlNtStatusToDosError(v21);
        else
          v15 = 0;
      }
    }
    if ( !v17 )
      return v15;
    goto LABEL_28;
  }
  return 87;
}

```

## disassembly

```asm
0x180092790  push    rbp
0x180092792  push    rsi
0x180092793  push    r12
0x180092795  push    r13
0x180092797  lea     rbp, [rsp-0A8h]
0x18009279f  sub     rsp, 1A8h
0x1800927a6  mov     rax, cs:__security_cookie
0x1800927ad  xor     rax, rsp
0x1800927b0  mov     [rbp+0C0h+var_50], rax
0x1800927b4  mov     r12, [rbp+0C0h+arg_28]
0x1800927bb  xorps   xmm1, xmm1
0x1800927be  mov     rsi, [rbp+0C0h+arg_30]
0x1800927c5  xorps   xmm0, xmm0
0x1800927c8  mov     r13, [rbp+0C0h+arg_40]
0x1800927cf  xor     eax, eax
0x1800927d1  mov     [rsp+1C0h+var_170], r9d
0x1800927d6  mov     r11, rdx
0x1800927d9  mov     [rsp+1C0h+var_168], r8
0x1800927de  mov     r10, rcx
0x1800927e1  mov     [rbp+0C0h+var_F0], rax
0x1800927e5  mov     [rbp+0C0h+var_60], rax
0x1800927e9  movups  [rsp+1C0h+var_160], xmm0
0x1800927ee  movups  [rsp+1C0h+var_150], xmm0
0x1800927f3  movups  [rbp+0C0h+var_140], xmm0
0x1800927f7  movups  [rbp+0C0h+var_130], xmm0
0x1800927fb  movups  [rbp+0C0h+var_120], xmm0
0x1800927ff  movups  [rbp+0C0h+var_110], xmm0
0x180092803  movups  [rbp+0C0h+var_100], xmm0
0x180092807  movups  [rbp+0C0h+var_E0], xmm1
0x18009280b  movups  [rbp+0C0h+var_D0], xmm1
0x18009280f  movups  [rbp+0C0h+var_C0], xmm1
0x180092813  movups  [rbp+0C0h+var_B0], xmm1
0x180092817  movups  [rbp+0C0h+var_A0], xmm1
0x18009281b  movups  [rbp+0C0h+var_90], xmm1
0x18009281f  movups  [rbp+0C0h+var_80], xmm1
0x180092823  movups  [rbp+0C0h+var_70], xmm1
0x180092827  test    rdx, rdx
0x18009282a  jz      loc_180092AF5
0x180092830  mov     eax, [rdx]
0x180092832  xor     ecx, ecx
0x180092834  mov     dword ptr [rbp+0C0h+var_140+8], eax
0x180092837  movzx   eax, byte ptr [rdx+4]
0x18009283b  mov     byte ptr [rbp+0C0h+var_140+0Ch], al
0x18009283e  movzx   eax, word ptr [rdx+5]
0x180092842  mov     word ptr [rbp+0C0h+var_140+0Dh], ax
0x180092846  movzx   eax, byte ptr [rdx+7]
0x18009284a  mov     byte ptr [rbp+0C0h+var_140+0Fh], al
0x18009284d  mov     rax, [rdx+8]
0x180092851  mov     qword ptr [rbp+0C0h+var_130], rax
0x180092855  mov     eax, r10d
0x180092858  shr     eax, 4
0x18009285b  mov     edx, r10d
0x18009285e  shr     rdx, 1
0x180092861  and     edx, 7
0x180092864  mov     [rsp+1C0h+var_20], rbx
0x18009286c  lea     rbx, cs:180000000h
0x180092873  mov     r8d, r10d
0x180092876  mov     r9, rva qword_1801C62A0[rbx+rdx*8]
0x18009287e  cmp     eax, ds:rva dword_1801934D0[rbx+rdx*4]
0x180092885  setb    cl
0x180092888  xor     eax, eax
0x18009288a  test    r9, r9
0x18009288d  setnz   al
0x180092890  and     ecx, eax
0x180092892  test    r10d, ecx
0x180092895  jnz     short loc_1800928BF
0x180092897  mov     eax, 6
0x18009289c  mov     rbx, [rsp+1C0h+var_20]
0x1800928a4  mov     rcx, [rbp+0C0h+var_50]
0x1800928a8  xor     rcx, rsp; StackCookie
0x1800928ab  call    __security_check_cookie
0x1800928b0  add     rsp, 1A8h
0x1800928b7  pop     r13
0x1800928b9  pop     r12
0x1800928bb  pop     rsi
0x1800928bc  pop     rbp
0x1800928bd  retn
0x1800928bf  shr     r8, 4
0x1800928c3  mov     ebx, 0
0x1800928c8  mov     rax, [r9+r8*8]
0x1800928cc  test    al, 1
0x1800928ce  cmovz   rbx, rax
0x1800928d2  test    rbx, rbx
0x1800928d5  jz      short loc_180092897
0x1800928d7  shr     r10, 20h
0x1800928db  cmp     r10w, [rbx+54h]
0x1800928e0  jnz     short loc_180092897
0x1800928e2  mov     [rsp+1C0h+var_30], r14
0x1800928ea  xor     r9d, r9d
0x1800928ed  mov     r14d, [rbp+0C0h+arg_38]
0x1800928f4  mov     [rsp+1C0h+var_38], r15
0x1800928fc  movzx   r15d, [rbp+0C0h+arg_20]
0x180092904  mov     [rsp+1C0h+var_28], rdi
0x18009290c  cmp     [rbx+0ECh], r9b
0x180092913  jz      short loc_18009295A
0x180092915  movzx   eax, byte ptr [rbx+0EDh]
0x18009291c  cmp     byte ptr [rbp+0C0h+var_140+0Ch], al
0x18009291f  ja      loc_180092AD1
0x180092925  test    byte ptr [rbx+0E8h], 40h
0x18009292c  mov     rdx, qword ptr [rbp+0C0h+var_130]
0x180092930  jz      short loc_18009293B
0x180092932  test    rdx, rdx
0x180092935  jz      loc_180092A82
0x18009293b  test    [rbx+0E0h], rdx
0x180092942  jz      short loc_18009295A
0x180092944  mov     rcx, [rbx+0D8h]
0x18009294b  mov     rax, rcx
0x18009294e  and     rax, rdx
0x180092951  cmp     rax, rcx
0x180092954  jz      loc_180092A82
0x18009295a  xor     dil, dil
0x18009295d  cmp     byte ptr [rbx+74h], 0
0x180092961  jz      loc_180092A14
0x180092967  movzx   eax, byte ptr [rbx+75h]
0x18009296b  cmp     byte ptr [rbp+0C0h+var_140+0Ch], al
0x18009296e  ja      loc_180092ADE
0x180092974  test    byte ptr [rbx+70h], 40h
0x180092978  mov     rdx, qword ptr [rbp+0C0h+var_130]
0x18009297c  jz      short loc_180092983
0x18009297e  test    rdx, rdx
0x180092981  jz      short loc_18009299A
0x180092983  test    [rbx+68h], rdx
0x180092987  jz      loc_180092A14
0x18009298d  mov     rax, [rbx+60h]
0x180092991  and     rax, rdx
0x180092994  cmp     rax, [rbx+60h]
0x180092998  jnz     short loc_180092A14
0x18009299a  xor     eax, eax
0x18009299c  mov     word ptr [rsp+1C0h+var_160+6], r15w
0x1800929a2  mov     word ptr [rsp+1C0h+var_160+4], ax
0x1800929a7  mov     dword ptr [rbp+0C0h+var_110+4], r14d
0x1800929ab  mov     qword ptr [rbp+0C0h+var_110+8], r13
0x1800929af  test    r12, r12
0x1800929b2  jnz     loc_180092AEB
0x1800929b8  mov     rax, gs:30h
0x1800929c1  movups  xmm0, xmmword ptr [rax+1710h]
0x1800929c8  mov     byte ptr [rbp+0C0h+var_110], 0
0x1800929cc  movups  [rbp+0C0h+var_120], xmm0
0x1800929d0  test    rsi, rsi
0x1800929d3  jz      short loc_1800929E0
0x1800929d5  movups  xmm0, xmmword ptr [rsi]
0x1800929d8  mov     byte ptr [rbp+0C0h+var_110], 1
0x1800929dc  movups  [rbp+0C0h+var_100], xmm0
0x1800929e0  mov     rax, [rsp+1C0h+var_168]
0x1800929e5  lea     r9, [rsp+1C0h+var_160]
0x1800929ea  mov     word ptr [rbp+0C0h+var_110+2], ax
0x1800929ee  mov     edx, 300h
0x1800929f3  mov     eax, [rsp+1C0h+var_170]
0x1800929f7  mov     r8d, 78h ; 'x'
0x1800929fd  mov     dword ptr [rbp+0C0h+var_F0], eax
0x180092a00  mov     rcx, [rbx+58h]
0x180092a04  call    NtTraceEvent
0x180092a09  test    eax, eax
0x180092a0b  jnz     loc_180092AFF
0x180092a11  xor     r9d, r9d
0x180092a14  test    dil, dil
0x180092a17  jz      short loc_180092A62
0x180092a19  xor     edx, edx
0x180092a1b  cmp     dword ptr [rbp+0C0h+var_60], edx
0x180092a1e  jbe     short loc_180092A62
0x180092a20  mov     eax, edx
0x180092a22  shl     rax, 5
0x180092a26  mov     r8, qword ptr [rbp+rax+0C0h+var_E0]
0x180092a2b  test    r9d, r9d
0x180092a2e  jz      short loc_180092A3B
0x180092a30  mov     rcx, qword ptr [rbp+rax+0C0h+var_E0+8]
0x180092a35  mov     word ptr [rcx+2], 0C00Dh
0x180092a3b  lea     rcx, [rbp+0C0h+var_D0]
0x180092a3f  inc     edx
0x180092a41  mov     rcx, [rcx+rax]
0x180092a45  lock dec dword ptr [rcx+0Ch]
0x180092a49  mov     ecx, [r8+14h]
0x180092a4d  mov     rax, cs:EtwpLoggerArray
0x180092a54  shl     rcx, 4
0x180092a58  lock dec dword ptr [rcx+rax+8]
0x180092a5d  cmp     edx, dword ptr [rbp+0C0h+var_60]
0x180092a60  jb      short loc_180092A20
0x180092a62  mov     rdi, [rsp+1C0h+var_28]
0x180092a6a  mov     eax, r9d
0x180092a6d  mov     r14, [rsp+1C0h+var_30]
0x180092a75  mov     r15, [rsp+1C0h+var_38]
0x180092a7d  jmp     loc_18009289C
0x180092a82  mov     r9, [rsp+1C0h+var_168]
0x180092a87  lea     rcx, [rbp+0C0h+var_E0]
0x180092a8b  mov     [rsp+1C0h+var_178], rcx
0x180092a90  xor     eax, eax
0x180092a92  mov     [rsp+1C0h+var_180], r13
0x180092a97  movzx   r8d, r15w
0x180092a9b  mov     [rsp+1C0h+var_188], r14d
0x180092aa0  mov     rdx, r11
0x180092aa3  mov     [rsp+1C0h+var_190], rsi
0x180092aa8  mov     rcx, rbx
0x180092aab  mov     [rsp+1C0h+var_198], r12
0x180092ab0  mov     dil, 1
0x180092ab3  shr     r9, 20h
0x180092ab7  mov     [rsp+1C0h+var_1A0], ax
0x180092abc  call    EtwpWriteToPrivateBuffers
0x180092ac1  mov     r9d, eax
0x180092ac4  test    eax, eax
0x180092ac6  jnz     loc_180092A19
0x180092acc  jmp     loc_18009295D
0x180092ad1  test    al, al
0x180092ad3  jnz     loc_18009295A
0x180092ad9  jmp     loc_180092925
0x180092ade  test    al, al
0x180092ae0  jnz     loc_180092A14
0x180092ae6  jmp     loc_180092974
0x180092aeb  movups  xmm0, xmmword ptr [r12]
0x180092af0  jmp     loc_1800929C8
0x180092af5  mov     eax, 57h ; 'W'
0x180092afa  jmp     loc_1800928A4
0x180092aff  mov     ecx, eax; Status
0x180092b01  call    RtlNtStatusToDosError
0x180092b06  mov     r9d, eax
0x180092b09  jmp     loc_180092A14
```
