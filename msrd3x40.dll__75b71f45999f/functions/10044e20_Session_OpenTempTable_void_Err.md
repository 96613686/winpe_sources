# Session::OpenTempTable(void *,Err &)

- ea: `0x10044e20`
- end: `0x100451c6`
- name: `?OpenTempTable@Session@@QAEPAVCursor@@PAXAAVErr@@@Z`
- size: `934`
- prototype: `struct Cursor *__thiscall(Session *__hidden this, void *, struct Err *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x10026200`
- `0x1002bf00`

## callees

- `0x1000eb60`
- `0x10019240`
- `0x10025ee0`
- `0x10044e20`
- `0x100518a0`
- `0x10051e80`
- `0x10052140`
- `0x10052e30`
- `0x100544e0`
- `0x10055260`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`
- `0x1005f490`

## pseudocode

```c
struct Cursor *__thiscall Session::OpenTempTable(Session *this, _DWORD *a2, struct Err *a3)
{
  _DWORD *v3; // ebx
  struct Err *v4; // edi
  int v5; // ecx
  _WORD *v6; // esi
  Table *v7; // eax
  int v8; // ecx
  int v9; // edx
  int v10; // eax
  const unsigned __int16 *v11; // ecx
  int v12; // edi
  int v13; // ecx
  unsigned __int16 v14; // ax
  int i; // ecx
  unsigned __int16 v16; // ax
  struct Err *v17; // esi
  int v18; // ecx
  _DWORD *v19; // edi
  unsigned int v21; // [esp-Ch] [ebp-1254h]
  unsigned int v22; // [esp-8h] [ebp-1250h]
  void *v23; // [esp+14h] [ebp-1234h]
  Table *v24; // [esp+18h] [ebp-1230h]
  char *v25; // [esp+18h] [ebp-1230h]
  _WORD *v26; // [esp+1Ch] [ebp-122Ch]
  int v27; // [esp+20h] [ebp-1228h]
  Table *Block; // [esp+2Ch] [ebp-121Ch]
  _WORD v30[2298]; // [esp+30h] [ebp-1218h] BYREF
  __int16 v31; // [esp+1224h] [ebp-24h] BYREF
  __int64 v32; // [esp+1226h] [ebp-22h]
  wchar_t v33; // [esp+122Eh] [ebp-1Ah]
  int v34; // [esp+1230h] [ebp-18h] BYREF
  int v35; // [esp+1234h] [ebp-14h]
  int v36; // [esp+1244h] [ebp-4h]

  v3 = a2;
  v4 = a3;
  v31 = 73;
  v5 = a2[6];
  v27 = v5;
  v32 = *(_QWORD *)L"ndex";
  v33 = aIndex[5];
  v34 = 3145776;
  v35 = 48;
  if ( v5 )
  {
    v26 = (_WORD *)a2[7];
  }
  else
  {
    v26 = v30;
    v30[0] = 0;
  }
  v6 = v30;
  if ( v5 )
    v6 = 0;
  v24 = (Table *)operator new(0x778u);
  v36 = 0;
  v7 = Table::Table(v24, *(struct Database **)(*((_DWORD *)this + 13) + 16), a3);
  Block = v7;
  v36 = -1;
  if ( !v7 )
  {
    Err::SetError(a3, -1011, v8);
    v7 = 0;
  }
  if ( (*(_BYTE *)a3 & 8) != 0
    || (Table::Create(v7, *((struct Transaction ***)this + 13), (unsigned __int16 *)&dword_10003A20, v21, v22, a3),
        (*(_BYTE *)a3 & 8) != 0) )
  {
    if ( Block )
    {
      Table::~Table(Block);
      operator delete(Block);
    }
  }
  else
  {
    v9 = 0;
    v25 = 0;
    ++*((_DWORD *)Block + 19);
    if ( (int)a2[2] > 0 )
    {
      v10 = v27;
      while ( 1 )
      {
        if ( v10 )
          v11 = *(const unsigned __int16 **)(v3[6] + 4 * v9);
        else
          v11 = (const unsigned __int16 *)&v34;
        v12 = 36 * v9;
        Table::AddColumn(
          Block,
          *((struct Instance **)this + 13),
          v11,
          (const struct tagTblColDef *)(36 * v9 + v3[3]),
          a3);
        if ( (*(_BYTE *)a3 & 8) != 0 )
        {
LABEL_25:
          v4 = a3;
          break;
        }
        v13 = *(unsigned __int16 *)(v3[3] + v12 + 32);
        v10 = v27;
        if ( v13 == 32 )
        {
          if ( !v27 )
            goto LABEL_20;
        }
        else if ( !v27 )
        {
          v14 = v34;
          *v6 = v13;
          *(_DWORD *)(v6 + 1) = __PAIR32__(HIWORD(v34), v14);
          *(_DWORD *)(v6 + 3) = v35;
          v6 += 5;
LABEL_20:
          for ( i = 2; i >= 0; --i )
          {
            v16 = *((_WORD *)&v34 + i) + 1;
            *((_WORD *)&v34 + i) = v16;
            if ( v16 <= 0x39u )
              break;
            *((_WORD *)&v34 + i) = 48;
          }
          v3 = a2;
          v10 = v27;
        }
        v9 = (int)(v25 + 1);
        v25 = (char *)v9;
        if ( v9 >= v3[2] )
          goto LABEL_25;
      }
    }
    if ( (*(_BYTE *)v4 & 8) == 0 )
    {
      if ( !v26 || !*v26 )
        goto LABEL_34;
      if ( !v27 )
        *v6 = 0;
      if ( *((_WORD *)v3 + 2) != 32 )
        v31 = *((_WORD *)v3 + 2);
      Table::AddIndex(Block, *((_DWORD *)this + 13), &v31, v3 + 4, v26, 0, v4, 0);
      if ( (*(_BYTE *)v4 & 8) == 0 )
      {
LABEL_34:
        v23 = operator new(0x16Cu);
        v36 = 1;
        v17 = a3;
        v19 = (_DWORD *)Cursor::Cursor(v23, *((_DWORD *)this + 13), Block, *v3, 0, v4, 0);
        v36 = -1;
        if ( !v19 )
          Err::SetError(a3, -1011, v18);
        if ( (*(_BYTE *)a3 & 8) == 0 )
        {
          Table::Release(Block, *((struct Instance **)this + 13));
          v19[83] = v3[5];
          if ( *v3 == 5 && v26 && *v26 )
          {
            (*(void (__thiscall **)(_DWORD *, __int16 *, struct Err *))(*v19 + 8))(v19, &v31, a3);
            v17 = a3;
          }
          if ( (*(_BYTE *)v17 & 8) == 0 )
            return (struct Cursor *)v19;
        }
        if ( v19 )
          (*(void (__thiscall **)(_DWORD *, int))*v19)(v19, 1);
      }
    }
    Table::Release(Block, *((struct Instance **)this + 13));
  }
  return 0;
}

```

## disassembly

```asm
0x10044e20  mov     edi, edi
0x10044e22  push    ebp
0x10044e23  mov     ebp, esp
0x10044e25  push    0FFFFFFFFh
0x10044e27  push    offset ?OpenTempTable@Session@@QAEPAVCursor@@PAXAAVErr@@@Z_SEH
0x10044e2c  mov     eax, large fs:0
0x10044e32  push    eax
0x10044e33  mov     eax, 122Ch
0x10044e38  call    __chkstk
0x10044e3d  mov     eax, ___security_cookie
0x10044e42  xor     eax, ebp
0x10044e44  mov     [ebp+var_10], eax
0x10044e47  push    ebx
0x10044e48  push    esi
0x10044e49  push    edi
0x10044e4a  push    eax; unsigned int
0x10044e4b  lea     eax, [ebp+var_C]
0x10044e4e  mov     large fs:0, eax
0x10044e54  mov     [ebp+var_1220], ecx
0x10044e5a  mov     ebx, [ebp+arg_0]
0x10044e5d  mov     eax, 49h ; 'I'
0x10044e62  movq    xmm0, qword ptr ds:aIndex+2; "ndex"
0x10044e6a  mov     edi, [ebp+arg_4]
0x10044e6d  mov     [ebp+var_24], ax
0x10044e71  mov     ecx, [ebx+18h]
0x10044e74  mov     ax, word ptr ds:aIndex+0Ah; ""
0x10044e7a  mov     [ebp+var_1234], ebx
0x10044e80  mov     [ebp+var_1224], edi
0x10044e86  mov     [ebp+var_1228], ecx
0x10044e8c  movq    [ebp+var_22], xmm0
0x10044e91  mov     [ebp+var_1A], ax
0x10044e95  mov     [ebp+var_18], 300030h
0x10044e9c  mov     [ebp+var_14], 30h ; '0'
0x10044ea3  test    ecx, ecx
0x10044ea5  jz      short loc_10044EB2
0x10044ea7  mov     eax, [ebx+1Ch]
0x10044eaa  mov     [ebp+var_122C], eax
0x10044eb0  jmp     short loc_10044EC7
0x10044eb2  lea     eax, [ebp+var_1218]
0x10044eb8  mov     [ebp+var_122C], eax
0x10044ebe  xor     eax, eax
0x10044ec0  mov     [ebp+var_1218], ax
0x10044ec7  xor     eax, eax
0x10044ec9  lea     esi, [ebp+var_1218]
0x10044ecf  test    ecx, ecx
0x10044ed1  push    778h; Size
0x10044ed6  cmovnz  esi, eax
0x10044ed9  call    ??2@YAPAXI@Z; operator new(uint)
0x10044ede  add     esp, 4
0x10044ee1  mov     [ebp+var_1230], eax
0x10044ee7  mov     ecx, [ebp+var_1220]
0x10044eed  mov     [ebp+var_4], 0
0x10044ef4  push    edi; struct Err *
0x10044ef5  mov     ecx, [ecx+34h]
0x10044ef8  push    dword ptr [ecx+10h]; struct Database *
0x10044efb  mov     ecx, eax; this
0x10044efd  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x10044f02  mov     [ebp+Block], eax
0x10044f08  mov     [ebp+var_4], 0FFFFFFFFh
0x10044f0f  test    eax, eax
0x10044f11  jnz     short loc_10044F26
0x10044f13  push    ecx
0x10044f14  push    0FFFFFC0Dh; unsigned int
0x10044f19  mov     ecx, edi
0x10044f1b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10044f20  mov     eax, [ebp+Block]
0x10044f26  test    byte ptr [edi], 8
0x10044f29  jnz     loc_10045187
0x10044f2f  mov     ecx, [ebp+var_1220]
0x10044f35  push    edi; struct Err *
0x10044f36  sub     esp, 8
0x10044f39  push    offset dword_10003A20; unsigned __int16 *
0x10044f3e  push    dword ptr [ecx+34h]; struct Instance *
0x10044f41  mov     ecx, eax; this
0x10044f43  call    ?Create@Table@@QAEXPAVInstance@@PBGKKAAVErr@@@Z; Table::Create(Instance *,ushort const *,ulong,ulong,Err &)
0x10044f48  test    byte ptr [edi], 8
0x10044f4b  jnz     loc_10045187
0x10044f51  mov     eax, [ebp+Block]
0x10044f57  xor     edx, edx
0x10044f59  mov     [ebp+var_1230], edx
0x10044f5f  inc     dword ptr [eax+4Ch]
0x10044f62  cmp     [ebx+8], edx
0x10044f65  jle     loc_10045047
0x10044f6b  mov     eax, [ebp+var_1228]
0x10044f71  test    eax, eax
0x10044f73  jz      short loc_10044F7D
0x10044f75  mov     eax, [ebx+18h]
0x10044f78  mov     ecx, [eax+edx*4]
0x10044f7b  jmp     short loc_10044F80
0x10044f7d  lea     ecx, [ebp+var_18]
0x10044f80  push    [ebp+var_1224]; struct Err *
0x10044f86  mov     eax, [ebx+0Ch]
0x10044f89  lea     edi, [edx+edx*8]
0x10044f8c  shl     edi, 2
0x10044f8f  add     eax, edi
0x10044f91  push    eax; struct tagTblColDef *
0x10044f92  mov     eax, [ebp+var_1220]
0x10044f98  push    ecx; unsigned __int16 *
0x10044f99  mov     ecx, [ebp+Block]; this
0x10044f9f  push    dword ptr [eax+34h]; struct Instance *
0x10044fa2  call    ?AddColumn@Table@@QAEPAVColumn@@PAVInstance@@PBGPBUtagTblColDef@@AAVErr@@@Z; Table::AddColumn(Instance *,ushort const *,tagTblColDef const *,Err &)
0x10044fa7  mov     eax, [ebp+var_1224]
0x10044fad  test    byte ptr [eax], 8
0x10044fb0  jnz     loc_10045041
0x10044fb6  mov     eax, [ebx+0Ch]
0x10044fb9  movzx   eax, word ptr [eax+edi+20h]
0x10044fbe  mov     ecx, eax
0x10044fc0  cmp     eax, 20h ; ' '
0x10044fc3  mov     eax, [ebp+var_1228]
0x10044fc9  jz      short loc_10044FF7
0x10044fcb  test    eax, eax
0x10044fcd  jnz     short loc_1004502B
0x10044fcf  movzx   eax, word ptr [ebp+var_18]
0x10044fd3  mov     [esi], cx
0x10044fd6  mov     [esi+2], ax
0x10044fda  movzx   eax, word ptr [ebp+var_18+2]
0x10044fde  mov     [esi+4], ax
0x10044fe2  movzx   eax, word ptr [ebp+var_14]
0x10044fe6  mov     [esi+6], ax
0x10044fea  movzx   eax, word ptr [ebp+var_14+2]
0x10044fee  mov     [esi+8], ax
0x10044ff2  add     esi, 0Ah
0x10044ff5  jmp     short loc_10044FFB
0x10044ff7  test    eax, eax
0x10044ff9  jnz     short loc_1004502B
0x10044ffb  mov     ecx, 2
0x10045000  lea     ebx, [ecx+2Eh]
0x10045003  mov     ax, word ptr [ebp+ecx*2+var_18]
0x10045008  inc     ax
0x1004500a  mov     word ptr [ebp+ecx*2+var_18], ax
0x1004500f  cmp     ax, 39h ; '9'
0x10045013  jbe     short loc_1004501F
0x10045015  mov     word ptr [ebp+ecx*2+var_18], bx
0x1004501a  sub     ecx, 1
0x1004501d  jns     short loc_10045003
0x1004501f  mov     ebx, [ebp+var_1234]
0x10045025  mov     eax, [ebp+var_1228]
0x1004502b  mov     edx, [ebp+var_1230]
0x10045031  inc     edx
0x10045032  mov     [ebp+var_1230], edx
0x10045038  cmp     edx, [ebx+8]
0x1004503b  jl      loc_10044F71
0x10045041  mov     edi, [ebp+var_1224]
0x10045047  test    byte ptr [edi], 8
0x1004504a  jnz     loc_10045171
0x10045050  mov     edx, [ebp+var_122C]
0x10045056  test    edx, edx
0x10045058  jz      short loc_100450A8
0x1004505a  cmp     word ptr [edx], 0
0x1004505e  jz      short loc_100450A8
0x10045060  cmp     [ebp+var_1228], 0
0x10045067  jnz     short loc_1004506E
0x10045069  xor     eax, eax
0x1004506b  mov     [esi], ax
0x1004506e  movzx   eax, word ptr [ebx+4]
0x10045072  mov     ecx, eax
0x10045074  cmp     eax, 20h ; ' '
0x10045077  jz      short loc_1004507D
0x10045079  mov     [ebp+var_24], cx
0x1004507d  mov     ecx, [ebp+Block]
0x10045083  lea     eax, [ebx+10h]
0x10045086  push    0
0x10045088  push    edi
0x10045089  push    0
0x1004508b  push    edx
0x1004508c  push    eax
0x1004508d  lea     eax, [ebp+var_24]
0x10045090  push    eax
0x10045091  mov     eax, [ebp+var_1220]
0x10045097  push    dword ptr [eax+34h]
0x1004509a  call    ?AddIndex@Table@@QAEPAVIndex@@PAVInstance@@PBGPAUtagTblIdxDef@@1IAAVErr@@W4TblRefOrIdx@@@Z; Table::AddIndex(Instance *,ushort const *,tagTblIdxDef *,ushort const *,uint,Err &,TblRefOrIdx)
0x1004509f  test    byte ptr [edi], 8
0x100450a2  jnz     loc_10045171
0x100450a8  push    16Ch; Size
0x100450ad  call    ??2@YAPAXI@Z; operator new(uint)
0x100450b2  add     esp, 4
0x100450b5  mov     [ebp+var_1234], eax
0x100450bb  mov     ecx, [ebp+var_1220]
0x100450c1  push    0
0x100450c3  push    edi
0x100450c4  push    0
0x100450c6  mov     [ebp+var_4], 1
0x100450cd  push    dword ptr [ebx]
0x100450cf  push    [ebp+Block]
0x100450d5  push    dword ptr [ecx+34h]
0x100450d8  mov     ecx, eax
0x100450da  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint)
0x100450df  mov     esi, [ebp+var_1224]
0x100450e5  mov     edi, eax
0x100450e7  mov     [ebp+var_4], 0FFFFFFFFh
0x100450ee  test    edi, edi
0x100450f0  jnz     short loc_100450FF
0x100450f2  push    ecx
0x100450f3  push    0FFFFFC0Dh
0x100450f8  mov     ecx, esi
0x100450fa  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100450ff  test    byte ptr [esi], 8
0x10045102  jnz     short loc_1004515B
0x10045104  mov     eax, [ebp+var_1220]
0x1004510a  mov     ecx, [ebp+Block]; this
0x10045110  push    dword ptr [eax+34h]; struct Instance *
0x10045113  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x10045118  mov     eax, [ebx+14h]
0x1004511b  mov     [edi+14Ch], eax
0x10045121  cmp     dword ptr [ebx], 5
0x10045124  jnz     short loc_10045152
0x10045126  mov     eax, [ebp+var_122C]
0x1004512c  test    eax, eax
0x1004512e  jz      short loc_10045152
0x10045130  cmp     word ptr [eax], 0
0x10045134  jz      short loc_10045152
0x10045136  mov     eax, [edi]
0x10045138  lea     ecx, [ebp+var_24]
0x1004513b  push    esi; unsigned int
0x1004513c  push    ecx; void *
0x1004513d  mov     esi, [eax+8]
0x10045140  mov     ecx, esi
0x10045142  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10045148  mov     ecx, edi
0x1004514a  call    esi
0x1004514c  mov     esi, [ebp+var_1224]
0x10045152  test    byte ptr [esi], 8
0x10045155  jnz     short loc_1004515B
0x10045157  mov     eax, edi
0x10045159  jmp     short loc_100451A8
0x1004515b  test    edi, edi
0x1004515d  jz      short loc_10045171
0x1004515f  mov     eax, [edi]
0x10045161  push    1; void *
0x10045163  mov     esi, [eax]
0x10045165  mov     ecx, esi
0x10045167  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004516d  mov     ecx, edi
0x1004516f  call    esi
0x10045171  mov     eax, [ebp+var_1220]
0x10045177  mov     ecx, [ebp+Block]; this
0x1004517d  push    dword ptr [eax+34h]; struct Instance *
0x10045180  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x10045185  jmp     short loc_100451A6
0x10045187  mov     ebx, [ebp+Block]
0x1004518d  test    ebx, ebx
0x1004518f  jz      short loc_100451A6
0x10045191  mov     ecx, ebx; this
0x10045193  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x10045198  push    778h; unsigned int
0x1004519d  push    ebx; Block
0x1004519e  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100451a3  add     esp, 8
0x100451a6  xor     eax, eax
0x100451a8  mov     ecx, [ebp+var_C]
0x100451ab  mov     large fs:0, ecx
0x100451b2  pop     ecx
0x100451b3  pop     edi
0x100451b4  pop     esi
0x100451b5  pop     ebx
0x100451b6  mov     ecx, [ebp+var_10]
0x100451b9  xor     ecx, ebp; StackCookie
0x100451bb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100451c0  mov     esp, ebp
0x100451c2  pop     ebp
0x100451c3  retn    8
0x100614a0  push    778h; unsigned int
0x100614a5  mov     eax, [ebp+var_1230]
0x100614ab  push    eax; Block
0x100614ac  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100614b1  add     esp, 8
0x100614b4  retn
0x100614b5  push    16Ch; unsigned int
0x100614ba  mov     eax, [ebp+var_1234]
0x100614c0  push    eax; Block
0x100614c1  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100614c6  add     esp, 8
0x100614c9  retn
0x100614cf  nop
0x100614d0  nop
0x100614d1  mov     edx, [esp-4+arg_4]
0x100614d5  lea     eax, [edx+0Ch]
0x100614d8  mov     ecx, [edx-123Ch]
0x100614de  xor     ecx, eax; StackCookie
0x100614e0  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100614e5  mov     ecx, [edx-4]
0x100614e8  xor     ecx, eax; StackCookie
0x100614ea  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100614ef  mov     eax, offset stru_10063EF4
0x100614f4  jmp     ___CxxFrameHandler3
```
