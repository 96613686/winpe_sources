# MinComObject<CSDKConfigurationController>::`vector deleting destructor'(uint)

- ea: `0x18000e800`
- end: `0x18000e834`
- name: `??_E?$MinComObject@VCSDKConfigurationController@@@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000b7e0`
- `0x18000e7e8`
- `0x18000e800`

## pseudocode

```c
void *__fastcall MinComObject<CSDKConfigurationController>::`vector deleting destructor'(void *Block, char a2)
{
  MinComObject<CSDKConfigurationController>::~MinComObject<CSDKConfigurationController>();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000e800  mov     [rsp+arg_0], rbx
0x18000e805  push    rdi
0x18000e806  sub     rsp, 20h
0x18000e80a  mov     ebx, edx
0x18000e80c  mov     rdi, rcx
0x18000e80f  call    ??1?$MinComObject@VCSDKConfigurationController@@@@UEAA@XZ; MinComObject<CSDKConfigurationController>::~MinComObject<CSDKConfigurationController>(void)
0x18000e814  test    bl, 1
0x18000e817  jz      short loc_18000E826
0x18000e819  mov     edx, 10h
0x18000e81e  mov     rcx, rdi; Block
0x18000e821  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e826  mov     rbx, [rsp+28h+arg_0]
0x18000e82b  mov     rax, rdi
0x18000e82e  add     rsp, 20h
0x18000e832  pop     rdi
0x18000e833  retn
```
