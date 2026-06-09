# TokenBindingGetHighestSupportedVersion

- ea: `0x1800236a0`
- end: `0x1800236f5`
- name: `TokenBindingGetHighestSupportedVersion`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007bd8`
- `0x1800236a0`

## pseudocode

```c
__int64 __fastcall TokenBindingGetHighestSupportedVersion(_BYTE *a1, _BYTE *a2)
{
  if ( !a1 || !a2 )
    return 2148073511LL;
  *a1 = 0;
  *a2 = 16;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 23, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x1800236a0  sub     rsp, 28h
0x1800236a4  test    rcx, rcx
0x1800236a7  jz      short loc_1800236EA
0x1800236a9  test    rdx, rdx
0x1800236ac  jz      short loc_1800236EA
0x1800236ae  mov     byte ptr [rcx], 0
0x1800236b1  mov     byte ptr [rdx], 10h
0x1800236b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236bb  lea     rax, WPP_GLOBAL_Control
0x1800236c2  cmp     rcx, rax
0x1800236c5  jz      short loc_1800236E6
0x1800236c7  mov     eax, [rcx+2Ch]
0x1800236ca  test    al, 4
0x1800236cc  jz      short loc_1800236E6
0x1800236ce  mov     rcx, [rcx+18h]
0x1800236d2  lea     r8, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids
0x1800236d9  mov     edx, 17h
0x1800236de  xor     r9d, r9d
0x1800236e1  call    WPP_SF_D
0x1800236e6  xor     eax, eax
0x1800236e8  jmp     short loc_1800236EF
0x1800236ea  mov     eax, 80090027h
0x1800236ef  add     rsp, 28h
0x1800236f3  retn
```
