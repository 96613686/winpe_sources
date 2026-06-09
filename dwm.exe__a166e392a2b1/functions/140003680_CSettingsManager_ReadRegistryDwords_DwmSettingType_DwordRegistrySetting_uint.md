# CSettingsManager::ReadRegistryDwords(DwmSettingType,DwordRegistrySetting *,uint)

- ea: `0x140003680`
- end: `0x1400036ca`
- name: `?ReadRegistryDwords@CSettingsManager@@UEAAJW4DwmSettingType@@PEAUDwordRegistrySetting@@I@Z`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140003680`
- `0x1400036e4`

## pseudocode

```c
__int64 __fastcall CSettingsManager::ReadRegistryDwords(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  unsigned int i; // ebx
  __int64 result; // rax

  for ( i = 0; i < a4; ++i )
  {
    result = CSettingsManager::GetDword(a1, a2, *(_QWORD *)(a3 + 16LL * i), *(_QWORD *)(a3 + 16LL * i + 8));
    if ( (int)result < 0 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x140003680  push    rbx
0x140003682  push    rbp
0x140003683  push    rsi
0x140003684  push    rdi
0x140003685  push    r14
0x140003687  sub     rsp, 20h
0x14000368b  mov     edi, r9d
0x14000368e  mov     rsi, r8
0x140003691  mov     ebp, edx
0x140003693  mov     r14, rcx
0x140003696  xor     ebx, ebx
0x140003698  cmp     ebx, edi
0x14000369a  jnb     short loc_1400036BD
0x14000369c  mov     r8d, ebx
0x14000369f  mov     edx, ebp
0x1400036a1  add     r8, r8
0x1400036a4  mov     rcx, r14
0x1400036a7  mov     r9, [rsi+r8*8+8]
0x1400036ac  mov     r8, [rsi+r8*8]
0x1400036b0  call    ?GetDword@CSettingsManager@@AEAAJW4DwmSettingType@@PEBGPEAK@Z; CSettingsManager::GetDword(DwmSettingType,ushort const *,ulong *)
0x1400036b5  test    eax, eax
0x1400036b7  js      short loc_1400036BF
0x1400036b9  inc     ebx
0x1400036bb  jmp     short loc_140003698
0x1400036bd  xor     eax, eax
0x1400036bf  add     rsp, 20h
0x1400036c3  pop     r14
0x1400036c5  pop     rdi
0x1400036c6  pop     rsi
0x1400036c7  pop     rbp
0x1400036c8  pop     rbx
0x1400036c9  retn
```
