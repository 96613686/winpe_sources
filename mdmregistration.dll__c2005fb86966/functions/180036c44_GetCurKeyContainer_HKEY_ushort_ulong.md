# GetCurKeyContainer(HKEY__ *,ushort *,ulong)

- ea: `0x180036c44`
- end: `0x180036c96`
- name: `?GetCurKeyContainer@@YAJPEAUHKEY__@@PEAGK@Z`
- size: `82`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x180036c44`
- `0x180044e94`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x180036c75`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180036c75`

## pseudocode

```c
int __fastcall GetCurKeyContainer(HKEY a1, unsigned __int16 *a2)
{
  int result; // eax

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = OmaDmRegistryGetString(a1, 0, L"CurKeyContainer", a2, 0x100u);
  if ( result < 0 )
    *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180036c44  mov     [rsp+arg_0], rbx
0x180036c49  push    rdi
0x180036c4a  sub     rsp, 30h
0x180036c4e  mov     rbx, rdx
0x180036c51  mov     rdi, rcx
0x180036c54  test    rdx, rdx
0x180036c57  jnz     short loc_180036C5E
0x180036c59  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL != szCurKeyContainer")
0x180036c5e  mov     r9, rbx
0x180036c61  mov     [rsp+38h+var_18], 100h
0x180036c69  lea     r8, aCurkeycontaine; "CurKeyContainer"
0x180036c70  xor     edx, edx
0x180036c72  mov     rcx, rdi
0x180036c75  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180036c7c  nop     dword ptr [rax+rax+00h]
0x180036c81  test    eax, eax
0x180036c83  jns     short loc_180036C8A
0x180036c85  xor     ecx, ecx
0x180036c87  mov     [rbx], cx
0x180036c8a  mov     rbx, [rsp+38h+arg_0]
0x180036c8f  add     rsp, 30h
0x180036c93  pop     rdi
0x180036c94  retn
```
