# PrjfPrepareSourceForRename

- ea: `0x140007cec`
- end: `0x1400080de`
- name: `PrjfPrepareSourceForRename`
- size: `1010`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, char)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14002c98c`

## callees

- `0x140002b50`
- `0x140002f3c`
- `0x140006570`
- `0x140007cec`
- `0x14000b1d0`
- `0x14000d128`
- `0x140039de8`
- `0x14003c4b8`
- `0x140041a3c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000806a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000806a`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140008025`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140008025`
- `FLTMGR!FltParseFileNameInformation` at `0x140007dc1`
- `FLTMGR!FltParseFileNameInformation` at `0x140007dc1`
- `FLTMGR!FltClose` at `0x140008056`
- `FLTMGR!FltClose` at `0x140008056`
- `FLTMGR!FltReleaseContext` at `0x14000807e`
- `FLTMGR!FltReleaseContext` at `0x140008092`
- `FLTMGR!FltReleaseContext` at `0x1400080a7`
- `FLTMGR!FltReleaseContext` at `0x1400080bb`
- `FLTMGR!FltReleaseContext` at `0x14000807e`
- `FLTMGR!FltReleaseContext` at `0x140008092`
- `FLTMGR!FltReleaseContext` at `0x1400080a7`
- `FLTMGR!FltReleaseContext` at `0x1400080bb`

## pseudocode

```c
__int64 __fastcall PrjfPrepareSourceForRename(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        char a4)
{
  unsigned int DoesNameExistInLayer; // ebx
  char ContextFileObject; // al
  PFLT_CONTEXT v9; // r12
  PFLT_CONTEXT v10; // rsi
  char v12; // [rsp+60h] [rbp-39h]
  PVOID Object; // [rsp+68h] [rbp-31h]
  __int64 v14; // [rsp+70h] [rbp-29h]
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-21h] BYREF
  PFLT_CONTEXT v16[2]; // [rsp+80h] [rbp-19h] BYREF
  HANDLE FileHandle; // [rsp+90h] [rbp-9h]
  PFLT_CONTEXT v18; // [rsp+98h] [rbp-1h]

  Context = 0;
  v16[0] = 0;
  v12 = 0;
  FileHandle = 0;
  Object = 0;
  v18 = 0;
  v14 = 0;
  DoesNameExistInLayer = 0;
  ContextFileObject = PrjfGetContextFileObject(Instance, FileObject, (__int64 *)&Context, v16);
  v9 = v16[0];
  v10 = Context;
  if ( ContextFileObject )
  {
    if ( Context && *((_DWORD *)Context + 16) != 3 )
    {
      if ( *(_DWORD *)v16[0] )
      {
        if ( *(_DWORD *)v16[0] == 1 )
        {
          DoesNameExistInLayer = -1073741637;
          goto LABEL_10;
        }
      }
      else if ( !a4 )
      {
        DoesNameExistInLayer = -1073741612;
        goto LABEL_10;
      }
    }
    DoesNameExistInLayer = PrjfDoesNameExistInLayer(CallbackData, Instance);
  }
LABEL_10:
  if ( v10 )
    FltReleaseContext(v10);
  if ( v9 )
    FltReleaseContext(v9);
  if ( v18 )
    FltReleaseContext(v18);
  return DoesNameExistInLayer;
}

```

## disassembly

```asm
0x140007cec  mov     [rsp-8+Instance], rdx
0x140007cf1  push    rbp
0x140007cf2  push    rbx
0x140007cf3  push    rsi
0x140007cf4  push    rdi
0x140007cf5  push    r12
0x140007cf7  push    r13
0x140007cf9  push    r14
0x140007cfb  push    r15
0x140007cfd  lea     rbp, [rsp-0Fh]
0x140007d02  sub     rsp, 0A8h
0x140007d09  xor     esi, esi
0x140007d0b  mov     rax, r8
0x140007d0e  mov     rdi, rdx
0x140007d11  mov     [rbp+47h+Context], rsi
0x140007d15  mov     r14b, r9b
0x140007d18  mov     [rbp+47h+var_60], rsi
0x140007d1c  mov     r15, rcx
0x140007d1f  mov     [rbp+47h+var_80], sil
0x140007d23  mov     rdx, rax; FileObject
0x140007d26  mov     [rbp+47h+FileHandle], rsi
0x140007d2a  mov     rcx, rdi; Instance
0x140007d2d  mov     [rbp+47h+Object], rsi
0x140007d31  lea     r9, [rbp+47h+var_60]
0x140007d35  mov     [rbp+47h+var_48], rsi
0x140007d39  lea     r8, [rbp+47h+Context]
0x140007d3d  mov     [rbp+47h+var_70], rsi
0x140007d41  mov     ebx, esi
0x140007d43  mov     r13d, esi
0x140007d46  call    PrjfGetContextFileObject
0x140007d4b  mov     r12, [rbp+47h+var_60]
0x140007d4f  mov     rsi, [rbp+47h+Context]
0x140007d53  test    al, al
0x140007d55  jz      loc_140008076
0x140007d5b  test    rsi, rsi
0x140007d5e  jz      short loc_140007D8C
0x140007d60  cmp     dword ptr [rsi+40h], 3
0x140007d64  jz      short loc_140007D8C
0x140007d66  mov     eax, [r12]
0x140007d6a  test    eax, eax
0x140007d6c  jnz     short loc_140007D7D
0x140007d6e  test    r14b, r14b
0x140007d71  jnz     short loc_140007D8C
0x140007d73  mov     ebx, 0C00000D4h
0x140007d78  jmp     loc_140008076
0x140007d7d  cmp     eax, 1
0x140007d80  jnz     short loc_140007D8C
0x140007d82  mov     ebx, 0C00000BBh
0x140007d87  jmp     loc_140008076
0x140007d8c  lea     r8, [rbp+47h+var_80]
0x140007d90  mov     rdx, rdi; Instance
0x140007d93  mov     rcx, r15; CallbackData
0x140007d96  call    PrjfDoesNameExistInLayer
0x140007d9b  mov     ebx, eax
0x140007d9d  test    eax, eax
0x140007d9f  js      loc_140008076
0x140007da5  cmp     [rbp+47h+var_80], r13b
0x140007da9  jz      loc_140008076
0x140007daf  mov     r14, [rbp+47h+FileNameInformation]
0x140007db3  xorps   xmm0, xmm0
0x140007db6  mov     rcx, r14; FileNameInformation
0x140007db9  mov     [rbp+47h+var_80], r13b
0x140007dbd  movups  xmmword ptr [rbp+47h+var_60], xmm0
0x140007dc1  call    cs:__imp_FltParseFileNameInformation
0x140007dc8  nop     dword ptr [rax+rax+00h]
0x140007dcd  mov     ebx, eax
0x140007dcf  test    eax, eax
0x140007dd1  js      loc_140008076
0x140007dd7  movups  xmm0, xmmword ptr [r14+8]
0x140007ddc  mov     eax, 0FFFEh
0x140007de1  sub     ax, [r14+58h]
0x140007de6  movd    ecx, xmm0
0x140007dea  movups  xmmword ptr [rbp+47h+var_60], xmm0
0x140007dee  add     cx, ax
0x140007df1  mov     word ptr [rbp+47h+var_60], cx
0x140007df5  cmp     cx, [r14+18h]
0x140007dfa  jnz     short loc_140007E01
0x140007dfc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140007e01  lea     rax, [rbp+47h+var_80]
0x140007e05  mov     rcx, rdi
0x140007e08  mov     [rsp+0E0h+var_B8], rax
0x140007e0d  lea     r9, [rbp+47h+FileHandle]
0x140007e11  lea     rax, [rbp+47h+Object]
0x140007e15  lea     rdx, [rbp+47h+var_60]
0x140007e19  mov     [rsp+0E0h+FileObject], rax
0x140007e1e  call    PrjfOpenPlaceHolder
0x140007e23  xor     ecx, ecx
0x140007e25  mov     ebx, eax
0x140007e27  test    eax, eax
0x140007e29  jns     short loc_140007EA3
0x140007e2b  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140007e31  lea     rax, WPP_RECORDER_INITIALIZED
0x140007e38  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007e3f  setnz   r8b
0x140007e43  and     dl, 20h
0x140007e46  jnz     short loc_140007E4D
0x140007e48  test    r8b, r8b
0x140007e4b  jz      short loc_140007E9A
0x140007e4d  mov     r9, cs:WPP_GLOBAL_Control
0x140007e54  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007e5b  mov     [rsp+0E0h+var_90], ebx
0x140007e5f  mov     ecx, 20Dh
0x140007e64  mov     [rsp+0E0h+var_98], 13EDh
0x140007e6c  mov     [rsp+0E0h+var_A0], rax
0x140007e71  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007e78  mov     r9, [r9+40h]
0x140007e7c  mov     [rsp+0E0h+var_A8], rax
0x140007e81  mov     word ptr [rsp+0E0h+var_B0], 71h ; 'q'
0x140007e88  mov     dword ptr [rsp+0E0h+var_B8], 0Dh
0x140007e90  mov     byte ptr [rsp+0E0h+FileObject], 2
0x140007e95  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140007e9a  mov     rdi, [rbp+47h+Object]
0x140007e9e  jmp     loc_14000804D
0x140007ea3  mov     r15, [rbp+47h+arg_28]
0x140007ea7  mov     rdi, [rbp+47h+Object]
0x140007eab  cmp     [rbp+47h+var_80], cl
0x140007eae  jz      loc_140008041
0x140007eb4  lea     rax, [rbp+47h+var_70]
0x140007eb8  xor     r9d, r9d
0x140007ebb  mov     [rsp+0E0h+var_A0], rax; __int64
0x140007ec0  mov     r8d, 80000000h
0x140007ec6  lea     rax, [rbp+47h+var_48]
0x140007eca  mov     rdx, rdi; FileObject
0x140007ecd  mov     [rsp+0E0h+var_A8], rax; __int64
0x140007ed2  mov     [rsp+0E0h+var_B0], rcx; __int64
0x140007ed7  mov     [rsp+0E0h+var_B8], rcx; __int64
0x140007edc  mov     byte ptr [rsp+0E0h+FileObject], cl; char
0x140007ee0  mov     rcx, [rbp+47h+Instance]; Instance
0x140007ee4  call    PrjfGetSetContextFileObject
0x140007ee9  mov     ebx, eax
0x140007eeb  test    eax, eax
0x140007eed  jns     short loc_140007F67
0x140007eef  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140007ef5  lea     rax, WPP_RECORDER_INITIALIZED
0x140007efc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007f03  setnz   r8b
0x140007f07  and     dl, 8
0x140007f0a  jnz     short loc_140007F11
0x140007f0c  test    r8b, r8b
0x140007f0f  jz      short loc_140007F5E
0x140007f11  mov     r9, cs:WPP_GLOBAL_Control
0x140007f18  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007f1f  mov     [rsp+0E0h+var_90], ebx
0x140007f23  mov     ecx, 213h
0x140007f28  mov     [rsp+0E0h+var_98], 1406h
0x140007f30  mov     [rsp+0E0h+var_A0], rax
0x140007f35  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007f3c  mov     r9, [r9+40h]
0x140007f40  mov     [rsp+0E0h+var_A8], rax
0x140007f45  mov     word ptr [rsp+0E0h+var_B0], 72h ; 'r'
0x140007f4c  mov     dword ptr [rsp+0E0h+var_B8], 13h
0x140007f54  mov     byte ptr [rsp+0E0h+FileObject], 2
0x140007f59  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140007f5e  mov     r13, [rbp+47h+var_70]
0x140007f62  jmp     loc_14000804D
0x140007f67  mov     r13, [rbp+47h+var_70]
0x140007f6b  lea     rdx, [r14+58h]; SourceString
0x140007f6f  mov     rcx, [rbp+47h+Instance]; Instance
0x140007f73  mov     [rsp+0E0h+var_B8], 0; __int64
0x140007f7c  mov     [rsp+0E0h+FileObject], rdi; FileObject
0x140007f81  mov     byte ptr [r13+2Ch], 1
0x140007f86  cmp     dword ptr [r12], 1
0x140007f8b  setz    r8b
0x140007f8f  xor     r9d, r9d
0x140007f92  call    PrjfAddInMemoryTombstone
0x140007f97  mov     ebx, eax
0x140007f99  test    eax, eax
0x140007f9b  jns     loc_140008022
0x140007fa1  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140007fa7  lea     rax, WPP_RECORDER_INITIALIZED
0x140007fae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007fb5  setnz   r8b
0x140007fb9  and     dl, 8
0x140007fbc  jnz     short loc_140007FC3
0x140007fbe  test    r8b, r8b
0x140007fc1  jz      short loc_140008010
0x140007fc3  mov     r9, cs:WPP_GLOBAL_Control
0x140007fca  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007fd1  mov     [rsp+0E0h+var_90], ebx
0x140007fd5  mov     ecx, 213h
0x140007fda  mov     [rsp+0E0h+var_98], 141Ah
0x140007fe2  mov     [rsp+0E0h+var_A0], rax
0x140007fe7  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007fee  mov     r9, [r9+40h]
0x140007ff2  mov     [rsp+0E0h+var_A8], rax
0x140007ff7  mov     word ptr [rsp+0E0h+var_B0], 73h ; 's'
0x140007ffe  mov     dword ptr [rsp+0E0h+var_B8], 13h
0x140008006  mov     byte ptr [rsp+0E0h+FileObject], 2
0x14000800b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140008010  mov     edx, 9
0x140008015  mov     r8d, ebx
0x140008018  lea     ecx, [rdx-6]
0x14000801b  call    PrjfTelemetryTombstoneFailureOperation
0x140008020  jmp     short loc_14000804D
0x140008022  mov     rcx, r14; FileNameInformation
0x140008025  call    cs:__imp_FltReferenceFileNameInformation
0x14000802c  nop     dword ptr [rax+rax+00h]
0x140008031  mov     [r15+18h], rdi
0x140008035  xor     edi, edi
0x140008037  mov     [r15+28h], rsi
0x14000803b  xor     esi, esi
0x14000803d  mov     [r15+20h], r14
0x140008041  cmp     dword ptr [r12], 1
0x140008046  setz    al
0x140008049  mov     [r15+30h], al
0x14000804d  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x140008051  test    rcx, rcx
0x140008054  jz      short loc_140008062
0x140008056  call    cs:__imp_FltClose
0x14000805d  nop     dword ptr [rax+rax+00h]
0x140008062  test    rdi, rdi
0x140008065  jz      short loc_140008076
0x140008067  mov     rcx, rdi; Object
0x14000806a  call    cs:__imp_ObfDereferenceObject
0x140008071  nop     dword ptr [rax+rax+00h]
0x140008076  test    rsi, rsi
0x140008079  jz      short loc_14000808A
0x14000807b  mov     rcx, rsi; Context
0x14000807e  call    cs:__imp_FltReleaseContext
0x140008085  nop     dword ptr [rax+rax+00h]
0x14000808a  test    r12, r12
0x14000808d  jz      short loc_14000809E
0x14000808f  mov     rcx, r12; Context
0x140008092  call    cs:__imp_FltReleaseContext
0x140008099  nop     dword ptr [rax+rax+00h]
0x14000809e  mov     rcx, [rbp+47h+var_48]; Context
0x1400080a2  test    rcx, rcx
0x1400080a5  jz      short loc_1400080B3
0x1400080a7  call    cs:__imp_FltReleaseContext
0x1400080ae  nop     dword ptr [rax+rax+00h]
0x1400080b3  test    r13, r13
0x1400080b6  jz      short loc_1400080C7
0x1400080b8  mov     rcx, r13; Context
0x1400080bb  call    cs:__imp_FltReleaseContext
0x1400080c2  nop     dword ptr [rax+rax+00h]
0x1400080c7  mov     eax, ebx
0x1400080c9  add     rsp, 0A8h
0x1400080d0  pop     r15
0x1400080d2  pop     r14
0x1400080d4  pop     r13
0x1400080d6  pop     r12
0x1400080d8  pop     rdi
0x1400080d9  pop     rsi
0x1400080da  pop     rbx
0x1400080db  pop     rbp
0x1400080dc  retn
```
