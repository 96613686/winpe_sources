# PrjfProcessFileDirectoryStatus

- ea: `0x140042cf0`
- end: `0x140042ea6`
- name: `PrjfProcessFileDirectoryStatus`
- size: `438`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140022320`

## callees

- `0x14000d128`
- `0x14003be88`
- `0x140042cf0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140042e87`
- `ntoskrnl!ObfDereferenceObject` at `0x140042e87`
- `FLTMGR!FltParseFileNameInformation` at `0x140042d55`
- `FLTMGR!FltParseFileNameInformation` at `0x140042d55`
- `FLTMGR!FltClose` at `0x140042e71`
- `FLTMGR!FltClose` at `0x140042e71`

## pseudocode

```c
__int64 __fastcall PrjfProcessFileDirectoryStatus(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  int v8; // edx
  int v9; // edi
  int v10; // r8d
  __int64 v11; // [rsp+20h] [rbp-68h]
  PVOID Object; // [rsp+60h] [rbp-28h] BYREF
  char v13; // [rsp+90h] [rbp+8h] BYREF
  HANDLE FileHandle; // [rsp+A8h] [rbp+20h] BYREF

  FileHandle = 0;
  Object = 0;
  v13 = 0;
  v6 = *(_DWORD *)(a1 + 24);
  if ( v6 != -1073741638 && v6 != -1073741565 && (v6 != -1073741771 || *(_BYTE *)(*(_QWORD *)(a1 + 16) + 35LL) != 2)
    || (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL) & 0x2000) != 0 )
  {
    return 0;
  }
  v9 = FltParseFileNameInformation(*(PFLT_FILE_NAME_INFORMATION *)(a3 + 48));
  if ( v9 >= 0 )
  {
    v9 = PrjfOpenAsReparsePoint(
           *(_QWORD *)(a3 + 48) + 8LL,
           0,
           *(struct _FLT_INSTANCE **)(a2 + 24),
           128,
           v11,
           &FileHandle,
           (PFILE_OBJECT *)&Object,
           0,
           0,
           0,
           &v13,
           0);
    if ( v9 >= 0 && v13 )
    {
      *(_DWORD *)(a1 + 24) = 260;
      *(_QWORD *)(a1 + 32) = 2684354594LL;
    }
    else
    {
      v9 = 0;
    }
  }
  else if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = BYTE2(xmmword_14001A3D0) & 8;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      531,
      v8,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      19,
      32,
      (__int64)&WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
      244,
      v9);
  }
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140042cf0  mov     rax, rsp
0x140042cf3  mov     [rax+10h], rbx
0x140042cf7  push    rbp
0x140042cf8  push    rsi
0x140042cf9  push    rdi
0x140042cfa  sub     rsp, 70h
0x140042cfe  mov     qword ptr [rax+20h], 0
0x140042d06  mov     rsi, r8
0x140042d09  mov     qword ptr [rax-28h], 0
0x140042d11  mov     rbp, rdx
0x140042d14  mov     byte ptr [rax+8], 0
0x140042d18  mov     rbx, rcx
0x140042d1b  mov     eax, [rcx+18h]
0x140042d1e  cmp     eax, 0C00000BAh
0x140042d23  jz      short loc_140042D3D
0x140042d25  cmp     eax, 0C0000103h
0x140042d2a  jz      short loc_140042D3D
0x140042d2c  cmp     eax, 0C0000035h
0x140042d31  jnz     short loc_140042D4A
0x140042d33  mov     rax, [rcx+10h]
0x140042d37  cmp     byte ptr [rax+23h], 2
0x140042d3b  jnz     short loc_140042D4A
0x140042d3d  mov     rax, [rcx+10h]
0x140042d41  test    dword ptr [rax+20h], 2000h
0x140042d48  jz      short loc_140042D51
0x140042d4a  xor     eax, eax
0x140042d4c  jmp     loc_140042E95
0x140042d51  mov     rcx, [r8+30h]; FileNameInformation
0x140042d55  call    cs:__imp_FltParseFileNameInformation
0x140042d5c  nop     dword ptr [rax+rax+00h]
0x140042d61  mov     edi, eax
0x140042d63  test    eax, eax
0x140042d65  jns     short loc_140042DDF
0x140042d67  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140042d6d  lea     rax, WPP_RECORDER_INITIALIZED
0x140042d74  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140042d7b  setnz   r8b
0x140042d7f  and     dl, 8
0x140042d82  jnz     short loc_140042D8D
0x140042d84  test    r8b, r8b
0x140042d87  jz      loc_140042E64
0x140042d8d  mov     r9, cs:WPP_GLOBAL_Control
0x140042d94  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140042d9b  mov     dword ptr [rsp+88h+var_38], edi
0x140042d9f  mov     ecx, 213h
0x140042da4  mov     dword ptr [rsp+88h+var_40], 5F4h
0x140042dac  mov     [rsp+88h+var_48], rax
0x140042db1  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140042db8  mov     r9, [r9+40h]
0x140042dbc  mov     [rsp+88h+var_50], rax
0x140042dc1  mov     word ptr [rsp+88h+var_58], 20h ; ' '
0x140042dc8  mov     dword ptr [rsp+88h+var_60], 13h
0x140042dd0  mov     byte ptr [rsp+88h+var_68], 2
0x140042dd5  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140042dda  jmp     loc_140042E64
0x140042ddf  mov     rcx, [rsi+30h]
0x140042de3  lea     rax, [rsp+88h+arg_0]
0x140042deb  mov     r8, [rbp+18h]
0x140042def  add     rcx, 8
0x140042df3  mov     [rsp+88h+var_30], 0
0x140042dfc  mov     r9d, 80h
0x140042e02  mov     [rsp+88h+var_38], rax
0x140042e07  xor     edx, edx
0x140042e09  mov     [rsp+88h+var_40], 0
0x140042e12  lea     rax, [rsp+88h+Object]
0x140042e17  mov     [rsp+88h+var_48], 0
0x140042e20  mov     [rsp+88h+var_50], 0
0x140042e29  mov     [rsp+88h+var_58], rax
0x140042e2e  lea     rax, [rsp+88h+FileHandle]
0x140042e36  mov     [rsp+88h+var_60], rax
0x140042e3b  call    PrjfOpenAsReparsePoint
0x140042e40  mov     edi, eax
0x140042e42  test    eax, eax
0x140042e44  js      short loc_140042E62
0x140042e46  cmp     [rsp+88h+arg_0], 0
0x140042e4e  jz      short loc_140042E62
0x140042e50  mov     eax, 0A0000022h
0x140042e55  mov     dword ptr [rbx+18h], 104h
0x140042e5c  mov     [rbx+20h], rax
0x140042e60  jmp     short loc_140042E64
0x140042e62  xor     edi, edi
0x140042e64  mov     rcx, [rsp+88h+FileHandle]; FileHandle
0x140042e6c  test    rcx, rcx
0x140042e6f  jz      short loc_140042E7D
0x140042e71  call    cs:__imp_FltClose
0x140042e78  nop     dword ptr [rax+rax+00h]
0x140042e7d  mov     rcx, [rsp+88h+Object]; Object
0x140042e82  test    rcx, rcx
0x140042e85  jz      short loc_140042E93
0x140042e87  call    cs:__imp_ObfDereferenceObject
0x140042e8e  nop     dword ptr [rax+rax+00h]
0x140042e93  mov     eax, edi
0x140042e95  mov     rbx, [rsp+88h+arg_8]
0x140042e9d  add     rsp, 70h
0x140042ea1  pop     rdi
0x140042ea2  pop     rsi
0x140042ea3  pop     rbp
0x140042ea4  retn
```
