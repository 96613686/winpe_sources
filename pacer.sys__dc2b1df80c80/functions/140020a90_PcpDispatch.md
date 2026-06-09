# PcpDispatch

- ea: `0x140020a90`
- end: `0x140020b4a`
- name: `PcpDispatch`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x14000d708`
- `0x14000d8b8`
- `0x140020a90`
- `0x140020b50`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140020b2b`
- `ntoskrnl!IofCompleteRequest` at `0x140020b2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020afc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020afc`

## pseudocode

```c
__int64 __fastcall PcpDispatch(__int64 a1, IRP *a2)
{
  __int64 CurrentStackLocation; // r9
  unsigned int v3; // esi
  unsigned int v5; // ebx
  unsigned int FileHandle; // eax
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF

  CurrentStackLocation = (__int64)a2->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  v8 = 0;
  if ( *(_BYTE *)CurrentStackLocation )
  {
    switch ( *(_BYTE *)CurrentStackLocation )
    {
      case 2:
        ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(CurrentStackLocation + 48) + 24LL), 0);
        v5 = 0;
        goto LABEL_12;
      case 0xE:
      case 0xF:
        FileHandle = PcpDispatchIoctl(a2, CurrentStackLocation, &v8);
        v3 = v8;
        break;
      case 0x12:
        FileHandle = PcpCleanupFileHandle(CurrentStackLocation);
        break;
      default:
        v5 = -1073741822;
LABEL_12:
        a2->IoStatus.Information = v3;
        a2->IoStatus.Status = v5;
        IofCompleteRequest(a2, 2);
        return v5;
    }
  }
  else
  {
    FileHandle = PcpCreateFileHandle(CurrentStackLocation);
  }
  v5 = FileHandle;
  if ( FileHandle != 259 )
    goto LABEL_12;
  return v5;
}

```

## disassembly

```asm
0x140020a90  mov     [rsp+arg_0], rbx
0x140020a95  mov     [rsp+arg_10], rsi
0x140020a9a  push    rdi
0x140020a9b  sub     rsp, 20h
0x140020a9f  mov     r9, [rdx+0B8h]
0x140020aa6  xor     esi, esi
0x140020aa8  mov     rdi, rdx
0x140020aab  mov     [rsp+28h+arg_8], esi
0x140020aaf  movzx   ecx, byte ptr [r9]
0x140020ab3  test    ecx, ecx
0x140020ab5  jz      short loc_140020B0C
0x140020ab7  sub     ecx, 2
0x140020aba  jz      short loc_140020AF2
0x140020abc  sub     ecx, 0Ch
0x140020abf  jz      short loc_140020ADC
0x140020ac1  sub     ecx, 1
0x140020ac4  jz      short loc_140020ADC
0x140020ac6  cmp     ecx, 3
0x140020ac9  jz      short loc_140020AD2
0x140020acb  mov     ebx, 0C0000002h
0x140020ad0  jmp     short loc_140020B1D
0x140020ad2  mov     rcx, r9
0x140020ad5  call    PcpCleanupFileHandle
0x140020ada  jmp     short loc_140020B14
0x140020adc  lea     r8, [rsp+28h+arg_8]
0x140020ae1  mov     rdx, r9
0x140020ae4  mov     rcx, rdi
0x140020ae7  call    PcpDispatchIoctl
0x140020aec  mov     esi, [rsp+28h+arg_8]
0x140020af0  jmp     short loc_140020B14
0x140020af2  mov     rcx, [r9+30h]
0x140020af6  xor     edx, edx; Tag
0x140020af8  mov     rcx, [rcx+18h]; P
0x140020afc  call    cs:__imp_ExFreePoolWithTag
0x140020b03  nop     dword ptr [rax+rax+00h]
0x140020b08  xor     ebx, ebx
0x140020b0a  jmp     short loc_140020B1D
0x140020b0c  mov     rcx, r9
0x140020b0f  call    PcpCreateFileHandle
0x140020b14  mov     ebx, eax
0x140020b16  cmp     eax, 103h
0x140020b1b  jz      short loc_140020B37
0x140020b1d  mov     eax, esi
0x140020b1f  mov     dl, 2; PriorityBoost
0x140020b21  mov     rcx, rdi; Irp
0x140020b24  mov     [rdi+38h], rax
0x140020b28  mov     [rdi+30h], ebx
0x140020b2b  call    cs:__imp_IofCompleteRequest
0x140020b32  nop     dword ptr [rax+rax+00h]
0x140020b37  mov     rsi, [rsp+28h+arg_10]
0x140020b3c  mov     eax, ebx
0x140020b3e  mov     rbx, [rsp+28h+arg_0]
0x140020b43  add     rsp, 20h
0x140020b47  pop     rdi
0x140020b48  retn
```
