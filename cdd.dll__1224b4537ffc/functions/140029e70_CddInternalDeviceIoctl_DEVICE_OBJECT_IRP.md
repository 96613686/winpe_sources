# CddInternalDeviceIoctl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140029e70`
- end: `0x140029f96`
- name: `?CddInternalDeviceIoctl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `294`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140029e70`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140029f7c`
- `ntoskrnl!IofCompleteRequest` at `0x140029f7c`
- `watchdog!WdLogSingleEntry2` at `0x140029ea0`
- `watchdog!WdLogSingleEntry2` at `0x140029ea0`
- `watchdog!WdLogSingleEntry3` at `0x140029f1e`
- `watchdog!WdLogSingleEntry3` at `0x140029f1e`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140029eb6`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140029f35`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140029eb6`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140029f35`

## pseudocode

```c
__int64 __fastcall CddInternalDeviceIoctl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  DWORD LowPart; // ecx
  unsigned int v5; // edi
  _QWORD *v6; // rax
  __int64 Options; // rdx
  _QWORD *v8; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 2301959 )
  {
    Options = CurrentStackLocation->Parameters.Create.Options;
    if ( (_DWORD)Options || CurrentStackLocation->Parameters.Read.Length != 8 )
    {
      WdLogSingleEntry3(3, Options, CurrentStackLocation->Parameters.Read.Length, -1073741306);
      WdLogGlobalForLineNumber = 152;
      v8 = (_QWORD *)WdLogNewEntry5_WdWarning();
      v8[3] = gCddImageInfo;
      v8[4] = (unsigned int)dword_14003E570;
      v8[5] = 215857758;
      WdLogGlobalForLineNumber = 152;
      v5 = -1073741306;
    }
    else
    {
      v5 = 0;
      *(_QWORD *)a2->UserBuffer = DrvEnableDriver;
    }
  }
  else
  {
    v5 = -1073741808;
    WdLogSingleEntry2(3, LowPart, -1073741808);
    WdLogGlobalForLineNumber = 171;
    v6 = (_QWORD *)WdLogNewEntry5_WdWarning();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 171;
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return v5;
}

```

## disassembly

```asm
0x140029e70  mov     [rsp+arg_0], rbx
0x140029e75  push    rdi
0x140029e76  sub     rsp, 20h
0x140029e7a  mov     rax, [rdx+0B8h]
0x140029e81  mov     rbx, rdx
0x140029e84  mov     ecx, [rax+18h]
0x140029e87  cmp     ecx, 232007h
0x140029e8d  jz      short loc_140029EEE
0x140029e8f  mov     edx, ecx
0x140029e91  mov     rdi, 0FFFFFFFFC0000010h
0x140029e98  mov     r8, rdi
0x140029e9b  mov     ecx, 3
0x140029ea0  call    cs:__imp_WdLogSingleEntry2
0x140029ea7  nop     dword ptr [rax+rax+00h]
0x140029eac  mov     cs:WdLogGlobalForLineNumber, 0ABh
0x140029eb6  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140029ebd  nop     dword ptr [rax+rax+00h]
0x140029ec2  mov     rcx, rax
0x140029ec5  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140029ecc  mov     [rcx+18h], rax
0x140029ed0  mov     eax, cs:dword_14003E570
0x140029ed6  mov     [rcx+20h], rax
0x140029eda  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x140029ee2  mov     cs:WdLogGlobalForLineNumber, 0ABh
0x140029eec  jmp     short loc_140029F6C
0x140029eee  mov     edx, [rax+10h]
0x140029ef1  mov     ecx, [rax+8]
0x140029ef4  test    edx, edx
0x140029ef6  jnz     short loc_140029F0F
0x140029ef8  cmp     ecx, 8
0x140029efb  jnz     short loc_140029F0F
0x140029efd  mov     rax, [rbx+70h]
0x140029f01  lea     rcx, DrvEnableDriver
0x140029f08  xor     edi, edi
0x140029f0a  mov     [rax], rcx
0x140029f0d  jmp     short loc_140029F6C
0x140029f0f  mov     r8, rcx
0x140029f12  mov     r9, 0FFFFFFFFC0000206h
0x140029f19  mov     ecx, 3
0x140029f1e  call    cs:__imp_WdLogSingleEntry3
0x140029f25  nop     dword ptr [rax+rax+00h]
0x140029f2a  mov     edi, 98h
0x140029f2f  mov     cs:WdLogGlobalForLineNumber, edi
0x140029f35  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140029f3c  nop     dword ptr [rax+rax+00h]
0x140029f41  mov     rcx, rax
0x140029f44  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140029f4b  mov     [rcx+18h], rax
0x140029f4f  mov     eax, cs:dword_14003E570
0x140029f55  mov     [rcx+20h], rax
0x140029f59  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x140029f61  mov     cs:WdLogGlobalForLineNumber, edi
0x140029f67  mov     edi, 0C0000206h
0x140029f6c  xor     edx, edx; PriorityBoost
0x140029f6e  mov     qword ptr [rbx+38h], 0
0x140029f76  mov     rcx, rbx; Irp
0x140029f79  mov     [rbx+30h], edi
0x140029f7c  call    cs:__imp_IofCompleteRequest
0x140029f83  nop     dword ptr [rax+rax+00h]
0x140029f88  mov     rbx, [rsp+28h+arg_0]
0x140029f8d  mov     eax, edi
0x140029f8f  add     rsp, 20h
0x140029f93  pop     rdi
0x140029f94  retn
```
