# SwitchKeyToSoftwareOnly

- ea: `0x1400028e8`
- end: `0x140002925`
- name: `SwitchKeyToSoftwareOnly`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001064`
- `0x140002510`

## callees

- `0x1400028e8`

## import_xrefs

- `cng!BCryptSetProperty` at `0x140002913`
- `cng!BCryptSetProperty` at `0x140002913`

## pseudocode

```c
NTSTATUS __fastcall SwitchKeyToSoftwareOnly(__int64 a1)
{
  NTSTATUS result; // eax

  if ( !*(_BYTE *)(a1 + 12) )
  {
    *(_BYTE *)(a1 + 12) = 1;
    return BCryptSetProperty(*(BCRYPT_HANDLE *)(a1 + 16), L"IV", (PUCHAR)(a1 + 40), 0x10u, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1400028e8  sub     rsp, 38h
0x1400028ec  cmp     byte ptr [rcx+0Ch], 0
0x1400028f0  jnz     short loc_14000291F
0x1400028f2  mov     byte ptr [rcx+0Ch], 1
0x1400028f6  lea     r8, [rcx+28h]; pbInput
0x1400028fa  mov     rcx, [rcx+10h]; hObject
0x1400028fe  lea     rdx, aIv; "IV"
0x140002905  mov     r9d, 10h; cbInput
0x14000290b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x140002913  call    cs:__imp_BCryptSetProperty
0x14000291a  nop     dword ptr [rax+rax+00h]
0x14000291f  add     rsp, 38h
0x140002923  retn
```
