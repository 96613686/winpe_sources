# CHNetPortMappingBinding::SetTargetComputerName(ushort *)

- ea: `0x180024e40`
- end: `0x180025092`
- name: `?SetTargetComputerName@CHNetPortMappingBinding@@UEAAJPEAG@Z`
- size: `594`
- prototype: `__int64 __fastcall(CHNetPortMappingBinding *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180005698`
- `0x180024208`
- `0x180024e40`
- `0x180029a3c`
- `0x18002a61c`
- `0x18002ac5c`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180024efe`
- `msvcrt!_wcsicmp` at `0x180024efe`
- `OLEAUT32!__imp_SysAllocString` at `0x180024f4d`
- `OLEAUT32!__imp_SysAllocString` at `0x180024f4d`
- `OLEAUT32!__imp_VariantInit` at `0x180024f3a`
- `OLEAUT32!__imp_VariantInit` at `0x180024f3a`
- `OLEAUT32!__imp_VariantClear` at `0x180024fa0`
- `OLEAUT32!__imp_VariantClear` at `0x180024fa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024f0b`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingBinding::SetTargetComputerName(struct IWbemServices **this, unsigned __int16 *a2)
{
  int WmiObjectFromPath; // edi
  struct IWbemServices *v5; // rax
  int v6; // ebx
  _BYTE v7[8]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-C8h] BYREF
  struct IWbemClassObject *v9; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t String2[256]; // [rsp+60h] [rbp-A0h] BYREF

  v7[0] = 0;
  v9 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !a2 )
    return 2147942487LL;
  StringCchCopyW(String2, 0x100u, a2);
  WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, _BYTE *))(*this)[7].lpVtbl)(this, v7);
  if ( !WmiObjectFromPath )
  {
    if ( !v7[0]
      || (v5 = *this,
          String1 = 0,
          (WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices **, wchar_t **))v5[8].lpVtbl)(
                                 this,
                                 &String1)) == 0)
      && (v6 = _wcsicmp(String1, String2), CoTaskMemFree(String1), v6) )
    {
      WmiObjectFromPath = GetWmiObjectFromPath(this[8], (unsigned __int16 *)this[9], &v9);
      if ( !WmiObjectFromPath )
      {
        VariantInit(&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(String2);
        if ( pvarg.llVal )
        {
          WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v9->lpVtbl->Put)(
                                v9,
                                L"TargetName",
                                0,
                                &pvarg,
                                0);
          VariantClear(&pvarg);
          if ( !WmiObjectFromPath )
          {
            WmiObjectFromPath = SetBooleanValue(v9, L"NameActive", 1u);
            if ( !WmiObjectFromPath )
            {
              LODWORD(String1) = 0;
              WmiObjectFromPath = CHNetPortMappingBinding::GenerateTargetAddress(
                                    (CHNetPortMappingBinding *)this,
                                    String2,
                                    (unsigned int *)&String1);
              if ( WmiObjectFromPath >= 0 )
              {
                pvarg.vt = 3;
                pvarg.lVal = (int)String1;
                WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v9->lpVtbl->Put)(
                                      v9,
                                      L"TargetIPAddress",
                                      0,
                                      &pvarg,
                                      0);
              }
              if ( !WmiObjectFromPath )
                WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64, _QWORD, _QWORD))this[8]->lpVtbl->PutInstance)(
                                      this[8],
                                      v9,
                                      1,
                                      0,
                                      0);
            }
          }
        }
        else
        {
          WmiObjectFromPath = -2147024882;
        }
        ((void (__fastcall *)(struct IWbemClassObject *))v9->lpVtbl->Release)(v9);
        if ( !WmiObjectFromPath )
          UpdateService(0x87u);
      }
    }
  }
  return (unsigned int)WmiObjectFromPath;
}

```

## disassembly

```asm
0x180024e40  mov     [rsp-8+arg_10], rbx
0x180024e45  push    rbp
0x180024e46  push    rsi
0x180024e47  push    rdi
0x180024e48  lea     rbp, [rsp-170h]
0x180024e50  sub     rsp, 270h
0x180024e57  mov     rax, cs:__security_cookie
0x180024e5e  xor     rax, rsp
0x180024e61  mov     [rbp+180h+var_20], rax
0x180024e68  xor     eax, eax
0x180024e6a  mov     [rsp+280h+var_250], 0
0x180024e6f  mov     [rsp+280h+var_240], 0
0x180024e78  xorps   xmm0, xmm0
0x180024e7b  mov     qword ptr [rsp+280h+pvarg+10h], rax
0x180024e80  mov     rsi, rcx
0x180024e83  movups  xmmword ptr [rsp+280h+pvarg], xmm0
0x180024e88  test    rdx, rdx
0x180024e8b  jnz     short loc_180024E97
0x180024e8d  mov     eax, 80070057h
0x180024e92  jmp     loc_180025070
0x180024e97  mov     r8, rdx; unsigned __int16 *
0x180024e9a  lea     rcx, [rsp+280h+String2]; unsigned __int16 *
0x180024e9f  mov     edx, 100h; unsigned __int64
0x180024ea4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024ea9  mov     r11, [rsi]
0x180024eac  lea     rdx, [rsp+280h+var_250]
0x180024eb1  mov     rcx, rsi
0x180024eb4  mov     rax, [r11+38h]
0x180024eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ebd  mov     edi, eax
0x180024ebf  test    eax, eax
0x180024ec1  jnz     loc_18002506E
0x180024ec7  cmp     [rsp+280h+var_250], al
0x180024ecb  jz      short loc_180024F19
0x180024ecd  mov     rax, [rsi]
0x180024ed0  lea     rdx, [rsp+280h+String1]
0x180024ed5  mov     rcx, rsi
0x180024ed8  mov     [rsp+280h+String1], 0
0x180024ee1  mov     rax, [rax+40h]
0x180024ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eea  mov     edi, eax
0x180024eec  test    eax, eax
0x180024eee  jnz     loc_18002506E
0x180024ef4  mov     rcx, [rsp+280h+String1]; String1
0x180024ef9  lea     rdx, [rsp+280h+String2]; String2
0x180024efe  call    cs:__imp__wcsicmp
0x180024f04  mov     rcx, [rsp+280h+String1]; pv
0x180024f09  mov     ebx, eax
0x180024f0b  call    cs:__imp_CoTaskMemFree
0x180024f11  test    ebx, ebx
0x180024f13  jz      loc_18002506E
0x180024f19  mov     rdx, [rsi+48h]; unsigned __int16 *
0x180024f1d  lea     r8, [rsp+280h+var_240]; struct IWbemClassObject **
0x180024f22  mov     rcx, [rsi+40h]; struct IWbemServices *
0x180024f26  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180024f2b  mov     edi, eax
0x180024f2d  test    eax, eax
0x180024f2f  jnz     loc_18002506E
0x180024f35  lea     rcx, [rsp+280h+pvarg]; pvarg
0x180024f3a  call    cs:__imp_VariantInit
0x180024f40  lea     eax, [rdi+8]
0x180024f43  lea     rcx, [rsp+280h+String2]; psz
0x180024f48  mov     word ptr [rsp+280h+pvarg], ax
0x180024f4d  call    cs:__imp_SysAllocString
0x180024f53  mov     rcx, rax
0x180024f56  mov     dword ptr [rsp+280h+pvarg+8], eax
0x180024f5a  sar     rcx, 20h
0x180024f5e  mov     dword ptr [rsp+280h+pvarg+0Ch], ecx
0x180024f62  test    rax, rax
0x180024f65  jnz     short loc_180024F71
0x180024f67  mov     edi, 8007000Eh
0x180024f6c  jmp     loc_18002504F
0x180024f71  mov     rcx, [rsp+280h+var_240]
0x180024f76  lea     r9, [rsp+280h+pvarg]
0x180024f7b  xor     r8d, r8d
0x180024f7e  mov     dword ptr [rsp+280h+var_260], 0
0x180024f86  lea     rdx, ?c_wszTargetName@@3QBGB; "TargetName"
0x180024f8d  mov     rax, [rcx]
0x180024f90  mov     rax, [rax+28h]
0x180024f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f99  lea     rcx, [rsp+280h+pvarg]; pvarg
0x180024f9e  mov     edi, eax
0x180024fa0  call    cs:__imp_VariantClear
0x180024fa6  test    edi, edi
0x180024fa8  jnz     loc_18002504F
0x180024fae  mov     rcx, [rsp+280h+var_240]; struct IWbemClassObject *
0x180024fb3  lea     rdx, ?c_wszNameActive@@3QBGB; "NameActive"
0x180024fba  mov     r8b, 1; unsigned __int8
0x180024fbd  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x180024fc2  mov     edi, eax
0x180024fc4  test    eax, eax
0x180024fc6  jnz     loc_18002504F
0x180024fcc  lea     r8, [rsp+280h+String1]; unsigned int *
0x180024fd1  mov     dword ptr [rsp+280h+String1], eax
0x180024fd5  lea     rdx, [rsp+280h+String2]; unsigned __int16 *
0x180024fda  mov     rcx, rsi; this
0x180024fdd  call    ?GenerateTargetAddress@CHNetPortMappingBinding@@AEAAJPEBGPEAK@Z; CHNetPortMappingBinding::GenerateTargetAddress(ushort const *,ulong *)
0x180024fe2  mov     edi, eax
0x180024fe4  test    eax, eax
0x180024fe6  js      short loc_180025024
0x180024fe8  mov     rcx, [rsp+280h+var_240]
0x180024fed  lea     r9, [rsp+280h+pvarg]
0x180024ff2  mov     eax, 3
0x180024ff7  mov     dword ptr [rsp+280h+var_260], 0
0x180024fff  mov     word ptr [rsp+280h+pvarg], ax
0x180025004  lea     rdx, ?c_wszTargetIPAddress@@3QBGB; "TargetIPAddress"
0x18002500b  mov     eax, dword ptr [rsp+280h+String1]
0x18002500f  xor     r8d, r8d
0x180025012  mov     dword ptr [rsp+280h+pvarg+8], eax
0x180025016  mov     rax, [rcx]
0x180025019  mov     rax, [rax+28h]
0x18002501d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025022  mov     edi, eax
0x180025024  test    edi, edi
0x180025026  jnz     short loc_18002504F
0x180025028  mov     rcx, [rsi+40h]
0x18002502c  lea     r8d, [rdi+1]
0x180025030  mov     rdx, [rsp+280h+var_240]
0x180025035  xor     r9d, r9d
0x180025038  mov     [rsp+280h+var_260], 0
0x180025041  mov     rax, [rcx]
0x180025044  mov     rax, [rax+70h]
0x180025048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002504d  mov     edi, eax
0x18002504f  mov     rcx, [rsp+280h+var_240]
0x180025054  mov     rax, [rcx]
0x180025057  mov     rax, [rax+10h]
0x18002505b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025060  test    edi, edi
0x180025062  jnz     short loc_18002506E
0x180025064  mov     ecx, 87h; dwControl
0x180025069  call    ?UpdateService@@YAXK@Z; UpdateService(ulong)
0x18002506e  mov     eax, edi
0x180025070  mov     rcx, [rbp+180h+var_20]
0x180025077  xor     rcx, rsp; StackCookie
0x18002507a  call    __security_check_cookie
0x18002507f  mov     rbx, [rsp+280h+arg_10]
0x180025087  add     rsp, 270h
0x18002508e  pop     rdi
0x18002508f  pop     rsi
0x180025090  pop     rbp
0x180025091  retn
```
