# HrSetupDiCreateDeviceInfoList(_GUID const *,HWND__ *,void * *)

- ea: `0x180030b90`
- end: `0x180030bc6`
- name: `?HrSetupDiCreateDeviceInfoList@@YAJPEBU_GUID@@PEAUHWND__@@PEAPEAX@Z`
- size: `54`
- prototype: `__int64 __fastcall(const struct _GUID *, HWND, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001e6c8`
- `0x1800211b4`
- `0x180025c44`

## callees

- `0x18003060c`
- `0x180030b90`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180030ba2`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180030ba2`

## pseudocode

```c
__int64 __fastcall HrSetupDiCreateDeviceInfoList(const struct _GUID *a1, HWND a2, void **a3)
{
  HDEVINFO DeviceInfoList; // rax
  unsigned int Win32Error; // ecx

  DeviceInfoList = SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0);
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    Win32Error = HrFromLastWin32Error();
    DeviceInfoList = 0;
  }
  else
  {
    Win32Error = 0;
  }
  *a3 = DeviceInfoList;
  return Win32Error;
}

```

## disassembly

```asm
0x180030b90  push    rbx
0x180030b92  sub     rsp, 20h
0x180030b96  xor     edx, edx; hwndParent
0x180030b98  lea     rcx, GUID_DEVCLASS_NET; ClassGuid
0x180030b9f  mov     rbx, r8
0x180030ba2  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180030ba8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030bac  jz      short loc_180030BB2
0x180030bae  xor     ecx, ecx
0x180030bb0  jmp     short loc_180030BBB
0x180030bb2  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030bb7  mov     ecx, eax
0x180030bb9  xor     eax, eax
0x180030bbb  mov     [rbx], rax
0x180030bbe  mov     eax, ecx
0x180030bc0  add     rsp, 20h
0x180030bc4  pop     rbx
0x180030bc5  retn
```
