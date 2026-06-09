# CMGetPartialProfileElement

- ea: `0x18000604c`
- end: `0x1800060e8`
- name: `CMGetPartialProfileElement`
- size: `156`
- prototype: `__int64 __fastcall(HPROFILE hProfile, TAGTYPE tag, DWORD dwOffset, PDWORD pcbElement, PVOID)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c0c`
- `0x1800042fc`
- `0x18000464c`
- `0x180005c70`
- `0x180006f00`
- `0x180007130`
- `0x180007418`
- `0x180019b00`
- `0x18001bb30`
- `0x18001c4a0`
- `0x18001de14`
- `0x18001e97c`
- `0x18001ef48`
- `0x18001f14c`
- `0x18001f23c`
- `0x180020828`
- `0x180020ae4`
- `0x180020c14`
- `0x180021060`
- `0x1800211ec`
- `0x18002145c`
- `0x180021554`
- `0x18002167c`
- `0x18003cb08`

## callees

- `0x18000604c`

## import_xrefs

- `mscms!GetColorProfileElement` at `0x1800060a4`
- `mscms!GetColorProfileElement` at `0x1800060a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006078`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060b3`

## pseudocode

```c
__int64 __fastcall CMGetPartialProfileElement(
        HPROFILE hProfile,
        TAGTYPE tag,
        DWORD dwOffset,
        PDWORD pcbElement,
        PVOID a5)
{
  PVOID pElement; // rbx
  WINBOOL pbReference; // [rsp+68h] [rbp+20h] BYREF

  pbReference = 0;
  if ( !pcbElement )
    return 0xFFFFFFFFLL;
  SetLastError(0);
  pElement = a5;
  if ( !a5 )
    *pcbElement = 0;
  if ( GetColorProfileElement(hProfile, tag, dwOffset, pcbElement, pElement, &pbReference) )
    return 0;
  if ( pElement )
    return 2012;
  return GetLastError() != 122 ? 0x7DC : 0;
}

```

## disassembly

```asm
0x18000604c  mov     [rsp+arg_0], rbx
0x180006051  mov     [rsp+arg_8], rbp
0x180006056  push    rsi
0x180006057  push    rdi
0x180006058  push    r14
0x18000605a  sub     rsp, 30h
0x18000605e  mov     [rsp+48h+arg_18], 0
0x180006066  mov     rdi, r9
0x180006069  mov     esi, r8d
0x18000606c  mov     ebp, edx
0x18000606e  mov     r14, rcx
0x180006071  test    r9, r9
0x180006074  jz      short loc_1800060E3
0x180006076  xor     ecx, ecx; dwErrCode
0x180006078  call    cs:__imp_SetLastError
0x18000607e  mov     rbx, [rsp+48h+arg_20]
0x180006083  test    rbx, rbx
0x180006086  jnz     short loc_18000608A
0x180006088  mov     [rdi], ebx
0x18000608a  lea     rax, [rsp+48h+arg_18]
0x18000608f  mov     r9, rdi; pcbElement
0x180006092  mov     [rsp+48h+pbReference], rax; pbReference
0x180006097  mov     r8d, esi; dwOffset
0x18000609a  mov     edx, ebp; tag
0x18000609c  mov     [rsp+48h+pElement], rbx; pElement
0x1800060a1  mov     rcx, r14; hProfile
0x1800060a4  call    cs:__imp_GetColorProfileElement
0x1800060aa  test    eax, eax
0x1800060ac  jnz     short loc_1800060DF
0x1800060ae  test    rbx, rbx
0x1800060b1  jnz     short loc_1800060D8
0x1800060b3  call    cs:__imp_GetLastError
0x1800060b9  sub     eax, 7Ah ; 'z'
0x1800060bc  neg     eax
0x1800060be  sbb     eax, eax
0x1800060c0  and     eax, 7DCh
0x1800060c5  mov     rbx, [rsp+48h+arg_0]
0x1800060ca  mov     rbp, [rsp+48h+arg_8]
0x1800060cf  add     rsp, 30h
0x1800060d3  pop     r14
0x1800060d5  pop     rdi
0x1800060d6  pop     rsi
0x1800060d7  retn
0x1800060d8  mov     eax, 7DCh
0x1800060dd  jmp     short loc_1800060C5
0x1800060df  xor     eax, eax
0x1800060e1  jmp     short loc_1800060C5
0x1800060e3  or      eax, 0FFFFFFFFh
0x1800060e6  jmp     short loc_1800060C5
```
