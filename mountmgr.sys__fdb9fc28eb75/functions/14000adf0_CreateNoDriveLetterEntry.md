# CreateNoDriveLetterEntry

- ea: `0x14000adf0`
- end: `0x14000afac`
- name: `CreateNoDriveLetterEntry`
- size: `444`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000acd8`
- `0x14000c528`
- `0x14000fcc0`
- `0x140018560`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002d70`
- `0x140002f80`
- `0x14000adf0`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x14000af76`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000af76`
- `ntoskrnl!ExAllocatePool2` at `0x14000aec2`
- `ntoskrnl!ExAllocatePool2` at `0x14000aec2`
- `ntoskrnl!RtlStringFromGUID` at `0x14000ae74`
- `ntoskrnl!RtlStringFromGUID` at `0x14000ae74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aedd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aedd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af87`
- `ntoskrnl!ExUuidCreate` at `0x14000ae21`
- `ntoskrnl!ExUuidCreate` at `0x14000ae21`

## string_xrefs

- `0x14000af5f`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
void __fastcall CreateNoDriveLetterEntry(unsigned __int16 *a1)
{
  NTSTATUS v2; // eax
  __int64 v3; // r8
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  WCHAR *Pool2; // rax
  WCHAR *v7; // rbx
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-28h] BYREF

  Uuid = 0;
  GuidString = 0;
  v2 = ExUuidCreate(&Uuid);
  if ( v2 >= 0 )
  {
    v2 = RtlStringFromGUID(&Uuid, &GuidString);
    if ( v2 >= 0 )
    {
      Pool2 = (WCHAR *)ExAllocatePool2(258, GuidString.Length + 4LL, 1098149453);
      v7 = Pool2;
      if ( Pool2 )
      {
        *Pool2 = 35;
        memmove(Pool2 + 1, GuidString.Buffer, GuidString.Length);
        v7[((unsigned __int64)GuidString.Length >> 1) + 1] = 0;
        ExFreePoolWithTag(GuidString.Buffer, 0);
        RtlWriteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", v7, 3u, a1 + 1, *a1);
        ExFreePoolWithTag(v7, 0);
      }
      else
      {
        ExFreePoolWithTag(GuidString.Buffer, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84);
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v5 = 83;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v5 = 82;
LABEL_5:
      WPP_SF_L(v4->AttachedDevice, v5, v3, (unsigned int)v2);
    }
  }
}

```

## disassembly

```asm
0x14000adf0  mov     [rsp+arg_8], rbx
0x14000adf5  push    rdi
0x14000adf6  sub     rsp, 60h
0x14000adfa  mov     rax, cs:__security_cookie
0x14000ae01  xor     rax, rsp
0x14000ae04  mov     [rsp+68h+var_18], rax
0x14000ae09  mov     rdi, rcx
0x14000ae0c  xorps   xmm0, xmm0
0x14000ae0f  xorps   xmm1, xmm1
0x14000ae12  lea     rcx, [rsp+68h+Uuid]; Uuid
0x14000ae17  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x14000ae1c  movups  xmmword ptr [rsp+68h+GuidString.Length], xmm1
0x14000ae21  call    cs:__imp_ExUuidCreate
0x14000ae28  nop     dword ptr [rax+rax+00h]
0x14000ae2d  test    eax, eax
0x14000ae2f  jns     short loc_14000AE6A
0x14000ae31  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae38  lea     rdx, WPP_GLOBAL_Control
0x14000ae3f  cmp     rcx, rdx
0x14000ae42  jz      loc_14000AF93
0x14000ae48  mov     edx, [rcx+2Ch]
0x14000ae4b  test    dl, 1
0x14000ae4e  jz      loc_14000AF93
0x14000ae54  mov     edx, 52h ; 'R'
0x14000ae59  mov     rcx, [rcx+18h]
0x14000ae5d  mov     r9d, eax
0x14000ae60  call    WPP_SF_L
0x14000ae65  jmp     loc_14000AF93
0x14000ae6a  lea     rdx, [rsp+68h+GuidString]; GuidString
0x14000ae6f  lea     rcx, [rsp+68h+Uuid]; Guid
0x14000ae74  call    cs:__imp_RtlStringFromGUID
0x14000ae7b  nop     dword ptr [rax+rax+00h]
0x14000ae80  test    eax, eax
0x14000ae82  jns     short loc_14000AEAE
0x14000ae84  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae8b  lea     rdx, WPP_GLOBAL_Control
0x14000ae92  cmp     rcx, rdx
0x14000ae95  jz      loc_14000AF93
0x14000ae9b  mov     edx, [rcx+2Ch]
0x14000ae9e  test    dl, 1
0x14000aea1  jz      loc_14000AF93
0x14000aea7  mov     edx, 53h ; 'S'
0x14000aeac  jmp     short loc_14000AE59
0x14000aeae  movzx   edx, [rsp+68h+GuidString.Length]
0x14000aeb3  mov     ecx, 102h
0x14000aeb8  add     rdx, 4
0x14000aebc  mov     r8d, 41746E4Dh
0x14000aec2  call    cs:__imp_ExAllocatePool2
0x14000aec9  nop     dword ptr [rax+rax+00h]
0x14000aece  mov     rbx, rax
0x14000aed1  test    rax, rax
0x14000aed4  jnz     short loc_14000AF19
0x14000aed6  mov     rcx, [rsp+68h+GuidString.Buffer]; P
0x14000aedb  xor     edx, edx; Tag
0x14000aedd  call    cs:__imp_ExFreePoolWithTag
0x14000aee4  nop     dword ptr [rax+rax+00h]
0x14000aee9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aef0  lea     rdx, WPP_GLOBAL_Control
0x14000aef7  cmp     rcx, rdx
0x14000aefa  jz      loc_14000AF93
0x14000af00  mov     eax, [rcx+2Ch]
0x14000af03  test    al, 4
0x14000af05  jz      loc_14000AF93
0x14000af0b  mov     rcx, [rcx+18h]
0x14000af0f  lea     edx, [rbx+54h]
0x14000af12  call    WPP_SF_
0x14000af17  jmp     short loc_14000AF93
0x14000af19  mov     word ptr [rax], 23h ; '#'
0x14000af1e  lea     rcx, [rax+2]; void *
0x14000af22  movzx   r8d, [rsp+68h+GuidString.Length]; Size
0x14000af28  mov     rdx, [rsp+68h+GuidString.Buffer]; Src
0x14000af2d  call    memmove
0x14000af32  movzx   ecx, [rsp+68h+GuidString.Length]
0x14000af37  xor     eax, eax
0x14000af39  shr     rcx, 1
0x14000af3c  xor     edx, edx; Tag
0x14000af3e  mov     [rbx+rcx*2+2], ax
0x14000af43  mov     rcx, [rsp+68h+GuidString.Buffer]; P
0x14000af48  call    cs:__imp_ExFreePoolWithTag
0x14000af4f  nop     dword ptr [rax+rax+00h]
0x14000af54  movzx   eax, word ptr [rdi]
0x14000af57  lea     rcx, [rdi+2]
0x14000af5b  mov     [rsp+68h+ValueLength], eax; ValueLength
0x14000af5f  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000af66  mov     [rsp+68h+ValueData], rcx; ValueData
0x14000af6b  mov     r9d, 3; ValueType
0x14000af71  xor     ecx, ecx; RelativeTo
0x14000af73  mov     r8, rbx; ValueName
0x14000af76  call    cs:__imp_RtlWriteRegistryValue
0x14000af7d  nop     dword ptr [rax+rax+00h]
0x14000af82  xor     edx, edx; Tag
0x14000af84  mov     rcx, rbx; P
0x14000af87  call    cs:__imp_ExFreePoolWithTag
0x14000af8e  nop     dword ptr [rax+rax+00h]
0x14000af93  mov     rcx, [rsp+68h+var_18]
0x14000af98  xor     rcx, rsp; StackCookie
0x14000af9b  call    __security_check_cookie
0x14000afa0  mov     rbx, [rsp+68h+arg_8]
0x14000afa5  add     rsp, 60h
0x14000afa9  pop     rdi
0x14000afaa  retn
```
