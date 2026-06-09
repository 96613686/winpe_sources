# CEventUnregister

- ea: `0x18002aeb4`
- end: `0x18002af88`
- name: `CEventUnregister`
- size: `212`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009ee0`

## callees

- `0x18002aeb4`
- `0x18002b158`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002af62`
- `ntdll!RtlLeaveCriticalSection` at `0x18002af62`
- `ntdll!RtlEnterCriticalSection` at `0x18002af07`
- `ntdll!RtlEnterCriticalSection` at `0x18002af07`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002af19`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002af19`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002af46`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002af46`

## pseudocode

```c
__int64 CEventUnregister()
{
  unsigned int v0; // ebx
  PVOID v1; // rax
  void *v2; // rdi
  _BYTE Buffer[56]; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v5; // [rsp+58h] [rbp-30h]

  if ( byte_18004DE60 )
  {
    memset_0(Buffer, 0, 0x48u);
    v5 = g_DsRoleRegistrationHandle;
    RtlEnterCriticalSection(&CriticalSection);
    v1 = RtlLookupElementGenericTableAvl(&Table, Buffer);
    v2 = v1;
    if ( v1 )
    {
      v0 = deinitEventList(v1);
      if ( v0 )
        goto LABEL_8;
      if ( RtlDeleteElementGenericTableAvl(&Table, v2) )
      {
        g_DsRoleRegistrationHandle = 0;
        goto LABEL_8;
      }
    }
    v0 = 6;
LABEL_8:
    RtlLeaveCriticalSection(&CriticalSection);
    return v0;
  }
  return 6;
}

```

## disassembly

```asm
0x18002aeb4  mov     [rsp+arg_0], rbx
0x18002aeb9  push    rdi
0x18002aeba  sub     rsp, 80h
0x18002aec1  mov     rax, cs:__security_cookie
0x18002aec8  xor     rax, rsp
0x18002aecb  mov     [rsp+88h+var_18], rax
0x18002aed0  mov     al, cs:byte_18004DE60
0x18002aed6  test    al, al
0x18002aed8  jnz     short loc_18002AEE4
0x18002aeda  mov     ebx, 6
0x18002aedf  jmp     loc_18002AF68
0x18002aee4  xor     edx, edx; Val
0x18002aee6  lea     rcx, [rsp+88h+Buffer]; void *
0x18002aeeb  lea     r8d, [rdx+48h]; Size
0x18002aeef  call    memset_0
0x18002aef4  mov     rax, cs:?g_DsRoleRegistrationHandle@@3_KA; unsigned __int64 g_DsRoleRegistrationHandle
0x18002aefb  lea     rcx, CriticalSection; CriticalSection
0x18002af02  mov     [rsp+88h+var_30], rax
0x18002af07  call    cs:__imp_RtlEnterCriticalSection
0x18002af0d  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18002af12  lea     rcx, Table; Table
0x18002af19  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18002af1f  mov     rdi, rax
0x18002af22  test    rax, rax
0x18002af25  jnz     short loc_18002AF2E
0x18002af27  mov     ebx, 6
0x18002af2c  jmp     short loc_18002AF5B
0x18002af2e  mov     rcx, rdi
0x18002af31  call    deinitEventList
0x18002af36  mov     ebx, eax
0x18002af38  test    eax, eax
0x18002af3a  jnz     short loc_18002AF5B
0x18002af3c  mov     rdx, rdi; Buffer
0x18002af3f  lea     rcx, Table; Table
0x18002af46  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002af4c  test    al, al
0x18002af4e  jz      short loc_18002AF27
0x18002af50  mov     cs:?g_DsRoleRegistrationHandle@@3_KA, 0; unsigned __int64 g_DsRoleRegistrationHandle
0x18002af5b  lea     rcx, CriticalSection; CriticalSection
0x18002af62  call    cs:__imp_RtlLeaveCriticalSection
0x18002af68  mov     eax, ebx
0x18002af6a  mov     rcx, [rsp+88h+var_18]
0x18002af6f  xor     rcx, rsp; StackCookie
0x18002af72  call    __security_check_cookie
0x18002af77  mov     rbx, [rsp+88h+arg_0]
0x18002af7f  add     rsp, 80h
0x18002af86  pop     rdi
0x18002af87  retn
```
