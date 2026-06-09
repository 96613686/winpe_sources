# CHNetPortMappingProtocol::SetPortW(ushort)

- ea: `0x1800240a0`
- end: `0x1800241ff`
- name: `?SetPortW@CHNetPortMappingProtocol@@UEAAJG@Z`
- size: `351`
- prototype: `__int64 __fastcall(CHNetPortMappingProtocol *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800240a0`
- `0x180029a3c`
- `0x18002a07c`
- `0x18002ac5c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800240ce`
- `OLEAUT32!__imp_VariantInit` at `0x1800240ce`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingProtocol::SetPortW(struct IWbemServices **this, unsigned __int16 a2)
{
  LONG v3; // esi
  unsigned int WmiObjectFromPath; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  __int16 v7; // [rsp+70h] [rbp+20h] BYREF
  struct IWbemClassObject *v8; // [rsp+80h] [rbp+30h] BYREF

  v3 = a2;
  v8 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( *((_BYTE *)this + 88) == 1 )
  {
    return (unsigned int)-2147024891;
  }
  else if ( (_WORD)v3 )
  {
    v7 = 0;
    WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, __int16 *))(*this)[7].lpVtbl)(this, &v7);
    if ( !WmiObjectFromPath && (_WORD)v3 != v7 )
    {
      LOBYTE(v7) = 0;
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, __int16 *))(*this)[5].lpVtbl)(this, &v7);
      if ( !WmiObjectFromPath )
      {
        if ( PortMappingProtocolExists(this[9], (unsigned __int16 *)this[12], v3, v7) )
        {
          return (unsigned int)-2147019886;
        }
        else
        {
          WmiObjectFromPath = GetWmiObjectFromPath(this[9], (unsigned __int16 *)this[10], &v8);
          if ( !WmiObjectFromPath )
          {
            pvarg.vt = 3;
            pvarg.lVal = v3;
            WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v8->lpVtbl->Put)(
                                  v8,
                                  L"Port",
                                  0,
                                  &pvarg,
                                  0);
            if ( !WmiObjectFromPath )
              WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64, _QWORD, _QWORD))this[9]->lpVtbl->PutInstance)(
                                    this[9],
                                    v8,
                                    1,
                                    0,
                                    0);
            ((void (__fastcall *)(struct IWbemClassObject *))v8->lpVtbl->Release)(v8);
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
0x1800240a0  mov     [rsp-18h+arg_8], rbx
0x1800240a5  push    rbp
0x1800240a6  push    rsi
0x1800240a7  push    rdi
0x1800240a8  mov     rbp, rsp
0x1800240ab  sub     rsp, 50h
0x1800240af  mov     rdi, rcx
0x1800240b2  movzx   esi, dx
0x1800240b5  xorps   xmm0, xmm0
0x1800240b8  mov     [rbp+arg_10], 0
0x1800240c0  xor     eax, eax
0x1800240c2  lea     rcx, [rbp+pvarg]; pvarg
0x1800240c6  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800240ca  mov     qword ptr [rbp+pvarg+10h], rax
0x1800240ce  call    cs:__imp_VariantInit
0x1800240d4  cmp     byte ptr [rdi+58h], 1
0x1800240d8  jnz     short loc_1800240E4
0x1800240da  mov     ebx, 80070005h
0x1800240df  jmp     loc_1800241F0
0x1800240e4  xor     eax, eax
0x1800240e6  cmp     ax, si
0x1800240e9  jnz     short loc_1800240F5
0x1800240eb  mov     ebx, 80070057h
0x1800240f0  jmp     loc_1800241F0
0x1800240f5  mov     [rbp+arg_0], ax
0x1800240f9  lea     rdx, [rbp+arg_0]
0x1800240fd  mov     rax, [rdi]
0x180024100  mov     rcx, rdi
0x180024103  mov     rax, [rax+38h]
0x180024107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002410c  mov     ebx, eax
0x18002410e  test    eax, eax
0x180024110  jnz     loc_1800241F0
0x180024116  cmp     si, [rbp+arg_0]
0x18002411a  jz      loc_1800241F0
0x180024120  mov     byte ptr [rbp+arg_0], al
0x180024123  lea     rdx, [rbp+arg_0]
0x180024127  mov     rax, [rdi]
0x18002412a  mov     rcx, rdi
0x18002412d  mov     rax, [rax+28h]
0x180024131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024136  mov     ebx, eax
0x180024138  test    eax, eax
0x18002413a  jnz     loc_1800241F0
0x180024140  mov     r9b, byte ptr [rbp+arg_0]; unsigned __int8
0x180024144  movzx   r8d, si; unsigned __int16
0x180024148  mov     rdx, [rdi+60h]; unsigned __int16 *
0x18002414c  mov     rcx, [rdi+48h]; struct IWbemServices *
0x180024150  call    ?PortMappingProtocolExists@@YAEPEAUIWbemServices@@PEAGGE@Z; PortMappingProtocolExists(IWbemServices *,ushort *,ushort,uchar)
0x180024155  test    al, al
0x180024157  jz      short loc_180024163
0x180024159  mov     ebx, 80071392h
0x18002415e  jmp     loc_1800241F0
0x180024163  mov     rdx, [rdi+50h]; unsigned __int16 *
0x180024167  lea     r8, [rbp+arg_10]; struct IWbemClassObject **
0x18002416b  mov     rcx, [rdi+48h]; struct IWbemServices *
0x18002416f  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180024174  mov     ebx, eax
0x180024176  test    eax, eax
0x180024178  jnz     short loc_1800241F0
0x18002417a  mov     rcx, [rbp+arg_10]
0x18002417e  lea     eax, [rbx+3]
0x180024181  mov     word ptr [rbp+pvarg], ax
0x180024185  lea     r9, [rbp+pvarg]
0x180024189  mov     dword ptr [rbp+pvarg+8], esi
0x18002418c  lea     rdx, ?c_wszPort@@3QBGB; "Port"
0x180024193  xor     r8d, r8d
0x180024196  mov     dword ptr [rsp+50h+var_30], ebx
0x18002419a  mov     rax, [rcx]
0x18002419d  mov     rax, [rax+28h]
0x1800241a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241a6  mov     ebx, eax
0x1800241a8  test    eax, eax
0x1800241aa  jnz     short loc_1800241D2
0x1800241ac  mov     rcx, [rdi+48h]
0x1800241b0  lea     r8d, [rbx+1]
0x1800241b4  mov     rdx, [rbp+arg_10]
0x1800241b8  xor     r9d, r9d
0x1800241bb  mov     [rsp+50h+var_30], 0
0x1800241c4  mov     rax, [rcx]
0x1800241c7  mov     rax, [rax+70h]
0x1800241cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241d0  mov     ebx, eax
0x1800241d2  mov     rcx, [rbp+arg_10]
0x1800241d6  mov     rax, [rcx]
0x1800241d9  mov     rax, [rax+10h]
0x1800241dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241e2  test    ebx, ebx
0x1800241e4  jnz     short loc_1800241F0
0x1800241e6  mov     ecx, 87h; dwControl
0x1800241eb  call    ?UpdateService@@YAXK@Z; UpdateService(ulong)
0x1800241f0  mov     eax, ebx
0x1800241f2  mov     rbx, [rsp+50h+arg_8]
0x1800241f7  add     rsp, 50h
0x1800241fb  pop     rdi
0x1800241fc  pop     rsi
0x1800241fd  pop     rbp
0x1800241fe  retn
```
