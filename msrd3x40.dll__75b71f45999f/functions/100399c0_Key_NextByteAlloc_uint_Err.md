# Key::NextByteAlloc(uint,Err &)

- ea: `0x100399c0`
- end: `0x10039afc`
- name: `?NextByteAlloc@Key@@AAEPAEIAAVErr@@@Z`
- size: `316`
- prototype: `unsigned __int8 *__thiscall(Key *__hidden this, unsigned int, struct Err *)`
- caller_count: `50`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x10011540`
- `0x10012190`
- `0x100142b0`
- `0x10014360`
- `0x100146f0`
- `0x100147e0`
- `0x10014a20`
- `0x10014ac0`
- `0x10014eb0`
- `0x100152d0`
- `0x10015590`
- `0x100158c0`
- `0x10015c30`
- `0x10016280`
- `0x10016630`
- `0x10016970`
- `0x10016a70`
- `0x10016bf0`
- `0x10016ca0`
- `0x10016f60`
- `0x10017010`
- `0x100171c0`
- `0x10017270`
- `0x100172e0`
- `0x10017390`
- `0x10017510`
- `0x100175c0`
- `0x10017890`
- `0x10017940`
- `0x10017e10`
- `0x10017ed0`
- `0x10018050`
- `0x10018100`
- `0x1001b010`
- `0x1001d350`
- `0x1002fa00`
- `0x10030270`
- `0x100322f0`
- `0x10038700`
- `0x10038750`
- `0x10038860`
- `0x100389b0`
- `0x10038b10`
- `0x10038c90`
- `0x10038e70`
- `0x10039180`
- `0x100394f0`
- `0x1004c6f0`
- `0x1004d040`
- `0x10058210`

## callees

- `0x10025ee0`
- `0x100399c0`
- `0x1005dedf`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f07c`

## pseudocode

```c
unsigned __int8 *__thiscall Key::NextByteAlloc(Key *this, unsigned int a2, void **a3)
{
  int v4; // ecx
  unsigned __int8 *result; // eax
  unsigned int v6; // ebx
  int v7; // eax
  void **v8; // edi
  void *v9; // eax
  bool v10; // zf
  void *v11; // eax
  size_t v12; // [esp-8h] [ebp-14h]
  unsigned int v13; // [esp+8h] [ebp-4h] BYREF

  v13 = 0;
  if ( FSafeSumUInt(&v13) )
  {
    v6 = v13;
    if ( v13 <= *((_DWORD *)this + 3) )
      return (unsigned __int8 *)(*(_DWORD *)this + *((_DWORD *)this + 1));
    v7 = *((_DWORD *)this + 2);
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        v9 = operator new[](v13);
        v8 = a3;
        v13 = (unsigned int)v9;
        v10 = (*(_BYTE *)a3 & 8) == 0;
        if ( (*(_BYTE *)a3 & 8) != 0 )
          goto LABEL_21;
        memcpy(v9, *((const void **)this + 1), *(_DWORD *)this);
        if ( *((_DWORD *)this + 1) )
          operator delete[](*((void **)this + 1));
        *((_DWORD *)this + 1) = v13;
        *((_DWORD *)this + 3) = v6;
      }
      else
      {
        v8 = a3;
        Err::SetError(a3, -1038, v4);
      }
    }
    else
    {
      v11 = operator new[](v13);
      v8 = a3;
      *((_DWORD *)this + 1) = v11;
      if ( (*(_BYTE *)a3 & 8) != 0 )
      {
        *((_DWORD *)this + 1) = (char *)this + 16;
      }
      else
      {
        v12 = *(_DWORD *)this;
        *((_DWORD *)this + 2) = 1;
        memcpy(v11, (char *)this + 16, v12);
        *((_DWORD *)this + 3) = v6;
      }
    }
    v10 = (*(_BYTE *)v8 & 8) == 0;
LABEL_21:
    if ( !v10 )
      return 0;
    return (unsigned __int8 *)(*(_DWORD *)this + *((_DWORD *)this + 1));
  }
  if ( (int)*a3 >= 8 )
    return 0;
  if ( ((unsigned int)*a3 & 0xFFFFFFFE) != 0 )
  {
    if ( a3[3] )
      operator delete[](a3[3]);
    if ( a3[4] )
      operator delete[](a3[4]);
  }
  *a3 = (void *)8;
  result = 0;
  a3[1] = (void *)-1003;
  a3[2] = 0;
  a3[3] = 0;
  a3[4] = 0;
  return result;
}

```

## disassembly

```asm
0x100399c0  mov     edi, edi
0x100399c2  push    ebp
0x100399c3  mov     ebp, esp
0x100399c5  push    ecx
0x100399c6  mov     edx, [ebp+arg_0]
0x100399c9  lea     eax, [ebp+var_4]
0x100399cc  push    ebx
0x100399cd  push    esi
0x100399ce  mov     esi, ecx
0x100399d0  mov     [ebp+var_4], 0
0x100399d7  push    eax
0x100399d8  mov     ecx, [esi]
0x100399da  call    _FSafeSumUInt@12; FSafeSumUInt(x,x,x)
0x100399df  test    eax, eax
0x100399e1  jnz     short loc_10039A44
0x100399e3  mov     esi, [ebp+arg_4]
0x100399e6  mov     eax, [esi]
0x100399e8  cmp     eax, 8
0x100399eb  jge     loc_10039AE5
0x100399f1  test    eax, 0FFFFFFFEh
0x100399f6  jz      short loc_10039A18
0x100399f8  mov     eax, [esi+0Ch]
0x100399fb  test    eax, eax
0x100399fd  jz      short loc_10039A08
0x100399ff  push    eax; Block
0x10039a00  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10039a05  add     esp, 4
0x10039a08  mov     eax, [esi+10h]
0x10039a0b  test    eax, eax
0x10039a0d  jz      short loc_10039A18
0x10039a0f  push    eax; Block
0x10039a10  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10039a15  add     esp, 4
0x10039a18  mov     dword ptr [esi], 8
0x10039a1e  xor     eax, eax
0x10039a20  mov     dword ptr [esi+4], 0FFFFFC15h
0x10039a27  mov     dword ptr [esi+8], 0
0x10039a2e  mov     dword ptr [esi+0Ch], 0
0x10039a35  mov     dword ptr [esi+10h], 0
0x10039a3c  pop     esi
0x10039a3d  pop     ebx
0x10039a3e  mov     esp, ebp
0x10039a40  pop     ebp
0x10039a41  retn    8
0x10039a44  mov     ebx, [ebp+var_4]
0x10039a47  cmp     ebx, [esi+0Ch]
0x10039a4a  jbe     loc_10039AEF
0x10039a50  mov     eax, [esi+8]
0x10039a53  push    edi
0x10039a54  sub     eax, 0
0x10039a57  jz      short loc_10039AAD
0x10039a59  sub     eax, 1
0x10039a5c  jz      short loc_10039A70
0x10039a5e  mov     edi, [ebp+arg_4]
0x10039a61  push    ecx
0x10039a62  push    0FFFFFBF2h
0x10039a67  mov     ecx, edi
0x10039a69  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10039a6e  jmp     short loc_10039ADF
0x10039a70  push    ebx; unsigned int
0x10039a71  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10039a76  mov     edi, [ebp+arg_4]
0x10039a79  add     esp, 4
0x10039a7c  mov     [ebp+var_4], eax
0x10039a7f  test    byte ptr [edi], 8
0x10039a82  jnz     short loc_10039AE2
0x10039a84  push    dword ptr [esi]; Size
0x10039a86  push    dword ptr [esi+4]; Src
0x10039a89  push    eax; void *
0x10039a8a  call    _memcpy
0x10039a8f  mov     eax, [esi+4]
0x10039a92  add     esp, 0Ch
0x10039a95  test    eax, eax
0x10039a97  jz      short loc_10039AA2
0x10039a99  push    eax; Block
0x10039a9a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10039a9f  add     esp, 4
0x10039aa2  mov     eax, [ebp+var_4]
0x10039aa5  mov     [esi+4], eax
0x10039aa8  mov     [esi+0Ch], ebx
0x10039aab  jmp     short loc_10039ADF
0x10039aad  push    ebx; unsigned int
0x10039aae  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10039ab3  mov     edi, [ebp+arg_4]
0x10039ab6  lea     ecx, [esi+10h]
0x10039ab9  add     esp, 4
0x10039abc  mov     [esi+4], eax
0x10039abf  test    byte ptr [edi], 8
0x10039ac2  jnz     short loc_10039ADC
0x10039ac4  push    dword ptr [esi]; Size
0x10039ac6  mov     dword ptr [esi+8], 1
0x10039acd  push    ecx; Src
0x10039ace  push    eax; void *
0x10039acf  call    _memcpy
0x10039ad4  add     esp, 0Ch
0x10039ad7  mov     [esi+0Ch], ebx
0x10039ada  jmp     short loc_10039ADF
0x10039adc  mov     [esi+4], ecx
0x10039adf  test    byte ptr [edi], 8
0x10039ae2  pop     edi
0x10039ae3  jz      short loc_10039AEF
0x10039ae5  pop     esi
0x10039ae6  xor     eax, eax
0x10039ae8  pop     ebx
0x10039ae9  mov     esp, ebp
0x10039aeb  pop     ebp
0x10039aec  retn    8
0x10039aef  mov     eax, [esi+4]
0x10039af2  add     eax, [esi]
0x10039af4  pop     esi
0x10039af5  pop     ebx
0x10039af6  mov     esp, ebp
0x10039af8  pop     ebp
0x10039af9  retn    8
```
