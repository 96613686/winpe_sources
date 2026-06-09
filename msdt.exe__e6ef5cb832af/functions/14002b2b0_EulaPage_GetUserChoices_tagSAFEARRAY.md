# EulaPage::GetUserChoices(tagSAFEARRAY * *)

- ea: `0x14002b2b0`
- end: `0x14002b406`
- name: `?GetUserChoices@EulaPage@@MEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(EulaPage *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000e72c`
- `0x140020420`
- `0x14002b2b0`

## import_xrefs

- `USER32!SendMessageW` at `0x14002b31e`
- `USER32!SendMessageW` at `0x14002b31e`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b34c`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b34c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b3e9`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b3e9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b37f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b37f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b3c9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b3c9`

## pseudocode

```c
__int64 __fastcall EulaPage::GetUserChoices(EulaPage *this, struct tagSAFEARRAY **a2)
{
  int NamedHandle; // eax
  unsigned int v4; // ebx
  int v5; // r9d
  BSTR v6; // rsi
  SAFEARRAY *v7; // rax
  struct tagSAFEARRAY *v8; // rbp
  HRESULT v9; // eax
  int v10; // r9d
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-28h] BYREF
  LONG rgIndices; // [rsp+70h] [rbp+18h] BYREF
  HWND hWnd; // [rsp+78h] [rbp+20h] BYREF

  rgIndices = 0;
  hWnd = 0;
  NamedHandle = WizardPage::GetNamedHandle(this, L"cbEula", &hWnd);
  v4 = NamedHandle;
  if ( NamedHandle >= 0 )
  {
    if ( SendMessageW(hWnd, 0xF0u, 0, 0) != 1 )
    {
      *a2 = 0;
      return v4;
    }
    rgsabound = (SAFEARRAYBOUND)1LL;
    v6 = SysAllocString(L"Accept");
    if ( !v6 )
    {
      NamedHandle = -2147024882;
      v5 = 2992;
      v4 = -2147024882;
      goto LABEL_3;
    }
    v7 = SafeArrayCreate(8u, 1u, &rgsabound);
    v8 = v7;
    if ( v7 )
    {
      v9 = SafeArrayPutElement(v7, &rgIndices, v6);
      v4 = v9;
      if ( v9 >= 0 )
      {
        *a2 = v8;
        goto LABEL_14;
      }
      v10 = 2998;
    }
    else
    {
      v9 = -2147024882;
      v10 = 2995;
      v4 = -2147024882;
    }
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EulaPage::GetUserChoices", v10, v9);
LABEL_14:
    SysFreeString(v6);
    return v4;
  }
  v5 = 2974;
LABEL_3:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EulaPage::GetUserChoices", v5, NamedHandle);
  return v4;
}

```

## disassembly

```asm
0x14002b2b0  mov     rax, rsp
0x14002b2b3  mov     [rax+8], rbx
0x14002b2b7  push    rbp
0x14002b2b8  push    rsi
0x14002b2b9  push    r14
0x14002b2bb  sub     rsp, 40h
0x14002b2bf  mov     r14, rdx
0x14002b2c2  mov     dword ptr [rax+18h], 0
0x14002b2c9  lea     rdx, aCbeula; "cbEula"
0x14002b2d0  mov     qword ptr [rax+20h], 0
0x14002b2d8  lea     r8, [rax+20h]; HWND *
0x14002b2dc  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002b2e1  mov     ebx, eax
0x14002b2e3  test    eax, eax
0x14002b2e5  jns     short loc_14002B30E
0x14002b2e7  mov     r9d, 0B9Eh
0x14002b2ed  lea     r8, aEulapageGetuse; "EulaPage::GetUserChoices"
0x14002b2f4  mov     [rsp+58h+var_38], eax
0x14002b2f8  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002b2ff  mov     ecx, 1; Level
0x14002b304  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002b309  jmp     loc_14002B3F5
0x14002b30e  mov     rcx, [rsp+58h+hWnd]; hWnd
0x14002b313  xor     r9d, r9d; lParam
0x14002b316  xor     r8d, r8d; wParam
0x14002b319  mov     edx, 0F0h; Msg
0x14002b31e  call    cs:__imp_SendMessageW
0x14002b325  nop     dword ptr [rax+rax+00h]
0x14002b32a  cmp     rax, 1
0x14002b32e  jz      short loc_14002B33C
0x14002b330  mov     qword ptr [r14], 0
0x14002b337  jmp     loc_14002B3F5
0x14002b33c  lea     rcx, aAccept; "Accept"
0x14002b343  mov     qword ptr [rsp+58h+rgsabound.cElements], 1
0x14002b34c  call    cs:__imp_SysAllocString
0x14002b353  nop     dword ptr [rax+rax+00h]
0x14002b358  mov     rsi, rax
0x14002b35b  test    rax, rax
0x14002b35e  jnz     short loc_14002B372
0x14002b360  mov     eax, 8007000Eh
0x14002b365  mov     r9d, 0BB0h
0x14002b36b  mov     ebx, eax
0x14002b36d  jmp     loc_14002B2ED
0x14002b372  mov     ecx, 8; vt
0x14002b377  lea     r8, [rsp+58h+rgsabound]; rgsabound
0x14002b37c  lea     edx, [rcx-7]; cDims
0x14002b37f  call    cs:__imp_SafeArrayCreate
0x14002b386  nop     dword ptr [rax+rax+00h]
0x14002b38b  mov     rbp, rax
0x14002b38e  test    rax, rax
0x14002b391  jnz     short loc_14002B3BE
0x14002b393  mov     eax, 8007000Eh
0x14002b398  mov     r9d, 0BB3h
0x14002b39e  mov     ebx, eax
0x14002b3a0  lea     r8, aEulapageGetuse; "EulaPage::GetUserChoices"
0x14002b3a7  mov     [rsp+58h+var_38], eax
0x14002b3ab  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002b3b2  mov     ecx, 1; Level
0x14002b3b7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002b3bc  jmp     short loc_14002B3E6
0x14002b3be  mov     r8, rsi; pv
0x14002b3c1  lea     rdx, [rsp+58h+rgIndices]; rgIndices
0x14002b3c6  mov     rcx, rbp; psa
0x14002b3c9  call    cs:__imp_SafeArrayPutElement
0x14002b3d0  nop     dword ptr [rax+rax+00h]
0x14002b3d5  mov     ebx, eax
0x14002b3d7  test    eax, eax
0x14002b3d9  jns     short loc_14002B3E3
0x14002b3db  mov     r9d, 0BB6h
0x14002b3e1  jmp     short loc_14002B3A0
0x14002b3e3  mov     [r14], rbp
0x14002b3e6  mov     rcx, rsi; bstrString
0x14002b3e9  call    cs:__imp_SysFreeString
0x14002b3f0  nop     dword ptr [rax+rax+00h]
0x14002b3f5  mov     eax, ebx
0x14002b3f7  mov     rbx, [rsp+58h+arg_0]
0x14002b3fc  add     rsp, 40h
0x14002b400  pop     r14
0x14002b402  pop     rsi
0x14002b403  pop     rbp
0x14002b404  retn
```
