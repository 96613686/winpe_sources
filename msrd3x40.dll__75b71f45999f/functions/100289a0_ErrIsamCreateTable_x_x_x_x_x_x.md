# ErrIsamCreateTable(x,x,x,x,x,x)

- ea: `0x100289a0`
- end: `0x10028af5`
- name: `_ErrIsamCreateTable@24`
- size: `341`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x100260d0`
- `0x10026140`
- `0x100270d0`
- `0x100289a0`
- `0x10035f50`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamCreateTable(void *a1, Instance *a2, unsigned __int16 *Src, int a4, int a5, void **a6)
{
  int v6; // esi
  struct Cursor *Table; // edi
  int v8; // eax
  int v9; // ecx
  unsigned int v11; // [esp-10h] [ebp-30h]
  unsigned int v12; // [esp-Ch] [ebp-2Ch]
  const unsigned __int16 *v13; // [esp+0h] [ebp-20h]
  void *v14[3]; // [esp+4h] [ebp-1Ch] BYREF
  void *Block; // [esp+10h] [ebp-10h]
  void *v16; // [esp+14h] [ebp-Ch]
  int v17; // [esp+18h] [ebp-8h]
  void *v18; // [esp+1Ch] [ebp-4h] BYREF

  ValidateName(v13, (struct Err *)1);
  if ( ((int)v14[0] & 8) != 0 )
  {
    if ( ((int)v14[0] & 1) != 0 )
    {
      v6 = 0;
      goto LABEL_16;
    }
    goto LABEL_4;
  }
  if ( WCSICMP(Src, wszMSysAccounts) && WCSICMP(Src, wszMSysGroups) )
  {
    Table = Instance::CreateTable(a2, Src, v11, v12, v14);
    if ( ((int)v14[0] & 8) == 0 )
    {
      v8 = (*(int (__thiscall **)(_DWORD, void *, void **, struct Cursor *, char *))(pJetInfoBlock + 36))(
             *(_DWORD *)(pJetInfoBlock + 36),
             a1,
             &v18,
             Table,
             &vtfndefIsam);
      v17 = v8;
      if ( v8 >= 0 )
      {
        (*(void (__thiscall **)(struct Cursor *, void *))(*(_DWORD *)Table + 88))(Table, v18);
        *a6 = v18;
      }
      else
      {
        if ( Table )
        {
          (**(void (__thiscall ***)(struct Cursor *, int))Table)(Table, 1);
          v8 = v17;
        }
        Err::SetError(v14, v8, v9);
      }
    }
    if ( ((int)v14[0] & 1) == 0 )
    {
LABEL_4:
      v6 = RealJetError(a1);
      goto LABEL_16;
    }
    v6 = 0;
  }
  else
  {
    (*(void (__thiscall **)(_DWORD, void *, unsigned __int16 *, _DWORD, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
      *(_DWORD *)(pJetInfoBlock + 44),
      a1,
      Src,
      0,
      0,
      -8198,
      0,
      0,
      0);
    v6 = -1002;
  }
LABEL_16:
  if ( ((int)v14[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v16 )
      operator delete[](v16);
  }
  return v6;
}

```

## disassembly

```asm
0x100289a0  mov     edi, edi
0x100289a2  push    ebp
0x100289a3  mov     ebp, esp
0x100289a5  sub     esp, 1Ch
0x100289a8  push    esi; unsigned __int16 *
0x100289a9  mov     esi, [ebp+Src]
0x100289ac  lea     edx, [ebp+var_1C]
0x100289af  mov     ecx, esi
0x100289b1  mov     [ebp+var_1C], 1
0x100289b8  call    ?ValidateName@@YGXPBGAAVErr@@@Z; ValidateName(ushort const *,Err &)
0x100289bd  mov     eax, [ebp+var_1C]
0x100289c0  test    al, 8
0x100289c2  jz      short loc_100289E1
0x100289c4  test    al, 1
0x100289c6  jz      short loc_100289CF
0x100289c8  xor     esi, esi
0x100289ca  jmp     loc_10028AC3
0x100289cf  mov     ecx, [ebp+arg_0]; void *
0x100289d2  lea     edx, [ebp+var_1C]
0x100289d5  call    RealJetError
0x100289da  mov     esi, eax
0x100289dc  jmp     loc_10028AC3
0x100289e1  mov     edx, offset _wszMSysAccounts; "MSysAccounts"
0x100289e6  mov     ecx, esi
0x100289e8  call    _WCSICMP@8; WCSICMP(x,x)
0x100289ed  test    eax, eax
0x100289ef  jz      loc_10028A99
0x100289f5  mov     edx, offset _wszMSysGroups; "MSysGroups"
0x100289fa  mov     ecx, esi
0x100289fc  call    _WCSICMP@8; WCSICMP(x,x)
0x10028a01  test    eax, eax
0x10028a03  jz      loc_10028A99
0x10028a09  mov     ecx, [ebp+arg_4]; this
0x10028a0c  lea     eax, [ebp+var_1C]
0x10028a0f  push    edi; unsigned int
0x10028a10  push    eax; struct Err *
0x10028a11  sub     esp, 8
0x10028a14  push    esi; Src
0x10028a15  call    ?CreateTable@Instance@@QAEPAVCursor@@PBGKKAAVErr@@@Z; Instance::CreateTable(ushort const *,ulong,ulong,Err &)
0x10028a1a  test    byte ptr [ebp+var_1C], 8
0x10028a1e  mov     edi, eax
0x10028a20  jnz     short loc_10028A8A
0x10028a22  mov     ecx, _pJetInfoBlock
0x10028a28  lea     eax, [ebp+var_4]
0x10028a2b  push    offset _vtfndefIsam
0x10028a30  push    edi
0x10028a31  push    eax; unsigned int
0x10028a32  mov     esi, [ecx+24h]
0x10028a35  mov     ecx, esi
0x10028a37  push    [ebp+arg_0]; void *
0x10028a3a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028a40  call    esi
0x10028a42  mov     [ebp+var_8], eax
0x10028a45  test    eax, eax
0x10028a47  jns     short loc_10028A6E
0x10028a49  test    edi, edi
0x10028a4b  jz      short loc_10028A62
0x10028a4d  mov     ecx, [edi]
0x10028a4f  push    1; void *
0x10028a51  mov     esi, [ecx]
0x10028a53  mov     ecx, esi
0x10028a55  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028a5b  mov     ecx, edi
0x10028a5d  call    esi
0x10028a5f  mov     eax, [ebp+var_8]
0x10028a62  push    ecx
0x10028a63  push    eax
0x10028a64  lea     ecx, [ebp+var_1C]
0x10028a67  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10028a6c  jmp     short loc_10028A8A
0x10028a6e  mov     eax, [edi]
0x10028a70  push    [ebp+var_4]; void *
0x10028a73  mov     esi, [eax+58h]
0x10028a76  mov     ecx, esi
0x10028a78  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028a7e  mov     ecx, edi
0x10028a80  call    esi
0x10028a82  mov     ecx, [ebp+arg_14]
0x10028a85  mov     eax, [ebp+var_4]
0x10028a88  mov     [ecx], eax
0x10028a8a  test    byte ptr [ebp+var_1C], 1
0x10028a8e  pop     edi
0x10028a8f  jz      loc_100289CF
0x10028a95  xor     esi, esi
0x10028a97  jmp     short loc_10028AC3
0x10028a99  mov     eax, _pJetInfoBlock
0x10028a9e  push    0
0x10028aa0  push    0
0x10028aa2  push    0
0x10028aa4  push    0FFFFDFFAh
0x10028aa9  push    0
0x10028aab  push    0
0x10028aad  push    esi; unsigned int
0x10028aae  mov     esi, [eax+2Ch]
0x10028ab1  mov     ecx, esi
0x10028ab3  push    [ebp+arg_0]; void *
0x10028ab6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028abc  call    esi
0x10028abe  mov     esi, 0FFFFFC16h
0x10028ac3  test    [ebp+var_1C], 0FFFFFFFEh
0x10028aca  jz      short loc_10028AEC
0x10028acc  mov     eax, [ebp+Block]
0x10028acf  test    eax, eax
0x10028ad1  jz      short loc_10028ADC
0x10028ad3  push    eax; Block
0x10028ad4  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028ad9  add     esp, 4
0x10028adc  mov     eax, [ebp+var_C]
0x10028adf  test    eax, eax
0x10028ae1  jz      short loc_10028AEC
0x10028ae3  push    eax; Block
0x10028ae4  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028ae9  add     esp, 4
0x10028aec  mov     eax, esi
0x10028aee  pop     esi
0x10028aef  mov     esp, ebp
0x10028af1  pop     ebp
0x10028af2  retn    18h
```
