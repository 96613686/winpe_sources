# CHNetPortMappingProtocol::GetIPProtocol(uchar *)

- ea: `0x180023a40`
- end: `0x180023afd`
- name: `?GetIPProtocol@CHNetPortMappingProtocol@@UEAAJPEAE@Z`
- size: `189`
- prototype: `__int64 __fastcall(CHNetPortMappingProtocol *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023a40`
- `0x180029a3c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180023a6c`
- `OLEAUT32!__imp_VariantInit` at `0x180023a6c`
- `OLEAUT32!__imp_VariantClear` at `0x180023aea`
- `OLEAUT32!__imp_VariantClear` at `0x180023aea`

## string_xrefs

- `0x180023aa9`: `IPProtocol`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingProtocol::GetIPProtocol(CHNetPortMappingProtocol *this, unsigned __int8 *a2)
{
  unsigned int WmiObjectFromPath; // ebx
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF
  struct IWbemClassObject *v7; // [rsp+78h] [rbp+10h] BYREF

  v7 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a2 )
  {
    WmiObjectFromPath = GetWmiObjectFromPath(
                          *((struct IWbemServices **)this + 9),
                          *((unsigned __int16 **)this + 10),
                          &v7);
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v7->lpVtbl->Get)(
                            v7,
                            L"IPProtocol",
                            0,
                            &pvarg,
                            0,
                            0);
      ((void (__fastcall *)(struct IWbemClassObject *))v7->lpVtbl->Release)(v7);
      if ( !WmiObjectFromPath )
      {
        *a2 = pvarg.bVal;
        VariantClear(&pvarg);
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
0x180023a40  mov     r11, rsp
0x180023a43  mov     [r11+8], rbx
0x180023a47  push    rdi
0x180023a48  sub     rsp, 60h
0x180023a4c  xorps   xmm0, xmm0
0x180023a4f  mov     qword ptr [r11+10h], 0
0x180023a57  mov     rbx, rcx
0x180023a5a  xor     eax, eax
0x180023a5c  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x180023a61  lea     rcx, [r11-28h]; pvarg
0x180023a65  mov     [r11-18h], rax
0x180023a69  mov     rdi, rdx
0x180023a6c  call    cs:__imp_VariantInit
0x180023a72  test    rdi, rdi
0x180023a75  jnz     short loc_180023A7E
0x180023a77  mov     ebx, 80004003h
0x180023a7c  jmp     short loc_180023AF0
0x180023a7e  mov     rdx, [rbx+50h]; unsigned __int16 *
0x180023a82  lea     r8, [rsp+68h+arg_8]; struct IWbemClassObject **
0x180023a87  mov     rcx, [rbx+48h]; struct IWbemServices *
0x180023a8b  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180023a90  mov     ebx, eax
0x180023a92  test    eax, eax
0x180023a94  jnz     short loc_180023AF0
0x180023a96  mov     rcx, [rsp+68h+arg_8]
0x180023a9b  lea     r9, [rsp+68h+pvarg]
0x180023aa0  mov     [rsp+68h+var_40], 0
0x180023aa9  lea     rdx, ?c_wszIPProtocol@@3QBGB; "IPProtocol"
0x180023ab0  xor     r8d, r8d
0x180023ab3  mov     [rsp+68h+var_48], 0
0x180023abc  mov     rax, [rcx]
0x180023abf  mov     rax, [rax+20h]
0x180023ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ac8  mov     rcx, [rsp+68h+arg_8]
0x180023acd  mov     ebx, eax
0x180023acf  mov     rax, [rcx]
0x180023ad2  mov     rax, [rax+10h]
0x180023ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023adb  test    ebx, ebx
0x180023add  jnz     short loc_180023AF0
0x180023adf  mov     al, byte ptr [rsp+68h+pvarg+8]
0x180023ae3  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180023ae8  mov     [rdi], al
0x180023aea  call    cs:__imp_VariantClear
0x180023af0  mov     eax, ebx
0x180023af2  mov     rbx, [rsp+68h+arg_0]
0x180023af7  add     rsp, 60h
0x180023afb  pop     rdi
0x180023afc  retn
```
