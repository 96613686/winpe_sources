# CipReportSiPolicyOverride

- ea: `0x18006f5c0`
- end: `0x18006fd24`
- name: `CipReportSiPolicyOverride`
- size: `1892`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006ef98`

## callees

- `0x18001daf4`
- `0x18002c0d0`
- `0x18002c500`
- `0x18006eccc`
- `0x18006f5c0`
- `0x18008f038`
- `0x18008f2d0`
- `0x180091448`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006fcc4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006fcd4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006fce4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006fcf4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006fcc4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006fcd4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006fce4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006fcf4`
- `ntoskrnl!EtwEventEnabled` at `0x18006f6d7`
- `ntoskrnl!EtwEventEnabled` at `0x18006f6d7`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006fc7d`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006fc7d`
- `ntoskrnl!EtwWrite` at `0x18006fca9`
- `ntoskrnl!EtwWrite` at `0x18006fca9`

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
  v19 = *(_QWORD *)(a1 + 2456);
  v51 = (*(_DWORD *)(a1 + 2368) >> 9) & 1;
  PolicyHash = CipGetPolicyHash(v19, v17, v62, &v50);
  if ( PolicyHash >= 0 )
  {
    PolicyHash = CiLogSIPolicyGetPolicyIDs(*(_QWORD *)(a1 + 2456), &v57, &v56);
    if ( PolicyHash >= 0 )
    {
      PolicyHash = CipGetPolicyHash(*(_QWORD *)(a1 + 2464), v21, v61, &v49);
      if ( PolicyHash >= 0 )
      {
        PolicyHash = CiLogSIPolicyGetPolicyIDs(*(_QWORD *)(a1 + 2464), &v55, &UnicodeString);
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
          v33 = *(_QWORD *)(a1 + 2464);
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
          v36 = *(_QWORD *)(a1 + 2456);
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
0x18006f5c0  mov     [rsp-8+arg_10], r8d
0x18006f5c5  push    rbp
0x18006f5c6  push    rbx
0x18006f5c7  push    rsi
0x18006f5c8  push    rdi
0x18006f5c9  push    r12
0x18006f5cb  push    r14
0x18006f5cd  push    r15
0x18006f5cf  lea     rbp, [rsp-310h]
0x18006f5d7  sub     rsp, 410h
0x18006f5de  mov     rax, cs:__security_cookie
0x18006f5e5  xor     rax, rsp
0x18006f5e8  mov     [rbp+340h+var_40], rax
0x18006f5ef  mov     rbx, rdx
0x18006f5f2  mov     rdi, rcx
0x18006f5f5  xor     edx, edx; Val
0x18006f5f7  lea     rcx, [rbp+340h+var_360]; void *
0x18006f5fb  mov     r8d, 280h; Size
0x18006f601  mov     r14, r9
0x18006f604  call    memset
0x18006f609  xor     r12d, r12d
0x18006f60c  lea     rcx, [rbp+340h+var_80]; void *
0x18006f613  xor     edx, edx; Val
0x18006f615  mov     [rsp+440h+var_3F0], r12w
0x18006f61b  mov     [rsp+440h+var_400], r12w
0x18006f621  mov     [rsp+440h+var_3F4], r12w
0x18006f627  lea     esi, [r12+40h]
0x18006f62c  mov     [rsp+440h+var_3F8], r12w
0x18006f632  mov     r8d, esi; Size
0x18006f635  mov     [rsp+440h+var_3E8], r12w
0x18006f63b  call    memset
0x18006f640  xorps   xmm0, xmm0
0x18006f643  mov     [rsp+440h+var_3D0], esi
0x18006f647  xorps   xmm1, xmm1
0x18006f64a  mov     [rsp+440h+var_3D8], r12w
0x18006f650  mov     r8d, esi; Size
0x18006f653  mov     [rsp+440h+var_3DC], r12w
0x18006f659  xor     edx, edx; Val
0x18006f65b  lea     rcx, [rbp+340h+var_C0]; void *
0x18006f662  movups  xmmword ptr [rbp+340h+var_398.Length], xmm0
0x18006f666  movups  xmmword ptr [rbp+340h+var_388.Length], xmm1
0x18006f66a  call    memset
0x18006f66f  xorps   xmm0, xmm0
0x18006f672  mov     [rsp+440h+var_3D4], esi
0x18006f676  xorps   xmm1, xmm1
0x18006f679  mov     [rsp+440h+var_3E4], r12w
0x18006f67f  lea     r8, [rbp+340h+var_3C0]
0x18006f683  mov     [rsp+440h+var_3E0], r12w
0x18006f689  lea     rdx, [rbp+340h+var_378]
0x18006f68d  mov     [rsp+440h+var_3EC], r12w
0x18006f693  mov     rcx, rbx
0x18006f696  mov     [rsp+440h+var_3FC], r12w
0x18006f69c  movups  xmmword ptr [rbp+340h+UnicodeString.Length], xmm0
0x18006f6a0  mov     [rsp+440h+var_3C8], r12d
0x18006f6a5  movups  xmmword ptr [rbp+340h+var_3A8.Length], xmm1
0x18006f6a9  mov     [rsp+440h+var_3CC], r12d
0x18006f6ae  movups  [rbp+340h+var_378], xmm0
0x18006f6b2  mov     [rbp+340h+var_3C0], r12
0x18006f6b6  call    CipQueryProcessName
0x18006f6bb  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006f6c2  lea     rdx, SiPolicyOverride; EventDescriptor
0x18006f6c9  movzx   esi, word ptr [rdi+328h]
0x18006f6d0  mov     r15, [rdi+330h]
0x18006f6d7  call    cs:__imp_EtwEventEnabled
0x18006f6de  nop     dword ptr [rax+rax+00h]
0x18006f6e3  test    al, al
0x18006f6e5  jnz     short loc_18006F6EE
0x18006f6e7  xor     eax, eax
0x18006f6e9  jmp     loc_18006FD02
0x18006f6ee  mov     eax, [rdi+940h]
0x18006f6f4  lea     r9, [rsp+440h+var_3D0]
0x18006f6f9  mov     rcx, [rdi+998h]
0x18006f700  lea     r8, [rbp+340h+var_80]
0x18006f707  shr     eax, 9
0x18006f70a  and     eax, 1
0x18006f70d  mov     [rsp+440h+var_3CC], eax
0x18006f711  call    CipGetPolicyHash
0x18006f716  mov     ebx, eax
0x18006f718  test    eax, eax
0x18006f71a  js      loc_18006FCB7
0x18006f720  mov     rcx, [rdi+998h]
0x18006f727  lea     r8, [rbp+340h+var_398]
0x18006f72b  lea     rdx, [rbp+340h+var_388]
0x18006f72f  call    CiLogSIPolicyGetPolicyIDs
0x18006f734  mov     ebx, eax
0x18006f736  test    eax, eax
0x18006f738  js      loc_18006FCB7
0x18006f73e  mov     rcx, [rdi+9A0h]
0x18006f745  lea     r9, [rsp+440h+var_3D4]
0x18006f74a  lea     r8, [rbp+340h+var_C0]
0x18006f751  call    CipGetPolicyHash
0x18006f756  mov     ebx, eax
0x18006f758  test    eax, eax
0x18006f75a  js      loc_18006FCB7
0x18006f760  mov     rcx, [rdi+9A0h]
0x18006f767  lea     r8, [rbp+340h+UnicodeString]
0x18006f76b  lea     rdx, [rbp+340h+var_3A8]
0x18006f76f  call    CiLogSIPolicyGetPolicyIDs
0x18006f774  mov     ebx, eax
0x18006f776  test    eax, eax
0x18006f778  js      loc_18006FCB7
0x18006f77e  movzx   ecx, word ptr [rdi+2E8h]
0x18006f785  movzx   eax, si
0x18006f788  shr     ax, 1
0x18006f78b  mov     [rsp+440h+var_400], ax
0x18006f790  movzx   eax, word ptr [rbp+340h+var_378]
0x18006f794  shr     ax, 1
0x18006f797  mov     [rsp+440h+var_3FC], ax
0x18006f79c  lea     rax, [rsp+440h+var_400]
0x18006f7a1  mov     [rbp+340h+var_360.Ptr], rax
0x18006f7a5  lea     rax, [rsp+440h+var_3FC]
0x18006f7aa  mov     [rbp+340h+var_340], rax
0x18006f7ae  mov     rax, qword ptr [rbp+340h+var_378+8]
0x18006f7b2  mov     [rbp+340h+var_330], rax
0x18006f7b6  movzx   eax, word ptr [rbp+340h+var_378]
0x18006f7ba  mov     [rbp+340h+var_328], eax
0x18006f7bd  lea     rax, [rbp+340h+arg_20]
0x18006f7c4  mov     [rbp+340h+var_320], rax
0x18006f7c8  mov     eax, [rbp+340h+arg_20]
0x18006f7ce  mov     [rbp+340h+var_308], eax
0x18006f7d1  lea     rax, [rbp+340h+arg_30]
0x18006f7d8  mov     [rbp+340h+var_300], rax
0x18006f7dc  mov     rax, [rbp+340h+arg_28]
0x18006f7e3  mov     [rbp+340h+var_2F0], rax
0x18006f7e7  mov     eax, [rbp+340h+arg_30]
0x18006f7ed  mov     [rbp+340h+var_2E8], eax
0x18006f7f0  lea     rax, [rbp+340h+arg_40]
0x18006f7f7  mov     [rbp+340h+var_2E0], rax
0x18006f7fb  mov     rax, [rbp+340h+arg_38]
0x18006f802  mov     [rbp+340h+var_2D0], rax
0x18006f806  mov     eax, [rbp+340h+arg_40]
0x18006f80c  mov     [rbp+340h+var_2C8], eax
0x18006f80f  lea     rax, [rbp+340h+arg_50]
0x18006f816  mov     [rbp+340h+var_2C0], rax
0x18006f81d  mov     rax, [rbp+340h+arg_48]
0x18006f824  mov     [rbp+340h+var_2B0], rax
0x18006f82b  mov     eax, [rbp+340h+arg_50]
0x18006f831  mov     [rbp+340h+var_2A8], eax
0x18006f837  lea     rax, [rbp+340h+arg_58]
0x18006f83e  mov     [rbp+340h+var_2A0], rax
0x18006f845  lea     rax, [rbp+340h+arg_10]
0x18006f84c  mov     [rbp+340h+var_290], rax
0x18006f853  lea     rax, [rsp+440h+var_3CC]
0x18006f858  mov     [rbp+340h+var_1F0], rax
0x18006f85f  movzx   eax, cx
0x18006f862  shr     ax, 1
0x18006f865  mov     [rsp+440h+var_3F8], ax
0x18006f86a  lea     rax, [rsp+440h+var_3F8]
0x18006f86f  mov     [rbp+340h+var_280], rax
0x18006f876  mov     rax, [rdi+2F0h]
0x18006f87d  mov     [rbp+340h+var_270], rax
0x18006f884  mov     [rbp+340h+var_268], ecx
0x18006f88a  movzx   ecx, word ptr [rdi+2F8h]
0x18006f891  movzx   eax, cx
0x18006f894  mov     qword ptr [rbp+340h+var_360.Size], 2
0x18006f89c  shr     ax, 1
0x18006f89f  mov     [rsp+440h+var_3F4], ax
0x18006f8a4  lea     rax, [rsp+440h+var_3F4]
0x18006f8a9  mov     [rbp+340h+var_260], rax
0x18006f8b0  mov     rax, [rdi+300h]
0x18006f8b7  mov     [rbp+340h+var_250], rax
0x18006f8be  mov     [rbp+340h+var_350], r15
0x18006f8c2  mov     [rbp+340h+var_348], esi
0x18006f8c5  mov     [rbp+340h+var_344], r12d
0x18006f8c9  mov     [rbp+340h+var_338], 2
0x18006f8d1  mov     [rbp+340h+var_324], r12d
0x18006f8d5  mov     [rbp+340h+var_318], 4
0x18006f8dd  mov     [rbp+340h+var_310], r14
0x18006f8e1  mov     [rbp+340h+var_304], r12d
0x18006f8e5  mov     [rbp+340h+var_2F8], 4
0x18006f8ed  mov     [rbp+340h+var_2E4], r12d
0x18006f8f1  mov     [rbp+340h+var_2D8], 4
0x18006f8f9  mov     [rbp+340h+var_2C4], r12d
0x18006f8fd  mov     [rbp+340h+var_2B8], 4
0x18006f908  mov     [rbp+340h+var_2A4], r12d
0x18006f90f  mov     [rbp+340h+var_298], 8
0x18006f91a  mov     [rbp+340h+var_288], 4
0x18006f925  mov     [rbp+340h+var_1E8], 4
0x18006f930  mov     [rbp+340h+var_278], 2
0x18006f93b  mov     [rbp+340h+var_264], r12d
0x18006f942  mov     [rbp+340h+var_258], 2
0x18006f94d  mov     [rbp+340h+var_248], ecx
0x18006f953  movzx   ecx, word ptr [rdi+308h]
0x18006f95a  mov     r9, [rdi+348h]
0x18006f961  movzx   eax, cx
0x18006f964  shr     ax, 1
0x18006f967  mov     [rsp+440h+var_3F0], ax
0x18006f96c  lea     rax, [rsp+440h+var_3F0]
0x18006f971  mov     [rbp+340h+var_240], rax
0x18006f978  mov     rax, [rdi+310h]
0x18006f97f  mov     [rbp+340h+var_230], rax
0x18006f986  mov     [rbp+340h+var_228], ecx
0x18006f98c  movzx   ecx, word ptr [rdi+318h]
0x18006f993  movzx   eax, cx
0x18006f996  movzx   r8d, r9w
0x18006f99a  shr     ax, 1
0x18006f99d  mov     [rsp+440h+var_3EC], ax
0x18006f9a2  lea     rax, [rsp+440h+var_3EC]
0x18006f9a7  mov     [rbp+340h+var_220], rax
0x18006f9ae  mov     rax, [rdi+320h]
0x18006f9b5  mov     [rbp+340h+var_210], rax
0x18006f9bc  mov     rax, r9
0x18006f9bf  shr     rax, 10h
0x18006f9c3  movzx   edx, ax
0x18006f9c6  mov     rax, r9
0x18006f9c9  mov     [rsp+440h+var_410], r8d
0x18006f9ce  lea     r8, pszFormat; "%hu.%hu.%hu.%hu"
0x18006f9d5  mov     [rbp+340h+var_208], ecx
0x18006f9db  mov     [rsp+440h+var_418], edx
0x18006f9df  mov     edx, 18h; cchDest
0x18006f9e4  shr     rax, 20h
0x18006f9e8  movzx   ecx, ax
0x18006f9eb  mov     dword ptr [rsp+440h+UserData], ecx
0x18006f9ef  lea     rcx, [rbp+340h+pszDest]; pszDest
0x18006f9f6  shr     r9, 30h
0x18006f9fa  mov     [rbp+340h+var_244], r12d
0x18006fa01  mov     [rbp+340h+var_238], 2
0x18006fa0c  mov     [rbp+340h+var_224], r12d
0x18006fa13  mov     [rbp+340h+var_218], 2
0x18006fa1e  mov     [rbp+340h+var_204], r12d
0x18006fa25  call    RtlStringCchPrintfA
0x18006fa2a  test    eax, eax
0x18006fa2c  jns     short loc_18006FA35
0x18006fa2e  mov     [rbp+340h+pszDest], r12b
0x18006fa35  lea     rax, [rbp+340h+pszDest]
0x18006fa3c  mov     [rbp+340h+var_200], rax
0x18006fa43  lea     rcx, [rbp+340h+pszDest]
0x18006fa4a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006fa4e  inc     rax
0x18006fa51  cmp     [rcx+rax], r12b
0x18006fa55  jnz     short loc_18006FA4E
0x18006fa57  mov     rdx, [rdi+340h]
0x18006fa5e  inc     eax
0x18006fa60  mov     [rbp+340h+var_1F8], eax
0x18006fa66  mov     [rbp+340h+var_1F4], r12d
0x18006fa6d  mov     [rbp+340h+var_1D8], 2
0x18006fa78  test    rdx, rdx
0x18006fa7b  jz      short loc_18006FAAA
0x18006fa7d  movzx   ecx, word ptr [rdi+338h]
0x18006fa84  movzx   eax, cx
0x18006fa87  mov     [rbp+340h+var_1D0], rdx
0x18006fa8e  shr     ax, 1
0x18006fa91  mov     [rsp+440h+var_3E8], ax
0x18006fa96  lea     rax, [rsp+440h+var_3E8]
0x18006fa9b  mov     [rbp+340h+var_1C8], ecx
0x18006faa1  mov     [rbp+340h+var_1C4], r12d
0x18006faa8  jmp     short loc_18006FAAF
0x18006faaa  lea     rax, [rsp+440h+var_3C8]
0x18006faaf  mov     [rbp+340h+var_1E0], rax
0x18006fab6  mov     r9, 0FFFFFFFFFFFFFD50h
0x18006fabd  mov     rcx, [rdi+9A0h]
0x18006fac4  mov     r8d, 2C0h
0x18006faca  movzx   eax, [rbp+340h+UnicodeString.Length]
0x18006face  shr     ax, 1
0x18006fad1  mov     [rsp+440h+var_3E4], ax
0x18006fad6  lea     rax, [rsp+440h+var_3E4]
0x18006fadb  mov     [rbp+340h+var_1C0], rax
0x18006fae2  mov     rax, [rbp+340h+UnicodeString.Buffer]
0x18006fae6  mov     [rbp+340h+var_1B0], rax
0x18006faed  movzx   eax, [rbp+340h+UnicodeString.Length]
0x18006faf1  mov     [rbp+340h+var_1A8], eax
0x18006faf7  movzx   eax, [rbp+340h+var_3A8.Length]
0x18006fafb  shr     ax, 1
0x18006fafe  mov     [rsp+440h+var_3E0], ax
0x18006fb03  lea     rax, [rsp+440h+var_3E0]
0x18006fb08  mov     [rbp+340h+var_1A0], rax
0x18006fb0f  mov     rax, [rbp+340h+var_3A8.Buffer]
0x18006fb13  mov     [rbp+340h+var_190], rax
0x18006fb1a  movzx   eax, [rbp+340h+var_3A8.Length]
0x18006fb1e  mov     [rbp+340h+var_188], eax
0x18006fb24  mov     [rbp+340h+var_1B8], 2
0x18006fb2f  mov     [rbp+340h+var_1A4], r12d
0x18006fb36  mov     [rbp+340h+var_198], 2
0x18006fb41  mov     [rbp+340h+var_184], r12d
0x18006fb48  cmp     dword ptr [rcx+28h], 6
0x18006fb4c  mov     [rbp+340h+var_178], 10h
0x18006fb57  sbb     rax, rax
0x18006fb5a  mov     [rbp+340h+var_168], 4
0x18006fb65  and     rax, r9
0x18006fb68  mov     [rbp+340h+var_154], r12d
0x18006fb6f  add     rax, r8
0x18006fb72  mov     [rbp+340h+var_148], 2
0x18006fb7d  add     rax, rcx
0x18006fb80  mov     [rbp+340h+var_134], r12d
0x18006fb87  mov     rcx, [rdi+998h]
0x18006fb8e  mov     [rbp+340h+var_180], rax
0x18006fb95  lea     rax, [rsp+440h+var_3D4]
0x18006fb9a  mov     [rbp+340h+var_170], rax
0x18006fba1  lea     rax, [rbp+340h+var_C0]
0x18006fba8  mov     [rbp+340h+var_160], rax
0x18006fbaf  mov     eax, [rsp+440h+var_3D4]
0x18006fbb3  mov     [rbp+340h+var_158], eax
0x18006fbb9  movzx   eax, [rbp+340h+var_398.Length]
0x18006fbbd  shr     ax, 1
0x18006fbc0  mov     [rsp+440h+var_3DC], ax
0x18006fbc5  lea     rax, [rsp+440h+var_3DC]
0x18006fbca  mov     [rbp+340h+var_150], rax
0x18006fbd1  mov     rax, [rbp+340h+var_398.Buffer]
0x18006fbd5  mov     [rbp+340h+var_140], rax
0x18006fbdc  movzx   eax, [rbp+340h+var_398.Length]
  ... truncated ...
```
