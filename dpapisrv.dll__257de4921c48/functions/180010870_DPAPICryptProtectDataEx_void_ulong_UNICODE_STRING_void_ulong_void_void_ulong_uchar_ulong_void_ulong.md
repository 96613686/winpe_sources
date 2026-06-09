# DPAPICryptProtectDataEx(void *,ulong,_UNICODE_STRING *,void *,ulong,void *,void *,ulong,uchar *,ulong,void * *,ulong *)

- ea: `0x180010870`
- end: `0x180010b5b`
- name: `?DPAPICryptProtectDataEx@@YAEPEAXKPEAU_UNICODE_STRING@@0K00KPEAEKPEAPEAXPEAK@Z`
- size: `747`
- prototype: `unsigned __int8 __fastcall(void *Src, size_t Size, struct _UNICODE_STRING *, unsigned __int8 *, ULONG, void *, void *, unsigned int, unsigned __int8 *, ULONG, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800107f0`

## callees

- `0x180006510`
- `0x180007f10`
- `0x1800097f0`
- `0x18000db40`
- `0x18000dbd0`
- `0x180010870`
- `0x180014c80`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x18003c62c`
- `0x18003c638`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010aca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010aca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010af6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001096a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001096a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180010a67`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180010a67`

## string_xrefs

- `0x180010910`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180010a1c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180010aac`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
unsigned __int8 __fastcall DPAPICryptProtectDataEx(
        void *Src,
        size_t Size,
        struct _UNICODE_STRING *a3,
        unsigned __int8 *a4,
        ULONG a5,
        void *a6,
        void *a7,
        unsigned int a8,
        unsigned __int8 *a9,
        ULONG a10,
        unsigned __int8 **a11,
        unsigned int *a12)
{
  SIZE_T v14; // r14
  DWORD v16; // ecx
  unsigned int v18; // eax
  int v19; // ebx
  unsigned __int8 *v20; // rax
  unsigned __int8 *v21; // rbp
  int v22; // edx
  SIZE_T v23; // rdx
  unsigned __int8 *v24; // rax
  unsigned __int8 *v25; // rax
  SIZE_T v26; // rcx
  unsigned __int8 *v27; // rax
  RPC_BINDING_HANDLE v28[2]; // [rsp+70h] [rbp-2C8h] BYREF
  int v29; // [rsp+84h] [rbp-2B4h]

  v14 = (unsigned int)Size;
  memset_0(v28, 0, 0x270u);
  if ( !g_fDPAPIInitialized )
  {
    v16 = 1359;
LABEL_3:
    SetLastError(v16);
    return 0;
  }
  v18 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v28, 0, 0, 0);
  v19 = v18;
  if ( v18 )
  {
    DebugTraceError(v18, "dwRetVal", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 2154);
LABEL_6:
    v16 = v19;
    goto LABEL_3;
  }
  if ( a11 && Src && a3 )
  {
    if ( v29 )
      CPSRevertToSelf(v28);
    *a11 = 0;
    *a12 = 0;
    v20 = (unsigned __int8 *)LocalAlloc(0, v14);
    v21 = v20;
    if ( v20 )
    {
      memcpy_0(v20, Src, v14);
      v19 = SPCryptProtect(v28, a11, a12, v21, v14, a3->Buffer, a4, a5, 0, a8 | 0x40000000, a9, a10);
      if ( v19 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            v22,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwRetVal",
            v19,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
            168);
      }
      else if ( *a11 )
      {
        v23 = *a12 + 20;
        if ( (unsigned int)v23 >= *a12 && (v24 = (unsigned __int8 *)LocalReAlloc(*a11, v23, 2u)) != 0 )
        {
          *a11 = v24;
          v19 = 0;
          memmove_0(v24 + 20, v24, *a12);
          *a12 += 20;
          v25 = *a11;
          *(_DWORD *)v25 = 1;
          *(GUID *)(v25 + 4) = g_guidDefaultProvider;
        }
        else
        {
          v19 = 8;
          DebugTraceError(8, "dwRetVal", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 2235);
          LocalFree(*a11);
          *a11 = 0;
          *a12 = 0;
        }
      }
      v26 = v14;
      v27 = v21;
      if ( (_DWORD)v14 )
      {
        do
        {
          *v27++ = 0;
          --v26;
        }
        while ( v26 );
      }
      LocalFree(v21);
    }
    else
    {
      v19 = 14;
    }
  }
  else
  {
    v19 = 87;
  }
  if ( v29 )
    CPSImpersonateCallingClient(v28, 1);
  CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v28);
  if ( v19 )
    goto LABEL_6;
  return 1;
}

```

## disassembly

```asm
0x180010870  push    rbx
0x180010872  push    rbp
0x180010873  push    rsi
0x180010874  push    rdi
0x180010875  push    r12
0x180010877  push    r13
0x180010879  push    r14
0x18001087b  push    r15
0x18001087d  sub     rsp, 2F8h
0x180010884  mov     rax, cs:__security_cookie
0x18001088b  xor     rax, rsp
0x18001088e  mov     [rsp+338h+var_58], rax
0x180010896  mov     rax, [rsp+338h+arg_40]
0x18001089e  mov     r13, r8
0x1800108a1  mov     rdi, [rsp+338h+arg_50]
0x1800108a9  mov     r15, rcx
0x1800108ac  mov     rsi, [rsp+338h+arg_58]
0x1800108b4  lea     rcx, [rsp+338h+var_2C8]; void *
0x1800108b9  mov     r14d, edx
0x1800108bc  mov     r8d, 270h; Size
0x1800108c2  xor     edx, edx; Val
0x1800108c4  mov     [rsp+338h+var_2D8], rax
0x1800108c9  mov     r12, r9
0x1800108cc  call    memset_0
0x1800108d1  cmp     cs:?g_fDPAPIInitialized@@3HA, 0; int g_fDPAPIInitialized
0x1800108d8  jnz     short loc_1800108F2
0x1800108da  mov     ecx, 54Fh; dwErrCode
0x1800108df  call    cs:__imp_SetLastError
0x1800108e6  nop     dword ptr [rax+rax+00h]
0x1800108eb  xor     al, al
0x1800108ed  jmp     loc_180010B36
0x1800108f2  xor     r9d, r9d; unsigned int *
0x1800108f5  lea     rcx, [rsp+338h+var_2C8]; struct CRYPT_SERVER_CONTEXT *
0x1800108fa  xor     r8d, r8d; unsigned __int16 **
0x1800108fd  xor     edx, edx; void *
0x1800108ff  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x180010904  mov     ebx, eax
0x180010906  test    eax, eax
0x180010908  jz      short loc_180010929
0x18001090a  mov     r9d, 86Ah
0x180010910  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180010917  lea     rdx, aDwretval; "dwRetVal"
0x18001091e  mov     ecx, eax
0x180010920  call    DebugTraceError
0x180010925  mov     ecx, ebx
0x180010927  jmp     short loc_1800108DF
0x180010929  test    rdi, rdi
0x18001092c  jz      loc_180010B04
0x180010932  test    r15, r15
0x180010935  jz      loc_180010B04
0x18001093b  test    r13, r13
0x18001093e  jz      loc_180010B04
0x180010944  cmp     [rsp+338h+var_2B4], 0
0x18001094c  jz      short loc_180010958
0x18001094e  lea     rcx, [rsp+338h+var_2C8]; void *
0x180010953  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x180010958  mov     qword ptr [rdi], 0
0x18001095f  mov     rdx, r14; uBytes
0x180010962  xor     ecx, ecx; uFlags
0x180010964  mov     dword ptr [rsi], 0
0x18001096a  call    cs:__imp_LocalAlloc
0x180010971  nop     dword ptr [rax+rax+00h]
0x180010976  mov     rbp, rax
0x180010979  test    rax, rax
0x18001097c  jnz     short loc_180010986
0x18001097e  lea     ebx, [rax+0Eh]
0x180010981  jmp     loc_180010B09
0x180010986  mov     r8, r14; Size
0x180010989  mov     rdx, r15; Src
0x18001098c  mov     rcx, rbp; void *
0x18001098f  call    memcpy_0
0x180010994  mov     eax, [rsp+338h+arg_48]
0x18001099b  xor     r15d, r15d
0x18001099e  mov     ecx, [rsp+338h+arg_38]
0x1800109a5  mov     r9, rbp; unsigned __int8 *
0x1800109a8  mov     [rsp+338h+var_2E0], eax; unsigned int
0x1800109ac  bts     ecx, 1Eh
0x1800109b0  mov     rax, [rsp+338h+var_2D8]
0x1800109b5  mov     r8, rsi; unsigned int *
0x1800109b8  mov     [rsp+338h+var_2E8], rax; unsigned __int8 *
0x1800109bd  mov     rdx, rdi; unsigned __int8 **
0x1800109c0  mov     eax, [rsp+338h+arg_20]
0x1800109c7  mov     [rsp+338h+var_2F0], ecx; unsigned int
0x1800109cb  lea     rcx, [rsp+338h+var_2C8]; void *
0x1800109d0  mov     [rsp+338h+var_2F8], r15; struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *
0x1800109d5  mov     [rsp+338h+var_300], eax; ULONG
0x1800109d9  mov     rax, [r13+8]
0x1800109dd  mov     [rsp+338h+var_308], r12; unsigned __int8 *
0x1800109e2  mov     [rsp+338h+Src], rax; Src
0x1800109e7  mov     [rsp+338h+var_318], r14d; unsigned int
0x1800109ec  call    ?SPCryptProtect@@YAKPEAXPEAPEAEPEAKPEAEKPEBG3KPEAU_SSCRYPTPROTECTDATA_PROMPTSTRUCT@@K3K@Z; SPCryptProtect(void *,uchar * *,ulong *,uchar *,ulong,ushort const *,uchar *,ulong,_SSCRYPTPROTECTDATA_PROMPTSTRUCT *,ulong,uchar *,ulong)
0x1800109f1  mov     ebx, eax
0x1800109f3  test    eax, eax
0x1800109f5  jz      short loc_180010A4C
0x1800109f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109fe  lea     rax, WPP_GLOBAL_Control
0x180010a05  cmp     rcx, rax
0x180010a08  jz      loc_180010ADC
0x180010a0e  test    byte ptr [rcx+1Ch], 1
0x180010a12  jz      loc_180010ADC
0x180010a18  mov     rcx, [rcx+10h]
0x180010a1c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180010a23  mov     dword ptr [rsp+338h+var_308], 8A8h
0x180010a2b  lea     r9, aDwretval; "dwRetVal"
0x180010a32  mov     [rsp+338h+Src], r8
0x180010a37  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180010a3e  mov     [rsp+338h+var_318], ebx
0x180010a42  call    WPP_SF_sDsd
0x180010a47  jmp     loc_180010ADC
0x180010a4c  mov     rcx, [rdi]; hMem
0x180010a4f  test    rcx, rcx
0x180010a52  jz      loc_180010ADC
0x180010a58  mov     eax, [rsi]
0x180010a5a  lea     edx, [rax+14h]; uBytes
0x180010a5d  cmp     edx, eax
0x180010a5f  jb      short loc_180010AA7
0x180010a61  mov     r8d, 2; uFlags
0x180010a67  call    cs:__imp_LocalReAlloc
0x180010a6e  nop     dword ptr [rax+rax+00h]
0x180010a73  test    rax, rax
0x180010a76  jz      short loc_180010AA7
0x180010a78  mov     [rdi], rax
0x180010a7b  lea     rcx, [rax+14h]; void *
0x180010a7f  mov     r8d, [rsi]; Size
0x180010a82  mov     rdx, rax; Src
0x180010a85  mov     ebx, r15d
0x180010a88  call    memmove_0
0x180010a8d  add     dword ptr [rsi], 14h
0x180010a90  mov     rax, [rdi]
0x180010a93  mov     dword ptr [rax], 1
0x180010a99  movups  xmm0, xmmword ptr cs:?g_guidDefaultProvider@@3U_GUID@@A.Data1; _GUID g_guidDefaultProvider ...
0x180010aa0  movdqu  xmmword ptr [rax+4], xmm0
0x180010aa5  jmp     short loc_180010ADC
0x180010aa7  mov     ebx, 8
0x180010aac  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180010ab3  mov     ecx, ebx
0x180010ab5  lea     rdx, aDwretval; "dwRetVal"
0x180010abc  mov     r9d, 8BBh
0x180010ac2  call    DebugTraceError
0x180010ac7  mov     rcx, [rdi]; hMem
0x180010aca  call    cs:__imp_LocalFree
0x180010ad1  nop     dword ptr [rax+rax+00h]
0x180010ad6  mov     [rdi], r15
0x180010ad9  mov     [rsi], r15d
0x180010adc  mov     rcx, r14
0x180010adf  mov     rax, rbp
0x180010ae2  test    r14d, r14d
0x180010ae5  jz      short loc_180010AF3
0x180010ae7  mov     [rax], r15b
0x180010aea  inc     rax
0x180010aed  sub     rcx, 1
0x180010af1  jnz     short loc_180010AE7
0x180010af3  mov     rcx, rbp; hMem
0x180010af6  call    cs:__imp_LocalFree
0x180010afd  nop     dword ptr [rax+rax+00h]
0x180010b02  jmp     short loc_180010B09
0x180010b04  mov     ebx, 57h ; 'W'
0x180010b09  cmp     [rsp+338h+var_2B4], 0
0x180010b11  jz      short loc_180010B22
0x180010b13  mov     edx, 1; int
0x180010b18  lea     rcx, [rsp+338h+var_2C8]; void *
0x180010b1d  call    ?CPSImpersonateCallingClient@@YAKPEAXH@Z; CPSImpersonateCallingClient(void *,int)
0x180010b22  lea     rcx, [rsp+338h+var_2C8]; struct CRYPT_SERVER_CONTEXT *
0x180010b27  call    ?CPSDeleteServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@@Z; CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *)
0x180010b2c  test    ebx, ebx
0x180010b2e  jnz     loc_180010925
0x180010b34  mov     al, 1
0x180010b36  mov     rcx, [rsp+338h+var_58]
0x180010b3e  xor     rcx, rsp; StackCookie
0x180010b41  call    __security_check_cookie
0x180010b46  add     rsp, 2F8h
0x180010b4d  pop     r15
0x180010b4f  pop     r14
0x180010b51  pop     r13
0x180010b53  pop     r12
0x180010b55  pop     rdi
0x180010b56  pop     rsi
0x180010b57  pop     rbp
0x180010b58  pop     rbx
0x180010b59  retn
```
