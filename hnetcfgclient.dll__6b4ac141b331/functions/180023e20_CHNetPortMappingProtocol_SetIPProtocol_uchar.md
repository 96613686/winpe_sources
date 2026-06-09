# CHNetPortMappingProtocol::SetIPProtocol(uchar)

- ea: `0x180023e20`
- end: `0x180023f7f`
- name: `?SetIPProtocol@CHNetPortMappingProtocol@@UEAAJE@Z`
- size: `351`
- prototype: `int(CHNetPortMappingProtocol *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180023e20`
- `0x180029a3c`
- `0x18002a07c`
- `0x18002ac5c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180023e4e`
- `OLEAUT32!__imp_VariantInit` at `0x180023e4e`

## string_xrefs

- `0x180023f0c`: `IPProtocol`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingProtocol::SetIPProtocol(struct IWbemServices **this, BYTE a2)
{
  unsigned int WmiObjectFromPath; // ebx
  struct IWbemServices *v5; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 v8; // [rsp+70h] [rbp+20h] BYREF
  struct IWbemClassObject *v9; // [rsp+80h] [rbp+30h] BYREF

  v9 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( *((_BYTE *)this + 88) == 1 )
  {
    return (unsigned int)-2147024891;
  }
  else if ( a2 )
  {
    v5 = *this;
    LOBYTE(v8) = 0;
    WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, unsigned __int16 *))v5[5].lpVtbl)(this, &v8);
    if ( !WmiObjectFromPath && a2 != (_BYTE)v8 )
    {
      v8 = 0;
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, unsigned __int16 *))(*this)[7].lpVtbl)(
                            this,
                            &v8);
      if ( !WmiObjectFromPath )
      {
        if ( PortMappingProtocolExists(this[9], (unsigned __int16 *)this[12], v8, a2) )
        {
          return (unsigned int)-2147019886;
        }
        else
        {
          WmiObjectFromPath = GetWmiObjectFromPath(this[9], (unsigned __int16 *)this[10], &v9);
          if ( !WmiObjectFromPath )
          {
            pvarg.vt = 17;
            pvarg.bVal = a2;
            WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v9->lpVtbl->Put)(
                                  v9,
                                  L"IPProtocol",
                                  0,
                                  &pvarg,
                                  0);
            if ( !WmiObjectFromPath )
              WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64, _QWORD, _QWORD))this[9]->lpVtbl->PutInstance)(
                                    this[9],
                                    v9,
                                    1,
                                    0,
                                    0);
            ((void (__fastcall *)(struct IWbemClassObject *))v9->lpVtbl->Release)(v9);
            if ( !WmiObjectFromPath )
              UpdateService(0x87u);
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return WmiObjectFromPath;
}

```

## disassembly

```asm
0x180023e20  mov     [rsp-18h+arg_8], rbx
0x180023e25  push    rbp
0x180023e26  push    rsi
0x180023e27  push    rdi
0x180023e28  mov     rbp, rsp
0x180023e2b  sub     rsp, 50h
0x180023e2f  mov     rdi, rcx
0x180023e32  mov     [rbp+arg_10], 0
0x180023e3a  xorps   xmm0, xmm0
0x180023e3d  lea     rcx, [rbp+pvarg]; pvarg
0x180023e41  xor     eax, eax
0x180023e43  mov     sil, dl
0x180023e46  movups  xmmword ptr [rbp+pvarg], xmm0
0x180023e4a  mov     qword ptr [rbp+pvarg+10h], rax
0x180023e4e  call    cs:__imp_VariantInit
0x180023e54  cmp     byte ptr [rdi+58h], 1
0x180023e58  jnz     short loc_180023E64
0x180023e5a  mov     ebx, 80070005h
0x180023e5f  jmp     loc_180023F70
0x180023e64  test    sil, sil
0x180023e67  jnz     short loc_180023E73
0x180023e69  mov     ebx, 80070057h
0x180023e6e  jmp     loc_180023F70
0x180023e73  mov     rax, [rdi]
0x180023e76  lea     rdx, [rbp+arg_0]
0x180023e7a  mov     rcx, rdi
0x180023e7d  mov     byte ptr [rbp+arg_0], 0
0x180023e81  mov     rax, [rax+28h]
0x180023e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e8a  mov     ebx, eax
0x180023e8c  test    eax, eax
0x180023e8e  jnz     loc_180023F70
0x180023e94  cmp     sil, byte ptr [rbp+arg_0]
0x180023e98  jz      loc_180023F70
0x180023e9e  mov     [rbp+arg_0], ax
0x180023ea2  lea     rdx, [rbp+arg_0]
0x180023ea6  mov     rax, [rdi]
0x180023ea9  mov     rcx, rdi
0x180023eac  mov     rax, [rax+38h]
0x180023eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eb5  mov     ebx, eax
0x180023eb7  test    eax, eax
0x180023eb9  jnz     loc_180023F70
0x180023ebf  movzx   r8d, [rbp+arg_0]; unsigned __int16
0x180023ec4  mov     r9b, sil; unsigned __int8
0x180023ec7  mov     rdx, [rdi+60h]; unsigned __int16 *
0x180023ecb  mov     rcx, [rdi+48h]; struct IWbemServices *
0x180023ecf  call    ?PortMappingProtocolExists@@YAEPEAUIWbemServices@@PEAGGE@Z; PortMappingProtocolExists(IWbemServices *,ushort *,ushort,uchar)
0x180023ed4  test    al, al
0x180023ed6  jz      short loc_180023EE2
0x180023ed8  mov     ebx, 80071392h
0x180023edd  jmp     loc_180023F70
0x180023ee2  mov     rdx, [rdi+50h]; unsigned __int16 *
0x180023ee6  lea     r8, [rbp+arg_10]; struct IWbemClassObject **
0x180023eea  mov     rcx, [rdi+48h]; struct IWbemServices *
0x180023eee  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180023ef3  mov     ebx, eax
0x180023ef5  test    eax, eax
0x180023ef7  jnz     short loc_180023F70
0x180023ef9  mov     rcx, [rbp+arg_10]
0x180023efd  lea     eax, [rbx+11h]
0x180023f00  mov     word ptr [rbp+pvarg], ax
0x180023f04  lea     r9, [rbp+pvarg]
0x180023f08  mov     byte ptr [rbp+pvarg+8], sil
0x180023f0c  lea     rdx, ?c_wszIPProtocol@@3QBGB; "IPProtocol"
0x180023f13  xor     r8d, r8d
0x180023f16  mov     dword ptr [rsp+50h+var_30], ebx
0x180023f1a  mov     rax, [rcx]
0x180023f1d  mov     rax, [rax+28h]
0x180023f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f26  mov     ebx, eax
0x180023f28  test    eax, eax
0x180023f2a  jnz     short loc_180023F52
0x180023f2c  mov     rcx, [rdi+48h]
0x180023f30  lea     r8d, [rbx+1]
0x180023f34  mov     rdx, [rbp+arg_10]
0x180023f38  xor     r9d, r9d
0x180023f3b  mov     [rsp+50h+var_30], 0
0x180023f44  mov     rax, [rcx]
0x180023f47  mov     rax, [rax+70h]
0x180023f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f50  mov     ebx, eax
0x180023f52  mov     rcx, [rbp+arg_10]
0x180023f56  mov     rax, [rcx]
0x180023f59  mov     rax, [rax+10h]
0x180023f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f62  test    ebx, ebx
0x180023f64  jnz     short loc_180023F70
0x180023f66  mov     ecx, 87h; dwControl
0x180023f6b  call    ?UpdateService@@YAXK@Z; UpdateService(ulong)
0x180023f70  mov     eax, ebx
0x180023f72  mov     rbx, [rsp+50h+arg_8]
0x180023f77  add     rsp, 50h
0x180023f7b  pop     rdi
0x180023f7c  pop     rsi
0x180023f7d  pop     rbp
0x180023f7e  retn
```
