# HsmFltPreSET_REPARSE_POINT

- ea: `0x140062db8`
- end: `0x140062f06`
- name: `HsmFltPreSET_REPARSE_POINT`
- size: `334`
- prototype: `__int64(__int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14004d8e0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140051c7c`
- `0x140062db8`
- `0x140062f10`
- `0x14006e010`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140062edd`
- `FLTMGR!FltReleaseContext` at `0x140062edd`

## pseudocode

```c
__int64 HsmFltPreSET_REPARSE_POINT(__int64 a1, __int64 a2, __int64 a3, ...)
{
  __int64 v3; // rdx
  unsigned int v6; // ebp
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v10; // r14
  __int64 v11; // r12
  __int64 InstanceContext; // rax
  void *v13; // r15
  int SyncProviderProcess; // ebx
  __int64 v15; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  va_list va1; // [rsp+90h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v15 = va_arg(va1, _QWORD);
  v3 = *(_QWORD *)(a1 + 16);
  v15 = 0;
  v6 = 1;
  if ( *(_DWORD *)(v3 + 32) >= 4u
    && ((unsigned __int8)HsmpIsPlaceholderHandle(a3) || (**(_DWORD **)(v7 + 48) & 0xFFFF0FFF) == dword_140029670) )
  {
    if ( a3 )
    {
      v10 = *(_QWORD *)(v8 + 16);
      v11 = *(_QWORD *)(*(_QWORD *)(v10 + 16) + 32LL);
    }
    else
    {
      v10 = 0;
      v11 = 0;
    }
    InstanceContext = HsmpGetInstanceContext(*(_QWORD *)(v7 + 16));
    v13 = (void *)InstanceContext;
    if ( InstanceContext )
    {
      SyncProviderProcess = HsmiCldGetSyncProviderProcess(
                              InstanceContext,
                              v10,
                              *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
                              (__int64 *)va);
      HsmDbgBreakOnStatus(SyncProviderProcess);
      if ( SyncProviderProcess >= 0 )
      {
        if ( !v15 )
        {
LABEL_16:
          FltReleaseContext(v13);
          if ( SyncProviderProcess < 0 )
          {
            *(_DWORD *)(a1 + 24) = SyncProviderProcess;
            v6 = 4;
            *(_QWORD *)(a1 + 32) = 0;
          }
          return v6;
        }
        SyncProviderProcess = -1073688808;
        HsmDbgBreakOnStatus(-1073688808);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_c4243d3071913aff92fc255103df7e39_Traceguids,
          a3,
          v10,
          v11,
          SyncProviderProcess);
      }
      goto LABEL_16;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140062db8  mov     rax, rsp
0x140062dbb  mov     [rax+8], rbx
0x140062dbf  mov     [rax+10h], rbp
0x140062dc3  mov     [rax+20h], r9
0x140062dc7  push    rsi
0x140062dc8  push    rdi
0x140062dc9  push    r12
0x140062dcb  push    r14
0x140062dcd  push    r15
0x140062dcf  sub     rsp, 40h
0x140062dd3  mov     rdx, [rcx+10h]
0x140062dd7  mov     rsi, r8
0x140062dda  mov     rdi, rcx
0x140062ddd  mov     qword ptr [rax+20h], 0
0x140062de5  mov     ebp, 1
0x140062dea  cmp     dword ptr [rdx+20h], 4
0x140062dee  jb      short loc_140062E10
0x140062df0  mov     rcx, r8
0x140062df3  call    HsmpIsPlaceholderHandle
0x140062df8  test    al, al
0x140062dfa  jnz     short loc_140062E2A
0x140062dfc  mov     rax, [rdx+30h]
0x140062e00  mov     ecx, [rax]
0x140062e02  and     ecx, 0FFFF0FFFh
0x140062e08  cmp     ecx, cs:dword_140029670
0x140062e0e  jz      short loc_140062E2A
0x140062e10  mov     rbx, [rsp+68h+arg_0]
0x140062e15  mov     eax, ebp
0x140062e17  mov     rbp, [rsp+68h+arg_8]
0x140062e1c  add     rsp, 40h
0x140062e20  pop     r15
0x140062e22  pop     r14
0x140062e24  pop     r12
0x140062e26  pop     rdi
0x140062e27  pop     rsi
0x140062e28  retn
0x140062e2a  test    rsi, rsi
0x140062e2d  jz      short loc_140062E3D
0x140062e2f  mov     r14, [r8+10h]
0x140062e33  mov     rax, [r14+10h]
0x140062e37  mov     r12, [rax+20h]
0x140062e3b  jmp     short loc_140062E43
0x140062e3d  xor     r14d, r14d
0x140062e40  xor     r12d, r12d
0x140062e43  mov     rcx, [rdx+10h]
0x140062e47  call    HsmpGetInstanceContext
0x140062e4c  mov     r15, rax
0x140062e4f  test    rax, rax
0x140062e52  jz      short loc_140062E10
0x140062e54  mov     r8, [rdi+10h]
0x140062e58  lea     r9, [rsp+68h+arg_18]
0x140062e60  mov     rdx, r14
0x140062e63  mov     rcx, rax
0x140062e66  mov     r8, [r8+8]
0x140062e6a  call    HsmiCldGetSyncProviderProcess
0x140062e6f  mov     ecx, eax
0x140062e71  mov     ebx, eax
0x140062e73  call    HsmDbgBreakOnStatus
0x140062e78  test    ebx, ebx
0x140062e7a  js      short loc_140062E93
0x140062e7c  cmp     [rsp+68h+arg_18], 0
0x140062e85  jz      short loc_140062EDA
0x140062e87  mov     ebx, 0C000CF18h
0x140062e8c  mov     ecx, ebx
0x140062e8e  call    HsmDbgBreakOnStatus
0x140062e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140062e9a  lea     rax, WPP_GLOBAL_Control
0x140062ea1  cmp     rcx, rax
0x140062ea4  jz      short loc_140062EDA
0x140062ea6  mov     eax, [rcx+2Ch]
0x140062ea9  test    bpl, al
0x140062eac  jz      short loc_140062EDA
0x140062eae  cmp     byte ptr [rcx+29h], 2
0x140062eb2  jb      short loc_140062EDA
0x140062eb4  mov     rcx, [rcx+18h]
0x140062eb8  lea     r8, WPP_c4243d3071913aff92fc255103df7e39_Traceguids
0x140062ebf  mov     [rsp+68h+var_38], ebx
0x140062ec3  mov     edx, 13h
0x140062ec8  mov     [rsp+68h+var_40], r12
0x140062ecd  mov     r9, rsi
0x140062ed0  mov     [rsp+68h+var_48], r14
0x140062ed5  call    WPP_SF_qqqd
0x140062eda  mov     rcx, r15; Context
0x140062edd  call    cs:__imp_FltReleaseContext
0x140062ee4  nop     dword ptr [rax+rax+00h]
0x140062ee9  test    ebx, ebx
0x140062eeb  jns     loc_140062E10
0x140062ef1  mov     [rdi+18h], ebx
0x140062ef4  mov     ebp, 4
0x140062ef9  mov     qword ptr [rdi+20h], 0
0x140062f01  jmp     loc_140062E10
```
