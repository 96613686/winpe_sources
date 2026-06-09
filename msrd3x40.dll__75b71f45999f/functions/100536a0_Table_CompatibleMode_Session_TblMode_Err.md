# Table::CompatibleMode(Session *,TblMode,Err &)

- ea: `0x100536a0`
- end: `0x1005394a`
- name: `?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z`
- size: `682`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1001dc70`
- `0x1001dfc0`
- `0x10035650`
- `0x10035910`
- `0x10036160`
- `0x100364e0`
- `0x10036620`
- `0x10053950`
- `0x10055ed0`

## callees

- `0x1000f750`
- `0x10020af0`
- `0x10025db0`
- `0x10025ee0`
- `0x100536a0`
- `0x10057e90`
- `0x10058160`
- `0x10059320`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Table::CompatibleMode(int this, struct Session *a2, unsigned int a3, struct Err *a4)
{
  unsigned int v5; // esi
  const unsigned __int16 *v6; // edi
  unsigned int v7; // eax
  Table *v8; // ecx
  unsigned int v9; // edx
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  struct Err *v15; // [esp-4h] [ebp-38h]

  v5 = a3;
  if ( a3 == 5 )
  {
    v5 = 1;
  }
  else if ( a3 == 6 )
  {
    v5 = 2;
  }
  else if ( *(_BYTE *)(this + 8) == 83 )
  {
    v5 = 0;
  }
  if ( *(_DWORD *)(this + 56) != -1 )
  {
    v6 = *(const unsigned __int16 **)this;
    if ( (*(_DWORD *)a4 & 0xFFFFFFFE) != 0 )
    {
      if ( *((_DWORD *)a4 + 3) )
        operator delete[](*((void **)a4 + 3));
      if ( *((_DWORD *)a4 + 4) )
        operator delete[](*((void **)a4 + 4));
    }
    *(_DWORD *)a4 = 8;
    *((_DWORD *)a4 + 1) = -1305;
    *((_DWORD *)a4 + 2) = -8300;
    Err::CopyString((Err *)this, (wchar_t *)a4 + 6, v6);
    *((_DWORD *)a4 + 4) = 0;
    return;
  }
  v7 = *(_DWORD *)(this + 48);
  if ( !v7 && (v5 == 3 || v5 == 4 || v5 == 1) )
  {
    Database::LockTable(*(_DWORD *)(this + 36), *(_DWORD *)(this + 40), v5, a4, 0);
    v8 = (Table *)this;
    v15 = a4;
    if ( (*(_BYTE *)a4 & 8) != 0 )
    {
      Table::ReportLockConflict((Table *)this, 0, a4);
      return;
    }
    *(_DWORD *)(this + 48) = v5;
    *(_DWORD *)(this + 44) = v5;
    goto LABEL_42;
  }
  v9 = *(_DWORD *)(this + 124);
  v10 = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      v7 = *(_DWORD *)(this + 48);
      if ( *(struct Session **)(*(_DWORD *)(this + 116) + 4 * v10) == a2 )
        break;
      if ( ++v10 >= v9 )
        goto LABEL_24;
    }
LABEL_25:
    if ( v5 <= 4 )
    {
      if ( *(_DWORD *)(this + 76) )
      {
        v12 = *(_DWORD *)(this + 44) + 5 * v5;
        v13 = *(&dword_10007240 + v12);
        if ( v13 )
        {
          Table::ReportLockConflict((Table *)this, v13, 0, a4);
          return;
        }
      }
      else
      {
        if ( v7 > 4 )
          goto LABEL_28;
        v11 = *(&dword_100071D8 + 5 * v5 + v7);
        if ( v11 )
        {
          Table::ReportLockConflict((Table *)this, v11, 0, a4);
          return;
        }
        v12 = 5 * v5 + *(_DWORD *)(this + 44);
      }
      *(_DWORD *)(this + 44) = dword_100072A8[v12];
      return;
    }
LABEL_28:
    Err::SetError(a4, -1003, v10);
    return;
  }
LABEL_24:
  if ( v10 != v9 )
    goto LABEL_25;
  if ( v5 > 4 || v7 > 4 )
  {
    Err::SetError(a4, -1003, v10);
  }
  else
  {
    v14 = *(&dword_10007240 + 4 * v5 + v5 + v7);
    if ( v14 )
      Table::ReportLockConflict((Table *)this, v14, 0, a4);
  }
  if ( (*(_BYTE *)a4 & 8) == 0 )
  {
    v15 = a4;
    v8 = (Table *)this;
LABEL_42:
    Table::AddSession(v8, a2, v15);
  }
}

```

## disassembly

```asm
0x100536a0  mov     edi, edi
0x100536a2  push    ebp
0x100536a3  mov     ebp, esp
0x100536a5  push    0FFFFFFFFh
0x100536a7  push    offset ?Release@Table@@QAEJPAVInstance@@@Z_SEH
0x100536ac  mov     eax, large fs:0
0x100536b2  push    eax
0x100536b3  sub     esp, 18h
0x100536b6  push    ebx
0x100536b7  push    esi
0x100536b8  push    edi
0x100536b9  mov     eax, ___security_cookie
0x100536be  xor     eax, ebp
0x100536c0  push    eax
0x100536c1  lea     eax, [ebp+var_C]
0x100536c4  mov     large fs:0, eax
0x100536ca  mov     edi, ecx
0x100536cc  mov     esi, [ebp+arg_4]
0x100536cf  cmp     esi, 5
0x100536d2  jnz     short loc_100536DB
0x100536d4  mov     esi, 1
0x100536d9  jmp     short loc_100536F0
0x100536db  cmp     esi, 6
0x100536de  jnz     short loc_100536E7
0x100536e0  mov     esi, 2
0x100536e5  jmp     short loc_100536F0
0x100536e7  xor     eax, eax
0x100536e9  cmp     byte ptr [edi+8], 53h ; 'S'
0x100536ed  cmovz   esi, eax
0x100536f0  cmp     dword ptr [edi+38h], 0FFFFFFFFh
0x100536f4  jz      short loc_1005375C
0x100536f6  mov     esi, [ebp+arg_8]
0x100536f9  mov     edi, [edi]
0x100536fb  test    dword ptr [esi], 0FFFFFFFEh
0x10053701  jz      short loc_10053723
0x10053703  mov     eax, [esi+0Ch]
0x10053706  test    eax, eax
0x10053708  jz      short loc_10053713
0x1005370a  push    eax; Block
0x1005370b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10053710  add     esp, 4
0x10053713  mov     eax, [esi+10h]
0x10053716  test    eax, eax
0x10053718  jz      short loc_10053723
0x1005371a  push    eax; Block
0x1005371b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10053720  add     esp, 4
0x10053723  push    edi; unsigned __int16 *
0x10053724  lea     eax, [esi+0Ch]
0x10053727  mov     dword ptr [esi], 8
0x1005372d  push    eax; unsigned __int16 **
0x1005372e  mov     dword ptr [esi+4], 0FFFFFAE7h
0x10053735  mov     dword ptr [esi+8], 0FFFFDF94h
0x1005373c  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x10053741  mov     dword ptr [esi+10h], 0
0x10053748  mov     ecx, [ebp+var_C]
0x1005374b  mov     large fs:0, ecx
0x10053752  pop     ecx
0x10053753  pop     edi
0x10053754  pop     esi
0x10053755  pop     ebx
0x10053756  mov     esp, ebp
0x10053758  pop     ebp
0x10053759  retn    0Ch
0x1005375c  mov     eax, [edi+30h]
0x1005375f  test    eax, eax
0x10053761  jnz     short loc_100537B2
0x10053763  cmp     esi, 3
0x10053766  jz      short loc_10053772
0x10053768  cmp     esi, 4
0x1005376b  jz      short loc_10053772
0x1005376d  cmp     esi, 1
0x10053770  jnz     short loc_100537B2
0x10053772  mov     ebx, [ebp+arg_8]
0x10053775  mov     ecx, [edi+24h]
0x10053778  push    0
0x1005377a  push    ebx
0x1005377b  push    esi
0x1005377c  push    dword ptr [edi+28h]
0x1005377f  call    ?LockTable@Database@@QAEXKW4TblLck@@AAVErr@@W4DBROLock@@@Z; Database::LockTable(ulong,TblLck,Err &,DBROLock)
0x10053784  test    byte ptr [ebx], 8
0x10053787  mov     ecx, edi; this
0x10053789  push    ebx; struct Err *
0x1005378a  jz      short loc_100537A7
0x1005378c  push    0; unsigned __int16 *
0x1005378e  call    ?ReportLockConflict@Table@@AAEXPBGAAVErr@@@Z; Table::ReportLockConflict(ushort const *,Err &)
0x10053793  mov     ecx, [ebp+var_C]
0x10053796  mov     large fs:0, ecx
0x1005379d  pop     ecx
0x1005379e  pop     edi
0x1005379f  pop     esi
0x100537a0  pop     ebx
0x100537a1  mov     esp, ebp
0x100537a3  pop     ebp
0x100537a4  retn    0Ch
0x100537a7  mov     [edi+30h], esi
0x100537aa  mov     [edi+2Ch], esi
0x100537ad  jmp     loc_1005392E
0x100537b2  mov     edx, [edi+7Ch]
0x100537b5  xor     ecx, ecx
0x100537b7  test    edx, edx
0x100537b9  jz      short loc_100537D0
0x100537bb  mov     ebx, [edi+74h]
0x100537be  mov     edi, edi
0x100537c0  mov     eax, [ebp+arg_0]
0x100537c3  cmp     [ebx+ecx*4], eax
0x100537c6  mov     eax, [edi+30h]
0x100537c9  jz      short loc_100537D8
0x100537cb  inc     ecx
0x100537cc  cmp     ecx, edx
0x100537ce  jb      short loc_100537C0
0x100537d0  cmp     ecx, edx
0x100537d2  jz      loc_100538BA
0x100537d8  test    esi, esi
0x100537da  jz      short loc_100537F0
0x100537dc  cmp     esi, 1
0x100537df  jz      short loc_100537F0
0x100537e1  cmp     esi, 2
0x100537e4  jz      short loc_100537F0
0x100537e6  cmp     esi, 3
0x100537e9  jz      short loc_100537F0
0x100537eb  cmp     esi, 4
0x100537ee  jnz     short loc_10053812
0x100537f0  cmp     dword ptr [edi+4Ch], 0
0x100537f4  jnz     loc_10053888
0x100537fa  test    eax, eax
0x100537fc  jz      short loc_10053834
0x100537fe  cmp     eax, 1
0x10053801  jz      short loc_10053834
0x10053803  cmp     eax, 2
0x10053806  jz      short loc_10053834
0x10053808  cmp     eax, 3
0x1005380b  jz      short loc_10053834
0x1005380d  cmp     eax, 4
0x10053810  jz      short loc_10053834
0x10053812  push    ecx
0x10053813  mov     ecx, [ebp+arg_8]
0x10053816  push    0FFFFFC15h
0x1005381b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10053820  mov     ecx, [ebp+var_C]
0x10053823  mov     large fs:0, ecx
0x1005382a  pop     ecx
0x1005382b  pop     edi
0x1005382c  pop     esi
0x1005382d  pop     ebx
0x1005382e  mov     esp, ebp
0x10053830  pop     ebp
0x10053831  retn    0Ch
0x10053834  lea     ecx, [esi+esi*4]
0x10053837  add     eax, ecx
0x10053839  mov     eax, ds:dword_100071D8[eax*4]
0x10053840  test    eax, eax
0x10053842  jz      short loc_10053865
0x10053844  push    [ebp+arg_8]; struct Err *
0x10053847  mov     ecx, edi; this
0x10053849  push    0; unsigned __int16 *
0x1005384b  push    eax; int
0x1005384c  call    ?ReportLockConflict@Table@@AAEXJPBGAAVErr@@@Z; Table::ReportLockConflict(long,ushort const *,Err &)
0x10053851  mov     ecx, [ebp+var_C]
0x10053854  mov     large fs:0, ecx
0x1005385b  pop     ecx
0x1005385c  pop     edi
0x1005385d  pop     esi
0x1005385e  pop     ebx
0x1005385f  mov     esp, ebp
0x10053861  pop     ebp
0x10053862  retn    0Ch
0x10053865  mov     eax, [edi+2Ch]
0x10053868  add     eax, ecx
0x1005386a  mov     eax, ds:dword_100072A8[eax*4]
0x10053871  mov     [edi+2Ch], eax
0x10053874  mov     ecx, [ebp+var_C]
0x10053877  mov     large fs:0, ecx
0x1005387e  pop     ecx
0x1005387f  pop     edi
0x10053880  pop     esi
0x10053881  pop     ebx
0x10053882  mov     esp, ebp
0x10053884  pop     ebp
0x10053885  retn    0Ch
0x10053888  lea     eax, [esi+esi*4]
0x1005388b  add     eax, [edi+2Ch]
0x1005388e  mov     ecx, ds:dword_10007240[eax*4]
0x10053895  test    ecx, ecx
0x10053897  jz      short loc_1005386A
0x10053899  push    [ebp+arg_8]; struct Err *
0x1005389c  push    0; unsigned __int16 *
0x1005389e  push    ecx; int
0x1005389f  mov     ecx, edi; this
0x100538a1  call    ?ReportLockConflict@Table@@AAEXJPBGAAVErr@@@Z; Table::ReportLockConflict(long,ushort const *,Err &)
0x100538a6  mov     ecx, [ebp+var_C]
0x100538a9  mov     large fs:0, ecx
0x100538b0  pop     ecx
0x100538b1  pop     edi
0x100538b2  pop     esi
0x100538b3  pop     ebx
0x100538b4  mov     esp, ebp
0x100538b6  pop     ebp
0x100538b7  retn    0Ch
0x100538ba  mov     ebx, [ebp+arg_8]
0x100538bd  test    esi, esi
0x100538bf  jz      short loc_100538E4
0x100538c1  cmp     esi, 1
0x100538c4  jz      short loc_100538E4
0x100538c6  cmp     esi, 2
0x100538c9  jz      short loc_100538E4
0x100538cb  cmp     esi, 3
0x100538ce  jz      short loc_100538E4
0x100538d0  cmp     esi, 4
0x100538d3  jz      short loc_100538E4
0x100538d5  push    ecx
0x100538d6  push    0FFFFFC15h
0x100538db  mov     ecx, ebx
0x100538dd  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100538e2  jmp     short loc_10053926
0x100538e4  test    eax, eax
0x100538e6  jz      short loc_1005390B
0x100538e8  cmp     eax, 1
0x100538eb  jz      short loc_1005390B
0x100538ed  cmp     eax, 2
0x100538f0  jz      short loc_1005390B
0x100538f2  cmp     eax, 3
0x100538f5  jz      short loc_1005390B
0x100538f7  cmp     eax, 4
0x100538fa  jz      short loc_1005390B
0x100538fc  push    ecx
0x100538fd  push    0FFFFFC15h
0x10053902  mov     ecx, ebx
0x10053904  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10053909  jmp     short loc_10053926
0x1005390b  lea     eax, [eax+esi*4]
0x1005390e  add     eax, esi
0x10053910  mov     eax, ds:dword_10007240[eax*4]
0x10053917  test    eax, eax
0x10053919  jz      short loc_10053926
0x1005391b  push    ebx; struct Err *
0x1005391c  push    0; unsigned __int16 *
0x1005391e  push    eax; int
0x1005391f  mov     ecx, edi; this
0x10053921  call    ?ReportLockConflict@Table@@AAEXJPBGAAVErr@@@Z; Table::ReportLockConflict(long,ushort const *,Err &)
0x10053926  test    byte ptr [ebx], 8
0x10053929  jnz     short loc_10053936
0x1005392b  push    ebx; struct Err *
0x1005392c  mov     ecx, edi; this
0x1005392e  push    [ebp+arg_0]; struct Session *
0x10053931  call    ?AddSession@Table@@QAEXPAVSession@@AAVErr@@@Z; Table::AddSession(Session *,Err &)
0x10053936  mov     ecx, [ebp+var_C]
0x10053939  mov     large fs:0, ecx
0x10053940  pop     ecx
0x10053941  pop     edi
0x10053942  pop     esi
0x10053943  pop     ebx
0x10053944  mov     esp, ebp
0x10053946  pop     ebp
0x10053947  retn    0Ch
0x10060f20  lea     ecx, [ebp+var_20]; this
0x10060f23  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060f2d  nop
0x10060f2e  nop
0x10060f2f  mov     edx, [esp-4+arg_4]
0x10060f33  lea     eax, [edx+0Ch]
0x10060f36  mov     ecx, [edx-28h]
0x10060f39  xor     ecx, eax; StackCookie
0x10060f3b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060f40  mov     eax, offset stru_10063AF8
0x10060f45  jmp     ___CxxFrameHandler3
```
