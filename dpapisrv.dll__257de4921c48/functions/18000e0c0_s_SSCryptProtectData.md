# s_SSCryptProtectData

- ea: `0x18000e0c0`
- end: `0x18000e3df`
- name: `s_SSCryptProtectData`
- size: `799`
- prototype: `__int64 __fastcall(void *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned __int16 *Src, unsigned __int8 *, ULONG, struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800097f0`
- `0x18000e0c0`
- `0x180014c80`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x18003c638`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e333`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e36b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e333`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e36b`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000e2a4`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000e2a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e38c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e38c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3a5`

## string_xrefs

- `0x18000e190`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000e258`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000e305`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall s_SSCryptProtectData(
        void *a1,
        unsigned __int8 **a2,
        unsigned int *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int16 *Src,
        unsigned __int8 *a7,
        ULONG a8,
        struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *a9,
        unsigned int a10,
        unsigned __int8 *a11,
        unsigned int a12)
{
  unsigned int v17; // ebx
  unsigned int v18; // esi
  __int64 v19; // rcx
  SIZE_T v20; // rdx
  unsigned __int8 *v21; // rax
  unsigned __int8 *v22; // rax
  _BYTE v23[24]; // [rsp+70h] [rbp-2C8h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-2B0h]
  HANDLE v25; // [rsp+90h] [rbp-2A8h]
  HLOCAL v26; // [rsp+98h] [rbp-2A0h]
  HLOCAL hMem; // [rsp+B8h] [rbp-280h]

  memset_0(v23, 0, 0x270u);
  if ( !g_fDPAPIInitialized )
    return 1359;
  if ( (a10 & 0x20000000) != 0 )
    return 87;
  v17 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v23, a1, 0, 0);
  if ( v17 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        v17,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
        97);
    return v17;
  }
  else
  {
    v18 = SPCryptProtect(v23, a2, a3, a4, a5, Src, a7, a8, a9, a10, a11, a12);
    v19 = a5;
    if ( a5 )
    {
      do
      {
        *a4++ = 0;
        --v19;
      }
      while ( v19 );
    }
    if ( v18 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          v18,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
          128);
    }
    else if ( *a2 )
    {
      v20 = *a3 + 20;
      if ( (unsigned int)v20 >= *a3 && (v21 = (unsigned __int8 *)LocalReAlloc(*a2, v20, 2u)) != 0 )
      {
        *a2 = v21;
        memmove_0(v21 + 20, v21, *a3);
        *a3 += 20;
        v18 = 0;
        v22 = *a2;
        *(_DWORD *)v22 = 1;
        *(GUID *)(v22 + 4) = g_guidDefaultProvider;
      }
      else
      {
        v18 = 8;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwRet",
            8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
            148);
        LocalFree(*a2);
        *a2 = 0;
        *a3 = 0;
      }
    }
    if ( hMem )
      LocalFree(hMem);
    if ( v26 )
    {
      LocalFree(v26);
      v26 = 0;
    }
    if ( hObject )
      CloseHandle(hObject);
    if ( v25 )
      CloseHandle(v25);
    return v18;
  }
}

```

## disassembly

```asm
0x18000e0c0  push    rbx
0x18000e0c2  push    rbp
0x18000e0c3  push    rdi
0x18000e0c4  push    r12
0x18000e0c6  push    r13
0x18000e0c8  push    r14
0x18000e0ca  push    r15
0x18000e0cc  sub     rsp, 300h
0x18000e0d3  mov     rax, cs:__security_cookie
0x18000e0da  xor     rax, rsp
0x18000e0dd  mov     [rsp+338h+var_58], rax
0x18000e0e5  mov     rax, [rsp+338h+arg_50]
0x18000e0ed  mov     r15, r8
0x18000e0f0  mov     rbp, [rsp+338h+arg_28]
0x18000e0f8  mov     r14, rdx
0x18000e0fb  mov     r12, [rsp+338h+arg_30]
0x18000e103  mov     rbx, rcx
0x18000e106  mov     r13, [rsp+338h+arg_40]
0x18000e10e  lea     rcx, [rsp+338h+var_2C8]; void *
0x18000e113  xor     edx, edx; Val
0x18000e115  mov     [rsp+338h+var_2D8], rax
0x18000e11a  mov     r8d, 270h; Size
0x18000e120  mov     rdi, r9
0x18000e123  call    memset_0
0x18000e128  cmp     cs:?g_fDPAPIInitialized@@3HA, 0; int g_fDPAPIInitialized
0x18000e12f  jnz     short loc_18000E13B
0x18000e131  mov     eax, 54Fh
0x18000e136  jmp     loc_18000E3BB
0x18000e13b  mov     [rsp+338h+var_40], rsi
0x18000e143  mov     esi, [rsp+338h+arg_48]
0x18000e14a  bt      esi, 1Dh
0x18000e14e  jnb     short loc_18000E15A
0x18000e150  mov     eax, 57h ; 'W'
0x18000e155  jmp     loc_18000E3B3
0x18000e15a  xor     r9d, r9d; unsigned int *
0x18000e15d  lea     rcx, [rsp+338h+var_2C8]; struct CRYPT_SERVER_CONTEXT *
0x18000e162  xor     r8d, r8d; unsigned __int16 **
0x18000e165  mov     rdx, rbx; void *
0x18000e168  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18000e16d  mov     ebx, eax
0x18000e16f  test    eax, eax
0x18000e171  jz      short loc_18000E1C2
0x18000e173  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e17a  lea     rcx, WPP_GLOBAL_Control
0x18000e181  cmp     rdx, rcx
0x18000e184  jz      short loc_18000E1BB
0x18000e186  test    byte ptr [rdx+1Ch], 1
0x18000e18a  jz      short loc_18000E1BB
0x18000e18c  mov     rcx, [rdx+10h]
0x18000e190  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000e197  mov     dword ptr [rsp+338h+var_308], 761h
0x18000e19f  lea     r9, aDwret; "dwRet"
0x18000e1a6  mov     [rsp+338h+Src], rax
0x18000e1ab  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000e1b2  mov     [rsp+338h+var_318], ebx
0x18000e1b6  call    WPP_SF_sDsd
0x18000e1bb  mov     eax, ebx
0x18000e1bd  jmp     loc_18000E3B3
0x18000e1c2  mov     eax, [rsp+338h+arg_58]
0x18000e1c9  lea     rcx, [rsp+338h+var_2C8]; void *
0x18000e1ce  mov     ebx, [rsp+338h+arg_20]
0x18000e1d5  mov     r9, rdi; unsigned __int8 *
0x18000e1d8  mov     [rsp+338h+var_2E0], eax; unsigned int
0x18000e1dc  mov     r8, r15; unsigned int *
0x18000e1df  mov     rax, [rsp+338h+var_2D8]
0x18000e1e4  mov     rdx, r14; unsigned __int8 **
0x18000e1e7  mov     [rsp+338h+var_2E8], rax; unsigned __int8 *
0x18000e1ec  mov     eax, [rsp+338h+arg_38]
0x18000e1f3  mov     [rsp+338h+var_2F0], esi; unsigned int
0x18000e1f7  mov     [rsp+338h+var_2F8], r13; struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *
0x18000e1fc  mov     [rsp+338h+var_300], eax; ULONG
0x18000e200  mov     [rsp+338h+var_308], r12; unsigned __int8 *
0x18000e205  mov     [rsp+338h+Src], rbp; Src
0x18000e20a  mov     [rsp+338h+var_318], ebx; unsigned int
0x18000e20e  call    ?SPCryptProtect@@YAKPEAXPEAPEAEPEAKPEAEKPEBG3KPEAU_SSCRYPTPROTECTDATA_PROMPTSTRUCT@@K3K@Z; SPCryptProtect(void *,uchar * *,ulong *,uchar *,ulong,ushort const *,uchar *,ulong,_SSCRYPTPROTECTDATA_PROMPTSTRUCT *,ulong,uchar *,ulong)
0x18000e213  mov     esi, eax
0x18000e215  mov     ecx, ebx
0x18000e217  test    ebx, ebx
0x18000e219  jz      short loc_18000E22D
0x18000e21b  nop     dword ptr [rax+rax+00h]
0x18000e220  mov     byte ptr [rdi], 0
0x18000e223  lea     rdi, [rdi+1]
0x18000e227  sub     rcx, 1
0x18000e22b  jnz     short loc_18000E220
0x18000e22d  xor     ebx, ebx
0x18000e22f  test    esi, esi
0x18000e231  jz      short loc_18000E288
0x18000e233  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e23a  lea     rcx, WPP_GLOBAL_Control
0x18000e241  cmp     rdx, rcx
0x18000e244  jz      loc_18000E345
0x18000e24a  test    byte ptr [rdx+1Ch], 1
0x18000e24e  jz      loc_18000E345
0x18000e254  mov     rcx, [rdx+10h]
0x18000e258  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000e25f  mov     dword ptr [rsp+338h+var_308], 780h
0x18000e267  lea     r9, aDwret; "dwRet"
0x18000e26e  mov     [rsp+338h+Src], rax
0x18000e273  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000e27a  mov     [rsp+338h+var_318], esi
0x18000e27e  call    WPP_SF_sDsd
0x18000e283  jmp     loc_18000E345
0x18000e288  mov     rcx, [r14]; hMem
0x18000e28b  test    rcx, rcx
0x18000e28e  jz      loc_18000E345
0x18000e294  mov     eax, [r15]
0x18000e297  lea     edx, [rax+14h]; uBytes
0x18000e29a  cmp     edx, eax
0x18000e29c  jb      short loc_18000E2E3
0x18000e29e  mov     r8d, 2; uFlags
0x18000e2a4  call    cs:__imp_LocalReAlloc
0x18000e2ab  nop     dword ptr [rax+rax+00h]
0x18000e2b0  test    rax, rax
0x18000e2b3  jz      short loc_18000E2E3
0x18000e2b5  mov     [r14], rax
0x18000e2b8  lea     rcx, [rax+14h]; void *
0x18000e2bc  mov     r8d, [r15]; Size
0x18000e2bf  mov     rdx, rax; Src
0x18000e2c2  call    memmove_0
0x18000e2c7  add     dword ptr [r15], 14h
0x18000e2cb  mov     esi, ebx
0x18000e2cd  mov     rax, [r14]
0x18000e2d0  mov     dword ptr [rax], 1
0x18000e2d6  movups  xmm0, xmmword ptr cs:?g_guidDefaultProvider@@3U_GUID@@A.Data1; _GUID g_guidDefaultProvider ...
0x18000e2dd  movups  xmmword ptr [rax+4], xmm0
0x18000e2e1  jmp     short loc_18000E345
0x18000e2e3  mov     esi, 8
0x18000e2e8  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e2ef  lea     rcx, WPP_GLOBAL_Control
0x18000e2f6  cmp     rdx, rcx
0x18000e2f9  jz      short loc_18000E330
0x18000e2fb  test    byte ptr [rdx+1Ch], 1
0x18000e2ff  jz      short loc_18000E330
0x18000e301  mov     rcx, [rdx+10h]
0x18000e305  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000e30c  mov     dword ptr [rsp+338h+var_308], 794h
0x18000e314  lea     r9, aDwret; "dwRet"
0x18000e31b  mov     [rsp+338h+Src], rax
0x18000e320  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000e327  mov     [rsp+338h+var_318], esi
0x18000e32b  call    WPP_SF_sDsd
0x18000e330  mov     rcx, [r14]; hMem
0x18000e333  call    cs:__imp_LocalFree
0x18000e33a  nop     dword ptr [rax+rax+00h]
0x18000e33f  mov     [r14], rbx
0x18000e342  mov     [r15], ebx
0x18000e345  mov     rcx, [rsp+338h+hMem]; hMem
0x18000e34d  test    rcx, rcx
0x18000e350  jz      short loc_18000E35E
0x18000e352  call    cs:__imp_LocalFree
0x18000e359  nop     dword ptr [rax+rax+00h]
0x18000e35e  mov     rcx, [rsp+338h+var_2A0]; hMem
0x18000e366  test    rcx, rcx
0x18000e369  jz      short loc_18000E37F
0x18000e36b  call    cs:__imp_LocalFree
0x18000e372  nop     dword ptr [rax+rax+00h]
0x18000e377  mov     [rsp+338h+var_2A0], rbx
0x18000e37f  mov     rcx, [rsp+338h+hObject]; hObject
0x18000e387  test    rcx, rcx
0x18000e38a  jz      short loc_18000E398
0x18000e38c  call    cs:__imp_CloseHandle
0x18000e393  nop     dword ptr [rax+rax+00h]
0x18000e398  mov     rcx, [rsp+338h+var_2A8]; hObject
0x18000e3a0  test    rcx, rcx
0x18000e3a3  jz      short loc_18000E3B1
0x18000e3a5  call    cs:__imp_CloseHandle
0x18000e3ac  nop     dword ptr [rax+rax+00h]
0x18000e3b1  mov     eax, esi
0x18000e3b3  mov     rsi, [rsp+338h+var_40]
0x18000e3bb  mov     rcx, [rsp+338h+var_58]
0x18000e3c3  xor     rcx, rsp; StackCookie
0x18000e3c6  call    __security_check_cookie
0x18000e3cb  add     rsp, 300h
0x18000e3d2  pop     r15
0x18000e3d4  pop     r14
0x18000e3d6  pop     r13
0x18000e3d8  pop     r12
0x18000e3da  pop     rdi
0x18000e3db  pop     rbp
0x18000e3dc  pop     rbx
0x18000e3dd  retn
```
