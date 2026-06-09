# IsRepositoryForceCheckEnabled(int &)

- ea: `0x18002dfd0`
- end: `0x18002e121`
- name: `?IsRepositoryForceCheckEnabled@@YAJAEAH@Z`
- size: `337`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x1800012b8`
- `0x180024ca0`
- `0x18002dfd0`
- `0x180043fa0`
- `0x180044170`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002e01d`
- `wbemcomn!GetMemLogObject` at `0x18002e0c3`
- `wbemcomn!GetMemLogObject` at `0x18002e01d`
- `wbemcomn!GetMemLogObject` at `0x18002e0c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e028`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e0ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e028`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e0ce`

## pseudocode

```c
__int64 __fastcall IsRepositoryForceCheckEnabled(int *a1, __int64 a2, int a3)
{
  int v4; // eax
  int v5; // r8d
  signed int Value; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  bool v11; // sf
  CMemoryLog *v12; // rax
  int v13; // [rsp+48h] [rbp+10h] BYREF
  int v14; // [rsp+50h] [rbp+18h] BYREF
  __int64 v15; // [rsp+58h] [rbp+20h] BYREF

  v15 = 0;
  v4 = DLRegOpenKeyExW(-2147483646, (unsigned int)L"SOFTWARE\\Microsoft\\Wbem\\CIMOM", a3, 131097, (__int64)&v15);
  Value = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      Value = (unsigned __int16)v4 | 0x80070000;
    if ( Value < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, Value);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)Value;
    }
    v9 = 122;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, (unsigned int)Value);
    return (unsigned int)Value;
  }
  v13 = 0;
  v14 = 4;
  Value = DLRegQueryValueExW(v15, (unsigned int)L"CheckRepositoryOnNextStartup", v5, 0, (__int64)&v13, (__int64)&v14);
  DLRegCloseKey(v15);
  v11 = Value < 0;
  if ( Value )
  {
    if ( Value > 0 )
    {
      Value = (unsigned __int16)Value | 0x80070000;
      v11 = Value < 0;
    }
    if ( v11 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, Value);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)Value;
    }
    v9 = 123;
    goto LABEL_10;
  }
  *a1 = v13 != 0;
  return 0;
}

```

## disassembly

```asm
0x18002dfd0  mov     r11, rsp
0x18002dfd3  mov     [r11+8], rbx
0x18002dfd7  push    rdi
0x18002dfd8  sub     rsp, 30h
0x18002dfdc  mov     rdi, rcx
0x18002dfdf  mov     qword ptr [r11+20h], 0
0x18002dfe7  lea     rax, [r11+20h]
0x18002dfeb  mov     rcx, 0FFFFFFFF80000002h
0x18002dff2  mov     r9d, 20019h
0x18002dff8  mov     [r11-18h], rax
0x18002dffc  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Wbem\\CIMOM"
0x18002e003  call    DLRegOpenKeyExW
0x18002e008  mov     ebx, eax
0x18002e00a  test    eax, eax
0x18002e00c  jz      short loc_18002E06C
0x18002e00e  jle     short loc_18002E019
0x18002e010  movzx   ebx, ax
0x18002e013  or      ebx, 80070000h
0x18002e019  test    ebx, ebx
0x18002e01b  jns     short loc_18002E02E
0x18002e01d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e023  mov     rcx, rax
0x18002e026  mov     edx, ebx
0x18002e028  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e02e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e035  lea     rax, WPP_GLOBAL_Control
0x18002e03c  cmp     rcx, rax
0x18002e03f  jz      short loc_18002E065
0x18002e041  test    byte ptr [rcx+1Ch], 1
0x18002e045  jz      short loc_18002E065
0x18002e047  cmp     byte ptr [rcx+19h], 2
0x18002e04b  jb      short loc_18002E065
0x18002e04d  mov     edx, 7Ah ; 'z'
0x18002e052  mov     rcx, [rcx+10h]
0x18002e056  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002e05d  mov     r9d, ebx
0x18002e060  call    WPP_SF_d
0x18002e065  mov     eax, ebx
0x18002e067  jmp     loc_18002E116
0x18002e06c  mov     rcx, [rsp+38h+arg_18]
0x18002e071  lea     rax, [rsp+38h+arg_10]
0x18002e076  mov     [rsp+38h+var_10], rax
0x18002e07b  lea     rdx, aCheckrepositor; "CheckRepositoryOnNextStartup"
0x18002e082  lea     rax, [rsp+38h+arg_8]
0x18002e087  mov     [rsp+38h+arg_8], 0
0x18002e08f  xor     r9d, r9d
0x18002e092  mov     [rsp+38h+var_18], rax
0x18002e097  mov     [rsp+38h+arg_10], 4
0x18002e09f  call    DLRegQueryValueExW
0x18002e0a4  mov     rcx, [rsp+38h+arg_18]
0x18002e0a9  mov     ebx, eax
0x18002e0ab  call    DLRegCloseKey
0x18002e0b0  test    ebx, ebx
0x18002e0b2  jz      short loc_18002E109
0x18002e0b4  jle     short loc_18002E0C1
0x18002e0b6  movzx   ebx, bx
0x18002e0b9  or      ebx, 80070000h
0x18002e0bf  test    ebx, ebx
0x18002e0c1  jns     short loc_18002E0D4
0x18002e0c3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e0c9  mov     rcx, rax
0x18002e0cc  mov     edx, ebx
0x18002e0ce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e0db  lea     rax, WPP_GLOBAL_Control
0x18002e0e2  cmp     rcx, rax
0x18002e0e5  jz      loc_18002E065
0x18002e0eb  test    byte ptr [rcx+1Ch], 1
0x18002e0ef  jz      loc_18002E065
0x18002e0f5  cmp     byte ptr [rcx+19h], 2
0x18002e0f9  jb      loc_18002E065
0x18002e0ff  mov     edx, 7Bh ; '{'
0x18002e104  jmp     loc_18002E052
0x18002e109  xor     eax, eax
0x18002e10b  cmp     [rsp+38h+arg_8], eax
0x18002e10f  setnz   al
0x18002e112  mov     [rdi], eax
0x18002e114  xor     eax, eax
0x18002e116  mov     rbx, [rsp+38h+arg_0]
0x18002e11b  add     rsp, 30h
0x18002e11f  pop     rdi
0x18002e120  retn
```
