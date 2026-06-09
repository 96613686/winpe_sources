# ReferenceCursor::OpenOtherTable(Err &)

- ea: `0x10035650`
- end: `0x1003584c`
- name: `?OpenOtherTable@ReferenceCursor@@AAEXAAVErr@@@Z`
- size: `508`
- prototype: `void __thiscall(ReferenceCursor *__hidden this, struct Err *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100354d0`
- `0x10035550`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x10035650`
- `0x100518a0`
- `0x10051e80`
- `0x10052140`
- `0x10053400`
- `0x100536a0`
- `0x10054060`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`

## pseudocode

```c
void __thiscall ReferenceCursor::OpenOtherTable(ReferenceCursor *this, struct Err *a2)
{
  int v3; // ecx
  int v4; // eax
  int v5; // ecx
  Table *v6; // edx
  int *v7; // edi
  unsigned int *v8; // ecx
  struct Database **v9; // esi
  struct Database *v10; // eax
  struct Err *v11; // ebx
  int v12; // ecx
  unsigned int v13; // edx
  Table *v14; // eax
  void *v15; // esi
  int v16; // eax
  Table *Block; // [esp+10h] [ebp-24h]
  unsigned int v18; // [esp+14h] [ebp-20h]
  struct Session **v19; // [esp+1Ch] [ebp-18h]
  unsigned int *v21; // [esp+24h] [ebp-10h]

  v3 = (*(int (__thiscall **)(ReferenceCursor *))(*(_DWORD *)this + 60))(this);
  v4 = *((_DWORD *)this + 94);
  if ( v4 < 0 || v4 >= *(_DWORD *)(v3 + 24) || *(_DWORD *)(v3 + 4 * v4 + 1524) == -1 )
  {
    v5 = 0;
  }
  else
  {
    _mm_lfence();
    v5 = *(_DWORD *)(v3 + 4 * *(_DWORD *)(v3 + 4 * v4 + 1524) + 1396);
  }
  v6 = (Table *)*((_DWORD *)this + 96);
  v7 = (int *)((char *)this + 384);
  v8 = (unsigned int *)(v5 + 48);
  v21 = v8;
  if ( v6 )
  {
    if ( *((_DWORD *)v6 + 10) == *v8 )
      return;
    v19 = (struct Session **)*((_DWORD *)this + 1);
    v9 = v19;
    Table::Release(v6, (struct Instance *)v19);
    v8 = v21;
  }
  else
  {
    v9 = (struct Database **)*((_DWORD *)this + 1);
    v21 = v8;
    v19 = v9;
  }
  v10 = v9[4];
  v11 = a2;
  v18 = *v8;
  v12 = 0;
  v13 = *((_DWORD *)v10 + 14);
  if ( v13 )
  {
    while ( 1 )
    {
      v11 = a2;
      if ( *(_DWORD *)(*(_DWORD *)(4 * v12 + *((_DWORD *)v10 + 12)) + 40) == v18 )
        break;
      if ( ++v12 >= v13 )
        goto LABEL_13;
    }
    v16 = *(_DWORD *)(4 * v12 + *((_DWORD *)v9[4] + 12));
    *v7 = v16;
    if ( v16 )
    {
      if ( *(_DWORD *)(*v7 + 40) != *(_DWORD *)((*(int (__thiscall **)(ReferenceCursor *))(*(_DWORD *)this + 60))(this)
                                              + 40) )
        Table::CompatibleMode(*v7, v19[3], 1u, a2);
      goto LABEL_25;
    }
  }
  else
  {
LABEL_13:
    *v7 = 0;
  }
  Block = (Table *)operator new(0x778u);
  v14 = Table::Table(Block, v9[4], v11);
  *v7 = (int)v14;
  if ( !v14 )
    Err::SetError(v11, -1011, v7);
  if ( (*(_BYTE *)v11 & 8) != 0 || (Table::Open(*v7, v9, *v21, 1, v11), (*(_BYTE *)v11 & 8) != 0) )
  {
    v15 = (void *)*v7;
    if ( *v7 )
    {
      Table::~Table((Table *)*v7);
      operator delete(v15);
    }
  }
  else if ( *v7 )
  {
    Table::GetName((Table *)*v7, (struct Instance *)v9);
  }
LABEL_25:
  if ( (*(_BYTE *)v11 & 8) != 0 )
  {
    *v7 = 0;
  }
  else if ( *v7 )
  {
    ++*(_DWORD *)(*v7 + 76);
  }
}

```

## disassembly

```asm
0x10035650  mov     edi, edi
0x10035652  push    ebp
0x10035653  mov     ebp, esp
0x10035655  push    0FFFFFFFFh
0x10035657  push    offset ?OpenOtherTable@ReferenceCursor@@AAEXAAVErr@@@Z_SEH
0x1003565c  mov     eax, large fs:0
0x10035662  push    eax
0x10035663  sub     esp, 18h
0x10035666  push    ebx
0x10035667  push    esi
0x10035668  push    edi; unsigned int
0x10035669  mov     eax, ___security_cookie
0x1003566e  xor     eax, ebp
0x10035670  push    eax; void *
0x10035671  lea     eax, [ebp+var_C]
0x10035674  mov     large fs:0, eax
0x1003567a  mov     ebx, ecx
0x1003567c  mov     [ebp+var_14], ebx
0x1003567f  mov     eax, [ebx]
0x10035681  mov     esi, [eax+3Ch]
0x10035684  mov     ecx, esi
0x10035686  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003568c  mov     ecx, ebx
0x1003568e  call    esi
0x10035690  mov     ecx, eax
0x10035692  mov     eax, [ebx+178h]
0x10035698  test    eax, eax
0x1003569a  js      short loc_100356BE
0x1003569c  cmp     eax, [ecx+18h]
0x1003569f  jge     short loc_100356BE
0x100356a1  cmp     dword ptr [ecx+eax*4+5F4h], 0FFFFFFFFh
0x100356a9  jz      short loc_100356BE
0x100356ab  lfence
0x100356ae  mov     eax, [ecx+eax*4+5F4h]
0x100356b5  mov     ecx, [ecx+eax*4+574h]
0x100356bc  jmp     short loc_100356C0
0x100356be  xor     ecx, ecx
0x100356c0  mov     edx, [ebx+180h]
0x100356c6  lea     edi, [ebx+180h]
0x100356cc  add     ecx, 30h ; '0'
0x100356cf  mov     [ebp+var_10], ecx
0x100356d2  test    edx, edx
0x100356d4  jz      short loc_100356F4
0x100356d6  mov     eax, [edx+28h]
0x100356d9  cmp     eax, [ecx]
0x100356db  jz      loc_10035838
0x100356e1  mov     esi, [ebx+4]
0x100356e4  mov     ecx, edx; this
0x100356e6  push    esi; struct Instance *
0x100356e7  mov     [ebp+var_18], esi
0x100356ea  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x100356ef  mov     ecx, [ebp+var_10]
0x100356f2  jmp     short loc_100356FD
0x100356f4  mov     esi, [ebx+4]
0x100356f7  mov     [ebp+var_10], ecx
0x100356fa  mov     [ebp+var_18], esi
0x100356fd  mov     eax, [esi+10h]
0x10035700  mov     ecx, [ecx]
0x10035702  mov     ebx, [ebp+arg_0]
0x10035705  mov     [ebp+var_20], ecx
0x10035708  xor     ecx, ecx
0x1003570a  mov     edx, [eax+38h]
0x1003570d  test    edx, edx
0x1003570f  jz      short loc_10035744
0x10035711  mov     eax, [eax+30h]
0x10035714  mov     [ebp+var_1C], eax
0x10035717  nop     word ptr [eax+eax+00000000h]
0x10035720  mov     ebx, [ebp+var_1C]
0x10035723  lea     eax, ds:0[ecx*4]
0x1003572a  mov     [ebp+Block], eax
0x1003572d  mov     eax, [eax+ebx]
0x10035730  mov     ebx, [ebp+var_20]
0x10035733  cmp     [eax+28h], ebx
0x10035736  mov     ebx, [ebp+arg_0]
0x10035739  jz      loc_100357BF
0x1003573f  inc     ecx
0x10035740  cmp     ecx, edx
0x10035742  jb      short loc_10035720
0x10035744  mov     dword ptr [edi], 0
0x1003574a  push    778h; Size
0x1003574f  call    ??2@YAPAXI@Z; operator new(uint)
0x10035754  add     esp, 4
0x10035757  mov     [ebp+Block], eax
0x1003575a  push    ebx; struct Err *
0x1003575b  mov     [ebp+var_4], 0
0x10035762  mov     ecx, eax; this
0x10035764  push    dword ptr [esi+10h]; struct Database *
0x10035767  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x1003576c  mov     [ebp+var_4], 0FFFFFFFFh
0x10035773  mov     ecx, edi
0x10035775  mov     [ecx], eax
0x10035777  test    eax, eax
0x10035779  jnz     short loc_10035788
0x1003577b  push    ecx
0x1003577c  push    0FFFFFC0Dh
0x10035781  mov     ecx, ebx
0x10035783  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10035788  test    byte ptr [ebx], 8
0x1003578b  jnz     short loc_100357A2
0x1003578d  mov     eax, [ebp+var_10]
0x10035790  mov     ecx, [edi]
0x10035792  push    ebx
0x10035793  push    1
0x10035795  push    dword ptr [eax]
0x10035797  push    esi
0x10035798  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x1003579d  test    byte ptr [ebx], 8
0x100357a0  jz      short loc_10035804
0x100357a2  mov     esi, [edi]
0x100357a4  test    esi, esi
0x100357a6  jz      short loc_10035810
0x100357a8  mov     ecx, esi; this
0x100357aa  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x100357af  push    778h; unsigned int
0x100357b4  push    esi; Block
0x100357b5  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100357ba  add     esp, 8
0x100357bd  jmp     short loc_10035810
0x100357bf  mov     eax, [esi+10h]
0x100357c2  mov     ecx, [ebp+Block]
0x100357c5  mov     eax, [eax+30h]
0x100357c8  mov     eax, [ecx+eax]
0x100357cb  mov     [edi], eax
0x100357cd  test    eax, eax
0x100357cf  jz      loc_1003574A
0x100357d5  mov     eax, [ebp+var_14]
0x100357d8  mov     eax, [eax]
0x100357da  mov     esi, [eax+3Ch]
0x100357dd  mov     ecx, esi
0x100357df  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100357e5  mov     ecx, [ebp+var_14]
0x100357e8  call    esi
0x100357ea  mov     ecx, [edi]
0x100357ec  mov     edx, [ecx+28h]
0x100357ef  cmp     edx, [eax+28h]
0x100357f2  jz      short loc_10035810
0x100357f4  mov     eax, [ebp+var_18]
0x100357f7  push    ebx
0x100357f8  push    1
0x100357fa  push    dword ptr [eax+0Ch]
0x100357fd  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x10035802  jmp     short loc_10035810
0x10035804  mov     ecx, [edi]; this
0x10035806  test    ecx, ecx
0x10035808  jz      short loc_10035810
0x1003580a  push    esi; struct Instance *
0x1003580b  call    ?GetName@Table@@QAEPAGPAVInstance@@@Z; Table::GetName(Instance *)
0x10035810  test    byte ptr [ebx], 8
0x10035813  jz      short loc_1003582F
0x10035815  mov     dword ptr [edi], 0
0x1003581b  mov     ecx, [ebp+var_C]
0x1003581e  mov     large fs:0, ecx
0x10035825  pop     ecx
0x10035826  pop     edi
0x10035827  pop     esi
0x10035828  pop     ebx
0x10035829  mov     esp, ebp
0x1003582b  pop     ebp
0x1003582c  retn    4
0x1003582f  mov     eax, [edi]
0x10035831  test    eax, eax
0x10035833  jz      short loc_10035838
0x10035835  inc     dword ptr [eax+4Ch]
0x10035838  mov     ecx, [ebp+var_C]
0x1003583b  mov     large fs:0, ecx
0x10035842  pop     ecx
0x10035843  pop     edi
0x10035844  pop     esi
0x10035845  pop     ebx
0x10035846  mov     esp, ebp
0x10035848  pop     ebp
0x10035849  retn    4
0x10060a80  push    778h; unsigned int
0x10060a85  mov     eax, [ebp+Block]
0x10060a88  push    eax; Block
0x10060a89  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060a8e  add     esp, 8
0x10060a91  retn
0x10060a97  nop
0x10060a98  nop
0x10060a99  mov     edx, [esp-4+arg_4]
0x10060a9d  lea     eax, [edx+0Ch]
0x10060aa0  mov     ecx, [edx-28h]
0x10060aa3  xor     ecx, eax; StackCookie
0x10060aa5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060aaa  mov     eax, offset stru_100637F4
0x10060aaf  jmp     ___CxxFrameHandler3
```
