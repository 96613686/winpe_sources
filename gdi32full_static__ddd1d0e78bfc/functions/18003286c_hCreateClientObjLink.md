# hCreateClientObjLink

- ea: `0x18003286c`
- end: `0x180032907`
- name: `hCreateClientObjLink`
- size: `155`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180031f30`
- `0x18003261c`
- `0x1800343a0`
- `0x180035920`
- `0x180035f10`
- `0x18006b9e0`
- `0x180071070`

## callees

- `0x18002d31c`
- `0x18003286c`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800328a4`
- `ntdll!RtlEnterCriticalSection` at `0x1800328a4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800328c7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800328c7`
- `win32u!NtGdiDeleteClientObj` at `0x1800328f7`
- `win32u!NtGdiDeleteClientObj` at `0x1800328f7`
- `win32u!NtGdiCreateClientObj` at `0x180032889`
- `win32u!NtGdiCreateClientObj` at `0x180032889`

## pseudocode

```c
__int64 __fastcall hCreateClientObjLink(__int64 a1, unsigned int a2)
{
  __int64 ClientObj; // rbx
  __int64 v4; // rdi

  if ( gbDisableMetaFiles )
    return 0;
  ClientObj = NtGdiCreateClientObj(a2);
  if ( ClientObj )
  {
    RtlEnterCriticalSection(&semLocal);
    v4 = plinkCreate(ClientObj, 40);
    RtlLeaveCriticalSection(&semLocal);
    if ( v4 )
    {
      *(_QWORD *)(v4 + 32) = a1;
    }
    else
    {
      NtGdiDeleteClientObj(ClientObj);
      return 0;
    }
  }
  return ClientObj;
}

```

## disassembly

```asm
0x18003286c  mov     [rsp+arg_0], rbx
0x180032871  mov     [rsp+arg_8], rsi
0x180032876  push    rdi
0x180032877  sub     rsp, 20h
0x18003287b  cmp     cs:gbDisableMetaFiles, 0
0x180032882  mov     rsi, rcx
0x180032885  jnz     short loc_1800328F0
0x180032887  mov     ecx, edx
0x180032889  call    cs:__imp_NtGdiCreateClientObj
0x180032890  nop     dword ptr [rax+rax+00h]
0x180032895  mov     rbx, rax
0x180032898  test    rax, rax
0x18003289b  jz      short loc_1800328DC
0x18003289d  lea     rcx, semLocal; CriticalSection
0x1800328a4  call    cs:__imp_RtlEnterCriticalSection
0x1800328ab  nop     dword ptr [rax+rax+00h]
0x1800328b0  mov     edx, 28h ; '('
0x1800328b5  mov     rcx, rbx
0x1800328b8  call    plinkCreate
0x1800328bd  lea     rcx, semLocal; CriticalSection
0x1800328c4  mov     rdi, rax
0x1800328c7  call    cs:__imp_RtlLeaveCriticalSection
0x1800328ce  nop     dword ptr [rax+rax+00h]
0x1800328d3  test    rdi, rdi
0x1800328d6  jz      short loc_1800328F4
0x1800328d8  mov     [rdi+20h], rsi
0x1800328dc  mov     rax, rbx
0x1800328df  mov     rbx, [rsp+28h+arg_0]
0x1800328e4  mov     rsi, [rsp+28h+arg_8]
0x1800328e9  add     rsp, 20h
0x1800328ed  pop     rdi
0x1800328ee  retn
0x1800328f0  xor     eax, eax
0x1800328f2  jmp     short loc_1800328DF
0x1800328f4  mov     rcx, rbx
0x1800328f7  call    cs:__imp_NtGdiDeleteClientObj
0x1800328fe  nop     dword ptr [rax+rax+00h]
0x180032903  xor     ebx, ebx
0x180032905  jmp     short loc_1800328DC
```
