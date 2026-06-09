# MyNewAbstractW

- ea: `0x1800178f8`
- end: `0x180017ceb`
- name: `MyNewAbstractW`
- size: `1011`
- prototype: `__int64 __fastcall(_DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1800178c0`
- `0x18001da5c`

## callees

- `0x1800178f8`
- `0x180017cf4`
- `0x180017e74`
- `0x180017efc`
- `0x180017f80`
- `0x18003cff6`
- `0x18003d040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179df`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800179c8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800179c8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180017cc0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180017cc0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017cae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180017cae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180017ca5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180017cb7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180017ca5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180017cb7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800179d1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800179d1`

## pseudocode

```c
__int64 __fastcall MyNewAbstractW(_DWORD *a1, _QWORD *a2)
{
  HGLOBAL v4; // rax
  char *v5; // rax
  char *v6; // rbx
  DWORD LastError; // edi
  int v8; // r8d
  __int64 v9; // r10
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  __int64 v12; // r10
  unsigned int v13; // ecx
  __int64 result; // rax
  HGLOBAL v15; // rax
  HGLOBAL v16; // rax
  _DWORD v17[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+68h] [rbp-98h]
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+78h] [rbp-88h]
  __m128i si128; // [rsp+80h] [rbp-80h] BYREF
  double v25; // [rsp+90h] [rbp-70h]
  char v26; // [rsp+98h] [rbp-68h] BYREF
  char v27[31]; // [rsp+99h] [rbp-67h] BYREF
  char v28[56]; // [rsp+B8h] [rbp-48h] BYREF

  strcpy(v27, "LogColorSpProfile      ");
  v26 = 24;
  strcpy(v28, "0©1996 by Heidelberger Druckmaschinen AG  U.J.K.");
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v22 = 0;
  v25 = DOUBLE_0_8249;
  v23 = 0;
  v17[0] = 63189;
  v17[1] = 0x10000;
  v17[2] = 54060;
  v4 = GlobalAlloc(0x42u, 0x21Au);
  v5 = (char *)GlobalLock(v4);
  v6 = v5;
  if ( v5 )
  {
    switch ( a1[4] )
    {
      case 1:
        v8 = 2;
        break;
      case 2:
        v8 = 1;
        break;
      case 3:
        v8 = 3;
        break;
      default:
        v8 = 0;
        break;
    }
    LastError = MyAdd_NL_Header(538, (_DWORD)v5, v8, 1935896178, 1380401696, 1482250784);
    if ( !LastError )
    {
      *((_DWORD *)v6 + 32) = 150994944;
      *((_DWORD *)v6 + 33) = 1668506980;
      *((_DWORD *)v6 + 34) = -268435456;
      *((_DWORD *)v6 + 35) = 1912602624;
      LastError = MyAdd_NL_DescriptionTag(v6 + 240, &v26);
      if ( !LastError )
      {
        *((_DWORD *)v6 + 36) = 1953526903;
        *((_DWORD *)v6 + 37) = 1644232704;
        *((_DWORD *)v6 + 38) = 335544320;
        MyAdd_NL_ColorantTag(v6 + 354, v17);
        LastError = NormalizeColor(
                      (int)a1 + 20,
                      (int)a1 + 32,
                      (int)a1 + 44,
                      (unsigned int)&si128,
                      (__int64)&v18,
                      (__int64)&v20,
                      (__int64)&v22);
        if ( !LastError )
        {
          *((_DWORD *)v6 + 39) = 1515804786;
          *((_DWORD *)v6 + 40) = 1979777024;
          *((_DWORD *)v6 + 41) = 335544320;
          MyAdd_NL_ColorantTag(v6 + 374, &v18);
          *((_DWORD *)v6 + 42) = 1515804775;
          *((_DWORD *)v6 + 43) = -1979645952;
          *((_DWORD *)v6 + 44) = 335544320;
          MyAdd_NL_ColorantTag(v9 + 20, &v20);
          *((_DWORD *)v6 + 45) = 1515804770;
          *((_DWORD *)v6 + 46) = -1644101632;
          *((_DWORD *)v6 + 47) = 335544320;
          MyAdd_NL_ColorantTag(v6 + 414, &v22);
          *((_DWORD *)v6 + 48) = 1129469042;
          *((_DWORD *)v6 + 49) = -1308557312;
          *((_DWORD *)v6 + 50) = 0x10000000;
          v10 = a1[14];
          *(_DWORD *)(v6 + 442) = 0x1000000;
          *(_QWORD *)(v6 + 434) = 1987212643;
          *((_WORD *)v6 + 223) = ((unsigned __int16)(v10 >> 8) >> 8) | (BYTE1(v10) << 8);
          *((_DWORD *)v6 + 51) = 1129469031;
          *((_DWORD *)v6 + 52) = -1040121856;
          *((_DWORD *)v6 + 53) = 0x10000000;
          v11 = a1[15];
          *(_DWORD *)(v12 + 84) = 0x1000000;
          *(_QWORD *)(v12 + 76) = 1987212643;
          *(_WORD *)(v12 + 88) = ((unsigned __int16)(v11 >> 8) >> 8) | (BYTE1(v11) << 8);
          *((_DWORD *)v6 + 54) = 1129469026;
          *((_DWORD *)v6 + 55) = -771686400;
          *((_DWORD *)v6 + 56) = 0x10000000;
          v13 = a1[16];
          *(_DWORD *)(v6 + 474) = 0x1000000;
          *(_QWORD *)(v6 + 466) = 1987212643;
          *((_WORD *)v6 + 239) = ((unsigned __int16)(v13 >> 8) >> 8) | (BYTE1(v13) << 8);
          *((_DWORD *)v6 + 57) = 1953656931;
          *((_DWORD *)v6 + 58) = -503250944;
          *((_DWORD *)v6 + 59) = 939524096;
          *(_QWORD *)(v6 + 482) = 1954047348;
          v28[48] = 0;
          memcpy_0(v6 + 490, &v28[1], (unsigned __int8)v28[0]);
          result = 0;
          *a2 = v6;
          return result;
        }
      }
    }
    v15 = GlobalHandle(v6);
    GlobalUnlock(v15);
    v16 = GlobalHandle(v6);
    GlobalFree(v16);
  }
  else
  {
    LastError = GetLastError();
  }
  *a2 = 0;
  return LastError;
}

```

## disassembly

```asm
0x1800178f8  push    rbp
0x1800178fa  push    rbx
0x1800178fb  push    rsi
0x1800178fc  push    rdi
0x1800178fd  push    r14
0x1800178ff  push    r15
0x180017901  lea     rbp, [rsp-8]
0x180017906  sub     rsp, 108h
0x18001790d  mov     rax, cs:__security_cookie
0x180017914  xor     rax, rsp
0x180017917  mov     [rbp+30h+var_40], rax
0x18001791b  movups  xmm0, cs:xmmword_18003F749
0x180017922  mov     rax, 622036393931A9C2h
0x18001792c  mov     r15, rdx
0x18001792f  movsd   xmm1, cs:qword_18003F759
0x180017937  mov     rsi, rcx
0x18001793a  movups  xmmword ptr [rbp+30h+var_97], xmm0
0x18001793e  mov     qword ptr [rbp+30h+var_78+1], rax
0x180017942  xor     eax, eax
0x180017944  movups  xmm0, xmmword ptr cs:a01996ByHeidelb+9; "y Heidelberger Druckmaschinen AG  U.J.K"...
0x18001794b  mov     edi, 21Ah
0x180017950  mov     [rbp+30h+var_98], 18h
0x180017954  movsd   qword ptr [rbp+30h+var_97+10h], xmm1
0x180017959  mov     edx, edi; dwBytes
0x18001795b  movups  xmm1, xmmword ptr cs:a01996ByHeidelb+19h; "ruckmaschinen AG  U.J.K."
0x180017962  lea     ecx, [rax+42h]; uFlags
0x180017965  mov     [rbp+30h+var_78], 30h ; '0'
0x180017969  movups  xmmword ptr [rbp+30h+var_78+9], xmm0
0x18001796d  mov     [rsp+130h+var_E0], rax
0x180017972  movups  xmm0, xmmword ptr cs:a01996ByHeidelb+22h; "inen AG  U.J.K."
0x180017979  mov     [rsp+130h+var_D8], eax
0x18001797d  movups  xmmword ptr [rbp+30h+var_78+19h], xmm1
0x180017981  mov     [rsp+130h+var_D0], rax
0x180017986  movups  xmmword ptr [rbp+30h+var_78+22h], xmm0
0x18001798a  mov     [rsp+130h+var_C8], eax
0x18001798e  movdqa  xmm0, cs:__xmm@3ff00000000000003feedab9f559b3d0
0x180017996  movups  [rbp+30h+var_B0], xmm0
0x18001799a  mov     [rsp+130h+var_C0], rax
0x18001799f  movsd   xmm0, cs:__real@3fea6594af4f0d84
0x1800179a7  movsd   [rbp+30h+var_A0], xmm0
0x1800179ac  mov     [rsp+130h+var_B8], eax
0x1800179b0  mov     [rsp+130h+var_F0], 0F6D5h
0x1800179b8  mov     [rsp+130h+var_EC], 10000h
0x1800179c0  mov     [rsp+130h+var_E8], 0D32Ch
0x1800179c8  call    cs:__imp_GlobalAlloc
0x1800179ce  mov     rcx, rax; hMem
0x1800179d1  call    cs:__imp_GlobalLock
0x1800179d7  mov     rbx, rax
0x1800179da  test    rax, rax
0x1800179dd  jnz     short loc_1800179EC
0x1800179df  call    cs:__imp_GetLastError
0x1800179e5  mov     edi, eax
0x1800179e7  jmp     loc_180017CC6
0x1800179ec  mov     ecx, [rsi+10h]
0x1800179ef  sub     ecx, 1
0x1800179f2  jz      short loc_180017A13
0x1800179f4  sub     ecx, 1
0x1800179f7  jz      short loc_180017A0B
0x1800179f9  cmp     ecx, 1
0x1800179fc  jz      short loc_180017A03
0x1800179fe  xor     r8d, r8d
0x180017a01  jmp     short loc_180017A19
0x180017a03  mov     r8d, 3
0x180017a09  jmp     short loc_180017A19
0x180017a0b  mov     r8d, 1
0x180017a11  jmp     short loc_180017A19
0x180017a13  mov     r8d, 2
0x180017a19  mov     dword ptr [rsp+130h+var_108], 58595A20h
0x180017a21  mov     r9d, 73636E72h
0x180017a27  mov     rdx, rbx
0x180017a2a  mov     dword ptr [rsp+130h+var_110], 52474220h
0x180017a32  mov     ecx, edi
0x180017a34  call    MyAdd_NL_Header
0x180017a39  mov     edi, eax
0x180017a3b  test    eax, eax
0x180017a3d  jnz     loc_180017CA2
0x180017a43  mov     dword ptr [rbx+80h], 9000000h
0x180017a4d  lea     rcx, [rbx+0F0h]
0x180017a54  mov     dword ptr [rbx+84h], 63736564h
0x180017a5e  lea     rdx, [rbp+30h+var_98]
0x180017a62  mov     dword ptr [rbx+88h], 0F0000000h
0x180017a6c  mov     dword ptr [rbx+8Ch], 72000000h
0x180017a76  call    MyAdd_NL_DescriptionTag
0x180017a7b  mov     edi, eax
0x180017a7d  test    eax, eax
0x180017a7f  jnz     loc_180017CA2
0x180017a85  mov     dword ptr [rbx+90h], 74707477h
0x180017a8f  lea     r14, [rbx+162h]
0x180017a96  mov     dword ptr [rbx+94h], 62010000h
0x180017aa0  lea     rdx, [rsp+130h+var_F0]
0x180017aa5  mov     rcx, r14
0x180017aa8  mov     dword ptr [rbx+98h], 14000000h
0x180017ab2  call    MyAdd_NL_ColorantTag
0x180017ab7  lea     rax, [rsp+130h+var_C0]
0x180017abc  mov     [rsp+130h+var_100], rax
0x180017ac1  lea     r8, [rsi+2Ch]
0x180017ac5  lea     rax, [rsp+130h+var_D0]
0x180017aca  mov     [rsp+130h+var_108], rax
0x180017acf  lea     rdx, [rsi+20h]
0x180017ad3  lea     rax, [rsp+130h+var_E0]
0x180017ad8  lea     rcx, [rsi+14h]
0x180017adc  mov     [rsp+130h+var_110], rax
0x180017ae1  lea     r9, [rbp+30h+var_B0]
0x180017ae5  call    NormalizeColor
0x180017aea  mov     edi, eax
0x180017aec  test    eax, eax
0x180017aee  jnz     loc_180017CA2
0x180017af4  mov     dword ptr [rbx+9Ch], 5A595872h
0x180017afe  lea     r10, [rbx+176h]
0x180017b05  mov     dword ptr [rbx+0A0h], 76010000h
0x180017b0f  lea     rdx, [rsp+130h+var_E0]
0x180017b14  mov     rcx, r10
0x180017b17  mov     dword ptr [rbx+0A4h], 14000000h
0x180017b21  call    MyAdd_NL_ColorantTag
0x180017b26  mov     dword ptr [rbx+0A8h], 5A595867h
0x180017b30  lea     rcx, [r10+14h]
0x180017b34  mov     dword ptr [rbx+0ACh], 8A010000h
0x180017b3e  lea     rdx, [rsp+130h+var_D0]
0x180017b43  mov     dword ptr [rbx+0B0h], 14000000h
0x180017b4d  call    MyAdd_NL_ColorantTag
0x180017b52  mov     dword ptr [rbx+0B4h], 5A595862h
0x180017b5c  lea     rcx, [rbx+19Eh]
0x180017b63  mov     dword ptr [rbx+0B8h], 9E010000h
0x180017b6d  lea     rdx, [rsp+130h+var_C0]
0x180017b72  mov     dword ptr [rbx+0BCh], 14000000h
0x180017b7c  call    MyAdd_NL_ColorantTag
0x180017b81  mov     dword ptr [rbx+0C0h], 43525472h
0x180017b8b  mov     r9d, 10000000h
0x180017b91  mov     dword ptr [rbx+0C4h], 0B2010000h
0x180017b9b  mov     edx, 1000000h
0x180017ba0  mov     [rbx+0C8h], r9d
0x180017ba7  mov     ecx, [rsi+38h]
0x180017baa  mov     [r14+58h], edx
0x180017bae  mov     qword ptr [r14+50h], 76727563h
0x180017bb6  shr     ecx, 8
0x180017bb9  movzx   eax, cl
0x180017bbc  shl     ax, 8
0x180017bc0  shr     cx, 8
0x180017bc4  or      ax, cx
0x180017bc7  mov     [r14+5Ch], ax
0x180017bcc  mov     dword ptr [rbx+0CCh], 43525467h
0x180017bd6  mov     dword ptr [rbx+0D0h], 0C2010000h
0x180017be0  mov     [rbx+0D4h], r9d
0x180017be7  mov     ecx, [rsi+3Ch]
0x180017bea  mov     [r10+54h], edx
0x180017bee  mov     qword ptr [r10+4Ch], 76727563h
0x180017bf6  shr     ecx, 8
0x180017bf9  movzx   eax, cl
0x180017bfc  shl     ax, 8
0x180017c00  shr     cx, 8
0x180017c04  or      ax, cx
0x180017c07  mov     [r10+58h], ax
0x180017c0c  mov     dword ptr [rbx+0D8h], 43525462h
0x180017c16  mov     dword ptr [rbx+0DCh], 0D2010000h
0x180017c20  mov     [rbx+0E0h], r9d
0x180017c27  mov     ecx, [rsi+40h]
0x180017c2a  mov     [rbx+1DAh], edx
0x180017c30  lea     rdx, [rbp+30h+var_78+1]; Src
0x180017c34  mov     qword ptr [rbx+1D2h], 76727563h
0x180017c3f  shr     ecx, 8
0x180017c42  movzx   eax, cl
0x180017c45  shl     ax, 8
0x180017c49  shr     cx, 8
0x180017c4d  or      ax, cx
0x180017c50  lea     rcx, [r14+88h]; void *
0x180017c57  mov     [rbx+1DEh], ax
0x180017c5e  mov     al, 30h ; '0'
0x180017c60  mov     dword ptr [rbx+0E4h], 74727063h
0x180017c6a  mov     dword ptr [rbx+0E8h], 0E2010000h
0x180017c74  mov     dword ptr [rbx+0ECh], 38000000h
0x180017c7e  movzx   eax, al
0x180017c81  mov     qword ptr [r14+80h], 74786574h
0x180017c8c  mov     [rbp+rax+30h+var_78], dil
0x180017c91  movzx   r8d, [rbp+30h+var_78]; Size
0x180017c96  call    memcpy_0
0x180017c9b  xor     eax, eax
0x180017c9d  mov     [r15], rbx
0x180017ca0  jmp     short loc_180017CCF
0x180017ca2  mov     rcx, rbx; pMem
0x180017ca5  call    cs:__imp_GlobalHandle
0x180017cab  mov     rcx, rax; hMem
0x180017cae  call    cs:__imp_GlobalUnlock
0x180017cb4  mov     rcx, rbx; pMem
0x180017cb7  call    cs:__imp_GlobalHandle
0x180017cbd  mov     rcx, rax; hMem
0x180017cc0  call    cs:__imp_GlobalFree
0x180017cc6  mov     qword ptr [r15], 0
0x180017ccd  mov     eax, edi
0x180017ccf  mov     rcx, [rbp+30h+var_40]
0x180017cd3  xor     rcx, rsp; StackCookie
0x180017cd6  call    __security_check_cookie
0x180017cdb  add     rsp, 108h
0x180017ce2  pop     r15
0x180017ce4  pop     r14
0x180017ce6  pop     rdi
0x180017ce7  pop     rsi
0x180017ce8  pop     rbx
0x180017ce9  pop     rbp
0x180017cea  retn
```
