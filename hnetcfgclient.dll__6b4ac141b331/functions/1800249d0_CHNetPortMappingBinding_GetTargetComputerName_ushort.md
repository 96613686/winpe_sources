# CHNetPortMappingBinding::GetTargetComputerName(ushort * *)

- ea: `0x1800249d0`
- end: `0x180024afc`
- name: `?GetTargetComputerName@CHNetPortMappingBinding@@UEAAJPEAPEAG@Z`
- size: `300`
- prototype: `__int64 __fastcall(CHNetPortMappingBinding *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005698`
- `0x1800249d0`
- `0x180029a3c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180024aaf`
- `OLEAUT32!__imp_SysStringLen` at `0x180024aaf`
- `OLEAUT32!__imp_VariantInit` at `0x180024a02`
- `OLEAUT32!__imp_VariantInit` at `0x180024a02`
- `OLEAUT32!__imp_VariantClear` at `0x180024ae4`
- `OLEAUT32!__imp_VariantClear` at `0x180024ae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024abd`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingBinding::GetTargetComputerName(CHNetPortMappingBinding *this, unsigned __int16 **a2)
{
  unsigned int WmiObjectFromPath; // ebx
  struct IWbemClassObject *v5; // rcx
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  char v10; // [rsp+88h] [rbp+28h] BYREF
  struct IWbemClassObject *v11; // [rsp+90h] [rbp+30h] BYREF

  v11 = 0;
  v10 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a2 )
  {
    *a2 = 0;
    WmiObjectFromPath = GetWmiObjectFromPath(
                          *((struct IWbemServices **)this + 8),
                          *((unsigned __int16 **)this + 9),
                          &v11);
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = (*(__int64 (__fastcall **)(CHNetPortMappingBinding *, char *))(*(_QWORD *)this + 56LL))(
                            this,
                            &v10);
      if ( !WmiObjectFromPath )
      {
        if ( v10 )
        {
          v5 = v11;
          *a2 = 0;
          WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v5->lpVtbl->Get)(
                                v5,
                                L"TargetName",
                                0,
                                &pvarg,
                                0,
                                0);
        }
        else
        {
          WmiObjectFromPath = -2147418113;
        }
      }
      ((void (__fastcall *)(struct IWbemClassObject *))v11->lpVtbl->Release)(v11);
      if ( !WmiObjectFromPath )
      {
        v6 = SysStringLen(pvarg.bstrVal) + 1;
        v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
        *a2 = v7;
        if ( v7 )
          StringCchCopyW(v7, (unsigned int)v6, pvarg.bstrVal);
        else
          WmiObjectFromPath = -2147024882;
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
0x1800249d0  mov     [rsp-18h+arg_0], rbx
0x1800249d5  push    rbp
0x1800249d6  push    rsi
0x1800249d7  push    rdi
0x1800249d8  mov     rbp, rsp
0x1800249db  sub     rsp, 60h
0x1800249df  mov     rdi, rcx
0x1800249e2  mov     [rbp+arg_10], 0
0x1800249ea  xorps   xmm0, xmm0
0x1800249ed  mov     [rbp+arg_8], 0
0x1800249f1  xor     eax, eax
0x1800249f3  lea     rcx, [rbp+pvarg]; pvarg
0x1800249f7  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800249fb  mov     qword ptr [rbp+pvarg+10h], rax
0x1800249ff  mov     rsi, rdx
0x180024a02  call    cs:__imp_VariantInit
0x180024a08  test    rsi, rsi
0x180024a0b  jnz     short loc_180024A17
0x180024a0d  mov     ebx, 80004003h
0x180024a12  jmp     loc_180024AEA
0x180024a17  mov     qword ptr [rsi], 0
0x180024a1e  lea     r8, [rbp+arg_10]; struct IWbemClassObject **
0x180024a22  mov     rdx, [rdi+48h]; unsigned __int16 *
0x180024a26  mov     rcx, [rdi+40h]; struct IWbemServices *
0x180024a2a  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180024a2f  mov     ebx, eax
0x180024a31  test    eax, eax
0x180024a33  jnz     loc_180024AEA
0x180024a39  mov     rax, [rdi]
0x180024a3c  lea     rdx, [rbp+arg_8]
0x180024a40  mov     rcx, rdi
0x180024a43  mov     rax, [rax+38h]
0x180024a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a4c  mov     ebx, eax
0x180024a4e  test    eax, eax
0x180024a50  jnz     short loc_180024A97
0x180024a52  cmp     [rbp+arg_8], al
0x180024a55  jnz     short loc_180024A5E
0x180024a57  mov     ebx, 8000FFFFh
0x180024a5c  jmp     short loc_180024A97
0x180024a5e  mov     rcx, [rbp+arg_10]
0x180024a62  lea     r9, [rbp+pvarg]
0x180024a66  mov     qword ptr [rsi], 0
0x180024a6d  lea     rdx, ?c_wszTargetName@@3QBGB; "TargetName"
0x180024a74  mov     [rsp+60h+var_38], 0
0x180024a7d  xor     r8d, r8d
0x180024a80  mov     [rsp+60h+var_40], 0
0x180024a89  mov     rax, [rcx]
0x180024a8c  mov     rax, [rax+20h]
0x180024a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a95  mov     ebx, eax
0x180024a97  mov     rcx, [rbp+arg_10]
0x180024a9b  mov     rax, [rcx]
0x180024a9e  mov     rax, [rax+10h]
0x180024aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aa7  test    ebx, ebx
0x180024aa9  jnz     short loc_180024AEA
0x180024aab  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x180024aaf  call    cs:__imp_SysStringLen
0x180024ab5  inc     eax
0x180024ab7  mov     edi, eax
0x180024ab9  lea     rcx, [rax+rax]; cb
0x180024abd  call    cs:__imp_CoTaskMemAlloc
0x180024ac3  mov     [rsi], rax
0x180024ac6  test    rax, rax
0x180024ac9  jz      short loc_180024ADB
0x180024acb  mov     r8, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x180024acf  mov     edx, edi; unsigned __int64
0x180024ad1  mov     rcx, rax; unsigned __int16 *
0x180024ad4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024ad9  jmp     short loc_180024AE0
0x180024adb  mov     ebx, 8007000Eh
0x180024ae0  lea     rcx, [rbp+pvarg]; pvarg
0x180024ae4  call    cs:__imp_VariantClear
0x180024aea  mov     eax, ebx
0x180024aec  mov     rbx, [rsp+60h+arg_0]
0x180024af4  add     rsp, 60h
0x180024af8  pop     rdi
0x180024af9  pop     rsi
0x180024afa  pop     rbp
0x180024afb  retn
```
