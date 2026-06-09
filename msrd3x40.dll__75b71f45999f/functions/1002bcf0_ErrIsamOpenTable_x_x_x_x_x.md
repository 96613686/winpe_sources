# ErrIsamOpenTable(x,x,x,x,x)

- ea: `0x1002bcf0`
- end: `0x1002bdf2`
- name: `_ErrIsamOpenTable@20`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10026140`
- `0x1002bcf0`
- `0x10036910`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamOpenTable(void *a1, struct Instance *a2, int *a3, unsigned __int16 *a4, int a5)
{
  unsigned int v5; // ecx
  void (__thiscall ***v6)(_DWORD, int); // eax
  int v7; // ecx
  void (__thiscall ***v8)(_DWORD, int); // ebx
  int v9; // edi
  int v11; // [esp+0h] [ebp-14h] BYREF
  void *Block; // [esp+Ch] [ebp-8h]
  void *v13; // [esp+10h] [ebp-4h]

  v11 = 1;
  if ( (a5 & 2) != 0 )
  {
    v5 = ((a5 >> 31) & 4) + 2;
  }
  else if ( (a5 & 4) != 0 )
  {
    v5 = 4 * (a5 & 1);
  }
  else if ( (a5 & 1) != 0 )
  {
    v5 = 3;
  }
  else
  {
    v5 = 4 * (a5 < 0) + 1;
  }
  v6 = Instance::OpenCursor(a2, a4, v5, (void **)&v11, (a5 & 8) != 0);
  v7 = v11;
  v8 = v6;
  if ( (v11 & 8) != 0 )
  {
    if ( (v11 & 1) != 0 )
    {
      v9 = 0;
      goto LABEL_17;
    }
    v9 = RealJetError(a1);
  }
  else
  {
    v9 = (*(int (__thiscall **)(_DWORD, void *, int *, void (__thiscall ***)(_DWORD, int), char *))(pJetInfoBlock + 36))(
           *(_DWORD *)(pJetInfoBlock + 36),
           a1,
           a3,
           v6,
           &vtfndefIsam);
    if ( v9 >= 0 )
    {
      (*v8)[22](v8, *a3);
    }
    else if ( v8 )
    {
      (**v8)(v8, 1);
    }
  }
  v7 = v11;
LABEL_17:
  if ( (v7 & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v13 )
      operator delete[](v13);
  }
  return v9;
}

```

## disassembly

```asm
0x1002bcf0  mov     edi, edi
0x1002bcf2  push    ebp
0x1002bcf3  mov     ebp, esp
0x1002bcf5  sub     esp, 14h
0x1002bcf8  mov     eax, [ebp+arg_10]
0x1002bcfb  mov     ecx, eax
0x1002bcfd  mov     [ebp+var_14], 1
0x1002bd04  test    al, 2
0x1002bd06  jz      short loc_1002BD13
0x1002bd08  sar     ecx, 1Fh
0x1002bd0b  and     ecx, 4
0x1002bd0e  add     ecx, 2
0x1002bd11  jmp     short loc_1002BD38
0x1002bd13  and     ecx, 1
0x1002bd16  test    al, 4
0x1002bd18  jz      short loc_1002BD1F
0x1002bd1a  shl     ecx, 2
0x1002bd1d  jmp     short loc_1002BD38
0x1002bd1f  test    ecx, ecx
0x1002bd21  jz      short loc_1002BD2A
0x1002bd23  mov     ecx, 3
0x1002bd28  jmp     short loc_1002BD38
0x1002bd2a  xor     ecx, ecx
0x1002bd2c  test    eax, eax
0x1002bd2e  sets    cl
0x1002bd31  lea     ecx, ds:1[ecx*4]
0x1002bd38  push    ebx
0x1002bd39  shr     eax, 3
0x1002bd3c  push    edi
0x1002bd3d  and     al, 1
0x1002bd3f  movzx   eax, al
0x1002bd42  push    eax
0x1002bd43  lea     eax, [ebp+var_14]
0x1002bd46  push    eax
0x1002bd47  push    ecx
0x1002bd48  push    [ebp+arg_C]
0x1002bd4b  mov     ecx, [ebp+arg_4]
0x1002bd4e  call    ?OpenCursor@Instance@@QAEPAVCursor@@PBGW4TblMode@@AAVErr@@E@Z; Instance::OpenCursor(ushort const *,TblMode,Err &,uchar)
0x1002bd53  mov     ecx, [ebp+var_14]
0x1002bd56  mov     ebx, eax
0x1002bd58  test    cl, 8
0x1002bd5b  jz      short loc_1002BD75
0x1002bd5d  test    cl, 1
0x1002bd60  jz      short loc_1002BD66
0x1002bd62  xor     edi, edi
0x1002bd64  jmp     short loc_1002BDC0
0x1002bd66  mov     ecx, [ebp+arg_0]; void *
0x1002bd69  lea     edx, [ebp+var_14]
0x1002bd6c  call    RealJetError
0x1002bd71  mov     edi, eax
0x1002bd73  jmp     short loc_1002BDBD
0x1002bd75  mov     eax, _pJetInfoBlock
0x1002bd7a  push    esi; unsigned int
0x1002bd7b  push    offset _vtfndefIsam
0x1002bd80  push    ebx
0x1002bd81  push    [ebp+arg_8]; unsigned int
0x1002bd84  mov     esi, [eax+24h]
0x1002bd87  mov     ecx, esi
0x1002bd89  push    [ebp+arg_0]; void *
0x1002bd8c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002bd92  call    esi
0x1002bd94  mov     edi, eax
0x1002bd96  test    edi, edi
0x1002bd98  jns     short loc_1002BDA6
0x1002bd9a  test    ebx, ebx
0x1002bd9c  jz      short loc_1002BDBC
0x1002bd9e  mov     eax, [ebx]
0x1002bda0  push    1
0x1002bda2  mov     esi, [eax]
0x1002bda4  jmp     short loc_1002BDB0
0x1002bda6  mov     eax, [ebx]
0x1002bda8  mov     ecx, [ebp+arg_8]
0x1002bdab  mov     esi, [eax+58h]
0x1002bdae  push    dword ptr [ecx]; void *
0x1002bdb0  mov     ecx, esi
0x1002bdb2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002bdb8  mov     ecx, ebx
0x1002bdba  call    esi
0x1002bdbc  pop     esi
0x1002bdbd  mov     ecx, [ebp+var_14]
0x1002bdc0  test    ecx, 0FFFFFFFEh
0x1002bdc6  jz      short loc_1002BDE8
0x1002bdc8  mov     eax, [ebp+Block]
0x1002bdcb  test    eax, eax
0x1002bdcd  jz      short loc_1002BDD8
0x1002bdcf  push    eax; Block
0x1002bdd0  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002bdd5  add     esp, 4
0x1002bdd8  mov     eax, [ebp+var_4]
0x1002bddb  test    eax, eax
0x1002bddd  jz      short loc_1002BDE8
0x1002bddf  push    eax; Block
0x1002bde0  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002bde5  add     esp, 4
0x1002bde8  mov     eax, edi
0x1002bdea  pop     edi
0x1002bdeb  pop     ebx
0x1002bdec  mov     esp, ebp
0x1002bdee  pop     ebp
0x1002bdef  retn    14h
```
