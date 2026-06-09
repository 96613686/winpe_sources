# DiskIoctlSetCacheInformation

- ea: `0x14000ef98`
- end: `0x14000f0ae`
- name: `DiskIoctlSetCacheInformation`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x14000ef98`
- `0x14000f750`
- `0x14000f804`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000efc0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000efc0`
- `CLASSPNP!ClassSetDeviceParameter` at `0x14000f082`
- `CLASSPNP!ClassSetDeviceParameter` at `0x14000f082`

## string_xrefs

- `0x14000f060`: `UserWriteCacheSetting`

## pseudocode

```c
__int64 __fastcall DiskIoctlSetCacheInformation(__int64 a1, __int64 a2)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *v2; // rdi
  __int64 v4; // rbp
  __int64 v6; // r14
  _DWORD *DriverData; // r15
  unsigned int v9; // ebx
  ULONG v10; // r9d

  v2 = *(struct _FUNCTIONAL_DEVICE_EXTENSION **)(a1 + 64);
  v4 = *(_QWORD *)(a2 + 184);
  v6 = *(_QWORD *)(a2 + 24);
  DriverData = v2->CommonExtension.DriverData;
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, a1, a2);
  }
  if ( *(_DWORD *)(v4 + 16) >= 0x18u )
  {
    v9 = DiskSetCacheInformation(v2, v6);
    v10 = *(_BYTE *)(v6 + 2) != 0;
    DriverData[130] = v10;
    ClassSetDeviceParameter(v2, (PWSTR)L"Disk", (PWSTR)L"UserWriteCacheSetting", v10);
    DiskLogCacheInformation(v2, v6, v9);
    return v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225476LL;
  }
}

```

## disassembly

```asm
0x14000ef98  push    rbx
0x14000ef9a  push    rbp
0x14000ef9b  push    rsi
0x14000ef9c  push    rdi
0x14000ef9d  push    r12
0x14000ef9f  push    r14
0x14000efa1  push    r15
0x14000efa3  sub     rsp, 30h
0x14000efa7  mov     rdi, [rcx+40h]
0x14000efab  mov     rbx, rdx
0x14000efae  mov     rbp, [rdx+0B8h]
0x14000efb5  mov     rsi, rcx
0x14000efb8  mov     r14, [rdx+18h]
0x14000efbc  mov     r15, [rdi+60h]
0x14000efc0  call    cs:__imp_KeGetCurrentIrql
0x14000efc7  nop     dword ptr [rax+rax+00h]
0x14000efcc  cmp     al, 2
0x14000efce  jb      short loc_14000EFDA
0x14000efd0  mov     eax, 0C0000148h
0x14000efd5  jmp     loc_14000F09E
0x14000efda  mov     rcx, cs:WPP_GLOBAL_Control
0x14000efe1  lea     r12, WPP_GLOBAL_Control
0x14000efe8  cmp     rcx, r12
0x14000efeb  jz      short loc_14000F017
0x14000efed  mov     eax, [rcx+2Ch]
0x14000eff0  test    al, 10h
0x14000eff2  jz      short loc_14000F017
0x14000eff4  cmp     byte ptr [rcx+29h], 4
0x14000eff8  jb      short loc_14000F017
0x14000effa  mov     rcx, [rcx+18h]
0x14000effe  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000f005  mov     edx, 3Dh ; '='
0x14000f00a  mov     [rsp+68h+var_48], rbx
0x14000f00f  mov     r9, rsi
0x14000f012  call    WPP_SF_qq
0x14000f017  cmp     dword ptr [rbp+10h], 18h
0x14000f01b  jnb     short loc_14000F052
0x14000f01d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f024  cmp     rcx, r12
0x14000f027  jz      short loc_14000F04B
0x14000f029  mov     eax, [rcx+2Ch]
0x14000f02c  test    al, 10h
0x14000f02e  jz      short loc_14000F04B
0x14000f030  cmp     byte ptr [rcx+29h], 2
0x14000f034  jb      short loc_14000F04B
0x14000f036  mov     rcx, [rcx+18h]
0x14000f03a  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000f041  mov     edx, 3Eh ; '>'
0x14000f046  call    WPP_SF_
0x14000f04b  mov     eax, 0C0000004h
0x14000f050  jmp     short loc_14000F09E
0x14000f052  mov     rdx, r14
0x14000f055  mov     rcx, rdi
0x14000f058  call    DiskSetCacheInformation
0x14000f05d  xor     r9d, r9d
0x14000f060  lea     r8, ParameterName; "UserWriteCacheSetting"
0x14000f067  cmp     [r14+2], r9b
0x14000f06b  lea     rdx, SubkeyName; "Disk"
0x14000f072  mov     rcx, rdi; FdoExtension
0x14000f075  mov     ebx, eax
0x14000f077  setnz   r9b; ParameterValue
0x14000f07b  mov     [r15+208h], r9d
0x14000f082  call    cs:__imp_ClassSetDeviceParameter
0x14000f089  nop     dword ptr [rax+rax+00h]
0x14000f08e  mov     r8d, ebx
0x14000f091  mov     rdx, r14
0x14000f094  mov     rcx, rdi
0x14000f097  call    DiskLogCacheInformation
0x14000f09c  mov     eax, ebx
0x14000f09e  add     rsp, 30h
0x14000f0a2  pop     r15
0x14000f0a4  pop     r14
0x14000f0a6  pop     r12
0x14000f0a8  pop     rdi
0x14000f0a9  pop     rsi
0x14000f0aa  pop     rbp
0x14000f0ab  pop     rbx
0x14000f0ac  retn
```
