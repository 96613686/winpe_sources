# CAdvanced::CreatePage(void *,_SP_DEVINFO_DATA *)

- ea: `0x180008e2c`
- end: `0x180008ef9`
- name: `?CreatePage@CAdvanced@@QEAAPEAU_PSP@@PEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `205`
- prototype: `struct _PSP *__fastcall(CAdvanced *__hidden this, HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180009224`

## callees

- `0x1800030e0`
- `0x180007f3c`
- `0x180008560`
- `0x180008e2c`
- `0x18000a5dc`
- `0x180011e58`

## import_xrefs

- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180008e6d`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180008e6d`

## pseudocode

```c
struct _PSP *__fastcall CAdvanced::CreatePage(CAdvanced *this, HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)
{
  __int64 v5; // rdi
  CAdvancedParams *v6; // rbx
  HKEY v8; // rax
  HKEY v9; // rcx
  int Win32Error; // eax
  unsigned int v11; // r8d
  const unsigned __int16 *v12; // r9
  const unsigned __int16 *v14; // [rsp+20h] [rbp-38h]
  const unsigned __int16 *v15; // [rsp+28h] [rbp-30h]
  HINSTANCE v16; // [rsp+30h] [rbp-28h]
  HKEY v17; // [rsp+60h] [rbp+8h] BYREF

  v5 = 0;
  v6 = (CAdvanced *)((char *)this + 16);
  v17 = 0;
  v8 = SetupDiOpenDevRegKey(DeviceInfoSet, DeviceInfoData, 1u, 0, 2u, 0xF003Fu);
  v9 = v8;
  if ( v8 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    Win32Error = HrFromLastWin32Error();
    v9 = 0;
    *(_QWORD *)v6 = 0;
    if ( Win32Error < 0 )
      return (struct _PSP *)v5;
  }
  else
  {
    *(_QWORD *)v6 = v8;
  }
  if ( HrRegOpenKeyEx(v9, L"Ndi\\Params", 0x2001Bu, &v17) >= 0 )
  {
    CAdvancedParams::FillParamList(v6, *(HKEY *)v6, v17);
    ATL::CRegKey::~CRegKey((ATL::CRegKey *)&v17);
    *((_DWORD *)v6 + 16) = 1;
    *((_QWORD *)v6 + 9) = DeviceInfoSet;
    *((_QWORD *)v6 + 10) = DeviceInfoData;
    return CPropSheetPage::CreatePage(this, 0x5E1u, v11, v12, v14, v15, v16);
  }
  return (struct _PSP *)v5;
}

```

## disassembly

```asm
0x180008e2c  mov     rax, rsp
0x180008e2f  mov     [rax+10h], rbx
0x180008e33  mov     [rax+18h], rbp
0x180008e37  push    rsi
0x180008e38  push    rdi
0x180008e39  push    r14
0x180008e3b  sub     rsp, 40h
0x180008e3f  mov     rsi, r8
0x180008e42  mov     dword ptr [rax-30h], 0F003Fh
0x180008e49  mov     rbp, rdx
0x180008e4c  mov     dword ptr [rax-38h], 2
0x180008e53  xor     edi, edi
0x180008e55  lea     rbx, [rcx+10h]
0x180008e59  mov     r14, rcx
0x180008e5c  mov     [rax+8], rdi
0x180008e60  xor     r9d, r9d; HwProfile
0x180008e63  mov     rdx, rsi; DeviceInfoData
0x180008e66  mov     rcx, rbp; DeviceInfoSet
0x180008e69  lea     r8d, [rdi+1]; Scope
0x180008e6d  call    cs:__imp_SetupDiOpenDevRegKey
0x180008e73  mov     rcx, rax
0x180008e76  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008e7a  jz      short loc_180008E81
0x180008e7c  mov     [rbx], rax
0x180008e7f  jmp     short loc_180008E8F
0x180008e81  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180008e86  xor     ecx, ecx; HKEY
0x180008e88  mov     [rbx], rcx
0x180008e8b  test    eax, eax
0x180008e8d  js      short loc_180008EE3
0x180008e8f  lea     r9, [rsp+58h+arg_0]; HKEY *
0x180008e94  mov     r8d, 2001Bh; unsigned int
0x180008e9a  lea     rdx, ?c_szRegKeyParamsFromInstance@@3QBGB; "Ndi\\Params"
0x180008ea1  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180008ea6  test    eax, eax
0x180008ea8  js      short loc_180008EE3
0x180008eaa  mov     r8, [rsp+58h+arg_0]; HKEY
0x180008eaf  mov     rcx, rbx; this
0x180008eb2  mov     rdx, [rbx]; HKEY
0x180008eb5  call    ?FillParamList@CAdvancedParams@@IEAAXPEAUHKEY__@@0@Z; CAdvancedParams::FillParamList(HKEY__ *,HKEY__ *)
0x180008eba  lea     rcx, [rsp+58h+arg_0]; this
0x180008ebf  call    ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
0x180008ec4  mov     edx, 5E1h; unsigned int
0x180008ec9  mov     dword ptr [rbx+40h], 1
0x180008ed0  mov     rcx, r14; this
0x180008ed3  mov     [rbx+48h], rbp
0x180008ed7  mov     [rbx+50h], rsi
0x180008edb  call    ?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@@Z; CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *)
0x180008ee0  mov     rdi, rax
0x180008ee3  mov     rbx, [rsp+58h+arg_8]
0x180008ee8  mov     rax, rdi
0x180008eeb  mov     rbp, [rsp+58h+arg_10]
0x180008ef0  add     rsp, 40h
0x180008ef4  pop     r14
0x180008ef6  pop     rdi
0x180008ef7  pop     rsi
0x180008ef8  retn
```
