# CFsiStashFile::CurrentPosition(void)

- ea: `0x18002e02c`
- end: `0x18002e091`
- name: `?CurrentPosition@CFsiStashFile@@QEAA_KXZ`
- size: `101`
- prototype: `unsigned __int64 __fastcall(CFsiStashFile *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002e31c`
- `0x18002e538`

## callees

- `0x180019034`
- `0x18001978c`
- `0x18002e02c`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18002e05f`
- `KERNEL32!SetFilePointer` at `0x18002e05f`

## pseudocode

```c
__int64 __fastcall CFsiStashFile::CurrentPosition(CFsiStashFile *this)
{
  __int64 v1; // rcx
  HANDLE *v2; // rcx
  __int64 v3; // rbx
  __int64 DistanceToMoveHigh; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v1 = *(_QWORD *)this;
  v6 = v1;
  if ( v1 )
    ++*(_DWORD *)(v1 + 8);
  v2 = *(HANDLE **)v1;
  HIDWORD(DistanceToMoveHigh) = 0;
  LODWORD(DistanceToMoveHigh) = SetFilePointer(*v2, 0, (PLONG)&DistanceToMoveHigh + 1, 1u);
  if ( (_DWORD)DistanceToMoveHigh != -1 || (v3 = 0, (int)ATL::AtlHresultFromLastError() >= 0) )
    v3 = DistanceToMoveHigh;
  SmartPtr<ATL::CAtlFile>::~SmartPtr<ATL::CAtlFile>(&v6);
  return v3;
}

```

## disassembly

```asm
0x18002e02c  push    rbx
0x18002e02e  sub     rsp, 20h
0x18002e032  mov     rcx, [rcx]
0x18002e035  mov     r9d, 1; dwMoveMethod
0x18002e03b  mov     [rsp+28h+arg_8], rcx
0x18002e040  test    rcx, rcx
0x18002e043  jz      short loc_18002E049
0x18002e045  add     [rcx+8], r9d
0x18002e049  mov     rcx, [rcx]
0x18002e04c  lea     r8, [rsp+28h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18002e051  xor     edx, edx; lDistanceToMove
0x18002e053  mov     qword ptr [rsp+30h], 0
0x18002e05c  mov     rcx, [rcx]; hFile
0x18002e05f  call    cs:__imp_SetFilePointer
0x18002e065  mov     dword ptr [rsp+28h+DistanceToMoveHigh], eax
0x18002e069  cmp     eax, 0FFFFFFFFh
0x18002e06c  jnz     short loc_18002E079
0x18002e06e  xor     ebx, ebx
0x18002e070  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002e075  test    eax, eax
0x18002e077  js      short loc_18002E07E
0x18002e079  mov     rbx, [rsp+28h+DistanceToMoveHigh]
0x18002e07e  lea     rcx, [rsp+28h+arg_8]
0x18002e083  call    ??1?$SmartPtr@VCAtlFile@ATL@@@@QEAA@XZ; SmartPtr<ATL::CAtlFile>::~SmartPtr<ATL::CAtlFile>(void)
0x18002e088  mov     rax, rbx
0x18002e08b  add     rsp, 20h
0x18002e08f  pop     rbx
0x18002e090  retn
```
