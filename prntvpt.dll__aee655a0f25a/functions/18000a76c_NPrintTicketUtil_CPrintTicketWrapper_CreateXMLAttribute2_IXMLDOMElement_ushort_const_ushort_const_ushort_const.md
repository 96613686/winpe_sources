# NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute2(IXMLDOMElement *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000a76c`
- end: `0x18000a95a`
- name: `?CreateXMLAttribute2@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11@Z`
- size: `494`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, OLECHAR *psz)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006d70`
- `0x1800073e4`

## callees

- `0x18000a76c`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a8c7`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a8c7`
- `OLEAUT32!__imp_VariantInit` at `0x18000a830`
- `OLEAUT32!__imp_VariantInit` at `0x18000a8d9`
- `OLEAUT32!__imp_VariantInit` at `0x18000a830`
- `OLEAUT32!__imp_VariantInit` at `0x18000a8d9`
- `OLEAUT32!__imp_VariantClear` at `0x18000a7c4`
- `OLEAUT32!__imp_VariantClear` at `0x18000a884`
- `OLEAUT32!__imp_VariantClear` at `0x18000a923`
- `OLEAUT32!__imp_VariantClear` at `0x18000a7c4`
- `OLEAUT32!__imp_VariantClear` at `0x18000a884`
- `OLEAUT32!__imp_VariantClear` at `0x18000a923`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute2(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        OLECHAR *psz)
{
  HRESULT v9; // ebx
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64 *, __int128 *, const unsigned __int16 *, const unsigned __int16 *, __int64 *); // rax
  BSTR v14; // rbx
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64 *, __int128 *); // rax
  __int64 *v17; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  __int128 v19; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int64 v21; // [rsp+98h] [rbp+28h] BYREF

  v17 = 0;
  v21 = 0;
  if ( a2 && a3 && a4 && psz )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v11 = (__int64 *)*((_QWORD *)this + 1);
    pvarg.vt = 3;
    pvarg.lVal = 2;
    v12 = *v11;
    pRecInfo = pvarg.pRecInfo;
    v13 = *(__int64 (__fastcall **)(__int64 *, __int128 *, const unsigned __int16 *, const unsigned __int16 *, __int64 *))(v12 + 448);
    v19 = *(_OWORD *)&pvarg.vt;
    v9 = v13(v11, &v19, a3, a4, &v21);
    VariantClear(&pvarg);
    if ( v9 >= 0 )
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v21)(v21, &IID_IXMLDOMAttribute, &v17);
      if ( v9 >= 0 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        v14 = SysAllocString(psz);
        if ( v14 )
        {
          VariantInit(&pvarg);
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)v14;
          v15 = *v17;
          pRecInfo = pvarg.pRecInfo;
          v16 = *(__int64 (__fastcall **)(__int64 *, __int128 *))(v15 + 360);
          v19 = *(_OWORD *)&pvarg.vt;
          v9 = v16(v17, &v19);
          if ( v9 >= 0 )
            v9 = VariantClear(&pvarg);
          else
            VariantClear(&pvarg);
          if ( v9 >= 0 )
            v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *, _QWORD))a2->lpVtbl->setAttributeNode)(
                   a2,
                   v17,
                   0);
        }
        else
        {
          v9 = -2147024882;
        }
      }
    }
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
    }
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a76c  mov     [rsp-18h+arg_0], rbx
0x18000a771  mov     [rsp-18h+arg_10], rsi
0x18000a776  push    rbp
0x18000a777  push    r14
0x18000a779  push    r15
0x18000a77b  mov     rbp, rsp
0x18000a77e  sub     rsp, 70h
0x18000a782  mov     [rbp+var_40], 0
0x18000a78a  mov     rbx, r9
0x18000a78d  mov     [rbp+arg_8], 0
0x18000a795  mov     r14, r8
0x18000a798  mov     rsi, rdx
0x18000a79b  mov     r15, rcx
0x18000a79e  test    rdx, rdx
0x18000a7a1  jnz     loc_18000A938
0x18000a7a7  mov     ebx, 80070057h
0x18000a7ac  lea     r11, [rsp+70h+var_s0]
0x18000a7b1  mov     eax, ebx
0x18000a7b3  mov     rbx, [r11+20h]
0x18000a7b7  mov     rsi, [r11+30h]
0x18000a7bb  mov     rsp, r11
0x18000a7be  pop     r15
0x18000a7c0  pop     r14
0x18000a7c2  pop     rbp
0x18000a7c3  retn
0x18000a7c4  call    cs:__imp_VariantClear
0x18000a7ca  mov     ebx, eax
0x18000a7cc  test    ebx, ebx
0x18000a7ce  js      short loc_18000A7EB
0x18000a7d0  mov     rax, [rsi]
0x18000a7d3  xor     r8d, r8d
0x18000a7d6  mov     rdx, [rbp+var_40]
0x18000a7da  mov     rcx, rsi
0x18000a7dd  mov     rax, [rax+180h]
0x18000a7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e9  mov     ebx, eax
0x18000a7eb  mov     rcx, [rbp+arg_8]
0x18000a7ef  test    rcx, rcx
0x18000a7f2  jz      short loc_18000A808
0x18000a7f4  mov     rax, [rcx]
0x18000a7f7  mov     rax, [rax+10h]
0x18000a7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a800  mov     [rbp+arg_8], 0
0x18000a808  mov     rcx, [rbp+var_40]
0x18000a80c  test    rcx, rcx
0x18000a80f  jz      short loc_18000A7AC
0x18000a811  mov     rax, [rcx]
0x18000a814  mov     rax, [rax+10h]
0x18000a818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a81d  jmp     short loc_18000A7AC
0x18000a81f  xorps   xmm0, xmm0
0x18000a822  lea     rcx, [rbp+pvarg]; pvarg
0x18000a826  xor     eax, eax
0x18000a828  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000a82c  mov     qword ptr [rbp+pvarg+10h], rax
0x18000a830  call    cs:__imp_VariantInit
0x18000a836  mov     rcx, [r15+8]
0x18000a83a  lea     rdx, [rbp+arg_8]
0x18000a83e  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000a843  mov     eax, 3
0x18000a848  mov     word ptr [rbp+pvarg], ax
0x18000a84c  mov     r9, rbx
0x18000a84f  mov     dword ptr [rbp+pvarg+8], 2
0x18000a856  mov     r8, r14
0x18000a859  mov     rax, [rcx]
0x18000a85c  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000a860  mov     [rsp+70h+var_50], rdx
0x18000a865  lea     rdx, [rbp+var_20]
0x18000a869  movsd   [rbp+var_10], xmm1
0x18000a86e  mov     rax, [rax+1C0h]
0x18000a875  movaps  [rbp+var_20], xmm0
0x18000a879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a87e  lea     rcx, [rbp+pvarg]; pvarg
0x18000a882  mov     ebx, eax
0x18000a884  call    cs:__imp_VariantClear
0x18000a88a  test    ebx, ebx
0x18000a88c  js      loc_18000A7EB
0x18000a892  mov     rcx, [rbp+arg_8]
0x18000a896  lea     r8, [rbp+var_40]
0x18000a89a  lea     rdx, IID_IXMLDOMAttribute
0x18000a8a1  mov     rax, [rcx]
0x18000a8a4  mov     rax, [rax]
0x18000a8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ac  mov     ebx, eax
0x18000a8ae  test    eax, eax
0x18000a8b0  js      loc_18000A7EB
0x18000a8b6  mov     rcx, [rbp+psz]; psz
0x18000a8ba  xorps   xmm0, xmm0
0x18000a8bd  xor     eax, eax
0x18000a8bf  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000a8c3  mov     qword ptr [rbp+pvarg+10h], rax
0x18000a8c7  call    cs:__imp_SysAllocString
0x18000a8cd  mov     rbx, rax
0x18000a8d0  test    rax, rax
0x18000a8d3  jz      short loc_18000A92E
0x18000a8d5  lea     rcx, [rbp+pvarg]; pvarg
0x18000a8d9  call    cs:__imp_VariantInit
0x18000a8df  mov     rcx, [rbp+var_40]
0x18000a8e3  lea     rdx, [rbp+var_20]
0x18000a8e7  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000a8ec  mov     eax, 8
0x18000a8f1  mov     word ptr [rbp+pvarg], ax
0x18000a8f5  mov     qword ptr [rbp+pvarg+8], rbx
0x18000a8f9  mov     rax, [rcx]
0x18000a8fc  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000a900  movsd   [rbp+var_10], xmm1
0x18000a905  mov     rax, [rax+168h]
0x18000a90c  movaps  [rbp+var_20], xmm0
0x18000a910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a915  lea     rcx, [rbp+pvarg]; pvarg
0x18000a919  mov     ebx, eax
0x18000a91b  test    eax, eax
0x18000a91d  jns     loc_18000A7C4
0x18000a923  call    cs:__imp_VariantClear
0x18000a929  jmp     loc_18000A7CC
0x18000a92e  mov     ebx, 8007000Eh
0x18000a933  jmp     loc_18000A7EB
0x18000a938  test    r14, r14
0x18000a93b  jz      loc_18000A7A7
0x18000a941  test    rbx, rbx
0x18000a944  jz      loc_18000A7A7
0x18000a94a  cmp     [rbp+psz], 0
0x18000a94f  jz      loc_18000A7A7
0x18000a955  jmp     loc_18000A81F
```
