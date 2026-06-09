# CHNetPortMappingBinding::SetTargetComputerAddress(ulong)

- ea: `0x180024cf0`
- end: `0x180024e3a`
- name: `?SetTargetComputerAddress@CHNetPortMappingBinding@@UEAAJK@Z`
- size: `330`
- prototype: `__int64 __fastcall(CHNetPortMappingBinding *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180024cf0`
- `0x180029a3c`
- `0x18002a61c`
- `0x18002ac5c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180024d96`
- `OLEAUT32!__imp_VariantInit` at `0x180024d96`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingBinding::SetTargetComputerAddress(struct IWbemServices **this, LONG a2)
{
  unsigned int WmiObjectFromPath; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  char v7; // [rsp+78h] [rbp+28h] BYREF
  int v8; // [rsp+80h] [rbp+30h] BYREF
  struct IWbemClassObject *v9; // [rsp+88h] [rbp+38h] BYREF

  v7 = 0;
  v9 = 0;
  v8 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( a2 )
  {
    WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, int *))(*this)[10].lpVtbl)(this, &v8);
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, char *))(*this)[7].lpVtbl)(this, &v7);
      if ( !WmiObjectFromPath && (a2 != v8 || v7) )
      {
        WmiObjectFromPath = GetWmiObjectFromPath(this[8], (unsigned __int16 *)this[9], &v9);
        if ( !WmiObjectFromPath )
        {
          VariantInit(&pvarg);
          pvarg.vt = 3;
          pvarg.lVal = a2;
          WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v9->lpVtbl->Put)(
                                v9,
                                L"TargetIPAddress",
                                0,
                                &pvarg,
                                0);
          if ( !WmiObjectFromPath )
          {
            WmiObjectFromPath = SetBooleanValue(v9, L"NameActive", 0);
            if ( !WmiObjectFromPath )
              WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64, _QWORD, _QWORD))this[8]->lpVtbl->PutInstance)(
                                    this[8],
                                    v9,
                                    1,
                                    0,
                                    0);
          }
          ((void (__fastcall *)(struct IWbemClassObject *))v9->lpVtbl->Release)(v9);
          if ( !WmiObjectFromPath )
            UpdateService(0x87u);
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
0x180024cf0  mov     [rsp-18h+arg_0], rbx
0x180024cf5  push    rbp
0x180024cf6  push    rsi
0x180024cf7  push    rdi
0x180024cf8  mov     rbp, rsp
0x180024cfb  sub     rsp, 50h
0x180024cff  xor     eax, eax
0x180024d01  mov     [rbp+arg_8], 0
0x180024d05  mov     [rbp+arg_18], 0
0x180024d0d  xorps   xmm0, xmm0
0x180024d10  mov     [rbp+arg_10], 0
0x180024d17  mov     esi, edx
0x180024d19  mov     qword ptr [rbp+pvarg+10h], rax
0x180024d1d  mov     rdi, rcx
0x180024d20  movups  xmmword ptr [rbp+pvarg], xmm0
0x180024d24  test    edx, edx
0x180024d26  jnz     short loc_180024D32
0x180024d28  mov     ebx, 80070057h
0x180024d2d  jmp     loc_180024E2B
0x180024d32  mov     rax, [rcx]
0x180024d35  lea     rdx, [rbp+arg_10]
0x180024d39  mov     rax, [rax+50h]
0x180024d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d42  mov     ebx, eax
0x180024d44  test    eax, eax
0x180024d46  jnz     loc_180024E2B
0x180024d4c  mov     rax, [rdi]
0x180024d4f  lea     rdx, [rbp+arg_8]
0x180024d53  mov     rcx, rdi
0x180024d56  mov     rax, [rax+38h]
0x180024d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d5f  mov     ebx, eax
0x180024d61  test    eax, eax
0x180024d63  jnz     loc_180024E2B
0x180024d69  cmp     esi, [rbp+arg_10]
0x180024d6c  jnz     short loc_180024D77
0x180024d6e  cmp     [rbp+arg_8], al
0x180024d71  jz      loc_180024E2B
0x180024d77  mov     rdx, [rdi+48h]; unsigned __int16 *
0x180024d7b  lea     r8, [rbp+arg_18]; struct IWbemClassObject **
0x180024d7f  mov     rcx, [rdi+40h]; struct IWbemServices *
0x180024d83  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180024d88  mov     ebx, eax
0x180024d8a  test    eax, eax
0x180024d8c  jnz     loc_180024E2B
0x180024d92  lea     rcx, [rbp+pvarg]; pvarg
0x180024d96  call    cs:__imp_VariantInit
0x180024d9c  mov     rcx, [rbp+arg_18]
0x180024da0  lea     eax, [rbx+3]
0x180024da3  mov     word ptr [rbp+pvarg], ax
0x180024da7  lea     r9, [rbp+pvarg]
0x180024dab  mov     dword ptr [rbp+pvarg+8], esi
0x180024dae  lea     rdx, ?c_wszTargetIPAddress@@3QBGB; "TargetIPAddress"
0x180024db5  xor     r8d, r8d
0x180024db8  mov     dword ptr [rsp+50h+var_30], ebx
0x180024dbc  mov     rax, [rcx]
0x180024dbf  mov     rax, [rax+28h]
0x180024dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dc8  mov     ebx, eax
0x180024dca  test    eax, eax
0x180024dcc  jnz     short loc_180024E0D
0x180024dce  mov     rcx, [rbp+arg_18]; struct IWbemClassObject *
0x180024dd2  lea     rdx, ?c_wszNameActive@@3QBGB; "NameActive"
0x180024dd9  xor     r8d, r8d; unsigned __int8
0x180024ddc  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x180024de1  mov     ebx, eax
0x180024de3  test    eax, eax
0x180024de5  jnz     short loc_180024E0D
0x180024de7  mov     rcx, [rdi+40h]
0x180024deb  lea     r8d, [rbx+1]
0x180024def  mov     rdx, [rbp+arg_18]
0x180024df3  xor     r9d, r9d
0x180024df6  mov     [rsp+50h+var_30], 0
0x180024dff  mov     rax, [rcx]
0x180024e02  mov     rax, [rax+70h]
0x180024e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e0b  mov     ebx, eax
0x180024e0d  mov     rcx, [rbp+arg_18]
0x180024e11  mov     rax, [rcx]
0x180024e14  mov     rax, [rax+10h]
0x180024e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e1d  test    ebx, ebx
0x180024e1f  jnz     short loc_180024E2B
0x180024e21  mov     ecx, 87h; dwControl
0x180024e26  call    ?UpdateService@@YAXK@Z; UpdateService(ulong)
0x180024e2b  mov     eax, ebx
0x180024e2d  mov     rbx, [rsp+50h+arg_0]
0x180024e32  add     rsp, 50h
0x180024e36  pop     rdi
0x180024e37  pop     rsi
0x180024e38  pop     rbp
0x180024e39  retn
```
