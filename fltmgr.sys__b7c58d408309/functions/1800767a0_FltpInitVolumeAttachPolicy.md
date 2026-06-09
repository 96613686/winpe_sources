# FltpInitVolumeAttachPolicy

- ea: `0x1800767a0`
- end: `0x1800768ad`
- name: `FltpInitVolumeAttachPolicy`
- size: `269`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180070c80`

## callees

- `0x180009f20`
- `0x18001f790`
- `0x180020580`
- `0x1800767a0`
- `0x1800768c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18007682d`
- `ntoskrnl!ZwClose` at `0x18007682d`
- `ntoskrnl!FsRtlOpenFileSystemRegistryKeyFromFsGuid` at `0x1800767db`
- `ntoskrnl!FsRtlOpenFileSystemRegistryKeyFromFsGuid` at `0x1800767db`

## pseudocode

```c
__int64 __fastcall FltpInitVolumeAttachPolicy(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rbp
  int v4; // edi
  __int64 result; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  HANDLE Handle; // [rsp+80h] [rbp+8h] BYREF

  v1 = a1 + 2152;
  Handle = 0;
  v2 = a1 + 2136;
  v4 = FsRtlOpenFileSystemRegistryKeyFromFsGuid(a1 + 2136, a1 + 2152, 131097, 0, &Handle);
  if ( (int)FltpDbgStatus(v4) >= 0 )
  {
    FltiAttachPolicyInit((__int64)Handle, (_DWORD *)(a1 + 2168));
    FltpLogEventInitAttachPolicy(a1);
  }
  if ( Handle )
    ZwClose(Handle);
  result = FltpDbgStatus(v4);
  if ( (int)result < 0 && (Microsoft_Windows_FilterManagerEnableBits & 4) != 0 )
    return McTemplateK0hzr0jjhzr4d_EtwWriteTransfer(
             *(_WORD *)(a1 + 176) >> 1,
             v6,
             v7,
             *(_WORD *)(a1 + 144) >> 1,
             *(_QWORD *)(a1 + 152),
             v2,
             v1,
             *(_WORD *)(a1 + 176) >> 1,
             *(_QWORD *)(a1 + 184),
             v4);
  return result;
}

```

## disassembly

```asm
0x1800767a0  mov     r11, rsp
0x1800767a3  push    rbx
0x1800767a4  push    rbp
0x1800767a5  push    rsi
0x1800767a6  push    rdi
0x1800767a7  sub     rsp, 58h
0x1800767ab  lea     rsi, [rcx+868h]
0x1800767b2  mov     qword ptr [r11+8], 0
0x1800767ba  lea     rbp, [rcx+858h]
0x1800767c1  mov     rbx, rcx
0x1800767c4  lea     rax, [r11+8]
0x1800767c8  mov     rdx, rsi
0x1800767cb  mov     rcx, rbp
0x1800767ce  mov     [r11-58h], rax
0x1800767d2  xor     r9d, r9d
0x1800767d5  mov     r8d, 20019h
0x1800767db  call    cs:__imp_FsRtlOpenFileSystemRegistryKeyFromFsGuid
0x1800767e2  nop     dword ptr [rax+rax+00h]
0x1800767e7  mov     r8d, 0CBEh
0x1800767ed  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x1800767f4  mov     ecx, eax
0x1800767f6  xor     r9d, r9d
0x1800767f9  mov     edi, eax
0x1800767fb  call    FltpDbgStatus
0x180076800  test    eax, eax
0x180076802  js      short loc_180076820
0x180076804  mov     rcx, [rsp+78h+Handle]
0x18007680c  lea     rdx, [rbx+878h]
0x180076813  call    FltiAttachPolicyInit
0x180076818  mov     rcx, rbx
0x18007681b  call    FltpLogEventInitAttachPolicy
0x180076820  mov     rcx, [rsp+78h+Handle]; Handle
0x180076828  test    rcx, rcx
0x18007682b  jz      short loc_180076839
0x18007682d  call    cs:__imp_ZwClose
0x180076834  nop     dword ptr [rax+rax+00h]
0x180076839  mov     r8d, 0CCDh
0x18007683f  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x180076846  xor     r9d, r9d
0x180076849  mov     ecx, edi
0x18007684b  call    FltpDbgStatus
0x180076850  test    eax, eax
0x180076852  jns     short loc_1800768A3
0x180076854  test    cs:Microsoft_Windows_FilterManagerEnableBits, 4
0x18007685b  jz      short loc_1800768A3
0x18007685d  mov     rax, [rbx+0B8h]
0x180076864  movzx   ecx, word ptr [rbx+0B0h]
0x18007686b  movzx   r9d, word ptr [rbx+90h]
0x180076873  mov     [rsp+78h+var_30], edi
0x180076877  mov     [rsp+78h+var_38], rax
0x18007687c  mov     rax, [rbx+98h]
0x180076883  shr     cx, 1
0x180076886  mov     [rsp+78h+var_40], cx
0x18007688b  mov     [rsp+78h+var_48], rsi
0x180076890  mov     [rsp+78h+var_50], rbp
0x180076895  shr     r9w, 1
0x180076899  mov     [rsp+78h+var_58], rax
0x18007689e  call    McTemplateK0hzr0jjhzr4d_EtwWriteTransfer
0x1800768a3  add     rsp, 58h
0x1800768a7  pop     rdi
0x1800768a8  pop     rsi
0x1800768a9  pop     rbp
0x1800768aa  pop     rbx
0x1800768ab  retn
```
