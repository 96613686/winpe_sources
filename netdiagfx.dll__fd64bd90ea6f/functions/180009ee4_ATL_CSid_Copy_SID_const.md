# ATL::CSid::Copy(_SID const &)

- ea: `0x180009ee4`
- end: `0x180009f4d`
- name: `?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z`
- size: `105`
- prototype: `void __fastcall(ATL::CSid *this, struct _SID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180007ce8`
- `0x180008754`

## callees

- `0x180005c18`
- `0x180009904`
- `0x180009ee4`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x180009ef7`
- `ADVAPI32!IsValidSid` at `0x180009ef7`
- `ADVAPI32!GetLengthSid` at `0x180009f04`
- `ADVAPI32!GetLengthSid` at `0x180009f04`
- `ADVAPI32!CopySid` at `0x180009f1c`
- `ADVAPI32!CopySid` at `0x180009f1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ATL::CSid::Copy(ATL::CSid *this, struct _SID *a2)
{
  DWORD LengthSid; // eax
  int Error; // eax

  if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
    ATL::AtlThrowImpl(-2147024809);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, a2) )
  {
    Error = ATL::AtlHresultFromLastError();
    *((_BYTE *)this + 76) = 0;
    ATL::AtlThrowImpl(Error);
  }
}

```

## disassembly

```asm
0x180009ee4  mov     [rsp+arg_0], rbx
0x180009ee9  push    rdi
0x180009eea  sub     rsp, 20h
0x180009eee  mov     rdi, rcx
0x180009ef1  mov     rbx, rdx
0x180009ef4  mov     rcx, rdx; pSid
0x180009ef7  call    cs:__imp_IsValidSid
0x180009efd  test    eax, eax
0x180009eff  jz      short loc_180009F37
0x180009f01  mov     rcx, rbx; pSid
0x180009f04  call    cs:__imp_GetLengthSid
0x180009f0a  cmp     eax, 44h ; 'D'
0x180009f0d  ja      short loc_180009F37
0x180009f0f  lea     rdx, [rdi+8]; pDestinationSid
0x180009f13  mov     byte ptr [rdi+4Ch], 1
0x180009f17  mov     r8, rbx; pSourceSid
0x180009f1a  mov     ecx, eax; nDestinationSidLength
0x180009f1c  call    cs:__imp_CopySid
0x180009f22  test    eax, eax
0x180009f24  jnz     short loc_180009F42
0x180009f26  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009f2b  mov     ecx, eax; int
0x180009f2d  mov     byte ptr [rdi+4Ch], 0
0x180009f31  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009f37  mov     ecx, 80070057h; int
0x180009f3c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009f42  mov     rbx, [rsp+28h+arg_0]
0x180009f47  add     rsp, 20h
0x180009f4b  pop     rdi
0x180009f4c  retn
```
