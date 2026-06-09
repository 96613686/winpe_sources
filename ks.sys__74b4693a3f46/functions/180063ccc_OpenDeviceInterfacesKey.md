# OpenDeviceInterfacesKey

- ea: `0x180063ccc`
- end: `0x180063d74`
- name: `OpenDeviceInterfacesKey`
- size: `168`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034d7c`
- `0x180035fc4`
- `0x1800631ec`
- `0x180063908`

## callees

- `0x18000c630`
- `0x180063ccc`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180063d11`
- `ntoskrnl!ZwCreateKey` at `0x180063d11`

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
0x180063ccc  mov     rax, rsp
0x180063ccf  mov     [rax+8], rbx
0x180063cd3  push    rdi
0x180063cd4  sub     rsp, 70h
0x180063cd8  xor     edi, edi
0x180063cda  mov     [rax-28h], rdx
0x180063cde  mov     [rax-48h], rdi
0x180063ce2  lea     r8, [rax-38h]; ObjectAttributes
0x180063ce6  xorps   xmm0, xmm0
0x180063ce9  mov     [rax-50h], edi
0x180063cec  xor     r9d, r9d; TitleIndex
0x180063cef  mov     [rax-58h], rdi
0x180063cf3  mov     edx, 0F003Fh; DesiredAccess
0x180063cf8  mov     qword ptr [rax-38h], 30h ; '0'
0x180063d00  mov     qword ptr [rax-20h], 240h
0x180063d08  mov     [rax-30h], rdi
0x180063d0c  movdqu  xmmword ptr [rax-18h], xmm0
0x180063d11  call    cs:__imp_ZwCreateKey
0x180063d18  nop     dword ptr [rax+rax+00h]
0x180063d1d  mov     ebx, eax
0x180063d1f  test    eax, eax
0x180063d21  jns     short loc_180063D63
0x180063d23  lea     rax, WPP_RECORDER_INITIALIZED
0x180063d2a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180063d31  jz      short loc_180063D63
0x180063d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180063d3a  cmp     [rcx+48h], di
0x180063d3e  jz      short loc_180063D63
0x180063d40  mov     rcx, [rcx+40h]
0x180063d44  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063d4b  lea     r9d, [rdi+3Ch]
0x180063d4f  mov     dword ptr [rsp+78h+var_50], ebx
0x180063d53  lea     r8d, [rdi+1]
0x180063d57  mov     [rsp+78h+var_58], rax
0x180063d5c  mov     dl, 5
0x180063d5e  call    WPP_RECORDER_SF_D
0x180063d63  mov     eax, ebx
0x180063d65  mov     rbx, [rsp+78h+arg_0]
0x180063d6d  add     rsp, 70h
0x180063d71  pop     rdi
0x180063d72  retn
```
