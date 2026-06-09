# GetRestoreType(ulong &)

- ea: `0x18003abac`
- end: `0x18003ad05`
- name: `?GetRestoreType@@YAJAEAK@Z`
- size: `345`
- prototype: `__int64 __fastcall(unsigned int *, __int64, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c950`
- `0x18002fd70`
- `0x18003c8a0`

## callees

- `0x1800012b8`
- `0x180024ca0`
- `0x18003abac`
- `0x180043fa0`
- `0x180044170`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003abff`
- `wbemcomn!GetMemLogObject` at `0x18003aca5`
- `wbemcomn!GetMemLogObject` at `0x18003abff`
- `wbemcomn!GetMemLogObject` at `0x18003aca5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ac0a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003acb0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ac0a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003acb0`

## pseudocode

```c
__int64 __fastcall GetRestoreType(unsigned int *a1, __int64 a2, int a3)
{
  int v4; // eax
  int v5; // r8d
  signed int Value; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  bool v11; // sf
  CMemoryLog *v12; // rax
  int v13; // [rsp+40h] [rbp+8h] BYREF
  int v14; // [rsp+48h] [rbp+10h] BYREF
  __int64 v15; // [rsp+50h] [rbp+18h] BYREF

  *a1 = 1;
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
    v9 = 10;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, (unsigned int)Value);
    return (unsigned int)Value;
  }
  v13 = 0;
  v14 = 4;
  Value = DLRegQueryValueExW(v15, (unsigned int)L"AutoRestoreEnabled", v5, 0, (__int64)&v13, (__int64)&v14);
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
    v9 = 11;
    goto LABEL_10;
  }
  if ( !v13 )
    *a1 = 0;
  return 0;
}

```

## disassembly

```asm
0x18003abac  mov     r11, rsp
0x18003abaf  mov     [r11+20h], rbx
0x18003abb3  push    rdi
0x18003abb4  sub     rsp, 30h
0x18003abb8  mov     rdi, rcx
0x18003abbb  mov     dword ptr [rcx], 1
0x18003abc1  lea     rax, [r11+18h]
0x18003abc5  mov     qword ptr [r11+18h], 0
0x18003abcd  mov     rcx, 0FFFFFFFF80000002h
0x18003abd4  mov     [r11-18h], rax
0x18003abd8  mov     r9d, 20019h
0x18003abde  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Wbem\\CIMOM"
0x18003abe5  call    DLRegOpenKeyExW
0x18003abea  mov     ebx, eax
0x18003abec  test    eax, eax
0x18003abee  jz      short loc_18003AC4E
0x18003abf0  jle     short loc_18003ABFB
0x18003abf2  movzx   ebx, ax
0x18003abf5  or      ebx, 80070000h
0x18003abfb  test    ebx, ebx
0x18003abfd  jns     short loc_18003AC10
0x18003abff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ac05  mov     rcx, rax
0x18003ac08  mov     edx, ebx
0x18003ac0a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ac10  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac17  lea     rax, WPP_GLOBAL_Control
0x18003ac1e  cmp     rcx, rax
0x18003ac21  jz      short loc_18003AC47
0x18003ac23  test    byte ptr [rcx+1Ch], 1
0x18003ac27  jz      short loc_18003AC47
0x18003ac29  cmp     byte ptr [rcx+19h], 2
0x18003ac2d  jb      short loc_18003AC47
0x18003ac2f  mov     edx, 0Ah
0x18003ac34  mov     rcx, [rcx+10h]
0x18003ac38  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003ac3f  mov     r9d, ebx
0x18003ac42  call    WPP_SF_d
0x18003ac47  mov     eax, ebx
0x18003ac49  jmp     loc_18003ACFA
0x18003ac4e  mov     rcx, [rsp+38h+arg_10]
0x18003ac53  lea     rax, [rsp+38h+arg_8]
0x18003ac58  mov     [rsp+38h+var_10], rax
0x18003ac5d  lea     rdx, aAutorestoreena; "AutoRestoreEnabled"
0x18003ac64  lea     rax, [rsp+38h+arg_0]
0x18003ac69  mov     [rsp+38h+arg_0], 0
0x18003ac71  xor     r9d, r9d
0x18003ac74  mov     [rsp+38h+var_18], rax
0x18003ac79  mov     [rsp+38h+arg_8], 4
0x18003ac81  call    DLRegQueryValueExW
0x18003ac86  mov     rcx, [rsp+38h+arg_10]
0x18003ac8b  mov     ebx, eax
0x18003ac8d  call    DLRegCloseKey
0x18003ac92  test    ebx, ebx
0x18003ac94  jz      short loc_18003ACEB
0x18003ac96  jle     short loc_18003ACA3
0x18003ac98  movzx   ebx, bx
0x18003ac9b  or      ebx, 80070000h
0x18003aca1  test    ebx, ebx
0x18003aca3  jns     short loc_18003ACB6
0x18003aca5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003acab  mov     rcx, rax
0x18003acae  mov     edx, ebx
0x18003acb0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003acb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003acbd  lea     rax, WPP_GLOBAL_Control
0x18003acc4  cmp     rcx, rax
0x18003acc7  jz      loc_18003AC47
0x18003accd  test    byte ptr [rcx+1Ch], 1
0x18003acd1  jz      loc_18003AC47
0x18003acd7  cmp     byte ptr [rcx+19h], 2
0x18003acdb  jb      loc_18003AC47
0x18003ace1  mov     edx, 0Bh
0x18003ace6  jmp     loc_18003AC34
0x18003aceb  cmp     [rsp+38h+arg_0], 0
0x18003acf0  jnz     short loc_18003ACF8
0x18003acf2  mov     dword ptr [rdi], 0
0x18003acf8  xor     eax, eax
0x18003acfa  mov     rbx, [rsp+38h+arg_18]
0x18003acff  add     rsp, 30h
0x18003ad03  pop     rdi
0x18003ad04  retn
```
