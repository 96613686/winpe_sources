# CRegKey::DeleteKey(ushort const *)

- ea: `0x18000412c`
- end: `0x1800041a1`
- name: `?DeleteKey@CRegKey@@QEBAXPEBG@Z`
- size: `117`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003fd0`

## callees

- `0x18000412c`
- `0x18000a360`
- `0x18000ab3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000413b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000413b`

## pseudocode

```c
void __fastcall CRegKey::DeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  int v2; // ebx
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v2 = RegDeleteKeyExW(*this, a2, 0, 0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_1eba886745fe349fd97ae921e3b476bf_Traceguids,
        (unsigned int)v2);
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    pExceptionObject = v2;
    throw (CExcept *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18000412c  push    rbx
0x18000412e  sub     rsp, 20h
0x180004132  mov     rcx, [rcx]; hKey
0x180004135  xor     r9d, r9d; Reserved
0x180004138  xor     r8d, r8d; samDesired
0x18000413b  call    cs:__imp_RegDeleteKeyExW
0x180004141  mov     ebx, eax
0x180004143  test    eax, eax
0x180004145  jz      short loc_18000419B
0x180004147  mov     rcx, cs:WPP_GLOBAL_Control
0x18000414e  lea     rax, WPP_GLOBAL_Control
0x180004155  cmp     rcx, rax
0x180004158  jz      short loc_180004178
0x18000415a  test    byte ptr [rcx+1Ch], 2
0x18000415e  jz      short loc_180004178
0x180004160  mov     rcx, [rcx+10h]
0x180004164  lea     r8, WPP_1eba886745fe349fd97ae921e3b476bf_Traceguids
0x18000416b  mov     edx, 0Dh
0x180004170  mov     r9d, ebx
0x180004173  call    WPP_SF_D
0x180004178  test    ebx, ebx
0x18000417a  jle     short loc_180004185
0x18000417c  movzx   ebx, bx
0x18000417f  or      ebx, 80070000h
0x180004185  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x18000418c  mov     [rsp+28h+pExceptionObject], ebx
0x180004190  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004195  call    _CxxThrowException_0
0x18000419b  add     rsp, 20h
0x18000419f  pop     rbx
0x1800041a0  retn
```
