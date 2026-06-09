# CHNetAppProtocol::SetOutgoingIPProtocol(uchar)

- ea: `0x180023270`
- end: `0x1800233d8`
- name: `?SetOutgoingIPProtocol@CHNetAppProtocol@@UEAAJE@Z`
- size: `360`
- prototype: `int(CHNetAppProtocol *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023270`
- `0x180027ca4`
- `0x180029a3c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800232d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800232d6`
- `OLEAUT32!__imp_SysFreeString` at `0x180023322`
- `OLEAUT32!__imp_SysFreeString` at `0x180023322`
- `OLEAUT32!__imp_VariantInit` at `0x1800232a4`
- `OLEAUT32!__imp_VariantInit` at `0x18002334b`
- `OLEAUT32!__imp_VariantInit` at `0x1800232a4`
- `OLEAUT32!__imp_VariantInit` at `0x18002334b`

## string_xrefs

- `0x180023364`: `OutgoingIPProtocol`

## pseudocode

```c
__int64 __fastcall CHNetAppProtocol::SetOutgoingIPProtocol(struct IWbemServices **this, unsigned __int8 a2)
{
  unsigned int WmiObjectFromPath; // ebx
  unsigned __int16 *v5; // rsi
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 v8; // [rsp+70h] [rbp+20h] BYREF
  struct IWbemClassObject *v9; // [rsp+80h] [rbp+30h] BYREF

  v9 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( *((_BYTE *)this + 80) == 1 )
  {
    return (unsigned int)-2147024891;
  }
  else if ( a2 )
  {
    v8 = 0;
    v5 = SysAllocString(L"WQL");
    if ( v5 )
    {
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, unsigned __int16 *))(*this)[7].lpVtbl)(
                            this,
                            &v8);
      if ( !WmiObjectFromPath && ApplicationProtocolExists(this[8], v5, v8, a2) )
        WmiObjectFromPath = -2147019886;
      SysFreeString(v5);
      if ( !WmiObjectFromPath )
      {
        WmiObjectFromPath = GetWmiObjectFromPath(this[8], (unsigned __int16 *)this[9], &v9);
        if ( !WmiObjectFromPath )
        {
          VariantInit(&pvarg);
          pvarg.vt = 17;
          pvarg.bVal = a2;
          WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v9->lpVtbl->Put)(
                                v9,
                                L"OutgoingIPProtocol",
                                0,
                                &pvarg,
                                0);
          if ( !WmiObjectFromPath )
            WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64, _QWORD, _QWORD))this[8]->lpVtbl->PutInstance)(
                                  this[8],
                                  v9,
                                  1,
                                  0,
                                  0);
          ((void (__fastcall *)(struct IWbemClassObject *))v9->lpVtbl->Release)(v9);
        }
      }
    }
    else
    {
      return (unsigned int)-2147024882;
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
0x180023270  mov     [rsp-18h+arg_8], rbx
0x180023275  mov     [rsp-18h+arg_18], rsi
0x18002327a  push    rbp
0x18002327b  push    rdi
0x18002327c  push    r14
0x18002327e  mov     rbp, rsp
0x180023281  sub     rsp, 50h
0x180023285  mov     rdi, rcx
0x180023288  mov     [rbp+arg_10], 0
0x180023290  xorps   xmm0, xmm0
0x180023293  lea     rcx, [rbp+pvarg]; pvarg
0x180023297  xor     eax, eax
0x180023299  mov     r14b, dl
0x18002329c  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800232a0  mov     qword ptr [rbp+pvarg+10h], rax
0x1800232a4  call    cs:__imp_VariantInit
0x1800232aa  cmp     byte ptr [rdi+50h], 1
0x1800232ae  jnz     short loc_1800232BA
0x1800232b0  mov     ebx, 80070005h
0x1800232b5  jmp     loc_1800233C1
0x1800232ba  test    r14b, r14b
0x1800232bd  jnz     short loc_1800232C9
0x1800232bf  mov     ebx, 80070057h
0x1800232c4  jmp     loc_1800233C1
0x1800232c9  xor     eax, eax
0x1800232cb  lea     rcx, ?c_wszWQL@@3QBGB; "WQL"
0x1800232d2  mov     [rbp+arg_0], ax
0x1800232d6  call    cs:__imp_SysAllocString
0x1800232dc  mov     rsi, rax
0x1800232df  test    rax, rax
0x1800232e2  jz      loc_1800233BC
0x1800232e8  mov     rax, [rdi]
0x1800232eb  lea     rdx, [rbp+arg_0]
0x1800232ef  mov     rcx, rdi
0x1800232f2  mov     rax, [rax+38h]
0x1800232f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232fb  mov     ebx, eax
0x1800232fd  test    eax, eax
0x1800232ff  jnz     short loc_18002331F
0x180023301  movzx   r8d, [rbp+arg_0]; unsigned __int16
0x180023306  mov     r9b, r14b; unsigned __int8
0x180023309  mov     rcx, [rdi+40h]; struct IWbemServices *
0x18002330d  mov     rdx, rsi; unsigned __int16 *
0x180023310  call    ?ApplicationProtocolExists@@YAEPEAUIWbemServices@@PEAGGE@Z; ApplicationProtocolExists(IWbemServices *,ushort *,ushort,uchar)
0x180023315  test    al, al
0x180023317  mov     ecx, 80071392h
0x18002331c  cmovnz  ebx, ecx
0x18002331f  mov     rcx, rsi; bstrString
0x180023322  call    cs:__imp_SysFreeString
0x180023328  test    ebx, ebx
0x18002332a  jnz     loc_1800233C1
0x180023330  mov     rdx, [rdi+48h]; unsigned __int16 *
0x180023334  lea     r8, [rbp+arg_10]; struct IWbemClassObject **
0x180023338  mov     rcx, [rdi+40h]; struct IWbemServices *
0x18002333c  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180023341  mov     ebx, eax
0x180023343  test    eax, eax
0x180023345  jnz     short loc_1800233C1
0x180023347  lea     rcx, [rbp+pvarg]; pvarg
0x18002334b  call    cs:__imp_VariantInit
0x180023351  mov     rcx, [rbp+arg_10]
0x180023355  lea     eax, [rbx+11h]
0x180023358  mov     word ptr [rbp+pvarg], ax
0x18002335c  lea     r9, [rbp+pvarg]
0x180023360  mov     byte ptr [rbp+pvarg+8], r14b
0x180023364  lea     rdx, ?c_wszOutgoingIPProtocol@@3QBGB; "OutgoingIPProtocol"
0x18002336b  xor     r8d, r8d
0x18002336e  mov     dword ptr [rsp+50h+var_30], ebx
0x180023372  mov     rax, [rcx]
0x180023375  mov     rax, [rax+28h]
0x180023379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002337e  mov     ebx, eax
0x180023380  test    eax, eax
0x180023382  jnz     short loc_1800233AA
0x180023384  mov     rcx, [rdi+40h]
0x180023388  lea     r8d, [rbx+1]
0x18002338c  mov     rdx, [rbp+arg_10]
0x180023390  xor     r9d, r9d
0x180023393  mov     [rsp+50h+var_30], 0
0x18002339c  mov     rax, [rcx]
0x18002339f  mov     rax, [rax+70h]
0x1800233a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233a8  mov     ebx, eax
0x1800233aa  mov     rcx, [rbp+arg_10]
0x1800233ae  mov     rax, [rcx]
0x1800233b1  mov     rax, [rax+10h]
0x1800233b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233ba  jmp     short loc_1800233C1
0x1800233bc  mov     ebx, 8007000Eh
0x1800233c1  lea     r11, [rsp+50h+var_s0]
0x1800233c6  mov     eax, ebx
0x1800233c8  mov     rbx, [r11+28h]
0x1800233cc  mov     rsi, [r11+38h]
0x1800233d0  mov     rsp, r11
0x1800233d3  pop     r14
0x1800233d5  pop     rdi
0x1800233d6  pop     rbp
0x1800233d7  retn
```
