# CiLogSIPolicyEvent

- ea: `0x18001d458`
- end: `0x18001dad7`
- name: `CiLogSIPolicyEvent`
- size: `1663`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, int, __int64, int, __int64, int, __int64, int, char, char, char, char, char, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18006c68c`
- `0x18006dee4`

## callees

- `0x18001d458`
- `0x18001dae0`
- `0x18002bef0`
- `0x18002c340`
- `0x18006dc18`
- `0x18009f370`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18001da8e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001da9e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001da8e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001da9e`
- `ntoskrnl!EtwEventEnabled` at `0x18001d51f`
- `ntoskrnl!EtwEventEnabled` at `0x18001d51f`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001da53`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001da53`
- `ntoskrnl!EtwWrite` at `0x18001da7b`
- `ntoskrnl!EtwWrite` at `0x18001da7b`

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
0x18001d458  mov     [rsp-8+arg_10], rbx
0x18001d45d  push    rbp
0x18001d45e  push    rsi
0x18001d45f  push    rdi
0x18001d460  push    r12
0x18001d462  push    r13
0x18001d464  push    r14
0x18001d466  push    r15
0x18001d468  lea     rbp, [rsp-240h]
0x18001d470  sub     rsp, 340h
0x18001d477  mov     rax, cs:__security_cookie
0x18001d47e  xor     rax, rsp
0x18001d481  mov     [rbp+270h+var_40], rax
0x18001d488  mov     r14, [rbp+270h+EventDescriptor]
0x18001d48f  mov     r13, r8
0x18001d492  mov     rsi, rdx
0x18001d495  mov     rbx, rcx
0x18001d498  xor     edx, edx; Val
0x18001d49a  lea     rcx, [rbp+270h+var_2E0]; void *
0x18001d49e  mov     r8d, 240h; Size
0x18001d4a4  mov     r15, r9
0x18001d4a7  call    memset
0x18001d4ac  xor     r12d, r12d
0x18001d4af  lea     rcx, [rbp+270h+var_80]; void *
0x18001d4b6  xor     edx, edx; Val
0x18001d4b8  mov     [rsp+370h+var_314], r12w
0x18001d4be  mov     [rsp+370h+var_32C], r12w
0x18001d4c4  mov     [rsp+370h+var_318], r12w
0x18001d4ca  lea     edi, [r12+40h]
0x18001d4cf  mov     [rsp+370h+var_31C], r12w
0x18001d4d5  mov     r8d, edi; Size
0x18001d4d8  mov     [rsp+370h+var_30C], r12w
0x18001d4de  call    memset
0x18001d4e3  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18001d4ea  xorps   xmm0, xmm0
0x18001d4ed  mov     rdx, r14; EventDescriptor
0x18001d4f0  mov     [rsp+370h+var_308], edi
0x18001d4f4  movups  xmmword ptr [rbp+270h+var_2F0.Length], xmm0
0x18001d4f8  mov     [rsp+370h+var_310], r12w
0x18001d4fe  movups  xmmword ptr [rsp+370h+UnicodeString.Length], xmm0
0x18001d503  mov     [rsp+370h+var_320], r12w
0x18001d509  mov     [rsp+370h+var_324], r12w
0x18001d50f  mov     [rsp+370h+var_328], r12w
0x18001d515  mov     [rsp+370h+var_330], r12d
0x18001d51a  mov     [rsp+370h+var_304], r12d
0x18001d51f  call    cs:__imp_EtwEventEnabled
0x18001d526  nop     dword ptr [rax+rax+00h]
0x18001d52b  test    al, al
0x18001d52d  jnz     short loc_18001D536
0x18001d52f  xor     eax, eax
0x18001d531  jmp     loc_18001DAAC
0x18001d536  test    rbx, rbx
0x18001d539  jz      short loc_18001D54B
0x18001d53b  mov     eax, [rbx+938h]
0x18001d541  shr     eax, 9
0x18001d544  and     eax, 1
0x18001d547  mov     [rsp+370h+var_304], eax
0x18001d54b  lea     r9, [rsp+370h+var_308]
0x18001d550  mov     rcx, rsi
0x18001d553  lea     r8, [rbp+270h+var_80]
0x18001d55a  call    CipGetPolicyHash
0x18001d55f  mov     edi, eax
0x18001d561  test    eax, eax
0x18001d563  js      loc_18001DA89
0x18001d569  lea     r8, [rsp+370h+UnicodeString]
0x18001d56e  mov     rcx, rsi
0x18001d571  lea     rdx, [rbp+270h+var_2F0]
0x18001d575  call    CiLogSIPolicyGetPolicyIDs
0x18001d57a  mov     edi, eax
0x18001d57c  test    eax, eax
0x18001d57e  js      loc_18001DA89
0x18001d584  movzx   ecx, word ptr [r13+0]
0x18001d589  movzx   edx, word ptr [r15]
0x18001d58d  movzx   eax, cx
0x18001d590  shr     ax, 1
0x18001d593  mov     [rsp+370h+var_32C], ax
0x18001d598  movzx   eax, dx
0x18001d59b  shr     ax, 1
0x18001d59e  mov     [rsp+370h+var_328], ax
0x18001d5a3  lea     rax, [rsp+370h+var_32C]
0x18001d5a8  mov     [rbp+270h+var_2E0.Ptr], rax
0x18001d5ac  mov     rax, [r13+8]
0x18001d5b0  mov     [rbp+270h+var_2D0], rax
0x18001d5b4  lea     rax, [rsp+370h+var_328]
0x18001d5b9  mov     [rbp+270h+var_2C0], rax
0x18001d5bd  mov     rax, [r15+8]
0x18001d5c1  mov     [rbp+270h+var_2B0], rax
0x18001d5c5  lea     rax, [rbp+270h+arg_78]
0x18001d5cc  mov     [rbp+270h+var_2A0], rax
0x18001d5d0  lea     rax, [rbp+270h+arg_80]
0x18001d5d7  mov     [rbp+270h+var_290], rax
0x18001d5db  lea     rax, [rbp+270h+arg_88]
0x18001d5e2  mov     [rbp+270h+var_280], rax
0x18001d5e6  lea     rax, [rbp+270h+arg_30]
0x18001d5ed  mov     [rbp+270h+var_270], rax
0x18001d5f1  mov     rax, [rbp+270h+arg_28]
0x18001d5f8  mov     [rbp+270h+var_260], rax
0x18001d5fc  mov     eax, [rbp+270h+arg_30]
0x18001d602  mov     [rbp+270h+var_258], eax
0x18001d605  lea     rax, [rbp+270h+arg_40]
0x18001d60c  mov     [rbp+270h+var_250], rax
0x18001d610  mov     rax, [rbp+270h+arg_38]
0x18001d617  mov     [rbp+270h+var_240], rax
0x18001d61b  mov     eax, [rbp+270h+arg_40]
0x18001d621  mov     [rbp+270h+var_238], eax
0x18001d624  lea     rax, [rbp+270h+arg_50]
0x18001d62b  mov     [rbp+270h+var_230], rax
0x18001d62f  mov     rax, [rbp+270h+arg_48]
0x18001d636  mov     [rbp+270h+var_220], rax
0x18001d63a  mov     eax, [rbp+270h+arg_50]
0x18001d640  mov     [rbp+270h+var_218], eax
0x18001d643  lea     rax, [rbp+270h+arg_60]
0x18001d64a  mov     [rbp+270h+var_210], rax
0x18001d64e  mov     rax, [rbp+270h+arg_58]
0x18001d655  mov     [rbp+270h+var_200], rax
0x18001d659  mov     eax, [rbp+270h+arg_60]
0x18001d65f  mov     [rbp+270h+var_1F8], eax
0x18001d662  lea     rax, [rbp+270h+arg_68]
0x18001d669  mov     [rbp+270h+var_1F0], rax
0x18001d670  lea     rax, [rbp+270h+arg_70]
0x18001d677  mov     [rbp+270h+var_1E0], rax
0x18001d67e  movzx   eax, [rsp+370h+UnicodeString.Length]
0x18001d683  shr     ax, 1
0x18001d686  mov     [rsp+370h+var_324], ax
0x18001d68b  lea     rax, [rsp+370h+var_324]
0x18001d690  mov     [rbp+270h+var_1D0], rax
0x18001d697  mov     rax, [rsp+370h+UnicodeString.Buffer]
0x18001d69c  mov     [rbp+270h+var_1C0], rax
0x18001d6a3  movzx   eax, [rsp+370h+UnicodeString.Length]
0x18001d6a8  mov     [rbp+270h+var_1B8], eax
0x18001d6ae  movzx   eax, [rbp+270h+var_2F0.Length]
0x18001d6b2  mov     qword ptr [rbp+270h+var_2E0.Size], 2
0x18001d6ba  mov     [rbp+270h+var_2C8], ecx
0x18001d6bd  mov     [rbp+270h+var_2C4], r12d
0x18001d6c1  mov     [rbp+270h+var_2B8], 2
0x18001d6c9  mov     [rbp+270h+var_2A8], edx
0x18001d6cc  mov     [rbp+270h+var_2A4], r12d
0x18001d6d0  mov     [rbp+270h+var_298], 1
0x18001d6d8  mov     [rbp+270h+var_288], 1
0x18001d6e0  mov     [rbp+270h+var_278], 4
0x18001d6e8  mov     [rbp+270h+var_268], 4
0x18001d6f0  mov     [rbp+270h+var_254], r12d
0x18001d6f4  mov     [rbp+270h+var_248], 4
0x18001d6fc  mov     [rbp+270h+var_234], r12d
0x18001d700  mov     [rbp+270h+var_228], 4
0x18001d708  mov     [rbp+270h+var_214], r12d
0x18001d70c  mov     [rbp+270h+var_208], 4
0x18001d714  mov     [rbp+270h+var_1F4], r12d
0x18001d718  mov     [rbp+270h+var_1E8], 8
0x18001d723  mov     [rbp+270h+var_1D8], 4
0x18001d72e  mov     [rbp+270h+var_1C8], 2
0x18001d739  mov     [rbp+270h+var_1B4], r12d
0x18001d740  shr     ax, 1
0x18001d743  mov     [rsp+370h+var_320], ax
0x18001d748  lea     rax, [rsp+370h+var_320]
0x18001d74d  mov     [rbp+270h+var_1B0], rax
0x18001d754  mov     rax, [rbp+270h+var_2F0.Buffer]
0x18001d758  mov     [rbp+270h+var_1A0], rax
0x18001d75f  movzx   eax, [rbp+270h+var_2F0.Length]
0x18001d763  mov     [rbp+270h+var_198], eax
0x18001d769  lea     rax, [rsp+370h+var_308]
0x18001d76e  mov     [rbp+270h+var_190], rax
0x18001d775  lea     rax, [rbp+270h+var_80]
0x18001d77c  mov     [rbp+270h+var_180], rax
0x18001d783  mov     eax, [rsp+370h+var_308]
0x18001d787  mov     [rbp+270h+var_178], eax
0x18001d78d  lea     rax, [rsp+370h+var_304]
0x18001d792  mov     [rbp+270h+var_D0], rax
0x18001d799  mov     [rbp+270h+var_1A8], 2
0x18001d7a4  mov     [rbp+270h+var_194], r12d
0x18001d7ab  mov     [rbp+270h+var_188], 4
0x18001d7b6  mov     [rbp+270h+var_174], r12d
0x18001d7bd  mov     [rbp+270h+var_C8], 4
0x18001d7c8  mov     [rbp+270h+var_168], 2
0x18001d7d3  mov     [rbp+270h+var_148], 2
0x18001d7de  mov     [rbp+270h+var_128], 2
0x18001d7e9  test    rbx, rbx
0x18001d7ec  jz      loc_18001D9B0
0x18001d7f2  movzx   ecx, word ptr [rbx+2E8h]
0x18001d7f9  mov     r9, [rbx+348h]
0x18001d800  movzx   eax, cx
0x18001d803  shr     ax, 1
0x18001d806  mov     [rsp+370h+var_31C], ax
0x18001d80b  lea     rax, [rsp+370h+var_31C]
0x18001d810  mov     [rbp+270h+var_170], rax
0x18001d817  mov     rax, [rbx+2F0h]
0x18001d81e  mov     [rbp+270h+var_160], rax
0x18001d825  mov     [rbp+270h+var_158], ecx
0x18001d82b  movzx   ecx, word ptr [rbx+2F8h]
0x18001d832  movzx   eax, cx
0x18001d835  mov     [rbp+270h+var_138], ecx
0x18001d83b  movzx   ecx, word ptr [rbx+308h]
0x18001d842  shr     ax, 1
0x18001d845  mov     [rsp+370h+var_318], ax
0x18001d84a  lea     rax, [rsp+370h+var_318]
0x18001d84f  mov     [rbp+270h+var_150], rax
0x18001d856  mov     rax, [rbx+300h]
0x18001d85d  mov     [rbp+270h+var_140], rax
0x18001d864  movzx   eax, cx
0x18001d867  shr     ax, 1
0x18001d86a  mov     [rsp+370h+var_314], ax
0x18001d86f  lea     rax, [rsp+370h+var_314]
0x18001d874  mov     [rbp+270h+var_130], rax
0x18001d87b  mov     rax, [rbx+310h]
0x18001d882  mov     [rbp+270h+var_120], rax
0x18001d889  mov     [rbp+270h+var_118], ecx
0x18001d88f  movzx   ecx, word ptr [rbx+318h]
0x18001d896  movzx   eax, cx
0x18001d899  movzx   r8d, r9w
0x18001d89d  shr     ax, 1
0x18001d8a0  mov     [rsp+370h+var_310], ax
0x18001d8a5  lea     rax, [rsp+370h+var_310]
0x18001d8aa  mov     [rbp+270h+var_110], rax
0x18001d8b1  mov     rax, [rbx+320h]
0x18001d8b8  mov     [rbp+270h+var_100], rax
0x18001d8bf  mov     rax, r9
0x18001d8c2  shr     rax, 10h
0x18001d8c6  movzx   edx, ax
0x18001d8c9  mov     rax, r9
0x18001d8cc  mov     [rsp+370h+var_340], r8d
0x18001d8d1  lea     r8, pszFormat; "%hu.%hu.%hu.%hu"
0x18001d8d8  mov     [rbp+270h+var_F8], ecx
0x18001d8de  mov     [rsp+370h+var_348], edx
0x18001d8e2  mov     edx, 18h; cchDest
0x18001d8e7  shr     rax, 20h
0x18001d8eb  movzx   ecx, ax
0x18001d8ee  mov     dword ptr [rsp+370h+UserData], ecx
0x18001d8f2  lea     rcx, [rbp+270h+pszDest]; pszDest
0x18001d8f9  shr     r9, 30h
0x18001d8fd  mov     [rbp+270h+var_154], r12d
0x18001d904  mov     [rbp+270h+var_134], r12d
0x18001d90b  mov     [rbp+270h+var_114], r12d
0x18001d912  mov     [rbp+270h+var_108], 2
0x18001d91d  mov     [rbp+270h+var_F4], r12d
0x18001d924  call    RtlStringCchPrintfA
0x18001d929  test    eax, eax
0x18001d92b  jns     short loc_18001D934
0x18001d92d  mov     [rbp+270h+pszDest], r12b
0x18001d934  lea     rax, [rbp+270h+pszDest]
0x18001d93b  mov     [rbp+270h+var_F0], rax
0x18001d942  lea     rcx, [rbp+270h+pszDest]
0x18001d949  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d94d  inc     rax
0x18001d950  cmp     [rcx+rax], r12b
0x18001d954  jnz     short loc_18001D94D
0x18001d956  mov     rdx, [rbx+340h]
0x18001d95d  inc     eax
0x18001d95f  mov     [rbp+270h+var_E8], eax
0x18001d965  mov     [rbp+270h+var_E4], r12d
0x18001d96c  mov     [rbp+270h+var_B8], 2
0x18001d977  test    rdx, rdx
0x18001d97a  jz      loc_18001DA2E
0x18001d980  movzx   ecx, word ptr [rbx+338h]
0x18001d987  movzx   eax, cx
0x18001d98a  mov     [rbp+270h+var_B0], rdx
0x18001d991  shr     ax, 1
0x18001d994  mov     [rsp+370h+var_30C], ax
0x18001d999  lea     rax, [rsp+370h+var_30C]
0x18001d99e  mov     [rbp+270h+var_A8], ecx
0x18001d9a4  mov     [rbp+270h+var_A4], r12d
0x18001d9ab  jmp     loc_18001DA33
0x18001d9b0  lea     rax, [rsp+370h+var_330]
0x18001d9b5  mov     [rbp+270h+var_108], 2
0x18001d9c0  mov     [rbp+270h+var_170], rax
0x18001d9c7  lea     rcx, [rbp+270h+pszDest]
0x18001d9ce  lea     rax, [rsp+370h+var_330]
0x18001d9d3  mov     [rbp+270h+pszDest], r12b
0x18001d9da  mov     [rbp+270h+var_150], rax
0x18001d9e1  lea     rax, [rsp+370h+var_330]
0x18001d9e6  mov     [rbp+270h+var_130], rax
0x18001d9ed  lea     rax, [rsp+370h+var_330]
0x18001d9f2  mov     [rbp+270h+var_110], rax
0x18001d9f9  lea     rax, [rbp+270h+pszDest]
0x18001da00  mov     [rbp+270h+var_F0], rax
0x18001da07  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001da0b  inc     rax
0x18001da0e  cmp     [rcx+rax], r12b
0x18001da12  jnz     short loc_18001DA0B
0x18001da14  inc     eax
0x18001da16  mov     [rbp+270h+var_E4], r12d
0x18001da1d  mov     [rbp+270h+var_E8], eax
0x18001da23  mov     [rbp+270h+var_B8], 2
0x18001da2e  lea     rax, [rsp+370h+var_330]
0x18001da33  mov     [rbp+270h+var_C0], rax
0x18001da3a  mov     rax, [rbp+270h+arg_20]
0x18001da41  mov     [rbp+270h+var_E0], rax
0x18001da48  mov     [rbp+270h+var_D8], 10h
0x18001da53  call    cs:__imp_IoGetActivityIdThread
0x18001da5a  nop     dword ptr [rax+rax+00h]
0x18001da5f  lea     rcx, [rbp+270h+var_2E0]
0x18001da63  mov     r9d, 24h ; '$'; UserDataCount
0x18001da69  mov     [rsp+370h+UserData], rcx; UserData
0x18001da6e  mov     r8, rax; ActivityId
0x18001da71  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18001da78  mov     rdx, r14; EventDescriptor
0x18001da7b  call    cs:__imp_EtwWrite
0x18001da82  nop     dword ptr [rax+rax+00h]
0x18001da87  mov     edi, eax
0x18001da89  lea     rcx, [rsp+370h+UnicodeString]; UnicodeString
0x18001da8e  call    cs:__imp_RtlFreeUnicodeString
  ... truncated ...
```
