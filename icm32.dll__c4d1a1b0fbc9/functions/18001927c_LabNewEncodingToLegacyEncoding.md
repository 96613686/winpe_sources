# LabNewEncodingToLegacyEncoding

- ea: `0x18001927c`
- end: `0x1800192df`
- name: `LabNewEncodingToLegacyEncoding`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`
- `0x18003cb08`

## callees

- `0x18001927c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001929f`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001929f`

## pseudocode

```c
__int64 __fastcall LabNewEncodingToLegacyEncoding(_WORD *a1, int a2)
{
  __int64 result; // rax
  _WORD *v5; // rdx
  __int64 v6; // r8

  EventWrite(g_etwHandle, &ADJUST_LAB_TO_LEGACY, 0, 0);
  result = (unsigned int)(3 * a2);
  v5 = a1;
  v6 = (int)result;
  if ( (int)result > 0 )
  {
    do
    {
      *v5 -= HIBYTE(*v5);
      result = ++v5 - a1;
    }
    while ( result < v6 );
  }
  return result;
}

```

## disassembly

```asm
0x18001927c  mov     [rsp+arg_0], rbx
0x180019281  push    rdi
0x180019282  sub     rsp, 20h
0x180019286  mov     ebx, edx
0x180019288  mov     rdi, rcx
0x18001928b  mov     rcx, cs:g_etwHandle; RegHandle
0x180019292  lea     rdx, ADJUST_LAB_TO_LEGACY; EventDescriptor
0x180019299  xor     r9d, r9d; UserData
0x18001929c  xor     r8d, r8d; UserDataCount
0x18001929f  call    cs:__imp_EventWrite
0x1800192a5  lea     eax, [rbx+rbx*2]
0x1800192a8  mov     rdx, rdi
0x1800192ab  movsxd  r8, eax
0x1800192ae  test    eax, eax
0x1800192b0  jle     short loc_1800192D4
0x1800192b2  movzx   ecx, word ptr [rdx]
0x1800192b5  movzx   eax, cx
0x1800192b8  shr     ax, 8
0x1800192bc  sub     cx, ax
0x1800192bf  mov     [rdx], cx
0x1800192c2  add     rdx, 2
0x1800192c6  mov     rax, rdx
0x1800192c9  sub     rax, rdi
0x1800192cc  sar     rax, 1
0x1800192cf  cmp     rax, r8
0x1800192d2  jl      short loc_1800192B2
0x1800192d4  mov     rbx, [rsp+28h+arg_0]
0x1800192d9  add     rsp, 20h
0x1800192dd  pop     rdi
0x1800192de  retn
```
