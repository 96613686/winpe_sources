# Database::OpenFile(ushort const *,ushort const *,ushort const *,DBOpenFreq,DBIntent,DBShare,Err &)

- ea: `0x10020080`
- end: `0x10020424`
- name: `?OpenFile@Database@@QAEXPBG00W4DBOpenFreq@@W4DBIntent@@W4DBShare@@AAVErr@@@Z`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x10044630`

## callees

- `0x10008180`
- `0x1000f750`
- `0x10010580`
- `0x10020080`
- `0x10020fa0`
- `0x10021d70`
- `0x10022030`
- `0x10022310`
- `0x100223b0`
- `0x10023360`
- `0x10025a60`
- `0x10025ee0`
- `0x10025f50`
- `0x10026020`
- `0x1002e140`
- `0x1002e5c0`
- `0x1005e3b0`
- `0x1005e7dc`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Database::OpenFile(
        int this,
        const WCHAR *a2,
        int a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        int a7,
        Err *a8)
{
  const WCHAR *v9; // edx
  int v10; // ebx
  int v11; // ebx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  const WCHAR *v16; // eax
  bool v17; // zf
  int v18; // ecx
  int v19; // eax
  _DWORD v20[2]; // [esp+14h] [ebp-11Ch] BYREF
  int v21; // [esp+1Ch] [ebp-114h] BYREF
  void *Block; // [esp+20h] [ebp-110h]
  void *v23; // [esp+24h] [ebp-10Ch]
  LPCWSTR lpFileName; // [esp+28h] [ebp-108h]
  int v25; // [esp+2Ch] [ebp-104h] BYREF
  CHAR MultiByteStr[32]; // [esp+30h] [ebp-100h] BYREF
  CHAR v27[32]; // [esp+50h] [ebp-E0h] BYREF
  WCHAR WideCharStr[34]; // [esp+70h] [ebp-C0h] BYREF
  WCHAR v29[34]; // [esp+B4h] [ebp-7Ch] BYREF
  _WORD v30[20]; // [esp+F8h] [ebp-38h] BYREF
  int v31; // [esp+12Ch] [ebp-4h]

  v9 = a2;
  lpFileName = a2;
  if ( a3 )
  {
    Database::ValidateConnectString(this, a3, v30, a4, 1, a8);
    v9 = lpFileName;
  }
  else
  {
    v30[0] = 0;
  }
  if ( (*(_BYTE *)a8 & 8) == 0 )
  {
    if ( a7 )
    {
      if ( a7 == 1 )
        *(_DWORD *)(this + 20) |= 4u;
    }
    else
    {
      *(_DWORD *)(this + 20) |= 2u;
    }
    v10 = a6;
    if ( !a6 || a6 == 3 )
      *(_DWORD *)(this + 20) |= 1u;
    File::Open((File *)(this + 4), v9, a8);
    if ( (*(_BYTE *)a8 & 8) == 0 )
      Database::AllocateHashTable((Database *)this, a8);
    if ( (*(_BYTE *)a8 & 1) != 0 || *((_DWORD *)a8 + 1) != -1024 )
    {
LABEL_42:
      if ( (*(_BYTE *)a8 & 8) != 0 )
        return;
      v21 = 0;
      Block = 0;
      v31 = 1;
      v16 = (const WCHAR *)Database::ValidateDatabaseFile(this, &v21, v30, v10, a8);
      v17 = (*(_BYTE *)a8 & 8) == 0;
      lpFileName = v16;
      if ( !v17 )
        goto LABEL_60;
      if ( a7 == 2 || a7 == 1 && v10 == 1 )
      {
        Database::OpenLockFile((Database *)this, a8);
        if ( (*(_DWORD *)a8 & 8) != 0 )
        {
          if ( (*(_DWORD *)a8 & 1) != 0 || *((_DWORD *)a8 + 1) != -1032 || v10 != 1 )
          {
            Err::Reset(a8);
            Err::SetError(a8, -1031, v18);
          }
        }
        else
        {
          Database::AssignUserNumber((Database *)this, (struct DBHeaderPage *)&v21, a4, a8);
        }
      }
      if ( (*(_BYTE *)a8 & 8) != 0 )
        goto LABEL_60;
      if ( v10 != 2 && v10 != 3 )
      {
        Database::CheckForCorruption((Database *)this, (struct DBHeaderPage *)&v21, a8);
        if ( (*(_BYTE *)a8 & 8) == 0 )
        {
LABEL_59:
          DBHeaderPage::SignatureDiffers(&v21, 256, this + 412);
LABEL_60:
          *(_DWORD *)(this + 100) = a7;
          *(_DWORD *)(this + 96) = a5;
          *(_DWORD *)(this + 68) = lpFileName;
          v19 = v21;
          *(_DWORD *)(this + 104) = v10;
          if ( v19 )
            --*(_WORD *)(v19 + 76);
          return;
        }
        *(_DWORD *)(this + 68) = 0;
      }
      if ( (*(_BYTE *)a8 & 8) != 0 )
        goto LABEL_60;
      goto LABEL_59;
    }
    v20[0] = 1;
    v31 = 0;
    Database::OpenLockFile((Database *)this, (struct Err *)v20);
    v11 = v20[0];
    if ( (v20[0] & 8) == 0 )
    {
      File::Read(*(File **)(this + 64), 0, MultiByteStr, 0x40u, (struct Err *)v20);
      v11 = v20[0];
      if ( (v20[0] & 8) == 0 )
      {
        v25 = 32;
        if ( ErrGenericMultiByteCbToNWide(0, 4u, MultiByteStr, 32, WideCharStr, (int)&v25) >= 0 )
        {
          if ( (unsigned int)(v25 - 1) > 0x1F )
          {
            WideCharStr[0] = 0;
          }
          else
          {
            if ( (unsigned int)(2 * v25) >= 0x42 )
              goto LABEL_63;
            WideCharStr[v25] = 0;
          }
        }
        else
        {
          Err::SetError(v20, -1003, v12);
          v11 = v20[0];
        }
        if ( (v11 & 8) == 0 )
        {
          v25 = 32;
          if ( ErrGenericMultiByteCbToNWide(0, 4u, v27, 32, v29, (int)&v25) < 0 )
          {
            Err::SetError(v20, -1003, v13);
            v11 = v20[0];
            goto LABEL_31;
          }
          v14 = v25;
          if ( (unsigned int)(v25 - 1) > 0x1F )
          {
            v29[0] = 0;
LABEL_31:
            if ( (v11 & 8) == 0 )
            {
              if ( (*(_BYTE *)a8 & 1) != 0 )
                v15 = 0;
              else
                v15 = *((_DWORD *)a8 + 1);
              Err::SetError(a8, v15, -8194, WideCharStr, v29, v14);
            }
            goto LABEL_36;
          }
          v14 = 2 * v25;
          if ( (unsigned int)(2 * v25) < 0x42 )
          {
            v29[v25] = 0;
            goto LABEL_31;
          }
LABEL_63:
          __report_rangecheckfailure();
        }
      }
    }
LABEL_36:
    v31 = -1;
    if ( (v11 & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v23 )
        operator delete[](v23);
    }
    v10 = a6;
    goto LABEL_42;
  }
}

```

## disassembly

```asm
0x10020080  mov     edi, edi
0x10020082  push    ebp
0x10020083  mov     ebp, esp
0x10020085  push    0FFFFFFFFh
0x10020087  push    offset ?OpenFile@Database@@QAEXPBG00W4DBOpenFreq@@W4DBIntent@@W4DBShare@@AAVErr@@@Z_SEH
0x1002008c  mov     eax, large fs:0
0x10020092  push    eax
0x10020093  sub     esp, 114h
0x10020099  mov     eax, ___security_cookie
0x1002009e  xor     eax, ebp
0x100200a0  mov     [ebp+var_10], eax
0x100200a3  push    ebx
0x100200a4  push    esi
0x100200a5  push    edi
0x100200a6  push    eax
0x100200a7  lea     eax, [ebp+var_C]
0x100200aa  mov     large fs:0, eax
0x100200b0  mov     edi, ecx
0x100200b2  mov     eax, [ebp+arg_4]
0x100200b5  mov     edx, [ebp+arg_0]
0x100200b8  mov     ecx, [ebp+arg_8]
0x100200bb  mov     esi, [ebp+arg_18]
0x100200be  mov     [ebp+lpFileName], edx
0x100200c4  mov     [ebp+var_120], ecx
0x100200ca  test    eax, eax
0x100200cc  jz      short loc_100200E6
0x100200ce  push    esi
0x100200cf  push    1
0x100200d1  push    ecx
0x100200d2  lea     ecx, [ebp+var_38]
0x100200d5  push    ecx
0x100200d6  push    eax
0x100200d7  mov     ecx, edi
0x100200d9  call    ?ValidateConnectString@Database@@IAEXPBGQAGKW4DBLocale@@AAVErr@@@Z; Database::ValidateConnectString(ushort const *,ushort * const,ulong,DBLocale,Err &)
0x100200de  mov     edx, [ebp+lpFileName]
0x100200e4  jmp     short loc_100200EC
0x100200e6  xor     eax, eax
0x100200e8  mov     [ebp+var_38], ax
0x100200ec  test    byte ptr [esi], 8
0x100200ef  jnz     loc_10020401
0x100200f5  mov     eax, [ebp+arg_14]
0x100200f8  sub     eax, 0
0x100200fb  jz      short loc_10020108
0x100200fd  sub     eax, 1
0x10020100  jnz     short loc_1002010C
0x10020102  or      dword ptr [edi+14h], 4
0x10020106  jmp     short loc_1002010C
0x10020108  or      dword ptr [edi+14h], 2
0x1002010c  mov     ebx, [ebp+arg_10]
0x1002010f  test    ebx, ebx
0x10020111  jz      short loc_10020118
0x10020113  cmp     ebx, 3
0x10020116  jnz     short loc_1002011C
0x10020118  or      dword ptr [edi+14h], 1
0x1002011c  push    esi; struct Err *
0x1002011d  lea     ecx, [edi+4]; this
0x10020120  push    edx; lpFileName
0x10020121  call    ?Open@File@@QAEXPBGAAVErr@@@Z; File::Open(ushort const *,Err &)
0x10020126  test    byte ptr [esi], 8
0x10020129  jnz     short loc_10020133
0x1002012b  push    esi; struct Err *
0x1002012c  mov     ecx, edi; this
0x1002012e  call    ?AllocateHashTable@Database@@IAEXAAVErr@@@Z; Database::AllocateHashTable(Err &)
0x10020133  test    byte ptr [esi], 1
0x10020136  jnz     loc_100202F2
0x1002013c  cmp     dword ptr [esi+4], 0FFFFFC00h
0x10020143  jnz     loc_100202F2
0x10020149  mov     [ebp+var_11C], 1
0x10020153  lea     eax, [ebp+var_11C]
0x10020159  mov     [ebp+var_4], 0
0x10020160  push    eax; struct Err *
0x10020161  mov     ecx, edi; this
0x10020163  call    ?OpenLockFile@Database@@IAEXAAVErr@@@Z; Database::OpenLockFile(Err &)
0x10020168  mov     ebx, [ebp+var_11C]
0x1002016e  test    bl, 8
0x10020171  jnz     loc_100202BA
0x10020177  mov     ecx, [edi+40h]; this
0x1002017a  lea     eax, [ebp+var_11C]
0x10020180  push    eax; struct Err *
0x10020181  push    40h ; '@'; nNumberOfBytesToRead
0x10020183  lea     eax, [ebp+MultiByteStr]
0x10020189  push    eax; lpBuffer
0x1002018a  push    0; lDistanceToMove
0x1002018c  call    ?Read@File@@QAEXKPAXKAAVErr@@@Z; File::Read(ulong,void *,ulong,Err &)
0x10020191  mov     ebx, [ebp+var_11C]
0x10020197  test    bl, 8
0x1002019a  jnz     loc_100202BA
0x100201a0  lea     eax, [ebp+var_104]
0x100201a6  mov     [ebp+var_104], 20h ; ' '
0x100201b0  push    eax; int
0x100201b1  lea     eax, [ebp+WideCharStr]
0x100201b7  mov     edx, 4; dwFlags
0x100201bc  push    eax; lpWideCharStr
0x100201bd  push    20h ; ' '; cbMultiByte
0x100201bf  lea     eax, [ebp+MultiByteStr]
0x100201c5  xor     ecx, ecx; CodePage
0x100201c7  push    eax; lpMultiByteStr
0x100201c8  call    _ErrGenericMultiByteCbToNWide@24; ErrGenericMultiByteCbToNWide(x,x,x,x,x,x)
0x100201cd  test    eax, eax
0x100201cf  jns     short loc_100201EA
0x100201d1  push    ecx
0x100201d2  push    0FFFFFC15h
0x100201d7  lea     ecx, [ebp+var_11C]
0x100201dd  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100201e2  mov     ebx, [ebp+var_11C]
0x100201e8  jmp     short loc_10020218
0x100201ea  mov     ecx, [ebp+var_104]
0x100201f0  lea     eax, [ecx-1]
0x100201f3  cmp     eax, 1Fh
0x100201f6  ja      short loc_1002020F
0x100201f8  add     ecx, ecx
0x100201fa  cmp     ecx, 42h ; 'B'
0x100201fd  jnb     loc_1002041F
0x10020203  xor     eax, eax
0x10020205  mov     [ebp+ecx+WideCharStr], ax
0x1002020d  jmp     short loc_10020218
0x1002020f  xor     eax, eax
0x10020211  mov     [ebp+WideCharStr], ax
0x10020218  test    bl, 8
0x1002021b  jnz     loc_100202BA
0x10020221  lea     eax, [ebp+var_104]
0x10020227  mov     [ebp+var_104], 20h ; ' '
0x10020231  push    eax; int
0x10020232  lea     eax, [ebp+var_7C]
0x10020235  mov     edx, 4; dwFlags
0x1002023a  push    eax; lpWideCharStr
0x1002023b  push    20h ; ' '; cbMultiByte
0x1002023d  lea     eax, [ebp+var_E0]
0x10020243  xor     ecx, ecx; CodePage
0x10020245  push    eax; lpMultiByteStr
0x10020246  call    _ErrGenericMultiByteCbToNWide@24; ErrGenericMultiByteCbToNWide(x,x,x,x,x,x)
0x1002024b  test    eax, eax
0x1002024d  jns     short loc_10020268
0x1002024f  push    ecx
0x10020250  push    0FFFFFC15h
0x10020255  lea     ecx, [ebp+var_11C]
0x1002025b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10020260  mov     ebx, [ebp+var_11C]
0x10020266  jmp     short loc_10020290
0x10020268  mov     ecx, [ebp+var_104]
0x1002026e  lea     eax, [ecx-1]
0x10020271  cmp     eax, 1Fh
0x10020274  ja      short loc_1002028A
0x10020276  add     ecx, ecx
0x10020278  cmp     ecx, 42h ; 'B'
0x1002027b  jnb     loc_1002041F
0x10020281  xor     eax, eax
0x10020283  mov     [ebp+ecx+var_7C], ax
0x10020288  jmp     short loc_10020290
0x1002028a  xor     eax, eax
0x1002028c  mov     [ebp+var_7C], ax
0x10020290  test    bl, 8
0x10020293  jnz     short loc_100202BA
0x10020295  test    byte ptr [esi], 1
0x10020298  jz      short loc_1002029E
0x1002029a  xor     eax, eax
0x1002029c  jmp     short loc_100202A1
0x1002029e  mov     eax, [esi+4]
0x100202a1  push    ecx
0x100202a2  lea     ecx, [ebp+var_7C]
0x100202a5  push    ecx
0x100202a6  lea     ecx, [ebp+WideCharStr]
0x100202ac  push    ecx
0x100202ad  push    0FFFFDFFEh
0x100202b2  push    eax
0x100202b3  mov     ecx, esi
0x100202b5  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x100202ba  mov     [ebp+var_4], 0FFFFFFFFh
0x100202c1  test    ebx, 0FFFFFFFEh
0x100202c7  jz      short loc_100202EF
0x100202c9  mov     eax, [ebp+Block]
0x100202cf  test    eax, eax
0x100202d1  jz      short loc_100202DC
0x100202d3  push    eax; Block
0x100202d4  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100202d9  add     esp, 4
0x100202dc  mov     eax, [ebp+var_10C]
0x100202e2  test    eax, eax
0x100202e4  jz      short loc_100202EF
0x100202e6  push    eax; Block
0x100202e7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100202ec  add     esp, 4
0x100202ef  mov     ebx, [ebp+arg_10]
0x100202f2  test    byte ptr [esi], 8
0x100202f5  jnz     loc_10020401
0x100202fb  mov     [ebp+var_114], 0
0x10020305  mov     [ebp+Block], 0
0x1002030f  push    esi
0x10020310  push    ebx
0x10020311  lea     eax, [ebp+var_38]
0x10020314  mov     [ebp+var_4], 1
0x1002031b  push    eax
0x1002031c  lea     eax, [ebp+var_114]
0x10020322  mov     ecx, edi
0x10020324  push    eax
0x10020325  call    ?ValidateDatabaseFile@Database@@IAE?AW4DBType@@PAVDBHeaderPage@@QBGW4DBIntent@@AAVErr@@@Z; Database::ValidateDatabaseFile(DBHeaderPage *,ushort const * const,DBIntent,Err &)
0x1002032a  test    byte ptr [esi], 8
0x1002032d  mov     [ebp+lpFileName], eax
0x10020333  jnz     loc_100203DB
0x10020339  mov     eax, [ebp+arg_14]
0x1002033c  cmp     eax, 2
0x1002033f  jz      short loc_1002034A
0x10020341  cmp     eax, 1
0x10020344  jnz     short loc_10020395
0x10020346  cmp     ebx, eax
0x10020348  jnz     short loc_10020395
0x1002034a  push    esi; struct Err *
0x1002034b  mov     ecx, edi; this
0x1002034d  call    ?OpenLockFile@Database@@IAEXAAVErr@@@Z; Database::OpenLockFile(Err &)
0x10020352  mov     eax, [esi]
0x10020354  test    al, 8
0x10020356  jnz     short loc_1002036F
0x10020358  push    esi; struct Err *
0x10020359  push    [ebp+var_120]; unsigned __int16 *
0x1002035f  lea     eax, [ebp+var_114]
0x10020365  mov     ecx, edi; this
0x10020367  push    eax; struct DBHeaderPage *
0x10020368  call    ?AssignUserNumber@Database@@IAEXPAVDBHeaderPage@@PBGAAVErr@@@Z; Database::AssignUserNumber(DBHeaderPage *,ushort const *,Err &)
0x1002036d  jmp     short loc_10020395
0x1002036f  test    al, 1
0x10020371  jnz     short loc_10020381
0x10020373  cmp     dword ptr [esi+4], 0FFFFFBF8h
0x1002037a  jnz     short loc_10020381
0x1002037c  cmp     ebx, 1
0x1002037f  jz      short loc_10020395
0x10020381  mov     ecx, esi; this
0x10020383  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x10020388  push    ecx
0x10020389  push    0FFFFFBF9h
0x1002038e  mov     ecx, esi
0x10020390  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10020395  test    byte ptr [esi], 8
0x10020398  jnz     short loc_100203DB
0x1002039a  cmp     ebx, 2
0x1002039d  jz      short loc_100203BF
0x1002039f  cmp     ebx, 3
0x100203a2  jz      short loc_100203BF
0x100203a4  push    esi; struct Err *
0x100203a5  lea     eax, [ebp+var_114]
0x100203ab  mov     ecx, edi; this
0x100203ad  push    eax; struct DBHeaderPage *
0x100203ae  call    ?CheckForCorruption@Database@@IAEXPAVDBHeaderPage@@AAVErr@@@Z; Database::CheckForCorruption(DBHeaderPage *,Err &)
0x100203b3  test    byte ptr [esi], 8
0x100203b6  jz      short loc_100203C4
0x100203b8  mov     dword ptr [edi+44h], 0
0x100203bf  test    byte ptr [esi], 8
0x100203c2  jnz     short loc_100203DB
0x100203c4  lea     eax, [edi+19Ch]
0x100203ca  push    eax
0x100203cb  push    100h
0x100203d0  lea     ecx, [ebp+var_114]
0x100203d6  call    ?SignatureDiffers@DBHeaderPage@@QAE?AW4DBBool@@IQAVDiskUShort@@@Z; DBHeaderPage::SignatureDiffers(uint,DiskUShort * const)
0x100203db  mov     eax, [ebp+arg_14]
0x100203de  mov     [edi+64h], eax
0x100203e1  mov     eax, [ebp+arg_C]
0x100203e4  mov     [edi+60h], eax
0x100203e7  mov     eax, [ebp+lpFileName]
0x100203ed  mov     [edi+44h], eax
0x100203f0  mov     eax, [ebp+var_114]
0x100203f6  mov     [edi+68h], ebx
0x100203f9  test    eax, eax
0x100203fb  jz      short loc_10020401
0x100203fd  dec     word ptr [eax+4Ch]
0x10020401  mov     ecx, [ebp+var_C]
0x10020404  mov     large fs:0, ecx
0x1002040b  pop     ecx
0x1002040c  pop     edi
0x1002040d  pop     esi
0x1002040e  pop     ebx
0x1002040f  mov     ecx, [ebp+var_10]
0x10020412  xor     ecx, ebp; StackCookie
0x10020414  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10020419  mov     esp, ebp
0x1002041b  pop     ebp
0x1002041c  retn    1Ch
0x1002041f  call    ___report_rangecheckfailure
0x10060410  lea     ecx, [ebp+var_11C]; this
0x10060416  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1006041b  lea     ecx, [ebp+var_114]; this
0x10060421  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x1006042b  nop
0x1006042c  nop
0x1006042d  mov     edx, [esp-4+arg_4]
0x10060431  lea     eax, [edx+0Ch]
0x10060434  mov     ecx, [edx-124h]
0x1006043a  xor     ecx, eax; StackCookie
0x1006043c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060441  mov     ecx, [edx-4]
0x10060444  xor     ecx, eax; StackCookie
0x10060446  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006044b  mov     eax, offset stru_10063348
0x10060450  jmp     ___CxxFrameHandler3
```
