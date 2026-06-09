# SetPackageName(void *,_SP_DEVINFO_DATA *)

- ea: `0x180015c40`
- end: `0x180015d19`
- name: `?SetPackageName@@YAHPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180013260`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x180015c40`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180015ce5`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180015ce5`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180015ca1`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180015ca1`

## pseudocode

```c
_BOOL8 __fastcall SetPackageName(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)
{
  struct _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v6[260]; // [rsp+38h] [rbp-230h] BYREF
  __int64 v7; // [rsp+240h] [rbp-28h]

  memset_0(v6, 0, 0x210u);
  ClassInstallParams.cbSize = 8;
  ClassInstallParams.InstallFunction = 37;
  if ( !SetupDiGetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, &ClassInstallParams, 0x218u, 0) )
    return 0;
  StringCchCopyW(v6, 0x104u, L"3FBF5B30-DEB4-11D1-AC97-00A0C903492B");
  v7 = *((_QWORD *)gpCodeDownLoadInfo + 1);
  return SetupDiSetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, &ClassInstallParams, 0x218u);
}

```

## disassembly

```asm
0x180015c40  mov     [rsp+arg_10], rbx
0x180015c45  push    rdi
0x180015c46  sub     rsp, 260h
0x180015c4d  mov     rax, cs:__security_cookie
0x180015c54  xor     rax, rsp
0x180015c57  mov     [rsp+268h+var_18], rax
0x180015c5f  mov     rdi, rdx
0x180015c62  mov     rbx, rcx
0x180015c65  xor     edx, edx; Val
0x180015c67  lea     rcx, [rsp+268h+var_230]; void *
0x180015c6c  mov     r8d, 210h; Size
0x180015c72  call    memset_0
0x180015c77  mov     r9d, 218h; ClassInstallParamsSize
0x180015c7d  mov     [rsp+268h+ClassInstallParams.cbSize], 8
0x180015c85  lea     r8, [rsp+268h+ClassInstallParams]; ClassInstallParams
0x180015c8a  mov     [rsp+268h+ClassInstallParams.InstallFunction], 25h ; '%'
0x180015c92  mov     rdx, rdi; DeviceInfoData
0x180015c95  mov     [rsp+268h+RequiredSize], 0; RequiredSize
0x180015c9e  mov     rcx, rbx; DeviceInfoSet
0x180015ca1  call    cs:__imp_SetupDiGetClassInstallParamsW
0x180015ca7  test    eax, eax
0x180015ca9  jz      short loc_180015CF6
0x180015cab  lea     r8, a3fbf5b30Deb411_0; "3FBF5B30-DEB4-11D1-AC97-00A0C903492B"
0x180015cb2  mov     edx, 104h; unsigned __int64
0x180015cb7  lea     rcx, [rsp+268h+var_230]; unsigned __int16 *
0x180015cbc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015cc1  mov     r11, cs:gpCodeDownLoadInfo
0x180015cc8  lea     r8, [rsp+268h+ClassInstallParams]; ClassInstallParams
0x180015ccd  mov     r9d, 218h; ClassInstallParamsSize
0x180015cd3  mov     rdx, rdi; DeviceInfoData
0x180015cd6  mov     rcx, rbx; DeviceInfoSet
0x180015cd9  mov     rax, [r11+8]
0x180015cdd  mov     [rsp+268h+var_28], rax
0x180015ce5  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180015ceb  xor     ecx, ecx
0x180015ced  test    eax, eax
0x180015cef  setnz   cl
0x180015cf2  mov     eax, ecx
0x180015cf4  jmp     short loc_180015CF8
0x180015cf6  xor     eax, eax
0x180015cf8  mov     rcx, [rsp+268h+var_18]
0x180015d00  xor     rcx, rsp; StackCookie
0x180015d03  call    __security_check_cookie
0x180015d08  mov     rbx, [rsp+268h+arg_10]
0x180015d10  add     rsp, 260h
0x180015d17  pop     rdi
0x180015d18  retn
```
