# AVrfpLoadAndInitializeProvider

- ea: `0x1800bbda8`
- end: `0x1800bc0f5`
- name: `AVrfpLoadAndInitializeProvider`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x180112488`

## callees

- `0x180007060`
- `0x18001f070`
- `0x180023e20`
- `0x18002ad90`
- `0x180050d08`
- `0x18005a9f0`
- `0x18005b470`
- `0x1800bbda8`
- `0x1800bcba0`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x1800bbf79`: `AVRF: provider %ws passed an invalid descriptor @ %p \n`
- `0x1800bbed2`: `AVRF: provider %ws is not a DLL image \n`
- `0x1800bbf99`: `AVRF: initialized provider %ws (descriptor @ %p) \n`
- `0x1800bc0e4`: `AVRF: verifier dll `%ws' \n`

## pseudocode

```c
char __fastcall AVrfpLoadAndInitializeProvider(__int64 a1)
{
  char v2; // bl
  __int64 *v3; // r15
  char v4; // si
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 i; // rcx
  __int64 NtSystemRoot; // rax
  __int64 v9; // rbx
  int Dll; // eax
  char v11; // bl
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  _DWORD *v16; // r14
  int v17; // ecx
  __int64 v19; // [rsp+38h] [rbp-F0h] BYREF
  _DWORD *v20; // [rsp+40h] [rbp-E8h] BYREF
  __int128 v21; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-D0h]
  _BYTE v23[128]; // [rsp+60h] [rbp-C8h] BYREF

  v22 = a1;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  memset_thunk_772440563353939046(v23, 0, 0x80u);
  v2 = 0;
  v3 = (__int64 *)(a1 + 24);
  v4 = 1;
  if ( (AVrfpDebug & 1) != 0 )
    DbgPrint("AVRF: verifier dll `%ws' \n", *v3);
  v5 = *v3;
  v6 = *(unsigned __int16 *)(a1 + 16) >> 1;
  for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
  {
    if ( *(_WORD *)(v5 + 2LL * (unsigned int)i) == 92 || *(_WORD *)(v5 + 2LL * (unsigned int)i) == 47 )
    {
      v2 = 1;
      break;
    }
  }
  if ( v2 == 1 )
  {
    DbgPrint("AVRF: Cannot load %ws from arbitrary location\n", *v3, v5);
    return 0;
  }
  *((_QWORD *)&v21 + 1) = qword_1801C5FF0;
  LODWORD(v21) = 34078720;
  NtSystemRoot = RtlGetNtSystemRoot(i, v6, v5);
  RtlAppendUnicodeToString(&v21, NtSystemRoot);
  RtlAppendUnicodeStringToString(&v21, &SlashSystem32SlashString);
  v9 = *((_QWORD *)&v21 + 1);
  LdrpInitializeDllPath(0, *((_QWORD *)&v21 + 1), v23);
  Dll = LdrpLoadDll((unsigned __int16 *)(a1 + 16), (__int64)v23, 1u, (__int64)&v19);
  if ( Dll < 0 )
  {
    DbgPrint(
      "AVRF: %ws: failed to load provider `%ws' (status %08X) from %ws\n",
      *(_QWORD *)(qword_1801CA8D0 + 96),
      *v3,
      (unsigned int)Dll,
      v9);
    return 0;
  }
  v11 = 0;
  v12 = v19;
  *(_QWORD *)(a1 + 32) = v19;
  v19 = 0;
  RtlImageNtHeaderEx(1, *(_QWORD *)(v12 + 48), 0, &v19);
  if ( v19 )
  {
    if ( (*(_WORD *)(v19 + 22) & 0x2000) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 32) + 104LL) |= 0x400u;
      v14 = *(_QWORD *)(a1 + 32);
      v15 = *(_QWORD *)(v14 + 56);
      if ( !v15 )
      {
        DbgPrint("AVRF: cannot find an entry point for provider %ws \n", *v3, v13);
        return 0;
      }
      v20 = 0;
      if ( (unsigned __int8)LdrpCallInitRoutine(v15, *(_QWORD *)(v14 + 48), 4, &v20) && (v16 = v20) != 0 )
      {
        if ( *v20 == 80 )
        {
          if ( (AVrfpDebug & 8) != 0 )
            DbgPrint("AVRF: initialized provider %ws (descriptor @ %p) \n", *v3, v20);
          *(_QWORD *)(a1 + 40) = *((_QWORD *)v16 + 1);
          *(_QWORD *)(a1 + 48) = *((_QWORD *)v16 + 2);
          *(_QWORD *)(a1 + 56) = *((_QWORD *)v16 + 3);
          *(_QWORD *)(a1 + 64) = *((_QWORD *)v16 + 9);
          *((_QWORD *)v16 + 4) = *(_QWORD *)(qword_1801CA8D0 + 96);
          v17 = AVrfpVerifierFlags;
          v16[10] = AVrfpVerifierFlags;
          v16[11] = AVrfpDebug;
          *((_QWORD *)v16 + 6) = RtlpGetStackTraceAddress;
          *((_QWORD *)v16 + 7) = RtlpDebugPageHeapCreate;
          *((_QWORD *)v16 + 8) = RtlpDebugPageHeapDestroy;
          if ( AVrfpEnabledSystemWide )
            v16[10] = v17 | 0x20000;
        }
        else
        {
          v11 = 1;
          DbgPrint("AVRF: provider %ws passed an invalid descriptor @ %p \n", *v3, v20);
        }
      }
      else
      {
        v11 = 1;
        DbgPrint("AVRF: provider %ws did not initialize correctly \n", *v3);
      }
    }
    else
    {
      DbgPrint("AVRF: provider %ws is not a DLL image \n", *v3);
      v11 = 1;
    }
  }
  else
  {
    v11 = 1;
  }
  if ( v11 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x1800bbda8  push    rbx
0x1800bbdaa  push    rsi
0x1800bbdab  push    rdi
0x1800bbdac  push    r13
0x1800bbdae  push    r14
0x1800bbdb0  push    r15
0x1800bbdb2  sub     rsp, 0F8h
0x1800bbdb9  mov     rax, cs:__security_cookie
0x1800bbdc0  xor     rax, rsp
0x1800bbdc3  mov     [rsp+128h+var_48], rax
0x1800bbdcb  mov     r13, rcx
0x1800bbdce  mov     [rsp+128h+var_D0], rcx
0x1800bbdd3  xor     edi, edi
0x1800bbdd5  mov     [rsp+128h+var_E8], rdi
0x1800bbdda  mov     [rsp+128h+var_F0], rdi
0x1800bbddf  xorps   xmm0, xmm0
0x1800bbde2  movups  [rsp+128h+var_E0], xmm0
0x1800bbde7  xor     edx, edx; Val
0x1800bbde9  mov     r8d, 80h; Size
0x1800bbdef  lea     rcx, [rsp+128h+var_C8]; void *
0x1800bbdf4  call    memset$thunk$772440563353939046
0x1800bbdf9  mov     bl, dil
0x1800bbdfc  lea     r15, [r13+18h]
0x1800bbe00  lea     esi, [rdi+1]
0x1800bbe03  test    byte ptr cs:AVrfpDebug, sil
0x1800bbe0a  jnz     loc_1800BC0E1
0x1800bbe10  mov     r8, [r15]
0x1800bbe13  movzx   edx, word ptr [r13+10h]
0x1800bbe18  shr     edx, 1
0x1800bbe1a  mov     ecx, edi
0x1800bbe1c  cmp     ecx, edx
0x1800bbe1e  jb      loc_1800BC0A3
0x1800bbe24  cmp     bl, sil
0x1800bbe27  jz      loc_1800BC0BC
0x1800bbe2d  lea     rax, qword_1801C5FF0
0x1800bbe34  mov     qword ptr [rsp+128h+var_E0+8], rax
0x1800bbe39  mov     dword ptr [rsp+128h+var_E0], 2080000h
0x1800bbe41  call    RtlGetNtSystemRoot
0x1800bbe46  mov     rdx, rax
0x1800bbe49  lea     rcx, [rsp+128h+var_E0]
0x1800bbe4e  call    RtlAppendUnicodeToString
0x1800bbe53  lea     rdx, SlashSystem32SlashString
0x1800bbe5a  lea     rcx, [rsp+128h+var_E0]
0x1800bbe5f  call    RtlAppendUnicodeStringToString
0x1800bbe64  lea     r8, [rsp+128h+var_C8]
0x1800bbe69  mov     rbx, qword ptr [rsp+128h+var_E0+8]
0x1800bbe6e  mov     rdx, rbx
0x1800bbe71  xor     ecx, ecx
0x1800bbe73  call    LdrpInitializeDllPath
0x1800bbe78  lea     r9, [rsp+128h+var_F0]
0x1800bbe7d  mov     r8d, esi
0x1800bbe80  lea     rdx, [rsp+128h+var_C8]
0x1800bbe85  lea     rcx, [r13+10h]; ArgList
0x1800bbe89  call    LdrpLoadDll
0x1800bbe8e  test    eax, eax
0x1800bbe90  js      loc_1800BC07F
0x1800bbe96  mov     bl, dil
0x1800bbe99  mov     rdx, [rsp+128h+var_F0]
0x1800bbe9e  mov     [r13+20h], rdx
0x1800bbea2  mov     [rsp+128h+var_F0], rdi
0x1800bbea7  lea     r9, [rsp+128h+var_F0]
0x1800bbeac  xor     r8d, r8d
0x1800bbeaf  mov     rdx, [rdx+30h]
0x1800bbeb3  mov     ecx, esi
0x1800bbeb5  call    RtlImageNtHeaderEx
0x1800bbeba  mov     rax, [rsp+128h+var_F0]
0x1800bbebf  test    rax, rax
0x1800bbec2  jz      short loc_1800BBEEA
0x1800bbec4  mov     ecx, 2000h
0x1800bbec9  test    [rax+16h], cx
0x1800bbecd  jnz     short loc_1800BBEF6
0x1800bbecf  mov     rdx, [r15]
0x1800bbed2  lea     rcx, aAvrfProviderWs_2; "AVRF: provider %ws is not a DLL image "...
0x1800bbed9  call    DbgPrint
0x1800bbede  mov     bl, sil
0x1800bbee1  mov     [rsp+128h+var_F8], bl
0x1800bbee5  jmp     loc_1800BC053
0x1800bbeea  mov     bl, sil
0x1800bbeed  mov     [rsp+128h+var_F8], bl
0x1800bbef1  jmp     loc_1800BC053
0x1800bbef6  jmp     short loc_1800BBF1D
0x1800bbef8  mov     rdx, [rsp+128h+var_D0]
0x1800bbefd  mov     rdx, [rdx+18h]
0x1800bbf01  lea     rcx, aAvrfExceptionR; "AVRF: exception raised while probing pr"...
0x1800bbf08  call    DbgPrint
0x1800bbf0d  mov     bl, 1
0x1800bbf0f  mov     [rsp+128h+var_F8], bl
0x1800bbf13  xor     edi, edi
0x1800bbf15  lea     esi, [rdi+1]
0x1800bbf18  jmp     loc_1800BC053
0x1800bbf1d  mov     rax, [r13+20h]
0x1800bbf21  bts     dword ptr [rax+68h], 0Ah
0x1800bbf26  mov     rdx, [r13+20h]
0x1800bbf2a  mov     rcx, [rdx+38h]
0x1800bbf2e  test    rcx, rcx
0x1800bbf31  jz      loc_1800BC0D5
0x1800bbf37  mov     [rsp+128h+var_E8], rdi
0x1800bbf3c  lea     r9, [rsp+128h+var_E8]
0x1800bbf41  mov     r8d, 4
0x1800bbf47  mov     rdx, [rdx+30h]
0x1800bbf4b  call    LdrpCallInitRoutine
0x1800bbf50  test    al, al
0x1800bbf52  jz      loc_1800BC01B
0x1800bbf58  mov     r14, [rsp+128h+var_E8]
0x1800bbf5d  test    r14, r14
0x1800bbf60  jz      loc_1800BC01B
0x1800bbf66  cmp     dword ptr [r14], 50h ; 'P'
0x1800bbf6a  jz      short loc_1800BBF8A
0x1800bbf6c  mov     bl, sil
0x1800bbf6f  mov     [rsp+128h+var_F8], bl
0x1800bbf73  mov     r8, r14
0x1800bbf76  mov     rdx, [r15]
0x1800bbf79  lea     rcx, aAvrfProviderWs; "AVRF: provider %ws passed an invalid de"...
0x1800bbf80  call    DbgPrint
0x1800bbf85  jmp     loc_1800BC031
0x1800bbf8a  test    byte ptr cs:AVrfpDebug, 8
0x1800bbf91  jz      short loc_1800BBFA5
0x1800bbf93  mov     r8, r14
0x1800bbf96  mov     rdx, [r15]
0x1800bbf99  lea     rcx, aAvrfInitialize; "AVRF: initialized provider %ws (descrip"...
0x1800bbfa0  call    DbgPrint
0x1800bbfa5  mov     rax, [r14+8]
0x1800bbfa9  mov     [r13+28h], rax
0x1800bbfad  mov     rax, [r14+10h]
0x1800bbfb1  mov     [r13+30h], rax
0x1800bbfb5  mov     rax, [r14+18h]
0x1800bbfb9  mov     [r13+38h], rax
0x1800bbfbd  mov     rax, [r14+48h]
0x1800bbfc1  mov     [r13+40h], rax
0x1800bbfc5  mov     rax, cs:qword_1801CA8D0
0x1800bbfcc  mov     rcx, [rax+60h]
0x1800bbfd0  mov     [r14+20h], rcx
0x1800bbfd4  mov     ecx, cs:AVrfpVerifierFlags
0x1800bbfda  mov     [r14+28h], ecx
0x1800bbfde  mov     eax, cs:AVrfpDebug
0x1800bbfe4  mov     [r14+2Ch], eax
0x1800bbfe8  lea     rax, RtlpGetStackTraceAddress
0x1800bbfef  mov     [r14+30h], rax
0x1800bbff3  lea     rax, RtlpDebugPageHeapCreate
0x1800bbffa  mov     [r14+38h], rax
0x1800bbffe  lea     rax, RtlpDebugPageHeapDestroy
0x1800bc005  mov     [r14+40h], rax
0x1800bc009  cmp     cs:AVrfpEnabledSystemWide, edi
0x1800bc00f  jz      short loc_1800BC031
0x1800bc011  bts     ecx, 11h
0x1800bc015  mov     [r14+28h], ecx
0x1800bc019  jmp     short loc_1800BC031
0x1800bc01b  mov     bl, sil
0x1800bc01e  mov     [rsp+128h+var_F8], bl
0x1800bc022  mov     rdx, [r15]
0x1800bc025  lea     rcx, aAvrfProviderWs_0; "AVRF: provider %ws did not initialize c"...
0x1800bc02c  call    DbgPrint
0x1800bc031  jmp     short loc_1800BC053
0x1800bc033  mov     rdx, [rsp+128h+var_D0]
0x1800bc038  mov     rdx, [rdx+18h]
0x1800bc03c  lea     rcx, aAvrfExceptionR_0; "AVRF: exception raised in provider %ws "...
0x1800bc043  call    DbgPrint
0x1800bc048  mov     bl, 1
0x1800bc04a  mov     [rsp+128h+var_F8], bl
0x1800bc04e  xor     edi, edi
0x1800bc050  lea     esi, [rdi+1]
0x1800bc053  test    bl, bl
0x1800bc055  jz      short loc_1800BC05A
0x1800bc057  mov     sil, dil
0x1800bc05a  mov     al, sil
0x1800bc05d  mov     rcx, [rsp+128h+var_48]
0x1800bc065  xor     rcx, rsp; StackCookie
0x1800bc068  call    __security_check_cookie
0x1800bc06d  add     rsp, 0F8h
0x1800bc074  pop     r15
0x1800bc076  pop     r14
0x1800bc078  pop     r13
0x1800bc07a  pop     rdi
0x1800bc07b  pop     rsi
0x1800bc07c  pop     rbx
0x1800bc07d  retn
0x1800bc07f  mov     [rsp+128h+var_108], rbx
0x1800bc084  mov     r9d, eax
0x1800bc087  mov     r8, [r15]
0x1800bc08a  mov     rdx, cs:qword_1801CA8D0
0x1800bc091  mov     rdx, [rdx+60h]
0x1800bc095  lea     rcx, aAvrfWsFailedTo; "AVRF: %ws: failed to load provider `%ws"...
0x1800bc09c  call    DbgPrint
0x1800bc0a1  jmp     short loc_1800BC057
0x1800bc0a3  mov     eax, ecx
0x1800bc0a5  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x1800bc0ab  jz      short loc_1800BC0CD
0x1800bc0ad  cmp     word ptr [r8+rax*2], 2Fh ; '/'
0x1800bc0b3  jz      short loc_1800BC0CD
0x1800bc0b5  add     ecx, esi
0x1800bc0b7  jmp     loc_1800BBE1C
0x1800bc0bc  mov     rdx, r8
0x1800bc0bf  lea     rcx, aAvrfCannotLoad; "AVRF: Cannot load %ws from arbitrary lo"...
0x1800bc0c6  call    DbgPrint
0x1800bc0cb  jmp     short loc_1800BC057
0x1800bc0cd  mov     bl, sil
0x1800bc0d0  jmp     loc_1800BBE24
0x1800bc0d5  mov     rdx, [r15]
0x1800bc0d8  lea     rcx, aAvrfCannotFind; "AVRF: cannot find an entry point for pr"...
0x1800bc0df  jmp     short loc_1800BC0C6
0x1800bc0e1  mov     rdx, [r15]
0x1800bc0e4  lea     rcx, aAvrfVerifierDl; "AVRF: verifier dll `%ws' \n"
0x1800bc0eb  call    DbgPrint
0x1800bc0f0  jmp     loc_1800BBE10
```
