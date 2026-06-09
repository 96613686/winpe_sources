# SdbpQueryAppCompatFlagsByExeID

- ea: `0x140ac64e4`
- end: `0x140ac65cd`
- name: `SdbpQueryAppCompatFlagsByExeID`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140ae3404`

## callees

- `0x1406daa70`
- `0x14097d158`
- `0x140ac64e4`
- `0x140ac65d4`
- `0x140ac67cc`

## string_xrefs

- `0x140ac650f`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x140ac65a3`: `AslRegistryGetUInt32 failed for key: '%ws' [%x]`
- `0x140ac6580`: `SdbpQueryAppCompatFlagsByExeID`
- `0x140ac65af`: `SdbpQueryAppCompatFlagsByExeID`
- `0x140ac6579`: `AslRegistryGetKey failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpQueryAppCompatFlagsByExeID(__int64 a1, __int64 a2, int a3, _DWORD *a4)
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
  Key = AslRegistryGetKey(&Handle, L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 0x80000100, a3);
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
0x140ac64e4  mov     rax, rsp
0x140ac64e7  mov     [rax+10h], rbx
0x140ac64eb  mov     [rax+8], rcx
0x140ac64ef  push    rbp
0x140ac64f0  push    rsi
0x140ac64f1  push    r14
0x140ac64f3  sub     rsp, 30h
0x140ac64f7  mov     r14, r9
0x140ac64fa  mov     dword ptr [rax+8], 0
0x140ac6501  mov     r9d, r8d
0x140ac6504  mov     qword ptr [rax+20h], 0
0x140ac650c  mov     rsi, rdx
0x140ac650f  lea     rbp, aSoftwareMicros_0; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x140ac6516  mov     r8d, 80000100h
0x140ac651c  lea     rcx, [rax+20h]
0x140ac6520  mov     rdx, rbp
0x140ac6523  call    AslRegistryGetKey
0x140ac6528  mov     ebx, eax
0x140ac652a  test    eax, eax
0x140ac652c  js      short loc_140AC6568
0x140ac652e  mov     rdx, [rsp+48h+Handle]
0x140ac6533  lea     rcx, [rsp+48h+arg_0]
0x140ac6538  mov     r8, rsi
0x140ac653b  call    AslRegistryGetUInt32
0x140ac6540  mov     ebx, eax
0x140ac6542  test    eax, eax
0x140ac6544  js      short loc_140AC6592
0x140ac6546  xor     ebx, ebx
0x140ac6548  cmp     [rsp+48h+Handle], 0
0x140ac654e  mov     eax, [rsp+48h+arg_0]
0x140ac6552  mov     [r14], eax
0x140ac6555  jnz     short loc_140AC65C1
0x140ac6557  mov     eax, ebx
0x140ac6559  mov     rbx, [rsp+48h+arg_8]
0x140ac655e  add     rsp, 30h
0x140ac6562  pop     r14
0x140ac6564  pop     rsi
0x140ac6565  pop     rbp
0x140ac6566  retn
0x140ac6568  cmp     eax, 0C0000034h
0x140ac656d  jz      short loc_140AC6548
0x140ac656f  mov     r8d, 40h ; '@'
0x140ac6575  mov     dword ptr [rsp+48h+var_28], eax
0x140ac6579  lea     r9, aAslregistryget_8; "AslRegistryGetKey failed [%x]"
0x140ac6580  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x140ac6587  lea     ecx, [r8-3Fh]
0x140ac658b  call    AslLogCallPrintf
0x140ac6590  jmp     short loc_140AC6548
0x140ac6592  cmp     eax, 0C0000034h
0x140ac6597  jz      short loc_140AC6548
0x140ac6599  mov     r8d, 4Bh ; 'K'
0x140ac659f  mov     [rsp+48h+var_20], eax
0x140ac65a3  lea     r9, aAslregistryget_7; "AslRegistryGetUInt32 failed for key: '%"...
0x140ac65aa  mov     [rsp+48h+var_28], rbp
0x140ac65af  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x140ac65b6  lea     ecx, [r8-4Ah]
0x140ac65ba  call    AslLogCallPrintf
0x140ac65bf  jmp     short loc_140AC6548
0x140ac65c1  mov     rcx, [rsp+48h+Handle]; Handle
0x140ac65c6  call    ZwClose
0x140ac65cb  jmp     short loc_140AC6557
```
