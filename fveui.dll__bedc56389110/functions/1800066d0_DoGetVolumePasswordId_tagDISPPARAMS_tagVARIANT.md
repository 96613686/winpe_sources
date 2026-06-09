# DoGetVolumePasswordId(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x1800066d0`
- end: `0x1800068f6`
- name: `?DoGetVolumePasswordId@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001bb0`
- `0x1800066d0`
- `0x18000ce84`

## import_xrefs

- `KERNEL32!HeapSize` at `0x18000689c`
- `KERNEL32!HeapSize` at `0x18000689c`
- `KERNEL32!HeapFree` at `0x180006883`
- `KERNEL32!HeapFree` at `0x1800068ca`
- `KERNEL32!HeapFree` at `0x180006883`
- `KERNEL32!HeapFree` at `0x1800068ca`
- `KERNEL32!HeapAlloc` at `0x1800067d5`
- `KERNEL32!HeapAlloc` at `0x1800067d5`
- `KERNEL32!GetProcessHeap` at `0x1800067c4`
- `KERNEL32!GetProcessHeap` at `0x180006875`
- `KERNEL32!GetProcessHeap` at `0x18000688e`
- `KERNEL32!GetProcessHeap` at `0x1800068bc`
- `KERNEL32!GetProcessHeap` at `0x1800067c4`
- `KERNEL32!GetProcessHeap` at `0x180006875`
- `KERNEL32!GetProcessHeap` at `0x18000688e`
- `KERNEL32!GetProcessHeap` at `0x1800068bc`
- `OLEAUT32!__imp_SysAllocString` at `0x180006839`
- `OLEAUT32!__imp_SysAllocString` at `0x180006839`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18000679f`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18000680d`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18000679f`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18000680d`
- `FVEAPI!FveSelectBestRecoveryPasswordByBackupInformation` at `0x180006755`
- `FVEAPI!FveSelectBestRecoveryPasswordByBackupInformation` at `0x180006755`
- `FVEAPI!FveCloseVolume` at `0x180006862`
- `FVEAPI!FveCloseVolume` at `0x180006862`
- `FVEAPI!FveOpenVolumeW` at `0x18000673d`
- `FVEAPI!FveOpenVolumeW` at `0x18000673d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DoGetVolumePasswordId(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  OLECHAR *v4; // rsi
  _DWORD *v5; // rdi
  int v6; // ebx
  int AuthMethodInformation; // eax
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rax
  OLECHAR *v11; // rcx
  BSTR v12; // rax
  int v13; // ecx
  HANDLE v14; // rax
  HANDLE v15; // rax
  SIZE_T v16; // rax
  _BYTE *i; // rcx
  HANDLE v18; // rax
  __int64 v20; // [rsp+20h] [rbp-29h] BYREF
  OLECHAR *psz; // [rsp+28h] [rbp-21h]
  SIZE_T dwBytes; // [rsp+30h] [rbp-19h] BYREF
  GUID rguid; // [rsp+38h] [rbp-11h] BYREF
  _OWORD v24[3]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v25; // [rsp+78h] [rbp+2Fh]

  rgvarg = a1->rgvarg;
  v20 = -1;
  memset(v24, 0, sizeof(v24));
  v25 = 0;
  v4 = 0;
  dwBytes = 0;
  v5 = 0;
  psz = 0;
  rguid = GUID_NULL;
  v6 = FveOpenVolumeW(rgvarg->llVal, 0, &v20);
  if ( v6 < 0 )
    goto LABEL_16;
  if ( (int)FveSelectBestRecoveryPasswordByBackupInformation(v20, &rguid) >= 0 )
  {
    if ( (int)ConvertGuidToWstr(&rguid) >= 0 )
    {
LABEL_12:
      v4 = psz;
      v11 = psz;
      a2->vt = 8;
      v12 = SysAllocString(v11);
      v13 = v6;
      a2->llVal = (LONGLONG)v12;
      if ( !v12 )
        v13 = -2147024882;
      v6 = v13;
      goto LABEL_16;
    }
    v4 = psz;
  }
  *(_QWORD *)&v24[0] = 0x100000038LL;
  DWORD2(v24[0]) = 0x80000;
  AuthMethodInformation = FveGetAuthMethodInformation(v20, v24, 56, &dwBytes);
  v6 = AuthMethodInformation;
  if ( AuthMethodInformation != -2147024774 )
  {
    if ( AuthMethodInformation >= 0 )
      v6 = 1;
    goto LABEL_16;
  }
  v8 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, v8);
  v5 = v10;
  if ( !v10 )
  {
    v6 = -2147024882;
    goto LABEL_16;
  }
  *v10 = 56;
  v10[1] = 1;
  v10[2] = 0x80000;
  v6 = FveGetAuthMethodInformation(v20, v10, dwBytes, &dwBytes);
  if ( v6 >= 0 )
  {
    v6 = ConvertGuidToWstr((GUID *)(v5 + 10));
    if ( v6 < 0 )
    {
      v4 = psz;
      goto LABEL_16;
    }
    goto LABEL_12;
  }
LABEL_16:
  if ( v20 != -1 )
  {
    FveCloseVolume();
    v20 = -1;
  }
  if ( v4 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v4);
  }
  if ( v5 )
  {
    v15 = GetProcessHeap();
    v16 = HeapSize(v15, 0, v5);
    if ( v16 != -1 )
    {
      for ( i = v5; v16; --v16 )
        *i++ = 0;
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v5);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800066d0  mov     [rsp-8+arg_10], rbx
0x1800066d5  mov     [rsp-8+arg_18], rsi
0x1800066da  push    rbp
0x1800066db  push    rdi
0x1800066dc  push    r14
0x1800066de  lea     rbp, [rsp-47h]
0x1800066e3  sub     rsp, 90h
0x1800066ea  mov     rax, cs:__security_cookie
0x1800066f1  xor     rax, rsp
0x1800066f4  mov     [rbp+57h+var_20], rax
0x1800066f8  mov     rcx, [rcx]
0x1800066fb  lea     r8, [rbp+57h+var_80]
0x1800066ff  xorps   xmm0, xmm0
0x180006702  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x18000670a  movups  [rbp+57h+var_58], xmm0
0x18000670e  xor     eax, eax
0x180006710  mov     r14, rdx
0x180006713  movups  [rbp+57h+var_48], xmm0
0x180006717  mov     [rbp+57h+var_28], rax
0x18000671b  xor     esi, esi
0x18000671d  movups  [rbp+57h+var_38], xmm0
0x180006721  mov     [rbp+57h+dwBytes], rax
0x180006725  xor     edx, edx
0x180006727  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000672e  xor     edi, edi
0x180006730  mov     [rbp+57h+psz], rsi
0x180006734  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x180006739  mov     rcx, [rcx+8]
0x18000673d  call    cs:__imp_FveOpenVolumeW
0x180006743  mov     ebx, eax
0x180006745  test    eax, eax
0x180006747  js      loc_180006858
0x18000674d  mov     rcx, [rbp+57h+var_80]
0x180006751  lea     rdx, [rbp+57h+rguid]
0x180006755  call    cs:__imp_FveSelectBestRecoveryPasswordByBackupInformation
0x18000675b  test    eax, eax
0x18000675d  js      short loc_180006778
0x18000675f  lea     rdx, [rbp+57h+psz]
0x180006763  lea     rcx, [rbp+57h+rguid]; rguid
0x180006767  call    _ConvertGuidToWstr
0x18000676c  test    eax, eax
0x18000676e  jns     loc_18000682C
0x180006774  mov     rsi, [rbp+57h+psz]
0x180006778  mov     rcx, [rbp+57h+var_80]
0x18000677c  lea     r9, [rbp+57h+dwBytes]
0x180006780  mov     r8d, 38h ; '8'
0x180006786  mov     dword ptr [rbp+57h+var_58], 38h ; '8'
0x18000678d  lea     rdx, [rbp+57h+var_58]
0x180006791  mov     dword ptr [rbp+57h+var_58+4], 1
0x180006798  mov     dword ptr [rbp+57h+var_58+8], 80000h
0x18000679f  call    cs:__imp_FveGetAuthMethodInformation
0x1800067a5  mov     ebx, eax
0x1800067a7  cmp     eax, 8007007Ah
0x1800067ac  jz      short loc_1800067C0
0x1800067ae  test    eax, eax
0x1800067b0  js      loc_180006858
0x1800067b6  mov     ebx, 1
0x1800067bb  jmp     loc_180006858
0x1800067c0  mov     rbx, [rbp+57h+dwBytes]
0x1800067c4  call    cs:__imp_GetProcessHeap
0x1800067ca  mov     r8, rbx; dwBytes
0x1800067cd  mov     edx, 8; dwFlags
0x1800067d2  mov     rcx, rax; hHeap
0x1800067d5  call    cs:__imp_HeapAlloc
0x1800067db  mov     rdi, rax
0x1800067de  test    rax, rax
0x1800067e1  jnz     short loc_1800067EA
0x1800067e3  mov     ebx, 8007000Eh
0x1800067e8  jmp     short loc_180006858
0x1800067ea  mov     dword ptr [rax], 38h ; '8'
0x1800067f0  lea     r9, [rbp+57h+dwBytes]
0x1800067f4  mov     dword ptr [rax+4], 1
0x1800067fb  mov     rdx, rdi
0x1800067fe  mov     dword ptr [rax+8], 80000h
0x180006805  mov     r8, [rbp+57h+dwBytes]
0x180006809  mov     rcx, [rbp+57h+var_80]
0x18000680d  call    cs:__imp_FveGetAuthMethodInformation
0x180006813  mov     ebx, eax
0x180006815  test    eax, eax
0x180006817  js      short loc_180006858
0x180006819  lea     rcx, [rdi+28h]; rguid
0x18000681d  lea     rdx, [rbp+57h+psz]
0x180006821  call    _ConvertGuidToWstr
0x180006826  mov     ebx, eax
0x180006828  test    eax, eax
0x18000682a  js      short loc_180006854
0x18000682c  mov     rsi, [rbp+57h+psz]
0x180006830  mov     rcx, rsi; psz
0x180006833  mov     word ptr [r14], 8
0x180006839  call    cs:__imp_SysAllocString
0x18000683f  mov     ecx, ebx
0x180006841  mov     ebx, 8007000Eh
0x180006846  test    rax, rax
0x180006849  mov     [r14+8], rax
0x18000684d  cmovz   ecx, ebx
0x180006850  mov     ebx, ecx
0x180006852  jmp     short loc_180006858
0x180006854  mov     rsi, [rbp+57h+psz]
0x180006858  mov     rcx, [rbp+57h+var_80]
0x18000685c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006860  jz      short loc_180006870
0x180006862  call    cs:__imp_FveCloseVolume
0x180006868  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x180006870  test    rsi, rsi
0x180006873  jz      short loc_180006889
0x180006875  call    cs:__imp_GetProcessHeap
0x18000687b  mov     r8, rsi; lpMem
0x18000687e  xor     edx, edx; dwFlags
0x180006880  mov     rcx, rax; hHeap
0x180006883  call    cs:__imp_HeapFree
0x180006889  test    rdi, rdi
0x18000688c  jz      short loc_1800068D0
0x18000688e  call    cs:__imp_GetProcessHeap
0x180006894  mov     r8, rdi; lpMem
0x180006897  xor     edx, edx; dwFlags
0x180006899  mov     rcx, rax; hHeap
0x18000689c  call    cs:__imp_HeapSize
0x1800068a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800068a6  jz      short loc_1800068D0
0x1800068a8  mov     rcx, rdi
0x1800068ab  test    rax, rax
0x1800068ae  jz      short loc_1800068BC
0x1800068b0  mov     byte ptr [rcx], 0
0x1800068b3  inc     rcx
0x1800068b6  sub     rax, 1
0x1800068ba  jnz     short loc_1800068B0
0x1800068bc  call    cs:__imp_GetProcessHeap
0x1800068c2  mov     r8, rdi; lpMem
0x1800068c5  xor     edx, edx; dwFlags
0x1800068c7  mov     rcx, rax; hHeap
0x1800068ca  call    cs:__imp_HeapFree
0x1800068d0  mov     eax, ebx
0x1800068d2  mov     rcx, [rbp+57h+var_20]
0x1800068d6  xor     rcx, rsp; StackCookie
0x1800068d9  call    __security_check_cookie
0x1800068de  lea     r11, [rsp+0A0h+var_10]
0x1800068e6  mov     rbx, [r11+30h]
0x1800068ea  mov     rsi, [r11+38h]
0x1800068ee  mov     rsp, r11
0x1800068f1  pop     r14
0x1800068f3  pop     rdi
0x1800068f4  pop     rbp
0x1800068f5  retn
```
