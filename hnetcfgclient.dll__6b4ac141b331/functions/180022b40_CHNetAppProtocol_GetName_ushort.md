# CHNetAppProtocol::GetName(ushort * *)

- ea: `0x180022b40`
- end: `0x180022c47`
- name: `?GetName@CHNetAppProtocol@@UEAAJPEAPEAG@Z`
- size: `263`
- prototype: `__int64 __fastcall(CHNetAppProtocol *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005698`
- `0x180022b40`
- `0x180029a3c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180022bf6`
- `OLEAUT32!__imp_SysStringLen` at `0x180022bf6`
- `OLEAUT32!__imp_VariantInit` at `0x180022b70`
- `OLEAUT32!__imp_VariantInit` at `0x180022b70`
- `OLEAUT32!__imp_VariantClear` at `0x180022c2d`
- `OLEAUT32!__imp_VariantClear` at `0x180022c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022c04`

## pseudocode

```c
__int64 __fastcall CHNetAppProtocol::GetName(CHNetAppProtocol *this, unsigned __int16 **a2)
{
  unsigned int WmiObjectFromPath; // ebx
  __int64 v5; // rsi
  unsigned __int16 *v6; // rax
  VARIANTARG pbstr; // [rsp+40h] [rbp-28h] BYREF
  struct IWbemClassObject *v9; // [rsp+78h] [rbp+10h] BYREF

  v9 = 0;
  memset(&pbstr, 0, sizeof(pbstr));
  VariantInit(&pbstr);
  if ( a2 )
  {
    *a2 = 0;
    WmiObjectFromPath = GetWmiObjectFromPath(
                          *((struct IWbemServices **)this + 8),
                          *((unsigned __int16 **)this + 9),
                          &v9);
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v9->lpVtbl->Get)(
                            v9,
                            L"Name",
                            0,
                            &pbstr,
                            0,
                            0);
      ((void (__fastcall *)(struct IWbemClassObject *))v9->lpVtbl->Release)(v9);
      if ( !WmiObjectFromPath )
      {
        v5 = SysStringLen(pbstr.bstrVal) + 1;
        v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5);
        *a2 = v6;
        if ( v6 )
          StringCchCopyW(v6, (unsigned int)v5, pbstr.bstrVal);
        else
          WmiObjectFromPath = -2147024882;
        VariantClear(&pbstr);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return WmiObjectFromPath;
}

```

## disassembly

```asm
0x180022b40  mov     r11, rsp
0x180022b43  mov     [r11+8], rbx
0x180022b47  mov     [r11+18h], rsi
0x180022b4b  push    rdi
0x180022b4c  sub     rsp, 60h
0x180022b50  xorps   xmm0, xmm0
0x180022b53  mov     qword ptr [r11+10h], 0
0x180022b5b  mov     rbx, rcx
0x180022b5e  xor     eax, eax
0x180022b60  movups  xmmword ptr [rsp+68h+pbstr], xmm0
0x180022b65  lea     rcx, [r11-28h]; pvarg
0x180022b69  mov     [r11-18h], rax
0x180022b6d  mov     rdi, rdx
0x180022b70  call    cs:__imp_VariantInit
0x180022b76  test    rdi, rdi
0x180022b79  jnz     short loc_180022B85
0x180022b7b  mov     ebx, 80004003h
0x180022b80  jmp     loc_180022C33
0x180022b85  mov     qword ptr [rdi], 0
0x180022b8c  lea     r8, [rsp+68h+arg_8]; struct IWbemClassObject **
0x180022b91  mov     rdx, [rbx+48h]; unsigned __int16 *
0x180022b95  mov     rcx, [rbx+40h]; struct IWbemServices *
0x180022b99  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180022b9e  mov     ebx, eax
0x180022ba0  test    eax, eax
0x180022ba2  jnz     loc_180022C33
0x180022ba8  mov     rcx, [rsp+68h+arg_8]
0x180022bad  lea     r9, [rsp+68h+pbstr]
0x180022bb2  mov     [rsp+68h+var_40], 0
0x180022bbb  lea     rdx, ?c_wszName@@3QBGB; "Name"
0x180022bc2  xor     r8d, r8d
0x180022bc5  mov     [rsp+68h+var_48], 0
0x180022bce  mov     rax, [rcx]
0x180022bd1  mov     rax, [rax+20h]
0x180022bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bda  mov     rcx, [rsp+68h+arg_8]
0x180022bdf  mov     ebx, eax
0x180022be1  mov     rax, [rcx]
0x180022be4  mov     rax, [rax+10h]
0x180022be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bed  test    ebx, ebx
0x180022bef  jnz     short loc_180022C33
0x180022bf1  mov     rcx, qword ptr [rsp+68h+pbstr+8]; pbstr
0x180022bf6  call    cs:__imp_SysStringLen
0x180022bfc  inc     eax
0x180022bfe  mov     esi, eax
0x180022c00  lea     rcx, [rax+rax]; cb
0x180022c04  call    cs:__imp_CoTaskMemAlloc
0x180022c0a  mov     [rdi], rax
0x180022c0d  test    rax, rax
0x180022c10  jz      short loc_180022C23
0x180022c12  mov     r8, qword ptr [rsp+68h+pbstr+8]; unsigned __int16 *
0x180022c17  mov     edx, esi; unsigned __int64
0x180022c19  mov     rcx, rax; unsigned __int16 *
0x180022c1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022c21  jmp     short loc_180022C28
0x180022c23  mov     ebx, 8007000Eh
0x180022c28  lea     rcx, [rsp+68h+pbstr]; pvarg
0x180022c2d  call    cs:__imp_VariantClear
0x180022c33  lea     r11, [rsp+68h+var_8]
0x180022c38  mov     eax, ebx
0x180022c3a  mov     rbx, [r11+10h]
0x180022c3e  mov     rsi, [r11+20h]
0x180022c42  mov     rsp, r11
0x180022c45  pop     rdi
0x180022c46  retn
```
