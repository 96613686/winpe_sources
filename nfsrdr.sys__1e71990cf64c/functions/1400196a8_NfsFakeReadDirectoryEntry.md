# NfsFakeReadDirectoryEntry

- ea: `0x1400196a8`
- end: `0x140019cc7`
- name: `NfsFakeReadDirectoryEntry`
- size: `1567`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140013dc0`

## callees

- `0x140008140`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140017590`
- `0x1400196a8`
- `0x140019d7c`
- `0x140019e3c`
- `0x1400280c4`
- `0x14002c764`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400198c1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400198c1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001991a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001991a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019b69`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019c69`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019b69`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019c69`
- `ntoskrnl!KeReleaseMutex` at `0x1400197f4`
- `ntoskrnl!KeReleaseMutex` at `0x14001983e`
- `ntoskrnl!KeReleaseMutex` at `0x1400197f4`
- `ntoskrnl!KeReleaseMutex` at `0x14001983e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019c46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019c7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019c46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019c7b`
- `ntoskrnl!ExAllocatePool2` at `0x1400197b3`
- `ntoskrnl!ExAllocatePool2` at `0x1400199a2`
- `ntoskrnl!ExAllocatePool2` at `0x1400197b3`
- `ntoskrnl!ExAllocatePool2` at `0x1400199a2`

## pseudocode

```c
__int64 __fastcall NfsFakeReadDirectoryEntry(
        __int64 a1,
        __int64 a2,
        void **a3,
        char a4,
        _QWORD *a5,
        _QWORD *a6,
        _DWORD *a7,
        _QWORD *a8,
        _QWORD *a9)
{
  __int64 v9; // rax
  void **v10; // r14
  _QWORD *v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // r13
  _QWORD *v17; // rax
  __int64 v18; // rdx
  void *Pool2; // rax
  unsigned int v20; // ebx
  char v21; // r12
  int v22; // r14d
  int v23; // r8d
  PVOID *v24; // rbx
  char *v25; // rax
  _QWORD *v26; // rcx
  PVOID v27; // rcx
  __int64 v28; // rax
  PVOID v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  _QWORD *v32; // rax
  int v33; // edx
  _DWORD *v34; // rax
  __int64 v36; // [rsp+40h] [rbp-51h]
  PVOID P[2]; // [rsp+48h] [rbp-49h] BYREF
  PVOID v38[2]; // [rsp+58h] [rbp-39h] BYREF
  UNICODE_STRING String1; // [rsp+68h] [rbp-29h] BYREF
  __int128 v40; // [rsp+78h] [rbp-19h] BYREF
  __int64 v41; // [rsp+E0h] [rbp+4Fh] BYREF
  __int64 v42; // [rsp+E8h] [rbp+57h]
  void **v43; // [rsp+F0h] [rbp+5Fh]
  char v44; // [rsp+F8h] [rbp+67h]

  v44 = a4;
  v43 = a3;
  v9 = *(_QWORD *)(a1 + 32);
  v40 = 0;
  LOBYTE(v41) = 0;
  v10 = a3;
  v36 = *(_QWORD *)(*(_QWORD *)(v9 + 32) + 48LL);
  *(_OWORD *)v38 = 0;
  String1 = 0;
  *(_OWORD *)P = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids);
  v13 = *v10;
  v42 = *(_QWORD *)(a1 + 40);
  v14 = *(_QWORD *)(a1 + 32);
  v15 = *(_QWORD *)(v14 + 40);
  v16 = *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL);
  v17 = a5;
  *(_DWORD *)v13 = 4;
  v13[9] = 0xFFFFFFFFLL;
  *v17 = 0xFFFFFFFFLL;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  *((_DWORD *)v13 + 22) = 0;
  HacAcquireLock(a2);
  v18 = (unsigned __int16)(*(_WORD *)(v15 + 8) + *(_WORD *)(a2 + 64));
  LOWORD(v38[0]) = v18;
  WORD1(v38[0]) = v18;
  Pool2 = (void *)ExAllocatePool2(258, v18, 877815374);
  v38[1] = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, *(const void **)(v15 + 16), *(unsigned __int16 *)(v15 + 8));
    memmove(
      (char *)v38[1] + 2 * ((unsigned __int64)*(unsigned __int16 *)(v15 + 8) >> 1),
      *(const void **)(a2 + 72),
      *(unsigned __int16 *)(a2 + 64));
    KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
    if ( v13[10] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids);
    }
    a5 = 0;
    P[1] = P;
    v21 = 0;
    v22 = 0;
    P[0] = P;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v16 + 216));
    while ( 1 )
    {
LABEL_21:
      if ( !(unsigned __int8)MdaFindPrefixOfUnicodePrefix(
                               *(_QWORD *)(v16 + 232),
                               (int)v38,
                               v23,
                               (int)&a5,
                               (__int64)&v41,
                               &String1) )
        goto LABEL_41;
      v24 = P;
      while ( 1 )
      {
        v24 = (PVOID *)*v24;
        if ( v24 == P )
          break;
        if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(v24 + 3), 1u) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_ZZZZ(
              WPP_GLOBAL_Control->AttachedDevice,
              37,
              (unsigned int)WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids,
              (_DWORD)v24 + 24,
              (__int64)v38,
              *((_QWORD *)v24[2] + 6),
              a5[6]);
          }
          goto LABEL_21;
        }
      }
      if ( v22 == v13[10] )
        break;
      v25 = (char *)ExAllocatePool2(258, 40, 1196582478);
      if ( !v25 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids);
        while ( 1 )
        {
          v27 = P[0];
          if ( P[0] == P )
            break;
          if ( *((PVOID **)P[0] + 1) != P )
            goto LABEL_45;
          v28 = *(_QWORD *)P[0];
          if ( *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0] )
            goto LABEL_45;
          P[0] = *(PVOID *)P[0];
          *(_QWORD *)(v28 + 8) = P;
          ExFreePoolWithTag(v27, 0);
        }
        v20 = -1073741670;
        goto LABEL_54;
      }
      *((_QWORD *)v25 + 2) = a5;
      *(UNICODE_STRING *)(v25 + 24) = String1;
      v26 = P[0];
      if ( *((PVOID **)P[0] + 1) != P )
LABEL_45:
        __fastfail(3u);
      *(PVOID *)v25 = P[0];
      *((_QWORD *)v25 + 1) = P;
      ++v22;
      v26[1] = v25;
      P[0] = v25;
    }
    v21 = 1;
LABEL_41:
    while ( 1 )
    {
      v29 = P[0];
      if ( P[0] == P )
        break;
      if ( *((PVOID **)P[0] + 1) != P )
        goto LABEL_45;
      v30 = *(_QWORD *)P[0];
      if ( *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0] )
        goto LABEL_45;
      P[0] = *(PVOID *)P[0];
      *(_QWORD *)(v30 + 8) = P;
      ExFreePoolWithTag(v29, 0);
    }
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          (unsigned int)WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids,
          (unsigned int)&String1,
          (__int64)v38);
      LOWORD(v40) = String1.Length >> 1;
      WORD1(v40) = (String1.Length >> 1) + 1;
      *((_QWORD *)&v40 + 1) = v13[32];
      v31 = NfsConvertUnicodeToAnsi(v36, &v40, &String1);
      v20 = v31;
      if ( v31 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            40,
            WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids,
            (unsigned int)v31);
LABEL_54:
        ExReleaseFastMutex(*(PFAST_MUTEX *)(v16 + 216));
        ExFreePoolWithTag(v38[1], 0);
        v10 = v43;
        goto LABEL_55;
      }
      v32 = a6;
      ++v13[10];
      v33 = (unsigned __int16)v40;
      v20 = 0;
      *v32 = v13[32];
      v34 = a7;
      *((_DWORD *)v13 + 22) = v33;
      *v34 = v33;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids, v38);
      if ( v44 )
        ExFreePoolWithTag(v13, 0);
      v20 = -2147483642;
      *v43 = 0;
    }
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v16 + 216));
    ExFreePoolWithTag(v38[1], 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids);
    KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
    v20 = -1073741670;
LABEL_55:
    if ( v44 )
      ExFreePoolWithTag(v13, 0);
    *v10 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids, v20);
  }
  return v20;
}

```

## disassembly

```asm
0x1400196a8  mov     [rsp-8+arg_18], r9b
0x1400196ad  mov     [rsp-8+arg_10], r8
0x1400196b2  push    rbp
0x1400196b3  push    rbx
0x1400196b4  push    rsi
0x1400196b5  push    rdi
0x1400196b6  push    r12
0x1400196b8  push    r13
0x1400196ba  push    r14
0x1400196bc  push    r15
0x1400196be  lea     rbp, [rsp-7]
0x1400196c3  sub     rsp, 98h
0x1400196ca  mov     rax, [rcx+20h]
0x1400196ce  xorps   xmm0, xmm0
0x1400196d1  movups  [rbp+3Fh+var_58], xmm0
0x1400196d5  mov     byte ptr [rbp+3Fh+arg_0], 0
0x1400196d9  mov     r14, r8
0x1400196dc  xorps   xmm1, xmm1
0x1400196df  mov     rbx, rdx
0x1400196e2  mov     r10, [rax+20h]
0x1400196e6  mov     rdi, rcx
0x1400196e9  mov     rax, [r10+30h]
0x1400196ed  mov     [rbp+3Fh+var_90], rax
0x1400196f1  movups  xmmword ptr [rbp+3Fh+var_78], xmm0
0x1400196f5  movups  xmmword ptr [rbp+3Fh+String1.Length], xmm1
0x1400196f9  movups  xmmword ptr [rbp+3Fh+P], xmm0
0x1400196fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140019704  lea     r15, WPP_GLOBAL_Control
0x14001970b  lea     r12, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids
0x140019712  cmp     rcx, r15
0x140019715  jz      short loc_14001972F
0x140019717  mov     eax, [rcx+2Ch]
0x14001971a  test    al, 2
0x14001971c  jz      short loc_14001972F
0x14001971e  mov     rcx, [rcx+18h]
0x140019722  mov     edx, 21h ; '!'
0x140019727  mov     r8, r12
0x14001972a  call    WPP_SF_
0x14001972f  mov     rax, [rdi+28h]
0x140019733  mov     ecx, 0FFFFFFFFh
0x140019738  mov     rsi, [r14]
0x14001973b  mov     [rbp+3Fh+arg_8], rax
0x14001973f  mov     rax, [rdi+20h]
0x140019743  mov     rdi, [rax+28h]
0x140019747  mov     rax, [rax+20h]
0x14001974b  mov     r13, [rax+20h]
0x14001974f  mov     rax, [rbp+3Fh+arg_20]
0x140019753  mov     dword ptr [rsi], 4
0x140019759  mov     [rsi+48h], rcx
0x14001975d  mov     [rax], rcx
0x140019760  mov     rax, [rbp+3Fh+arg_38]
0x140019767  test    rax, rax
0x14001976a  jz      short loc_140019773
0x14001976c  mov     qword ptr [rax], 0
0x140019773  mov     rax, [rbp+3Fh+arg_40]
0x14001977a  test    rax, rax
0x14001977d  jz      short loc_140019786
0x14001977f  mov     qword ptr [rax], 0
0x140019786  mov     rcx, rbx
0x140019789  mov     dword ptr [rsi+58h], 0
0x140019790  call    HacAcquireLock
0x140019795  movzx   ecx, word ptr [rbx+40h]
0x140019799  mov     r8d, 3452664Eh
0x14001979f  add     cx, [rdi+8]
0x1400197a3  movzx   edx, cx
0x1400197a6  mov     ecx, 102h
0x1400197ab  mov     word ptr [rbp+3Fh+var_78], dx
0x1400197af  mov     word ptr [rbp+3Fh+var_78+2], dx
0x1400197b3  call    cs:__imp_ExAllocatePool2
0x1400197ba  nop     dword ptr [rax+rax+00h]
0x1400197bf  mov     [rbp+3Fh+var_78+8], rax
0x1400197c3  test    rax, rax
0x1400197c6  jnz     short loc_14001980A
0x1400197c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400197cf  lea     edi, [rax+1]
0x1400197d2  cmp     rcx, r15
0x1400197d5  jz      short loc_1400197EE
0x1400197d7  mov     eax, [rcx+2Ch]
0x1400197da  test    dil, al
0x1400197dd  jz      short loc_1400197EE
0x1400197df  mov     rcx, [rcx+18h]
0x1400197e3  lea     edx, [rdi+21h]
0x1400197e6  mov     r8, r12
0x1400197e9  call    WPP_SF_
0x1400197ee  mov     rcx, [rbx+28h]; Mutex
0x1400197f2  xor     edx, edx; Wait
0x1400197f4  call    cs:__imp_KeReleaseMutex
0x1400197fb  nop     dword ptr [rax+rax+00h]
0x140019800  mov     ebx, 0C000009Ah
0x140019805  jmp     loc_140019B92
0x14001980a  movzx   r8d, word ptr [rdi+8]; Size
0x14001980f  mov     rcx, rax; void *
0x140019812  mov     rdx, [rdi+10h]; Src
0x140019816  call    memmove
0x14001981b  movzx   ecx, word ptr [rdi+8]
0x14001981f  mov     rax, [rbp+3Fh+var_78+8]
0x140019823  movzx   r8d, word ptr [rbx+40h]; Size
0x140019828  mov     rdx, [rbx+48h]; Src
0x14001982c  shr     rcx, 1
0x14001982f  lea     rcx, [rax+rcx*2]; void *
0x140019833  call    memmove
0x140019838  mov     rcx, [rbx+28h]; Mutex
0x14001983c  xor     edx, edx; Wait
0x14001983e  call    cs:__imp_KeReleaseMutex
0x140019845  nop     dword ptr [rax+rax+00h]
0x14001984a  mov     r9, [rsi+50h]
0x14001984e  test    r9, r9
0x140019851  jnz     short loc_140019878
0x140019853  mov     rcx, cs:WPP_GLOBAL_Control
0x14001985a  cmp     rcx, r15
0x14001985d  jz      short loc_14001989C
0x14001985f  mov     eax, [rcx+2Ch]
0x140019862  test    al, 2
0x140019864  jz      short loc_14001989C
0x140019866  mov     rcx, [rcx+18h]
0x14001986a  lea     edx, [r9+23h]
0x14001986e  mov     r8, r12
0x140019871  call    WPP_SF_
0x140019876  jmp     short loc_14001989C
0x140019878  mov     rcx, cs:WPP_GLOBAL_Control
0x14001987f  cmp     rcx, r15
0x140019882  jz      short loc_14001989C
0x140019884  mov     eax, [rcx+2Ch]
0x140019887  test    al, 2
0x140019889  jz      short loc_14001989C
0x14001988b  mov     rcx, [rcx+18h]
0x14001988f  mov     edx, 24h ; '$'
0x140019894  mov     r8, r12
0x140019897  call    WPP_SF_q
0x14001989c  lea     rax, [rbp+3Fh+P]
0x1400198a0  mov     [rbp+3Fh+arg_20], 0
0x1400198a8  mov     [rbp+3Fh+P+8], rax
0x1400198ac  xor     r12b, r12b
0x1400198af  lea     rax, [rbp+3Fh+P]
0x1400198b3  xor     r14d, r14d
0x1400198b6  mov     [rbp+3Fh+P], rax
0x1400198ba  mov     rcx, [r13+0D8h]; FastMutex
0x1400198c1  call    cs:__imp_ExAcquireFastMutex
0x1400198c8  nop     dword ptr [rax+rax+00h]
0x1400198cd  lea     edi, [r14+1]
0x1400198d1  mov     rcx, [r13+0E8h]; int
0x1400198d8  lea     rax, [rbp+3Fh+String1]
0x1400198dc  mov     [rsp+0D0h+FirstName], rax; FirstName
0x1400198e1  lea     r9, [rbp+3Fh+arg_20]; int
0x1400198e5  lea     rax, [rbp+3Fh+arg_0]
0x1400198e9  lea     rdx, [rbp+3Fh+var_78]; int
0x1400198ed  mov     [rsp+0D0h+var_B0], rax; __int64
0x1400198f2  call    MdaFindPrefixOfUnicodePrefix
0x1400198f7  test    al, al
0x1400198f9  jz      loc_140019A6A
0x1400198ff  lea     rbx, [rbp+3Fh+P]
0x140019903  mov     rbx, [rbx]
0x140019906  lea     rax, [rbp+3Fh+P]
0x14001990a  cmp     rbx, rax
0x14001990d  jz      short loc_140019985
0x14001990f  mov     r8b, dil; CaseInSensitive
0x140019912  lea     rdx, [rbx+18h]; String2
0x140019916  lea     rcx, [rbp+3Fh+String1]; String1
0x14001991a  call    cs:__imp_RtlEqualUnicodeString
0x140019921  nop     dword ptr [rax+rax+00h]
0x140019926  test    al, al
0x140019928  jz      short loc_140019903
0x14001992a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019931  lea     rax, WPP_GLOBAL_Control
0x140019938  cmp     rcx, rax
0x14001993b  jz      short loc_1400198D1
0x14001993d  mov     eax, [rcx+2Ch]
0x140019940  test    al, 2
0x140019942  jz      short loc_1400198D1
0x140019944  mov     rax, [rbp+3Fh+arg_20]
0x140019948  lea     r9, [rbx+18h]
0x14001994c  mov     r10, [rbx+10h]
0x140019950  mov     edx, 25h ; '%'
0x140019955  mov     rcx, [rcx+18h]
0x140019959  mov     r8, [rax+30h]
0x14001995d  mov     rax, [r10+30h]
0x140019961  mov     [rsp+0D0h+var_A0], r8
0x140019966  lea     r8, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids
0x14001996d  mov     [rsp+0D0h+FirstName], rax
0x140019972  lea     rax, [rbp+3Fh+var_78]
0x140019976  mov     [rsp+0D0h+var_B0], rax
0x14001997b  call    WPP_SF_ZZZZ
0x140019980  jmp     loc_1400198D1
0x140019985  mov     eax, r14d
0x140019988  cmp     rax, [rsi+50h]
0x14001998c  jz      loc_140019A67
0x140019992  mov     edx, 28h ; '('
0x140019997  mov     ecx, 102h
0x14001999c  mov     r8d, 4752664Eh
0x1400199a2  call    cs:__imp_ExAllocatePool2
0x1400199a9  nop     dword ptr [rax+rax+00h]
0x1400199ae  test    rax, rax
0x1400199b1  jz      short loc_1400199F1
0x1400199b3  mov     rcx, [rbp+3Fh+arg_20]
0x1400199b7  lea     rdx, [rbp+3Fh+P]
0x1400199bb  mov     [rax+10h], rcx
0x1400199bf  movups  xmm0, xmmword ptr [rbp+3Fh+String1.Length]
0x1400199c3  movdqu  xmmword ptr [rax+18h], xmm0
0x1400199c8  mov     rcx, [rbp+3Fh+P]
0x1400199cc  cmp     [rcx+8], rdx
0x1400199d0  jnz     loc_140019AA6
0x1400199d6  mov     [rax], rcx
0x1400199d9  lea     rdx, [rbp+3Fh+P]
0x1400199dd  mov     [rax+8], rdx
0x1400199e1  add     r14d, edi
0x1400199e4  mov     [rcx+8], rax
0x1400199e8  mov     [rbp+3Fh+P], rax
0x1400199ec  jmp     loc_1400198D1
0x1400199f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400199f8  lea     r15, WPP_GLOBAL_Control
0x1400199ff  cmp     rcx, r15
0x140019a02  jz      short loc_140019A21
0x140019a04  mov     eax, [rcx+2Ch]
0x140019a07  test    dil, al
0x140019a0a  jz      short loc_140019A21
0x140019a0c  mov     rcx, [rcx+18h]
0x140019a10  lea     r8, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids
0x140019a17  mov     edx, 26h ; '&'
0x140019a1c  call    WPP_SF_
0x140019a21  mov     rcx, [rbp+3Fh+P]; P
0x140019a25  lea     rax, [rbp+3Fh+P]
0x140019a29  cmp     rcx, rax
0x140019a2c  jz      short loc_140019A5D
0x140019a2e  lea     rax, [rbp+3Fh+P]
0x140019a32  cmp     [rcx+8], rax
0x140019a36  jnz     short loc_140019AA6
0x140019a38  mov     rax, [rcx]
0x140019a3b  cmp     [rax+8], rcx
0x140019a3f  jnz     short loc_140019AA6
0x140019a41  lea     rdx, [rbp+3Fh+P]
0x140019a45  mov     [rbp+3Fh+P], rax
0x140019a49  mov     [rax+8], rdx
0x140019a4d  xor     edx, edx; Tag
0x140019a4f  call    cs:__imp_ExFreePoolWithTag
0x140019a56  nop     dword ptr [rax+rax+00h]
0x140019a5b  jmp     short loc_140019A21
0x140019a5d  mov     ebx, 0C000009Ah
0x140019a62  jmp     loc_140019B62
0x140019a67  mov     r12b, dil
0x140019a6a  mov     rcx, [rbp+3Fh+P]; P
0x140019a6e  lea     rax, [rbp+3Fh+P]
0x140019a72  cmp     rcx, rax
0x140019a75  jz      short loc_140019AAD
0x140019a77  lea     rax, [rbp+3Fh+P]
0x140019a7b  cmp     [rcx+8], rax
0x140019a7f  jnz     short loc_140019AA6
0x140019a81  mov     rax, [rcx]
0x140019a84  cmp     [rax+8], rcx
0x140019a88  jnz     short loc_140019AA6
0x140019a8a  lea     rdx, [rbp+3Fh+P]
0x140019a8e  mov     [rbp+3Fh+P], rax
0x140019a92  mov     [rax+8], rdx
0x140019a96  xor     edx, edx; Tag
0x140019a98  call    cs:__imp_ExFreePoolWithTag
0x140019a9f  nop     dword ptr [rax+rax+00h]
0x140019aa4  jmp     short loc_140019A6A
0x140019aa6  mov     ecx, 3
0x140019aab  int     29h; Win8: RtlFailFast(ecx)
0x140019aad  test    r12b, r12b
0x140019ab0  jz      loc_140019C08
0x140019ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140019abd  lea     r15, WPP_GLOBAL_Control
0x140019ac4  cmp     rcx, r15
0x140019ac7  jz      short loc_140019AF2
0x140019ac9  mov     eax, [rcx+2Ch]
0x140019acc  test    al, 2
0x140019ace  jz      short loc_140019AF2
0x140019ad0  mov     rcx, [rcx+18h]
0x140019ad4  lea     rax, [rbp+3Fh+var_78]
0x140019ad8  mov     edx, 27h ; '''
0x140019add  mov     [rsp+0D0h+var_B0], rax
0x140019ae2  lea     r9, [rbp+3Fh+String1]
0x140019ae6  lea     r8, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids
0x140019aed  call    WPP_SF_ZZ
0x140019af2  movzx   eax, [rbp+3Fh+String1.Length]
0x140019af6  lea     r8, [rbp+3Fh+String1]
0x140019afa  mov     rcx, [rbp+3Fh+var_90]
0x140019afe  lea     rdx, [rbp+3Fh+var_58]
0x140019b02  shr     ax, 1
0x140019b05  mov     word ptr [rbp+3Fh+var_58], ax
0x140019b09  add     ax, di
0x140019b0c  mov     word ptr [rbp+3Fh+var_58+2], ax
0x140019b10  mov     rax, [rsi+100h]
0x140019b17  mov     qword ptr [rbp+3Fh+var_58+8], rax
0x140019b1b  mov     rax, [rbp+3Fh+arg_8]
0x140019b1f  mov     eax, [rax+20h]
0x140019b22  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140019b26  call    NfsConvertUnicodeToAnsi
0x140019b2b  mov     ebx, eax
0x140019b2d  test    eax, eax
0x140019b2f  jns     loc_140019BE5
0x140019b35  mov     rcx, cs:WPP_GLOBAL_Control
0x140019b3c  cmp     rcx, r15
0x140019b3f  jz      short loc_140019B62
0x140019b41  mov     r8d, [rcx+2Ch]
0x140019b45  test    dil, r8b
0x140019b48  jz      short loc_140019B62
0x140019b4a  mov     rcx, [rcx+18h]
0x140019b4e  lea     r8, WPP_5c6a788431e334dc2cddcd22b57d59fa_Traceguids
0x140019b55  mov     edx, 28h ; '('
  ... truncated ...
```
