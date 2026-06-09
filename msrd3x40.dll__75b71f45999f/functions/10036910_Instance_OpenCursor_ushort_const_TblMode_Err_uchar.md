# Instance::OpenCursor(ushort const *,TblMode,Err &,uchar)

- ea: `0x10036910`
- end: `0x10036a69`
- name: `?OpenCursor@Instance@@QAEPAVCursor@@PBGW4TblMode@@AAVErr@@E@Z`
- size: `345`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1002a350`
- `0x1002ac50`
- `0x1002b230`
- `0x1002bcf0`
- `0x10056280`

## callees

- `0x1000eb60`
- `0x10019240`
- `0x10025ee0`
- `0x10036620`
- `0x10036910`
- `0x10051e80`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`

## pseudocode

```c
void (__thiscall ***__thiscall Instance::OpenCursor(
        struct Instance *this,
        unsigned __int16 *a2,
        unsigned int a3,
        void **a4,
        unsigned __int8 a5))(_DWORD, int)
{
  int v5; // esi
  void (__thiscall ***v6)(_DWORD, int); // edi
  Table *v7; // ebx
  void (__thiscall ***v8)(_DWORD, int); // eax
  int v9; // ecx
  _BYTE *v10; // esi
  char v11; // cl
  void *Block; // [esp+10h] [ebp-18h]
  void *Blocka; // [esp+10h] [ebp-18h]
  char v16; // [esp+1Bh] [ebp-Dh] BYREF
  int v17; // [esp+24h] [ebp-4h]

  v5 = a3;
  v16 = 0;
  v6 = 0;
  v7 = Instance::OpenTable(this, a2, a3, &v16, a4);
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_12;
  if ( a3 != 6 )
  {
    if ( a3 != 7 )
    {
      if ( a3 == 5 )
        goto LABEL_18;
      if ( *((_BYTE *)v7 + 8) != 83 )
        goto LABEL_9;
    }
    v5 = 0;
    goto LABEL_9;
  }
  if ( *((_BYTE *)v7 + 8) != 83 )
  {
    v5 = 2;
LABEL_9:
    Block = operator new(0x16Cu);
    v17 = 1;
    v8 = (void (__thiscall ***)(_DWORD, int))Cursor::Cursor(Block, this, v7, v5, 0, a4, a5);
    v10 = a4;
    goto LABEL_10;
  }
LABEL_18:
  Blocka = operator new(0x16Cu);
  v10 = a4;
  v17 = 0;
  v8 = (void (__thiscall ***)(_DWORD, int))Cursor::Cursor(Blocka, this, v7, *((_DWORD *)v7 + 11), 1, a4, a5);
LABEL_10:
  v6 = v8;
  if ( v8 )
  {
    if ( (*v10 & 8) != 0 )
    {
      (**v8)(v8, 1);
      v11 = 0;
      v6 = 0;
      goto LABEL_13;
    }
  }
  else
  {
    Err::SetError(v10, -1011, v9);
  }
LABEL_12:
  v11 = v16;
LABEL_13:
  if ( (*(_BYTE *)a4 & 8) != 0 && v11 == 1 && v7 )
  {
    Table::~Table(v7);
    operator delete(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x10036910  mov     edi, edi
0x10036912  push    ebp
0x10036913  mov     ebp, esp
0x10036915  push    0FFFFFFFFh
0x10036917  push    offset ?OpenCursor@Instance@@QAEPAVCursor@@PBGW4TblMode@@AAVErr@@E@Z_SEH
0x1003691c  mov     eax, large fs:0
0x10036922  push    eax
0x10036923  sub     esp, 0Ch
0x10036926  push    ebx
0x10036927  push    esi
0x10036928  push    edi
0x10036929  mov     eax, ___security_cookie
0x1003692e  xor     eax, ebp
0x10036930  push    eax; unsigned int
0x10036931  lea     eax, [ebp+var_C]
0x10036934  mov     large fs:0, eax
0x1003693a  mov     eax, ecx
0x1003693c  mov     [ebp+var_14], eax
0x1003693f  push    [ebp+arg_8]
0x10036942  mov     esi, [ebp+arg_4]
0x10036945  lea     ecx, [ebp+var_D]
0x10036948  push    ecx
0x10036949  push    esi
0x1003694a  push    [ebp+arg_0]
0x1003694d  mov     ecx, eax
0x1003694f  mov     [ebp+var_D], 0
0x10036953  xor     edi, edi
0x10036955  call    ?OpenTable@Instance@@QAEPAVTable@@PBGW4TblMode@@AAEAAVErr@@@Z; Instance::OpenTable(ushort const *,TblMode,uchar &,Err &)
0x1003695a  mov     ebx, eax
0x1003695c  mov     eax, [ebp+arg_8]
0x1003695f  test    byte ptr [eax], 8
0x10036962  jnz     short loc_100369D5
0x10036964  cmp     esi, 6
0x10036967  jnz     short loc_10036978
0x10036969  cmp     byte ptr [ebx+8], 53h ; 'S'
0x1003696d  jz      loc_10036A14
0x10036973  lea     esi, [edi+2]
0x10036976  jmp     short loc_1003698E
0x10036978  cmp     esi, 7
0x1003697b  jz      short loc_1003698C
0x1003697d  cmp     esi, 5
0x10036980  jz      loc_10036A14
0x10036986  cmp     byte ptr [ebx+8], 53h ; 'S'
0x1003698a  jnz     short loc_1003698E
0x1003698c  xor     esi, esi
0x1003698e  push    16Ch; Size
0x10036993  call    ??2@YAPAXI@Z; operator new(uint)
0x10036998  add     esp, 4
0x1003699b  mov     [ebp+Block], eax
0x1003699e  movzx   ecx, [ebp+arg_C]
0x100369a2  push    ecx
0x100369a3  push    [ebp+arg_8]
0x100369a6  mov     ecx, eax
0x100369a8  mov     [ebp+var_4], 1
0x100369af  push    0
0x100369b1  push    esi
0x100369b2  push    ebx
0x100369b3  push    [ebp+var_14]
0x100369b6  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint)
0x100369bb  mov     esi, [ebp+arg_8]
0x100369be  mov     edi, eax
0x100369c0  test    edi, edi
0x100369c2  jnz     loc_10036A49
0x100369c8  push    ecx
0x100369c9  push    0FFFFFC0Dh
0x100369ce  mov     ecx, esi
0x100369d0  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100369d5  mov     cl, [ebp+var_D]
0x100369d8  mov     eax, [ebp+arg_8]
0x100369db  test    byte ptr [eax], 8
0x100369de  jz      short loc_100369FE
0x100369e0  cmp     cl, 1
0x100369e3  jnz     short loc_100369FE
0x100369e5  test    ebx, ebx
0x100369e7  jz      short loc_100369FE
0x100369e9  mov     ecx, ebx; this
0x100369eb  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x100369f0  push    778h; unsigned int
0x100369f5  push    ebx; Block
0x100369f6  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100369fb  add     esp, 8
0x100369fe  mov     eax, edi
0x10036a00  mov     ecx, [ebp+var_C]
0x10036a03  mov     large fs:0, ecx
0x10036a0a  pop     ecx
0x10036a0b  pop     edi
0x10036a0c  pop     esi
0x10036a0d  pop     ebx
0x10036a0e  mov     esp, ebp
0x10036a10  pop     ebp
0x10036a11  retn    10h
0x10036a14  push    16Ch; Size
0x10036a19  call    ??2@YAPAXI@Z; operator new(uint)
0x10036a1e  mov     ecx, eax
0x10036a20  add     esp, 4
0x10036a23  mov     [ebp+Block], ecx
0x10036a26  movzx   eax, [ebp+arg_C]
0x10036a2a  mov     esi, [ebp+arg_8]
0x10036a2d  push    eax
0x10036a2e  push    esi
0x10036a2f  push    1
0x10036a31  mov     [ebp+var_4], 0
0x10036a38  push    dword ptr [ebx+2Ch]
0x10036a3b  push    ebx
0x10036a3c  push    [ebp+var_14]
0x10036a3f  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint)
0x10036a44  jmp     loc_100369BE
0x10036a49  test    byte ptr [esi], 8
0x10036a4c  jz      short loc_100369D5
0x10036a4e  mov     eax, [edi]
0x10036a50  push    1; void *
0x10036a52  mov     esi, [eax]
0x10036a54  mov     ecx, esi
0x10036a56  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036a5c  mov     ecx, edi
0x10036a5e  call    esi
0x10036a60  xor     cl, cl
0x10036a62  xor     edi, edi
0x10036a64  jmp     loc_100369D8
0x10060c50  push    16Ch; unsigned int
0x10060c55  mov     eax, [ebp+Block]
0x10060c58  push    eax; Block
0x10060c59  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060c5e  add     esp, 8
0x10060c61  retn
0x10060c62  push    16Ch; unsigned int
0x10060c67  mov     eax, [ebp+Block]
0x10060c6a  push    eax; Block
0x10060c6b  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060c70  add     esp, 8
0x10060c73  retn
0x10060c79  nop
0x10060c7a  nop
0x10060c7b  mov     edx, [esp-4+arg_4]
0x10060c7f  lea     eax, [edx+0Ch]
0x10060c82  mov     ecx, [edx-1Ch]
0x10060c85  xor     ecx, eax; StackCookie
0x10060c87  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060c8c  mov     eax, offset stru_10063918
0x10060c91  jmp     ___CxxFrameHandler3
```
