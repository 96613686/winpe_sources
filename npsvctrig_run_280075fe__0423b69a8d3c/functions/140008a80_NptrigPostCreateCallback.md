# NptrigPostCreateCallback

- ea: `0x140008a80`
- end: `0x140008c61`
- name: `NptrigPostCreateCallback`
- size: `481`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001220`
- `0x1400017b0`
- `0x140008330`
- `0x140008a80`
- `0x14000a460`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140008b8e`
- `ntoskrnl!RtlCompareMemory` at `0x140008b8e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140008ae8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140008ae8`
- `FLTMGR!FltReleasePushLockEx` at `0x140008b5d`
- `FLTMGR!FltReleasePushLockEx` at `0x140008bb7`
- `FLTMGR!FltReleasePushLockEx` at `0x140008b5d`
- `FLTMGR!FltReleasePushLockEx` at `0x140008bb7`

## pseudocode

```c
__int64 __fastcall NptrigPostCreateCallback(PFLT_CALLBACK_DATA Data, __int64 a2, __int64 a3, int a4)
{
  __int64 v7; // rax
  _WORD *v8; // rcx
  __int64 v9; // r8
  const void *v10; // r14
  unsigned int v11; // ebp
  const void **v12; // rsi
  int v13; // eax
  __int64 v14; // rax

  if ( (a4 & 0x200001) == 0 && Data->IoStatus.Status == -1073741772 && (Data->Iopb->Parameters.Create.Options & 1) == 0 )
  {
    v14 = *(_QWORD *)(a2 + 32);
    if ( v14 )
    {
      if ( *(_WORD *)(v14 + 88) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, a3, Data);
        FltAcquirePushLockExclusiveEx(WPP_MAIN_CB.DeviceExtension, 0);
        v7 = *(_QWORD *)(a2 + 32);
        v8 = *(_WORD **)(v7 + 96);
        v9 = *(unsigned __int16 *)(v7 + 88);
        v10 = v8 + 1;
        v11 = v9 - 2;
        v12 = (const void **)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
        if ( *v8 != 92 )
        {
          v10 = *(const void **)(v7 + 96);
          v11 = *(unsigned __int16 *)(v7 + 88);
        }
        while ( v12 != (const void **)WPP_MAIN_CB.DeviceExtension + 1 )
        {
          if ( *((unsigned __int16 *)v12 + 8) == v11 && RtlCompareMemory(v10, v12[3], v11) == v11 )
          {
            v13 = NptrigHandleTriggerableIo(v12);
            if ( v13 >= 0 )
            {
              FltReleasePushLockEx(WPP_MAIN_CB.DeviceExtension, 0);
              NptrigAlterIoStatus(Data);
              return 0;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 14, (unsigned int)v13, Data, v13);
            }
LABEL_15:
            FltReleasePushLockEx(WPP_MAIN_CB.DeviceExtension, 0);
            return 0;
          }
          v12 = (const void **)*v12;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, v9, Data);
        goto LABEL_15;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140008a80  push    rbx
0x140008a82  push    rdi
0x140008a83  sub     rsp, 38h
0x140008a87  mov     rdi, rdx
0x140008a8a  mov     rbx, rcx
0x140008a8d  test    r9d, 200001h
0x140008a94  jnz     short loc_140008AA3
0x140008a96  cmp     dword ptr [rcx+18h], 0C0000034h
0x140008a9d  jz      loc_140008BD2
0x140008aa3  xor     eax, eax
0x140008aa5  add     rsp, 38h
0x140008aa9  pop     rdi
0x140008aaa  pop     rbx
0x140008aab  retn
0x140008aad  mov     [rsp+48h+arg_0], rbp
0x140008ab2  mov     [rsp+48h+arg_8], rsi
0x140008ab7  mov     [rsp+48h+arg_10], r14
0x140008abc  mov     [rsp+48h+var_18], r15
0x140008ac1  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ac8  lea     r15, WPP_GLOBAL_Control
0x140008acf  cmp     rcx, r15
0x140008ad2  jz      short loc_140008ADF
0x140008ad4  mov     eax, [rcx+2Ch]
0x140008ad7  test    al, 4
0x140008ad9  jnz     loc_140008BFF
0x140008adf  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140008ae6  xor     edx, edx
0x140008ae8  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140008aef  nop     dword ptr [rax+rax+00h]
0x140008af4  mov     rax, [rdi+20h]
0x140008af8  mov     rcx, [rax+60h]
0x140008afc  movzx   r8d, word ptr [rax+58h]
0x140008b01  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140008b08  cmp     word ptr [rcx], 5Ch ; '\'
0x140008b0c  lea     r14, [rcx+2]
0x140008b10  lea     ebp, [r8-2]
0x140008b14  mov     rsi, [rax+8]
0x140008b18  cmovnz  r14, rcx
0x140008b1c  cmovnz  ebp, r8d
0x140008b20  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140008b27  add     rax, 8
0x140008b2b  cmp     rsi, rax
0x140008b2e  jz      short loc_140008B3D
0x140008b30  movzx   eax, word ptr [rsi+10h]
0x140008b34  cmp     eax, ebp
0x140008b36  jz      short loc_140008B82
0x140008b38  mov     rsi, [rsi]
0x140008b3b  jmp     short loc_140008B20
0x140008b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b44  cmp     rcx, r15
0x140008b47  jz      short loc_140008B54
0x140008b49  mov     eax, [rcx+2Ch]
0x140008b4c  test    al, 4
0x140008b4e  jnz     loc_140008C4B
0x140008b54  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140008b5b  xor     edx, edx
0x140008b5d  call    cs:__imp_FltReleasePushLockEx
0x140008b64  nop     dword ptr [rax+rax+00h]
0x140008b69  mov     r14, [rsp+48h+arg_10]
0x140008b6e  mov     rsi, [rsp+48h+arg_8]
0x140008b73  mov     rbp, [rsp+48h+arg_0]
0x140008b78  mov     r15, [rsp+48h+var_18]
0x140008b7d  jmp     loc_140008AA3
0x140008b82  mov     rdx, [rsi+18h]; Source2
0x140008b86  mov     rcx, r14; Source1
0x140008b89  mov     r8d, ebp; Length
0x140008b8c  mov     edi, ebp
0x140008b8e  call    cs:__imp_RtlCompareMemory
0x140008b95  nop     dword ptr [rax+rax+00h]
0x140008b9a  cmp     rax, rdi
0x140008b9d  jnz     short loc_140008B38
0x140008b9f  mov     rcx, rsi
0x140008ba2  call    NptrigHandleTriggerableIo
0x140008ba7  mov     r8d, eax
0x140008baa  test    eax, eax
0x140008bac  js      short loc_140008C15
0x140008bae  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140008bb5  xor     edx, edx
0x140008bb7  call    cs:__imp_FltReleasePushLockEx
0x140008bbe  nop     dword ptr [rax+rax+00h]
0x140008bc3  mov     edx, 0C00000ACh
0x140008bc8  mov     rcx, rbx; Data
0x140008bcb  call    NptrigAlterIoStatus
0x140008bd0  jmp     short loc_140008B69
0x140008bd2  mov     rax, [rcx+10h]
0x140008bd6  mov     ecx, [rax+20h]
0x140008bd9  test    cl, 1
0x140008bdc  jnz     loc_140008AA3
0x140008be2  mov     rax, [rdx+20h]
0x140008be6  test    rax, rax
0x140008be9  jz      loc_140008AA3
0x140008bef  cmp     word ptr [rax+58h], 0
0x140008bf4  jz      loc_140008AA3
0x140008bfa  jmp     loc_140008AAD
0x140008bff  mov     rcx, [rcx+18h]
0x140008c03  mov     edx, 0Ch
0x140008c08  mov     r9, rbx
0x140008c0b  call    WPP_SF_q
0x140008c10  jmp     loc_140008ADF
0x140008c15  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c1c  cmp     rcx, r15
0x140008c1f  jz      loc_140008B54
0x140008c25  mov     eax, [rcx+2Ch]
0x140008c28  test    al, 1
0x140008c2a  jz      loc_140008B54
0x140008c30  mov     rcx, [rcx+18h]
0x140008c34  mov     edx, 0Eh
0x140008c39  mov     r9, rbx
0x140008c3c  mov     [rsp+48h+var_28], r8d
0x140008c41  call    WPP_SF_qd
0x140008c46  jmp     loc_140008B54
0x140008c4b  mov     rcx, [rcx+18h]
0x140008c4f  mov     edx, 0Dh
0x140008c54  mov     r9, rbx
0x140008c57  call    WPP_SF_q
0x140008c5c  jmp     loc_140008B54
```
