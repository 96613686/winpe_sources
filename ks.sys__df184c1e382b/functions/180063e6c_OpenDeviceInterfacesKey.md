# OpenDeviceInterfacesKey

- ea: `0x180063e6c`
- end: `0x180063f14`
- name: `OpenDeviceInterfacesKey`
- size: `168`
- prototype: `__int64 __fastcall(void **, UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034e8c`
- `0x1800360d4`
- `0x18006338c`
- `0x180063aa8`

## callees

- `0x18000c630`
- `0x180063e6c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180063eb1`
- `ntoskrnl!ZwCreateKey` at `0x180063eb1`

## pseudocode

```c
__int64 __fastcall OpenDeviceInterfacesKey(void **a1, UNICODE_STRING *a2)
{
  int v2; // edx
  NTSTATUS v3; // ebx
  __int64 v5; // [rsp+28h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES v6; // [rsp+40h] [rbp-38h] BYREF

  v6.ObjectName = a2;
  *(_QWORD *)&v6.Length = 48;
  *(_QWORD *)&v6.Attributes = 576;
  v6.RootDirectory = 0;
  *(_OWORD *)&v6.SecurityDescriptor = 0;
  v3 = ZwCreateKey(a1, 0xF003Fu, &v6, 0, 0, 0, 0);
  if ( v3 < 0
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v5) = v3;
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      1,
      60,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
      v5);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180063e6c  mov     rax, rsp
0x180063e6f  mov     [rax+8], rbx
0x180063e73  push    rdi
0x180063e74  sub     rsp, 70h
0x180063e78  xor     edi, edi
0x180063e7a  mov     [rax-28h], rdx
0x180063e7e  mov     [rax-48h], rdi
0x180063e82  lea     r8, [rax-38h]; ObjectAttributes
0x180063e86  xorps   xmm0, xmm0
0x180063e89  mov     [rax-50h], edi
0x180063e8c  xor     r9d, r9d; TitleIndex
0x180063e8f  mov     [rax-58h], rdi
0x180063e93  mov     edx, 0F003Fh; DesiredAccess
0x180063e98  mov     qword ptr [rax-38h], 30h ; '0'
0x180063ea0  mov     qword ptr [rax-20h], 240h
0x180063ea8  mov     [rax-30h], rdi
0x180063eac  movdqu  xmmword ptr [rax-18h], xmm0
0x180063eb1  call    cs:__imp_ZwCreateKey
0x180063eb8  nop     dword ptr [rax+rax+00h]
0x180063ebd  mov     ebx, eax
0x180063ebf  test    eax, eax
0x180063ec1  jns     short loc_180063F03
0x180063ec3  lea     rax, WPP_RECORDER_INITIALIZED
0x180063eca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180063ed1  jz      short loc_180063F03
0x180063ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180063eda  cmp     [rcx+48h], di
0x180063ede  jz      short loc_180063F03
0x180063ee0  mov     rcx, [rcx+40h]
0x180063ee4  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063eeb  lea     r9d, [rdi+3Ch]
0x180063eef  mov     dword ptr [rsp+78h+var_50], ebx
0x180063ef3  lea     r8d, [rdi+1]
0x180063ef7  mov     [rsp+78h+var_58], rax
0x180063efc  mov     dl, 5
0x180063efe  call    WPP_RECORDER_SF_D
0x180063f03  mov     eax, ebx
0x180063f05  mov     rbx, [rsp+78h+arg_0]
0x180063f0d  add     rsp, 70h
0x180063f11  pop     rdi
0x180063f12  retn
```
