# TypeInfoBuilder::Create(ushort const *,ulong,TypeInfoBuilder * *)

- ea: `0x180087014`
- end: `0x18008724e`
- name: `?Create@TypeInfoBuilder@@SAJPEBGKPEAPEAV1@@Z`
- size: `570`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct TypeInfoBuilder **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180076880`

## callees

- `0x1800576a0`
- `0x180073a08`
- `0x180087014`
- `0x1800872ec`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x18008708e`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x18008708e`

## pseudocode

```c
__int64 __fastcall TypeInfoBuilder::Create(const unsigned __int16 *a1, unsigned int a2, ICreateTypeLib2 ***a3)
{
  ICreateTypeLib2 **v6; // rax
  ICreateTypeLib2 **v7; // rbx
  HRESULT DispatchTypeInfo; // edi
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  struct ITypeInfo *v13; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+20h] BYREF

  v14 = 0;
  v13 = 0;
  v6 = (ICreateTypeLib2 **)operator new(0x18u);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 0;
    v6[1] = 0;
    v6[2] = 0;
    DispatchTypeInfo = GetDispatchTypeInfo(&v13);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    v9 = v7 + 2;
    DispatchTypeInfo = CreateTypeLib2(SYS_WIN32, L"JSDeb.tlb", v7 + 2);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 80LL))(*v9, a2);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v9 + 32LL))(
                         *v9,
                         L"JScriptTypeLib");
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v9 + 56LL))(
                         *v9,
                         L"JScript Type Library");
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v9 + 40LL))(*v9, 10, 8);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v9 + 48LL))(*v9, &IID_IScriptTypeLib);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 88LL))(*v9, 0);
    if ( DispatchTypeInfo < 0 )
      goto LABEL_17;
    v10 = *v9;
    v11 = v7 + 1;
    DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, ICreateTypeLib2 **))(*(_QWORD *)v10 + 24LL))(
                         v10,
                         a1,
                         4,
                         v7 + 1);
    if ( DispatchTypeInfo < 0
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*v11 + 40LL))(
                               *v11,
                               L"JScript Type Info"),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v11 + 24LL))(
                               *v11,
                               &IID_IScriptTypeInfo),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v11 + 56LL))(*v11, 10, 8),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, struct ITypeInfo *, unsigned int *))(*(_QWORD *)*v11 + 64LL))(
                               *v11,
                               v13,
                               &v14),
          DispatchTypeInfo < 0)
      || (DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v11 + 80LL))(*v11, 0, v14),
          DispatchTypeInfo < 0) )
    {
LABEL_17:
      TypeInfoBuilder::Release((TypeInfoBuilder *)v7);
    }
    else
    {
      DispatchTypeInfo = 0;
      *a3 = v7;
    }
  }
  else
  {
    DispatchTypeInfo = -2147024882;
  }
  if ( v13 )
    ((void (__fastcall *)(struct ITypeInfo *))v13->lpVtbl->Release)(v13);
  return (unsigned int)DispatchTypeInfo;
}

```

## disassembly

```asm
0x180087014  mov     rax, rsp
0x180087017  push    rbx
0x180087018  push    rbp
0x180087019  push    rsi
0x18008701a  push    rdi
0x18008701b  push    r14
0x18008701d  push    r15
0x18008701f  sub     rsp, 48h
0x180087023  mov     r15, rcx
0x180087026  mov     dword ptr [rax+20h], 0
0x18008702d  mov     ecx, 18h; Size
0x180087032  mov     qword ptr [rax-48h], 0
0x18008703a  mov     r14, r8
0x18008703d  mov     ebp, edx
0x18008703f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180087044  mov     rbx, rax
0x180087047  test    rax, rax
0x18008704a  jz      loc_180087224
0x180087050  lea     rcx, [rsp+78h+var_48]; struct ITypeInfo **
0x180087055  mov     qword ptr [rax], 0
0x18008705c  mov     qword ptr [rax+8], 0
0x180087064  mov     qword ptr [rax+10h], 0
0x18008706c  call    ?GetDispatchTypeInfo@@YAJPEAPEAUITypeInfo@@@Z; GetDispatchTypeInfo(ITypeInfo * *)
0x180087071  mov     edi, eax
0x180087073  test    eax, eax
0x180087075  js      loc_18008721A
0x18008707b  lea     rsi, [rbx+10h]
0x18008707f  mov     ecx, 1; syskind
0x180087084  mov     r8, rsi; ppctlib
0x180087087  lea     rdx, aJsdebTlb; "JSDeb.tlb"
0x18008708e  call    cs:__imp_CreateTypeLib2
0x180087094  mov     edi, eax
0x180087096  test    eax, eax
0x180087098  js      loc_18008721A
0x18008709e  mov     rcx, [rsi]
0x1800870a1  mov     edx, ebp
0x1800870a3  mov     rax, [rcx]
0x1800870a6  mov     rax, [rax+50h]
0x1800870aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800870af  mov     edi, eax
0x1800870b1  test    eax, eax
0x1800870b3  js      loc_18008721A
0x1800870b9  mov     rcx, [rsi]
0x1800870bc  lea     rdx, aJscripttypelib; "JScriptTypeLib"
0x1800870c3  mov     rax, [rcx]
0x1800870c6  mov     rax, [rax+20h]
0x1800870ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800870cf  mov     edi, eax
0x1800870d1  test    eax, eax
0x1800870d3  js      loc_18008721A
0x1800870d9  mov     rcx, [rsi]
0x1800870dc  lea     rdx, aJscriptTypeLib; "JScript Type Library"
0x1800870e3  mov     rax, [rcx]
0x1800870e6  mov     rax, [rax+38h]
0x1800870ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800870ef  mov     edi, eax
0x1800870f1  test    eax, eax
0x1800870f3  js      loc_18008721A
0x1800870f9  mov     rcx, [rsi]
0x1800870fc  mov     ebp, 8
0x180087101  mov     r8d, ebp
0x180087104  mov     rax, [rcx]
0x180087107  lea     edx, [rbp+2]
0x18008710a  mov     rax, [rax+28h]
0x18008710e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087113  mov     edi, eax
0x180087115  test    eax, eax
0x180087117  js      loc_18008721A
0x18008711d  mov     rcx, [rsi]
0x180087120  lea     rdx, IID_IScriptTypeLib
0x180087127  mov     rax, [rcx]
0x18008712a  mov     rax, [rax+30h]
0x18008712e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087133  mov     edi, eax
0x180087135  test    eax, eax
0x180087137  js      loc_18008721A
0x18008713d  mov     rcx, [rsi]
0x180087140  xor     edx, edx
0x180087142  mov     rax, [rcx]
0x180087145  mov     rax, [rax+58h]
0x180087149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008714e  mov     edi, eax
0x180087150  test    eax, eax
0x180087152  js      loc_18008721A
0x180087158  mov     rcx, [rsi]
0x18008715b  lea     r8d, [rbp-4]
0x18008715f  lea     rsi, [rbx+8]
0x180087163  mov     rdx, r15
0x180087166  mov     r9, rsi
0x180087169  mov     rax, [rcx]
0x18008716c  mov     rax, [rax+18h]
0x180087170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087175  mov     edi, eax
0x180087177  test    eax, eax
0x180087179  js      loc_18008721A
0x18008717f  mov     rcx, [rsi]
0x180087182  lea     rdx, aJscriptTypeInf; "JScript Type Info"
0x180087189  mov     rax, [rcx]
0x18008718c  mov     rax, [rax+28h]
0x180087190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087195  mov     edi, eax
0x180087197  test    eax, eax
0x180087199  js      short loc_18008721A
0x18008719b  mov     rcx, [rsi]
0x18008719e  lea     rdx, IID_IScriptTypeInfo
0x1800871a5  mov     rax, [rcx]
0x1800871a8  mov     rax, [rax+18h]
0x1800871ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871b1  mov     edi, eax
0x1800871b3  test    eax, eax
0x1800871b5  js      short loc_18008721A
0x1800871b7  mov     rcx, [rsi]
0x1800871ba  lea     edx, [rbp+2]
0x1800871bd  mov     r8d, ebp
0x1800871c0  mov     rax, [rcx]
0x1800871c3  mov     rax, [rax+38h]
0x1800871c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871cc  mov     edi, eax
0x1800871ce  test    eax, eax
0x1800871d0  js      short loc_18008721A
0x1800871d2  mov     rcx, [rsi]
0x1800871d5  lea     r8, [rsp+78h+arg_18]
0x1800871dd  mov     rdx, [rsp+78h+var_48]
0x1800871e2  mov     rax, [rcx]
0x1800871e5  mov     rax, [rax+40h]
0x1800871e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871ee  mov     edi, eax
0x1800871f0  test    eax, eax
0x1800871f2  js      short loc_18008721A
0x1800871f4  mov     rcx, [rsi]
0x1800871f7  xor     edx, edx
0x1800871f9  mov     r8d, [rsp+78h+arg_18]
0x180087201  mov     rax, [rcx]
0x180087204  mov     rax, [rax+50h]
0x180087208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008720d  mov     edi, eax
0x18008720f  test    eax, eax
0x180087211  js      short loc_18008721A
0x180087213  xor     edi, edi
0x180087215  mov     [r14], rbx
0x180087218  jmp     short loc_180087229
0x18008721a  mov     rcx, rbx; this
0x18008721d  call    ?Release@TypeInfoBuilder@@QEAAXXZ; TypeInfoBuilder::Release(void)
0x180087222  jmp     short loc_180087229
0x180087224  mov     edi, 8007000Eh
0x180087229  mov     rcx, [rsp+78h+var_48]
0x18008722e  test    rcx, rcx
0x180087231  jz      short loc_18008723F
0x180087233  mov     rax, [rcx]
0x180087236  mov     rax, [rax+10h]
0x18008723a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008723f  mov     eax, edi
0x180087241  add     rsp, 48h
0x180087245  pop     r15
0x180087247  pop     r14
0x180087249  pop     rdi
0x18008724a  pop     rsi
0x18008724b  pop     rbp
0x18008724c  pop     rbx
0x18008724d  retn
```
