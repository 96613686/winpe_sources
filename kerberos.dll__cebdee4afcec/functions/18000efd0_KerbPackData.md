# KerbPackData

- ea: `0x18000efd0`
- end: `0x18000f1ee`
- name: `KerbPackData`
- size: `542`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *, _QWORD *)`
- caller_count: `33`
- callee_count: `6`
- tags: ``

## callers

- `0x180009fe4`
- `0x18000e9e0`
- `0x180014380`
- `0x180019678`
- `0x18003a1f0`
- `0x18003d3f0`
- `0x18003e170`
- `0x180042a40`
- `0x1800520f4`
- `0x180066a14`
- `0x18006a79c`
- `0x18006e98c`
- `0x180086258`
- `0x180086478`
- `0x18008663c`
- `0x180086d4c`
- `0x180087070`
- `0x18008e4f4`
- `0x1800904f4`
- `0x18009fa48`
- `0x1800b0688`
- `0x1800b6600`
- `0x1800bc57c`
- `0x1800bfc00`
- `0x1800c30d8`
- `0x1800c8650`
- `0x1800c9070`
- `0x1800c90c0`
- `0x1800c9800`
- `0x1800c9a10`
- `0x1800ca5b0`
- `0x1800cabf0`
- `0x1800daa64`

## callees

- `0x18000efd0`
- `0x18006ccec`
- `0x18007108c`
- `0x1800744cf`
- `0x180077804`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f148`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f148`
- `MSASN1!ASN1_CreateModule` at `0x18000f051`
- `MSASN1!ASN1_CreateModule` at `0x18000f051`
- `MSASN1!ASN1_CreateEncoder` at `0x18000f071`
- `MSASN1!ASN1_CreateEncoder` at `0x18000f071`
- `MSASN1!ASN1_FreeEncoded` at `0x18000f0fd`
- `MSASN1!ASN1_FreeEncoded` at `0x18000f0fd`
- `MSASN1!ASN1_Encode` at `0x18000f099`
- `MSASN1!ASN1_Encode` at `0x18000f099`
- `MSASN1!ASN1_CloseEncoder` at `0x18000f11a`
- `MSASN1!ASN1_CloseEncoder` at `0x18000f11a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KerbPackData(__int64 a1, unsigned int a2, _DWORD *a3, _QWORD *a4)
{
  __int64 Module; // rax
  unsigned int Encoder; // eax
  int v10; // eax
  void *v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  SIZE_T v16; // rbx
  HLOCAL v17; // rax
  _QWORD v18[7]; // [rsp+50h] [rbp-38h] BYREF

  v18[0] = 0;
  if ( fKRB5ModuleStarted )
  {
    Module = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               81,
               off_1800F62D0,
               off_1800F6040,
               off_1800F6560,
               qword_1800FE8B0,
               895644267);
    KRB5_Module = Module;
  }
  Encoder = ASN1_CreateEncoder(Module, v18, 0, 0, 0);
  if ( !Encoder )
  {
    v10 = ASN1_Encode(v18[0], a1, a2, 16, 0, 0);
    if ( v10 >= 0 )
    {
      if ( KerbGlobalPackageState == 1 )
      {
        v11 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)(*(unsigned int *)(v18[0] + 28LL));
      }
      else
      {
        v16 = *(unsigned int *)(v18[0] + 28LL);
        v17 = LocalAlloc(0, v16);
        v11 = v17;
        if ( v17 )
        {
          memset_0(v17, 0, v16);
          *a4 = v11;
          goto LABEL_8;
        }
      }
      *a4 = v11;
      if ( !v11 )
      {
        v13 = v18[0];
        v12 = 60;
        v14 = 0;
        goto LABEL_9;
      }
LABEL_8:
      v12 = 0;
      memcpy_0(v11, *(const void **)(v18[0] + 16LL), *(unsigned int *)(v18[0] + 28LL));
      v13 = v18[0];
      v14 = *(_DWORD *)(v18[0] + 28LL);
LABEL_9:
      *a3 = v14;
      ASN1_FreeEncoded(v13, *(_QWORD *)(v13 + 16));
      goto LABEL_10;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
        (unsigned int)v10);
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
LABEL_14:
    v12 = 60;
    goto LABEL_10;
  }
  WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, Encoder);
  v12 = 60;
LABEL_10:
  if ( v18[0] )
    ASN1_CloseEncoder();
  return v12;
}

```

## disassembly

```asm
0x18000efd0  push    rbx
0x18000efd2  push    rbp
0x18000efd3  push    rsi
0x18000efd4  push    rdi
0x18000efd5  push    r14
0x18000efd7  sub     rsp, 60h
0x18000efdb  xor     ebp, ebp
0x18000efdd  mov     rsi, r9
0x18000efe0  cmp     cs:?fKRB5ModuleStarted@@3HA, ebp; int fKRB5ModuleStarted
0x18000efe6  mov     r14, r8
0x18000efe9  mov     ebx, edx
0x18000efeb  mov     [rsp+88h+var_38], rbp
0x18000eff0  mov     rdi, rcx
0x18000eff3  jnz     loc_18000F180
0x18000eff9  mov     [rsp+88h+var_48], 3562726Bh
0x18000f001  lea     rax, qword_1800FE8B0
0x18000f008  mov     [rsp+88h+var_50], rax
0x18000f00d  mov     edx, 400h
0x18000f012  lea     rax, off_1800F6560
0x18000f019  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18000f023  mov     [rsp+88h+var_58], rax
0x18000f028  mov     ecx, 10000h
0x18000f02d  lea     rax, off_1800F6040
0x18000f034  mov     r9d, 51h ; 'Q'
0x18000f03a  mov     [rsp+88h+var_60], rax
0x18000f03f  mov     r8d, 1000h
0x18000f045  lea     rax, off_1800F62D0
0x18000f04c  mov     [rsp+88h+var_68], rax
0x18000f051  call    cs:__imp_ASN1_CreateModule
0x18000f057  mov     cs:KRB5_Module, rax
0x18000f05e  xor     r9d, r9d
0x18000f061  mov     [rsp+88h+var_68], rbp
0x18000f066  xor     r8d, r8d
0x18000f069  lea     rdx, [rsp+88h+var_38]
0x18000f06e  mov     rcx, rax
0x18000f071  call    cs:__imp_ASN1_CreateEncoder
0x18000f077  test    eax, eax
0x18000f079  jnz     loc_18000F18C
0x18000f07f  mov     rcx, [rsp+88h+var_38]
0x18000f084  mov     r9d, 10h
0x18000f08a  mov     dword ptr [rsp+88h+var_60], ebp
0x18000f08e  mov     r8d, ebx
0x18000f091  mov     rdx, rdi
0x18000f094  mov     [rsp+88h+var_68], rbp
0x18000f099  call    cs:__imp_ASN1_Encode
0x18000f09f  test    eax, eax
0x18000f0a1  js      short loc_18000F122
0x18000f0a3  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000f0aa  mov     rax, [rsp+88h+var_38]
0x18000f0af  mov     ecx, [rax+1Ch]
0x18000f0b2  jnz     loc_18000F140
0x18000f0b8  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000f0bf  mov     rax, [rax+28h]
0x18000f0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0c8  mov     rdi, rax
0x18000f0cb  mov     [rsi], rdi
0x18000f0ce  test    rdi, rdi
0x18000f0d1  jz      loc_18000F16F
0x18000f0d7  mov     rdx, [rsp+88h+var_38]
0x18000f0dc  mov     rcx, rdi; void *
0x18000f0df  mov     ebx, ebp
0x18000f0e1  mov     r8d, [rdx+1Ch]; Size
0x18000f0e5  mov     rdx, [rdx+10h]; Src
0x18000f0e9  call    memcpy_0
0x18000f0ee  mov     rcx, [rsp+88h+var_38]
0x18000f0f3  mov     eax, [rcx+1Ch]
0x18000f0f6  mov     [r14], eax
0x18000f0f9  mov     rdx, [rcx+10h]
0x18000f0fd  call    cs:__imp_ASN1_FreeEncoded
0x18000f103  mov     rcx, [rsp+88h+var_38]
0x18000f108  test    rcx, rcx
0x18000f10b  jnz     short loc_18000F11A
0x18000f10d  mov     eax, ebx
0x18000f10f  add     rsp, 60h
0x18000f113  pop     r14
0x18000f115  pop     rdi
0x18000f116  pop     rsi
0x18000f117  pop     rbp
0x18000f118  pop     rbx
0x18000f119  retn
0x18000f11a  call    cs:__imp_ASN1_CloseEncoder
0x18000f120  jmp     short loc_18000F10D
0x18000f122  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f129  lea     rdx, WPP_GLOBAL_Control
0x18000f130  cmp     rcx, rdx
0x18000f133  jnz     loc_18000F1C7
0x18000f139  mov     ebx, 3Ch ; '<'
0x18000f13e  jmp     short loc_18000F103
0x18000f140  mov     rbx, rcx
0x18000f143  mov     rdx, rcx; uBytes
0x18000f146  xor     ecx, ecx; uFlags
0x18000f148  call    cs:__imp_LocalAlloc
0x18000f14e  mov     rdi, rax
0x18000f151  test    rax, rax
0x18000f154  jz      loc_18000F0CB
0x18000f15a  mov     r8, rbx; Size
0x18000f15d  xor     edx, edx; Val
0x18000f15f  mov     rcx, rax; void *
0x18000f162  call    memset_0
0x18000f167  mov     [rsi], rdi
0x18000f16a  jmp     loc_18000F0D7
0x18000f16f  mov     rcx, [rsp+88h+var_38]
0x18000f174  mov     ebx, 3Ch ; '<'
0x18000f179  mov     eax, ebp
0x18000f17b  jmp     loc_18000F0F6
0x18000f180  mov     rax, cs:KRB5_Module
0x18000f187  jmp     loc_18000F05E
0x18000f18c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f193  lea     rdx, WPP_GLOBAL_Control
0x18000f19a  cmp     rcx, rdx
0x18000f19d  jz      short loc_18000F139
0x18000f19f  test    byte ptr [rcx+1Ch], 1
0x18000f1a3  jz      short loc_18000F139
0x18000f1a5  mov     rcx, [rcx+10h]
0x18000f1a9  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18000f1b0  mov     edx, 24h ; '$'
0x18000f1b5  mov     r9d, eax
0x18000f1b8  call    WPP_SF_D
0x18000f1bd  mov     ebx, 3Ch ; '<'
0x18000f1c2  jmp     loc_18000F103
0x18000f1c7  test    byte ptr [rcx+1Ch], 1
0x18000f1cb  jz      loc_18000F139
0x18000f1d1  mov     rcx, [rcx+10h]
0x18000f1d5  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18000f1dc  mov     edx, 25h ; '%'
0x18000f1e1  mov     r9d, eax
0x18000f1e4  call    WPP_SF_d
0x18000f1e9  jmp     loc_18000F139
```
