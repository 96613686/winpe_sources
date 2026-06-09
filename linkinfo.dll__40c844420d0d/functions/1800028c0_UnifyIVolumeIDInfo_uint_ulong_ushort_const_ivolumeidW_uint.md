# UnifyIVolumeIDInfo(uint,ulong,ushort const *,_ivolumeidW * *,uint *)

- ea: `0x1800028c0`
- end: `0x180002aeb`
- name: `?UnifyIVolumeIDInfo@@YAHIKPEBGPEAPEAU_ivolumeidW@@PEAI@Z`
- size: `555`
- prototype: `int(unsigned int, unsigned int, const unsigned __int16 *, struct _ivolumeidW **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800023f0`
- `0x180002500`

## callees

- `0x180001ae0`
- `0x1800028c0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002ab2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180002ab2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180002983`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180002983`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180002961`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180002961`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002927`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002927`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800029ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800029ad`

## pseudocode

```c
__int64 __fastcall UnifyIVolumeIDInfo(int a1, int a2, WCHAR *a3, struct _ivolumeidW **a4, unsigned int *a5)
{
  unsigned int v8; // eax
  __int64 v9; // rbx
  unsigned int v10; // r15d
  int v11; // esi
  unsigned int v12; // ecx
  int v13; // r12d
  __int64 result; // rax
  _DWORD *v15; // rax
  __int64 v16; // r10
  _BYTE *v17; // r9
  __int64 v18; // rcx
  CHAR *v19; // r8
  _BYTE *v20; // rcx
  unsigned __int64 v21; // rax
  CHAR MultiByteStr[272]; // [rsp+50h] [rbp-368h] BYREF
  WCHAR WideCharStr[264]; // [rsp+160h] [rbp-258h] BYREF

  v8 = WideCharToMultiByte(0, 0, a3, -1, MultiByteStr, 260, 0, 0);
  v9 = v8;
  if ( v8 && (v10 = MultiByteToWideChar(0, 0, MultiByteStr, -1, WideCharStr, 260)) != 0 && !lstrcmpW(a3, WideCharStr) )
  {
    v11 = 0;
    v12 = v9 + 16;
    v13 = v9 + 21;
  }
  else
  {
    v11 = 1;
    v10 = lstrlenW(a3) + 1;
    v21 = 2LL * v10;
    if ( v21 > 0xFFFFFFFF )
      return 0;
    v13 = v9 + 21;
    v12 = v21 + ((v9 + 21) & 0xFFFFFFFE);
  }
  *a5 = v12;
  result = (__int64)LocalAlloc(0x40u, v12);
  *a4 = (struct _ivolumeidW *)result;
  if ( result )
  {
    *(_DWORD *)result = *a5;
    *((_DWORD *)*a4 + 1) = a1;
    *((_DWORD *)*a4 + 2) = a2;
    v15 = *a4;
    if ( v11 )
    {
      v15[3] = 20;
      *((_DWORD *)*a4 + 4) = v13 & 0xFFFFFFFE;
      StringCchCopyW((unsigned __int16 *)((char *)*a4 + *((unsigned int *)*a4 + 4)), v10, a3);
    }
    else
    {
      v15[3] = 16;
    }
    v16 = v9;
    v17 = (char *)*a4 + *((unsigned int *)*a4 + 3);
    v18 = 2147483646;
    if ( (unsigned int)(v9 - 1) > 0x7FFFFFFE )
    {
      result = 1;
      if ( (_DWORD)v9 )
        *v17 = 0;
    }
    else
    {
      v19 = MultiByteStr;
      do
      {
        if ( !v18 )
          break;
        if ( !*v19 )
          break;
        *v17++ = *v19++;
        --v18;
        --v16;
      }
      while ( v16 );
      v20 = v17 - 1;
      result = 1;
      if ( v16 )
        v20 = v17;
      *v20 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800028c0  mov     [rsp+arg_0], rbx
0x1800028c5  push    rbp
0x1800028c6  push    rsi
0x1800028c7  push    rdi
0x1800028c8  push    r12
0x1800028ca  push    r13
0x1800028cc  push    r14
0x1800028ce  push    r15
0x1800028d0  sub     rsp, 380h
0x1800028d7  mov     rax, cs:__security_cookie
0x1800028de  xor     rax, rsp
0x1800028e1  mov     [rsp+3B8h+var_48], rax
0x1800028e9  mov     r14, [rsp+3B8h+arg_20]
0x1800028f1  lea     rax, [rsp+3B8h+MultiByteStr]
0x1800028f6  xor     r12d, r12d
0x1800028f9  mov     [rsp+3B8h+var_378], ecx
0x1800028fd  mov     [rsp+3B8h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180002902  mov     rdi, r9
0x180002905  mov     [rsp+3B8h+lpDefaultChar], r12; lpDefaultChar
0x18000290a  mov     r13d, edx
0x18000290d  mov     [rsp+3B8h+cbMultiByte], 104h; cbMultiByte
0x180002915  xor     edx, edx; dwFlags
0x180002917  xor     ecx, ecx; CodePage
0x180002919  mov     [rsp+3B8h+lpMultiByteStr], rax; lpMultiByteStr
0x18000291e  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180002924  mov     rbp, r8
0x180002927  call    cs:__imp_WideCharToMultiByte
0x18000292e  nop     dword ptr [rax+rax+00h]
0x180002933  mov     ebx, eax
0x180002935  test    eax, eax
0x180002937  jz      loc_180002AAA
0x18000293d  lea     rax, [rsp+3B8h+WideCharStr]
0x180002945  mov     [rsp+3B8h+cbMultiByte], 104h; cchWideChar
0x18000294d  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180002953  mov     [rsp+3B8h+lpMultiByteStr], rax; lpWideCharStr
0x180002958  lea     r8, [rsp+3B8h+MultiByteStr]; lpMultiByteStr
0x18000295d  xor     edx, edx; dwFlags
0x18000295f  xor     ecx, ecx; CodePage
0x180002961  call    cs:__imp_MultiByteToWideChar
0x180002968  nop     dword ptr [rax+rax+00h]
0x18000296d  mov     r15d, eax
0x180002970  test    eax, eax
0x180002972  jz      loc_180002AAA
0x180002978  lea     rdx, [rsp+3B8h+WideCharStr]; lpString2
0x180002980  mov     rcx, rbp; lpString1
0x180002983  call    cs:__imp_lstrcmpW
0x18000298a  nop     dword ptr [rax+rax+00h]
0x18000298f  test    eax, eax
0x180002991  jnz     loc_180002AAA
0x180002997  mov     esi, r12d
0x18000299a  lea     ecx, [rbx+10h]
0x18000299d  lea     r12d, [rbx+15h]
0x1800029a1  mov     rdx, r14
0x1800029a4  mov     [rdx], ecx
0x1800029a6  mov     edx, ecx; uBytes
0x1800029a8  mov     ecx, 40h ; '@'; uFlags
0x1800029ad  call    cs:__imp_LocalAlloc
0x1800029b4  nop     dword ptr [rax+rax+00h]
0x1800029b9  mov     [rdi], rax
0x1800029bc  test    rax, rax
0x1800029bf  jz      loc_180002A6E
0x1800029c5  mov     ecx, [r14]
0x1800029c8  mov     [rax], ecx
0x1800029ca  mov     rax, [rdi]
0x1800029cd  mov     ecx, [rsp+3B8h+var_378]
0x1800029d1  mov     [rax+4], ecx
0x1800029d4  mov     rax, [rdi]
0x1800029d7  mov     [rax+8], r13d
0x1800029db  mov     rax, [rdi]
0x1800029de  test    esi, esi
0x1800029e0  jnz     loc_180002A70
0x1800029e6  mov     dword ptr [rax+0Ch], 10h
0x1800029ed  mov     rcx, [rdi]
0x1800029f0  lea     eax, [rbx-1]
0x1800029f3  mov     r10, rbx
0x1800029f6  mov     r9d, [rcx+0Ch]
0x1800029fa  add     r9, rcx
0x1800029fd  mov     ecx, 7FFFFFFEh
0x180002a02  cmp     eax, ecx
0x180002a04  ja      loc_180002A9B
0x180002a0a  lea     r8, [rsp+3B8h+MultiByteStr]
0x180002a0f  nop
0x180002a10  test    rcx, rcx
0x180002a13  jz      short loc_180002A2F
0x180002a15  movzx   edx, byte ptr [r8]
0x180002a19  test    dl, dl
0x180002a1b  jz      short loc_180002A2F
0x180002a1d  mov     [r9], dl
0x180002a20  inc     r8
0x180002a23  inc     r9
0x180002a26  dec     rcx
0x180002a29  sub     r10, 1
0x180002a2d  jnz     short loc_180002A10
0x180002a2f  test    r10, r10
0x180002a32  lea     rcx, [r9-1]
0x180002a36  mov     eax, 1
0x180002a3b  cmovnz  rcx, r9
0x180002a3f  mov     byte ptr [rcx], 0
0x180002a42  mov     rcx, [rsp+3B8h+var_48]
0x180002a4a  xor     rcx, rsp; StackCookie
0x180002a4d  call    __security_check_cookie
0x180002a52  mov     rbx, [rsp+3B8h+arg_0]
0x180002a5a  add     rsp, 380h
0x180002a61  pop     r15
0x180002a63  pop     r14
0x180002a65  pop     r13
0x180002a67  pop     r12
0x180002a69  pop     rdi
0x180002a6a  pop     rsi
0x180002a6b  pop     rbp
0x180002a6c  retn
0x180002a6e  jmp     short loc_180002A42
0x180002a70  mov     dword ptr [rax+0Ch], 14h
0x180002a77  and     r12d, 0FFFFFFFEh
0x180002a7b  mov     rax, [rdi]
0x180002a7e  mov     r8, rbp; unsigned __int16 *
0x180002a81  mov     edx, r15d; unsigned __int64
0x180002a84  mov     [rax+10h], r12d
0x180002a88  mov     rax, [rdi]
0x180002a8b  mov     ecx, [rax+10h]
0x180002a8e  add     rcx, rax; unsigned __int16 *
0x180002a91  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002a96  jmp     loc_1800029ED
0x180002a9b  mov     eax, 1
0x180002aa0  test    ebx, ebx
0x180002aa2  jz      short loc_180002A42
0x180002aa4  mov     byte ptr [r9], 0
0x180002aa8  jmp     short loc_180002A42
0x180002aaa  mov     rcx, rbp; lpString
0x180002aad  mov     esi, 1
0x180002ab2  call    cs:__imp_lstrlenW
0x180002ab9  nop     dword ptr [rax+rax+00h]
0x180002abe  mov     ecx, 0FFFFFFFFh
0x180002ac3  lea     r15d, [rax+1]
0x180002ac7  mov     eax, r15d
0x180002aca  add     rax, rax
0x180002acd  cmp     rax, rcx
0x180002ad0  ja      short loc_180002AE3
0x180002ad2  lea     r12d, [rbx+15h]
0x180002ad6  mov     ecx, r12d
0x180002ad9  and     ecx, 0FFFFFFFEh
0x180002adc  add     ecx, eax
0x180002ade  jmp     loc_1800029A1
0x180002ae3  mov     eax, r12d
0x180002ae6  jmp     loc_180002A42
```
