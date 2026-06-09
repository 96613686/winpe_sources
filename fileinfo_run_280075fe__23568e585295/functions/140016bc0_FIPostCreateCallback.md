# FIPostCreateCallback

- ea: `0x140016bc0`
- end: `0x140016dab`
- name: `FIPostCreateCallback`
- size: `491`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x140001570`
- `0x140001790`
- `0x140001da0`
- `0x140001f20`
- `0x1400028c8`
- `0x1400033f0`
- `0x14000e5a0`
- `0x140012bd8`
- `0x1400138d4`
- `0x140014520`
- `0x140014bf0`
- `0x140016bc0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140016d4f`
- `FLTMGR!FltReleaseContext` at `0x140016d4f`

## pseudocode

```c
__int64 __fastcall FIPostCreateCallback(PFLT_CALLBACK_DATA CallbackData, _QWORD *a2, __int64 a3, char a4)
{
  NTSTATUS Status; // eax
  FLT_FILE_NAME_OPTIONS v9; // eax
  int v10; // eax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rbp
  _DWORD *v12; // rsi
  ULONG Options; // ebp
  _QWORD v15[9]; // [rsp+20h] [rbp-48h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp+8h] BYREF
  int v17; // [rsp+88h] [rbp+20h] BYREF

  v15[0] = a2[2];
  v15[1] = a2[3];
  v15[2] = a2[4];
  Context = 0;
  if ( *(_QWORD *)(qword_140009A00 + 24) )
    FIETWLogOperationEnd(CallbackData);
  if ( (a4 & 1) == 0 )
  {
    Status = CallbackData->IoStatus.Status;
    if ( Status >= 0 && Status != 260 && Status != 264 )
    {
      if ( *(_QWORD *)(qword_140009A00 + 16)
        && (CallbackData->Iopb->Parameters.Create.Options & 0xFF000000) != 0x1000000
        && CallbackData->IoStatus.Information != 1 )
      {
        v9 = FIGetFileNameOptions(a2[4]);
        FIETWLogFileCreate(CallbackData, (__int64)a2, v9, 1102);
      }
      v17 = 0;
      v10 = FIStreamGet(CallbackData, v15, &Context, &v17);
      Iopb = CallbackData->Iopb;
      v12 = Context;
      if ( v10 >= 0 )
      {
        Options = Iopb->Parameters.Create.Options;
        if ( (Options & 0x1000) != 0 )
        {
          FILockExclusiveAcquire((char *)Context + 40);
          FIStreamVolatileBitFieldBitSet(v12, 5, 1);
          FILockExclusiveRelease(v12 + 10);
        }
        if ( dword_140009A70 == 1 )
        {
          if ( (v12[14] & 1) != 0 )
          {
            FIStreamGetInfo(CallbackData);
          }
          else if ( HIBYTE(Options) - 4 <= 1u )
          {
            FITruncationLog(v12, 2, 0);
          }
        }
      }
      else if ( (Iopb->OperationFlags & 2) != 0 && (Iopb->Parameters.Create.Options & 0x1000) != 0 )
      {
        FIVolumeAddPagefile(0, v15, CallbackData);
      }
      if ( v12 )
        FltReleaseContext(v12);
    }
  }
  if ( (*(_DWORD *)(a2[4] + 80LL) & 0x400000) != 0
    && ((CallbackData->Iopb->Parameters.Create.ShareAccess & 6) == 0 || (*(_DWORD *)(a2[4] + 80LL) & 0x800) != 0) )
  {
    _InterlockedDecrement(&dword_1400099F8);
  }
  if ( (a3 & 7) != 0 )
    FIPfFileFSOpPostCallbackCleanup(a3);
  return 0;
}

```

## disassembly

```asm
0x140016bc0  mov     r11, rsp
0x140016bc3  mov     [r11+10h], rbx
0x140016bc7  push    rbp
0x140016bc8  push    rsi
0x140016bc9  push    rdi
0x140016bca  push    r14
0x140016bcc  push    r15
0x140016bce  sub     rsp, 40h
0x140016bd2  mov     rax, [rdx+10h]
0x140016bd6  mov     ebx, r9d
0x140016bd9  mov     [r11-48h], rax
0x140016bdd  mov     r15, r8
0x140016be0  mov     rax, [rdx+18h]
0x140016be4  mov     r14, rdx
0x140016be7  mov     [r11-40h], rax
0x140016beb  mov     rdi, rcx
0x140016bee  mov     rax, [rdx+20h]
0x140016bf2  mov     [r11-38h], rax
0x140016bf6  mov     rax, cs:qword_140009A00
0x140016bfd  mov     qword ptr [r11+8], 0
0x140016c05  mov     r9, [rax+18h]
0x140016c09  test    r9, r9
0x140016c0c  jz      short loc_140016C13
0x140016c0e  call    FIETWLogOperationEnd
0x140016c13  test    bl, 1
0x140016c16  jnz     loc_140016D5B
0x140016c1c  mov     eax, [rdi+18h]
0x140016c1f  test    eax, eax
0x140016c21  js      loc_140016D5B
0x140016c27  cmp     eax, 104h
0x140016c2c  jz      loc_140016D5B
0x140016c32  cmp     eax, 108h
0x140016c37  jz      loc_140016D5B
0x140016c3d  mov     rax, cs:qword_140009A00
0x140016c44  mov     rcx, [rax+10h]
0x140016c48  test    rcx, rcx
0x140016c4b  jz      short loc_140016C89
0x140016c4d  mov     rax, [rdi+10h]
0x140016c51  mov     ecx, [rax+20h]
0x140016c54  and     ecx, 0FF000000h
0x140016c5a  cmp     ecx, 1000000h
0x140016c60  jz      short loc_140016C89
0x140016c62  cmp     qword ptr [rdi+20h], 1
0x140016c67  jz      short loc_140016C89
0x140016c69  mov     rcx, [r14+20h]
0x140016c6d  mov     ebx, 44Eh
0x140016c72  call    FIGetFileNameOptions
0x140016c77  mov     r8d, eax
0x140016c7a  movzx   r9d, bx
0x140016c7e  mov     rdx, r14
0x140016c81  mov     rcx, rdi
0x140016c84  call    FIETWLogFileCreate
0x140016c89  lea     r9, [rsp+68h+arg_18]
0x140016c91  mov     [rsp+68h+arg_18], 0
0x140016c9c  lea     r8, [rsp+68h+Context]
0x140016ca1  mov     rcx, rdi
0x140016ca4  lea     rdx, [rsp+68h+var_48]
0x140016ca9  call    FIStreamGet
0x140016cae  mov     rbp, [rdi+10h]
0x140016cb2  mov     rsi, [rsp+68h+Context]
0x140016cb7  test    eax, eax
0x140016cb9  jns     short loc_140016CDF
0x140016cbb  test    byte ptr [rbp+6], 2
0x140016cbf  jz      loc_140016D47
0x140016cc5  test    dword ptr [rbp+20h], 1000h
0x140016ccc  jz      short loc_140016D47
0x140016cce  mov     r8, rdi
0x140016cd1  lea     rdx, [rsp+68h+var_48]
0x140016cd6  xor     ecx, ecx
0x140016cd8  call    FIVolumeAddPagefile
0x140016cdd  jmp     short loc_140016D47
0x140016cdf  mov     ebp, [rbp+20h]
0x140016ce2  bt      ebp, 0Ch
0x140016ce6  jnb     short loc_140016D0B
0x140016ce8  lea     rcx, [rsi+28h]
0x140016cec  call    FILockExclusiveAcquire
0x140016cf1  mov     edx, 5
0x140016cf6  mov     rcx, rsi
0x140016cf9  lea     r8d, [rdx-4]
0x140016cfd  call    FIStreamVolatileBitFieldBitSet
0x140016d02  lea     rcx, [rsi+28h]
0x140016d06  call    FILockExclusiveRelease
0x140016d0b  cmp     cs:dword_140009A70, 1
0x140016d12  jnz     short loc_140016D47
0x140016d14  mov     eax, [rsi+38h]
0x140016d17  test    al, 1
0x140016d19  jz      short loc_140016D2D
0x140016d1b  mov     r8, rsi
0x140016d1e  lea     rdx, [rsp+68h+var_48]
0x140016d23  mov     rcx, rdi; CallbackData
0x140016d26  call    FIStreamGetInfo
0x140016d2b  jmp     short loc_140016D47
0x140016d2d  shr     ebp, 18h
0x140016d30  sub     ebp, 4
0x140016d33  cmp     ebp, 1
0x140016d36  ja      short loc_140016D47
0x140016d38  xor     r8d, r8d
0x140016d3b  mov     rcx, rsi
0x140016d3e  lea     edx, [r8+2]
0x140016d42  call    FITruncationLog
0x140016d47  test    rsi, rsi
0x140016d4a  jz      short loc_140016D5B
0x140016d4c  mov     rcx, rsi; Context
0x140016d4f  call    cs:__imp_FltReleaseContext
0x140016d56  nop     dword ptr [rax+rax+00h]
0x140016d5b  mov     rax, [rdi+10h]
0x140016d5f  movzx   edx, word ptr [rax+2Ah]
0x140016d63  mov     rax, [r14+20h]
0x140016d67  mov     ecx, [rax+50h]
0x140016d6a  bt      ecx, 16h
0x140016d6e  jnb     short loc_140016D89
0x140016d70  test    dl, 6
0x140016d73  jz      short loc_140016D82
0x140016d75  mov     rax, [r14+20h]
0x140016d79  mov     ecx, [rax+50h]
0x140016d7c  bt      ecx, 0Bh
0x140016d80  jnb     short loc_140016D89
0x140016d82  lock dec cs:dword_1400099F8
0x140016d89  test    r15b, 7
0x140016d8d  jz      short loc_140016D97
0x140016d8f  mov     rcx, r15
0x140016d92  call    FIPfFileFSOpPostCallbackCleanup
0x140016d97  mov     rbx, [rsp+68h+arg_8]
0x140016d9c  xor     eax, eax
0x140016d9e  add     rsp, 40h
0x140016da2  pop     r15
0x140016da4  pop     r14
0x140016da6  pop     rdi
0x140016da7  pop     rsi
0x140016da8  pop     rbp
0x140016da9  retn
```
