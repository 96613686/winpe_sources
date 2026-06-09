# CHNetPortMappingBinding::GetProtocol(IHNetPortMappingProtocol * *)

- ea: `0x180024790`
- end: `0x1800248ee`
- name: `?GetProtocol@CHNetPortMappingBinding@@UEAAJPEAPEAUIHNetPortMappingProtocol@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(CHNetPortMappingBinding *__hidden this, struct IHNetPortMappingProtocol **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010218`
- `0x180023db8`
- `0x180024790`
- `0x180028c48`
- `0x180029a3c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180024837`
- `OLEAUT32!__imp_VariantClear` at `0x180024837`

## string_xrefs

- `0x1800247f7`: `Protocol`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingBinding::GetProtocol(
        CHNetPortMappingBinding *this,
        struct IHNetPortMappingProtocol **a2)
{
  int WmiObjectFromPath; // ebx
  CHNetPortMappingProtocol *v5; // rsi
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  struct IWbemClassObject *v8; // [rsp+98h] [rbp+38h] BYREF
  struct IWbemClassObject *v9; // [rsp+A0h] [rbp+40h] BYREF
  CHNetPortMappingProtocol *v10; // [rsp+A8h] [rbp+48h] BYREF

  v9 = 0;
  v8 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( a2 )
  {
    *a2 = 0;
    WmiObjectFromPath = GetWmiObjectFromPath(
                          *((struct IWbemServices **)this + 8),
                          *((unsigned __int16 **)this + 9),
                          &v8);
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v8->lpVtbl->Get)(
                            v8,
                            L"Protocol",
                            0,
                            &pvarg,
                            0,
                            0);
      if ( !WmiObjectFromPath )
      {
        WmiObjectFromPath = GetWmiObjectFromPath(*((struct IWbemServices **)this + 8), pvarg.bstrVal, &v9);
        VariantClear(&pvarg);
        if ( WmiObjectFromPath )
        {
          if ( WmiObjectFromPath == -2147217406 )
            DeleteWmiInstance(*((struct IWbemServices **)this + 8), v8);
        }
        else
        {
          v10 = 0;
          WmiObjectFromPath = ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance((volatile int **)&v10);
          if ( WmiObjectFromPath >= 0 )
          {
            v5 = v10;
            (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v10 + 8LL))(v10);
            WmiObjectFromPath = CHNetPortMappingProtocol::Initialize(v5, *((struct IWbemServices **)this + 8), v9);
            if ( WmiObjectFromPath >= 0 )
              WmiObjectFromPath = (**(__int64 (__fastcall ***)(CHNetPortMappingProtocol *, GUID *, struct IHNetPortMappingProtocol **))v5)(
                                    v5,
                                    &GUID_85d18b7e_3032_11d4_9348_00c04f8eeb71,
                                    a2);
            (*(void (__fastcall **)(CHNetPortMappingProtocol *))(*(_QWORD *)v5 + 16LL))(v5);
          }
          ((void (__fastcall *)(struct IWbemClassObject *))v9->lpVtbl->Release)(v9);
        }
      }
      ((void (__fastcall *)(struct IWbemClassObject *))v8->lpVtbl->Release)(v8);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)WmiObjectFromPath;
}

```

## disassembly

```asm
0x180024790  push    rbp
0x180024792  push    rbx
0x180024793  push    rsi
0x180024794  push    rdi
0x180024795  push    r14
0x180024797  mov     rbp, rsp
0x18002479a  sub     rsp, 60h
0x18002479e  xor     eax, eax
0x1800247a0  xorps   xmm0, xmm0
0x1800247a3  mov     qword ptr [rbp+pvarg+10h], rax
0x1800247a7  mov     r14, rdx
0x1800247aa  mov     [rbp+arg_10], rax
0x1800247ae  mov     rdi, rcx
0x1800247b1  mov     [rbp+arg_8], rax
0x1800247b5  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800247b9  test    rdx, rdx
0x1800247bc  jnz     short loc_1800247C8
0x1800247be  mov     ebx, 80004003h
0x1800247c3  jmp     loc_1800248E1
0x1800247c8  mov     [rdx], rax
0x1800247cb  lea     r8, [rbp+arg_8]; struct IWbemClassObject **
0x1800247cf  mov     rdx, [rcx+48h]; unsigned __int16 *
0x1800247d3  mov     rcx, [rcx+40h]; struct IWbemServices *
0x1800247d7  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x1800247dc  mov     ebx, eax
0x1800247de  test    eax, eax
0x1800247e0  jnz     loc_1800248E1
0x1800247e6  mov     rcx, [rbp+arg_8]
0x1800247ea  lea     r9, [rbp+pvarg]
0x1800247ee  mov     [rsp+60h+var_38], 0
0x1800247f7  lea     rdx, ?c_wszProtocol@@3QBGB; "Protocol"
0x1800247fe  xor     r8d, r8d
0x180024801  mov     [rsp+60h+var_40], 0
0x18002480a  mov     rax, [rcx]
0x18002480d  mov     rax, [rax+20h]
0x180024811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024816  mov     ebx, eax
0x180024818  test    eax, eax
0x18002481a  jnz     loc_1800248D1
0x180024820  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x180024824  lea     r8, [rbp+arg_10]; struct IWbemClassObject **
0x180024828  mov     rcx, [rdi+40h]; struct IWbemServices *
0x18002482c  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180024831  lea     rcx, [rbp+pvarg]; pvarg
0x180024835  mov     ebx, eax
0x180024837  call    cs:__imp_VariantClear
0x18002483d  test    ebx, ebx
0x18002483f  jnz     short loc_1800248BC
0x180024841  lea     rcx, [rbp+arg_18]
0x180024845  mov     [rbp+arg_18], 0
0x18002484d  call    ?CreateInstance@?$CComObject@VCHNetPortMappingProtocol@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetPortMappingProtocol>::CreateInstance(ATL::CComObject<CHNetPortMappingProtocol> * *)
0x180024852  mov     ebx, eax
0x180024854  test    eax, eax
0x180024856  js      short loc_1800248AA
0x180024858  mov     rsi, [rbp+arg_18]
0x18002485c  mov     rcx, rsi
0x18002485f  mov     rax, [rsi]
0x180024862  mov     rax, [rax+8]
0x180024866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002486b  mov     r8, [rbp+arg_10]; struct IWbemClassObject *
0x18002486f  mov     rcx, rsi; this
0x180024872  mov     rdx, [rdi+40h]; struct IWbemServices *
0x180024876  call    ?Initialize@CHNetPortMappingProtocol@@QEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; CHNetPortMappingProtocol::Initialize(IWbemServices *,IWbemClassObject *)
0x18002487b  mov     ebx, eax
0x18002487d  test    eax, eax
0x18002487f  js      short loc_18002489B
0x180024881  mov     rax, [rsi]
0x180024884  lea     rdx, _GUID_85d18b7e_3032_11d4_9348_00c04f8eeb71
0x18002488b  mov     r8, r14
0x18002488e  mov     rcx, rsi
0x180024891  mov     rax, [rax]
0x180024894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024899  mov     ebx, eax
0x18002489b  mov     rax, [rsi]
0x18002489e  mov     rcx, rsi
0x1800248a1  mov     rax, [rax+10h]
0x1800248a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248aa  mov     rcx, [rbp+arg_10]
0x1800248ae  mov     rax, [rcx]
0x1800248b1  mov     rax, [rax+10h]
0x1800248b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248ba  jmp     short loc_1800248D1
0x1800248bc  cmp     ebx, 80041002h
0x1800248c2  jnz     short loc_1800248D1
0x1800248c4  mov     rdx, [rbp+arg_8]; struct IWbemClassObject *
0x1800248c8  mov     rcx, [rdi+40h]; struct IWbemServices *
0x1800248cc  call    ?DeleteWmiInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; DeleteWmiInstance(IWbemServices *,IWbemClassObject *)
0x1800248d1  mov     rcx, [rbp+arg_8]
0x1800248d5  mov     rax, [rcx]
0x1800248d8  mov     rax, [rax+10h]
0x1800248dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248e1  mov     eax, ebx
0x1800248e3  add     rsp, 60h
0x1800248e7  pop     r14
0x1800248e9  pop     rdi
0x1800248ea  pop     rsi
0x1800248eb  pop     rbx
0x1800248ec  pop     rbp
0x1800248ed  retn
```
