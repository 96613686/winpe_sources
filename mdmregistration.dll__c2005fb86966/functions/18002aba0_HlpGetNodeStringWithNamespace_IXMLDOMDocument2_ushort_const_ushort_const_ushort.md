# HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)

- ea: `0x18002aba0`
- end: `0x18002af22`
- name: `?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z`
- size: `898`
- prototype: `int(struct IXMLDOMDocument2 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800284a0`
- `0x180028728`
- `0x180028ee8`
- `0x180029ac4`
- `0x18002bc50`

## callees

- `0x180022544`
- `0x18002aba0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x18002ad5f`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x18002ad93`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x18002ad5f`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x18002ad93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002adf8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002adf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002aea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002aea0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ade1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ae8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ade1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ae8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ace8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ace8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad09`
- `OLEAUT32!__imp_SysAllocString` at `0x18002abf1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ac3a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002abf1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ac3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002acfa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aeb5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aecb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002acfa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aeb5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aecb`
- `OLEAUT32!__imp_SysStringLen` at `0x18002adb5`
- `OLEAUT32!__imp_SysStringLen` at `0x18002adb5`
- `OLEAUT32!__imp_VariantClear` at `0x18002ac22`
- `OLEAUT32!__imp_VariantClear` at `0x18002ac8f`
- `OLEAUT32!__imp_VariantClear` at `0x18002ac22`
- `OLEAUT32!__imp_VariantClear` at `0x18002ac8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall HlpGetNodeStringWithNamespace(
        struct IXMLDOMDocument2 *a1,
        unsigned __int16 *a2,
        OLECHAR *a3,
        unsigned __int16 **a4)
{
  const OLECHAR *v5; // r14
  OLECHAR *v7; // rdi
  unsigned __int16 *v8; // rsi
  signed int v9; // r14d
  struct IXMLDOMDocument2Vtbl *lpVtbl; // r15
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, BSTR *); // r12
  OLECHAR *v13; // r15
  DWORD LastError; // r14d
  OLECHAR *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  OLECHAR *i; // rbx
  int v19; // eax
  _WORD *v20; // rbx
  UINT v21; // eax
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v25; // rbx
  __int64 v26; // rax
  BSTR v27; // rcx
  unsigned __int16 v28; // r9
  const unsigned __int16 *v29; // rcx
  HANDLE v30; // rax
  _QWORD v32[3]; // [rsp+20h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-40h] BYREF
  VARIANTARG v34; // [rsp+50h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+D8h] [rbp+60h] BYREF

  v5 = a2;
  v32[0] = 0;
  bstrString = 0;
  v7 = 0;
  v8 = 0;
  v32[1] = 0;
  if ( !a4 )
  {
    v9 = -2147467261;
    goto LABEL_41;
  }
  *a4 = 0;
  if ( !a3 )
    goto LABEL_40;
  v7 = SysAllocString(a3);
  v32[2] = v7;
  if ( !v7 )
    goto LABEL_40;
  if ( !v5 )
    goto LABEL_53;
  lpVtbl = a1->lpVtbl;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v5);
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v34 = pvarg;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const OLECHAR *, VARIANTARG *))lpVtbl->setProperty)(
         a1,
         L"SelectionNamespaces",
         &v34);
  VariantClear(&pvarg);
  if ( v9 >= 0 )
  {
LABEL_53:
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, _QWORD *))a1->lpVtbl->selectSingleNode)(
           a1,
           v7,
           v32);
    if ( v9 >= 0 )
    {
      v11 = v32[0];
      if ( v32[0] )
      {
        v12 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v32[0] + 208LL);
        v13 = bstrString;
        if ( bstrString )
        {
          LastError = GetLastError();
          SysFreeString(v13);
          SetLastError(LastError);
        }
        bstrString = 0;
        v9 = v12(v11, &bstrString);
        if ( v9 >= 0 )
        {
          v15 = bstrString;
          if ( bstrString && *bstrString )
          {
            v16 = -1;
            v17 = -1;
            do
              ++v17;
            while ( bstrString[v17] );
            if ( !(unsigned int)_o_isspace(bstrString[v17 - 1]) )
              goto LABEL_25;
            do
              ++v16;
            while ( bstrString[v16] );
            for ( i = &bstrString[v16 - 1]; ; --i )
            {
              v19 = _o_isspace(*i);
              v15 = bstrString;
              if ( !v19 || i <= bstrString )
                break;
            }
            v20 = i + 1;
            if ( v20 )
            {
              *v20 = 0;
LABEL_25:
              v15 = bstrString;
            }
          }
          v21 = SysStringLen(v15);
          if ( v21 + 1 < v21 || (v22 = 2LL * (v21 + 1), v22 > 0xFFFFFFFF) )
          {
            v9 = -2147024362;
            goto LABEL_41;
          }
          v23 = (unsigned int)v22;
          ProcessHeap = GetProcessHeap();
          a3 = (OLECHAR *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v23);
          v8 = a3;
          if ( a3 )
          {
            v25 = v23 >> 1;
            if ( v25 )
            {
              v26 = 2147483646;
              v27 = bstrString;
              a2 = a3;
              do
              {
                if ( !v26 )
                  break;
                v28 = *v27;
                if ( !*v27 )
                  break;
                ++v27;
                *a2++ = v28;
                --v26;
                --v25;
              }
              while ( v25 );
              v29 = a2 - 1;
              if ( v25 )
                v29 = a2;
              *v29 = 0;
              v9 = v25 == 0 ? 0x8007007A : 0;
              if ( v25 )
              {
                v8 = 0;
                *a4 = a3;
              }
            }
            else
            {
              v9 = -2147024809;
            }
            goto LABEL_41;
          }
LABEL_40:
          v9 = -2147024882;
        }
      }
    }
  }
LABEL_41:
  if ( v8 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v8);
  }
  if ( v7 )
    SysFreeString(v7);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v32[0] )
    (*(void (__fastcall **)(_QWORD, unsigned __int16 *, OLECHAR *))(*(_QWORD *)v32[0] + 16LL))(v32[0], a2, a3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002aba0  push    rbp
0x18002aba2  push    rbx
0x18002aba3  push    rsi
0x18002aba4  push    rdi
0x18002aba5  push    r12
0x18002aba7  push    r13
0x18002aba9  push    r14
0x18002abab  push    r15
0x18002abad  mov     rbp, rsp
0x18002abb0  sub     rsp, 78h
0x18002abb4  mov     r13, r9
0x18002abb7  mov     r14, rdx
0x18002abba  mov     rbx, rcx
0x18002abbd  xor     r12d, r12d
0x18002abc0  mov     [rbp+var_58], r12
0x18002abc4  mov     [rbp+bstrString], r12
0x18002abc8  mov     edi, r12d
0x18002abcb  mov     esi, r12d
0x18002abce  mov     [rbp+var_50], r12
0x18002abd2  test    r9, r9
0x18002abd5  jnz     short loc_18002ABE2
0x18002abd7  mov     r14d, 80004003h
0x18002abdd  jmp     loc_18002AE87
0x18002abe2  mov     [r9], r12
0x18002abe5  test    r8, r8
0x18002abe8  jz      loc_18002AE81
0x18002abee  mov     rcx, r8; psz
0x18002abf1  call    cs:__imp_SysAllocString
0x18002abf8  nop     dword ptr [rax+rax+00h]
0x18002abfd  mov     rdi, rax
0x18002ac00  mov     [rbp+var_48], rax
0x18002ac04  test    rax, rax
0x18002ac07  jz      loc_18002AE81
0x18002ac0d  test    r14, r14
0x18002ac10  jz      loc_18002ACA4
0x18002ac16  mov     r15, [rbx]
0x18002ac19  mov     word ptr [rbp+pvarg], r12w
0x18002ac1e  lea     rcx, [rbp+pvarg]; pvarg
0x18002ac22  call    cs:__imp_VariantClear
0x18002ac29  nop     dword ptr [rax+rax+00h]
0x18002ac2e  mov     eax, 8
0x18002ac33  mov     word ptr [rbp+pvarg], ax
0x18002ac37  mov     rcx, r14; psz
0x18002ac3a  call    cs:__imp_SysAllocString
0x18002ac41  nop     dword ptr [rax+rax+00h]
0x18002ac46  mov     rcx, rax
0x18002ac49  mov     dword ptr [rbp+pvarg+8], ecx
0x18002ac4c  sar     rax, 20h
0x18002ac50  mov     dword ptr [rbp+pvarg+0Ch], eax
0x18002ac53  test    rcx, rcx
0x18002ac56  jz      loc_18002AF06
0x18002ac5c  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18002ac60  movaps  [rbp+var_28], xmm0
0x18002ac64  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002ac69  movsd   [rbp+var_18], xmm1
0x18002ac6e  lea     r8, [rbp+var_28]
0x18002ac72  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18002ac79  mov     rcx, rbx
0x18002ac7c  mov     rax, [r15+280h]
0x18002ac83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac88  mov     r14d, eax
0x18002ac8b  lea     rcx, [rbp+pvarg]; pvarg
0x18002ac8f  call    cs:__imp_VariantClear
0x18002ac96  nop     dword ptr [rax+rax+00h]
0x18002ac9b  test    r14d, r14d
0x18002ac9e  js      loc_18002AE87
0x18002aca4  mov     rax, [rbx]
0x18002aca7  lea     r8, [rbp+var_58]
0x18002acab  mov     rdx, rdi
0x18002acae  mov     rcx, rbx
0x18002acb1  mov     rax, [rax+128h]
0x18002acb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acbd  mov     r14d, eax
0x18002acc0  test    eax, eax
0x18002acc2  js      loc_18002AE87
0x18002acc8  mov     rbx, [rbp+var_58]
0x18002accc  test    rbx, rbx
0x18002accf  jz      loc_18002AE87
0x18002acd5  mov     rax, [rbx]
0x18002acd8  mov     r12, [rax+0D0h]
0x18002acdf  mov     r15, [rbp+bstrString]
0x18002ace3  test    r15, r15
0x18002ace6  jz      short loc_18002AD15
0x18002ace8  call    cs:__imp_GetLastError
0x18002acef  nop     dword ptr [rax+rax+00h]
0x18002acf4  mov     r14d, eax
0x18002acf7  mov     rcx, r15; bstrString
0x18002acfa  call    cs:__imp_SysFreeString
0x18002ad01  nop     dword ptr [rax+rax+00h]
0x18002ad06  mov     ecx, r14d; dwErrCode
0x18002ad09  call    cs:__imp_SetLastError
0x18002ad10  nop     dword ptr [rax+rax+00h]
0x18002ad15  mov     [rbp+bstrString], 0
0x18002ad1d  lea     rdx, [rbp+bstrString]
0x18002ad21  mov     rcx, rbx
0x18002ad24  mov     rax, r12
0x18002ad27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad2c  mov     r14d, eax
0x18002ad2f  xor     r12d, r12d
0x18002ad32  test    eax, eax
0x18002ad34  js      loc_18002AE87
0x18002ad3a  mov     rcx, [rbp+bstrString]
0x18002ad3e  test    rcx, rcx
0x18002ad41  jz      short loc_18002ADB5
0x18002ad43  cmp     r12w, [rcx]
0x18002ad47  jz      short loc_18002ADB5
0x18002ad49  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ad4d  mov     rax, rbx
0x18002ad50  inc     rax
0x18002ad53  cmp     [rcx+rax*2], r12w
0x18002ad58  jnz     short loc_18002AD50
0x18002ad5a  movzx   ecx, word ptr [rcx+rax*2-2]
0x18002ad5f  call    cs:__imp__o_isspace
0x18002ad66  nop     dword ptr [rax+rax+00h]
0x18002ad6b  test    eax, eax
0x18002ad6d  jz      short loc_18002ADB1
0x18002ad6f  mov     rax, [rbp+bstrString]
0x18002ad73  inc     rbx
0x18002ad76  cmp     [rax+rbx*2], r12w
0x18002ad7b  jnz     short loc_18002AD73
0x18002ad7d  sub     rax, 2
0x18002ad81  lea     rbx, [rax+rbx*2]
0x18002ad85  jmp     short loc_18002AD90
0x18002ad87  cmp     rbx, rcx
0x18002ad8a  jbe     short loc_18002ADA7
0x18002ad8c  sub     rbx, 2
0x18002ad90  movzx   ecx, word ptr [rbx]
0x18002ad93  call    cs:__imp__o_isspace
0x18002ad9a  nop     dword ptr [rax+rax+00h]
0x18002ad9f  mov     rcx, [rbp+bstrString]
0x18002ada3  test    eax, eax
0x18002ada5  jnz     short loc_18002AD87
0x18002ada7  add     rbx, 2
0x18002adab  jz      short loc_18002ADB5
0x18002adad  mov     [rbx], r12w
0x18002adb1  mov     rcx, [rbp+bstrString]; pbstr
0x18002adb5  call    cs:__imp_SysStringLen
0x18002adbc  nop     dword ptr [rax+rax+00h]
0x18002adc1  lea     ecx, [rax+1]
0x18002adc4  cmp     ecx, eax
0x18002adc6  jb      loc_18002AE79
0x18002adcc  mov     eax, ecx
0x18002adce  add     rax, rax
0x18002add1  mov     ecx, 0FFFFFFFFh
0x18002add6  cmp     rax, rcx
0x18002add9  ja      loc_18002AE79
0x18002addf  mov     ebx, eax
0x18002ade1  call    cs:__imp_GetProcessHeap
0x18002ade8  nop     dword ptr [rax+rax+00h]
0x18002aded  mov     rcx, rax; hHeap
0x18002adf0  mov     r8d, ebx; dwBytes
0x18002adf3  mov     edx, 8; dwFlags
0x18002adf8  call    cs:__imp_HeapAlloc
0x18002adff  nop     dword ptr [rax+rax+00h]
0x18002ae04  mov     r8, rax
0x18002ae07  mov     rsi, rax
0x18002ae0a  test    rax, rax
0x18002ae0d  jz      short loc_18002AE81
0x18002ae0f  shr     rbx, 1
0x18002ae12  jz      short loc_18002AE71
0x18002ae14  mov     eax, 7FFFFFFEh
0x18002ae19  mov     rcx, [rbp+bstrString]
0x18002ae1d  mov     rdx, rsi
0x18002ae20  test    rax, rax
0x18002ae23  jz      short loc_18002AE44
0x18002ae25  movzx   r9d, word ptr [rcx]
0x18002ae29  test    r9w, r9w
0x18002ae2d  jz      short loc_18002AE44
0x18002ae2f  add     rcx, 2
0x18002ae33  mov     [rdx], r9w
0x18002ae37  add     rdx, 2
0x18002ae3b  dec     rax
0x18002ae3e  sub     rbx, 1
0x18002ae42  jnz     short loc_18002AE20
0x18002ae44  mov     rax, rbx
0x18002ae47  neg     rax
0x18002ae4a  sbb     r14d, r14d
0x18002ae4d  not     r14d
0x18002ae50  lea     rcx, [rdx-2]
0x18002ae54  test    rbx, rbx
0x18002ae57  cmovnz  rcx, rdx
0x18002ae5b  mov     [rcx], r12w
0x18002ae5f  and     r14d, 8007007Ah
0x18002ae66  js      short loc_18002AE87
0x18002ae68  mov     rsi, r12
0x18002ae6b  mov     [r13+0], r8
0x18002ae6f  jmp     short loc_18002AE87
0x18002ae71  mov     r14d, 80070057h
0x18002ae77  jmp     short loc_18002AE87
0x18002ae79  mov     r14d, 80070216h
0x18002ae7f  jmp     short loc_18002AE87
0x18002ae81  mov     r14d, 8007000Eh
0x18002ae87  test    rsi, rsi
0x18002ae8a  jz      short loc_18002AEAD
0x18002ae8c  call    cs:__imp_GetProcessHeap
0x18002ae93  nop     dword ptr [rax+rax+00h]
0x18002ae98  mov     rcx, rax; hHeap
0x18002ae9b  mov     r8, rsi; lpMem
0x18002ae9e  xor     edx, edx; dwFlags
0x18002aea0  call    cs:__imp_HeapFree
0x18002aea7  nop     dword ptr [rax+rax+00h]
0x18002aeac  nop
0x18002aead  test    rdi, rdi
0x18002aeb0  jz      short loc_18002AEC2
0x18002aeb2  mov     rcx, rdi; bstrString
0x18002aeb5  call    cs:__imp_SysFreeString
0x18002aebc  nop     dword ptr [rax+rax+00h]
0x18002aec1  nop
0x18002aec2  mov     rcx, [rbp+bstrString]; bstrString
0x18002aec6  test    rcx, rcx
0x18002aec9  jz      short loc_18002AED8
0x18002aecb  call    cs:__imp_SysFreeString
0x18002aed2  nop     dword ptr [rax+rax+00h]
0x18002aed7  nop
0x18002aed8  mov     rbx, [rbp+var_58]
0x18002aedc  test    rbx, rbx
0x18002aedf  jz      short loc_18002AEF1
0x18002aee1  mov     rax, [rbx]
0x18002aee4  mov     rcx, rbx
0x18002aee7  mov     rax, [rax+10h]
0x18002aeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aef0  nop
0x18002aef1  mov     eax, r14d
0x18002aef4  add     rsp, 78h
0x18002aef8  pop     r15
0x18002aefa  pop     r14
0x18002aefc  pop     r13
0x18002aefe  pop     r12
0x18002af00  pop     rdi
0x18002af01  pop     rsi
0x18002af02  pop     rbx
0x18002af03  pop     rbp
0x18002af04  retn
0x18002af06  mov     eax, 0Ah
0x18002af0b  mov     word ptr [rbp+pvarg], ax
0x18002af0f  mov     r14d, 8007000Eh
0x18002af15  mov     dword ptr [rbp+pvarg+8], r14d
0x18002af19  mov     ecx, r14d; int
0x18002af1c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
