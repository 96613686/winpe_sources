# HsmFltPreSET_REPARSE_POINT_EX

- ea: `0x140046980`
- end: `0x140046ae4`
- name: `HsmFltPreSET_REPARSE_POINT_EX`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14004d7c0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140046980`
- `0x140051b5c`
- `0x140062df0`
- `0x14006def0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140046aaa`
- `FLTMGR!FltReleaseContext` at `0x140046aaa`

## pseudocode

```c
__int64 HsmFltPreSET_REPARSE_POINT_EX(__int64 a1, __int64 a2, __int64 a3, ...)
{
  __int64 v3; // rdx
  unsigned int v6; // ebp
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r14
  __int64 v10; // r12
  __int64 InstanceContext; // rax
  void *v12; // r15
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
  if ( *(_DWORD *)(v3 + 32) >= 0x24u )
  {
    if ( (unsigned __int8)HsmpIsPlaceholderHandle(a3)
      || (v8 = *(_QWORD *)(v7 + 48), (*(_DWORD *)(v8 + 32) & 0xFFFF0FFF) == dword_140029670)
      || (*(_DWORD *)(v8 + 4) & 0xFFFF0FFF) == dword_140029670 )
    {
      if ( a3 )
      {
        v9 = *(_QWORD *)(a3 + 16);
        v10 = *(_QWORD *)(*(_QWORD *)(v9 + 16) + 32LL);
      }
      else
      {
        v9 = 0;
        v10 = 0;
      }
      InstanceContext = HsmpGetInstanceContext(*(_QWORD *)(v7 + 16));
      v12 = (void *)InstanceContext;
      if ( InstanceContext )
      {
        SyncProviderProcess = HsmiCldGetSyncProviderProcess(
                                InstanceContext,
                                v9,
                                *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
                                (__int64 *)va);
        HsmDbgBreakOnStatus((unsigned int)SyncProviderProcess);
        if ( SyncProviderProcess >= 0 )
        {
          if ( !v15 )
          {
LABEL_16:
            FltReleaseContext(v12);
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
            20,
            WPP_c4243d3071913aff92fc255103df7e39_Traceguids,
            a3,
            v9,
            v10,
            SyncProviderProcess);
        }
        goto LABEL_16;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140046980  mov     rax, rsp
0x140046983  mov     [rax+8], rbx
0x140046987  mov     [rax+10h], rbp
0x14004698b  mov     [rax+20h], r9
0x14004698f  push    rsi
0x140046990  push    rdi
0x140046991  push    r12
0x140046993  push    r14
0x140046995  push    r15
0x140046997  sub     rsp, 40h
0x14004699b  mov     rdx, [rcx+10h]
0x14004699f  mov     rsi, r8
0x1400469a2  mov     rdi, rcx
0x1400469a5  mov     qword ptr [rax+20h], 0
0x1400469ad  mov     ebp, 1
0x1400469b2  cmp     dword ptr [rdx+20h], 24h ; '$'
0x1400469b6  jb      loc_140046ACA
0x1400469bc  mov     rcx, r8
0x1400469bf  call    HsmpIsPlaceholderHandle
0x1400469c4  test    al, al
0x1400469c6  jnz     short loc_1400469F3
0x1400469c8  mov     rcx, [rdx+30h]
0x1400469cc  mov     r9d, 0FFFF0FFFh
0x1400469d2  mov     r8d, cs:dword_140029670
0x1400469d9  mov     eax, [rcx+20h]
0x1400469dc  and     eax, r9d
0x1400469df  cmp     eax, r8d
0x1400469e2  jz      short loc_1400469F3
0x1400469e4  mov     eax, [rcx+4]
0x1400469e7  and     eax, r9d
0x1400469ea  cmp     eax, r8d
0x1400469ed  jnz     loc_140046ACA
0x1400469f3  test    rsi, rsi
0x1400469f6  jz      short loc_140046A06
0x1400469f8  mov     r14, [rsi+10h]
0x1400469fc  mov     rax, [r14+10h]
0x140046a00  mov     r12, [rax+20h]
0x140046a04  jmp     short loc_140046A0C
0x140046a06  xor     r14d, r14d
0x140046a09  xor     r12d, r12d
0x140046a0c  mov     rcx, [rdx+10h]
0x140046a10  call    HsmpGetInstanceContext
0x140046a15  mov     r15, rax
0x140046a18  test    rax, rax
0x140046a1b  jz      loc_140046ACA
0x140046a21  mov     r8, [rdi+10h]
0x140046a25  lea     r9, [rsp+68h+arg_18]
0x140046a2d  mov     rdx, r14
0x140046a30  mov     rcx, rax
0x140046a33  mov     r8, [r8+8]
0x140046a37  call    HsmiCldGetSyncProviderProcess
0x140046a3c  mov     ecx, eax
0x140046a3e  mov     ebx, eax
0x140046a40  call    HsmDbgBreakOnStatus
0x140046a45  test    ebx, ebx
0x140046a47  js      short loc_140046A60
0x140046a49  cmp     [rsp+68h+arg_18], 0
0x140046a52  jz      short loc_140046AA7
0x140046a54  mov     ebx, 0C000CF18h
0x140046a59  mov     ecx, ebx
0x140046a5b  call    HsmDbgBreakOnStatus
0x140046a60  mov     rcx, cs:WPP_GLOBAL_Control
0x140046a67  lea     rax, WPP_GLOBAL_Control
0x140046a6e  cmp     rcx, rax
0x140046a71  jz      short loc_140046AA7
0x140046a73  mov     eax, [rcx+2Ch]
0x140046a76  test    bpl, al
0x140046a79  jz      short loc_140046AA7
0x140046a7b  cmp     byte ptr [rcx+29h], 2
0x140046a7f  jb      short loc_140046AA7
0x140046a81  mov     rcx, [rcx+18h]
0x140046a85  lea     r8, WPP_c4243d3071913aff92fc255103df7e39_Traceguids
0x140046a8c  mov     [rsp+68h+var_38], ebx
0x140046a90  mov     edx, 14h
0x140046a95  mov     [rsp+68h+var_40], r12
0x140046a9a  mov     r9, rsi
0x140046a9d  mov     [rsp+68h+var_48], r14
0x140046aa2  call    WPP_SF_qqqd
0x140046aa7  mov     rcx, r15; Context
0x140046aaa  call    cs:__imp_FltReleaseContext
0x140046ab1  nop     dword ptr [rax+rax+00h]
0x140046ab6  test    ebx, ebx
0x140046ab8  jns     short loc_140046ACA
0x140046aba  mov     [rdi+18h], ebx
0x140046abd  mov     ebp, 4
0x140046ac2  mov     qword ptr [rdi+20h], 0
0x140046aca  mov     rbx, [rsp+68h+arg_0]
0x140046acf  mov     eax, ebp
0x140046ad1  mov     rbp, [rsp+68h+arg_8]
0x140046ad6  add     rsp, 40h
0x140046ada  pop     r15
0x140046adc  pop     r14
0x140046ade  pop     r12
0x140046ae0  pop     rdi
0x140046ae1  pop     rsi
0x140046ae2  retn
```
