# CHNetAppProtocol::GetOutgoingIPProtocol(uchar *)

- ea: `0x180022c50`
- end: `0x180022d0d`
- name: `?GetOutgoingIPProtocol@CHNetAppProtocol@@UEAAJPEAE@Z`
- size: `189`
- prototype: `__int64 __fastcall(CHNetAppProtocol *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180022c50`
- `0x180029a3c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180022c7c`
- `OLEAUT32!__imp_VariantInit` at `0x180022c7c`
- `OLEAUT32!__imp_VariantClear` at `0x180022cfa`
- `OLEAUT32!__imp_VariantClear` at `0x180022cfa`

## string_xrefs

- `0x180022cb9`: `OutgoingIPProtocol`

## pseudocode

```c
__int64 __fastcall CHNetAppProtocol::GetOutgoingIPProtocol(CHNetAppProtocol *this, unsigned __int8 *a2)
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
                          *((struct IWbemServices **)this + 8),
                          *((unsigned __int16 **)this + 9),
                          &v7);
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v7->lpVtbl->Get)(
                            v7,
                            L"OutgoingIPProtocol",
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
0x180022c50  mov     r11, rsp
0x180022c53  mov     [r11+8], rbx
0x180022c57  push    rdi
0x180022c58  sub     rsp, 60h
0x180022c5c  xorps   xmm0, xmm0
0x180022c5f  mov     qword ptr [r11+10h], 0
0x180022c67  mov     rbx, rcx
0x180022c6a  xor     eax, eax
0x180022c6c  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x180022c71  lea     rcx, [r11-28h]; pvarg
0x180022c75  mov     [r11-18h], rax
0x180022c79  mov     rdi, rdx
0x180022c7c  call    cs:__imp_VariantInit
0x180022c82  test    rdi, rdi
0x180022c85  jnz     short loc_180022C8E
0x180022c87  mov     ebx, 80004003h
0x180022c8c  jmp     short loc_180022D00
0x180022c8e  mov     rdx, [rbx+48h]; unsigned __int16 *
0x180022c92  lea     r8, [rsp+68h+arg_8]; struct IWbemClassObject **
0x180022c97  mov     rcx, [rbx+40h]; struct IWbemServices *
0x180022c9b  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180022ca0  mov     ebx, eax
0x180022ca2  test    eax, eax
0x180022ca4  jnz     short loc_180022D00
0x180022ca6  mov     rcx, [rsp+68h+arg_8]
0x180022cab  lea     r9, [rsp+68h+pvarg]
0x180022cb0  mov     [rsp+68h+var_40], 0
0x180022cb9  lea     rdx, ?c_wszOutgoingIPProtocol@@3QBGB; "OutgoingIPProtocol"
0x180022cc0  xor     r8d, r8d
0x180022cc3  mov     [rsp+68h+var_48], 0
0x180022ccc  mov     rax, [rcx]
0x180022ccf  mov     rax, [rax+20h]
0x180022cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cd8  mov     rcx, [rsp+68h+arg_8]
0x180022cdd  mov     ebx, eax
0x180022cdf  mov     rax, [rcx]
0x180022ce2  mov     rax, [rax+10h]
0x180022ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ceb  test    ebx, ebx
0x180022ced  jnz     short loc_180022D00
0x180022cef  mov     al, byte ptr [rsp+68h+pvarg+8]
0x180022cf3  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180022cf8  mov     [rdi], al
0x180022cfa  call    cs:__imp_VariantClear
0x180022d00  mov     eax, ebx
0x180022d02  mov     rbx, [rsp+68h+arg_0]
0x180022d07  add     rsp, 60h
0x180022d0b  pop     rdi
0x180022d0c  retn
```
