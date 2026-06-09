# NgcUtils::DecryptData(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001b9b4`
- end: `0x18001bb1e`
- name: `?DecryptData@NgcUtils@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z`
- size: `362`
- prototype: `__int64 __usercall@<rax>(BCRYPT_KEY_HANDLE hKey@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned int@<r9d>, SIZE_T uBytes, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004e40`

## callees

- `0x180006538`
- `0x18001b9b4`
- `0x180028380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bac9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bac9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ba38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ba38`
- `bcrypt!BCryptDecrypt` at `0x18001ba05`
- `bcrypt!BCryptDecrypt` at `0x18001baa1`
- `bcrypt!BCryptDecrypt` at `0x18001ba05`
- `bcrypt!BCryptDecrypt` at `0x18001baa1`

## string_xrefs

- `0x18001ba14`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001bab0`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001baf8`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::DecryptData(
        BCRYPT_KEY_HANDLE hKey,
        PUCHAR pbInput,
        ULONG cbInput,
        __int64 a4,
        SIZE_T uBytes,
        UCHAR **a6,
        unsigned __int8 **a7)
{
  NTSTATUS v10; // eax
  __int64 v12; // rdi
  UCHAR *v13; // rax
  UCHAR *pbOutput; // rbx
  UCHAR *i; // rcx
  NTSTATUS v16; // eax
  unsigned int v17; // edi
  unsigned __int8 **v18; // rcx
  int pbIV; // [rsp+20h] [rbp-58h]
  int pbIVa; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  LODWORD(uBytes) = 0;
  v10 = BCryptDecrypt(hKey, pbInput, cbInput, 0, 0, 0, 0, 0, (ULONG *)&uBytes, 1u);
  if ( v10 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x30C,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v10,
             pbIV);
  v12 = (unsigned int)uBytes;
  v13 = (UCHAR *)LocalAlloc(0, (unsigned int)uBytes);
  pbOutput = v13;
  if ( v13 )
  {
    for ( i = &v13[v12]; v13 != i; ++v13 )
      *v13 = 0;
    v16 = BCryptDecrypt(hKey, pbInput, cbInput, 0, 0, 0, pbOutput, uBytes, (ULONG *)&uBytes, 1u);
    if ( v16 >= 0 )
    {
      v18 = a7;
      *a6 = pbOutput;
      *(_DWORD *)v18 = uBytes;
      return 0;
    }
    else
    {
      v17 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x31B,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
              (const char *)(unsigned int)v16,
              pbIVa);
      LocalFree(pbOutput);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      pbIV);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001b9b4  mov     r11, rsp
0x18001b9b7  push    rbx
0x18001b9b8  push    rbp
0x18001b9b9  push    rsi
0x18001b9ba  push    rdi
0x18001b9bb  push    r14
0x18001b9bd  sub     rsp, 50h
0x18001b9c1  mov     [rsp+78h+dwFlags], 1; dwFlags
0x18001b9c9  lea     rax, [r11+28h]
0x18001b9cd  mov     [r11-38h], rax
0x18001b9d1  xor     r9d, r9d; pPaddingInfo
0x18001b9d4  mov     [rsp+78h+cbOutput], 0; cbOutput
0x18001b9dc  mov     esi, r8d
0x18001b9df  mov     qword ptr [r11-48h], 0
0x18001b9e7  mov     rbp, rdx
0x18001b9ea  mov     [rsp+78h+cbIV], 0; cbIV
0x18001b9f2  mov     r14, rcx
0x18001b9f5  mov     qword ptr [r11-58h], 0
0x18001b9fd  mov     dword ptr [r11+28h], 0
0x18001ba05  call    cs:__imp_BCryptDecrypt
0x18001ba0b  test    eax, eax
0x18001ba0d  jns     short loc_18001BA2D
0x18001ba0f  mov     rcx, [rsp+78h]; this
0x18001ba14  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001ba1b  mov     r9d, eax; char *
0x18001ba1e  mov     edx, 30Ch; void *
0x18001ba23  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001ba28  jmp     loc_18001BB13
0x18001ba2d  mov     edi, dword ptr [rsp+78h+uBytes]
0x18001ba34  xor     ecx, ecx; uFlags
0x18001ba36  mov     edx, edi; uBytes
0x18001ba38  call    cs:__imp_LocalAlloc
0x18001ba3e  mov     rbx, rax
0x18001ba41  test    rax, rax
0x18001ba44  jz      loc_18001BAF3
0x18001ba4a  lea     rcx, [rdi+rax]
0x18001ba4e  cmp     rax, rcx
0x18001ba51  jz      short loc_18001BA5F
0x18001ba53  xor     edx, edx
0x18001ba55  mov     [rax], dl
0x18001ba57  inc     rax
0x18001ba5a  cmp     rax, rcx
0x18001ba5d  jnz     short loc_18001BA53
0x18001ba5f  mov     eax, dword ptr [rsp+78h+uBytes]
0x18001ba66  lea     rcx, [rsp+78h+uBytes]
0x18001ba6e  mov     [rsp+78h+dwFlags], 1; dwFlags
0x18001ba76  xor     r9d, r9d; pPaddingInfo
0x18001ba79  mov     [rsp+78h+pcbResult], rcx; pcbResult
0x18001ba7e  mov     r8d, esi; cbInput
0x18001ba81  mov     [rsp+78h+cbOutput], eax; cbOutput
0x18001ba85  mov     rdx, rbp; pbInput
0x18001ba88  mov     [rsp+78h+pbOutput], rbx; pbOutput
0x18001ba8d  mov     rcx, r14; hKey
0x18001ba90  mov     [rsp+78h+cbIV], 0; cbIV
0x18001ba98  mov     [rsp+78h+pbIV], 0; int
0x18001baa1  call    cs:__imp_BCryptDecrypt
0x18001baa7  test    eax, eax
0x18001baa9  jns     short loc_18001BAD3
0x18001baab  mov     rcx, [rsp+78h]; this
0x18001bab0  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001bab7  mov     r9d, eax; char *
0x18001baba  mov     edx, 31Bh; void *
0x18001babf  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001bac4  mov     rcx, rbx; hMem
0x18001bac7  mov     edi, eax
0x18001bac9  call    cs:__imp_LocalFree
0x18001bacf  mov     eax, edi
0x18001bad1  jmp     short loc_18001BB13
0x18001bad3  mov     rax, [rsp+78h+arg_28]
0x18001badb  mov     rcx, [rsp+78h+arg_30]
0x18001bae3  mov     [rax], rbx
0x18001bae6  mov     eax, dword ptr [rsp+78h+uBytes]
0x18001baed  mov     [rcx], eax
0x18001baef  xor     eax, eax
0x18001baf1  jmp     short loc_18001BB13
0x18001baf3  mov     rcx, [rsp+78h]; this
0x18001baf8  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001baff  mov     ebx, 8007000Eh
0x18001bb04  mov     edx, 30Fh; void *
0x18001bb09  mov     r9d, ebx; char *
0x18001bb0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb11  mov     eax, ebx
0x18001bb13  add     rsp, 50h
0x18001bb17  pop     r14
0x18001bb19  pop     rdi
0x18001bb1a  pop     rsi
0x18001bb1b  pop     rbp
0x18001bb1c  pop     rbx
0x18001bb1d  retn
```
