# EXTERNAL_AccessibleObjectFromEvent

- ea: `0x1800079d0`
- end: `0x180007b87`
- name: `EXTERNAL_AccessibleObjectFromEvent`
- size: `439`
- prototype: `HRESULT __stdcall(HWND hwnd, DWORD dwId, DWORD dwChildId, IAccessible **ppacc, VARIANT *pvarChild)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800079d0`
- `0x180007b90`
- `0x1800093c0`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180007a4b`
- `OLEAUT32!__imp_VariantInit` at `0x180007a84`
- `OLEAUT32!__imp_VariantInit` at `0x180007a4b`
- `OLEAUT32!__imp_VariantInit` at `0x180007a84`
- `OLEAUT32!__imp_VariantCopy` at `0x180007adc`
- `OLEAUT32!__imp_VariantCopy` at `0x180007adc`
- `USER32!IsWindow` at `0x180007a32`
- `USER32!IsWindow` at `0x180007a32`

## pseudocode

```c
HRESULT __stdcall EXTERNAL_AccessibleObjectFromEvent(
        HWND hwnd,
        DWORD dwId,
        DWORD dwChildId,
        IAccessible **ppacc,
        VARIANT *pvarChild)
{
  VARIANTARG *v9; // rcx
  int v10; // ebx
  __int64 v11; // rax
  IAccessible *v12; // rax
  VARIANTARG *v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG v17; // [rsp+40h] [rbp-20h] BYREF
  void *ppvObject; // [rsp+98h] [rbp+38h] BYREF

  if ( !g_fInitedOleacc )
    InitOleacc();
  ppvObject = 0;
  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !ppacc || !pvarChild || !IsWindow(hwnd) && hwnd )
    return -2147024809;
  v9 = pvarChild;
  *ppacc = 0;
  VariantInit(v9);
  ppvObject = 0;
  v10 = AccessibleObjectFromWindow_0(hwnd, dwId, &IID_IAccessible, &ppvObject);
  if ( v10 >= 0 )
  {
    if ( ppvObject )
    {
      VariantInit(&pvarg);
      pvarg.lVal = dwChildId;
      pvarg.vt = 3;
      v15 = 0;
      v11 = *(_QWORD *)ppvObject;
      v17 = pvarg;
      if ( (*(int (__fastcall **)(void *, VARIANTARG *, __int64 *))(v11 + 72))(ppvObject, &v17, &v15) < 0 || !v15 )
      {
        v12 = (IAccessible *)ppvObject;
LABEL_10:
        v13 = pvarChild;
        *ppacc = v12;
        return VariantCopy(v13, &pvarg);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
      v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v15)(v15, &IID_IAccessible, &ppvObject);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v10 < 0 )
        return v10;
      v12 = (IAccessible *)ppvObject;
      if ( ppvObject )
      {
        pvarg.lVal = 0;
        goto LABEL_10;
      }
    }
    return -2147467259;
  }
  return v10;
}

```

## disassembly

```asm
0x1800079d0  mov     [rsp-18h+arg_0], rbx
0x1800079d5  mov     [rsp-18h+arg_8], rsi
0x1800079da  push    rbp
0x1800079db  push    r14
0x1800079dd  push    r15
0x1800079df  mov     rbp, rsp
0x1800079e2  sub     rsp, 60h
0x1800079e6  cmp     cs:?g_fInitedOleacc@@3HA, 0; int g_fInitedOleacc
0x1800079ed  mov     rsi, r9
0x1800079f0  mov     r15d, r8d
0x1800079f3  mov     r14d, edx
0x1800079f6  mov     rbx, rcx
0x1800079f9  jz      loc_180007B7D
0x1800079ff  xor     eax, eax
0x180007a01  mov     [rbp+ppvObject], 0
0x180007a09  mov     [rbp+var_40], 0
0x180007a11  xorps   xmm0, xmm0
0x180007a14  mov     qword ptr [rbp+pvarg+10h], rax
0x180007a18  movups  xmmword ptr [rbp+pvarg], xmm0
0x180007a1c  test    rsi, rsi
0x180007a1f  jz      loc_180007B73
0x180007a25  cmp     [rbp+pvarChild], rax
0x180007a29  jz      loc_180007B73
0x180007a2f  mov     rcx, rbx; hWnd
0x180007a32  call    cs:__imp_IsWindow
0x180007a38  test    eax, eax
0x180007a3a  jz      loc_180007B6A
0x180007a40  mov     rcx, [rbp+pvarChild]; pvarg
0x180007a44  mov     qword ptr [rsi], 0
0x180007a4b  call    cs:__imp_VariantInit
0x180007a51  lea     r9, [rbp+ppvObject]; ppvObject
0x180007a55  mov     [rbp+ppvObject], 0
0x180007a5d  lea     r8, IID_IAccessible; riid
0x180007a64  mov     edx, r14d; dwId
0x180007a67  mov     rcx, rbx; hwnd
0x180007a6a  call    AccessibleObjectFromWindow_0
0x180007a6f  mov     ebx, eax
0x180007a71  test    eax, eax
0x180007a73  js      short loc_180007AE4
0x180007a75  cmp     [rbp+ppvObject], 0
0x180007a7a  jz      loc_180007B60
0x180007a80  lea     rcx, [rbp+pvarg]; pvarg
0x180007a84  call    cs:__imp_VariantInit
0x180007a8a  mov     rcx, [rbp+ppvObject]
0x180007a8e  lea     r8, [rbp+var_40]
0x180007a92  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180007a97  lea     rdx, [rbp+var_20]
0x180007a9b  mov     dword ptr [rbp+pvarg+8], r15d
0x180007a9f  mov     eax, 3
0x180007aa4  mov     word ptr [rbp+pvarg], ax
0x180007aa8  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180007aac  mov     [rbp+var_40], 0
0x180007ab4  mov     rax, [rcx]
0x180007ab7  movaps  [rbp+var_20], xmm0
0x180007abb  movsd   [rbp+var_10], xmm1
0x180007ac0  mov     rax, [rax+48h]
0x180007ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac9  test    eax, eax
0x180007acb  jns     short loc_180007AFC
0x180007acd  mov     rax, [rbp+ppvObject]
0x180007ad1  mov     rcx, [rbp+pvarChild]; pvargDest
0x180007ad5  lea     rdx, [rbp+pvarg]; pvargSrc
0x180007ad9  mov     [rsi], rax
0x180007adc  call    cs:__imp_VariantCopy
0x180007ae2  mov     ebx, eax
0x180007ae4  lea     r11, [rsp+60h+var_s0]
0x180007ae9  mov     eax, ebx
0x180007aeb  mov     rbx, [r11+20h]
0x180007aef  mov     rsi, [r11+28h]
0x180007af3  mov     rsp, r11
0x180007af6  pop     r15
0x180007af8  pop     r14
0x180007afa  pop     rbp
0x180007afb  retn
0x180007afc  cmp     [rbp+var_40], 0
0x180007b01  jz      short loc_180007ACD
0x180007b03  mov     rcx, [rbp+ppvObject]
0x180007b07  mov     rax, [rcx]
0x180007b0a  mov     rax, [rax+10h]
0x180007b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b13  mov     rcx, [rbp+var_40]
0x180007b17  lea     r8, [rbp+ppvObject]
0x180007b1b  mov     [rbp+ppvObject], 0
0x180007b23  lea     rdx, IID_IAccessible
0x180007b2a  mov     rax, [rcx]
0x180007b2d  mov     rax, [rax]
0x180007b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b35  mov     rcx, [rbp+var_40]
0x180007b39  mov     ebx, eax
0x180007b3b  mov     rax, [rcx]
0x180007b3e  mov     rax, [rax+10h]
0x180007b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b47  test    ebx, ebx
0x180007b49  js      short loc_180007AE4
0x180007b4b  mov     rax, [rbp+ppvObject]
0x180007b4f  test    rax, rax
0x180007b52  jz      short loc_180007B60
0x180007b54  mov     dword ptr [rbp+pvarg+8], 0
0x180007b5b  jmp     loc_180007AD1
0x180007b60  mov     ebx, 80004005h
0x180007b65  jmp     loc_180007AE4
0x180007b6a  test    rbx, rbx
0x180007b6d  jz      loc_180007A40
0x180007b73  mov     ebx, 80070057h
0x180007b78  jmp     loc_180007AE4
0x180007b7d  call    ?InitOleacc@@YAHXZ; InitOleacc(void)
0x180007b82  jmp     loc_1800079FF
```
