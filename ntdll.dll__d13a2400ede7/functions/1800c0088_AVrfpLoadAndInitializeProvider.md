# AVrfpLoadAndInitializeProvider

- ea: `0x1800c0088`
- end: `0x1800c03d5`
- name: `AVrfpLoadAndInitializeProvider`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x180113878`

## callees

- `0x180007060`
- `0x18001f070`
- `0x180023e10`
- `0x180036fa0`
- `0x18006d6e8`
- `0x1800773d0`
- `0x180077e50`
- `0x1800c0088`
- `0x1800c0e80`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x1800c0259`: `AVRF: provider %ws passed an invalid descriptor @ %p \n`
- `0x1800c01b2`: `AVRF: provider %ws is not a DLL image \n`
- `0x1800c0279`: `AVRF: initialized provider %ws (descriptor @ %p) \n`
- `0x1800c03c4`: `AVRF: verifier dll `%ws' \n`

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
0x1800c0088  push    rbx
0x1800c008a  push    rsi
0x1800c008b  push    rdi
0x1800c008c  push    r13
0x1800c008e  push    r14
0x1800c0090  push    r15
0x1800c0092  sub     rsp, 0F8h
0x1800c0099  mov     rax, cs:__security_cookie
0x1800c00a0  xor     rax, rsp
0x1800c00a3  mov     [rsp+128h+var_48], rax
0x1800c00ab  mov     r13, rcx
0x1800c00ae  mov     [rsp+128h+var_D0], rcx
0x1800c00b3  xor     edi, edi
0x1800c00b5  mov     [rsp+128h+var_E8], rdi
0x1800c00ba  mov     [rsp+128h+var_F0], rdi
0x1800c00bf  xorps   xmm0, xmm0
0x1800c00c2  movups  [rsp+128h+var_E0], xmm0
0x1800c00c7  xor     edx, edx; Val
0x1800c00c9  mov     r8d, 80h; Size
0x1800c00cf  lea     rcx, [rsp+128h+var_C8]; void *
0x1800c00d4  call    memset$thunk$772440563353939046
0x1800c00d9  mov     bl, dil
0x1800c00dc  lea     r15, [r13+18h]
0x1800c00e0  lea     esi, [rdi+1]
0x1800c00e3  test    byte ptr cs:AVrfpDebug, sil
0x1800c00ea  jnz     loc_1800C03C1
0x1800c00f0  mov     r8, [r15]
0x1800c00f3  movzx   edx, word ptr [r13+10h]
0x1800c00f8  shr     edx, 1
0x1800c00fa  mov     ecx, edi
0x1800c00fc  cmp     ecx, edx
0x1800c00fe  jb      loc_1800C0383
0x1800c0104  cmp     bl, sil
0x1800c0107  jz      loc_1800C039C
0x1800c010d  lea     rax, qword_1801C5FF0
0x1800c0114  mov     qword ptr [rsp+128h+var_E0+8], rax
0x1800c0119  mov     dword ptr [rsp+128h+var_E0], 2080000h
0x1800c0121  call    RtlGetNtSystemRoot
0x1800c0126  mov     rdx, rax
0x1800c0129  lea     rcx, [rsp+128h+var_E0]
0x1800c012e  call    RtlAppendUnicodeToString
0x1800c0133  lea     rdx, SlashSystem32SlashString
0x1800c013a  lea     rcx, [rsp+128h+var_E0]
0x1800c013f  call    RtlAppendUnicodeStringToString
0x1800c0144  lea     r8, [rsp+128h+var_C8]
0x1800c0149  mov     rbx, qword ptr [rsp+128h+var_E0+8]
0x1800c014e  mov     rdx, rbx
0x1800c0151  xor     ecx, ecx
0x1800c0153  call    LdrpInitializeDllPath
0x1800c0158  lea     r9, [rsp+128h+var_F0]
0x1800c015d  mov     r8d, esi
0x1800c0160  lea     rdx, [rsp+128h+var_C8]
0x1800c0165  lea     rcx, [r13+10h]; ArgList
0x1800c0169  call    LdrpLoadDll
0x1800c016e  test    eax, eax
0x1800c0170  js      loc_1800C035F
0x1800c0176  mov     bl, dil
0x1800c0179  mov     rdx, [rsp+128h+var_F0]
0x1800c017e  mov     [r13+20h], rdx
0x1800c0182  mov     [rsp+128h+var_F0], rdi
0x1800c0187  lea     r9, [rsp+128h+var_F0]
0x1800c018c  xor     r8d, r8d
0x1800c018f  mov     rdx, [rdx+30h]
0x1800c0193  mov     ecx, esi
0x1800c0195  call    RtlImageNtHeaderEx
0x1800c019a  mov     rax, [rsp+128h+var_F0]
0x1800c019f  test    rax, rax
0x1800c01a2  jz      short loc_1800C01CA
0x1800c01a4  mov     ecx, 2000h
0x1800c01a9  test    [rax+16h], cx
0x1800c01ad  jnz     short loc_1800C01D6
0x1800c01af  mov     rdx, [r15]
0x1800c01b2  lea     rcx, aAvrfProviderWs_2; "AVRF: provider %ws is not a DLL image "...
0x1800c01b9  call    DbgPrint
0x1800c01be  mov     bl, sil
0x1800c01c1  mov     [rsp+128h+var_F8], bl
0x1800c01c5  jmp     loc_1800C0333
0x1800c01ca  mov     bl, sil
0x1800c01cd  mov     [rsp+128h+var_F8], bl
0x1800c01d1  jmp     loc_1800C0333
0x1800c01d6  jmp     short loc_1800C01FD
0x1800c01d8  mov     rdx, [rsp+128h+var_D0]
0x1800c01dd  mov     rdx, [rdx+18h]
0x1800c01e1  lea     rcx, aAvrfExceptionR; "AVRF: exception raised while probing pr"...
0x1800c01e8  call    DbgPrint
0x1800c01ed  mov     bl, 1
0x1800c01ef  mov     [rsp+128h+var_F8], bl
0x1800c01f3  xor     edi, edi
0x1800c01f5  lea     esi, [rdi+1]
0x1800c01f8  jmp     loc_1800C0333
0x1800c01fd  mov     rax, [r13+20h]
0x1800c0201  bts     dword ptr [rax+68h], 0Ah
0x1800c0206  mov     rdx, [r13+20h]
0x1800c020a  mov     rcx, [rdx+38h]
0x1800c020e  test    rcx, rcx
0x1800c0211  jz      loc_1800C03B5
0x1800c0217  mov     [rsp+128h+var_E8], rdi
0x1800c021c  lea     r9, [rsp+128h+var_E8]
0x1800c0221  mov     r8d, 4
0x1800c0227  mov     rdx, [rdx+30h]
0x1800c022b  call    LdrpCallInitRoutine
0x1800c0230  test    al, al
0x1800c0232  jz      loc_1800C02FB
0x1800c0238  mov     r14, [rsp+128h+var_E8]
0x1800c023d  test    r14, r14
0x1800c0240  jz      loc_1800C02FB
0x1800c0246  cmp     dword ptr [r14], 50h ; 'P'
0x1800c024a  jz      short loc_1800C026A
0x1800c024c  mov     bl, sil
0x1800c024f  mov     [rsp+128h+var_F8], bl
0x1800c0253  mov     r8, r14
0x1800c0256  mov     rdx, [r15]
0x1800c0259  lea     rcx, aAvrfProviderWs; "AVRF: provider %ws passed an invalid de"...
0x1800c0260  call    DbgPrint
0x1800c0265  jmp     loc_1800C0311
0x1800c026a  test    byte ptr cs:AVrfpDebug, 8
0x1800c0271  jz      short loc_1800C0285
0x1800c0273  mov     r8, r14
0x1800c0276  mov     rdx, [r15]
0x1800c0279  lea     rcx, aAvrfInitialize; "AVRF: initialized provider %ws (descrip"...
0x1800c0280  call    DbgPrint
0x1800c0285  mov     rax, [r14+8]
0x1800c0289  mov     [r13+28h], rax
0x1800c028d  mov     rax, [r14+10h]
0x1800c0291  mov     [r13+30h], rax
0x1800c0295  mov     rax, [r14+18h]
0x1800c0299  mov     [r13+38h], rax
0x1800c029d  mov     rax, [r14+48h]
0x1800c02a1  mov     [r13+40h], rax
0x1800c02a5  mov     rax, cs:qword_1801CA8D0
0x1800c02ac  mov     rcx, [rax+60h]
0x1800c02b0  mov     [r14+20h], rcx
0x1800c02b4  mov     ecx, cs:AVrfpVerifierFlags
0x1800c02ba  mov     [r14+28h], ecx
0x1800c02be  mov     eax, cs:AVrfpDebug
0x1800c02c4  mov     [r14+2Ch], eax
0x1800c02c8  lea     rax, RtlpGetStackTraceAddress
0x1800c02cf  mov     [r14+30h], rax
0x1800c02d3  lea     rax, RtlpDebugPageHeapCreate
0x1800c02da  mov     [r14+38h], rax
0x1800c02de  lea     rax, RtlpDebugPageHeapDestroy
0x1800c02e5  mov     [r14+40h], rax
0x1800c02e9  cmp     cs:AVrfpEnabledSystemWide, edi
0x1800c02ef  jz      short loc_1800C0311
0x1800c02f1  bts     ecx, 11h
0x1800c02f5  mov     [r14+28h], ecx
0x1800c02f9  jmp     short loc_1800C0311
0x1800c02fb  mov     bl, sil
0x1800c02fe  mov     [rsp+128h+var_F8], bl
0x1800c0302  mov     rdx, [r15]
0x1800c0305  lea     rcx, aAvrfProviderWs_0; "AVRF: provider %ws did not initialize c"...
0x1800c030c  call    DbgPrint
0x1800c0311  jmp     short loc_1800C0333
0x1800c0313  mov     rdx, [rsp+128h+var_D0]
0x1800c0318  mov     rdx, [rdx+18h]
0x1800c031c  lea     rcx, aAvrfExceptionR_0; "AVRF: exception raised in provider %ws "...
0x1800c0323  call    DbgPrint
0x1800c0328  mov     bl, 1
0x1800c032a  mov     [rsp+128h+var_F8], bl
0x1800c032e  xor     edi, edi
0x1800c0330  lea     esi, [rdi+1]
0x1800c0333  test    bl, bl
0x1800c0335  jz      short loc_1800C033A
0x1800c0337  mov     sil, dil
0x1800c033a  mov     al, sil
0x1800c033d  mov     rcx, [rsp+128h+var_48]
0x1800c0345  xor     rcx, rsp; StackCookie
0x1800c0348  call    __security_check_cookie
0x1800c034d  add     rsp, 0F8h
0x1800c0354  pop     r15
0x1800c0356  pop     r14
0x1800c0358  pop     r13
0x1800c035a  pop     rdi
0x1800c035b  pop     rsi
0x1800c035c  pop     rbx
0x1800c035d  retn
0x1800c035f  mov     [rsp+128h+var_108], rbx
0x1800c0364  mov     r9d, eax
0x1800c0367  mov     r8, [r15]
0x1800c036a  mov     rdx, cs:qword_1801CA8D0
0x1800c0371  mov     rdx, [rdx+60h]
0x1800c0375  lea     rcx, aAvrfWsFailedTo; "AVRF: %ws: failed to load provider `%ws"...
0x1800c037c  call    DbgPrint
0x1800c0381  jmp     short loc_1800C0337
0x1800c0383  mov     eax, ecx
0x1800c0385  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x1800c038b  jz      short loc_1800C03AD
0x1800c038d  cmp     word ptr [r8+rax*2], 2Fh ; '/'
0x1800c0393  jz      short loc_1800C03AD
0x1800c0395  add     ecx, esi
0x1800c0397  jmp     loc_1800C00FC
0x1800c039c  mov     rdx, r8
0x1800c039f  lea     rcx, aAvrfCannotLoad; "AVRF: Cannot load %ws from arbitrary lo"...
0x1800c03a6  call    DbgPrint
0x1800c03ab  jmp     short loc_1800C0337
0x1800c03ad  mov     bl, sil
0x1800c03b0  jmp     loc_1800C0104
0x1800c03b5  mov     rdx, [r15]
0x1800c03b8  lea     rcx, aAvrfCannotFind; "AVRF: cannot find an entry point for pr"...
0x1800c03bf  jmp     short loc_1800C03A6
0x1800c03c1  mov     rdx, [r15]
0x1800c03c4  lea     rcx, aAvrfVerifierDl; "AVRF: verifier dll `%ws' \n"
0x1800c03cb  call    DbgPrint
0x1800c03d0  jmp     loc_1800C00F0
```
