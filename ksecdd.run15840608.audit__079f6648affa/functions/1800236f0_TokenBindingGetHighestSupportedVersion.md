# TokenBindingGetHighestSupportedVersion

- ea: `0x1800236f0`
- end: `0x180023745`
- name: `TokenBindingGetHighestSupportedVersion`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007bd8`
- `0x1800236f0`

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
0x1800236f0  sub     rsp, 28h
0x1800236f4  test    rcx, rcx
0x1800236f7  jz      short loc_18002373A
0x1800236f9  test    rdx, rdx
0x1800236fc  jz      short loc_18002373A
0x1800236fe  mov     byte ptr [rcx], 0
0x180023701  mov     byte ptr [rdx], 10h
0x180023704  mov     rcx, cs:WPP_GLOBAL_Control
0x18002370b  lea     rax, WPP_GLOBAL_Control
0x180023712  cmp     rcx, rax
0x180023715  jz      short loc_180023736
0x180023717  mov     eax, [rcx+2Ch]
0x18002371a  test    al, 4
0x18002371c  jz      short loc_180023736
0x18002371e  mov     rcx, [rcx+18h]
0x180023722  lea     r8, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids
0x180023729  mov     edx, 17h
0x18002372e  xor     r9d, r9d
0x180023731  call    WPP_SF_D
0x180023736  xor     eax, eax
0x180023738  jmp     short loc_18002373F
0x18002373a  mov     eax, 80090027h
0x18002373f  add     rsp, 28h
0x180023743  retn
```
