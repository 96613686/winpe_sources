# __RTDynamicCast

- ea: `0x18000e090`
- end: `0x18000e209`
- name: `__RTDynamicCast`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000abd0`
- `0x18000ac60`
- `0x18000b680`
- `0x18000dba8`
- `0x18000dd2c`
- `0x18000ddec`
- `0x18000e090`

## import_xrefs

- `ntdll!RtlPcToFileHeader` at `0x18000e107`
- `ntdll!RtlPcToFileHeader` at `0x18000e107`

## string_xrefs

- `0x18000e1c2`: `Access violation - no RTTI data!`

## pseudocode

```c
__int64 __fastcall _RTDynamicCast(_QWORD *a1, int a2, __int64 a3, __int64 a4, int a5)
{
  int v8; // esi
  __int64 result; // rax
  _DWORD *v10; // rdi
  char *v11; // rbx
  char *v12; // rcx
  int v13; // edx
  int v14; // r9d
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rax
  _BYTE pExceptionObject[88]; // [rsp+40h] [rbp-58h] BYREF
  PVOID BaseOfImage; // [rsp+A0h] [rbp+8h] BYREF

  v8 = (int)a1;
  if ( !a1 )
    return 0;
  v10 = *(_DWORD **)(*a1 - 8LL);
  v11 = (char *)a1 - (unsigned int)v10[1];
  if ( v10[2] )
    v11 -= *(int *)((char *)a1 - (unsigned int)v10[2]);
  if ( *v10 )
  {
    v12 = (char *)v10 - (int)v10[5];
  }
  else
  {
    BaseOfImage = 0;
    v12 = (char *)RtlPcToFileHeader(v10, &BaseOfImage);
    BaseOfImage = v12;
  }
  v13 = *(_DWORD *)&v12[v10[4] + 4];
  if ( (v13 & 1) != 0 )
  {
    v14 = v8 - a2 - (_DWORD)v11;
    if ( (v13 & 2) != 0 )
      result = FindVITargetTypeInstance((_DWORD)v11, (_DWORD)v10, a3, v14, a4, (__int64)v12);
    else
      result = FindMITargetTypeInstance((_DWORD)v11, (_DWORD)v10, a3, v14, a4, (__int64)v12);
  }
  else
  {
    result = FindSITargetTypeInstance(v10, a3, a4, v12);
  }
  v15 = result;
  if ( result )
  {
    v16 = 0;
    v17 = *(int *)(result + 12);
    if ( (int)v17 >= 0 )
    {
      _mm_lfence();
      v16 = v17 + *(int *)(*(_QWORD *)&v11[v17] + *(int *)(v15 + 16));
    }
    return (__int64)&v11[v16 + *(int *)(v15 + 8)];
  }
  else if ( a5 )
  {
    bad_cast::bad_cast((bad_cast *)pExceptionObject, "Bad dynamic_cast!");
    throw (bad_cast *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18000e090  push    rbx
0x18000e092  push    rsi
0x18000e093  push    rdi
0x18000e094  push    r12
0x18000e096  push    r14
0x18000e098  push    r15
0x18000e09a  sub     rsp, 68h
0x18000e09e  mov     r14, r9
0x18000e0a1  mov     r15, r8
0x18000e0a4  movsxd  r12, edx
0x18000e0a7  mov     rsi, rcx
0x18000e0aa  test    rcx, rcx
0x18000e0ad  jnz     short loc_18000E0BF
0x18000e0af  xor     eax, eax
0x18000e0b1  add     rsp, 68h
0x18000e0b5  pop     r15
0x18000e0b7  pop     r14
0x18000e0b9  pop     r12
0x18000e0bb  pop     rdi
0x18000e0bc  pop     rsi
0x18000e0bd  pop     rbx
0x18000e0be  retn
0x18000e0bf  mov     rax, [rcx]
0x18000e0c2  mov     rdi, [rax-8]
0x18000e0c6  mov     eax, [rdi+4]
0x18000e0c9  mov     rbx, rsi
0x18000e0cc  sub     rbx, rax
0x18000e0cf  mov     [rsp+98h+var_60], rbx
0x18000e0d4  cmp     dword ptr [rdi+8], 0
0x18000e0d8  jz      short loc_18000E0EB
0x18000e0da  mov     eax, [rdi+8]
0x18000e0dd  sub     rcx, rax
0x18000e0e0  movsxd  rax, dword ptr [rcx]
0x18000e0e3  sub     rbx, rax
0x18000e0e6  mov     [rsp+98h+var_60], rbx
0x18000e0eb  mov     rcx, rdi; PcValue
0x18000e0ee  cmp     dword ptr [rdi], 0
0x18000e0f1  jnz     short loc_18000E11A
0x18000e0f3  mov     [rsp+98h+BaseOfImage], 0
0x18000e0ff  lea     rdx, [rsp+98h+BaseOfImage]; BaseOfImage
0x18000e107  call    cs:__imp_RtlPcToFileHeader
0x18000e10d  mov     rcx, rax
0x18000e110  mov     [rsp+98h+BaseOfImage], rax
0x18000e118  jmp     short loc_18000E121
0x18000e11a  movsxd  rax, dword ptr [rdi+14h]
0x18000e11e  sub     rcx, rax
0x18000e121  movsxd  rax, dword ptr [rdi+10h]
0x18000e125  mov     edx, [rax+rcx+4]
0x18000e129  test    dl, 1
0x18000e12c  jnz     short loc_18000E141
0x18000e12e  mov     r9, rcx
0x18000e131  mov     r8, r14
0x18000e134  mov     rdx, r15
0x18000e137  mov     rcx, rdi
0x18000e13a  call    FindSITargetTypeInstance
0x18000e13f  jmp     short loc_18000E16E
0x18000e141  sub     rsi, r12
0x18000e144  sub     rsi, rbx
0x18000e147  mov     [rsp+98h+var_70], rcx
0x18000e14c  mov     r9, rsi
0x18000e14f  mov     r8, r15
0x18000e152  mov     [rsp+98h+var_78], r14
0x18000e157  mov     rcx, rbx
0x18000e15a  test    dl, 2
0x18000e15d  mov     rdx, rdi
0x18000e160  jnz     short loc_18000E169
0x18000e162  call    FindMITargetTypeInstance
0x18000e167  jmp     short loc_18000E16E
0x18000e169  call    FindVITargetTypeInstance
0x18000e16e  mov     r8, rax
0x18000e171  test    rax, rax
0x18000e174  jz      short loc_18000E1A9
0x18000e176  xor     ecx, ecx
0x18000e178  movsxd  rax, dword ptr [rax+0Ch]
0x18000e17c  test    eax, eax
0x18000e17e  js      short loc_18000E195
0x18000e180  lfence
0x18000e183  mov     rdx, rax
0x18000e186  movsxd  rcx, dword ptr [r8+10h]
0x18000e18a  mov     rax, [rax+rbx]
0x18000e18e  movsxd  rcx, dword ptr [rax+rcx]
0x18000e192  add     rcx, rdx
0x18000e195  movsxd  rax, dword ptr [r8+8]
0x18000e199  add     rax, rcx
0x18000e19c  add     rax, rbx
0x18000e19f  mov     [rsp+98h+var_68], rax
0x18000e1a4  jmp     loc_18000E0B1
0x18000e1a9  mov     [rsp+98h+var_68], rax
0x18000e1ae  cmp     [rsp+98h+arg_20], eax
0x18000e1b5  jnz     short loc_18000E1E5
0x18000e1b7  jmp     short loc_18000E1A4
0x18000e1b9  mov     [rsp+98h+var_68], 0
0x18000e1c2  lea     rdx, aAccessViolatio; "Access violation - no RTTI data!"
0x18000e1c9  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18000e1ce  call    ??0__non_rtti_object@@QEAA@PEBD@Z; __non_rtti_object::__non_rtti_object(char const *)
0x18000e1d3  lea     rdx, _TI3?AV__non_rtti_object@@; pThrowInfo
0x18000e1da  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000e1df  call    _CxxThrowException
0x18000e1e5  lea     rdx, aBadDynamicCast; "Bad dynamic_cast!"
0x18000e1ec  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18000e1f1  call    ??0bad_cast@@QEAA@PEBD@Z; bad_cast::bad_cast(char const *)
0x18000e1f6  lea     rdx, _TI2?AVbad_cast@@; pThrowInfo
0x18000e1fd  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000e202  call    _CxxThrowException
0x18007b40e  push    rbp
0x18007b410  sub     rsp, 30h
0x18007b414  mov     rbp, rdx
0x18007b417  mov     rax, [rcx]
0x18007b41a  xor     ecx, ecx
0x18007b41c  cmp     dword ptr [rax], 0C0000005h
0x18007b422  setz    cl
0x18007b425  mov     eax, ecx
0x18007b427  add     rsp, 30h
0x18007b42b  pop     rbp
0x18007b42c  retn
```
