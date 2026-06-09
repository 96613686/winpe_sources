# CCAInfo::AddCertType(ushort const *)

- ea: `0x1800354fc`
- end: `0x1800356b0`
- name: `?AddCertType@CCAInfo@@QEAAJPEBG@Z`
- size: `436`
- prototype: `__int64 __fastcall(CCAInfo *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002d050`

## callees

- `0x18000596c`
- `0x180008400`
- `0x18000d520`
- `0x180013a86`
- `0x18002e340`
- `0x1800354fc`
- `0x180036460`

## import_xrefs

- `msvcrt!wcschr` at `0x180035567`
- `msvcrt!wcschr` at `0x18003557b`
- `msvcrt!wcschr` at `0x180035567`
- `msvcrt!wcschr` at `0x18003557b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035604`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035604`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003569b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003569b`

## string_xrefs

- `0x180035543`: `certificateTemplates`
- `0x18003563a`: `certificateTemplates`
- `0x180035666`: `certificateTemplates`

## pseudocode

```c
__int64 __fastcall CCAInfo::AddCertType(CCAInfo *this, unsigned __int16 *a2)
{
  unsigned __int16 **v2; // rsi
  unsigned int v5; // ebx
  unsigned int v6; // ecx
  int v7; // edx
  int Property; // eax
  wchar_t *v9; // rbx
  _QWORD *v10; // rcx
  __int64 i; // rbp
  __int64 v12; // r15
  const WCHAR *v13; // rcx
  __int64 v14; // rcx
  unsigned __int16 **v15; // rax
  unsigned __int16 *v17[9]; // [rsp+20h] [rbp-48h] BYREF
  void *Src; // [rsp+78h] [rbp+10h] BYREF

  v2 = 0;
  v17[0] = a2;
  v17[1] = 0;
  Src = 0;
  if ( a2 )
  {
    Property = CCAInfo::GetProperty(this, L"certificateTemplates", (unsigned __int16 ***)&Src);
    v5 = Property;
    if ( Property )
    {
      v6 = 122422053;
    }
    else
    {
      v9 = wcschr(a2, 0x7Cu);
      if ( v9 || (v9 = wcschr(a2, 0x7Du)) != 0 )
        ++v9;
      v10 = Src;
      if ( Src && *(_QWORD *)Src )
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v12 = i;
          v13 = (const WCHAR *)v10[i];
          if ( !v13 )
            break;
          if ( !(unsigned int)mylstrcmpNLSub(v13, a2, -1, 1)
            || v9 && !(unsigned int)mylstrcmpNLSub(*(PCNZWCH *)((char *)Src + v12 * 8), v9, -1, 1) )
          {
            v5 = 0;
            goto LABEL_25;
          }
          v10 = Src;
        }
        v15 = (unsigned __int16 **)LocalAlloc(0, 8LL * (unsigned int)(i + 2));
        v2 = v15;
        if ( !v15 )
        {
          v5 = -2147024882;
          v6 = 125174565;
          v7 = -2147024882;
          goto LABEL_24;
        }
        memcpy_0(v15, Src, 8 * i);
        v2[v12] = a2;
        v2[(unsigned int)(i + 1)] = 0;
        Property = CCAInfo::SetProperty(this, L"certificateTemplates", v2);
        v5 = Property;
        if ( !Property )
          goto LABEL_25;
        v6 = 125764389;
      }
      else
      {
        Property = CCAInfo::SetProperty(this, L"certificateTemplates", v17);
        v5 = Property;
        if ( !Property )
          goto LABEL_25;
        v6 = 123339557;
      }
    }
    v7 = Property;
    goto LABEL_24;
  }
  v5 = -2147467261;
  v6 = 122094373;
  v7 = -2147467261;
LABEL_24:
  CSPrintErrorLineFile(v6, v7);
LABEL_25:
  if ( Src )
    CAFreeCertTypeExtensions(v14, Src);
  if ( v2 )
    LocalFree(v2);
  return v5;
}

```

## disassembly

```asm
0x1800354fc  push    rbx
0x1800354fe  push    rbp
0x1800354ff  push    rsi
0x180035500  push    rdi
0x180035501  push    r14
0x180035503  push    r15
0x180035505  sub     rsp, 38h
0x180035509  xor     esi, esi
0x18003550b  mov     [rsp+68h+var_48], rdx
0x180035510  mov     [rsp+68h+var_40], 0
0x180035519  mov     rdi, rdx
0x18003551c  mov     [rsp+68h+Src], 0
0x180035525  mov     r14, rcx
0x180035528  test    rdx, rdx
0x18003552b  jnz     short loc_18003553E
0x18003552d  mov     ebx, 80004003h
0x180035532  mov     ecx, 7470325h; this
0x180035537  mov     edx, ebx
0x180035539  jmp     loc_18003567F
0x18003553e  lea     r8, [rsp+68h+Src]; unsigned __int16 ***
0x180035543  lea     rdx, aCertificatetem; "certificateTemplates"
0x18003554a  call    ?GetProperty@CCAInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCAInfo::GetProperty(ushort const *,ushort * * *)
0x18003554f  mov     ebx, eax
0x180035551  test    eax, eax
0x180035553  jz      short loc_18003555F
0x180035555  mov     ecx, 74C0325h
0x18003555a  jmp     loc_18003567D
0x18003555f  mov     edx, 7Ch ; '|'; Ch
0x180035564  mov     rcx, rdi; Str
0x180035567  call    cs:__imp_wcschr
0x18003556d  mov     rbx, rax
0x180035570  test    rax, rax
0x180035573  jnz     short loc_180035589
0x180035575  lea     edx, [rax+7Dh]; Ch
0x180035578  mov     rcx, rdi; Str
0x18003557b  call    cs:__imp_wcschr
0x180035581  mov     rbx, rax
0x180035584  test    rax, rax
0x180035587  jz      short loc_18003558D
0x180035589  add     rbx, 2
0x18003558d  mov     rcx, [rsp+68h+Src]
0x180035592  test    rcx, rcx
0x180035595  jz      loc_18003565E
0x18003559b  cmp     [rcx], rsi
0x18003559e  jz      loc_18003565E
0x1800355a4  xor     ebp, ebp
0x1800355a6  lea     r15, ds:0[rbp*8]
0x1800355ae  mov     rcx, [r15+rcx]; lpString1
0x1800355b2  test    rcx, rcx
0x1800355b5  jz      short loc_1800355FB
0x1800355b7  mov     r9b, 1; bool
0x1800355ba  or      r8d, 0FFFFFFFFh; int
0x1800355be  mov     rdx, rdi; unsigned __int16 *
0x1800355c1  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800355c6  test    eax, eax
0x1800355c8  jz      short loc_1800355F4
0x1800355ca  test    rbx, rbx
0x1800355cd  jz      short loc_1800355EB
0x1800355cf  mov     rcx, [rsp+68h+Src]
0x1800355d4  mov     r9b, 1; bool
0x1800355d7  or      r8d, 0FFFFFFFFh; int
0x1800355db  mov     rdx, rbx; unsigned __int16 *
0x1800355de  mov     rcx, [r15+rcx]; lpString1
0x1800355e2  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800355e7  test    eax, eax
0x1800355e9  jz      short loc_1800355F4
0x1800355eb  mov     rcx, [rsp+68h+Src]
0x1800355f0  inc     ebp
0x1800355f2  jmp     short loc_1800355A6
0x1800355f4  xor     ebx, ebx
0x1800355f6  jmp     loc_180035684
0x1800355fb  lea     edx, [rbp+2]
0x1800355fe  xor     ecx, ecx; uFlags
0x180035600  shl     rdx, 3; uBytes
0x180035604  call    cs:__imp_LocalAlloc
0x18003560a  mov     rsi, rax
0x18003560d  test    rax, rax
0x180035610  jnz     short loc_180035620
0x180035612  mov     ebx, 8007000Eh
0x180035617  mov     ecx, 7760325h
0x18003561c  mov     edx, ebx
0x18003561e  jmp     short loc_18003567F
0x180035620  mov     rdx, [rsp+68h+Src]; Src
0x180035625  mov     r8, r15; Size
0x180035628  mov     rcx, rsi; void *
0x18003562b  call    memcpy_0
0x180035630  lea     eax, [rbp+1]
0x180035633  mov     [r15+rsi], rdi
0x180035637  mov     r8, rsi; unsigned __int16 **
0x18003563a  lea     rdx, aCertificatetem; "certificateTemplates"
0x180035641  mov     rcx, r14; this
0x180035644  mov     qword ptr [rsi+rax*8], 0
0x18003564c  call    ?SetProperty@CCAInfo@@QEAAJPEBGPEAPEAG@Z; CCAInfo::SetProperty(ushort const *,ushort * *)
0x180035651  mov     ebx, eax
0x180035653  test    eax, eax
0x180035655  jz      short loc_180035684
0x180035657  mov     ecx, 77F0325h
0x18003565c  jmp     short loc_18003567D
0x18003565e  lea     r8, [rsp+68h+var_48]; unsigned __int16 **
0x180035663  mov     rcx, r14; this
0x180035666  lea     rdx, aCertificatetem; "certificateTemplates"
0x18003566d  call    ?SetProperty@CCAInfo@@QEAAJPEBGPEAPEAG@Z; CCAInfo::SetProperty(ushort const *,ushort * *)
0x180035672  mov     ebx, eax
0x180035674  test    eax, eax
0x180035676  jz      short loc_180035684
0x180035678  mov     ecx, 75A0325h; unsigned int
0x18003567d  mov     edx, eax; int
0x18003567f  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035684  mov     rdx, [rsp+68h+Src]
0x180035689  test    rdx, rdx
0x18003568c  jz      short loc_180035693
0x18003568e  call    CAFreeCertTypeExtensions
0x180035693  test    rsi, rsi
0x180035696  jz      short loc_1800356A1
0x180035698  mov     rcx, rsi; hMem
0x18003569b  call    cs:__imp_LocalFree
0x1800356a1  mov     eax, ebx
0x1800356a3  add     rsp, 38h
0x1800356a7  pop     r15
0x1800356a9  pop     r14
0x1800356ab  pop     rdi
0x1800356ac  pop     rsi
0x1800356ad  pop     rbp
0x1800356ae  pop     rbx
0x1800356af  retn
```
