# CHNetPortMappingProtocol::GetName(ushort * *)

- ea: `0x180023b10`
- end: `0x180023ca3`
- name: `?GetName@CHNetPortMappingProtocol@@UEAAJPEAPEAG@Z`
- size: `403`
- prototype: `__int64 __fastcall(CHNetPortMappingProtocol *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005698`
- `0x180023b10`
- `0x180029a3c`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180023bea`
- `msvcrt!_wtoi` at `0x180023bea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023c08`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023c08`
- `OLEAUT32!__imp_SysStringLen` at `0x180023c42`
- `OLEAUT32!__imp_SysStringLen` at `0x180023c42`
- `OLEAUT32!__imp_VariantInit` at `0x180023b5b`
- `OLEAUT32!__imp_VariantInit` at `0x180023b5b`
- `OLEAUT32!__imp_VariantClear` at `0x180023c79`
- `OLEAUT32!__imp_VariantClear` at `0x180023c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023c50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHNetPortMappingProtocol::GetName(CHNetPortMappingProtocol *this, unsigned __int16 **a2)
{
  unsigned int WmiObjectFromPath; // ebx
  UINT v5; // eax
  int StringW; // eax
  __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  struct IWbemClassObject *v12; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[256]; // [rsp+60h] [rbp-A0h] BYREF

  v12 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a2 )
    return (unsigned int)-2147467261;
  *a2 = 0;
  WmiObjectFromPath = GetWmiObjectFromPath(
                        *((struct IWbemServices **)this + 9),
                        *((unsigned __int16 **)this + 10),
                        &v12);
  if ( !WmiObjectFromPath )
  {
    WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v12->lpVtbl->Get)(
                          v12,
                          L"Name",
                          0,
                          &pvarg,
                          0,
                          0);
    ((void (__fastcall *)(struct IWbemClassObject *))v12->lpVtbl->Release)(v12);
    if ( !WmiObjectFromPath )
    {
      if ( *((_BYTE *)this + 88) )
      {
        v5 = _wtoi(pvarg.bstrVal);
        if ( v5 )
        {
          StringW = LoadStringW(hInstance, v5, Buffer, 256);
          if ( StringW )
          {
            v7 = (unsigned int)(StringW + 1);
            v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7);
            *a2 = v8;
            if ( !v8 )
              goto LABEL_13;
            StringCchCopyW(v8, (unsigned int)v7, Buffer);
          }
        }
      }
      if ( *a2 )
      {
LABEL_14:
        VariantClear(&pvarg);
        return WmiObjectFromPath;
      }
      v9 = SysStringLen(pvarg.bstrVal) + 1;
      v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9);
      *a2 = v10;
      if ( v10 )
      {
        StringCchCopyW(v10, (unsigned int)v9, pvarg.bstrVal);
        goto LABEL_14;
      }
LABEL_13:
      WmiObjectFromPath = -2147024882;
      goto LABEL_14;
    }
  }
  return WmiObjectFromPath;
}

```

## disassembly

```asm
0x180023b10  mov     [rsp-8+arg_10], rbx
0x180023b15  push    rbp
0x180023b16  push    rsi
0x180023b17  push    rdi
0x180023b18  lea     rbp, [rsp-170h]
0x180023b20  sub     rsp, 270h
0x180023b27  mov     rax, cs:__security_cookie
0x180023b2e  xor     rax, rsp
0x180023b31  mov     [rbp+180h+var_20], rax
0x180023b38  mov     rsi, rcx
0x180023b3b  mov     [rsp+280h+var_240], 0
0x180023b44  xorps   xmm0, xmm0
0x180023b47  lea     rcx, [rsp+280h+pvarg]; pvarg
0x180023b4c  xor     eax, eax
0x180023b4e  mov     rdi, rdx
0x180023b51  movups  xmmword ptr [rsp+280h+pvarg], xmm0
0x180023b56  mov     qword ptr [rsp+280h+pvarg+10h], rax
0x180023b5b  call    cs:__imp_VariantInit
0x180023b61  test    rdi, rdi
0x180023b64  jnz     short loc_180023B70
0x180023b66  mov     ebx, 80004003h
0x180023b6b  jmp     loc_180023C7F
0x180023b70  mov     qword ptr [rdi], 0
0x180023b77  lea     r8, [rsp+280h+var_240]; struct IWbemClassObject **
0x180023b7c  mov     rdx, [rsi+50h]; unsigned __int16 *
0x180023b80  mov     rcx, [rsi+48h]; struct IWbemServices *
0x180023b84  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180023b89  mov     ebx, eax
0x180023b8b  test    eax, eax
0x180023b8d  jnz     loc_180023C7F
0x180023b93  mov     rcx, [rsp+280h+var_240]
0x180023b98  lea     r9, [rsp+280h+pvarg]
0x180023b9d  mov     [rsp+280h+var_258], 0
0x180023ba6  lea     rdx, ?c_wszName@@3QBGB; "Name"
0x180023bad  xor     r8d, r8d
0x180023bb0  mov     [rsp+280h+var_260], 0
0x180023bb9  mov     rax, [rcx]
0x180023bbc  mov     rax, [rax+20h]
0x180023bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bc5  mov     rcx, [rsp+280h+var_240]
0x180023bca  mov     ebx, eax
0x180023bcc  mov     rax, [rcx]
0x180023bcf  mov     rax, [rax+10h]
0x180023bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bd8  test    ebx, ebx
0x180023bda  jnz     loc_180023C7F
0x180023be0  cmp     [rsi+58h], bl
0x180023be3  jz      short loc_180023C37
0x180023be5  mov     rcx, qword ptr [rsp+280h+pvarg+8]; String
0x180023bea  call    cs:__imp__wtoi
0x180023bf0  test    eax, eax
0x180023bf2  jz      short loc_180023C37
0x180023bf4  mov     rcx, cs:hInstance; hInstance
0x180023bfb  lea     r8, [rsp+280h+Buffer]; lpBuffer
0x180023c00  mov     r9d, 100h; cchBufferMax
0x180023c06  mov     edx, eax; uID
0x180023c08  call    cs:__imp_LoadStringW
0x180023c0e  test    eax, eax
0x180023c10  jz      short loc_180023C37
0x180023c12  inc     eax
0x180023c14  mov     esi, eax
0x180023c16  lea     rcx, [rax+rax]; cb
0x180023c1a  call    cs:__imp_CoTaskMemAlloc
0x180023c20  mov     [rdi], rax
0x180023c23  test    rax, rax
0x180023c26  jz      short loc_180023C6F
0x180023c28  lea     r8, [rsp+280h+Buffer]; unsigned __int16 *
0x180023c2d  mov     edx, esi; unsigned __int64
0x180023c2f  mov     rcx, rax; unsigned __int16 *
0x180023c32  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023c37  cmp     qword ptr [rdi], 0
0x180023c3b  jnz     short loc_180023C74
0x180023c3d  mov     rcx, qword ptr [rsp+280h+pvarg+8]; pbstr
0x180023c42  call    cs:__imp_SysStringLen
0x180023c48  inc     eax
0x180023c4a  mov     esi, eax
0x180023c4c  lea     rcx, [rax+rax]; cb
0x180023c50  call    cs:__imp_CoTaskMemAlloc
0x180023c56  mov     [rdi], rax
0x180023c59  test    rax, rax
0x180023c5c  jz      short loc_180023C6F
0x180023c5e  mov     r8, qword ptr [rsp+280h+pvarg+8]; unsigned __int16 *
0x180023c63  mov     edx, esi; unsigned __int64
0x180023c65  mov     rcx, rax; unsigned __int16 *
0x180023c68  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023c6d  jmp     short loc_180023C74
0x180023c6f  mov     ebx, 8007000Eh
0x180023c74  lea     rcx, [rsp+280h+pvarg]; pvarg
0x180023c79  call    cs:__imp_VariantClear
0x180023c7f  mov     eax, ebx
0x180023c81  mov     rcx, [rbp+180h+var_20]
0x180023c88  xor     rcx, rsp; StackCookie
0x180023c8b  call    __security_check_cookie
0x180023c90  mov     rbx, [rsp+280h+arg_10]
0x180023c98  add     rsp, 270h
0x180023c9f  pop     rdi
0x180023ca0  pop     rsi
0x180023ca1  pop     rbp
0x180023ca2  retn
```
