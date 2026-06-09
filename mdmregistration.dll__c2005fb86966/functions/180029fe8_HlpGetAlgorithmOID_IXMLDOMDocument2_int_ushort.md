# HlpGetAlgorithmOID(IXMLDOMDocument2 *,int,ushort * *)

- ea: `0x180029fe8`
- end: `0x18002a458`
- name: `?HlpGetAlgorithmOID@@YAJPEAUIXMLDOMDocument2@@HPEAPEAG@Z`
- size: `1136`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028728`

## callees

- `0x180029fe8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002a16d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002a16d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002a153`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002a1d9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002a153`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002a1d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a234`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a234`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a43d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a43d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a21d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a429`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a21d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a429`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a02f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a057`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a072`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a02f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a057`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a072`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a256`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a265`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a275`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a289`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a387`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a39f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a256`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a265`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a275`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a289`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a387`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a39f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a1f1`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a1f1`

## pseudocode

```c
__int64 __fastcall HlpGetAlgorithmOID(struct IXMLDOMDocument2 *a1, int a2, unsigned __int16 **a3)
{
  int v3; // edi
  OLECHAR *v7; // r13
  OLECHAR *v8; // r14
  signed int v9; // ebx
  BSTR v10; // rsi
  __int64 v11; // r8
  wchar_t *v12; // rax
  __int64 v13; // rcx
  wchar_t *v14; // rax
  UINT v15; // eax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v19; // rsi
  unsigned __int64 v21; // rdi
  BSTR v22; // rcx
  __int64 v23; // rax
  unsigned __int16 *v24; // rdx
  unsigned __int16 *v25; // rcx
  HANDLE v26; // rax
  BSTR pbstr; // [rsp+20h] [rbp-30h] BYREF
  __int64 v28; // [rsp+28h] [rbp-28h] BYREF
  wchar_t *Str; // [rsp+30h] [rbp-20h] BYREF
  __int64 v30; // [rsp+38h] [rbp-18h] BYREF
  __int64 v31; // [rsp+40h] [rbp-10h] BYREF
  int v32; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v30 = 0;
  v28 = 0;
  v33 = 0;
  v31 = 0;
  Str = 0;
  pbstr = 0;
  v32 = 0;
  *a3 = 0;
  v7 = SysAllocString(L"//p:GetPoliciesResponse//p:oIDs//p:oID//p:value");
  if ( !v7 )
  {
    v8 = 0;
LABEL_3:
    v9 = -2147024882;
    goto LABEL_26;
  }
  v8 = SysAllocString(L"//p:oIDReferenceID");
  if ( !v8 )
    goto LABEL_3;
  v10 = SysAllocString(L"//p:value");
  if ( !v10 )
    goto LABEL_3;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, __int64 *))a1->lpVtbl->selectNodes)(a1, v7, &v31);
  if ( v9 >= 0 )
  {
    if ( v31 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 64LL))(v31, &v32);
      if ( v9 >= 0 && v32 > 0 )
      {
        while ( 1 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 56LL))(
                 v31,
                 (unsigned int)v3,
                 &v30);
          if ( v9 < 0 )
            goto LABEL_26;
          v9 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v30 + 296LL))(v30, v8, &v28);
          if ( v9 < 0 )
            goto LABEL_36;
          v11 = v28;
          if ( v28 )
            break;
          v13 = v33;
LABEL_38:
          if ( v30 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            v11 = v28;
            v13 = v33;
            v30 = 0;
          }
          if ( v11 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            v13 = v33;
            v28 = 0;
          }
          if ( v13 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            v33 = 0;
          }
          SysFreeString(Str);
          Str = 0;
          SysFreeString(pbstr);
          ++v3;
          pbstr = 0;
          if ( v3 >= v32 )
            goto LABEL_26;
        }
        v9 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v28 + 208LL))(v28, &Str);
        if ( v9 < 0 )
          goto LABEL_26;
        v12 = wcschr(Str, 0x20u);
        if ( v12 )
          *v12 = 0;
        if ( a2 == (unsigned int)_o__wtoi(Str)
          && (v9 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v30 + 296LL))(v30, v10, &v33),
              v9 >= 0) )
        {
          v13 = v33;
          if ( v33 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v33 + 208LL))(v33, &pbstr);
            if ( v9 < 0 )
              goto LABEL_26;
            v14 = wcschr(pbstr, 0x20u);
            if ( v14 )
              *v14 = 0;
            v15 = SysStringLen(pbstr);
            if ( v15 + 1 < v15 || (v16 = 2LL * (v15 + 1), v16 > 0xFFFFFFFF) )
            {
              v9 = -2147024362;
            }
            else
            {
              v17 = (unsigned int)v16;
              ProcessHeap = GetProcessHeap();
              v19 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v17);
              if ( !v19 )
              {
                v9 = -2147024882;
                goto LABEL_26;
              }
              v21 = v17 >> 1;
              if ( v21 )
              {
                v22 = pbstr;
                v23 = 2147483646;
                v24 = v19;
                do
                {
                  if ( !v23 )
                    break;
                  if ( !*v22 )
                    break;
                  *v24++ = *v22++;
                  --v23;
                  --v21;
                }
                while ( v21 );
                v25 = v24 - 1;
                if ( v21 )
                  v25 = v24;
                *v25 = 0;
                v9 = v21 == 0 ? 0x8007007A : 0;
                if ( v21 )
                {
                  *a3 = v19;
                  goto LABEL_26;
                }
              }
              else
              {
                v9 = -2147024809;
              }
              v26 = GetProcessHeap();
              HeapFree(v26, 0, v19);
            }
            goto LABEL_26;
          }
        }
        else
        {
LABEL_36:
          v13 = v33;
        }
        v11 = v28;
        goto LABEL_38;
      }
    }
  }
LABEL_26:
  SysFreeString(v7);
  SysFreeString(v8);
  SysFreeString(Str);
  Str = 0;
  SysFreeString(pbstr);
  pbstr = 0;
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029fe8  mov     [rsp-38h+arg_0], rbx
0x180029fed  push    rbp
0x180029fee  push    rsi
0x180029fef  push    rdi
0x180029ff0  push    r12
0x180029ff2  push    r13
0x180029ff4  push    r14
0x180029ff6  push    r15
0x180029ff8  mov     rbp, rsp
0x180029ffb  sub     rsp, 50h
0x180029fff  xor     edi, edi
0x18002a001  mov     rbx, rcx
0x18002a004  lea     rcx, aPGetpoliciesre_1; "//p:GetPoliciesResponse//p:oIDs//p:oID/"...
0x18002a00b  mov     [rbp+var_18], rdi
0x18002a00f  mov     [rbp+var_28], rdi
0x18002a013  mov     r15, r8
0x18002a016  mov     [rbp+arg_18], rdi
0x18002a01a  mov     r12d, edx
0x18002a01d  mov     [rbp+var_10], rdi
0x18002a021  mov     [rbp+Str], rdi
0x18002a025  mov     [rbp+pbstr], rdi
0x18002a029  mov     [rbp+arg_10], edi
0x18002a02c  mov     [r8], rdi
0x18002a02f  call    cs:__imp_SysAllocString
0x18002a036  nop     dword ptr [rax+rax+00h]
0x18002a03b  mov     r13, rax
0x18002a03e  test    rax, rax
0x18002a041  jnz     short loc_18002A050
0x18002a043  mov     r14d, edi
0x18002a046  mov     ebx, 8007000Eh
0x18002a04b  jmp     loc_18002A253
0x18002a050  lea     rcx, aPOidreferencei; "//p:oIDReferenceID"
0x18002a057  call    cs:__imp_SysAllocString
0x18002a05e  nop     dword ptr [rax+rax+00h]
0x18002a063  mov     r14, rax
0x18002a066  test    rax, rax
0x18002a069  jz      short loc_18002A046
0x18002a06b  lea     rcx, aPValue; "//p:value"
0x18002a072  call    cs:__imp_SysAllocString
0x18002a079  nop     dword ptr [rax+rax+00h]
0x18002a07e  mov     rsi, rax
0x18002a081  test    rax, rax
0x18002a084  jz      short loc_18002A046
0x18002a086  mov     rax, [rbx]
0x18002a089  lea     r8, [rbp+var_10]
0x18002a08d  mov     rdx, r13
0x18002a090  mov     rcx, rbx
0x18002a093  mov     rax, [rax+120h]
0x18002a09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a09f  mov     ebx, eax
0x18002a0a1  test    eax, eax
0x18002a0a3  js      loc_18002A253
0x18002a0a9  mov     rcx, [rbp+var_10]
0x18002a0ad  test    rcx, rcx
0x18002a0b0  jz      loc_18002A253
0x18002a0b6  mov     rax, [rcx]
0x18002a0b9  lea     rdx, [rbp+arg_10]
0x18002a0bd  mov     rax, [rax+40h]
0x18002a0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0c6  mov     ebx, eax
0x18002a0c8  test    eax, eax
0x18002a0ca  js      loc_18002A253
0x18002a0d0  cmp     [rbp+arg_10], edi
0x18002a0d3  jle     loc_18002A253
0x18002a0d9  mov     rcx, [rbp+var_10]
0x18002a0dd  lea     r8, [rbp+var_18]
0x18002a0e1  mov     edx, edi
0x18002a0e3  mov     rax, [rcx]
0x18002a0e6  mov     rax, [rax+38h]
0x18002a0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0ef  mov     ebx, eax
0x18002a0f1  test    eax, eax
0x18002a0f3  js      loc_18002A251
0x18002a0f9  mov     rcx, [rbp+var_18]
0x18002a0fd  lea     r8, [rbp+var_28]
0x18002a101  mov     rdx, r14
0x18002a104  mov     rax, [rcx]
0x18002a107  mov     rax, [rax+128h]
0x18002a10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a113  mov     ebx, eax
0x18002a115  test    eax, eax
0x18002a117  js      loc_18002A31A
0x18002a11d  mov     r8, [rbp+var_28]
0x18002a121  test    r8, r8
0x18002a124  jz      loc_18002A314
0x18002a12a  mov     rax, [r8]
0x18002a12d  lea     rdx, [rbp+Str]
0x18002a131  mov     rcx, r8
0x18002a134  mov     rax, [rax+0D0h]
0x18002a13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a140  mov     ebx, eax
0x18002a142  test    eax, eax
0x18002a144  js      loc_18002A251
0x18002a14a  mov     rcx, [rbp+Str]; Str
0x18002a14e  mov     edx, 20h ; ' '; Ch
0x18002a153  call    cs:__imp_wcschr
0x18002a15a  nop     dword ptr [rax+rax+00h]
0x18002a15f  test    rax, rax
0x18002a162  jz      short loc_18002A169
0x18002a164  xor     ecx, ecx
0x18002a166  mov     [rax], cx
0x18002a169  mov     rcx, [rbp+Str]
0x18002a16d  call    cs:__imp__o__wtoi
0x18002a174  nop     dword ptr [rax+rax+00h]
0x18002a179  cmp     r12d, eax
0x18002a17c  jnz     loc_18002A31A
0x18002a182  mov     rcx, [rbp+var_18]
0x18002a186  lea     r8, [rbp+arg_18]
0x18002a18a  mov     rdx, rsi
0x18002a18d  mov     rax, [rcx]
0x18002a190  mov     rax, [rax+128h]
0x18002a197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a19c  mov     ebx, eax
0x18002a19e  test    eax, eax
0x18002a1a0  js      loc_18002A31A
0x18002a1a6  mov     rcx, [rbp+arg_18]
0x18002a1aa  test    rcx, rcx
0x18002a1ad  jz      loc_18002A31E
0x18002a1b3  mov     rax, [rcx]
0x18002a1b6  lea     rdx, [rbp+pbstr]
0x18002a1ba  mov     rax, [rax+0D0h]
0x18002a1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1c6  xor     edi, edi
0x18002a1c8  mov     ebx, eax
0x18002a1ca  test    eax, eax
0x18002a1cc  js      loc_18002A253
0x18002a1d2  mov     rcx, [rbp+pbstr]; Str
0x18002a1d6  lea     edx, [rdi+20h]; Ch
0x18002a1d9  call    cs:__imp_wcschr
0x18002a1e0  nop     dword ptr [rax+rax+00h]
0x18002a1e5  test    rax, rax
0x18002a1e8  jz      short loc_18002A1ED
0x18002a1ea  mov     [rax], di
0x18002a1ed  mov     rcx, [rbp+pbstr]; pbstr
0x18002a1f1  call    cs:__imp_SysStringLen
0x18002a1f8  nop     dword ptr [rax+rax+00h]
0x18002a1fd  lea     ecx, [rax+1]
0x18002a200  cmp     ecx, eax
0x18002a202  jb      loc_18002A44E
0x18002a208  mov     eax, ecx
0x18002a20a  mov     ecx, 0FFFFFFFFh
0x18002a20f  add     rax, rax
0x18002a212  cmp     rax, rcx
0x18002a215  ja      loc_18002A44E
0x18002a21b  mov     edi, eax
0x18002a21d  call    cs:__imp_GetProcessHeap
0x18002a224  nop     dword ptr [rax+rax+00h]
0x18002a229  mov     r8d, edi; dwBytes
0x18002a22c  mov     edx, 8; dwFlags
0x18002a231  mov     rcx, rax; hHeap
0x18002a234  call    cs:__imp_HeapAlloc
0x18002a23b  nop     dword ptr [rax+rax+00h]
0x18002a240  mov     rsi, rax
0x18002a243  test    rax, rax
0x18002a246  jnz     loc_18002A3C3
0x18002a24c  mov     ebx, 8007000Eh
0x18002a251  xor     edi, edi
0x18002a253  mov     rcx, r13; bstrString
0x18002a256  call    cs:__imp_SysFreeString
0x18002a25d  nop     dword ptr [rax+rax+00h]
0x18002a262  mov     rcx, r14; bstrString
0x18002a265  call    cs:__imp_SysFreeString
0x18002a26c  nop     dword ptr [rax+rax+00h]
0x18002a271  mov     rcx, [rbp+Str]; bstrString
0x18002a275  call    cs:__imp_SysFreeString
0x18002a27c  nop     dword ptr [rax+rax+00h]
0x18002a281  mov     rcx, [rbp+pbstr]; bstrString
0x18002a285  mov     [rbp+Str], rdi
0x18002a289  call    cs:__imp_SysFreeString
0x18002a290  nop     dword ptr [rax+rax+00h]
0x18002a295  mov     rcx, [rbp+var_18]
0x18002a299  mov     [rbp+pbstr], rdi
0x18002a29d  test    rcx, rcx
0x18002a2a0  jz      short loc_18002A2B2
0x18002a2a2  mov     rax, [rcx]
0x18002a2a5  mov     rax, [rax+10h]
0x18002a2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2ae  mov     [rbp+var_18], rdi
0x18002a2b2  mov     rcx, [rbp+var_28]
0x18002a2b6  test    rcx, rcx
0x18002a2b9  jz      short loc_18002A2CB
0x18002a2bb  mov     rax, [rcx]
0x18002a2be  mov     rax, [rax+10h]
0x18002a2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2c7  mov     [rbp+var_28], rdi
0x18002a2cb  mov     rcx, [rbp+arg_18]
0x18002a2cf  test    rcx, rcx
0x18002a2d2  jz      short loc_18002A2E4
0x18002a2d4  mov     rax, [rcx]
0x18002a2d7  mov     rax, [rax+10h]
0x18002a2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2e0  mov     [rbp+arg_18], rdi
0x18002a2e4  mov     rcx, [rbp+var_10]
0x18002a2e8  test    rcx, rcx
0x18002a2eb  jz      short loc_18002A2F9
0x18002a2ed  mov     rax, [rcx]
0x18002a2f0  mov     rax, [rax+10h]
0x18002a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2f9  mov     eax, ebx
0x18002a2fb  mov     rbx, [rsp+50h+arg_0]
0x18002a303  add     rsp, 50h
0x18002a307  pop     r15
0x18002a309  pop     r14
0x18002a30b  pop     r13
0x18002a30d  pop     r12
0x18002a30f  pop     rdi
0x18002a310  pop     rsi
0x18002a311  pop     rbp
0x18002a312  retn
0x18002a314  mov     rcx, [rbp+arg_18]
0x18002a318  jmp     short loc_18002A322
0x18002a31a  mov     rcx, [rbp+arg_18]
0x18002a31e  mov     r8, [rbp+var_28]
0x18002a322  mov     rdx, [rbp+var_18]
0x18002a326  test    rdx, rdx
0x18002a329  jz      short loc_18002A34A
0x18002a32b  mov     rax, [rdx]
0x18002a32e  mov     rcx, rdx
0x18002a331  mov     rax, [rax+10h]
0x18002a335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a33a  mov     r8, [rbp+var_28]
0x18002a33e  mov     rcx, [rbp+arg_18]
0x18002a342  mov     [rbp+var_18], 0
0x18002a34a  test    r8, r8
0x18002a34d  jz      short loc_18002A36A
0x18002a34f  mov     rax, [r8]
0x18002a352  mov     rcx, r8
0x18002a355  mov     rax, [rax+10h]
0x18002a359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a35e  mov     rcx, [rbp+arg_18]
0x18002a362  mov     [rbp+var_28], 0
0x18002a36a  test    rcx, rcx
0x18002a36d  jz      short loc_18002A383
0x18002a36f  mov     rax, [rcx]
0x18002a372  mov     rax, [rax+10h]
0x18002a376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a37b  mov     [rbp+arg_18], 0
0x18002a383  mov     rcx, [rbp+Str]; bstrString
0x18002a387  call    cs:__imp_SysFreeString
0x18002a38e  nop     dword ptr [rax+rax+00h]
0x18002a393  mov     rcx, [rbp+pbstr]; bstrString
0x18002a397  mov     [rbp+Str], 0
0x18002a39f  call    cs:__imp_SysFreeString
0x18002a3a6  nop     dword ptr [rax+rax+00h]
0x18002a3ab  inc     edi
0x18002a3ad  mov     [rbp+pbstr], 0
0x18002a3b5  cmp     edi, [rbp+arg_10]
0x18002a3b8  jl      loc_18002A0D9
0x18002a3be  jmp     loc_18002A251
0x18002a3c3  shr     rdi, 1
0x18002a3c6  jz      short loc_18002A422
0x18002a3c8  mov     rcx, [rbp+pbstr]
0x18002a3cc  mov     eax, 7FFFFFFEh
0x18002a3d1  mov     rdx, rsi
0x18002a3d4  test    rax, rax
0x18002a3d7  jz      short loc_18002A3F8
0x18002a3d9  movzx   r8d, word ptr [rcx]
0x18002a3dd  test    r8w, r8w
0x18002a3e1  jz      short loc_18002A3F8
0x18002a3e3  mov     [rdx], r8w
0x18002a3e7  add     rcx, 2
0x18002a3eb  add     rdx, 2
0x18002a3ef  dec     rax
0x18002a3f2  sub     rdi, 1
0x18002a3f6  jnz     short loc_18002A3D4
0x18002a3f8  mov     rax, rdi
0x18002a3fb  lea     rcx, [rdx-2]
0x18002a3ff  neg     rax
0x18002a402  sbb     ebx, ebx
0x18002a404  test    rdi, rdi
0x18002a407  not     ebx
0x18002a409  cmovnz  rcx, rdx
0x18002a40d  xor     edi, edi
0x18002a40f  mov     [rcx], di
0x18002a412  and     ebx, 8007007Ah
0x18002a418  js      short loc_18002A429
0x18002a41a  mov     [r15], rsi
0x18002a41d  jmp     loc_18002A253
0x18002a422  mov     ebx, 80070057h
0x18002a427  xor     edi, edi
0x18002a429  call    cs:__imp_GetProcessHeap
0x18002a430  nop     dword ptr [rax+rax+00h]
0x18002a435  mov     r8, rsi; lpMem
0x18002a438  xor     edx, edx; dwFlags
0x18002a43a  mov     rcx, rax; hHeap
0x18002a43d  call    cs:__imp_HeapFree
0x18002a444  nop     dword ptr [rax+rax+00h]
0x18002a449  jmp     loc_18002A253
0x18002a44e  mov     ebx, 80070216h
0x18002a453  jmp     loc_18002A253
```
