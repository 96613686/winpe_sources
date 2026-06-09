# Session::OpenDatabase(ushort const *,ushort const *,DBOpenFreq,DBIntent,DBShare,Err &)

- ea: `0x10044630`
- end: `0x1004484b`
- name: `?OpenDatabase@Session@@QAEPAVInstance@@PBG0W4DBOpenFreq@@W4DBIntent@@W4DBShare@@AAVErr@@@Z`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x10027d60`

## callees

- `0x1000eb60`
- `0x1001f350`
- `0x1001f440`
- `0x10020080`
- `0x10025ee0`
- `0x10026060`
- `0x1002e9d0`
- `0x10035910`
- `0x10035e10`
- `0x10044630`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10044785`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10044785`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1004471a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1004471a`

## pseudocode

```c
struct Session *__thiscall Session::OpenDatabase(
        int this,
        const unsigned __int16 *cchDest,
        int a3,
        int a4,
        int a5,
        int a6,
        Err *a7)
{
  int v7; // ebx
  struct Database *v8; // esi
  unsigned int i; // edi
  Database *v10; // eax
  int v11; // ecx
  Database *v12; // ebx
  size_t *v13; // ebx
  unsigned int v14; // kr00_4
  size_t *v15; // eax
  int v16; // ecx
  const WCHAR *v18; // eax
  int v19; // eax
  Instance *v20; // eax
  int v21; // ecx
  struct Session *v22; // edi
  Database *Block; // [esp+10h] [ebp-18h]
  Instance *Blocka; // [esp+10h] [ebp-18h]
  struct Session *v26; // [esp+14h] [ebp-14h]
  int v27; // [esp+18h] [ebp-10h]

  v7 = *(_DWORD *)(this + 48);
  v8 = 0;
  for ( i = 0; i < *(_DWORD *)(v7 + 20); v8 = 0 )
  {
    v8 = *(struct Database **)(*(_DWORD *)(v7 + 12) + 4 * i);
    if ( File::IsSameFilename((char *)v8 + 4, cchDest) && (*((_DWORD *)v8 + 26) == a5 || !a5) )
      break;
    ++i;
  }
  if ( v8 )
  {
    if ( a4 == 1 || *((_DWORD *)v8 + 24) == 1 )
    {
      Err::SetError(a7, -1202, this);
    }
    else
    {
      v19 = *((_DWORD *)v8 + 17);
      if ( v19 == 3 || v19 == 4 )
        Err::SetWarning(a7, 1208);
    }
    v12 = 0;
  }
  else
  {
    Block = (Database *)operator new(0x3CCu);
    v10 = Database::Database(Block, *(struct Connection **)(this + 48), a7);
    v12 = v10;
    v27 = (int)v10;
    if ( (*(_BYTE *)a7 & 8) != 0 )
      goto LABEL_36;
    if ( v10 )
    {
      v13 = 0;
      if ( cchDest )
      {
        v14 = wcslen(cchDest);
        v15 = (size_t *)_malloc(2 * (v14 + 1));
        v13 = v15;
        if ( !v15 )
        {
          Err::SetError(a7, -1011, v16);
          return 0;
        }
        WCSCPY2(v15, (size_t)cchDest, v14 + 1);
      }
      v18 = 0;
      v8 = (struct Database *)v27;
      if ( cchDest )
        v18 = (const WCHAR *)v13;
      Database::OpenFile(v27, v18, a3, (const unsigned __int16 *)(this + 156), a4, a5, a6, a7);
      if ( v13 )
        _free(v13);
      v12 = (Database *)v27;
    }
    else
    {
      Err::SetError(a7, -1011, v11);
    }
  }
  if ( (*(_BYTE *)a7 & 8) != 0 )
    goto LABEL_36;
  Blocka = (Instance *)operator new(0x4Cu);
  v20 = Instance::Instance(Blocka, (struct Session *)this, v8, a7);
  v26 = v20;
  if ( v20 )
  {
    if ( (*(_BYTE *)a7 & 8) == 0 )
      goto LABEL_29;
    Instance::Release(v20);
LABEL_36:
    v22 = 0;
    goto LABEL_30;
  }
  Err::SetError(a7, -1011, v21);
LABEL_29:
  v22 = v26;
LABEL_30:
  if ( v12 )
  {
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)v12 + 18, 0xFFFFFFFF) )
      (**(void (__thiscall ***)(Database *, int))v12)(v12, 1);
  }
  return v22;
}

```

## disassembly

```asm
0x10044630  mov     edi, edi
0x10044632  push    ebp
0x10044633  mov     ebp, esp
0x10044635  push    0FFFFFFFFh
0x10044637  push    offset ?OpenDatabase@Session@@QAEPAVInstance@@PBG0W4DBOpenFreq@@W4DBIntent@@W4DBShare@@AAVErr@@@Z_SEH
0x1004463c  mov     eax, large fs:0
0x10044642  push    eax
0x10044643  sub     esp, 0Ch
0x10044646  push    ebx
0x10044647  push    esi
0x10044648  push    edi
0x10044649  mov     eax, ___security_cookie
0x1004464e  xor     eax, ebp
0x10044650  push    eax; unsigned int
0x10044651  lea     eax, [ebp+var_C]
0x10044654  mov     large fs:0, eax
0x1004465a  mov     eax, ecx
0x1004465c  mov     [ebp+var_14], eax
0x1004465f  mov     ebx, [eax+30h]
0x10044662  xor     esi, esi
0x10044664  xor     edi, edi
0x10044666  cmp     [ebx+14h], esi
0x10044669  jbe     short loc_10044699
0x1004466b  nop     dword ptr [eax+eax+00h]
0x10044670  mov     eax, [ebx+0Ch]
0x10044673  push    [ebp+cchDest]
0x10044676  mov     esi, [eax+edi*4]
0x10044679  lea     ecx, [esi+4]
0x1004467c  call    ?IsSameFilename@File@@QAE?AW4FileBoolean@@PBG@Z; File::IsSameFilename(ushort const *)
0x10044681  test    eax, eax
0x10044683  jz      short loc_10044691
0x10044685  mov     eax, [ebp+arg_C]
0x10044688  cmp     [esi+68h], eax
0x1004468b  jz      short loc_10044699
0x1004468d  test    eax, eax
0x1004468f  jz      short loc_10044699
0x10044691  inc     edi
0x10044692  xor     esi, esi
0x10044694  cmp     edi, [ebx+14h]
0x10044697  jb      short loc_10044670
0x10044699  mov     edi, [ebp+arg_14]
0x1004469c  test    esi, esi
0x1004469e  jnz     loc_10044793
0x100446a4  push    3CCh; Size
0x100446a9  call    ??2@YAPAXI@Z; operator new(uint)
0x100446ae  add     esp, 4
0x100446b1  mov     [ebp+Block], eax
0x100446b4  mov     ecx, [ebp+var_14]
0x100446b7  push    edi; struct Err *
0x100446b8  mov     [ebp+var_4], 0
0x100446bf  push    dword ptr [ecx+30h]; struct Connection *
0x100446c2  mov     ecx, eax; this
0x100446c4  call    ??0Database@@QAE@PAVConnection@@AAVErr@@@Z; Database::Database(Connection *,Err &)
0x100446c9  mov     ebx, eax
0x100446cb  mov     [ebp+var_4], 0FFFFFFFFh
0x100446d2  test    byte ptr [edi], 8
0x100446d5  mov     [ebp+var_10], ebx
0x100446d8  jnz     loc_10044847
0x100446de  test    ebx, ebx
0x100446e0  jnz     short loc_100446F4
0x100446e2  push    ecx
0x100446e3  push    0FFFFFC0Dh
0x100446e8  mov     ecx, edi
0x100446ea  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100446ef  jmp     loc_100447C9
0x100446f4  mov     esi, [ebp+cchDest]
0x100446f7  xor     ebx, ebx
0x100446f9  test    esi, esi
0x100446fb  jz      short loc_10044758
0x100446fd  mov     ecx, esi
0x100446ff  lea     edx, [ecx+2]
0x10044702  mov     ax, [ecx]
0x10044705  add     ecx, 2
0x10044708  test    ax, ax
0x1004470b  jnz     short loc_10044702
0x1004470d  sub     ecx, edx
0x1004470f  sar     ecx, 1
0x10044711  lea     eax, [ecx+1]
0x10044714  mov     [ebp+Block], eax
0x10044717  add     eax, eax
0x10044719  push    eax; Size
0x1004471a  call    ds:__imp__malloc
0x10044720  mov     ebx, eax
0x10044722  add     esp, 4
0x10044725  test    ebx, ebx
0x10044727  jnz     short loc_1004474C
0x10044729  push    ecx
0x1004472a  push    0FFFFFC0Dh
0x1004472f  mov     ecx, edi
0x10044731  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10044736  xor     eax, eax
0x10044738  mov     ecx, [ebp+var_C]
0x1004473b  mov     large fs:0, ecx
0x10044742  pop     ecx
0x10044743  pop     edi
0x10044744  pop     esi
0x10044745  pop     ebx
0x10044746  mov     esp, ebp
0x10044748  pop     ebp
0x10044749  retn    18h
0x1004474c  push    [ebp+Block]; int
0x1004474f  mov     edx, esi; cchDest
0x10044751  mov     ecx, ebx; pcchNewDestLength
0x10044753  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10044758  mov     eax, [ebp+var_14]
0x1004475b  push    edi
0x1004475c  push    [ebp+arg_10]
0x1004475f  add     eax, 9Ch
0x10044764  push    [ebp+arg_C]
0x10044767  push    [ebp+arg_8]
0x1004476a  push    eax
0x1004476b  push    [ebp+arg_4]
0x1004476e  xor     eax, eax
0x10044770  test    esi, esi
0x10044772  mov     esi, [ebp+var_10]
0x10044775  mov     ecx, esi
0x10044777  cmovnz  eax, ebx
0x1004477a  push    eax
0x1004477b  call    ?OpenFile@Database@@QAEXPBG00W4DBOpenFreq@@W4DBIntent@@W4DBShare@@AAVErr@@@Z; Database::OpenFile(ushort const *,ushort const *,ushort const *,DBOpenFreq,DBIntent,DBShare,Err &)
0x10044780  test    ebx, ebx
0x10044782  jz      short loc_1004478E
0x10044784  push    ebx; Block
0x10044785  call    ds:__imp__free
0x1004478b  add     esp, 4
0x1004478e  mov     ebx, [ebp+var_10]
0x10044791  jmp     short loc_100447C9
0x10044793  cmp     [ebp+arg_8], 1
0x10044797  jz      short loc_100447BA
0x10044799  cmp     dword ptr [esi+60h], 1
0x1004479d  jz      short loc_100447BA
0x1004479f  mov     eax, [esi+44h]
0x100447a2  cmp     eax, 3
0x100447a5  jz      short loc_100447AC
0x100447a7  cmp     eax, 4
0x100447aa  jnz     short loc_100447C7
0x100447ac  push    4B8h; int
0x100447b1  mov     ecx, edi; this
0x100447b3  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x100447b8  jmp     short loc_100447C7
0x100447ba  push    ecx
0x100447bb  push    0FFFFFB4Eh
0x100447c0  mov     ecx, edi
0x100447c2  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100447c7  xor     ebx, ebx
0x100447c9  test    byte ptr [edi], 8
0x100447cc  jnz     short loc_10044847
0x100447ce  push    4Ch ; 'L'; Size
0x100447d0  call    ??2@YAPAXI@Z; operator new(uint)
0x100447d5  add     esp, 4
0x100447d8  mov     [ebp+Block], eax
0x100447db  push    edi; struct Err *
0x100447dc  push    esi; struct Database *
0x100447dd  push    [ebp+var_14]; struct Session *
0x100447e0  mov     ecx, eax; this
0x100447e2  mov     [ebp+var_4], 1
0x100447e9  call    ??0Instance@@QAE@PAVSession@@PAVDatabase@@AAVErr@@@Z; Instance::Instance(Session *,Database *,Err &)
0x100447ee  mov     [ebp+var_14], eax
0x100447f1  test    eax, eax
0x100447f3  jnz     short loc_1004483B
0x100447f5  push    ecx
0x100447f6  push    0FFFFFC0Dh
0x100447fb  mov     ecx, edi
0x100447fd  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10044802  mov     edi, [ebp+var_14]
0x10044805  test    ebx, ebx
0x10044807  jz      short loc_10044825
0x10044809  or      eax, 0FFFFFFFFh
0x1004480c  lock xadd [ebx+48h], eax
0x10044811  jnz     short loc_10044825
0x10044813  mov     edx, [ebx]
0x10044815  push    1; void *
0x10044817  mov     esi, [edx]
0x10044819  mov     ecx, esi
0x1004481b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10044821  mov     ecx, ebx
0x10044823  call    esi
0x10044825  mov     eax, edi
0x10044827  mov     ecx, [ebp+var_C]
0x1004482a  mov     large fs:0, ecx
0x10044831  pop     ecx
0x10044832  pop     edi
0x10044833  pop     esi
0x10044834  pop     ebx
0x10044835  mov     esp, ebp
0x10044837  pop     ebp
0x10044838  retn    18h
0x1004483b  test    byte ptr [edi], 8
0x1004483e  jz      short loc_10044802
0x10044840  mov     ecx, eax; this
0x10044842  call    ?Release@Instance@@QAEXXZ; Instance::Release(void)
0x10044847  xor     edi, edi
0x10044849  jmp     short loc_10044805
0x10061410  push    3CCh; unsigned int
0x10061415  mov     eax, [ebp+Block]
0x10061418  push    eax; Block
0x10061419  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006141e  add     esp, 8
0x10061421  retn
0x10061422  push    4Ch ; 'L'; unsigned int
0x10061424  mov     eax, [ebp+Block]
0x10061427  push    eax; Block
0x10061428  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006142d  add     esp, 8
0x10061430  retn
0x10061436  nop
0x10061437  nop
0x10061438  mov     edx, [esp-4+arg_4]
0x1006143c  lea     eax, [edx+0Ch]
0x1006143f  mov     ecx, [edx-1Ch]
0x10061442  xor     ecx, eax; StackCookie
0x10061444  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061449  mov     eax, offset stru_10063E8C
0x1006144e  jmp     ___CxxFrameHandler3
```
