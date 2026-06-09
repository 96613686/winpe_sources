# EapFreeEapConfigArray

- ea: `0x1800390ec`
- end: `0x1800391aa`
- name: `EapFreeEapConfigArray`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038f5c`
- `0x1800391b0`

## callees

- `0x1800390ec`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x180039134`
- `MobileNetworking!FreeMemory` at `0x180039164`
- `MobileNetworking!FreeMemory` at `0x18003918d`
- `MobileNetworking!FreeMemory` at `0x180039134`
- `MobileNetworking!FreeMemory` at `0x180039164`
- `MobileNetworking!FreeMemory` at `0x18003918d`

## string_xrefs

- `0x18003912d`: `EapFreeEapConfigArray`
- `0x18003915d`: `EapFreeEapConfigArray`
- `0x180039183`: `EapFreeEapConfigArray`

## pseudocode

```c
__int64 __fastcall EapFreeEapConfigArray(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 v3; // rsi
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  __int64 result; // rax

  v1 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 8) && *(_DWORD *)(a1 + 4) )
  {
    v3 = 0;
    do
    {
      v4 = (_QWORD *)(*v1 + 16LL + 40 * v3);
      if ( *v4 )
      {
        FreeMemory(v4, "EapFreeEapConfigArray", 62);
        *(_QWORD *)(*v1 + 40 * v3 + 16) = 0;
      }
      v5 = (_QWORD *)(*v1 + 24LL + 40 * v3);
      if ( *v5 )
      {
        FreeMemory(v5, "EapFreeEapConfigArray", 67);
        *(_QWORD *)(*v1 + 40 * v3 + 16) = 0;
      }
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < *(_DWORD *)(a1 + 4) );
    result = FreeMemory(v1, "EapFreeEapConfigArray", 71);
    *v1 = 0;
    *(_DWORD *)(a1 + 4) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800390ec  push    rbx
0x1800390ee  push    rbp
0x1800390ef  push    rsi
0x1800390f0  push    rdi
0x1800390f1  sub     rsp, 28h
0x1800390f5  lea     rbx, [rcx+8]
0x1800390f9  mov     rdi, rcx
0x1800390fc  cmp     qword ptr [rbx], 0
0x180039100  jz      loc_1800391A1
0x180039106  cmp     dword ptr [rcx+4], 0
0x18003910a  jbe     loc_1800391A1
0x180039110  xor     esi, esi
0x180039112  mov     rcx, [rbx]
0x180039115  lea     rbp, [rsi+rsi*4]
0x180039119  add     rcx, 10h
0x18003911d  lea     rcx, [rcx+rbp*8]
0x180039121  cmp     qword ptr [rcx], 0
0x180039125  jz      short loc_180039146
0x180039127  mov     r8d, 3Eh ; '>'
0x18003912d  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x180039134  call    cs:__imp_FreeMemory
0x18003913a  mov     rax, [rbx]
0x18003913d  mov     qword ptr [rax+rbp*8+10h], 0
0x180039146  mov     rcx, [rbx]
0x180039149  add     rcx, 18h
0x18003914d  lea     rcx, [rcx+rbp*8]
0x180039151  cmp     qword ptr [rcx], 0
0x180039155  jz      short loc_180039176
0x180039157  mov     r8d, 43h ; 'C'
0x18003915d  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x180039164  call    cs:__imp_FreeMemory
0x18003916a  mov     rax, [rbx]
0x18003916d  mov     qword ptr [rax+rbp*8+10h], 0
0x180039176  inc     esi
0x180039178  cmp     esi, [rdi+4]
0x18003917b  jb      short loc_180039112
0x18003917d  mov     r8d, 47h ; 'G'
0x180039183  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x18003918a  mov     rcx, rbx
0x18003918d  call    cs:__imp_FreeMemory
0x180039193  mov     qword ptr [rbx], 0
0x18003919a  mov     dword ptr [rdi+4], 0
0x1800391a1  add     rsp, 28h
0x1800391a5  pop     rdi
0x1800391a6  pop     rsi
0x1800391a7  pop     rbp
0x1800391a8  pop     rbx
0x1800391a9  retn
```
