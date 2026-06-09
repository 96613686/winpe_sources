# StSecpGetSidFromPackageFullName

- ea: `0x14000dd14`
- end: `0x14000dd60`
- name: `StSecpGetSidFromPackageFullName`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140010f90`

## callees

- `0x14000dd14`
- `0x14000dff8`
- `0x140011350`
- `0x1400122e0`

## pseudocode

```c
__int64 __fastcall StSecpGetSidFromPackageFullName(__int64 a1, wchar_t **a2)
{
  int SidFromPackageFamilyName; // ebx
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-18h] BYREF

  SourceString = 0;
  SidFromPackageFamilyName = StSecpPackageFamilyNameFromFullName(a1, &SourceString);
  if ( SidFromPackageFamilyName >= 0 )
    SidFromPackageFamilyName = StSecpGetSidFromPackageFamilyName(&SourceString, a2);
  StSecFree(SourceString.Buffer);
  return (unsigned int)SidFromPackageFamilyName;
}

```

## disassembly

```asm
0x14000dd14  mov     [rsp+arg_0], rbx
0x14000dd19  push    rdi
0x14000dd1a  sub     rsp, 30h
0x14000dd1e  mov     rdi, rdx
0x14000dd21  xorps   xmm0, xmm0
0x14000dd24  lea     rdx, [rsp+38h+SourceString]
0x14000dd29  movups  xmmword ptr [rsp+38h+SourceString.Length], xmm0
0x14000dd2e  call    StSecpPackageFamilyNameFromFullName
0x14000dd33  mov     ebx, eax
0x14000dd35  test    eax, eax
0x14000dd37  js      short loc_14000DD48
0x14000dd39  mov     rdx, rdi
0x14000dd3c  lea     rcx, [rsp+38h+SourceString]; SourceString
0x14000dd41  call    StSecpGetSidFromPackageFamilyName
0x14000dd46  mov     ebx, eax
0x14000dd48  mov     rcx, [rsp+38h+SourceString.Buffer]
0x14000dd4d  call    StSecFree
0x14000dd52  mov     eax, ebx
0x14000dd54  mov     rbx, [rsp+38h+arg_0]
0x14000dd59  add     rsp, 30h
0x14000dd5d  pop     rdi
0x14000dd5e  retn
```
