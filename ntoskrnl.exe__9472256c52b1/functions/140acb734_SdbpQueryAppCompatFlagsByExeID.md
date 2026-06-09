# SdbpQueryAppCompatFlagsByExeID

- ea: `0x140acb734`
- end: `0x140acb81d`
- name: `SdbpQueryAppCompatFlagsByExeID`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140ae90d4`

## callees

- `0x1406dd5c0`
- `0x1408c2f88`
- `0x140acb734`
- `0x140acb824`
- `0x140acba1c`

## string_xrefs

- `0x140acb75f`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x140acb7d0`: `SdbpQueryAppCompatFlagsByExeID`
- `0x140acb7ff`: `SdbpQueryAppCompatFlagsByExeID`
- `0x140acb7f3`: `AslRegistryGetUInt32 failed for key: '%ws' [%x]`
- `0x140acb7c9`: `AslRegistryGetKey failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpQueryAppCompatFlagsByExeID(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  int Key; // eax
  unsigned int v7; // ebx
  int UInt32; // eax
  bool v9; // zf
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+54h] [rbp+Ch]
  HANDLE Handle; // [rsp+68h] [rbp+20h] BYREF

  v12 = HIDWORD(a1);
  v11 = 0;
  Handle = 0;
  Key = AslRegistryGetKey(
          &Handle,
          L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
          2147483904LL,
          a3);
  v7 = Key;
  if ( Key < 0 )
  {
    if ( Key != -1073741772 )
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpQueryAppCompatFlagsByExeID",
        64,
        (unsigned int)"AslRegistryGetKey failed [%x]");
  }
  else
  {
    UInt32 = AslRegistryGetUInt32(&v11, Handle, a2);
    v7 = UInt32;
    if ( UInt32 < 0 )
    {
      if ( UInt32 != -1073741772 )
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpQueryAppCompatFlagsByExeID",
          75,
          (unsigned int)"AslRegistryGetUInt32 failed for key: '%ws' [%x]");
    }
    else
    {
      v7 = 0;
    }
  }
  v9 = Handle == 0;
  *a4 = v11;
  if ( !v9 )
    ZwClose(Handle);
  return v7;
}

```

## disassembly

```asm
0x140acb734  mov     rax, rsp
0x140acb737  mov     [rax+10h], rbx
0x140acb73b  mov     [rax+8], rcx
0x140acb73f  push    rbp
0x140acb740  push    rsi
0x140acb741  push    r14
0x140acb743  sub     rsp, 30h
0x140acb747  mov     r14, r9
0x140acb74a  mov     dword ptr [rax+8], 0
0x140acb751  mov     r9d, r8d
0x140acb754  mov     qword ptr [rax+20h], 0
0x140acb75c  mov     rsi, rdx
0x140acb75f  lea     rbp, aSoftwareMicros_0; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x140acb766  mov     r8d, 80000100h
0x140acb76c  lea     rcx, [rax+20h]
0x140acb770  mov     rdx, rbp
0x140acb773  call    AslRegistryGetKey
0x140acb778  mov     ebx, eax
0x140acb77a  test    eax, eax
0x140acb77c  js      short loc_140ACB7B8
0x140acb77e  mov     rdx, [rsp+48h+Handle]
0x140acb783  lea     rcx, [rsp+48h+arg_0]
0x140acb788  mov     r8, rsi
0x140acb78b  call    AslRegistryGetUInt32
0x140acb790  mov     ebx, eax
0x140acb792  test    eax, eax
0x140acb794  js      short loc_140ACB7E2
0x140acb796  xor     ebx, ebx
0x140acb798  cmp     [rsp+48h+Handle], 0
0x140acb79e  mov     eax, [rsp+48h+arg_0]
0x140acb7a2  mov     [r14], eax
0x140acb7a5  jnz     short loc_140ACB811
0x140acb7a7  mov     eax, ebx
0x140acb7a9  mov     rbx, [rsp+48h+arg_8]
0x140acb7ae  add     rsp, 30h
0x140acb7b2  pop     r14
0x140acb7b4  pop     rsi
0x140acb7b5  pop     rbp
0x140acb7b6  retn
0x140acb7b8  cmp     eax, 0C0000034h
0x140acb7bd  jz      short loc_140ACB798
0x140acb7bf  mov     r8d, 40h ; '@'
0x140acb7c5  mov     dword ptr [rsp+48h+var_28], eax
0x140acb7c9  lea     r9, aAslregistryget_8; "AslRegistryGetKey failed [%x]"
0x140acb7d0  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x140acb7d7  lea     ecx, [r8-3Fh]
0x140acb7db  call    AslLogCallPrintf
0x140acb7e0  jmp     short loc_140ACB798
0x140acb7e2  cmp     eax, 0C0000034h
0x140acb7e7  jz      short loc_140ACB798
0x140acb7e9  mov     r8d, 4Bh ; 'K'
0x140acb7ef  mov     [rsp+48h+var_20], eax
0x140acb7f3  lea     r9, aAslregistryget_7; "AslRegistryGetUInt32 failed for key: '%"...
0x140acb7fa  mov     [rsp+48h+var_28], rbp
0x140acb7ff  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x140acb806  lea     ecx, [r8-4Ah]
0x140acb80a  call    AslLogCallPrintf
0x140acb80f  jmp     short loc_140ACB798
0x140acb811  mov     rcx, [rsp+48h+Handle]; Handle
0x140acb816  call    ZwClose
0x140acb81b  jmp     short loc_140ACB7A7
```
