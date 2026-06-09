# NptrigPostCreateNamedPipeCallback

- ea: `0x140008cb0`
- end: `0x140008ebc`
- name: `NptrigPostCreateNamedPipeCallback`
- size: `524`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400017b0`
- `0x140008cb0`
- `0x140008ed0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140008dcc`
- `ntoskrnl!RtlCompareMemory` at `0x140008dcc`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140008d07`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140008d07`
- `FLTMGR!FltReleaseContext` at `0x140008daf`
- `FLTMGR!FltReleaseContext` at `0x140008daf`
- `FLTMGR!FltReleasePushLockEx` at `0x140008d81`
- `FLTMGR!FltReleasePushLockEx` at `0x140008d81`
- `FLTMGR!FltGetInstanceContext` at `0x140008e20`
- `FLTMGR!FltGetInstanceContext` at `0x140008e20`

## pseudocode

```c
__int64 __fastcall NptrigPostCreateNamedPipeCallback(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v6; // rax
  __int64 v8; // rax
  _WORD *v9; // rcx
  __int64 v10; // r8
  unsigned __int16 *v11; // rbx
  const void *v12; // r14
  unsigned int v13; // ebp
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  PFLT_CONTEXT Context; // [rsp+20h] [rbp-28h] BYREF

  Context = 0;
  if ( (a4 & 1) == 0 && !*(_DWORD *)(a1 + 24) && (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) & 1) == 0 )
  {
    v6 = *(_QWORD *)(a2 + 32);
    if ( v6 )
    {
      if ( *(_WORD *)(v6 + 88) )
      {
        FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, v16, a1);
        FltAcquirePushLockExclusiveEx(WPP_MAIN_CB.DeviceExtension, 0);
        v8 = *(_QWORD *)(a2 + 32);
        v9 = *(_WORD **)(v8 + 96);
        v10 = *(unsigned __int16 *)(v8 + 88);
        v11 = (unsigned __int16 *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
        v12 = v9 + 1;
        v13 = v10 - 2;
        if ( *v9 != 92 )
        {
          v12 = *(const void **)(v8 + 96);
          v13 = *(unsigned __int16 *)(v8 + 88);
        }
        while ( v11 != (unsigned __int16 *)WPP_MAIN_CB.DeviceExtension + 4 )
        {
          if ( v11[8] == v13 && RtlCompareMemory(v12, *((const void **)v11 + 3), v13) == v13 )
          {
            if ( *((_DWORD *)v11 + 8) == 3 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                v15 = 17;
LABEL_29:
                WPP_SF_q(v14->AttachedDevice, v15, v10, a1);
                goto LABEL_14;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, v10, a1);
              }
              NptrigReleasePendingRequests(v11, Context, 0);
              *((_DWORD *)v11 + 8) = 3;
            }
            goto LABEL_14;
          }
          v11 = *(unsigned __int16 **)v11;
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          v15 = 16;
          goto LABEL_29;
        }
LABEL_14:
        FltReleasePushLockEx(WPP_MAIN_CB.DeviceExtension, 0);
        if ( Context )
          FltReleaseContext(Context);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140008cb0  push    rbx
0x140008cb2  push    rsi
0x140008cb3  sub     rsp, 38h
0x140008cb7  mov     [rsp+48h+Context], 0
0x140008cc0  mov     rbx, rdx
0x140008cc3  mov     rsi, rcx
0x140008cc6  test    r9b, 1
0x140008cca  jnz     short loc_140008CF4
0x140008ccc  cmp     dword ptr [rcx+18h], 0
0x140008cd0  jnz     short loc_140008CF4
0x140008cd2  mov     rax, [rcx+10h]
0x140008cd6  mov     r8d, [rax+20h]
0x140008cda  test    r8b, 1
0x140008cde  jnz     short loc_140008CF4
0x140008ce0  mov     rax, [rdx+20h]
0x140008ce4  test    rax, rax
0x140008ce7  jz      short loc_140008CF4
0x140008ce9  cmp     word ptr [rax+58h], 0
0x140008cee  jnz     loc_140008E08
0x140008cf4  xor     eax, eax
0x140008cf6  add     rsp, 38h
0x140008cfa  pop     rsi
0x140008cfb  pop     rbx
0x140008cfc  retn
0x140008cfe  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140008d05  xor     edx, edx
0x140008d07  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140008d0e  nop     dword ptr [rax+rax+00h]
0x140008d13  mov     rax, [rbx+20h]
0x140008d17  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x140008d1e  mov     [rsp+48h+arg_8], rdi
0x140008d23  mov     rcx, [rax+60h]
0x140008d27  movzx   r8d, word ptr [rax+58h]
0x140008d2c  mov     rbx, [rbx+8]
0x140008d30  cmp     word ptr [rcx], 5Ch ; '\'
0x140008d34  lea     r14, [rcx+2]
0x140008d38  lea     ebp, [r8-2]
0x140008d3c  cmovnz  r14, rcx
0x140008d40  cmovnz  ebp, r8d
0x140008d44  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140008d4b  add     rax, 8
0x140008d4f  cmp     rbx, rax
0x140008d52  jz      short loc_140008D61
0x140008d54  movzx   eax, word ptr [rbx+10h]
0x140008d58  cmp     eax, ebp
0x140008d5a  jz      short loc_140008DC0
0x140008d5c  mov     rbx, [rbx]
0x140008d5f  jmp     short loc_140008D44
0x140008d61  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d68  cmp     rcx, r15
0x140008d6b  jz      short loc_140008D78
0x140008d6d  mov     eax, [rcx+2Ch]
0x140008d70  test    al, 4
0x140008d72  jnz     loc_140008EA6
0x140008d78  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140008d7f  xor     edx, edx
0x140008d81  call    cs:__imp_FltReleasePushLockEx
0x140008d88  nop     dword ptr [rax+rax+00h]
0x140008d8d  mov     rcx, [rsp+48h+Context]; Context
0x140008d92  mov     r15, [rsp+48h+var_18]
0x140008d97  mov     r14, [rsp+48h+arg_10]
0x140008d9c  mov     rdi, [rsp+48h+arg_8]
0x140008da1  mov     rbp, [rsp+48h+arg_0]
0x140008da6  test    rcx, rcx
0x140008da9  jz      loc_140008CF4
0x140008daf  call    cs:__imp_FltReleaseContext
0x140008db6  nop     dword ptr [rax+rax+00h]
0x140008dbb  jmp     loc_140008CF4
0x140008dc0  mov     rdx, [rbx+18h]; Source2
0x140008dc4  mov     rcx, r14; Source1
0x140008dc7  mov     r8d, ebp; Length
0x140008dca  mov     edi, ebp
0x140008dcc  call    cs:__imp_RtlCompareMemory
0x140008dd3  nop     dword ptr [rax+rax+00h]
0x140008dd8  cmp     rax, rdi
0x140008ddb  jnz     loc_140008D5C
0x140008de1  cmp     dword ptr [rbx+20h], 3
0x140008de5  jnz     short loc_140008E64
0x140008de7  mov     rcx, cs:WPP_GLOBAL_Control
0x140008dee  cmp     rcx, r15
0x140008df1  jz      short loc_140008D78
0x140008df3  mov     eax, [rcx+2Ch]
0x140008df6  test    al, 4
0x140008df8  jz      loc_140008D78
0x140008dfe  mov     edx, 11h
0x140008e03  jmp     loc_140008EAB
0x140008e08  mov     rcx, [rbx+18h]; Instance
0x140008e0c  lea     rdx, [rsp+48h+Context]; Context
0x140008e11  mov     [rsp+48h+arg_0], rbp
0x140008e16  mov     [rsp+48h+arg_10], r14
0x140008e1b  mov     [rsp+48h+var_18], r15
0x140008e20  call    cs:__imp_FltGetInstanceContext
0x140008e27  nop     dword ptr [rax+rax+00h]
0x140008e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e33  lea     r15, WPP_GLOBAL_Control
0x140008e3a  cmp     rcx, r15
0x140008e3d  jz      loc_140008CFE
0x140008e43  mov     eax, [rcx+2Ch]
0x140008e46  test    al, 4
0x140008e48  jz      loc_140008CFE
0x140008e4e  mov     rcx, [rcx+18h]
0x140008e52  mov     edx, 0Fh
0x140008e57  mov     r9, rsi
0x140008e5a  call    WPP_SF_q
0x140008e5f  jmp     loc_140008CFE
0x140008e64  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e6b  cmp     rcx, r15
0x140008e6e  jz      short loc_140008E77
0x140008e70  mov     eax, [rcx+2Ch]
0x140008e73  test    al, 4
0x140008e75  jnz     short loc_140008E93
0x140008e77  mov     rdx, [rsp+48h+Context]
0x140008e7c  xor     r8d, r8d
0x140008e7f  mov     rcx, rbx
0x140008e82  call    NptrigReleasePendingRequests
0x140008e87  mov     dword ptr [rbx+20h], 3
0x140008e8e  jmp     loc_140008D78
0x140008e93  mov     rcx, [rcx+18h]
0x140008e97  mov     edx, 12h
0x140008e9c  mov     r9, rsi
0x140008e9f  call    WPP_SF_q
0x140008ea4  jmp     short loc_140008E77
0x140008ea6  mov     edx, 10h
0x140008eab  mov     rcx, [rcx+18h]
0x140008eaf  mov     r9, rsi
0x140008eb2  call    WPP_SF_q
0x140008eb7  jmp     loc_140008D78
```
