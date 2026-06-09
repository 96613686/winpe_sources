# SetupAutoLog(ushort const *,ushort const *,int)

- ea: `0x180006450`
- end: `0x18000648d`
- name: `?SetupAutoLog@@YAJPEBG0H@Z`
- size: `61`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180005c14`
- `0x180006450`
- `0x1800064a0`

## string_xrefs

- `0x18000646c`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
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
0x180006450  push    rbx; int
0x180006452  sub     rsp, 20h
0x180006456  mov     r9d, 4; int
0x18000645c  call    ?SetupAutoLogWithTraceLevel@@YAJPEBG0HH@Z; SetupAutoLogWithTraceLevel(ushort const *,ushort const *,int,int)
0x180006461  mov     ebx, eax
0x180006463  test    eax, eax
0x180006465  jns     short loc_180006484
0x180006467  mov     rcx, [rsp+28h]; this
0x18000646c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006473  mov     r9d, eax; char *
0x180006476  mov     edx, 125h; void *
0x18000647b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006480  mov     eax, ebx
0x180006482  jmp     short loc_180006486
0x180006484  xor     eax, eax
0x180006486  add     rsp, 20h
0x18000648a  pop     rbx
0x18000648b  retn
```
