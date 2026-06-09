# AllocAndOpenKnownStores(ulong *,void * * *)

- ea: `0x1800321cc`
- end: `0x180032310`
- name: `?AllocAndOpenKnownStores@@YAHPEAKPEAPEAPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(unsigned int *, void ***)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c7d0`
- `0x180032abc`

## callees

- `0x1800321cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800321e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800321e9`
- `CRYPT32!CertOpenStore` at `0x18003221d`
- `CRYPT32!CertOpenStore` at `0x180032250`
- `CRYPT32!CertOpenStore` at `0x180032280`
- `CRYPT32!CertOpenStore` at `0x1800322b0`
- `CRYPT32!CertOpenStore` at `0x1800322e1`
- `CRYPT32!CertOpenStore` at `0x18003221d`
- `CRYPT32!CertOpenStore` at `0x180032250`
- `CRYPT32!CertOpenStore` at `0x180032280`
- `CRYPT32!CertOpenStore` at `0x1800322b0`
- `CRYPT32!CertOpenStore` at `0x1800322e1`

## pseudocode

```c
__int64 __fastcall AllocAndOpenKnownStores(unsigned int *a1, void ***a2)
{
  void **v4; // rax
  HCERTSTORE v5; // rax
  HCERTSTORE v6; // rax
  HCERTSTORE v7; // rax
  HCERTSTORE v8; // rax
  HCERTSTORE v9; // rax

  v4 = (void **)LocalAlloc(0x40u, 0x28u);
  *a2 = v4;
  if ( !v4 )
    return 0;
  *a1 = 0;
  v5 = CertOpenStore((LPCSTR)9, 0, 0, 0x18001u, "ROOT");
  if ( !v5 )
    return 0;
  (*a2)[(*a1)++] = v5;
  v6 = CertOpenStore((LPCSTR)9, 0, 0, 0x18001u, "TRUST");
  if ( v6 )
    (*a2)[(*a1)++] = v6;
  v7 = CertOpenStore((LPCSTR)9, 0, 0, 0x18001u, "CA");
  if ( v7 )
    (*a2)[(*a1)++] = v7;
  v8 = CertOpenStore((LPCSTR)9, 0, 0, 0x18001u, "MY");
  if ( v8 )
    (*a2)[(*a1)++] = v8;
  v9 = CertOpenStore((LPCSTR)9, 0, 0, 0x28001u, "SPC");
  if ( v9 )
    (*a2)[(*a1)++] = v9;
  return 1;
}

```

## disassembly

```asm
0x1800321cc  mov     [rsp+arg_0], rbx
0x1800321d1  mov     [rsp+arg_8], rbp
0x1800321d6  push    rdi
0x1800321d7  sub     rsp, 30h
0x1800321db  mov     rdi, rdx
0x1800321de  mov     rbx, rcx
0x1800321e1  mov     edx, 28h ; '('; uBytes
0x1800321e6  lea     ecx, [rdx+18h]; uFlags
0x1800321e9  call    cs:__imp_LocalAlloc
0x1800321ef  mov     [rdi], rax
0x1800321f2  test    rax, rax
0x1800321f5  jz      loc_1800322FE
0x1800321fb  xor     edx, edx; dwEncodingType
0x1800321fd  mov     dword ptr [rbx], 0
0x180032203  lea     rax, aRoot; "ROOT"
0x18003220a  mov     r9d, 18001h; dwFlags
0x180032210  xor     r8d, r8d; hCryptProv
0x180032213  mov     [rsp+38h+pvPara], rax; pvPara
0x180032218  lea     ebp, [rdx+9]
0x18003221b  mov     ecx, ebp; lpszStoreProvider
0x18003221d  call    cs:__imp_CertOpenStore
0x180032223  test    rax, rax
0x180032226  jz      loc_1800322FE
0x18003222c  mov     edx, [rbx]
0x18003222e  mov     r9d, 18001h; dwFlags
0x180032234  mov     rcx, [rdi]
0x180032237  xor     r8d, r8d; hCryptProv
0x18003223a  mov     [rcx+rdx*8], rax
0x18003223e  lea     rax, aTrust; "TRUST"
0x180032245  inc     dword ptr [rbx]
0x180032247  xor     edx, edx; dwEncodingType
0x180032249  mov     ecx, ebp; lpszStoreProvider
0x18003224b  mov     [rsp+38h+pvPara], rax; pvPara
0x180032250  call    cs:__imp_CertOpenStore
0x180032256  test    rax, rax
0x180032259  jz      short loc_180032266
0x18003225b  mov     edx, [rbx]
0x18003225d  mov     rcx, [rdi]
0x180032260  mov     [rcx+rdx*8], rax
0x180032264  inc     dword ptr [rbx]
0x180032266  lea     rax, aCa; "CA"
0x18003226d  mov     r9d, 18001h; dwFlags
0x180032273  xor     r8d, r8d; hCryptProv
0x180032276  mov     [rsp+38h+pvPara], rax; pvPara
0x18003227b  xor     edx, edx; dwEncodingType
0x18003227d  mov     rcx, rbp; lpszStoreProvider
0x180032280  call    cs:__imp_CertOpenStore
0x180032286  test    rax, rax
0x180032289  jz      short loc_180032296
0x18003228b  mov     edx, [rbx]
0x18003228d  mov     rcx, [rdi]
0x180032290  mov     [rcx+rdx*8], rax
0x180032294  inc     dword ptr [rbx]
0x180032296  lea     rax, aMy; "MY"
0x18003229d  mov     r9d, 18001h; dwFlags
0x1800322a3  xor     r8d, r8d; hCryptProv
0x1800322a6  mov     [rsp+38h+pvPara], rax; pvPara
0x1800322ab  xor     edx, edx; dwEncodingType
0x1800322ad  mov     rcx, rbp; lpszStoreProvider
0x1800322b0  call    cs:__imp_CertOpenStore
0x1800322b6  test    rax, rax
0x1800322b9  jz      short loc_1800322C7
0x1800322bb  mov     r8d, [rbx]
0x1800322be  mov     rdx, [rdi]
0x1800322c1  mov     [rdx+r8*8], rax
0x1800322c5  inc     dword ptr [rbx]
0x1800322c7  lea     rax, aSpc; "SPC"
0x1800322ce  mov     r9d, 28001h; dwFlags
0x1800322d4  xor     r8d, r8d; hCryptProv
0x1800322d7  mov     [rsp+38h+pvPara], rax; pvPara
0x1800322dc  xor     edx, edx; dwEncodingType
0x1800322de  mov     rcx, rbp; lpszStoreProvider
0x1800322e1  call    cs:__imp_CertOpenStore
0x1800322e7  test    rax, rax
0x1800322ea  jz      short loc_1800322F7
0x1800322ec  mov     edx, [rbx]
0x1800322ee  mov     rcx, [rdi]
0x1800322f1  mov     [rcx+rdx*8], rax
0x1800322f5  inc     dword ptr [rbx]
0x1800322f7  mov     eax, 1
0x1800322fc  jmp     short loc_180032300
0x1800322fe  xor     eax, eax
0x180032300  mov     rbx, [rsp+38h+arg_0]
0x180032305  mov     rbp, [rsp+38h+arg_8]
0x18003230a  add     rsp, 30h
0x18003230e  pop     rdi
0x18003230f  retn
```
