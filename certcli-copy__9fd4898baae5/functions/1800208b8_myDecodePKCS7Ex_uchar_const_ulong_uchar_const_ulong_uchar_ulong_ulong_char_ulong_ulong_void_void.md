# myDecodePKCS7Ex(uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *,ulong *,char * *,ulong *,ulong *,void * *,void * *)

- ea: `0x1800208b8`
- end: `0x180020a63`
- name: `?myDecodePKCS7Ex@@YAJPEBEK0KPEAPEAEPEAK2PEAPEAD22PEAPEAX4@Z`
- size: `427`
- prototype: `__int64 __usercall@<rax>(BYTE *pbData@<rcx>, DWORD cbData@<edx>, const unsigned __int8 *@<r8>, unsigned int@<r9d>, HLOCAL hMem, unsigned int *, unsigned int *, char **, unsigned int *, unsigned int *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180029be4`

## callees

- `0x1800208b8`
- `0x180021438`
- `0x18002966c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a46`
- `CRYPT32!CryptMsgClose` at `0x180020a2a`
- `CRYPT32!CryptMsgClose` at `0x180020a2a`
- `CRYPT32!CryptMsgUpdate` at `0x18002095c`
- `CRYPT32!CryptMsgUpdate` at `0x18002095c`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180020926`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180020926`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180020942`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180020974`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800209a9`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800209de`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180020942`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180020974`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800209a9`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800209de`

## pseudocode

```c
__int64 __fastcall myDecodePKCS7Ex(
        BYTE *pbData,
        DWORD cbData,
        const unsigned __int8 *a3,
        __int64 a4,
        HLOCAL hMem,
        unsigned int *a6,
        unsigned int *a7,
        char **a8,
        unsigned int *a9,
        unsigned int *a10,
        void **a11,
        void **a12)
{
  HCRYPTMSG v14; // rax
  void *v15; // rdi
  unsigned int v16; // ebx
  int Param; // eax
  unsigned int v18; // eax

  if ( a8 )
    *a8 = 0;
  if ( a12 )
    *a12 = 0;
  v14 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v15 = v14;
  if ( !v14 )
  {
    v16 = myHLastError();
    CSPrintErrorLineFile(0x8E801CAu, v16);
    return v16;
  }
  if ( !CryptMsgUpdate(v14, pbData, cbData, 1) )
  {
    v16 = myHLastError();
    CSPrintErrorLineFile(0x8EE01CAu, v16);
LABEL_18:
    CryptMsgClose(v15);
    return v16;
  }
  Param = myCryptMsgGetParam(v15, 4);
  if ( Param )
    CSPrintErrorLineFile(0x8FF01CAu, Param);
  v18 = myCryptMsgGetParam(v15, 2);
  v16 = v18;
  if ( v18 )
  {
    CSPrintErrorLineFile(0x91001CAu, v18);
    goto LABEL_18;
  }
  LocalFree(0);
  if ( a12 )
  {
    *a12 = v15;
    v15 = 0;
  }
  if ( a8 )
    *a8 = 0;
  v16 = 0;
  if ( v15 )
    goto LABEL_18;
  return v16;
}

```

## disassembly

```asm
0x1800208b8  mov     [rsp-38h+arg_0], rbx
0x1800208bd  mov     [rsp-38h+arg_18], r9d
0x1800208c2  mov     [rsp-38h+arg_10], r8
0x1800208c7  push    rbp
0x1800208c8  push    rsi
0x1800208c9  push    rdi
0x1800208ca  push    r12
0x1800208cc  push    r13
0x1800208ce  push    r14
0x1800208d0  push    r15
0x1800208d2  mov     rbp, rsp
0x1800208d5  sub     rsp, 30h
0x1800208d9  mov     r12, [rbp+arg_38]
0x1800208dd  xor     eax, eax
0x1800208df  mov     [rbp+hMem], rax
0x1800208e3  mov     ebx, edx
0x1800208e5  mov     [rbp+arg_18], eax
0x1800208e8  mov     r13, rcx
0x1800208eb  mov     [rbp+arg_28], rax
0x1800208ef  mov     r14d, eax
0x1800208f2  mov     dword ptr [rbp+arg_10], eax
0x1800208f5  mov     esi, eax
0x1800208f7  test    r12, r12
0x1800208fa  jz      short loc_180020900
0x1800208fc  mov     [r12], rax
0x180020900  mov     r15, [rbp+arg_58]
0x180020907  test    r15, r15
0x18002090a  jz      short loc_18002090F
0x18002090c  mov     [r15], rax
0x18002090f  mov     [rsp+30h+pStreamInfo], rax; pStreamInfo
0x180020914  xor     r9d, r9d; hCryptProv
0x180020917  xor     r8d, r8d; dwMsgType
0x18002091a  mov     [rsp+30h+pRecipientInfo], rax; pRecipientInfo
0x18002091f  xor     edx, edx; dwFlags
0x180020921  mov     ecx, 10001h; dwMsgEncodingType
0x180020926  call    cs:__imp_CryptMsgOpenToDecode
0x18002092c  mov     rdi, rax
0x18002092f  test    rax, rax
0x180020932  jnz     short loc_18002094D
0x180020934  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180020939  mov     edx, eax
0x18002093b  mov     ecx, 8E801CAh
0x180020940  mov     ebx, eax
0x180020942  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180020948  jmp     loc_180020A4C
0x18002094d  mov     r9d, 1; fFinal
0x180020953  mov     r8d, ebx; cbData
0x180020956  mov     rdx, r13; pbData
0x180020959  mov     rcx, rdi; hCryptMsg
0x18002095c  call    cs:__imp_CryptMsgUpdate
0x180020962  test    eax, eax
0x180020964  jnz     short loc_18002097F
0x180020966  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002096b  mov     edx, eax
0x18002096d  mov     ecx, 8EE01CAh
0x180020972  mov     ebx, eax
0x180020974  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002097a  jmp     loc_180020A27
0x18002097f  lea     rax, [rbp+arg_10]
0x180020983  mov     edx, 4
0x180020988  mov     [rsp+30h+pStreamInfo], rax
0x18002098d  mov     rcx, rdi
0x180020990  lea     rax, [rbp+arg_28]
0x180020994  mov     [rsp+30h+pRecipientInfo], rax
0x180020999  call    ?myCryptMsgGetParam@@YAJPEAXKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myCryptMsgGetParam(void *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x18002099e  test    eax, eax
0x1800209a0  jz      short loc_1800209AF
0x1800209a2  mov     edx, eax
0x1800209a4  mov     ecx, 8FF01CAh
0x1800209a9  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800209af  lea     rax, [rbp+arg_18]
0x1800209b3  mov     [rbp+arg_18], esi
0x1800209b6  mov     [rsp+30h+pStreamInfo], rax
0x1800209bb  mov     edx, 2
0x1800209c0  lea     rax, [rbp+hMem]
0x1800209c4  mov     rcx, rdi
0x1800209c7  mov     [rsp+30h+pRecipientInfo], rax
0x1800209cc  call    ?myCryptMsgGetParam@@YAJPEAXKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myCryptMsgGetParam(void *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x1800209d1  mov     ebx, eax
0x1800209d3  test    eax, eax
0x1800209d5  jz      short loc_1800209EE
0x1800209d7  mov     edx, eax
0x1800209d9  mov     ecx, 91001CAh
0x1800209de  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800209e4  mov     r14, [rbp+hMem]
0x1800209e8  mov     rsi, [rbp+arg_28]
0x1800209ec  jmp     short loc_180020A27
0x1800209ee  cmp     [rbp+arg_18], esi
0x1800209f1  jnz     short loc_1800209FF
0x1800209f3  mov     rcx, [rbp+hMem]; hMem
0x1800209f7  call    cs:__imp_LocalFree
0x1800209fd  jmp     short loc_180020A03
0x1800209ff  mov     r14, [rbp+hMem]
0x180020a03  test    r15, r15
0x180020a06  jz      short loc_180020A0D
0x180020a08  mov     [r15], rdi
0x180020a0b  xor     edi, edi
0x180020a0d  test    r12, r12
0x180020a10  jz      short loc_180020A1C
0x180020a12  mov     rax, [rbp+arg_28]
0x180020a16  mov     [r12], rax
0x180020a1a  jmp     short loc_180020A20
0x180020a1c  mov     rsi, [rbp+arg_28]
0x180020a20  xor     ebx, ebx
0x180020a22  test    rdi, rdi
0x180020a25  jz      short loc_180020A30
0x180020a27  mov     rcx, rdi; hCryptMsg
0x180020a2a  call    cs:__imp_CryptMsgClose
0x180020a30  test    r14, r14
0x180020a33  jz      short loc_180020A3E
0x180020a35  mov     rcx, r14; hMem
0x180020a38  call    cs:__imp_LocalFree
0x180020a3e  test    rsi, rsi
0x180020a41  jz      short loc_180020A4C
0x180020a43  mov     rcx, rsi; hMem
0x180020a46  call    cs:__imp_LocalFree
0x180020a4c  mov     eax, ebx
0x180020a4e  mov     rbx, [rsp+30h+arg_0]
0x180020a53  add     rsp, 30h
0x180020a57  pop     r15
0x180020a59  pop     r14
0x180020a5b  pop     r13
0x180020a5d  pop     r12
0x180020a5f  pop     rdi
0x180020a60  pop     rsi
0x180020a61  pop     rbp
0x180020a62  retn
```
