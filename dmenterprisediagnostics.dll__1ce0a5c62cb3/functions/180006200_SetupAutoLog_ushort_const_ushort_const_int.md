# SetupAutoLog(ushort const *,ushort const *,int)

- ea: `0x180006200`
- end: `0x18000623c`
- name: `?SetupAutoLog@@YAJPEBG0H@Z`
- size: `60`
- prototype: `__int64 __fastcall(wchar_t *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180005a14`
- `0x180006200`
- `0x180006250`

## string_xrefs

- `0x18000621c`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetupAutoLog(wchar_t *a1, const unsigned __int16 *a2, int a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = SetupAutoLogWithTraceLevel(a1, a2, a3, 4);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x125,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180006200  push    rbx; int
0x180006202  sub     rsp, 20h
0x180006206  mov     r9d, 4; int
0x18000620c  call    ?SetupAutoLogWithTraceLevel@@YAJPEBG0HH@Z; SetupAutoLogWithTraceLevel(ushort const *,ushort const *,int,int)
0x180006211  mov     ebx, eax
0x180006213  test    eax, eax
0x180006215  jns     short loc_180006234
0x180006217  mov     rcx, [rsp+28h]; this
0x18000621c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006223  mov     r9d, eax; char *
0x180006226  mov     edx, 125h; void *
0x18000622b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006230  mov     eax, ebx
0x180006232  jmp     short loc_180006236
0x180006234  xor     eax, eax
0x180006236  add     rsp, 20h
0x18000623a  pop     rbx
0x18000623b  retn
```
