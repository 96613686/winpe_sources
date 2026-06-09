# DafCreateDeviceInterfaceChallengeContext

- ea: `0x180009e20`
- end: `0x180009f9b`
- name: `DafCreateDeviceInterfaceChallengeContext`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000178c`
- `0x1800017fc`
- `0x180002f10`
- `0x180009aa0`
- `0x180009e20`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180009f2f`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180009f2f`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180009efb`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180009efb`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180009ed4`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180009ed4`

## pseudocode

```c
__int64 __fastcall DafCreateDeviceInterfaceChallengeContext(__int64 a1, struct _DAC_CLIENT_CONTEXT **a2)
{
  __int64 v2; // r8
  int ObjectProperties; // ebx
  __int64 Property; // rax

  v2 = (unsigned int)tls_index;
  if ( dword_180015A5C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180015A5C);
    if ( dword_180015A5C == -1 )
    {
      *(DEVPROPKEY *)byte_180015980 = DEVPKEY_Device_InstanceId;
      dword_180015994 = 0;
      qword_180015998 = 0;
      Init_thread_footer(&dword_180015A5C);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_303e45e916c7361cf38ffe655d6c194e_Traceguids);
  if ( a1 )
  {
    ObjectProperties = DevGetObjectProperties(1, a1, 0);
    if ( ObjectProperties >= 0 )
    {
      Property = DevFindProperty(&DEVPKEY_Device_InstanceId, 0, 0, 0, 0);
      if ( !Property
        || *(_DWORD *)(Property + 32) != 18
        || (ObjectProperties = DafCreateDeviceChallengeContext(*(_WORD **)(Property + 40), a2),
            ObjectProperties == -2147024894) )
      {
        ObjectProperties = -2140930037;
      }
    }
  }
  else
  {
    ObjectProperties = -2147024809;
  }
  DevFreeObjectProperties(0, 0, v2);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x180009e20  mov     [rsp+arg_8], rbx
0x180009e25  push    rdi
0x180009e26  sub     rsp, 40h
0x180009e2a  mov     r8d, cs:_tls_index
0x180009e31  mov     rbx, rcx
0x180009e34  mov     rax, gs:58h
0x180009e3d  mov     rdi, rdx
0x180009e40  mov     ecx, 4
0x180009e45  mov     rax, [rax+r8*8]
0x180009e49  mov     eax, [rcx+rax]
0x180009e4c  cmp     cs:dword_180015A5C, eax
0x180009e52  jg      loc_180009F42
0x180009e58  mov     [rsp+48h+arg_0], 0
0x180009e60  mov     [rsp+48h+arg_10], 0
0x180009e69  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e70  lea     rax, WPP_GLOBAL_Control
0x180009e77  cmp     rcx, rax
0x180009e7a  jz      short loc_180009E97
0x180009e7c  cmp     byte ptr [rcx+19h], 4
0x180009e80  jb      short loc_180009E97
0x180009e82  mov     rcx, [rcx+10h]
0x180009e86  lea     r8, WPP_303e45e916c7361cf38ffe655d6c194e_Traceguids
0x180009e8d  mov     edx, 0Eh
0x180009e92  call    WPP_SF_s
0x180009e97  test    rbx, rbx
0x180009e9a  jnz     short loc_180009EA6
0x180009e9c  mov     ebx, 80070057h
0x180009ea1  jmp     loc_180009F26
0x180009ea6  lea     rax, [rsp+48h+arg_10]
0x180009eab  mov     ecx, 1
0x180009eb0  mov     [rsp+48h+var_18], rax
0x180009eb5  mov     r9d, ecx
0x180009eb8  lea     rax, [rsp+48h+arg_0]
0x180009ebd  xor     r8d, r8d
0x180009ec0  mov     [rsp+48h+var_20], rax
0x180009ec5  mov     rdx, rbx
0x180009ec8  lea     rax, byte_180015980
0x180009ecf  mov     [rsp+48h+var_28], rax
0x180009ed4  call    cs:__imp_DevGetObjectProperties
0x180009eda  mov     ebx, eax
0x180009edc  test    eax, eax
0x180009ede  js      short loc_180009F26
0x180009ee0  mov     rax, [rsp+48h+arg_10]
0x180009ee5  lea     rcx, DEVPKEY_Device_InstanceId
0x180009eec  mov     r9d, [rsp+48h+arg_0]
0x180009ef1  xor     r8d, r8d
0x180009ef4  xor     edx, edx
0x180009ef6  mov     [rsp+48h+var_28], rax
0x180009efb  call    cs:__imp_DevFindProperty
0x180009f01  test    rax, rax
0x180009f04  jz      short loc_180009F21
0x180009f06  cmp     dword ptr [rax+20h], 12h
0x180009f0a  jnz     short loc_180009F21
0x180009f0c  mov     rcx, [rax+28h]
0x180009f10  mov     rdx, rdi
0x180009f13  call    DafCreateDeviceChallengeContext
0x180009f18  mov     ebx, eax
0x180009f1a  cmp     eax, 80070002h
0x180009f1f  jnz     short loc_180009F26
0x180009f21  mov     ebx, 8064000Bh
0x180009f26  mov     rdx, [rsp+48h+arg_10]
0x180009f2b  mov     ecx, [rsp+48h+arg_0]
0x180009f2f  call    cs:__imp_DevFreeObjectProperties
0x180009f35  mov     eax, ebx
0x180009f37  mov     rbx, [rsp+48h+arg_8]
0x180009f3c  add     rsp, 40h
0x180009f40  pop     rdi
0x180009f41  retn
0x180009f42  lea     rcx, dword_180015A5C
0x180009f49  call    _Init_thread_header
0x180009f4e  cmp     cs:dword_180015A5C, 0FFFFFFFFh
0x180009f55  jnz     loc_180009E58
0x180009f5b  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180009f62  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x180009f68  lea     rcx, dword_180015A5C
0x180009f6f  mov     dword ptr cs:byte_180015980+10h, eax
0x180009f75  movups  xmmword ptr cs:byte_180015980, xmm0
0x180009f7c  mov     cs:dword_180015994, 0
0x180009f86  mov     cs:qword_180015998, 0
0x180009f91  call    _Init_thread_footer
0x180009f96  jmp     loc_180009E58
```
