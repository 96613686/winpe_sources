# SetRepositoryCheckOnStartup(bool)

- ea: `0x18003d050`
- end: `0x18003d17c`
- name: `?SetRepositoryCheckOnStartup@@YAJ_N@Z`
- size: `300`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c950`
- `0x18002fd70`

## callees

- `0x1800012b8`
- `0x180024ca0`
- `0x18003d050`
- `0x180043fa0`
- `0x180044208`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003d09d`
- `wbemcomn!GetMemLogObject` at `0x18003d135`
- `wbemcomn!GetMemLogObject` at `0x18003d09d`
- `wbemcomn!GetMemLogObject` at `0x18003d135`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003d0a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003d140`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003d0a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003d140`

## pseudocode

```c
__int64 __fastcall SetRepositoryCheckOnStartup(unsigned __int8 a1, __int64 a2, int a3)
{
  int v3; // edi
  int v4; // eax
  int v5; // r8d
  signed int v6; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  bool v11; // sf
  CMemoryLog *v12; // rax
  int v13; // [rsp+48h] [rbp+10h] BYREF
  __int64 v14; // [rsp+50h] [rbp+18h] BYREF

  v3 = a1;
  v14 = 0;
  v4 = DLRegOpenKeyExW(-2147483646, (unsigned int)L"SOFTWARE\\Microsoft\\Wbem\\CIMOM", a3, 131078, (__int64)&v14);
  v6 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v6 = (unsigned __int16)v4 | 0x80070000;
    if ( v6 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v6);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v6;
    }
    v9 = 12;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, (unsigned int)v6);
    return (unsigned int)v6;
  }
  v13 = v3;
  v6 = DLRegSetValueExW(v14, (unsigned int)L"CheckRepositoryOnNextStartup", v5, 4, (__int64)&v13, 4);
  DLRegCloseKey(v14);
  v11 = v6 < 0;
  if ( v6 )
  {
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v11 = v6 < 0;
    }
    if ( v11 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, v6);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v6;
    }
    v9 = 13;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x18003d050  mov     r11, rsp
0x18003d053  mov     [r11+8], rbx
0x18003d057  push    rdi
0x18003d058  sub     rsp, 30h
0x18003d05c  movzx   edi, cl
0x18003d05f  lea     rax, [r11+18h]
0x18003d063  mov     rcx, 0FFFFFFFF80000002h
0x18003d06a  mov     [r11-18h], rax
0x18003d06e  mov     r9d, 20006h
0x18003d074  mov     qword ptr [r11+18h], 0
0x18003d07c  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Wbem\\CIMOM"
0x18003d083  call    DLRegOpenKeyExW
0x18003d088  mov     ebx, eax
0x18003d08a  test    eax, eax
0x18003d08c  jz      short loc_18003D0EC
0x18003d08e  jle     short loc_18003D099
0x18003d090  movzx   ebx, ax
0x18003d093  or      ebx, 80070000h
0x18003d099  test    ebx, ebx
0x18003d09b  jns     short loc_18003D0AE
0x18003d09d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003d0a3  mov     rcx, rax
0x18003d0a6  mov     edx, ebx
0x18003d0a8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d0ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0b5  lea     rax, WPP_GLOBAL_Control
0x18003d0bc  cmp     rcx, rax
0x18003d0bf  jz      short loc_18003D0E5
0x18003d0c1  test    byte ptr [rcx+1Ch], 1
0x18003d0c5  jz      short loc_18003D0E5
0x18003d0c7  cmp     byte ptr [rcx+19h], 2
0x18003d0cb  jb      short loc_18003D0E5
0x18003d0cd  mov     edx, 0Ch
0x18003d0d2  mov     rcx, [rcx+10h]
0x18003d0d6  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003d0dd  mov     r9d, ebx
0x18003d0e0  call    WPP_SF_d
0x18003d0e5  mov     eax, ebx
0x18003d0e7  jmp     loc_18003D171
0x18003d0ec  mov     rcx, [rsp+38h+arg_10]
0x18003d0f1  lea     rax, [rsp+38h+arg_8]
0x18003d0f6  mov     r9d, 4
0x18003d0fc  mov     [rsp+38h+arg_8], edi
0x18003d100  mov     [rsp+38h+var_10], r9d
0x18003d105  lea     rdx, aCheckrepositor; "CheckRepositoryOnNextStartup"
0x18003d10c  mov     [rsp+38h+var_18], rax
0x18003d111  call    DLRegSetValueExW
0x18003d116  mov     rcx, [rsp+38h+arg_10]
0x18003d11b  mov     ebx, eax
0x18003d11d  call    DLRegCloseKey
0x18003d122  test    ebx, ebx
0x18003d124  jz      short loc_18003D16F
0x18003d126  jle     short loc_18003D133
0x18003d128  movzx   ebx, bx
0x18003d12b  or      ebx, 80070000h
0x18003d131  test    ebx, ebx
0x18003d133  jns     short loc_18003D146
0x18003d135  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003d13b  mov     rcx, rax
0x18003d13e  mov     edx, ebx
0x18003d140  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d146  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d14d  lea     rax, WPP_GLOBAL_Control
0x18003d154  cmp     rcx, rax
0x18003d157  jz      short loc_18003D0E5
0x18003d159  test    byte ptr [rcx+1Ch], 1
0x18003d15d  jz      short loc_18003D0E5
0x18003d15f  cmp     byte ptr [rcx+19h], 2
0x18003d163  jb      short loc_18003D0E5
0x18003d165  mov     edx, 0Dh
0x18003d16a  jmp     loc_18003D0D2
0x18003d16f  xor     eax, eax
0x18003d171  mov     rbx, [rsp+38h+arg_0]
0x18003d176  add     rsp, 30h
0x18003d17a  pop     rdi
0x18003d17b  retn
```
