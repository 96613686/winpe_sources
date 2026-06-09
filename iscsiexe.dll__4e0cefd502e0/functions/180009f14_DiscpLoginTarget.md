# DiscpLoginTarget

- ea: `0x180009f14`
- end: `0x18000a3fb`
- name: `DiscpLoginTarget`
- size: `1255`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, __int64, __int64, __int64, size_t, void *, int, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180009898`
- `0x18000b720`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180009c74`
- `0x180009f14`
- `0x18000b444`
- `0x180016d20`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpCopyToCountedString` at `0x18000a112`
- `ISCSIUM!DiscpCopyToCountedString` at `0x18000a129`
- `ISCSIUM!DiscpCopyToCountedString` at `0x18000a143`
- `ISCSIUM!DiscpCopyToCountedString` at `0x18000a112`
- `ISCSIUM!DiscpCopyToCountedString` at `0x18000a129`
- `ISCSIUM!DiscpCopyToCountedString` at `0x18000a143`
- `ISCSIUM!DiscpExecuteMethod` at `0x18000a33d`
- `ISCSIUM!DiscpExecuteMethod` at `0x18000a33d`
- `ISCSIUM!DiscpUnicodeToAnsi` at `0x18000a032`
- `ISCSIUM!DiscpUnicodeToAnsi` at `0x18000a032`
- `ISCSIUM!DiscpAllocMemory` at `0x18000a0b1`
- `ISCSIUM!DiscpAllocMemory` at `0x18000a0b1`
- `ISCSIUM!DiscpFreeMemory` at `0x18000a399`
- `ISCSIUM!DiscpFreeMemory` at `0x18000a3a8`
- `ISCSIUM!DiscpFreeMemory` at `0x18000a3b6`
- `ISCSIUM!DiscpFreeMemory` at `0x18000a3c5`
- `ISCSIUM!DiscpFreeMemory` at `0x18000a399`
- `ISCSIUM!DiscpFreeMemory` at `0x18000a3a8`
- `ISCSIUM!DiscpFreeMemory` at `0x18000a3b6`
- `ISCSIUM!DiscpFreeMemory` at `0x18000a3c5`
- `ISCSIUM!DiscpULongAddList` at `0x18000a0a4`
- `ISCSIUM!DiscpULongAddList` at `0x18000a0a4`

## pseudocode

```c
__int64 __fastcall DiscpLoginTarget(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        size_t a10,
        void *a11,
        int a12,
        char a13,
        __int64 a14,
        __int64 a15)
{
  char *v15; // rdi
  unsigned int DefaultiScsiName; // ebx
  char v17; // al
  unsigned int v18; // r12d
  __int64 v19; // r14
  int v20; // ebx
  unsigned __int64 v21; // rax
  unsigned int v22; // eax
  char *v23; // rax
  __int64 v24; // rdx
  unsigned int v25; // r8d
  __int64 v26; // rdx
  __int64 v27; // rcx
  void *v28; // rdx
  unsigned int v29; // ebx
  int v30; // ebx
  void *v31; // rdx
  __int64 v32; // rsi
  __int64 v33; // r14
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rcx
  _QWORD *v38; // rdx
  __int64 v39; // rax
  _QWORD *v40; // rcx
  char v42; // [rsp+50h] [rbp-89h]
  __int16 v43; // [rsp+58h] [rbp-81h] BYREF
  size_t Size; // [rsp+60h] [rbp-79h] BYREF
  void *v45; // [rsp+68h] [rbp-71h] BYREF
  __int64 v46; // [rsp+70h] [rbp-69h] BYREF
  int v47; // [rsp+78h] [rbp-61h]
  __int64 v48; // [rsp+80h] [rbp-59h] BYREF
  __int64 v49; // [rsp+88h] [rbp-51h]
  __int64 v50; // [rsp+90h] [rbp-49h]
  void *Src; // [rsp+98h] [rbp-41h]
  __int64 v52; // [rsp+A0h] [rbp-39h]
  __int64 v53; // [rsp+A8h] [rbp-31h]
  __int64 v54; // [rsp+B0h] [rbp-29h]
  __int64 v55; // [rsp+B8h] [rbp-21h]
  _DWORD v56[6]; // [rsp+C0h] [rbp-19h] BYREF

  v55 = a15;
  v54 = a14;
  v52 = a6;
  Src = a11;
  v49 = a3;
  v47 = a2;
  v53 = a1;
  v43 = 0;
  v46 = 0;
  Size = 0;
  v45 = 0;
  if ( __PAIR16__(DiscpRequireOneWayCHAP, DiscpRequireMutualCHAP)
    && (!a8
     || *(char *)(a8 + 4) >= 0
     || (!DiscpRequireOneWayCHAP || *(_DWORD *)(a8 + 12) != 1) && *(_DWORD *)(a8 + 12) != 2) )
  {
    return 4026466405LL;
  }
  v48 = 0;
  v15 = 0;
  DefaultiScsiName = DiscpGetDefaultiScsiName((__int64)&v48);
  if ( DefaultiScsiName )
    goto LABEL_46;
  v17 = 0;
  v50 = v48;
  v18 = 0;
  v42 = 0;
  if ( !a8 )
    goto LABEL_16;
  LODWORD(v19) = 0;
  if ( (*(_BYTE *)(a8 + 4) & 0x20) != 0 && *(_QWORD *)(a8 + 48) )
  {
    LODWORD(v19) = *(_DWORD *)(a8 + 36);
    v17 = 1;
    v42 = 1;
  }
  if ( (*(_BYTE *)(a8 + 4) & 0x40) != 0 && *(_QWORD *)(a8 + 56) )
    v18 = *(_DWORD *)(a8 + 40);
  if ( !v17 )
  {
LABEL_16:
    DefaultiScsiName = DiscpUnicodeToAnsi(v48, &v45, 0);
    if ( DefaultiScsiName )
      goto LABEL_46;
    v19 = -1;
    do
      ++v19;
    while ( *((_BYTE *)v45 + v19) );
  }
  v20 = 480;
  if ( a7 )
  {
    v21 = 16LL * *(unsigned int *)(a7 + 1504);
    if ( v21 > 0xFFFFFFFF )
      goto LABEL_26;
    v22 = v21 + 480;
    if ( v22 < 0x1E0 )
      goto LABEL_26;
    v20 = v22;
  }
  v56[3] = a10;
  v56[0] = 2536;
  v56[1] = v19;
  v56[2] = v18;
  v56[4] = v20;
  if ( (int)DiscpULongAddList(v56, 5, &Size) < 0 )
  {
LABEL_26:
    DefaultiScsiName = 87;
    goto LABEL_46;
  }
  v23 = (char *)DiscpAllocMemory((unsigned int)Size);
  v15 = v23;
  if ( v23 )
  {
    memset_0(v23, 0, (unsigned int)Size);
    v24 = v50;
    *(_DWORD *)v15 = v47;
    *((_QWORD *)v15 + 5) = a9;
    *((_DWORD *)v15 + 9) = a5;
    v15[618] = a13;
    DiscpCopyToCountedString(v15 + 620, v24, 223);
    DiscpCopyToCountedString(v15 + 1580, v49, 223);
    DiscpCopyToCountedString(v15 + 1068, L"Microsoft Windows Software Initiator", 255);
    *((_WORD *)v15 + 1026) = 446;
    if ( a7 )
    {
      v25 = 0;
      *((_DWORD *)v15 + 508) = *(_DWORD *)(a7 + 1496);
      *((_DWORD *)v15 + 509) = *(_DWORD *)(a7 + 1500);
      v15[2500] = a13;
      for ( *((_DWORD *)v15 + 512) = *(_DWORD *)(a7 + 1504);
            v25 < *(_DWORD *)(a7 + 1504);
            *(_DWORD *)&v15[8 * v26 + 2520] = *(_DWORD *)(*(_QWORD *)(a7 + 1512) + 8 * v26) )
      {
        v26 = 2LL * v25;
        v27 = 2 * (v25++ + 157LL);
        *(_QWORD *)&v15[8 * v27] = *(_QWORD *)(*(_QWORD *)(a7 + 1512) + 8 * v26 + 8);
      }
    }
    else
    {
      v15[2500] = a13;
      *((_QWORD *)v15 + 254) = -1;
      *((_DWORD *)v15 + 512) = 0;
    }
    v28 = Src;
    v29 = v20 + 2032;
    *((_DWORD *)v15 + 153) = a10;
    memcpy_0(&v15[v29], v28, (unsigned int)a10);
    v30 = a10 + v29;
    *((_DWORD *)v15 + 151) = v19;
    *((_DWORD *)v15 + 1) = 32;
    if ( v42 )
      v31 = *(void **)(a8 + 48);
    else
      v31 = v45;
    memcpy_0(&v15[v30], v31, (unsigned int)v19);
    *((_DWORD *)v15 + 152) = v18;
    if ( a8 )
    {
      *((_DWORD *)v15 + 1) |= *(_DWORD *)(a8 + 4);
      *((_DWORD *)v15 + 2) = *(_DWORD *)(a8 + 16);
      *((_DWORD *)v15 + 3) = *(_DWORD *)(a8 + 20);
      *((_DWORD *)v15 + 4) = *(_DWORD *)(a8 + 24);
      *((_DWORD *)v15 + 5) = *(_DWORD *)(a8 + 28);
      *((_DWORD *)v15 + 6) = *(_DWORD *)(a8 + 32);
      *((_DWORD *)v15 + 7) = *(_DWORD *)(a8 + 8);
      *((_DWORD *)v15 + 8) = *(_DWORD *)(a8 + 12);
      if ( v18 )
        memcpy_0(&v15[(unsigned int)(v30 + v19)], *(const void **)(a8 + 56), v18);
    }
    v32 = v53;
    v33 = v52;
    DefaultiScsiName = DiscpBuildIScsiIpAddress(*(_DWORD *)(v53 + 20) & 1, v52 + 512, 1, (int *)v15 + 12);
    if ( DefaultiScsiName )
      goto LABEL_46;
    v35 = v49;
    *((_WORD *)v15 + 300) = *(_WORD *)(v33 + 1024);
    DefaultiScsiName = DiscpSelectISIDForTarget(v35, v34, &v43);
    if ( DefaultiScsiName )
      goto LABEL_46;
    *((_WORD *)v15 + 308) = v43;
    v36 = *(_QWORD *)(v32 + 40);
    HIDWORD(Size) = 280;
    DefaultiScsiName = DiscpExecuteMethod(MSiSCSI_Operations_GUID, 0, v36, 30, v15, Size, &v46, (char *)&Size + 4, 24);
    if ( DefaultiScsiName )
    {
      v46 = 0;
    }
    else
    {
      v37 = v46;
      DefaultiScsiName = *(_DWORD *)v46;
      if ( !*(_DWORD *)v46 )
      {
        v38 = (_QWORD *)v54;
        *(_QWORD *)(v54 + 8) = *(_QWORD *)(v46 + 8);
        *v38 = *(_QWORD *)(v32 + 24);
        v39 = *(_QWORD *)(v37 + 16);
        v40 = (_QWORD *)v55;
        *(_QWORD *)(v55 + 8) = v39;
        *v40 = *(_QWORD *)(v32 + 24);
        goto LABEL_46;
      }
    }
    if ( DefaultiScsiName - 4200 <= 2 )
      DefaultiScsiName = -268500924;
    goto LABEL_46;
  }
  DefaultiScsiName = 8;
LABEL_46:
  if ( v45 )
    DiscpFreeMemory(v45);
  if ( v46 )
    DiscpFreeMemory(v46);
  if ( v15 )
    DiscpFreeMemory(v15);
  if ( v48 )
    DiscpFreeMemory(v48);
  return DefaultiScsiName;
}

```

## disassembly

```asm
0x180009f14  mov     [rsp-8+arg_8], rbx
0x180009f19  push    rbp
0x180009f1a  push    rsi
0x180009f1b  push    rdi
0x180009f1c  push    r12
0x180009f1e  push    r13
0x180009f20  push    r14
0x180009f22  push    r15
0x180009f24  lea     rbp, [rsp-7]
0x180009f29  sub     rsp, 0E0h
0x180009f30  mov     rax, cs:__security_cookie
0x180009f37  xor     rax, rsp
0x180009f3a  mov     [rbp+37h+var_38], rax
0x180009f3e  mov     rax, [rbp+37h+arg_70]
0x180009f45  xor     r13d, r13d
0x180009f48  mov     r15, [rbp+37h+arg_30]
0x180009f4c  mov     rsi, [rbp+37h+arg_38]
0x180009f50  mov     [rbp+37h+var_58], rax
0x180009f54  mov     rax, [rbp+37h+arg_68]
0x180009f5b  mov     [rbp+37h+var_60], rax
0x180009f5f  mov     rax, [rbp+37h+arg_28]
0x180009f63  mov     [rbp+37h+var_70], rax
0x180009f67  mov     rax, [rbp+37h+arg_50]
0x180009f6e  mov     [rbp+37h+Src], rax
0x180009f72  mov     al, cs:DiscpRequireOneWayCHAP
0x180009f78  mov     [rbp+37h+var_88], r8
0x180009f7c  mov     [rbp+37h+var_98], edx
0x180009f7f  mov     [rbp+37h+var_68], rcx
0x180009f83  mov     [rsp+110h+var_B8], r13w
0x180009f89  mov     [rbp+37h+var_A0], r13
0x180009f8d  mov     dword ptr [rbp+37h+Size], r13d
0x180009f91  mov     dword ptr [rbp+37h+Size+4], r13d
0x180009f95  mov     [rbp+37h+var_A8], r13
0x180009f99  test    al, al
0x180009f9b  jnz     short loc_180009FA6
0x180009f9d  cmp     cs:DiscpRequireMutualCHAP, r13b
0x180009fa4  jz      short loc_180009FCD
0x180009fa6  test    rsi, rsi
0x180009fa9  jz      loc_18000A3CF
0x180009faf  test    byte ptr [rsi+4], 80h
0x180009fb3  jz      loc_18000A3CF
0x180009fb9  test    al, al
0x180009fbb  jz      short loc_180009FC3
0x180009fbd  cmp     dword ptr [rsi+0Ch], 1
0x180009fc1  jz      short loc_180009FCD
0x180009fc3  cmp     dword ptr [rsi+0Ch], 2
0x180009fc7  jnz     loc_18000A3CF
0x180009fcd  lea     rcx, [rbp+37h+var_90]
0x180009fd1  mov     [rbp+37h+var_90], r13
0x180009fd5  mov     rdi, r13
0x180009fd8  call    DiscpGetDefaultiScsiName
0x180009fdd  mov     ebx, eax
0x180009fdf  test    eax, eax
0x180009fe1  jnz     loc_18000A390
0x180009fe7  mov     rcx, [rbp+37h+var_90]
0x180009feb  mov     al, r13b
0x180009fee  mov     [rbp+37h+var_80], rcx
0x180009ff2  mov     r12d, r13d
0x180009ff5  mov     [rsp+110h+var_C0], al
0x180009ff9  test    rsi, rsi
0x180009ffc  jz      short loc_18000A02B
0x180009ffe  test    byte ptr [rsi+4], 20h
0x18000a002  mov     r14d, r13d
0x18000a005  jz      short loc_18000A017
0x18000a007  cmp     [rsi+30h], r13
0x18000a00b  jz      short loc_18000A017
0x18000a00d  mov     r14d, [rsi+24h]
0x18000a011  mov     al, 1
0x18000a013  mov     [rsp+110h+var_C0], al
0x18000a017  test    byte ptr [rsi+4], 40h
0x18000a01b  jz      short loc_18000A027
0x18000a01d  cmp     [rsi+38h], r13
0x18000a021  jz      short loc_18000A027
0x18000a023  mov     r12d, [rsi+28h]
0x18000a027  test    al, al
0x18000a029  jnz     short loc_18000A053
0x18000a02b  xor     r8d, r8d
0x18000a02e  lea     rdx, [rbp+37h+var_A8]
0x18000a032  call    cs:__imp_DiscpUnicodeToAnsi
0x18000a038  mov     ebx, eax
0x18000a03a  test    eax, eax
0x18000a03c  jnz     loc_18000A390
0x18000a042  mov     rax, [rbp+37h+var_A8]
0x18000a046  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a04a  inc     r14
0x18000a04d  cmp     [rax+r14], r13b
0x18000a051  jnz     short loc_18000A04A
0x18000a053  mov     ebx, 1E0h
0x18000a058  mov     ecx, 0FFFFFFFFh
0x18000a05d  test    r15, r15
0x18000a060  jz      short loc_18000A07A
0x18000a062  mov     eax, [r15+5E0h]
0x18000a069  shl     rax, 4
0x18000a06d  cmp     rax, rcx
0x18000a070  ja      short loc_18000A0C7
0x18000a072  add     eax, ebx
0x18000a074  cmp     eax, ebx
0x18000a076  jb      short loc_18000A0C7
0x18000a078  mov     ebx, eax
0x18000a07a  mov     r13d, dword ptr [rbp+37h+arg_48]
0x18000a081  lea     r8, [rbp+37h+Size]
0x18000a085  mov     edx, 5
0x18000a08a  mov     [rbp+37h+var_44], r13d
0x18000a08e  lea     rcx, [rbp+37h+var_50]
0x18000a092  mov     [rbp+37h+var_50], 9E8h
0x18000a099  mov     [rbp+37h+var_4C], r14d
0x18000a09d  mov     [rbp+37h+var_48], r12d
0x18000a0a1  mov     [rbp+37h+var_40], ebx
0x18000a0a4  call    cs:__imp_DiscpULongAddList
0x18000a0aa  test    eax, eax
0x18000a0ac  js      short loc_18000A0C7
0x18000a0ae  mov     ecx, dword ptr [rbp+37h+Size]
0x18000a0b1  call    cs:__imp_DiscpAllocMemory
0x18000a0b7  mov     rdi, rax
0x18000a0ba  test    rax, rax
0x18000a0bd  jnz     short loc_18000A0D1
0x18000a0bf  lea     ebx, [rax+8]
0x18000a0c2  jmp     loc_18000A390
0x18000a0c7  mov     ebx, 57h ; 'W'
0x18000a0cc  jmp     loc_18000A390
0x18000a0d1  mov     r8d, dword ptr [rbp+37h+Size]; Size
0x18000a0d5  xor     edx, edx; Val
0x18000a0d7  mov     rcx, rdi; void *
0x18000a0da  call    memset_0
0x18000a0df  mov     eax, [rbp+37h+var_98]
0x18000a0e2  lea     rcx, [rdi+26Ch]
0x18000a0e9  mov     rdx, [rbp+37h+var_80]
0x18000a0ed  mov     r8d, 0DFh
0x18000a0f3  mov     [rdi], eax
0x18000a0f5  mov     rax, [rbp+37h+arg_40]
0x18000a0fc  mov     [rdi+28h], rax
0x18000a100  mov     eax, [rbp+37h+arg_20]
0x18000a103  mov     [rdi+24h], eax
0x18000a106  mov     al, [rbp+37h+arg_60]
0x18000a10c  mov     [rdi+26Ah], al
0x18000a112  call    cs:__imp_DiscpCopyToCountedString
0x18000a118  mov     rdx, [rbp+37h+var_88]
0x18000a11c  lea     rcx, [rdi+62Ch]
0x18000a123  mov     r8d, 0DFh
0x18000a129  call    cs:__imp_DiscpCopyToCountedString
0x18000a12f  lea     rcx, [rdi+42Ch]
0x18000a136  mov     r8d, 0FFh
0x18000a13c  lea     rdx, aMicrosoftWindo; "Microsoft Windows Software Initiator"
0x18000a143  call    cs:__imp_DiscpCopyToCountedString
0x18000a149  mov     word ptr [rdi+804h], 1BEh
0x18000a152  test    r15, r15
0x18000a155  jz      loc_18000A1DC
0x18000a15b  mov     eax, [r15+5D8h]
0x18000a162  xor     r8d, r8d
0x18000a165  mov     [rdi+7F0h], eax
0x18000a16b  mov     eax, [r15+5DCh]
0x18000a172  mov     [rdi+7F4h], eax
0x18000a178  mov     al, [rbp+37h+arg_60]
0x18000a17e  mov     [rdi+9C4h], al
0x18000a184  mov     eax, [r15+5E0h]
0x18000a18b  mov     [rdi+800h], eax
0x18000a191  cmp     [r15+5E0h], r8d
0x18000a198  jbe     short loc_18000A1FD
0x18000a19a  mov     rax, [r15+5E8h]
0x18000a1a1  mov     ecx, r8d
0x18000a1a4  add     rcx, 9Dh
0x18000a1ab  mov     edx, r8d
0x18000a1ae  add     rdx, rdx
0x18000a1b1  add     rcx, rcx
0x18000a1b4  inc     r8d
0x18000a1b7  mov     rax, [rax+rdx*8+8]
0x18000a1bc  mov     [rdi+rcx*8], rax
0x18000a1c0  mov     rax, [r15+5E8h]
0x18000a1c7  mov     ecx, [rax+rdx*8]
0x18000a1ca  mov     [rdi+rdx*8+9D8h], ecx
0x18000a1d1  cmp     r8d, [r15+5E0h]
0x18000a1d8  jb      short loc_18000A19A
0x18000a1da  jmp     short loc_18000A1FD
0x18000a1dc  mov     al, [rbp+37h+arg_60]
0x18000a1e2  mov     [rdi+9C4h], al
0x18000a1e8  mov     qword ptr [rdi+7F0h], 0FFFFFFFFFFFFFFFFh
0x18000a1f3  mov     dword ptr [rdi+800h], 0
0x18000a1fd  mov     rdx, [rbp+37h+Src]; Src
0x18000a201  add     ebx, 7F0h
0x18000a207  mov     ecx, ebx
0x18000a209  mov     r8, r13; Size
0x18000a20c  add     rcx, rdi; void *
0x18000a20f  mov     [rdi+264h], r13d
0x18000a216  call    memcpy_0
0x18000a21b  add     ebx, r13d
0x18000a21e  mov     [rdi+25Ch], r14d
0x18000a225  mov     ecx, ebx
0x18000a227  xor     r13d, r13d
0x18000a22a  add     rcx, rdi; void *
0x18000a22d  mov     dword ptr [rdi+4], 20h ; ' '
0x18000a234  mov     r8d, r14d; Size
0x18000a237  cmp     [rsp+110h+var_C0], r13b
0x18000a23c  jz      short loc_18000A244
0x18000a23e  mov     rdx, [rsi+30h]
0x18000a242  jmp     short loc_18000A248
0x18000a244  mov     rdx, [rbp+37h+var_A8]; Src
0x18000a248  call    memcpy_0
0x18000a24d  mov     [rdi+260h], r12d
0x18000a254  test    rsi, rsi
0x18000a257  jz      short loc_18000A2A1
0x18000a259  mov     eax, [rsi+4]
0x18000a25c  or      [rdi+4], eax
0x18000a25f  mov     eax, [rsi+10h]
0x18000a262  mov     [rdi+8], eax
0x18000a265  mov     eax, [rsi+14h]
0x18000a268  mov     [rdi+0Ch], eax
0x18000a26b  mov     eax, [rsi+18h]
0x18000a26e  mov     [rdi+10h], eax
0x18000a271  mov     eax, [rsi+1Ch]
0x18000a274  mov     [rdi+14h], eax
0x18000a277  mov     eax, [rsi+20h]
0x18000a27a  mov     [rdi+18h], eax
0x18000a27d  mov     eax, [rsi+8]
0x18000a280  mov     [rdi+1Ch], eax
0x18000a283  mov     eax, [rsi+0Ch]
0x18000a286  mov     [rdi+20h], eax
0x18000a289  test    r12d, r12d
0x18000a28c  jz      short loc_18000A2A1
0x18000a28e  mov     rdx, [rsi+38h]; Src
0x18000a292  lea     ecx, [rbx+r14]
0x18000a296  add     rcx, rdi; void *
0x18000a299  mov     r8d, r12d; Size
0x18000a29c  call    memcpy_0
0x18000a2a1  mov     rsi, [rbp+37h+var_68]
0x18000a2a5  lea     r9, [rdi+30h]
0x18000a2a9  mov     r14, [rbp+37h+var_70]
0x18000a2ad  mov     r8b, 1
0x18000a2b0  mov     ecx, [rsi+14h]
0x18000a2b3  and     cl, 1
0x18000a2b6  lea     rdx, [r14+200h]
0x18000a2bd  call    DiscpBuildIScsiIpAddress
0x18000a2c2  mov     ebx, eax
0x18000a2c4  test    eax, eax
0x18000a2c6  jnz     loc_18000A390
0x18000a2cc  movzx   eax, word ptr [r14+400h]
0x18000a2d4  lea     r8, [rsp+110h+var_B8]
0x18000a2d9  mov     rcx, [rbp+37h+var_88]
0x18000a2dd  mov     [rdi+258h], ax
0x18000a2e4  call    DiscpSelectISIDForTarget
0x18000a2e9  mov     ebx, eax
0x18000a2eb  test    eax, eax
0x18000a2ed  jnz     loc_18000A390
0x18000a2f3  movzx   eax, [rsp+110h+var_B8]
0x18000a2f8  lea     r9d, [rbx+1Eh]
0x18000a2fc  mov     [rdi+268h], ax
0x18000a303  lea     rcx, MSiSCSI_Operations_GUID
0x18000a30a  mov     r8, [rsi+28h]
0x18000a30e  lea     rax, [rbp+37h+Size+4]
0x18000a312  mov     [rsp+110h+var_D0], 18h
0x18000a31a  xor     edx, edx
0x18000a31c  mov     [rsp+110h+var_D8], rax
0x18000a321  lea     rax, [rbp+37h+var_A0]
0x18000a325  mov     [rsp+110h+var_E0], rax
0x18000a32a  mov     eax, dword ptr [rbp+37h+Size]
0x18000a32d  mov     [rsp+110h+var_E8], eax
0x18000a331  mov     [rsp+110h+var_F0], rdi
0x18000a336  mov     dword ptr [rbp+37h+Size+4], 118h
0x18000a33d  call    cs:__imp_DiscpExecuteMethod
0x18000a343  mov     ebx, eax
0x18000a345  test    eax, eax
0x18000a347  jnz     short loc_18000A37B
0x18000a349  mov     rcx, [rbp+37h+var_A0]
0x18000a34d  mov     ebx, [rcx]
0x18000a34f  test    ebx, ebx
0x18000a351  jnz     short loc_18000A37F
0x18000a353  mov     rax, [rcx+8]
0x18000a357  mov     rdx, [rbp+37h+var_60]
0x18000a35b  mov     [rdx+8], rax
0x18000a35f  mov     rax, [rsi+18h]
0x18000a363  mov     [rdx], rax
0x18000a366  mov     rax, [rcx+10h]
0x18000a36a  mov     rcx, [rbp+37h+var_58]
0x18000a36e  mov     [rcx+8], rax
0x18000a372  mov     rax, [rsi+18h]
0x18000a376  mov     [rcx], rax
0x18000a379  jmp     short loc_18000A390
0x18000a37b  mov     [rbp+37h+var_A0], r13
0x18000a37f  lea     eax, [rbx-1068h]
0x18000a385  mov     ecx, 0EFFF0044h
0x18000a38a  cmp     eax, 2
0x18000a38d  cmovbe  ebx, ecx
0x18000a390  mov     rcx, [rbp+37h+var_A8]
0x18000a394  test    rcx, rcx
0x18000a397  jz      short loc_18000A39F
0x18000a399  call    cs:__imp_DiscpFreeMemory
0x18000a39f  mov     rcx, [rbp+37h+var_A0]
0x18000a3a3  test    rcx, rcx
0x18000a3a6  jz      short loc_18000A3AE
0x18000a3a8  call    cs:__imp_DiscpFreeMemory
0x18000a3ae  test    rdi, rdi
0x18000a3b1  jz      short loc_18000A3BC
0x18000a3b3  mov     rcx, rdi
0x18000a3b6  call    cs:__imp_DiscpFreeMemory
0x18000a3bc  mov     rcx, [rbp+37h+var_90]
0x18000a3c0  test    rcx, rcx
0x18000a3c3  jz      short loc_18000A3CB
0x18000a3c5  call    cs:__imp_DiscpFreeMemory
0x18000a3cb  mov     eax, ebx
0x18000a3cd  jmp     short loc_18000A3D4
0x18000a3cf  mov     eax, 0EFFF0065h
  ... truncated ...
```
