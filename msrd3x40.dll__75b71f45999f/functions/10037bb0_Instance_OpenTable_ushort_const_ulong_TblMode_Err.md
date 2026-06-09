# Instance::OpenTable(ushort const *,ulong,TblMode,Err &)

- ea: `0x10037bb0`
- end: `0x10037c96`
- name: `?OpenTable@Instance@@AAEPAVTable@@PBGKW4TblMode@@AAVErr@@@Z`
- size: `230`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10036160`
- `0x100364e0`
- `0x10036620`

## callees

- `0x1001df90`
- `0x10025ee0`
- `0x10037bb0`
- `0x100518a0`
- `0x10051e80`
- `0x10053400`
- `0x10053f40`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`

## pseudocode

```c
Table *__thiscall Instance::OpenTable(
        struct Session **this,
        unsigned __int16 *Src,
        unsigned int a3,
        int a4,
        struct Err *a5)
{
  Table *v6; // eax
  struct Err *v7; // ecx
  Table *v8; // esi
  unsigned int v10; // ecx
  Table *Block; // [esp+10h] [ebp-10h]

  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    Block = (Table *)operator new(0x778u);
    v6 = Table::Table(Block, this[4], a5);
    v8 = v6;
    if ( !v6 )
    {
      Err::SetError(a5, -1011, v7);
      return v8;
    }
    if ( (*(_BYTE *)a5 & 8) != 0 )
    {
      Table::~Table(v6);
      operator delete(v8);
    }
    else
    {
      Table::SetName(v6, Src, v7);
      if ( (*(_BYTE *)a5 & 8) == 0 )
      {
        Table::Open((int)v8, this, a3, a4, a5);
        if ( (*(_BYTE *)a5 & 8) == 0 )
          return v8;
      }
      Table::`scalar deleting destructor'(v8, v10);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10037bb0  mov     edi, edi
0x10037bb2  push    ebp
0x10037bb3  mov     ebp, esp
0x10037bb5  push    0FFFFFFFFh
0x10037bb7  push    offset ?OpenTable@Instance@@AAEPAVTable@@PBGKW4TblMode@@AAVErr@@@Z_SEH
0x10037bbc  mov     eax, large fs:0
0x10037bc2  push    eax
0x10037bc3  push    ecx
0x10037bc4  push    ebx
0x10037bc5  push    esi
0x10037bc6  push    edi
0x10037bc7  mov     eax, ___security_cookie
0x10037bcc  xor     eax, ebp
0x10037bce  push    eax
0x10037bcf  lea     eax, [ebp+var_C]
0x10037bd2  mov     large fs:0, eax
0x10037bd8  mov     ebx, ecx
0x10037bda  mov     edi, [ebp+arg_C]
0x10037bdd  test    byte ptr [edi], 8
0x10037be0  jnz     loc_10037C80
0x10037be6  push    778h; Size
0x10037beb  call    ??2@YAPAXI@Z; operator new(uint)
0x10037bf0  add     esp, 4
0x10037bf3  mov     [ebp+Block], eax
0x10037bf6  push    edi; struct Err *
0x10037bf7  mov     [ebp+var_4], 0
0x10037bfe  mov     ecx, eax; this
0x10037c00  push    dword ptr [ebx+10h]; struct Database *
0x10037c03  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x10037c08  mov     esi, eax
0x10037c0a  mov     [ebp+var_4], 0FFFFFFFFh
0x10037c11  test    esi, esi
0x10037c13  jnz     short loc_10037C38
0x10037c15  push    ecx
0x10037c16  push    0FFFFFC0Dh
0x10037c1b  mov     ecx, edi
0x10037c1d  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10037c22  mov     eax, esi
0x10037c24  mov     ecx, [ebp+var_C]
0x10037c27  mov     large fs:0, ecx
0x10037c2e  pop     ecx
0x10037c2f  pop     edi
0x10037c30  pop     esi
0x10037c31  pop     ebx
0x10037c32  mov     esp, ebp
0x10037c34  pop     ebp
0x10037c35  retn    10h
0x10037c38  test    byte ptr [edi], 8
0x10037c3b  jz      short loc_10037C54
0x10037c3d  mov     ecx, esi; this
0x10037c3f  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x10037c44  push    778h; unsigned int
0x10037c49  push    esi; Block
0x10037c4a  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10037c4f  add     esp, 8
0x10037c52  jmp     short loc_10037C80
0x10037c54  push    ecx; struct Err *
0x10037c55  push    [ebp+Src]; Src
0x10037c58  mov     ecx, esi; this
0x10037c5a  call    ?SetName@Table@@QAEXPBGAAVErr@@@Z; Table::SetName(ushort const *,Err &)
0x10037c5f  test    byte ptr [edi], 8
0x10037c62  jnz     short loc_10037C78
0x10037c64  push    edi
0x10037c65  push    [ebp+arg_8]
0x10037c68  mov     ecx, esi
0x10037c6a  push    [ebp+arg_4]
0x10037c6d  push    ebx
0x10037c6e  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x10037c73  test    byte ptr [edi], 8
0x10037c76  jz      short loc_10037C22
0x10037c78  push    ecx; unsigned int
0x10037c79  mov     ecx, esi; this
0x10037c7b  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x10037c80  xor     eax, eax
0x10037c82  mov     ecx, [ebp+var_C]
0x10037c85  mov     large fs:0, ecx
0x10037c8c  pop     ecx
0x10037c8d  pop     edi
0x10037c8e  pop     esi
0x10037c8f  pop     ebx
0x10037c90  mov     esp, ebp
0x10037c92  pop     ebp
0x10037c93  retn    10h
0x10060d70  push    778h; unsigned int
0x10060d75  mov     eax, [ebp+Block]
0x10060d78  push    eax; Block
0x10060d79  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060d7e  add     esp, 8
0x10060d81  retn
0x10060d87  nop
0x10060d88  nop
0x10060d89  mov     edx, [esp-4+arg_4]
0x10060d8d  lea     eax, [edx+0Ch]
0x10060d90  mov     ecx, [edx-14h]
0x10060d93  xor     ecx, eax; StackCookie
0x10060d95  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060d9a  mov     eax, offset stru_100639E0
0x10060d9f  jmp     ___CxxFrameHandler3
```
