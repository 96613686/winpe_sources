# CiLogSIPolicyEvent

- ea: `0x18001d398`
- end: `0x18001da17`
- name: `CiLogSIPolicyEvent`
- size: `1663`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, int, __int64, int, __int64, int, __int64, int, char, char, char, char, char, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18006d460`
- `0x18006f194`

## callees

- `0x18001d398`
- `0x18001da20`
- `0x18002bf20`
- `0x18002c380`
- `0x18006e9ec`
- `0x1800a09a0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18001d9ce`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001d9de`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001d9ce`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001d9de`
- `ntoskrnl!EtwEventEnabled` at `0x18001d45f`
- `ntoskrnl!EtwEventEnabled` at `0x18001d45f`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001d993`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001d993`
- `ntoskrnl!EtwWrite` at `0x18001d9bb`
- `ntoskrnl!EtwWrite` at `0x18001d9bb`

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
  const EVENT_DESCRIPTOR *v19; // r14
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
    v52 = (*(_DWORD *)(a1 + 2360) >> 9) & 1;
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
          goto LABEL_19;
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
LABEL_19:
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v54);
  return (unsigned int)PolicyHash;
}

```

## disassembly

```asm
0x18001d398  mov     [rsp-8+arg_10], rbx
0x18001d39d  push    rbp
0x18001d39e  push    rsi
0x18001d39f  push    rdi
0x18001d3a0  push    r12
0x18001d3a2  push    r13
0x18001d3a4  push    r14
0x18001d3a6  push    r15
0x18001d3a8  lea     rbp, [rsp-240h]
0x18001d3b0  sub     rsp, 340h
0x18001d3b7  mov     rax, cs:__security_cookie
0x18001d3be  xor     rax, rsp
0x18001d3c1  mov     [rbp+270h+var_40], rax
0x18001d3c8  mov     r14, [rbp+270h+EventDescriptor]
0x18001d3cf  mov     r13, r8
0x18001d3d2  mov     rsi, rdx
0x18001d3d5  mov     rbx, rcx
0x18001d3d8  xor     edx, edx; Val
0x18001d3da  lea     rcx, [rbp+270h+var_2E0]; void *
0x18001d3de  mov     r8d, 240h; Size
0x18001d3e4  mov     r15, r9
0x18001d3e7  call    memset
0x18001d3ec  xor     r12d, r12d
0x18001d3ef  lea     rcx, [rbp+270h+var_80]; void *
0x18001d3f6  xor     edx, edx; Val
0x18001d3f8  mov     [rsp+370h+var_314], r12w
0x18001d3fe  mov     [rsp+370h+var_32C], r12w
0x18001d404  mov     [rsp+370h+var_318], r12w
0x18001d40a  lea     edi, [r12+40h]
0x18001d40f  mov     [rsp+370h+var_31C], r12w
0x18001d415  mov     r8d, edi; Size
0x18001d418  mov     [rsp+370h+var_30C], r12w
0x18001d41e  call    memset
0x18001d423  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18001d42a  xorps   xmm0, xmm0
0x18001d42d  mov     rdx, r14; EventDescriptor
0x18001d430  mov     [rsp+370h+var_308], edi
0x18001d434  movups  xmmword ptr [rbp+270h+var_2F0.Length], xmm0
0x18001d438  mov     [rsp+370h+var_310], r12w
0x18001d43e  movups  xmmword ptr [rsp+370h+UnicodeString.Length], xmm0
0x18001d443  mov     [rsp+370h+var_320], r12w
0x18001d449  mov     [rsp+370h+var_324], r12w
0x18001d44f  mov     [rsp+370h+var_328], r12w
0x18001d455  mov     [rsp+370h+var_330], r12d
0x18001d45a  mov     [rsp+370h+var_304], r12d
0x18001d45f  call    cs:__imp_EtwEventEnabled
0x18001d466  nop     dword ptr [rax+rax+00h]
0x18001d46b  test    al, al
0x18001d46d  jnz     short loc_18001D476
0x18001d46f  xor     eax, eax
0x18001d471  jmp     loc_18001D9EC
0x18001d476  test    rbx, rbx
0x18001d479  jz      short loc_18001D48B
0x18001d47b  mov     eax, [rbx+938h]
0x18001d481  shr     eax, 9
0x18001d484  and     eax, 1
0x18001d487  mov     [rsp+370h+var_304], eax
0x18001d48b  lea     r9, [rsp+370h+var_308]
0x18001d490  mov     rcx, rsi
0x18001d493  lea     r8, [rbp+270h+var_80]
0x18001d49a  call    CipGetPolicyHash
0x18001d49f  mov     edi, eax
0x18001d4a1  test    eax, eax
0x18001d4a3  js      loc_18001D9C9
0x18001d4a9  lea     r8, [rsp+370h+UnicodeString]
0x18001d4ae  mov     rcx, rsi
0x18001d4b1  lea     rdx, [rbp+270h+var_2F0]
0x18001d4b5  call    CiLogSIPolicyGetPolicyIDs
0x18001d4ba  mov     edi, eax
0x18001d4bc  test    eax, eax
0x18001d4be  js      loc_18001D9C9
0x18001d4c4  movzx   ecx, word ptr [r13+0]
0x18001d4c9  movzx   edx, word ptr [r15]
0x18001d4cd  movzx   eax, cx
0x18001d4d0  shr     ax, 1
0x18001d4d3  mov     [rsp+370h+var_32C], ax
0x18001d4d8  movzx   eax, dx
0x18001d4db  shr     ax, 1
0x18001d4de  mov     [rsp+370h+var_328], ax
0x18001d4e3  lea     rax, [rsp+370h+var_32C]
0x18001d4e8  mov     [rbp+270h+var_2E0.Ptr], rax
0x18001d4ec  mov     rax, [r13+8]
0x18001d4f0  mov     [rbp+270h+var_2D0], rax
0x18001d4f4  lea     rax, [rsp+370h+var_328]
0x18001d4f9  mov     [rbp+270h+var_2C0], rax
0x18001d4fd  mov     rax, [r15+8]
0x18001d501  mov     [rbp+270h+var_2B0], rax
0x18001d505  lea     rax, [rbp+270h+arg_78]
0x18001d50c  mov     [rbp+270h+var_2A0], rax
0x18001d510  lea     rax, [rbp+270h+arg_80]
0x18001d517  mov     [rbp+270h+var_290], rax
0x18001d51b  lea     rax, [rbp+270h+arg_88]
0x18001d522  mov     [rbp+270h+var_280], rax
0x18001d526  lea     rax, [rbp+270h+arg_30]
0x18001d52d  mov     [rbp+270h+var_270], rax
0x18001d531  mov     rax, [rbp+270h+arg_28]
0x18001d538  mov     [rbp+270h+var_260], rax
0x18001d53c  mov     eax, [rbp+270h+arg_30]
0x18001d542  mov     [rbp+270h+var_258], eax
0x18001d545  lea     rax, [rbp+270h+arg_40]
0x18001d54c  mov     [rbp+270h+var_250], rax
0x18001d550  mov     rax, [rbp+270h+arg_38]
0x18001d557  mov     [rbp+270h+var_240], rax
0x18001d55b  mov     eax, [rbp+270h+arg_40]
0x18001d561  mov     [rbp+270h+var_238], eax
0x18001d564  lea     rax, [rbp+270h+arg_50]
0x18001d56b  mov     [rbp+270h+var_230], rax
0x18001d56f  mov     rax, [rbp+270h+arg_48]
0x18001d576  mov     [rbp+270h+var_220], rax
0x18001d57a  mov     eax, [rbp+270h+arg_50]
0x18001d580  mov     [rbp+270h+var_218], eax
0x18001d583  lea     rax, [rbp+270h+arg_60]
0x18001d58a  mov     [rbp+270h+var_210], rax
0x18001d58e  mov     rax, [rbp+270h+arg_58]
0x18001d595  mov     [rbp+270h+var_200], rax
0x18001d599  mov     eax, [rbp+270h+arg_60]
0x18001d59f  mov     [rbp+270h+var_1F8], eax
0x18001d5a2  lea     rax, [rbp+270h+arg_68]
0x18001d5a9  mov     [rbp+270h+var_1F0], rax
0x18001d5b0  lea     rax, [rbp+270h+arg_70]
0x18001d5b7  mov     [rbp+270h+var_1E0], rax
0x18001d5be  movzx   eax, [rsp+370h+UnicodeString.Length]
0x18001d5c3  shr     ax, 1
0x18001d5c6  mov     [rsp+370h+var_324], ax
0x18001d5cb  lea     rax, [rsp+370h+var_324]
0x18001d5d0  mov     [rbp+270h+var_1D0], rax
0x18001d5d7  mov     rax, [rsp+370h+UnicodeString.Buffer]
0x18001d5dc  mov     [rbp+270h+var_1C0], rax
0x18001d5e3  movzx   eax, [rsp+370h+UnicodeString.Length]
0x18001d5e8  mov     [rbp+270h+var_1B8], eax
0x18001d5ee  movzx   eax, [rbp+270h+var_2F0.Length]
0x18001d5f2  mov     qword ptr [rbp+270h+var_2E0.Size], 2
0x18001d5fa  mov     [rbp+270h+var_2C8], ecx
0x18001d5fd  mov     [rbp+270h+var_2C4], r12d
0x18001d601  mov     [rbp+270h+var_2B8], 2
0x18001d609  mov     [rbp+270h+var_2A8], edx
0x18001d60c  mov     [rbp+270h+var_2A4], r12d
0x18001d610  mov     [rbp+270h+var_298], 1
0x18001d618  mov     [rbp+270h+var_288], 1
0x18001d620  mov     [rbp+270h+var_278], 4
0x18001d628  mov     [rbp+270h+var_268], 4
0x18001d630  mov     [rbp+270h+var_254], r12d
0x18001d634  mov     [rbp+270h+var_248], 4
0x18001d63c  mov     [rbp+270h+var_234], r12d
0x18001d640  mov     [rbp+270h+var_228], 4
0x18001d648  mov     [rbp+270h+var_214], r12d
0x18001d64c  mov     [rbp+270h+var_208], 4
0x18001d654  mov     [rbp+270h+var_1F4], r12d
0x18001d658  mov     [rbp+270h+var_1E8], 8
0x18001d663  mov     [rbp+270h+var_1D8], 4
0x18001d66e  mov     [rbp+270h+var_1C8], 2
0x18001d679  mov     [rbp+270h+var_1B4], r12d
0x18001d680  shr     ax, 1
0x18001d683  mov     [rsp+370h+var_320], ax
0x18001d688  lea     rax, [rsp+370h+var_320]
0x18001d68d  mov     [rbp+270h+var_1B0], rax
0x18001d694  mov     rax, [rbp+270h+var_2F0.Buffer]
0x18001d698  mov     [rbp+270h+var_1A0], rax
0x18001d69f  movzx   eax, [rbp+270h+var_2F0.Length]
0x18001d6a3  mov     [rbp+270h+var_198], eax
0x18001d6a9  lea     rax, [rsp+370h+var_308]
0x18001d6ae  mov     [rbp+270h+var_190], rax
0x18001d6b5  lea     rax, [rbp+270h+var_80]
0x18001d6bc  mov     [rbp+270h+var_180], rax
0x18001d6c3  mov     eax, [rsp+370h+var_308]
0x18001d6c7  mov     [rbp+270h+var_178], eax
0x18001d6cd  lea     rax, [rsp+370h+var_304]
0x18001d6d2  mov     [rbp+270h+var_D0], rax
0x18001d6d9  mov     [rbp+270h+var_1A8], 2
0x18001d6e4  mov     [rbp+270h+var_194], r12d
0x18001d6eb  mov     [rbp+270h+var_188], 4
0x18001d6f6  mov     [rbp+270h+var_174], r12d
0x18001d6fd  mov     [rbp+270h+var_C8], 4
0x18001d708  mov     [rbp+270h+var_168], 2
0x18001d713  mov     [rbp+270h+var_148], 2
0x18001d71e  mov     [rbp+270h+var_128], 2
0x18001d729  test    rbx, rbx
0x18001d72c  jz      loc_18001D8F0
0x18001d732  movzx   ecx, word ptr [rbx+2E8h]
0x18001d739  mov     r9, [rbx+348h]
0x18001d740  movzx   eax, cx
0x18001d743  shr     ax, 1
0x18001d746  mov     [rsp+370h+var_31C], ax
0x18001d74b  lea     rax, [rsp+370h+var_31C]
0x18001d750  mov     [rbp+270h+var_170], rax
0x18001d757  mov     rax, [rbx+2F0h]
0x18001d75e  mov     [rbp+270h+var_160], rax
0x18001d765  mov     [rbp+270h+var_158], ecx
0x18001d76b  movzx   ecx, word ptr [rbx+2F8h]
0x18001d772  movzx   eax, cx
0x18001d775  mov     [rbp+270h+var_138], ecx
0x18001d77b  movzx   ecx, word ptr [rbx+308h]
0x18001d782  shr     ax, 1
0x18001d785  mov     [rsp+370h+var_318], ax
0x18001d78a  lea     rax, [rsp+370h+var_318]
0x18001d78f  mov     [rbp+270h+var_150], rax
0x18001d796  mov     rax, [rbx+300h]
0x18001d79d  mov     [rbp+270h+var_140], rax
0x18001d7a4  movzx   eax, cx
0x18001d7a7  shr     ax, 1
0x18001d7aa  mov     [rsp+370h+var_314], ax
0x18001d7af  lea     rax, [rsp+370h+var_314]
0x18001d7b4  mov     [rbp+270h+var_130], rax
0x18001d7bb  mov     rax, [rbx+310h]
0x18001d7c2  mov     [rbp+270h+var_120], rax
0x18001d7c9  mov     [rbp+270h+var_118], ecx
0x18001d7cf  movzx   ecx, word ptr [rbx+318h]
0x18001d7d6  movzx   eax, cx
0x18001d7d9  movzx   r8d, r9w
0x18001d7dd  shr     ax, 1
0x18001d7e0  mov     [rsp+370h+var_310], ax
0x18001d7e5  lea     rax, [rsp+370h+var_310]
0x18001d7ea  mov     [rbp+270h+var_110], rax
0x18001d7f1  mov     rax, [rbx+320h]
0x18001d7f8  mov     [rbp+270h+var_100], rax
0x18001d7ff  mov     rax, r9
0x18001d802  shr     rax, 10h
0x18001d806  movzx   edx, ax
0x18001d809  mov     rax, r9
0x18001d80c  mov     [rsp+370h+var_340], r8d
0x18001d811  lea     r8, pszFormat; "%hu.%hu.%hu.%hu"
0x18001d818  mov     [rbp+270h+var_F8], ecx
0x18001d81e  mov     [rsp+370h+var_348], edx
0x18001d822  mov     edx, 18h; cchDest
0x18001d827  shr     rax, 20h
0x18001d82b  movzx   ecx, ax
0x18001d82e  mov     dword ptr [rsp+370h+UserData], ecx
0x18001d832  lea     rcx, [rbp+270h+pszDest]; pszDest
0x18001d839  shr     r9, 30h
0x18001d83d  mov     [rbp+270h+var_154], r12d
0x18001d844  mov     [rbp+270h+var_134], r12d
0x18001d84b  mov     [rbp+270h+var_114], r12d
0x18001d852  mov     [rbp+270h+var_108], 2
0x18001d85d  mov     [rbp+270h+var_F4], r12d
0x18001d864  call    RtlStringCchPrintfA
0x18001d869  test    eax, eax
0x18001d86b  jns     short loc_18001D874
0x18001d86d  mov     [rbp+270h+pszDest], r12b
0x18001d874  lea     rax, [rbp+270h+pszDest]
0x18001d87b  mov     [rbp+270h+var_F0], rax
0x18001d882  lea     rcx, [rbp+270h+pszDest]
0x18001d889  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d88d  inc     rax
0x18001d890  cmp     [rcx+rax], r12b
0x18001d894  jnz     short loc_18001D88D
0x18001d896  mov     rdx, [rbx+340h]
0x18001d89d  inc     eax
0x18001d89f  mov     [rbp+270h+var_E8], eax
0x18001d8a5  mov     [rbp+270h+var_E4], r12d
0x18001d8ac  mov     [rbp+270h+var_B8], 2
0x18001d8b7  test    rdx, rdx
0x18001d8ba  jz      loc_18001D96E
0x18001d8c0  movzx   ecx, word ptr [rbx+338h]
0x18001d8c7  movzx   eax, cx
0x18001d8ca  mov     [rbp+270h+var_B0], rdx
0x18001d8d1  shr     ax, 1
0x18001d8d4  mov     [rsp+370h+var_30C], ax
0x18001d8d9  lea     rax, [rsp+370h+var_30C]
0x18001d8de  mov     [rbp+270h+var_A8], ecx
0x18001d8e4  mov     [rbp+270h+var_A4], r12d
0x18001d8eb  jmp     loc_18001D973
0x18001d8f0  lea     rax, [rsp+370h+var_330]
0x18001d8f5  mov     [rbp+270h+var_108], 2
0x18001d900  mov     [rbp+270h+var_170], rax
0x18001d907  lea     rcx, [rbp+270h+pszDest]
0x18001d90e  lea     rax, [rsp+370h+var_330]
0x18001d913  mov     [rbp+270h+pszDest], r12b
0x18001d91a  mov     [rbp+270h+var_150], rax
0x18001d921  lea     rax, [rsp+370h+var_330]
0x18001d926  mov     [rbp+270h+var_130], rax
0x18001d92d  lea     rax, [rsp+370h+var_330]
0x18001d932  mov     [rbp+270h+var_110], rax
0x18001d939  lea     rax, [rbp+270h+pszDest]
0x18001d940  mov     [rbp+270h+var_F0], rax
0x18001d947  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d94b  inc     rax
0x18001d94e  cmp     [rcx+rax], r12b
0x18001d952  jnz     short loc_18001D94B
0x18001d954  inc     eax
0x18001d956  mov     [rbp+270h+var_E4], r12d
0x18001d95d  mov     [rbp+270h+var_E8], eax
0x18001d963  mov     [rbp+270h+var_B8], 2
0x18001d96e  lea     rax, [rsp+370h+var_330]
0x18001d973  mov     [rbp+270h+var_C0], rax
0x18001d97a  mov     rax, [rbp+270h+arg_20]
0x18001d981  mov     [rbp+270h+var_E0], rax
0x18001d988  mov     [rbp+270h+var_D8], 10h
0x18001d993  call    cs:__imp_IoGetActivityIdThread
0x18001d99a  nop     dword ptr [rax+rax+00h]
0x18001d99f  lea     rcx, [rbp+270h+var_2E0]
0x18001d9a3  mov     r9d, 24h ; '$'; UserDataCount
0x18001d9a9  mov     [rsp+370h+UserData], rcx; UserData
0x18001d9ae  mov     r8, rax; ActivityId
0x18001d9b1  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18001d9b8  mov     rdx, r14; EventDescriptor
0x18001d9bb  call    cs:__imp_EtwWrite
0x18001d9c2  nop     dword ptr [rax+rax+00h]
0x18001d9c7  mov     edi, eax
0x18001d9c9  lea     rcx, [rsp+370h+UnicodeString]; UnicodeString
0x18001d9ce  call    cs:__imp_RtlFreeUnicodeString
  ... truncated ...
```
