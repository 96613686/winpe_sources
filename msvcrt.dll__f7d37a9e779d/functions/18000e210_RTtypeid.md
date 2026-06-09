# __RTtypeid

- ea: `0x18000e210`
- end: `0x18000e2c7`
- name: `__RTtypeid`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000abd0`
- `0x18000acc0`
- `0x18000b680`
- `0x18000e210`

## import_xrefs

- `ntdll!RtlPcToFileHeader` at `0x18000e238`
- `ntdll!RtlPcToFileHeader` at `0x18000e238`

## string_xrefs

- `0x18000e2a4`: `Access violation - no RTTI data!`
- `0x18000e25e`: `Attempted a typeid of NULL pointer!`
- `0x18000e281`: `Bad read pointer - no RTTI data!`

## pseudocode

```c
char *__fastcall _RTtypeid(_QWORD *a1)
{
  int *v1; // rbx
  char *v2; // rcx
  char *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  PVOID BaseOfImage; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 )
  {
    bad_typeid::bad_typeid((bad_typeid *)pExceptionObject, "Attempted a typeid of NULL pointer!");
    throw (bad_typeid *)pExceptionObject;
  }
  v1 = *(int **)(*a1 - 8LL);
  if ( *v1 )
  {
    v2 = (char *)v1 - v1[5];
  }
  else
  {
    BaseOfImage = 0;
    v2 = (char *)RtlPcToFileHeader(v1, &BaseOfImage);
    BaseOfImage = v2;
  }
  result = &v2[v1[3]];
  if ( !result )
  {
    __non_rtti_object::__non_rtti_object((__non_rtti_object *)pExceptionObject, "Bad read pointer - no RTTI data!");
    throw (__non_rtti_object *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18000e210  push    rbx
0x18000e212  sub     rsp, 40h
0x18000e216  test    rcx, rcx
0x18000e219  jz      short loc_18000E25E
0x18000e21b  mov     rax, [rcx]
0x18000e21e  mov     rbx, [rax-8]
0x18000e222  mov     rcx, rbx; PcValue
0x18000e225  cmp     dword ptr [rbx], 0
0x18000e228  jnz     short loc_18000E248
0x18000e22a  mov     [rsp+48h+BaseOfImage], 0
0x18000e233  lea     rdx, [rsp+48h+BaseOfImage]; BaseOfImage
0x18000e238  call    cs:__imp_RtlPcToFileHeader
0x18000e23e  mov     rcx, rax
0x18000e241  mov     [rsp+48h+BaseOfImage], rax
0x18000e246  jmp     short loc_18000E24F
0x18000e248  movsxd  rax, dword ptr [rbx+14h]
0x18000e24c  sub     rcx, rax
0x18000e24f  movsxd  rax, dword ptr [rbx+0Ch]
0x18000e253  add     rax, rcx
0x18000e256  jz      short loc_18000E281
0x18000e258  add     rsp, 40h
0x18000e25c  pop     rbx
0x18000e25d  retn
0x18000e25e  lea     rdx, aAttemptedAType; "Attempted a typeid of NULL pointer!"
0x18000e265  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000e26a  call    ??0bad_typeid@@QEAA@PEBD@Z; bad_typeid::bad_typeid(char const *)
0x18000e26f  lea     rdx, _TI2?AVbad_typeid@@; pThrowInfo
0x18000e276  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e27b  call    _CxxThrowException
0x18000e281  lea     rdx, aBadReadPointer; "Bad read pointer - no RTTI data!"
0x18000e288  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000e28d  call    ??0__non_rtti_object@@QEAA@PEBD@Z; __non_rtti_object::__non_rtti_object(char const *)
0x18000e292  lea     rdx, _TI3?AV__non_rtti_object@@; pThrowInfo
0x18000e299  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e29e  call    _CxxThrowException
0x18000e2a4  lea     rdx, aAccessViolatio; "Access violation - no RTTI data!"
0x18000e2ab  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000e2b0  call    ??0__non_rtti_object@@QEAA@PEBD@Z; __non_rtti_object::__non_rtti_object(char const *)
0x18000e2b5  lea     rdx, _TI3?AV__non_rtti_object@@; pThrowInfo
0x18000e2bc  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e2c1  call    _CxxThrowException
0x18007b3e8  push    rbp
0x18007b3ea  sub     rsp, 20h
0x18007b3ee  mov     rbp, rdx
0x18007b3f1  mov     rax, [rcx]
0x18007b3f4  xor     ecx, ecx
0x18007b3f6  cmp     dword ptr [rax], 0C0000005h
0x18007b3fc  setz    cl
0x18007b3ff  mov     eax, ecx
0x18007b401  add     rsp, 20h
0x18007b405  pop     rbp
0x18007b406  retn
```
