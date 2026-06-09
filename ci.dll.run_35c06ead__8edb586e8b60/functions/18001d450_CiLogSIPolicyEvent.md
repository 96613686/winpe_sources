# CiLogSIPolicyEvent

- ea: `0x18001d450`
- end: `0x18001daec`
- name: `CiLogSIPolicyEvent`
- size: `1692`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, int, __int64, int, __int64, int, __int64, int, char, char, char, char, char, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18006d740`
- `0x18006f474`

## callees

- `0x18001d450`
- `0x18001daf4`
- `0x18002c0d0`
- `0x18002c500`
- `0x18006cebc`
- `0x18006eccc`
- `0x180091448`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18001daa3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001dab3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001daa3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001dab3`
- `ntoskrnl!EtwEventEnabled` at `0x18001d517`
- `ntoskrnl!EtwEventEnabled` at `0x18001d517`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001da4b`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001da4b`
- `ntoskrnl!EtwWrite` at `0x18001da73`
- `ntoskrnl!EtwWrite` at `0x18001da73`

## pseudocode

```c
__int64 __fastcall CiLogSIPolicyEvent(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        ULONGLONG a5,
        ULONGLONG a6,
        ULONG a7,
        ULONGLONG a8,
        ULONG a9,
        ULONGLONG a10,
        ULONG a11,
        ULONGLONG a12,
        ULONG a13,
        char a14,
        char a15,
        char a16,
        char a17,
        char a18,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v19; // r15
  __int64 v24; // rdx
  NTSTATUS PolicyHash; // edi
  ULONG v27; // ecx
  ULONG v28; // edx
  ULONG v29; // ecx
  unsigned __int64 v30; // r9
  unsigned __int16 v31; // ax
  ULONG v32; // ecx
  ULONG v33; // ecx
  __int64 v34; // rax
  ULONGLONG v35; // rdx
  ULONG v36; // ecx
  unsigned __int16 v37; // ax
  __int16 *v38; // rax
  __int64 v39; // rax
  const GUID *ActivityIdThread; // rax
  int v41; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v42; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v43; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v44; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v45; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v46; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v47; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v48; // [rsp+5Ch] [rbp-A4h] BYREF
  __int16 v49; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v50; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG v51; // [rsp+68h] [rbp-98h] BYREF
  int v52; // [rsp+6Ch] [rbp-94h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v54; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[36]; // [rsp+90h] [rbp-70h] BYREF
  char pszDest[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v57[64]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v19 = EventDescriptor;
  memset(UserData, 0, sizeof(UserData));
  v48 = 0;
  v42 = 0;
  v47 = 0;
  v46 = 0;
  v50 = 0;
  memset(v57, 0, sizeof(v57));
  v51 = 64;
  v54 = 0;
  v49 = 0;
  UnicodeString = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v41 = 0;
  v52 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  if ( a1 )
    v52 = (*(_DWORD *)(a1 + 2368) >> 9) & 1;
  PolicyHash = CipGetPolicyHash(a2, v24, v57, &v51);
  if ( PolicyHash >= 0 )
  {
    PolicyHash = CiLogSIPolicyGetPolicyIDs(a2, &v54, &UnicodeString);
    if ( PolicyHash >= 0 )
    {
      v27 = *a3;
      v28 = *a4;
      v42 = *a3 >> 1;
      v43 = (unsigned __int16)v28 >> 1;
      UserData[0].Ptr = (ULONGLONG)&v42;
      UserData[1].Ptr = *((_QWORD *)a3 + 1);
      UserData[2].Ptr = (ULONGLONG)&v43;
      UserData[3].Ptr = *((_QWORD *)a4 + 1);
      UserData[4].Ptr = (ULONGLONG)&a16;
      UserData[5].Ptr = (ULONGLONG)&a17;
      UserData[6].Ptr = (ULONGLONG)&a18;
      UserData[7].Ptr = (ULONGLONG)&a7;
      UserData[8].Ptr = a6;
      UserData[8].Size = a7;
      UserData[9].Ptr = (ULONGLONG)&a9;
      UserData[10].Ptr = a8;
      UserData[10].Size = a9;
      UserData[11].Ptr = (ULONGLONG)&a11;
      UserData[12].Ptr = a10;
      UserData[12].Size = a11;
      UserData[13].Ptr = (ULONGLONG)&a13;
      UserData[14].Ptr = a12;
      UserData[14].Size = a13;
      UserData[15].Ptr = (ULONGLONG)&a14;
      UserData[16].Ptr = (ULONGLONG)&a15;
      v44 = UnicodeString.Length >> 1;
      UserData[17].Ptr = (ULONGLONG)&v44;
      UserData[18].Ptr = (ULONGLONG)UnicodeString.Buffer;
      UserData[18].Size = UnicodeString.Length;
      *(_QWORD *)&UserData[0].Size = 2;
      UserData[1].Size = v27;
      UserData[1].Reserved = 0;
      *(_QWORD *)&UserData[2].Size = 2;
      UserData[3].Size = v28;
      UserData[3].Reserved = 0;
      *(_QWORD *)&UserData[4].Size = 1;
      *(_QWORD *)&UserData[5].Size = 1;
      *(_QWORD *)&UserData[6].Size = 4;
      *(_QWORD *)&UserData[7].Size = 4;
      UserData[8].Reserved = 0;
      *(_QWORD *)&UserData[9].Size = 4;
      UserData[10].Reserved = 0;
      *(_QWORD *)&UserData[11].Size = 4;
      UserData[12].Reserved = 0;
      *(_QWORD *)&UserData[13].Size = 4;
      UserData[14].Reserved = 0;
      *(_QWORD *)&UserData[15].Size = 8;
      *(_QWORD *)&UserData[16].Size = 4;
      *(_QWORD *)&UserData[17].Size = 2;
      UserData[18].Reserved = 0;
      v45 = v54.Length >> 1;
      UserData[19].Ptr = (ULONGLONG)&v45;
      UserData[20].Ptr = (ULONGLONG)v54.Buffer;
      UserData[20].Size = v54.Length;
      UserData[21].Ptr = (ULONGLONG)&v51;
      UserData[22].Ptr = (ULONGLONG)v57;
      UserData[22].Size = v51;
      UserData[33].Ptr = (ULONGLONG)&v52;
      *(_QWORD *)&UserData[19].Size = 2;
      UserData[20].Reserved = 0;
      *(_QWORD *)&UserData[21].Size = 4;
      UserData[22].Reserved = 0;
      *(_QWORD *)&UserData[33].Size = 4;
      *(_QWORD *)&UserData[23].Size = 2;
      *(_QWORD *)&UserData[25].Size = 2;
      *(_QWORD *)&UserData[27].Size = 2;
      if ( a1 )
      {
        v29 = *(unsigned __int16 *)(a1 + 744);
        v30 = *(_QWORD *)(a1 + 840);
        v46 = *(_WORD *)(a1 + 744) >> 1;
        UserData[23].Ptr = (ULONGLONG)&v46;
        UserData[24].Ptr = *(_QWORD *)(a1 + 752);
        UserData[24].Size = v29;
        v31 = *(_WORD *)(a1 + 760);
        UserData[26].Size = v31;
        v32 = *(unsigned __int16 *)(a1 + 776);
        v47 = v31 >> 1;
        UserData[25].Ptr = (ULONGLONG)&v47;
        UserData[26].Ptr = *(_QWORD *)(a1 + 768);
        v48 = (unsigned __int16)v32 >> 1;
        UserData[27].Ptr = (ULONGLONG)&v48;
        UserData[28].Ptr = *(_QWORD *)(a1 + 784);
        UserData[28].Size = v32;
        v33 = *(unsigned __int16 *)(a1 + 792);
        v49 = *(_WORD *)(a1 + 792) >> 1;
        UserData[29].Ptr = (ULONGLONG)&v49;
        UserData[30].Ptr = *(_QWORD *)(a1 + 800);
        UserData[30].Size = v33;
        UserData[24].Reserved = 0;
        UserData[26].Reserved = 0;
        UserData[28].Reserved = 0;
        *(_QWORD *)&UserData[29].Size = 2;
        UserData[30].Reserved = 0;
        if ( RtlStringCchPrintfA(
               pszDest,
               0x18u,
               "%hu.%hu.%hu.%hu",
               HIWORD(v30),
               WORD2(v30),
               WORD1(v30),
               (unsigned __int16)v30) < 0 )
          pszDest[0] = 0;
        UserData[31].Ptr = (ULONGLONG)pszDest;
        v34 = -1;
        do
          ++v34;
        while ( pszDest[v34] );
        v35 = *(_QWORD *)(a1 + 832);
        UserData[31].Size = v34 + 1;
        UserData[31].Reserved = 0;
        *(_QWORD *)&UserData[34].Size = 2;
        if ( v35 )
        {
          v36 = *(unsigned __int16 *)(a1 + 824);
          v37 = *(_WORD *)(a1 + 824);
          UserData[35].Ptr = v35;
          v50 = v37 >> 1;
          v38 = &v50;
          UserData[35].Size = v36;
          UserData[35].Reserved = 0;
LABEL_18:
          UserData[34].Ptr = (ULONGLONG)v38;
          UserData[32].Ptr = a5;
          *(_QWORD *)&UserData[32].Size = 16;
          ActivityIdThread = (const GUID *)IoGetActivityIdThread();
          PolicyHash = EtwWrite(g_EtwEventHandle, v19, ActivityIdThread, 0x24u, UserData);
          if ( PolicyHash >= 0 && a1 )
          {
            if ( *(_QWORD *)(a1 + 2320) )
              CiLogCimContextEvent(a1, a3);
          }
          goto LABEL_22;
        }
      }
      else
      {
        *(_QWORD *)&UserData[29].Size = 2;
        UserData[23].Ptr = (ULONGLONG)&v41;
        pszDest[0] = 0;
        UserData[25].Ptr = (ULONGLONG)&v41;
        UserData[27].Ptr = (ULONGLONG)&v41;
        UserData[29].Ptr = (ULONGLONG)&v41;
        UserData[31].Ptr = (ULONGLONG)pszDest;
        v39 = -1;
        do
          ++v39;
        while ( pszDest[v39] );
        UserData[31].Reserved = 0;
        UserData[31].Size = v39 + 1;
        *(_QWORD *)&UserData[34].Size = 2;
      }
      v38 = (__int16 *)&v41;
      goto LABEL_18;
    }
  }
LABEL_22:
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v54);
  return (unsigned int)PolicyHash;
}

```

## disassembly

```asm
0x18001d450  mov     [rsp-8+arg_18], rbx
0x18001d455  push    rbp
0x18001d456  push    rsi
0x18001d457  push    rdi
0x18001d458  push    r12
0x18001d45a  push    r13
0x18001d45c  push    r14
0x18001d45e  push    r15
0x18001d460  lea     rbp, [rsp-240h]
0x18001d468  sub     rsp, 340h
0x18001d46f  mov     rax, cs:__security_cookie
0x18001d476  xor     rax, rsp
0x18001d479  mov     [rbp+270h+var_40], rax
0x18001d480  mov     r15, [rbp+270h+EventDescriptor]
0x18001d487  mov     r14, r8
0x18001d48a  mov     rsi, rdx
0x18001d48d  mov     rbx, rcx
0x18001d490  xor     edx, edx; Val
0x18001d492  lea     rcx, [rbp+270h+var_2E0]; void *
0x18001d496  mov     r8d, 240h; Size
0x18001d49c  mov     r13, r9
0x18001d49f  call    memset
0x18001d4a4  xor     r12d, r12d
0x18001d4a7  lea     rcx, [rbp+270h+var_80]; void *
0x18001d4ae  xor     edx, edx; Val
0x18001d4b0  mov     [rsp+370h+var_314], r12w
0x18001d4b6  mov     [rsp+370h+var_32C], r12w
0x18001d4bc  mov     [rsp+370h+var_318], r12w
0x18001d4c2  lea     edi, [r12+40h]
0x18001d4c7  mov     [rsp+370h+var_31C], r12w
0x18001d4cd  mov     r8d, edi; Size
0x18001d4d0  mov     [rsp+370h+var_30C], r12w
0x18001d4d6  call    memset
0x18001d4db  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18001d4e2  xorps   xmm0, xmm0
0x18001d4e5  mov     rdx, r15; EventDescriptor
0x18001d4e8  mov     [rsp+370h+var_308], edi
0x18001d4ec  movups  xmmword ptr [rbp+270h+var_2F0.Length], xmm0
0x18001d4f0  mov     [rsp+370h+var_310], r12w
0x18001d4f6  movups  xmmword ptr [rsp+370h+UnicodeString.Length], xmm0
0x18001d4fb  mov     [rsp+370h+var_320], r12w
0x18001d501  mov     [rsp+370h+var_324], r12w
0x18001d507  mov     [rsp+370h+var_328], r12w
0x18001d50d  mov     [rsp+370h+var_330], r12d
0x18001d512  mov     [rsp+370h+var_304], r12d
0x18001d517  call    cs:__imp_EtwEventEnabled
0x18001d51e  nop     dword ptr [rax+rax+00h]
0x18001d523  test    al, al
0x18001d525  jnz     short loc_18001D52E
0x18001d527  xor     eax, eax
0x18001d529  jmp     loc_18001DAC1
0x18001d52e  test    rbx, rbx
0x18001d531  jz      short loc_18001D543
0x18001d533  mov     eax, [rbx+940h]
0x18001d539  shr     eax, 9
0x18001d53c  and     eax, 1
0x18001d53f  mov     [rsp+370h+var_304], eax
0x18001d543  lea     r9, [rsp+370h+var_308]
0x18001d548  mov     rcx, rsi
0x18001d54b  lea     r8, [rbp+270h+var_80]
0x18001d552  call    CipGetPolicyHash
0x18001d557  mov     edi, eax
0x18001d559  test    eax, eax
0x18001d55b  js      loc_18001DA9E
0x18001d561  lea     r8, [rsp+370h+UnicodeString]
0x18001d566  mov     rcx, rsi
0x18001d569  lea     rdx, [rbp+270h+var_2F0]
0x18001d56d  call    CiLogSIPolicyGetPolicyIDs
0x18001d572  mov     edi, eax
0x18001d574  test    eax, eax
0x18001d576  js      loc_18001DA9E
0x18001d57c  movzx   ecx, word ptr [r14]
0x18001d580  movzx   edx, word ptr [r13+0]
0x18001d585  movzx   eax, cx
0x18001d588  shr     ax, 1
0x18001d58b  mov     [rsp+370h+var_32C], ax
0x18001d590  movzx   eax, dx
0x18001d593  shr     ax, 1
0x18001d596  mov     [rsp+370h+var_328], ax
0x18001d59b  lea     rax, [rsp+370h+var_32C]
0x18001d5a0  mov     [rbp+270h+var_2E0.Ptr], rax
0x18001d5a4  mov     rax, [r14+8]
0x18001d5a8  mov     [rbp+270h+var_2D0], rax
0x18001d5ac  lea     rax, [rsp+370h+var_328]
0x18001d5b1  mov     [rbp+270h+var_2C0], rax
0x18001d5b5  mov     rax, [r13+8]
0x18001d5b9  mov     [rbp+270h+var_2B0], rax
0x18001d5bd  lea     rax, [rbp+270h+arg_78]
0x18001d5c4  mov     [rbp+270h+var_2A0], rax
0x18001d5c8  lea     rax, [rbp+270h+arg_80]
0x18001d5cf  mov     [rbp+270h+var_290], rax
0x18001d5d3  lea     rax, [rbp+270h+arg_88]
0x18001d5da  mov     [rbp+270h+var_280], rax
0x18001d5de  lea     rax, [rbp+270h+arg_30]
0x18001d5e5  mov     [rbp+270h+var_270], rax
0x18001d5e9  mov     rax, [rbp+270h+arg_28]
0x18001d5f0  mov     [rbp+270h+var_260], rax
0x18001d5f4  mov     eax, [rbp+270h+arg_30]
0x18001d5fa  mov     [rbp+270h+var_258], eax
0x18001d5fd  lea     rax, [rbp+270h+arg_40]
0x18001d604  mov     [rbp+270h+var_250], rax
0x18001d608  mov     rax, [rbp+270h+arg_38]
0x18001d60f  mov     [rbp+270h+var_240], rax
0x18001d613  mov     eax, [rbp+270h+arg_40]
0x18001d619  mov     [rbp+270h+var_238], eax
0x18001d61c  lea     rax, [rbp+270h+arg_50]
0x18001d623  mov     [rbp+270h+var_230], rax
0x18001d627  mov     rax, [rbp+270h+arg_48]
0x18001d62e  mov     [rbp+270h+var_220], rax
0x18001d632  mov     eax, [rbp+270h+arg_50]
0x18001d638  mov     [rbp+270h+var_218], eax
0x18001d63b  lea     rax, [rbp+270h+arg_60]
0x18001d642  mov     [rbp+270h+var_210], rax
0x18001d646  mov     rax, [rbp+270h+arg_58]
0x18001d64d  mov     [rbp+270h+var_200], rax
0x18001d651  mov     eax, [rbp+270h+arg_60]
0x18001d657  mov     [rbp+270h+var_1F8], eax
0x18001d65a  lea     rax, [rbp+270h+arg_68]
0x18001d661  mov     [rbp+270h+var_1F0], rax
0x18001d668  lea     rax, [rbp+270h+arg_70]
0x18001d66f  mov     [rbp+270h+var_1E0], rax
0x18001d676  movzx   eax, [rsp+370h+UnicodeString.Length]
0x18001d67b  shr     ax, 1
0x18001d67e  mov     [rsp+370h+var_324], ax
0x18001d683  lea     rax, [rsp+370h+var_324]
0x18001d688  mov     [rbp+270h+var_1D0], rax
0x18001d68f  mov     rax, [rsp+370h+UnicodeString.Buffer]
0x18001d694  mov     [rbp+270h+var_1C0], rax
0x18001d69b  movzx   eax, [rsp+370h+UnicodeString.Length]
0x18001d6a0  mov     [rbp+270h+var_1B8], eax
0x18001d6a6  movzx   eax, [rbp+270h+var_2F0.Length]
0x18001d6aa  mov     qword ptr [rbp+270h+var_2E0.Size], 2
0x18001d6b2  mov     [rbp+270h+var_2C8], ecx
0x18001d6b5  mov     [rbp+270h+var_2C4], r12d
0x18001d6b9  mov     [rbp+270h+var_2B8], 2
0x18001d6c1  mov     [rbp+270h+var_2A8], edx
0x18001d6c4  mov     [rbp+270h+var_2A4], r12d
0x18001d6c8  mov     [rbp+270h+var_298], 1
0x18001d6d0  mov     [rbp+270h+var_288], 1
0x18001d6d8  mov     [rbp+270h+var_278], 4
0x18001d6e0  mov     [rbp+270h+var_268], 4
0x18001d6e8  mov     [rbp+270h+var_254], r12d
0x18001d6ec  mov     [rbp+270h+var_248], 4
0x18001d6f4  mov     [rbp+270h+var_234], r12d
0x18001d6f8  mov     [rbp+270h+var_228], 4
0x18001d700  mov     [rbp+270h+var_214], r12d
0x18001d704  mov     [rbp+270h+var_208], 4
0x18001d70c  mov     [rbp+270h+var_1F4], r12d
0x18001d710  mov     [rbp+270h+var_1E8], 8
0x18001d71b  mov     [rbp+270h+var_1D8], 4
0x18001d726  mov     [rbp+270h+var_1C8], 2
0x18001d731  mov     [rbp+270h+var_1B4], r12d
0x18001d738  shr     ax, 1
0x18001d73b  mov     [rsp+370h+var_320], ax
0x18001d740  lea     rax, [rsp+370h+var_320]
0x18001d745  mov     [rbp+270h+var_1B0], rax
0x18001d74c  mov     rax, [rbp+270h+var_2F0.Buffer]
0x18001d750  mov     [rbp+270h+var_1A0], rax
0x18001d757  movzx   eax, [rbp+270h+var_2F0.Length]
0x18001d75b  mov     [rbp+270h+var_198], eax
0x18001d761  lea     rax, [rsp+370h+var_308]
0x18001d766  mov     [rbp+270h+var_190], rax
0x18001d76d  lea     rax, [rbp+270h+var_80]
0x18001d774  mov     [rbp+270h+var_180], rax
0x18001d77b  mov     eax, [rsp+370h+var_308]
0x18001d77f  mov     [rbp+270h+var_178], eax
0x18001d785  lea     rax, [rsp+370h+var_304]
0x18001d78a  mov     [rbp+270h+var_D0], rax
0x18001d791  mov     [rbp+270h+var_1A8], 2
0x18001d79c  mov     [rbp+270h+var_194], r12d
0x18001d7a3  mov     [rbp+270h+var_188], 4
0x18001d7ae  mov     [rbp+270h+var_174], r12d
0x18001d7b5  mov     [rbp+270h+var_C8], 4
0x18001d7c0  mov     [rbp+270h+var_168], 2
0x18001d7cb  mov     [rbp+270h+var_148], 2
0x18001d7d6  mov     [rbp+270h+var_128], 2
0x18001d7e1  test    rbx, rbx
0x18001d7e4  jz      loc_18001D9A8
0x18001d7ea  movzx   ecx, word ptr [rbx+2E8h]
0x18001d7f1  mov     r9, [rbx+348h]
0x18001d7f8  movzx   eax, cx
0x18001d7fb  shr     ax, 1
0x18001d7fe  mov     [rsp+370h+var_31C], ax
0x18001d803  lea     rax, [rsp+370h+var_31C]
0x18001d808  mov     [rbp+270h+var_170], rax
0x18001d80f  mov     rax, [rbx+2F0h]
0x18001d816  mov     [rbp+270h+var_160], rax
0x18001d81d  mov     [rbp+270h+var_158], ecx
0x18001d823  movzx   ecx, word ptr [rbx+2F8h]
0x18001d82a  movzx   eax, cx
0x18001d82d  mov     [rbp+270h+var_138], ecx
0x18001d833  movzx   ecx, word ptr [rbx+308h]
0x18001d83a  shr     ax, 1
0x18001d83d  mov     [rsp+370h+var_318], ax
0x18001d842  lea     rax, [rsp+370h+var_318]
0x18001d847  mov     [rbp+270h+var_150], rax
0x18001d84e  mov     rax, [rbx+300h]
0x18001d855  mov     [rbp+270h+var_140], rax
0x18001d85c  movzx   eax, cx
0x18001d85f  shr     ax, 1
0x18001d862  mov     [rsp+370h+var_314], ax
0x18001d867  lea     rax, [rsp+370h+var_314]
0x18001d86c  mov     [rbp+270h+var_130], rax
0x18001d873  mov     rax, [rbx+310h]
0x18001d87a  mov     [rbp+270h+var_120], rax
0x18001d881  mov     [rbp+270h+var_118], ecx
0x18001d887  movzx   ecx, word ptr [rbx+318h]
0x18001d88e  movzx   eax, cx
0x18001d891  movzx   r8d, r9w
0x18001d895  shr     ax, 1
0x18001d898  mov     [rsp+370h+var_310], ax
0x18001d89d  lea     rax, [rsp+370h+var_310]
0x18001d8a2  mov     [rbp+270h+var_110], rax
0x18001d8a9  mov     rax, [rbx+320h]
0x18001d8b0  mov     [rbp+270h+var_100], rax
0x18001d8b7  mov     rax, r9
0x18001d8ba  shr     rax, 10h
0x18001d8be  movzx   edx, ax
0x18001d8c1  mov     rax, r9
0x18001d8c4  mov     [rsp+370h+var_340], r8d
0x18001d8c9  lea     r8, pszFormat; "%hu.%hu.%hu.%hu"
0x18001d8d0  mov     [rbp+270h+var_F8], ecx
0x18001d8d6  mov     [rsp+370h+var_348], edx
0x18001d8da  mov     edx, 18h; cchDest
0x18001d8df  shr     rax, 20h
0x18001d8e3  movzx   ecx, ax
0x18001d8e6  mov     dword ptr [rsp+370h+UserData], ecx
0x18001d8ea  lea     rcx, [rbp+270h+pszDest]; pszDest
0x18001d8f1  shr     r9, 30h
0x18001d8f5  mov     [rbp+270h+var_154], r12d
0x18001d8fc  mov     [rbp+270h+var_134], r12d
0x18001d903  mov     [rbp+270h+var_114], r12d
0x18001d90a  mov     [rbp+270h+var_108], 2
0x18001d915  mov     [rbp+270h+var_F4], r12d
0x18001d91c  call    RtlStringCchPrintfA
0x18001d921  test    eax, eax
0x18001d923  jns     short loc_18001D92C
0x18001d925  mov     [rbp+270h+pszDest], r12b
0x18001d92c  lea     rax, [rbp+270h+pszDest]
0x18001d933  mov     [rbp+270h+var_F0], rax
0x18001d93a  lea     rcx, [rbp+270h+pszDest]
0x18001d941  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d945  inc     rax
0x18001d948  cmp     [rcx+rax], r12b
0x18001d94c  jnz     short loc_18001D945
0x18001d94e  mov     rdx, [rbx+340h]
0x18001d955  inc     eax
0x18001d957  mov     [rbp+270h+var_E8], eax
0x18001d95d  mov     [rbp+270h+var_E4], r12d
0x18001d964  mov     [rbp+270h+var_B8], 2
0x18001d96f  test    rdx, rdx
0x18001d972  jz      loc_18001DA26
0x18001d978  movzx   ecx, word ptr [rbx+338h]
0x18001d97f  movzx   eax, cx
0x18001d982  mov     [rbp+270h+var_B0], rdx
0x18001d989  shr     ax, 1
0x18001d98c  mov     [rsp+370h+var_30C], ax
0x18001d991  lea     rax, [rsp+370h+var_30C]
0x18001d996  mov     [rbp+270h+var_A8], ecx
0x18001d99c  mov     [rbp+270h+var_A4], r12d
0x18001d9a3  jmp     loc_18001DA2B
0x18001d9a8  lea     rax, [rsp+370h+var_330]
0x18001d9ad  mov     [rbp+270h+var_108], 2
0x18001d9b8  mov     [rbp+270h+var_170], rax
0x18001d9bf  lea     rcx, [rbp+270h+pszDest]
0x18001d9c6  lea     rax, [rsp+370h+var_330]
0x18001d9cb  mov     [rbp+270h+pszDest], r12b
0x18001d9d2  mov     [rbp+270h+var_150], rax
0x18001d9d9  lea     rax, [rsp+370h+var_330]
0x18001d9de  mov     [rbp+270h+var_130], rax
0x18001d9e5  lea     rax, [rsp+370h+var_330]
0x18001d9ea  mov     [rbp+270h+var_110], rax
0x18001d9f1  lea     rax, [rbp+270h+pszDest]
0x18001d9f8  mov     [rbp+270h+var_F0], rax
0x18001d9ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001da03  inc     rax
0x18001da06  cmp     [rcx+rax], r12b
0x18001da0a  jnz     short loc_18001DA03
0x18001da0c  inc     eax
0x18001da0e  mov     [rbp+270h+var_E4], r12d
0x18001da15  mov     [rbp+270h+var_E8], eax
0x18001da1b  mov     [rbp+270h+var_B8], 2
0x18001da26  lea     rax, [rsp+370h+var_330]
0x18001da2b  mov     [rbp+270h+var_C0], rax
0x18001da32  mov     rax, [rbp+270h+arg_20]
0x18001da39  mov     [rbp+270h+var_E0], rax
0x18001da40  mov     [rbp+270h+var_D8], 10h
0x18001da4b  call    cs:__imp_IoGetActivityIdThread
0x18001da52  nop     dword ptr [rax+rax+00h]
0x18001da57  lea     rcx, [rbp+270h+var_2E0]
0x18001da5b  mov     r9d, 24h ; '$'; UserDataCount
0x18001da61  mov     [rsp+370h+UserData], rcx; UserData
0x18001da66  mov     r8, rax; ActivityId
0x18001da69  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18001da70  mov     rdx, r15; EventDescriptor
0x18001da73  call    cs:__imp_EtwWrite
0x18001da7a  nop     dword ptr [rax+rax+00h]
0x18001da7f  mov     edi, eax
0x18001da81  test    eax, eax
0x18001da83  js      short loc_18001DA9E
  ... truncated ...
```
