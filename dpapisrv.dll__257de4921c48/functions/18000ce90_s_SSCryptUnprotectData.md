# s_SSCryptUnprotectData

- ea: `0x18000ce90`
- end: `0x18000d12a`
- name: `s_SSCryptUnprotectData`
- size: `666`
- prototype: `__int64 __fastcall(void *, unsigned __int8 **, unsigned int *, _BYTE *, unsigned int, unsigned __int16 **, unsigned __int8 *, ULONG cbInput, struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *, unsigned int, unsigned __int8 *, ULONG)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800097f0`
- `0x18000ce90`
- `0x180016370`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d09a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d09a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0f1`

## string_xrefs

- `0x18000cf83`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000d05a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall s_SSCryptUnprotectData(
        void *a1,
        unsigned __int8 **a2,
        unsigned int *a3,
        _BYTE *a4,
        unsigned int a5,
        unsigned __int16 **a6,
        unsigned __int8 *a7,
        ULONG cbInput,
        struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *a9,
        unsigned int a10,
        unsigned __int8 *a11,
        ULONG a12)
{
  bool v16; // zf
  unsigned int v18; // eax
  unsigned int v19; // edi
  unsigned int v20; // eax
  int v21; // edx
  __int64 v22; // rcx
  _BYTE v23[24]; // [rsp+70h] [rbp-2B8h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-2A0h]
  HANDLE v25; // [rsp+90h] [rbp-298h]
  HLOCAL v26; // [rsp+98h] [rbp-290h]
  HLOCAL hMem; // [rsp+B8h] [rbp-270h]

  memset_0(v23, 0, 0x270u);
  v16 = g_fDPAPIInitialized == 0;
  *a2 = 0;
  *a3 = 0;
  if ( v16 )
    return 1359;
  if ( (a10 & 0x20000000) != 0 )
    return 87;
  if ( a5 < 0x14 )
    return 13;
  v18 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v23, a1, 0, 0);
  v19 = v18;
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
        222);
  }
  else
  {
    if ( *(_DWORD *)a4 == 1 )
    {
      v20 = SPCryptUnprotect(v23, a2, a3, a4 + 20, a5 - 20, a6, a7, cbInput, a9, a10, a11, a12);
      v22 = a5;
      v19 = v20;
      do
      {
        *a4++ = 0;
        --v22;
      }
      while ( v22 );
      if ( v20 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            v21,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwRet",
            v20,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
            4);
      }
      else
      {
        v19 = 0;
      }
    }
    else
    {
      v19 = 13;
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
  }
  return v19;
}

```

## disassembly

```asm
0x18000ce90  push    rbx
0x18000ce92  push    rdi
0x18000ce93  push    r12
0x18000ce95  push    r13
0x18000ce97  push    r14
0x18000ce99  push    r15
0x18000ce9b  sub     rsp, 2F8h
0x18000cea2  mov     rax, cs:__security_cookie
0x18000cea9  xor     rax, rsp
0x18000ceac  mov     [rsp+328h+var_48], rax
0x18000ceb4  mov     rax, [rsp+328h+arg_40]
0x18000cebc  mov     r15, r8
0x18000cebf  mov     r12, [rsp+328h+arg_28]
0x18000cec7  mov     r14, rdx
0x18000ceca  mov     r13, [rsp+328h+arg_30]
0x18000ced2  mov     rdi, rcx
0x18000ced5  mov     [rsp+328h+var_2C0], rax
0x18000ceda  lea     rcx, [rsp+328h+var_2B8]; void *
0x18000cedf  mov     rax, [rsp+328h+arg_50]
0x18000cee7  xor     edx, edx; Val
0x18000cee9  mov     r8d, 270h; Size
0x18000ceef  mov     [rsp+328h+var_2C8], rax
0x18000cef4  mov     rbx, r9
0x18000cef7  call    memset_0
0x18000cefc  xor     eax, eax
0x18000cefe  cmp     cs:?g_fDPAPIInitialized@@3HA, eax; int g_fDPAPIInitialized
0x18000cf04  mov     [r14], rax
0x18000cf07  mov     [r15], eax
0x18000cf0a  jnz     short loc_18000CF16
0x18000cf0c  mov     eax, 54Fh
0x18000cf11  jmp     loc_18000D107
0x18000cf16  mov     [rsp+328h+var_38], rbp
0x18000cf1e  mov     ebp, [rsp+328h+arg_48]
0x18000cf25  bt      ebp, 1Dh
0x18000cf29  jnb     short loc_18000CF35
0x18000cf2b  mov     eax, 57h ; 'W'
0x18000cf30  jmp     loc_18000D0FF
0x18000cf35  cmp     [rsp+328h+arg_20], 14h
0x18000cf3d  jnb     short loc_18000CF49
0x18000cf3f  mov     eax, 0Dh
0x18000cf44  jmp     loc_18000D0FF
0x18000cf49  xor     r9d, r9d; unsigned int *
0x18000cf4c  lea     rcx, [rsp+328h+var_2B8]; struct CRYPT_SERVER_CONTEXT *
0x18000cf51  xor     r8d, r8d; unsigned __int16 **
0x18000cf54  mov     rdx, rdi; void *
0x18000cf57  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18000cf5c  mov     edi, eax
0x18000cf5e  test    eax, eax
0x18000cf60  jz      short loc_18000CFB7
0x18000cf62  mov     rdx, cs:WPP_GLOBAL_Control
0x18000cf69  lea     rcx, WPP_GLOBAL_Control
0x18000cf70  cmp     rdx, rcx
0x18000cf73  jz      loc_18000D0FD
0x18000cf79  test    byte ptr [rdx+1Ch], 1
0x18000cf7d  jz      loc_18000D0FD
0x18000cf83  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000cf8a  mov     dword ptr [rsp+328h+var_2F8], 7DEh
0x18000cf92  mov     [rsp+328h+var_300], rcx
0x18000cf97  lea     r9, aDwret; "dwRet"
0x18000cf9e  mov     rcx, [rdx+10h]
0x18000cfa2  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000cfa9  mov     [rsp+328h+var_308], eax
0x18000cfad  call    WPP_SF_sDsd
0x18000cfb2  jmp     loc_18000D0FD
0x18000cfb7  cmp     dword ptr [rbx], 1
0x18000cfba  jz      short loc_18000CFC6
0x18000cfbc  mov     edi, 0Dh
0x18000cfc1  jmp     loc_18000D08D
0x18000cfc6  mov     eax, [rsp+328h+arg_58]
0x18000cfcd  lea     r9, [rbx+14h]; unsigned __int8 *
0x18000cfd1  mov     [rsp+328h+var_2D0], eax; ULONG
0x18000cfd5  mov     ecx, ebx
0x18000cfd7  mov     rax, [rsp+328h+var_2C8]
0x18000cfdc  sub     ecx, r9d
0x18000cfdf  add     ecx, [rsp+328h+arg_20]
0x18000cfe6  mov     r8, r15; unsigned int *
0x18000cfe9  mov     [rsp+328h+var_2D8], rax; unsigned __int8 *
0x18000cfee  mov     rdx, r14; unsigned __int8 **
0x18000cff1  mov     rax, [rsp+328h+var_2C0]
0x18000cff6  mov     [rsp+328h+var_2E0], ebp; unsigned int
0x18000cffa  mov     [rsp+328h+var_2E8], rax; struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *
0x18000cfff  mov     eax, [rsp+328h+arg_38]
0x18000d006  mov     [rsp+328h+cbInput], eax; cbInput
0x18000d00a  mov     [rsp+328h+var_2F8], r13; unsigned __int8 *
0x18000d00f  mov     [rsp+328h+var_300], r12; unsigned __int16 **
0x18000d014  mov     [rsp+328h+var_308], ecx; unsigned int
0x18000d018  lea     rcx, [rsp+328h+var_2B8]; void *
0x18000d01d  call    ?SPCryptUnprotect@@YAKPEAXPEAPEAEPEAKPEAEKPEAPEAG3KPEAU_SSCRYPTPROTECTDATA_PROMPTSTRUCT@@K3K@Z; SPCryptUnprotect(void *,uchar * *,ulong *,uchar *,ulong,ushort * *,uchar *,ulong,_SSCRYPTPROTECTDATA_PROMPTSTRUCT *,ulong,uchar *,ulong)
0x18000d022  mov     ecx, [rsp+328h+arg_20]
0x18000d029  mov     edi, eax
0x18000d02b  test    rcx, rcx
0x18000d02e  jz      short loc_18000D03D
0x18000d030  mov     byte ptr [rbx], 0
0x18000d033  lea     rbx, [rbx+1]
0x18000d037  sub     rcx, 1
0x18000d03b  jnz     short loc_18000D030
0x18000d03d  test    edi, edi
0x18000d03f  jz      short loc_18000D08B
0x18000d041  mov     rax, cs:WPP_GLOBAL_Control
0x18000d048  lea     rcx, WPP_GLOBAL_Control
0x18000d04f  cmp     rax, rcx
0x18000d052  jz      short loc_18000D08D
0x18000d054  test    byte ptr [rax+1Ch], 1
0x18000d058  jz      short loc_18000D08D
0x18000d05a  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000d061  mov     dword ptr [rsp+328h+var_2F8], 804h
0x18000d069  mov     [rsp+328h+var_300], rcx
0x18000d06e  lea     r9, aDwret; "dwRet"
0x18000d075  mov     rcx, [rax+10h]
0x18000d079  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000d080  mov     [rsp+328h+var_308], edi
0x18000d084  call    WPP_SF_sDsd
0x18000d089  jmp     short loc_18000D08D
0x18000d08b  xor     edi, edi
0x18000d08d  mov     rcx, [rsp+328h+hMem]; hMem
0x18000d095  test    rcx, rcx
0x18000d098  jz      short loc_18000D0A6
0x18000d09a  call    cs:__imp_LocalFree
0x18000d0a1  nop     dword ptr [rax+rax+00h]
0x18000d0a6  mov     rcx, [rsp+328h+var_290]; hMem
0x18000d0ae  test    rcx, rcx
0x18000d0b1  jz      short loc_18000D0CB
0x18000d0b3  call    cs:__imp_LocalFree
0x18000d0ba  nop     dword ptr [rax+rax+00h]
0x18000d0bf  mov     [rsp+328h+var_290], 0
0x18000d0cb  mov     rcx, [rsp+328h+hObject]; hObject
0x18000d0d3  test    rcx, rcx
0x18000d0d6  jz      short loc_18000D0E4
0x18000d0d8  call    cs:__imp_CloseHandle
0x18000d0df  nop     dword ptr [rax+rax+00h]
0x18000d0e4  mov     rcx, [rsp+328h+var_298]; hObject
0x18000d0ec  test    rcx, rcx
0x18000d0ef  jz      short loc_18000D0FD
0x18000d0f1  call    cs:__imp_CloseHandle
0x18000d0f8  nop     dword ptr [rax+rax+00h]
0x18000d0fd  mov     eax, edi
0x18000d0ff  mov     rbp, [rsp+328h+var_38]
0x18000d107  mov     rcx, [rsp+328h+var_48]
0x18000d10f  xor     rcx, rsp; StackCookie
0x18000d112  call    __security_check_cookie
0x18000d117  add     rsp, 2F8h
0x18000d11e  pop     r15
0x18000d120  pop     r14
0x18000d122  pop     r13
0x18000d124  pop     r12
0x18000d126  pop     rdi
0x18000d127  pop     rbx
0x18000d128  retn
```
