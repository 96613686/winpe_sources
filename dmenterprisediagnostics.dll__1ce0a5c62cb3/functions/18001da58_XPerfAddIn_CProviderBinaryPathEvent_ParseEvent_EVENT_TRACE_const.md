# XPerfAddIn::CProviderBinaryPathEvent::ParseEvent(_EVENT_TRACE const *)

- ea: `0x18001da58`
- end: `0x18001db5d`
- name: `?ParseEvent@CProviderBinaryPathEvent@XPerfAddIn@@QEAAJPEBU_EVENT_TRACE@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this, const struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d360`

## callees

- `0x18000c3d8`
- `0x18001c244`
- `0x18001c58c`
- `0x18001da58`

## pseudocode

```c
__int64 __fastcall XPerfAddIn::CProviderBinaryPathEvent::ParseEvent(
        XPerfAddIn::CProviderBinaryPathEvent *this,
        const struct _EVENT_TRACE *a2)
{
  unsigned __int64 MofLength; // rsi
  unsigned int *MofData; // r15
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rdi
  __int64 v8; // r14
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int64 i; // r8
  ATL::CAtlException *v14; // [rsp+20h] [rbp-28h] BYREF

  if ( !a2->MofData )
    return 262403;
  MofLength = a2->MofLength;
  if ( MofLength < 4 )
    return 262403;
  MofData = (unsigned int *)a2->MofData;
  v6 = MofLength - 4;
  v7 = *MofData;
  v8 = 16 * v7;
  if ( v6 < 16 * v7 )
    return 262403;
  try
  {
    v9 = *(_QWORD *)this;
    v10 = (__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 4;
    if ( v7 < v10 )
    {
      v11 = v9 + v8;
LABEL_13:
      *((_QWORD *)this + 1) = v11;
      goto LABEL_14;
    }
    if ( v7 > v10 )
    {
      if ( v7 <= (*((_QWORD *)this + 2) - v9) >> 4 )
      {
        v11 = std::_Uninitialized_value_construct_n<std::allocator<_GUID>>(*((_QWORD *)this + 1), v7 - v10);
        goto LABEL_13;
      }
      std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(this, *MofData);
    }
LABEL_14:
    v12 = v6 - v8;
    for ( i = 0; i < v7; ++i )
      *(_OWORD *)(*(_QWORD *)this + 16 * i) = *(_OWORD *)&MofData[4 * i + 1];
    ATL::CSimpleStringT<unsigned short,0>::SetString(
      (char *)this + 24,
      &MofData[(unsigned __int64)v8 / 4 + 1],
      (unsigned int)(v12 >> 1));
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException *v14 )
  {
    return *(unsigned int *)v14;
  }
  return 0;
}

```

## disassembly

```asm
0x18001da58  mov     [rsp+arg_0], rbx
0x18001da5d  mov     [rsp+arg_10], rsi
0x18001da62  push    rdi
0x18001da63  push    r14
0x18001da65  push    r15
0x18001da67  sub     rsp, 30h
0x18001da6b  mov     rbx, rcx
0x18001da6e  cmp     qword ptr [rdx+48h], 0
0x18001da73  jnz     short loc_18001DA7F
0x18001da75  mov     eax, 40103h
0x18001da7a  jmp     loc_18001DB48
0x18001da7f  mov     esi, [rdx+50h]
0x18001da82  cmp     rsi, 4
0x18001da86  jnb     short loc_18001DA92
0x18001da88  mov     eax, 40103h
0x18001da8d  jmp     loc_18001DB48
0x18001da92  mov     r15, [rdx+48h]
0x18001da96  add     rsi, 0FFFFFFFFFFFFFFFCh
0x18001da9a  mov     edi, [r15]
0x18001da9d  mov     r14d, edi
0x18001daa0  shl     r14, 4
0x18001daa4  cmp     rsi, r14
0x18001daa7  jnb     short loc_18001DAB3
0x18001daa9  mov     eax, 40103h
0x18001daae  jmp     loc_18001DB48
0x18001dab3  mov     rdx, [rcx]
0x18001dab6  mov     rcx, [rcx+8]
0x18001daba  sub     rcx, rdx
0x18001dabd  sar     rcx, 4
0x18001dac1  cmp     rdi, rcx
0x18001dac4  jnb     short loc_18001DACC
0x18001dac6  lea     rax, [rdx+r14]
0x18001daca  jmp     short loc_18001DAF7
0x18001dacc  jbe     short loc_18001DAFB
0x18001dace  mov     rax, [rbx+10h]
0x18001dad2  sub     rax, rdx
0x18001dad5  sar     rax, 4
0x18001dad9  mov     rdx, rdi
0x18001dadc  cmp     rdi, rax
0x18001dadf  jbe     short loc_18001DAEB
0x18001dae1  mov     rcx, rbx
0x18001dae4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001dae9  jmp     short loc_18001DAFB
0x18001daeb  sub     rdx, rcx
0x18001daee  mov     rcx, [rbx+8]
0x18001daf2  call    ??$_Uninitialized_value_construct_n@V?$allocator@U_GUID@@@std@@@std@@YAPEAU_GUID@@PEAU1@_KAEAV?$allocator@U_GUID@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<_GUID>>(_GUID *,unsigned __int64,std::allocator<_GUID> &)
0x18001daf7  mov     [rbx+8], rax
0x18001dafb  lea     rdx, [r15+4]
0x18001daff  add     rdx, r14
0x18001db02  sub     rsi, r14
0x18001db05  xor     r8d, r8d
0x18001db08  test    rdi, rdi
0x18001db0b  jz      short loc_18001DB29
0x18001db0d  mov     rcx, r8
0x18001db10  add     rcx, rcx
0x18001db13  mov     rax, [rbx]
0x18001db16  movups  xmm0, xmmword ptr [r15+rcx*8+4]
0x18001db1c  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x18001db21  inc     r8
0x18001db24  cmp     r8, rdi
0x18001db27  jb      short loc_18001DB0D
0x18001db29  shr     rsi, 1
0x18001db2c  lea     rcx, [rbx+18h]
0x18001db30  mov     r8d, esi
0x18001db33  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001db38  nop
0x18001db39  xor     eax, eax
0x18001db3b  jmp     short loc_18001DB48
0x18001db3d  mov     eax, 8007000Eh
0x18001db42  jmp     short loc_18001DB48
0x18001db44  mov     eax, [rsp+48h+arg_8]
0x18001db48  mov     rbx, [rsp+48h+arg_0]
0x18001db4d  mov     rsi, [rsp+48h+arg_10]
0x18001db52  add     rsp, 30h
0x18001db56  pop     r15
0x18001db58  pop     r14
0x18001db5a  pop     rdi
0x18001db5b  retn
```
