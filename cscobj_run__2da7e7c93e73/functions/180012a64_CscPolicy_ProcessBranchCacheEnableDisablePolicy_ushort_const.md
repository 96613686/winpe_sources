# CscPolicy_ProcessBranchCacheEnableDisablePolicy(ushort const *)

- ea: `0x180012a64`
- end: `0x180012b41`
- name: `?CscPolicy_ProcessBranchCacheEnableDisablePolicy@@YAJPEBG@Z`
- size: `221`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012120`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180012a64`
- `0x180013284`

## import_xrefs

- `CSCAPI!OfflineFilesStart` at `0x180012ace`
- `CSCAPI!OfflineFilesStart` at `0x180012ace`

## string_xrefs

- `0x180012ab5`: `SOFTWARE\Policies\Microsoft\PeerDist\Service`

## pseudocode

```c
__int64 __fastcall CscPolicy_ProcessBranchCacheEnableDisablePolicy(const unsigned __int16 *a1)
{
  int EnabledPolicy; // ebx
  unsigned int v2; // eax
  const unsigned __int16 *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids);
  LODWORD(v4) = 0;
  EnabledPolicy = CscPolicy_QueryEnabledPolicy(
                    L"SOFTWARE\\Policies\\Microsoft\\PeerDist\\Service",
                    L"Enable",
                    (int *)&v4);
  if ( EnabledPolicy >= 0 && (_DWORD)v4 )
  {
    v2 = OfflineFilesStart();
    if ( v2 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, v2);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids);
    }
  }
  else if ( (_WORD)EnabledPolicy == 2 )
  {
    return 0;
  }
  return (unsigned int)EnabledPolicy;
}

```

## disassembly

```asm
0x180012a64  mov     [rsp+arg_8], rbx
0x180012a69  mov     [rsp+arg_0], rcx
0x180012a6e  push    rdi
0x180012a6f  sub     rsp, 20h
0x180012a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a7a  lea     rdi, WPP_GLOBAL_Control
0x180012a81  cmp     rcx, rdi
0x180012a84  jz      short loc_180012AA1
0x180012a86  test    byte ptr [rcx+1Ch], 80h
0x180012a8a  jz      short loc_180012AA1
0x180012a8c  mov     rcx, [rcx+10h]
0x180012a90  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012a97  mov     edx, 21h ; '!'
0x180012a9c  call    WPP_SF_
0x180012aa1  lea     r8, [rsp+28h+arg_0]; int *
0x180012aa6  mov     dword ptr [rsp+28h+arg_0], 0
0x180012aae  lea     rdx, aEnable; "Enable"
0x180012ab5  lea     rcx, SubKey; "SOFTWARE\\Policies\\Microsoft\\PeerDist"...
0x180012abc  call    ?CscPolicy_QueryEnabledPolicy@@YAJPEBG0PEAH@Z; CscPolicy_QueryEnabledPolicy(ushort const *,ushort const *,int *)
0x180012ac1  mov     ebx, eax
0x180012ac3  test    eax, eax
0x180012ac5  js      short loc_180012B2B
0x180012ac7  cmp     dword ptr [rsp+28h+arg_0], 0
0x180012acc  jz      short loc_180012B2B
0x180012ace  call    cs:__imp_OfflineFilesStart
0x180012ad4  test    eax, eax
0x180012ad6  jnz     short loc_180012AFF
0x180012ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012adf  cmp     rcx, rdi
0x180012ae2  jz      short loc_180012B34
0x180012ae4  test    byte ptr [rcx+1Ch], 80h
0x180012ae8  jz      short loc_180012B34
0x180012aea  mov     rcx, [rcx+10h]
0x180012aee  lea     edx, [rax+22h]
0x180012af1  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012af8  call    WPP_SF_
0x180012afd  jmp     short loc_180012B34
0x180012aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b06  cmp     rcx, rdi
0x180012b09  jz      short loc_180012B34
0x180012b0b  test    byte ptr [rcx+1Ch], 2
0x180012b0f  jz      short loc_180012B34
0x180012b11  mov     rcx, [rcx+10h]
0x180012b15  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012b1c  mov     edx, 23h ; '#'
0x180012b21  mov     r9d, eax
0x180012b24  call    WPP_SF_d
0x180012b29  jmp     short loc_180012B34
0x180012b2b  xor     eax, eax
0x180012b2d  cmp     bx, 2
0x180012b31  cmovz   ebx, eax
0x180012b34  mov     eax, ebx
0x180012b36  mov     rbx, [rsp+28h+arg_8]
0x180012b3b  add     rsp, 20h
0x180012b3f  pop     rdi
0x180012b40  retn
```
