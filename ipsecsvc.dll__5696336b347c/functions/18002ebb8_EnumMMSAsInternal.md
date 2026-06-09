# EnumMMSAsInternal

- ea: `0x18002ebb8`
- end: `0x18002efb3`
- name: `EnumMMSAsInternal`
- size: `1019`
- prototype: `__int64 __fastcall(__int64, _QWORD *, UINT32 *, UINT32 *, UINT32 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180012000`

## callees

- `0x18000e510`
- `0x180017534`
- `0x1800175dc`
- `0x18002db18`
- `0x18002dba4`
- `0x18002ebb8`
- `0x180042ef8`
- `0x18004446c`
- `0x18004d05e`
- `0x18004d090`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18002ef57`
- `fwpuclnt!FwpmEngineClose0` at `0x18002ef57`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002ef4c`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002ef4c`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002ef8b`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002ef8b`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18002ecae`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18002ecae`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002ec5a`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002ec5a`
- `fwpuclnt!IkeextSaEnum0` at `0x18002ed0d`
- `fwpuclnt!IkeextSaEnum0` at `0x18002ed0d`

## pseudocode

```c
__int64 __fastcall EnumMMSAsInternal(__int64 a1, _QWORD *a2, UINT32 *a3, UINT32 *a4, UINT32 *a5)
{
  UINT32 v5; // esi
  __int64 v9; // rdi
  UINT32 v10; // r14d
  DWORD v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  IKEEXT_SA_DETAILS0 *v14; // rcx
  __int64 v15; // rcx
  UINT32 *v16; // rax
  UINT32 numEntriesReturned; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE engineHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h]
  IKEEXT_SA_DETAILS0 **entries; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE enumHandle; // [rsp+50h] [rbp-B0h] BYREF
  size_t Size; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h]
  UINT32 *v25; // [rsp+68h] [rbp-98h]
  _OWORD v26[14]; // [rsp+70h] [rbp-90h] BYREF

  v5 = 0;
  v24 = a1;
  v25 = a4;
  engineHandle = 0;
  enumHandle = 0;
  entries = 0;
  numEntriesReturned = 0;
  v9 = 0;
  v20 = 0;
  memset_0(v26, 0, sizeof(v26));
  v10 = 0;
  Size = 0;
  if ( *a5 )
    goto LABEL_42;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a2 = 0;
  v11 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v13 = 25;
LABEL_6:
      WPP_SF_d(v12[2], v13, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v11);
      goto LABEL_43;
    }
    goto LABEL_43;
  }
  v11 = IkeextSaCreateEnumHandle0(engineHandle, 0, &enumHandle);
  if ( v11 == -2144206780 )
  {
    v11 = 0;
    goto LABEL_43;
  }
  if ( !v11 )
  {
    v11 = IkeextSaEnum0(engineHandle, enumHandle, 0xFFFFFFFF, &entries, &numEntriesReturned);
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = 27;
        goto LABEL_6;
      }
      goto LABEL_43;
    }
    if ( numEntriesReturned && entries )
    {
      v11 = NsuSizeTMultiply(numEntriesReturned, 224, &Size);
      if ( v11 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v13 = 28;
          goto LABEL_6;
        }
      }
      else
      {
        v11 = SPDApiBufferAllocate(Size);
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v11);
          }
          v9 = v20;
        }
        else
        {
          v9 = v20;
          while ( v5 < numEntriesReturned )
          {
            v14 = entries[v5];
            if ( v14->keyModuleType != IKEEXT_KEY_MODULE_IKEV2 )
            {
              v11 = ConvertMMSAFromBfeToSpd(v14, v26);
              if ( v11 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    30,
                    WPP_c57b73e384023a72e58561d5d38b8882_Traceguids,
                    v11);
                }
                v5 = 0;
                goto LABEL_43;
              }
              if ( (unsigned int)MatchMMSATemplate(v24, v26) )
              {
                v15 = 224LL * v10++;
                *(_OWORD *)(v15 + v9) = v26[0];
                *(_OWORD *)(v15 + v9 + 16) = v26[1];
                *(_OWORD *)(v15 + v9 + 32) = v26[2];
                *(_OWORD *)(v15 + v9 + 48) = v26[3];
                *(_OWORD *)(v15 + v9 + 64) = v26[4];
                *(_OWORD *)(v15 + v9 + 80) = v26[5];
                *(_OWORD *)(v15 + v9 + 96) = v26[6];
                *(_OWORD *)(v15 + v9 + 112) = v26[7];
                *(_OWORD *)(v15 + v9 + 128) = v26[8];
                *(_OWORD *)(v15 + v9 + 144) = v26[9];
                *(_OWORD *)(v15 + v9 + 160) = v26[10];
                *(_OWORD *)(v15 + v9 + 176) = v26[11];
                *(_OWORD *)(v15 + v9 + 192) = v26[12];
                *(_OWORD *)(v15 + v9 + 208) = v26[13];
              }
              else
              {
                CleanupSAEntry(v26);
              }
            }
            ++v5;
          }
          v5 = 0;
          if ( !v10 )
            goto LABEL_42;
          v16 = v25;
          *a2 = v9;
          *a3 = v10;
          *a5 = v10;
          *v16 = v10;
        }
      }
      goto LABEL_43;
    }
LABEL_42:
    v11 = 232;
    goto LABEL_43;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v13 = 26;
    goto LABEL_6;
  }
LABEL_43:
  IkeextSaDestroyEnumHandle0(engineHandle, enumHandle);
  FwpmEngineClose0(engineHandle);
  if ( v11 )
  {
    if ( v10 )
    {
      do
        CleanupSAEntry((void *)(v9 + 224LL * v5++));
      while ( v5 < v10 );
    }
    SPDApiBufferFree(v9);
  }
  FwpmFreeMemory0((void **)&entries);
  return v11;
}

```

## disassembly

```asm
0x18002ebb8  push    rbp
0x18002ebba  push    rbx
0x18002ebbb  push    rsi
0x18002ebbc  push    rdi
0x18002ebbd  push    r12
0x18002ebbf  push    r13
0x18002ebc1  push    r14
0x18002ebc3  push    r15
0x18002ebc5  lea     rbp, [rsp-68h]
0x18002ebca  sub     rsp, 168h
0x18002ebd1  mov     rax, cs:__security_cookie
0x18002ebd8  xor     rax, rsp
0x18002ebdb  mov     [rbp+0A0h+var_50], rax
0x18002ebdf  mov     r15, [rbp+0A0h+arg_20]
0x18002ebe6  xor     esi, esi
0x18002ebe8  mov     rbx, r9
0x18002ebeb  mov     [rsp+1A0h+var_140], rcx
0x18002ebf0  mov     r13, r8
0x18002ebf3  mov     [rsp+1A0h+var_138], rbx
0x18002ebf8  mov     r12, rdx
0x18002ebfb  mov     [rsp+1A0h+var_168], rsi
0x18002ec00  xor     edx, edx; Val
0x18002ec02  mov     [rsp+1A0h+enumHandle], rsi
0x18002ec07  mov     r8d, 0E0h; Size
0x18002ec0d  mov     [rsp+1A0h+entries], rsi
0x18002ec12  lea     rcx, [rsp+1A0h+var_130]; void *
0x18002ec17  mov     [rsp+1A0h+numEntriesReturned], esi
0x18002ec1b  mov     edi, esi
0x18002ec1d  mov     [rsp+1A0h+var_160], rsi
0x18002ec22  call    memset_0
0x18002ec27  mov     r14d, esi
0x18002ec2a  mov     [rsp+1A0h+Size], rsi
0x18002ec2f  cmp     [r15], esi
0x18002ec32  jnz     loc_18002EF3D
0x18002ec38  mov     [r13+0], esi
0x18002ec3c  lea     rax, [rsp+1A0h+var_168]
0x18002ec41  mov     [rbx], esi
0x18002ec43  lea     edx, [rsi+0Ah]; authnService
0x18002ec46  mov     [r15], esi
0x18002ec49  xor     r9d, r9d; session
0x18002ec4c  xor     r8d, r8d; authIdentity
0x18002ec4f  mov     [r12], rsi
0x18002ec53  xor     ecx, ecx; serverName
0x18002ec55  mov     [rsp+1A0h+engineHandle], rax; engineHandle
0x18002ec5a  call    cs:__imp_FwpmEngineOpen0
0x18002ec60  mov     ebx, eax
0x18002ec62  test    eax, eax
0x18002ec64  jz      short loc_18002ECA2
0x18002ec66  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec6d  lea     rax, WPP_GLOBAL_Control
0x18002ec74  cmp     rcx, rax
0x18002ec77  jz      loc_18002EF42
0x18002ec7d  test    byte ptr [rcx+1Ch], 10h
0x18002ec81  jz      loc_18002EF42
0x18002ec87  lea     edx, [rsi+19h]
0x18002ec8a  mov     rcx, [rcx+10h]
0x18002ec8e  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002ec95  mov     r9d, ebx
0x18002ec98  call    WPP_SF_d
0x18002ec9d  jmp     loc_18002EF42
0x18002eca2  mov     rcx, [rsp+1A0h+var_168]; engineHandle
0x18002eca7  lea     r8, [rsp+1A0h+enumHandle]; enumHandle
0x18002ecac  xor     edx, edx; enumTemplate
0x18002ecae  call    cs:__imp_IkeextSaCreateEnumHandle0
0x18002ecb4  mov     ebx, eax
0x18002ecb6  cmp     eax, 80320044h
0x18002ecbb  jnz     short loc_18002ECC4
0x18002ecbd  mov     ebx, esi
0x18002ecbf  jmp     loc_18002EF42
0x18002ecc4  test    ebx, ebx
0x18002ecc6  jz      short loc_18002ECF0
0x18002ecc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eccf  lea     rax, WPP_GLOBAL_Control
0x18002ecd6  cmp     rcx, rax
0x18002ecd9  jz      loc_18002EF42
0x18002ecdf  test    byte ptr [rcx+1Ch], 10h
0x18002ece3  jz      loc_18002EF42
0x18002ece9  mov     edx, 1Ah
0x18002ecee  jmp     short loc_18002EC8A
0x18002ecf0  mov     rdx, [rsp+1A0h+enumHandle]; enumHandle
0x18002ecf5  lea     rax, [rsp+1A0h+numEntriesReturned]
0x18002ecfa  mov     rcx, [rsp+1A0h+var_168]; engineHandle
0x18002ecff  lea     r9, [rsp+1A0h+entries]; entries
0x18002ed04  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x18002ed08  mov     [rsp+1A0h+engineHandle], rax; numEntriesReturned
0x18002ed0d  call    cs:__imp_IkeextSaEnum0
0x18002ed13  mov     ebx, eax
0x18002ed15  test    eax, eax
0x18002ed17  jz      short loc_18002ED44
0x18002ed19  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed20  lea     rax, WPP_GLOBAL_Control
0x18002ed27  cmp     rcx, rax
0x18002ed2a  jz      loc_18002EF42
0x18002ed30  test    byte ptr [rcx+1Ch], 10h
0x18002ed34  jz      loc_18002EF42
0x18002ed3a  mov     edx, 1Bh
0x18002ed3f  jmp     loc_18002EC8A
0x18002ed44  mov     eax, [rsp+1A0h+numEntriesReturned]
0x18002ed48  test    eax, eax
0x18002ed4a  jz      loc_18002EF3D
0x18002ed50  cmp     [rsp+1A0h+entries], rsi
0x18002ed55  jz      loc_18002EF3D
0x18002ed5b  mov     ecx, eax
0x18002ed5d  lea     r8, [rsp+1A0h+Size]
0x18002ed62  mov     edx, 0E0h
0x18002ed67  call    NsuSizeTMultiply
0x18002ed6c  mov     ebx, eax
0x18002ed6e  test    eax, eax
0x18002ed70  jz      short loc_18002ED9D
0x18002ed72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed79  lea     rax, WPP_GLOBAL_Control
0x18002ed80  cmp     rcx, rax
0x18002ed83  jz      loc_18002EF42
0x18002ed89  test    byte ptr [rcx+1Ch], 10h
0x18002ed8d  jz      loc_18002EF42
0x18002ed93  mov     edx, 1Ch
0x18002ed98  jmp     loc_18002EC8A
0x18002ed9d  mov     rcx, [rsp+1A0h+Size]; Size
0x18002eda2  lea     rdx, [rsp+1A0h+var_160]
0x18002eda7  call    SPDApiBufferAllocate
0x18002edac  mov     ebx, eax
0x18002edae  test    eax, eax
0x18002edb0  jz      short loc_18002EDED
0x18002edb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002edb9  lea     rax, WPP_GLOBAL_Control
0x18002edc0  cmp     rcx, rax
0x18002edc3  jz      short loc_18002EDE3
0x18002edc5  test    byte ptr [rcx+1Ch], 10h
0x18002edc9  jz      short loc_18002EDE3
0x18002edcb  mov     rcx, [rcx+10h]
0x18002edcf  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002edd6  mov     edx, 1Dh
0x18002eddb  mov     r9d, ebx
0x18002edde  call    WPP_SF_d
0x18002ede3  mov     rdi, [rsp+1A0h+var_160]
0x18002ede8  jmp     loc_18002EF42
0x18002eded  mov     rdi, [rsp+1A0h+var_160]
0x18002edf2  cmp     esi, [rsp+1A0h+numEntriesReturned]
0x18002edf6  jnb     loc_18002EF21
0x18002edfc  mov     rax, [rsp+1A0h+entries]
0x18002ee01  mov     ecx, esi
0x18002ee03  mov     rcx, [rax+rcx*8]
0x18002ee07  cmp     dword ptr [rcx+8], 2
0x18002ee0b  jz      loc_18002EEE5
0x18002ee11  lea     rdx, [rsp+1A0h+var_130]
0x18002ee16  call    ConvertMMSAFromBfeToSpd
0x18002ee1b  mov     ebx, eax
0x18002ee1d  test    eax, eax
0x18002ee1f  jnz     loc_18002EEEC
0x18002ee25  mov     rcx, [rsp+1A0h+var_140]
0x18002ee2a  lea     rdx, [rsp+1A0h+var_130]
0x18002ee2f  call    MatchMMSATemplate
0x18002ee34  test    eax, eax
0x18002ee36  jz      loc_18002EEDB
0x18002ee3c  movups  xmm0, [rsp+1A0h+var_130]
0x18002ee41  mov     eax, r14d
0x18002ee44  imul    rcx, rax, 0E0h
0x18002ee4b  inc     r14d
0x18002ee4e  movups  xmmword ptr [rcx+rdi], xmm0
0x18002ee52  movups  xmm1, [rbp+0A0h+var_120]
0x18002ee56  movups  xmmword ptr [rcx+rdi+10h], xmm1
0x18002ee5b  movups  xmm0, [rbp+0A0h+var_110]
0x18002ee5f  movups  xmmword ptr [rcx+rdi+20h], xmm0
0x18002ee64  movups  xmm1, [rbp+0A0h+var_100]
0x18002ee68  movups  xmmword ptr [rcx+rdi+30h], xmm1
0x18002ee6d  movups  xmm0, [rbp+0A0h+var_F0]
0x18002ee71  movups  xmmword ptr [rcx+rdi+40h], xmm0
0x18002ee76  movups  xmm1, [rbp+0A0h+var_E0]
0x18002ee7a  movups  xmmword ptr [rcx+rdi+50h], xmm1
0x18002ee7f  movups  xmm0, [rbp+0A0h+var_D0]
0x18002ee83  movups  xmmword ptr [rcx+rdi+60h], xmm0
0x18002ee88  movups  xmm1, [rbp+0A0h+var_C0]
0x18002ee8c  movups  xmmword ptr [rcx+rdi+70h], xmm1
0x18002ee91  movups  xmm0, [rbp+0A0h+var_B0]
0x18002ee95  movups  xmmword ptr [rcx+rdi+80h], xmm0
0x18002ee9d  movups  xmm1, [rbp+0A0h+var_A0]
0x18002eea1  movups  xmmword ptr [rcx+rdi+90h], xmm1
0x18002eea9  movups  xmm0, [rbp+0A0h+var_90]
0x18002eead  movups  xmmword ptr [rcx+rdi+0A0h], xmm0
0x18002eeb5  movups  xmm1, [rbp+0A0h+var_80]
0x18002eeb9  movups  xmmword ptr [rcx+rdi+0B0h], xmm1
0x18002eec1  movups  xmm0, [rbp+0A0h+var_70]
0x18002eec5  movups  xmmword ptr [rcx+rdi+0C0h], xmm0
0x18002eecd  movups  xmm1, [rbp+0A0h+var_60]
0x18002eed1  movups  xmmword ptr [rcx+rdi+0D0h], xmm1
0x18002eed9  jmp     short loc_18002EEE5
0x18002eedb  lea     rcx, [rsp+1A0h+var_130]; void *
0x18002eee0  call    CleanupSAEntry
0x18002eee5  inc     esi
0x18002eee7  jmp     loc_18002EDF2
0x18002eeec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eef3  lea     rax, WPP_GLOBAL_Control
0x18002eefa  cmp     rcx, rax
0x18002eefd  jz      short loc_18002EF1D
0x18002eeff  test    byte ptr [rcx+1Ch], 10h
0x18002ef03  jz      short loc_18002EF1D
0x18002ef05  mov     rcx, [rcx+10h]
0x18002ef09  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002ef10  mov     edx, 1Eh
0x18002ef15  mov     r9d, ebx
0x18002ef18  call    WPP_SF_d
0x18002ef1d  xor     esi, esi
0x18002ef1f  jmp     short loc_18002EF42
0x18002ef21  xor     esi, esi
0x18002ef23  test    r14d, r14d
0x18002ef26  jz      short loc_18002EF3D
0x18002ef28  mov     rax, [rsp+1A0h+var_138]
0x18002ef2d  mov     [r12], rdi
0x18002ef31  mov     [r13+0], r14d
0x18002ef35  mov     [r15], r14d
0x18002ef38  mov     [rax], r14d
0x18002ef3b  jmp     short loc_18002EF42
0x18002ef3d  mov     ebx, 0E8h
0x18002ef42  mov     rdx, [rsp+1A0h+enumHandle]; enumHandle
0x18002ef47  mov     rcx, [rsp+1A0h+var_168]; engineHandle
0x18002ef4c  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x18002ef52  mov     rcx, [rsp+1A0h+var_168]; engineHandle
0x18002ef57  call    cs:__imp_FwpmEngineClose0
0x18002ef5d  test    ebx, ebx
0x18002ef5f  jz      short loc_18002EF86
0x18002ef61  test    r14d, r14d
0x18002ef64  jz      short loc_18002EF7E
0x18002ef66  mov     eax, esi
0x18002ef68  imul    rcx, rax, 0E0h
0x18002ef6f  add     rcx, rdi; void *
0x18002ef72  call    CleanupSAEntry
0x18002ef77  inc     esi
0x18002ef79  cmp     esi, r14d
0x18002ef7c  jb      short loc_18002EF66
0x18002ef7e  mov     rcx, rdi
0x18002ef81  call    SPDApiBufferFree
0x18002ef86  lea     rcx, [rsp+1A0h+entries]; p
0x18002ef8b  call    cs:__imp_FwpmFreeMemory0
0x18002ef91  mov     eax, ebx
0x18002ef93  mov     rcx, [rbp+0A0h+var_50]
0x18002ef97  xor     rcx, rsp; StackCookie
0x18002ef9a  call    __security_check_cookie
0x18002ef9f  add     rsp, 168h
0x18002efa6  pop     r15
0x18002efa8  pop     r14
0x18002efaa  pop     r13
0x18002efac  pop     r12
0x18002efae  pop     rdi
0x18002efaf  pop     rsi
0x18002efb0  pop     rbx
0x18002efb1  pop     rbp
0x18002efb2  retn
```
