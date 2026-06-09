# ClipInstallLicense

- ea: `0x1800228b0`
- end: `0x180022cf6`
- name: `ClipInstallLicense`
- size: `1094`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x1800011bc`
- `0x1800017f0`
- `0x180002b3c`
- `0x1800031ac`
- `0x18000717c`
- `0x18001a810`
- `0x1800228b0`
- `0x180023820`
- `0x1800246b4`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b90`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180022c07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180022c07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022905`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022bfd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022905`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022bfd`

## pseudocode

```c
__int64 __fastcall ClipInstallLicense(__int64 a1, unsigned int a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v7; // rcx
  int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // r9d
  DWORD v16; // edx
  const WCHAR *v17; // rsi
  const WCHAR *v18; // rbx
  const WCHAR *v19; // rax
  const WCHAR *v20; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  unsigned int v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  const WCHAR *v27; // [rsp+78h] [rbp-88h] BYREF
  const WCHAR *v28; // [rsp+80h] [rbp-80h] BYREF
  LARGE_INTEGER v29; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER Frequency; // [rsp+90h] [rbp-70h] BYREF
  LONGLONG v31; // [rsp+98h] [rbp-68h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-60h]
  __int128 *v33; // [rsp+A8h] [rbp-58h]
  __int128 v34; // [rsp+B0h] [rbp-50h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-38h] BYREF
  __int16 v37; // [rsp+D0h] [rbp-30h]
  char v38[32]; // [rsp+E0h] [rbp-20h] BYREF
  int *v39; // [rsp+100h] [rbp+0h]
  __int64 v40; // [rsp+108h] [rbp+8h]
  const WCHAR **v41; // [rsp+110h] [rbp+10h]
  __int64 v42; // [rsp+118h] [rbp+18h]
  const WCHAR **v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+128h] [rbp+28h]
  LONGLONG *v45; // [rsp+130h] [rbp+30h]
  __int64 v46; // [rsp+138h] [rbp+38h]
  void *retaddr; // [rsp+188h] [rbp+88h]

  v32 = (__int64)&v34 + 8;
  v24 = a2;
  v33 = &v34;
  v25 = a4;
  v34 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  if ( !a1 || !a3 || !a5 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_21:
    sub_180002B3C(v7);
    goto LABEL_22;
  }
  v9 = sub_18001A810(v32, 1, 4, &v24);
  v8 = v9;
  if ( v9 < 0 )
    sub_180002B3C((unsigned int)v9);
  sub_1800031AC((unsigned int)v8);
  if ( v8 < 0 )
    goto LABEL_20;
  v10 = sub_18001A810(v32, 2, v24, a3);
  v8 = v10;
  if ( v10 < 0 )
    sub_180002B3C((unsigned int)v10);
  sub_1800031AC((unsigned int)v8);
  if ( v8 < 0 )
    goto LABEL_20;
  v11 = sub_18001A810(v32, 3, 4, &v25);
  v8 = v11;
  if ( v11 < 0 )
    sub_180002B3C((unsigned int)v11);
  sub_1800031AC((unsigned int)v8);
  if ( v8 < 0 )
    goto LABEL_20;
  v12 = sub_1800246B4(a1, 0, v32, (__int64)&v34);
  v8 = v12;
  if ( v12 < 0 )
    sub_180002B3C((unsigned int)v12);
  sub_1800031AC((unsigned int)v8);
  if ( v8 < 0 )
    goto LABEL_20;
  v13 = sub_18000717C(v33, 1, 16, a5);
  v8 = v13;
  if ( v13 < 0 )
    sub_180002B3C((unsigned int)v13);
  sub_1800031AC((unsigned int)v8);
  if ( v8 < 0 )
  {
LABEL_20:
    v7 = (unsigned int)v8;
    goto LABEL_21;
  }
LABEL_22:
  if ( dword_180030958 != v8 )
  {
    if ( v8 == -2147024891 )
    {
      v28 = 0;
      v27 = 0;
      sub_180023820(retaddr, v14, &v28, &v27);
      v16 = 1000;
      v17 = v28;
      if ( v24 < 0x3E8 )
        v16 = v24;
      v18 = v27;
      if ( (unsigned int)dword_180030048 > 5
        && (qword_180030058 & 0x400000000000LL) != 0
        && (qword_180030060 & 0x400000000000LL) == qword_180030060 )
      {
        v37 = v16;
        v19 = &LocaleName;
        v36 = a3;
        v20 = v27;
        v29.LowPart = v16;
        if ( !v27 )
          v20 = &LocaleName;
        Frequency.QuadPart = (LONGLONG)v20;
        if ( v28 )
          v19 = v28;
        v31 = (LONGLONG)v19;
        LODWORD(v27) = v25;
        LODWORD(v28) = v24;
        v26 = -2147024891;
        sub_180001008(
          (_DWORD)v20,
          (unsigned int)&word_18002C896,
          qword_180030060,
          v15,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v31,
          (__int64)&Frequency,
          (__int64)&v29,
          (__int64)&v36);
      }
      dword_180030958 = -2147024891;
      if ( v18 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v18 - 2));
        sub_1800031AC(0);
      }
      if ( v17 )
      {
        v22 = GetProcessHeap();
        HeapFree(v22, 0, (LPVOID)(v17 - 2));
        sub_1800031AC(0);
      }
    }
    else if ( v8 < 0 )
    {
      if ( (unsigned int)dword_180030048 > 5
        && (qword_180030058 & 0x400000000000LL) != 0
        && (qword_180030060 & 0x400000000000LL) == qword_180030060 )
      {
        Frequency.QuadPart = 0;
        v29.QuadPart = 0;
        QueryPerformanceCounter(&v29);
        QueryPerformanceFrequency(&Frequency);
        LODWORD(v28) = v8;
        v46 = 8;
        v44 = 4;
        v31 = 1000000 * (v29.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
        LODWORD(v27) = v25;
        v26 = v24;
        v45 = &v31;
        v43 = &v28;
        v41 = &v27;
        v39 = &v26;
        v42 = 4;
        v40 = 4;
        sub_1800011BC(&dword_180030048, byte_18002C849, 0, 0, 6, v38);
      }
      dword_180030958 = v8;
    }
  }
  sub_1800031AC((unsigned int)v8);
  if ( *((_QWORD *)&v34 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v34 + 1) + 16LL))(*((_QWORD *)&v34 + 1));
    *((_QWORD *)&v34 + 1) = 0;
  }
  if ( (_QWORD)v34 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v34 + 16LL))(v34);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800228b0  push    rbp
0x1800228b2  push    rbx
0x1800228b3  push    rsi
0x1800228b4  push    rdi
0x1800228b5  push    r13
0x1800228b7  push    r14
0x1800228b9  lea     rbp, [rsp-58h]
0x1800228be  sub     rsp, 158h
0x1800228c5  mov     rax, cs:__security_cookie
0x1800228cc  xor     rax, rsp
0x1800228cf  mov     [rbp+80h+var_40], rax
0x1800228d3  mov     rbx, [rbp+80h+arg_20]
0x1800228da  lea     rax, [rbp+80h+var_D0+8]
0x1800228de  mov     [rbp+80h+var_E0], rax
0x1800228e2  mov     rsi, rcx
0x1800228e5  lea     rax, [rbp+80h+var_D0]
0x1800228e9  mov     [rsp+180h+var_120], edx
0x1800228ed  xorps   xmm0, xmm0
0x1800228f0  mov     [rbp+80h+var_D8], rax
0x1800228f4  lea     rcx, [rbp+80h+PerformanceCount]; lpPerformanceCount
0x1800228f8  mov     [rsp+180h+var_118], r9d
0x1800228fd  mov     r14, r8
0x180022900  movdqu  [rbp+80h+var_D0], xmm0
0x180022905  call    cs:QueryPerformanceCounter
0x18002290b  mov     r13d, 4
0x180022911  test    rsi, rsi
0x180022914  jnz     short loc_180022922
0x180022916  mov     ecx, 80070057h
0x18002291b  mov     edi, ecx
0x18002291d  jmp     loc_180022A17
0x180022922  test    r14, r14
0x180022925  jz      short loc_180022916
0x180022927  test    rbx, rbx
0x18002292a  jz      short loc_180022916
0x18002292c  mov     rcx, [rbp+80h+var_E0]
0x180022930  lea     r9, [rsp+180h+var_120]
0x180022935  mov     r8d, r13d
0x180022938  mov     edx, 1
0x18002293d  call    sub_18001A810
0x180022942  mov     edi, eax
0x180022944  test    eax, eax
0x180022946  jns     short loc_18002294F
0x180022948  mov     ecx, eax
0x18002294a  call    sub_180002B3C
0x18002294f  mov     ecx, edi
0x180022951  call    sub_1800031AC
0x180022956  test    edi, edi
0x180022958  js      loc_180022A15
0x18002295e  mov     r8d, [rsp+180h+var_120]
0x180022963  mov     r9, r14
0x180022966  mov     rcx, [rbp+80h+var_E0]
0x18002296a  mov     edx, 2
0x18002296f  call    sub_18001A810
0x180022974  mov     edi, eax
0x180022976  test    eax, eax
0x180022978  jns     short loc_180022981
0x18002297a  mov     ecx, eax
0x18002297c  call    sub_180002B3C
0x180022981  mov     ecx, edi
0x180022983  call    sub_1800031AC
0x180022988  test    edi, edi
0x18002298a  js      loc_180022A15
0x180022990  mov     rcx, [rbp+80h+var_E0]
0x180022994  lea     r9, [rsp+180h+var_118]
0x180022999  mov     r8d, r13d
0x18002299c  mov     edx, 3
0x1800229a1  call    sub_18001A810
0x1800229a6  mov     edi, eax
0x1800229a8  test    eax, eax
0x1800229aa  jns     short loc_1800229B3
0x1800229ac  mov     ecx, eax
0x1800229ae  call    sub_180002B3C
0x1800229b3  mov     ecx, edi
0x1800229b5  call    sub_1800031AC
0x1800229ba  test    edi, edi
0x1800229bc  js      short loc_180022A15
0x1800229be  mov     r8, [rbp+80h+var_E0]
0x1800229c2  lea     r9, [rbp+80h+var_D0]
0x1800229c6  xor     edx, edx
0x1800229c8  mov     rcx, rsi
0x1800229cb  call    sub_1800246B4
0x1800229d0  mov     edi, eax
0x1800229d2  test    eax, eax
0x1800229d4  jns     short loc_1800229DD
0x1800229d6  mov     ecx, eax
0x1800229d8  call    sub_180002B3C
0x1800229dd  mov     ecx, edi
0x1800229df  call    sub_1800031AC
0x1800229e4  test    edi, edi
0x1800229e6  js      short loc_180022A15
0x1800229e8  mov     rcx, [rbp+80h+var_D8]
0x1800229ec  mov     edx, 1
0x1800229f1  mov     r9, rbx
0x1800229f4  lea     r8d, [rdx+0Fh]
0x1800229f8  call    sub_18000717C
0x1800229fd  mov     edi, eax
0x1800229ff  test    eax, eax
0x180022a01  jns     short loc_180022A0A
0x180022a03  mov     ecx, eax
0x180022a05  call    sub_180002B3C
0x180022a0a  mov     ecx, edi
0x180022a0c  call    sub_1800031AC
0x180022a11  test    edi, edi
0x180022a13  jns     short loc_180022A1C
0x180022a15  mov     ecx, edi
0x180022a17  call    sub_180002B3C
0x180022a1c  cmp     cs:dword_180030958, edi
0x180022a22  jz      loc_180022C9F
0x180022a28  cmp     edi, 80070005h
0x180022a2e  jnz     loc_180022BA2
0x180022a34  mov     rcx, [rbp+88h]
0x180022a3b  lea     r9, [rsp+180h+var_108]
0x180022a40  lea     r8, [rbp+80h+var_100]
0x180022a44  mov     [rbp+80h+var_100], 0
0x180022a4c  mov     [rsp+180h+var_108], 0
0x180022a55  call    sub_180023820
0x180022a5a  mov     eax, cs:dword_180030048
0x180022a60  mov     edx, 3E8h
0x180022a65  cmp     [rsp+180h+var_120], edx
0x180022a69  mov     rsi, [rbp+80h+var_100]
0x180022a6d  cmovb   edx, [rsp+180h+var_120]
0x180022a72  mov     rbx, [rsp+180h+var_108]
0x180022a77  cmp     eax, 5
0x180022a7a  jbe     loc_180022B4D
0x180022a80  mov     r8, cs:qword_180030060
0x180022a87  mov     rcx, 400000000000h
0x180022a91  mov     rax, cs:qword_180030058
0x180022a98  test    rcx, rax
0x180022a9b  jz      loc_180022B4D
0x180022aa1  mov     rax, r8
0x180022aa4  and     rax, rcx
0x180022aa7  cmp     rax, r8
0x180022aaa  jnz     loc_180022B4D
0x180022ab0  mov     eax, 0FFFFh
0x180022ab5  cmp     edx, eax
0x180022ab7  ja      short loc_180022ABC
0x180022ab9  movzx   eax, dx
0x180022abc  mov     [rbp+80h+var_B0], ax
0x180022ac0  lea     rax, LocaleName
0x180022ac7  mov     [rbp+80h+var_B8], r14
0x180022acb  mov     rcx, rbx
0x180022ace  mov     dword ptr [rbp+80h+var_F8], edx
0x180022ad1  test    rbx, rbx
0x180022ad4  jnz     short loc_180022AD9
0x180022ad6  mov     rcx, rax
0x180022ad9  mov     qword ptr [rbp+80h+Frequency], rcx
0x180022add  test    rsi, rsi
0x180022ae0  jz      short loc_180022AE5
0x180022ae2  mov     rax, rsi
0x180022ae5  mov     [rbp+80h+var_E8], rax
0x180022ae9  lea     rdx, word_18002C896
0x180022af0  mov     eax, [rsp+180h+var_118]
0x180022af4  mov     dword ptr [rsp+180h+var_108], eax
0x180022af8  mov     eax, [rsp+180h+var_120]
0x180022afc  mov     dword ptr [rbp+80h+var_100], eax
0x180022aff  lea     rax, [rbp+80h+var_B8]
0x180022b03  mov     [rsp+180h+var_130], rax
0x180022b08  lea     rax, [rbp+80h+var_F8]
0x180022b0c  mov     [rsp+180h+var_138], rax
0x180022b11  lea     rax, [rbp+80h+Frequency]
0x180022b15  mov     [rsp+180h+var_140], rax
0x180022b1a  lea     rax, [rbp+80h+var_E8]
0x180022b1e  mov     [rsp+180h+var_148], rax
0x180022b23  lea     rax, [rsp+180h+var_110]
0x180022b28  mov     [rsp+180h+var_150], rax
0x180022b2d  lea     rax, [rsp+180h+var_108]
0x180022b32  mov     [rsp+180h+var_158], rax
0x180022b37  lea     rax, [rbp+80h+var_100]
0x180022b3b  mov     [rsp+180h+var_160], rax
0x180022b40  mov     [rsp+180h+var_110], 80070005h
0x180022b48  call    sub_180001008
0x180022b4d  mov     cs:dword_180030958, 80070005h
0x180022b57  test    rbx, rbx
0x180022b5a  jz      short loc_180022B78
0x180022b5c  call    cs:GetProcessHeap
0x180022b62  lea     r8, [rbx-4]; lpMem
0x180022b66  xor     edx, edx; dwFlags
0x180022b68  mov     rcx, rax; hHeap
0x180022b6b  call    cs:HeapFree
0x180022b71  xor     ecx, ecx
0x180022b73  call    sub_1800031AC
0x180022b78  test    rsi, rsi
0x180022b7b  jz      loc_180022C9F
0x180022b81  call    cs:GetProcessHeap
0x180022b87  lea     r8, [rsi-4]; lpMem
0x180022b8b  xor     edx, edx; dwFlags
0x180022b8d  mov     rcx, rax; hHeap
0x180022b90  call    cs:HeapFree
0x180022b96  xor     ecx, ecx
0x180022b98  call    sub_1800031AC
0x180022b9d  jmp     loc_180022C9F
0x180022ba2  test    edi, edi
0x180022ba4  jns     loc_180022C9F
0x180022baa  mov     eax, cs:dword_180030048
0x180022bb0  cmp     eax, 5
0x180022bb3  jbe     loc_180022C99
0x180022bb9  mov     rdx, cs:qword_180030060
0x180022bc0  mov     rcx, 400000000000h
0x180022bca  mov     rax, cs:qword_180030058
0x180022bd1  test    rcx, rax
0x180022bd4  jz      loc_180022C99
0x180022bda  mov     rax, rdx
0x180022bdd  and     rax, rcx
0x180022be0  cmp     rax, rdx
0x180022be3  jnz     loc_180022C99
0x180022be9  lea     rcx, [rbp+80h+var_F8]; lpPerformanceCount
0x180022bed  mov     qword ptr [rbp+80h+Frequency], 0
0x180022bf5  mov     qword ptr [rbp+80h+var_F8], 0
0x180022bfd  call    cs:QueryPerformanceCounter
0x180022c03  lea     rcx, [rbp+80h+Frequency]; lpFrequency
0x180022c07  call    cs:QueryPerformanceFrequency
0x180022c0d  mov     rax, qword ptr [rbp+80h+var_F8]
0x180022c11  lea     rcx, dword_180030048
0x180022c18  sub     rax, qword ptr [rbp+80h+PerformanceCount]
0x180022c1c  xor     r9d, r9d
0x180022c1f  imul    rax, 0F4240h
0x180022c26  xor     r8d, r8d
0x180022c29  mov     dword ptr [rbp+80h+var_100], edi
0x180022c2c  cqo
0x180022c2e  mov     [rbp+80h+var_48], 8
0x180022c36  idiv    qword ptr [rbp+80h+Frequency]
0x180022c3a  lea     rdx, byte_18002C849
0x180022c41  mov     [rbp+80h+var_58], r13
0x180022c45  mov     [rbp+80h+var_E8], rax
0x180022c49  mov     eax, [rsp+180h+var_118]
0x180022c4d  mov     dword ptr [rsp+180h+var_108], eax
0x180022c51  mov     eax, [rsp+180h+var_120]
0x180022c55  mov     [rsp+180h+var_110], eax
0x180022c59  lea     rax, [rbp+80h+var_E8]
0x180022c5d  mov     [rbp+80h+var_50], rax
0x180022c61  lea     rax, [rbp+80h+var_100]
0x180022c65  mov     [rbp+80h+var_60], rax
0x180022c69  lea     rax, [rsp+180h+var_108]
0x180022c6e  mov     [rbp+80h+var_70], rax
0x180022c72  lea     rax, [rsp+180h+var_110]
0x180022c77  mov     [rbp+80h+var_80], rax
0x180022c7b  lea     rax, [rbp+80h+var_A0]
0x180022c7f  mov     [rsp+180h+var_158], rax
0x180022c84  mov     dword ptr [rsp+180h+var_160], 6
0x180022c8c  mov     [rbp+80h+var_68], r13
0x180022c90  mov     [rbp+80h+var_78], r13
0x180022c94  call    sub_1800011BC
0x180022c99  mov     cs:dword_180030958, edi
0x180022c9f  mov     ecx, edi
0x180022ca1  call    sub_1800031AC
0x180022ca6  mov     rcx, qword ptr [rbp+80h+var_D0+8]
0x180022caa  test    rcx, rcx
0x180022cad  jz      short loc_180022CC3
0x180022caf  mov     rax, [rcx]
0x180022cb2  mov     rax, [rax+10h]
0x180022cb6  call    j__guard_dispatch_icall
0x180022cbb  mov     qword ptr [rbp+80h+var_D0+8], 0
0x180022cc3  mov     rcx, qword ptr [rbp+80h+var_D0]
0x180022cc7  test    rcx, rcx
0x180022cca  jz      short loc_180022CD8
0x180022ccc  mov     rdx, [rcx]
0x180022ccf  mov     rax, [rdx+10h]
0x180022cd3  call    j__guard_dispatch_icall
0x180022cd8  mov     eax, edi
0x180022cda  mov     rcx, [rbp+80h+var_40]
0x180022cde  xor     rcx, rsp; StackCookie
0x180022ce1  call    __security_check_cookie
0x180022ce6  add     rsp, 158h
0x180022ced  pop     r14
0x180022cef  pop     r13
0x180022cf1  pop     rdi
0x180022cf2  pop     rsi
0x180022cf3  pop     rbx
0x180022cf4  pop     rbp
0x180022cf5  retn
```
