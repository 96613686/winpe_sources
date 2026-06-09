# LuafvPreDirectoryControl

- ea: `0x140017cc0`
- end: `0x140017e57`
- name: `LuafvPreDirectoryControl`
- size: `407`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140014df0`
- `0x140017cc0`
- `0x14001860c`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140017dbe`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140017dbe`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140017d91`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140017d91`
- `FLTMGR!FltGetStreamHandleContext` at `0x140017d37`
- `FLTMGR!FltGetStreamHandleContext` at `0x140017d37`
- `FLTMGR!FltReleaseContext` at `0x140017d4b`
- `FLTMGR!FltReleaseContext` at `0x140017d4b`

## pseudocode

```c
__int64 __fastcall LuafvPreDirectoryControl(PFLT_CALLBACK_DATA Data, __int64 a2)
{
  struct _FILE_OBJECT *v3; // rdx
  PVOID FsContext; // rdi
  unsigned int v6; // ebx
  struct _FLT_INSTANCE *v8; // rcx
  signed int LowPart; // edx
  bool v10; // zf
  int v11; // ecx
  int StoreDirectory; // eax
  NTSTATUS v13; // ebx
  PFLT_CONTEXT Context; // [rsp+58h] [rbp+10h] BYREF

  Context = 0;
  v3 = *(struct _FILE_OBJECT **)(a2 + 32);
  if ( !v3 )
    goto LABEL_2;
  FsContext = v3->FsContext;
  if ( FsContext && *(_WORD *)FsContext == 30310 )
  {
    Context = (PFLT_CONTEXT)*((_QWORD *)FsContext + 32);
    goto LABEL_3;
  }
  v8 = *(struct _FLT_INSTANCE **)(a2 + 24);
  if ( v8 && FltGetStreamHandleContext(v8, v3, &Context) >= 0 )
  {
    FsContext = 0;
  }
  else
  {
LABEL_2:
    FsContext = 0;
    Context = 0;
  }
LABEL_3:
  v6 = 1;
  if ( !Context || Data->Iopb->MinorFunction != 1 || (*((_BYTE *)Context + 52) & 0xA) == 0 || IoGetTopLevelIrp() )
    goto LABEL_4;
  LowPart = Data->Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart > 60 )
  {
    if ( LowPart != 63 && LowPart != 78 && LowPart != 79 )
    {
      v11 = LowPart - 80;
      v10 = LowPart == 80;
      goto LABEL_28;
    }
  }
  else if ( LowPart != 60 && LowPart != 1 && LowPart != 2 && LowPart != 3 && LowPart != 12 )
  {
    v11 = LowPart - 37;
    v10 = LowPart == 37;
LABEL_28:
    if ( !v10 && v11 != 1 )
      goto LABEL_4;
  }
  if ( (*(_BYTE *)(*(_QWORD *)Context + 40LL) & 1) != 0 )
  {
    StoreDirectory = LuafvQueryStoreDirectory(*(PFLT_INSTANCE *)(a2 + 24));
    v13 = StoreDirectory;
    if ( StoreDirectory < 0 )
    {
      if ( StoreDirectory == -1073741773
        || (LuafvLogFileError((int)Data, 0, (const EVENT_DESCRIPTOR *)LuafvQueryDirectoryFailed, StoreDirectory),
            v13 == -1073741670) )
      {
        Data->IoStatus.Status = v13;
        Data->IoStatus.Information = 0;
      }
    }
    FltSetCallbackDataDirty(Data);
    v6 = 4;
  }
  else
  {
    v6 = LowPart == 12;
  }
LABEL_4:
  if ( !FsContext && Context )
    FltReleaseContext(Context);
  return v6;
}

```

## disassembly

```asm
0x140017cc0  push    rbx
0x140017cc2  push    rbp
0x140017cc3  push    rsi
0x140017cc4  push    rdi
0x140017cc5  sub     rsp, 28h
0x140017cc9  mov     rbp, rdx
0x140017ccc  mov     [rsp+48h+Context], 0
0x140017cd5  mov     rdx, [rdx+20h]; FileObject
0x140017cd9  mov     rsi, rcx
0x140017cdc  test    rdx, rdx
0x140017cdf  jnz     short loc_140017D16
0x140017ce1  xor     edi, edi
0x140017ce3  mov     [rsp+48h+Context], rdi
0x140017ce8  mov     rcx, [rsp+48h+Context]
0x140017ced  mov     ebx, 1
0x140017cf2  test    rcx, rcx
0x140017cf5  jnz     loc_140017DA7
0x140017cfb  test    rdi, rdi
0x140017cfe  jnz     short loc_140017D0A
0x140017d00  mov     rcx, [rsp+48h+Context]; Context
0x140017d05  test    rcx, rcx
0x140017d08  jnz     short loc_140017D4B
0x140017d0a  mov     eax, ebx
0x140017d0c  add     rsp, 28h
0x140017d10  pop     rdi
0x140017d11  pop     rsi
0x140017d12  pop     rbp
0x140017d13  pop     rbx
0x140017d14  retn
0x140017d16  mov     rdi, [rdx+18h]
0x140017d1a  test    rdi, rdi
0x140017d1d  jz      short loc_140017D29
0x140017d1f  mov     eax, 7666h
0x140017d24  cmp     [rdi], ax
0x140017d27  jz      short loc_140017D59
0x140017d29  mov     rcx, [rbp+18h]; Instance
0x140017d2d  test    rcx, rcx
0x140017d30  jz      short loc_140017CE1
0x140017d32  lea     r8, [rsp+48h+Context]; Context
0x140017d37  call    cs:__imp_FltGetStreamHandleContext
0x140017d3e  nop     dword ptr [rax+rax+00h]
0x140017d43  test    eax, eax
0x140017d45  js      short loc_140017CE1
0x140017d47  xor     edi, edi
0x140017d49  jmp     short loc_140017CE8
0x140017d4b  call    cs:__imp_FltReleaseContext
0x140017d52  nop     dword ptr [rax+rax+00h]
0x140017d57  jmp     short loc_140017D0A
0x140017d59  mov     rax, [rdi+100h]
0x140017d60  mov     [rsp+48h+Context], rax
0x140017d65  jmp     short loc_140017CE8
0x140017d67  mov     r9d, ebx
0x140017d6a  lea     r8, LuafvQueryDirectoryFailed
0x140017d71  xor     edx, edx
0x140017d73  mov     rcx, rsi
0x140017d76  call    LuafvLogFileError
0x140017d7b  cmp     ebx, 0C000009Ah
0x140017d81  jnz     short loc_140017D8E
0x140017d83  mov     [rsi+18h], ebx
0x140017d86  mov     qword ptr [rsi+20h], 0
0x140017d8e  mov     rcx, rsi; Data
0x140017d91  call    cs:__imp_FltSetCallbackDataDirty
0x140017d98  nop     dword ptr [rax+rax+00h]
0x140017d9d  mov     ebx, 4
0x140017da2  jmp     loc_140017CFB
0x140017da7  mov     rax, [rsi+10h]
0x140017dab  cmp     [rax+5], bl
0x140017dae  jnz     loc_140017CFB
0x140017db4  test    byte ptr [rcx+34h], 0Ah
0x140017db8  jz      loc_140017CFB
0x140017dbe  call    cs:__imp_IoGetTopLevelIrp
0x140017dc5  nop     dword ptr [rax+rax+00h]
0x140017dca  test    rax, rax
0x140017dcd  jnz     loc_140017CFB
0x140017dd3  mov     rax, [rsi+10h]
0x140017dd7  mov     edx, [rax+28h]
0x140017dda  cmp     edx, 3Ch ; '<'
0x140017ddd  jg      short loc_140017E06
0x140017ddf  jz      short loc_140017E16
0x140017de1  mov     ecx, edx
0x140017de3  sub     ecx, ebx
0x140017de5  jz      short loc_140017E16
0x140017de7  sub     ecx, ebx
0x140017de9  jz      short loc_140017E16
0x140017deb  sub     ecx, ebx
0x140017ded  jz      short loc_140017E16
0x140017def  sub     ecx, 9
0x140017df2  jz      short loc_140017E16
0x140017df4  sub     ecx, 19h
0x140017df7  jmp     short loc_140017DFB
0x140017df9  sub     ecx, ebx
0x140017dfb  jz      short loc_140017E16
0x140017dfd  cmp     ecx, ebx
0x140017dff  jz      short loc_140017E16
0x140017e01  jmp     loc_140017CFB
0x140017e06  mov     ecx, edx
0x140017e08  sub     ecx, 3Fh ; '?'
0x140017e0b  jz      short loc_140017E16
0x140017e0d  sub     ecx, 0Fh
0x140017e10  jz      short loc_140017E16
0x140017e12  sub     ecx, ebx
0x140017e14  jnz     short loc_140017DF9
0x140017e16  mov     rax, [rsp+48h+Context]
0x140017e1b  mov     r8, [rax]
0x140017e1e  test    [r8+28h], bl
0x140017e22  jz      short loc_140017E4A
0x140017e24  mov     rcx, [rbp+18h]; Instance
0x140017e28  mov     rdx, rsi
0x140017e2b  call    LuafvQueryStoreDirectory
0x140017e30  mov     ebx, eax
0x140017e32  test    eax, eax
0x140017e34  jns     loc_140017D8E
0x140017e3a  cmp     eax, 0C0000033h
0x140017e3f  jz      loc_140017D83
0x140017e45  jmp     loc_140017D67
0x140017e4a  xor     ebx, ebx
0x140017e4c  cmp     edx, 0Ch
0x140017e4f  setz    bl
0x140017e52  jmp     loc_140017CFB
```
