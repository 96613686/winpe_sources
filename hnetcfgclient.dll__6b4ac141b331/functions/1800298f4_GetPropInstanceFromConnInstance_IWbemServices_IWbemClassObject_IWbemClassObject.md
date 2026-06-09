# GetPropInstanceFromConnInstance(IWbemServices *,IWbemClassObject *,IWbemClassObject * *)

- ea: `0x1800298f4`
- end: `0x180029a36`
- name: `?GetPropInstanceFromConnInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@PEAPEAU2@@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemClassObject *, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18001dcc8`
- `0x18002914c`

## callees

- `0x180001ec4`
- `0x1800056dc`
- `0x1800298f4`
- `0x180029a3c`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180029a10`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029a10`
- `OLEAUT32!__imp_SysAllocString` at `0x180029996`
- `OLEAUT32!__imp_SysAllocString` at `0x180029996`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299b7`
- `OLEAUT32!__imp_SysStringLen` at `0x180029965`
- `OLEAUT32!__imp_SysStringLen` at `0x180029965`
- `OLEAUT32!__imp_VariantClear` at `0x1800299fd`
- `OLEAUT32!__imp_VariantClear` at `0x1800299fd`

## pseudocode

```c
__int64 __fastcall GetPropInstanceFromConnInstance(
        struct IWbemServices *a1,
        struct IWbemClassObject *a2,
        struct IWbemClassObject **a3)
{
  unsigned __int16 *v3; // rdi
  HRESULT (__stdcall *Get)(IWbemClassObject *, LPCWSTR, int, VARIANT *, CIMTYPE *, int *); // rax
  unsigned int WmiObjectFromPath; // ebx
  UINT v8; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rax
  OLECHAR *v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // kr00_8
  VARIANTARG pbstr; // [rsp+40h] [rbp-268h] BYREF
  OLECHAR psz[264]; // [rsp+60h] [rbp-248h] BYREF

  v3 = 0;
  Get = a2->lpVtbl->Get;
  memset(&pbstr, 0, sizeof(pbstr));
  WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))Get)(
                        a2,
                        L"Guid",
                        0,
                        &pbstr,
                        0,
                        0);
  if ( WmiObjectFromPath )
    goto LABEL_12;
  v8 = SysStringLen(pbstr.bstrVal) + 67;
  v9 = 256;
  if ( v8 > 0x100 )
  {
    v9 = v8;
    v13 = v8 + 1;
    v12 = 2 * v13;
    if ( !is_mul_ok(v13, 2u) )
      v12 = -1;
    v3 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v3 )
    {
      v3 = psz;
      goto LABEL_10;
    }
  }
  else
  {
    v3 = psz;
  }
  StringCchPrintfW(
    v3,
    (unsigned int)(v9 + 1),
    L"HNet_ConnectionProperties.Connection=\"HNet_Connection.Guid=\\\"%s\\\"\"",
    pbstr.llVal);
  v10 = SysAllocString(v3);
  v11 = v10;
  if ( v10 )
  {
    WmiObjectFromPath = GetWmiObjectFromPath(a1, v10, a3);
    SysFreeString(v11);
    goto LABEL_11;
  }
LABEL_10:
  WmiObjectFromPath = -2147024882;
LABEL_11:
  VariantClear(&pbstr);
  if ( psz != v3 )
LABEL_12:
    operator delete[](v3);
  return WmiObjectFromPath;
}

```

## disassembly

```asm
0x1800298f4  push    rbx
0x1800298f6  push    rbp
0x1800298f7  push    rsi
0x1800298f8  push    rdi
0x1800298f9  push    r14
0x1800298fb  sub     rsp, 280h
0x180029902  mov     rax, cs:__security_cookie
0x180029909  xor     rax, rsp
0x18002990c  mov     [rsp+2A8h+var_38], rax
0x180029914  xor     eax, eax
0x180029916  lea     r9, [rsp+2A8h+pbstr]
0x18002991b  mov     [rsp+2A8h+var_258], rax
0x180029920  mov     r10, rdx
0x180029923  mov     rax, [rdx]
0x180029926  xor     edi, edi
0x180029928  mov     r14, r8
0x18002992b  mov     [rsp+2A8h+var_280], rdi
0x180029930  mov     rbp, rcx
0x180029933  mov     [rsp+2A8h+var_288], rdi
0x180029938  xorps   xmm0, xmm0
0x18002993b  lea     rdx, ?c_wszGuid@@3QBGB; "Guid"
0x180029942  mov     rax, [rax+20h]
0x180029946  xor     r8d, r8d
0x180029949  mov     rcx, r10
0x18002994c  movups  xmmword ptr [rsp+2A8h+pbstr], xmm0
0x180029951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029956  mov     ebx, eax
0x180029958  test    eax, eax
0x18002995a  jnz     loc_180029A0D
0x180029960  mov     rcx, [rsp+2A8h+pbstr+8]; pbstr
0x180029965  call    cs:__imp_SysStringLen
0x18002996b  add     eax, 43h ; 'C'
0x18002996e  mov     ebx, 100h
0x180029973  cmp     eax, ebx
0x180029975  ja      short loc_1800299BF
0x180029977  lea     rdi, [rsp+2A8h+psz]
0x18002997c  mov     r9, [rsp+2A8h+pbstr+8]
0x180029981  lea     edx, [rbx+1]; unsigned __int64
0x180029984  lea     r8, ?c_wszConnectionPropertiesPathFormat@@3QBGB; "HNet_ConnectionProperties.Connection=\""...
0x18002998b  mov     rcx, rdi; unsigned __int16 *
0x18002998e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029993  mov     rcx, rdi; psz
0x180029996  call    cs:__imp_SysAllocString
0x18002999c  mov     rsi, rax
0x18002999f  test    rax, rax
0x1800299a2  jz      short loc_1800299F3
0x1800299a4  mov     r8, r14; struct IWbemClassObject **
0x1800299a7  mov     rdx, rax; unsigned __int16 *
0x1800299aa  mov     rcx, rbp; struct IWbemServices *
0x1800299ad  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x1800299b2  mov     rcx, rsi; bstrString
0x1800299b5  mov     ebx, eax
0x1800299b7  call    cs:__imp_SysFreeString
0x1800299bd  jmp     short loc_1800299F8
0x1800299bf  lea     ecx, [rax+1]
0x1800299c2  mov     ebx, eax
0x1800299c4  mov     eax, 2
0x1800299c9  mul     rcx
0x1800299cc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800299d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800299da  cmovb   rax, rcx
0x1800299de  mov     rcx, rax; unsigned __int64
0x1800299e1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800299e6  mov     rdi, rax
0x1800299e9  test    rax, rax
0x1800299ec  jnz     short loc_18002997C
0x1800299ee  lea     rdi, [rsp+2A8h+psz]
0x1800299f3  mov     ebx, 8007000Eh
0x1800299f8  lea     rcx, [rsp+2A8h+pbstr]; pvarg
0x1800299fd  call    cs:__imp_VariantClear
0x180029a03  lea     rax, [rsp+2A8h+psz]
0x180029a08  cmp     rax, rdi
0x180029a0b  jz      short loc_180029A16
0x180029a0d  mov     rcx, rdi
0x180029a10  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029a16  mov     eax, ebx
0x180029a18  mov     rcx, [rsp+2A8h+var_38]
0x180029a20  xor     rcx, rsp; StackCookie
0x180029a23  call    __security_check_cookie
0x180029a28  add     rsp, 280h
0x180029a2f  pop     r14
0x180029a31  pop     rdi
0x180029a32  pop     rsi
0x180029a33  pop     rbp
0x180029a34  pop     rbx
0x180029a35  retn
```
