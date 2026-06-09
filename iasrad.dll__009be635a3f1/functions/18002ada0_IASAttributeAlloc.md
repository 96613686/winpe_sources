# IASAttributeAlloc

- ea: `0x18002ada0`
- end: `0x18002ae1a`
- name: `IASAttributeAlloc`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012c68`
- `0x180017544`
- `0x1800181e8`
- `0x18001b0ec`
- `0x18001b4a0`

## callees

- `0x18002ada0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002adf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002adf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002adc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002adc0`

## pseudocode

```c
__int64 __fastcall IASAttributeAlloc(int a1, LPVOID *a2)
{
  LPVOID *i; // rbx
  _OWORD *v5; // rax
  _DWORD *v6; // rax

  for ( i = a2; ; ++i )
  {
    if ( !a1 )
      return 0;
    v5 = CoTaskMemAlloc(0x28u);
    *i = v5;
    if ( !v5 )
      break;
    *v5 = 0;
    --a1;
    v5[1] = 0;
    *((_QWORD *)v5 + 4) = 0;
    v6 = *i;
    *v6 = 1;
  }
  while ( i > a2 )
    CoTaskMemFree(*--i);
  return 8;
}

```

## disassembly

```asm
0x18002ada0  mov     [rsp+arg_0], rbx
0x18002ada5  mov     [rsp+arg_8], rsi
0x18002adaa  push    rdi
0x18002adab  sub     rsp, 20h
0x18002adaf  mov     rdi, rdx
0x18002adb2  mov     esi, ecx
0x18002adb4  mov     rbx, rdx
0x18002adb7  test    esi, esi
0x18002adb9  jz      short loc_18002AE08
0x18002adbb  mov     ecx, 28h ; '('; cb
0x18002adc0  call    cs:__imp_CoTaskMemAlloc
0x18002adc6  mov     [rbx], rax
0x18002adc9  test    rax, rax
0x18002adcc  jz      short loc_18002ADFC
0x18002adce  xorps   xmm0, xmm0
0x18002add1  xor     ecx, ecx
0x18002add3  movups  xmmword ptr [rax], xmm0
0x18002add6  dec     esi
0x18002add8  movups  xmmword ptr [rax+10h], xmm0
0x18002addc  mov     [rax+20h], rcx
0x18002ade0  mov     rax, [rbx]
0x18002ade3  add     rbx, 8
0x18002ade7  mov     dword ptr [rax], 1
0x18002aded  jmp     short loc_18002ADB7
0x18002adef  sub     rbx, 8
0x18002adf3  mov     rcx, [rbx]; pv
0x18002adf6  call    cs:__imp_CoTaskMemFree
0x18002adfc  cmp     rbx, rdi
0x18002adff  ja      short loc_18002ADEF
0x18002ae01  mov     eax, 8
0x18002ae06  jmp     short loc_18002AE0A
0x18002ae08  xor     eax, eax
0x18002ae0a  mov     rbx, [rsp+28h+arg_0]
0x18002ae0f  mov     rsi, [rsp+28h+arg_8]
0x18002ae14  add     rsp, 20h
0x18002ae18  pop     rdi
0x18002ae19  retn
```
