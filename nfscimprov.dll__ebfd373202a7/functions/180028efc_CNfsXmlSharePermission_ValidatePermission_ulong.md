# CNfsXmlSharePermission::ValidatePermission(ulong *)

- ea: `0x180028efc`
- end: `0x180028f9f`
- name: `?ValidatePermission@CNfsXmlSharePermission@@AEAAEPEAK@Z`
- size: `163`
- prototype: `unsigned __int8 __fastcall(CNfsXmlSharePermission *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002783c`

## callees

- `0x180028efc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180028f2d`
- `msvcrt!_wcsicmp` at `0x180028f51`
- `msvcrt!_wcsicmp` at `0x180028f77`
- `msvcrt!_wcsicmp` at `0x180028f2d`
- `msvcrt!_wcsicmp` at `0x180028f51`
- `msvcrt!_wcsicmp` at `0x180028f77`

## string_xrefs

- `0x180028f26`: `No-Access`
- `0x180028f4a`: `ReadOnly`
- `0x180028f70`: `ReadWrite`

## pseudocode

```c
char __fastcall CNfsXmlSharePermission::ValidatePermission(CNfsXmlSharePermission *this, unsigned int *a2)
{
  const wchar_t *v2; // rbx
  char v4; // di
  const wchar_t *v5; // rdx
  const wchar_t *v6; // rdx

  v2 = (const wchar_t *)((char *)this + 64);
  v4 = 1;
  if ( *((_QWORD *)this + 11) < 8u )
    v5 = (const wchar_t *)((char *)this + 64);
  else
    v5 = *(const wchar_t **)v2;
  if ( _wcsicmp(L"No-Access", v5) )
  {
    if ( *((_QWORD *)v2 + 3) < 8u )
      v6 = v2;
    else
      v6 = *(const wchar_t **)v2;
    if ( _wcsicmp(L"ReadOnly", v6) )
    {
      if ( *((_QWORD *)v2 + 3) >= 8u )
        v2 = *(const wchar_t **)v2;
      if ( _wcsicmp(L"ReadWrite", v2) )
        return 0;
      else
        *a2 = 4;
    }
    else
    {
      *a2 = 2;
    }
  }
  else
  {
    *a2 = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x180028efc  mov     [rsp+arg_0], rbx
0x180028f01  mov     [rsp+arg_8], rsi
0x180028f06  push    rdi
0x180028f07  sub     rsp, 20h
0x180028f0b  lea     rbx, [rcx+40h]
0x180028f0f  mov     rsi, rdx
0x180028f12  cmp     qword ptr [rbx+18h], 8
0x180028f17  mov     edi, 1
0x180028f1c  jb      short loc_180028F23
0x180028f1e  mov     rdx, [rbx]
0x180028f21  jmp     short loc_180028F26
0x180028f23  mov     rdx, rbx; String2
0x180028f26  lea     rcx, aNoAccess_0; "No-Access"
0x180028f2d  call    cs:__imp__wcsicmp
0x180028f33  test    eax, eax
0x180028f35  jnz     short loc_180028F3B
0x180028f37  mov     [rsi], edi
0x180028f39  jmp     short loc_180028F8C
0x180028f3b  cmp     qword ptr [rbx+18h], 8
0x180028f40  jb      short loc_180028F47
0x180028f42  mov     rdx, [rbx]
0x180028f45  jmp     short loc_180028F4A
0x180028f47  mov     rdx, rbx; String2
0x180028f4a  lea     rcx, aReadonly; "ReadOnly"
0x180028f51  call    cs:__imp__wcsicmp
0x180028f57  test    eax, eax
0x180028f59  jnz     short loc_180028F63
0x180028f5b  mov     dword ptr [rsi], 2
0x180028f61  jmp     short loc_180028F8C
0x180028f63  cmp     qword ptr [rbx+18h], 8
0x180028f68  jb      short loc_180028F6D
0x180028f6a  mov     rbx, [rbx]
0x180028f6d  mov     rdx, rbx; String2
0x180028f70  lea     rcx, aReadwrite; "ReadWrite"
0x180028f77  call    cs:__imp__wcsicmp
0x180028f7d  test    eax, eax
0x180028f7f  jnz     short loc_180028F89
0x180028f81  mov     dword ptr [rsi], 4
0x180028f87  jmp     short loc_180028F8C
0x180028f89  xor     dil, dil
0x180028f8c  mov     rbx, [rsp+28h+arg_0]
0x180028f91  mov     al, dil
0x180028f94  mov     rsi, [rsp+28h+arg_8]
0x180028f99  add     rsp, 20h
0x180028f9d  pop     rdi
0x180028f9e  retn
```
