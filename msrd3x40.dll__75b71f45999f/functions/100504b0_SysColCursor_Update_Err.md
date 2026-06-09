# SysColCursor::Update(Err &)

- ea: `0x100504b0`
- end: `0x1005061d`
- name: `?Update@SysColCursor@@UAEKAAVErr@@@Z`
- size: `365`
- prototype: `unsigned int __thiscall(SysColCursor *__hidden this, struct Err *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x10025ee0`
- `0x10043450`
- `0x100435f0`
- `0x100504b0`
- `0x10051890`
- `0x10057520`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
unsigned int __thiscall SysColCursor::Update(SysColCursor *this, void **a2)
{
  _DWORD *v3; // edi
  int v4; // ecx
  int v5; // edx
  struct Instance *v6; // eax
  int v7; // eax
  struct Err *v8; // ecx
  struct Instance *v10; // [esp+14h] [ebp-18h]
  int v11; // [esp+18h] [ebp-14h]
  int v12; // [esp+1Ch] [ebp-10h]

  if ( *((_DWORD *)this + 97) == 3 )
  {
    if ( (int)*a2 < 8 )
    {
      if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
      {
        if ( a2[3] )
          operator delete[](a2[3]);
        if ( a2[4] )
          operator delete[](a2[4]);
      }
      *a2 = (void *)8;
      a2[1] = (void *)-1609;
      a2[2] = 0;
      a2[3] = 0;
      a2[4] = 0;
    }
    goto LABEL_19;
  }
  v3 = (_DWORD *)*((_DWORD *)this + 94);
  v4 = *((__int16 *)this + 196);
  v5 = *((_DWORD *)this + 96);
  v6 = (struct Instance *)*((_DWORD *)this + 91);
  ++v3[85];
  v12 = v4;
  v11 = v5;
  v10 = v6;
  if ( v3[11] == 2 || v3[12] == 8 )
  {
    v7 = *(_DWORD *)(v3[9] + 104);
    if ( v7 && v7 != 3 )
      goto LABEL_16;
    Err::SetError(a2, -1809, v4);
  }
  else
  {
    Err::SetError(a2, -1309, v4);
  }
  v5 = v11;
  v4 = v12;
LABEL_16:
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    *(_DWORD *)(v3[v5 + 94] + 24) = v4;
    PresOrderList::Remove((PresOrderList *)(v3 + 90), *(_DWORD *)(v3[v5 + 94] + 12));
    PresOrderList::Insert((PresOrderList *)(v3 + 90), *(const unsigned __int16 **)(v3[v11 + 94] + 4), v11, v12, v8);
    Table::DDLPerformed((Table *)v3, v10);
  }
  --v3[85];
LABEL_19:
  *((_DWORD *)this + 97) = 3;
  return 0;
}

```

## disassembly

```asm
0x100504b0  mov     edi, edi
0x100504b2  push    ebp
0x100504b3  mov     ebp, esp
0x100504b5  push    0FFFFFFFFh
0x100504b7  push    offset ?Update@SysColCursor@@UAEKAAVErr@@@Z_SEH
0x100504bc  mov     eax, large fs:0
0x100504c2  push    eax
0x100504c3  sub     esp, 10h
0x100504c6  push    ebx
0x100504c7  push    esi
0x100504c8  push    edi
0x100504c9  mov     eax, ___security_cookie
0x100504ce  xor     eax, ebp
0x100504d0  push    eax
0x100504d1  lea     eax, [ebp+var_C]
0x100504d4  mov     large fs:0, eax
0x100504da  mov     ebx, ecx
0x100504dc  cmp     dword ptr [ebx+184h], 3
0x100504e3  jnz     short loc_10050541
0x100504e5  mov     esi, [ebp+arg_0]
0x100504e8  mov     eax, [esi]
0x100504ea  cmp     eax, 8
0x100504ed  jge     loc_100505FD
0x100504f3  test    eax, 0FFFFFFFEh
0x100504f8  jz      short loc_1005051A
0x100504fa  mov     eax, [esi+0Ch]
0x100504fd  test    eax, eax
0x100504ff  jz      short loc_1005050A
0x10050501  push    eax; Block
0x10050502  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050507  add     esp, 4
0x1005050a  mov     eax, [esi+10h]
0x1005050d  test    eax, eax
0x1005050f  jz      short loc_1005051A
0x10050511  push    eax; Block
0x10050512  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050517  add     esp, 4
0x1005051a  mov     dword ptr [esi], 8
0x10050520  mov     dword ptr [esi+4], 0FFFFF9B7h
0x10050527  mov     dword ptr [esi+8], 0
0x1005052e  mov     dword ptr [esi+0Ch], 0
0x10050535  mov     dword ptr [esi+10h], 0
0x1005053c  jmp     loc_100505FD
0x10050541  mov     edi, [ebx+178h]
0x10050547  movsx   ecx, word ptr [ebx+188h]
0x1005054e  mov     edx, [ebx+180h]
0x10050554  mov     eax, [ebx+16Ch]
0x1005055a  inc     dword ptr [edi+154h]
0x10050560  mov     [ebp+var_10], ecx
0x10050563  mov     [ebp+var_14], edx
0x10050566  mov     [ebp+var_18], eax
0x10050569  mov     [ebp+var_1C], edi
0x1005056c  mov     esi, [ebp+arg_0]
0x1005056f  mov     [ebp+var_4], 0
0x10050576  cmp     dword ptr [edi+2Ch], 2
0x1005057a  jz      short loc_1005058A
0x1005057c  cmp     dword ptr [edi+30h], 8
0x10050580  jz      short loc_1005058A
0x10050582  push    ecx
0x10050583  push    0FFFFFAE3h
0x10050588  jmp     short loc_1005059F
0x1005058a  mov     eax, [edi+24h]
0x1005058d  mov     eax, [eax+68h]
0x10050590  test    eax, eax
0x10050592  jz      short loc_10050599
0x10050594  cmp     eax, 3
0x10050597  jnz     short loc_100505AC
0x10050599  push    ecx
0x1005059a  push    0FFFFF8EFh
0x1005059f  mov     ecx, esi
0x100505a1  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100505a6  mov     edx, [ebp+var_14]
0x100505a9  mov     ecx, [ebp+var_10]
0x100505ac  test    byte ptr [esi], 8
0x100505af  jnz     short loc_100505F7
0x100505b1  mov     eax, [edi+edx*4+178h]
0x100505b8  mov     [eax+18h], ecx
0x100505bb  lea     ecx, [edi+168h]; this
0x100505c1  mov     eax, [edi+edx*4+178h]
0x100505c8  push    dword ptr [eax+0Ch]; int
0x100505cb  call    ?Remove@PresOrderList@@QAEHH@Z; PresOrderList::Remove(int)
0x100505d0  mov     eax, [ebp+var_14]
0x100505d3  push    ecx; struct Err *
0x100505d4  push    [ebp+var_10]; int
0x100505d7  lea     ecx, [edi+168h]; this
0x100505dd  push    eax; int
0x100505de  mov     eax, [edi+eax*4+178h]
0x100505e5  push    dword ptr [eax+4]; unsigned __int16 *
0x100505e8  call    ?Insert@PresOrderList@@QAEXPBGHHAAVErr@@@Z; PresOrderList::Insert(ushort const *,int,int,Err &)
0x100505ed  push    [ebp+var_18]; struct Instance *
0x100505f0  mov     ecx, edi; this
0x100505f2  call    ?DDLPerformed@Table@@AAEXPAVInstance@@@Z; Table::DDLPerformed(Instance *)
0x100505f7  dec     dword ptr [edi+154h]
0x100505fd  mov     dword ptr [ebx+184h], 3
0x10050607  xor     eax, eax
0x10050609  mov     ecx, [ebp+var_C]
0x1005060c  mov     large fs:0, ecx
0x10050613  pop     ecx
0x10050614  pop     edi
0x10050615  pop     esi
0x10050616  pop     ebx
0x10050617  mov     esp, ebp
0x10050619  pop     ebp
0x1005061a  retn    4
0x10061980  lea     ecx, [ebp+var_1C]; this
0x10061983  jmp     ??1TblSemaphore@@QAE@XZ; TblSemaphore::~TblSemaphore(void)
0x1006198d  nop
0x1006198e  nop
0x1006198f  mov     edx, [esp-4+arg_4]
0x10061993  lea     eax, [edx+0Ch]
0x10061996  mov     ecx, [edx-20h]
0x10061999  xor     ecx, eax; StackCookie
0x1006199b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100619a0  mov     eax, offset stru_10064274
0x100619a5  jmp     ___CxxFrameHandler3
```
