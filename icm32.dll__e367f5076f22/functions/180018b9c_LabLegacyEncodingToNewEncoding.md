# LabLegacyEncodingToNewEncoding

- ea: `0x180018b9c`
- end: `0x180018c0f`
- name: `LabLegacyEncodingToNewEncoding`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`

## callees

- `0x180018b9c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180018bbf`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180018bbf`

## pseudocode

```c
__int64 __fastcall LabLegacyEncodingToNewEncoding(unsigned __int16 *a1, int a2)
{
  __int64 result; // rax
  unsigned __int16 *v5; // rdx
  __int64 v6; // r8
  unsigned __int16 v7; // cx

  EventWrite(g_etwHandle, &ADJUST_LAB_TO_V4, 0, 0);
  result = (unsigned int)(3 * a2);
  v5 = a1;
  v6 = (int)result;
  if ( (int)result > 0 )
  {
    do
    {
      v7 = *v5;
      if ( *v5 > 0xFF00u )
        v7 = -256;
      *v5++ = v7 + HIBYTE(v7);
      result = v5 - a1;
    }
    while ( result < v6 );
  }
  return result;
}

```

## disassembly

```asm
0x180018b9c  mov     [rsp+arg_0], rbx
0x180018ba1  push    rdi
0x180018ba2  sub     rsp, 20h
0x180018ba6  mov     ebx, edx
0x180018ba8  mov     rdi, rcx
0x180018bab  mov     rcx, cs:g_etwHandle; RegHandle
0x180018bb2  lea     rdx, ADJUST_LAB_TO_V4; EventDescriptor
0x180018bb9  xor     r9d, r9d; UserData
0x180018bbc  xor     r8d, r8d; UserDataCount
0x180018bbf  call    cs:__imp_EventWrite
0x180018bc5  lea     eax, [rbx+rbx*2]
0x180018bc8  mov     rdx, rdi
0x180018bcb  movsxd  r8, eax
0x180018bce  test    eax, eax
0x180018bd0  jle     short loc_180018C04
0x180018bd2  mov     r9d, 0FF00h
0x180018bd8  movzx   ecx, word ptr [rdx]
0x180018bdb  cmp     cx, r9w
0x180018bdf  jbe     short loc_180018BE5
0x180018be1  movzx   ecx, r9w
0x180018be5  movzx   eax, cx
0x180018be8  shr     ax, 8
0x180018bec  add     ax, cx
0x180018bef  mov     [rdx], ax
0x180018bf2  add     rdx, 2
0x180018bf6  mov     rax, rdx
0x180018bf9  sub     rax, rdi
0x180018bfc  sar     rax, 1
0x180018bff  cmp     rax, r8
0x180018c02  jl      short loc_180018BD8
0x180018c04  mov     rbx, [rsp+28h+arg_0]
0x180018c09  add     rsp, 20h
0x180018c0d  pop     rdi
0x180018c0e  retn
```
