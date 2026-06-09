# CAdvanced::Apply(void)

- ea: `0x180008cc0`
- end: `0x180008d96`
- name: `?Apply@CAdvanced@@QEAAXXZ`
- size: `214`
- prototype: `void __fastcall(CAdvanced *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180009730`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x180007f3c`
- `0x1800082c4`
- `0x180008cc0`
- `0x18000a8bc`
- `0x18000aa78`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180008d6b`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180008d6b`

## pseudocode

```c
void __fastcall CAdvanced::Apply(CAdvanced *this)
{
  __int64 *v1; // rbx
  int v3; // ebp
  __int64 v4; // rdi
  struct _SP_DEVINFO_DATA *v5; // rdx
  void *v6; // rcx
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-288h] BYREF

  v1 = (__int64 *)*((_QWORD *)this + 13);
  v3 = 0;
  while ( v1 != *((__int64 **)this + 14) )
  {
    v4 = *v1;
    if ( *(_DWORD *)(*v1 + 260) )
    {
      *(_DWORD *)(v4 + 260) = 0;
      v3 = 1;
      CValue::Copy((CValue *)(v4 + 40), (struct CValue *)v4);
      CValue::FSaveToRegistry((CValue *)v4, *(HKEY *)(v4 + 208), *(LPCWSTR *)(v4 + 216));
    }
    ++v1;
  }
  if ( v3 )
  {
    memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
    HrSetupDiGetDeviceInstallParams(*((HDEVINFO *)this + 11), *((PSP_DEVINFO_DATA *)this + 12), &DeviceInstallParams);
    v5 = (struct _SP_DEVINFO_DATA *)*((_QWORD *)this + 12);
    v6 = (void *)*((_QWORD *)this + 11);
    DeviceInstallParams.FlagsEx |= 0x400u;
    if ( !SetupDiSetDeviceInstallParamsW(v6, v5, &DeviceInstallParams) )
      HrFromLastWin32Error();
  }
}

```

## disassembly

```asm
0x180008cc0  push    rbx
0x180008cc2  push    rbp
0x180008cc3  push    rsi
0x180008cc4  push    rdi
0x180008cc5  sub     rsp, 288h
0x180008ccc  mov     rax, cs:__security_cookie
0x180008cd3  xor     rax, rsp
0x180008cd6  mov     [rsp+2A8h+var_38], rax
0x180008cde  mov     rbx, [rcx+68h]
0x180008ce2  mov     rsi, rcx
0x180008ce5  xor     ebp, ebp
0x180008ce7  cmp     rbx, [rsi+70h]
0x180008ceb  jz      short loc_180008D30
0x180008ced  mov     rdi, [rbx]
0x180008cf0  cmp     dword ptr [rdi+104h], 0
0x180008cf7  jz      short loc_180008D2A
0x180008cf9  lea     rcx, [rdi+28h]; this
0x180008cfd  mov     dword ptr [rdi+104h], 0
0x180008d07  mov     rdx, rdi; struct CValue *
0x180008d0a  mov     ebp, 1
0x180008d0f  call    ?Copy@CValue@@QEAAXPEAV1@@Z; CValue::Copy(CValue *)
0x180008d14  mov     r8, [rdi+0D8h]; lpValueName
0x180008d1b  mov     rcx, rdi; this
0x180008d1e  mov     rdx, [rdi+0D0h]; hKey
0x180008d25  call    ?FSaveToRegistry@CValue@@QEAAHPEAUHKEY__@@PEBG@Z; CValue::FSaveToRegistry(HKEY__ *,ushort const *)
0x180008d2a  add     rbx, 8
0x180008d2e  jmp     short loc_180008CE7
0x180008d30  test    ebp, ebp
0x180008d32  jz      short loc_180008D7A
0x180008d34  xor     edx, edx; Val
0x180008d36  lea     rcx, [rsp+2A8h+DeviceInstallParams]; void *
0x180008d3b  mov     r8d, 248h; Size
0x180008d41  call    memset_0
0x180008d46  mov     rdx, [rsi+60h]; DeviceInfoData
0x180008d4a  lea     r8, [rsp+2A8h+DeviceInstallParams]; DeviceInstallParams
0x180008d4f  mov     rcx, [rsi+58h]; DeviceInfoSet
0x180008d53  call    ?HrSetupDiGetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; HrSetupDiGetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W *)
0x180008d58  mov     rdx, [rsi+60h]; DeviceInfoData
0x180008d5c  lea     r8, [rsp+2A8h+DeviceInstallParams]; DeviceInstallParams
0x180008d61  mov     rcx, [rsi+58h]; DeviceInfoSet
0x180008d65  bts     [rsp+2A8h+DeviceInstallParams.FlagsEx], 0Ah
0x180008d6b  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180008d71  test    eax, eax
0x180008d73  jnz     short loc_180008D7A
0x180008d75  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180008d7a  mov     rcx, [rsp+2A8h+var_38]
0x180008d82  xor     rcx, rsp; StackCookie
0x180008d85  call    __security_check_cookie
0x180008d8a  add     rsp, 288h
0x180008d91  pop     rdi
0x180008d92  pop     rsi
0x180008d93  pop     rbp
0x180008d94  pop     rbx
0x180008d95  retn
```
