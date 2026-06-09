# ClipCallServer

- ea: `0x18001dfd0`
- end: `0x18001e3ea`
- name: `ClipCallServer`
- size: `1050`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, LONGLONG)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x18001003c`
- `0x18001eb10`

## callees

- `0x1800011bc`
- `0x1800017f0`
- `0x180002b3c`
- `0x1800031ac`
- `0x1800038b8`
- `0x180003a10`
- `0x180006f34`
- `0x18000717c`
- `0x18001a478`
- `0x18001a810`
- `0x18001dfd0`
- `0x1800246b4`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e3b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e3c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e3b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e3c2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001e298`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001e298`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e043`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e28d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e043`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e28d`

## pseudocode

```c
__int64 __fastcall ClipCallServer(__int64 a1, const WCHAR *a2, __int64 a3, LONGLONG a4)
{
  HLOCAL v4; // r14
  void *QuadPart; // r15
  LARGE_INTEGER v6; // rsi
  int v10; // r13d
  __int64 v11; // rcx
  int v12; // ebx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  LARGE_INTEGER *v19; // r12
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  unsigned int v24; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-A5h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-A1h] BYREF
  LARGE_INTEGER Frequency; // [rsp+40h] [rbp-99h] BYREF
  LARGE_INTEGER v28; // [rsp+48h] [rbp-91h] BYREF
  __int64 v29; // [rsp+50h] [rbp-89h] BYREF
  __int128 *v30; // [rsp+58h] [rbp-81h]
  __int128 v31; // [rsp+60h] [rbp-79h] BYREF
  LONGLONG v32; // [rsp+70h] [rbp-69h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-61h] BYREF
  _BYTE v34[32]; // [rsp+80h] [rbp-59h] BYREF
  const WCHAR *v35; // [rsp+A0h] [rbp-39h]
  int v36; // [rsp+A8h] [rbp-31h]
  int v37; // [rsp+ACh] [rbp-2Dh]
  unsigned int *v38; // [rsp+B0h] [rbp-29h]
  __int64 v39; // [rsp+B8h] [rbp-21h]
  HLOCAL *p_hMem; // [rsp+C0h] [rbp-19h]
  __int64 v41; // [rsp+C8h] [rbp-11h]
  LONGLONG *v42; // [rsp+D0h] [rbp-9h]
  __int64 v43; // [rsp+D8h] [rbp-1h]

  v32 = a4;
  v24 = 0;
  v4 = 0;
  hMem = 0;
  QuadPart = 0;
  v25 = 0;
  v6.QuadPart = 0;
  Frequency.QuadPart = 0;
  v28.QuadPart = 0;
  v29 = (__int64)&v31 + 8;
  v30 = &v31;
  v31 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v10 = 2;
  if ( a1 && a2 )
  {
    if ( a3 )
    {
      v13 = sub_18001A478(a3, &hMem, &v24);
      v4 = hMem;
      v12 = v13;
      if ( v13 < 0 )
      {
LABEL_6:
        v11 = (unsigned int)v12;
        goto LABEL_34;
      }
    }
    else
    {
      v24 = 0;
    }
    LODWORD(hMem) = 0;
    v14 = sub_1800038B8(a2, &hMem);
    v12 = v14;
    if ( v14 < 0 || (v14 = sub_18001A810(v29, 1, (unsigned int)hMem, a2), v12 = v14, v14 < 0) )
      sub_180002B3C((unsigned int)v14);
    sub_1800031AC((unsigned int)v12);
    if ( v12 < 0 )
      goto LABEL_6;
    v15 = sub_18001A810(v29, 2, 4, &v24);
    v12 = v15;
    if ( v15 < 0 )
      sub_180002B3C((unsigned int)v15);
    sub_1800031AC((unsigned int)v12);
    if ( v12 < 0 )
      goto LABEL_6;
    v16 = sub_18001A810(v29, 3, v24, v4);
    v12 = v16;
    if ( v16 < 0 )
      sub_180002B3C((unsigned int)v16);
    sub_1800031AC((unsigned int)v12);
    if ( v12 < 0 )
      goto LABEL_6;
    v17 = sub_1800246B4(a1, 7, v29, (__int64)&v31);
    v12 = v17;
    if ( v17 < 0 )
      sub_180002B3C((unsigned int)v17);
    sub_1800031AC((unsigned int)v12);
    if ( v12 == -2147023782 )
    {
      v18 = sub_1800246B4(a1, 7, v29, (__int64)&v31);
      v12 = v18;
      if ( v18 < 0 )
        sub_180002B3C((unsigned int)v18);
      sub_1800031AC((unsigned int)v12);
    }
    if ( v12 < 0 )
    {
      v11 = (unsigned int)v12;
      goto LABEL_34;
    }
    v19 = (LARGE_INTEGER *)v32;
    if ( !v32 )
      goto LABEL_44;
    v20 = sub_18000717C(v30, 1, 4, &v25);
    v12 = v20;
    if ( v20 < 0 )
      sub_180002B3C((unsigned int)v20);
    sub_1800031AC((unsigned int)v12);
    if ( v12 < 0 )
      goto LABEL_6;
    v21 = sub_180006F34(&v29, 2, v25, &Frequency);
    QuadPart = (void *)Frequency.QuadPart;
    v12 = v21;
    if ( v21 >= 0 )
    {
      v21 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))sub_180003A10)(
              (LARGE_INTEGER)Frequency.QuadPart,
              v25,
              &v28);
      v12 = v21;
      if ( v21 >= 0 )
      {
        *v19 = v28;
        goto LABEL_44;
      }
      v6 = v28;
    }
    v11 = (unsigned int)v21;
  }
  else
  {
    v11 = 2147942487LL;
    v12 = -2147024809;
  }
LABEL_34:
  sub_180002B3C(v11);
  if ( (unsigned int)dword_180030048 > 5
    && (qword_180030058 & 0x400000000000LL) != 0
    && (qword_180030060 & 0x400000000000LL) == qword_180030060 )
  {
    Frequency.QuadPart = 0;
    v28.QuadPart = 0;
    QueryPerformanceCounter(&v28);
    QueryPerformanceFrequency(&Frequency);
    LODWORD(hMem) = v12;
    v43 = 8;
    v41 = 4;
    v32 = 1000000 * (v28.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
    v25 = v24;
    v42 = &v32;
    p_hMem = &hMem;
    v38 = &v25;
    v39 = 4;
    if ( a2 )
    {
      v22 = -1;
      do
        ++v22;
      while ( a2[v22] );
      v10 = 2 * v22 + 2;
    }
    else
    {
      a2 = &LocaleName;
    }
    v35 = a2;
    v36 = v10;
    v37 = 0;
    sub_1800011BC(&dword_180030048, byte_18002C6D3, 0, 0, 6, v34);
  }
LABEL_44:
  sub_1800031AC((unsigned int)v12);
  if ( *((_QWORD *)&v31 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v31 + 1) + 16LL))(*((_QWORD *)&v31 + 1));
    *((_QWORD *)&v31 + 1) = 0;
  }
  if ( (_QWORD)v31 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31 + 16LL))(v31);
    *(_QWORD *)&v31 = 0;
  }
  if ( v6.QuadPart )
    (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v6.QuadPart + 16LL))(v6);
  if ( QuadPart )
    LocalFree(QuadPart);
  if ( v4 )
    LocalFree(v4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001dfd0  push    rbp
0x18001dfd2  push    rbx
0x18001dfd3  push    rsi
0x18001dfd4  push    rdi
0x18001dfd5  push    r12
0x18001dfd7  push    r13
0x18001dfd9  push    r14
0x18001dfdb  push    r15
0x18001dfdd  lea     rbp, [rsp-1Fh]
0x18001dfe2  sub     rsp, 0F8h
0x18001dfe9  mov     rax, cs:__security_cookie
0x18001dff0  xor     rax, rsp
0x18001dff3  mov     [rbp+57h+var_50], rax
0x18001dff7  xor     eax, eax
0x18001dff9  mov     [rbp+57h+var_C0], r9
0x18001dffd  mov     [rsp+130h+var_100], eax
0x18001e001  mov     r14d, eax
0x18001e004  mov     [rsp+130h+hMem], rax
0x18001e009  mov     r15d, eax
0x18001e00c  mov     [rsp+130h+var_FC], eax
0x18001e010  mov     esi, eax
0x18001e012  mov     qword ptr [rsp+130h+Frequency], rax
0x18001e017  mov     r12, rcx
0x18001e01a  mov     qword ptr [rsp+130h+var_E8], rax
0x18001e01f  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18001e023  lea     rax, [rbp+57h+var_D0+8]
0x18001e027  xorps   xmm0, xmm0
0x18001e02a  mov     [rsp+130h+var_E0], rax
0x18001e02f  mov     rbx, r8
0x18001e032  lea     rax, [rbp+57h+var_D0]
0x18001e036  mov     rdi, rdx
0x18001e039  mov     [rsp+130h+var_D8], rax
0x18001e03e  movdqu  [rbp+57h+var_D0], xmm0
0x18001e043  call    cs:QueryPerformanceCounter
0x18001e049  xor     eax, eax
0x18001e04b  lea     r13d, [rsi+2]
0x18001e04f  test    r12, r12
0x18001e052  jnz     short loc_18001E060
0x18001e054  mov     ecx, 80070057h
0x18001e059  mov     ebx, ecx
0x18001e05b  jmp     loc_18001E237
0x18001e060  test    rdi, rdi
0x18001e063  jz      short loc_18001E054
0x18001e065  test    rbx, rbx
0x18001e068  jz      short loc_18001E090
0x18001e06a  lea     r8, [rsp+130h+var_100]
0x18001e06f  mov     rcx, rbx
0x18001e072  lea     rdx, [rsp+130h+hMem]
0x18001e077  call    sub_18001A478
0x18001e07c  mov     r14, [rsp+130h+hMem]
0x18001e081  mov     ebx, eax
0x18001e083  xor     eax, eax
0x18001e085  test    ebx, ebx
0x18001e087  jns     short loc_18001E094
0x18001e089  mov     ecx, ebx
0x18001e08b  jmp     loc_18001E237
0x18001e090  mov     [rsp+130h+var_100], eax
0x18001e094  lea     rdx, [rsp+130h+hMem]
0x18001e099  mov     dword ptr [rsp+130h+hMem], eax
0x18001e09d  mov     rcx, rdi
0x18001e0a0  call    sub_1800038B8
0x18001e0a5  mov     ebx, eax
0x18001e0a7  test    eax, eax
0x18001e0a9  js      short loc_18001E0C8
0x18001e0ab  mov     r8d, dword ptr [rsp+130h+hMem]
0x18001e0b0  mov     r9, rdi
0x18001e0b3  mov     rcx, [rsp+130h+var_E0]
0x18001e0b8  mov     edx, 1
0x18001e0bd  call    sub_18001A810
0x18001e0c2  mov     ebx, eax
0x18001e0c4  test    eax, eax
0x18001e0c6  jns     short loc_18001E0CF
0x18001e0c8  mov     ecx, eax
0x18001e0ca  call    sub_180002B3C
0x18001e0cf  mov     ecx, ebx
0x18001e0d1  call    sub_1800031AC
0x18001e0d6  test    ebx, ebx
0x18001e0d8  js      short loc_18001E089
0x18001e0da  mov     rcx, [rsp+130h+var_E0]
0x18001e0df  lea     r9, [rsp+130h+var_100]
0x18001e0e4  mov     r8d, 4
0x18001e0ea  mov     edx, r13d
0x18001e0ed  call    sub_18001A810
0x18001e0f2  mov     ebx, eax
0x18001e0f4  test    eax, eax
0x18001e0f6  jns     short loc_18001E0FF
0x18001e0f8  mov     ecx, eax
0x18001e0fa  call    sub_180002B3C
0x18001e0ff  mov     ecx, ebx
0x18001e101  call    sub_1800031AC
0x18001e106  test    ebx, ebx
0x18001e108  js      loc_18001E089
0x18001e10e  mov     r8d, [rsp+130h+var_100]
0x18001e113  mov     r9, r14
0x18001e116  mov     rcx, [rsp+130h+var_E0]
0x18001e11b  mov     edx, 3
0x18001e120  call    sub_18001A810
0x18001e125  mov     ebx, eax
0x18001e127  test    eax, eax
0x18001e129  jns     short loc_18001E132
0x18001e12b  mov     ecx, eax
0x18001e12d  call    sub_180002B3C
0x18001e132  mov     ecx, ebx
0x18001e134  call    sub_1800031AC
0x18001e139  test    ebx, ebx
0x18001e13b  js      loc_18001E089
0x18001e141  mov     r8, [rsp+130h+var_E0]
0x18001e146  lea     r9, [rbp+57h+var_D0]
0x18001e14a  mov     edx, 7
0x18001e14f  mov     rcx, r12
0x18001e152  call    sub_1800246B4
0x18001e157  mov     ebx, eax
0x18001e159  test    eax, eax
0x18001e15b  jns     short loc_18001E164
0x18001e15d  mov     ecx, eax
0x18001e15f  call    sub_180002B3C
0x18001e164  mov     ecx, ebx
0x18001e166  call    sub_1800031AC
0x18001e16b  cmp     ebx, 8007045Ah
0x18001e171  jnz     short loc_18001E1A2
0x18001e173  mov     r8, [rsp+130h+var_E0]
0x18001e178  lea     r9, [rbp+57h+var_D0]
0x18001e17c  mov     edx, 7
0x18001e181  mov     rcx, r12
0x18001e184  call    sub_1800246B4
0x18001e189  xor     r12d, r12d
0x18001e18c  mov     ebx, eax
0x18001e18e  test    eax, eax
0x18001e190  jns     short loc_18001E199
0x18001e192  mov     ecx, eax
0x18001e194  call    sub_180002B3C
0x18001e199  mov     ecx, ebx
0x18001e19b  call    sub_1800031AC
0x18001e1a0  jmp     short loc_18001E1A5
0x18001e1a2  xor     r12d, r12d
0x18001e1a5  test    ebx, ebx
0x18001e1a7  jns     short loc_18001E1B0
0x18001e1a9  mov     ecx, ebx
0x18001e1ab  jmp     loc_18001E23A
0x18001e1b0  mov     r12, [rbp+57h+var_C0]
0x18001e1b4  test    r12, r12
0x18001e1b7  jz      loc_18001E35C
0x18001e1bd  mov     rcx, [rsp+130h+var_D8]
0x18001e1c2  lea     r9, [rsp+130h+var_FC]
0x18001e1c7  mov     edx, 1
0x18001e1cc  lea     r8d, [rdx+3]
0x18001e1d0  call    sub_18000717C
0x18001e1d5  mov     ebx, eax
0x18001e1d7  test    eax, eax
0x18001e1d9  jns     short loc_18001E1E2
0x18001e1db  mov     ecx, eax
0x18001e1dd  call    sub_180002B3C
0x18001e1e2  mov     ecx, ebx
0x18001e1e4  call    sub_1800031AC
0x18001e1e9  test    ebx, ebx
0x18001e1eb  js      loc_18001E089
0x18001e1f1  mov     r8d, [rsp+130h+var_FC]
0x18001e1f6  lea     r9, [rsp+130h+Frequency]
0x18001e1fb  mov     edx, r13d
0x18001e1fe  lea     rcx, [rsp+130h+var_E0]
0x18001e203  call    sub_180006F34
0x18001e208  mov     r15, qword ptr [rsp+130h+Frequency]
0x18001e20d  mov     ebx, eax
0x18001e20f  test    eax, eax
0x18001e211  js      short loc_18001E235
0x18001e213  mov     edx, [rsp+130h+var_FC]
0x18001e217  lea     r8, [rsp+130h+var_E8]
0x18001e21c  mov     rcx, r15
0x18001e21f  call    sub_180003A10
0x18001e224  xor     ecx, ecx
0x18001e226  mov     ebx, eax
0x18001e228  test    eax, eax
0x18001e22a  jns     loc_18001E353
0x18001e230  mov     rsi, qword ptr [rsp+130h+var_E8]
0x18001e235  mov     ecx, eax
0x18001e237  xor     r12d, r12d
0x18001e23a  call    sub_180002B3C
0x18001e23f  mov     ecx, cs:dword_180030048
0x18001e245  cmp     ecx, 5
0x18001e248  jbe     loc_18001E35C
0x18001e24e  mov     rcx, cs:qword_180030060
0x18001e255  mov     rdx, 400000000000h
0x18001e25f  mov     rax, cs:qword_180030058
0x18001e266  test    rdx, rax
0x18001e269  jz      loc_18001E35C
0x18001e26f  mov     rax, rcx
0x18001e272  and     rax, rdx
0x18001e275  cmp     rax, rcx
0x18001e278  jnz     loc_18001E35C
0x18001e27e  lea     rcx, [rsp+130h+var_E8]; lpPerformanceCount
0x18001e283  mov     qword ptr [rsp+130h+Frequency], r12
0x18001e288  mov     qword ptr [rsp+130h+var_E8], r12
0x18001e28d  call    cs:QueryPerformanceCounter
0x18001e293  lea     rcx, [rsp+130h+Frequency]; lpFrequency
0x18001e298  call    cs:QueryPerformanceFrequency
0x18001e29e  mov     rax, qword ptr [rsp+130h+var_E8]
0x18001e2a3  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x18001e2a7  imul    rax, 0F4240h
0x18001e2ae  mov     dword ptr [rsp+130h+hMem], ebx
0x18001e2b2  cqo
0x18001e2b4  mov     [rbp+57h+var_58], 8
0x18001e2bc  idiv    qword ptr [rsp+130h+Frequency]
0x18001e2c1  mov     [rbp+57h+var_68], 4
0x18001e2c9  mov     [rbp+57h+var_C0], rax
0x18001e2cd  mov     eax, [rsp+130h+var_100]
0x18001e2d1  mov     [rsp+130h+var_FC], eax
0x18001e2d5  lea     rax, [rbp+57h+var_C0]
0x18001e2d9  mov     [rbp+57h+var_60], rax
0x18001e2dd  lea     rax, [rsp+130h+hMem]
0x18001e2e2  mov     [rbp+57h+var_70], rax
0x18001e2e6  lea     rax, [rsp+130h+var_FC]
0x18001e2eb  mov     [rbp+57h+var_80], rax
0x18001e2ef  mov     [rbp+57h+var_78], 4
0x18001e2f7  test    rdi, rdi
0x18001e2fa  jz      short loc_18001E314
0x18001e2fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e300  inc     rax
0x18001e303  cmp     [rdi+rax*2], r12w
0x18001e308  jnz     short loc_18001E300
0x18001e30a  lea     r13d, ds:2[rax*2]
0x18001e312  jmp     short loc_18001E31B
0x18001e314  lea     rdi, LocaleName
0x18001e31b  lea     rax, [rbp+57h+var_B0]
0x18001e31f  mov     [rbp+57h+var_90], rdi
0x18001e323  mov     [rsp+130h+var_108], rax
0x18001e328  lea     rdx, byte_18002C6D3
0x18001e32f  xor     r9d, r9d
0x18001e332  mov     [rsp+130h+var_110], 6
0x18001e33a  xor     r8d, r8d
0x18001e33d  mov     [rbp+57h+var_88], r13d
0x18001e341  lea     rcx, dword_180030048
0x18001e348  mov     [rbp+57h+var_84], r12d
0x18001e34c  call    sub_1800011BC
0x18001e351  jmp     short loc_18001E35C
0x18001e353  mov     rax, qword ptr [rsp+130h+var_E8]
0x18001e358  mov     [r12], rax
0x18001e35c  mov     ecx, ebx
0x18001e35e  call    sub_1800031AC
0x18001e363  mov     rcx, qword ptr [rbp+57h+var_D0+8]
0x18001e367  xor     r12d, r12d
0x18001e36a  test    rcx, rcx
0x18001e36d  jz      short loc_18001E37F
0x18001e36f  mov     rax, [rcx]
0x18001e372  mov     rax, [rax+10h]
0x18001e376  call    j__guard_dispatch_icall
0x18001e37b  mov     qword ptr [rbp+57h+var_D0+8], r12
0x18001e37f  mov     rcx, qword ptr [rbp+57h+var_D0]
0x18001e383  test    rcx, rcx
0x18001e386  jz      short loc_18001E398
0x18001e388  mov     rax, [rcx]
0x18001e38b  mov     rax, [rax+10h]
0x18001e38f  call    j__guard_dispatch_icall
0x18001e394  mov     qword ptr [rbp+57h+var_D0], r12
0x18001e398  test    rsi, rsi
0x18001e39b  jz      short loc_18001E3AC
0x18001e39d  mov     rax, [rsi]
0x18001e3a0  mov     rcx, rsi
0x18001e3a3  mov     rax, [rax+10h]
0x18001e3a7  call    j__guard_dispatch_icall
0x18001e3ac  test    r15, r15
0x18001e3af  jz      short loc_18001E3BA
0x18001e3b1  mov     rcx, r15; hMem
0x18001e3b4  call    cs:__imp_LocalFree
0x18001e3ba  test    r14, r14
0x18001e3bd  jz      short loc_18001E3C8
0x18001e3bf  mov     rcx, r14; hMem
0x18001e3c2  call    cs:__imp_LocalFree
0x18001e3c8  mov     eax, ebx
0x18001e3ca  mov     rcx, [rbp+57h+var_50]
0x18001e3ce  xor     rcx, rsp; StackCookie
0x18001e3d1  call    __security_check_cookie
0x18001e3d6  add     rsp, 0F8h
0x18001e3dd  pop     r15
0x18001e3df  pop     r14
0x18001e3e1  pop     r13
0x18001e3e3  pop     r12
0x18001e3e5  pop     rdi
0x18001e3e6  pop     rsi
0x18001e3e7  pop     rbx
0x18001e3e8  pop     rbp
0x18001e3e9  retn
```
