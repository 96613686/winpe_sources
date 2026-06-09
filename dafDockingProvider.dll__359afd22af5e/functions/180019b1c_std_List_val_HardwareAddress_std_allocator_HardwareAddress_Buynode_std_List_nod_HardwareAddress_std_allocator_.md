# std::_List_val<HardwareAddress,std::allocator<HardwareAddress>>::_Buynode(std::_List_nod<HardwareAddress,std::allocator<HardwareAddress>>::_Node *,std::_List_nod<HardwareAddress,std::allocator<HardwareAddress>>::_Node *,HardwareAddress const &)

- ea: `0x180019b1c`
- end: `0x180019bda`
- name: `?_Buynode@?$_List_val@VHardwareAddress@@V?$allocator@VHardwareAddress@@@std@@@std@@QEAAPEAU_Node@?$_List_nod@VHardwareAddress@@V?$allocator@VHardwareAddress@@@std@@@2@PEAU342@0AEBVHardwareAddress@@@Z`
- size: `190`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001884c`

## callees

- `0x180001484`
- `0x1800020bd`
- `0x18001117c`
- `0x180019b1c`

## pseudocode

```c
_QWORD *__fastcall std::_List_val<HardwareAddress>::_Buynode(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *result; // rax
  const char *v8; // rdx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  result = operator new(0x20u);
  if ( !result )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v8);
    throw (std::bad_alloc *)pExceptionObject;
  }
  *result = a2;
  result[1] = a3;
  *((_DWORD *)result + 6) = *(_DWORD *)(a4 + 8);
  *((_WORD *)result + 14) = *(_WORD *)(a4 + 12);
  result[2] = *((unsigned __int8 *)result + 29)
            | ((*((unsigned __int8 *)result + 28)
              | ((*((unsigned __int8 *)result + 27)
                | ((*((unsigned __int8 *)result + 26)
                  | ((*((unsigned __int8 *)result + 25) | ((unsigned __int64)*((unsigned __int8 *)result + 24) << 8)) << 8)) << 8)) << 8)) << 8);
  return result;
}

```

## disassembly

```asm
0x180019b1c  mov     [rsp+arg_8], rbx
0x180019b21  mov     [rsp+arg_10], rsi
0x180019b26  mov     [rsp+arg_0], rcx
0x180019b2b  push    rdi
0x180019b2c  sub     rsp, 40h
0x180019b30  mov     rbx, r9
0x180019b33  mov     rdi, r8
0x180019b36  mov     rsi, rdx
0x180019b39  mov     ecx, 20h ; ' '; Size
0x180019b3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019b43  mov     r10, rax
0x180019b46  mov     [rsp+48h+arg_0], rax
0x180019b4b  test    rax, rax
0x180019b4e  jz      short loc_180019BBE
0x180019b50  mov     [rax], rsi
0x180019b53  mov     [rax+8], rdi
0x180019b57  mov     ecx, [rbx+8]
0x180019b5a  mov     [rax+18h], ecx
0x180019b5d  movzx   eax, word ptr [rbx+0Ch]
0x180019b61  mov     [r10+1Ch], ax
0x180019b66  movzx   ecx, byte ptr [r10+18h]
0x180019b6b  shl     rcx, 8
0x180019b6f  movzx   eax, byte ptr [r10+19h]
0x180019b74  or      rcx, rax
0x180019b77  shl     rcx, 8
0x180019b7b  movzx   eax, byte ptr [r10+1Ah]
0x180019b80  or      rcx, rax
0x180019b83  shl     rcx, 8
0x180019b87  movzx   eax, byte ptr [r10+1Bh]
0x180019b8c  or      rcx, rax
0x180019b8f  shl     rcx, 8
0x180019b93  movzx   eax, byte ptr [r10+1Ch]
0x180019b98  or      rcx, rax
0x180019b9b  shl     rcx, 8
0x180019b9f  movzx   eax, byte ptr [r10+1Dh]
0x180019ba4  or      rcx, rax
0x180019ba7  mov     [r10+10h], rcx
0x180019bab  mov     rax, r10
0x180019bae  mov     rbx, [rsp+48h+arg_8]
0x180019bb3  mov     rsi, [rsp+48h+arg_10]
0x180019bb8  add     rsp, 40h
0x180019bbc  pop     rdi
0x180019bbd  retn
0x180019bbe  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180019bc3  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180019bc8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180019bcf  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180019bd4  call    _CxxThrowException_0
```
