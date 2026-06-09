# LuafvPreDirectoryControl

- ea: `0x140017c70`
- end: `0x140017e07`
- name: `LuafvPreDirectoryControl`
- size: `407`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140014df0`
- `0x140017c70`
- `0x1400185bc`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140017d6e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140017d6e`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140017d41`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140017d41`
- `FLTMGR!FltGetStreamHandleContext` at `0x140017ce7`
- `FLTMGR!FltGetStreamHandleContext` at `0x140017ce7`
- `FLTMGR!FltReleaseContext` at `0x140017cfb`
- `FLTMGR!FltReleaseContext` at `0x140017cfb`

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
        || (LuafvLogFileError(Data, 0, LuafvQueryDirectoryFailed, (unsigned int)StoreDirectory), v13 == -1073741670) )
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
0x140017c70  push    rbx
0x140017c72  push    rbp
0x140017c73  push    rsi
0x140017c74  push    rdi
0x140017c75  sub     rsp, 28h
0x140017c79  mov     rbp, rdx
0x140017c7c  mov     [rsp+48h+Context], 0
0x140017c85  mov     rdx, [rdx+20h]; FileObject
0x140017c89  mov     rsi, rcx
0x140017c8c  test    rdx, rdx
0x140017c8f  jnz     short loc_140017CC6
0x140017c91  xor     edi, edi
0x140017c93  mov     [rsp+48h+Context], rdi
0x140017c98  mov     rcx, [rsp+48h+Context]
0x140017c9d  mov     ebx, 1
0x140017ca2  test    rcx, rcx
0x140017ca5  jnz     loc_140017D57
0x140017cab  test    rdi, rdi
0x140017cae  jnz     short loc_140017CBA
0x140017cb0  mov     rcx, [rsp+48h+Context]; Context
0x140017cb5  test    rcx, rcx
0x140017cb8  jnz     short loc_140017CFB
0x140017cba  mov     eax, ebx
0x140017cbc  add     rsp, 28h
0x140017cc0  pop     rdi
0x140017cc1  pop     rsi
0x140017cc2  pop     rbp
0x140017cc3  pop     rbx
0x140017cc4  retn
0x140017cc6  mov     rdi, [rdx+18h]
0x140017cca  test    rdi, rdi
0x140017ccd  jz      short loc_140017CD9
0x140017ccf  mov     eax, 7666h
0x140017cd4  cmp     [rdi], ax
0x140017cd7  jz      short loc_140017D09
0x140017cd9  mov     rcx, [rbp+18h]; Instance
0x140017cdd  test    rcx, rcx
0x140017ce0  jz      short loc_140017C91
0x140017ce2  lea     r8, [rsp+48h+Context]; Context
0x140017ce7  call    cs:__imp_FltGetStreamHandleContext
0x140017cee  nop     dword ptr [rax+rax+00h]
0x140017cf3  test    eax, eax
0x140017cf5  js      short loc_140017C91
0x140017cf7  xor     edi, edi
0x140017cf9  jmp     short loc_140017C98
0x140017cfb  call    cs:__imp_FltReleaseContext
0x140017d02  nop     dword ptr [rax+rax+00h]
0x140017d07  jmp     short loc_140017CBA
0x140017d09  mov     rax, [rdi+100h]
0x140017d10  mov     [rsp+48h+Context], rax
0x140017d15  jmp     short loc_140017C98
0x140017d17  mov     r9d, ebx
0x140017d1a  lea     r8, LuafvQueryDirectoryFailed
0x140017d21  xor     edx, edx
0x140017d23  mov     rcx, rsi
0x140017d26  call    LuafvLogFileError
0x140017d2b  cmp     ebx, 0C000009Ah
0x140017d31  jnz     short loc_140017D3E
0x140017d33  mov     [rsi+18h], ebx
0x140017d36  mov     qword ptr [rsi+20h], 0
0x140017d3e  mov     rcx, rsi; Data
0x140017d41  call    cs:__imp_FltSetCallbackDataDirty
0x140017d48  nop     dword ptr [rax+rax+00h]
0x140017d4d  mov     ebx, 4
0x140017d52  jmp     loc_140017CAB
0x140017d57  mov     rax, [rsi+10h]
0x140017d5b  cmp     [rax+5], bl
0x140017d5e  jnz     loc_140017CAB
0x140017d64  test    byte ptr [rcx+34h], 0Ah
0x140017d68  jz      loc_140017CAB
0x140017d6e  call    cs:__imp_IoGetTopLevelIrp
0x140017d75  nop     dword ptr [rax+rax+00h]
0x140017d7a  test    rax, rax
0x140017d7d  jnz     loc_140017CAB
0x140017d83  mov     rax, [rsi+10h]
0x140017d87  mov     edx, [rax+28h]
0x140017d8a  cmp     edx, 3Ch ; '<'
0x140017d8d  jg      short loc_140017DB6
0x140017d8f  jz      short loc_140017DC6
0x140017d91  mov     ecx, edx
0x140017d93  sub     ecx, ebx
0x140017d95  jz      short loc_140017DC6
0x140017d97  sub     ecx, ebx
0x140017d99  jz      short loc_140017DC6
0x140017d9b  sub     ecx, ebx
0x140017d9d  jz      short loc_140017DC6
0x140017d9f  sub     ecx, 9
0x140017da2  jz      short loc_140017DC6
0x140017da4  sub     ecx, 19h
0x140017da7  jmp     short loc_140017DAB
0x140017da9  sub     ecx, ebx
0x140017dab  jz      short loc_140017DC6
0x140017dad  cmp     ecx, ebx
0x140017daf  jz      short loc_140017DC6
0x140017db1  jmp     loc_140017CAB
0x140017db6  mov     ecx, edx
0x140017db8  sub     ecx, 3Fh ; '?'
0x140017dbb  jz      short loc_140017DC6
0x140017dbd  sub     ecx, 0Fh
0x140017dc0  jz      short loc_140017DC6
0x140017dc2  sub     ecx, ebx
0x140017dc4  jnz     short loc_140017DA9
0x140017dc6  mov     rax, [rsp+48h+Context]
0x140017dcb  mov     r8, [rax]
0x140017dce  test    [r8+28h], bl
0x140017dd2  jz      short loc_140017DFA
0x140017dd4  mov     rcx, [rbp+18h]; Instance
0x140017dd8  mov     rdx, rsi
0x140017ddb  call    LuafvQueryStoreDirectory
0x140017de0  mov     ebx, eax
0x140017de2  test    eax, eax
0x140017de4  jns     loc_140017D3E
0x140017dea  cmp     eax, 0C0000033h
0x140017def  jz      loc_140017D33
0x140017df5  jmp     loc_140017D17
0x140017dfa  xor     ebx, ebx
0x140017dfc  cmp     edx, 0Ch
0x140017dff  setz    bl
0x140017e02  jmp     loc_140017CAB
```
