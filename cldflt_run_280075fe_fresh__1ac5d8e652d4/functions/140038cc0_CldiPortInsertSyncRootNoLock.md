# CldiPortInsertSyncRootNoLock

- ea: `0x140038cc0`
- end: `0x140038dcc`
- name: `CldiPortInsertSyncRootNoLock`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003baf0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140038cc0`
- `0x1400560c8`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140038da3`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140038da3`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140038d78`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140038d78`

## pseudocode

```c
__int64 __fastcall CldiPortInsertSyncRootNoLock(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  struct _RTL_AVL_TABLE *v10; // rdi
  _QWORD Buffer[7]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int8 NewElement; // [rsp+88h] [rbp+10h] BYREF

  Buffer[1] = a2;
  NewElement = 0;
  Buffer[0] = a3;
  v7 = CldiPortLookupSyncRootNoLock(a1, a3);
  v8 = v7;
  if ( v7 )
  {
    if ( *(_QWORD *)(v7 + 96) && *(_QWORD *)(v7 + 24) != a4 )
    {
      v9 = -1073688823;
      HsmDbgBreakOnStatus(3221278473LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_452df49304b034ad87c0baec305776b3_Traceguids,
          a3,
          a4,
          *(_QWORD *)(v8 + 24),
          -1073688823);
      }
      return v9;
    }
    v10 = (struct _RTL_AVL_TABLE *)(a1 + 152);
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 152), Buffer);
  }
  else
  {
    v10 = (struct _RTL_AVL_TABLE *)(a1 + 152);
  }
  v9 = 0;
  if ( !RtlInsertElementGenericTableAvl(v10, Buffer, 0x10u, &NewElement) )
  {
    v9 = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
  }
  return v9;
}

```

## disassembly

```asm
0x140038cc0  mov     rax, rsp
0x140038cc3  push    rbx
0x140038cc4  push    rbp
0x140038cc5  push    rsi
0x140038cc6  push    rdi
0x140038cc7  sub     rsp, 58h
0x140038ccb  mov     [rax-30h], rdx
0x140038ccf  mov     rsi, r9
0x140038cd2  mov     rdx, r8
0x140038cd5  mov     byte ptr [rax+10h], 0
0x140038cd9  mov     rbp, r8
0x140038cdc  mov     [rax-38h], r8
0x140038ce0  mov     rbx, rcx
0x140038ce3  call    CldiPortLookupSyncRootNoLock
0x140038ce8  mov     rdi, rax
0x140038ceb  test    rax, rax
0x140038cee  jz      loc_140038D86
0x140038cf4  mov     rdx, [rax+60h]
0x140038cf8  test    rdx, rdx
0x140038cfb  jz      short loc_140038D69
0x140038cfd  cmp     [rax+18h], rsi
0x140038d01  jz      short loc_140038D69
0x140038d03  mov     ebx, 0C000CF09h
0x140038d08  mov     ecx, ebx
0x140038d0a  call    HsmDbgBreakOnStatus
0x140038d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140038d16  lea     rax, WPP_GLOBAL_Control
0x140038d1d  cmp     rcx, rax
0x140038d20  jz      loc_140038DC0
0x140038d26  test    dword ptr [rcx+2Ch], 100h
0x140038d2d  jz      loc_140038DC0
0x140038d33  cmp     byte ptr [rcx+29h], 2
0x140038d37  jb      loc_140038DC0
0x140038d3d  mov     rax, [rdi+18h]
0x140038d41  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x140038d48  mov     rcx, [rcx+18h]
0x140038d4c  mov     edx, 0Ah
0x140038d51  mov     [rsp+78h+var_48], ebx
0x140038d55  mov     r9, rbp
0x140038d58  mov     [rsp+78h+var_50], rax
0x140038d5d  mov     [rsp+78h+var_58], rsi
0x140038d62  call    WPP_SF_qqqd
0x140038d67  jmp     short loc_140038DC0
0x140038d69  lea     rdi, [rbx+98h]
0x140038d70  mov     rcx, rdi; Table
0x140038d73  lea     rdx, [rsp+78h+Buffer]; Buffer
0x140038d78  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140038d7f  nop     dword ptr [rax+rax+00h]
0x140038d84  jmp     short loc_140038D8D
0x140038d86  lea     rdi, [rbx+98h]
0x140038d8d  xor     ebx, ebx
0x140038d8f  lea     r9, [rsp+78h+NewElement]; NewElement
0x140038d97  lea     rdx, [rsp+78h+Buffer]; Buffer
0x140038d9c  mov     rcx, rdi; Table
0x140038d9f  lea     r8d, [rbx+10h]; BufferSize
0x140038da3  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140038daa  nop     dword ptr [rax+rax+00h]
0x140038daf  test    rax, rax
0x140038db2  jnz     short loc_140038DC0
0x140038db4  mov     ebx, 0C000009Ah
0x140038db9  mov     ecx, ebx
0x140038dbb  call    HsmDbgBreakOnStatus
0x140038dc0  mov     eax, ebx
0x140038dc2  add     rsp, 58h
0x140038dc6  pop     rdi
0x140038dc7  pop     rsi
0x140038dc8  pop     rbp
0x140038dc9  pop     rbx
0x140038dca  retn
```
