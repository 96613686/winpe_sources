# ProcessPerInstanceAddRegSections(void *,_SP_DEVINFO_DATA *,_PSETUP_LOCAL_DATA *)

- ea: `0x180015b84`
- end: `0x180015c3a`
- name: `?ProcessPerInstanceAddRegSections@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_PSETUP_LOCAL_DATA@@@Z`
- size: `182`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, struct _PSETUP_LOCAL_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180013804`

## callees

- `0x180015b84`
- `0x18001c660`
- `0x180020b60`
- `0x180036684`

## import_xrefs

- `SETUPAPI!SetupCloseInfFile` at `0x180015c1c`
- `SETUPAPI!SetupCloseInfFile` at `0x180015c1c`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180015c13`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180015c13`

## pseudocode

```c
__int64 __fastcall ProcessPerInstanceAddRegSections(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        struct _PSETUP_LOCAL_DATA *a3)
{
  unsigned int v6; // edi
  void *v7; // rax
  void *v8; // rbx
  PCWSTR SectionName; // [rsp+A0h] [rbp+18h] BYREF

  SectionName = 0;
  v6 = StrCatAlloc(&SectionName, *((_QWORD *)a3 + 2), L".ProcessPerPnpInstance", 0);
  if ( !v6 )
  {
    v7 = (void *)OpenPrinterInfFile(*(unsigned __int16 **)a3, 0);
    v8 = v7;
    if ( v7 != (void *)-1LL )
    {
      SetupInstallFromInfSectionW(0, v7, SectionName, 4u, 0, 0, 0, 0, 0, DeviceInfoSet, DeviceInfoData);
      SetupCloseInfFile(v8);
    }
  }
  DllFreeSplMem(SectionName);
  return v6;
}

```

## disassembly

```asm
0x180015b84  mov     rax, rsp
0x180015b87  push    rbx
0x180015b88  push    rbp
0x180015b89  push    rsi
0x180015b8a  push    rdi
0x180015b8b  sub     rsp, 68h
0x180015b8f  mov     rbx, r8
0x180015b92  mov     qword ptr [rax+18h], 0
0x180015b9a  mov     rsi, rdx
0x180015b9d  lea     r8, aProcessperpnpi; ".ProcessPerPnpInstance"
0x180015ba4  mov     rbp, rcx
0x180015ba7  xor     r9d, r9d
0x180015baa  lea     rcx, [rax+18h]
0x180015bae  mov     rdx, [rbx+10h]
0x180015bb2  call    StrCatAlloc
0x180015bb7  mov     edi, eax
0x180015bb9  test    eax, eax
0x180015bbb  jnz     short loc_180015C22
0x180015bbd  mov     rcx, [rbx]; unsigned __int16 *
0x180015bc0  xor     edx, edx
0x180015bc2  call    OpenPrinterInfFile
0x180015bc7  mov     rbx, rax
0x180015bca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015bce  jz      short loc_180015C22
0x180015bd0  mov     r8, [rsp+88h+SectionName]; SectionName
0x180015bd8  lea     r9d, [rdi+4]; Flags
0x180015bdc  mov     [rsp+88h+DeviceInfoData], rsi; DeviceInfoData
0x180015be1  mov     rdx, rax; InfHandle
0x180015be4  mov     [rsp+88h+DeviceInfoSet], rbp; DeviceInfoSet
0x180015be9  xor     ecx, ecx; Owner
0x180015beb  mov     [rsp+88h+Context], 0; Context
0x180015bf4  mov     [rsp+88h+MsgHandler], 0; MsgHandler
0x180015bfd  mov     [rsp+88h+CopyFlags], edi; CopyFlags
0x180015c01  mov     [rsp+88h+SourceRootPath], 0; SourceRootPath
0x180015c0a  mov     [rsp+88h+RelativeKeyRoot], 0; RelativeKeyRoot
0x180015c13  call    cs:__imp_SetupInstallFromInfSectionW
0x180015c19  mov     rcx, rbx; InfHandle
0x180015c1c  call    cs:__imp_SetupCloseInfFile
0x180015c22  mov     rcx, [rsp+88h+SectionName]
0x180015c2a  call    DllFreeSplMem
0x180015c2f  mov     eax, edi
0x180015c31  add     rsp, 68h
0x180015c35  pop     rdi
0x180015c36  pop     rsi
0x180015c37  pop     rbp
0x180015c38  pop     rbx
0x180015c39  retn
```
