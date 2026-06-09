# PsmpQueryApplicationPerformance(_PSM_APPLICATION_USAGE_INFO *,_PSM_APPLICATION_PERFORMANCE_INFORMATION *)

- ea: `0x180002860`
- end: `0x180003297`
- name: `?PsmpQueryApplicationPerformance@@YAXPEAU_PSM_APPLICATION_USAGE_INFO@@PEAU_PSM_APPLICATION_PERFORMANCE_INFORMATION@@@Z`
- size: `2615`
- prototype: `void __fastcall(struct _PSM_APPLICATION_USAGE_INFO *, struct _PSM_APPLICATION_PERFORMANCE_INFORMATION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002550`

## callees

- `0x180002860`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180003233`
- `ntdll!RtlFreeHeap` at `0x180003233`
- `ntdll!RtlCopySid` at `0x1800028e6`
- `ntdll!RtlCopySid` at `0x1800028e6`
- `ntdll!RtlAllocateHeap` at `0x1800028a1`
- `ntdll!RtlAllocateHeap` at `0x1800028a1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000296e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000296e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800029ad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800029ad`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180002902`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180002902`

## pseudocode

```c
void __fastcall PsmpQueryApplicationPerformance(
        struct _PSM_APPLICATION_USAGE_INFO *a1,
        struct _PSM_APPLICATION_PERFORMANCE_INFORMATION *a2)
{
  _QWORD *Heap; // r14
  __int64 v5; // rcx
  __int64 v6; // rdx
  _WORD *v7; // r8
  _WORD *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r10
  _WORD *v11; // rcx
  __int64 v12; // r11
  __int64 v13; // rbx
  int v14[4]; // [rsp+20h] [rbp-138h] BYREF
  _BYTE v15[256]; // [rsp+30h] [rbp-128h] BYREF

  v14[0] = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xB18u);
  if ( Heap )
  {
    *(_OWORD *)a2 = 0;
    *((_OWORD *)a2 + 1) = 0;
    *((_OWORD *)a2 + 2) = 0;
    *((_OWORD *)a2 + 3) = 0;
    *((_DWORD *)a2 + 16) = 0;
    RtlCopySid(0x44u, a2, (char *)a1 + 40);
    v5 = *((_QWORD *)a1 + 1);
    v14[0] = 256;
    PsmGetPackageFullNameFromKey(v5, v15, v14);
    v6 = 128;
    v7 = v15;
    v8 = (_WORD *)((char *)a2 + 68);
    v9 = 2147483646;
    v10 = 0;
    do
    {
      if ( !v9 )
        break;
      if ( !*v7 )
        break;
      *v8++ = *v7++;
      --v9;
      ++v10;
      --v6;
    }
    while ( v6 );
    v11 = v8 - 1;
    v12 = v10 - 1;
    if ( v6 )
    {
      v11 = v8;
      v12 = v10;
    }
    *v11 = 0;
    if ( v6 )
    {
      v13 = 128 - v12;
      if ( v12 != 128 && v12 != 127 && (unsigned __int64)(2 * v13) > 2 )
        memset_0((char *)a2 + 2 * v12 + 70, 0, 2 * v13 - 2);
    }
    RtlAcquireSRWLockExclusive((char *)a1 + 120);
    memcpy_0(Heap + 2, (char *)a1 + 136, 0xB00u);
    *Heap = *((_QWORD *)a1 + 14);
    *((_DWORD *)Heap + 2) = *((_DWORD *)a1 + 33);
    Heap[354] = *((_QWORD *)a1 + 106);
    RtlReleaseSRWLockExclusive((char *)a1 + 120);
    *((_QWORD *)a2 + 41) = *Heap;
    *((_DWORD *)a2 + 246) = *((_DWORD *)Heap + 2);
    *((_QWORD *)a2 + 58) = Heap[354];
    *((_QWORD *)a2 + 42) = Heap[4] + Heap[136] + Heap[312];
    *((_QWORD *)a2 + 44) = Heap[2] + Heap[134] + Heap[310];
    *((_QWORD *)a2 + 43) = Heap[48] + Heap[92] + Heap[180];
    *((_QWORD *)a2 + 45) = Heap[46] + Heap[90];
    *((_QWORD *)a2 + 47) = Heap[49] + Heap[93] + Heap[181];
    *((_QWORD *)a2 + 46) = Heap[5] + Heap[137] + Heap[313];
    *((_QWORD *)a2 + 48) = Heap[7] + Heap[139] + Heap[315];
    *((_QWORD *)a2 + 49) = Heap[8] + Heap[140] + Heap[316];
    *((_QWORD *)a2 + 50) = Heap[9] + Heap[141] + Heap[317];
    *((_QWORD *)a2 + 51) = Heap[10] + Heap[142] + Heap[318];
    *((_QWORD *)a2 + 52) = Heap[11] + Heap[143] + Heap[319];
    *((_QWORD *)a2 + 53) = Heap[51] + Heap[95] + Heap[183];
    *((_QWORD *)a2 + 54) = Heap[52] + Heap[96] + Heap[184];
    *((_QWORD *)a2 + 55) = Heap[53] + Heap[97] + Heap[185];
    *((_QWORD *)a2 + 56) = Heap[54] + Heap[98] + Heap[186];
    *((_QWORD *)a2 + 57) = Heap[55] + Heap[99] + Heap[187];
    *((_QWORD *)a2 + 59) = Heap[4];
    *((_QWORD *)a2 + 60) = Heap[48];
    *((_QWORD *)a2 + 61) = Heap[92];
    *((_QWORD *)a2 + 62) = Heap[136] + Heap[312];
    *((_QWORD *)a2 + 63) = Heap[180];
    *((_QWORD *)a2 + 64) = Heap[224] + Heap[268];
    *((_QWORD *)a2 + 89) = Heap[20] + Heap[152] + Heap[328];
    *((_QWORD *)a2 + 90) = Heap[21] + Heap[153] + Heap[329];
    *((_QWORD *)a2 + 91) = Heap[22] + Heap[154] + Heap[330];
    *((_QWORD *)a2 + 92) = Heap[23] + Heap[155] + Heap[331];
    *((_QWORD *)a2 + 93) = Heap[24] + Heap[156] + Heap[332];
    *((_QWORD *)a2 + 118) = Heap[64] + Heap[108] + Heap[196];
    *((_QWORD *)a2 + 119) = Heap[65] + Heap[109] + Heap[197];
    *((_QWORD *)a2 + 120) = Heap[66] + Heap[110] + Heap[198];
    *((_QWORD *)a2 + 121) = Heap[67] + Heap[111] + Heap[199];
    *((_QWORD *)a2 + 122) = Heap[68] + Heap[112] + Heap[200];
    *((_QWORD *)a2 + 65) = Heap[12] + Heap[144] + Heap[320];
    *((_QWORD *)a2 + 73) = Heap[38] + Heap[170] + Heap[346];
    *((_QWORD *)a2 + 81) = Heap[30] + Heap[162] + Heap[338];
    *((_QWORD *)a2 + 94) = Heap[56] + Heap[100] + Heap[188];
    *((_QWORD *)a2 + 102) = Heap[82] + Heap[126] + Heap[214];
    *((_QWORD *)a2 + 110) = Heap[74] + Heap[118] + Heap[206];
    *((_QWORD *)a2 + 66) = Heap[13] + Heap[145] + Heap[321];
    *((_QWORD *)a2 + 74) = Heap[39] + Heap[171] + Heap[347];
    *((_QWORD *)a2 + 82) = Heap[31] + Heap[163] + Heap[339];
    *((_QWORD *)a2 + 95) = Heap[57] + Heap[101] + Heap[189];
    *((_QWORD *)a2 + 103) = Heap[83] + Heap[127] + Heap[215];
    *((_QWORD *)a2 + 111) = Heap[75] + Heap[119] + Heap[207];
    *((_QWORD *)a2 + 67) = Heap[14] + Heap[146] + Heap[322];
    *((_QWORD *)a2 + 75) = Heap[40] + Heap[172] + Heap[348];
    *((_QWORD *)a2 + 83) = Heap[32] + Heap[164] + Heap[340];
    *((_QWORD *)a2 + 96) = Heap[58] + Heap[102] + Heap[190];
    *((_QWORD *)a2 + 104) = Heap[84] + Heap[128] + Heap[216];
    *((_QWORD *)a2 + 112) = Heap[76] + Heap[120] + Heap[208];
    *((_QWORD *)a2 + 68) = Heap[15] + Heap[147] + Heap[323];
    *((_QWORD *)a2 + 76) = Heap[41] + Heap[173] + Heap[349];
    *((_QWORD *)a2 + 84) = Heap[33] + Heap[165] + Heap[341];
    *((_QWORD *)a2 + 97) = Heap[59] + Heap[103] + Heap[191];
    *((_QWORD *)a2 + 105) = Heap[85] + Heap[129] + Heap[217];
    *((_QWORD *)a2 + 113) = Heap[77] + Heap[121] + Heap[209];
    *((_QWORD *)a2 + 69) = Heap[16] + Heap[148] + Heap[324];
    *((_QWORD *)a2 + 77) = Heap[42] + Heap[174] + Heap[350];
    *((_QWORD *)a2 + 85) = Heap[34] + Heap[166] + Heap[342];
    *((_QWORD *)a2 + 98) = Heap[60] + Heap[104] + Heap[192];
    *((_QWORD *)a2 + 106) = Heap[86] + Heap[130] + Heap[218];
    *((_QWORD *)a2 + 114) = Heap[78] + Heap[122] + Heap[210];
    *((_QWORD *)a2 + 70) = Heap[17] + Heap[149] + Heap[325];
    *((_QWORD *)a2 + 78) = Heap[43] + Heap[175] + Heap[351];
    *((_QWORD *)a2 + 86) = Heap[35] + Heap[167] + Heap[343];
    *((_QWORD *)a2 + 99) = Heap[61] + Heap[105] + Heap[193];
    *((_QWORD *)a2 + 107) = Heap[87] + Heap[131] + Heap[219];
    *((_QWORD *)a2 + 115) = Heap[79] + Heap[123] + Heap[211];
    *((_QWORD *)a2 + 71) = Heap[18] + Heap[150] + Heap[326];
    *((_QWORD *)a2 + 79) = Heap[44] + Heap[176] + Heap[352];
    *((_QWORD *)a2 + 87) = Heap[36] + Heap[168] + Heap[344];
    *((_QWORD *)a2 + 100) = Heap[62] + Heap[106] + Heap[194];
    *((_QWORD *)a2 + 108) = Heap[88] + Heap[132] + Heap[220];
    *((_QWORD *)a2 + 116) = Heap[80] + Heap[124] + Heap[212];
    *((_QWORD *)a2 + 72) = Heap[19] + Heap[151] + Heap[327];
    *((_QWORD *)a2 + 80) = Heap[45] + Heap[177] + Heap[353];
    *((_QWORD *)a2 + 88) = Heap[37] + Heap[169] + Heap[345];
    *((_QWORD *)a2 + 101) = Heap[63] + Heap[107] + Heap[195];
    *((_QWORD *)a2 + 109) = Heap[89] + Heap[133] + Heap[221];
    *((_QWORD *)a2 + 117) = Heap[81] + Heap[125] + Heap[213];
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
}

```

## disassembly

```asm
0x180002860  push    rbp
0x180002862  push    rsi
0x180002863  push    r14
0x180002865  sub     rsp, 140h
0x18000286c  mov     rax, cs:__security_cookie
0x180002873  xor     rax, rsp
0x180002876  mov     [rsp+158h+var_28], rax
0x18000287e  mov     rbp, rcx
0x180002881  mov     [rsp+158h+var_138], 0
0x180002889  mov     rcx, gs:60h
0x180002892  mov     rsi, rdx
0x180002895  xor     edx, edx; Flags
0x180002897  mov     r8d, 0B18h; Size
0x18000289d  mov     rcx, [rcx+30h]; HeapHandle
0x1800028a1  call    cs:__imp_RtlAllocateHeap
0x1800028a7  mov     r14, rax
0x1800028aa  test    rax, rax
0x1800028ad  jz      loc_180003249
0x1800028b3  xorps   xmm0, xmm0
0x1800028b6  mov     [rsp+158h+arg_10], rbx
0x1800028be  movups  xmmword ptr [rsi], xmm0
0x1800028c1  xor     eax, eax
0x1800028c3  lea     r8, [rbp+28h]; SourceSid
0x1800028c7  movups  xmmword ptr [rsi+10h], xmm0
0x1800028cb  mov     rdx, rsi; DestinationSid
0x1800028ce  mov     ecx, 44h ; 'D'; DestinationSidLength
0x1800028d3  movups  xmmword ptr [rsi+20h], xmm0
0x1800028d7  mov     [rsp+158h+arg_18], rdi
0x1800028df  movups  xmmword ptr [rsi+30h], xmm0
0x1800028e3  mov     [rsi+40h], eax
0x1800028e6  call    cs:__imp_RtlCopySid
0x1800028ec  mov     rcx, [rbp+8]
0x1800028f0  lea     r8, [rsp+158h+var_138]
0x1800028f5  lea     rdx, [rsp+158h+var_128]
0x1800028fa  mov     [rsp+158h+var_138], 100h
0x180002902  call    cs:__imp_PsmGetPackageFullNameFromKey
0x180002908  lea     rdi, [rsi+44h]
0x18000290c  mov     ebx, 80h
0x180002911  mov     edx, ebx
0x180002913  lea     r8, [rsp+158h+var_128]
0x180002918  mov     r9, rdi
0x18000291b  mov     ecx, 7FFFFFFEh
0x180002920  xor     r10d, r10d
0x180002923  test    rcx, rcx
0x180002926  jz      short loc_180002949
0x180002928  movzx   eax, word ptr [r8]
0x18000292c  test    ax, ax
0x18000292f  jz      short loc_180002949
0x180002931  mov     [r9], ax
0x180002935  add     r8, 2
0x180002939  add     r9, 2
0x18000293d  dec     rcx
0x180002940  inc     r10
0x180002943  sub     rdx, 1
0x180002947  jnz     short loc_180002923
0x180002949  test    rdx, rdx
0x18000294c  lea     rcx, [r9-2]
0x180002950  lea     r11, [r10-1]
0x180002954  cmovnz  rcx, r9
0x180002958  cmovnz  r11, r10
0x18000295c  xor     eax, eax
0x18000295e  mov     [rcx], ax
0x180002961  test    rdx, rdx
0x180002964  jnz     loc_180003265
0x18000296a  lea     rcx, [rbp+78h]
0x18000296e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002974  lea     rcx, [r14+10h]; void *
0x180002978  mov     r8d, 0B00h; Size
0x18000297e  lea     rdx, [rbp+88h]; Src
0x180002985  call    memcpy_0
0x18000298a  mov     rax, [rbp+70h]
0x18000298e  lea     rcx, [rbp+78h]
0x180002992  mov     [r14], rax
0x180002995  mov     eax, [rbp+84h]
0x18000299b  mov     [r14+8], eax
0x18000299f  mov     rax, [rbp+350h]
0x1800029a6  mov     [r14+0B10h], rax
0x1800029ad  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800029b3  mov     rax, [r14]
0x1800029b6  mov     [rsi+148h], rax
0x1800029bd  mov     eax, [r14+8]
0x1800029c1  mov     [rsi+3D8h], eax
0x1800029c7  mov     rax, [r14+0B10h]
0x1800029ce  mov     [rsi+1D0h], rax
0x1800029d5  mov     rax, [r14+9C0h]
0x1800029dc  add     rax, [r14+440h]
0x1800029e3  add     rax, [r14+20h]
0x1800029e7  mov     [rsi+150h], rax
0x1800029ee  mov     rax, [r14+9B0h]
0x1800029f5  add     rax, [r14+430h]
0x1800029fc  add     rax, [r14+10h]
0x180002a00  mov     [rsi+160h], rax
0x180002a07  mov     rax, [r14+5A0h]
0x180002a0e  add     rax, [r14+2E0h]
0x180002a15  add     rax, [r14+180h]
0x180002a1c  mov     [rsi+158h], rax
0x180002a23  mov     rax, [r14+2D0h]
0x180002a2a  add     rax, [r14+170h]
0x180002a31  mov     [rsi+168h], rax
0x180002a38  mov     rax, [r14+5A8h]
0x180002a3f  add     rax, [r14+2E8h]
0x180002a46  add     rax, [r14+188h]
0x180002a4d  mov     [rsi+178h], rax
0x180002a54  mov     rax, [r14+9C8h]
0x180002a5b  add     rax, [r14+448h]
0x180002a62  add     rax, [r14+28h]
0x180002a66  mov     [rsi+170h], rax
0x180002a6d  mov     rax, [r14+9D8h]
0x180002a74  add     rax, [r14+458h]
0x180002a7b  add     rax, [r14+38h]
0x180002a7f  mov     [rsi+180h], rax
0x180002a86  mov     rax, [r14+9E0h]
0x180002a8d  add     rax, [r14+460h]
0x180002a94  add     rax, [r14+40h]
0x180002a98  mov     [rsi+188h], rax
0x180002a9f  mov     rax, [r14+9E8h]
0x180002aa6  add     rax, [r14+468h]
0x180002aad  add     rax, [r14+48h]
0x180002ab1  mov     [rsi+190h], rax
0x180002ab8  mov     rax, [r14+9F0h]
0x180002abf  add     rax, [r14+470h]
0x180002ac6  add     rax, [r14+50h]
0x180002aca  mov     [rsi+198h], rax
0x180002ad1  mov     rax, [r14+9F8h]
0x180002ad8  add     rax, [r14+478h]
0x180002adf  add     rax, [r14+58h]
0x180002ae3  mov     [rsi+1A0h], rax
0x180002aea  mov     rax, [r14+5B8h]
0x180002af1  add     rax, [r14+2F8h]
0x180002af8  add     rax, [r14+198h]
0x180002aff  mov     [rsi+1A8h], rax
0x180002b06  mov     rax, [r14+5C0h]
0x180002b0d  add     rax, [r14+300h]
0x180002b14  add     rax, [r14+1A0h]
0x180002b1b  mov     [rsi+1B0h], rax
0x180002b22  mov     rax, [r14+5C8h]
0x180002b29  add     rax, [r14+308h]
0x180002b30  add     rax, [r14+1A8h]
0x180002b37  mov     [rsi+1B8h], rax
0x180002b3e  mov     rax, [r14+5D0h]
0x180002b45  add     rax, [r14+310h]
0x180002b4c  add     rax, [r14+1B0h]
0x180002b53  mov     [rsi+1C0h], rax
0x180002b5a  mov     rax, [r14+5D8h]
0x180002b61  add     rax, [r14+318h]
0x180002b68  add     rax, [r14+1B8h]
0x180002b6f  mov     [rsi+1C8h], rax
0x180002b76  mov     rax, [r14+20h]
0x180002b7a  mov     [rsi+1D8h], rax
0x180002b81  mov     rax, [r14+180h]
0x180002b88  mov     [rsi+1E0h], rax
0x180002b8f  mov     rax, [r14+2E0h]
0x180002b96  mov     [rsi+1E8h], rax
0x180002b9d  mov     rax, [r14+9C0h]
0x180002ba4  add     rax, [r14+440h]
0x180002bab  mov     [rsi+1F0h], rax
0x180002bb2  mov     rax, [r14+5A0h]
0x180002bb9  mov     [rsi+1F8h], rax
0x180002bc0  mov     rax, [r14+860h]
0x180002bc7  add     rax, [r14+700h]
0x180002bce  mov     [rsi+200h], rax
0x180002bd5  mov     rax, [r14+0A40h]
0x180002bdc  add     rax, [r14+4C0h]
0x180002be3  add     rax, [r14+0A0h]
0x180002bea  mov     [rsi+2C8h], rax
0x180002bf1  mov     rax, [r14+0A48h]
0x180002bf8  add     rax, [r14+4C8h]
0x180002bff  add     rax, [r14+0A8h]
0x180002c06  mov     [rsi+2D0h], rax
0x180002c0d  mov     rax, [r14+0A50h]
0x180002c14  add     rax, [r14+4D0h]
0x180002c1b  add     rax, [r14+0B0h]
0x180002c22  mov     [rsi+2D8h], rax
0x180002c29  mov     rax, [r14+0A58h]
0x180002c30  add     rax, [r14+4D8h]
0x180002c37  add     rax, [r14+0B8h]
0x180002c3e  mov     [rsi+2E0h], rax
0x180002c45  mov     rax, [r14+0A60h]
0x180002c4c  add     rax, [r14+4E0h]
0x180002c53  add     rax, [r14+0C0h]
0x180002c5a  mov     [rsi+2E8h], rax
0x180002c61  mov     rax, [r14+620h]
0x180002c68  add     rax, [r14+360h]
0x180002c6f  add     rax, [r14+200h]
0x180002c76  mov     [rsi+3B0h], rax
0x180002c7d  mov     rax, [r14+628h]
0x180002c84  add     rax, [r14+368h]
0x180002c8b  add     rax, [r14+208h]
0x180002c92  mov     [rsi+3B8h], rax
0x180002c99  mov     rax, [r14+630h]
0x180002ca0  add     rax, [r14+370h]
0x180002ca7  add     rax, [r14+210h]
0x180002cae  mov     [rsi+3C0h], rax
0x180002cb5  mov     rax, [r14+638h]
0x180002cbc  add     rax, [r14+378h]
0x180002cc3  add     rax, [r14+218h]
0x180002cca  mov     [rsi+3C8h], rax
0x180002cd1  mov     rax, [r14+640h]
0x180002cd8  add     rax, [r14+380h]
0x180002cdf  add     rax, [r14+220h]
0x180002ce6  mov     [rsi+3D0h], rax
0x180002ced  mov     rax, [r14+0A00h]
0x180002cf4  add     rax, [r14+480h]
0x180002cfb  add     rax, [r14+60h]
0x180002cff  mov     [rsi+208h], rax
0x180002d06  mov     rax, [r14+0AD0h]
0x180002d0d  add     rax, [r14+550h]
0x180002d14  add     rax, [r14+130h]
0x180002d1b  mov     [rsi+248h], rax
0x180002d22  mov     rax, [r14+0A90h]
0x180002d29  add     rax, [r14+510h]
0x180002d30  add     rax, [r14+0F0h]
0x180002d37  mov     [rsi+288h], rax
0x180002d3e  mov     rax, [r14+5E0h]
0x180002d45  add     rax, [r14+320h]
0x180002d4c  add     rax, [r14+1C0h]
0x180002d53  mov     [rsi+2F0h], rax
0x180002d5a  mov     rax, [r14+6B0h]
0x180002d61  add     rax, [r14+3F0h]
0x180002d68  add     rax, [r14+290h]
0x180002d6f  mov     [rsi+330h], rax
0x180002d76  mov     rax, [r14+670h]
0x180002d7d  add     rax, [r14+3B0h]
0x180002d84  add     rax, [r14+250h]
0x180002d8b  mov     [rsi+370h], rax
0x180002d92  mov     rax, [r14+0A08h]
0x180002d99  add     rax, [r14+488h]
0x180002da0  add     rax, [r14+68h]
0x180002da4  mov     [rsi+210h], rax
0x180002dab  mov     rax, [r14+0AD8h]
0x180002db2  add     rax, [r14+558h]
0x180002db9  add     rax, [r14+138h]
0x180002dc0  mov     [rsi+250h], rax
0x180002dc7  mov     rax, [r14+0A98h]
0x180002dce  add     rax, [r14+518h]
0x180002dd5  add     rax, [r14+0F8h]
0x180002ddc  mov     [rsi+290h], rax
0x180002de3  mov     rax, [r14+5E8h]
0x180002dea  add     rax, [r14+328h]
0x180002df1  add     rax, [r14+1C8h]
0x180002df8  mov     [rsi+2F8h], rax
0x180002dff  mov     rax, [r14+6B8h]
0x180002e06  add     rax, [r14+3F8h]
0x180002e0d  add     rax, [r14+298h]
0x180002e14  mov     [rsi+338h], rax
0x180002e1b  mov     rax, [r14+678h]
0x180002e22  add     rax, [r14+3B8h]
0x180002e29  add     rax, [r14+258h]
0x180002e30  mov     [rsi+378h], rax
0x180002e37  mov     rax, [r14+0A10h]
0x180002e3e  add     rax, [r14+490h]
0x180002e45  add     rax, [r14+70h]
0x180002e49  mov     [rsi+218h], rax
0x180002e50  mov     rax, [r14+0AE0h]
0x180002e57  add     rax, [r14+560h]
0x180002e5e  add     rax, [r14+140h]
0x180002e65  mov     [rsi+258h], rax
0x180002e6c  mov     rax, [r14+0AA0h]
0x180002e73  add     rax, [r14+520h]
0x180002e7a  add     rax, [r14+100h]
0x180002e81  mov     [rsi+298h], rax
0x180002e88  mov     rax, [r14+5F0h]
0x180002e8f  add     rax, [r14+330h]
0x180002e96  add     rax, [r14+1D0h]
0x180002e9d  mov     [rsi+300h], rax
0x180002ea4  mov     rax, [r14+6C0h]
0x180002eab  add     rax, [r14+400h]
0x180002eb2  add     rax, [r14+2A0h]
0x180002eb9  mov     [rsi+340h], rax
0x180002ec0  mov     rax, [r14+680h]
0x180002ec7  add     rax, [r14+3C0h]
0x180002ece  add     rax, [r14+260h]
0x180002ed5  mov     [rsi+380h], rax
0x180002edc  mov     rax, [r14+0A18h]
0x180002ee3  add     rax, [r14+498h]
0x180002eea  add     rax, [r14+78h]
0x180002eee  mov     [rsi+220h], rax
0x180002ef5  mov     rax, [r14+0AE8h]
0x180002efc  add     rax, [r14+568h]
0x180002f03  add     rax, [r14+148h]
0x180002f0a  mov     [rsi+260h], rax
0x180002f11  mov     rax, [r14+0AA8h]
0x180002f18  add     rax, [r14+528h]
0x180002f1f  add     rax, [r14+108h]
0x180002f26  mov     [rsi+2A0h], rax
0x180002f2d  mov     rax, [r14+5F8h]
0x180002f34  add     rax, [r14+338h]
0x180002f3b  add     rax, [r14+1D8h]
0x180002f42  mov     [rsi+308h], rax
0x180002f49  mov     rax, [r14+6C8h]
0x180002f50  add     rax, [r14+408h]
0x180002f57  add     rax, [r14+2A8h]
0x180002f5e  mov     [rsi+348h], rax
0x180002f65  mov     rax, [r14+688h]
0x180002f6c  add     rax, [r14+3C8h]
0x180002f73  add     rax, [r14+268h]
0x180002f7a  mov     [rsi+388h], rax
0x180002f81  mov     rax, [r14+0A20h]
0x180002f88  add     rax, [r14+4A0h]
0x180002f8f  add     rax, [r14+80h]
  ... truncated ...
```
