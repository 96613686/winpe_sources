# ValidatePermission(ushort const *,ulong *)

- ea: `0x180031804`
- end: `0x180031882`
- name: `?ValidatePermission@@YAEPEBGPEAK@Z`
- size: `126`
- prototype: `unsigned __int8 __fastcall(wchar_t *String2, unsigned int *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c88`
- `0x18000ac38`
- `0x18000af84`
- `0x18000b72c`
- `0x18000b9d8`
- `0x18000c034`
- `0x18000c520`
- `0x18000c814`

## callees

- `0x180031804`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180031828`
- `msvcrt!_wcsicmp` at `0x180031840`
- `msvcrt!_wcsicmp` at `0x18003185c`
- `msvcrt!_wcsicmp` at `0x180031828`
- `msvcrt!_wcsicmp` at `0x180031840`
- `msvcrt!_wcsicmp` at `0x18003185c`

## string_xrefs

- `0x180031821`: `no-access`
- `0x180031839`: `readonly`
- `0x180031855`: `readwrite`

## pseudocode

```c
char __fastcall ValidatePermission(wchar_t *String2, unsigned int *a2)
{
  char v4; // bl

  v4 = 1;
  if ( _wcsicmp(L"no-access", String2) )
  {
    if ( _wcsicmp(L"readonly", String2) )
    {
      if ( _wcsicmp(L"readwrite", String2) )
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
0x180031804  mov     [rsp+arg_0], rbx
0x180031809  mov     [rsp+arg_8], rsi
0x18003180e  push    rdi
0x18003180f  sub     rsp, 20h
0x180031813  mov     rdi, rdx
0x180031816  mov     rsi, rcx
0x180031819  mov     rdx, rcx; String2
0x18003181c  mov     ebx, 1
0x180031821  lea     rcx, aNoAccess; "no-access"
0x180031828  call    cs:__imp__wcsicmp
0x18003182e  test    eax, eax
0x180031830  jnz     short loc_180031836
0x180031832  mov     [rdi], ebx
0x180031834  jmp     short loc_180031870
0x180031836  mov     rdx, rsi; String2
0x180031839  lea     rcx, aReadonly_0; "readonly"
0x180031840  call    cs:__imp__wcsicmp
0x180031846  test    eax, eax
0x180031848  jnz     short loc_180031852
0x18003184a  mov     dword ptr [rdi], 2
0x180031850  jmp     short loc_180031870
0x180031852  mov     rdx, rsi; String2
0x180031855  lea     rcx, aReadwrite_0; "readwrite"
0x18003185c  call    cs:__imp__wcsicmp
0x180031862  test    eax, eax
0x180031864  jnz     short loc_18003186E
0x180031866  mov     dword ptr [rdi], 4
0x18003186c  jmp     short loc_180031870
0x18003186e  xor     bl, bl
0x180031870  mov     rsi, [rsp+28h+arg_8]
0x180031875  mov     al, bl
0x180031877  mov     rbx, [rsp+28h+arg_0]
0x18003187c  add     rsp, 20h
0x180031880  pop     rdi
0x180031881  retn
```
