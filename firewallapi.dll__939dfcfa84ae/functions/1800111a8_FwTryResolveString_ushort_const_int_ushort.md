# FwTryResolveString(ushort const *,int,ushort * *)

- ea: `0x1800111a8`
- end: `0x18001121a`
- name: `?FwTryResolveString@@YAJPEBGHPEAPEAG@Z`
- size: `114`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010e50`

## callees

- `0x1800111a8`

## import_xrefs

- `fwbase!FwLoadIndirectString` at `0x1800111c6`
- `fwbase!FwLoadIndirectString` at `0x1800111c6`
- `fwbase!FwReportReturnError` at `0x18001120c`
- `fwbase!FwReportReturnError` at `0x18001120c`
- `fwbase!FwStringCopy` at `0x1800111f1`
- `fwbase!FwStringCopy` at `0x1800111f1`

## pseudocode

```c
__int64 __fastcall FwTryResolveString(const unsigned __int16 *a1, __int64 a2, unsigned __int16 **a3)
{
  int IndirectString; // ebx
  int v7; // eax

  if ( *a1 != 64 || (IndirectString = FwLoadIndirectString(a1, a3), IndirectString < 0) )
  {
    v7 = FwStringCopy(a1, a3);
    IndirectString = v7;
    if ( v7 < 0 )
      FwReportReturnError("FwTryResolveString", (unsigned int)v7);
  }
  return (unsigned int)IndirectString;
}

```

## disassembly

```asm
0x1800111a8  mov     [rsp+arg_0], rbx
0x1800111ad  mov     [rsp+arg_8], rsi
0x1800111b2  push    rdi
0x1800111b3  sub     rsp, 20h
0x1800111b7  cmp     word ptr [rcx], 40h ; '@'
0x1800111bb  mov     rsi, r8
0x1800111be  mov     rdi, rcx
0x1800111c1  jnz     short loc_1800111EB
0x1800111c3  mov     rdx, r8
0x1800111c6  call    cs:__imp_FwLoadIndirectString
0x1800111cd  nop     dword ptr [rax+rax+00h]
0x1800111d2  mov     ebx, eax
0x1800111d4  test    eax, eax
0x1800111d6  js      short loc_1800111EB
0x1800111d8  mov     rsi, [rsp+28h+arg_8]
0x1800111dd  mov     eax, ebx
0x1800111df  mov     rbx, [rsp+28h+arg_0]
0x1800111e4  add     rsp, 20h
0x1800111e8  pop     rdi
0x1800111e9  retn
0x1800111eb  mov     rdx, rsi
0x1800111ee  mov     rcx, rdi
0x1800111f1  call    cs:__imp_FwStringCopy
0x1800111f8  nop     dword ptr [rax+rax+00h]
0x1800111fd  mov     ebx, eax
0x1800111ff  test    eax, eax
0x180011201  jns     short loc_1800111D8
0x180011203  mov     edx, eax
0x180011205  lea     rcx, aFwtryresolvest; "FwTryResolveString"
0x18001120c  call    cs:__imp_FwReportReturnError
0x180011213  nop     dword ptr [rax+rax+00h]
0x180011218  jmp     short loc_1800111D8
```
