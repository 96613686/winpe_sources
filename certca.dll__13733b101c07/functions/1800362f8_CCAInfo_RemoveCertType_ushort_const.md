# CCAInfo::RemoveCertType(ushort const *)

- ea: `0x1800362f8`
- end: `0x18003645a`
- name: `?RemoveCertType@CCAInfo@@QEAAJPEBG@Z`
- size: `354`
- prototype: `__int64 __fastcall(CCAProperty **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002e970`

## callees

- `0x18000596c`
- `0x180008400`
- `0x18000d520`
- `0x18002e340`
- `0x1800362f8`
- `0x180036460`

## import_xrefs

- `msvcrt!wcschr` at `0x180036374`
- `msvcrt!wcschr` at `0x1800363a2`
- `msvcrt!wcschr` at `0x1800363b9`
- `msvcrt!wcschr` at `0x180036374`
- `msvcrt!wcschr` at `0x1800363a2`
- `msvcrt!wcschr` at `0x1800363b9`

## string_xrefs

- `0x180036339`: `certificateTemplates`
- `0x18003640e`: `certificateTemplates`

## pseudocode

```c
__int64 __fastcall CCAInfo::RemoveCertType(CCAProperty **this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // ecx
  int v6; // edx
  __int64 v7; // rcx
  unsigned int Property; // eax
  wchar_t *v9; // rax
  const unsigned __int16 *v10; // rbx
  unsigned __int16 **v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // rdi
  wchar_t *v14; // rax
  const WCHAR *v15; // rax
  int v16; // eax
  unsigned __int16 **v18; // [rsp+48h] [rbp+10h] BYREF

  v18 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 128058149;
    v6 = -2147467261;
LABEL_3:
    CSPrintErrorLineFile(v5, v6);
    goto LABEL_22;
  }
  Property = CCAInfo::GetProperty(this, L"certificateTemplates", &v18);
  v4 = Property;
  if ( Property )
  {
    v6 = Property;
    v5 = 128320293;
    goto LABEL_3;
  }
  if ( v18 && *v18 )
  {
    v9 = wcschr(a2, 0x7Du);
    if ( v9 )
      v10 = v9 + 1;
    else
      v10 = a2;
    v11 = v18;
    v12 = 0;
    v13 = 0;
    if ( *v18 )
    {
      do
      {
        v14 = wcschr(v11[v13], 0x7Cu);
        if ( v14 || (v14 = wcschr(v18[v13], 0x7Du)) != 0 )
          v15 = v14 + 1;
        else
          v15 = v18[v13];
        if ( (unsigned int)mylstrcmpNLSub(v15, v10, -1, 1u) )
        {
          v18[v12] = v18[v13];
          v12 = (unsigned int)(v12 + 1);
        }
        v11 = v18;
        v13 = (unsigned int)(v13 + 1);
      }
      while ( v18[v13] );
    }
    v11[v12] = 0;
    v16 = CCAInfo::SetProperty((CCAInfo *)this, L"certificateTemplates", v18);
    v4 = v16;
    if ( v16 )
    {
      v6 = v16;
      v5 = 131138341;
      goto LABEL_3;
    }
  }
  else
  {
    v4 = 0;
  }
LABEL_22:
  if ( v18 )
    CAFreeCertTypeExtensions(v7, v18);
  return v4;
}

```

## disassembly

```asm
0x1800362f8  mov     [rsp+arg_0], rbx
0x1800362fd  mov     [rsp+arg_10], rbp
0x180036302  push    rsi
0x180036303  push    rdi
0x180036304  push    r14
0x180036306  sub     rsp, 20h
0x18003630a  mov     [rsp+38h+arg_8], 0
0x180036313  mov     rdi, rdx
0x180036316  mov     r14, rcx
0x180036319  test    rdx, rdx
0x18003631c  jnz     short loc_180036334
0x18003631e  mov     ebx, 80004003h
0x180036323  mov     ecx, 7A20325h; unsigned int
0x180036328  mov     edx, ebx; int
0x18003632a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003632f  jmp     loc_180036436
0x180036334  lea     r8, [rsp+38h+arg_8]; unsigned __int16 ***
0x180036339  lea     rdx, aCertificatetem; "certificateTemplates"
0x180036340  call    ?GetProperty@CCAInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCAInfo::GetProperty(ushort const *,ushort * * *)
0x180036345  mov     ebx, eax
0x180036347  test    eax, eax
0x180036349  jz      short loc_180036354
0x18003634b  mov     edx, eax
0x18003634d  mov     ecx, 7A60325h
0x180036352  jmp     short loc_18003632A
0x180036354  mov     rdx, [rsp+38h+arg_8]
0x180036359  test    rdx, rdx
0x18003635c  jz      loc_180036434
0x180036362  cmp     qword ptr [rdx], 0
0x180036366  jz      loc_180036434
0x18003636c  mov     edx, 7Dh ; '}'; Ch
0x180036371  mov     rcx, rdi; Str
0x180036374  call    cs:__imp_wcschr
0x18003637a  mov     rbx, rax
0x18003637d  test    rax, rax
0x180036380  jz      short loc_180036388
0x180036382  add     rbx, 2
0x180036386  jmp     short loc_18003638B
0x180036388  mov     rbx, rdi
0x18003638b  mov     rcx, [rsp+38h+arg_8]
0x180036390  xor     esi, esi
0x180036392  xor     edi, edi
0x180036394  cmp     [rcx], rsi
0x180036397  jz      short loc_180036406
0x180036399  mov     rcx, [rcx+rdi*8]; Str
0x18003639d  mov     edx, 7Ch ; '|'; Ch
0x1800363a2  call    cs:__imp_wcschr
0x1800363a8  test    rax, rax
0x1800363ab  jnz     short loc_1800363CF
0x1800363ad  mov     rcx, [rsp+38h+arg_8]
0x1800363b2  lea     edx, [rax+7Dh]; Ch
0x1800363b5  mov     rcx, [rcx+rdi*8]; Str
0x1800363b9  call    cs:__imp_wcschr
0x1800363bf  test    rax, rax
0x1800363c2  jnz     short loc_1800363CF
0x1800363c4  mov     rax, [rsp+38h+arg_8]
0x1800363c9  mov     rax, [rax+rdi*8]
0x1800363cd  jmp     short loc_1800363D3
0x1800363cf  add     rax, 2
0x1800363d3  mov     r9b, 1; bool
0x1800363d6  or      r8d, 0FFFFFFFFh; int
0x1800363da  mov     rdx, rbx; unsigned __int16 *
0x1800363dd  mov     rcx, rax; lpString1
0x1800363e0  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800363e5  test    eax, eax
0x1800363e7  jz      short loc_1800363F8
0x1800363e9  mov     rcx, [rsp+38h+arg_8]
0x1800363ee  mov     rax, [rcx+rdi*8]
0x1800363f2  mov     [rcx+rsi*8], rax
0x1800363f6  inc     esi
0x1800363f8  mov     rcx, [rsp+38h+arg_8]
0x1800363fd  inc     edi
0x1800363ff  cmp     qword ptr [rcx+rdi*8], 0
0x180036404  jnz     short loc_180036399
0x180036406  mov     qword ptr [rcx+rsi*8], 0
0x18003640e  lea     rdx, aCertificatetem; "certificateTemplates"
0x180036415  mov     r8, [rsp+38h+arg_8]; unsigned __int16 **
0x18003641a  mov     rcx, r14; this
0x18003641d  call    ?SetProperty@CCAInfo@@QEAAJPEBGPEAPEAG@Z; CCAInfo::SetProperty(ushort const *,ushort * *)
0x180036422  mov     ebx, eax
0x180036424  test    eax, eax
0x180036426  jz      short loc_180036436
0x180036428  mov     edx, eax
0x18003642a  mov     ecx, 7D10325h
0x18003642f  jmp     loc_18003632A
0x180036434  xor     ebx, ebx
0x180036436  mov     rdx, [rsp+38h+arg_8]
0x18003643b  test    rdx, rdx
0x18003643e  jz      short loc_180036445
0x180036440  call    CAFreeCertTypeExtensions
0x180036445  mov     rbp, [rsp+38h+arg_10]
0x18003644a  mov     eax, ebx
0x18003644c  mov     rbx, [rsp+38h+arg_0]
0x180036451  add     rsp, 20h
0x180036455  pop     r14
0x180036457  pop     rdi
0x180036458  pop     rsi
0x180036459  retn
```
