# SPCryptSetProviderProperty

- ea: `0x18000c8c0`
- end: `0x18000cd96`
- name: `SPCryptSetProviderProperty`
- size: `1238`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _DWORD *, unsigned int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006b3c`
- `0x18000af80`
- `0x18000b250`
- `0x18000c8c0`
- `0x18000d3d0`
- `0x18000def0`
- `0x180025210`
- `0x1800398b0`
- `0x1800622e0`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000c91f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000c91f`
- `ntdll!RtlReleaseResource` at `0x18000c976`
- `ntdll!RtlReleaseResource` at `0x18000c976`

## string_xrefs

- `0x18000ca20`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000ca73`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000cad3`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000cb17`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000cb62`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000cc27`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000cc44`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000cc9a`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000ccb5`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000cd54`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000cd7c`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`

## pseudocode

```c
__int64 __fastcall SPCryptSetProviderProperty(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5)
{
  size_t v5; // r14
  int v10; // edx
  int v11; // r8d
  unsigned __int64 v12; // rax
  unsigned int v13; // ebx
  int v14; // edx
  int v15; // ebp
  int v16; // r8d
  int v17; // edx
  int v18; // r8d
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rcx
  int v22; // edx
  int v23; // r8d
  __int64 v24; // rax
  unsigned int SystemDirectory; // eax
  __int64 v26; // rcx
  void *v27; // rax
  __int64 v28; // r9
  const WCHAR *v29; // [rsp+60h] [rbp+8h] BYREF

  v5 = a4;
  if ( a1 && *(_DWORD *)a1 >= 0xA0u && *(_DWORD *)(a1 + 4) == 1263751248 )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(a1 + 64), 1u);
    if ( a2 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      if ( v12 > 0x40 )
      {
        v13 = -2146893785;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            v11,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
            55);
        goto LABEL_15;
      }
      v15 = wcscmp_0(a2, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION");
      if ( !a3 && v15 || (unsigned int)v5 > 0x7FFFFFFF )
      {
        v13 = -2146893785;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            v16,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
            69);
        goto LABEL_15;
      }
      if ( (a5 & 0xFFFFFFBF) != 0 )
      {
        v13 = -2146893815;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            v16,
            (unsigned int)"Status",
            9,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
            76);
        goto LABEL_15;
      }
      if ( !wcscmp_0(a2, L"Use Context") )
      {
        if ( !a3 || (unsigned int)v5 > 0x7FFFFFFD )
        {
          v13 = -2146893785;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v17,
              v18,
              (unsigned int)"Status",
              39,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
              86);
          goto LABEL_15;
        }
        v26 = *(_QWORD *)(a1 + 32);
        if ( v26 )
          MSCryptFree(v26);
        v27 = (void *)SafeAllocaAllocateFromHeap(v5 + 2);
        *(_QWORD *)(a1 + 32) = v27;
        if ( v27 )
        {
          memcpy_0(v27, a3, v5);
          *(_WORD *)(*(_QWORD *)(a1 + 32) + 2 * (v5 >> 1)) = 0;
          goto LABEL_23;
        }
        v28 = 1891;
      }
      else
      {
        if ( !wcscmp_0(a2, L"MSSP/Client Process ID") )
        {
          if ( (_DWORD)v5 != 4 )
          {
            v13 = -2146893819;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v19,
                v20,
                (unsigned int)"Status",
                5,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
                116);
            goto LABEL_15;
          }
          *(_DWORD *)(a1 + 60) = *a3;
          goto LABEL_23;
        }
        if ( v15 )
        {
          v13 = -2146893783;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v19,
              v20,
              (unsigned int)"Status",
              41,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
              169);
          goto LABEL_15;
        }
        v21 = *(_QWORD *)(a1 + 40);
        v29 = 0;
        if ( v21 )
        {
          MSCryptFree(v21);
          *(_QWORD *)(a1 + 40) = 0;
        }
        if ( !(_DWORD)v5 )
        {
LABEL_23:
          v13 = 0;
          goto LABEL_15;
        }
        v13 = ValidateAlternateStorageLocation(a3, (unsigned int)v5, &v29);
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v22,
              v23,
              (unsigned int)"Status",
              v13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
              143);
          goto LABEL_15;
        }
        v24 = SafeAllocaAllocateFromHeap(v5);
        *(_QWORD *)(a1 + 40) = v24;
        if ( v24 )
        {
          SystemDirectory = CreateSystemDirectory(v29, 0, 3u);
          v13 = SystemDirectory;
          if ( !SystemDirectory )
          {
            memcpy_0(*(void **)(a1 + 40), a3, v5);
            goto LABEL_23;
          }
          DebugTraceError(
            SystemDirectory,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
            1952);
LABEL_15:
          RtlReleaseResource((PRTL_RESOURCE)(a1 + 64));
          return v13;
        }
        v28 = 1943;
      }
      v13 = -2146893810;
      DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v28);
      goto LABEL_15;
    }
    v13 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 1841);
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
      42);
  return 2148073510LL;
}

```

## disassembly

```asm
0x18000c8c0  mov     [rsp+arg_18], rbx
0x18000c8c5  push    rdi
0x18000c8c6  push    r14
0x18000c8c8  push    r15
0x18000c8ca  sub     rsp, 40h
0x18000c8ce  mov     r14d, r9d
0x18000c8d1  mov     r15, r8
0x18000c8d4  mov     rbx, rdx
0x18000c8d7  mov     rdi, rcx
0x18000c8da  test    rcx, rcx
0x18000c8dd  jz      short loc_18000C8F0
0x18000c8df  cmp     dword ptr [rcx], 0A0h
0x18000c8e5  jb      short loc_18000C8F0
0x18000c8e7  cmp     dword ptr [rcx+4], 4B535050h
0x18000c8ee  jz      short loc_18000C914
0x18000c8f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8f7  lea     rax, WPP_GLOBAL_Control
0x18000c8fe  cmp     rcx, rax
0x18000c901  jz      short loc_18000C90D
0x18000c903  test    byte ptr [rcx+1Ch], 1
0x18000c907  jnz     loc_18000CC40
0x18000c90d  mov     eax, 80090026h
0x18000c912  jmp     short loc_18000C989
0x18000c914  mov     dl, 1; Wait
0x18000c916  mov     [rsp+58h+arg_10], rsi
0x18000c91b  add     rcx, 40h ; '@'; Resource
0x18000c91f  call    cs:__imp_RtlAcquireResourceExclusive
0x18000c926  nop     dword ptr [rax+rax+00h]
0x18000c92b  test    rbx, rbx
0x18000c92e  jz      loc_18000CCAF
0x18000c934  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c93b  nop     dword ptr [rax+rax+00h]
0x18000c940  inc     rax
0x18000c943  cmp     word ptr [rbx+rax*2], 0
0x18000c948  jnz     short loc_18000C940
0x18000c94a  cmp     rax, 40h ; '@'
0x18000c94e  jbe     short loc_18000C999
0x18000c950  mov     ebx, 80090027h
0x18000c955  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c95c  lea     rax, WPP_GLOBAL_Control
0x18000c963  cmp     rcx, rax
0x18000c966  jz      short loc_18000C972
0x18000c968  test    byte ptr [rcx+1Ch], 1
0x18000c96c  jnz     loc_18000CA1C
0x18000c972  lea     rcx, [rdi+40h]; Resource
0x18000c976  call    cs:__imp_RtlReleaseResource
0x18000c97d  nop     dword ptr [rax+rax+00h]
0x18000c982  mov     rsi, [rsp+58h+arg_10]
0x18000c987  mov     eax, ebx
0x18000c989  mov     rbx, [rsp+58h+arg_18]
0x18000c98e  add     rsp, 40h
0x18000c992  pop     r15
0x18000c994  pop     r14
0x18000c996  pop     rdi
0x18000c997  retn
0x18000c999  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x18000c9a0  mov     [rsp+58h+arg_8], rbp
0x18000c9a5  mov     rcx, rbx; String1
0x18000c9a8  call    wcscmp_0
0x18000c9ad  mov     ebp, eax
0x18000c9af  test    r15, r15
0x18000c9b2  jz      loc_18000CCD7
0x18000c9b8  cmp     r14d, 7FFFFFFFh
0x18000c9bf  ja      loc_18000CBF9
0x18000c9c5  test    [rsp+58h+arg_20], 0FFFFFFBFh
0x18000c9d0  jnz     short loc_18000CA4D
0x18000c9d2  lea     rdx, aUseContext; "Use Context"
0x18000c9d9  mov     rcx, rbx; String1
0x18000c9dc  call    wcscmp_0
0x18000c9e1  test    eax, eax
0x18000c9e3  jz      loc_18000CA9C
0x18000c9e9  lea     rdx, aMsspClientProc; "MSSP/Client Process ID"
0x18000c9f0  mov     rcx, rbx; String1
0x18000c9f3  call    wcscmp_0
0x18000c9f8  test    eax, eax
0x18000c9fa  jnz     loc_18000CB30
0x18000ca00  cmp     r14d, 4
0x18000ca04  jnz     loc_18000CAE9
0x18000ca0a  mov     eax, [r15]
0x18000ca0d  mov     [rdi+3Ch], eax
0x18000ca10  xor     ebx, ebx
0x18000ca12  mov     rbp, [rsp+58h+arg_8]
0x18000ca17  jmp     loc_18000C972
0x18000ca1c  mov     rcx, [rcx+10h]
0x18000ca20  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ca27  mov     [rsp+58h+var_28], 737h
0x18000ca2f  lea     r9, aStatus; "Status"
0x18000ca36  mov     [rsp+58h+var_30], rax
0x18000ca3b  mov     [rsp+58h+var_38], 80090027h
0x18000ca43  call    WPP_SF_sDsd
0x18000ca48  jmp     loc_18000C972
0x18000ca4d  mov     ebx, 80090009h
0x18000ca52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca59  lea     rax, WPP_GLOBAL_Control
0x18000ca60  cmp     rcx, rax
0x18000ca63  jz      short loc_18000CA12
0x18000ca65  test    byte ptr [rcx+1Ch], 1
0x18000ca69  jz      short loc_18000CA12
0x18000ca6b  mov     [rsp+58h+var_28], 74Ch
0x18000ca73  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ca7a  mov     [rsp+58h+var_30], rax
0x18000ca7f  mov     [rsp+58h+var_38], 80090009h
0x18000ca87  mov     rcx, [rcx+10h]
0x18000ca8b  lea     r9, aStatus; "Status"
0x18000ca92  call    WPP_SF_sDsd
0x18000ca97  jmp     loc_18000CA12
0x18000ca9c  test    r15, r15
0x18000ca9f  jnz     loc_18000CCE4
0x18000caa5  mov     ebx, 80090027h
0x18000caaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cab1  lea     rax, WPP_GLOBAL_Control
0x18000cab8  cmp     rcx, rax
0x18000cabb  jz      loc_18000CA12
0x18000cac1  test    byte ptr [rcx+1Ch], 1
0x18000cac5  jz      loc_18000CA12
0x18000cacb  mov     [rsp+58h+var_28], 756h
0x18000cad3  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cada  mov     [rsp+58h+var_30], rax
0x18000cadf  mov     [rsp+58h+var_38], 80090027h
0x18000cae7  jmp     short loc_18000CA87
0x18000cae9  mov     ebx, 80090005h
0x18000caee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caf5  lea     rax, WPP_GLOBAL_Control
0x18000cafc  cmp     rcx, rax
0x18000caff  jz      loc_18000CA12
0x18000cb05  test    byte ptr [rcx+1Ch], 1
0x18000cb09  jz      loc_18000CA12
0x18000cb0f  mov     [rsp+58h+var_28], 774h
0x18000cb17  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cb1e  mov     [rsp+58h+var_30], rax
0x18000cb23  mov     [rsp+58h+var_38], 80090005h
0x18000cb2b  jmp     loc_18000CA87
0x18000cb30  test    ebp, ebp
0x18000cb32  jz      short loc_18000CB7B
0x18000cb34  mov     ebx, 80090029h
0x18000cb39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb40  lea     rax, WPP_GLOBAL_Control
0x18000cb47  cmp     rcx, rax
0x18000cb4a  jz      loc_18000CA12
0x18000cb50  test    byte ptr [rcx+1Ch], 1
0x18000cb54  jz      loc_18000CA12
0x18000cb5a  mov     [rsp+58h+var_28], 7A9h
0x18000cb62  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cb69  mov     [rsp+58h+var_30], rax
0x18000cb6e  mov     [rsp+58h+var_38], 80090029h
0x18000cb76  jmp     loc_18000CA87
0x18000cb7b  mov     rcx, [rdi+28h]
0x18000cb7f  mov     [rsp+58h+arg_0], 0
0x18000cb88  test    rcx, rcx
0x18000cb8b  jnz     loc_18000CD3C
0x18000cb91  test    r14d, r14d
0x18000cb94  jz      loc_18000CA10
0x18000cb9a  lea     r8, [rsp+58h+arg_0]
0x18000cb9f  mov     edx, r14d
0x18000cba2  mov     rcx, r15
0x18000cba5  call    ValidateAlternateStorageLocation
0x18000cbaa  mov     ebx, eax
0x18000cbac  test    eax, eax
0x18000cbae  jnz     loc_18000CC71
0x18000cbb4  mov     rcx, r14
0x18000cbb7  call    SafeAllocaAllocateFromHeap
0x18000cbbc  mov     [rdi+28h], rax
0x18000cbc0  test    rax, rax
0x18000cbc3  jz      loc_18000CD4E
0x18000cbc9  mov     rcx, [rsp+58h+arg_0]
0x18000cbce  xor     edx, edx
0x18000cbd0  mov     r8d, 3
0x18000cbd6  call    CreateSystemDirectory
0x18000cbdb  mov     ebx, eax
0x18000cbdd  test    eax, eax
0x18000cbdf  jnz     loc_18000CD76
0x18000cbe5  mov     rcx, [rdi+28h]; void *
0x18000cbe9  mov     r8, r14; Size
0x18000cbec  mov     rdx, r15; Src
0x18000cbef  call    memcpy_0
0x18000cbf4  jmp     loc_18000CA10
0x18000cbf9  mov     ebx, 80090027h
0x18000cbfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc05  lea     rax, WPP_GLOBAL_Control
0x18000cc0c  cmp     rcx, rax
0x18000cc0f  jz      loc_18000CA12
0x18000cc15  test    byte ptr [rcx+1Ch], 1
0x18000cc19  jz      loc_18000CA12
0x18000cc1f  mov     [rsp+58h+var_28], 745h
0x18000cc27  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cc2e  mov     [rsp+58h+var_30], rax
0x18000cc33  mov     [rsp+58h+var_38], 80090027h
0x18000cc3b  jmp     loc_18000CA87
0x18000cc40  mov     rcx, [rcx+10h]
0x18000cc44  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cc4b  mov     [rsp+58h+var_28], 72Ah
0x18000cc53  lea     r9, aStatus; "Status"
0x18000cc5a  mov     [rsp+58h+var_30], rax
0x18000cc5f  mov     [rsp+58h+var_38], 80090026h
0x18000cc67  call    WPP_SF_sDsd
0x18000cc6c  jmp     loc_18000C90D
0x18000cc71  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc78  lea     rax, WPP_GLOBAL_Control
0x18000cc7f  cmp     rcx, rax
0x18000cc82  jz      loc_18000CA12
0x18000cc88  test    byte ptr [rcx+1Ch], 1
0x18000cc8c  jz      loc_18000CA12
0x18000cc92  mov     [rsp+58h+var_28], 78Fh
0x18000cc9a  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cca1  mov     [rsp+58h+var_30], rax
0x18000cca6  mov     [rsp+58h+var_38], ebx
0x18000ccaa  jmp     loc_18000CA87
0x18000ccaf  mov     r9d, 731h
0x18000ccb5  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ccbc  lea     rdx, aStatus; "Status"
0x18000ccc3  mov     ecx, 80090027h
0x18000ccc8  mov     ebx, 80090027h
0x18000cccd  call    DebugTraceError
0x18000ccd2  jmp     loc_18000C972
0x18000ccd7  test    ebp, ebp
0x18000ccd9  jnz     loc_18000CBF9
0x18000ccdf  jmp     loc_18000C9B8
0x18000cce4  cmp     r14d, 7FFFFFFDh
0x18000cceb  ja      loc_18000CAA5
0x18000ccf1  mov     rcx, [rdi+20h]
0x18000ccf5  test    rcx, rcx
0x18000ccf8  jz      short loc_18000CCFF
0x18000ccfa  call    MSCryptFree
0x18000ccff  lea     rcx, [r14+2]
0x18000cd03  mov     rbx, r14
0x18000cd06  call    SafeAllocaAllocateFromHeap
0x18000cd0b  mov     [rdi+20h], rax
0x18000cd0f  test    rax, rax
0x18000cd12  jnz     short loc_18000CD1C
0x18000cd14  mov     r9d, 763h
0x18000cd1a  jmp     short loc_18000CD54
0x18000cd1c  mov     r8, rbx; Size
0x18000cd1f  mov     rdx, r15; Src
0x18000cd22  mov     rcx, rax; void *
0x18000cd25  call    memcpy_0
0x18000cd2a  mov     rcx, [rdi+20h]
0x18000cd2e  shr     rbx, 1
0x18000cd31  xor     eax, eax
0x18000cd33  mov     [rcx+rbx*2], ax
0x18000cd37  jmp     loc_18000CA10
0x18000cd3c  call    MSCryptFree
0x18000cd41  mov     qword ptr [rdi+28h], 0
0x18000cd49  jmp     loc_18000CB91
0x18000cd4e  mov     r9d, 797h
0x18000cd54  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cd5b  mov     ecx, 8009000Eh
0x18000cd60  lea     rdx, aStatus; "Status"
0x18000cd67  mov     ebx, 8009000Eh
0x18000cd6c  call    DebugTraceError
0x18000cd71  jmp     loc_18000CA12
0x18000cd76  mov     r9d, 7A0h
0x18000cd7c  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cd83  lea     rdx, aStatus; "Status"
0x18000cd8a  mov     ecx, eax
0x18000cd8c  call    DebugTraceError
0x18000cd91  jmp     loc_18000CA12
```
