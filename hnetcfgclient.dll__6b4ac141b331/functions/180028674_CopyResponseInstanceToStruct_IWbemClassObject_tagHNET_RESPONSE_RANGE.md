# CopyResponseInstanceToStruct(IWbemClassObject *,tagHNET_RESPONSE_RANGE *)

- ea: `0x180028674`
- end: `0x180028783`
- name: `?CopyResponseInstanceToStruct@@YAJPEAUIWbemClassObject@@PEAUtagHNET_RESPONSE_RANGE@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(struct IWbemClassObject *, struct tagHNET_RESPONSE_RANGE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022df0`

## callees

- `0x180028674`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800286d7`
- `OLEAUT32!__imp_VariantClear` at `0x180028721`
- `OLEAUT32!__imp_VariantClear` at `0x18002876b`
- `OLEAUT32!__imp_VariantClear` at `0x1800286d7`
- `OLEAUT32!__imp_VariantClear` at `0x180028721`
- `OLEAUT32!__imp_VariantClear` at `0x18002876b`

## string_xrefs

- `0x1800286af`: `IPProtocol`

## pseudocode

```c
__int64 __fastcall CopyResponseInstanceToStruct(struct IWbemClassObject *a1, struct tagHNET_RESPONSE_RANGE *a2)
{
  unsigned int v4; // ebx
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v4 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
         a1,
         L"IPProtocol",
         0,
         &pvarg,
         0,
         0);
  if ( !v4 )
  {
    *(_BYTE *)a2 = pvarg.bVal;
    VariantClear(&pvarg);
    v4 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
           a1,
           L"StartPort",
           0,
           &pvarg,
           0,
           0);
    if ( !v4 )
    {
      *((_WORD *)a2 + 1) = pvarg.iVal;
      VariantClear(&pvarg);
      v4 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
             a1,
             L"EndPort",
             0,
             &pvarg,
             0,
             0);
      if ( !v4 )
      {
        *((_WORD *)a2 + 2) = pvarg.iVal;
        VariantClear(&pvarg);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180028674  mov     r11, rsp
0x180028677  mov     [r11+8], rbx
0x18002867b  mov     [r11+10h], rsi
0x18002867f  push    rdi
0x180028680  sub     rsp, 60h
0x180028684  xor     eax, eax
0x180028686  mov     qword ptr [r11-40h], 0
0x18002868e  xorps   xmm0, xmm0
0x180028691  mov     qword ptr [r11-48h], 0
0x180028699  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18002869e  mov     [r11-18h], rax
0x1800286a2  lea     r9, [r11-28h]
0x1800286a6  mov     rax, [rcx]
0x1800286a9  mov     rsi, rdx
0x1800286ac  xor     r8d, r8d
0x1800286af  lea     rdx, ?c_wszIPProtocol@@3QBGB; "IPProtocol"
0x1800286b6  mov     rdi, rcx
0x1800286b9  mov     rax, [rax+20h]
0x1800286bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286c2  mov     ebx, eax
0x1800286c4  test    eax, eax
0x1800286c6  jnz     loc_180028771
0x1800286cc  mov     al, byte ptr [rsp+68h+pvarg+8]
0x1800286d0  lea     rcx, [rsp+68h+pvarg]; pvarg
0x1800286d5  mov     [rsi], al
0x1800286d7  call    cs:__imp_VariantClear
0x1800286dd  mov     rax, [rdi]
0x1800286e0  lea     r9, [rsp+68h+pvarg]
0x1800286e5  mov     [rsp+68h+var_40], 0
0x1800286ee  lea     rdx, ?c_wszStartPort@@3QBGB; "StartPort"
0x1800286f5  xor     r8d, r8d
0x1800286f8  mov     [rsp+68h+var_48], 0
0x180028701  mov     rcx, rdi
0x180028704  mov     rax, [rax+20h]
0x180028708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002870d  mov     ebx, eax
0x18002870f  test    eax, eax
0x180028711  jnz     short loc_180028771
0x180028713  movzx   eax, word ptr [rsp+68h+pvarg+8]
0x180028718  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18002871d  mov     [rsi+2], ax
0x180028721  call    cs:__imp_VariantClear
0x180028727  mov     rax, [rdi]
0x18002872a  lea     r9, [rsp+68h+pvarg]
0x18002872f  mov     [rsp+68h+var_40], 0
0x180028738  lea     rdx, ?c_wszEndPort@@3QBGB; "EndPort"
0x18002873f  xor     r8d, r8d
0x180028742  mov     [rsp+68h+var_48], 0
0x18002874b  mov     rcx, rdi
0x18002874e  mov     rax, [rax+20h]
0x180028752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028757  mov     ebx, eax
0x180028759  test    eax, eax
0x18002875b  jnz     short loc_180028771
0x18002875d  movzx   eax, word ptr [rsp+68h+pvarg+8]
0x180028762  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180028767  mov     [rsi+4], ax
0x18002876b  call    cs:__imp_VariantClear
0x180028771  mov     rsi, [rsp+68h+arg_8]
0x180028776  mov     eax, ebx
0x180028778  mov     rbx, [rsp+68h+arg_0]
0x18002877d  add     rsp, 60h
0x180028781  pop     rdi
0x180028782  retn
```
