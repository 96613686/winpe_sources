# CCscWmiMethod::_GetMethodObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)

- ea: `0x18001b674`
- end: `0x18001b8b4`
- name: `?_GetMethodObject@CCscWmiMethod@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(CCscWmiMethod *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019adc`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800186c0`
- `0x18001b674`
- `0x18001c17c`
- `0x18001c208`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001b6f4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b784`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b6f4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b784`
- `OLEAUT32!__imp_VariantClear` at `0x18001b845`
- `OLEAUT32!__imp_VariantClear` at `0x18001b84f`
- `OLEAUT32!__imp_VariantClear` at `0x18001b845`
- `OLEAUT32!__imp_VariantClear` at `0x18001b84f`

## pseudocode

```c
__int64 __fastcall CCscWmiMethod::_GetMethodObject(
        CCscWmiMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemClassObject **a4)
{
  int v8; // ebx
  __int64 v9; // rdx
  HRESULT (__stdcall *GetObjectA)(IWbemServices *, const BSTR, int, IWbemContext *, IWbemClassObject **, IWbemCallResult **); // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rdx
  int v14; // eax
  int v15; // r8d
  struct IWbemClassObject *v16; // rcx
  VARIANTARG v18; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  signed __int64 v20; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+48h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  v8 = 0;
  *a4 = 0;
  if ( *((_QWORD *)this + 4) )
    goto LABEL_22;
  v9 = *((_QWORD *)this + 2);
  v18.vt = 0;
  ATL::CComVariant::operator=(&v18, v9);
  if ( SysStringLen(v18.bstrVal) )
  {
    GetObjectA = a2->lpVtbl->GetObjectA;
    v21 = 0;
    v8 = ((__int64 (__fastcall *)(struct IWbemServices *, LONGLONG, _QWORD, struct IWbemContext *, __int64 *, _QWORD))GetObjectA)(
           a2,
           v18.llVal,
           0,
           a3,
           &v21,
           0);
    if ( v8 >= 0 )
    {
      v13 = *((_QWORD *)this + 3);
      pvarg.vt = 0;
      ATL::CComVariant::operator=(&pvarg, v13);
      if ( SysStringLen(pvarg.bstrVal) )
      {
        v20 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, LONGLONG, _QWORD, _QWORD, signed __int64 *))(*(_QWORD *)v21 + 152LL))(
                v21,
                pvarg.llVal,
                0,
                0,
                &v20);
        v8 = v14;
        if ( v14 >= 0 )
        {
          if ( !_InterlockedCompareExchange64((volatile signed __int64 *)this + 4, v20, 0) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
          (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_DSS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 49, v15, v14, v18.llVal, pvarg.llVal);
        }
      }
      else
      {
        v8 = -2147024882;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      VariantClear(&pvarg);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_DS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v11, v12, v8, v18.llVal);
    }
  }
  else
  {
    v8 = -2147024882;
  }
  VariantClear(&v18);
  if ( v8 >= 0 )
  {
LABEL_22:
    v16 = (struct IWbemClassObject *)*((_QWORD *)this + 4);
    *a4 = v16;
    ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->AddRef)(v16);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      50,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001b674  mov     [rsp-28h+arg_8], rbx
0x18001b679  mov     [rsp-28h+arg_10], rsi
0x18001b67e  push    rbp
0x18001b67f  push    rdi
0x18001b680  push    r13
0x18001b682  push    r14
0x18001b684  push    r15
0x18001b686  mov     rbp, rsp
0x18001b689  sub     rsp, 70h
0x18001b68d  mov     r15, r9
0x18001b690  mov     r14, r8
0x18001b693  mov     rsi, rdx
0x18001b696  mov     rdi, rcx
0x18001b699  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6a0  lea     r13, WPP_GLOBAL_Control
0x18001b6a7  cmp     rcx, r13
0x18001b6aa  jz      short loc_18001B6CA
0x18001b6ac  test    dword ptr [rcx+1Ch], 4000000h
0x18001b6b3  jz      short loc_18001B6CA
0x18001b6b5  mov     rcx, [rcx+10h]
0x18001b6b9  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b6c0  mov     edx, 2Fh ; '/'
0x18001b6c5  call    WPP_SF_
0x18001b6ca  xor     ebx, ebx
0x18001b6cc  mov     qword ptr [r15], 0
0x18001b6d3  cmp     [rdi+20h], rbx
0x18001b6d7  jnz     loc_18001B859
0x18001b6dd  mov     rdx, [rdi+10h]
0x18001b6e1  lea     rcx, [rbp+var_30]
0x18001b6e5  xor     eax, eax
0x18001b6e7  mov     word ptr [rbp+var_30], ax
0x18001b6eb  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18001b6f0  mov     rcx, qword ptr [rbp+var_30+8]; pbstr
0x18001b6f4  call    cs:__imp_SysStringLen
0x18001b6fa  test    eax, eax
0x18001b6fc  jnz     short loc_18001B708
0x18001b6fe  mov     ebx, 8007000Eh
0x18001b703  jmp     loc_18001B84B
0x18001b708  mov     rax, [rsi]
0x18001b70b  lea     rcx, [rbp+arg_18]
0x18001b70f  mov     rdx, qword ptr [rbp+var_30+8]
0x18001b713  mov     r9, r14
0x18001b716  mov     [rsp+70h+var_48], rbx
0x18001b71b  xor     r8d, r8d
0x18001b71e  mov     [rsp+70h+var_50], rcx
0x18001b723  mov     rcx, rsi
0x18001b726  mov     rax, [rax+30h]
0x18001b72a  mov     [rbp+arg_18], rbx
0x18001b72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b733  mov     ebx, eax
0x18001b735  test    eax, eax
0x18001b737  jns     short loc_18001B76D
0x18001b739  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b740  cmp     rcx, r13
0x18001b743  jz      loc_18001B84B
0x18001b749  test    byte ptr [rcx+1Ch], 2
0x18001b74d  jz      loc_18001B84B
0x18001b753  mov     rax, qword ptr [rbp+var_30+8]
0x18001b757  mov     r9d, ebx
0x18001b75a  mov     rcx, [rcx+10h]
0x18001b75e  mov     [rsp+70h+var_50], rax
0x18001b763  call    WPP_SF_DS
0x18001b768  jmp     loc_18001B84B
0x18001b76d  mov     rdx, [rdi+18h]
0x18001b771  lea     rcx, [rbp+pvarg]
0x18001b775  xor     eax, eax
0x18001b777  mov     word ptr [rbp+pvarg], ax
0x18001b77b  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18001b780  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x18001b784  call    cs:__imp_SysStringLen
0x18001b78a  test    eax, eax
0x18001b78c  jnz     short loc_18001B798
0x18001b78e  mov     ebx, 8007000Eh
0x18001b793  jmp     loc_18001B831
0x18001b798  mov     rcx, [rbp+arg_18]
0x18001b79c  lea     rdx, [rbp+arg_0]
0x18001b7a0  mov     [rbp+arg_0], 0
0x18001b7a8  xor     r9d, r9d
0x18001b7ab  mov     [rsp+70h+var_50], rdx
0x18001b7b0  xor     r8d, r8d
0x18001b7b3  mov     rdx, qword ptr [rbp+pvarg+8]
0x18001b7b7  mov     rax, [rcx]
0x18001b7ba  mov     rax, [rax+98h]
0x18001b7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7c6  mov     ebx, eax
0x18001b7c8  test    eax, eax
0x18001b7ca  jns     short loc_18001B803
0x18001b7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7d3  cmp     rcx, r13
0x18001b7d6  jz      short loc_18001B831
0x18001b7d8  test    byte ptr [rcx+1Ch], 2
0x18001b7dc  jz      short loc_18001B831
0x18001b7de  mov     rax, qword ptr [rbp+pvarg+8]
0x18001b7e2  mov     edx, 31h ; '1'
0x18001b7e7  mov     rcx, [rcx+10h]
0x18001b7eb  mov     r9d, ebx
0x18001b7ee  mov     [rsp+70h+var_48], rax
0x18001b7f3  mov     rax, qword ptr [rbp+var_30+8]
0x18001b7f7  mov     [rsp+70h+var_50], rax
0x18001b7fc  call    WPP_SF_DSS
0x18001b801  jmp     short loc_18001B831
0x18001b803  mov     rcx, [rbp+arg_0]
0x18001b807  xor     eax, eax
0x18001b809  lock cmpxchg [rdi+20h], rcx
0x18001b80f  jnz     short loc_18001B821
0x18001b811  mov     rcx, [rdi+20h]
0x18001b815  mov     rax, [rcx]
0x18001b818  mov     rax, [rax+8]
0x18001b81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b821  mov     rcx, [rbp+arg_0]
0x18001b825  mov     rax, [rcx]
0x18001b828  mov     rax, [rax+10h]
0x18001b82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b831  mov     rcx, [rbp+arg_18]
0x18001b835  mov     rax, [rcx]
0x18001b838  mov     rax, [rax+10h]
0x18001b83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b841  lea     rcx, [rbp+pvarg]; pvarg
0x18001b845  call    cs:__imp_VariantClear
0x18001b84b  lea     rcx, [rbp+var_30]; pvarg
0x18001b84f  call    cs:__imp_VariantClear
0x18001b855  test    ebx, ebx
0x18001b857  js      short loc_18001B86C
0x18001b859  mov     rcx, [rdi+20h]
0x18001b85d  mov     [r15], rcx
0x18001b860  mov     rax, [rcx]
0x18001b863  mov     rax, [rax+8]
0x18001b867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b86c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b873  cmp     rcx, r13
0x18001b876  jz      short loc_18001B899
0x18001b878  test    dword ptr [rcx+1Ch], 4000000h
0x18001b87f  jz      short loc_18001B899
0x18001b881  mov     rcx, [rcx+10h]
0x18001b885  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b88c  mov     edx, 32h ; '2'
0x18001b891  mov     r9d, ebx
0x18001b894  call    WPP_SF_d
0x18001b899  lea     r11, [rsp+70h+var_s0]
0x18001b89e  mov     eax, ebx
0x18001b8a0  mov     rbx, [r11+38h]
0x18001b8a4  mov     rsi, [r11+40h]
0x18001b8a8  mov     rsp, r11
0x18001b8ab  pop     r15
0x18001b8ad  pop     r14
0x18001b8af  pop     r13
0x18001b8b1  pop     rdi
0x18001b8b2  pop     rbp
0x18001b8b3  retn
```
