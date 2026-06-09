# DsRolepCreateParentTrustObject

- ea: `0x1800217f0`
- end: `0x180021a68`
- name: `DsRolepCreateParentTrustObject`
- size: `632`
- prototype: `__int64 __fastcall(HANDLE hToken, LSA_HANDLE PolicyHandle, __int64, char, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180021a70`

## callees

- `0x18002043c`
- `0x180020dbc`
- `0x1800217f0`
- `0x180021f68`
- `0x18002c012`

## import_xrefs

- `msvcrt!malloc` at `0x1800218c7`
- `msvcrt!malloc` at `0x180021916`
- `msvcrt!malloc` at `0x1800219ff`
- `msvcrt!malloc` at `0x1800218c7`
- `msvcrt!malloc` at `0x180021916`
- `msvcrt!malloc` at `0x1800219ff`
- `msvcrt!free` at `0x180021908`
- `msvcrt!free` at `0x180021957`
- `msvcrt!free` at `0x180021a40`
- `msvcrt!free` at `0x180021908`
- `msvcrt!free` at `0x180021957`
- `msvcrt!free` at `0x180021a40`

## string_xrefs

- `0x1800219bb`: `Parent trust object already exists on parent\n`
- `0x180021a31`: `Parent LsaCreateTrustedDomainEx on %ws failed with 0x%lx\n`

## pseudocode

```c
__int64 __fastcall DsRolepCreateParentTrustObject(
        HANDLE hToken,
        LSA_HANDLE PolicyHandle,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 *a6)
{
  int v6; // eax
  __int64 v8; // r9
  WCHAR *v10; // rdx
  unsigned __int64 v12; // rcx
  _WORD *v13; // rax
  _WORD *v14; // rbx
  _WORD *v15; // rax
  _WORD *v16; // rbx
  int v17; // ebx
  bool v18; // sf
  unsigned int Length; // esi
  _WORD *v20; // rax
  _WORD *v21; // rdi
  struct _TRUSTED_DOMAIN_INFORMATION_EX Src; // [rsp+30h] [rbp-48h] BYREF
  __int64 v24; // [rsp+D0h] [rbp+58h] BYREF

  *(_QWORD *)&Src.TrustAttributes = 0;
  v6 = *(_DWORD *)(a3 + 18);
  v8 = *(unsigned __int16 *)(a3 + 16);
  v10 = *(WCHAR **)(a3 + 24);
  v24 = 0;
  memset(&Src, 0, 32);
  *(_DWORD *)&Src.Name.MaximumLength = v6;
  *(&Src.Name.MaximumLength + 2) = *(_WORD *)(a3 + 22);
  LOWORD(v6) = *(_WORD *)a3;
  Src.Name.Length = v8;
  Src.Name.Buffer = v10;
  Src.FlatName.Length = v6;
  *(_DWORD *)&Src.FlatName.MaximumLength = *(_DWORD *)(a3 + 2);
  *(&Src.FlatName.MaximumLength + 2) = *(_WORD *)(a3 + 6);
  Src.FlatName.Buffer = *(PWSTR *)(a3 + 8);
  *(_OWORD *)&Src.Sid = *(unsigned __int64 *)(a3 + 64);
  if ( (_WORD)v8 )
  {
    v12 = (unsigned __int64)(v8 - 1) >> 1;
    if ( v10[v12] == 46 )
    {
      v10[v12] = 0;
      Src.Name.Length -= 2;
    }
  }
  *(_QWORD *)&Src.TrustDirection = 0x200000003LL;
  Src.TrustAttributes = 32;
  DsRolepLogPrintRoutine(4, "Creating trusted domain object on parent\n");
  v13 = malloc(Src.Name.Length + 2LL);
  v14 = v13;
  if ( v13 )
  {
    memcpy_0(v13, Src.Name.Buffer, Src.Name.Length);
    v14[(unsigned __int64)Src.Name.Length >> 1] = 0;
    DsRolepLogPrintRoutine(4, "\tDnsDomain: %ws\n", v14, 0);
    free(v14);
  }
  v15 = malloc(Src.FlatName.Length + 2LL);
  v16 = v15;
  if ( v15 )
  {
    memcpy_0(v15, Src.FlatName.Buffer, Src.FlatName.Length);
    v16[(unsigned __int64)Src.FlatName.Length >> 1] = 0;
    DsRolepLogPrintRoutine(4, "\tFlat name: %ws\n", v16, 0);
    free(v16);
  }
  DsRolepLogPrintRoutine(4, "\tDirection: %lu\n", Src.TrustDirection);
  DsRolepLogPrintRoutine(4, "\tType: %lu\n", Src.TrustType);
  DsRolepLogPrintRoutine(4, "\tAttributes: 0x%lx\n", Src.TrustAttributes);
  v17 = ImpLsaCreateTrustedDomainEx(hToken, PolicyHandle, &Src, a5);
  if ( v17 == -1073741771 )
  {
    DsRolepLogPrintRoutine(4, "Parent trust object already exists on parent\n");
    v17 = DsRolepHandlePreExistingTrustObject(hToken, PolicyHandle, &Src, a4 & 0x20, (__int64)&v24);
  }
  else
  {
    v18 = v17 < 0;
    if ( !v17 )
      goto LABEL_14;
    Length = Src.Name.Length;
    v20 = malloc(Src.Name.Length + 2LL);
    v21 = v20;
    if ( v20 )
    {
      memcpy_0(v20, Src.Name.Buffer, Length);
      v21[(unsigned __int64)Src.Name.Length >> 1] = 0;
      DsRolepLogPrintRoutine(4, "Parent LsaCreateTrustedDomainEx on %ws failed with 0x%lx\n", v21, (unsigned int)v17);
      free(v21);
    }
  }
  v18 = v17 < 0;
LABEL_14:
  if ( !v18 )
    *a6 = v24;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800217f0  push    rbp
0x1800217f2  push    rbx
0x1800217f3  push    rsi
0x1800217f4  push    rdi
0x1800217f5  push    r12
0x1800217f7  push    r13
0x1800217f9  push    r14
0x1800217fb  push    r15
0x1800217fd  mov     rbp, rsp
0x180021800  sub     rsp, 78h
0x180021804  xor     eax, eax
0x180021806  xorps   xmm0, xmm0
0x180021809  mov     [rbp+var_18], rax
0x18002180d  xor     r12d, r12d
0x180021810  mov     eax, [r8+12h]
0x180021814  mov     esi, r9d
0x180021817  movzx   r9d, word ptr [r8+10h]
0x18002181c  mov     r14, rdx
0x18002181f  mov     rdx, [r8+18h]
0x180021823  mov     r15, rcx
0x180021826  mov     [rbp+arg_10], r12
0x18002182a  movups  xmmword ptr [rbp+Src], xmm0
0x18002182e  mov     dword ptr [rbp+Src+2], eax
0x180021831  movzx   eax, word ptr [r8+16h]
0x180021836  mov     word ptr [rbp+Src+6], ax
0x18002183a  movzx   eax, word ptr [r8]
0x18002183e  mov     word ptr [rbp+Src], r9w
0x180021843  mov     [rbp+Src+8], rdx
0x180021847  movups  xmmword ptr [rbp+var_38], xmm0
0x18002184b  mov     word ptr [rbp+var_38], ax
0x18002184f  mov     eax, [r8+2]
0x180021853  mov     dword ptr [rbp+var_38+2], eax
0x180021856  movzx   eax, word ptr [r8+6]
0x18002185b  mov     word ptr [rbp+var_38+6], ax
0x18002185f  mov     rax, [r8+8]
0x180021863  mov     [rbp+var_38+8], rax
0x180021867  mov     rax, [r8+40h]
0x18002186b  movups  [rbp+var_28], xmm0
0x18002186f  mov     qword ptr [rbp+var_28], rax
0x180021873  test    r9w, r9w
0x180021877  jz      short loc_180021895
0x180021879  lea     rcx, [r9-1]
0x18002187d  shr     rcx, 1
0x180021880  cmp     word ptr [rdx+rcx*2], 2Eh ; '.'
0x180021885  jnz     short loc_180021895
0x180021887  mov     eax, 0FFFEh
0x18002188c  mov     [rdx+rcx*2], r12w
0x180021891  add     word ptr [rbp+Src], ax
0x180021895  mov     r13d, 4
0x18002189b  mov     dword ptr [rbp+var_28+8], 3
0x1800218a2  mov     ecx, r13d
0x1800218a5  mov     dword ptr [rbp+var_28+0Ch], 2
0x1800218ac  lea     rdx, aCreatingTruste_0; "Creating trusted domain object on paren"...
0x1800218b3  mov     dword ptr [rbp+var_18], 20h ; ' '
0x1800218ba  call    DsRolepLogPrintRoutine
0x1800218bf  movzx   edi, word ptr [rbp+Src]
0x1800218c3  lea     rcx, [rdi+2]; Size
0x1800218c7  call    cs:__imp_malloc
0x1800218cd  mov     rbx, rax
0x1800218d0  test    rax, rax
0x1800218d3  jz      short loc_18002190E
0x1800218d5  mov     rdx, [rbp+Src+8]; Src
0x1800218d9  mov     r8d, edi; Size
0x1800218dc  mov     rcx, rax; void *
0x1800218df  call    memcpy_0
0x1800218e4  movzx   edx, word ptr [rbp+Src]
0x1800218e8  xor     r9d, r9d
0x1800218eb  shr     rdx, 1
0x1800218ee  mov     r8, rbx
0x1800218f1  mov     ecx, r13d
0x1800218f4  mov     [rbx+rdx*2], r12w
0x1800218f9  lea     rdx, aDnsdomainWs; "\tDnsDomain: %ws\n"
0x180021900  call    DsRolepLogPrintRoutine
0x180021905  mov     rcx, rbx; Block
0x180021908  call    cs:__imp_free
0x18002190e  movzx   edi, word ptr [rbp+var_38]
0x180021912  lea     rcx, [rdi+2]; Size
0x180021916  call    cs:__imp_malloc
0x18002191c  mov     rbx, rax
0x18002191f  test    rax, rax
0x180021922  jz      short loc_18002195D
0x180021924  mov     rdx, [rbp+var_38+8]; Src
0x180021928  mov     r8d, edi; Size
0x18002192b  mov     rcx, rax; void *
0x18002192e  call    memcpy_0
0x180021933  movzx   edx, word ptr [rbp+var_38]
0x180021937  xor     r9d, r9d
0x18002193a  shr     rdx, 1
0x18002193d  mov     r8, rbx
0x180021940  mov     ecx, r13d
0x180021943  mov     [rbx+rdx*2], r12w
0x180021948  lea     rdx, aFlatNameWs; "\tFlat name: %ws\n"
0x18002194f  call    DsRolepLogPrintRoutine
0x180021954  mov     rcx, rbx; Block
0x180021957  call    cs:__imp_free
0x18002195d  mov     r8d, dword ptr [rbp+var_28+8]
0x180021961  lea     rdx, aDirectionLu; "\tDirection: %lu\n"
0x180021968  mov     ecx, r13d
0x18002196b  call    DsRolepLogPrintRoutine
0x180021970  mov     r8d, dword ptr [rbp+var_28+0Ch]
0x180021974  lea     rdx, aTypeLu; "\tType: %lu\n"
0x18002197b  mov     ecx, r13d
0x18002197e  call    DsRolepLogPrintRoutine
0x180021983  mov     r8d, dword ptr [rbp+var_18]
0x180021987  lea     rdx, aAttributes0xLx; "\tAttributes: 0x%lx\n"
0x18002198e  mov     ecx, r13d
0x180021991  call    DsRolepLogPrintRoutine
0x180021996  mov     r9, [rbp+arg_20]
0x18002199a  lea     rax, [rbp+arg_10]
0x18002199e  lea     r8, [rbp+Src]
0x1800219a2  mov     [rsp+78h+var_50], rax
0x1800219a7  mov     rdx, r14
0x1800219aa  mov     rcx, r15
0x1800219ad  call    ImpLsaCreateTrustedDomainEx
0x1800219b2  mov     ebx, eax
0x1800219b4  cmp     eax, 0C0000035h
0x1800219b9  jnz     short loc_1800219F3
0x1800219bb  lea     rdx, aParentTrustObj; "Parent trust object already exists on p"...
0x1800219c2  mov     ecx, r13d
0x1800219c5  call    DsRolepLogPrintRoutine
0x1800219ca  mov     r9, [rbp+arg_20]
0x1800219ce  lea     rax, [rbp+arg_10]
0x1800219d2  and     sil, 20h
0x1800219d6  mov     [rsp+78h+var_50], rax; __int64
0x1800219db  lea     r8, [rbp+Src]; TrustedDomainInformation
0x1800219df  mov     [rsp+78h+var_58], sil; char
0x1800219e4  mov     rdx, r14; PolicyHandle
0x1800219e7  mov     rcx, r15; hToken
0x1800219ea  call    DsRolepHandlePreExistingTrustObject
0x1800219ef  mov     ebx, eax
0x1800219f1  jmp     short loc_180021A46
0x1800219f3  test    ebx, ebx
0x1800219f5  jz      short loc_180021A48
0x1800219f7  movzx   esi, word ptr [rbp+Src]
0x1800219fb  lea     rcx, [rsi+2]; Size
0x1800219ff  call    cs:__imp_malloc
0x180021a05  mov     rdi, rax
0x180021a08  test    rax, rax
0x180021a0b  jz      short loc_180021A46
0x180021a0d  mov     rdx, [rbp+Src+8]; Src
0x180021a11  mov     r8d, esi; Size
0x180021a14  mov     rcx, rax; void *
0x180021a17  call    memcpy_0
0x180021a1c  movzx   edx, word ptr [rbp+Src]
0x180021a20  mov     r9d, ebx
0x180021a23  shr     rdx, 1
0x180021a26  mov     r8, rdi
0x180021a29  mov     ecx, r13d
0x180021a2c  mov     [rdi+rdx*2], r12w
0x180021a31  lea     rdx, aParentLsacreat; "Parent LsaCreateTrustedDomainEx on %ws "...
0x180021a38  call    DsRolepLogPrintRoutine
0x180021a3d  mov     rcx, rdi; Block
0x180021a40  call    cs:__imp_free
0x180021a46  test    ebx, ebx
0x180021a48  js      short loc_180021A55
0x180021a4a  mov     rcx, [rbp+arg_28]
0x180021a4e  mov     rax, [rbp+arg_10]
0x180021a52  mov     [rcx], rax
0x180021a55  mov     eax, ebx
0x180021a57  add     rsp, 78h
0x180021a5b  pop     r15
0x180021a5d  pop     r14
0x180021a5f  pop     r13
0x180021a61  pop     r12
0x180021a63  pop     rdi
0x180021a64  pop     rsi
0x180021a65  pop     rbx
0x180021a66  pop     rbp
0x180021a67  retn
```
