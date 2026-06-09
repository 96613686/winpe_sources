# HsmFltPreSET_REPARSE_POINT

- ea: `0x140062c98`
- end: `0x140062de6`
- name: `HsmFltPreSET_REPARSE_POINT`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14004d7c0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140051b5c`
- `0x140062c98`
- `0x140062df0`
- `0x14006def0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140062dbd`
- `FLTMGR!FltReleaseContext` at `0x140062dbd`

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
      HsmDbgBreakOnStatus((unsigned int)SyncProviderProcess);
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
        HsmDbgBreakOnStatus(3221278488LL);
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
0x140062c98  mov     rax, rsp
0x140062c9b  mov     [rax+8], rbx
0x140062c9f  mov     [rax+10h], rbp
0x140062ca3  mov     [rax+20h], r9
0x140062ca7  push    rsi
0x140062ca8  push    rdi
0x140062ca9  push    r12
0x140062cab  push    r14
0x140062cad  push    r15
0x140062caf  sub     rsp, 40h
0x140062cb3  mov     rdx, [rcx+10h]
0x140062cb7  mov     rsi, r8
0x140062cba  mov     rdi, rcx
0x140062cbd  mov     qword ptr [rax+20h], 0
0x140062cc5  mov     ebp, 1
0x140062cca  cmp     dword ptr [rdx+20h], 4
0x140062cce  jb      short loc_140062CF0
0x140062cd0  mov     rcx, r8
0x140062cd3  call    HsmpIsPlaceholderHandle
0x140062cd8  test    al, al
0x140062cda  jnz     short loc_140062D0A
0x140062cdc  mov     rax, [rdx+30h]
0x140062ce0  mov     ecx, [rax]
0x140062ce2  and     ecx, 0FFFF0FFFh
0x140062ce8  cmp     ecx, cs:dword_140029670
0x140062cee  jz      short loc_140062D0A
0x140062cf0  mov     rbx, [rsp+68h+arg_0]
0x140062cf5  mov     eax, ebp
0x140062cf7  mov     rbp, [rsp+68h+arg_8]
0x140062cfc  add     rsp, 40h
0x140062d00  pop     r15
0x140062d02  pop     r14
0x140062d04  pop     r12
0x140062d06  pop     rdi
0x140062d07  pop     rsi
0x140062d08  retn
0x140062d0a  test    rsi, rsi
0x140062d0d  jz      short loc_140062D1D
0x140062d0f  mov     r14, [r8+10h]
0x140062d13  mov     rax, [r14+10h]
0x140062d17  mov     r12, [rax+20h]
0x140062d1b  jmp     short loc_140062D23
0x140062d1d  xor     r14d, r14d
0x140062d20  xor     r12d, r12d
0x140062d23  mov     rcx, [rdx+10h]
0x140062d27  call    HsmpGetInstanceContext
0x140062d2c  mov     r15, rax
0x140062d2f  test    rax, rax
0x140062d32  jz      short loc_140062CF0
0x140062d34  mov     r8, [rdi+10h]
0x140062d38  lea     r9, [rsp+68h+arg_18]
0x140062d40  mov     rdx, r14
0x140062d43  mov     rcx, rax
0x140062d46  mov     r8, [r8+8]
0x140062d4a  call    HsmiCldGetSyncProviderProcess
0x140062d4f  mov     ecx, eax
0x140062d51  mov     ebx, eax
0x140062d53  call    HsmDbgBreakOnStatus
0x140062d58  test    ebx, ebx
0x140062d5a  js      short loc_140062D73
0x140062d5c  cmp     [rsp+68h+arg_18], 0
0x140062d65  jz      short loc_140062DBA
0x140062d67  mov     ebx, 0C000CF18h
0x140062d6c  mov     ecx, ebx
0x140062d6e  call    HsmDbgBreakOnStatus
0x140062d73  mov     rcx, cs:WPP_GLOBAL_Control
0x140062d7a  lea     rax, WPP_GLOBAL_Control
0x140062d81  cmp     rcx, rax
0x140062d84  jz      short loc_140062DBA
0x140062d86  mov     eax, [rcx+2Ch]
0x140062d89  test    bpl, al
0x140062d8c  jz      short loc_140062DBA
0x140062d8e  cmp     byte ptr [rcx+29h], 2
0x140062d92  jb      short loc_140062DBA
0x140062d94  mov     rcx, [rcx+18h]
0x140062d98  lea     r8, WPP_c4243d3071913aff92fc255103df7e39_Traceguids
0x140062d9f  mov     [rsp+68h+var_38], ebx
0x140062da3  mov     edx, 13h
0x140062da8  mov     [rsp+68h+var_40], r12
0x140062dad  mov     r9, rsi
0x140062db0  mov     [rsp+68h+var_48], r14
0x140062db5  call    WPP_SF_qqqd
0x140062dba  mov     rcx, r15; Context
0x140062dbd  call    cs:__imp_FltReleaseContext
0x140062dc4  nop     dword ptr [rax+rax+00h]
0x140062dc9  test    ebx, ebx
0x140062dcb  jns     loc_140062CF0
0x140062dd1  mov     [rdi+18h], ebx
0x140062dd4  mov     ebp, 4
0x140062dd9  mov     qword ptr [rdi+20h], 0
0x140062de1  jmp     loc_140062CF0
```
