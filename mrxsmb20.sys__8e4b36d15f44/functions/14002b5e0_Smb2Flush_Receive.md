# Smb2Flush_Receive

- ea: `0x14002b5e0`
- end: `0x14002b667`
- name: `Smb2Flush_Receive`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, int, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14002b5e0`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002b60d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002b60d`

## pseudocode

```c
__int64 __fastcall Smb2Flush_Receive(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, int a5, _DWORD *a6)
{
  int v6; // ebx
  __int64 result; // rax

  v6 = *(_DWORD *)(a3 + 16);
  *a6 = a5;
  if ( !v6 )
  {
    if ( a4 >= 0x44 )
    {
      if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 64) & 1) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                        * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                       % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88)
                                                                                               + 424LL)
                                                                                   + 1488LL))
                                                        + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                        + 84));
    }
    else
    {
      v6 = -1073741629;
    }
  }
  *(_DWORD *)(a1 + 16) = v6;
  result = 0;
  *(_DWORD *)(a1 + 20) = 0;
  return result;
}

```

## disassembly

```asm
0x14002b5e0  mov     [rsp+arg_0], rbx
0x14002b5e5  push    rdi
0x14002b5e6  sub     rsp, 20h
0x14002b5ea  mov     ebx, [r8+10h]
0x14002b5ee  mov     rdi, rcx
0x14002b5f1  mov     rdx, [rsp+28h+arg_28]
0x14002b5f6  mov     eax, [rsp+28h+arg_20]
0x14002b5fa  mov     [rdx], eax
0x14002b5fc  test    ebx, ebx
0x14002b5fe  jnz     short loc_14002B64F
0x14002b600  cmp     r9d, 44h ; 'D'
0x14002b604  jnb     short loc_14002B60D
0x14002b606  mov     ebx, 0C00000C3h
0x14002b60b  jmp     short loc_14002B64F
0x14002b60d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002b614  nop     dword ptr [rax+rax+00h]
0x14002b619  test    byte ptr [rax+40h], 1
0x14002b61d  jz      short loc_14002B64F
0x14002b61f  mov     rax, [rdi+58h]
0x14002b623  xor     edx, edx
0x14002b625  mov     r8, [rax+1A8h]
0x14002b62c  mov     eax, gs:1A4h
0x14002b634  div     dword ptr [r8+5D0h]
0x14002b63b  mov     rax, [r8+5C8h]
0x14002b642  lea     rdx, [rdx+rdx*2]
0x14002b646  shl     rdx, 6
0x14002b64a  lock inc dword ptr [rdx+rax+54h]
0x14002b64f  mov     [rdi+10h], ebx
0x14002b652  xor     eax, eax
0x14002b654  mov     rbx, [rsp+28h+arg_0]
0x14002b659  mov     dword ptr [rdi+14h], 0
0x14002b660  add     rsp, 20h
0x14002b664  pop     rdi
0x14002b665  retn
```
