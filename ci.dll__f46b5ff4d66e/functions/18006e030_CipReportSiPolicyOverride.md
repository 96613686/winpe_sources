# CipReportSiPolicyOverride

- ea: `0x18006e030`
- end: `0x18006e794`
- name: `CipReportSiPolicyOverride`
- size: `1892`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18005bd08`

## callees

- `0x18001dae0`
- `0x18002bef0`
- `0x18002c340`
- `0x18006dc18`
- `0x18006e030`
- `0x18009eac8`
- `0x18009ed60`
- `0x18009f370`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e734`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e744`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e754`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e764`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e734`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e744`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e754`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006e764`
- `ntoskrnl!EtwEventEnabled` at `0x18006e147`
- `ntoskrnl!EtwEventEnabled` at `0x18006e147`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006e6ed`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006e6ed`
- `ntoskrnl!EtwWrite` at `0x18006e719`
- `ntoskrnl!EtwWrite` at `0x18006e719`

## pseudocode

```c
__int64 __fastcall CipReportSiPolicyOverride(
        __int64 a1,
        __int64 a2,
        int a3,
        ULONGLONG a4,
        ULONG a5,
        ULONGLONG a6,
        ULONG a7,
        ULONGLONG a8,
        ULONG a9,
        ULONGLONG a10,
        ULONG a11,
        char a12)
{
  ULONG v15; // esi
  ULONGLONG v16; // r15
  __int64 v17; // rdx
  __int64 v19; // rcx
  NTSTATUS PolicyHash; // ebx
  __int64 v21; // rdx
  ULONG v22; // ecx
  ULONG v23; // ecx
  unsigned __int16 v24; // ax
  ULONG v25; // ecx
  unsigned __int64 v26; // r9
  ULONG v27; // ecx
  __int64 v28; // rax
  ULONGLONG v29; // rdx
  ULONG v30; // ecx
  unsigned __int16 v31; // ax
  __int16 *v32; // rax
  __int64 v33; // rcx
  bool v34; // cf
  ULONGLONG v35; // rax
  __int64 v36; // rcx
  const GUID *ActivityIdThread; // rax
  __int16 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v39; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v40; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v41; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v43; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v44; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v45; // [rsp+5Ch] [rbp-A4h] BYREF
  __int16 v46; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v47; // [rsp+64h] [rbp-9Ch] BYREF
  __int16 v48; // [rsp+68h] [rbp-98h] BYREF
  ULONG v49; // [rsp+6Ch] [rbp-94h] BYREF
  ULONG v50; // [rsp+70h] [rbp-90h] BYREF
  int v51; // [rsp+74h] [rbp-8Ch] BYREF
  int v52; // [rsp+78h] [rbp-88h] BYREF
  __int64 v53; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v55; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v56; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v57; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v58; // [rsp+C8h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[40]; // [rsp+E0h] [rbp-20h] BYREF
  char pszDest[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v61[64]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v62[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v63; // [rsp+460h] [rbp+360h] BYREF

  v63 = a3;
  memset(UserData, 0, sizeof(UserData));
  v42 = 0;
  v38 = 0;
  v41 = 0;
  v40 = 0;
  v44 = 0;
  memset(v62, 0, sizeof(v62));
  v50 = 64;
  v48 = 0;
  v47 = 0;
  v56 = 0;
  v57 = 0;
  memset(v61, 0, sizeof(v61));
  v49 = 64;
  v45 = 0;
  v46 = 0;
  v43 = 0;
  v39 = 0;
  UnicodeString = 0;
  v52 = 0;
  v55 = 0;
  v51 = 0;
  v58 = 0;
  v53 = 0;
  CipQueryProcessName(a2, &v58, &v53);
  v15 = *(unsigned __int16 *)(a1 + 808);
  v16 = *(_QWORD *)(a1 + 816);
  if ( !EtwEventEnabled(g_EtwEventHandle, &SiPolicyOverride) )
    return 0;
  v19 = *(_QWORD *)(a1 + 2448);
  v51 = (*(_DWORD *)(a1 + 2360) >> 9) & 1;
  PolicyHash = CipGetPolicyHash(v19, v17, v62, &v50);
  if ( PolicyHash >= 0 )
  {
    PolicyHash = CiLogSIPolicyGetPolicyIDs(*(_QWORD *)(a1 + 2448), &v57, &v56);
    if ( PolicyHash >= 0 )
    {
      PolicyHash = CipGetPolicyHash(*(_QWORD *)(a1 + 2456), v21, v61, &v49);
      if ( PolicyHash >= 0 )
      {
        PolicyHash = CiLogSIPolicyGetPolicyIDs(*(_QWORD *)(a1 + 2456), &v55, &UnicodeString);
        if ( PolicyHash >= 0 )
        {
          v22 = *(unsigned __int16 *)(a1 + 744);
          v38 = (unsigned __int16)v15 >> 1;
          v39 = (unsigned __int16)v58 >> 1;
          UserData[0].Ptr = (ULONGLONG)&v38;
          UserData[2].Ptr = (ULONGLONG)&v39;
          UserData[3].Ptr = *((_QWORD *)&v58 + 1);
          UserData[3].Size = (unsigned __int16)v58;
          UserData[4].Ptr = (ULONGLONG)&a5;
          UserData[5].Size = a5;
          UserData[6].Ptr = (ULONGLONG)&a7;
          UserData[7].Ptr = a6;
          UserData[7].Size = a7;
          UserData[8].Ptr = (ULONGLONG)&a9;
          UserData[9].Ptr = a8;
          UserData[9].Size = a9;
          UserData[10].Ptr = (ULONGLONG)&a11;
          UserData[11].Ptr = a10;
          UserData[11].Size = a11;
          UserData[12].Ptr = (ULONGLONG)&a12;
          UserData[13].Ptr = (ULONGLONG)&v63;
          UserData[23].Ptr = (ULONGLONG)&v51;
          v40 = (unsigned __int16)v22 >> 1;
          UserData[14].Ptr = (ULONGLONG)&v40;
          UserData[15].Ptr = *(_QWORD *)(a1 + 752);
          UserData[15].Size = v22;
          v23 = *(unsigned __int16 *)(a1 + 760);
          v24 = *(_WORD *)(a1 + 760);
          *(_QWORD *)&UserData[0].Size = 2;
          v41 = v24 >> 1;
          UserData[16].Ptr = (ULONGLONG)&v41;
          UserData[17].Ptr = *(_QWORD *)(a1 + 768);
          UserData[1].Ptr = v16;
          UserData[1].Size = v15;
          UserData[1].Reserved = 0;
          *(_QWORD *)&UserData[2].Size = 2;
          UserData[3].Reserved = 0;
          *(_QWORD *)&UserData[4].Size = 4;
          UserData[5].Ptr = a4;
          UserData[5].Reserved = 0;
          *(_QWORD *)&UserData[6].Size = 4;
          UserData[7].Reserved = 0;
          *(_QWORD *)&UserData[8].Size = 4;
          UserData[9].Reserved = 0;
          *(_QWORD *)&UserData[10].Size = 4;
          UserData[11].Reserved = 0;
          *(_QWORD *)&UserData[12].Size = 8;
          *(_QWORD *)&UserData[13].Size = 4;
          *(_QWORD *)&UserData[23].Size = 4;
          *(_QWORD *)&UserData[14].Size = 2;
          UserData[15].Reserved = 0;
          *(_QWORD *)&UserData[16].Size = 2;
          UserData[17].Size = v23;
          v25 = *(unsigned __int16 *)(a1 + 776);
          v26 = *(_QWORD *)(a1 + 840);
          v42 = *(_WORD *)(a1 + 776) >> 1;
          UserData[18].Ptr = (ULONGLONG)&v42;
          UserData[19].Ptr = *(_QWORD *)(a1 + 784);
          UserData[19].Size = v25;
          v27 = *(unsigned __int16 *)(a1 + 792);
          v43 = *(_WORD *)(a1 + 792) >> 1;
          UserData[20].Ptr = (ULONGLONG)&v43;
          UserData[21].Ptr = *(_QWORD *)(a1 + 800);
          UserData[21].Size = v27;
          UserData[17].Reserved = 0;
          *(_QWORD *)&UserData[18].Size = 2;
          UserData[19].Reserved = 0;
          *(_QWORD *)&UserData[20].Size = 2;
          UserData[21].Reserved = 0;
          if ( RtlStringCchPrintfA(
                 pszDest,
                 0x18u,
                 "%hu.%hu.%hu.%hu",
                 HIWORD(v26),
                 WORD2(v26),
                 WORD1(v26),
                 (unsigned __int16)v26) < 0 )
            pszDest[0] = 0;
          UserData[22].Ptr = (ULONGLONG)pszDest;
          v28 = -1;
          do
            ++v28;
          while ( pszDest[v28] );
          v29 = *(_QWORD *)(a1 + 832);
          UserData[22].Size = v28 + 1;
          UserData[22].Reserved = 0;
          *(_QWORD *)&UserData[24].Size = 2;
          if ( v29 )
          {
            v30 = *(unsigned __int16 *)(a1 + 824);
            v31 = *(_WORD *)(a1 + 824);
            UserData[25].Ptr = v29;
            v44 = v31 >> 1;
            v32 = &v44;
            UserData[25].Size = v30;
            UserData[25].Reserved = 0;
          }
          else
          {
            v32 = (__int16 *)&v52;
          }
          UserData[24].Ptr = (ULONGLONG)v32;
          v33 = *(_QWORD *)(a1 + 2456);
          v45 = UnicodeString.Length >> 1;
          UserData[26].Ptr = (ULONGLONG)&v45;
          UserData[27].Ptr = (ULONGLONG)UnicodeString.Buffer;
          UserData[27].Size = UnicodeString.Length;
          v46 = v55.Length >> 1;
          UserData[28].Ptr = (ULONGLONG)&v46;
          UserData[29].Ptr = (ULONGLONG)v55.Buffer;
          UserData[29].Size = v55.Length;
          *(_QWORD *)&UserData[26].Size = 2;
          UserData[27].Reserved = 0;
          *(_QWORD *)&UserData[28].Size = 2;
          UserData[29].Reserved = 0;
          v34 = *(_DWORD *)(v33 + 40) < 6u;
          *(_QWORD *)&UserData[30].Size = 16;
          *(_QWORD *)&UserData[31].Size = 4;
          UserData[32].Reserved = 0;
          *(_QWORD *)&UserData[33].Size = 2;
          v35 = v33 + (-(__int64)v34 & 0xFFFFFFFFFFFFFD50uLL) + 704;
          UserData[34].Reserved = 0;
          v36 = *(_QWORD *)(a1 + 2448);
          UserData[30].Ptr = v35;
          UserData[31].Ptr = (ULONGLONG)&v49;
          UserData[32].Ptr = (ULONGLONG)v61;
          UserData[32].Size = v49;
          v47 = v56.Length >> 1;
          UserData[33].Ptr = (ULONGLONG)&v47;
          UserData[34].Ptr = (ULONGLONG)v56.Buffer;
          UserData[34].Size = v56.Length;
          v48 = v57.Length >> 1;
          UserData[35].Ptr = (ULONGLONG)&v48;
          UserData[36].Ptr = (ULONGLONG)v57.Buffer;
          UserData[36].Size = v57.Length;
          *(_QWORD *)&UserData[35].Size = 2;
          UserData[36].Reserved = 0;
          v34 = *(_DWORD *)(v36 + 40) < 6u;
          *(_QWORD *)&UserData[37].Size = 16;
          *(_QWORD *)&UserData[38].Size = 4;
          UserData[39].Reserved = 0;
          UserData[37].Ptr = v36 + (-(__int64)v34 & 0xFFFFFFFFFFFFFD50uLL) + 704;
          UserData[38].Ptr = (ULONGLONG)&v50;
          UserData[39].Ptr = (ULONGLONG)v62;
          UserData[39].Size = v50;
          ActivityIdThread = (const GUID *)IoGetActivityIdThread();
          PolicyHash = EtwWrite(g_EtwEventHandle, &SiPolicyOverride, ActivityIdThread, 0x28u, UserData);
        }
      }
    }
  }
  CipReleaseProcessName(v53);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v55);
  RtlFreeUnicodeString(&v56);
  RtlFreeUnicodeString(&v57);
  return (unsigned int)PolicyHash;
}

```

## disassembly

```asm
0x18006e030  mov     [rsp-8+arg_10], r8d
0x18006e035  push    rbp
0x18006e036  push    rbx
0x18006e037  push    rsi
0x18006e038  push    rdi
0x18006e039  push    r12
0x18006e03b  push    r14
0x18006e03d  push    r15
0x18006e03f  lea     rbp, [rsp-310h]
0x18006e047  sub     rsp, 410h
0x18006e04e  mov     rax, cs:__security_cookie
0x18006e055  xor     rax, rsp
0x18006e058  mov     [rbp+340h+var_40], rax
0x18006e05f  mov     rbx, rdx
0x18006e062  mov     rdi, rcx
0x18006e065  xor     edx, edx; Val
0x18006e067  lea     rcx, [rbp+340h+var_360]; void *
0x18006e06b  mov     r8d, 280h; Size
0x18006e071  mov     r14, r9
0x18006e074  call    memset
0x18006e079  xor     r12d, r12d
0x18006e07c  lea     rcx, [rbp+340h+var_80]; void *
0x18006e083  xor     edx, edx; Val
0x18006e085  mov     [rsp+440h+var_3F0], r12w
0x18006e08b  mov     [rsp+440h+var_400], r12w
0x18006e091  mov     [rsp+440h+var_3F4], r12w
0x18006e097  lea     esi, [r12+40h]
0x18006e09c  mov     [rsp+440h+var_3F8], r12w
0x18006e0a2  mov     r8d, esi; Size
0x18006e0a5  mov     [rsp+440h+var_3E8], r12w
0x18006e0ab  call    memset
0x18006e0b0  xorps   xmm0, xmm0
0x18006e0b3  mov     [rsp+440h+var_3D0], esi
0x18006e0b7  xorps   xmm1, xmm1
0x18006e0ba  mov     [rsp+440h+var_3D8], r12w
0x18006e0c0  mov     r8d, esi; Size
0x18006e0c3  mov     [rsp+440h+var_3DC], r12w
0x18006e0c9  xor     edx, edx; Val
0x18006e0cb  lea     rcx, [rbp+340h+var_C0]; void *
0x18006e0d2  movups  xmmword ptr [rbp+340h+var_398.Length], xmm0
0x18006e0d6  movups  xmmword ptr [rbp+340h+var_388.Length], xmm1
0x18006e0da  call    memset
0x18006e0df  xorps   xmm0, xmm0
0x18006e0e2  mov     [rsp+440h+var_3D4], esi
0x18006e0e6  xorps   xmm1, xmm1
0x18006e0e9  mov     [rsp+440h+var_3E4], r12w
0x18006e0ef  lea     r8, [rbp+340h+var_3C0]
0x18006e0f3  mov     [rsp+440h+var_3E0], r12w
0x18006e0f9  lea     rdx, [rbp+340h+var_378]
0x18006e0fd  mov     [rsp+440h+var_3EC], r12w
0x18006e103  mov     rcx, rbx
0x18006e106  mov     [rsp+440h+var_3FC], r12w
0x18006e10c  movups  xmmword ptr [rbp+340h+UnicodeString.Length], xmm0
0x18006e110  mov     [rsp+440h+var_3C8], r12d
0x18006e115  movups  xmmword ptr [rbp+340h+var_3A8.Length], xmm1
0x18006e119  mov     [rsp+440h+var_3CC], r12d
0x18006e11e  movups  [rbp+340h+var_378], xmm0
0x18006e122  mov     [rbp+340h+var_3C0], r12
0x18006e126  call    CipQueryProcessName
0x18006e12b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006e132  lea     rdx, SiPolicyOverride; EventDescriptor
0x18006e139  movzx   esi, word ptr [rdi+328h]
0x18006e140  mov     r15, [rdi+330h]
0x18006e147  call    cs:__imp_EtwEventEnabled
0x18006e14e  nop     dword ptr [rax+rax+00h]
0x18006e153  test    al, al
0x18006e155  jnz     short loc_18006E15E
0x18006e157  xor     eax, eax
0x18006e159  jmp     loc_18006E772
0x18006e15e  mov     eax, [rdi+938h]
0x18006e164  lea     r9, [rsp+440h+var_3D0]
0x18006e169  mov     rcx, [rdi+990h]
0x18006e170  lea     r8, [rbp+340h+var_80]
0x18006e177  shr     eax, 9
0x18006e17a  and     eax, 1
0x18006e17d  mov     [rsp+440h+var_3CC], eax
0x18006e181  call    CipGetPolicyHash
0x18006e186  mov     ebx, eax
0x18006e188  test    eax, eax
0x18006e18a  js      loc_18006E727
0x18006e190  mov     rcx, [rdi+990h]
0x18006e197  lea     r8, [rbp+340h+var_398]
0x18006e19b  lea     rdx, [rbp+340h+var_388]
0x18006e19f  call    CiLogSIPolicyGetPolicyIDs
0x18006e1a4  mov     ebx, eax
0x18006e1a6  test    eax, eax
0x18006e1a8  js      loc_18006E727
0x18006e1ae  mov     rcx, [rdi+998h]
0x18006e1b5  lea     r9, [rsp+440h+var_3D4]
0x18006e1ba  lea     r8, [rbp+340h+var_C0]
0x18006e1c1  call    CipGetPolicyHash
0x18006e1c6  mov     ebx, eax
0x18006e1c8  test    eax, eax
0x18006e1ca  js      loc_18006E727
0x18006e1d0  mov     rcx, [rdi+998h]
0x18006e1d7  lea     r8, [rbp+340h+UnicodeString]
0x18006e1db  lea     rdx, [rbp+340h+var_3A8]
0x18006e1df  call    CiLogSIPolicyGetPolicyIDs
0x18006e1e4  mov     ebx, eax
0x18006e1e6  test    eax, eax
0x18006e1e8  js      loc_18006E727
0x18006e1ee  movzx   ecx, word ptr [rdi+2E8h]
0x18006e1f5  movzx   eax, si
0x18006e1f8  shr     ax, 1
0x18006e1fb  mov     [rsp+440h+var_400], ax
0x18006e200  movzx   eax, word ptr [rbp+340h+var_378]
0x18006e204  shr     ax, 1
0x18006e207  mov     [rsp+440h+var_3FC], ax
0x18006e20c  lea     rax, [rsp+440h+var_400]
0x18006e211  mov     [rbp+340h+var_360.Ptr], rax
0x18006e215  lea     rax, [rsp+440h+var_3FC]
0x18006e21a  mov     [rbp+340h+var_340], rax
0x18006e21e  mov     rax, qword ptr [rbp+340h+var_378+8]
0x18006e222  mov     [rbp+340h+var_330], rax
0x18006e226  movzx   eax, word ptr [rbp+340h+var_378]
0x18006e22a  mov     [rbp+340h+var_328], eax
0x18006e22d  lea     rax, [rbp+340h+arg_20]
0x18006e234  mov     [rbp+340h+var_320], rax
0x18006e238  mov     eax, [rbp+340h+arg_20]
0x18006e23e  mov     [rbp+340h+var_308], eax
0x18006e241  lea     rax, [rbp+340h+arg_30]
0x18006e248  mov     [rbp+340h+var_300], rax
0x18006e24c  mov     rax, [rbp+340h+arg_28]
0x18006e253  mov     [rbp+340h+var_2F0], rax
0x18006e257  mov     eax, [rbp+340h+arg_30]
0x18006e25d  mov     [rbp+340h+var_2E8], eax
0x18006e260  lea     rax, [rbp+340h+arg_40]
0x18006e267  mov     [rbp+340h+var_2E0], rax
0x18006e26b  mov     rax, [rbp+340h+arg_38]
0x18006e272  mov     [rbp+340h+var_2D0], rax
0x18006e276  mov     eax, [rbp+340h+arg_40]
0x18006e27c  mov     [rbp+340h+var_2C8], eax
0x18006e27f  lea     rax, [rbp+340h+arg_50]
0x18006e286  mov     [rbp+340h+var_2C0], rax
0x18006e28d  mov     rax, [rbp+340h+arg_48]
0x18006e294  mov     [rbp+340h+var_2B0], rax
0x18006e29b  mov     eax, [rbp+340h+arg_50]
0x18006e2a1  mov     [rbp+340h+var_2A8], eax
0x18006e2a7  lea     rax, [rbp+340h+arg_58]
0x18006e2ae  mov     [rbp+340h+var_2A0], rax
0x18006e2b5  lea     rax, [rbp+340h+arg_10]
0x18006e2bc  mov     [rbp+340h+var_290], rax
0x18006e2c3  lea     rax, [rsp+440h+var_3CC]
0x18006e2c8  mov     [rbp+340h+var_1F0], rax
0x18006e2cf  movzx   eax, cx
0x18006e2d2  shr     ax, 1
0x18006e2d5  mov     [rsp+440h+var_3F8], ax
0x18006e2da  lea     rax, [rsp+440h+var_3F8]
0x18006e2df  mov     [rbp+340h+var_280], rax
0x18006e2e6  mov     rax, [rdi+2F0h]
0x18006e2ed  mov     [rbp+340h+var_270], rax
0x18006e2f4  mov     [rbp+340h+var_268], ecx
0x18006e2fa  movzx   ecx, word ptr [rdi+2F8h]
0x18006e301  movzx   eax, cx
0x18006e304  mov     qword ptr [rbp+340h+var_360.Size], 2
0x18006e30c  shr     ax, 1
0x18006e30f  mov     [rsp+440h+var_3F4], ax
0x18006e314  lea     rax, [rsp+440h+var_3F4]
0x18006e319  mov     [rbp+340h+var_260], rax
0x18006e320  mov     rax, [rdi+300h]
0x18006e327  mov     [rbp+340h+var_250], rax
0x18006e32e  mov     [rbp+340h+var_350], r15
0x18006e332  mov     [rbp+340h+var_348], esi
0x18006e335  mov     [rbp+340h+var_344], r12d
0x18006e339  mov     [rbp+340h+var_338], 2
0x18006e341  mov     [rbp+340h+var_324], r12d
0x18006e345  mov     [rbp+340h+var_318], 4
0x18006e34d  mov     [rbp+340h+var_310], r14
0x18006e351  mov     [rbp+340h+var_304], r12d
0x18006e355  mov     [rbp+340h+var_2F8], 4
0x18006e35d  mov     [rbp+340h+var_2E4], r12d
0x18006e361  mov     [rbp+340h+var_2D8], 4
0x18006e369  mov     [rbp+340h+var_2C4], r12d
0x18006e36d  mov     [rbp+340h+var_2B8], 4
0x18006e378  mov     [rbp+340h+var_2A4], r12d
0x18006e37f  mov     [rbp+340h+var_298], 8
0x18006e38a  mov     [rbp+340h+var_288], 4
0x18006e395  mov     [rbp+340h+var_1E8], 4
0x18006e3a0  mov     [rbp+340h+var_278], 2
0x18006e3ab  mov     [rbp+340h+var_264], r12d
0x18006e3b2  mov     [rbp+340h+var_258], 2
0x18006e3bd  mov     [rbp+340h+var_248], ecx
0x18006e3c3  movzx   ecx, word ptr [rdi+308h]
0x18006e3ca  mov     r9, [rdi+348h]
0x18006e3d1  movzx   eax, cx
0x18006e3d4  shr     ax, 1
0x18006e3d7  mov     [rsp+440h+var_3F0], ax
0x18006e3dc  lea     rax, [rsp+440h+var_3F0]
0x18006e3e1  mov     [rbp+340h+var_240], rax
0x18006e3e8  mov     rax, [rdi+310h]
0x18006e3ef  mov     [rbp+340h+var_230], rax
0x18006e3f6  mov     [rbp+340h+var_228], ecx
0x18006e3fc  movzx   ecx, word ptr [rdi+318h]
0x18006e403  movzx   eax, cx
0x18006e406  movzx   r8d, r9w
0x18006e40a  shr     ax, 1
0x18006e40d  mov     [rsp+440h+var_3EC], ax
0x18006e412  lea     rax, [rsp+440h+var_3EC]
0x18006e417  mov     [rbp+340h+var_220], rax
0x18006e41e  mov     rax, [rdi+320h]
0x18006e425  mov     [rbp+340h+var_210], rax
0x18006e42c  mov     rax, r9
0x18006e42f  shr     rax, 10h
0x18006e433  movzx   edx, ax
0x18006e436  mov     rax, r9
0x18006e439  mov     [rsp+440h+var_410], r8d
0x18006e43e  lea     r8, pszFormat; "%hu.%hu.%hu.%hu"
0x18006e445  mov     [rbp+340h+var_208], ecx
0x18006e44b  mov     [rsp+440h+var_418], edx
0x18006e44f  mov     edx, 18h; cchDest
0x18006e454  shr     rax, 20h
0x18006e458  movzx   ecx, ax
0x18006e45b  mov     dword ptr [rsp+440h+UserData], ecx
0x18006e45f  lea     rcx, [rbp+340h+pszDest]; pszDest
0x18006e466  shr     r9, 30h
0x18006e46a  mov     [rbp+340h+var_244], r12d
0x18006e471  mov     [rbp+340h+var_238], 2
0x18006e47c  mov     [rbp+340h+var_224], r12d
0x18006e483  mov     [rbp+340h+var_218], 2
0x18006e48e  mov     [rbp+340h+var_204], r12d
0x18006e495  call    RtlStringCchPrintfA
0x18006e49a  test    eax, eax
0x18006e49c  jns     short loc_18006E4A5
0x18006e49e  mov     [rbp+340h+pszDest], r12b
0x18006e4a5  lea     rax, [rbp+340h+pszDest]
0x18006e4ac  mov     [rbp+340h+var_200], rax
0x18006e4b3  lea     rcx, [rbp+340h+pszDest]
0x18006e4ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e4be  inc     rax
0x18006e4c1  cmp     [rcx+rax], r12b
0x18006e4c5  jnz     short loc_18006E4BE
0x18006e4c7  mov     rdx, [rdi+340h]
0x18006e4ce  inc     eax
0x18006e4d0  mov     [rbp+340h+var_1F8], eax
0x18006e4d6  mov     [rbp+340h+var_1F4], r12d
0x18006e4dd  mov     [rbp+340h+var_1D8], 2
0x18006e4e8  test    rdx, rdx
0x18006e4eb  jz      short loc_18006E51A
0x18006e4ed  movzx   ecx, word ptr [rdi+338h]
0x18006e4f4  movzx   eax, cx
0x18006e4f7  mov     [rbp+340h+var_1D0], rdx
0x18006e4fe  shr     ax, 1
0x18006e501  mov     [rsp+440h+var_3E8], ax
0x18006e506  lea     rax, [rsp+440h+var_3E8]
0x18006e50b  mov     [rbp+340h+var_1C8], ecx
0x18006e511  mov     [rbp+340h+var_1C4], r12d
0x18006e518  jmp     short loc_18006E51F
0x18006e51a  lea     rax, [rsp+440h+var_3C8]
0x18006e51f  mov     [rbp+340h+var_1E0], rax
0x18006e526  mov     r9, 0FFFFFFFFFFFFFD50h
0x18006e52d  mov     rcx, [rdi+998h]
0x18006e534  mov     r8d, 2C0h
0x18006e53a  movzx   eax, [rbp+340h+UnicodeString.Length]
0x18006e53e  shr     ax, 1
0x18006e541  mov     [rsp+440h+var_3E4], ax
0x18006e546  lea     rax, [rsp+440h+var_3E4]
0x18006e54b  mov     [rbp+340h+var_1C0], rax
0x18006e552  mov     rax, [rbp+340h+UnicodeString.Buffer]
0x18006e556  mov     [rbp+340h+var_1B0], rax
0x18006e55d  movzx   eax, [rbp+340h+UnicodeString.Length]
0x18006e561  mov     [rbp+340h+var_1A8], eax
0x18006e567  movzx   eax, [rbp+340h+var_3A8.Length]
0x18006e56b  shr     ax, 1
0x18006e56e  mov     [rsp+440h+var_3E0], ax
0x18006e573  lea     rax, [rsp+440h+var_3E0]
0x18006e578  mov     [rbp+340h+var_1A0], rax
0x18006e57f  mov     rax, [rbp+340h+var_3A8.Buffer]
0x18006e583  mov     [rbp+340h+var_190], rax
0x18006e58a  movzx   eax, [rbp+340h+var_3A8.Length]
0x18006e58e  mov     [rbp+340h+var_188], eax
0x18006e594  mov     [rbp+340h+var_1B8], 2
0x18006e59f  mov     [rbp+340h+var_1A4], r12d
0x18006e5a6  mov     [rbp+340h+var_198], 2
0x18006e5b1  mov     [rbp+340h+var_184], r12d
0x18006e5b8  cmp     dword ptr [rcx+28h], 6
0x18006e5bc  mov     [rbp+340h+var_178], 10h
0x18006e5c7  sbb     rax, rax
0x18006e5ca  mov     [rbp+340h+var_168], 4
0x18006e5d5  and     rax, r9
0x18006e5d8  mov     [rbp+340h+var_154], r12d
0x18006e5df  add     rax, r8
0x18006e5e2  mov     [rbp+340h+var_148], 2
0x18006e5ed  add     rax, rcx
0x18006e5f0  mov     [rbp+340h+var_134], r12d
0x18006e5f7  mov     rcx, [rdi+990h]
0x18006e5fe  mov     [rbp+340h+var_180], rax
0x18006e605  lea     rax, [rsp+440h+var_3D4]
0x18006e60a  mov     [rbp+340h+var_170], rax
0x18006e611  lea     rax, [rbp+340h+var_C0]
0x18006e618  mov     [rbp+340h+var_160], rax
0x18006e61f  mov     eax, [rsp+440h+var_3D4]
0x18006e623  mov     [rbp+340h+var_158], eax
0x18006e629  movzx   eax, [rbp+340h+var_398.Length]
0x18006e62d  shr     ax, 1
0x18006e630  mov     [rsp+440h+var_3DC], ax
0x18006e635  lea     rax, [rsp+440h+var_3DC]
0x18006e63a  mov     [rbp+340h+var_150], rax
0x18006e641  mov     rax, [rbp+340h+var_398.Buffer]
0x18006e645  mov     [rbp+340h+var_140], rax
0x18006e64c  movzx   eax, [rbp+340h+var_398.Length]
  ... truncated ...
```
