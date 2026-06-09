# EtwpEventWriteFull

- ea: `0x180086330`
- end: `0x1800866ae`
- name: `EtwpEventWriteFull`
- size: `894`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, unsigned __int16, _GUID *, __int128 *, int, __int64)`
- caller_count: `14`
- callee_count: `5`
- tags: ``

## callers

- `0x180001008`
- `0x180002120`
- `0x180085450`
- `0x1800854a0`
- `0x1800ad3e0`
- `0x1800ad510`
- `0x1800d9288`
- `0x1800e5040`
- `0x18011f0e0`
- `0x1801365b8`
- `0x180136660`
- `0x18014e5d8`
- `0x18014e670`
- `0x18015ca50`

## callees

- `0x1800369a0`
- `0x180086330`
- `0x1800866c0`
- `0x18015ee80`
- `0x180162000`

## pseudocode

```c
__int64 __fastcall EtwpEventWriteFull(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int16 a5,
        _GUID *a6,
        __int128 *a7,
        int a8,
        __int64 a9)
{
  int v9; // r11d
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned __int64 v13; // r8
  __int64 v14; // rbx
  ULONG v15; // r9d
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

  v9 = a2;
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
    v11 = qword_1801C62B0[v10];
    if ( ((v11 != 0 && (unsigned int)a1 >> 4 < dword_1801930E0[v10]) & (unsigned __int8)a1) == 0 )
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
      v15 = EtwpWriteToPrivateBuffers(v14, v9, a5, HIDWORD(a3), 0, (__int64)a6, (__int64)a7, a8, a9, (__int64)&v34);
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
0x180086330  push    rbp
0x180086332  push    rsi
0x180086333  push    r12
0x180086335  push    r13
0x180086337  lea     rbp, [rsp-0A8h]
0x18008633f  sub     rsp, 1A8h
0x180086346  mov     rax, cs:__security_cookie
0x18008634d  xor     rax, rsp
0x180086350  mov     [rbp+0C0h+var_50], rax
0x180086354  mov     r12, [rbp+0C0h+arg_28]
0x18008635b  xorps   xmm1, xmm1
0x18008635e  mov     rsi, [rbp+0C0h+arg_30]
0x180086365  xorps   xmm0, xmm0
0x180086368  mov     r13, [rbp+0C0h+arg_40]
0x18008636f  xor     eax, eax
0x180086371  mov     [rsp+1C0h+var_170], r9d
0x180086376  mov     r11, rdx
0x180086379  mov     [rsp+1C0h+var_168], r8
0x18008637e  mov     r10, rcx
0x180086381  mov     [rbp+0C0h+var_F0], rax
0x180086385  mov     [rbp+0C0h+var_60], rax
0x180086389  movups  [rsp+1C0h+var_160], xmm0
0x18008638e  movups  [rsp+1C0h+var_150], xmm0
0x180086393  movups  [rbp+0C0h+var_140], xmm0
0x180086397  movups  [rbp+0C0h+var_130], xmm0
0x18008639b  movups  [rbp+0C0h+var_120], xmm0
0x18008639f  movups  [rbp+0C0h+var_110], xmm0
0x1800863a3  movups  [rbp+0C0h+var_100], xmm0
0x1800863a7  movups  [rbp+0C0h+var_E0], xmm1
0x1800863ab  movups  [rbp+0C0h+var_D0], xmm1
0x1800863af  movups  [rbp+0C0h+var_C0], xmm1
0x1800863b3  movups  [rbp+0C0h+var_B0], xmm1
0x1800863b7  movups  [rbp+0C0h+var_A0], xmm1
0x1800863bb  movups  [rbp+0C0h+var_90], xmm1
0x1800863bf  movups  [rbp+0C0h+var_80], xmm1
0x1800863c3  movups  [rbp+0C0h+var_70], xmm1
0x1800863c7  test    rdx, rdx
0x1800863ca  jz      loc_180086695
0x1800863d0  mov     eax, [rdx]
0x1800863d2  xor     ecx, ecx
0x1800863d4  mov     dword ptr [rbp+0C0h+var_140+8], eax
0x1800863d7  movzx   eax, byte ptr [rdx+4]
0x1800863db  mov     byte ptr [rbp+0C0h+var_140+0Ch], al
0x1800863de  movzx   eax, word ptr [rdx+5]
0x1800863e2  mov     word ptr [rbp+0C0h+var_140+0Dh], ax
0x1800863e6  movzx   eax, byte ptr [rdx+7]
0x1800863ea  mov     byte ptr [rbp+0C0h+var_140+0Fh], al
0x1800863ed  mov     rax, [rdx+8]
0x1800863f1  mov     qword ptr [rbp+0C0h+var_130], rax
0x1800863f5  mov     eax, r10d
0x1800863f8  shr     eax, 4
0x1800863fb  mov     edx, r10d
0x1800863fe  shr     rdx, 1
0x180086401  and     edx, 7
0x180086404  mov     [rsp+1C0h+var_20], rbx
0x18008640c  lea     rbx, cs:180000000h
0x180086413  mov     r8d, r10d
0x180086416  mov     r9, rva qword_1801C62B0[rbx+rdx*8]
0x18008641e  cmp     eax, ds:rva dword_1801930E0[rbx+rdx*4]
0x180086425  setb    cl
0x180086428  xor     eax, eax
0x18008642a  test    r9, r9
0x18008642d  setnz   al
0x180086430  and     ecx, eax
0x180086432  test    r10d, ecx
0x180086435  jnz     short loc_18008645F
0x180086437  mov     eax, 6
0x18008643c  mov     rbx, [rsp+1C0h+var_20]
0x180086444  mov     rcx, [rbp+0C0h+var_50]
0x180086448  xor     rcx, rsp; StackCookie
0x18008644b  call    __security_check_cookie
0x180086450  add     rsp, 1A8h
0x180086457  pop     r13
0x180086459  pop     r12
0x18008645b  pop     rsi
0x18008645c  pop     rbp
0x18008645d  retn
0x18008645f  shr     r8, 4
0x180086463  mov     ebx, 0
0x180086468  mov     rax, [r9+r8*8]
0x18008646c  test    al, 1
0x18008646e  cmovz   rbx, rax
0x180086472  test    rbx, rbx
0x180086475  jz      short loc_180086437
0x180086477  shr     r10, 20h
0x18008647b  cmp     r10w, [rbx+54h]
0x180086480  jnz     short loc_180086437
0x180086482  mov     [rsp+1C0h+var_30], r14
0x18008648a  xor     r9d, r9d
0x18008648d  mov     r14d, [rbp+0C0h+arg_38]
0x180086494  mov     [rsp+1C0h+var_38], r15
0x18008649c  movzx   r15d, [rbp+0C0h+arg_20]
0x1800864a4  mov     [rsp+1C0h+var_28], rdi
0x1800864ac  cmp     [rbx+0ECh], r9b
0x1800864b3  jz      short loc_1800864FA
0x1800864b5  movzx   eax, byte ptr [rbx+0EDh]
0x1800864bc  cmp     byte ptr [rbp+0C0h+var_140+0Ch], al
0x1800864bf  ja      loc_180086671
0x1800864c5  test    byte ptr [rbx+0E8h], 40h
0x1800864cc  mov     rdx, qword ptr [rbp+0C0h+var_130]
0x1800864d0  jz      short loc_1800864DB
0x1800864d2  test    rdx, rdx
0x1800864d5  jz      loc_180086622
0x1800864db  test    [rbx+0E0h], rdx
0x1800864e2  jz      short loc_1800864FA
0x1800864e4  mov     rcx, [rbx+0D8h]
0x1800864eb  mov     rax, rcx
0x1800864ee  and     rax, rdx
0x1800864f1  cmp     rax, rcx
0x1800864f4  jz      loc_180086622
0x1800864fa  xor     dil, dil
0x1800864fd  cmp     byte ptr [rbx+74h], 0
0x180086501  jz      loc_1800865B4
0x180086507  movzx   eax, byte ptr [rbx+75h]
0x18008650b  cmp     byte ptr [rbp+0C0h+var_140+0Ch], al
0x18008650e  ja      loc_18008667E
0x180086514  test    byte ptr [rbx+70h], 40h
0x180086518  mov     rdx, qword ptr [rbp+0C0h+var_130]
0x18008651c  jz      short loc_180086523
0x18008651e  test    rdx, rdx
0x180086521  jz      short loc_18008653A
0x180086523  test    [rbx+68h], rdx
0x180086527  jz      loc_1800865B4
0x18008652d  mov     rax, [rbx+60h]
0x180086531  and     rax, rdx
0x180086534  cmp     rax, [rbx+60h]
0x180086538  jnz     short loc_1800865B4
0x18008653a  xor     eax, eax
0x18008653c  mov     word ptr [rsp+1C0h+var_160+6], r15w
0x180086542  mov     word ptr [rsp+1C0h+var_160+4], ax
0x180086547  mov     dword ptr [rbp+0C0h+var_110+4], r14d
0x18008654b  mov     qword ptr [rbp+0C0h+var_110+8], r13
0x18008654f  test    r12, r12
0x180086552  jnz     loc_18008668B
0x180086558  mov     rax, gs:30h
0x180086561  movups  xmm0, xmmword ptr [rax+1710h]
0x180086568  mov     byte ptr [rbp+0C0h+var_110], 0
0x18008656c  movups  [rbp+0C0h+var_120], xmm0
0x180086570  test    rsi, rsi
0x180086573  jz      short loc_180086580
0x180086575  movups  xmm0, xmmword ptr [rsi]
0x180086578  mov     byte ptr [rbp+0C0h+var_110], 1
0x18008657c  movups  [rbp+0C0h+var_100], xmm0
0x180086580  mov     rax, [rsp+1C0h+var_168]
0x180086585  lea     r9, [rsp+1C0h+var_160]
0x18008658a  mov     word ptr [rbp+0C0h+var_110+2], ax
0x18008658e  mov     edx, 300h
0x180086593  mov     eax, [rsp+1C0h+var_170]
0x180086597  mov     r8d, 78h ; 'x'
0x18008659d  mov     dword ptr [rbp+0C0h+var_F0], eax
0x1800865a0  mov     rcx, [rbx+58h]
0x1800865a4  call    NtTraceEvent
0x1800865a9  test    eax, eax
0x1800865ab  jnz     loc_18008669F
0x1800865b1  xor     r9d, r9d
0x1800865b4  test    dil, dil
0x1800865b7  jz      short loc_180086602
0x1800865b9  xor     edx, edx
0x1800865bb  cmp     dword ptr [rbp+0C0h+var_60], edx
0x1800865be  jbe     short loc_180086602
0x1800865c0  mov     eax, edx
0x1800865c2  shl     rax, 5
0x1800865c6  mov     r8, qword ptr [rbp+rax+0C0h+var_E0]
0x1800865cb  test    r9d, r9d
0x1800865ce  jz      short loc_1800865DB
0x1800865d0  mov     rcx, qword ptr [rbp+rax+0C0h+var_E0+8]
0x1800865d5  mov     word ptr [rcx+2], 0C00Dh
0x1800865db  lea     rcx, [rbp+0C0h+var_D0]
0x1800865df  inc     edx
0x1800865e1  mov     rcx, [rcx+rax]
0x1800865e5  lock dec dword ptr [rcx+0Ch]
0x1800865e9  mov     ecx, [r8+14h]
0x1800865ed  mov     rax, cs:EtwpLoggerArray
0x1800865f4  shl     rcx, 4
0x1800865f8  lock dec dword ptr [rcx+rax+8]
0x1800865fd  cmp     edx, dword ptr [rbp+0C0h+var_60]
0x180086600  jb      short loc_1800865C0
0x180086602  mov     rdi, [rsp+1C0h+var_28]
0x18008660a  mov     eax, r9d
0x18008660d  mov     r14, [rsp+1C0h+var_30]
0x180086615  mov     r15, [rsp+1C0h+var_38]
0x18008661d  jmp     loc_18008643C
0x180086622  mov     r9, [rsp+1C0h+var_168]
0x180086627  lea     rcx, [rbp+0C0h+var_E0]
0x18008662b  mov     [rsp+1C0h+var_178], rcx
0x180086630  xor     eax, eax
0x180086632  mov     [rsp+1C0h+var_180], r13
0x180086637  movzx   r8d, r15w
0x18008663b  mov     [rsp+1C0h+var_188], r14d
0x180086640  mov     rdx, r11
0x180086643  mov     [rsp+1C0h+var_190], rsi
0x180086648  mov     rcx, rbx
0x18008664b  mov     [rsp+1C0h+var_198], r12
0x180086650  mov     dil, 1
0x180086653  shr     r9, 20h
0x180086657  mov     [rsp+1C0h+var_1A0], ax
0x18008665c  call    EtwpWriteToPrivateBuffers
0x180086661  mov     r9d, eax
0x180086664  test    eax, eax
0x180086666  jnz     loc_1800865B9
0x18008666c  jmp     loc_1800864FD
0x180086671  test    al, al
0x180086673  jnz     loc_1800864FA
0x180086679  jmp     loc_1800864C5
0x18008667e  test    al, al
0x180086680  jnz     loc_1800865B4
0x180086686  jmp     loc_180086514
0x18008668b  movups  xmm0, xmmword ptr [r12]
0x180086690  jmp     loc_180086568
0x180086695  mov     eax, 57h ; 'W'
0x18008669a  jmp     loc_180086444
0x18008669f  mov     ecx, eax; Status
0x1800866a1  call    RtlNtStatusToDosError
0x1800866a6  mov     r9d, eax
0x1800866a9  jmp     loc_1800865B4
```
