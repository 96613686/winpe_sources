# CXMLTag::SetTagDataType(wchar_t const *,uint)

- ea: `0x18000cb70`
- end: `0x18000cc63`
- name: `?SetTagDataType@CXMLTag@@AEAAXPEB_WI@Z`
- size: `243`
- prototype: `void __fastcall(CXMLTag *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000bea0`

## callees

- `0x18000cb70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cbd3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cbf6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cc1c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cc46`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cbd3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cbf6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cc1c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000cc46`

## pseudocode

```c
void __fastcall CXMLTag::SetTagDataType(CXMLTag *this, const wchar_t *a2, int a3, __int64 a4)
{
  *((_DWORD *)this + 228) = 0;
  if ( !a3 )
    return;
  if ( *a2 != 66 )
  {
    switch ( *a2 )
    {
      case 'D':
LABEL_15:
        if ( !(unsigned int)_o__wcsnicmp(L"date", a2, 4, a4) )
          *((_DWORD *)this + 228) = 5;
        return;
      case 'F':
LABEL_13:
        if ( !(unsigned int)_o__wcsnicmp(L"float", a2, 5, a4) )
          *((_DWORD *)this + 228) = 3;
        return;
      case 'S':
LABEL_11:
        if ( !(unsigned int)_o__wcsnicmp(L"string", a2, 6, a4) )
          *((_DWORD *)this + 228) = 1;
        return;
    }
    if ( *a2 != 98 )
    {
      if ( *a2 != 100 )
      {
        if ( *a2 != 102 )
        {
          if ( *a2 != 115 )
            return;
          goto LABEL_11;
        }
        goto LABEL_13;
      }
      goto LABEL_15;
    }
  }
  if ( !(unsigned int)_o__wcsnicmp(L"boolean", a2, 7, a4) )
    *((_DWORD *)this + 228) = 2;
}

```

## disassembly

```asm
0x18000cb70  push    rbx
0x18000cb72  sub     rsp, 20h
0x18000cb76  mov     dword ptr [rcx+390h], 0
0x18000cb80  mov     rbx, rcx
0x18000cb83  test    r8d, r8d
0x18000cb86  jnz     short loc_18000CB8E
0x18000cb88  add     rsp, 20h
0x18000cb8c  pop     rbx
0x18000cb8d  retn
0x18000cb8e  cmp     word ptr [rdx], 42h ; 'B'
0x18000cb92  jz      loc_18000CC39
0x18000cb98  cmp     word ptr [rdx], 44h ; 'D'
0x18000cb9c  jz      short loc_18000CC0F
0x18000cb9e  cmp     word ptr [rdx], 46h ; 'F'
0x18000cba2  jz      short loc_18000CBE9
0x18000cba4  cmp     word ptr [rdx], 53h ; 'S'
0x18000cba8  jz      short loc_18000CBC6
0x18000cbaa  cmp     word ptr [rdx], 62h ; 'b'
0x18000cbae  jz      loc_18000CC39
0x18000cbb4  cmp     word ptr [rdx], 64h ; 'd'
0x18000cbb8  jz      short loc_18000CC0F
0x18000cbba  cmp     word ptr [rdx], 66h ; 'f'
0x18000cbbe  jz      short loc_18000CBE9
0x18000cbc0  cmp     word ptr [rdx], 73h ; 's'
0x18000cbc4  jnz     short loc_18000CB88
0x18000cbc6  mov     r8d, 6
0x18000cbcc  lea     rcx, aString; "string"
0x18000cbd3  call    cs:__imp__o__wcsnicmp
0x18000cbd9  test    eax, eax
0x18000cbdb  jnz     short loc_18000CB88
0x18000cbdd  mov     dword ptr [rbx+390h], 1
0x18000cbe7  jmp     short loc_18000CB88
0x18000cbe9  mov     r8d, 5
0x18000cbef  lea     rcx, aFloat; "float"
0x18000cbf6  call    cs:__imp__o__wcsnicmp
0x18000cbfc  test    eax, eax
0x18000cbfe  jnz     short loc_18000CB88
0x18000cc00  mov     dword ptr [rbx+390h], 3
0x18000cc0a  jmp     loc_18000CB88
0x18000cc0f  mov     r8d, 4
0x18000cc15  lea     rcx, aDate; "date"
0x18000cc1c  call    cs:__imp__o__wcsnicmp
0x18000cc22  test    eax, eax
0x18000cc24  jnz     loc_18000CB88
0x18000cc2a  mov     dword ptr [rbx+390h], 5
0x18000cc34  jmp     loc_18000CB88
0x18000cc39  mov     r8d, 7
0x18000cc3f  lea     rcx, aBoolean; "boolean"
0x18000cc46  call    cs:__imp__o__wcsnicmp
0x18000cc4c  test    eax, eax
0x18000cc4e  jnz     loc_18000CB88
0x18000cc54  mov     dword ptr [rbx+390h], 2
0x18000cc5e  jmp     loc_18000CB88
```
