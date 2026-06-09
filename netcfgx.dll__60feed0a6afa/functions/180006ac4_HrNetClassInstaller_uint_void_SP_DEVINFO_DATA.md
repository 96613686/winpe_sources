# _HrNetClassInstaller(uint,void *,_SP_DEVINFO_DATA *)

- ea: `0x180006ac4`
- end: `0x180006cf8`
- name: `?_HrNetClassInstaller@@YAJIPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(int, void *, struct _SP_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x1800066b0`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x1800068e4`
- `0x180006a2c`
- `0x180006ac4`
- `0x180006ecc`
- `0x180007f3c`
- `0x1800083e8`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180006c6c`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180006c6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _HrNetClassInstaller(int a1, void *a2, struct _SP_DEVINFO_DATA *a3)
{
  unsigned int FixedSizeClassInstallParams; // edi
  __int64 v6; // rdi
  const unsigned __int16 *String; // rax
  __int64 v8; // rdx
  char *v9; // rcx
  char *v10; // rax
  _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+20h] [rbp-438h] BYREF
  char v13; // [rsp+28h] [rbp-430h] BYREF

  FixedSizeClassInstallParams = -2146500082;
  switch ( a1 )
  {
    case 25:
      if ( a3
        && (*(_QWORD *)&GUID_DEVCLASS_NET.Data1 == *(_QWORD *)&a3->ClassGuid.Data1
         && *(_QWORD *)GUID_DEVCLASS_NET.Data4 == *(_QWORD *)a3->ClassGuid.Data4
         || *(_QWORD *)&GUID_DEVCLASS_INFRARED.Data1 == *(_QWORD *)&a3->ClassGuid.Data1
         && *(_QWORD *)GUID_DEVCLASS_INFRARED.Data4 == *(_QWORD *)a3->ClassGuid.Data4
         || *(_QWORD *)&GUID_DEVCLASS_NETTRANS.Data1 == *(_QWORD *)&a3->ClassGuid.Data1
         && *(_QWORD *)GUID_DEVCLASS_NETTRANS.Data4 == *(_QWORD *)a3->ClassGuid.Data4
         || *(_QWORD *)&GUID_DEVCLASS_NETCLIENT.Data1 == *(_QWORD *)&a3->ClassGuid.Data1
         && *(_QWORD *)GUID_DEVCLASS_NETCLIENT.Data4 == *(_QWORD *)a3->ClassGuid.Data4
         || *(_QWORD *)&GUID_DEVCLASS_NETSERVICE.Data1 == *(_QWORD *)&a3->ClassGuid.Data1
         && *(_QWORD *)GUID_DEVCLASS_NETSERVICE.Data4 == *(_QWORD *)a3->ClassGuid.Data4)
        && (*(_QWORD *)&GUID_DEVCLASS_NET.Data1 != *(_QWORD *)&a3->ClassGuid.Data1
         || *(_QWORD *)GUID_DEVCLASS_NET.Data4 != *(_QWORD *)a3->ClassGuid.Data4)
        && (*(_QWORD *)&GUID_DEVCLASS_INFRARED.Data1 != *(_QWORD *)&a3->ClassGuid.Data1
         || *(_QWORD *)GUID_DEVCLASS_INFRARED.Data4 != *(_QWORD *)a3->ClassGuid.Data4) )
      {
        return 0;
      }
      break;
    case 1:
      HrCiPrepareSelectDeviceDialog(a2, a3);
      break;
    case 39:
      memset_0(&ClassInstallParams, 0, 0x408u);
      FixedSizeClassInstallParams = HrSetupDiGetFixedSizeClassInstallParams(a2, a3, &ClassInstallParams, 1032);
      if ( !FixedSizeClassInstallParams )
      {
        v6 = 2147483646;
        String = SzLoadString(hModule, 0x36C8u);
        v8 = 512;
        v9 = &v13;
        do
        {
          if ( !v6 )
            break;
          if ( !*String )
            break;
          *(_WORD *)v9 = *String++;
          v9 += 2;
          --v6;
          --v8;
        }
        while ( v8 );
        v10 = v9 - 2;
        if ( v8 )
          v10 = v9;
        FixedSizeClassInstallParams = 0;
        *(_WORD *)v10 = 0;
        if ( !SetupDiSetClassInstallParamsW(a2, a3, &ClassInstallParams, 0x408u) )
        {
          FixedSizeClassInstallParams = HrFromLastWin32Error();
          if ( (FixedSizeClassInstallParams & 0x80000000) != 0 )
            return (unsigned int)-2146500082;
        }
        if ( !FixedSizeClassInstallParams )
          return FixedSizeClassInstallParams;
      }
      if ( FixedSizeClassInstallParams != -2146500082
        && FixedSizeClassInstallParams != -2147023673
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_4f46983905763d4bb11ae9f3e50cb4bc_Traceguids,
          FixedSizeClassInstallParams);
      }
      break;
  }
  return FixedSizeClassInstallParams;
}

```

## disassembly

```asm
0x180006ac4  mov     [rsp+arg_0], rbx
0x180006ac9  push    rbp
0x180006aca  push    rsi
0x180006acb  push    rdi
0x180006acc  sub     rsp, 440h
0x180006ad3  mov     rax, cs:__security_cookie
0x180006ada  xor     rax, rsp
0x180006add  mov     [rsp+458h+var_28], rax
0x180006ae5  mov     rbx, r8
0x180006ae8  mov     rbp, rdx
0x180006aeb  mov     edi, 800F020Eh
0x180006af0  cmp     ecx, 19h
0x180006af3  jnz     loc_180006BB5
0x180006af9  xor     esi, esi
0x180006afb  test    rbx, rbx
0x180006afe  jz      loc_180006CD3
0x180006b04  mov     r9, qword ptr cs:GUID_DEVCLASS_NET.Data1
0x180006b0b  mov     rcx, qword ptr cs:GUID_DEVCLASS_INFRARED.Data4
0x180006b12  mov     rdx, qword ptr cs:GUID_DEVCLASS_INFRARED.Data1
0x180006b19  mov     r8, qword ptr cs:GUID_DEVCLASS_NET.Data4
0x180006b20  cmp     r9, [rbx+4]
0x180006b24  jnz     short loc_180006B2C
0x180006b26  cmp     r8, [rbx+0Ch]
0x180006b2a  jz      short loc_180006B8E
0x180006b2c  cmp     rdx, [rbx+4]
0x180006b30  jnz     short loc_180006B38
0x180006b32  cmp     rcx, [rbx+0Ch]
0x180006b36  jz      short loc_180006B8E
0x180006b38  mov     rax, qword ptr cs:GUID_DEVCLASS_NETTRANS.Data1
0x180006b3f  cmp     rax, [rbx+4]
0x180006b43  jnz     short loc_180006B52
0x180006b45  mov     rax, qword ptr cs:GUID_DEVCLASS_NETTRANS.Data4
0x180006b4c  cmp     rax, [rbx+0Ch]
0x180006b50  jz      short loc_180006B8E
0x180006b52  mov     rax, qword ptr cs:GUID_DEVCLASS_NETCLIENT.Data1
0x180006b59  cmp     rax, [rbx+4]
0x180006b5d  jnz     short loc_180006B6C
0x180006b5f  mov     rax, qword ptr cs:GUID_DEVCLASS_NETCLIENT.Data4
0x180006b66  cmp     rax, [rbx+0Ch]
0x180006b6a  jz      short loc_180006B8E
0x180006b6c  mov     rax, qword ptr cs:GUID_DEVCLASS_NETSERVICE.Data1
0x180006b73  cmp     rax, [rbx+4]
0x180006b77  jnz     loc_180006CD3
0x180006b7d  mov     rax, qword ptr cs:GUID_DEVCLASS_NETSERVICE.Data4
0x180006b84  cmp     rax, [rbx+0Ch]
0x180006b88  jnz     loc_180006CD3
0x180006b8e  cmp     r9, [rbx+4]
0x180006b92  jnz     short loc_180006B9E
0x180006b94  cmp     r8, [rbx+0Ch]
0x180006b98  jz      loc_180006CD3
0x180006b9e  cmp     rdx, [rbx+4]
0x180006ba2  jnz     short loc_180006BAE
0x180006ba4  cmp     rcx, [rbx+0Ch]
0x180006ba8  jz      loc_180006CD3
0x180006bae  mov     edi, esi
0x180006bb0  jmp     loc_180006CD3
0x180006bb5  cmp     ecx, 1
0x180006bb8  jnz     short loc_180006BCA
0x180006bba  mov     rdx, rbx; DeviceInfoData
0x180006bbd  mov     rcx, rbp; void *
0x180006bc0  call    ?HrCiPrepareSelectDeviceDialog@@YAJPEAXPEAU_SP_DEVINFO_DATA@@@Z; HrCiPrepareSelectDeviceDialog(void *,_SP_DEVINFO_DATA *)
0x180006bc5  jmp     loc_180006CD3
0x180006bca  cmp     ecx, 27h ; '''
0x180006bcd  jnz     loc_180006CD3
0x180006bd3  xor     edx, edx; Val
0x180006bd5  lea     rcx, [rsp+458h+ClassInstallParams]; void *
0x180006bda  mov     r8d, 408h; Size
0x180006be0  call    memset_0
0x180006be5  mov     r9d, 408h; int
0x180006beb  lea     r8, [rsp+458h+ClassInstallParams]; ClassInstallParams
0x180006bf0  mov     rdx, rbx; DeviceInfoData
0x180006bf3  mov     rcx, rbp; DeviceInfoSet
0x180006bf6  call    ?HrSetupDiGetFixedSizeClassInstallParams@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_CLASSINSTALL_HEADER@@H@Z; HrSetupDiGetFixedSizeClassInstallParams(void *,_SP_DEVINFO_DATA *,_SP_CLASSINSTALL_HEADER *,int)
0x180006bfb  xor     esi, esi
0x180006bfd  mov     edi, eax
0x180006bff  test    eax, eax
0x180006c01  jnz     loc_180006C8C
0x180006c07  mov     rcx, cs:hModule; hModule
0x180006c0e  mov     edx, 36C8h; unsigned int
0x180006c13  mov     edi, 7FFFFFFEh
0x180006c18  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x180006c1d  mov     edx, 200h
0x180006c22  lea     rcx, [rsp+458h+var_430]
0x180006c27  test    rdi, rdi
0x180006c2a  jz      short loc_180006C4B
0x180006c2c  movzx   r8d, word ptr [rax]
0x180006c30  test    r8w, r8w
0x180006c34  jz      short loc_180006C4B
0x180006c36  mov     [rcx], r8w
0x180006c3a  add     rax, 2
0x180006c3e  add     rcx, 2
0x180006c42  dec     rdi
0x180006c45  sub     rdx, 1
0x180006c49  jnz     short loc_180006C27
0x180006c4b  test    rdx, rdx
0x180006c4e  lea     rax, [rcx-2]
0x180006c52  mov     r9d, 408h; ClassInstallParamsSize
0x180006c58  lea     r8, [rsp+458h+ClassInstallParams]; ClassInstallParams
0x180006c5d  cmovnz  rax, rcx
0x180006c61  mov     rdx, rbx; DeviceInfoData
0x180006c64  mov     rcx, rbp; DeviceInfoSet
0x180006c67  mov     edi, esi
0x180006c69  mov     [rax], si
0x180006c6c  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180006c72  test    eax, eax
0x180006c74  jnz     short loc_180006C88
0x180006c76  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006c7b  mov     edi, eax
0x180006c7d  test    eax, eax
0x180006c7f  jns     short loc_180006C88
0x180006c81  mov     edi, 800F020Eh
0x180006c86  jmp     short loc_180006CD3
0x180006c88  test    edi, edi
0x180006c8a  jz      short loc_180006CD3
0x180006c8c  cmp     edi, 800F020Eh
0x180006c92  jz      short loc_180006CD3
0x180006c94  cmp     edi, 800704C7h
0x180006c9a  jz      short loc_180006CD3
0x180006c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ca3  lea     rax, WPP_GLOBAL_Control
0x180006caa  cmp     rcx, rax
0x180006cad  jz      short loc_180006CD3
0x180006caf  cmp     byte ptr [rcx+19h], 2
0x180006cb3  jb      short loc_180006CD3
0x180006cb5  test    byte ptr [rcx+1Ch], 10h
0x180006cb9  jz      short loc_180006CD3
0x180006cbb  mov     rcx, [rcx+10h]
0x180006cbf  lea     r8, WPP_4f46983905763d4bb11ae9f3e50cb4bc_Traceguids
0x180006cc6  mov     edx, 0Ah
0x180006ccb  mov     r9d, edi
0x180006cce  call    WPP_SF_d
0x180006cd3  mov     eax, edi
0x180006cd5  mov     rcx, [rsp+458h+var_28]
0x180006cdd  xor     rcx, rsp; StackCookie
0x180006ce0  call    __security_check_cookie
0x180006ce5  mov     rbx, [rsp+458h+arg_0]
0x180006ced  add     rsp, 440h
0x180006cf4  pop     rdi
0x180006cf5  pop     rsi
0x180006cf6  pop     rbp
0x180006cf7  retn
```
