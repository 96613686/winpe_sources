# XPerfAddIn::CProviderBinaryPathEvent::ParseEvent(_EVENT_TRACE const *)

- ea: `0x18001e594`
- end: `0x18001e699`
- name: `?ParseEvent@CProviderBinaryPathEvent@XPerfAddIn@@QEAAJPEBU_EVENT_TRACE@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this, const struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001de90`

## callees

- `0x18000c9a8`
- `0x18001cd24`
- `0x18001d068`
- `0x18001e594`

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
0x18001e594  mov     [rsp+arg_0], rbx
0x18001e599  mov     [rsp+arg_10], rsi
0x18001e59e  push    rdi
0x18001e59f  push    r14
0x18001e5a1  push    r15
0x18001e5a3  sub     rsp, 30h
0x18001e5a7  mov     rbx, rcx
0x18001e5aa  cmp     qword ptr [rdx+48h], 0
0x18001e5af  jnz     short loc_18001E5BB
0x18001e5b1  mov     eax, 40103h
0x18001e5b6  jmp     loc_18001E684
0x18001e5bb  mov     esi, [rdx+50h]
0x18001e5be  cmp     rsi, 4
0x18001e5c2  jnb     short loc_18001E5CE
0x18001e5c4  mov     eax, 40103h
0x18001e5c9  jmp     loc_18001E684
0x18001e5ce  mov     r15, [rdx+48h]
0x18001e5d2  add     rsi, 0FFFFFFFFFFFFFFFCh
0x18001e5d6  mov     edi, [r15]
0x18001e5d9  mov     r14d, edi
0x18001e5dc  shl     r14, 4
0x18001e5e0  cmp     rsi, r14
0x18001e5e3  jnb     short loc_18001E5EF
0x18001e5e5  mov     eax, 40103h
0x18001e5ea  jmp     loc_18001E684
0x18001e5ef  mov     rdx, [rcx]
0x18001e5f2  mov     rcx, [rcx+8]
0x18001e5f6  sub     rcx, rdx
0x18001e5f9  sar     rcx, 4
0x18001e5fd  cmp     rdi, rcx
0x18001e600  jnb     short loc_18001E608
0x18001e602  lea     rax, [rdx+r14]
0x18001e606  jmp     short loc_18001E633
0x18001e608  jbe     short loc_18001E637
0x18001e60a  mov     rax, [rbx+10h]
0x18001e60e  sub     rax, rdx
0x18001e611  sar     rax, 4
0x18001e615  mov     rdx, rdi
0x18001e618  cmp     rdi, rax
0x18001e61b  jbe     short loc_18001E627
0x18001e61d  mov     rcx, rbx
0x18001e620  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001e625  jmp     short loc_18001E637
0x18001e627  sub     rdx, rcx
0x18001e62a  mov     rcx, [rbx+8]
0x18001e62e  call    ??$_Uninitialized_value_construct_n@V?$allocator@U_GUID@@@std@@@std@@YAPEAU_GUID@@PEAU1@_KAEAV?$allocator@U_GUID@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<_GUID>>(_GUID *,unsigned __int64,std::allocator<_GUID> &)
0x18001e633  mov     [rbx+8], rax
0x18001e637  lea     rdx, [r15+4]
0x18001e63b  add     rdx, r14
0x18001e63e  sub     rsi, r14
0x18001e641  xor     r8d, r8d
0x18001e644  test    rdi, rdi
0x18001e647  jz      short loc_18001E665
0x18001e649  mov     rcx, r8
0x18001e64c  add     rcx, rcx
0x18001e64f  mov     rax, [rbx]
0x18001e652  movups  xmm0, xmmword ptr [r15+rcx*8+4]
0x18001e658  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x18001e65d  inc     r8
0x18001e660  cmp     r8, rdi
0x18001e663  jb      short loc_18001E649
0x18001e665  shr     rsi, 1
0x18001e668  lea     rcx, [rbx+18h]
0x18001e66c  mov     r8d, esi
0x18001e66f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e674  nop
0x18001e675  xor     eax, eax
0x18001e677  jmp     short loc_18001E684
0x18001e679  mov     eax, 8007000Eh
0x18001e67e  jmp     short loc_18001E684
0x18001e680  mov     eax, [rsp+48h+arg_8]
0x18001e684  mov     rbx, [rsp+48h+arg_0]
0x18001e689  mov     rsi, [rsp+48h+arg_10]
0x18001e68e  add     rsp, 30h
0x18001e692  pop     r15
0x18001e694  pop     r14
0x18001e696  pop     rdi
0x18001e697  retn
```
