# DriverPackageReaderDism::DriverPackageReaderDism(CDriverMap *)

- ea: `0x18004e618`
- end: `0x18004e8e6`
- name: `??0DriverPackageReaderDism@@QEAA@PEAVCDriverMap@@@Z`
- size: `718`
- prototype: `DriverPackageReaderDism *__fastcall(DriverPackageReaderDism *__hidden this, struct CDriverMap *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180046388`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x18004e618`
- `0x18004eda0`
- `0x18005e3ec`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e8b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e8b7`

## string_xrefs

- `0x18004e693`: `DriverPackageReaderDism::DriverPackageReaderDism`
- `0x18004e6be`: `DriverPackageReaderDism::DriverPackageReaderDism`
- `0x18004e725`: `DriverPackageReaderDism::DriverPackageReaderDism`
- `0x18004e7f2`: `DriverPackageReaderDism::DriverPackageReaderDism`
- `0x18004e820`: `DriverPackageReaderDism::DriverPackageReaderDism`
- `0x18004e74d`: `DismOpenSession`
- `0x18004e786`: `DismDelete`
- `0x18004e7c8`: `dismapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DriverPackageReaderDism *__fastcall DriverPackageReaderDism::DriverPackageReaderDism(
        DriverPackageReaderDism *this,
        struct CDriverMap *a2)
{
  FILE *v3; // rax
  FILE *v4; // rax
  FILE *v5; // rax
  int v6; // eax
  DWORD v7; // edi
  FILE *v8; // rax
  FILE *v9; // rax
  FILE *v10; // rax
  DWORD v11; // ecx
  int inited; // eax
  _QWORD v14[14]; // [rsp+40h] [rbp-39h] BYREF

  *(_QWORD *)this = &DriverPackageReaderDism::`vftable';
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 5) = 0;
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 3) = 0;
  if ( *((_QWORD *)this + 1) )
  {
    v14[0] = "DismInitialize";
    v14[1] = (char *)this + 32;
    v14[2] = "DismOpenSession";
    v14[3] = (char *)this + 40;
    v14[4] = "DismGetDrivers";
    v14[5] = (char *)this + 48;
    v14[6] = "DismGetDriverInfo";
    v14[7] = (char *)this + 56;
    v14[8] = "DismDelete";
    v14[9] = (char *)this + 64;
    v14[10] = "DismCloseSession";
    v14[11] = (char *)this + 72;
    v14[12] = "DismShutdown";
    v14[13] = (char *)this + 80;
    v6 = ResolveImportedApis((__int64)L"dismapi.dll", 7u, (__int64)v14, (HMODULE *)this + 3);
    v7 = v6;
    if ( v6 >= 0 )
    {
      inited = DriverPackageReaderDism::InitDismSession(this);
      v11 = inited;
      if ( inited < 0 )
      {
        if ( (inited & 0x1FFF0000) == 0x70000 )
          v11 = (unsigned __int16)inited;
      }
      else
      {
        *((_DWORD *)this + 5) = 1;
        v11 = 0;
      }
    }
    else
    {
      AslLogCallPrintf(
        3,
        "DriverPackageReaderDism::DriverPackageReaderDism",
        48,
        "0x%08x Failed to retrieve dism apis.",
        v6);
      if ( EnableDevInvStdErrLog )
      {
        v8 = o___acrt_iob_func_0(2u);
        fprintf(v8, "Info: %s, %u: ", "DriverPackageReaderDism::DriverPackageReaderDism", 48);
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "0x%08x Failed to retrieve dism apis.", v7);
        v10 = o___acrt_iob_func_0(2u);
        fprintf(v10, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x4000000, "0x%08x Failed to retrieve dism apis.", v7);
      if ( (v7 & 0x1FFF0000) == 0x70000 )
        v7 = (unsigned __int16)v7;
      v11 = v7;
    }
    SetLastError(v11);
  }
  else
  {
    AslLogCallPrintf(2, "DriverPackageReaderDism::DriverPackageReaderDism", 28, "DriverMap is NULL [%#x]", -2147467259);
    if ( EnableDevInvStdErrLog )
    {
      v3 = o___acrt_iob_func_0(2u);
      fprintf(v3, "Error: %s, %u: ", "DriverPackageReaderDism::DriverPackageReaderDism", 28);
      v4 = o___acrt_iob_func_0(2u);
      fprintf(v4, "DriverMap is NULL [%#x]", -2147467259);
      v5 = o___acrt_iob_func_0(2u);
      fprintf(v5, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "DriverMap is NULL [%#x]", -2147467259);
    AslLogCallPrintf(1, "DriverPackageReaderDism::DriverPackageReaderDism", 28, "DriverMap is NULL [%#x]", -2147467259);
  }
  return this;
}

```

## disassembly

```asm
0x18004e618  mov     [rsp-8+arg_8], rbx
0x18004e61d  mov     [rsp-8+arg_10], rdi
0x18004e622  push    rbp
0x18004e623  push    r12
0x18004e625  push    r14
0x18004e627  lea     rbp, [rsp-47h]
0x18004e62c  sub     rsp, 0C0h
0x18004e633  mov     rax, cs:__security_cookie
0x18004e63a  xor     rax, rsp
0x18004e63d  mov     [rbp+57h+var_20], rax
0x18004e641  mov     rbx, rcx
0x18004e644  mov     [rbp+57h+var_A0], rcx
0x18004e648  lea     rax, ??_7DriverPackageReaderDism@@6B@; const DriverPackageReaderDism::`vftable'
0x18004e64f  mov     [rcx], rax
0x18004e652  lea     r9, [rcx+18h]
0x18004e656  mov     qword ptr [r9], 0
0x18004e65d  mov     dword ptr [rcx+14h], 0
0x18004e664  mov     [rcx+8], rdx
0x18004e668  mov     qword ptr [r9], 0
0x18004e66f  cmp     qword ptr [rcx+8], 0
0x18004e674  jnz     loc_18004E73A
0x18004e67a  mov     edi, 80004005h
0x18004e67f  mov     [rsp+0D0h+var_B0], edi
0x18004e683  lea     r12, aDrivermapIsNul; "DriverMap is NULL [%#x]"
0x18004e68a  mov     r9, r12
0x18004e68d  mov     r8d, 1Ch
0x18004e693  lea     rdx, aDriverpackager_10; "DriverPackageReaderDism::DriverPackageR"...
0x18004e69a  lea     r14d, [r8-1Ah]
0x18004e69e  mov     ecx, r14d
0x18004e6a1  call    AslLogCallPrintf
0x18004e6a6  cmp     cs:EnableDevInvStdErrLog, 0
0x18004e6ad  jz      short loc_18004E6FE
0x18004e6af  mov     ecx, r14d; Ix
0x18004e6b2  call    _o___acrt_iob_func_0
0x18004e6b7  mov     rcx, rax; Stream
0x18004e6ba  lea     r9d, [r14+1Ah]
0x18004e6be  lea     r8, aDriverpackager_10; "DriverPackageReaderDism::DriverPackageR"...
0x18004e6c5  lea     rdx, Format; "Error: %s, %u: "
0x18004e6cc  call    fprintf
0x18004e6d1  mov     ecx, r14d; Ix
0x18004e6d4  call    _o___acrt_iob_func_0
0x18004e6d9  mov     rcx, rax; Stream
0x18004e6dc  mov     r8d, edi
0x18004e6df  mov     rdx, r12; Format
0x18004e6e2  call    fprintf
0x18004e6e7  mov     ecx, r14d; Ix
0x18004e6ea  call    _o___acrt_iob_func_0
0x18004e6ef  mov     rcx, rax; Stream
0x18004e6f2  lea     rdx, asc_18011EAD8; "\n"
0x18004e6f9  call    fprintf
0x18004e6fe  cmp     cs:g_DeviceMapLogFunction, 0
0x18004e706  jz      short loc_18004E718
0x18004e708  mov     r8d, edi
0x18004e70b  mov     rdx, r12
0x18004e70e  mov     ecx, 2000000h
0x18004e713  call    TraceMessageCallback
0x18004e718  mov     [rsp+0D0h+var_B0], edi
0x18004e71c  mov     r9, r12
0x18004e71f  mov     r8d, 1Ch
0x18004e725  lea     rdx, aDriverpackager_10; "DriverPackageReaderDism::DriverPackageR"...
0x18004e72c  lea     ecx, [r8-1Bh]
0x18004e730  call    AslLogCallPrintf
0x18004e735  jmp     loc_18004E8BE
0x18004e73a  lea     rax, aDisminitialize; "DismInitialize"
0x18004e741  mov     [rbp+57h+var_90], rax
0x18004e745  lea     rax, [rcx+20h]
0x18004e749  mov     [rbp+57h+var_88], rax
0x18004e74d  lea     rax, aDismopensessio; "DismOpenSession"
0x18004e754  mov     [rbp+57h+var_80], rax
0x18004e758  lea     rax, [rcx+28h]
0x18004e75c  mov     [rbp+57h+var_78], rax
0x18004e760  lea     rax, aDismgetdrivers; "DismGetDrivers"
0x18004e767  mov     [rbp+57h+var_70], rax
0x18004e76b  lea     rax, [rcx+30h]
0x18004e76f  mov     [rbp+57h+var_68], rax
0x18004e773  lea     rax, aDismgetdriveri_0; "DismGetDriverInfo"
0x18004e77a  mov     [rbp+57h+var_60], rax
0x18004e77e  lea     rax, [rcx+38h]
0x18004e782  mov     [rbp+57h+var_58], rax
0x18004e786  lea     rax, aDismdelete; "DismDelete"
0x18004e78d  mov     [rbp+57h+var_50], rax
0x18004e791  lea     rax, [rcx+40h]
0x18004e795  mov     [rbp+57h+var_48], rax
0x18004e799  lea     rax, aDismclosesessi; "DismCloseSession"
0x18004e7a0  mov     [rbp+57h+var_40], rax
0x18004e7a4  lea     rax, [rcx+48h]
0x18004e7a8  mov     [rbp+57h+var_38], rax
0x18004e7ac  lea     rax, aDismshutdown; "DismShutdown"
0x18004e7b3  mov     [rbp+57h+var_30], rax
0x18004e7b7  lea     rax, [rcx+50h]
0x18004e7bb  mov     [rbp+57h+var_28], rax
0x18004e7bf  lea     r8, [rbp+57h+var_90]
0x18004e7c3  mov     edx, 7
0x18004e7c8  lea     rcx, aDismapiDll; "dismapi.dll"
0x18004e7cf  call    ?ResolveImportedApis@@YAJPEBGKPEAU_IMPORTED_API_MAP@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; ResolveImportedApis(ushort const *,ulong,_IMPORTED_API_MAP *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &)
0x18004e7d4  mov     edi, eax
0x18004e7d6  test    eax, eax
0x18004e7d8  jns     loc_18004E88F
0x18004e7de  mov     [rsp+0D0h+var_B0], eax
0x18004e7e2  lea     r12, a0x08xFailedToR; "0x%08x Failed to retrieve dism apis."
0x18004e7e9  mov     r9, r12
0x18004e7ec  mov     r8d, 30h ; '0'
0x18004e7f2  lea     rdx, aDriverpackager_10; "DriverPackageReaderDism::DriverPackageR"...
0x18004e7f9  lea     ecx, [r8-2Dh]
0x18004e7fd  call    AslLogCallPrintf
0x18004e802  cmp     cs:EnableDevInvStdErrLog, 0
0x18004e809  jz      short loc_18004E860
0x18004e80b  mov     r14d, 2
0x18004e811  mov     ecx, r14d; Ix
0x18004e814  call    _o___acrt_iob_func_0
0x18004e819  mov     rcx, rax; Stream
0x18004e81c  lea     r9d, [r14+2Eh]
0x18004e820  lea     r8, aDriverpackager_10; "DriverPackageReaderDism::DriverPackageR"...
0x18004e827  lea     rdx, aInfoSU; "Info: %s, %u: "
0x18004e82e  call    fprintf
0x18004e833  mov     ecx, r14d; Ix
0x18004e836  call    _o___acrt_iob_func_0
0x18004e83b  mov     rcx, rax; Stream
0x18004e83e  mov     r8d, edi
0x18004e841  mov     rdx, r12; Format
0x18004e844  call    fprintf
0x18004e849  mov     ecx, r14d; Ix
0x18004e84c  call    _o___acrt_iob_func_0
0x18004e851  mov     rcx, rax; Stream
0x18004e854  lea     rdx, asc_18011EAD8; "\n"
0x18004e85b  call    fprintf
0x18004e860  cmp     cs:g_DeviceMapLogFunction, 0
0x18004e868  jz      short loc_18004E87A
0x18004e86a  mov     r8d, edi
0x18004e86d  mov     rdx, r12
0x18004e870  mov     ecx, 4000000h
0x18004e875  call    TraceMessageCallback
0x18004e87a  mov     eax, edi
0x18004e87c  and     eax, 1FFF0000h
0x18004e881  cmp     eax, 70000h
0x18004e886  jnz     short loc_18004E88B
0x18004e888  movzx   edi, di
0x18004e88b  mov     ecx, edi
0x18004e88d  jmp     short loc_18004E8B7
0x18004e88f  mov     rcx, rbx; this
0x18004e892  call    ?InitDismSession@DriverPackageReaderDism@@AEAAJXZ; DriverPackageReaderDism::InitDismSession(void)
0x18004e897  mov     ecx, eax
0x18004e899  test    eax, eax
0x18004e89b  js      short loc_18004E8A8
0x18004e89d  mov     dword ptr [rbx+14h], 1
0x18004e8a4  xor     ecx, ecx
0x18004e8a6  jmp     short loc_18004E8B7
0x18004e8a8  and     eax, 1FFF0000h
0x18004e8ad  cmp     eax, 70000h
0x18004e8b2  jnz     short loc_18004E8B7
0x18004e8b4  movzx   ecx, cx; dwErrCode
0x18004e8b7  call    cs:__imp_SetLastError
0x18004e8bd  nop
0x18004e8be  mov     rax, rbx
0x18004e8c1  mov     rcx, [rbp+57h+var_20]
0x18004e8c5  xor     rcx, rsp; StackCookie
0x18004e8c8  call    __security_check_cookie
0x18004e8cd  lea     r11, [rsp+0D0h+var_10]
0x18004e8d5  mov     rbx, [r11+28h]
0x18004e8d9  mov     rdi, [r11+30h]
0x18004e8dd  mov     rsp, r11
0x18004e8e0  pop     r14
0x18004e8e2  pop     r12
0x18004e8e4  pop     rbp
0x18004e8e5  retn
```
