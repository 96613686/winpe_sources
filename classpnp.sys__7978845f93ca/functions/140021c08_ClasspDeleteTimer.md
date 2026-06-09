# ClasspDeleteTimer

- ea: `0x140021c08`
- end: `0x140021c70`
- name: `ClasspDeleteTimer`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400231f0`
- `0x1400579b4`

## callees

- `0x140021c08`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x140021c44`
- `ntoskrnl!ExDeleteTimer` at `0x140021c44`

## pseudocode

```c
__int64 __fastcall ClasspDeleteTimer(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 result; // rax
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h]

  LOBYTE(a2) = 1;
  if ( (*(_BYTE *)(a1 + 104) & 1) != 0 )
  {
    v2 = *(_QWORD *)(a1 + 1144);
    if ( v2 )
    {
      v3 = *(_QWORD *)(v2 + 928);
      if ( v3 )
      {
        v5 = 0;
        v6 = 0;
        result = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int128 *))ExDeleteTimer)(v3, a2, 0, &v5);
        *(_QWORD *)(v2 + 928) = 0;
      }
      *(_BYTE *)(v2 + 1504) = 0;
      *(_BYTE *)(v2 + 1581) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140021c08  push    rbx
0x140021c0a  sub     rsp, 40h
0x140021c0e  mov     dl, 1
0x140021c10  test    [rcx+68h], dl
0x140021c13  jz      short loc_140021C69
0x140021c15  mov     rbx, [rcx+478h]
0x140021c1c  test    rbx, rbx
0x140021c1f  jz      short loc_140021C69
0x140021c21  mov     rcx, [rbx+3A0h]
0x140021c28  test    rcx, rcx
0x140021c2b  jz      short loc_140021C5B
0x140021c2d  xorps   xmm0, xmm0
0x140021c30  lea     r9, [rsp+48h+var_28]
0x140021c35  xor     eax, eax
0x140021c37  xor     r8d, r8d
0x140021c3a  movups  [rsp+48h+var_28], xmm0
0x140021c3f  mov     [rsp+48h+var_18], rax
0x140021c44  call    cs:__imp_ExDeleteTimer
0x140021c4b  nop     dword ptr [rax+rax+00h]
0x140021c50  mov     qword ptr [rbx+3A0h], 0
0x140021c5b  mov     byte ptr [rbx+5E0h], 0
0x140021c62  mov     byte ptr [rbx+62Dh], 0
0x140021c69  add     rsp, 40h
0x140021c6d  pop     rbx
0x140021c6e  retn
```
