# DoUnlockWithKey(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180007b00`
- end: `0x180007d9a`
- name: `?DoUnlockWithKey@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001bb0`
- `0x180002774`
- `0x180007b00`
- `0x18000cf64`
- `0x18000d248`
- `0x18000d358`
- `0x18000d66c`

## import_xrefs

- `KERNEL32!HeapSize` at `0x180007bf2`
- `KERNEL32!HeapSize` at `0x180007d21`
- `KERNEL32!HeapSize` at `0x180007bf2`
- `KERNEL32!HeapSize` at `0x180007d21`
- `KERNEL32!HeapFree` at `0x180007c20`
- `KERNEL32!HeapFree` at `0x180007d4f`
- `KERNEL32!HeapFree` at `0x180007d68`
- `KERNEL32!HeapFree` at `0x180007c20`
- `KERNEL32!HeapFree` at `0x180007d4f`
- `KERNEL32!HeapFree` at `0x180007d68`
- `KERNEL32!GetProcessHeap` at `0x180007be4`
- `KERNEL32!GetProcessHeap` at `0x180007c12`
- `KERNEL32!GetProcessHeap` at `0x180007d13`
- `KERNEL32!GetProcessHeap` at `0x180007d41`
- `KERNEL32!GetProcessHeap` at `0x180007d5a`
- `KERNEL32!GetProcessHeap` at `0x180007be4`
- `KERNEL32!GetProcessHeap` at `0x180007c12`
- `KERNEL32!GetProcessHeap` at `0x180007d13`
- `KERNEL32!GetProcessHeap` at `0x180007d41`
- `KERNEL32!GetProcessHeap` at `0x180007d5a`
- `FVEAPI!FveUnlockVolumeWithAccessMode` at `0x180007cb3`
- `FVEAPI!FveUnlockVolumeWithAccessMode` at `0x180007cb3`
- `FVEAPI!FveCloseVolume` at `0x180007bd0`
- `FVEAPI!FveCloseVolume` at `0x180007cff`
- `FVEAPI!FveCloseVolume` at `0x180007bd0`
- `FVEAPI!FveCloseVolume` at `0x180007cff`
- `FVEAPI!FveOpenVolumeW` at `0x180007c95`
- `FVEAPI!FveOpenVolumeW` at `0x180007c95`

## pseudocode

```c
__int64 __fastcall DoUnlockWithKey(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  void *v4; // rdi
  VARIANTARG *rgvarg; // rax
  char *v6; // rsi
  LONGLONG llVal; // r12
  int AuthMethodGuids; // eax
  int v9; // ebx
  char v10; // r13
  unsigned int i; // r14d
  HANDLE ProcessHeap; // rax
  SIZE_T v13; // rax
  _BYTE *j; // rcx
  HANDLE v15; // rax
  int v16; // eax
  HANDLE v17; // rax
  SIZE_T v18; // rax
  _BYTE *k; // rcx
  HANDLE v20; // rax
  HANDLE v21; // rax
  _BYTE v23[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  void *v26; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  LONGLONG v28; // [rsp+48h] [rbp-B8h]
  LONGLONG v29; // [rsp+50h] [rbp-B0h]
  _BYTE v30[528]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  v26 = 0;
  memset_0(v30, 0, 0x208u);
  rgvarg = a1->rgvarg;
  v6 = 0;
  v24 = -1;
  lpMem = 0;
  v25 = 0;
  llVal = rgvarg->llVal;
  v23[0] = 0;
  if ( !llVal || (v28 = rgvarg[1].llVal) == 0 )
  {
    v9 = -2147467261;
    goto LABEL_29;
  }
  v29 = rgvarg[2].llVal;
  AuthMethodGuids = GetAuthMethodGuids(llVal, &lpMem, &v25);
  v6 = (char *)lpMem;
  v9 = AuthMethodGuids;
  if ( AuthMethodGuids < 0 )
    goto LABEL_29;
  v10 = 0;
  for ( i = 0; i < v25; ++i )
  {
    if ( v24 != -1 )
    {
      FveCloseVolume();
      v24 = -1;
    }
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      v13 = HeapSize(ProcessHeap, 0, v4);
      if ( v13 != -1 )
      {
        for ( j = v4; v13; --v13 )
          *j++ = 0;
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v4);
      }
      v4 = 0;
      v26 = 0;
    }
    if ( (int)UsesProtector(llVal, &v6[16 * i], 0x40000, v23) >= 0
      && v23[0]
      && (int)GetKeyFilename(llVal, &v6[16 * i], v28, v30) >= 0 )
    {
      if ( (int)GetKeyFromFile(v30, &v26) >= 0 )
      {
        v16 = FveOpenVolumeW(llVal, 0, &v24);
        v4 = v26;
        v9 = v16;
        if ( v16 < 0 )
          continue;
        v9 = FveUnlockVolumeWithAccessMode(v24, v26, v29);
        if ( v9 >= 0 )
        {
          v10 = 1;
          break;
        }
      }
      else
      {
        v4 = v26;
      }
    }
    v9 = 0;
  }
  if ( v9 >= 0 )
  {
    a2->vt = 19;
    if ( v10 )
      a2->lVal = 0;
    else
      a2->lVal = -2147024894;
  }
LABEL_29:
  if ( v24 != -1 )
  {
    FveCloseVolume();
    v24 = -1;
  }
  if ( v4 )
  {
    v17 = GetProcessHeap();
    v18 = HeapSize(v17, 0, v4);
    if ( v18 != -1 )
    {
      for ( k = v4; v18; --v18 )
        *k++ = 0;
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v4);
    }
  }
  if ( v6 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v6);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007b00  mov     [rsp-8+arg_10], rbx
0x180007b05  push    rbp
0x180007b06  push    rsi
0x180007b07  push    rdi
0x180007b08  push    r12
0x180007b0a  push    r13
0x180007b0c  push    r14
0x180007b0e  push    r15
0x180007b10  lea     rbp, [rsp-180h]
0x180007b18  sub     rsp, 280h
0x180007b1f  mov     rax, cs:__security_cookie
0x180007b26  xor     rax, rsp
0x180007b29  mov     [rbp+1B0h+var_40], rax
0x180007b30  mov     r15, rdx
0x180007b33  mov     rbx, rcx
0x180007b36  xor     edi, edi
0x180007b38  lea     rcx, [rsp+2B0h+var_250]; void *
0x180007b3d  xor     edx, edx; Val
0x180007b3f  mov     [rsp+2B0h+var_278], rdi
0x180007b44  mov     r8d, 208h; Size
0x180007b4a  call    memset_0
0x180007b4f  mov     rax, [rbx]
0x180007b52  xor     esi, esi
0x180007b54  mov     [rsp+2B0h+var_288], 0FFFFFFFFFFFFFFFFh
0x180007b5d  mov     [rsp+2B0h+lpMem], rsi
0x180007b62  mov     [rsp+2B0h+var_280], esi
0x180007b66  mov     r12, [rax+8]
0x180007b6a  mov     [rsp+2B0h+var_290], sil
0x180007b6f  test    r12, r12
0x180007b72  jz      loc_180007CEF
0x180007b78  mov     rcx, [rax+20h]
0x180007b7c  mov     [rsp+2B0h+var_268], rcx
0x180007b81  test    rcx, rcx
0x180007b84  jz      loc_180007CEF
0x180007b8a  mov     rax, [rax+38h]
0x180007b8e  lea     r8, [rsp+2B0h+var_280]
0x180007b93  lea     rdx, [rsp+2B0h+lpMem]
0x180007b98  mov     [rsp+2B0h+var_260], rax
0x180007b9d  mov     rcx, r12
0x180007ba0  call    _GetAuthMethodGuids
0x180007ba5  mov     rsi, [rsp+2B0h+lpMem]
0x180007baa  mov     ebx, eax
0x180007bac  test    eax, eax
0x180007bae  js      loc_180007CF4
0x180007bb4  xor     r13b, r13b
0x180007bb7  xor     r14d, r14d
0x180007bba  cmp     r14d, [rsp+2B0h+var_280]
0x180007bbf  jnb     loc_180007CCC
0x180007bc5  mov     rcx, [rsp+2B0h+var_288]
0x180007bca  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007bce  jz      short loc_180007BDF
0x180007bd0  call    cs:__imp_FveCloseVolume
0x180007bd6  mov     [rsp+2B0h+var_288], 0FFFFFFFFFFFFFFFFh
0x180007bdf  test    rdi, rdi
0x180007be2  jz      short loc_180007C2D
0x180007be4  call    cs:__imp_GetProcessHeap
0x180007bea  mov     r8, rdi; lpMem
0x180007bed  xor     edx, edx; dwFlags
0x180007bef  mov     rcx, rax; hHeap
0x180007bf2  call    cs:__imp_HeapSize
0x180007bf8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007bfc  jz      short loc_180007C26
0x180007bfe  mov     rcx, rdi
0x180007c01  test    rax, rax
0x180007c04  jz      short loc_180007C12
0x180007c06  mov     [rcx], r13b
0x180007c09  inc     rcx
0x180007c0c  sub     rax, 1
0x180007c10  jnz     short loc_180007C06
0x180007c12  call    cs:__imp_GetProcessHeap
0x180007c18  mov     r8, rdi; lpMem
0x180007c1b  xor     edx, edx; dwFlags
0x180007c1d  mov     rcx, rax; hHeap
0x180007c20  call    cs:__imp_HeapFree
0x180007c26  xor     edi, edi
0x180007c28  mov     [rsp+2B0h+var_278], rdi
0x180007c2d  mov     ebx, r14d
0x180007c30  lea     r9, [rsp+2B0h+var_290]
0x180007c35  shl     rbx, 4
0x180007c39  mov     r8d, 40000h
0x180007c3f  add     rbx, rsi
0x180007c42  mov     rcx, r12
0x180007c45  mov     rdx, rbx
0x180007c48  call    _UsesProtector
0x180007c4d  test    eax, eax
0x180007c4f  js      short loc_180007CBF
0x180007c51  cmp     [rsp+2B0h+var_290], r13b
0x180007c56  jz      short loc_180007CBF
0x180007c58  mov     r8, [rsp+2B0h+var_268]
0x180007c5d  lea     r9, [rsp+2B0h+var_250]
0x180007c62  mov     rdx, rbx
0x180007c65  mov     rcx, r12
0x180007c68  call    _GetKeyFilename
0x180007c6d  test    eax, eax
0x180007c6f  js      short loc_180007CBF
0x180007c71  lea     rdx, [rsp+2B0h+var_278]
0x180007c76  lea     rcx, [rsp+2B0h+var_250]
0x180007c7b  call    _GetKeyFromFile
0x180007c80  test    eax, eax
0x180007c82  jns     short loc_180007C8B
0x180007c84  mov     rdi, [rsp+2B0h+var_278]
0x180007c89  jmp     short loc_180007CBF
0x180007c8b  lea     r8, [rsp+2B0h+var_288]
0x180007c90  xor     edx, edx
0x180007c92  mov     rcx, r12
0x180007c95  call    cs:__imp_FveOpenVolumeW
0x180007c9b  mov     rdi, [rsp+2B0h+var_278]
0x180007ca0  mov     ebx, eax
0x180007ca2  test    eax, eax
0x180007ca4  js      short loc_180007CC1
0x180007ca6  mov     r8, [rsp+2B0h+var_260]
0x180007cab  mov     rdx, rdi
0x180007cae  mov     rcx, [rsp+2B0h+var_288]
0x180007cb3  call    cs:__imp_FveUnlockVolumeWithAccessMode
0x180007cb9  mov     ebx, eax
0x180007cbb  test    eax, eax
0x180007cbd  jns     short loc_180007CC9
0x180007cbf  xor     ebx, ebx
0x180007cc1  inc     r14d
0x180007cc4  jmp     loc_180007BBA
0x180007cc9  mov     r13b, 1
0x180007ccc  test    ebx, ebx
0x180007cce  js      short loc_180007CF4
0x180007cd0  mov     word ptr [r15], 13h
0x180007cd6  test    r13b, r13b
0x180007cd9  jnz     short loc_180007CE5
0x180007cdb  mov     dword ptr [r15+8], 80070002h
0x180007ce3  jmp     short loc_180007CF4
0x180007ce5  mov     dword ptr [r15+8], 0
0x180007ced  jmp     short loc_180007CF4
0x180007cef  mov     ebx, 80004003h
0x180007cf4  mov     rcx, [rsp+2B0h+var_288]
0x180007cf9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007cfd  jz      short loc_180007D0E
0x180007cff  call    cs:__imp_FveCloseVolume
0x180007d05  mov     [rsp+2B0h+var_288], 0FFFFFFFFFFFFFFFFh
0x180007d0e  test    rdi, rdi
0x180007d11  jz      short loc_180007D55
0x180007d13  call    cs:__imp_GetProcessHeap
0x180007d19  mov     r8, rdi; lpMem
0x180007d1c  xor     edx, edx; dwFlags
0x180007d1e  mov     rcx, rax; hHeap
0x180007d21  call    cs:__imp_HeapSize
0x180007d27  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007d2b  jz      short loc_180007D55
0x180007d2d  mov     rcx, rdi
0x180007d30  test    rax, rax
0x180007d33  jz      short loc_180007D41
0x180007d35  mov     byte ptr [rcx], 0
0x180007d38  inc     rcx
0x180007d3b  sub     rax, 1
0x180007d3f  jnz     short loc_180007D35
0x180007d41  call    cs:__imp_GetProcessHeap
0x180007d47  mov     r8, rdi; lpMem
0x180007d4a  xor     edx, edx; dwFlags
0x180007d4c  mov     rcx, rax; hHeap
0x180007d4f  call    cs:__imp_HeapFree
0x180007d55  test    rsi, rsi
0x180007d58  jz      short loc_180007D6E
0x180007d5a  call    cs:__imp_GetProcessHeap
0x180007d60  mov     r8, rsi; lpMem
0x180007d63  xor     edx, edx; dwFlags
0x180007d65  mov     rcx, rax; hHeap
0x180007d68  call    cs:__imp_HeapFree
0x180007d6e  mov     eax, ebx
0x180007d70  mov     rcx, [rbp+1B0h+var_40]
0x180007d77  xor     rcx, rsp; StackCookie
0x180007d7a  call    __security_check_cookie
0x180007d7f  mov     rbx, [rsp+2B0h+arg_10]
0x180007d87  add     rsp, 280h
0x180007d8e  pop     r15
0x180007d90  pop     r14
0x180007d92  pop     r13
0x180007d94  pop     r12
0x180007d96  pop     rdi
0x180007d97  pop     rsi
0x180007d98  pop     rbp
0x180007d99  retn
```
