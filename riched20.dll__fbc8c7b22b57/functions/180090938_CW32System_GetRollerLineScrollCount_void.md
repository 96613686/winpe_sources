# CW32System::GetRollerLineScrollCount(void)

- ea: `0x180090938`
- end: `0x18009096d`
- name: `?GetRollerLineScrollCount@CW32System@@SAJXZ`
- size: `53`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18005d438`
- `0x18006adf4`

## callees

- `0x180090938`

## import_xrefs

- `USER32!SystemParametersInfoA` at `0x180090955`
- `USER32!SystemParametersInfoA` at `0x180090955`

## pseudocode

```c
__int64 CW32System::GetRollerLineScrollCount(void)
{
  __int64 result; // rax

  result = (unsigned int)CW32System::_cLineScroll;
  if ( !CW32System::_cLineScroll )
  {
    SystemParametersInfoA(0x68u, 0, &CW32System::_cLineScroll, 0);
    return (unsigned int)CW32System::_cLineScroll;
  }
  return result;
}

```

## disassembly

```asm
0x180090938  sub     rsp, 28h
0x18009093c  mov     eax, cs:?_cLineScroll@CW32System@@0JA; long CW32System::_cLineScroll
0x180090942  test    eax, eax
0x180090944  jnz     short loc_180090967
0x180090946  xor     r9d, r9d; fWinIni
0x180090949  lea     r8, ?_cLineScroll@CW32System@@0JA; pvParam
0x180090950  xor     edx, edx; uiParam
0x180090952  lea     ecx, [rax+68h]; uiAction
0x180090955  call    cs:__imp_SystemParametersInfoA
0x18009095c  nop     dword ptr [rax+rax+00h]
0x180090961  mov     eax, cs:?_cLineScroll@CW32System@@0JA; long CW32System::_cLineScroll
0x180090967  add     rsp, 28h
0x18009096b  retn
```
