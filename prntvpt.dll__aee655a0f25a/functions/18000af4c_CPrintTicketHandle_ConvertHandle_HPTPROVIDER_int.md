# CPrintTicketHandle::ConvertHandle(HPTPROVIDER__ *,int)

- ea: `0x18000af4c`
- end: `0x18000afa2`
- name: `?ConvertHandle@CPrintTicketHandle@@SAPEAV1@PEAUHPTPROVIDER__@@H@Z`
- size: `86`
- prototype: `struct CPrintTicketHandle *__fastcall(HPTPROVIDER, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac80`
- `0x18000adb0`
- `0x18000ae80`
- `0x180018d70`
- `0x180018f10`
- `0x180019050`
- `0x1800191a0`

## callees

- `0x18000af4c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000af6e`
- `KERNEL32!GetCurrentThreadId` at `0x18000af6e`

## pseudocode

```c
struct CPrintTicketHandle *__fastcall CPrintTicketHandle::ConvertHandle(HPTPROVIDER a1, int a2)
{
  int v4; // ebx

  if ( a1 && *((HPTPROVIDER *)a1 + 1) == a1 )
  {
    v4 = *((_DWORD *)a1 + 4);
    if ( GetCurrentThreadId() == v4 )
      return (struct CPrintTicketHandle *)a1;
    if ( *((_DWORD *)a1 + 9) )
    {
      if ( a2 )
        *((_DWORD *)a1 + 8) = 0;
      return (struct CPrintTicketHandle *)a1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000af4c  mov     [rsp+arg_0], rbx
0x18000af51  mov     [rsp+arg_8], rsi
0x18000af56  push    rdi
0x18000af57  sub     rsp, 20h
0x18000af5b  mov     esi, edx
0x18000af5d  mov     rdi, rcx
0x18000af60  test    rcx, rcx
0x18000af63  jz      short loc_18000AF8B
0x18000af65  cmp     [rcx+8], rcx
0x18000af69  jnz     short loc_18000AF8B
0x18000af6b  mov     ebx, [rcx+10h]
0x18000af6e  call    cs:__imp_GetCurrentThreadId
0x18000af74  cmp     eax, ebx
0x18000af76  jnz     short loc_18000AF8F
0x18000af78  mov     rax, rdi
0x18000af7b  mov     rbx, [rsp+28h+arg_0]
0x18000af80  mov     rsi, [rsp+28h+arg_8]
0x18000af85  add     rsp, 20h
0x18000af89  pop     rdi
0x18000af8a  retn
0x18000af8b  xor     eax, eax
0x18000af8d  jmp     short loc_18000AF7B
0x18000af8f  cmp     dword ptr [rdi+24h], 0
0x18000af93  jz      short loc_18000AF8B
0x18000af95  test    esi, esi
0x18000af97  jz      short loc_18000AF78
0x18000af99  mov     dword ptr [rdi+20h], 0
0x18000afa0  jmp     short loc_18000AF78
```
